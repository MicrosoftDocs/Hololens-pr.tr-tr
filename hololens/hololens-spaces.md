---
title: Fiziksel alanları HoloLens ile eşleme
description: HoloLens, bir alanın zaman içinde nasıl göründüğünü öğrenir. Kullanıcılar, HoloLens 'i alana göre belirli yollarla taşıyarak bu süreci kolaylaştırabilir.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: Hololens, Windows Mixed Reality, tasarım, uzamsal eşleme, HoloLens, yüzey yeniden oluşturma, kafes, baş izleme, eşleme
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380219"
---
# <a name="map-physical-spaces-with-hololens"></a>Fiziksel alanları HoloLens ile eşleme

HoloLens ile fiziksel dünyayı hologramlar. Bunu yapmak için, HoloLens 'in sizin çevresindeki fiziksel dünyayı öğreni ve bu alana hologragram yerleştirdiğinizden emin olması gerekir.

Zaman içinde, HoloLens, gördüğü ortamın *uzamsal haritasını* oluşturur.  HoloLens, ortamı değiştiği için Haritayı güncelleştirir. Oturum açtığınız ve cihaz açık olduğu sürece, HoloLens, uzamsal haritalarınızı oluşturur ve güncelleştirir. Cihaza bir boşluk işaret eden kameraları varsa veya bu cihazı aşdıysanız, HoloLens alanı eşlemeyi dener. HoloLens zaman içinde bir alanı öğrenirken, HoloLens 'in alanınızı daha hızlı ve verimli bir şekilde eşlemesine yardımcı olabilirsiniz.  

> [!NOTE]
> HoloLens 'niz alanınızı eşleyemiyorum veya ayar dışında, HoloLens sınırlı mod girebilir. Sınırlı modda, hologramlar elde edemeyeceksiniz.

Bu makalede, HoloLens 'in alanları nasıl eşleştiği, uzamsal eşlemenin nasıl geliştirilmesi ve HoloLens 'in topladığı uzamsal verilerin nasıl yönetileceği açıklanmaktadır.

## <a name="choosing-and-setting-up-and-your-space"></a>Alanı seçme ve ayarlama

Ortamınızdaki özellikler, HoloLens 'in bir alanı yorumlamasını zorlaştırır. Hafif düzeyler, boşluk içindeki malzemeler, nesnelerin düzeni ve daha fazlası, HoloLens 'in bir alanı nasıl eşlediğini etkiler.

HoloLens, belirli ortam türlerinde en iyi şekilde çalışmaktadır. En iyi uzamsal Haritayı oluşturmak için, yeterli ışığı ve çok fazla alanı olan bir oda seçin. Büyük ve yarı saydam yüzeylere (örneğin, yansıtmalar veya gauzy CURTAINS) sahip olan karanlık boşluklar ve odalar kullanmaktan kaçının.

HoloLens, ınkapılı kullanım için iyileştirilmiştir. Uzamsal eşleme Ayrıca Wi-Fi açıldığında en iyi şekilde çalışıyor, ancak bir ağa bağlı olması gerekmez. HoloLens bağlı veya kimliği doğrulanmamış olsa bile Wi-Fi erişim noktalarını alabilir. HoloLens işlevselliği, erişim noktalarının internet 'e bağlı mi yoksa yalnızca intranet/yerel mi olduğunu değiştirmez.

HoloLens 'i yalnızca kasa olmayan güvenli yerlerde kullanın. [Daha fazla güvenlik](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Alanınızı eşleme

Şimdi yedek dosyanızı eşleştirmeye başlamaya hazırsınız.  HoloLens, kisörlerinizi eşleştirmeye başladığında, alanın üzerine yayıldığı bir kafes grafik görürsünüz.  Karma Gerçeklik ana sayfasında, eşlenmiş bir yüzey üzerinde seçim yaparak Haritayı gösterecek şekilde tetikleyebilirsiniz.

Harika bir uzamsal harita oluşturmaya yönelik yönergeler aşağıda verilmiştir.

### <a name="understand-the-scenarios-for-the-area"></a>Alanla ilgili senaryoları anlayın

Haritanın ilgili ve tamamlanmış olması için HoloLens 'in kullanıldığı en çok zaman harcamanız önemlidir. Örneğin, HoloLens için bir Kullanıcı senaryosu A noktası A 'dan B 'ye geçmeyi içeriyorsa, taşırken tüm yönlere bakarak bu yolu üç kez iki kez gözden getirin.  

### <a name="walk-slowly-around-the-space"></a>Alanı etrafında yavaşça ilerleme

Alan etrafında çok hızlı bir şekilde gezinirken, HoloLens 'in eşleme alanlarının kaçırılması olasıdır. Her 5-8 metrede elde edeceğiniz şekilde, her yerden daha fazla hareket edin.  

Düzgün hareketler, HoloLens eşlemenin daha verimli bir şekilde sağlanmasına da yardımcı olur.

### <a name="look-in-all-directions"></a>Tüm yönergelere bakın

Siz eşleme yaparken, alanı, noktaların birbirlerine göreli olduğu yerde, HoloLens 'e daha fazla veri verir.  

Örneğin, HoloLens, bir odanın nerede olduğunu bilmiyor olabilir.  

Alanı eşleştirdiğinizde zemin üzerinde görünmemenizi unutmayın.

