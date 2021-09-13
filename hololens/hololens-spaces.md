---
title: Fiziksel alanları HoloLens
description: HoloLens zaman içinde bir boşluğun nasıl göründüğünü öğrenir. Kullanıcılar, alanı belirli yollarla HoloLens bu süreci kolaylaştırabilirsiniz.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, tasarım, uzamsal eşleme, HoloLens, yüzey yeniden yapılandırma, örgü, baş izleme, eşleme
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036501"
---
# <a name="map-physical-spaces-with-hololens"></a>Fiziksel alanları HoloLens

HoloLens hologramları fiziksel dünyanız ile karıştırıyor. Bunu yapmak için HoloLens fiziksel dünya hakkında bilgi edinmek ve hologramları bu uzaya nereye yer ayazmanız gerekir.

Zaman içinde HoloLens, gördüklerini *ortamın* uzamsal haritasını oluşturmasını sağlar.  HoloLens ortam değiştikça haritayı da günceller. Oturum açtığınız ve cihaz açık olduğu sürece, uzamsal HoloLens oluşturur ve günceller. Cihazı bir alana işaret eden kameralarla tutarsanız veya takıyorsanız, HoloLens alanı eşlemeye çalışır. Bu HoloLens bir alanı zaman içinde doğal olarak öğrenirken, alanlarınızı daha hızlı ve verimli bir şekilde eşlemenize HoloLens yardımcı olabilir.  

> [!NOTE]
> Çalışma HoloLens alanınız eşleyenene kadar eşleyene HoloLens sınırlı moda girebilirsiniz. Sınırlı modda, çevrenize hologramlar yer alasınız.

Bu makalede alanları HoloLens eşleme, uzamsal eşlemeyi geliştirme ve bu alanlardan toplayan uzamsal HoloLens açıklanmıştır.

## <a name="choosing-and-setting-up-and-your-space"></a>Alanınızı seçme ve ayarlama

Ortamınız içinde yer alan özellikler, ortamın HoloLens yorumlamayı zorlaştırabilirsiniz. Açık düzeyler, boşlukta malzemeler, nesnelerin düzeni ve daha fazlası bir alanı eşleme HoloLens etkileyebilir.

HoloLens, belirli türlerde en iyi şekilde çalışır. En iyi uzamsal haritayı üretmek için yeterli ışık ve yeterli alana sahip bir oda seçin. Koyu alanlardan ve çok koyu, parlak veya saydam yüzeylere (örneğin, yansıtmalar veya gauzy perdeleri) sahip olan odaları kaçının.

HoloLens iç mekan kullanımı için en iyi duruma getirilmiş. Uzamsal eşleme, Wi-Fi bir ağa bağlı olması gerekse de en iyi şekilde çalışır. HoloLens, Wi-Fi veya kimliği doğrulanmamış olsa bile erişim noktaları elde eder. HoloLens, erişim noktalarının internete bağlı mı yoksa yalnızca intranet/yerel mi olduğunu değiştirmez.

