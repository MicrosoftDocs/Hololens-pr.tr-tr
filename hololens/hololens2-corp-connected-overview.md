---
title: dağıtım kılavuzu – Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-genel bakış
description: kurumsal bağlantılı bir ağ üzerinden Dynamics 365 kılavuzlarıyla HoloLens 2 cihazı kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637022"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="d2434-104">dağıtım kılavuzu-Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-genel bakış</span><span class="sxs-lookup"><span data-stu-id="d2434-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="d2434-105">bu kılavuz, bt uzmanlarının Dynamics 365 kılavuzlarıyla (kılavuzlar) Microsoft HoloLens 2 cihaz planlaması ve dağıtmalarına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="d2434-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="d2434-106">Bu kılavuz, pilot ve üretim dağıtımları için harika ve [B: kuruluşunuzun ağ Kılavuzu Içinde dağıtma senaryosuna](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) benzer.</span><span class="sxs-lookup"><span data-stu-id="d2434-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="d2434-107">kavram kanıtlarınızı test ettikten sonra, HoloLens kuruluşunuza tümleştirmeyle ileri doğru gitmek için bu kılavuzu kullanın.</span><span class="sxs-lookup"><span data-stu-id="d2434-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="d2434-108">Bu kılavuzda, cihazlarınızın mevcut cihaz yönetimine nasıl kaydedileceğini, gereken lisansları nasıl uygulayacağını ve son kullanıcılarınızın bir Dynamics 365 Kılavuzu çalıştıracağını ve cihaz kurulduktan sonra özel iş kolu uygulamaları kullanmasını nasıl doğrulayacağız.</span><span class="sxs-lookup"><span data-stu-id="d2434-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d2434-109">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="d2434-109">Prerequisites</span></span>

<span data-ttu-id="d2434-110">Aşağıdaki altyapı zaten yerinde olmalıdır:</span><span class="sxs-lookup"><span data-stu-id="d2434-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="d2434-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d2434-111">Wi-Fi</span></span>
    - <span data-ttu-id="d2434-112">İç kaynaklara erişimi olan dahili kurumsal ağ ve internet veya bulut hizmetlerine sınırlı erişim</span><span class="sxs-lookup"><span data-stu-id="d2434-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="d2434-113">Cihaz tabanlı sertifika kimlik doğrulaması.</span><span class="sxs-lookup"><span data-stu-id="d2434-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="d2434-114">Azure Active Directory (azure ad) MDM otomatik kaydıyla birleştir ([azure ad P1 aboneliği](/azure/active-directory/fundamentals/active-directory-whatis) gerekir)</span><span class="sxs-lookup"><span data-stu-id="d2434-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="d2434-115">MDM (Intune) yönetiliyor</span><span class="sxs-lookup"><span data-stu-id="d2434-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="d2434-116">Bir veya daha fazla uygulama MDM aracılığıyla dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="d2434-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="d2434-117">Ağ</span><span class="sxs-lookup"><span data-stu-id="d2434-117">Network</span></span> 
    - <span data-ttu-id="d2434-118">Sertifikalar (SCEP veya PKCS)</span><span class="sxs-lookup"><span data-stu-id="d2434-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="d2434-119">Ara sunucu yapılandırması</span><span class="sxs-lookup"><span data-stu-id="d2434-119">Proxy configuration</span></span>
- <span data-ttu-id="d2434-120">Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d2434-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="d2434-121">Cihaz başına tek veya birden çok Kullanıcı desteklenir.</span><span class="sxs-lookup"><span data-stu-id="d2434-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="d2434-122">Belirli kullanım örneklerine göre uygulanan cihaz kilitleme yapılandırmalarının farklı düzeyleri, tam açık tek uygulama bilgi noktası ile uygulanır.</span><span class="sxs-lookup"><span data-stu-id="d2434-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="d2434-123">Kılavuzlar lisanslama ve gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d2434-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="d2434-124">Azure AD hesabı</span><span class="sxs-lookup"><span data-stu-id="d2434-124">Azure AD account</span></span>
- <span data-ttu-id="d2434-125">Dynamics 365 kılavuzlar uygulamalar PC ve HoloLens</span><span class="sxs-lookup"><span data-stu-id="d2434-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="d2434-126">Dynamics 365 kılavuzlar aboneliği</span><span class="sxs-lookup"><span data-stu-id="d2434-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="d2434-127">Microsoft Dataverse (dahil)</span><span class="sxs-lookup"><span data-stu-id="d2434-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="d2434-128">Power Apps (dahil)</span><span class="sxs-lookup"><span data-stu-id="d2434-128">Power Apps (included)</span></span>
- <span data-ttu-id="d2434-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="d2434-129">Power BI Desktop</span></span>
- <span data-ttu-id="d2434-130">Ağ bağlantısı</span><span class="sxs-lookup"><span data-stu-id="d2434-130">Network Connectivity</span></span>

