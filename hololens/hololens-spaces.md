---
title: Fiziksel alanları HoloLens eşleme
description: HoloLens, bir alanın zaman içinde nasıl göründüğünü öğrenir. kullanıcılar, HoloLens alana belirli yollarla taşıyarak bu süreci kolaylaştırabilir.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, tasarım, uzamsal eşleme, HoloLens, yüzey yeniden oluşturma, kafes, baş izleme, eşleme
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640051"
---
# <a name="map-physical-spaces-with-hololens"></a>Fiziksel alanları HoloLens eşleme

fiziksel dünyala HoloLens karışımlar hologramlar. bunu yapmak için HoloLens, dünyanın dört bir yanındaki fiziksel dünya hakkında bilgi edinmek ve bu alana hologragram yerleştirdiğinizden emin olmanız gerekir.

zaman içinde HoloLens, göründüğü ortamın *uzamsal haritasını* oluşturur.  HoloLens, ortam değiştikçe haritayı güncelleştirir. oturum açtığınız ve cihaz açık olduğu sürece, HoloLens uzamsal haritalarınızı oluşturup günceller. cihaza bir boşluk işaret eden kameraları varsa veya bu cihazı aşdıysanız, HoloLens alanı eşlemeye çalışır. HoloLens zaman içinde bir alanı öğrenirken, alanınızı daha hızlı ve verimli bir şekilde eşlemeye HoloLens yardımcı olmak için kullanabileceğiniz yollar vardır.  

> [!NOTE]
> HoloLens alanınızı eşleyemezsiniz veya ayarlama işlemi yapıyorsanız HoloLens sınırlı mod girebilir. Sınırlı modda, hologramlar elde edemeyeceksiniz.

bu makalede, HoloLens alanları nasıl eşlediğini, uzamsal eşlemenin nasıl iyileştireceğinizi ve HoloLens tarafından toplanan uzamsal verilerin nasıl yönetileceği açıklanmaktadır.

## <a name="choosing-and-setting-up-and-your-space"></a>Alanı seçme ve ayarlama

ortamınızdaki özellikler, HoloLens bir alanı yorumlamasını zorlaştırır. hafif düzeyler, alandaki malzemeler, nesnelerin düzeni ve daha fazlası, HoloLens bir alanı nasıl eşlediğini etkiler.

HoloLens, belirli türde ortamlarda en iyi şekilde işe yarar. En iyi uzamsal Haritayı oluşturmak için, yeterli ışığı ve çok fazla alanı olan bir oda seçin. Büyük ve yarı saydam yüzeylere (örneğin, yansıtmalar veya gauzy CURTAINS) sahip olan karanlık boşluklar ve odalar kullanmaktan kaçının.

HoloLens, ınkapılı kullanım için iyileştirilmiştir. Uzamsal eşleme Ayrıca Wi-Fi açıldığında en iyi şekilde çalışıyor, ancak bir ağa bağlı olması gerekmez. HoloLens, bağlı veya kimliği doğrulanmamış olsa da Wi-Fi erişim noktalarını alabilir. HoloLens işlevselliği, erişim noktalarının internet 'e bağlı mi yoksa yalnızca intranet/yerel mi olduğunu değiştirmez.

