---
title: Sık sorulan güvenlik soruları
description: HoloLens karma gerçeklik cihazlarıyla ilgili sık sorulan güvenlik soruları ve yanıtları ile güncel kalın.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: Hololens, Windows Mixed Reality, güvenlik
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379154"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Sık sorulan HoloLens (1. Genel) güvenlik soruları

1. **HoloLens 1 teklifi hangi düzeyde veri korumasına sahiptir?**
    1. Bkz. [HoloLens (1. Genel) BitLocker şifrelemesi](hololens1-encryption.md)
1. **Ne tür bir kablosuz kullanılıyor?**
    1. 802.11 AC ve Bluetooth 4,1 LE
1. **Ne tür bir mimari eklendi?  Örneğin: nokta, kafes ya da başka bir şey var mı?**
    1. Wi-Fi, diğer kablosuz erişim noktalarıyla iletişim kurmak için altyapı modunda kullanılabilir.
    1. Müşteriler, müşterilerin uygulaması tarafından veya diğer Bluetooth cihazlarında destekliyorsa, birden çok HoloLens arasında eşler arası konuşabilmek için Bluetooth kullanılabilir.
1. **FCC ID nedir?**
    1. C3K1688
1. **Cihaz üzerinde hangi sıklık aralığı ve kanallar üzerinde çalışır ve yapılandırılabilir?**
    1. Wi-Fi: sıklık aralığı Kullanıcı tarafından yapılandırılabilir değildir ve kullanım ülkesi ' ne bağlıdır. ABD Wi-Fi hem 2,4 GHz (1-11) kanalları hem de 5 GHz (36-64, 100-165) kanalları kullanır.
    1. Bluetooth: Bluetooth Standart 2,4-2.48 GHz aralığını kullanır.
1. **Cihaz belirli sıklıklara izin verebilir veya bu frekansları engelleyebilir mi?**
    1. Bu, Kullanıcı/cihaz tarafından denetlenebilir değildir.
