---
title: Uzaktan Yardım ile buluta bağlı HoloLens 2 ' ye genel bakış
description: Dynamics 365 uzaktan yardım 'ı kullanarak, HoloLens 2 cihazlarını buluta bağlı bir ağ üzerinden kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, bulut bağlantılı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923542"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="1f421-104">Dağıtım Kılavuzu – uzaktan yardım ile buluta bağlı HoloLens 2 – genel bakış</span><span class="sxs-lookup"><span data-stu-id="1f421-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="1f421-105">Bu kılavuz, BT uzmanlarının Microsoft HoloLens 2 cihazlarını kendi kuruluşlarına uzaktan yardım ile planlayıp dağıtmalarına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="1f421-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="1f421-106">Bu, çeşitli HoloLens 2 kullanım örnekleri genelinde kuruluşunuza yönelik kavram kanıtı dağıtımları için bir model olarak görev yapar.</span><span class="sxs-lookup"><span data-stu-id="1f421-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="1f421-107">Kurulum, [senaryoya A 'ya benzer: bulut bağlantı cihazlarına dağıtın](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span><span class="sxs-lookup"><span data-stu-id="1f421-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="1f421-108">Kılavuz sırasında cihazlarınızı cihaz yönetimine kaydetme, gerektiğinde lisans uygulama ve son kullanıcılarınızın cihaz kurulumu üzerinde uzaktan yardım 'ı hemen kullanabildiğini doğrulama konusunda ele alınacaktır.</span><span class="sxs-lookup"><span data-stu-id="1f421-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="1f421-109">Bunu yapmak için, ayarlama ve çalıştırma için gereken önemli parçaların üzerine giderek, HoloLens 2 ile ölçeklendirerek dağıtım elde edilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="1f421-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="1f421-110">Bu kılavuzda başka cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bu seçenekleri tamamladıktan sonra araştırmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="1f421-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f421-111">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="1f421-111">Prerequisites</span></span>

<span data-ttu-id="1f421-112">HoloLens 2 ' nin dağıtılması için aşağıdaki altyapının olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1f421-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="1f421-113">Aksi takdirde, Azure ve Intune kurulumu bu kılavuza dahildir:</span><span class="sxs-lookup"><span data-stu-id="1f421-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="1f421-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1f421-114">Wi-Fi</span></span>
    - <span data-ttu-id="1f421-115">Ağlar genellikle Internet ve bulut hizmetlerine açıktır</span><span class="sxs-lookup"><span data-stu-id="1f421-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="1f421-116">Azure Active Directory (Azure AD) MDM otomatik kaydıyla birleştir ([Azure AD P1 aboneliği](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) gerekir)</span><span class="sxs-lookup"><span data-stu-id="1f421-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="1f421-117">MDM (Intune) yönetiliyor</span><span class="sxs-lookup"><span data-stu-id="1f421-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="1f421-118">Bir veya daha fazla uygulama MDM aracılığıyla dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="1f421-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="1f421-119">Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="1f421-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="1f421-120">Cihaz başına tek veya birden çok Kullanıcı desteklenir.</span><span class="sxs-lookup"><span data-stu-id="1f421-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Buluta bağlı senaryo" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="1f421-122">Uzaktan Yardım hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="1f421-122">Learn about Remote Assist</span></span>

<span data-ttu-id="1f421-123">Uzaktan Yardım, işbirliğine dayalı bakım ve onarım, uzaktan denetleme ve bilgi paylaşımı ve eğitim sağlar.</span><span class="sxs-lookup"><span data-stu-id="1f421-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="1f421-124">Kullanıcıları farklı rollerdeki ve konumlardaki uzak yardım 'ı kullanarak bir teknisyen, Microsoft ekiplerinde bulunan uzak ortak çalışan ile bağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="1f421-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="1f421-125">Bu kişiler, aynı konumda&#39;de olsa da sorunları gerçek zamanlı olarak çözümlemek için video, ekran görüntüleri ve ek açıklamaları birleştirebilirler.</span><span class="sxs-lookup"><span data-stu-id="1f421-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="1f421-126">Uzak ortak çalışanlar, referans görüntülerini, şemaları ve diğer faydalı bilgileri, teknisyen üzerinde çalışırken kaya ve sorunsuz çalışma sırasında Şemasız bir şekilde bir araya girmek için bu kişilerin fiziksel alanı&#39;ekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="1f421-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="1f421-127">Uzaktan Yardım lisanslama ve gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1f421-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="1f421-128">Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)</span><span class="sxs-lookup"><span data-stu-id="1f421-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="1f421-129">[Uzaktan Yardım aboneliği](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span><span class="sxs-lookup"><span data-stu-id="1f421-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="1f421-130">Dynamics 365 uzaktan yardım kullanıcısı</span><span class="sxs-lookup"><span data-stu-id="1f421-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="1f421-131">Uzaktan Yardım lisansı</span><span class="sxs-lookup"><span data-stu-id="1f421-131">Remote Assist license</span></span>
- <span data-ttu-id="1f421-132">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="1f421-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="1f421-133">Microsoft ekipleri kullanıcısı</span><span class="sxs-lookup"><span data-stu-id="1f421-133">Microsoft Teams user</span></span>

- <span data-ttu-id="1f421-134">Microsoft ekipleri veya [takımlar Freemıum](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="1f421-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="1f421-135">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="1f421-135">Network connectivity</span></span>

<span data-ttu-id="1f421-136">Bu [çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir.</span><span class="sxs-lookup"><span data-stu-id="1f421-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="1f421-137">Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.</span><span class="sxs-lookup"><span data-stu-id="1f421-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="1f421-138">Bu kılavuzda şunları yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="1f421-138">In this guide you will:</span></span>

<span data-ttu-id="1f421-139">Hazırlanır</span><span class="sxs-lookup"><span data-stu-id="1f421-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1f421-140">HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="1f421-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="1f421-141">Azure AD hakkında daha fazla bilgi edinin ve bunu&#39;ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1f421-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="1f421-142">Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="1f421-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="1f421-143">MDM hakkında daha fazla bilgi edinin ve zaten bir tane&#39;yoksa Intune ile ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1f421-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="1f421-144">Uzaktan Yardım ağ gereksinimleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="1f421-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="1f421-145">İsteğe bağlı: kurumsal kaynaklara bağlanmak için VPN</span><span class="sxs-lookup"><span data-stu-id="1f421-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="1f421-146">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="1f421-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1f421-147">Kullanıcı ve grup oluşturma.</span><span class="sxs-lookup"><span data-stu-id="1f421-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="1f421-148">Azure AD 'de otomatik kayıt ayarlama.</span><span class="sxs-lookup"><span data-stu-id="1f421-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="1f421-149">Uygulama lisanslarınızı atama.</span><span class="sxs-lookup"><span data-stu-id="1f421-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="1f421-150">Dağıt:</span><span class="sxs-lookup"><span data-stu-id="1f421-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1f421-151">HoloLens 2 ' 'nizi ayarlayın ve kaydı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="1f421-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="1f421-152">Uzaktan Yardım araması yapacağınızı doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="1f421-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="1f421-153">Korumanız</span><span class="sxs-lookup"><span data-stu-id="1f421-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1f421-154">Microsoft Store uygulamasını kullanarak uzaktan yardımı güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="1f421-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="1f421-155">Destek planı oluşturma.</span><span class="sxs-lookup"><span data-stu-id="1f421-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="1f421-156">Geliştirme planı.</span><span class="sxs-lookup"><span data-stu-id="1f421-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="1f421-157">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="1f421-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1f421-158">Buluta bağlı dağıtım-hazırlama</span><span class="sxs-lookup"><span data-stu-id="1f421-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

