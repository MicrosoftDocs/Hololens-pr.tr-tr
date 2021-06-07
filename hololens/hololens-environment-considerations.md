---
title: HoloLens ortam konuları
description: Cihazı gözler ve ortamınız için en iyi hale getirirken HoloLens kullanarak mümkün olan en iyi deneyimi elde edin.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holographic çerçevesi, görünüm alanı, FOV, ayar, boşluk, ortam, nasıl yapılır, HoloLens, karma gerçeklik, karma gerçeklik kulaklıklar
ms.openlocfilehash: f4d3feb379a1f9815b940614fcd4b29b062f5cdc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380238"
---
# <a name="hololens-environment-considerations"></a>HoloLens ortam konuları

HoloLens, Holographic ' i "gerçek" Dünya ile karıştırır. Duvardaki bir holographic uygulama penceresi "askıda kalıyor", Tabletop üzerinde bir holographic Ballerina, tavşan arkadaşınızın baş başınızın en üstünde Oturar. Tam ekran bir oyun veya uygulama kullanırken, Holographic dünyası, ortaya çıkacak olan, ancak yine de alan etrafında görebilir ve taşıyabilirsiniz.

Yerleştirdiğiniz hologramlar, cihazınızı kapatsanız bile bunları yerleştirdiğiniz yere kalır.

## <a name="setting-up-an-environment"></a>Ortam ayarlama

HoloLens cihazları, bir alanda bulunan kullanıcıları *izleyerek* kararlı ve doğru hologragram nasıl yerleştirileceğini öğreniyor. Doğru izleme olmadan cihaz, ortamı veya içindeki kullanıcıyı anlamaz. Hologramlar yanlış yerlerde görünebilir, her seferinde aynı noktada görünmez veya hiç görünmez. Kullanıcıları izlemek için kullanılan veriler, *uzamsal haritada* temsil edilir.  

İzleme performansı, kullanıcının içinde bulunduğu ortam tarafından büyük ölçüde etkilenir ve bir ortamın tutarlı ve tutarlı izlemeye göre ayarlanması, bir bilim yerine bir sanatdır. Birçok farklı ortam faktörü, izlemeyi etkinleştirmek için birlikte kullanılır, ancak karma gerçeklik geliştiricisi olarak, daha iyi izleme için bir alan ayarlamayı aklınızda bulundurmanız gereken birkaç etken vardır.

### <a name="lighting"></a>Işık

Windows Mixed Reality, kullanıcının konumunu izlemek için görsel ışık kullanır. Bir ortam çok parlak olduğunda, kameralar doygun alabilir ve hiçbir şey görülmez. Ortam çok karanlık ise, kameralar yeterli bilgi çekemez ve hiçbir şey görülmez. Işıklandırma, sorunsuz bir şekilde ve yeterince parlak olmalıdır, ancak hafif bir şekilde göz atabilmelidir.  

Bir genel Dim alanında parlak ışık noktaları olan alanlar da sorunlu olduğundan, kameranın parlak boşlukların içine ve dışına geçerek ayarlanmasında de sorun vardır. Bu, cihazın "kayıp" olmasına neden olabilir ve açık olan değişikliğin konumdaki değişikliğe eşit olduğunu düşünün. Bir alandaki kararlı hafif düzeyler daha iyi izlemeye neden olur.  

Güneş zaman içinde önemli ölçüde farklılık gösterebileceğinden, her türlü açık hava ışığı da izleyicide kararsızlığa neden olabilir. Örneğin, yaz ve kış içindeki aynı alanda izleme büyük ölçüde farklı sonuçlar oluşturabilir, bu da ikinci iki açık ışık yılın farklı saatlerinde daha yüksek olabilir.  

Bir Luxmeter varsa, sürekli bir 500-1000 Lux, başlamak için iyi bir yerdir.  

#### <a name="types-of-lighting"></a>Aydınlatma türleri

