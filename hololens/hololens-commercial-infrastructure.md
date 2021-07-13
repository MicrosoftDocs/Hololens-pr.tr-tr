---
title: HoloLens için altyapı yönergeleri
description: kablosuz ağ desteği, uzaktan yardım ve mobil cihaz yönetimi dahil HoloLens cihazlara yönelik altyapı yönergeleri hakkında bilgi edinin.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639293"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="00011-103">Ağınızı HoloLens için yapılandırma</span><span class="sxs-lookup"><span data-stu-id="00011-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="00011-104">Belgenin bu bölümü aşağıdaki kişileri gerektirecektir:</span><span class="sxs-lookup"><span data-stu-id="00011-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="00011-105">Ara sunucu/güvenlik duvarında değişiklik yapma izinleri olan ağ yöneticisi</span><span class="sxs-lookup"><span data-stu-id="00011-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="00011-106">Azure Active Directory Yöneticileri</span><span class="sxs-lookup"><span data-stu-id="00011-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="00011-107">Mobil Device Manager Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="00011-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="00011-108">Altyapı gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="00011-108">Infrastructure Requirements</span></span>

<span data-ttu-id="00011-109">HoloLens, temel tarafında Azure ile tümleştirilmiş bir mobil cihaz Windows.</span><span class="sxs-lookup"><span data-stu-id="00011-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="00011-110">kablosuz ağ kullanılabilirliği (wi-fi) ve Microsoft hizmetleri erişimi olan ticari ortamlarda en iyi şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="00011-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="00011-111">Kritik bulut Hizmetleri şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="00011-111">Critical cloud services include:</span></span>

- <span data-ttu-id="00011-112">Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="00011-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="00011-113">Windows Güncelleştirme (WU)</span><span class="sxs-lookup"><span data-stu-id="00011-113">Windows Update (WU)</span></span>

<span data-ttu-id="00011-114">ticari müşterilerin, HoloLens cihazları ölçekli olarak yönetmesi için enterprise mobility management (EMM) veya mobil cihaz yönetimi (MDM) altyapısına ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="00011-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="00011-115">bu kılavuz bir örnek olarak [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) kullanır, ancak Microsoft Policy için tam desteğe sahip tüm sağlayıcılar HoloLens destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="00011-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="00011-116">HoloLens 2 ' i desteklediklerinde mobil cihaz yönetimi sağlayıcınızı sorun.</span><span class="sxs-lookup"><span data-stu-id="00011-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="00011-117">HoloLens, sınırlı sayıda bulut bağlantısı kesik deneyimler destekler.</span><span class="sxs-lookup"><span data-stu-id="00011-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="00011-118">Kablosuz ağ EAP desteği</span><span class="sxs-lookup"><span data-stu-id="00011-118">Wireless network EAP support</span></span>