### <a name="cover-key-areas-multiple-times"></a>Anahtar bölgelerini birden çok kez Kapla

Bir alandan çok kez geçiş yapmak, ilk yönergede kaçırmış olabilecek özellikleri çekmeye yardımcı olur. İdeal bir harita oluşturmak için bir alandan üç kez geçiş yapmayı deneyin.

Mümkünse, bu taşımaları tekrarlarken, bir yönde bir alandan yürüyerek harcama süresini geri çevirip, daha sonra da bulunduğunuz şekilde geri dönün.

### <a name="take-your-time-mapping-the-area"></a>Alanı eşleştirmeye göre zamandan yararlanın

HoloLens 'in tamamen eşlenme ve kendini kendi ilerleyebilir olarak ayarlaması için 15 ila 20 dakika sürebilir. HoloLens kullanmayı planladığınız bir alanınız varsa, alanı eşlemek için bu sürenin önüne geçmek daha sonra sorunları önleyebilir.  

## <a name="possible-errors-in-the-spatial-map"></a>Uzamsal haritada olası hatalar

Uzamsal eşleme verilerinde hatalar birkaç kategoride yer almalıdır:

- *Delik*: uzamsal eşleme verilerinde gerçek dünyada yüzeyler yok.
- *Hallucinations*: gerçek dünyada mevcut olmayan uzamsal eşleme verilerinde yüzeyler var.
- *Solucan delikleri*: HoloLens ', bir haritanın farklı bir bölümünde olduğunu düşünerek uzamsal haritanın parçasını kaybeder.
- *Sapma*: uzamsal eşleme verilerinde yüzeyler, gerçek dünya yüzeyleriyle birlikte gönderilir ya da kullanıma alınır.

Bu hatalardan herhangi birini görürseniz lütfen geri bildirim göndermek için [Feedbackhub ' ı](hololens-feedback.md) kullanın.

## <a name="security-and-storage-for-spatial-data"></a>Uzamsal veriler için güvenlik ve depolama

Microsoft HoloLens için Windows 10 sürüm 1803 güncelleştirmesi ve üzeri, eşleme verilerini yerel (cihazda) bir veritabanında depolar.

Cihaz bir BILGISAYARA takılıyken veya dosya Gezgini uygulaması kullanılırken bile, HoloLens kullanıcıları harita veritabanına doğrudan erişemez. HoloLens 'te BitLocker etkinleştirildiğinde, depolanan harita verileri de tüm birimle birlikte şifrelenir.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>HoloLens 'ten harita verilerini ve bilinen boşlukları kaldırma

**Ayarlar > sistem > Hologragram**'da harita verilerini silmeye yönelik iki seçenek vardır:

- Yakın hologramlar silmek için **yakın Hologragram kaldır**' ı seçin. Bu komut, harita verilerini ve geçerli alana ait bağlantılı hologramlar temizler. Aynı alanda cihazı kullanmaya devam ederseniz, silinen bilgileri değiştirmek için yepyeni bir harita oluşturur ve depolar.

   > [!NOTE]
   > "Yakındaki" hologramlar, geçerli alanın aynı eşleme bölümünde sabitlenmiş hologramlar.

   Örneğin, bu seçeneği, ana ilgili harita verilerini etkilemeden iş ile ilgili harita verilerini temizlemek için kullanabilirsiniz.

- Tüm hologramlar silmek için **Tüm hologramlar 'ı kaldır**' ı seçin. Bu komut, cihazda depolanan tüm harita verilerini ve tüm bağlantılı hologramlar temizler. Herhangi bir hologragram açıkça yerleştirmeniz gerekir. Daha önce yerleştirdiğiniz hologramlar yeniden keşfedemeyeceksiniz.

> [!NOTE]
> Yakın veya tüm hologramlar kaldırıldıktan sonra, HoloLens hemen taramaya ve geçerli alanı eşleştirmeye başlar.

### <a name="wi-fi-data-in-spatial-maps"></a>Uzamsal eşlemlerdeki verileri Wi-Fi

HoloLens, hologram konumlarının ve bilinen boşlukların HoloLens veritabanı içinde depolanan eşleme bölümlerinin ilişkilendirilmesi için Wi-Fi özellikleri depolar. Wi-Fi özellikleriyle ilgili bilgiler, kullanıcılar tarafından erişilemez ve bulut kullanılarak veya telemetri kullanılarak Microsoft 'a gönderilmez.

Wi-Fi etkinleştirildiği sürece, HoloLens, verileri yakın Wi-Fi erişim noktalarıyla eşler. Bir ağın bağlı olup olmadığı veya yakın bir şekilde algılanıp algılanmadığı davranıştaki bir farklılık yoktur. Wi-Fi devre dışıysa, HoloLens hala boşluğu arar. Ancak, HoloLens 'in, alanlar veritabanında daha fazla harita verisi araması yapması gerekir ve hologramlar bulmak için daha fazla zaman gerekebilir. Wi-Fi bilgisi olmadan, HoloLens, haritanın doğru kısmını bulmak için etkin taramaları tüm hologram tutturucularını ve cihazda depolanan bölümleri eşlemek zorunda değildir.

## <a name="related-topics"></a>İlgili konular

- [Uzamsal eşleme tasarımı](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