yalnızca güvenilir yerlerde HoloLens, riskleri olmadan kullanın. [Daha fazla güvenlik](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Alanınızı eşleme

Şimdi yedek dosyanızı eşleştirmeye başlamaya hazırsınız.  HoloLens, kisörlerinizi eşleştirmeye başladığında, alanın üzerine yayıldığı bir kafes grafik görürsünüz.  Karma Gerçeklik ana sayfasında, eşlenmiş bir yüzey üzerinde seçim yaparak Haritayı gösterecek şekilde tetikleyebilirsiniz.

Harika bir uzamsal harita oluşturmaya yönelik yönergeler aşağıda verilmiştir.

### <a name="understand-the-scenarios-for-the-area"></a>Alanla ilgili senaryoları anlayın

haritanın ilgili ve tamamlanmış olması için HoloLens kullandığınız en çok zaman harcamanız önemlidir. örneğin, HoloLens bir kullanıcı senaryosu a noktasından B noktasına geçmeyi içeriyorsa, hareket ettirirken tüm yönlere bakarak bu yolu üç kez iki kez gözden getirin.  

### <a name="walk-slowly-around-the-space"></a>Alanı etrafında yavaşça ilerleme

alan etrafında çok hızlı bir şekilde gezinmenize yol, HoloLens eşleme alanlarının kaçırmasına yol gösterecektir. Her 5-8 metrede elde edeceğiniz şekilde, her yerden daha fazla hareket edin.  

kesintisiz hareketler HoloLens eşlemenin daha verimli bir şekilde sağlanmasına da yardımcı olur.

### <a name="look-in-all-directions"></a>Tüm yönergelere bakın

bu alanı eşleştirdiğinizde, noktaların birbirlerine göreli olduğu durumlarda HoloLens daha fazla veri verilir.  

örneğin, HoloLens bir odadaki tavan nerede olduğunu bilmiyor olabilir.  

Alanı eşleştirdiğinizde zemin üzerinde görünmemenizi unutmayın.

### <a name="cover-key-areas-multiple-times"></a>Anahtar bölgelerini birden çok kez Kapla

Bir alandan çok kez geçiş yapmak, ilk yönergede kaçırmış olabilecek özellikleri çekmeye yardımcı olur. İdeal bir harita oluşturmak için bir alandan üç kez geçiş yapmayı deneyin.

Mümkünse, bu taşımaları tekrarlarken, bir yönde bir alandan yürüyerek harcama süresini geri çevirip, daha sonra da bulunduğunuz şekilde geri dönün.

### <a name="take-your-time-mapping-the-area"></a>Alanı eşleştirmeye göre zamandan yararlanın

HoloLens tamamen eşlenme ve kendini kendi ilerleyebilir olarak ayarlaması için 15 ila 20 dakika sürebilir. en sık bir HoloLens kullanmayı planladığınız bir alanınız varsa, bu zaman, alanı eşlemek için en öne çıkan sorunları daha sonra engelleyebilir.  

## <a name="possible-errors-in-the-spatial-map"></a>Uzamsal haritada olası hatalar

Uzamsal eşleme verilerinde hatalar birkaç kategoride yer almalıdır:

- *Delik*: uzamsal eşleme verilerinde gerçek dünyada yüzeyler yok.
- *Hallucinations*: gerçek dünyada mevcut olmayan uzamsal eşleme verilerinde yüzeyler var.
- *solucan delikleri*: HoloLens ', uzamsal haritanın bir parçasını, gerçekten de haritanın farklı bir bölümünde olduğunu düşünerek, ' kaybeder '.
- *Sapma*: uzamsal eşleme verilerinde yüzeyler, gerçek dünya yüzeyleriyle birlikte gönderilir ya da kullanıma alınır.

Bu hatalardan herhangi birini görürseniz lütfen geri bildirim göndermek için [Feedbackhub ' ı](hololens-feedback.md) kullanın.

## <a name="security-and-storage-for-spatial-data"></a>Uzamsal veriler için güvenlik ve depolama

Microsoft HoloLens ve sonraki sürümleri için Windows 10 sürüm 1803 güncelleştirmesi, yerel (cihazdaki) bir veritabanında eşleme verilerini depolar.

HoloLens kullanıcılar, cihaz bir bilgisayara takılıyken veya dosya gezgini uygulaması kullanılırken bile harita veritabanına doğrudan erişemez. BitLocker HoloLens etkinleştirildiğinde, depolanan harita verileri de tüm birimle birlikte şifrelenir.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Harita verilerini ve bilinen boşlukları HoloLens kaldır

**Ayarlar > sistemi > Hologramlar** eşleme verilerini silmeye yönelik iki seçenek vardır:

- Yakın hologramlar silmek için **yakın Hologragram kaldır**' ı seçin. Bu komut, harita verilerini ve geçerli alana ait bağlantılı hologramlar temizler. Aynı alanda cihazı kullanmaya devam ederseniz, silinen bilgileri değiştirmek için yepyeni bir harita oluşturur ve depolar.

   > [!NOTE]
   > "Yakındaki" hologramlar, geçerli alanın aynı eşleme bölümünde sabitlenmiş hologramlar.

   Örneğin, bu seçeneği, ana ilgili harita verilerini etkilemeden iş ile ilgili harita verilerini temizlemek için kullanabilirsiniz.

- Tüm hologramlar silmek için **Tüm hologramlar 'ı kaldır**' ı seçin. Bu komut, cihazda depolanan tüm harita verilerini ve tüm bağlantılı hologramlar temizler. Herhangi bir hologragram açıkça yerleştirmeniz gerekir. Daha önce yerleştirdiğiniz hologramlar yeniden keşfedemeyeceksiniz.

> [!NOTE]
> yakın veya tüm hologramlar kaldırıldıktan sonra, HoloLens hemen taramaya ve geçerli alanı eşleştirmeye başlar.

### <a name="wi-fi-data-in-spatial-maps"></a>Uzamsal eşlemlerdeki verileri Wi-Fi

HoloLens, hologram konumlarını ve bilinen boşlukların HoloLens veritabanı içinde depolanan eşleme bölümlerini ilişkilendirmenize yardımcı olmak için Wi-Fi özelliklerini depolar. Wi-Fi özellikleriyle ilgili bilgiler, kullanıcılar tarafından erişilemez ve bulut kullanılarak veya telemetri kullanılarak Microsoft 'a gönderilmez.

Wi-Fi etkinleştirildiği sürece HoloLens harita verilerini yakın Wi-Fi erişim noktalarıyla ilişkilendirir. Bir ağın bağlı olup olmadığı veya yakın bir şekilde algılanıp algılanmadığı davranıştaki bir farklılık yoktur. Wi-Fi devre dışıysa, HoloLens hala alanı arar. ancak, HoloLens alanlar veritabanında daha fazla harita verisi aramak ve hologramlar bulmak için daha fazla zaman gerekebilir. Wi-Fi bilgisi olmadan, HoloLens, haritanın doğru kısmını bulmak için etkin taramaları tüm hologram tutturucularını ve cihazda depolanan bölümleri eşlemek için gerekir.

## <a name="related-topics"></a>İlgili konular

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
