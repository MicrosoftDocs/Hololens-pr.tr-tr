---
title: sayfa Ayarlar görünürlüğü
description: HoloLens karışık gerçeklik cihazlarındaki pagevisibilitylist ve Guide için desteklenen urı 'ler listemize göre güncel tutun.
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
ms.openlocfilehash: d2747da37ae198f7a2c051593da3ffd4cb4476dfaa7a3078a7749fa1fc912ba2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665645"
---
# <a name="page-settings-visibility"></a>sayfa Ayarlar görünürlüğü

HoloLens cihazların yönetilebilir özelliklerinden biri, Ayarlar uygulamasında görülen sayfaları kısıtlamak için [Ayarlar/pagevisibilitylist ilkesini](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) kullanmaktır. pagevisibilitylist, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

> [!NOTE]
> bu özellik, HoloLens 2 cihazları için yalnızca [Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) veya üzeri sürümlerde kullanılabilir. Lütfen için kullanmayı planladığınız cihazların güncelleştirildiğinden emin olun.


## <a name="examples"></a>Örnekler
Sayfalar, yayımlanan URI 'lerin kısaltılmış bir sürümü tarafından tanımlanır. Bu, URI 'nin "MS-Settings:" öneki anlamına gelir.

Aşağıdaki örnek, yalnızca sırasıyla URI "Network-WiFi" ve "Bluetooth" içeren hakkında ve Bluetooth sayfalarına erişime izin veren bir ilkeyi göstermektedir:
- `showonly:network-wifi;network-proxy;bluetooth`

Aşağıdaki örnek, işletim sistemi sıfırlama sayfasını gizleyecek bir ilke gösterir:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Bu ilkeyi Intune aracılığıyla dağıtma

Intune 'a sağlanacak yapılandırma değerleri şunlardır:

- **Ad:** Profil için yönetici tarafından tercih edilen görünen ad.
- **OMA-URI:** Ayar sayfasının [kapsamı](/windows/client-management/mdm/policy-configuration-service-provider)dahil olmak üzere tam URI 'si. Bu sayfadaki Bu örnekler, `./Device` kapsamı kullanıyor.
- **Değer:** *Yalnızca* belirtilen sayfaların gizlenmesi veya gösterilmesi gerektiğini belirten bir dize değeri. Olası değerler şunlardır `hide:<pagename>` `showonly:<pagename>` . 
 
Birden çok sayfa, noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.

1. Özel bir **ilke** oluşturun.
1. **OMA-URI** ayarlandığında, tam kapsamlı URI girin. Örneğin: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Veri çekmeyi seçerken şunu seçin: **dize**
1. **Değer** belirtirken Yukarıdaki kılavuzu kullanın. Örneğin: **`showonly:network-wifi;network-proxy;bluetooth`** veya **`hide:reset`** 
> [!IMPORTANT]
> Özel cihaz yapılandırmasını cihazın içinde olmasını amaçladığı bir gruba atadığınızdan emin olun. Bu adım gerçekleştirilmediğinden, ilke gönderilir ancak uygulanmaz.

ıntune grupları ve cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [HoloLens MDM yapılandırması](hololens-mdm-configure.md) .


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Bu ilkeyi bir sağlama paketi aracılığıyla dağıtma

bunlar, Windows yapılandırma tasarımcısı 'nda belirtilecektir yapılandırma değerlerdir:

**Değer:** *Yalnızca* belirtilen sayfaların gizlenmesi veya gösterilmesi gerektiğini belirten bir dize değeri. Olası değerler şunlardır `hide:<pagename>` `showonly:<pagename>` . Birden çok sayfa, noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.


1. Windows yapılandırma tasarımcısında paketinizi oluştururken **ilkeler > Ayarlar > pagevisibilitylist** ' e gidin
1. Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Sağlama paketinizi dışarı aktarın.
1. Paketi cihazınıza uygulayın.
bir sağlama paketini oluşturma ve uygulama hakkında tam ayrıntılar için [HoloLens sağlama sayfasını](hololens-provisioning.md)ziyaret edin.


seçtiğiniz yöntemden bağımsız olarak cihazınız artık değişiklikleri almalıdır ve kullanıcılar aşağıdaki Ayarlar uygulamayla sunulacaktır.

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

Ayarlar uygulama sayfalarını kendi sayfa seçiminizi gösterecek veya gizleyecek şekilde yapılandırmak için, HoloLens 'de bulunan Ayarlar urı 'lere göz atın.

## <a name="settings-uris"></a>Ayarlar Þ

HoloLens cihazların ve Windows 10 cihazların Ayarlar uygulamasında farklı bir sayfa seçimi vardır. Bu sayfada yalnızca HoloLens var olan ayarları bulacaksınız.

