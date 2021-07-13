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
# <a name="page-settings-visibility"></a><span data-ttu-id="3c07d-104">Sayfa Ayarlar Görünürlüğü</span><span class="sxs-lookup"><span data-stu-id="3c07d-104">Page Settings Visibility</span></span>

<span data-ttu-id="3c07d-105">HoloLens cihazları için yönetilebilir özelliklerden biri, [Ayarlar/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ilkesi kullanarak Ayarlar uygulama içinde görülen sayfaları kısıtlamaktır.</span><span class="sxs-lookup"><span data-stu-id="3c07d-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="3c07d-106">PageVisibilityList, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkedir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="3c07d-107">Bu özellik yalnızca [Holographic 20H2 veya Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) veya daha yeni sürümlerde kullanılabilir HoloLens 2 cihazlar için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="3c07d-108">Bunu kullanmayı niyetli cihazların güncelleştirilmiş olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="3c07d-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="3c07d-109">Örnekler</span><span class="sxs-lookup"><span data-stu-id="3c07d-109">Examples</span></span>
<span data-ttu-id="3c07d-110">Sayfalar, yayımlanmış URI'lerin kısaltılmış bir sürümüyle tanımlanır ve bu sürüm URI'den "ms-settings:" ön eki eksi değerdir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="3c07d-111">Aşağıdaki örnekte, sırasıyla "network-wifi" ve "bluetooth" URI'sine sahip olan yalnızca hakkında ve Bluetooth sayfalarına erişime izin verecek bir ilke yer almaktadır:</span><span class="sxs-lookup"><span data-stu-id="3c07d-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="3c07d-112">Aşağıdaki örnek, işletim sistemi sıfırlama sayfasını gizleyen bir ilkeyi göstermektedir:</span><span class="sxs-lookup"><span data-stu-id="3c07d-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="3c07d-113">Bu ilkeyi Intune aracılığıyla dağıtma</span><span class="sxs-lookup"><span data-stu-id="3c07d-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="3c07d-114">Bunlar, Intune'a sağlanmalıdır yapılandırma değerleridir:</span><span class="sxs-lookup"><span data-stu-id="3c07d-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="3c07d-115">**Ad:** Profil için yöneticinin tercih ettiği görünen ad.</span><span class="sxs-lookup"><span data-stu-id="3c07d-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="3c07d-116">**OMA-URI:** Kapsamı dahil olmak üzere ayar sayfasının tam [URI'sı.](/windows/client-management/mdm/policy-configuration-service-provider)</span><span class="sxs-lookup"><span data-stu-id="3c07d-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="3c07d-117">Bu sayfada yer alan bu örnekler kapsamı `./Device` kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="3c07d-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="3c07d-118">**Değer:** Yalnızca belirtilen sayfaları gizlemeyi veya göstermeyi *belirten* bir dize değeri.</span><span class="sxs-lookup"><span data-stu-id="3c07d-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="3c07d-119">Olası değerler ve `hide:<pagename>` `showonly:<pagename>` değerleridir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="3c07d-120">Birden çok sayfa noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="3c07d-121">Özel ilke **oluşturun.**</span><span class="sxs-lookup"><span data-stu-id="3c07d-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="3c07d-122">**OMA-URI'yi ayarlarken** tam kapsamlı URI'yi girin.</span><span class="sxs-lookup"><span data-stu-id="3c07d-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="3c07d-123">Örneğin: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="3c07d-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="3c07d-124">Veri seçiminizi şu şekilde seçin: **Dize**</span><span class="sxs-lookup"><span data-stu-id="3c07d-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="3c07d-125">Değer **belirtirken** yukarıdaki kılavuzu kullanın.</span><span class="sxs-lookup"><span data-stu-id="3c07d-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="3c07d-126">Örneğin: **`showonly:network-wifi;network-proxy;bluetooth`** veya **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="3c07d-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="3c07d-127">Özel cihaz yapılandırmasını cihazın içinde olması amaçlanan bir gruba atadığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="3c07d-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="3c07d-128">Bu adım gerçekleştirilene kadar ilke uygulanır ancak uygulanmaz.</span><span class="sxs-lookup"><span data-stu-id="3c07d-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="3c07d-129">Intune HoloLens cihaz yapılandırmaları hakkında daha fazla bilgi için bkz. [MDM](hololens-mdm-configure.md) yapılandırmasını yapılandırma.</span><span class="sxs-lookup"><span data-stu-id="3c07d-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="3c07d-130">Bu ilkeyi Sağlama Paketi aracılığıyla dağıtma</span><span class="sxs-lookup"><span data-stu-id="3c07d-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="3c07d-131">Bunlar, Yapılandırma Tasarımcısı'nda Windows değerleridir:</span><span class="sxs-lookup"><span data-stu-id="3c07d-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="3c07d-132">**Değer:** Yalnızca belirtilen sayfaları gizlemeyi veya göstermeyi *belirten* bir dize değeri.</span><span class="sxs-lookup"><span data-stu-id="3c07d-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="3c07d-133">Olası değerler ve `hide:<pagename>` `showonly:<pagename>` değerleridir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="3c07d-134">Birden çok sayfa noktalı virgülle ayrılarak belirtilebilir ve ortak sayfaların listesi aşağıda bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="3c07d-135">Windows Configuration Designer'da paketinizi oluştururken İlkeler > Ayarlar > **PageVisibilityList'e gidin**</span><span class="sxs-lookup"><span data-stu-id="3c07d-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="3c07d-136">Dizeyi girin: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="3c07d-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="3c07d-137">Sağlama Paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="3c07d-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="3c07d-138">Paketi cihazınıza uygulama.</span><span class="sxs-lookup"><span data-stu-id="3c07d-138">Apply the package to your device.</span></span>
<span data-ttu-id="3c07d-139">Sağlama paketi oluşturma ve uygulama hakkında ayrıntılı bilgi için HoloLens [sayfasını ziyaret edin.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="3c07d-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="3c07d-140">Seçilen yöntemden bağımsız olarak cihazınızın artık değişiklikleri alması gerekir ve kullanıcılara aşağıdaki Ayarlar sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="3c07d-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="3c07d-142">Uygulama sayfalarını Ayarlar kendi sayfa seçiminizi gösterecek veya gizleyişini yapılandıracak şekilde yapılandırmak için, Ayarlar URL'leri HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3c07d-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="3c07d-143">Ayarlar Urı</span><span class="sxs-lookup"><span data-stu-id="3c07d-143">Settings URIs</span></span>

<span data-ttu-id="3c07d-144">HoloLens ve Windows 10 cihazlarda, uygulamanın içinde farklı sayfa Ayarlar vardır.</span><span class="sxs-lookup"><span data-stu-id="3c07d-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="3c07d-145">Bu sayfada yalnızca bu sayfada mevcut olan ayarları HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3c07d-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="3c07d-146">Hesaplar</span><span class="sxs-lookup"><span data-stu-id="3c07d-146">Accounts</span></span>
| <span data-ttu-id="3c07d-147">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-147">Settings page</span></span>           | <span data-ttu-id="3c07d-148">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="3c07d-149">İş veya okul hesabına erişme</span><span class="sxs-lookup"><span data-stu-id="3c07d-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="3c07d-150">Iris Kaydı</span><span class="sxs-lookup"><span data-stu-id="3c07d-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="3c07d-151">Oturum Açma Seçenekleri</span><span class="sxs-lookup"><span data-stu-id="3c07d-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="3c07d-152">Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="3c07d-152">Apps</span></span>
| <span data-ttu-id="3c07d-153">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-153">Settings page</span></span> | <span data-ttu-id="3c07d-154">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3c07d-155">Uygulamalar & özellikleri <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="3c07d-156">Gelişmiş & <sup>2</sup> > uygulamalar ve özellikler</span><span class="sxs-lookup"><span data-stu-id="3c07d-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="3c07d-157">Çevrimdışı & <sup>2</sup> > uygulamalar Haritalar özellikleri</span><span class="sxs-lookup"><span data-stu-id="3c07d-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="3c07d-158">Çevrimdışı & haritalar > 2 Haritalar > uygulamalar <sup>ve özellikler</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="3c07d-159">Cihazlar</span><span class="sxs-lookup"><span data-stu-id="3c07d-159">Devices</span></span>
| <span data-ttu-id="3c07d-160">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-160">Settings page</span></span> | <span data-ttu-id="3c07d-161">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3c07d-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3c07d-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="3c07d-163">Fare <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="3c07d-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="3c07d-165">Gizlilik</span><span class="sxs-lookup"><span data-stu-id="3c07d-165">Privacy</span></span>
| <span data-ttu-id="3c07d-166">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-166">Settings page</span></span>            | <span data-ttu-id="3c07d-167">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="3c07d-168">Hesap Bilgileri</span><span class="sxs-lookup"><span data-stu-id="3c07d-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="3c07d-169">Uygulama Tanılama</span><span class="sxs-lookup"><span data-stu-id="3c07d-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="3c07d-170">Arka Plan Uygulamaları</span><span class="sxs-lookup"><span data-stu-id="3c07d-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="3c07d-171">Takvim</span><span class="sxs-lookup"><span data-stu-id="3c07d-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="3c07d-172">Çağrı Geçmişi</span><span class="sxs-lookup"><span data-stu-id="3c07d-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="3c07d-173">Kamera</span><span class="sxs-lookup"><span data-stu-id="3c07d-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="3c07d-174">Kişiler</span><span class="sxs-lookup"><span data-stu-id="3c07d-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="3c07d-175">Tanılama ve & Geri Bildirimi</span><span class="sxs-lookup"><span data-stu-id="3c07d-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="3c07d-176">Belgeler</span><span class="sxs-lookup"><span data-stu-id="3c07d-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="3c07d-177">E-posta</span><span class="sxs-lookup"><span data-stu-id="3c07d-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="3c07d-178">Dosya sistemi</span><span class="sxs-lookup"><span data-stu-id="3c07d-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="3c07d-179">Genel <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="3c07d-180">Mürekkep & kişiselleştirme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="3c07d-181">Konum</span><span class="sxs-lookup"><span data-stu-id="3c07d-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="3c07d-182">Mesajlaşma</span><span class="sxs-lookup"><span data-stu-id="3c07d-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="3c07d-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="3c07d-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="3c07d-184">Hareket <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="3c07d-185">Bildirimler</span><span class="sxs-lookup"><span data-stu-id="3c07d-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="3c07d-186">Diğer cihazlar</span><span class="sxs-lookup"><span data-stu-id="3c07d-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="3c07d-187">Resimler</span><span class="sxs-lookup"><span data-stu-id="3c07d-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="3c07d-188">Radyo</span><span class="sxs-lookup"><span data-stu-id="3c07d-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="3c07d-189">Ekran görüntüsü <sup>kenarlıklar 2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="3c07d-190">Ekran görüntüleri ve uygulamalar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="3c07d-191">Konuşma</span><span class="sxs-lookup"><span data-stu-id="3c07d-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="3c07d-192">Görevler</span><span class="sxs-lookup"><span data-stu-id="3c07d-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="3c07d-193">Kullanıcı hareketleri</span><span class="sxs-lookup"><span data-stu-id="3c07d-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="3c07d-194">Videolar</span><span class="sxs-lookup"><span data-stu-id="3c07d-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="3c07d-195">Ses Etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="3c07d-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="3c07d-196">Ağ ve İnternet</span><span class="sxs-lookup"><span data-stu-id="3c07d-196">Network & Internet</span></span>
| <span data-ttu-id="3c07d-197">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-197">Settings page</span></span> | <span data-ttu-id="3c07d-198">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="3c07d-199">Uçak Modu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="3c07d-200">Ara sunucu</span><span class="sxs-lookup"><span data-stu-id="3c07d-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="3c07d-201">VPN</span><span class="sxs-lookup"><span data-stu-id="3c07d-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="3c07d-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3c07d-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="3c07d-203">Sistem</span><span class="sxs-lookup"><span data-stu-id="3c07d-203">System</span></span>
| <span data-ttu-id="3c07d-204">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-204">Settings page</span></span>      | <span data-ttu-id="3c07d-205">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="3c07d-206">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="3c07d-207">Pil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="3c07d-208">Renkler</span><span class="sxs-lookup"><span data-stu-id="3c07d-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="3c07d-209">Hologramlar <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="3c07d-210"><sup>2. Ayar</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="3c07d-211">Bildirimler & eylemleri</span><span class="sxs-lookup"><span data-stu-id="3c07d-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="3c07d-212">Paylaşılan Deneyimler</span><span class="sxs-lookup"><span data-stu-id="3c07d-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="3c07d-213">Ses <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="3c07d-214">Ses > Uygulama birimi ve cihaz tercihi <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="3c07d-215">Ses > Ses cihazlarını yönetme <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="3c07d-216">Depolama</span><span class="sxs-lookup"><span data-stu-id="3c07d-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="3c07d-217">Depolama > Sense <sup>2 Depolama yi Yapılandırma</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="3c07d-218">Saat & Dili</span><span class="sxs-lookup"><span data-stu-id="3c07d-218">Time & Language</span></span>
| <span data-ttu-id="3c07d-219">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-219">Settings page</span></span> | <span data-ttu-id="3c07d-220">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="3c07d-221">Tarih & saat <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="3c07d-222">Klavye <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="3c07d-223">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="3c07d-224">Dil <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="3c07d-225">Dil</span><span class="sxs-lookup"><span data-stu-id="3c07d-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="3c07d-226">Region</span><span class="sxs-lookup"><span data-stu-id="3c07d-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="3c07d-227">Güncelleştirme & Güvenliği</span><span class="sxs-lookup"><span data-stu-id="3c07d-227">Update & Security</span></span>
| <span data-ttu-id="3c07d-228">Ayarlar sayfası</span><span class="sxs-lookup"><span data-stu-id="3c07d-228">Settings page</span></span>                         | <span data-ttu-id="3c07d-229">URI</span><span class="sxs-lookup"><span data-stu-id="3c07d-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="3c07d-230">Gelişmiş Seçenekler</span><span class="sxs-lookup"><span data-stu-id="3c07d-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="3c07d-231">Kurtarma & <sup>2'ye sıfırlama</sup></span><span class="sxs-lookup"><span data-stu-id="3c07d-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="3c07d-232">Windows Insider Programı</span><span class="sxs-lookup"><span data-stu-id="3c07d-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="3c07d-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="3c07d-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="3c07d-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="3c07d-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="3c07d-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="3c07d-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="3c07d-236">Windows Güncelleştirme - Güncelleştirmeleri denetler</span><span class="sxs-lookup"><span data-stu-id="3c07d-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="3c07d-237"><sup>1</sup> - Windows Holographic sürüm 21H1'den önceki sürümler için, aşağıdaki iki URL sizi Gelişmiş seçenekler veya Seçenekler **sayfalarına** **gerçekten** götürmektedir; Yalnızca Güncelleştirme sayfasındaki ana Windows gösterir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="3c07d-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="3c07d-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="3c07d-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="3c07d-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="3c07d-240"><sup>2</sup> - Windows Holographic 21H1 veya daha üst bir üzerinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3c07d-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="3c07d-241">URL'lerin Windows 10 Ayarlar için lütfen başlatma ayarları [belgelerini ziyaret](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) edin.</span><span class="sxs-lookup"><span data-stu-id="3c07d-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
