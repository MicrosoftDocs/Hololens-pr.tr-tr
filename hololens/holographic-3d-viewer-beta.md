---
title: HoloLens 'da 3b görüntüleyici Beta kullanma (1. genel)
description: HoloLens (1. gen) üzerindeki 3b görüntüleyici Beta 'nın desteklediği dosya ve özellik türlerini ve uygulamanın nasıl kullanılacağını ve nasıl giderileceğini açıklar.
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
ms.openlocfilehash: d25a87bd210535e36e18f165b5461141c40aa292a07c560018ba7c0cbf76f6ba
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664936"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>HoloLens 'da 3b görüntüleyici Beta kullanma (1. genel)

3b görüntüleyici Beta, HoloLens (1. gen) üzerindeki 3b modelleri görüntülemenize olanak sağlar. *desteklenen* . fbx dosyalarını Microsoft Edge, OneDrive ve diğer uygulamalardan açabilir ve görüntüleyebilirsiniz.

>[!NOTE]
>bu makale,. fbx dosyalarını destekleyen ve yalnızca HoloLens (1. gen) ' de kullanılabilen, modern Unity **3b görüntüleyici Beta** uygulaması için geçerlidir. HoloLens 2 ' deki önceden yüklenmiş **3b görüntüleyici** uygulaması, karma gerçeklik ana bilgisayarında özel. glb 3d modellerini açmayı destekler (daha fazla bilgi için [varlık gereksinimlerine genel bakış](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) bölümüne bakın.

>[!IMPORTANT]
>3b görüntüleyici Beta, HoloLens için Microsoft Store (1. gen) kullanılabilir kalacağından, artık etkin bir geliştirme aşamasındadır ve artık desteklenmez.

3B görüntüleyici beta sürümünde bir 3B modeli açmada sorun yaşıyorsanız veya 3B modelinizin bazı özellikleri desteklenmiyorsa, aşağıdaki [desteklenen içerik belirtimleri](#supported-content-specifications) bölümüne bakın.

3B Viewer Beta ile kullanım için 3B modelleri derlemek veya iyileştirmek için bkz. aşağıdaki [3B Viewer Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta) .

HoloLens bir 3B model açmak için iki yol vardır. daha fazla bilgi için bkz. aşağıda [HoloLens fbx dosyalarını görüntüleme](#viewing-fbx-files-on-hololens) .

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

- Doku haritalarının siyah malzemelerinden veya siyah alanlarından kaçının. Hologramlar hafif yapılır, bu nedenle HoloLens siyahların (ışık yokluğu) saydam hale getirilir.
- Oluşturma aracınızdan FBX 'e vermeden önce tüm geometrinin göründüğünden ve kilidinin açık olduğundan ve geometri içeren katmanların kapalı veya şablonlu olduğundan emin olun. Görünürlük dikkate alınmıyor.
- Düğümler arasında çok büyük çeviri uzaklıklarını önleyin (örneğin, 100.000 birim). Bu, modelin taşınmakta/ölçeklendirildiğinde/döndürüldüğünde değişmesine neden olabilir.

### <a name="performance-optimization"></a>Performansı en iyi duruma getirme

en iyi sonuçlar için yazma işlemi sırasında HoloLens üzerinde içerik yazarken ve 3b görüntüleyici Beta uygulamasında doğrulama yaparken performansı göz önünde bulundurun. 3b görüntüleyici Beta, içeriğin gerçek zamanlı ve performansa HoloLens donanım özelliklerine tabidir.  

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

## <a name="viewing-fbx-files-on-hololens"></a>HoloLens üzerinde FBX dosyalarını görüntüleme

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Microsoft Edge bir FBX dosyası açın

fbx dosyaları, HoloLens Microsoft Edge kullanılarak doğrudan bir web sitesinden açılabilir.

1. Microsoft Edge ' de, görüntülemek istediğiniz fbx dosyasını içeren web sayfasına gidin.
1. İndirilecek dosyayı seçin.
1. indirme işlemi tamamlandığında, dosyayı 3b görüntüleyici Beta sürümünde açmak için Microsoft Edge **aç** düğmesini seçin.

İndirilen dosyaya daha sonra Microsoft Edge karşıdan yüklemeler kullanılarak yeniden açılabilir. bir 3b modeli kaydetmek ve devam etmek için dosyayı bilgisayarınızda indirin ve OneDrive hesabınıza kaydedin. Dosya daha sonra OneDrive uygulamasından HoloLens.

> [!NOTE]
> İndirilebilir FBX modellerine sahip bazı web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar. 3B Görüntüleyici Beta ZIP dosyalarını doğrudan açamaz. Bunun yerine, FBX dosyasını ayıklamak için bilgisayarınızı kullanın ve dosyayı OneDrive kaydedin. Dosya daha sonra OneDrive uygulamasından HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Dosyadan FBX OneDrive

FBX dosyaları, OneDrive üzerinde OneDrive kullanılarak HoloLens. HoloLens'de OneDrive Microsoft Store uygulamasını kullanarak FBX dosyasını bilgisayarınıza yüklemiş OneDrive emin olun.

FBX OneDrive iki farklı şekilde HoloLens Beta 3B Görüntüleyici açılabilir:

- OneDrive'HoloLens FBX dosyasını seçerek Beta'da 3B Görüntüleyici açın.
- Beta 3B Görüntüleyici'yi açın, araç çubuğunu göstermek için havadan dokunun ve Dosya **Aç'ı seçin.** OneDrive, bir FBX dosyası seçmenize olanak sağlar.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>3D modeli açtım bir uyarı görüyorum

3B Görüntüleyici Beta tarafından desteklenen özellikler içeren bir 3D modeli açmaya çalışırken veya model çok karmaşıksa ve performans etkilenebilirse bir uyarıyla karşınız olur. 3B Görüntüleyici Beta 3D modeli yüklemeye devam eder, ancak performans veya görsel uygunluk tehlikeye girebilir.

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Bir uyarı görüyorum ve 3D modeli yüklenemedi

3B Görüntüleyici Beta, karmaşıklık veya dosya boyutu nedeniyle 3B modeli yükleyene kadar ya da FBX dosyası bozuk veya geçersiz olduğunda bir hata iletisiyle karşınız. Toplam model, köşe veya tire sayısı sınırına ulaştınız ve aynı anda açabilirsiniz.  

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve [Dosya ve model sınırlamaları.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>3D modelim yüklenmiyor ama beklendiği gibi görünmüyor

3D modeliniz Beta sürümünde beklendiği gibi 3B Görüntüleyici, araç çubuğunu göstermek için havadan dokunun ve Ayrıntılar'ı **seçin.** 3B Görüntüleyici Beta tarafından 3B Görüntüleyici dosyanın yönleri uyarı olarak vurgulanır.

Gördüğünüz en yaygın sorun, eksik dokular olabilir çünkü bunlar FBX dosyasına ekli değildir. Bu durumda model beyaz görünür. Oluşturma aracınızı doku ekleme seçeneği seçiliyken FBX'e aktararak bu sorun oluşturma işlemiyle çözülebilirsiniz.

Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>3D modelimi görüntülerken performans düşüşleri yaşanıyor

3D modeli yüklerken ve görüntülerken performans, modelin karmaşıklığından, model sayısının aynı anda açılmasından veya etkin animasyonlarla model sayısından etkilenebilir.

Daha fazla bilgi için bkz. Beta ve Dosya ve model [3B Görüntüleyici için 3D](#optimizing-3d-models-for-3d-viewer-beta) [modelleri iyileştirme.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>HoloLens'da FBX dosyasını 3B Görüntüleyici beta sürümünde açılmaz

3B Görüntüleyici Beta, yüklenirken .fbx dosya uzantısıyla otomatik olarak ilişkilendirilır.

Bir FBX dosyası açmaya ve sizi Microsoft Store'a yönlendiren bir iletişim kutusu görmeye devam ediyorsanız, şu anda dosya üzerinde .fbx dosya uzantısıyla ilişkilendirilmiş bir HoloLens.

Beta'3B Görüntüleyici yüklü olduğunu doğrulayın. Yüklü değilse, dosyanın Microsoft Store'HoloLens.

Beta 3B Görüntüleyici yüklüyse Beta'3B Görüntüleyici açın ve dosyayı yeniden açmayı deneyin. Sorun devam ederse Beta sürümünü kaldırıp 3B Görüntüleyici yükleyin. Bu, .fbx dosya uzantısını beta sürümüyle 3B Görüntüleyici eder.

FBX dosyası açılmaya çalışıldıktan sonra 3B Görüntüleyici Beta dışında bir uygulama açılırsa, bu uygulama büyük olasılıkla 3B Görüntüleyici Beta'dan sonra yüklenmiştir ve .fbx dosya uzantısıyla ilişkilendirmeyi ele almış olur. Beta'3B Görüntüleyici .fbx dosya uzantısıyla ilişkilendirilmeyi tercih ediyorsanız, Beta'3B Görüntüleyici yükleyin.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3B Görüntüleyici Beta'da Dosya Aç düğmesi uygulama başlatamıyor

Dosya **Aç düğmesi,** dosya seçici işleviyle ilişkili uygulamayı HoloLens. Yüklü OneDrive, Dosya Aç **düğmesinin** dosya açma OneDrive. Ancak, şu anda dosya seçici işleviyle ilişkilendirilmiş bir uygulama HoloLens, dosya seçici işlevine Microsoft Store.

Dosya **Aç düğmesi** OneDrive dışında bir uygulama başlatıyorsa, bu uygulama büyük olasılıkla OneDrive yüklendikten ve dosya seçici işleviyle ilişkilendirmeyi ele aldı. Beta'OneDrive Dosya Aç düğmesini seçerek  başlatmayı tercih ediyorsanız, 3B Görüntüleyici'yi kaldırın ve OneDrive.

Dosya **Aç düğmesi** etkin durumda değilse, tek bir anda Beta sürümünde açabilirsiniz 3B Görüntüleyici sınırına ulaştınız. Beta sürümünde 40 modeli 3B Görüntüleyici, ek modeller açabileceksiniz.

## <a name="additional-resources"></a>Ek kaynaklar

- [Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) - Yalnızca arşivleme amacıyla. Bu forum artık etkin değil.
- [Üçüncü taraf bildirimler](https://www.microsoft.com/{lang-locale}/legal/products)
