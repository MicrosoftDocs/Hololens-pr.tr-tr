---
title: HoloLens ortamıyla ilgili dikkat edilmesi gerekenler
description: HoloLens kullanarak mümkün olan en iyi deneyimi elde etmek için cihazı göz ve ortamınız için en iyi duruma getirme.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holografik çerçeve, görünüm alanı, fov, ayarlama, boşluklar, ortam, nasıl yapılanlar, HoloLens, karma gerçeklik, karma gerçeklik başlığı
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924358"
---
# <a name="hololens-environment-considerations"></a>HoloLens ortamıyla ilgili dikkat edilmesi gerekenler

HoloLens holografik dünyayı "gerçek" dünyayla karıştırarak çevrenize hologramlar yerleştiriyor. Holografik bir uygulama penceresi duvarda "askıda" takılıyor, masanın üzerinde holografik bir balerin döner, bilmeden arkadaşınızın kafasının üzerinde yer alır. Çevreleyici bir oyun veya uygulama kullanırken holografik dünya çevrenizi dolduracak şekilde yayılır ancak siz de alanı görebilir ve hareket ettirebilirsiniz.

Cihazınızı kapatsanız bile, konan hologramlar bunları koyarak kalır.

## <a name="setting-up-an-environment"></a>Ortam ayarlama

HoloLens cihazları, kullanıcıları bir alana takip etmek için kararlı ve doğru *hologramlar* nasıl ekleyeceklerini biliyor. Cihaz düzgün izleme olmadan ortamı veya içindeki kullanıcıyı anlamaz. Hologramlar yanlış yerlerde görünebilir, her zaman aynı yerde görünmez veya hiç görünmez. Kullanıcıları izlemek için kullanılan veriler uzamsal haritada *gösterilir.*  

İzleme performansı, kullanıcının içinde olduğu ortamdan büyük ölçüde etkilemektedir ve kararlı ve tutarlı bir izlemenin tetiklenmesini sağlamak için bir ortamı ayarlamak bir bilim değil bir sanattır. İzlemeye olanak sağlamak için birçok farklı çevresel faktör bir araya getirilmiştir, ancak Karma Gerçeklik geliştiricisi olarak daha iyi izleme için bir alan ayarlamak için göz alıcı çeşitli faktörler vardır.

### <a name="lighting"></a>Işık

Windows Mixed Reality konumunu izlemek için görsel ışığı kullanır. Ortam çok parlak olduğunda kameralar doygunluğa sahip olabilir ve hiçbir şey görülmez. Ortam çok koyusa kameralar yeterli bilgiyi alamiyor ve hiçbir şey görülemiyor. Aydınlatma, insanların hiç çaba olmadan göreceği kadar parlak olmalı ve ışık o kadar da parlak olmayabilir.  

Genel bir dim alanında parlak ışık noktalarının bulunduğu alanlar da sorunludur çünkü kameranın parlak alanların içinde ve dışında hareket etmek için ayarlanması gerekmektedir. Bu, cihazın "kaybolarak" neden olabilir ve ışık değişikliğinin konum değişikliğine eşit olduğunu düşünebilirsiniz. Bir alanda kararlı ışık düzeyleri daha iyi izleme sağlar.  

Güneş zaman içinde önemli ölçüde değişiklik gösterene kadar tüm dış mekan aydınlatmaları izleyicide yer alan bir değişkenlik durumuna da neden olabilir. Örneğin yaz mevsiminde aynı alanda izlemek ile yaz ayları arasında izlemek önemli ölçüde farklı sonuçlar üretebilir. Bunun sonucunda dışında ikinci el ışığı yılın farklı zamanlarında daha yüksek olabilir.  

Birmeter'ın varsa 500-1000 saat başlangıç yapmak için iyi bir yerdir.  

#### <a name="types-of-lighting"></a>Aydınlatma türleri

