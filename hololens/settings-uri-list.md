---
title: Sayfa ayarları görünürlüğü
description: PageVisibilityList için desteklenen URI 'Ler listemize ve HoloLens karma gerçeklik cihazlarındaki kılavuza göre güncel tutun.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: Hololens, Hololens 2, atanan erişim, bilgi noktası, ayarlar sayfası
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924341"
---
# <a name="page-settings-visibility"></a>Sayfa ayarları görünürlüğü

HoloLens cihazlarına yönelik yönetilebilir özelliklerden biri, ayarlar uygulaması içinde görülen sayfaları kısıtlamak için [Settings/PageVisibilityList ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) kullanmaktır. PageVisibilityList, BT yöneticilerinin sistem ayarları uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilen bu hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

> [!NOTE]
> Bu özellik, HoloLens 2 cihazları için yalnızca [Windows holographic, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) veya üzeri sürümlerde ayrılabilir. Lütfen için kullanmayı planladığınız cihazların güncelleştirildiğinden emin olun.

Aşağıdaki örnek, yalnızca, sırasıyla URI "MS-Settings: Network-WiFi" ve "MS-Settings: Bluetooth" içeren hakkında ve Bluetooth sayfalarına erişime izin veren bir ilkeyi göstermektedir:
- `showonly:network-wifi;network-proxy;bluetooth`

Bunu bir sağlama paketi aracılığıyla ayarlamak için:

1. Windows yapılandırma Tasarımcısı 'nda paketinizi oluştururken **ilkeler > ayarlar > PageVisibilityList** ' e gidin
1. Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Sağlama paketinizi dışarı aktarın.
1. Paketi cihazınıza uygulayın.
Bir sağlama paketini oluşturma ve uygulama hakkında tam Ayrıntılar için [Bu sayfayı](hololens-provisioning.md)ziyaret edin.

Bu, OMA-URI kullanılarak Intune aracılığıyla yapılabilir:

1. Özel bir **ilke** oluşturun.
1. OMA-URI ayarlandığında dizeyi kullanın: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Veri çekmeyi seçerken şunu seçin: **dize**
1. Değer şunu yazarken kullanın: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Özel cihaz yapılandırmasını cihazın içinde olmasını amaçladığı bir gruba atadığınızdan emin olun.

Intune grupları ve cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [HoloLens MDM yapılandırması](hololens-mdm-configure.md) .

Seçtiğiniz yöntemden bağımsız olarak cihazınız artık değişiklikleri almalıdır ve kullanıcılar aşağıdaki ayarlar uygulamasıyla sunulacaktır.

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

Kendi sayfa seçiminizi göstermek veya gizlemek üzere ayarlar uygulama sayfalarını yapılandırmak için, HoloLens 'te bulunan ayarlar URI 'Lere göz atın.

## <a name="settings-uris"></a>Ayarlar URI 'Leri

HoloLens cihazlarının ve Windows 10 cihazlarının Ayarlar uygulamasında farklı bir sayfa seçimi vardır. Bu sayfada yalnızca HoloLens 'te var olan ayarları bulacaksınız.

