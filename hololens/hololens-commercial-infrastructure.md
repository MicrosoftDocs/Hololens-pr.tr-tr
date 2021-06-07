---
title: HoloLens için Altyapı Yönergeleri
description: Kablosuz ağ desteği, uzaktan yardım ve mobil cihaz yönetimi dahil olmak üzere HoloLens cihazları için altyapı yönergeleri hakkında bilgi edinebilirsiniz.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380157"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="9b027-103">HoloLens için Anızı Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9b027-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="9b027-104">Belgenin bu bölümü için aşağıdaki kişiler gerekir:</span><span class="sxs-lookup"><span data-stu-id="9b027-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="9b027-105">Ara sunucuda/güvenlik duvarında değişiklik yapma izinlerine sahip Ağ Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="9b027-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="9b027-106">Azure Active Directory Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="9b027-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="9b027-107">Mobil Cihaz Yöneticisi Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="9b027-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="9b027-108">Altyapı Gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="9b027-108">Infrastructure Requirements</span></span>

<span data-ttu-id="9b027-109">HoloLens, temel olarak Azure ile tümleştirilmiş bir Windows mobil cihazıdır.</span><span class="sxs-lookup"><span data-stu-id="9b027-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="9b027-110">En iyi, kablosuz ağ kullanılabilirliği (wi-fi) ve kablosuz ağ erişimi olan ticari ortamlarda Microsoft hizmetleri.</span><span class="sxs-lookup"><span data-stu-id="9b027-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="9b027-111">Kritik bulut hizmetleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9b027-111">Critical cloud services include:</span></span>

- <span data-ttu-id="9b027-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9b027-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="9b027-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="9b027-113">Windows Update (WU)</span></span>

<span data-ttu-id="9b027-114">Ticari müşterilerin HoloLens cihazlarını büyük ölçekte yönetmek için kurumsal mobilite yönetimi (EMM) veya mobil cihaz yönetimi (MDM) altyapısına ihtiyacı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9b027-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="9b027-115">Bu kılavuzda [örnek olarak Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) ancak Microsoft İlkesi'ne tam destek veren tüm sağlayıcılar HoloLens'i destekleyene kadar her sağlayıcıyı destekler.</span><span class="sxs-lookup"><span data-stu-id="9b027-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="9b027-116">Mobil cihaz yönetimi sağlayıcınıza HoloLens 2'ye destek olup olduklarını sorun.</span><span class="sxs-lookup"><span data-stu-id="9b027-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="9b027-117">HoloLens sınırlı bir bulut bağlantısız deneyimi destekler.</span><span class="sxs-lookup"><span data-stu-id="9b027-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="9b027-118">Kablosuz ağ EAP desteği</span><span class="sxs-lookup"><span data-stu-id="9b027-118">Wireless network EAP support</span></span>

