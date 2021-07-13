---
title: Lisans gereksinimleri
description: mobil cihaz yönetimi, HoloLens ve uzaktan yardım için ihtiyacınız olan tüm lisans gereksinimleri ve yönergeleriyle güncel tutun.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635900"
---
# <a name="license-requirements"></a><span data-ttu-id="b5362-103">Lisans gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="b5362-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="b5362-104">HoloLens 2 cihaz (yönetilen)</span><span class="sxs-lookup"><span data-stu-id="b5362-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="b5362-105">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="b5362-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="b5362-106">Active Directory (AD) HoloLens cihazlarını yönetmek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="b5362-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="b5362-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) veya başka bir MDM.</span><span class="sxs-lookup"><span data-stu-id="b5362-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="b5362-108">[HoloLens 2 için Windows Autopilot](hololens2-autopilot.md)-hem bt yöneticileri hem de son kullanıcılar için sağlama deneyimini basitleştirir.</span><span class="sxs-lookup"><span data-stu-id="b5362-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="b5362-109">bt yöneticileri HoloLens 2 ilkeyi önceden yapılandırabilir ve ilk önyükleme sonrasında cihazlar, sıfır son kullanıcı etkileşimi ile iş için kullanıma yönelik duruma dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="b5362-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="b5362-110">Windows Autopilot, önce [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) ve [otomatik kayıt](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 'nin düşük dokunma Autopilot akışı ve cihaz dağıtımı için yapılandırılmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b5362-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="b5362-111">İş kullanım örneği:</span><span class="sxs-lookup"><span data-stu-id="b5362-111">Business Use Case:</span></span> 

- <span data-ttu-id="b5362-112">[Dağıtım senaryosu A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) -kavram kanıtı veya pilot dağıtım.</span><span class="sxs-lookup"><span data-stu-id="b5362-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="b5362-113">[Dağıtım senaryosu B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) -ölçekli dağıtım.</span><span class="sxs-lookup"><span data-stu-id="b5362-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="b5362-114">HoloLens 2 cihaz-yalnızca (yönetilmeyen)</span><span class="sxs-lookup"><span data-stu-id="b5362-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="b5362-115">Bir Microsoft hesabı (MSA) veya yerel hesap kullanırken bu hesaplar için ek lisans gerekmez.</span><span class="sxs-lookup"><span data-stu-id="b5362-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="b5362-116">Yerel hesap</span><span class="sxs-lookup"><span data-stu-id="b5362-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="b5362-117">bu hesabın Windows yapılandırma tasarımcısı (wcd) ile bir süre önce [sağlanması](hololens-provisioning.md#provisioning-package-hololens-wizard) gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5362-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="b5362-118">Microsoft hesabı (MSA)</span><span class="sxs-lookup"><span data-stu-id="b5362-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="b5362-119">Bu hesaplardan birini kullanan bir cihaz için birden fazla kullanıcı desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="b5362-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="b5362-120">İş kullanım örneği:</span><span class="sxs-lookup"><span data-stu-id="b5362-120">Business Use Case:</span></span> 

- <span data-ttu-id="b5362-121">[Dağıtım senaryosu C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -çevrimdışı veya güvenli dağıtım.</span><span class="sxs-lookup"><span data-stu-id="b5362-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="b5362-122">Dynamics 365 lisanslama ve gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="b5362-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="b5362-123">Dynamics 365 uzaktan yardım</span><span class="sxs-lookup"><span data-stu-id="b5362-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="b5362-124">Yönetici</span><span class="sxs-lookup"><span data-stu-id="b5362-124">Admin</span></span>

- <span data-ttu-id="b5362-125">Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)</span><span class="sxs-lookup"><span data-stu-id="b5362-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="b5362-126">[Uzaktan Yardım aboneliği](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="b5362-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="b5362-127">Dynamics 365 uzaktan yardım kullanıcısı</span><span class="sxs-lookup"><span data-stu-id="b5362-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="b5362-128">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="b5362-128">Azure AD account</span></span>

- <span data-ttu-id="b5362-129">Uzaktan Yardım lisansı</span><span class="sxs-lookup"><span data-stu-id="b5362-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="b5362-130">Microsoft Teams, uzaktan yardım ile paketlenmiştir</span><span class="sxs-lookup"><span data-stu-id="b5362-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="b5362-131">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="b5362-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="b5362-132">Microsoft Teams kullanıcı</span><span class="sxs-lookup"><span data-stu-id="b5362-132">Microsoft Teams user</span></span>

- <span data-ttu-id="b5362-133">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="b5362-133">Azure AD account</span></span>

- <span data-ttu-id="b5362-134">Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="b5362-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="b5362-135">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="b5362-135">Network connectivity</span></span>

<span data-ttu-id="b5362-136">Bu [çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5362-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="b5362-137">Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.</span><span class="sxs-lookup"><span data-stu-id="b5362-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="b5362-138">Dynamics 365 kılavuzlar</span><span class="sxs-lookup"><span data-stu-id="b5362-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="b5362-139">Yönetici</span><span class="sxs-lookup"><span data-stu-id="b5362-139">Admin</span></span>

- <span data-ttu-id="b5362-140">Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)</span><span class="sxs-lookup"><span data-stu-id="b5362-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="b5362-141">Dynamics 365 [Kılavuzlar aboneliği veya ücretsiz deneme](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="b5362-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="b5362-142">Kılavuzlar yazarı</span><span class="sxs-lookup"><span data-stu-id="b5362-142">Guides Author</span></span>

1. <span data-ttu-id="b5362-143">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="b5362-143">Azure AD account</span></span>
1. [<span data-ttu-id="b5362-144">Dynamics 365 kılavuzlar lisansı</span><span class="sxs-lookup"><span data-stu-id="b5362-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="b5362-145">Bir PC 'de veya HoloLens yüklü olan Dynamics 365 kılavuzlar uygulaması</span><span class="sxs-lookup"><span data-stu-id="b5362-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="b5362-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (analiz panosunu görüntülemek için kullanılır)</span><span class="sxs-lookup"><span data-stu-id="b5362-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="b5362-147">Yazar rolü (kılavuz oluşturmak için)</span><span class="sxs-lookup"><span data-stu-id="b5362-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="b5362-148">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="b5362-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="b5362-149">Kılavuzlar kullanıcısı</span><span class="sxs-lookup"><span data-stu-id="b5362-149">Guides User</span></span>

1. <span data-ttu-id="b5362-150">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="b5362-150">Azure AD account</span></span>
1. [<span data-ttu-id="b5362-151">Dynamics 365 kılavuzlar lisansı</span><span class="sxs-lookup"><span data-stu-id="b5362-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="b5362-152">Dynamics 365 kılavuzlar uygulaması HoloLens yüklendi</span><span class="sxs-lookup"><span data-stu-id="b5362-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="b5362-153">İşleç rolü (test etmek veya kılavuzlar kullanmak için)</span><span class="sxs-lookup"><span data-stu-id="b5362-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="b5362-154">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="b5362-154">Network Connectivity</span></span>