<span data-ttu-id="d2434-131">[![Corp bağlı ağ diyagramı, 1 ](./images/deployment-guides-revised-scenario-b-01-1.png) . aşama](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2434-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="d2434-132">[![Corp bağlı ağ diyagramı, Aşama 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d2434-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="d2434-133">Bu kılavuzda şunları yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="d2434-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="d2434-134">Hazırlama</span><span class="sxs-lookup"><span data-stu-id="d2434-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="d2434-135">HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="d2434-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="d2434-136">Azure AD hakkında daha fazla bilgi edinin ve yoksa bir tane ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="d2434-137">Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="d2434-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="d2434-138">MDM hakkında daha fazla bilgi edinin ve henüz bir hazırlayın yoksa Intune ile ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="d2434-139">Sertifika tabanlı Wi-Fi hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="d2434-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="d2434-140">Proxy hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="d2434-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="d2434-141">Iş kolu uygulamalarını nasıl kullanabileceğinizi anlayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="d2434-142">Kuruluşunuzun kılavuzlarını nasıl kullanabileceğiniz hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="d2434-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="d2434-143">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="d2434-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="d2434-144">Kullanıcı ve grup oluşturma.</span><span class="sxs-lookup"><span data-stu-id="d2434-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="d2434-145">Otomatik kayıt ayarlama.</span><span class="sxs-lookup"><span data-stu-id="d2434-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="d2434-146">Wi-Fi sertifikaları ve profilleri kurumsal Wi-Fi bağlantı için ayarlama.</span><span class="sxs-lookup"><span data-stu-id="d2434-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="d2434-147">Upload ve iş kolu (LOB) uygulama paketleri atayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="d2434-148">Dynamics 365 kılavuzlarını ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="d2434-149">Bilgi noktası modunu yapılandırma (isteğe bağlı).</span><span class="sxs-lookup"><span data-stu-id="d2434-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="d2434-150">WDAC yapılandırma (isteğe bağlı).</span><span class="sxs-lookup"><span data-stu-id="d2434-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="d2434-151">Dağıtma</span><span class="sxs-lookup"><span data-stu-id="d2434-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="d2434-152">Kaydı cihaz ve MDM aracılığıyla doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="d2434-153">Wi-Fi sertifikalarını doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="d2434-154">LOB uygulaması yüklemesini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="d2434-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="d2434-155">Yazma ve çalıştırma aracılığıyla kılavuzların doğrulanması.</span><span class="sxs-lookup"><span data-stu-id="d2434-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="d2434-156">Bakım</span><span class="sxs-lookup"><span data-stu-id="d2434-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="d2434-157">güncelleştirme HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="d2434-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="d2434-158">Kılavuzlarını güncelleştirme (Mağaza uygulamaları).</span><span class="sxs-lookup"><span data-stu-id="d2434-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="d2434-159">LOB uygulamalarını güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="d2434-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="d2434-160">Geliştirme planı.</span><span class="sxs-lookup"><span data-stu-id="d2434-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="d2434-161">Destek planı oluşturma.</span><span class="sxs-lookup"><span data-stu-id="d2434-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="d2434-162">Cihaz yönetimi seçenekleri.</span><span class="sxs-lookup"><span data-stu-id="d2434-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="d2434-163">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="d2434-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="d2434-164">Kurumsal bağlı dağıtım-hazırlama</span><span class="sxs-lookup"><span data-stu-id="d2434-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