Bir alanda farklı ışık türleri de izlemeyi etkileyebilir. It üzerinden çalışan AC elektrik ile hafif bulbs Pulse-AC sıklığı 50 Hz ise, hafif bir şekilde 50 Hz 'e sahiptir. İnsan için, bu pulun fark etmez. Ancak, HoloLens ' 30 fps, bu değişiklikleri görür. bazı kareler iyi bir şekilde aydınlatılır, bazıları kötü bir şekilde aydınlatılır ve kamera hafif bir şekilde telafi etmeye çalıştığında bu, bazıları aşırı gösterilir.  

ABD 'de, elektrik frekansı Standart 60 Hz 'dir. bu nedenle, ampullü, 60 HoloLens ile, Hololens ' 30 FPS kare hızına hizalanır. Ancak, birçok ülkede 50 Hz 'in bir AC frekansı standardı vardır; bu da bazı HoloLens çerçevelerinin pulu sırasında alınması ve başkalarının bu şekilde yapılmadığı anlamına gelir. Özellikle, Avrupa 'daki akıcı oressan ışıklandırma, sorunlara yol açabilecek şekilde bilinmektedir.  

Titreşme sorunlarını çözmeyi deneyebilmeniz gereken birkaç nokta vardır. Sıcaklık, ampul yaşı ve ısınma döngüleri, akıcı bir şekilde titreşme ve bulsan 'ları değiştirme konusunda yaygın nedenlerdir. Bulbs 'ları daha sıkı hale getirme ve geçerli çizlerin sabit olduğundan emin olma da yardımcı olabilir.  

### <a name="items-in-a-space"></a>Bir alandaki öğeler

HoloLens, bir boşluk içinde kendisini bulmak için, *Özellikler* olarak da bilinen benzersiz çevresel yer işaretlerini kullanır.  

Cihaz her yerde nerede olduğunu bilmenin bir yolu olmadığı için bir cihaz neredeyse hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde hiçbir şekilde izlenemez. Bir alanın duvarlara özellik eklemek, genellikle izlemeyi geliştirmenin iyi bir yoludur. Posterler, simgeler bir duvar, bitkiler, benzersiz nesneler veya diğer benzer öğelere tüm yardım. Karmaşık masası, iyi izlemeye yol gösteren bir ortama yönelik iyi bir örnektir. tek bir alanda birçok farklı özellik vardır.  

Ayrıca, aynı alanda benzersiz özellikler kullanın. Bir duvar üzerinde birden çok kez yinelenen poster, örneğin, HoloLens, ne kadar yinelenen postıt olduğunu bilmez. Benzersiz özellikler eklemenin yaygın bir yolu, bir alanın duvarlar ve tabanı üzerinde benzersiz, yinelenmeyen desenler oluşturmak için, maske bantlarının çizgilerini kullanmaktır.  

Kendinize sormanız gereken iyi bir soru: sahnenin yalnızca küçük bir miktarını görüyorsanız, kendinizi alana benzersiz bir şekilde buladınız mı? Aksi takdirde, cihazda sorun izleme de olur.

#### <a name="wormholes"></a>Solucan delikleri

Aynı olan iki alan veya bölgeseniz, izleyici aynı olduğunu düşünebilir. Bu, cihazın başka bir yerde düşünmeye karşı daha çarpıcı hale gelir. Bu tür yinelenen alan *solucan delikleri* çağrımız.  

Solucan boşluklarını engellemek için aynı alandaki aynı alanları engellemeye çalışın. Aynı alanlara bazen fabrika istasyonları, bir bina, sunucu rafları veya iş istasyonlarıyla ilgili pencereler dahil olabilir. Her bir benzer alana yönelik alanların etiketlenmesi veya benzersiz özelliklerin eklenmesi, solucan delikleri azaltmaya yardımcı olabilir.

### <a name="movement-in-a-space"></a>Bir boşluk içine taşıma

