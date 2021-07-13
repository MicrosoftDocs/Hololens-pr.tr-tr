---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleri ile çalışmaya başlamayı ve bir sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamayı HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636132"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="8fcdc-103">Microsoft HoloLens için Insider önizlemesi</span><span class="sxs-lookup"><span data-stu-id="8fcdc-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="8fcdc-104">Yeni sürümler için en son Insider Önizleme derlemeleri HoloLens!</span><span class="sxs-lookup"><span data-stu-id="8fcdc-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="8fcdc-105">Hızlı bir şekilde çalışmaya [başlamanız ve bir sonraki](hololens-insider.md#start-receiving-insider-builds) büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="8fcdc-106">Windows Insider Sürüm Notları</span><span class="sxs-lookup"><span data-stu-id="8fcdc-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="8fcdc-107">Windows Insiders'a yeni özellikler Windows heyecanla başlayacağız.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="8fcdc-108">En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="8fcdc-109">Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme ekley Windows devam edeceğiz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="8fcdc-110">Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="8fcdc-111">Özellik</span><span class="sxs-lookup"><span data-stu-id="8fcdc-111">Feature</span></span>                 | <span data-ttu-id="8fcdc-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8fcdc-112">Description</span></span>                | <span data-ttu-id="8fcdc-113">Kullanıcı veya Senaryo</span><span class="sxs-lookup"><span data-stu-id="8fcdc-113">User or Scenario</span></span> | <span data-ttu-id="8fcdc-114">Derleme tanıtıldı</span><span class="sxs-lookup"><span data-stu-id="8fcdc-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="8fcdc-115">Rapor ayrıntıları için CSP HoloLens değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="8fcdc-116">Veri sorgulamak için yeni CSP'ler</span><span class="sxs-lookup"><span data-stu-id="8fcdc-116">New CSPs for to query data</span></span> | <span data-ttu-id="8fcdc-117">IT Yöneticileri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-117">IT Admins</span></span>    | <span data-ttu-id="8fcdc-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="8fcdc-118">20348.1403</span></span>                 |
| [<span data-ttu-id="8fcdc-119">CSP tarafından denetlenen otomatik oturum açma ilkesi</span><span class="sxs-lookup"><span data-stu-id="8fcdc-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="8fcdc-120">Bir hesapta otomatik olarak oturum açmak için kullanılır</span><span class="sxs-lookup"><span data-stu-id="8fcdc-120">Used to log in an account automatically</span></span> | <span data-ttu-id="8fcdc-121">IT Yöneticileri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-121">IT Admins</span></span> | <span data-ttu-id="8fcdc-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="8fcdc-122">20348.1405</span></span> |
| [<span data-ttu-id="8fcdc-123">Sertifika Yöneticisi için PFX dosyası desteği</span><span class="sxs-lookup"><span data-stu-id="8fcdc-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="8fcdc-124">Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleme</span><span class="sxs-lookup"><span data-stu-id="8fcdc-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="8fcdc-125">Son Kullanıcı</span><span class="sxs-lookup"><span data-stu-id="8fcdc-125">End User</span></span> | <span data-ttu-id="8fcdc-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="8fcdc-126">20348.1405</span></span> |
| [<span data-ttu-id="8fcdc-127">Gelişmiş tanılama raporunu Ayarlar'da HoloLens</span><span class="sxs-lookup"><span data-stu-id="8fcdc-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="8fcdc-128">Cihazda MDM tanılama günlüklerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="8fcdc-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="8fcdc-129">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="8fcdc-129">Troubleshooting</span></span> | <span data-ttu-id="8fcdc-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="8fcdc-130">20348.1405</span></span> |
| [<span data-ttu-id="8fcdc-131">Çevrimdışı Tanılama bildirimleri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="8fcdc-132">Günlük toplama için görsel geri bildirim</span><span class="sxs-lookup"><span data-stu-id="8fcdc-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="8fcdc-133">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="8fcdc-133">Troubleshooting</span></span> | <span data-ttu-id="8fcdc-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="8fcdc-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="8fcdc-135">Rapor ayrıntıları için CSP HoloLens değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="8fcdc-136">Windows Insider derlemesinde tanıtıldı, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="8fcdc-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="8fcdc-137">Aşağıdaki CSP'ler, cihazlarından gelen bilgileri bildirmenin yeni HoloLens güncelleştirildi.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="8fcdc-138">DevDetail CSP - Ücretsiz Depolama</span><span class="sxs-lookup"><span data-stu-id="8fcdc-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="8fcdc-139">DevDetail CSP artık cihaz üzerinde boş depolama alanı HoloLens raporlar.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="8fcdc-140">Bu değer, uygulamanın Ayarlar sayfasında gösterilen değerle yaklaşık Depolama eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="8fcdc-141">Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer aleladedir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="8fcdc-142">./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="8fcdc-143">DeviceStatus CSP - SSID ve BSSID</span><span class="sxs-lookup"><span data-stu-id="8fcdc-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="8fcdc-144">DeviceStatus CSP artık etkin olarak bağlı olduğu Wi-Fi SSID ve BSSID HoloLens raporlar.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="8fcdc-145">Aşağıda bu bilgileri içeren belirli düğümler yer almaktadır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="8fcdc-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/SSID</span><span class="sxs-lookup"><span data-stu-id="8fcdc-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="8fcdc-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/BSSID</span><span class="sxs-lookup"><span data-stu-id="8fcdc-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="8fcdc-148">NetworkIdentifiers sorgulamak için örnek syncml blobu (MDM satıcıları için)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="8fcdc-149">CSP tarafından denetlenen otomatik oturum açma ilkesi</span><span class="sxs-lookup"><span data-stu-id="8fcdc-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="8fcdc-150">Bu yeni AutoLogonUser ilkesi, bir kullanıcının otomatik olarak oturum açıp oturum açmayacaklarını kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="8fcdc-151">Bazı müşteriler, bir kimliğe bağlı ancak herhangi bir oturum açma deneyimi istemeden cihazları ayarlamak ister.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="8fcdc-152">Imagine cihazı alacak ve uzaktan yardım'ı hemen kullanmaya devam edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="8fcdc-153">Veya cihazları hızla dağıtarak son kullanıcılarının oturum açma HoloLens olanaklı olma avantajından da yararlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="8fcdc-154">İlke boş olmayan bir değere ayarlanırsa, otomatik oturum açma kullanıcısını e-posta adresi belirtir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="8fcdc-155">Belirtilen kullanıcının otomatik oturum açmayı etkinleştirmek için cihazda en az bir kez oturum açması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="8fcdc-156">Yeni ilke Dizesi değerinin `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI'sı</span><span class="sxs-lookup"><span data-stu-id="8fcdc-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="8fcdc-157">Aynı e-posta adresine sahip kullanıcı otomatik oturum açmayı etkinleştirmiş olur.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="8fcdc-158">Bu ilkenin yapılandırıldığında, ilkede belirtilen kullanıcının en az bir kez oturum açması gerekir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="8fcdc-159">İlk oturum açma sonrasında cihazın yeniden başlatılması, belirtilen kullanıcının otomatik olarak oturum açmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="8fcdc-160">Yalnızca tek bir otomatik oturum açma kullanıcısı de destekler.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="8fcdc-161">Etkinleştirildikten sonra, otomatik olarak oturum açan kullanıcı el ile oturumu kapatamayacaktır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="8fcdc-162">Farklı bir kullanıcı olarak oturum aç için ilkenin önce devre dışı bırakılmıştır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="8fcdc-163">Büyük işletim sistemi güncelleştirmeleri gibi bazı olaylar, belirtilen kullanıcının otomatik oturum açma davranışını sürdürmesi için cihazda yeniden oturum açmasını gerekli kilebilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="8fcdc-164">Otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="8fcdc-165">Sertifika Yöneticisi için PFX dosyası desteği</span><span class="sxs-lookup"><span data-stu-id="8fcdc-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="8fcdc-166">Windows Insider derlemesi 20348.1405'te tanıtıldı.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="8fcdc-167">Artık .pfx sertifikalarını [kullanmak için](certificate-manager.md) Sertifika Yöneticisi'ne destek ekledik.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="8fcdc-168">Kullanıcılar Güvenlik Sertifikalarını Ayarlar'&'a gidin ve Sertifika yükle'yi seçerek kullanıcı arabirimi  >    >  artık .pfx sertifika dosyasını destekliyor. </span><span class="sxs-lookup"><span data-stu-id="8fcdc-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="8fcdc-169">Kullanıcılar özel anahtarla .pfx sertifikasını kullanıcı deposuna veya makine deposuna aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="8fcdc-170">Gelişmiş tanılama raporunu Ayarlar'da HoloLens</span><span class="sxs-lookup"><span data-stu-id="8fcdc-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="8fcdc-171">Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="8fcdc-172">Bu yeni özellikle daha önce, Ayarlar Hesapları Erişim iş veya okul aracılığıyla toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra cihazın MDM üzerinden veya cihazın yakınından yapılması ve Yönetim günlüklerinizi dışarı aktar'ı seçerek yakındaki bir pc'de  ->    >  görüntüleyebilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="8fcdc-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="8fcdc-173">Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="8fcdc-174">MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.**</span><span class="sxs-lookup"><span data-stu-id="8fcdc-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="8fcdc-175">Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-175">This will generate and open the report in a new Edge window.</span></span>

![Gelişmiş tanılama raporunu uygulamanın Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="8fcdc-177">Çevrimdışı Tanılama bildirimleri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="8fcdc-178">Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="8fcdc-179">Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="8fcdc-180">Artık Windows Insider derlemelerine eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="8fcdc-181">Birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="8fcdc-182">Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)
 
<span data-ttu-id="8fcdc-185">Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="8fcdc-186">Bu ses, bildirime ek olarak çalınacak.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="8fcdc-187">Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="8fcdc-188">Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="8fcdc-189">Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="8fcdc-190">Düzeltmeler ve geliştirmeler:</span><span class="sxs-lookup"><span data-stu-id="8fcdc-190">Fixes and improvements:</span></span>

- <span data-ttu-id="8fcdc-191">Kilitlenmiş [dosyaların indir Cihaz Portalı isteminin olmadığının bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="8fcdc-192">Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="8fcdc-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="8fcdc-193">Insider derlemelerini almaya başlama</span><span class="sxs-lookup"><span data-stu-id="8fcdc-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="8fcdc-194">Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="8fcdc-195">"Cihazı yeniden başlat" sesli komutu iyi çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="8fcdc-196">Ayrıca, Ayarlar/Windows Insider Programı.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="8fcdc-197">Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="8fcdc-198">Bir HoloLens 2 cihazında Ayarlar   >  **Update & Security**  >  **Windows Insider Programı'a gidin** ve Kullanmaya başlayın.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="8fcdc-199">Windows Insider olarak kaydetmek için kullanılan hesabı bağlama.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="8fcdc-200">Windows artık Kanallar'a taşınıyor.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="8fcdc-201">**Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="8fcdc-202">Bu, eşlemenin şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="8fcdc-202">Here is what that mapping looks like:</span></span>

![Windows Insider kanalları açıklaması](images/WindowsInsiderChannels.png)

<span data-ttu-id="8fcdc-204">daha fazla bilgi için bkz. Windows bloglarda [Windows ınsider kanalları tanıtma](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .</span><span class="sxs-lookup"><span data-stu-id="8fcdc-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="8fcdc-205">sonra, **Windows için etkin geliştirme**' yı seçin, **Dev kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="8fcdc-206">**> şimdi yeniden başlatmak Için Onayla** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="8fcdc-207">cihazınız yeniden başlatıldıktan sonra, **Ayarlar > güncelleştirme & güvenlik** ' e gidin > en son derlemeyi almak için güncelleştirmeleri denetleyin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="8fcdc-208">Güncelleştirme hatası 0x80070490 iş-etrafında</span><span class="sxs-lookup"><span data-stu-id="8fcdc-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="8fcdc-209">Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli çalışmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="8fcdc-210">Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="8fcdc-211">Aşama tek sürüm önizlemesi</span><span class="sxs-lookup"><span data-stu-id="8fcdc-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="8fcdc-212">Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **yayın önizleme kanalını** seçin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="8fcdc-213">Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="8fcdc-214">Güncelleştirme sonrasında, ikinci aşamada devam edin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="8fcdc-215">İkinci geliştirme kanalı aşaması</span><span class="sxs-lookup"><span data-stu-id="8fcdc-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="8fcdc-216">Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **geliştirme kanalı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="8fcdc-217">Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="8fcdc-218">FFU indirme ve Flash yönleri</span><span class="sxs-lookup"><span data-stu-id="8fcdc-218">FFU download and flash directions</span></span>

<span data-ttu-id="8fcdc-219">Bir uçuş imzalı FFU ile test etmek için önce, uçuşdan ayrılmadan önce cihazınızın kilidini açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="8fcdc-220">BILGISAYAR üzerinde:</span><span class="sxs-lookup"><span data-stu-id="8fcdc-220">On PC:</span></span>
    1. <span data-ttu-id="8fcdc-221">Hesabınızı ' den bilgisayarınıza indirin [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="8fcdc-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="8fcdc-222">Microsoft Store: ile yay (Gelişmiş kurtarma Yardımcısı) yüklemesini yapın [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="8fcdc-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="8fcdc-223">HoloLens uçuşlamada kilit açma: **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' nı açın ve cihazı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="8fcdc-224">Flash FFU-şimdi yay kullanarak uçuştan imzalanmış FFU 'yi yakıp sönebilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="8fcdc-225">Geri bildirim ve rapor sorunları sağlama</span><span class="sxs-lookup"><span data-stu-id="8fcdc-225">Provide feedback and report issues</span></span>

<span data-ttu-id="8fcdc-226">geri bildirim ve rapor sorunları sağlamak için lütfen HoloLens [geri bildirim merkezi uygulamasını](hololens-feedback.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="8fcdc-227">Geri Bildirim Hub 'ı kullanmak, mühendislerimizin hata ayıklamasına ve sorunu çözmeye yardımcı olmak için gerekli tüm tanılama bilgilerinin eklenmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="8fcdc-228">HoloLens çince ve japonca sürümü ile ilgili sorunlar aynı şekilde bildirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="8fcdc-229">Belge klasörünüze geri bildirim hub 'ı (sorulduğunda **Evet** ' i seçin) isteyip istemediğinizi soran istemi kabul ettiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="8fcdc-230">Geliştiriciler için göz önünde</span><span class="sxs-lookup"><span data-stu-id="8fcdc-230">Note for developers</span></span>

<span data-ttu-id="8fcdc-231">HoloLens Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemeye hoş geldiniz ve önerilir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="8fcdc-232">başlamak için [HoloLens geliştirici belgelerine](https://developer.microsoft.com/windows/mixed-reality/development) göz atın.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="8fcdc-233">Aynı yönergeler HoloLens Insider Derlemeleriyle birlikte çalışır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="8fcdc-234">HoloLens geliştirme için kullanmakta olduğunuz Unity ve Visual Studio derlemelerin aynısını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="8fcdc-235">Insider derlemelerini almayı durdur</span><span class="sxs-lookup"><span data-stu-id="8fcdc-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="8fcdc-236">artık Windows Holographic ınsider derlemelerini almak istemiyorsanız, HoloLens bir üretim derlemesi çalıştırırken devre dışı bırakabilirsiniz veya cihazınızı Windows Holographic 'ın ınsider sürümüne kurtarmak için gelişmiş kurtarma yardımcısı 'nı kullanarak [cihazınızı kurtarabilirsiniz](hololens-recovery.md) .</span><span class="sxs-lookup"><span data-stu-id="8fcdc-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="8fcdc-237">Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydolmamış kullanıcıların mavi bir ekran deneymesinin bilinen bir sorunu vardır.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="8fcdc-238">Daha sonra cihazlarını el ile kurtarmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="8fcdc-239">Etkilenmiş olmanız veya olmadıysanız ilgili tüm ayrıntılar için lütfen bu [bilinen sorunu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)izleyin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="8fcdc-240">HoloLens bir üretim derlemesi çalıştırdığından emin olmak için:</span><span class="sxs-lookup"><span data-stu-id="8fcdc-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="8fcdc-241">**Ayarlar > sistem >**' e gidin ve derleme numarasını bulun.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="8fcdc-242">[Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="8fcdc-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="8fcdc-243">Insider derlemelerini devre dışı bırakmak için:</span><span class="sxs-lookup"><span data-stu-id="8fcdc-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="8fcdc-244">üretim yapısını çalıştıran bir HoloLens, **Ayarlar > & güvenlik > Windows ınsider programı**' na gidin ve **ınsider derlemelerini durdur**' u seçin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="8fcdc-245">Cihazınızı devre dışı bırakmak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="8fcdc-245">Follow the instructions to opt out your device.</span></span>
