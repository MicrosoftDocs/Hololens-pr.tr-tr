---
title: Durum ayrımı ve yalıtım
description: HoloLens 2 karma gerçeklik cihazındaki durum ayrımı, yalıtım, kod imzalama ve defender uygulamaları hakkında bilgi edinebilirsiniz.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: güvenlik, hololens, State separation, State separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380258"
---
# <a name="state-separation-and-isolation"></a>Durum ayrımı ve yalıtım

Durum ayrımı ve yalıtımı, Hololens 2 işletim sisteminin kritik bölümlerini değişmeye karşı korur( işletim sisteminin güvenilir bir durumda önyüklensin için gerekenler gibi). Yalıtım teknolojisiyle güvenilmeyen uygulamalar, sistem güvenliğini etkilemelerini engellemek için yalıtılmış bir korumalı alan ortamına taşınır.

## <a name="state-separation"></a>Durum ayrımı

HoloLens 2'de durum ayrımı, güvenlik ve hizmet kullanılabilirliğini (güncelleştirme) önemli ölçüde artırır ve uygulama verilerinizin korunmasına yardımcı olur.  Durum ayrımı aşağıdaki gibi çalışır:
  * Çekirdek işletim sistemi, çekirdek işletim sistemi biriminde (işletim sistemini güncelleştiren güvenilir veya doğrulanmış Microsoft işletim sistemi) depolanır.
  * İşletim sisteminin çalışma zamanında değiştirilebilir bölümleri (indirilebilir sürücüler ve yapılandırmalar gibi), verileri bölümleme ve güvenli, ayrı depolama konumlarında depolamak için daha fazla durum ayrımı kullanın.
  * Her güvenli depolama konumu, ilişkili farklı güvenlik ilkelerine sahiptir ve aşağıdaki bölümde ayrıntılı olarak açıklanmasıyla çeşitli güvenlik avantajları sunar.

## <a name="state-separation-benefits"></a>Durum ayrımı avantajları

  * Güvenlik: HoloLens 2'de öne çıkan durum ayrımı platform bütünlüğünü, kötü amaçlı yazılım dayanıklılığını ve kullanıcı veri korumasını önemli ölçüde artırır. İşletim sisteminin kontrol edilemez bir kısmını ayırıp salt okunur veya bütünlük korumalı hale soğutan durum ayrımı, kötü amaçlı yazılımların soğuk bir yeniden başlatma sırasında kalıcılığını son derece zorlaştırabilir. 
  * Güncelleştirmeler: HoloLens 2 ile temel işletim sistemi değiştirilmez hale geldi ve cihaza verilerin geri kalanından temiz bir şekilde ayrıldığında güncelleştirmeler basit ve güvenilir hale geldi.  Ayrıca durum ayrımı, önemli ölçüde daha hızlı güncelleştirmeler için önemli bir temel sağlar ve bu da işletim sisteminin tek adımda (atomik birim) değiştirilmesini sağlar.
  * Cihaz sıfırlama: HoloLens 2 sıfırlaması, dahili ve dış depolama konumları dahil olmak üzere cihazda kullanıcı tarafından oluşturulan verileri ve kullanıcı uygulama verilerini temizler. Geçerli işletim sistemi uygulamalarını ve güvenlik açısından kritik uygulamaları ve geçerli Microsoft ve OEM özelleştirilmiş uygulamalarını (Önceden Yüklenmiş) korur. Bu Önceden Yüklenmiş uygulamalar, sıfırlama tamamlandıktan sonra cihazda yeniden kullanılabilir

### <a name="state-separation-states"></a>Durum ayrımı durumları

Durum ayrımı, işletim sisteminin yalnızca Microsoft tarafından güvenilen cihaz bileşenleri tarafından değiştirilene kadar devam etmesi ve yeniden başlatmalarda yalnızca yüksek değerli durumların kalıcı olması için izin verilir; diğer sistem durumu yalnızca önyükleme oturumu süresince mevcuttur ve yeniden başlatma sonrasında atılır. Durum ayrımı hızla cihazın fabrika durumuna geri döner. Windows Holographic for Business durumları şu ayrı kategorilere ayrılabilir:
  * Çekirdek işletim sistemi – Unalterable state
  * İşletim Sistemi Verileri – Değiştirilebilir durum 
  * Kullanıcı Verileri – Değiştirilebilir durum

Bu HoloLens 2 işletim durumları aşağıdaki bölümde açıklanmıştır.

#### <a name="core-operating-system"></a>Çekirdek işletim sistemi

Sabit bir durum, değiştirilemez olan yürütülebilir dosyalardan ve verilerden oluşur ve yalnızca güncelleştirme yüklemesi sırasında Microsoft tarafından değiştirilebilir. Çekirdek işletim sisteminin bu tür bir güncelleştirmesi sırasında, istenen en son işletim durumunu içeren yeni bir görüntü etkinleştirilir.
Yükseltilemez durum salt okunur (veya bütünlük korumalıdır) olarak işaretlenir ve yükseltilmiş ayrıcalıklara sahip kötü amaçlı yazılımların kalıcılığını engeller. Aşağıdaki yürütülebilir dosyalar ve veriler sabit durumda korunur:
  * Windows Holographic gelen kutusu sürücüleri
  * İşletim sistemi ikilileri
  * Windows gelen kutusu sürücüleri
  * Windows kayıt defteri kovanının (HKLM) içinde depolanan statik Windows Holographic ayarları
    * Örnek: HKLM, bir makinede yüklü uygulamalar için yapılandırma bilgilerini depolar. Ayrıca donanımı ve ilgili sürücüleri algılamak için bilgileri de depolar.
