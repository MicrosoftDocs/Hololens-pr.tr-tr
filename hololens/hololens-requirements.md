---
title: Ticari bir ortamda HoloLens 2 dağıtımını planlama
description: Altyapı, sanal ağ ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtma ve yönetme hakkında daha fazla bilgi Azure Active Directory bilgi edinebilirsiniz.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924613"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="9714d-103">Yaygın Dağıtım Senaryoları</span><span class="sxs-lookup"><span data-stu-id="9714d-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="9714d-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="9714d-104">Overview</span></span>

<span data-ttu-id="9714d-105">Bu sayfa, kuruluş içinde 2 cihaz dağıtma ve yönetmeye ilişkin üç yaygın senaryo için Microsoft HoloLens üst düzey mimariye genel bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="9714d-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="9714d-106">Genellikle, cihazlarınızı yönetme ve kuruluş kaynaklarına erişme, büyük ölçüde zaten var olan faktörler tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="9714d-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="9714d-107">Mevcut altyapınıza bağlı olarak, aşağıdaki senaryolarda ortak cihaz yönetimi stilini (MDM) gözden geçirmenizi ve ardından hangi senaryonun ihtiyaçlarınıza uygun olduğunu belirlemek için ticari bir ortamda [HoloLens 2](hololens-core-components.md) dağıtımlarını planlama makalesini okumaya davet ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="9714d-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="9714d-108">Dağıtımınız sırasında kullanabileceğiniz üç ilgili kılavuz da vardır.</span><span class="sxs-lookup"><span data-stu-id="9714d-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="9714d-109">Buluta bağlı ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="9714d-110">Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="9714d-111">Kurumsal ağ dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="9714d-112">Çevrimdışı güvenli ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="9714d-113">Senaryo A: Buluta bağlı cihazlara dağıtma</span><span class="sxs-lookup"><span data-stu-id="9714d-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="9714d-114">Bu senaryo, yönetilen mobil cihazları bir şirket içinde dağıtmakla karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="9714d-115">HoloLens 2, öncelikli olarak şirket ağının dışında olan ortamlarda kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="9714d-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="9714d-116">Şirket kaynaklarına erişilemiyor veya VPN üzerinden sınırlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="9714d-117">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="9714d-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="9714d-118">Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır.</span><span class="sxs-lookup"><span data-stu-id="9714d-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="9714d-119">Azure AD'ye Mobil Cihaz Yönetimi (MDM) Otomatik Kaydı--MDM (Intune) Tarafından Yönetilen</span><span class="sxs-lookup"><span data-stu-id="9714d-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9714d-120">Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma</span><span class="sxs-lookup"><span data-stu-id="9714d-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="9714d-121">Desteklenen cihaz başına tek veya birden çok kullanıcı</span><span class="sxs-lookup"><span data-stu-id="9714d-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9714d-122">Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9714d-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9714d-123">MDM aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="9714d-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="9714d-124">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="9714d-124">Common Challenges</span></span>
   * <span data-ttu-id="9714d-125">Senaryo gereksinimlerine göre HoloLens 2'ye uygulanacak MDM yapılandırmalarını belirleme.</span><span class="sxs-lookup"><span data-stu-id="9714d-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="9714d-126">[![Senaryo A diyagramı ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9714d-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="9714d-127">İlgili Buluta bağlı kılavuzda HoloLens 2'nin cihaz yönetiminize nasıl kaydedeceği, gerektiğinde lisansları nasıl uygulayacakları ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulama adımları yer almaktadır.</span><span class="sxs-lookup"><span data-stu-id="9714d-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="9714d-128">Kısa vadeli veya uzun vadeli dış kullanım için uzak bir siteye cihaz dağıtmak için Dış İstemciler kılavuzunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="9714d-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9714d-129">Buluta bağlı ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="9714d-130">Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="9714d-131">Senaryo B: Kuruluş ağının içine dağıtma</span><span class="sxs-lookup"><span data-stu-id="9714d-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="9714d-132">Bu senaryo, çoğu bilgisayar için klasik dağıtımla Windows 10 aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9714d-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="9714d-133">HoloLens 2, şirket içi kaynaklara erişimi olan birincil olarak şirket ağına kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="9714d-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="9714d-134">İnternet ve bulut hizmetleri sınırlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="9714d-135">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="9714d-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="9714d-136">Wi-Fi, iç kaynaklara erişimi olan ve İnternet'e veya Bulut hizmetlerine sınırlı erişimi olan bir iç kurumsal ağdır.</span><span class="sxs-lookup"><span data-stu-id="9714d-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="9714d-137">MDM Otomatik Kaydı ile Azure AD'ye Katılma</span><span class="sxs-lookup"><span data-stu-id="9714d-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="9714d-138">MDM (Intune) Yönetilen</span><span class="sxs-lookup"><span data-stu-id="9714d-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="9714d-139">Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma</span><span class="sxs-lookup"><span data-stu-id="9714d-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="9714d-140">Desteklenen cihaz başına tek veya birden çok kullanıcı</span><span class="sxs-lookup"><span data-stu-id="9714d-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="9714d-141">Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9714d-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="9714d-142">MDM aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="9714d-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="9714d-143">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="9714d-143">Common Challenges</span></span>
   * <span data-ttu-id="9714d-144">HoloLens 2, şirket içi AD'ye katılmayı veya SCCM'i desteklemez.</span><span class="sxs-lookup"><span data-stu-id="9714d-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="9714d-145">MDM ile yalnızca Azure AD'ye katılma.</span><span class="sxs-lookup"><span data-stu-id="9714d-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="9714d-146">Günümüzde birçok şirket, System Center Yapılandırma Yöneticisi (SCCM) tarafından yönetilen şirket içi AD'ye katılmış cihazlar olarak bu senaryoda Windows 10 bilgisayarlarını dağıtmaya devam ediyor ve bulut tabanlı MDM çözümleri aracılığıyla iç Windows 10 cihazlarını yönetmek için dağıtılmış/yapılandırılmış altyapıya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="9714d-147">HoloLens 2 buluta özel bir cihaz olduğundan, Kullanıcı kimlik doğrulaması, işletim sistemi güncelleştirmeleri, MDM yönetimi ve diğer hizmetler için yoğun olarak İnternet'e ve buluta bağlı hizmetlere bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="9714d-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="9714d-148">Şirket ağına bağlanırken Büyük olasılıkla HoloLens 2'ye ve üzerinde çalıştıran uygulamalara erişimi etkinleştirmek için Ara Sunucu/Güvenlik Duvarı kurallarının ayarlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9714d-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="9714d-149">Kurumsal Wi-Fi bağlantısı genellikle cihazın veya kullanıcının ağ kimlik doğrulaması için sertifikalar gerektirir.</span><span class="sxs-lookup"><span data-stu-id="9714d-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="9714d-150">MDM aracılığıyla cihazlarına sertifika dağıtmak Windows 10 gerekli altyapının veya ayarların yapılandırılması zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="9714d-151">[![Senaryo B1 diyagramı ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9714d-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="9714d-152">[![Senaryo B2 diyagramı ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9714d-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="9714d-153">İlgili Kurumsal ağ kılavuzu, HoloLens 2'nin mevcut cihaz yönetiminize nasıl kaydedilir, gerektiğinde lisanslar nasıl uygulanacak ve son kullanıcılarının bir Dynamics 365 Kılavuzu çalıştırabileceklerini ve cihaz ayarlandıktan sonra özel iş hattı uygulamalarını kullanabileceğini nasıl doğrulayabilecekleri hakkında bilgi verir.</span><span class="sxs-lookup"><span data-stu-id="9714d-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9714d-154">Kurumsal ağ dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="9714d-155">Senaryo C: Güvenli çevrimdışı ortamda dağıtma</span><span class="sxs-lookup"><span data-stu-id="9714d-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="9714d-156">Bu, yüksek oranda güvenli veya gizli konumlar için tipik bir dağıtımdır.</span><span class="sxs-lookup"><span data-stu-id="9714d-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="9714d-157">HoloLens 2, ağ veya internet erişimine sahip değilken öncelikli olarak çevrimdışı kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="9714d-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="9714d-158">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="9714d-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="9714d-159">Wi-Fi devre dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="9714d-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="9714d-160">Gerekirse, LAN bağlantısı için USB üzerinden Ethernet etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="9714d-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="9714d-161">Yönetilmiyor.</span><span class="sxs-lookup"><span data-stu-id="9714d-161">Not Managed.</span></span>
   * <span data-ttu-id="9714d-162">Cihaz oturum açma için yerel kullanıcı hesabı.</span><span class="sxs-lookup"><span data-stu-id="9714d-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="9714d-163">HoloLens 2 yalnızca bir yerel hesabı destekler.</span><span class="sxs-lookup"><span data-stu-id="9714d-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="9714d-164">Cihaz kilitleme yapılandırmalarının farklı düzeyleri, belirli kullanım örneklerine göre Sağlama Paketleri aracılığıyla uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9714d-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="9714d-165">Bu yapılandırmalar genellikle güvenli ortam gereksinimleri nedeniyle kısıtlanır.</span><span class="sxs-lookup"><span data-stu-id="9714d-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="9714d-166">Sağlama Paketi aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="9714d-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="9714d-167">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="9714d-167">Common Challenges</span></span>
   * <span data-ttu-id="9714d-168">Sağlama Paketleri aracılığıyla kullanılabilen sınırlı bir yapılandırma kümesi vardır</span><span class="sxs-lookup"><span data-stu-id="9714d-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="9714d-169">Bulut hizmetleri kullanılamaz, bu nedenle HoloLens 2 özelliklerini sınırlandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="9714d-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="9714d-170">Bu cihazların el ile yapılandırılması, yapılandırılması ve güncelleştirilmiş olması nedeniyle daha yüksek yönetim yükü.</span><span class="sxs-lookup"><span data-stu-id="9714d-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="9714d-171">[![Çevrimdışı Güvenli diyagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9714d-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="9714d-172">İlgili Çevrimdışı güvenli kılavuz, güvenli ortamlarda kullanmak üzere Bir HoloLens 2'nin kilitlenmesini sağlayan örnek sağlama paketini uygulamaya dair yönerge sağlar.</span><span class="sxs-lookup"><span data-stu-id="9714d-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9714d-173">Çevrimdışı güvenli ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="9714d-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