Bir alanda farklı ışık türleri de izlemeyi etkileyene kadar devam ediyor olabilir. Ac elektriğinin üzerinden geçen ampullerin darbesi- AC sıklığı 50Yik ise ışık darbesi 50Yık'ta olur. Bir insan için bu titreşim fark değil. Ancak HoloLens'in 30 saniyelik kamerası bu değişiklikleri görür. Bazı kareler iyi yanacaktır, bazıları kötü yanacaktır ve bazıları ışık darbelerini telafi etmeye çalıştığında aşırı açığa çıkar.  

ABD'de elektrik sıklığı standardı 60Hz' olduğu için ampul darbeleri HoloLens'in kare hızıyla uyumlu hale getirildi - 60 Pulse pulses, HoloLens'in 30 KARE kare hızıyla hizalanır. Ancak birçok ülkede AC frequency standardı 50Yik olarak kabul edilir ve bu da bazı HoloLens çerçevelerinin kalp atışları sırasında alınmayacak olduğu anlamına gelir. Özellikle Avrupa'daki dalgalı aydınlatmanın soruna neden olduğu biliniyordu.  

Titreşim sorunlarını çözmeye çalışabilirsiniz. Sıcaklık, ampul yaşı ve sıcaklama döngüleri, dalgalı titreşimin ve ampullerin değiştirilmesinin yaygın nedenleridir. Ampulleri sıkılaştırma ve geçerli çekmelerin sabit olduğundan emin olmak da yardımcı olabilir.  

### <a name="items-in-a-space"></a>Bir boşlukta öğeler

HoloLens, kendisini bir alanda bulmak için özellikler olarak *da bilinen* benzersiz ortam yer işaretleri kullanır.  

Cihazın, uzayın hangi alanında olduğunu bilmeye hiçbir yolu yoktur ve kötü bir özellikten neredeyse hiçbir zaman iz bindiri. Bir boşluğun duvarlarına özellik eklemek genellikle izlemeyi geliştirmenin iyi bir yolu olur. Posterler, duvara dokunan semboller, bitkilerin, benzersiz nesnelerin veya diğer benzer öğelerin hepsi yardımcı olur. Dağınık masa, iyi izlemeye yol açan bir ortama iyi bir örnektir. Tek bir alanda birçok farklı özellik vardır.  

Ayrıca, aynı alanda benzersiz özellikler kullanın. Örneğin, aynı poster bir duvar üzerinde birden çok kez tekrarlanır ve HoloLens, tekrarlanan posterlerden hangisine baktığı hakkında bilgi alamayacaksa cihaz karışıklığına neden olur. Benzersiz özellikler eklemenin yaygın yollarından biri, bir boşluğun duvarları ve zemini üzerinde benzersiz ve tekrarsız desenler oluşturmak için maskeleme bandı çizgilerini kullanmaktır.  

Kendinize sormanız gereken iyi bir soru: Sahnenin yalnızca küçük bir miktarını görmüş olursanız, alanda kendinizi benzersiz bir şekilde bulamaz mısınız? Yoksa, cihazın izleme sorunları da olabilir.

#### <a name="wormholes"></a>Wormholes

İki alanınız veya bölge aynı görünüyorsa izleyici bunların aynı olduğunu düşünmektedir. Bu, cihazın başka bir yerde olduğunu düşünmesi için kendini kandırarak sonuç verir. Bu tür yinelenen alanlar *wormholes olarak çağrılır.*  

Wormhole'ları önlemek için aynı alanda aynı alanları önlemeyi deneyin. Aynı alanlar bazen fabrika istasyonlarını, bina pencerelerini, sunucu raflarını veya iş istasyonlarını içerebilir. Alanları etiketlemek veya benzer bir alana benzersiz özellikler eklemek, wormhole'ları hafifleterek yardımcı olabilir.

### <a name="movement-in-a-space"></a>Bir alanda hareket

Ortamınız sürekli değişiyorsa, cihazın bulunacak kararlı bir özelliği yoktur.  

