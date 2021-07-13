---
title: ticari bir ortamda HoloLens 2 dağıtımı planlama
description: altyapı, azure active directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtmak ve yönetmek için temel gereksinimler hakkında bilgi edinin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639089"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="09d01-103">ticari bir ortamda HoloLens 2 dağıtımı planlama</span><span class="sxs-lookup"><span data-stu-id="09d01-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="09d01-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="09d01-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="09d01-105">bu genel bakış, bt uzmanlarının bir kuruluşta Microsoft HoloLens 2 cihaz dağıtma ve yönetme ile ilgili hususları anlamalarına yardımcı olmaya yöneliktir.</span><span class="sxs-lookup"><span data-stu-id="09d01-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="09d01-106">cihaz son kullanıcıları için bkz. [HoloLens 2](hololens2-setup.md) ' yi kullanmaya başlamak için kullanıma hazırlanıyor.</span><span class="sxs-lookup"><span data-stu-id="09d01-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="09d01-107">HoloLens 2, kuruluşlar için güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan Windows 10 Holographic çalışır.</span><span class="sxs-lookup"><span data-stu-id="09d01-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="09d01-108">Windows 10 Holographic, şirketlerinin cihazları, verileri ve uygulamaları üzerinde denetim sağlamak için uçtan uca cihaz yaşam döngüsü yönetimini destekler.</span><span class="sxs-lookup"><span data-stu-id="09d01-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="09d01-109">HoloLens 2, standart yaşam döngüsü uygulamalarına, cihaz kaydı, yapılandırma ve uygulama yönetiminden kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak bakım ve kullanımdan kaldırma için kolayca eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="09d01-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="09d01-110">aşağıdaki adımlar ve video, kuruluşunuzda HoloLens 2 benimseme sürecinde size rehberlik etmenize yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="09d01-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![1. Adım](images/1green.png)| <br/> <span data-ttu-id="09d01-112">**[ortak dağıtım senaryoları](hololens-requirements.md)**: dağıtım senaryolarını anlayın ve HoloLens 2 cihaz dağıtmak için gereken çekirdek bileşenleri keşfedebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="09d01-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![2. Adım](images/2green.png)| <br/> <span data-ttu-id="09d01-114">**[hazırlama](#prepare)**: HoloLens 2 için gereken altyapı temelleri hakkında bilgi sahibi olun.</span><span class="sxs-lookup"><span data-stu-id="09d01-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![3. Adım](images/3green.png) | <br/> <span data-ttu-id="09d01-116">**[Yapılandırma](#configure)**: bulut tabanlı bir dağıtım için gerekli bileşenlerinizi nasıl yapılandıracağınızı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="09d01-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![4. Adım](images/4green.png) | <br/> <span data-ttu-id="09d01-118">**[Dağıtım](#deploy)**: cihazlarınızı dağıtmayı ve uygulamalarınızı güvenli ve etkili bir şekilde dağıtmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="09d01-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![5. Adım](images/5green.png) | <br/> <span data-ttu-id="09d01-120">**[bakım](#maintain)**: HoloLens 2 cihazlarınızın durumunu doğru bir şekilde korumak ve kurumsal ilkeyle uyumluluğu sağlamak için gerekenleri öğrenin.</span><span class="sxs-lookup"><span data-stu-id="09d01-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="09d01-121">Hazırlama</span><span class="sxs-lookup"><span data-stu-id="09d01-121">Prepare</span></span>

<span data-ttu-id="09d01-122">HoloLens 2 özelliklerini tam olarak desteklemek için gereken temel altyapı hizmetleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="09d01-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="09d01-123">Bileşen</span><span class="sxs-lookup"><span data-stu-id="09d01-123">Component</span></span> | <span data-ttu-id="09d01-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09d01-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="09d01-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="09d01-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="09d01-126">HoloLens 2 için kimlik ve erişim yönetimi sağlar</span><span class="sxs-lookup"><span data-stu-id="09d01-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="09d01-127">Mobil Cihaz Yönetimi</span><span class="sxs-lookup"><span data-stu-id="09d01-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="09d01-128">kiracınıza bağlı HoloLens 2 cihazı yönetir</span><span class="sxs-lookup"><span data-stu-id="09d01-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="09d01-129">Wi-Fi ağı</span><span class="sxs-lookup"><span data-stu-id="09d01-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="09d01-130">Wi-Fi kullanılabilir ve cihazlar Internet 'e bağlanabilir</span><span class="sxs-lookup"><span data-stu-id="09d01-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="09d01-131">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="09d01-131">Configure</span></span>

<span data-ttu-id="09d01-132">kuruluşunuzun Azure AD kiracısına ve MDM 'ye HoloLens 2 ' ye kaydolma ve yapılandırma için düşük dokunma çözümleri olarak ıntune ve Autopilot kullanın.</span><span class="sxs-lookup"><span data-stu-id="09d01-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="09d01-133">Bileşen</span><span class="sxs-lookup"><span data-stu-id="09d01-133">Component</span></span> | <span data-ttu-id="09d01-134">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09d01-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="09d01-135">Otomatik kayıt</span><span class="sxs-lookup"><span data-stu-id="09d01-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="09d01-136">İlk oturum açma işleminden sonra cihazlar Azure AD 'ye otomatik olarak kaydolduktan sonra MDM 'ye kaydolur</span><span class="sxs-lookup"><span data-stu-id="09d01-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="09d01-137">Uygulama lisansları</span><span class="sxs-lookup"><span data-stu-id="09d01-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="09d01-138">Kullanıcılara, Kullanıcı gruplarına veya cihaz gruplarına uygulanabilir</span><span class="sxs-lookup"><span data-stu-id="09d01-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="09d01-139">Azure kullanıcıları ve grupları</span><span class="sxs-lookup"><span data-stu-id="09d01-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="09d01-140">HoloLens 2 için yapılandırmaların ve lisansların atanmasını sağlar</span><span class="sxs-lookup"><span data-stu-id="09d01-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="09d01-141">Dağıtma</span><span class="sxs-lookup"><span data-stu-id="09d01-141">Deploy</span></span>

<span data-ttu-id="09d01-142">HoloLens 2 cihazlarınızı dağıtın ve yapılandırmalarını doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="09d01-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="09d01-143">Bileşen</span><span class="sxs-lookup"><span data-stu-id="09d01-143">Component</span></span> | <span data-ttu-id="09d01-144">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09d01-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="09d01-145">Kayıt doğrulama</span><span class="sxs-lookup"><span data-stu-id="09d01-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="09d01-146">cihazın azure AD 'ye Ayarlar veya azure portalından katıldığını doğrulama</span><span class="sxs-lookup"><span data-stu-id="09d01-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="09d01-147">Sertifika doğrulama</span><span class="sxs-lookup"><span data-stu-id="09d01-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="09d01-148">Ayarları denetleyin ve doğru şekilde dağıtıldığını doğrulayın</span><span class="sxs-lookup"><span data-stu-id="09d01-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="09d01-149">Uygulama yüklemelerini doğrula</span><span class="sxs-lookup"><span data-stu-id="09d01-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="09d01-150">uygulamanın mevcut olduğunu ve HoloLens 2 ' de çalıştığını doğrulayın</span><span class="sxs-lookup"><span data-stu-id="09d01-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="09d01-151">Bakım</span><span class="sxs-lookup"><span data-stu-id="09d01-151">Maintain</span></span>

<span data-ttu-id="09d01-152">HoloLens 2 ve uygulamalarının güncel kalmasını sağlamak için MDM sisteminizle birlikte iş için Windows Update veya Microsoft Store kullanın.</span><span class="sxs-lookup"><span data-stu-id="09d01-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="09d01-153">Bileşen</span><span class="sxs-lookup"><span data-stu-id="09d01-153">Component</span></span> | <span data-ttu-id="09d01-154">Açıklama</span><span class="sxs-lookup"><span data-stu-id="09d01-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="09d01-155">güncelleştirme HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="09d01-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="09d01-156">iş için Windows güncelleştirmeleri sayesinde güncelleştirmeleri gerektiği şekilde yapılandırın</span><span class="sxs-lookup"><span data-stu-id="09d01-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="09d01-157">Uygulamaları güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="09d01-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="09d01-158">MDM sisteminiz veya Microsoft Store ile yapılandırma</span><span class="sxs-lookup"><span data-stu-id="09d01-158">Configure through your MDM system or the Microsoft Store</span></span>