- <span data-ttu-id="00011-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="00011-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="00011-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="00011-120">PEAP-TLS</span></span>
- <span data-ttu-id="00011-121">TLS</span><span class="sxs-lookup"><span data-stu-id="00011-121">TLS</span></span>
- <span data-ttu-id="00011-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="00011-122">TTLS-CHAP</span></span>
- <span data-ttu-id="00011-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="00011-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="00011-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="00011-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="00011-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="00011-125">TTLS-PAP</span></span>
- <span data-ttu-id="00011-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="00011-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="00011-127">HoloLens Belirli ağ gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="00011-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="00011-128">Ağ güvenlik duvarınız üzerinde bu uç nokta [listesine](hololens-offline.md) izin verildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="00011-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="00011-129">bu, HoloLens düzgün çalışmasını sağlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="00011-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="00011-130">Belirli ağ gereksinimlerine uzak yardım</span><span class="sxs-lookup"><span data-stu-id="00011-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="00011-131">Uzaktan Yardım 'ın en iyi performansı için önerilen bant genişliği 1,5 MB/sn 'dir.</span><span class="sxs-lookup"><span data-stu-id="00011-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="00011-132">Ek bilgi için [ayrıntılı ağ gereksinimlerine](/MicrosoftTeams/prepare-network) bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="00011-133">**(Lütfen ağın en az 1,5 Mbps 'Lik ağ hızına sahip olmadığını, uzaktan yardım 'ın çalışmaya devam etmesi gerektiğini unutmayın. Ancak kalite zarar verebilir).**</span><span class="sxs-lookup"><span data-stu-id="00011-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="00011-134">Microsoft Teams çalışmasını sağlamak için bu bağlantı noktalarına ve url 'lere ağ güvenlik duvarında izin verildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="00011-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="00011-135">[En son bağlantı noktası listesiyle](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)güncel kalın.</span><span class="sxs-lookup"><span data-stu-id="00011-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="00011-136">[Uzaktan Yardım için belirli ağ gereksinimleri](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="00011-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="00011-137">[Kuruluşunuzun ağını Microsoft Teams için hazırlama](/MicrosoftTeams/prepare-network) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="00011-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="00011-138">Belirli ağ gereksinimlerine kılavuzluk eder</span><span class="sxs-lookup"><span data-stu-id="00011-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="00011-139">Kılavuzlar yalnızca uygulamayı indirmek ve kullanmak için ağ erişimi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="00011-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="00011-140">Azure Active Directory Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="00011-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="00011-141">Bu adım yalnızca şirketiniz HoloLens yönetimini planlıyorsa gereklidir.</span><span class="sxs-lookup"><span data-stu-id="00011-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="00011-142">Azure AD lisansına sahip olduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="00011-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="00011-143">daha fazla bilgi için lütfen [lisans gereksinimlerini HoloLens](hololens-licenses-requirements.md) .</span><span class="sxs-lookup"><span data-stu-id="00011-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="00011-144">Otomatik kayıt kullanmayı planlıyorsanız, [Azure ad kaydı](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) ' nı yapılandırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="00011-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="00011-145">Şirketinizin kullanıcılarının Azure Active Directory (Azure AD) olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="00011-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="00011-146">Kullanıcıları eklemek için aşağıdaki [yönergelere](/azure/active-directory/fundamentals/add-users-azure-active-directory) bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="00011-147">Benzer lisanslara ihtiyaç duyan kullanıcıların aynı gruba eklenmesini öneririz.</span><span class="sxs-lookup"><span data-stu-id="00011-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="00011-148">Grup oluşturma</span><span class="sxs-lookup"><span data-stu-id="00011-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="00011-149">Gruplara kullanıcı ekleme</span><span class="sxs-lookup"><span data-stu-id="00011-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="00011-150">Şirketinizin kullanıcılarına (veya kullanıcı grubuna) gerekli lisansların atandığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="00011-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="00011-151">Lisans atamanız gerekiyorsa, bu [yönergeleri](/azure/active-directory/fundamentals/license-users-groups)izleyin.</span><span class="sxs-lookup"><span data-stu-id="00011-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="00011-152">bu adımı yalnızca kullanıcıların HoloLens/mobil cihazını size kaydetmesi bekleniyorsa (üç seçenek bulunur), bu adımlar, şirketinizin kullanıcılarının (veya bir kullanıcı grubunun) cihaz ekleyebileceği şekilde emin olmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="00011-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="00011-153">**Seçenek 1:** Tüm kullanıcılara cihazları Azure AD 'ye ekleme izni verin.</span><span class="sxs-lookup"><span data-stu-id="00011-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="00011-154">**Azure Portal yönetici**  >  olarak oturum açın **Azure Active Directory**  >  **Cihazlar**  >  **cihaz Ayarlar**  >
 **Kullanıcıları, cihazları Azure AD 'ye *Tüm* kullanıcılara birleştirebileceği şekilde ayarla**</span><span class="sxs-lookup"><span data-stu-id="00011-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="00011-155">**Seçenek 2:** seçili kullanıcılara/gruplara cihazları azure ad 'ye eklemek için yönetici Azure Active Directory cihaz cihazı **olarak Azure portal oturum açma** izni verin  >    >    >  **Ayarlar**  >
 **kullanıcılar cihazları azure ad 'ye,** 
 ![ azure ad 'ye katılmış cihazların yapılandırmasını gösteren seçili görüntüye katabilir](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="00011-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="00011-156">**Seçenek 3:** Tüm kullanıcıların cihazlarını etki alanına katılmasını engelleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="00011-157">Bu, tüm cihazların el ile kaydedilmesi gerektiği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="00011-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="00011-158">Mobil Device Manager Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="00011-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="00011-159">Devam eden cihaz yönetimi</span><span class="sxs-lookup"><span data-stu-id="00011-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="00011-160">Bu adım yalnızca şirketiniz HoloLens yönetmeyi planlıyorsa gereklidir.</span><span class="sxs-lookup"><span data-stu-id="00011-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="00011-161">Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza göre değişir.</span><span class="sxs-lookup"><span data-stu-id="00011-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="00011-162">Çoğu genel işlevselliğe sahiptir ancak kullanıcı arabirimi yaygın olarak farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="00011-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="00011-163">[CSP 'ler (yapılandırma hizmeti sağlayıcıları)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) ağınızdaki cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="00011-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="00011-164">başvuru için [HoloLens csp 'lerin listesine](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="00011-165">[Uyumluluk ilkeleri](/intune/device-compliance-get-started) , cihazların kurumsal altyapınızda uyumlu olması için uyması gereken kural ve ayarlardır.</span><span class="sxs-lookup"><span data-stu-id="00011-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="00011-166">Uyumlu olmayan cihazlarda şirket kaynaklarına erişimi engellemek için bu ilkeleri koşullu erişimle birlikte kullanın.</span><span class="sxs-lookup"><span data-stu-id="00011-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="00011-167">Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="00011-168">[Uyumluluk Ilkesi oluşturun](/intune/protect/compliance-policy-create-windows).</span><span class="sxs-lookup"><span data-stu-id="00011-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="00011-169">Koşullu erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesini sağlar/reddeder.</span><span class="sxs-lookup"><span data-stu-id="00011-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="00011-170">Yararlı bulabileceğiniz iki belge, CA dağıtımınızı ve [En Iyi uygulamalarınızı](/azure/active-directory/conditional-access/best-practices) [planlıyor](/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="00011-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="00011-171">[Bu makalede](/intune/fundamentals/windows-holographic-for-business) , ıntune 'un HoloLens için yönetim araçları ele alım.</span><span class="sxs-lookup"><span data-stu-id="00011-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="00011-172">Cihaz profili oluşturma</span><span class="sxs-lookup"><span data-stu-id="00011-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="00011-173">Güncelleştirmeleri yönetme</span><span class="sxs-lookup"><span data-stu-id="00011-173">Manage updates</span></span>