Ortamınız sürekli olarak kaydırılmışsa ve değişiyorsa, cihazın yerini almak için kararlı bir özelliği yoktur.  

Daha fazla hareketli nesneler, kişiler de dahil olmak üzere, izlemeyi kaybetmeniz daha kolay. Taşıyıcı köklerinin, farklı yapım durumlarında öğelerin ve bir alandaki çok sayıda kişinin, izleme sorunlarına neden olduğu bilinmektedir.

HoloLens, bu değişikliklere hızlıca uyum sağlayabilir, ancak yalnızca bu alan cihaza açık bir şekilde görünür. Genellikle, uzamsal haritada hatalara neden olabilecek, gerçeğe göre görülmeyen bölgeler. Örneğin, bir Kullanıcı bir arkadaşınızı tarar ve arkadaşınız odadan çıktığında onu kapatır. Kullanıcı artık boş alanı yeniden taraana kadar arkadaşınızın ' hayalet ' temsili uzamsal eşleme verilerinde kalır.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Kullanıcının alanındaki öğelere yakınlığı

Benzer şekilde, insanlara yakın nesnelere kadar odaklanamadığı gibi, nesneler kameralarına yakın olduğunda HoloLens Bir nesne her iki kamera ile de görülemeyecek kadar yakınsa veya bir nesne bir kamerayı engelliyorsa, cihaz, nesneyle ilgili izleme konusunda çok daha fazla soruna sahip olur.  

Kameralar bir nesneden 15 cm 'den daha yakın olmadığını görebilir.

### <a name="surfaces-in-a-space"></a>Boşluk içindeki yüzeyler

Kesin yansıtıcı yüzeyler büyük olasılıkla izlemeyi etkileyen açısına göre farklılık gösterir. Yepyeni bir otomobil düşünün. Bu arada dolaşdığınızda açık bir şekilde yansıtır ve taşırken farklı nesne nesneleri görürsünüz. İzleyicide, yüzeyde yansıtılan farklı nesneler değişen bir ortamı temsil eder ve cihaz izlemeyi kaybeder.

Daha az parçalı nesneler izlemek daha kolay.

### <a name="wi-fi-fingerprint-considerations"></a>Parmak izi Wi-Fi konuları

Wi-Fi etkinleştirildiği sürece eşleme verileri, gerçek bir WiFi ağına/yönlendiriciye bağlanmasa bile, bir Wi-Fi parmak iziyle bağıntılı olur. Wi-Fi Info olmadan Space ve hologragram tanınması biraz daha yavaş olabilir. Wi-Fi sinyalleri önemli ölçüde değişseniz, cihaz tamamen farklı bir alanda olduğunu düşünebilir.

Ağ kimliği (SSID veya MAC adresi gibi) Microsoft 'a gönderilmez ve tüm Wi-Fi başvuruları HoloLens üzerinde yerel olarak tutulur.

## <a name="mapping-new-spaces"></a>Yeni boşlukları eşleme

Yeni bir boşluk girdiğinizde (veya var olan bir alanı yüklediğinizde), alanın üzerine yayan bir kafes grafik görürsünüz. Bu, cihazınızın sursörlerinizi eşlemediği anlamına gelir. HoloLens zaman içinde boşluk öğrenirken, boşluk eşlemek için ipuçları ve püf noktaları vardır.

## <a name="environment-management"></a>Ortam yönetimi

Kullanıcıların hologratları "temizleyebileceği" ve HoloLens 'in bir alanı "unutmasına" olanak tanıyan iki ayar vardır. Ayarlar uygulamasındaki **Hologragram ve ortamlarda** bulunur, ikinci ayar de Ayarlar uygulamasında **Gizlilik** altında görünür.  

1. **Yakın hologragram silin**. Bu ayarı seçtiğinizde, HoloLens tüm bağlantılı hologragram ve cihazın bulunduğu "geçerli alan" için tüm depolanan harita verilerini siler. Aynı alana hologram yeniden yerleştirildiğinde, bu konum için veritabanında yeni bir harita bölümü oluşturulup depolanacak.

