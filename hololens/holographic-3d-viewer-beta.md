---
title: 3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)
description: HoloLens (1. Nesil) üzerinde Beta 3B Görüntüleyici tarafından desteklene dosya ve özellik türlerini ve uygulamanın nasıl kullan ve sorun giderilenlerini açıklar.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036285"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)

3B Görüntüleyici Beta, 3D modelleri HoloLens (1. nesil) görüntülemenizi sağlar. Desteklenen .fbx *dosyalarını Microsoft Edge,* OneDrive ve diğer uygulamalardan açabilir ve görüntüebilirsiniz.

>[!NOTE]
>Bu makale, .fbx **dosyalarını destekleyen** ve yalnızca HoloLens 'de (1. nesil) kullanılabilen tam kapsamlı Unity 3B Görüntüleyici Beta uygulaması için geçerlidir. HoloLens [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) **2'de önceden** yüklenmiş 3B Görüntüleyici uygulaması, karma gerçeklik giriş bölmesinde özel .glb 3B modellerin açılmasını destekler (diğer ayrıntılar için bkz. Varlık gereksinimlerine genel bakış.

>[!IMPORTANT]
>3B Görüntüleyici Beta, Microsoft Store için HoloLens (1. nesil) sürümünde kullanılabilir durumda kalsa da, artık etkin geliştirme aşamasında değildir ve artık desteklemektedir.

3B Görüntüleyici Beta'da 3D modeli açma konusunda sorun varsa veya 3D modelinizin bazı özellikleri desteklenmiyorsa aşağıdaki Desteklenen içerik [belirtimleri'ne](#supported-content-specifications) bakın.

3D modelleri 3B Görüntüleyici Beta ile kullanmak üzere derlemek veya iyileştirmek için aşağıdaki [3D](#optimizing-3d-models-for-3d-viewer-beta) modelleri 3B Görüntüleyici Beta için iyileştirme.

İki farklı modelde 3D modeli açmanın iki HoloLens. Daha [fazla bilgi için aşağıdaki FBX HoloLens FBX](#viewing-fbx-files-on-hololens) dosyalarını görüntüleme.

Bu konuları okuduktan sonra sorun ediyorsanız aşağıdaki Sorun [giderme'ye](#troubleshooting) bakın.

## <a name="supported-content-specifications"></a>Desteklenen içerik belirtimleri

### <a name="file-format"></a>Dosya biçimi

- FBX biçimi
- En yüksek FBX sürümü 2015.1.0

### <a name="file-size"></a>Dosya boyutu

- En az 5 KB
- En fazla 500 MB

### <a name="geometry"></a>Geometri

- Yalnızca çokgen modeller. Alt bölüm yüzeyleri veya BESB'ler yok
- Sağ el ile koordinat sistemi
- Dönüştürme matrislerini yalıtma desteklenmiyor

### <a name="textures"></a>Dokular

- Doku eşlemeleri FBX dosyasına ekli olmalı
- Desteklenen görüntü biçimleri
  - JPEG ve PNG görüntüleri
  - BMP görüntüleri (24 bit RGB gerçek renk)
  - TGA görüntüleri (24 bit RGB ve 32 bit RGBQ gerçek renk)
- 2048x2048 en yüksek doku çözünürlüğü
- En fazla bir eşlemli harita, bir normal harita ve mesh başına bir yansıma küpü haritası
- Doku dokularında alfa kanalı, piksellerin %50'nin altına inerse atılır

### <a name="animation"></a>Animasyon

- Tek tek nesnelerde ölçeklendirme/döndürme/çeviri animasyonu
- Deri ile Cilde (sıkı) animasyon
  - Köşe başına en fazla 4 etki

### <a name="materials"></a>Malzemeler

- Lambert ve P lambda malzemeleri, ayarlanabilir parametrelerle birlikte de desteklendi
- Lambert için desteklenen malzeme özellikleri
  - Ana Doku (RGB + Alfa Testi)
  - Yayma Rengi (RGB)
  - Ortam Rengi (RGB)
- Piser için desteklenen malzeme özellikleri
  - Ana Doku (RGB + Alfa Testi)
  - Yayma Rengi (RGB)
  - Ortam Rengi (RGB)
  - Specular Color (RGB)
  - Hazır olma
  - Yansıtma
- Özel malzemeler desteklenmiyor
- Örgü başına en fazla bir malzeme
- En fazla bir malzeme katmanı
- Dosya başına en fazla 8 malzeme

### <a name="file-and-model-limitations"></a>Dosya ve model sınırlamaları

Dosya boyutunun yanı sıra beta sürümünde aynı anda açabilirsiniz modellerin, köşelerin ve meshes sayısının sabit 3B Görüntüleyici vardır:

- Model başına en fazla 500 MB dosya boyutu
- Köşeler: Tüm açık modellerde 600.000 birleşik
- Tireler: Tüm açık modellerde 1.600 birleşik
- Aynı anda en fazla 40 model açılır

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3B Görüntüleyici Beta için 3D modelleri iyileştirme

### <a name="special-considerations"></a>Dikkat edilmesi gereken özel noktalar

- Doku eşlemelerinde siyah malzemelerden veya siyah alanlardan kaçının. Hologramlar, bu nedenle HoloLens siyahı (ışık yokluğu) saydam olarak işler.
- Oluşturma aracınızı FBX'e aktarmadan önce, tüm geometrinin görünür ve açık olduğundan ve geometri içeren hiçbir katmanın kapalı veya şablona sahip olmadığını emin olun. Görünürlüğün kabul edilene bir şey olmadığını.
- Düğümler arasında çok büyük çeviri uzaklıklarından kaçının (örneğin, 100.000 birim). Bu, modelin taşınırken/ölçeklendirirken/döndürülürken hareket uzemesini sağlar.

### <a name="performance-optimization"></a>Performansı en iyi duruma getirme

en iyi sonuçları elde etmek için içerik yazma ve 3B Görüntüleyici beta HoloLens doğrulama sırasında performansı unutmayın. 3B Görüntüleyici Beta, içeriği gerçek zamanlı olarak işler ve performans, HoloLens özelliklerine tabi olur.  

3D modelde performansı etkileyen birçok değişken vardır. 3B Görüntüleyici 150.000'den fazla köşe veya 400'den fazla meshes varsa Beta yükte bir uyarı gösterir. Animasyonların diğer açık modellerin performansı üzerinde etkisi olabilir. Ayrıca, beta sürümünde aynı anda açabilirsiniz toplam sayı modelleri, köşeleri ve meshes için de sabit sınırlar 3B Görüntüleyici (bkz. [Dosya ve model sınırlamaları).](#file-and-model-limitations)  

Model karmaşıklığı nedeniyle 3D modeli iyi çalışmıyorsa şunları göz önünde bulundurarak:

- Çokgen sayısını azaltma
- Zorlu animasyonda yer alan yerlerin sayısını azaltma
- Kendi kendine kapanmayı önleme

Çift taraflı işleme, performans 3B Görüntüleyici varsayılan olarak kapalı olmasına rağmen Beta sürümünde de desteklenebildi. Bu, Ayrıntılar sayfasındaki **Çift Taraflı** düğme aracılığıyla **açık** olabilir. En iyi performans için içeriğinize çift taraflı işlemeye gerek yok.

### <a name="validating-your-3d-model"></a>3D modelinizi doğrulama

HoloLens'da Beta'3B Görüntüleyici açarak modelinizi HoloLens. Modelinizin  desteklenmeyen içerikle ilgili özelliklerini ve uyarılarını (varsa) görüntülemek için Ayrıntılar düğmesini seçin.

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Gerçek hayattaki boyutlara sahip 3B modelleri işleme

Varsayılan olarak, 3B Görüntüleyici Beta 3D modelleri kullanıcıya göre uygun boyutta ve konumda görüntüler. Ancak gerçek hayattan yaşam ölçümleriyle 3B modelin işlemesi önemli ise (örneğin, bir oda içindeki evlerin modellerini değerlendirirken), içerik oluşturucu dosyanın meta verilerinde bu modelin hem uygulama hem de kullanıcı tarafından yeniden boyutlandırmasını önlemek için bir bayrak ayarlamasını sağlar.

Modelin ölçeklendirimsini önlemek için sahnenin Microsoft_DisableScale adlı herhangi bir nesnesine boole özel özniteliği ekleyin ve true olarak ayarlayın. 3B Görüntüleyici Beta, FBX dosyasındaki FbxSystemUnit bilgilerini dikkate alar. Beta'3B Görüntüleyici ölçeği FBX birimi başına 1 ölçüm olarak ölçeklendirin.

## <a name="viewing-fbx-files-on-hololens"></a>FBX dosyalarını HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Dosyadan FBX Microsoft Edge

FBX dosyaları doğrudan bir web sitesinden, Microsoft Edge üzerinden HoloLens.

1. Bu Microsoft Edge, görüntülemek istediğiniz FBX dosyasını içeren web sayfasına gidin.
1. İndirilen dosyayı seçin.
1. İndirme işlemi tamamlandığında, dosyayı **Beta'da** açmak Microsoft Edge aç düğmesini 3B Görüntüleyici.

İndirilen dosyaya daha sonra dosyada İndirilenler kullanılarak erişilebilir ve Microsoft Edge. 3D modeli kaydetmek ve sürekli erişim sağlamak için dosyayı bilgisayarınıza indirin ve OneDrive kaydedin. Dosya daha sonra OneDrive uygulamasından HoloLens.

> [!NOTE]
> İndirilebilir FBX modellerine sahip bazı web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar. 3B Görüntüleyici Beta, ZIP dosyalarını doğrudan açamaz. Bunun yerine, FBX dosyasını ayıklamak için bilgisayarınızı kullanın ve dosyayı OneDrive kaydedin. Dosya daha sonra OneDrive uygulamasından HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Dosyadan FBX OneDrive

FBX dosyaları, OneDrive üzerinde OneDrive kullanılarak HoloLens. HoloLens'de OneDrive Microsoft Store uygulamasını kullanarak FBX dosyasını bilgisayarınıza yüklemiş OneDrive emin olun.

FBX OneDrive iki farklı şekilde HoloLens beta 3B Görüntüleyici FBX dosyaları açılabilir:

- OneDrive'HoloLens FBX dosyasını seçerek Beta'da 3B Görüntüleyici açın.
- Beta 3B Görüntüleyici'ı açın, araç çubuğunu göstermek için havadan dokunun ve Dosya **Aç'ı seçin.** OneDrive, bir FBX dosyası seçmenize olanak sağlar.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D modeli açtım bir uyarı görüyorum

3B Görüntüleyici Beta tarafından desteklenen özellikler içeren bir 3D modeli açmaya çalışırken veya model çok karmaşıksa ve performans etkilenebilirse bir uyarıyla karşınız olur. 3B Görüntüleyici Beta 3D modeli yüklemeye devam eder, ancak performans veya görsel uygunluk tehlikeye girebilir.

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Bir uyarı görüyorum ve 3D modeli yüklenemedi

3B Görüntüleyici Beta, karmaşıklık veya dosya boyutu nedeniyle bir 3B modeli yükleyenene veya FBX dosyası bozuk ya da geçersiz olduğunda bir hata iletisi alırsınız. Toplam model sayısı, köşe veya tire sayısı sınırına ulaştınız ve aynı anda açabilirsiniz.  

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve [Dosya ve model sınırlamaları.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>3D modelim yüklenmiyor ama beklendiği gibi görünmüyor

Beta sürümünde 3D modeliniz beklendiği gibi 3B Görüntüleyici görünmüyorsa, araç çubuğunu göstermek için havadan dokunun ve Ayrıntılar'ı **seçin.** 3B Görüntüleyici Beta tarafından 3B Görüntüleyici dosyanın yönleri uyarı olarak vurgulanır.

Gördüğünüz en yaygın sorun, eksik dokular olabilir çünkü bunlar FBX dosyasına ekli değildir. Bu durumda model beyaz görünür. Oluşturma aracınızı doku ekleme seçeneği seçiliyken FBX'e aktararak bu sorun oluşturma işlemiyle çözülebilirsiniz.

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>3D modelimi görüntülerken performans düşüşleri yaşanıyor

3D modeli yüklerken ve görüntülerken performans modelin karmaşıklığından, aynı anda açık olan model sayısından veya etkin animasyonlarla model sayısından etkilenebilir.

Daha fazla bilgi için bkz. Beta ve Dosya ve model [3B Görüntüleyici için 3D](#optimizing-3d-models-for-3d-viewer-beta) [modelleri iyileştirme.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Bir FBX dosyasını HoloLens beta sürümünde 3B Görüntüleyici

3B Görüntüleyici Beta, yüklenirken .fbx dosya uzantısıyla otomatik olarak ilişkilendirilır.

Bir FBX dosyası açmaya ve sizi Microsoft Store'a yönlendiren bir iletişim kutusu görmeye devam ediyorsanız, şu anda HoloLens'da .fbx dosya uzantısıyla ilişkilendirilmiş bir uygulamanız HoloLens.

3B Görüntüleyici Beta'nın yüklü olduğunu doğrulayın. Yüklü değilse, Microsoft Store'den HoloLens.

Beta 3B Görüntüleyici yüklüyse Beta'3B Görüntüleyici açın ve dosyayı yeniden açmayı deneyin. Sorun devam ederse Beta sürümünü kaldırıp 3B Görüntüleyici yükleyin. Bu, .fbx dosya uzantısını beta sürümüyle 3B Görüntüleyici eder.

FBX dosyası açılmaya çalışıldıktan sonra 3B Görüntüleyici Beta dışında bir uygulama açılırsa, bu uygulama büyük olasılıkla 3B Görüntüleyici Beta'dan sonra yüklenmiştir ve .fbx dosya uzantısıyla ilişkilendirmeyi ele almış olur. Beta'3B Görüntüleyici .fbx dosya uzantısıyla ilişkilendirilmeyi tercih ediyorsanız, Beta'3B Görüntüleyici yükleyin.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3B Görüntüleyici Beta'da Dosya Aç düğmesi uygulama başlatamıyor

Dosya **Aç düğmesi,** dosya seçici işleviyle ilişkili uygulamayı HoloLens. Yüklü OneDrive, Dosya **Aç düğmesinin** dosya açma OneDrive. Ancak, şu anda dosya seçici işleviyle ilişkilendirilmiş bir uygulama HoloLens, dosya seçici işlevine Microsoft Store.

Dosya **Aç düğmesi** OneDrive dışında bir uygulama başlatıyorsa, bu uygulama OneDrive yüklendikten ve dosya seçici işleviyle ilişkilendirmeyi ele aldı. Beta'OneDrive Dosya Aç düğmesini seçerek  başlatmayı tercih ediyorsanız, 3B Görüntüleyici'yi kaldırın ve OneDrive.

Dosya **Aç düğmesi** etkin durumda değilse, tek bir anda Beta sürümünde açabilirsiniz 3B Görüntüleyici sınırına ulaştınız. Beta'da 40 model 3B Görüntüleyici, ek modeller açabileceksiniz.

## <a name="additional-resources"></a>Ek kaynaklar

- [Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) - Yalnızca arşivleme amacıyla. Bu forum artık etkin değil.
- [Üçüncü taraf bildirimler](https://www.microsoft.com/{lang-locale}/legal/products)