### <a name="accounts"></a>Hesaplar
| Ayarlar sayfası           | URI                                            |
|-------------------------|------------------------------------------------|
| İş veya okul hesabına erişme | `workplace`                         |
| Iris kaydı       | `signinoptions-launchirisenrollment` |
| Oturum açma seçenekleri         | ` signinoptions `                   |

### <a name="apps"></a>Uygulamalar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Uygulamalar & Özellikler <sup>2</sup>     | `appsfeatures` <br> |
| Uygulamalar & Özellikler > Gelişmiş Seçenekler <sup>2</sup>     | `appsfeatures-app` <br> |
| uygulamalar & özellikler > çevrimdışı Haritalar <sup>2</sup>     | `maps-maps` <br> |
| uygulamalar & özellikler > çevrimdışı Haritalar > indirme haritaları <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Cihazlar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Fare <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Gizlilik
| Ayarlar sayfası            | URI                                             |
|--------------------------|-------------------------------------------------|
| Hesap bilgileri             | `privacy-accountinfo`              |
| Uygulama Tanılama        | `privacy-appdiagnostics`              |
| Arka plan uygulamaları        | `privacy-backgroundapps`              |
| Takvim                 | `privacy-calendar`                    |
| Arama geçmişi             | `privacy-callhistory`                 |
| Kamera                   | `privacy-webcam`                      |
| Kişiler                 | `privacy-contacts`                    |
| Tanılama & geri bildirimi | `privacy-feedback`                    |
| Belgeler                | `privacy-documents`                   |
| E-posta                    | `privacy-email`                       |
| Dosya sistemi              | `privacy-broadfilesystemaccess`       |
| Genel <sup>2</sup>             | `privacy-general`       |
| Mürekkeple & yazma kişiselleştirme <sup>2</sup>             | `privacy-speechtyping`       |
| Konum                 | `privacy-location`                    |
| Mesajlaşma                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Hareket <sup>2</sup>               | `privacy-motion`                  |
| Bildirimler            | `privacy-notifications`               |
| Diğer cihazlar            | `privacy-customdevices`               |
| Resimler                 | `privacy-pictures`                    |
| Radyolara                   | `privacy-radios`                      |
| Ekran görüntüsü kenarlıkları <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Ekran görüntüleri ve uygulamalar <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Konuşma                   | `privacy-speech`                      |
| Görevler                    | `privacy-tasks`                       |
| Kullanıcı hareketleri           | `privacy-backgroundspatialperception` |
| Videolar                   | `privacy-videos`                      |
| Ses etkinleştirme       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Ağ ve İnternet
| Ayarlar sayfası | URI                              |
|---------------|----------------------------------|
| Uçak modu <sup>2</sup> | `network-airplanemode`        |
| Ara sunucu | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Sistem
| Ayarlar sayfası      | URI                                |
|--------------------|------------------------------------|
| Pil <sup>2</sup>           | `batterysaver`<br>|
| Pil <sup>2</sup>           | `batterysaver-settings`<br>|
| Renkler             | `colors`<br>`personalization-colors` |
| Hologramlar <sup>2</sup>  |  `holograms`  |
| <sup>2. Ayar</sup> |  `calibration` |
| Bildirimler & eylemleri  | `notifications`          |
| Paylaşılan Deneyimler | `crossdevice` 
| Ses <sup>2</sup>           | `sound`<br>|
| Ses > Uygulama birimi ve cihaz tercihi <sup>2</sup>           | `apps-volume`<br>|
| Ses > Ses cihazlarını yönetme <sup>2</sup>           | `sound-devices`<br>|
| Depolama            | `storagesense`           |
| Depolama > Sense <sup>2 Depolama yi Yapılandırma</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Saat & Dili
| Ayarlar sayfası | URI                                           |
|---------------|-----------------------------------------------|
| Tarih & saat <sup>2</sup> | `dateandtime`                  |
| Klavye <sup>2</sup> | `keyboard`                  |
| Dil <sup>2</sup> | `language`                  |
| Dil <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Dil      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region        | `regionformatting`                  |

### <a name="update--security"></a>Güncelleştirme & Güvenliği
| Ayarlar sayfası                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Gelişmiş Seçenekler                    | `windowsupdate-options`         |
| Kurtarma & <sup>2'ye sıfırlama</sup>      | `reset`         |
| Windows Insider Programı               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Güncelleştirme - Güncelleştirmeleri denetler | `windowsupdate-action`          |


- <sup>1</sup> - Windows Holographic sürüm 21H1'den önceki sürümler için, aşağıdaki iki URL sizi Gelişmiş seçenekler veya Seçenekler **sayfalarına** **gerçekten** götürmektedir; Yalnızca Güncelleştirme sayfasındaki ana Windows gösterir.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> - Windows Holographic 21H1 veya daha üst bir üzerinde kullanılabilir.


URL'lerin Windows 10 Ayarlar için lütfen başlatma ayarları [belgelerini ziyaret](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) edin.
