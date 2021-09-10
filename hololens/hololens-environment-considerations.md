---
title: HoloLens ortamı konuları
description: cihazı gözler ve ortamınız için en iyi hale getirirken HoloLens kullanarak mümkün olan en iyi deneyimi elde edin.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holographic çerçevesi, görünüm alanı, fov, ayarlama, boşluklar, ortam, nasıl yapılır, HoloLens, karma gerçeklik, karma gerçeklik kulaklıklar
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427304"
---
# <a name="hololens-environment-considerations"></a>HoloLens ortamı konuları

HoloLens, "gerçek" dünya ile holographic karıştırır ve bu da kisörlerinizi hologramlar olarak yerleştirir. Duvardaki bir holographic uygulama penceresi "askıda kalıyor", Tabletop üzerinde bir holographic Ballerina, tavşan arkadaşınızın baş başınızın en üstünde Oturar. Tam ekran bir oyun veya uygulama kullanırken, Holographic dünyası, ortaya çıkacak olan, ancak yine de alan etrafında görebilir ve taşıyabilirsiniz.

Yerleştirdiğiniz hologramlar, cihazınızı kapatsanız bile bunları yerleştirdiğiniz yere kalır.

## <a name="setting-up-an-environment"></a>Ortam ayarlama

HoloLens cihazlar, bir alanda kullanıcıları *izleyerek* kararlı ve doğru hologramlar yerleştirmeyi bilir. Doğru izleme olmadan cihaz, ortamı veya içindeki kullanıcıyı anlamaz. Hologramlar yanlış yerlerde görünebilir, her seferinde aynı noktada görünmez veya hiç görünmez. Kullanıcıları izlemek için kullanılan veriler, *uzamsal haritada* temsil edilir.  

İzleme performansı, kullanıcının içinde bulunduğu ortam tarafından büyük ölçüde etkilenir ve bir ortamın tutarlı ve tutarlı izlemeye göre ayarlanması, bir bilim yerine bir sanatdır. Birçok farklı ortam faktörü, izlemeyi etkinleştirmek için birlikte kullanılır, ancak karma gerçeklik geliştiricisi olarak, daha iyi izleme için bir alan ayarlamayı aklınızda bulundurmanız gereken birkaç etken vardır.

### <a name="lighting"></a>Işık

Windows Mixed Reality, kullanıcının konumunu izlemek için görsel ışık kullanır. Bir ortam çok parlak olduğunda, kameralar doygun alabilir ve hiçbir şey görülmez. Ortam çok karanlık ise, kameralar yeterli bilgi çekemez ve hiçbir şey görülmez. Işıklandırma, sorunsuz bir şekilde ve yeterince parlak olmalıdır, ancak hafif bir şekilde göz atabilmelidir.  

Bir genel Dim alanında parlak ışık noktaları olan alanlar da sorunlu olduğundan, kameranın parlak boşlukların içine ve dışına geçerek ayarlanmasında de sorun vardır. Bu, cihazın "kayıp" olmasına neden olabilir ve açık olan değişikliğin konumdaki değişikliğe eşit olduğunu düşünün. Bir alandaki kararlı hafif düzeyler daha iyi izlemeye neden olur.  

Güneş zaman içinde önemli ölçüde farklılık gösterebileceğinden, her türlü açık hava ışığı da izleyicide kararsızlığa neden olabilir. Örneğin, yaz ve kış içindeki aynı alanda izleme büyük ölçüde farklı sonuçlar oluşturabilir, bu da ikinci iki açık ışık yılın farklı saatlerinde daha yüksek olabilir.  

Bir Luxmeter varsa, sürekli bir 500-1000 Lux, başlamak için iyi bir yerdir.  

#### <a name="types-of-lighting"></a>Aydınlatma türleri

