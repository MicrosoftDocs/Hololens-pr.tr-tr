---
title: Sayfa Ayarlar Görünürlüğü
description: PageVisibilityList için desteklenen URI'ler listemizi ve karma gerçeklik cihazlarının HoloLens takip edin.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, atanan erişim, bilgi noktası, ayarlar sayfası
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 5ac3ff27085fd2f7c5bc1de0e461079a673bbb23
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637175"
---
# <a name="page-settings-visibility"></a>Sayfa Ayarlar Görünürlüğü

HoloLens cihazları için yönetilebilir özelliklerden biri, [Ayarlar/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ilkesi kullanarak Ayarlar uygulama içinde görülen sayfaları kısıtlamaktır. PageVisibilityList, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkedir.

> [!NOTE]
> Bu özellik yalnızca [Holographic 20H2 veya Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) veya daha yeni sürümlerde kullanılabilir HoloLens 2 cihazlar için kullanılabilir. Bunu kullanmayı niyetli cihazların güncelleştirilmiş olduğundan emin olun.


## <a name="examples"></a>Örnekler
Sayfalar, yayımlanmış URI'lerin kısaltılmış bir sürümüyle tanımlanır ve bu sürüm URI'den "ms-settings:" ön eki eksi değerdir.

Aşağıdaki örnekte, sırasıyla "network-wifi" ve "bluetooth" URI'sine sahip olan yalnızca hakkında ve Bluetooth sayfalarına erişime izin verecek bir ilke yer almaktadır:
- `showonly:network-wifi;network-proxy;bluetooth`

Aşağıdaki örnek, işletim sistemi sıfırlama sayfasını gizleyen bir ilkeyi göstermektedir:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Bu ilkeyi Intune aracılığıyla dağıtma

Bunlar, Intune'a sağlanmalıdır yapılandırma değerleridir:

- **Ad:** Profil için yöneticinin tercih ettiği görünen ad.
- **OMA-URI:** Kapsamı dahil olmak üzere ayar sayfasının tam [URI'sı.](/windows/client-management/mdm/policy-configuration-service-provider) Bu sayfada yer alan bu örnekler kapsamı `./Device` kullanıyor.
- **Değer:** Yalnızca belirtilen sayfaları gizlemeyi veya göstermeyi *belirten* bir dize değeri. Olası değerler ve `hide:<pagename>` `showonly:<pagename>` değerleridir. 
 
Birden çok sayfa noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.

1. Özel ilke **oluşturun.**
1. **OMA-URI'yi ayarlarken** tam kapsamlı URI'yi girin. Örneğin: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Veri seçiminizi şu şekilde seçin: **Dize**
1. Değer **belirtirken** yukarıdaki kılavuzu kullanın. Örneğin: **`showonly:network-wifi;network-proxy;bluetooth`** veya **`hide:reset`** 
> [!IMPORTANT]
> Özel cihaz yapılandırmasını cihazın içinde olması amaçlanan bir gruba atadığınızdan emin olun. Bu adım gerçekleştirilene kadar ilke uygulanır ancak uygulanmaz.

Intune HoloLens cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [MDM](hololens-mdm-configure.md) yapılandırmasını yapılandırma.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Bu ilkeyi Sağlama Paketi aracılığıyla dağıtma

Bunlar, Yapılandırma Tasarımcısı'nda Windows değerleridir:

**Değer:** Yalnızca belirtilen sayfaları gizlemeyi veya göstermeyi *belirten* bir dize değeri. Olası değerler ve `hide:<pagename>` `showonly:<pagename>` değerleridir. Birden çok sayfa noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.


1. Windows Configuration Designer'da paketinizi oluştururken İlkeler > Ayarlar > **PageVisibilityList'e gidin**
1. Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Sağlama Paketinizi dışarı aktarın.
1. Paketi cihazınıza uygulama.
Sağlama paketi oluşturma ve uygulama hakkında ayrıntılı bilgi için HoloLens [sayfasını ziyaret edin.](hololens-provisioning.md)


Seçilen yöntemden bağımsız olarak cihazınızın artık değişiklikleri alması gerekir ve kullanıcılara aşağıdaki Ayarlar sunulacaktır.

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

Uygulama sayfalarını Ayarlar kendi sayfa seçiminizi gösterecek veya gizleyişini yapılandıracak şekilde yapılandırmak için, Ayarlar URL'leri HoloLens.

## <a name="settings-uris"></a>Ayarlar Urı

HoloLens ve Windows 10 cihazlarda, uygulamanın içinde farklı sayfa Ayarlar vardır. Bu sayfada yalnızca bu sayfada mevcut olan ayarları HoloLens.

### <a name="accounts"></a>Hesaplar
| Ayarlar sayfası           | URI                                            |
|-------------------------|------------------------------------------------|
| İş veya okul hesabına erişme | `workplace`                         |
| Iris Kaydı       | `signinoptions-launchirisenrollment` |
| Oturum Açma Seçenekleri         | ` signinoptions `                   |

### <a name="apps"></a>Uygulamalar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Uygulamalar & özellikleri <sup>2</sup>     | `appsfeatures` <br> |
| Gelişmiş & <sup>2</sup> > uygulamalar ve özellikler     | `appsfeatures-app` <br> |
| Çevrimdışı & <sup>2</sup> > uygulamalar Haritalar özellikleri     | `maps-maps` <br> |
| Çevrimdışı & haritalar > 2 Haritalar > uygulamalar <sup>ve özellikler</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Cihazlar
| Ayarlar sayfası | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Fare <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Gizlilik
| Ayarlar sayfası            | URI                                             |
|--------------------------|-------------------------------------------------|
| Hesap Bilgileri             | `privacy-accountinfo`              |
| Uygulama Tanılama        | `privacy-appdiagnostics`              |
| Arka Plan Uygulamaları        | `privacy-backgroundapps`              |
| Takvim                 | `privacy-calendar`                    |
| Çağrı Geçmişi             | `privacy-callhistory`                 |
| Kamera                   | `privacy-webcam`                      |
| Kişiler                 | `privacy-contacts`                    |
| Tanılama ve & Geri Bildirimi | `privacy-feedback`                    |
| Belgeler                | `privacy-documents`                   |
| E-posta                    | `privacy-email`                       |
| Dosya sistemi              | `privacy-broadfilesystemaccess`       |
| Genel <sup>2</sup>             | `privacy-general`       |
| Mürekkep & kişiselleştirme <sup>2</sup>             | `privacy-speechtyping`       |
| Konum                 | `privacy-location`                    |
| Mesajlaşma                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Hareket <sup>2</sup>               | `privacy-motion`                  |
| Bildirimler            | `privacy-notifications`               |
| Diğer cihazlar            | `privacy-customdevices`               |
| Resimler                 | `privacy-pictures`                    |
| Radyo                   | `privacy-radios`                      |
| Ekran görüntüsü <sup>kenarlıklar 2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Ekran görüntüleri ve uygulamalar <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Konuşma                   | `privacy-speech`                      |
| Görevler                    | `privacy-tasks`                       |
| Kullanıcı hareketleri           | `privacy-backgroundspatialperception` |
| Videolar                   | `privacy-videos`                      |
| Ses Etkinleştirme       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Ağ ve İnternet
| Ayarlar sayfası | URI                              |
|---------------|----------------------------------|
| Uçak Modu <sup>2</sup> | `network-airplanemode`        |
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


URL'lerin Windows 10 Ayarlar için lütfen başlatma ayarları [belgelerini ziyaret](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) edin.
