---
title: HoloLens 'te 3B görüntüleyici Beta kullanma (1. Genel)
description: HoloLens (1. gen) üzerinde 3D görüntüleyicisinin desteklediği dosya ve özellik türlerini ve uygulamayı nasıl kullanacağınızı ve sorun giderebileceğinizi açıklar.
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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380178"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>HoloLens 'te 3B görüntüleyici Beta kullanma (1. Genel)

3B görüntüleyici Beta, HoloLens 'te 3B modelleri görüntülemenize olanak sağlar (1. Genel). *Desteklenen* . fbx dosyalarını Microsoft Edge, OneDrive ve diğer uygulamalardan açabilir ve görüntüleyebilirsiniz.

>[!NOTE]
>Bu makale,. fbx dosyalarını destekleyen ve yalnızca HoloLens (1. gen) üzerinde kullanılabilen, modern Unity **3B görüntüleyici Beta** uygulaması için geçerlidir. HoloLens 2 ' deki önceden yüklenmiş **3B görüntüleyici** uygulaması, karma gerçeklik ana bilgisayarında özel. GLB 3D modellerini açmayı destekler (daha fazla bilgi için [varlık gereksinimlerine genel bakış](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) bölümüne bakın.

>[!IMPORTANT]
>3B görüntüleyici Beta, HoloLens (1. gen) için Microsoft Store kullanılabilir kalacağından, artık etkin bir geliştirme aşamasındadır ve artık desteklenmemektedir.