Bir alanda farklı ışık türleri de izlemeyi etkileyebilir. It üzerinden çalışan AC elektrik ile hafif bulbs Pulse-AC sıklığı 50 Hz ise, hafif bir şekilde 50 Hz 'e sahiptir. İnsan için, bu pulun fark etmez. ancak, HoloLens ' 30 fps kare bu değişiklikleri görür. bazı kareler iyi aydınlatılır, bazıları kötü bir şekilde aydınlatılır ve kamera hafif bir şekilde telafi etmeye çalıştığında bazı çok açık olur.  

abd 'de, elektrik frekansı standart 60 hz 'dir. bu nedenle ampullü HoloLens ' kare hızı-60 hz, HoloLens ' 30 FPS kare hızına hizalanır. ancak, birçok ülkede 50 Hz 'in bir AC frekansı standardı vardır. bu, bazı HoloLens karelerin pulu sırasında alınması ve başkalarının bu şekilde yapılmadığı anlamına gelir. Özellikle, Avrupa 'daki akıcı oressan ışıklandırma, sorunlara yol açabilecek şekilde bilinmektedir.  

Titreşme sorunlarını çözmeyi deneyebilmeniz gereken birkaç nokta vardır. Sıcaklık, ampul yaşı ve ısınma döngüleri, akıcı bir şekilde titreşme ve bulsan 'ları değiştirme konusunda yaygın nedenlerdir. Bulbs 'ları daha sıkı hale getirme ve geçerli çizlerin sabit olduğundan emin olma da yardımcı olabilir.  

### <a name="items-in-a-space"></a>Bir alandaki öğeler

HoloLens, kendisini bir boşluk içinde bulmak için *özellikler* olarak da bilinen benzersiz çevresel yer işaretlerini kullanır.  

Cihaz her yerde nerede olduğunu bilmenin bir yolu olmadığı için bir cihaz neredeyse hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde izlenemez. Bir alanın duvarlara özellik eklemek, genellikle izlemeyi geliştirmenin iyi bir yoludur. Posterler, simgeler bir duvar, bitkiler, benzersiz nesneler veya diğer benzer öğelere tüm yardım. Karmaşık masası, iyi izlemeye yol gösteren bir ortama yönelik iyi bir örnektir. tek bir alanda birçok farklı özellik vardır.  

Ayrıca, aynı alanda benzersiz özellikler kullanın. bir duvar üzerinde birden çok kez yinelenen poster, örneğin HoloLens, ne kadar yinelenen posteri olduğunu bilmez. Benzersiz özellikler eklemenin yaygın bir yolu, bir alanın duvarlar ve tabanı üzerinde benzersiz, yinelenmeyen desenler oluşturmak için, maske bantlarının çizgilerini kullanmaktır.  

Kendinize sormanız gereken iyi bir soru: sahnenin yalnızca küçük bir miktarını görüyorsanız, kendinizi alana benzersiz bir şekilde buladınız mı? Aksi takdirde, cihazda sorun izleme de olur.

#### <a name="wormholes"></a>Solucan delikleri

Aynı olan iki alan veya bölgeseniz, izleyici aynı olduğunu düşünebilir. Bu, cihazın başka bir yerde düşünmeye karşı daha çarpıcı hale gelir. Bu tür yinelenen alan *solucan delikleri* çağrımız.  

Solucan boşluklarını engellemek için aynı alandaki aynı alanları engellemeye çalışın. Aynı alanlara bazen fabrika istasyonları, bir bina, sunucu rafları veya iş istasyonlarıyla ilgili pencereler dahil olabilir. Her bir benzer alana yönelik alanların etiketlenmesi veya benzersiz özelliklerin eklenmesi, solucan delikleri azaltmaya yardımcı olabilir.

### <a name="movement-in-a-space"></a>Bir boşluk içine taşıma

Ortamınız sürekli olarak kaydırılmışsa ve değişiyorsa, cihazın yerini almak için kararlı bir özelliği yoktur.  

Daha fazla hareketli nesneler, kişiler de dahil olmak üzere, izlemeyi kaybetmeniz daha kolay. Taşıyıcı köklerinin, farklı yapım durumlarında öğelerin ve bir alandaki çok sayıda kişinin, izleme sorunlarına neden olduğu bilinmektedir.