- <span data-ttu-id="9b027-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="9b027-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="9b027-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="9b027-120">PEAP-TLS</span></span>
- <span data-ttu-id="9b027-121">TLS</span><span class="sxs-lookup"><span data-stu-id="9b027-121">TLS</span></span>
- <span data-ttu-id="9b027-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="9b027-122">TTLS-CHAP</span></span>
- <span data-ttu-id="9b027-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="9b027-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="9b027-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="9b027-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="9b027-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="9b027-125">TTLS-PAP</span></span>
- <span data-ttu-id="9b027-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="9b027-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="9b027-127">HoloLens'e Özgü Ağ Gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="9b027-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="9b027-128">Ağ güvenlik [duvarında bu](hololens-offline.md) uç nokta listesine izin verili olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="9b027-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="9b027-129">Bu, HoloLens'in düzgün çalışmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="9b027-130">Remote Assist'e Özgü Ağ Gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="9b027-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="9b027-131">Remote Assist'in en iyi performansı için önerilen bant genişliği 1,5 Mb/sn'dir.</span><span class="sxs-lookup"><span data-stu-id="9b027-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="9b027-132">Ek bilgi [için ayrıntılı ağ](https://docs.microsoft.com/MicrosoftTeams/prepare-network) gereksinimlerine bakın.</span><span class="sxs-lookup"><span data-stu-id="9b027-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="9b027-133">**(Ağ hızınız en az 1,5 Mb/sn değilse Remote Assist'in çalışmaya devam eder. Ancak kalite düşük olabilir).**</span><span class="sxs-lookup"><span data-stu-id="9b027-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="9b027-134">Microsoft Teams'in çalışmasını sağlamak için ağ güvenlik duvarında bu bağlantı noktalarına ve URL'lere izin verili olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="9b027-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="9b027-135">bağlantı noktalarının en son [listesiyle güncel kalın.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="9b027-135">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="9b027-136">Remote Assist için belirli Ağ [Gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)</span><span class="sxs-lookup"><span data-stu-id="9b027-136">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="9b027-137">Microsoft Teams için kuruluş [ağına hazırlanma hakkında daha fazla bilgi](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="9b027-137">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="9b027-138">Kılavuzlar Belirli Ağ Gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="9b027-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="9b027-139">Kılavuzlar yalnızca uygulamayı indirmek ve kullanmak için ağ erişimi gerektirir.</span><span class="sxs-lookup"><span data-stu-id="9b027-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="9b027-140">Azure Active Directory Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9b027-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="9b027-141">Bu adım yalnızca, şirketiniz HoloLens'i yönetmeyi planlıyorsa gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9b027-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="9b027-142">Azure AD Lisansına sahip olduğundan emin olmak.</span><span class="sxs-lookup"><span data-stu-id="9b027-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="9b027-143">Ek [bilgi için lütfen HoloLens](hololens-licenses-requirements.md) Lisans Gereksinimleri.</span><span class="sxs-lookup"><span data-stu-id="9b027-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="9b027-144">Otomatik Kayıt kullanmayı planlıyorsanız Azure AD kaydı [yapılandırmanız gerekir.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="9b027-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="9b027-145">Şirket kullanıcılarının şirket içinde (Azure AD) Azure Active Directory emin olmak.</span><span class="sxs-lookup"><span data-stu-id="9b027-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="9b027-146">Kullanıcı eklemek için [aşağıdaki](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) yönergelere bakın.</span><span class="sxs-lookup"><span data-stu-id="9b027-146">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="9b027-147">Benzer lisanslara ihtiyacı olan kullanıcıların aynı gruba eklenmelerini öneririz.</span><span class="sxs-lookup"><span data-stu-id="9b027-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="9b027-148">Grup Oluşturma</span><span class="sxs-lookup"><span data-stu-id="9b027-148">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="9b027-149">Gruplara kullanıcı ekleme</span><span class="sxs-lookup"><span data-stu-id="9b027-149">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="9b027-150">Şirket kullanıcılarının (veya kullanıcı grubunun) gerekli lisanslara atanmalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="9b027-151">Lisans atamanız gerekirse şu yönergeleri [izleyin.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="9b027-151">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="9b027-152">Bu adımı yalnızca kullanıcıların HoloLens/Mobile cihazlarını size kaydetmesi bekleniyorsa uygulayın (Üç seçenek vardır) Bu adımlar, şirket kullanıcılarının (veya bir kullanıcı grubunun) cihaz ekleyeci olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="9b027-153">**1. Seçenek:** Tüm kullanıcılara cihazları Azure AD'ye katma izni verme.</span><span class="sxs-lookup"><span data-stu-id="9b027-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="9b027-154">**Yönetici olarak Azure portal oturum açın**  >  **Azure Active Directory**  >  **Cihazlar**  >  **Cihaz Ayarları**  >
 **Kullanıcılar cihazları Azure AD'ye katabilirsiniz'i All olarak *ayarlayın***</span><span class="sxs-lookup"><span data-stu-id="9b027-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="9b027-155">**2. Seçenek:** Seçili kullanıcılara/gruplara cihazları Azure AD'ye katma izni verme **Yönetici olarak Azure portal'da** oturum açma Azure Active Directory Cihazları Cihaz Ayarları Kullanıcılar cihazları Azure AD'ye katarak  >    >    >    >
 **Azure AD'ye** 
 ![ katılabilir](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="9b027-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="9b027-156">**3. Seçenek:** Tüm kullanıcıların cihazlarını etki alanına eklemesini engelleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="9b027-157">Bu, tüm cihazların el ile kaydolması gerektirmektedir.</span><span class="sxs-lookup"><span data-stu-id="9b027-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="9b027-158">Mobil Cihaz Yöneticisi Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9b027-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="9b027-159">Devam eden cihaz yönetimi</span><span class="sxs-lookup"><span data-stu-id="9b027-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="9b027-160">Bu adım yalnızca, şirket HoloLens'i yönetmeyi planlıyorsa gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9b027-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="9b027-161">Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="9b027-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="9b027-162">Çoğu genel işleve sahiptir ancak kullanıcı arabirimi büyük ölçüde değişiklik gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="9b027-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="9b027-163">[CSP'ler (Yapılandırma](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Hizmeti Sağlayıcıları), ağ üzerinde cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="9b027-163">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="9b027-164">Başvuru için [HoloLens CSP'leri](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) listesine bakın.</span><span class="sxs-lookup"><span data-stu-id="9b027-164">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="9b027-165">[Uyumluluk ilkeleri,](https://docs.microsoft.com/intune/device-compliance-get-started) cihazların kurumsal altyapınıza uyumlu olması için karşılaması gereken kurallar ve ayarlardır.</span><span class="sxs-lookup"><span data-stu-id="9b027-165">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="9b027-166">Uyumlu olmayan cihazların şirket kaynaklarına erişimini engellemek için Koşullu Erişim ile bu ilkeleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="9b027-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="9b027-167">Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="9b027-168">[Uyumluluk İlkesi oluşturun.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="9b027-168">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="9b027-169">Koşullu Erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesine izin verir/erişimini geri verir.</span><span class="sxs-lookup"><span data-stu-id="9b027-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="9b027-170">CA Dağıtımınızı planlama ve En İyi [Yöntemler belgelerini yararlı](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) [bulabilirsiniz.](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="9b027-170">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="9b027-171">[Bu makalede,](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) Intune'un HoloLens için yönetim araçları hakkında bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-171">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="9b027-172">Cihaz profili oluşturma</span><span class="sxs-lookup"><span data-stu-id="9b027-172">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="9b027-173">Güncelleştirmeleri yönetme</span><span class="sxs-lookup"><span data-stu-id="9b027-173">Manage updates</span></span>

<span data-ttu-id="9b027-174">Intune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil olmak üzere Windows 10 cihazlar için güncelleştirme halkaları adlı bir özellik içerir.</span><span class="sxs-lookup"><span data-stu-id="9b027-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="9b027-175">Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yük olduğunu belirleyen bir grup ayar içerir.</span><span class="sxs-lookup"><span data-stu-id="9b027-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="9b027-176">Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="9b027-177">Güncelleştirmeleri güncelleştirmeye hazır olana kadar süresiz olarak duraklatmayı da seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="9b027-178">[Intune ile güncelleştirme halkalarını yapılandırma hakkında daha fazla bilgi okuyun.](https://docs.microsoft.com/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="9b027-178">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="9b027-179">Uygulama yönetimi</span><span class="sxs-lookup"><span data-stu-id="9b027-179">Application management</span></span>

<span data-ttu-id="9b027-180">HoloLens uygulamalarını yönetmek için:</span><span class="sxs-lookup"><span data-stu-id="9b027-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="9b027-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9b027-181">Microsoft Store</span></span>  
  <span data-ttu-id="9b027-182">Bu Microsoft Store, HoloLens'de uygulamaları dağıtmanın ve tüketmenin en iyi yolu.</span><span class="sxs-lookup"><span data-stu-id="9b027-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="9b027-183">Mağazada zaten bulunan çok çeşitli temel HoloLens uygulamaları vardır veya kendi uygulamalarınızı [yayımlayın.](https://docs.microsoft.com/windows/uwp/publish/)</span><span class="sxs-lookup"><span data-stu-id="9b027-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="9b027-184">Mağazada bulunan tüm uygulamalar herkese açık bir şekilde kullanılabilir, ancak kabul edilebilir değilse uygulamanın genel kullanıma İş İçin Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="9b027-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="9b027-185">İş İçin Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9b027-185">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="9b027-186">İş İçin Microsoft Store ve Eğitim, kurumsal ortamınız için özel bir depodur.</span><span class="sxs-lookup"><span data-stu-id="9b027-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="9b027-187">Bu araç, Microsoft Store ve HoloLens Windows 10 de yerleşik olarak yer alan uygulamaları kullanarak, uygulamaları bulmanızı, edinmenizi, dağıtmanızı ve yönetmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="9b027-188">Ayrıca, ticari ortamınıza özgü ancak dünyaya değil, uygulamaları dağıtmanıza da olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="9b027-189">Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi</span><span class="sxs-lookup"><span data-stu-id="9b027-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="9b027-190">Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş hattı uygulamalarını doğrudan kayıtlı bir cihaz kümesine dağıtmak için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="9b027-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="9b027-191">[Intune uygulaması yüklemesi için bu makaleye bakın.](https://docs.microsoft.com/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="9b027-191">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="9b027-192">_önerilmez_ Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="9b027-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="9b027-193">Uygulamalar doğrudan HoloLens'e de doğrudan sanal Windows Cihaz Portalı.</span><span class="sxs-lookup"><span data-stu-id="9b027-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="9b027-194">Geliştirici Modunun cihaz portalını kullanmak için etkinleştirilmesi gerektirildiğinden bu önerilmez.</span><span class="sxs-lookup"><span data-stu-id="9b027-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="9b027-195">[HoloLens'e uygulama yükleme hakkında daha fazla bilgi edinin.](https://docs.microsoft.com/hololens/hololens-install-apps)</span><span class="sxs-lookup"><span data-stu-id="9b027-195">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <a name="certificates"></a><span data-ttu-id="9b027-196">Sertifikalar</span><span class="sxs-lookup"><span data-stu-id="9b027-196">Certificates</span></span>

<span data-ttu-id="9b027-197">Sertifikaları MDM sağlayıcınız aracılığıyla dağıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="9b027-198">Şirketiniz sertifika gerektiriyorsa, Intune PKCS, PFX ve SCEP'yi destekler.</span><span class="sxs-lookup"><span data-stu-id="9b027-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="9b027-199">Hangi sertifikanın şirket için doğru olduğunu anlamak önemlidir.</span><span class="sxs-lookup"><span data-stu-id="9b027-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="9b027-200">Hangi sertifikanın [sizin için en](https://docs.microsoft.com/intune/protect/certificates-configure) uygun olduğunu belirlemek için lütfen sertifika yapılandırmaları belgelerini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="9b027-200">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="9b027-201">HoloLens Kimlik Doğrulaması için sertifika kullanmayı planlıyorsanız, PFX veya SCEP sizin için uygun olabilir.</span><span class="sxs-lookup"><span data-stu-id="9b027-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="9b027-202">SCEP kullanmak için [aşağıdaki adımlara bakın.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="9b027-202">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="9b027-203">Holographics for Business Commercial Suite'e Yükseltme</span><span class="sxs-lookup"><span data-stu-id="9b027-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="9b027-204">Windows Holographics for Business (ticari paket), yalnızca HoloLens 1. nesil cihazlara yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="9b027-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="9b027-205">Profil HoloLens 2 cihazlarına uygulanmaz.</span><span class="sxs-lookup"><span data-stu-id="9b027-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="9b027-206">Holografik yükseltme belgelerinde ticari pakete yükseltme [yönergelerini](https://docs.microsoft.com/intune/configuration/holographic-upgrade) bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="9b027-207">Microsoft Intune Kullanarak Bilgi Noktası Modunu Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="9b027-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="9b027-208">Eşitleme Microsoft Store Intune'a (Aşağıdaki yönergelere [bakın).](https://docs.microsoft.com/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="9b027-208">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="9b027-209">Uygulama ayarlarınızı denetleme</span><span class="sxs-lookup"><span data-stu-id="9b027-209">Check your app settings</span></span>
    1. <span data-ttu-id="9b027-210">Microsoft Store Business hesabınızla oturum açın</span><span class="sxs-lookup"><span data-stu-id="9b027-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="9b027-211">**> Ürün ve Hizmetleri > Uygulamaları ve Yazılımlarını Yönetme > Eşitlemek istediğiniz uygulamayı seçin > Özel Mağaza Kullanılabilirliği > "Herkes" veya "Belirli Gruplar"ı seçin**</span><span class="sxs-lookup"><span data-stu-id="9b027-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="9b027-212">Istediğiniz uygulamayı görmüyorsanız mağazada uygulama arayarak uygulamayı "ala" gerekir.</span><span class="sxs-lookup"><span data-stu-id="9b027-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="9b027-213">**Sağ üst köşedeki "Ara"** çubuğuna tıklayın > uygulamanın adını yazın ve > tıklayın ve "Al" > seçin.</span><span class="sxs-lookup"><span data-stu-id="9b027-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="9b027-214">Uygulamalarınızı Intune'da > İstemci Uygulamaları **> Uygulamalar'da görmüyorsanız,** uygulamalarınızı [yeniden eşitlemeniz gerekir.](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)</span><span class="sxs-lookup"><span data-stu-id="9b027-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="9b027-215">Bilgi Noktası modu için cihaz profili oluşturma</span><span class="sxs-lookup"><span data-stu-id="9b027-215">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="9b027-216">"Kullanıcı oturum açma türü" olarak "Azure AD" kullanarak farklı kullanıcıları farklı Bilgi Noktası Modu deneyimleri olacak şekilde yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9b027-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="9b027-217">Ancak, bu seçenek yalnızca Çoklu Uygulama bilgi noktası modunda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9b027-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="9b027-218">Çoklu Uygulama bilgi noktası modu yalnızca bir uygulamayla ve birden çok uygulamayla çalışır.</span><span class="sxs-lookup"><span data-stu-id="9b027-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Intune'da Bilgi Noktası Modu Yapılandırmasını gösteren resim](images/aad-kioskmode.png)

<span data-ttu-id="9b027-220">Diğer MDM hizmetleri için yönergeler için sağlayıcınızın belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="9b027-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="9b027-221">MDM hizmetinize bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanıyorsanız [HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) bilgi noktası yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="9b027-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="9b027-222">Sertifikalar ve Kimlik Doğrulaması</span><span class="sxs-lookup"><span data-stu-id="9b027-222">Certificates and Authentication</span></span>

<span data-ttu-id="9b027-223">Sertifikalar MDM'ler aracılığıyla dağıtılabilir (MDM Bölümünde "sertifikalar" [bölümüne bakın).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="9b027-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="9b027-224">Sertifikalar, paket sağlama aracılığıyla HoloLens'e de dağıtılabilir.</span><span class="sxs-lookup"><span data-stu-id="9b027-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="9b027-225">Daha fazla [bilgi için lütfen bkz. HoloLens](hololens-provisioning.md) Sağlama.</span><span class="sxs-lookup"><span data-stu-id="9b027-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="9b027-226">Ek Intune Hızlı Bağlantıları</span><span class="sxs-lookup"><span data-stu-id="9b027-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="9b027-227">[Profil Oluşturma:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiller, kuruluşta cihazlara gelecek ayarları eklemenize ve yapılandırmanıza olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="9b027-227">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