Bunları sabit (bütünlük ve salt okunur korumalı) durumda koruyarak, çekirdek işletim sisteminin her zaman güvenilir bir durumda ilk kez sinik olmasını sağlaruz. Buna ek olarak, bir cihaz sıfırlanırsa, cihazın yalnızca bu sabit bölümdeki bileşenlerde ilk kez değiştirilebilir. 

#### <a name="operating-system-data"></a>İşletim sistemi verileri 

Çalışma zamanında değiştirilebilir yürütülebilir dosyaların ve verilerin (ve işletim sistemi işlevi için kritik öneme sahip olmayan) atılabilir ve veriler bozuk veya tehlikeye atılmış olduğunda yeniden oluşturulabilir. Yüksek değerli bir değiştirilebilir durum, işletim sistemi tarafından kalıcı hale için işlevsel olarak gereklidir veya işletim sistemi kapatma işlemi sırasında ve/veya desteklenen Windows işletim sistemi ve cihaz senaryoları tarafından yeniden başlatmalarda kalıcı olması beklenir. Yüksek değerli tarifeli durum örnekleri:
  * Tüm kullanıcılar için konumu devre dışı bırakma gibi, IT Yöneticisi tarafından yapılandırılan genel cihaz ayarları.
  * Wi-fi ağ bağlantısı, veri cihazı tarafından anımsanan ağlara ve ilişkili bağlantı parolalarına erişin.
  * Ayarlar, günlükler de dahil olmak üzere kilitlenme bilgi dökümleri.
  * Yeni bulunan cihazlar için sürücüler isteğe bağlı olarak indirilir.
HoloLens 2'de yüksek değerli bir değiştirilebilir durum, işletim sistemi Veri güvenliği konumu üzerinde, diske kaydedilmiş bir dosya olarak veya kalıcı bir kayıt defteri kovanının içinde yer almaktadır.

#### <a name="user-data"></a>Kullanıcı verileri

Son durum kategorisi, UWP uygulamaları veya işletim sistemi tarafından üretilen veya kalıcı olan kullanıcı verilerini temsil eder. İndirilenler, Belgeler, Videolar, kullanıcı profilleri ve HKEY_CURRENT_USER gibi tüm bilinen kullanıcı klasörleri de bu konumda depolanır. Bu veriler düzgün kimlik bilgileri olmadan ayıklanır; Verilerinizin nasıl korundu hakkında daha fazla bilgi edinmek için bkz. [Şifreleme ve Veri Koruması.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Yalıtım

Bu dengeyi elde etmek için HoloLens 2'nin önyükleme, donanım denetimi ve oturum açma gibi birincil işlevler için kullanılan temel bir işletim sistemi vardır. Çekirdek işletim sisteminde çalışan yalnızca iki uygulama kümesi vardır: önceden yüklenmiş uygulamalar ve UWP uygulamaları.

## <a name="code-signing"></a>Kod imzalama

Dijital olarak imzalama kodu, yürütülebilir dosya ve betiklerin güvenilir bir kaynak tarafından imzalanmasından sonra değiştirilmediğinin kanıtlanmasına olanak sağlar ve bu sayede kimlik ve bütünlük sağlar. HoloLens 2'nin varsayılan olarak güvenen yetkilileri Microsoft ve Microsoft Store. IT [yöneticileri, ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) ve [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) CSP'leri aracılığıyla cihaza yeni sertifikalar ekleyebilir. Ek yüklenen veya iş yeri [uygulamalarına güvenmek için AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) [ilkesi de kullanabilirler.](https://docs.microsoft.com/intune/apps/lob-apps-windows) Sertifikalar, "Cihaz" kullanıyorsanız HKLM/Kök'te veya "Kullanıcı" kullanıyorsanız HKCU'da depolanan yerel makine sertifika depolamada yer almaktadır.

## <a name="defender-protections"></a>Defender korumaları
HoloLens 2 Microsoft hizmetleri kullanıcılara gelişmiş bir güvenlik düzeyi vermek için aşağıdaki özellikleri kullanır:

* [Defender SmartScreen,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) Windows Holographic'de işletim sistemi tarafından otomatik olarak etkinleştirilir ve kimlik avı ile kötü amaçlı yazılımlara ve kötü amaçlı olabilecek dosyaların Edge'e indirildikten sonra korunmasına karşı koruma sağlar. Kullanıcı tarafından kapatılamaz, ancak ilke aracılığıyla devre dışı bırakılabilir.

* [Defender Güvenlik](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) Duvarı, yetkisiz ağ trafiğinin cihazınıza ve cihazınıza akışını engeller. Varsayılan olarak etkindir ve yerel eylemler veya ilkeler aracılığıyla müşteri tarafından yapılandırılamaz. 

* [Windows Defender Denetimi:](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2, WDAC'ı destekler ve bu sayede, IT yöneticisinin cihaza uygulama denetim ilkeleri uygulamasına izin verir. Daha fazla bilgi için [MSFT Intune ile HoloLens 2 cihazlarında WDAC kullanmablandırabilirsiniz.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) 

IT yöneticileri Bu ilkeler aracılığıyla [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) ve tarayıcı davranışı aracılığıyla SmartScreen [davranışını yönetebilir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

