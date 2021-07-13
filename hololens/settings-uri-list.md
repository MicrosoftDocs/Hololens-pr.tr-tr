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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639242"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="e023b-104">sayfa Ayarlar görünürlüğü</span><span class="sxs-lookup"><span data-stu-id="e023b-104">Page Settings Visibility</span></span>

<span data-ttu-id="e023b-105">HoloLens cihazların yönetilebilir özelliklerinden biri, Ayarlar uygulamasında görülen sayfaları kısıtlamak için [Ayarlar/pagevisibilitylist ilkesini](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="e023b-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="e023b-106">pagevisibilitylist, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.</span><span class="sxs-lookup"><span data-stu-id="e023b-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="e023b-107">bu özellik, HoloLens 2 cihazları için yalnızca [Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) veya üzeri sürümlerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e023b-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="e023b-108">Lütfen için kullanmayı planladığınız cihazların güncelleştirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="e023b-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="e023b-109">Örnekler</span><span class="sxs-lookup"><span data-stu-id="e023b-109">Examples</span></span>
<span data-ttu-id="e023b-110">Sayfalar, yayımlanan URI 'lerin kısaltılmış bir sürümü tarafından tanımlanır. Bu, URI 'nin "MS-Settings:" öneki anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="e023b-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="e023b-111">Aşağıdaki örnek, yalnızca sırasıyla URI "Network-WiFi" ve "Bluetooth" içeren hakkında ve Bluetooth sayfalarına erişime izin veren bir ilkeyi göstermektedir:</span><span class="sxs-lookup"><span data-stu-id="e023b-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="e023b-112">Aşağıdaki örnek, işletim sistemi sıfırlama sayfasını gizleyecek bir ilke gösterir:</span><span class="sxs-lookup"><span data-stu-id="e023b-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="e023b-113">Bu ilkeyi Intune aracılığıyla dağıtma</span><span class="sxs-lookup"><span data-stu-id="e023b-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="e023b-114">Intune 'a sağlanacak yapılandırma değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="e023b-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="e023b-115">**Ad:** Profil için yönetici tarafından tercih edilen görünen ad.</span><span class="sxs-lookup"><span data-stu-id="e023b-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="e023b-116">**OMA-URI:** Ayar sayfasının [kapsamı](/windows/client-management/mdm/policy-configuration-service-provider)dahil olmak üzere tam URI 'si.</span><span class="sxs-lookup"><span data-stu-id="e023b-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="e023b-117">Bu sayfadaki Bu örnekler, `./Device` kapsamı kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="e023b-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="e023b-118">**Değer:** *Yalnızca* belirtilen sayfaların gizlenmesi veya gösterilmesi gerektiğini belirten bir dize değeri.</span><span class="sxs-lookup"><span data-stu-id="e023b-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="e023b-119">Olası değerler şunlardır `hide:<pagename>` `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="e023b-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="e023b-120">Birden çok sayfa, noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="e023b-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="e023b-121">Özel bir **ilke** oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e023b-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="e023b-122">**OMA-URI** ayarlandığında, tam kapsamlı URI girin.</span><span class="sxs-lookup"><span data-stu-id="e023b-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="e023b-123">Örneğin: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="e023b-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="e023b-124">Veri çekmeyi seçerken şunu seçin: **dize**</span><span class="sxs-lookup"><span data-stu-id="e023b-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="e023b-125">**Değer** belirtirken Yukarıdaki kılavuzu kullanın.</span><span class="sxs-lookup"><span data-stu-id="e023b-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="e023b-126">Örneğin: **`showonly:network-wifi;network-proxy;bluetooth`** veya **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="e023b-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="e023b-127">Özel cihaz yapılandırmasını cihazın içinde olmasını amaçladığı bir gruba atadığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="e023b-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="e023b-128">Bu adım gerçekleştirilmediğinden, ilke gönderilir ancak uygulanmaz.</span><span class="sxs-lookup"><span data-stu-id="e023b-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="e023b-129">ıntune grupları ve cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [HoloLens MDM yapılandırması](hololens-mdm-configure.md) .</span><span class="sxs-lookup"><span data-stu-id="e023b-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="e023b-130">Bu ilkeyi bir sağlama paketi aracılığıyla dağıtma</span><span class="sxs-lookup"><span data-stu-id="e023b-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="e023b-131">bunlar, Windows yapılandırma tasarımcısı 'nda belirtilecektir yapılandırma değerlerdir:</span><span class="sxs-lookup"><span data-stu-id="e023b-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="e023b-132">**Değer:** *Yalnızca* belirtilen sayfaların gizlenmesi veya gösterilmesi gerektiğini belirten bir dize değeri.</span><span class="sxs-lookup"><span data-stu-id="e023b-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="e023b-133">Olası değerler şunlardır `hide:<pagename>` `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="e023b-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="e023b-134">Birden çok sayfa, noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="e023b-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="e023b-135">Windows yapılandırma tasarımcısında paketinizi oluştururken **ilkeler > Ayarlar > pagevisibilitylist** ' e gidin</span><span class="sxs-lookup"><span data-stu-id="e023b-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="e023b-136">Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="e023b-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="e023b-137">Sağlama paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="e023b-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="e023b-138">Paketi cihazınıza uygulayın.</span><span class="sxs-lookup"><span data-stu-id="e023b-138">Apply the package to your device.</span></span>
<span data-ttu-id="e023b-139">bir sağlama paketini oluşturma ve uygulama hakkında tam ayrıntılar için [HoloLens sağlama sayfasını](hololens-provisioning.md)ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="e023b-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="e023b-140">seçtiğiniz yöntemden bağımsız olarak cihazınız artık değişiklikleri almalıdır ve kullanıcılar aşağıdaki Ayarlar uygulamayla sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="e023b-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="e023b-142">Ayarlar uygulama sayfalarını kendi sayfa seçiminizi gösterecek veya gizleyecek şekilde yapılandırmak için, HoloLens 'de bulunan Ayarlar urı 'lere göz atın.</span><span class="sxs-lookup"><span data-stu-id="e023b-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="e023b-143">Ayarlar Þ</span><span class="sxs-lookup"><span data-stu-id="e023b-143">Settings URIs</span></span>

<span data-ttu-id="e023b-144">HoloLens cihazların ve Windows 10 cihazların Ayarlar uygulamasında farklı bir sayfa seçimi vardır.</span><span class="sxs-lookup"><span data-stu-id="e023b-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="e023b-145">Bu sayfada yalnızca HoloLens var olan ayarları bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="e023b-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="e023b-146">Hesaplar</span><span class="sxs-lookup"><span data-stu-id="e023b-146">Accounts</span></span>
| <span data-ttu-id="e023b-147">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-147">Settings page</span></span>           | <span data-ttu-id="e023b-148">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="e023b-149">İş veya okul hesabına erişme</span><span class="sxs-lookup"><span data-stu-id="e023b-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="e023b-150">Iris kaydı</span><span class="sxs-lookup"><span data-stu-id="e023b-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="e023b-151">Oturum açma seçenekleri</span><span class="sxs-lookup"><span data-stu-id="e023b-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="e023b-152">Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="e023b-152">Apps</span></span>
| <span data-ttu-id="e023b-153">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-153">Settings page</span></span> | <span data-ttu-id="e023b-154">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="e023b-155">Uygulamalar & Özellikler <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="e023b-156">Uygulamalar & Özellikler > Gelişmiş Seçenekler <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="e023b-157">uygulamalar & özellikler > çevrimdışı Haritalar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="e023b-158">uygulamalar & özellikler > çevrimdışı Haritalar > indirme haritaları <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="e023b-159">Cihazlar</span><span class="sxs-lookup"><span data-stu-id="e023b-159">Devices</span></span>
| <span data-ttu-id="e023b-160">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-160">Settings page</span></span> | <span data-ttu-id="e023b-161">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="e023b-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="e023b-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="e023b-163">Fare <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="e023b-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="e023b-165">Gizlilik</span><span class="sxs-lookup"><span data-stu-id="e023b-165">Privacy</span></span>
| <span data-ttu-id="e023b-166">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-166">Settings page</span></span>            | <span data-ttu-id="e023b-167">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="e023b-168">Hesap bilgileri</span><span class="sxs-lookup"><span data-stu-id="e023b-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="e023b-169">Uygulama Tanılama</span><span class="sxs-lookup"><span data-stu-id="e023b-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="e023b-170">Arka plan uygulamaları</span><span class="sxs-lookup"><span data-stu-id="e023b-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="e023b-171">Takvim</span><span class="sxs-lookup"><span data-stu-id="e023b-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="e023b-172">Arama geçmişi</span><span class="sxs-lookup"><span data-stu-id="e023b-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="e023b-173">Kamera</span><span class="sxs-lookup"><span data-stu-id="e023b-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="e023b-174">Kişiler</span><span class="sxs-lookup"><span data-stu-id="e023b-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="e023b-175">Tanılama & geri bildirimi</span><span class="sxs-lookup"><span data-stu-id="e023b-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="e023b-176">Belgeler</span><span class="sxs-lookup"><span data-stu-id="e023b-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="e023b-177">E-posta</span><span class="sxs-lookup"><span data-stu-id="e023b-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="e023b-178">Dosya sistemi</span><span class="sxs-lookup"><span data-stu-id="e023b-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="e023b-179">Genel <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="e023b-180">Mürekkeple & yazma kişiselleştirme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="e023b-181">Konum</span><span class="sxs-lookup"><span data-stu-id="e023b-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="e023b-182">Mesajlaşma</span><span class="sxs-lookup"><span data-stu-id="e023b-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="e023b-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="e023b-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="e023b-184">Hareket <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="e023b-185">Bildirimler</span><span class="sxs-lookup"><span data-stu-id="e023b-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="e023b-186">Diğer cihazlar</span><span class="sxs-lookup"><span data-stu-id="e023b-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="e023b-187">Resimler</span><span class="sxs-lookup"><span data-stu-id="e023b-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="e023b-188">Radyolara</span><span class="sxs-lookup"><span data-stu-id="e023b-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="e023b-189">Ekran görüntüsü kenarlıkları <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="e023b-190">Ekran görüntüleri ve uygulamalar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="e023b-191">Konuşma</span><span class="sxs-lookup"><span data-stu-id="e023b-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="e023b-192">Görevler</span><span class="sxs-lookup"><span data-stu-id="e023b-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="e023b-193">Kullanıcı hareketleri</span><span class="sxs-lookup"><span data-stu-id="e023b-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="e023b-194">Videolar</span><span class="sxs-lookup"><span data-stu-id="e023b-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="e023b-195">Ses etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="e023b-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="e023b-196">Ağ ve İnternet</span><span class="sxs-lookup"><span data-stu-id="e023b-196">Network & Internet</span></span>
| <span data-ttu-id="e023b-197">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-197">Settings page</span></span> | <span data-ttu-id="e023b-198">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="e023b-199">Uçak modu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="e023b-200">Ara sunucu</span><span class="sxs-lookup"><span data-stu-id="e023b-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="e023b-201">VPN</span><span class="sxs-lookup"><span data-stu-id="e023b-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="e023b-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e023b-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="e023b-203">Sistem</span><span class="sxs-lookup"><span data-stu-id="e023b-203">System</span></span>
| <span data-ttu-id="e023b-204">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-204">Settings page</span></span>      | <span data-ttu-id="e023b-205">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="e023b-206">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="e023b-207">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="e023b-208">Renkler</span><span class="sxs-lookup"><span data-stu-id="e023b-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="e023b-209">Hologramlar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="e023b-210"><sup>2. Ayar</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="e023b-211">Bildirimler & eylemleri</span><span class="sxs-lookup"><span data-stu-id="e023b-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="e023b-212">Paylaşılan Deneyimler</span><span class="sxs-lookup"><span data-stu-id="e023b-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="e023b-213">Ses <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="e023b-214">Ses > Uygulama birimi ve cihaz tercihi <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="e023b-215">Ses > Ses cihazlarını yönetme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="e023b-216">Depolama</span><span class="sxs-lookup"><span data-stu-id="e023b-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="e023b-217">Depolama > Sense <sup>2 Depolama yi Yapılandırma</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="e023b-218">Saat & Dili</span><span class="sxs-lookup"><span data-stu-id="e023b-218">Time & Language</span></span>
| <span data-ttu-id="e023b-219">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-219">Settings page</span></span> | <span data-ttu-id="e023b-220">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="e023b-221">Tarih & saat <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="e023b-222">Klavye <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="e023b-223">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="e023b-224">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="e023b-225">Dil</span><span class="sxs-lookup"><span data-stu-id="e023b-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="e023b-226">Region</span><span class="sxs-lookup"><span data-stu-id="e023b-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="e023b-227">Güncelleştirme & Güvenliği</span><span class="sxs-lookup"><span data-stu-id="e023b-227">Update & Security</span></span>
| <span data-ttu-id="e023b-228">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="e023b-228">Settings page</span></span>                         | <span data-ttu-id="e023b-229">URI</span><span class="sxs-lookup"><span data-stu-id="e023b-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="e023b-230">Gelişmiş Seçenekler</span><span class="sxs-lookup"><span data-stu-id="e023b-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="e023b-231">Kurtarma & <sup>2'ye sıfırlama</sup></span><span class="sxs-lookup"><span data-stu-id="e023b-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="e023b-232">Windows Insider Programı</span><span class="sxs-lookup"><span data-stu-id="e023b-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="e023b-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="e023b-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="e023b-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="e023b-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="e023b-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="e023b-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="e023b-236">Windows Güncelleştirme - Güncelleştirmeleri denetler</span><span class="sxs-lookup"><span data-stu-id="e023b-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="e023b-237"><sup>1</sup> - Windows Holographic sürüm 21H1'den önceki sürümler için, aşağıdaki iki URL sizi Gelişmiş seçenekler veya Seçenekler **sayfalarına** **gerçekten** götürmektedir; Yalnızca Güncelleştirme sayfasındaki ana Windows gösterir.</span><span class="sxs-lookup"><span data-stu-id="e023b-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="e023b-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="e023b-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="e023b-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="e023b-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="e023b-240"><sup>2</sup> - Windows Holographic 21H1 veya daha üst bir üzerinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e023b-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="e023b-241">URL'lerin Windows 10 Ayarlar için lütfen başlatma ayarları [belgelerini ziyaret](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) edin.</span><span class="sxs-lookup"><span data-stu-id="e023b-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