HoloLens, bu değişikliklere hızlı bir şekilde uyum sağlayabilir, ancak yalnızca bu alan cihaza açık bir şekilde görünür. Genellikle, uzamsal haritada hatalara neden olabilecek, gerçeğe göre görülmeyen bölgeler. Örneğin, bir Kullanıcı bir arkadaşınızı tarar ve arkadaşınız odadan çıktığında onu kapatır. Kullanıcı artık boş alanı yeniden taraana kadar arkadaşınızın ' hayalet ' temsili uzamsal eşleme verilerinde kalır.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Kullanıcının alanındaki öğelere yakınlığı

benzer şekilde, insanlara yakın nesneler üzerinde daha iyi odaklanamadığı gibi, nesneler kameralarına yakın olduğunda HoloLens. Bir nesne her iki kamera ile de görülemeyecek kadar yakınsa veya bir nesne bir kamerayı engelliyorsa, cihaz, nesneyle ilgili izleme konusunda çok daha fazla soruna sahip olur.  

Kameralar bir nesneden 15 cm 'den daha yakın olmadığını görebilir.

### <a name="surfaces-in-a-space"></a>Boşluk içindeki yüzeyler

Kesin yansıtıcı yüzeyler büyük olasılıkla izlemeyi etkileyen açısına göre farklılık gösterir. Yepyeni bir otomobil düşünün. Bu arada dolaşdığınızda açık bir şekilde yansıtır ve taşırken farklı nesne nesneleri görürsünüz. İzleyicide, yüzeyde yansıtılan farklı nesneler değişen bir ortamı temsil eder ve cihaz izlemeyi kaybeder.

Daha az parçalı nesneler izlemek daha kolay.

### <a name="wi-fi-fingerprint-considerations"></a>Parmak izi Wi-Fi konuları

Wi-Fi etkinleştirildiği sürece eşleme verileri, gerçek bir WiFi ağına/yönlendiriciye bağlanmasa bile, bir Wi-Fi parmak iziyle bağıntılı olur. Wi-Fi Info olmadan Space ve hologragram tanınması biraz daha yavaş olabilir. Wi-Fi sinyalleri önemli ölçüde değişseniz, cihaz tamamen farklı bir alanda olduğunu düşünebilir.

Ağ kimliği (SSID veya MAC adresi gibi) Microsoft 'a gönderilmez ve tüm Wi-Fi başvuruları HoloLens yerel olarak tutulur.

## <a name="mapping-new-spaces"></a>Yeni boşlukları eşleme

Yeni bir boşluk girdiğinizde (veya var olan bir alanı yüklediğinizde), alanın üzerine yayan bir kafes grafik görürsünüz. Bu, cihazınızın sursörlerinizi eşlemediği anlamına gelir. HoloLens zaman içinde boşluk öğrenirken, boşluk eşlemek için ipuçları ve püf noktaları vardır.

## <a name="environment-management"></a>Ortam yönetimi

kullanıcıların hologratları "temizleyebileceği" HoloLens ve bir alanı "unutmasına" izin veren iki ayar vardır. ayarlar uygulamasındaki **Hologramlar ve ortamlarda** , ikinci ayar de ayarlar uygulamasında **gizlilik** altında görünür.  

1. **Yakın hologragram silin**. bu ayarı seçtiğinizde, HoloLens tüm bağlantılı hologramlar ve cihazın bulunduğu "geçerli alan" için tüm depolanan harita verilerini siler. Aynı alana hologram yeniden yerleştirildiğinde, bu konum için veritabanında yeni bir harita bölümü oluşturulup depolanacak.

1. **Tüm hologramlar silin**. bu ayar seçildiğinde HoloLens tüm veri veritabanlarının tüm harita verilerini ve bağlantılı hologramlar silecektir. Herhangi bir hologragram yeniden keşfedilecek ve tüm hologram, veritabanında depolama Haritası bölümlerine yeni yerleştirilmesi gerekir.

