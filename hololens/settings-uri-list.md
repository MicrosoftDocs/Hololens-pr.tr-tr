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
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380213"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="43800-104">Sayfa ayarları görünürlüğü</span><span class="sxs-lookup"><span data-stu-id="43800-104">Page Settings Visibility</span></span>

<span data-ttu-id="43800-105">HoloLens cihazlarına yönelik yönetilebilir özelliklerden biri, ayarlar uygulaması içinde görülen sayfaları kısıtlamak için [Settings/PageVisibilityList ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="43800-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="43800-106">PageVisibilityList, BT yöneticilerinin sistem ayarları uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilen bu hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.</span><span class="sxs-lookup"><span data-stu-id="43800-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="43800-107">Bu özellik, HoloLens 2 cihazları için yalnızca [Windows holographic, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) veya üzeri sürümlerde ayrılabilir.</span><span class="sxs-lookup"><span data-stu-id="43800-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="43800-108">Lütfen için kullanmayı planladığınız cihazların güncelleştirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="43800-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="43800-109">Aşağıdaki örnek, yalnızca, sırasıyla URI "MS-Settings: Network-WiFi" ve "MS-Settings: Bluetooth" içeren hakkında ve Bluetooth sayfalarına erişime izin veren bir ilkeyi göstermektedir:</span><span class="sxs-lookup"><span data-stu-id="43800-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="43800-110">Bunu bir sağlama paketi aracılığıyla ayarlamak için:</span><span class="sxs-lookup"><span data-stu-id="43800-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="43800-111">Windows yapılandırma Tasarımcısı 'nda paketinizi oluştururken **ilkeler > ayarlar > PageVisibilityList** ' e gidin</span><span class="sxs-lookup"><span data-stu-id="43800-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="43800-112">Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="43800-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="43800-113">Sağlama paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="43800-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="43800-114">Paketi cihazınıza uygulayın.</span><span class="sxs-lookup"><span data-stu-id="43800-114">Apply the package to your device.</span></span>
<span data-ttu-id="43800-115">Bir sağlama paketini oluşturma ve uygulama hakkında tam Ayrıntılar için [Bu sayfayı](hololens-provisioning.md)ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="43800-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="43800-116">Bu, OMA-URI kullanılarak Intune aracılığıyla yapılabilir:</span><span class="sxs-lookup"><span data-stu-id="43800-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="43800-117">Özel bir **ilke** oluşturun.</span><span class="sxs-lookup"><span data-stu-id="43800-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="43800-118">OMA-URI ayarlandığında dizeyi kullanın: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="43800-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="43800-119">Veri çekmeyi seçerken şunu seçin: **dize**</span><span class="sxs-lookup"><span data-stu-id="43800-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="43800-120">Değer şunu yazarken kullanın: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="43800-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="43800-121">Özel cihaz yapılandırmasını cihazın içinde olmasını amaçladığı bir gruba atadığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="43800-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="43800-122">Intune grupları ve cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [HoloLens MDM yapılandırması](hololens-mdm-configure.md) .</span><span class="sxs-lookup"><span data-stu-id="43800-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="43800-123">Seçtiğiniz yöntemden bağımsız olarak cihazınız artık değişiklikleri almalıdır ve kullanıcılar aşağıdaki ayarlar uygulamasıyla sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="43800-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="43800-125">Kendi sayfa seçiminizi göstermek veya gizlemek üzere ayarlar uygulama sayfalarını yapılandırmak için, HoloLens 'te bulunan ayarlar URI 'Lere göz atın.</span><span class="sxs-lookup"><span data-stu-id="43800-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="43800-126">Ayarlar URI 'Leri</span><span class="sxs-lookup"><span data-stu-id="43800-126">Settings URIs</span></span>

<span data-ttu-id="43800-127">HoloLens cihazlarının ve Windows 10 cihazlarının Ayarlar uygulamasında farklı bir sayfa seçimi vardır.</span><span class="sxs-lookup"><span data-stu-id="43800-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="43800-128">Bu sayfada yalnızca HoloLens 'te var olan ayarları bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="43800-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="43800-129">Hesaplar</span><span class="sxs-lookup"><span data-stu-id="43800-129">Accounts</span></span>
| <span data-ttu-id="43800-130">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-130">Settings page</span></span>           | <span data-ttu-id="43800-131">URI</span><span class="sxs-lookup"><span data-stu-id="43800-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="43800-132">İş veya okul hesabına erişme</span><span class="sxs-lookup"><span data-stu-id="43800-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="43800-133">Iris kaydı</span><span class="sxs-lookup"><span data-stu-id="43800-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="43800-134">Oturum açma seçenekleri</span><span class="sxs-lookup"><span data-stu-id="43800-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="43800-135">Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="43800-135">Apps</span></span>
| <span data-ttu-id="43800-136">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-136">Settings page</span></span> | <span data-ttu-id="43800-137">URI</span><span class="sxs-lookup"><span data-stu-id="43800-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="43800-138">Uygulamalar & Özellikler<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="43800-139">Uygulamalar & Özellikler > Gelişmiş Seçenekler <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="43800-140">Uygulamalar & Özellikler > çevrimdışı haritalar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="43800-141">Uygulamalar & Özellikler > çevrimdışı haritalar > Indirme haritaları <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="43800-142">Cihazlar</span><span class="sxs-lookup"><span data-stu-id="43800-142">Devices</span></span>
| <span data-ttu-id="43800-143">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-143">Settings page</span></span> | <span data-ttu-id="43800-144">URI</span><span class="sxs-lookup"><span data-stu-id="43800-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="43800-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="43800-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="43800-146">Fare <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="43800-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="43800-148">Gizlilik</span><span class="sxs-lookup"><span data-stu-id="43800-148">Privacy</span></span>
| <span data-ttu-id="43800-149">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-149">Settings page</span></span>            | <span data-ttu-id="43800-150">URI</span><span class="sxs-lookup"><span data-stu-id="43800-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="43800-151">Hesap bilgileri</span><span class="sxs-lookup"><span data-stu-id="43800-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="43800-152">Uygulama Tanılama</span><span class="sxs-lookup"><span data-stu-id="43800-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="43800-153">Arka plan uygulamaları</span><span class="sxs-lookup"><span data-stu-id="43800-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="43800-154">Takvim</span><span class="sxs-lookup"><span data-stu-id="43800-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="43800-155">Arama geçmişi</span><span class="sxs-lookup"><span data-stu-id="43800-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="43800-156">Kamera</span><span class="sxs-lookup"><span data-stu-id="43800-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="43800-157">Kişiler</span><span class="sxs-lookup"><span data-stu-id="43800-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="43800-158">Tanılama & geri bildirimi</span><span class="sxs-lookup"><span data-stu-id="43800-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="43800-159">Belgeler</span><span class="sxs-lookup"><span data-stu-id="43800-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="43800-160">E-posta</span><span class="sxs-lookup"><span data-stu-id="43800-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="43800-161">Dosya sistemi</span><span class="sxs-lookup"><span data-stu-id="43800-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="43800-162">Genel <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="43800-163">Mürekkeple & yazma kişiselleştirme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="43800-164">Konum</span><span class="sxs-lookup"><span data-stu-id="43800-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="43800-165">Mesajlaşma</span><span class="sxs-lookup"><span data-stu-id="43800-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="43800-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="43800-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="43800-167">Hareket <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="43800-168">Bildirimler</span><span class="sxs-lookup"><span data-stu-id="43800-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="43800-169">Diğer cihazlar</span><span class="sxs-lookup"><span data-stu-id="43800-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="43800-170">Resimler</span><span class="sxs-lookup"><span data-stu-id="43800-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="43800-171">Radyolara</span><span class="sxs-lookup"><span data-stu-id="43800-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="43800-172">Ekran görüntüsü kenarlıkları <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="43800-173">Ekran görüntüleri ve uygulamalar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="43800-174">Konuşma</span><span class="sxs-lookup"><span data-stu-id="43800-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="43800-175">Görevler</span><span class="sxs-lookup"><span data-stu-id="43800-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="43800-176">Kullanıcı hareketleri</span><span class="sxs-lookup"><span data-stu-id="43800-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="43800-177">Videolar</span><span class="sxs-lookup"><span data-stu-id="43800-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="43800-178">Ses etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="43800-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="43800-179">Ağ ve İnternet</span><span class="sxs-lookup"><span data-stu-id="43800-179">Network & Internet</span></span>
| <span data-ttu-id="43800-180">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-180">Settings page</span></span> | <span data-ttu-id="43800-181">URI</span><span class="sxs-lookup"><span data-stu-id="43800-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="43800-182">Uçak modu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="43800-183">Ara sunucu</span><span class="sxs-lookup"><span data-stu-id="43800-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="43800-184">VPN</span><span class="sxs-lookup"><span data-stu-id="43800-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="43800-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="43800-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="43800-186">Sistem</span><span class="sxs-lookup"><span data-stu-id="43800-186">System</span></span>
| <span data-ttu-id="43800-187">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-187">Settings page</span></span>      | <span data-ttu-id="43800-188">URI</span><span class="sxs-lookup"><span data-stu-id="43800-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="43800-189">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="43800-190">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="43800-191">Renkler</span><span class="sxs-lookup"><span data-stu-id="43800-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="43800-192">Hologragram <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="43800-193">Ayarlama <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="43800-194">Bildirimler & eylemler</span><span class="sxs-lookup"><span data-stu-id="43800-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="43800-195">Paylaşılan deneyimler</span><span class="sxs-lookup"><span data-stu-id="43800-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="43800-196">Ses <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="43800-197">Ses > uygulama hacmi ve cihaz tercihi <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="43800-198">Ses > ses cihazlarını yönetme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="43800-199">Depolama</span><span class="sxs-lookup"><span data-stu-id="43800-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="43800-200">Depolama > Configue depolama algılaması <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="43800-201">Zaman & dili</span><span class="sxs-lookup"><span data-stu-id="43800-201">Time & Language</span></span>
| <span data-ttu-id="43800-202">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-202">Settings page</span></span> | <span data-ttu-id="43800-203">URI</span><span class="sxs-lookup"><span data-stu-id="43800-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="43800-204">Tarih & saat <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="43800-205">Klavye <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="43800-206">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="43800-207">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="43800-208">Dil</span><span class="sxs-lookup"><span data-stu-id="43800-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="43800-209">Region</span><span class="sxs-lookup"><span data-stu-id="43800-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="43800-210">& güvenliğini Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="43800-210">Update & Security</span></span>
| <span data-ttu-id="43800-211">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="43800-211">Settings page</span></span>                         | <span data-ttu-id="43800-212">URI</span><span class="sxs-lookup"><span data-stu-id="43800-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="43800-213">Gelişmiş Seçenekler</span><span class="sxs-lookup"><span data-stu-id="43800-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="43800-214">& kurtarmayı Sıfırla <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="43800-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="43800-215">Windows Insider Programı</span><span class="sxs-lookup"><span data-stu-id="43800-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="43800-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="43800-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="43800-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="43800-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="43800-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="43800-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="43800-219">Windows Update-güncelleştirmeleri denetler</span><span class="sxs-lookup"><span data-stu-id="43800-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="43800-220"><sup>1</sup> Windows holographic, sürüm 21H1 ' den önceki sürümlerde, aşağıdaki iki URI gerçekte sizi **Gelişmiş seçeneklere** veya **seçenek** sayfalarına götürür; yalnızca ana Windows Update sayfasını engeller veya gösterir.</span><span class="sxs-lookup"><span data-stu-id="43800-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="43800-221">MS-Settings: windowsupdate-seçenekler</span><span class="sxs-lookup"><span data-stu-id="43800-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="43800-222">MS-Settings: windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="43800-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="43800-223"><sup>2</sup> -Windows holographic 21H1 veya üzeri sürümlerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="43800-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="43800-224">Windows 10 ayarları URI 'lerinin tam listesi için lütfen [başlatma ayarları](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) belgelerini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="43800-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