<span data-ttu-id="00011-174">ıntune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil Windows 10 cihazları için güncelleştirme halkaları adlı bir özellik içerir.</span><span class="sxs-lookup"><span data-stu-id="00011-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="00011-175">Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yükleneceğini tespit eden bir grup ayar içerir.</span><span class="sxs-lookup"><span data-stu-id="00011-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="00011-176">Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="00011-177">Güncelleştirmeleri, güncelleştirmeye hazırsanız süresiz olarak duraklatıp de seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="00011-178">[Intune ile güncelleştirme halkalarını yapılandırma](/intune/windows-update-for-business-configure)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="00011-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="00011-179">Uygulama yönetimi</span><span class="sxs-lookup"><span data-stu-id="00011-179">Application management</span></span>

<span data-ttu-id="00011-180">HoloLens uygulamalarını yönetme:</span><span class="sxs-lookup"><span data-stu-id="00011-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="00011-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="00011-181">Microsoft Store</span></span>  
  <span data-ttu-id="00011-182">Microsoft Store, uygulamaları HoloLens dağıtmak ve kullanmak için en iyi yoldur.</span><span class="sxs-lookup"><span data-stu-id="00011-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="00011-183">mağazada zaten bulunan harika bir çekirdek HoloLens uygulamalar kümesi vardır veya [kendi kendinize yayımlayabilirsiniz](/windows/uwp/publish/).</span><span class="sxs-lookup"><span data-stu-id="00011-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="00011-184">depodaki tüm uygulamalar herkese açık olarak kullanılabilir, ancak kabul edilebilir değilse İş İçin Microsoft Store kullanıma alın.</span><span class="sxs-lookup"><span data-stu-id="00011-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="00011-185">İş İçin Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="00011-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="00011-186">İş İçin Microsoft Store ve eğitim, kurumsal ortamınız için özel bir depodır.</span><span class="sxs-lookup"><span data-stu-id="00011-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="00011-187">kuruluşunuzun uygulamalarını bulmak, almak, dağıtmak ve yönetmek için Windows 10 ve HoloLens yerleşik Microsoft Store kullanmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="00011-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="00011-188">Ayrıca ticari ortamınıza özgü olan ancak dünyayı olmayan uygulamaları dağıtmanıza imkan tanır.</span><span class="sxs-lookup"><span data-stu-id="00011-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="00011-189">Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi</span><span class="sxs-lookup"><span data-stu-id="00011-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="00011-190">Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş kolu uygulamalarını doğrudan bir kayıtlı cihaz kümesine dağıtmanın bir yolunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="00011-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="00011-191">[Intune uygulama yüklemesi](/intune/apps-deploy)için bu makaleye bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="00011-192">_önerilmez_ Cihaz portalı</span><span class="sxs-lookup"><span data-stu-id="00011-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="00011-193">uygulamalar, Windows cihaz portalı kullanılarak doğrudan HoloLens de yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="00011-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="00011-194">Bu, geliştirici modunun cihaz portalını kullanmak için etkinleştirilmesi gerektiğinden önerilmez.</span><span class="sxs-lookup"><span data-stu-id="00011-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="00011-195">[HoloLens uygulamalar yükleme](hololens-install-apps.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="00011-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="00011-196">Sertifikalar</span><span class="sxs-lookup"><span data-stu-id="00011-196">Certificates</span></span>

<span data-ttu-id="00011-197">Sertifika, MDM sağlayıcınız aracılığıyla dağıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="00011-198">Şirketiniz sertifika gerektiriyorsa Intune, PKCS, PFX ve SCEP 'yi destekler.</span><span class="sxs-lookup"><span data-stu-id="00011-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="00011-199">Şirketiniz için hangi sertifikanın doğru olduğunu anlamak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="00011-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="00011-200">Size en uygun sertifikayı öğrenmek için lütfen [sertifika yapılandırması](/intune/protect/certificates-configure) belgelerini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="00011-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="00011-201">HoloLens kimlik doğrulaması için sertifika kullanmayı planlıyorsanız PFX veya SCEP sizin için uygun olabilir.</span><span class="sxs-lookup"><span data-stu-id="00011-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="00011-202">[SCEP](/intune/protect/certificates-profile-scep)kullanımı için aşağıdaki adımlara bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="00011-203">Business Commercial Suite için holografik 'e yükseltme</span><span class="sxs-lookup"><span data-stu-id="00011-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="00011-204">Windows iş için holografik (ticari paket) yalnızca 1. gen cihaz HoloLens yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="00011-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="00011-205">profil HoloLens 2 cihaza uygulanmaz.</span><span class="sxs-lookup"><span data-stu-id="00011-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="00011-206">[Holographic Upgrade](/intune/configuration/holographic-upgrade) belgelerindeki Commercial Suite 'e yükseltme yönergelerini bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="00011-207">Microsoft Intune kullanarak bilgi noktası modunu yapılandırma</span><span class="sxs-lookup"><span data-stu-id="00011-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="00011-208">Microsoft Store ıntune 'a eşitleyin (aşağıdaki [yönergelere](/intune/apps/windows-store-for-business)bakın).</span><span class="sxs-lookup"><span data-stu-id="00011-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="00011-209">Uygulama ayarlarınızı denetleyin</span><span class="sxs-lookup"><span data-stu-id="00011-209">Check your app settings</span></span>
    1. <span data-ttu-id="00011-210">Microsoft Store iş hesabınızda oturum açın</span><span class="sxs-lookup"><span data-stu-id="00011-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="00011-211">**> ürünlerini ve hizmetlerini > uygulama ve yazılım > yönetme > özel mağaza kullanılabilirliği eşitlemek istediğiniz uygulamayı seçin > "Herkes" veya "belirli gruplar" ı seçin**</span><span class="sxs-lookup"><span data-stu-id="00011-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="00011-212">İstediğiniz uygulamayı görmüyorsanız, uygulamanız için depoyu arayarak uygulamayı "almanız" gerekir.</span><span class="sxs-lookup"><span data-stu-id="00011-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="00011-213">**Sağ üst köşedeki "ara" çubuğuna tıklayın > uygulamanın adını yazın > uygulamaya tıklayın > "Al" seçeneğini belirleyin**.</span><span class="sxs-lookup"><span data-stu-id="00011-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="00011-214">Uygulamalarınızı **ıntune > Istemci uygulamaları > uygulamalar** ' da görmüyorsanız uygulamalarınızı yeniden [eşitlemeniz](/intune/apps/windows-store-for-business#synchronize-apps) gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="00011-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="00011-215">Bilgi noktası modu için bir cihaz profili oluşturma</span><span class="sxs-lookup"><span data-stu-id="00011-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="00011-216">Farklı kullanıcıları, "Kullanıcı oturum açma türü" olarak "Azure AD" kullanarak farklı bilgi noktası modu deneyimleri olacak şekilde yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="00011-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="00011-217">Ancak, bu seçenek yalnızca çok uygulama bilgi noktası modunda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="00011-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="00011-218">Çoklu uygulama bilgi noktası modu, birden çok uygulama ile yalnızca bir uygulamayla birlikte çalışır.</span><span class="sxs-lookup"><span data-stu-id="00011-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune 'da bilgi noktası modunun yapılandırılmasını gösteren resim](images/aad-kioskmode.png)

<span data-ttu-id="00011-220">Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="00011-221">MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanmanız gerekiyorsa [HoloLens bilgi noktası](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="00011-222">Sertifikalar ve kimlik doğrulama</span><span class="sxs-lookup"><span data-stu-id="00011-222">Certificates and Authentication</span></span>

<span data-ttu-id="00011-223">Sertifikalar, MDM aracılığıyla dağıtılabilir ( [MDM bölümünde](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)"Sertifikalar" konusuna bakın).</span><span class="sxs-lookup"><span data-stu-id="00011-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="00011-224">sertifikalar, paket sağlama aracılığıyla HoloLens da dağıtılabilir.</span><span class="sxs-lookup"><span data-stu-id="00011-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="00011-225">lütfen daha fazla bilgi için [HoloLens sağlama](hololens-provisioning.md) konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="00011-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="00011-226">Ek Intune hızlı bağlantıları</span><span class="sxs-lookup"><span data-stu-id="00011-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="00011-227">[Profil oluşturma:](/intune/configuration/device-profile-create) Profiller, kuruluşunuzdaki cihazlara gönderilecek ayarları eklemenize ve yapılandırmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="00011-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