## <a name="hologram-quality"></a>Hologram kalitesi

Hologramlar, ortamınız genelinde yüksek, düşük ve tüm çevresinde yerleştirilebilecek, ancak bunları gözlerinizin önünde bulunan bir [holographic çerçevesi](/windows/mixed-reality/holographic-frame) aracılığıyla görebileceksiniz. En iyi görünümü elde etmek için, tüm çerçeveyi görebilmeniz için cihazınızı ayarladığınızdan emin olun. Ve ortamınıza göz atın ve bunu inceleyin!

[hologramlar](/windows/mixed-reality/hologram) için net, net ve kararlı bir şekilde görünebilmeniz için HoloLens yalnızca sizin için ayarlanması gerekir. HoloLens ilk kez ayarladığınızda, bu işlem size kılavuzluk eden bir işlemdir. Daha sonra, hologram doğru görünmüyorsa veya çok sayıda hata görüyorsanız, ayarlamalar yapabilirsiniz.

Boşluk eşleştirmede boşluklar varsa, yakın hologramlar silmeyi ve boşluğu yeniden eşlemeyi deneyin.

### <a name="calibration"></a>Ayarları

Hologramlar, jaray veya titremesi ise veya hologramlar yerleştirilirken sorun yaşıyorsanız, denenecek ilk şey [ayar uygulamasıdır](hololens-calibration.md). Bu uygulama, HoloLens kullanırken herhangi bir rahatımız yaşsanız da yardımcı olabilir.

ayarlama uygulamasına ulaşmak için **Ayarlar**  >  **sistem**  >  **yardımcı programları**' na gidin. **Ayarlamayı aç** ' ı seçin ve yönergeleri izleyin.

başka birisi HoloLens kullanacaksa, cihaz kendileri için düzgün şekilde ayarlanabilmesi için önce ayarlama uygulamasını çalıştırmaları gerekir.

## <a name="temperature-and-regulatory-information"></a>Sıcaklık ve mevzuat bilgileri

[mevzuat bilgilerini HoloLens](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): sıcaklık aralığı, elden çıkarma, radyo ve TV girişimi hakkında bilgiler içerir.

[malzemelerde](https://www.microsoft.com/legal/compliance/materials-substances) "HoloLens" ayrıntılarına bakın ve > çevresel uyumluluk (PDF) konusunda 33 makalesine ulaşın.

Cihazınızı kullanırken izlenecek bazı yönergeler aşağıda verilmiştir:

1. Cihazı kullanmadan önce bir saat boyunca, cihazı sıcaklık aralığı içinde (bekleme veya kapalı) bir ortamda depolayın.
1. Cihaz, sıcaklık aralığı içindeki bir ortamda kullanın.
1. Cihaz iç kapatuşlarını kullanın.
1. Cihazı gölgede kullan; Hatta kapıları, Windows ya da ufuk ışıkları de doğrudan sunmaktan kaçının.
1. Yukarıdaki yönergeleri izlerseniz ancak beklenmeyen fazla Isıtma sorunlarıyla karşılaşırsanız, [geri bildirim](hololens-feedback.md)göndermek için aşağıdaki adımları izleyin. 
    1. Cihazınızda **tam** veya **isteğe bağlı** telemetrinin etkinleştirildiğinden emin olun. Etkin değilse etkinleştirin. 
    >[!CAUTION]
    > Telemetri, ısı olayları için geriye dönük olarak etkin değildir. aşırı Isıtma sırasında etkinleştirilmelidir veya gerekli veriler yakalanmaz.
    
    2. Isıtma sorununu yeniden oluşturun.
    3. Fazla Isıtma gerçekleştiği tarih ve saati dahil edin.
    4. [Geri bildirim](hololens-feedback.md)gönderin.

## <a name="see-also"></a>Ayrıca bkz.

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
- [Hologramlar](/windows/mixed-reality/hologram)