Yalnızca HoloLens tehlikeleri olan güvenli yerlerde kullanın. [Güvenlik hakkında daha fazla bilgi.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Alanınızı eşleme

Artık yedeklerinizi eşlemeye başlayabilirsiniz.  HoloLens eşlemeye başladığında, alana yayılmış bir örgü grafiğiyle karşınıza çıkar.  Karma gerçeklik giriş'te eşlenmiş bir yüzeyde öğesini seçerek haritayı gösterecek şekilde tetiklersiniz.

İşte harika bir uzamsal haritayı inşa etmek için yönergeler.

### <a name="understand-the-scenarios-for-the-area"></a>Alan için senaryoları anlama

Haritanın uygun ve eksiksiz olması için en fazla HoloLens zaman harcamanız önemlidir. Örneğin, A noktasından B noktasına HoloLens bir kullanıcı senaryosu varsa, siz hareket ettiyken her yönde bakarak bu yolu iki veya üç kez izleyin.  

### <a name="walk-slowly-around-the-space"></a>Alanda yavaş bir şekilde dolaşın

Alanda çok hızlı bir şekilde ilerlersanız, harita alanlarının HoloLens olabilir. Uzayda yavaş bir şekilde dolaşın ve etrafınıza bakmak için her 5-8 fit'te bir durduruluyor.  

Düzgün hareket, haritanın daha HoloLens yardımcı olur.

### <a name="look-in-all-directions"></a>Her yönde bakın

Siz alanı eşlerken bu alanı HoloLens noktaların birbirine göreli olduğu daha fazla veri verir.  

Örneğin, yukarı bakamıyorsanız, HoloLens tavanın nerede olduğunu bilmiyor olabilir.  

Alanı eşlerken zemine bakmayı unutmayın.

### <a name="cover-key-areas-multiple-times"></a>Önemli alanları birden çok kez kapsıyor

Bir alanda birden çok kez ilerlemek, ilk kılavuzda gözden kaçırabilirsiniz özellikleri almaya yardımcı olur. İdeal bir harita oluşturmak için bir alanı iki veya üç kez çapraz geçişe deneyin.

Mümkünse, bu hareketleri tekrarlarken bir alanda tek yönde dolaşarak zaman harcayarak geri dönüp geri dönerek geri dönersiniz.

### <a name="take-your-time-mapping-the-area"></a>Alanı eşlemeye zaman at

Tam olarak haritanın ve çevrenin kendisini ayarlaması HoloLens 15 ile 20 dakika arasında sürebilir. Sık sık bir depolama alanı kullanmayı planlayabilirsiniz HoloLens, alanı eşlemek için bu kadar zaman almak daha sonra sorunları önlenebilir.  

## <a name="possible-errors-in-the-spatial-map"></a>Uzamsal haritada olası hatalar

Uzamsal eşleme verilerinde hatalar birkaç kategoriye ayrılır:

- *Delikler:* Gerçek dünya yüzeyleri uzamsal eşleme verilerinden eksiktir.
- Uzamsallıklar: Yüzeyler, gerçek dünyada mevcut olmayan uzamsal eşleme verilerde yer alır.
- *Wormholes:* HoloLens farklı bir parçası olduğunu düşünerek uzamsal haritanın bir bölümünü 'kaybeder'.
- *Yanlılık:* Uzamsal eşleme verisi yüzeyleri, gerçek dünya yüzeyleriyle kusursuz bir şekilde hizalanır.

Bu hatalardan herhangi birini görüyorsanız geri bildirim göndermek için [FeedbackHub'ı](hololens-feedback.md) kullanın.

## <a name="security-and-storage-for-spatial-data"></a>Uzamsal veriler için güvenlik ve depolama

Windows 10 için sürüm 1803 Microsoft HoloLens, eşleme verilerini yerel (cihaz üzerinde) veritabanında depolar.

HoloLens, cihaz bir bilgisayara takılı olsa bile veya bir bilgisayar uygulaması kullanırken bile harita veritabanına Dosya Gezgini erişemektedir. Veri kaynağında BitLocker HoloLens, depolanan eşleme verileri de birimin tamamı ile birlikte şifrelenir.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Harita verilerini ve bilinen alanları HoloLens

Ayarlar > **System > Hologramlar'da harita verilerini silmek için iki seçenek vardır:**

- Yakındaki hologramları silmek için Yakındaki **hologramları kaldır'ı seçin.** Bu komut, geçerli alan için harita verilerini ve sabitli hologramları temizler. Cihazı aynı alanda kullanmaya devam edersanız silinen bilgilerin yerini alacak yepyeni bir harita bölümü oluşturur ve depolar.

   > [!NOTE]
   > "Yakındaki" hologramlar, geçerli alanda aynı harita bölümüne sabitli hologramlardır.

   Örneğin, evle ilgili harita verilerini etkilemeden işle ilgili harita verilerini temizlemek için bu seçeneği kullanabilirsiniz.

- Tüm hologramları silmek için Tüm **hologramları kaldır'ı seçin.** Bu komut, hem cihazda depolanan tüm harita verilerini hem de sabitli hologramları temizler. Tüm hologramları açıkça yere ayazmanız gerekir. Önceden yerleştirilmiş hologramları yeniden keşfedesiniz.

> [!NOTE]
> Yakındaki veya tüm hologramları kaldırdikten sonra, HoloLens hemen taramaya ve geçerli alanı eşlemeye başlar.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi haritalarda verileri toplama

HoloLens, Wi-Fi alan veritabanında depolanan hologram konumlarını ve harita bölümlerinin arasında HoloLens özellikleri depolar. Bu Wi-Fi özellikleri hakkında bilgiler kullanıcılar tarafından erişilemez ve bulut kullanılarak veya telemetri kullanılarak Microsoft'a gönderilmez.

Bu bağlantı Wi-Fi sürece, HoloLens yakınlardaki erişim noktalarıyla Wi-Fi arasında ilişki vardır. Bir ağın bağlı olması veya yakın bir yerde algılandığından davranışta bir fark yoktur. Bu Wi-Fi devre dışı bırakılırsa HoloLens yine de alanı arar. Ancak HoloLens verilerde daha fazla arama yapmak gerekir ve hologramları bulmak için daha fazla zaman gerekir. Veri Wi-Fi olmadan, HoloLens haritanın doğru kısmını bulmak için etkin taramaları cihazda depolanan tüm hologram sabit noktaları ve harita bölümleriyle karşılaştırması gerekir.

## <a name="related-topics"></a>İlgili konular

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