İnsanlar da dahil olmak üzere bir alanda ne kadar çok hareketli nesne olursa izlemesi o kadar kolay olur. Taşıma bantlarının, farklı yapı durumlarında yer alan öğelerin ve bir alanda yer alan birçok kişinin takip sorunlarına neden olduğu biliniyordu.

HoloLens bu değişikliklere hızlı bir şekilde uyum sağlar ancak bu alan yalnızca cihaz tarafından açıkça görülebilir. Sık sık görülen alanlar gerçekliğin gerisinde olabilir ve bu da uzamsal haritada hatalara neden olabilir. Örneğin, bir kullanıcı bir arkadaşı tarar ve sonra arkadaş odayı terk ederken geri döner. Kullanıcının 'hayalet' temsili, kullanıcı artık boş alanı yeniden tarayana kadar uzamsal eşleme verisinde kalıcı olur.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Kullanıcının alanda öğelere yakınlığı

İnsanların gözlere yakın nesnelere nasıl iyi odaklanamalarına benzer şekilde HoloLens de nesneler kameraların yakınında olduğunda zorlar. Bir nesne iki kamerayla da görülemayacak kadar yakınsa veya bir nesne bir kamerayı engelliyorsa, cihazda nesneye karşı izlemeyle ilgili çok daha fazla sorun olur.  

Kameralar bir nesneden 15 cm'den daha yakın bir şey görmemektedir.

### <a name="surfaces-in-a-space"></a>Bir alanda yüzeyler

Güçlü yansıtıcı yüzeyler, izlemeyi etkileyen açıya bağlı olarak farklı görünüyor olabilir. Yepyeni bir araba düşünebilirsiniz. Etrafında hareket edersiniz, ışık yansır ve hareket ederken yüzeyde farklı nesneler görüyorsunuz. İzleyici için, yüzeye yansıyan farklı nesneler değişen bir ortamı temsil eder ve cihaz izlemeyi kaybeder.

Daha az parlak nesnelere karşı izlemek daha kolaydır.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi parmak izi ile ilgili dikkat edilmesi gerekenler

Bu Wi-Fi sürece, gerçek bir WiFi ağına/yönlendiriciye bağlı Wi-Fi bile harita verileri bir parmak iziyle ilişkilidir. Bu Wi-Fi olmadan, alan ve hologramlar biraz daha yavaş tanınıyor olabilir. Sinyaller Wi-Fi değişirse, cihaz tamamen farklı bir alanda olduğunu düşünebilirsiniz.

Ağ tanımlama (SSID veya MAC adresi gibi) Microsoft'a gönderilmez ve tüm Wi-Fi HoloLens'te yerel olarak tutulur.

## <a name="mapping-new-spaces"></a>Yeni alanları eşleme

Yeni bir boşluk (veya var olan bir alanı yükle) girersiniz, alana yayılmış bir örgü grafiğiyle karşınız olur. Bu, cihazınızın çevrenizi eşleyeni anlamına gelir. HoloLens zaman içinde bir alan öğrenirken, alanları eşlemeye dair ipuçları ve püf noktaları vardır.

## <a name="environment-management"></a>Ortam yönetimi

Kullanıcıların hologramları "temizlemesine" ve HoloLens'in bir alanı "unutması" için neden olan iki ayar vardır. Ayarlar uygulamasında **hologramlar ve ortamlar** vardır ve ikinci ayar ayarlar uygulamasında Gizlilik **altında** da görünür.  

1. **Yakındaki hologramları silin.** Bu ayarı seçerek HoloLens, cihazın bulunduğu "geçerli alan" için tüm sabitli hologramları ve depolanmış harita verilerini siler. Hologramlar aynı alana yeniden yerleştirilsin diye yeni bir harita bölümü oluşturulur ve bu konum için veritabanında depolanır.

