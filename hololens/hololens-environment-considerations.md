---
title: HoloLens hakkında dikkat edilmesi gerekenler
description: Cihazı göz ve ortamınız HoloLens en iyi duruma getirmeniz için mümkün olan en iyi deneyimi elde edin.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holografik çerçeve, görünüm alanı, fov, ayarlama, boşluklar, ortam, nasıl HoloLens, karma gerçeklik, karma gerçeklik başlığı
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036340"
---
# <a name="hololens-environment-considerations"></a>HoloLens hakkında dikkat edilmesi gerekenler

HoloLens holografik dünyayı "gerçek" dünyayla karıştırarak çevrenize hologramlar yerleştirerek. Holografik bir uygulama penceresi duvarda "askıda" takılıyor, masanın üzerinde holografik bir balerinler takılıyor, atlı atlar, farkında olmayan arkadaşınızın kafasının üzerine takılıyor. Çevreleyici bir oyun veya uygulama kullanırken holografik dünya çevrenizi dolduracak şekilde yayılır ancak siz de alanı görebilir ve hareket ettirebilirsiniz.

Cihazınızı kapatsanız bile, konan hologramlar bunları koyarak kalır.

## <a name="setting-up-an-environment"></a>Ortam ayarlama

HoloLens cihazları, kullanıcıları bir alana takip ettirerek kararlı ve doğru *hologramlar* nasıl yer ala bilmektedir. Cihaz düzgün izleme olmadan ortamı veya içindeki kullanıcıyı anlamaz. Hologramlar yerde görünebilir, her zaman aynı yerde görünmez veya hiç görünmez. Kullanıcıları izlemek için kullanılan veriler uzamsal haritada *gösterilir.*  

İzleme performansı, kullanıcının içinde olduğu ortamdan büyük ölçüde etkilemektedir ve kararlı ve tutarlı bir izlemenin tetiklenmesini sağlamak için bir ortamı ayarlamak bir bilim değil bir sanattır. İzlemeyi etkinleştirmek için birçok farklı çevresel faktör bir araya getirilmiştir, ancak Karma Gerçeklik geliştiricisi olarak daha iyi izleme için bir alan ayarlamak için göz alıcı çeşitli faktörler vardır.

### <a name="lighting"></a>Işık

Windows Mixed Reality konumunu izlemek için görsel ışığı kullanır. Ortam çok parlak olduğunda kameralar doygunluğa sahip olabilir ve hiçbir şey görülmez. Ortam çok koyusa kameralar yeterli bilgiyi alamiyor ve hiçbir şey görülemiyor. Aydınlatma, insanların hiç çaba olmadan göreceği kadar parlak olmalı ve ışık o kadar da parlak olmayabilir.  

Genel bir dim alanında parlak ışık noktalarının bulunduğu alanlar da sorunludur çünkü kameranın parlak alanların içinde ve dışında hareket etmek için ayarlanması gerekmektedir. Bu, cihazın "kaybolarak" neden olabilir ve ışık değişikliğinin konum değişikliğine eşit olduğunu düşünebilirsiniz. Bir alanda kararlı ışık düzeyleri daha iyi izleme sağlar.  

Güneş zaman içinde önemli ölçüde değişiklik gösterene kadar tüm dış mekan aydınlatmaları izleyicide yer alan bir değişkenlik durumuna da neden olabilir. Örneğin yaz mevsiminde aynı alanda izlemek ile yaz ayları arasında izlemek önemli ölçüde farklı sonuçlar üretebilir. Bunun sonucunda dışında ikinci el ışığı yılın farklı zamanlarında daha yüksek olabilir.  

Birmeter'ın varsa 500-1000 saat başlangıç yapmak için iyi bir yerdir.  

#### <a name="types-of-lighting"></a>Aydınlatma türleri

