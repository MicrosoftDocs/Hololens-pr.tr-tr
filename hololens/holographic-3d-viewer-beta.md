---
title: HoloLens 'de 3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428334"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>HoloLens 'de 3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)

3B Görüntüleyici Beta, 3D modelleri HoloLens (1. nesil) görüntülemenizi sağlar. Desteklenen .fbx *dosyalarını Microsoft Edge,* OneDrive ve diğer uygulamalardan açabilir ve görüntüebilirsiniz.

>[!NOTE]
>Bu makale, .fbx **dosyalarını destekleyen** ve yalnızca HoloLens (1. nesil) olan tam kapsamlı Unity 3B Görüntüleyici Beta uygulaması için geçerlidir. HoloLens [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) **2'de önceden** yüklenmiş 3B Görüntüleyici uygulaması, karma gerçeklik ana bölmesinde özel .glb 3B modellerin açılmasını destekler (diğer ayrıntılar için bkz. Varlık gereksinimlerine genel bakış.

>[!IMPORTANT]
>3B Görüntüleyici Beta, HoloLens (1. nesil) için Microsoft Store sürümünde kullanılabilir durumda kalsa da, artık etkin geliştirme aşamasında değildir ve artık desteklemektedir.

3B Görüntüleyici Beta'da 3D modeli açma konusunda sorun varsa veya 3D modelinizin bazı özellikleri desteklenmiyorsa aşağıdaki Desteklenen içerik [belirtimleri'ne](#supported-content-specifications) bakın.

3D modelleri 3B Görüntüleyici Beta ile kullanmak üzere derlemek veya iyileştirmek için aşağıdaki [3D](#optimizing-3d-models-for-3d-viewer-beta) modelleri 3B Görüntüleyici Beta için iyileştirme.

İki farklı modelde 3D modeli açmanın iki HoloLens. Daha [fazla bilgi edinmek için aşağıdaki FBX HoloLens FBX](#viewing-fbx-files-on-hololens) dosyalarını görüntülemeye bakın.

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

Dosya boyutunun yanı sıra beta sürümünde aynı anda açabilirsiniz model, köşe ve tire sayısı için sabit 3B Görüntüleyici:

- Model başına en fazla 500 MB dosya boyutu
- Köşeler: Tüm açık modellerde 600.000 birleşik
- Tireler: Tüm açık modellerde 1.600 birleşik
- Aynı anda en fazla 40 model açılır

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3B Görüntüleyici Beta için 3D 3B Görüntüleyici iyileştirme

### <a name="special-considerations"></a>Dikkat edilmesi gereken özel noktalar

- Doku eşlemelerinde siyah malzemelerden veya siyah alanlardan kaçının. Hologramlar, bu nedenle HoloLens siyahı (ışık yokluğu) saydam olarak işler.
- Oluşturma aracınızı FBX'e aktarmadan önce, tüm geometrinin görünür ve açık olduğundan ve geometri içeren hiçbir katmanın kapalı veya şablona sahip olmadığını emin olun. Görünürlüğün kabul edilene bir şey olmadığını.
- Düğümler arasında çok büyük çeviri uzaklıklarından kaçının (örneğin, 100.000 birim). Bu, modelin taşınırken/ölçeklendirirken/döndürülürken hareket uzemesini sağlar.

### <a name="performance-optimization"></a>Performansı en iyi duruma getirme

İçerik yazma ve en iyi sonuçları elde etmek için 3B Görüntüleyici beta HoloLens doğrulama sırasında performansı göz unutmayın. 3B Görüntüleyici Beta içeriği gerçek zamanlı olarak işler ve performans, HoloLens özelliklerine tabi olur.  

3D modelde performansı etkileyen birçok değişken vardır. 3B Görüntüleyici 150.000'den fazla köşe veya 400'den fazla meshes varsa Beta yükte bir uyarı gösterir. Animasyonların diğer açık modellerin performansı üzerinde etkisi olabilir. Ayrıca, Beta sürümünde aynı anda açabilirsiniz toplam sayı modelleri, köşeleri ve meshes için de sabit sınırlar 3B Görüntüleyici (bkz. [Dosya ve model sınırlamaları).](#file-and-model-limitations)  

Model karmaşıklığı nedeniyle 3D modeli iyi çalışmıyorsa şunları göz önünde bulundurarak:

- Çokgen sayısını azaltma
- Zorlu animasyonda yer alan yerlerin sayısını azaltma
- Kendi kendine kapanmayı önleme

Beta sürümünde çift taraflı işleme 3B Görüntüleyici, ancak performans nedeniyle varsayılan olarak kapalıdır. Bu, Ayrıntılar sayfasındaki **Çift Taraflı** düğme aracılığıyla **açık** olabilir. En iyi performans için içeriğinize çift taraflı işlemeye gerek yok.

### <a name="validating-your-3d-model"></a>3D modelinizi doğrulama

HoloLens'da Beta'3B Görüntüleyici açarak modelinizi HoloLens. Modelinizin  desteklenmeyen içerikle ilgili özelliklerini ve uyarılarını (varsa) görüntülemek için Ayrıntılar düğmesini seçin.

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Gerçek hayattaki boyutlara sahip 3B modelleri işleme

Varsayılan olarak, 3B Görüntüleyici Beta 3D modelleri kullanıcıya göre uygun boyutta ve konumda görüntüler. Ancak gerçek hayattan yaşam ölçümleriyle 3B modelin işlemesi önemli ise (örneğin, bir oda içindeki evlerin modellerini değerlendirirken), içerik oluşturucu dosyanın meta verilerinde bu modelin hem uygulama hem de kullanıcı tarafından yeniden boyutlandırmasını önlemek için bir bayrak ayarlamasını sağlar.

Modelin ölçeklendirmesini önlemek için sahnenin Microsoft_DisableScale adlı herhangi bir nesnesine boole özel özniteliği ekleyin ve true olarak ayarlayın. 3B Görüntüleyici Beta, FBX dosyasına ek olarak FbxSystemUnit bilgilerini dikkate alar. Beta'3B Görüntüleyici ölçeği FBX birimi başına 1 ölçüm olarak ölçeklendirin.

## <a name="viewing-fbx-files-on-hololens"></a>FBX dosyalarını HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Dosyadan FBX dosyası Microsoft Edge

FBX dosyaları doğrudan bir web sitesinden, Microsoft Edge üzerinden HoloLens.

1. Bu Microsoft Edge, görüntülemek istediğiniz FBX dosyasını içeren web sayfasına gidin.
1. İndirilen dosyayı seçin.
1. İndirme işlemi tamamlandığında, dosyayı **Beta'da** açmak Microsoft Edge aç düğmesini 3B Görüntüleyici.

İndirilen dosyaya daha sonra dosyada İndirilenler kullanılarak erişilebilir ve Microsoft Edge. 3D modeli kaydetmek ve sürekli erişim sağlamak için dosyayı bilgisayarınıza indirin ve OneDrive kaydedin. dosya daha sonra HoloLens OneDrive uygulamasından açılabilir.

> [!NOTE]
> İndirilebilir FBX modelleriyle bazı Web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar. 3B görüntüleyici Beta, ZIP dosyalarını doğrudan açamaz. bunun yerine, PC 'nizi kullanarak fbx dosyasını ayıklayın ve OneDrive hesabınıza kaydedin. dosya daha sonra HoloLens OneDrive uygulamasından açılabilir.

### <a name="open-an-fbx-file-from-onedrive"></a>OneDrive bir FBX dosyası açın

fbx dosyaları, HoloLens OneDrive uygulaması kullanılarak OneDrive açılabilir. HoloLens Microsoft Store uygulamasını kullanarak OneDrive yüklediğinizden ve fbx dosyasını bilgisayarınızda OneDrive için zaten karşıya yüklediğinizden emin olun.

OneDrive bir kez, fbx dosyaları 3b görüntüleyici Beta kullanılarak HoloLens iki şekilde açılabilir:

- HoloLens üzerinde OneDrive başlatın ve bunu 3b görüntüleyici Beta sürümünde açmak için fbx dosyasını seçin.
- 3B görüntüleyici Beta 'yı başlatın, AIR ' e dokunarak araç çubuğunu görüntüleyin ve **Dosya Aç**' ı seçin. OneDrive başlatılacak ve bir fbx dosyası seçmenize olanak sağlar.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3B model açtığımda bir uyarı görüyorum

3B görüntüleyici Beta tarafından desteklenmeyen özellikler içeren bir 3B modeli açmaya çalışırsanız veya model çok karmaşıksa ve performans etkileniyorsa bir uyarı görürsünüz. 3B görüntüleyici Beta, 3B modeli yüklemeye devam eder, ancak performans veya görsel uygunluk tehlikeye girebilir.

Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve 3B [Görüntüleyici Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Bir uyarı görüyorum ve 3B model yüklenmiyor

3B görüntüleyici Beta, karmaşıklık veya dosya boyutu nedeniyle veya FBX dosyası bozuksa veya geçersiz olduğunda bir 3B modeli Yükleyememesinin ardından bir hata mesajı görürsünüz. Ayrıca, aynı anda açabilme toplam model, köşe veya kafes sayısı sınırına ulaştıysanız bir hata iletisi görürsünüz.  

Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve [dosya ve model sınırlamaları](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>3B modelim yükleniyor, ancak beklendiği gibi görünmüyor

3B modeliniz, 3B görüntüleyici Beta 'da beklenildiği gibi görünmüyorsa, AIR ' e dokunarak araç çubuğunu görüntüleyin ve **Ayrıntılar**' ı seçin. Dosyanın 3B görüntüleyici Beta tarafından desteklenmeyen yönleri, uyarı olarak vurgulanır.

Büyük olasılıkla FBX dosyasına gömülü olmadıklarından, görebileceğiniz en yaygın sorunun dokuları eksik. Bu durumda, model beyaz görünür. Bu sorun, oluşturma aracınızdan, dokuları Ekle seçeneği belirlenmiş olarak FBX 'e dışarı aktararak oluşturma sürecinde çözülebilir.

Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve 3B [Görüntüleyici Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>3B modelmi görüntülerken Performans düşmem deneyimim

Bir 3B modeli yükleme ve görüntüleme performansı, modelin karmaşıklığına, eşzamanlı olarak açık olan model sayısına veya etkin animasyonlarla model sayısına göre etkilenebilir.

Daha fazla bilgi için bkz. 3B görüntüleyici Beta ve [dosya ve model sınırlamaları](#file-and-model-limitations) [Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta) .

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>HoloLens üzerinde bir fbx dosyası açtığımda, bu dosya 3b görüntüleyici Beta sürümünde açılmaz

3B görüntüleyici Beta, yüklendiğinde. FBX dosya uzantısıyla otomatik olarak ilişkilendirilir.

bir fbx dosyası açmaya çalışırsanız ve Microsoft Store yönlendiren bir iletişim kutusu görürseniz, şu anda HoloLens. fbx dosya uzantısıyla ilişkili bir uygulamanız yok.

3B görüntüleyici Beta 'nın yüklü olduğunu doğrulayın. yüklü değilse, HoloLens Microsoft Store adresinden indirin.

3B görüntüleyici beta sürümü zaten yüklüyse, 3B Görüntüleyicisi Beta 'yı başlatın ve sonra dosyayı açmayı yeniden deneyin. Sorun devam ederse, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin. Bu işlem,. FBX dosya uzantısını 3B görüntüleyici Beta ile yeniden ilişkilendirir.

Bir FBX dosyasını açmaya çalışmak, 3B görüntüleyici beta dışında bir uygulama açarsa, bu uygulama büyük olasılıkla 3B görüntüleyici beta sürümünden sonra yüklenmiş ve. FBX dosya uzantısıyla ilişkilendirmeyi gerçekleştirmiştir. 3B görüntüleyici Beta 'nın. FBX dosya uzantısıyla ilişkilendirilmesini tercih ediyorsanız, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3B görüntüleyici Beta 'daki Dosya Aç düğmesi bir uygulama başlatamaz

**Dosya Aç** düğmesi, Hololens dosya seçici işleviyle ilişkili uygulamayı açar. OneDrive yüklüyse, **dosya aç** düğmesi OneDrive başlatmalı. ancak, şu anda HoloLens dosya seçici işleviyle ilişkili bir uygulama yoksa, Microsoft Store yönlendirilirsiniz.

**dosya aç** düğmesi OneDrive dışında bir uygulama başlatırsa, bu uygulama büyük olasılıkla OneDrive sonra yüklenmiş ve dosya seçici işleviyle ilişkilendirmeyi gerçekleştirmiştir. 3b görüntüleyici Beta 'da **dosya aç** düğmesini seçerken OneDrive başlatmak isterseniz, OneDrive kaldırın ve yeniden yükleyin.

**Dosya Aç** düğmesi etkin değilse, 3B görüntüleyici Beta 'da tek seferde açık olabilecek modellerin sınırına ulaşmış olabilirsiniz. 3B görüntüleyici Beta 'da 40 modelleriniz varsa, ek modeller açabilmek için önce bazılarını kapatmanız gerekir.

## <a name="additional-resources"></a>Ek kaynaklar

- [Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) -yalnızca arşivleme amaçlıdır. Bu forum artık etkin değil.
- [Üçüncü taraf bildirimleri](https://www.microsoft.com/{lang-locale}/legal/products)