1. **Hem iletim hem de alma için güç düzeyi nedir? Ayarlanabilir mi? İşlem aralığı nedir?**
    1. Emisyonlarını test standartlarımızın [burada](https://fccid.io/C3K1688)bulabilirsiniz. İşlem aralığı, erişim noktasına ve ortama oldukça bağlıdır, ancak kabaca daha yüksek kaliteli telefonlardan, tabletlere veya bilgisayarlara eşdeğerdir.
1. **Normal işlem için vergi döngüsü/yaşam süresi nedir?**
    1. 2-3 saat etkin kullanım ve en fazla iki haftalık bekleme süresi
    1. Pil ömrü kullanılamıyor.
1. **Bir araç Aralık içinde olmadığında iletme ve alma davranışı nedir?**
    1. HoloLens iletme/alma standart Wi-Fi/Bluetooth düzenlerini izler. Kendi aralığının kenarından, girişin tamamen bağlantısı kesilene kadar kesik bir bağlantı olduğunu fark edeceksiniz, ancak aralığa geri döndüğünüzde hızlı bir şekilde yeniden bağlanmanız gerekir.
1. **Fit kare başına dağıtım yoğunluğu nedir?**
    1. Bu, Ağ altyapınıza bağımlıdır.
1. **Cihaz altyapıyı istemci olarak kullanabilir miyim?**
    1. Yes
1. **Hangi protokol kullanılıyor?**
    1. HoloLens herhangi bir özel protokol kullanmaz
1. **İşletim sistemi güncelleştirme sıklığı: HL için işletim sistemi güncelleştirmelerinin sıklığı nedir?  Bir küme zamanlaması var mı?  Microsoft, gerektiğinde güvenlik düzeltme ekleri yayımlar, vb.**
    1. Microsoft, HoloLens 'e Windows 10 ' da tam olarak aynı şekilde yapılan işletim sistemi güncelleştirmeleri sağlar. Yılda bir tane olmak üzere her yıl için genellikle iki önemli güncelleştirme vardır. HoloLens bir Windows cihazı olduğu için, güncelleştirme kavramı diğer tüm Windows cihazlarından ile aynıdır. Microsoft, gerektiğinde güvenlik düzeltme eklerini yayınlar ve diğer herhangi bir Windows cihazında yapılan kavramla aynı kavramı izler.
1. **İşletim sistemi sağlamlaştırma – işletim sistemini sağlamlaştırmak için hangi seçenekler vardır?  Gereksiz uygulamaları veya hizmetleri kaldırabilir veya kapatabilir miyim?**
    1. HoloLens bir akıllı telefon gibi davranır. Diğer modern Windows cihazlarına benzer. HoloLens, MobileIron, AirWatch veya SOTI gibi Microsoft Intune veya diğer modern cihaz yönetimi çözümleri tarafından yönetilebilir. Cihaza güvenlik ilkeleri koymak için bu yönetim sistemlerinde ayarlayabileceğiniz Ilkeler vardır ve cihazın güvenliğini sağlamak için bu Ilkeleri kullanabilirsiniz. İsterseniz gereksiz uygulamaları silme seçeneği de vardır.
1. **Yazılım uygulamaları nasıl yönetilecektir ve güncelleştirilir? Microsoft Mağazası 'nda yaşayan uygulamalar için hangi uygulamaların yüklendiğini ve uygulama güncelleştirme işlemini tanımlamak için hangi denetim gerekir?**
    1. HoloLens yalnızca Windows Mağazası aracılığıyla yazılım uygulamalarını alır. Yalnızca appx uygulama paketleri yüklenebilir ve bu, HoloLens 'in kullanımı için geliştirilmiştir. Bunu, HoloLens cihazını gösteren uygulamanın yanında küçük bir logo ile Microsoft Store görebilirsiniz. Mağaza uygulamalarının yönetimi üzerinde sahip olduğunuz herhangi bir denetim, HoloLens için de geçerlidir. Resmi mağaza veya iş için mağaza kavramını kullanabilirsiniz. Uygulamalar dışarıdan yüklenebilir (bir Windows cihazında uygulama yüklemek için el ile gerçekleştirilen işlem) veya bir MDM aracılığıyla yönetilebilir, böylece uygulamalar gerektiğinde otomatik olarak mağaza üzerinden alınır.
1. **HoloLens için depodaki uygulamalara yönelik güncelleştirmelerin sıklığı nedir?**
    1. Microsoft Store aynı kavram ve uygulamaları buradan izlediğimize göre, güncelleştirme çevrimi uygulamanın geliştiricisi tarafından belirlenir. Depodaki güncelleştirme mekanizmasını denetlemek için gereken tüm yönetim seçenekleri, HoloLens için de geçerlidir.
1. **HoloLens için güvenli bir önyükleme özelliği var mı?**
    1. Yes
1. **Cihazdan çevre birimi desteğini devre dışı bırakmak veya bağlantısını kesmek için bir özellik var mı?**
    1. Yes
1. **Cihazda bağlantı noktalarının kullanımını denetleme veya devre dışı bırakma olanağı var mı?**
    1. HoloLens yalnızca iki bağlantı noktası içerir (bir tane kulaklık için ve biri veya bilgisayarlara bağlanmak için). İşlev ve kurtarma nedeniyle bağlantı noktasını devre dışı bırakabilme özelliği yoktur.
1. **Virüsten koruma, uç nokta algılama, IP 'ler, uygulama denetimi izin listesi: virüsten koruma, uç nokta algılama, IP 'ler, uygulama denetimi izin verilenler listesi vb.**
    1. Windows holographic for Business (ticari paket), Windows Defender akıllı ekranını destekler. Bir virüsten koruma şirketi uygulamasını Evrensel Windows Platformu oluşturup yayımlayadiyse, HoloLens 'te indirilebilir. Mevcut olduğunda, bunu HoloLens için hiçbir şirket yapmadıysanız.
    1. Uygulamaların yalnızca belirli uygulamaların indirilebileceği, Microsoft kurumsal mağaza kullanılarak yapılmasına izin verme olanağı vardır. Ayrıca, MDM aracılığıyla cihazdaki belirli uygulamaların çalıştırılacağını veya hatta görünebileceğini de kilitleyemezsiniz.
1. **Cihazı, uzun bir süre çevrimdışı ise güncelleştirene kadar, üretim ağından karantinaya alabilir mi?  Ex. cihaz, bir dönem boyunca (altı ay) olmayan ve hiçbir güncelleştirme, düzeltme eki, vb. içermeyen bir çekmecede oturmuş.  Ağ üzerinde çalışmayı denediğinde, ağa katılmayı bilmemiz için önce başka bir ağ üzerinde güncelleştirme yapmanız gerektiğini ve daha sonra bu ağa işaret ederiz.**
    1. Bu, altyapı düzeyinde bir MDM ya da şirket içi sunucu tarafından yönetilebilen bir şeydir. Cihaz, belirtilen bir güncelleştirme sürümünü karşılamıyorsa uyumlu değil olarak işaretlenmiş olabilir.
1. **Microsoft, Microsoft 'un cihaz paylaşımı veya uzaktan destek için cihaza bağlanmasına izin veren bir arka kapı veya hizmetlere erişim içeriyor mu?**
    1. Hayır
1. **Güvenilen iletişim için bir PKI sertifikası üretilirken, bu cihazda yalnızca o cihaza özgü olduğunu ve bu cihaza özel olarak verildiğimiz veya cihazın kimliğine bürünmek için kullanılmamış olması için sertifikanın cihazda oluşturulmasını istiyoruz. Bu, HoloLens üzerinde mi doğru? Değilse, olası bir risk azaltma yoksa?**
    1. SCEP için CSR, cihazın kendisinde oluşturulur. Intune ve şirket içi SCEP Bağlayıcısı, istemciye gönderilen bir sınama dizesi ekleyerek ve doğrulayarak isteklerin güvenliğini sağlamaya yardımcı olur.
    1. HoloLens (1. gen ve 2. gen) bir TPM modülüne sahip olduğundan, bu sertifikalar TPM modülünde depolanır ve ayıklanamaz. Ayrıca, ayıklanamasa da, farklı cihazlarda Sertifika/anahtar kullanılamamasına neden olan farklı bir cihazda sınama dizeleri doğrulanamadı.
