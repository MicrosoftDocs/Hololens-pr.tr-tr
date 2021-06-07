---
title: Cloud connected HoloLens 2 with Remote Assist'e genel bakış
description: Dynamics 365 Remote Assist kullanarak Bir Bulut Bağlantılı ağ üzerinden HoloLens 2 cihazlarını kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378958"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="1ab55-104">Dağıtım Kılavuzu – Remote Assist ile buluta bağlı HoloLens 2 – Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="1ab55-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="1ab55-105">Bu kılavuz, BT uzmanlarının dynamics 365 Remote Assist ile buluta bağlı olan cihazları dynamics 365 remote Assist ile genel olarak kullanma amacını kullanarak Microsoft HoloLens 2 cihazları planlamalarına ve kuruluşlarına dağıtmalarına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="1ab55-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="1ab55-106">Bunun, çeşitli HoloLens 2 kullanım örnekleri genelinde kuruluşa yapılan kavram kanıtı dağıtımları için bir model olarak görev yapacaktır.</span><span class="sxs-lookup"><span data-stu-id="1ab55-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="1ab55-107">Kılavuz sırasında cihaz yönetiminize cihaz yönetimine cihaz kaydetmeyi, gerektiğinde lisansları uygulamayı ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulamayı da kapsıyoruz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="1ab55-108">Bunu yapmak için, HoloLens 2 ile büyük ölçekte dağıtıma ulaşmak için gerekli olan önemli altyapı parçalarının üzerinden geçeceğiz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="1ab55-109">[![Buluta bağlı senaryo ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1ab55-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="1ab55-110">Bu Kılavuzda</span><span class="sxs-lookup"><span data-stu-id="1ab55-110">In this Guide</span></span>

<span data-ttu-id="1ab55-111">Bu kılavuzda, HoloLens cihazlarınız üzerinde kuruluş içinde Remote Assist'i ayarlamaya yönelik belirli bir hedef vardır.</span><span class="sxs-lookup"><span data-stu-id="1ab55-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="1ab55-112">Bu hedefe ulaşmak için gerekli olan gerekliliklere yer veacağız.</span><span class="sxs-lookup"><span data-stu-id="1ab55-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="1ab55-113">Bu hedefe odaklanmak amacıyla, bu dağıtım için iyileştirme yapmak veya yapılandırmak için gereken öğeleri azaltmak amacıyla belirli hazırlıklar ve yapılandırmalar önceden seçilir.</span><span class="sxs-lookup"><span data-stu-id="1ab55-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="1ab55-114">Bu seçenekler size bildirecek ve dağıtımınızı iş gereksinimlerinize göre özelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="1ab55-115">Bu, senaryo [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Bulut bağlantısı cihazlarına dağıtmaya benzer bir kurulumdur. Bu, şunları içerecek birçok Kavram Kanıtı dağıtımı için iyi bir seçenektir:</span><span class="sxs-lookup"><span data-stu-id="1ab55-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="1ab55-116">Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır</span><span class="sxs-lookup"><span data-stu-id="1ab55-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="1ab55-117">MDM Otomatik Kaydı ile Azure AD'ye Katılma -- MDM (Intune) Yönetilen</span><span class="sxs-lookup"><span data-stu-id="1ab55-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="1ab55-118">Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma</span><span class="sxs-lookup"><span data-stu-id="1ab55-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="1ab55-119">Desteklenen cihaz başına tek veya birden çok kullanıcı</span><span class="sxs-lookup"><span data-stu-id="1ab55-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="1ab55-120">Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır</span><span class="sxs-lookup"><span data-stu-id="1ab55-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="1ab55-121">Bu kılavuzda başka hiçbir cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bitirdikten sonra bu seçenekleri keşfetmeniz teşvik edilecektir.</span><span class="sxs-lookup"><span data-stu-id="1ab55-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="1ab55-122">Remote Assist hakkında bilgi</span><span class="sxs-lookup"><span data-stu-id="1ab55-122">Learn about Remote Assist</span></span>

<span data-ttu-id="1ab55-123">Remote Assist işbirliğine dayalı bakım ve onarım, uzaktan incelemenin yanı sıra bilgi paylaşımı ve eğitim sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ab55-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="1ab55-124">Remote Assist kullanan bir teknisyen farklı rollerdeki ve konumlarda bulunan insanları bağlayarak Microsoft Teams'de bir uzak ortak çalışanla bağlantı kurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="1ab55-125">Aynı konumda olmayan sorunları gerçek zamanlı olarak çözmek için video, ekran&#39;ek açıklamaları bir araya ekleyebilirler.</span><span class="sxs-lookup"><span data-stu-id="1ab55-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="1ab55-126">Uzak ortak çalışanlar, HoloLens üzerinde çalışırken şemaya başvurmak için teknisyenin fiziksel&#39;referans görüntüleri, şemalar ve diğer yararlı bilgiler ekler.</span><span class="sxs-lookup"><span data-stu-id="1ab55-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="1ab55-127">Bu kılavuzda şunların için:</span><span class="sxs-lookup"><span data-stu-id="1ab55-127">In this guide you will:</span></span>

<span data-ttu-id="1ab55-128">Hazırlamak:</span><span class="sxs-lookup"><span data-stu-id="1ab55-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1ab55-129">HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="1ab55-130">Azure AD hakkında daha fazla bilgi edinin ve yoksa&#39;ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1ab55-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="1ab55-131">Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="1ab55-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="1ab55-132">MDM hakkında daha fazla bilgi edinmek ve henüz hazır&#39;Intune ile ayarlama.</span><span class="sxs-lookup"><span data-stu-id="1ab55-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="1ab55-133">Remote Assist'in ağ gereksinimleri hakkında bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ab55-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="1ab55-134">İsteğe bağlı: Kuruluş kaynaklarına bağlanmak için VPN</span><span class="sxs-lookup"><span data-stu-id="1ab55-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="1ab55-135">Yapılandırmak:</span><span class="sxs-lookup"><span data-stu-id="1ab55-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1ab55-136">Kullanıcılar ve Gruplar oluşturma.</span><span class="sxs-lookup"><span data-stu-id="1ab55-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="1ab55-137">Azure AD'de Otomatik kayıt ayarlama.</span><span class="sxs-lookup"><span data-stu-id="1ab55-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="1ab55-138">Uygulama lisanslarınızı atama.</span><span class="sxs-lookup"><span data-stu-id="1ab55-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="1ab55-139">Dağıt:</span><span class="sxs-lookup"><span data-stu-id="1ab55-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1ab55-140">HoloLens 2'nizi ayarlayın ve kaydı doğrular.</span><span class="sxs-lookup"><span data-stu-id="1ab55-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="1ab55-141">Remote Assist çağrısı yapmak için bir doğrulama.</span><span class="sxs-lookup"><span data-stu-id="1ab55-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="1ab55-142">Korumak:</span><span class="sxs-lookup"><span data-stu-id="1ab55-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1ab55-143">Microsoft Store uygulamasını kullanarak Remote Assist'i güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="1ab55-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="1ab55-144">Destek planı yapma.</span><span class="sxs-lookup"><span data-stu-id="1ab55-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="1ab55-145">Geliştirme planı.</span><span class="sxs-lookup"><span data-stu-id="1ab55-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="1ab55-146">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="1ab55-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1ab55-147">Buluta bağlı dağıtım - Hazırlama</span><span class="sxs-lookup"><span data-stu-id="1ab55-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

