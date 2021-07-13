---
title: Yaygın Dağıtım Senaryoları
description: Altyapı, Azure Active Directory ve HoloLens mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda Azure Active Directory yönetme hakkında daha fazla bilgi edinebilirsiniz.
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
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635475"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="88ef4-103">Yaygın Dağıtım Senaryoları</span><span class="sxs-lookup"><span data-stu-id="88ef4-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="88ef4-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="88ef4-104">Overview</span></span>

<span data-ttu-id="88ef4-105">Bu sayfa, kuruluş içindeki 2 cihazı dağıtma ve yönetmeye ilişkin üç yaygın senaryo için Microsoft HoloLens bir mimariye genel bakış sağlar.</span><span class="sxs-lookup"><span data-stu-id="88ef4-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="88ef4-106">Genellikle, cihazlarınızı yönetme ve kuruluş kaynaklarına erişme, büyük ölçüde zaten var olan faktörler tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="88ef4-107">Mevcut altyapınıza bağlı olarak, aşağıdaki senaryolarda ortak cihaz yönetimi stilini (MDM) gözden geçirmenizi ve ardından, hangi senaryonun ihtiyaçlarınıza uygun olduğunu belirlemek için ticari bir ortamda Planning [HoloLens 2 deployments](hololens-core-components.md) (Planlama HoloLens 2 dağıtımları) makalesini okumanızı davet ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="88ef4-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="88ef4-108">Dağıtımınız sırasında kullanabileceğiniz üç ilgili kılavuz da vardır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="88ef4-109">Buluta bağlı ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="88ef4-110">Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="88ef4-111">Kurumsal ağ dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="88ef4-112">Çevrimdışı güvenli ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="88ef4-113">Senaryo A: Buluta bağlı cihazlara dağıtma</span><span class="sxs-lookup"><span data-stu-id="88ef4-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="88ef4-114">Bu senaryo, yönetilen mobil cihazları bir şirket içinde dağıtmakla karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="88ef4-115">HoloLens 2, birincil olarak şirket ağının dışında olan ortamlarda kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="88ef4-116">Şirket kaynaklarına erişilemiyor veya VPN üzerinden sınırlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="88ef4-117">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="88ef4-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="88ef4-118">Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="88ef4-119">Azure AD'ye Mobil Cihaz Yönetimi (MDM) Otomatik Kaydı--MDM (Intune) Tarafından Yönetilen</span><span class="sxs-lookup"><span data-stu-id="88ef4-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="88ef4-120">Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma</span><span class="sxs-lookup"><span data-stu-id="88ef4-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="88ef4-121">Desteklenen cihaz başına tek veya birden çok kullanıcı</span><span class="sxs-lookup"><span data-stu-id="88ef4-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="88ef4-122">Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="88ef4-123">MDM aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="88ef4-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="88ef4-124">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="88ef4-124">Common Challenges</span></span>
   * <span data-ttu-id="88ef4-125">Senaryo gereksinimlerine göre HoloLens 2'ye uygulanacak MDM yapılandırmalarını belirleme.</span><span class="sxs-lookup"><span data-stu-id="88ef4-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="88ef4-126">[![Senaryo A diyagramı ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88ef4-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="88ef4-127">İlgili Buluta bağlı kılavuzda, HoloLens 2'nin cihaz yönetiminize nasıl kaydedeceği, gerektiğinde lisansları nasıl uygulayacakları ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulama adımları açıklanır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="88ef4-128">Kısa vadeli veya uzun vadeli dış kullanım için uzak bir siteye cihaz dağıtmak için Dış İstemciler kılavuzunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="88ef4-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="88ef4-129">Buluta bağlı ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="88ef4-130">Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="88ef4-131">Senaryo B: Kuruluş ağının içine dağıtma</span><span class="sxs-lookup"><span data-stu-id="88ef4-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="88ef4-132">Bu senaryo, çoğu bilgisayar için klasik dağıtımla Windows 10 aynıdır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="88ef4-133">HoloLens 2, şirket içi şirket kaynaklarına erişimi olan birincil olarak şirket ağına kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="88ef4-134">İnternet ve bulut hizmetleri sınırlı olabilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="88ef4-135">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="88ef4-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="88ef4-136">Wi-Fi, iç kaynaklara erişimi olan ve İnternet'e veya Bulut hizmetlerine sınırlı erişimi olan bir iç kurumsal ağdır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="88ef4-137">MDM Otomatik Kaydı ile Azure AD'ye Katılma</span><span class="sxs-lookup"><span data-stu-id="88ef4-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="88ef4-138">MDM (Intune) Yönetilen</span><span class="sxs-lookup"><span data-stu-id="88ef4-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="88ef4-139">Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma</span><span class="sxs-lookup"><span data-stu-id="88ef4-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="88ef4-140">Desteklenen cihaz başına tek veya birden çok kullanıcı</span><span class="sxs-lookup"><span data-stu-id="88ef4-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="88ef4-141">Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="88ef4-142">MDM aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="88ef4-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="88ef4-143">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="88ef4-143">Common Challenges</span></span>
   * <span data-ttu-id="88ef4-144">HoloLens 2, şirket içi AD'ye katılmayı veya SCCM'i desteklemez.</span><span class="sxs-lookup"><span data-stu-id="88ef4-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="88ef4-145">MDM ile yalnızca Azure AD'ye katılma.</span><span class="sxs-lookup"><span data-stu-id="88ef4-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="88ef4-146">Günümüzde birçok şirket, System Center Configuration Manager (SCCM) tarafından yönetilen şirket içi AD'ye katılmış cihazlar olarak bu senaryoda Windows 10 bilgisayarlarını dağıtmaya devam ediyor ve bulut tabanlı MDM çözümleri aracılığıyla iç Windows 10 cihazlarını yönetmek için dağıtılmış/yapılandırılmış altyapıya sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="88ef4-147">2 HoloLens ilk bulut cihazı olduğundan, Kullanıcı kimlik doğrulaması, işletim sistemi güncelleştirmeleri, MDM yönetimi ve diğer hizmetler için İnternet'e ve buluta bağlı hizmetlere yoğun şekilde güvenmektedir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="88ef4-148">Şirket ağına bağlanırken, HoloLens 2'ye ve üzerinde çalıştıran uygulamalara erişimi etkinleştirmek için büyük olasılıkla Ara Sunucu/Güvenlik Duvarı kurallarının ayarlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="88ef4-149">Kurumsal Wi-Fi bağlantısı genellikle cihazın veya kullanıcının ağ kimlik doğrulaması için sertifikalar gerektirir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="88ef4-150">MDM aracılığıyla cihazlarına sertifika dağıtmak Windows 10 gerekli altyapının veya ayarların yapılandırılması zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="88ef4-151">[![Senaryo B1 diyagramı ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88ef4-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="88ef4-152">[![Senaryo B2 diyagramı ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88ef4-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="88ef4-153">İlgili Kurumsal ağ kılavuzu, HoloLens 2'i mevcut cihaz yönetiminize kaydetme, gerektiğinde lisans uygulama ve son kullanıcılarının bir Dynamics 365 Kılavuzu çalıştıranın yanı sıra cihaz ayarlama sonrasında özel iş hattı uygulamalarını kullanabileceğini doğrulama hakkında bilgi verir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="88ef4-154">Kurumsal ağ dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="88ef4-155">Senaryo C: Güvenli çevrimdışı ortamda dağıtma</span><span class="sxs-lookup"><span data-stu-id="88ef4-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="88ef4-156">Bu, yüksek oranda güvenli veya gizli konumlar için tipik bir dağıtımdır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="88ef4-157">HoloLens 2, ağ veya internet erişimine sahip değilken öncelikli olarak çevrimdışı kullanım için dağıtılır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="88ef4-158">Temel Ortak Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="88ef4-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="88ef4-159">Wi-Fi devre dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="88ef4-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="88ef4-160">Gerekirse, LAN bağlantısı için USB üzerinden Ethernet etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="88ef4-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="88ef4-161">Yönetilmiyor.</span><span class="sxs-lookup"><span data-stu-id="88ef4-161">Not Managed.</span></span>
   * <span data-ttu-id="88ef4-162">Cihaz oturum açma için yerel kullanıcı hesabı.</span><span class="sxs-lookup"><span data-stu-id="88ef4-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="88ef4-163">HoloLens 2 yalnızca bir yerel hesabı destekler.</span><span class="sxs-lookup"><span data-stu-id="88ef4-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="88ef4-164">Cihaz kilitleme yapılandırmalarının farklı düzeyleri, belirli kullanım örneklerine göre Sağlama Paketleri aracılığıyla uygulanır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="88ef4-165">Bu yapılandırmalar genellikle güvenli ortam gereksinimleri nedeniyle kısıtlanır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="88ef4-166">Sağlama Paketi aracılığıyla bir veya daha fazla uygulama dağıtılır</span><span class="sxs-lookup"><span data-stu-id="88ef4-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="88ef4-167">Yaygın Zorluklar</span><span class="sxs-lookup"><span data-stu-id="88ef4-167">Common Challenges</span></span>
   * <span data-ttu-id="88ef4-168">Sağlama Paketleri aracılığıyla kullanılabilen sınırlı bir yapılandırma kümesi vardır</span><span class="sxs-lookup"><span data-stu-id="88ef4-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="88ef4-169">Bulut hizmetleri kullanılamaz, bu nedenle 2. HoloLens sınırlayıcıdır.</span><span class="sxs-lookup"><span data-stu-id="88ef4-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="88ef4-170">Bu cihazların el ile yapılandırılması, yapılandırılması ve güncelleştirilmiş olması nedeniyle daha yüksek yönetim yükü.</span><span class="sxs-lookup"><span data-stu-id="88ef4-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="88ef4-171">[![Çevrimdışı Güvenli diyagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="88ef4-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="88ef4-172">İlgili Çevrimdışı güvenli kılavuz, güvenli ortamlarda kullanmak üzere bir HoloLens 2'nin kilitlenmesini sağlayan örnek Sağlama Paketi uygulama yönergesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="88ef4-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="88ef4-173">Çevrimdışı güvenli ortam dağıtım kılavuzu</span><span class="sxs-lookup"><span data-stu-id="88ef4-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