Bir alanda farklı ışık türleri de izlemeyi etkileyene kadar devam ediyor olabilir. Ac elektriğinin üzerinden geçen ampullerin darbesi- AC sıklığı 50Yik ise ışık darbesi 50Yık'ta olur. Bir insan için bu titreşim fark değil. Ancak HoloLens 30 saniyelik kamera bu değişiklikleri görür. Bazı kareler iyi yanacaktır, bazıları kötü yanacaktır ve bazıları ışık darbelerini telafi etmeye çalıştığında aşırı açığa çıkar.  

ABD'de elektrik sıklığı standardı 60Yıl olduğu için ampul kalp atışları HoloLens'nin kare hızıyla uyumlu hale getirildi - 60 Pulse, HoloLens'nin 30 PULSE kare hızıyla hizalanır. Ancak, birçok ülkede AC frequency standardı 50Yiktir; bu da bazı HoloLens karelerin kalp atışları sırasında alınmayacak olduğu anlamına gelir. Özellikle Avrupa'daki dalgalı aydınlatmanın soruna neden olduğu biliniyordu.  

Titreşim sorunlarını çözmeye çalışabilirsiniz. Sıcaklık, ampul yaşı ve sıcaklama döngüleri, dalgalı titreşimin ve ampullerin değiştirilmesinin yaygın nedenleridir. Ampulleri sıkılaştırma ve geçerli çekimlerin sabit olduğundan emin olmak da yardımcı olabilir.  

### <a name="items-in-a-space"></a>Bir boşlukta öğeler

HoloLens, kendisini bir alanda bulmak için özellikler olarak da *bilinen* benzersiz ortam yer işaretleri kullanır.  

Cihazın, uzayın hangi alanında olduğunu bilmeye hiçbir yolu yoktur ve kötü bir özellikten neredeyse hiçbir zaman iz bindiri. Bir boşluğun duvarlarına özellik eklemek genellikle izlemeyi geliştirmenin iyi bir yolu olur. Posterler, duvara dokunan semboller, bitkilerin, benzersiz nesnelerin veya diğer benzer öğelerin hepsi yardımcı olur. Dağınık masa, iyi izlemeye yol açan bir ortama iyi bir örnektir. Tek bir alanda birçok farklı özellik vardır.  

Ayrıca, aynı alanda benzersiz özellikler kullanın. Aynı poster bir duvar üzerinde birden çok kez tekrarlanır. Örneğin, HoloLens tekrarlayan posterlerden hangilerine baktığı hakkında bilgi alamayacak şekilde cihaz karışıklığına neden olur. Benzersiz özellikler eklemenin yaygın yollarından biri, bir boşluğun duvarları ve zemini üzerinde benzersiz ve tekrarsız desenler oluşturmak için maskeleme bandı çizgilerini kullanmaktır.  

Kendinize sormanız gereken iyi bir soru: Sahnenin yalnızca küçük bir miktarını görmüş olursanız, alanda kendinizi benzersiz bir şekilde bulamaz mısınız? Yoksa, cihazın izleme sorunları da olabilir.

#### <a name="wormholes"></a>Wormholes

İki alanınız veya bölge aynı görünüyorsa izleyici bunların aynı olduğunu düşünmektedir. Bu, cihazın başka bir yerde olduğunu düşünmesi için kendini kandırarak sonuç verir. Bu tür yinelenen alanlar *wormholes olarak çağrılır.*  

Wormhole'ları önlemek için aynı alanda aynı alanları önlemeyi deneyin. Aynı alanlar bazen fabrika istasyonlarını, bir bina pencerelerini, sunucu raflarını veya iş istasyonlarını içerebilir. Alanları etiketlemek veya benzer bir alana benzersiz özellikler eklemek, wormhole'ları hafifleterek yardımcı olabilir.

### <a name="movement-in-a-space"></a>Bir alanda hareket

Ortamınız sürekli değişiyorsa, cihazın bulunacak kararlı bir özelliği yoktur.  