3B görüntüleyici beta sürümünde bir 3B modeli açmada sorun yaşıyorsanız veya 3B modelinizin bazı özellikleri desteklenmiyorsa, aşağıdaki [desteklenen içerik belirtimleri](#supported-content-specifications) bölümüne bakın.

3B Viewer Beta ile kullanım için 3B modelleri derlemek veya iyileştirmek için bkz. aşağıdaki [3B Viewer Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta) .

HoloLens üzerinde 3B model açmak için iki yol vardır. Daha fazla bilgi için bkz. aşağıdaki [HoloLens 'TE FBX dosyalarını görüntüleme](#viewing-fbx-files-on-hololens) .

Bu konuları okuduktan sonra sorun yaşıyorsanız, aşağıdaki [sorun giderme](#troubleshooting) bölümüne bakın.

## <a name="supported-content-specifications"></a>Desteklenen içerik belirtimleri

### <a name="file-format"></a>Dosya biçimi

- FBX biçimi
- Maksimum FBX sürümü 2015.1.0

### <a name="file-size"></a>Dosya boyutu

- En az 5 KB
- Maksimum 500 MB

### <a name="geometry"></a>Geometri

- Yalnızca Çokgen modeller. Alt bölme yüzeyleri veya NURBs yok
- Sağ elli koordinat sistemi
- Dönüştürme matrislerini kırpma desteklenmiyor

### <a name="textures"></a>Dokular

- Doku haritaları FBX dosyasına katıştırılmalıdır
- Desteklenen görüntü biçimleri
  - JPEG ve PNG görüntüleri
  - BMP görüntüleri (24 bit RGB True-Color)
  - TGA görüntüleri (24 bit RGB ve 32-bit RGBQ gerçek renk)
- Maksimum dok48x2048 doku çözünürlüğü
- Her ağ için en fazla bir dağıtılmış harita, bir normal harita ve bir yansıma küpü Haritası
- Dağıtma dokularıyla alfa kanalı, %50 altındaysa piksellerin atılmasına neden olur

### <a name="animation"></a>Animasyon

- Ayrı nesnelerde ölçek/döndürme/çeviri animasyonu
- Kaplama ile iskelet (Rigged) animasyonu
  - Köşe başına en fazla 4 etkiler

### <a name="materials"></a>Malzemeler

- Lambda ve Phong malzemeleri, ayarlanabilir parametrelerle desteklenir
- Lambert için desteklenen malzeme özellikleri
  - Ana doku (RGB + Alfa testi)
  - Dağıtma rengi (RGB)
  - Çevresel renk (RGB)
- Phong için desteklenen malzeme özellikleri
  - Ana doku (RGB + Alfa testi)
  - Dağıtma rengi (RGB)
  - Çevresel renk (RGB)
  - Yansımalı renk (RGB)
  - Parlaklık
  - Reflectivity
- Özel malzemeler desteklenmez
- Her ağ için en fazla bir malzeme
- En fazla bir malzeme katmanı
- Dosya başına en fazla 8 malzeme

### <a name="file-and-model-limitations"></a>Dosya ve model sınırlamaları

3B görüntüleyici Beta 'da eşzamanlı olarak kullanılabilecek model, köşe ve kafeslerin sayısını ve dosya boyutunda sabit sınırlar vardır:

- model başına 500 MB en büyük dosya boyutu
- Köşeler: 600.000 tüm açık modellerde birleştirilmiş
- Kafesler: 1.600 tüm açık modellerde birleştirilmiş
- Tek seferde en fazla 40 Model açık

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>3B Görüntüleyicisi Beta için 3B modellerini iyileştirme

### <a name="special-considerations"></a>Özel Konular

- Doku haritalarının siyah malzemelerinden veya siyah alanlarından kaçının. Hologragram hafif yapılır, bu nedenle HoloLens, saydam olarak siyah (ışık yokluğu) oluşturur.
- Oluşturma aracınızdan FBX 'e vermeden önce tüm geometrinin göründüğünden ve kilidinin açık olduğundan ve geometri içeren katmanların kapalı veya şablonlu olduğundan emin olun. Görünürlük dikkate alınmıyor.
- Düğümler arasında çok büyük çeviri uzaklıklarını önleyin (örneğin, 100.000 birim). Bu, modelin taşınmakta/ölçeklendirildiğinde/döndürüldüğünde değişmesine neden olabilir.

### <a name="performance-optimization"></a>Performansı en iyi duruma getirme

En iyi sonuçlar için yazma işlemi sırasında HoloLens 'teki 3B görüntüleyici Beta uygulamasında içerik yazarken ve doğrulama yaparken performansı göz önünde bulundurun. 3B görüntüleyici Beta, içeriğin gerçek zamanlı ve performansa göre HoloLens donanım özelliklerine tabidir.  

3B modelde performansı etkileyebilecek birçok değişken vardır. 150.000 ' den fazla köşe veya 400 ' den fazla yer varsa 3B görüntüleyici Beta, yükleme sırasında bir uyarı gösterir. Animasyonların diğer açık modellerin performansına etkisi olabilir. Ayrıca, 3B görüntüleyici Beta 'da eşzamanlı olarak açabilme toplam sayı modelleri, köşeleri ve kafeslerde de sabit sınırlar vardır (bkz. [dosya ve model sınırlamaları](#file-and-model-limitations)).  

Model karmaşıklığı nedeniyle 3B model iyi çalışmıyorsa şunları göz önünde bulundurun:

- Çokgen sayısını azaltma
- Rigged animasyonunda kemik sayısını azaltma
- Kendinden occlusiyon

Çift taraflı işleme, 3B görüntüleyici beta sürümünde desteklenir, ancak performans nedenleriyle varsayılan olarak devre dışıdır. Bu, **Ayrıntılar** sayfasındaki **çift taraflı** düğme aracılığıyla açılabilir. En iyi performansı elde etmek için içeriğinizdeki çift taraflı işleme gereksinimini önleyin.

### <a name="validating-your-3d-model"></a>3B modeliniz doğrulanıyor

HoloLens üzerinde 3B görüntüleyici Beta 'da açarak modelinizi doğrulayın. Modelinizin özelliklerini ve desteklenmeyen içerik (varsa) uyarılarını görüntülemek için **Ayrıntılar** düğmesini seçin.

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Gerçek-ömür boyutları ile 3B modeller işleme

Varsayılan olarak, 3B görüntüleyici Beta, 3B modellerini kullanıcıya göre rahat bir boyutta ve konumda görüntüler. Ancak, gerçek-yaşam ölçümlerine sahip bir 3B modelin işlenmesi önemliyse (örneğin, bir odada mobilya modellerini değerlendirirken), içerik Oluşturucu bu modelin hem uygulama hem de Kullanıcı tarafından yeniden boyutlandırılmasına engel olmak için dosyanın meta verileri içinde bir bayrak ayarlayabilir.

Modelin ölçeklendirilmesini engellemek için, Microsoft_DisableScale adlı sahnedeki herhangi bir nesneye bir Boole özel özniteliği ekleyin ve bunu true olarak ayarlayın. daha sonra 3B görüntüleyici Beta, FBX dosyasına bakmış olan FbxSystemUnit bilgilerine göre değişir. 3B görüntüleyici beta sürümündeki ölçek, FBX birimi başına 1 ölçüm 'tir.

## <a name="viewing-fbx-files-on-hololens"></a>HoloLens 'te FBX dosyalarını görüntüleme

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Microsoft Edge 'den bir FBX dosyası açın

FBX dosyaları, HoloLens üzerinde Microsoft Edge kullanılarak doğrudan bir Web sitesinden açılabilir.

1. Microsoft Edge 'de, görüntülemek istediğiniz FBX dosyasını içeren Web sayfasına gidin.
1. İndirilecek dosyayı seçin.
1. İndirme işlemi tamamlandığında, dosyayı 3B görüntüleyici Beta 'da açmak için Microsoft Edge 'de **Aç** düğmesini seçin.

İndirilen dosyaya daha sonra Microsoft Edge 'de Indirmeler kullanılarak erişilebilir ve bu dosya açılabilir. Bir 3B modeli kaydetmek ve erişmeye devam etmek için, dosyayı bilgisayarınızda indirin ve OneDrive hesabınıza kaydedin. Daha sonra dosya, HoloLens üzerinde OneDrive uygulamasından açılabilir.

> [!NOTE]
> İndirilebilir FBX modelleriyle bazı Web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar. 3B görüntüleyici Beta, ZIP dosyalarını doğrudan açamaz. Bunun yerine, PC 'nizi kullanarak FBX dosyasını ayıklayın ve OneDrive hesabınıza kaydedin. Daha sonra dosya, HoloLens üzerinde OneDrive uygulamasından açılabilir.

### <a name="open-an-fbx-file-from-onedrive"></a>OneDrive 'dan bir FBX dosyası açın

FBX dosyaları, HoloLens üzerinde OneDrive uygulaması kullanılarak OneDrive 'dan açılabilir. HoloLens üzerinde Microsoft Store uygulamasını kullanarak OneDrive 'ı yüklediğinizden ve FBX dosyasını BILGISAYARıNıZDA OneDrive 'a zaten yüklemiş olduğunuzdan emin olun.

OneDrive 'daki bir kez, FBX dosyaları 3B görüntüleyici Beta kullanılarak HoloLens 'te iki şekilde açılabilir:

- HoloLens üzerinde OneDrive 'ı başlatın ve bunu 3B görüntüleyici Beta 'da açmak için FBX dosyasını seçin.
- 3B görüntüleyici Beta 'yı başlatın, AIR ' e dokunarak araç çubuğunu görüntüleyin ve **Dosya Aç**' ı seçin. OneDrive başlatılır ve bir FBX dosyası seçmenize olanak sağlar.

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

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>HoloLens 'te bir FBX dosyası açtığımda, bu, 3B görüntüleyici beta sürümünde açılmaz

3B görüntüleyici Beta, yüklendiğinde. FBX dosya uzantısıyla otomatik olarak ilişkilendirilir.

Bir FBX dosyası açmaya çalışırsanız ve Microsoft Store yönlendiren bir iletişim kutusu görürseniz, şu anda HoloLens üzerinde. FBX dosya uzantısıyla ilişkili bir uygulamanız yok.

3B görüntüleyici Beta 'nın yüklü olduğunu doğrulayın. Yüklü değilse, HoloLens üzerinde Microsoft Store indirin.

3B görüntüleyici beta sürümü zaten yüklüyse, 3B Görüntüleyicisi Beta 'yı başlatın ve sonra dosyayı açmayı yeniden deneyin. Sorun devam ederse, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin. Bu işlem,. FBX dosya uzantısını 3B görüntüleyici Beta ile yeniden ilişkilendirir.

Bir FBX dosyasını açmaya çalışmak, 3B görüntüleyici beta dışında bir uygulama açarsa, bu uygulama büyük olasılıkla 3B görüntüleyici beta sürümünden sonra yüklenmiş ve. FBX dosya uzantısıyla ilişkilendirmeyi gerçekleştirmiştir. 3B görüntüleyici Beta 'nın. FBX dosya uzantısıyla ilişkilendirilmesini tercih ediyorsanız, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3B görüntüleyici Beta 'daki Dosya Aç düğmesi bir uygulama başlatamaz

**Dosya Aç** düğmesi, Hololens üzerinde dosya seçici işleviyle ilişkili uygulamayı açar. OneDrive yüklüyse, **Dosya Aç** düğmesi OneDrive 'ı başlatacaktır. Ancak şu anda, HoloLens 'te yüklü dosya seçici işleviyle ilişkili bir uygulama yoksa Microsoft Store yönlendirilirsiniz.

**Dosya Aç** düğmesi OneDrive dışında bir uygulama başlatırsa, bu uygulama OneDrive 'dan sonra büyük olasılıkla yüklenmiş ve dosya seçici işleviyle ilişkilendirmeyi gerçekleştirmiştir. 3B görüntüleyici Beta 'da **Dosya Aç** düğmesini seçerken OneDrive 'ın başlatılmasını tercih ediyorsanız, OneDrive 'ı kaldırın ve yeniden yükleyin.

**Dosya Aç** düğmesi etkin değilse, 3B görüntüleyici Beta 'da tek seferde açık olabilecek modellerin sınırına ulaşmış olabilirsiniz. 3B görüntüleyici Beta 'da 40 modelleriniz varsa, ek modeller açabilmek için önce bazılarını kapatmanız gerekir.

## <a name="additional-resources"></a>Ek kaynaklar

- [Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) -yalnızca arşivleme amaçlıdır. Bu forum artık etkin değil.
- [Üçüncü taraf bildirimleri](https://www.microsoft.com/{lang-locale}/legal/products)
