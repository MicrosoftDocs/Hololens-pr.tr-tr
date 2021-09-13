---
title: Durum ayrımı ve yalıtımı
description: HoloLens 2 karma gerçeklik cihazında durum ayrımı, yalıtım, kod imzalama ve defender uygulamaları hakkında bilgi edinin.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Güvenlik, Hololens, durum ayrımı, durum ayırma ve yalıtım, Hololens 2, hololens2 güvenlik, güvenlik genel bakış, güvenlik mimarisi, mimari, Hololens 2 mimarisi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036581"
---
# <a name="state-separation-and-isolation"></a>Durum ayrımı ve yalıtımı

Durum ayrımı ve yalıtım, Hololens 2 işletim sisteminin değişiklik yapması gereken kritik bölümlerini korur. Örneğin, işletim sisteminin güvenilir bir duruma önyükleme yapması için gerekli olanlar gibi. Yalıtım teknolojisiyle, güvenilir olmayan uygulamalar, sistem güvenliğini etkilememesini sağlamak için yalıtılmış bir korumalı alan ortamına taşınır.

## <a name="state-separation"></a>Durum ayrımı

HoloLens 2 büyük ölçüde üzerindeki durum ayrımı, güvenlik ve bakım (güncelleştirme) iyileştirir ve uygulama verilerinizin korunmasına yardımcı olur.  Durum ayrımı aşağıdaki gibi çalışmaktadır:
  * Çekirdek işletim sistemi çekirdek işletim sistemi biriminde saklanır (güvenilen veya doğrulanmış Microsoft işletim sistemini güncelleştiren).
  * İşletim sisteminin çalışma zamanında (indirilebilir sürücüler ve Konfigürasyonlar gibi) değiştirilebilecek kısımları, verileri bölümlemek için daha fazla durum ayrımı kullanır ve güvenli, ayrı depolama konumlarında depolar.
  * Her güvenli depolama konumunun ilişkili farklı güvenlik ilkeleri vardır ve aşağıdaki bölümde ayrıntılı güvenlik avantajları sunar.

## <a name="state-separation-benefits"></a>Durum ayrımı avantajları

  * güvenlik: HoloLens 2 ' de tanıtılan durum ayrımı, platform bütünlüğünü, kötü amaçlı yazılım dirençi ve kullanıcı veri korumasını önemli ölçüde geliştirir İşletim sisteminin geriye kalan bölümünü ayırarak ve salt okunurdur veya bütünlüğü korunuyorsa, durum ayrımı kötü amaçlı yazılımların soğuk bir yeniden başlatmada korunmasını son derece zorlaştırıyor. 
  * güncelleştirmeler: HoloLens 2 ile, çekirdek işletim sistemi değiştirilemeyen ve cihazdaki verilerin geri kalanından düzgün şekilde ayrıldıktan sonra güncelleştirmeler basit ve güvenilir hale gelir.  Ayrıca, durum ayrımı önemli bir şekilde daha hızlı güncelleştirmeler için, işletim sisteminin tek bir adımda (atomik birim) değiştirilmesine izin veren çok daha hızlı bir şekilde çalışır.
  * cihaz sıfırlama: HoloLens 2 sıfırlama, iç ve dış depolama konumları dahil olmak üzere cihazdaki kullanıcı tarafından oluşturulan verileri ve kullanıcı uygulama verilerini temizler. Geçerli işletim sistemi uygulamalarını ve kritik güvenlik uygulamalarını ve geçerli Microsoft ve OEM özelleştirilmiş uygulamalarını (önceden yüklenmiş) korur. Bu önceden yüklenmiş uygulamalar, sıfırlama işlemi tamamlandıktan sonra cihazda yeniden alınabilir

### <a name="state-separation-states"></a>Durum ayrımı durumları

Durum ayrımı, işletim sisteminin yalnızca Microsoft 'un güvenilir cihaz bileşenleri tarafından değiştirilebilmesini ve yalnızca yüksek değerli durumun yeniden başlatmalar genelinde kalıcı olmasına olanak sağlar; diğer sistem durumu yalnızca önyükleme oturumunun süresi boyunca bulunur ve bir yeniden başlatmadan sonra atılır. Durum ayrımı olması, cihazı fabrika durumuna geri döndürür. Windows Holographic for Business durumlar, bu farklı kategorilere ayrılabilir:
  * Çekirdek işletim sistemi – Tasmeyebilir durumu
  * İşletim sistemi verileri – diğer durum 
  * Kullanıcı verileri – bir daha fazla durum

bu HoloLens 2 işletim durumlarının her biri aşağıdaki bölümde açıklanmıştır.

#### <a name="core-operating-system"></a>Çekirdek işletim sistemi

Sabit bir durum, değişiklik kaldıramayacak yürütülebilir dosyalardan ve verilerden oluşur ve yalnızca güncelleştirmelerin yüklenmesi sırasında Microsoft tarafından değiştirilebilir. Bu tür bir çekirdek işletim sisteminin güncelleştirilmesi sırasında, istenen en son işletim durumunu içeren yeni bir görüntü etkinleştirilmiştir.
Geriye doğru olmayan durum salt okunurdur (veya başka türlü bütünlüğü korunan) olarak işaretlenir ve yükseltilmiş ayrıcalıklarla herhangi bir kötü amaçlı yazılımın kalıcılığını önler. Aşağıdaki yürütülebilir dosyalar ve veriler değişmez durumda korunur:
  * Windows Holographic gelen kutusu sürücüleri
  * İşletim sistemi ikilileri
  * Windows gelen kutusu sürücüleri
  * Windows kayıt defteri kovanında depolanan statik Windows Holographic ayarları (HKLM)
    * Örnek: HKLM bir makinede yüklü olan uygulamaların yapılandırma bilgilerini depolar. Ayrıca, donanımı ve ilgili sürücüleri algılayan bilgileri de depolar.
