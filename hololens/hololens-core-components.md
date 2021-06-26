---
title: Ticari bir ortamda HoloLens 2 dağıtımını planlama
description: Altyapı, Azure Active Directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens'i dağıtmak ve yönetmek için temel ihtiyaçları öğrenin.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961477"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="28abb-103">Ticari bir ortamda HoloLens 2 dağıtımını planlama</span><span class="sxs-lookup"><span data-stu-id="28abb-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="28abb-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="28abb-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="28abb-105">Bu genel bakış, BT uzmanlarının kuruluş içindeki 2 cihazı dağıtmaya ve yönetmeye Microsoft HoloLens dikkat edilmesi gerekenleri anlamalarında yardımcı olmak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="28abb-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="28abb-106">Cihaz son kullanıcıları için [bkz. Çalışmaya başlamanın](hololens2-setup.md) temelleri.</span><span class="sxs-lookup"><span data-stu-id="28abb-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="28abb-107">HoloLens 2, Windows 10 Holographic güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan sanal ağlarda çalışır.</span><span class="sxs-lookup"><span data-stu-id="28abb-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="28abb-108">Windows 10 Holographic, şirketlere cihazları, verileri ve uygulamaları üzerinde denetim vermek için uz-2 4 cihaz yaşam döngüsü yönetimini destekler.</span><span class="sxs-lookup"><span data-stu-id="28abb-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="28abb-109">HoloLens 2, kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak cihaz kaydı, yapılandırma ve uygulama yönetiminden bakım ve kullanımdan sonra standart yaşam döngüsü uygulamalarına kolayca dahil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="28abb-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="28abb-110">Aşağıdaki adımlar, HoloLens 2'nin kuruluş içinde benimsenmesi sürecinde size yol yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="28abb-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![1. Adım](images/1green.png)| <br/> <span data-ttu-id="28abb-112">**[Yaygın Dağıtım Senaryoları:](hololens-requirements.md)** Dağıtım senaryolarını anlama ve HoloLens 2 cihazlarını dağıtmak için gereken temel bileşenleri keşfetme.</span><span class="sxs-lookup"><span data-stu-id="28abb-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![2. Adım](images/2green.png)| <br/> <span data-ttu-id="28abb-114">**[Hazırlama:](#prepare)** HoloLens 2 için gereken altyapı temelleri hakkında bilgi sahibi olma.</span><span class="sxs-lookup"><span data-stu-id="28abb-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![3. Adım](images/3green.png) | <br/> <span data-ttu-id="28abb-116">**[Yapılandırma:](#configure)** Bulut tabanlı dağıtım için temel bileşenlerinizi yapılandırmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="28abb-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![4. Adım](images/4green.png) | <br/> <span data-ttu-id="28abb-118">**[Dağıtma:](#deploy)** Cihazlarınızı dağıtmayı ve uygulamalarınızı güvenli ve verimli bir şekilde dağıtmayı keşfedin.</span><span class="sxs-lookup"><span data-stu-id="28abb-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![5. Adım](images/5green.png) | <br/> <span data-ttu-id="28abb-120">**[Bakım:](#maintain)** HoloLens 2 cihazlarınızı düzgün bir şekilde korumak ve şirket ilkesiyle uyumluluğu sağlamak için gerekenleri bulun.</span><span class="sxs-lookup"><span data-stu-id="28abb-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="28abb-121">Hazırlama</span><span class="sxs-lookup"><span data-stu-id="28abb-121">Prepare</span></span>

<span data-ttu-id="28abb-122">Tüm HoloLens 2 özelliklerini desteklemek için gereken temel altyapı hizmetleri hakkında bilgi edinmek.</span><span class="sxs-lookup"><span data-stu-id="28abb-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="28abb-123">Bileşen</span><span class="sxs-lookup"><span data-stu-id="28abb-123">Component</span></span> | <span data-ttu-id="28abb-124">Açıklama</span><span class="sxs-lookup"><span data-stu-id="28abb-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="28abb-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="28abb-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="28abb-126">HoloLens 2 için kimlik ve erişim yönetimi sağlar</span><span class="sxs-lookup"><span data-stu-id="28abb-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="28abb-127">Mobil Cihaz Yönetimi</span><span class="sxs-lookup"><span data-stu-id="28abb-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="28abb-128">Kiracınıza bağlı HoloLens 2 cihazlarını yönetir</span><span class="sxs-lookup"><span data-stu-id="28abb-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="28abb-129">Wi-Fi Ağı</span><span class="sxs-lookup"><span data-stu-id="28abb-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="28abb-130">Wi-Fi kullanılabilir ve cihazlar İnternet'e bağlanabilir</span><span class="sxs-lookup"><span data-stu-id="28abb-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="28abb-131">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="28abb-131">Configure</span></span>

<span data-ttu-id="28abb-132">HoloLens 2'nin kuruluşun Azure AD kiracısına ve MDM'sine kaydolması ve yapılandırılması için intune ve Autopilot'u düşük temaslı çözümler olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="28abb-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="28abb-133">Bileşen</span><span class="sxs-lookup"><span data-stu-id="28abb-133">Component</span></span> | <span data-ttu-id="28abb-134">Açıklama</span><span class="sxs-lookup"><span data-stu-id="28abb-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="28abb-135">Otomatik Kayıt</span><span class="sxs-lookup"><span data-stu-id="28abb-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="28abb-136">İlk oturum açma sonrasında cihazlar otomatik olarak Azure AD'ye kaydedilir ve MDM'ye kaydedilir</span><span class="sxs-lookup"><span data-stu-id="28abb-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="28abb-137">Uygulama Lisansları</span><span class="sxs-lookup"><span data-stu-id="28abb-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="28abb-138">Kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir</span><span class="sxs-lookup"><span data-stu-id="28abb-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="28abb-139">Azure Kullanıcıları ve Grupları</span><span class="sxs-lookup"><span data-stu-id="28abb-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="28abb-140">HoloLens 2 için yapılandırma ve lisans atamaya yardımcı olur</span><span class="sxs-lookup"><span data-stu-id="28abb-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="28abb-141">Dağıtma</span><span class="sxs-lookup"><span data-stu-id="28abb-141">Deploy</span></span>

<span data-ttu-id="28abb-142">HoloLens 2 cihazlarınızı dağıtarak yapılandırmalarını doğrular.</span><span class="sxs-lookup"><span data-stu-id="28abb-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="28abb-143">Bileşen</span><span class="sxs-lookup"><span data-stu-id="28abb-143">Component</span></span> | <span data-ttu-id="28abb-144">Açıklama</span><span class="sxs-lookup"><span data-stu-id="28abb-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="28abb-145">Kayıt Doğrulama</span><span class="sxs-lookup"><span data-stu-id="28abb-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="28abb-146">Cihazda Ayarlar'dan veya Azure Portal'dan Azure AD'ye Katılmış olduğunu doğrulama</span><span class="sxs-lookup"><span data-stu-id="28abb-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="28abb-147">Sertifika Doğrulama</span><span class="sxs-lookup"><span data-stu-id="28abb-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="28abb-148">Ayarları denetleyin ve doğru dağıtıldıklarını doğrulayın</span><span class="sxs-lookup"><span data-stu-id="28abb-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="28abb-149">Uygulama yüklemelerini doğrulama</span><span class="sxs-lookup"><span data-stu-id="28abb-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="28abb-150">Uygulamanın mevcut olduğunu ve HoloLens 2'niz üzerinde çalıştığını onaylayın</span><span class="sxs-lookup"><span data-stu-id="28abb-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="28abb-151">Bakım</span><span class="sxs-lookup"><span data-stu-id="28abb-151">Maintain</span></span>

<span data-ttu-id="28abb-152">HoloLens 2 İş İçin Windows Update ve uygulamalarınızı güncel tutmak için MDM sisteminiz veya Microsoft Store ile birlikte MDM sisteminizi kullanın.</span><span class="sxs-lookup"><span data-stu-id="28abb-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="28abb-153">Bileşen</span><span class="sxs-lookup"><span data-stu-id="28abb-153">Component</span></span> | <span data-ttu-id="28abb-154">Açıklama</span><span class="sxs-lookup"><span data-stu-id="28abb-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="28abb-155">HoloLens 2'i güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="28abb-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="28abb-156">İş için Windows Güncelleştirmeleri aracılığıyla güncelleştirmeleri gereken şekilde yapılandırma</span><span class="sxs-lookup"><span data-stu-id="28abb-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="28abb-157">Uygulamaları güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="28abb-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="28abb-158">MDM sisteminiz veya Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="28abb-158">Configure through your MDM system or the Microsoft Store</span></span>
