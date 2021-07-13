---
title: uzaktan yardım ile buluta bağlı HoloLens 2 ' ye genel bakış
description: Dynamics 365 uzaktan yardım 'ı kullanarak bir buluta bağlı ağ üzerinden HoloLens 2 cihazı kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635135"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="15511-104">dağıtım kılavuzu – buluta bağlı HoloLens 2 uzaktan yardım ile genel bakış</span><span class="sxs-lookup"><span data-stu-id="15511-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="15511-105">bu kılavuz, bt uzmanlarının kuruluşa uzak yardım ile Microsoft HoloLens 2 cihaz planlaması ve dağıtmalarına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="15511-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="15511-106">bu, kuruluşunuz için çeşitli HoloLens 2 kullanım durumlarında kavram kanıtı olan dağıtımlar için bir model olarak görev yapar.</span><span class="sxs-lookup"><span data-stu-id="15511-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="15511-107">Kurulum, [senaryoya A 'ya benzer: bulut bağlantı cihazlarına dağıtın](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span><span class="sxs-lookup"><span data-stu-id="15511-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="15511-108">Kılavuz sırasında cihazlarınızı cihaz yönetimine kaydetme, gerektiğinde lisans uygulama ve son kullanıcılarınızın cihaz kurulumu üzerinde uzaktan yardım 'ı hemen kullanabildiğini doğrulama konusunda ele alınacaktır.</span><span class="sxs-lookup"><span data-stu-id="15511-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="15511-109">bunu yapmak için, kurulumu ve çalışmayı sağlamak için gereken önemli parçaların üzerine gidecektir. HoloLens 2 ile uygun ölçekte dağıtım elde edin.</span><span class="sxs-lookup"><span data-stu-id="15511-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="15511-110">Bu kılavuzda başka cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bu seçenekleri tamamladıktan sonra araştırmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="15511-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15511-111">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="15511-111">Prerequisites</span></span>

<span data-ttu-id="15511-112">HoloLens 2 ' i dağıtmak için aşağıdaki altyapının olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="15511-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="15511-113">Aksi takdirde, Azure ve Intune kurulumu bu kılavuza dahildir:</span><span class="sxs-lookup"><span data-stu-id="15511-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="15511-114">Bu, senaryo A 'ya benzer bir şekilde ayarlanmıştır [: bulut Connect cihazlarına dağıtma](/hololens/common-scenarios#scenario-a), bu, birçok kavram kanıtı sağlamak için iyi bir seçenektir. Bu, şunlar dahil olacaktır:</span><span class="sxs-lookup"><span data-stu-id="15511-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="15511-115">Wi-Fi ağlar genellikle Internet ve bulut hizmetlerine tamamen açıktır</span><span class="sxs-lookup"><span data-stu-id="15511-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="15511-116">MDM otomatik kayıt ile Azure AD katılımı--MDM (Intune) yönetilen</span><span class="sxs-lookup"><span data-stu-id="15511-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="15511-117">Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="15511-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="15511-118">Cihaz başına tek veya birden çok Kullanıcı desteklenir.</span><span class="sxs-lookup"><span data-stu-id="15511-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Buluta bağlı senaryo" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="15511-120">Uzaktan Yardım hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="15511-120">Learn about Remote Assist</span></span>

<span data-ttu-id="15511-121">Uzaktan Yardım, işbirliğine dayalı bakım ve onarım, uzaktan denetleme ve bilgi paylaşımı ve eğitim sağlar.</span><span class="sxs-lookup"><span data-stu-id="15511-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="15511-122">Kullanıcıları farklı rollerdeki ve konumlardaki uzak yardım 'ı kullanarak bir teknisyen, Microsoft Teams üzerinde uzak ortak çalışan ile bağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="15511-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="15511-123">Bu kişiler, aynı konumda&#39;de olsa da sorunları gerçek zamanlı olarak çözümlemek için video, ekran görüntüleri ve ek açıklamaları birleştirebilirler.</span><span class="sxs-lookup"><span data-stu-id="15511-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="15511-124">Uzak ortak çalışanlar başvuru görüntülerini, şemaları ve diğer faydalı bilgileri, HoloLens üzerinde çalışırken ve ücretsiz olarak çalışırken şemalara başvurabilmesi için&#39;fiziksel alanı ekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="15511-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="15511-125">Uzaktan Yardım lisanslama ve gereksinimler</span><span class="sxs-lookup"><span data-stu-id="15511-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="15511-126">Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)</span><span class="sxs-lookup"><span data-stu-id="15511-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="15511-127">[Uzaktan Yardım aboneliği](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="15511-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="15511-128">Dynamics 365 uzaktan yardım kullanıcısı</span><span class="sxs-lookup"><span data-stu-id="15511-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="15511-129">Uzaktan Yardım lisansı</span><span class="sxs-lookup"><span data-stu-id="15511-129">Remote Assist license</span></span>
- <span data-ttu-id="15511-130">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="15511-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="15511-131">Microsoft Teams kullanıcı</span><span class="sxs-lookup"><span data-stu-id="15511-131">Microsoft Teams user</span></span>

- <span data-ttu-id="15511-132">Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="15511-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="15511-133">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="15511-133">Network connectivity</span></span>

<span data-ttu-id="15511-134">Bu [çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir.</span><span class="sxs-lookup"><span data-stu-id="15511-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="15511-135">Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.</span><span class="sxs-lookup"><span data-stu-id="15511-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="15511-136">Bu kılavuzda şunları yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="15511-136">In this guide you will:</span></span>

<span data-ttu-id="15511-137">Hazırlanır</span><span class="sxs-lookup"><span data-stu-id="15511-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15511-138">HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="15511-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="15511-139">Azure AD hakkında daha fazla bilgi edinin ve bunu&#39;ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="15511-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="15511-140">Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="15511-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="15511-141">MDM hakkında daha fazla bilgi edinin ve zaten bir tane&#39;yoksa Intune ile ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="15511-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="15511-142">Uzaktan Yardım ağ gereksinimleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="15511-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="15511-143">İsteğe bağlı: kurumsal kaynaklara bağlanmak için VPN</span><span class="sxs-lookup"><span data-stu-id="15511-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="15511-144">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="15511-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15511-145">Kullanıcı ve grup oluşturma.</span><span class="sxs-lookup"><span data-stu-id="15511-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="15511-146">Azure AD 'de otomatik kayıt ayarlama.</span><span class="sxs-lookup"><span data-stu-id="15511-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="15511-147">Uygulama lisanslarınızı atama.</span><span class="sxs-lookup"><span data-stu-id="15511-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="15511-148">Dağıt:</span><span class="sxs-lookup"><span data-stu-id="15511-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15511-149">HoloLens 2 ' 'nizi ayarlayın ve kaydı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="15511-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="15511-150">Uzaktan Yardım araması yapacağınızı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="15511-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="15511-151">Korumanız</span><span class="sxs-lookup"><span data-stu-id="15511-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="15511-152">Microsoft Store uygulamasını kullanarak uzaktan yardımı güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="15511-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="15511-153">Destek planı oluşturma.</span><span class="sxs-lookup"><span data-stu-id="15511-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="15511-154">Geliştirme planı.</span><span class="sxs-lookup"><span data-stu-id="15511-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="15511-155">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="15511-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="15511-156">Buluta bağlı dağıtım-hazırlama</span><span class="sxs-lookup"><span data-stu-id="15511-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