1. **Tüm hologramlar silin**. Bu ayar seçildiğinde, HoloLens tüm harita verilerini ve tüm boşluk veritabanlarının bağlantılı holograklarını silecektir. Herhangi bir hologragram yeniden keşfedilecek ve tüm hologram, veritabanında depolama Haritası bölümlerine yeni yerleştirilmesi gerekir.

## <a name="hologram-quality"></a>Hologram kalitesi

Hologragram, ortamınız geneline (yüksek, düşük ve tüm çevresinde) yerleştirilebilecek, ancak bunları gözlerinizin önünde bulunan bir [holographic çerçevesi](/windows/mixed-reality/holographic-frame) aracılığıyla görebileceksiniz. En iyi görünümü elde etmek için, tüm çerçeveyi görebilmeniz için cihazınızı ayarladığınızdan emin olun. Ve ortamınıza göz atın ve bunu inceleyin!

[Hologramelerinizi](/windows/mixed-reality/hologram) net, net ve kararlı bir şekilde görmek Için, Hololens 'nizin yalnızca sizin için ayarlanması gerekir. HoloLens 'nizi ilk kez ayarladığınızda, bu işlem size kılavuzluk eden bir işlemdir. Daha sonra, hologram doğru görünmüyorsa veya çok sayıda hata görüyorsanız, ayarlamalar yapabilirsiniz.

Boşluk eşleştirmede boşluklar varsa, yakın hologramlar silmeyi ve boşluğu yeniden eşlemeyi deneyin.

### <a name="calibration"></a>Ayarları

Hologramlar, jaray veya titremesi ise veya hologramlar yerleştirilirken sorun yaşıyorsanız, denenecek ilk şey [ayar uygulamasıdır](hololens-calibration.md). HoloLens'inizi kullanırken herhangi bir sorun yaşıyorsanız bu uygulama da yardımcı olabilir.

Ayarlama uygulamasına gitmek için Ayarlar Sistem Yardımcı  >    >  **Programları'nı seçin.** Ayarlamayı **Aç'ı** seçin ve yönergeleri izleyin.

HoloLens'inizi başka biri kullanacaksa cihazın düzgün şekilde ayarlanmış olması için önce Ayar uygulamasını çalıştırması gerekir.

## <a name="temperature-and-regulatory-information"></a>Sıcaklık ve mevzuat bilgileri

[HoloLens Mevzuat bilgileri:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Sıcaklık aralığı, atma, radyo ve TV girişimi ve daha fazlası hakkında bilgi içerir.

REACH Makalesi 33 Çevre Uyumluluğunda [Açıklanması](https://www.microsoft.com/legal/compliance/materials-substances) (PDF) > makalesinde "HoloLens" ile ilgili ayrıntılara bakın.

Cihazınızı kullanırken aşağıdaki yönergeleri izleyin:

1. Cihazı kullanmadan önce bir saat boyunca sıcaklık aralığı içinde (Beklemede veya Kapalı) bir ortamda depolar.
1. Cihazı sıcaklık aralığı içindeki bir ortamda kullanın.
1. Cihazı iç mekanda kullanma.
1. Cihazı gölgede kullanma; iç mekanda bile pencereler veya skylight'lar için doğrudan ışıklardan kaçının.
1. Yukarıdaki yönergeleri takip ediyorsanız ama beklenmeyen aşırı atlama sorunlarıyla karşılaşıyorsanız, Geri Bildirim göndermeden önce Tam / İsteğe bağlı telemetri'nin etkinleştirildiğinden [emin olun.](hololens-feedback.md) Aşırı atılan sorunları araştırmak için tam /isteğe bağlı telemetri gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
- [Hologram](/windows/mixed-reality/hologram)