Bunları sabit (bütünlük ve salt okuma korumalı) durumunda koruyarak, çekirdek işletim sisteminin her zaman güvenilir bir duruma önyüklemesinde emin veriyoruz. Ayrıca, bir cihaz sıfırlandığında, cihazın yalnızca bu sabit bölümde olan bileşenlere önyüklendiğinden emin olabilirsiniz. 

#### <a name="operating-system-data"></a>İşletim sistemi verileri 

Çalışma zamanında değişebilen (ve işletim sistemi işlevi için kritik olmayan) yürütülebilir dosyaların ve verilerin atılacağını ve verilerin bozulmuş ya da tehlikeye düşmesi durumunda yoksayılabilir ve yeniden oluşturulabilir olduğunu unutmayın. yüksek değerli yeniden uygulanabilecek bir durum, işletim sistemi tarafından kalıcı hale getirilmesi ya da işletim sistemi kapatılırken ve/veya desteklenen Windows işletim sistemi ve cihaz senaryoları tarafından yeniden başlatmalar arasında kalıcı olması beklenmelidir. Yüksek değerli kesilebilir duruma örnek olarak şunlar verilebilir:
  * BT Yöneticisi tarafından, tüm kullanıcıların konumunu devre dışı bırakmak gibi genel cihaz ayarları yapılandırılmıştır.
  * Wi-Fi ağ bağlantısı erişimi veri-cihaz-anımsanan ağlar ve ilişkili bağlantı parolaları.
  * Ayarlar, günlükler dahil kilitlenme dökümleri.
  * Sürücüler yeni bulunan cihazlar için isteğe bağlı olarak indirilir.
HoloLens 2 ' deki yüksek değerli bir durum, disk üzerinde kaydedilmiş bir dosya olarak veya kalıcı bir kayıt defteri kovanında işletim sistemi veri güvenlik konumunda bulunur.

#### <a name="user-data"></a>Kullanıcı verileri

Son durum kategorisi, UWP uygulamaları veya işletim sistemi tarafından üretilen veya kalıcı Kullanıcı verilerini temsil eder. Indirmeler, belgeler, videolar, Kullanıcı profilleri ve HKEY_CURRENT_USER Hive gibi bilinen tüm Kullanıcı klasörleri de bu konumda depolanır. Bu veriler uygun kimlik bilgileri olmadan ayıklanamıyor; verilerinizin nasıl korunduğu hakkında daha fazla bilgi edinmek için bkz. [şifreleme ve veri koruma](security-encryption-data-protection.md).

##  <a name="isolation"></a>Yalıtım

bu dengeyi elde etmek için HoloLens 2 ' nin önyükleme, donanım denetimi, oturum açma gibi birincil işlevler için kullanılan bir çekirdek işletim sistemi vardır. Çekirdek işletim sistemi – önceden yüklenmiş uygulamalar ve UWP uygulamaları üzerinde çalışan yalnızca iki uygulama kümesi vardır.

## <a name="code-signing"></a>Kod imzalama

Kod dijital olarak imzalandığında, yürütülebilir dosyalar ve betikler güvenilir bir kaynak tarafından imzalandığından, bu nedenle özgünlük ve bütünlük sağlayan bir öğe için değişiklik yapılmasına izin verir. varsayılan olarak HoloLens 2 güveni olan yetkililer Microsoft ve Microsoft Store. BT yöneticileri, [Clientcertificateinstall](/windows/client-management/mdm/clientcertificateinstall-csp) ve [Rootcatrustedcertificates](/windows/client-management/mdm/rootcacertificates-csp) CSP 'leri aracılığıyla cihaza yeni sertifikalar ekleyebilir. Ayrıca, diğer dışarıdan yüklenen veya [Iş kolu uygulamalarına](/intune/apps/lob-apps-windows)güvenmek Için [AllowAllTrustedApps ilkesini](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) de kullanabilirler. Sertifikalar, "Kullanıcı" kullanılıyorsa "cihaz" veya HKCU ' da kullanılıyorsa, HKLM/root içinde depolanan yerel makine sertifika deposunda bulunur.

## <a name="defender-protections"></a>Defender korumaları
HoloLens 2 kullanıcılara gelişmiş bir güvenlik düzeyi sağlamak için Microsoft hizmetleri kullanır:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) , işletim sistemi tarafından Windows Holographic üzerinde otomatik olarak etkinleştirilir ve potansiyel olarak kötü amaçlı olabilecek dosyaların indirilme yanı sıra kimlik avından ve kötü amaçlı yazılımlara karşı koruma sağlar. Kullanıcı tarafından kapatılamaz, ancak ilke üzerinden devre dışı bırakılabilir.

* [Defender güvenlik duvarı](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) , yetkisiz ağ trafiğinin cihazınıza veya cihazınızdan akışını engeller. Varsayılan olarak etkindir ve yerel eylemler veya ilke aracılığıyla müşteri tarafından yapılandırılamaz. 

* [uygulama denetimi Windows Defender](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2, bt yöneticisinin cihaza uygulama denetim ilkeleri göndererek gönderebileceği WDAC 'yi destekler. daha fazla bilgi, [MSFT ıntune ile HoloLens 2 cihazlarda WDAC kullanma](/mem/intune/configuration/custom-profile-hololens)bölümünde bulunabilir. 

BT yöneticileri, [Bu ilkeler](/windows/client-management/mdm/policy-csps-supported-by-hololens2)aracılığıyla, [allowsmartscreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) ve tarayıcı davranışı aracılığıyla SmartScreen davranışını yönetebilir. 