İnsanlar da dahil olmak üzere bir alanda ne kadar çok hareketli nesne olursa izlemesi o kadar kolay olur. Taşıma bantlarının, farklı yapı durumlarında yer alan öğelerin ve bir alanda yer alan birçok kişinin takip sorunlarına neden olduğu biliniyordu.

Bu HoloLens bu değişikliklere hızlı bir şekilde uyarlanabilir, ancak bu alan cihaza açıkça görünür olduğunda kullanılabilir. Sık sık görülen alanlar gerçekliğin gerisinde olabilir ve bu da uzamsal haritada hatalara neden olabilir. Örneğin, bir kullanıcı bir arkadaşı tarar ve sonra arkadaş odayı terk ederken geri döner. Kullanıcının 'hayalet' temsili, kullanıcı artık boş alanı yeniden tarayana kadar uzamsal eşleme verisinde kalıcı olur.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Kullanıcının alanda öğelere yakınlığı

İnsanların gözlere yakın nesnelere nasıl iyi odaklanamalarına benzer HoloLens nesneler kameralarına yakın olduğunda zorlar. Bir nesne iki kamerayla da görülemayacak kadar yakınsa veya bir nesne bir kamerayı engelliyorsa, cihazda nesneye karşı izlemeyle ilgili çok daha fazla sorun olur.  

Kameralar bir nesneden 15 cm'den daha yakın bir şey görmemektedir.

### <a name="surfaces-in-a-space"></a>Bir alanda yüzeyler

Güçlü yansıtıcı yüzeyler, izlemeyi etkileyen açıya bağlı olarak farklı görünüyor olabilir. Yepyeni bir araba düşünebilirsiniz. Etrafında hareket edersiniz, ışık yansır ve hareket ederken yüzeyde farklı nesneler görüyorsunuz. İzleyici için, yüzeye yansıyan farklı nesneler değişen bir ortamı temsil eder ve cihaz izlemeyi kaybeder.

Daha az parlak nesnelere karşı izlemek daha kolaydır.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi parmak izi ile ilgili dikkat edilmesi gerekenler

Bu Wi-Fi, gerçek bir WiFi ağına/yönlendiriciye bağlı Wi-Fi bile harita verileri bir parmak iziyle ilişkilidir. Bu Wi-Fi olmadan, alan ve hologramlar biraz daha yavaş tanınıyor olabilir. Sinyaller Wi-Fi ölçüde değişirse, cihaz tamamen farklı bir alanda olduğunu düşünebilirsiniz.

Ağ tanımlama (SSID veya MAC adresi gibi) Microsoft'a gönderilmez ve tüm Wi-Fi yerel olarak HoloLens.

## <a name="mapping-new-spaces"></a>Yeni alanları eşleme

Yeni bir boşluk (veya var olan bir alanı yükle) girersiniz, alana yayılmış bir örgü grafiğiyle karşınız olur. Bu, cihazınızın çevrenizi eşleyeni anlamına gelir. Bir HoloLens zaman içinde bir alan öğrenirken, alanları eşlemeye yardımcı olacak ipuçları ve püf noktaları vardır.

## <a name="environment-management"></a>Ortam yönetimi

Kullanıcıların hologramları "temizlemelerini" ve bir alanı "unutmalarını" HoloLens iki ayar vardır. Ayarlar uygulamasında **Hologramlar ortamlarda,** ikinci ayar da ayarlar uygulamasında Gizlilik **altında** görünür.  

1. **Yakındaki hologramları silin.** Bu ayarı seçerek HoloLens tüm sabitli hologramları ve cihazın bulunduğu "geçerli alan" için depolanan tüm harita verilerini siler. Hologramlar aynı alana yeniden yerleştirilsin diye yeni bir harita bölümü oluşturulur ve bu konum için veritabanında depolanır.

1. **Tüm hologramları silin.** Bu ayarı seçerek HoloLens tüm boşluk veritabanlarında TÜM harita verilerini ve sabitli hologramları silersiniz. Hiçbir hologram yeniden keşfedilmayacak ve tüm hologramların veritabanında harita bölümlerini yeniden depolamak için yeni yerleştirilleri gerekir.