### <a name="accounts"></a>Hesaplar
| Ayarlar sayfası           | URI                                            |
|-------------------------|------------------------------------------------|
| İş veya okul hesabına erişme | `ms-settings:workplace`                         |
| Iris kaydı       | `ms-settings:signinoptions-launchirisenrollment` |
| Oturum açma seçenekleri         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Uygulamalar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Uygulamalar & Özellikler<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Uygulamalar & Özellikler > Gelişmiş Seçenekler <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Uygulamalar & Özellikler > çevrimdışı haritalar <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Uygulamalar & Özellikler > çevrimdışı haritalar > Indirme haritaları <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Cihazlar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Fare <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Gizlilik
| Ayarlar sayfası            | URI                                             |
|--------------------------|-------------------------------------------------|
| Hesap bilgileri             | `ms-settings:privacy-accountinfo`              |
| Uygulama Tanılama        | `ms-settings:privacy-appdiagnostics`              |
| Arka plan uygulamaları        | `ms-settings:privacy-backgroundapps`              |
| Takvim                 | `ms-settings:privacy-calendar`                    |
| Arama geçmişi             | `ms-settings:privacy-callhistory`                 |
| Kamera                   | `ms-settings:privacy-webcam`                      |
| Kişiler                 | `ms-settings:privacy-contacts`                    |
| Tanılama & geri bildirimi | `ms-settings:privacy-feedback`                    |
| Belgeler                | `ms-settings:privacy-documents`                   |
| E-posta                    | `ms-settings:privacy-email`                       |
| Dosya sistemi              | `ms-settings:privacy-broadfilesystemaccess`       |
| Genel <sup>2</sup>             | `ms-settings:privacy-general`       |
| Mürekkeple & yazma kişiselleştirme <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Konum                 | `ms-settings:privacy-location`                    |
| Mesajlaşma                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| Hareket <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Bildirimler            | `ms-settings:privacy-notifications`               |
| Diğer cihazlar            | `ms-settings:privacy-customdevices`               |
| Resimler                 | `ms-settings:privacy-pictures`                    |
| Radyolara                   | `ms-settings:privacy-radios`                      |
| Ekran görüntüsü kenarlıkları <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Ekran görüntüleri ve uygulamalar <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Konuşma                   | `ms-settings:privacy-speech`                      |
| Görevler                    | `ms-settings:privacy-tasks`                       |
| Kullanıcı hareketleri           | `ms-settings:privacy-backgroundspatialperception` |
| Videolar                   | `ms-settings:privacy-videos`                      |
| Ses etkinleştirme       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Ağ ve İnternet
| Ayarlar sayfası | URI                              |
|---------------|----------------------------------|
| Uçak modu <sup>2</sup> | `ms-settings:network-airplanemode`        |
| Ara sunucu | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Sistem
| Ayarlar sayfası      | URI                                |
|--------------------|------------------------------------|
| Pil <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Pil <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Renkler             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologragram <sup>2</sup>  |  `ms-settings:holograms`  |
| Ayarlama <sup>2</sup> |  `ms-settings:calibration` |
| Bildirimler & eylemler  | `ms-settings:notifications`          |
| Paylaşılan deneyimler | `ms-settings:crossdevice` 
| Ses <sup>2</sup>           | `ms-settings:sound`<br>|
| Ses > uygulama hacmi ve cihaz tercihi <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Ses > ses cihazlarını yönetme <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Depolama            | `ms-settings:storagesense`           |
| Depolama > depolama algılaması yapılandırma <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Saat & Dili
| Ayarlar sayfası | URI                                           |
|---------------|-----------------------------------------------|
| Tarih & saat <sup>2</sup> | `ms-settings:dateandtime`                  |
| Klavye <sup>2</sup> | `ms-settings:keyboard`                  |
| Dil <sup>2</sup> | `ms-settings:language`                  |
| Dil <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Dil      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Güncelleştirme & Güvenliği
| Ayarlar sayfası                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Gelişmiş Seçenekler                    | `ms-settings:windowsupdate-options`         |
| Kurtarma & <sup>2'ye sıfırlama</sup>      | `ms-settings:reset`         |
| Windows Insider Programı               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update - Güncelleştirmeleri denetler | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> - Windows Holographic sürüm 21H1'den önceki sürümlerde, aşağıdaki iki URL sizi Gelişmiş seçenekler veya Seçenekler **sayfalarına** **gerçekten de** götürmektedir; yalnızca ana sayfayı Windows Update gösterir.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> - Windows Holographic 21H1 veya üzerinde kullanılabilir.


Ayarlar URL'Windows 10 tam listesi için lütfen başlatma ayarları [belgelerini ziyaret](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) edin.