1. **Tüm hologramları silin.** Bu ayarı seçerek HoloLens, boşluk veritabanlarının tamamına tüm harita verilerini ve sabitli hologramları siler. Hiçbir hologram yeniden keşfedilmayacak ve tüm hologramların veritabanında harita bölümlerini yeniden depolamak için yeni yerleştirilleri gerekir.

## <a name="hologram-quality"></a>Hologram kalitesi

Hologramlar ortamınız genelinde (yüksek, düşük ve etrafınıza) yerleştirilse de, göz önünde bulunan [holografik](/windows/mixed-reality/holographic-frame) bir çerçeve aracılığıyla bunları bulabilirsiniz. En iyi görünümü elde etmek için cihazınızı çerçevenin tamamını görmek için ayardan emin olun. Ayrıca ortamınızı keşfetmekten çekinmeyin!

Hologramların [güzel,](/windows/mixed-reality/hologram) net ve kararlı olması için HoloLens'inizin sizin için ayarlanmış olması gerekir. HoloLens'inizi ilk kez ayar her zaman bu süreçte yönlendirmiş oluruz. Daha sonra hologramlar doğru görünmüyorsa veya çok sayıda hata görüyorsanız ayarlamalar da yapacaktır.

Eşleme alanlarıyla ilgili sorun varsa yakındaki hologramları silerek alanı yeniden eşlemeyi deneyin.

### <a name="calibration"></a>Kalibrasyon

Hologramların titreşimli veya shaky gibi görünüyorsa ya da hologram yerleştirme konusunda sorun varsa, denemeniz gereken ilk şey [Ayar uygulamasıdır.](hololens-calibration.md) HoloLens'inizi kullanırken herhangi bir sorun yaşıyorsanız bu uygulama da yardımcı olabilir.

Ayarlama uygulamasına gitmek için Ayarlar Sistem Yardımcı  >    >  **Programları'nı seçin.** Ayarlamayı **Aç'ı** seçin ve yönergeleri izleyin.

HoloLens'inizi başka biri kullanacaksa, cihazın kendileri için düzgün şekilde ayarlanmış olması için önce HoloLens uygulamasını çalıştırması gerekir.

## <a name="temperature-and-regulatory-information"></a>Sıcaklık ve mevzuat bilgileri

[HoloLens Mevzuat bilgileri:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Sıcaklık aralığı, atma, radyo ve TV girişimi ve daha fazlası hakkında bilgi içerir.

REACH Makalesi 33 Çevre Uyumluluğunda [Açıklanması](https://www.microsoft.com/legal/compliance/materials-substances) (PDF) > makalesinde "HoloLens" ile ilgili ayrıntılara bakın.

Cihazınızı kullanırken aşağıdaki yönergeleri izleyin:

1. Cihazı kullanmadan önce bir saat boyunca sıcaklık aralığı içinde (Beklemede veya Kapalı) bir ortamda depolar.
1. Cihazı sıcaklık aralığı içindeki bir ortamda kullanın.
1. Cihazı iç mekanda kullanma.
1. Cihazı gölgede kullanma; hatta iç mekanda pencereler veya skylight'lar olsa da doğrudan güneş ışığından kaçının.
1. Yukarıdaki yönergeleri takip ediyorsanız ancak beklenmeyen aşırı atlama sorunlarıyla karşılaşıyorsanız, Geri Bildirim'i gönderme için aşağıdaki adımları [izleyin.](hololens-feedback.md) 
    1. Cihazda **Tam veya** **İsteğe** Bağlı telemetri'nin etkinleştirildiğinden emin olun. Doğru değilse etkinleştirin. 
    >[!CAUTION]
    > Telemetri, termal olaylar için geçmişe dönük değildir; aşırıya atlama sırasında etkinleştirilmesi gerekir, yoksa gerekli veriler yakalanmaz.
    
    2. ısıtma sorunu yeniden üretin.
    3. Aşırı atlamanın meydana geldiği tarihi ve saati içerir.
    4. Geri [Bildirim gönderin.](hololens-feedback.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
- [Hologram](/windows/mixed-reality/hologram)