## <a name="hologram-quality"></a>Hologram kalitesi

Hologramlar ortamınız genelinde (yüksek, düşük ve her yerde) yer açabilirsiniz ancak [](/windows/mixed-reality/holographic-frame) bunları göz önünde bulunan holografik bir çerçeve aracılığıyla da bulabilirsiniz. En iyi görünümü elde etmek için cihazınızı çerçevenin tamamını görmek için ayardan emin olun. Ayrıca ortamınızı keşfetmekten çekinmeyin!

Hologramların [güzel,](/windows/mixed-reality/hologram) net ve kararlı bir şekilde HoloLens tam olarak sizin için ayarlanmış olması gerekir. Kullanıcılarınızı ilk kez HoloLens, bu süreçte size yol açık olur. Daha sonra hologramlar doğru görünmüyorsa veya çok sayıda hata görüyorsanız ayarlamalar da yapacaktır.

Eşleme alanlarıyla ilgili sorun varsa yakındaki hologramları silerek alanı yeniden eşlemeyi deneyin.

### <a name="calibration"></a>Kalibrasyon

Hologramların titreşimli veya shaky gibi görünüyorsa ya da hologram yerleştirme konusunda sorun varsa, denemeniz gereken ilk şey [Ayar uygulamasıdır.](hololens-calibration.md) Bu uygulama, uygulamanın kullanımı sırasında herhangi bir sorun yaşıyorsanız HoloLens.

Ayarlama uygulamasına gitmek için Sistem Yardımcı **Programları'Ayarlar**  >    >  **gidin.** Ayarlamayı **Aç'ı** seçin ve yönergeleri izleyin.

Cihazınızı başka biri HoloLens cihaz için düzgün şekilde ayarlansın diye önce Ayar uygulamasını çalıştırması gerekir.

## <a name="temperature-and-regulatory-information"></a>Sıcaklık ve mevzuat bilgileri

[HoloLens:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Sıcaklık aralığı, atma, radyo ve TV girişimi ve daha fazlası hakkında bilgi içerir.

REACH Makalesi 33 HoloLens (PDF) [makale](https://www.microsoft.com/legal/compliance/materials-substances) > sinde "HoloLens" ile ilgili ayrıntılara bakın.

Cihazınızı kullanırken aşağıdaki yönergeleri izleyin:

1. Cihazı kullanmadan önce bir saat boyunca sıcaklık aralığı içinde (Beklemede veya Kapalı) bir ortamda depolar.
1. Cihazı sıcaklık aralığı içindeki bir ortamda kullanın.
1. Cihazı iç mekanda kullanma.
1. Cihazı gölgede kullanma; hatta iç mekanda pencereler veya skylight'lar olsa da doğrudan güneş ışığından kaçının.
1. Yukarıdaki yönergeleri takip ediyorsanız ancak beklenmeyen aşırı atlama sorunlarıyla karşılaşıyorsanız, Geri Bildirim'i gönderme için aşağıdaki adımları [izleyin.](hololens-feedback.md) 
    1. Cihazda **Tam veya** **İsteğe** Bağlı telemetri'nin etkinleştirildiğinden emin olun. Doğru değilse etkinleştirin. 
    >[!CAUTION]
    > Telemetri, termik olaylar için geçmişe dönük değildir. Aşırıya atılama sırasında etkinleştirilmesi gerekir, yoksa gerekli veriler yakalanmaz.
    
    2. ısıtma sorunu yeniden üretin.
    3. Aşırı atlamanın meydana geldiği tarihi ve saati içerir.
    4. Geri [Bildirim gönderin.](hololens-feedback.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Uzamsal eşleme tasarımı](/windows/mixed-reality/spatial-mapping)
- [Hologramlar](/windows/mixed-reality/hologram)
