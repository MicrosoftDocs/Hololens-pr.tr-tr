---
title: Genel Bakış-uygulama yönetimi
description: Mobil cihaz yönetimi, iş için Microsoft Mağazası ve sağlama paketleri ile karma gerçeklik uygulama yönetimine genel bir bakış ile çalışmaya başlayın.
keywords: HoloLens, kullanıcı, hesap, uygulama, uygulama yönetimi,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635560"
---
# <a name="app-management-overview"></a><span data-ttu-id="bd35d-104">Uygulama Yönetimi: genel bakış</span><span class="sxs-lookup"><span data-stu-id="bd35d-104">App Management: Overview</span></span>

<span data-ttu-id="bd35d-105">farklı yollarla uygulama dağıtabilirsiniz: **mobil cihaz yönetimi (MDM)**, **İş İçin Microsoft Store**, **Microsoft Store** veya **sağlama** aracılığıyla yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd35d-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="bd35d-106">Mobil cihaz yönetimi (MDM)</span><span class="sxs-lookup"><span data-stu-id="bd35d-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="bd35d-107">Bir MDM çözümü, BT karar mekanizmalarının ve yöneticilerin şirket içi, iş kolu uygulamalarını veya mağaza aracılığıyla uygulama satın almasını (bir Kullanıcı grubu için) sağlar.</span><span class="sxs-lookup"><span data-stu-id="bd35d-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="bd35d-108">HoloLens cihazlar [uygulama yönetimi](app-deploy-intune.md)için en iyi Microsoft Endpoint Manager (ıntune) ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="bd35d-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="bd35d-109">ıntune ayrıca, Şirket Portalı indirilebilir deneyim aracılığıyla kullanıcılara, bt tarafından yönetilen uygulamalar üzerinde daha ayrıntılı denetim sağlar.</span><span class="sxs-lookup"><span data-stu-id="bd35d-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="bd35d-110">Aşağıdaki yönergeler, uygulamalarını Intune ile yönetmek isteyen kullanıcılar içindir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="bd35d-111">Microsoft, uygulama ve cihaz yönetimi için Intune kullanmayı önerir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="bd35d-112">Mobil cihaz yönetimi (MDM) şunları için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="bd35d-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="bd35d-113">MDM dağıtılan + Şirket Portalı</span><span class="sxs-lookup"><span data-stu-id="bd35d-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="bd35d-114">Iş kolu (genel olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="bd35d-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="bd35d-115">Şirket Portalı aracılığıyla kullanılabilir uygulamaların el ile yüklenmesi</span><span class="sxs-lookup"><span data-stu-id="bd35d-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="bd35d-116">MDM ilkesi aracılığıyla yönetici gönderimi</span><span class="sxs-lookup"><span data-stu-id="bd35d-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="bd35d-117">MDM üzerinden otomatik güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="bd35d-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="bd35d-118">İş İçin Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bd35d-118">Microsoft Store for Business</span></span>

<span data-ttu-id="bd35d-119">[İş İçin Microsoft Store](app-deploy-store-business.md) , bt karar mekanizmalarının ve işletmelerin ücretsiz ve ücretli uygulamaları bulmasını, almalarını, yönetmesi ve dağıtmalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="bd35d-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="bd35d-120">bt yöneticileri, Microsoft Store uygulamalarını ve özel iş kolu uygulamalarını tek bir envanterde yönetebilir, ayrıca gerektiğinde lisansları atayabilir ve yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bd35d-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="bd35d-121">daha fazla bilgi için [İş İçin Microsoft Store kullanmaya yönelik önkoşulları](/microsoft-store/prerequisites-microsoft-store-for-business)ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="bd35d-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="bd35d-122">İş İçin Microsoft Store için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="bd35d-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="bd35d-123">Kamu veya Iş kolu uygulamaları</span><span class="sxs-lookup"><span data-stu-id="bd35d-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="bd35d-124">MDM ilişkilendirmesi aracılığıyla gerekli uygulamaların otomatik yüklemesi</span><span class="sxs-lookup"><span data-stu-id="bd35d-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="bd35d-125">Kullanıcı uygulamaları el ile indirir</span><span class="sxs-lookup"><span data-stu-id="bd35d-125">User manually downloads apps</span></span>
* <span data-ttu-id="bd35d-126">Otomatik güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="bd35d-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="bd35d-127">Microsoft Mağazası uygulamaları</span><span class="sxs-lookup"><span data-stu-id="bd35d-127">Microsoft Store apps</span></span>

<span data-ttu-id="bd35d-128">Microsoft Store, bt karar mekanizmalarının ve işletmelerin ortak uygulamaları bulmasını, almalarını, yönetmesini ve dağıtmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="bd35d-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="bd35d-129">bu Microsoft Store için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="bd35d-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="bd35d-130">Yalnızca ortak uygulamalar</span><span class="sxs-lookup"><span data-stu-id="bd35d-130">Public apps only</span></span>
* <span data-ttu-id="bd35d-131">Kullanıcı uygulamaları el ile indirir</span><span class="sxs-lookup"><span data-stu-id="bd35d-131">User manually downloads apps</span></span>
* <span data-ttu-id="bd35d-132">Internet 'e bağlıysa otomatik güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="bd35d-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="bd35d-133">Daha fazla bilgi için [holographic Store Apps](/hololens/holographic-store-apps)sayfasını ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="bd35d-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="bd35d-134">Sağlama paketleri aracılığıyla yüklemesi</span><span class="sxs-lookup"><span data-stu-id="bd35d-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="bd35d-135">[Sağlama paketleri](app-deploy-provisioning-package.md) , BT uzmanlarının ve YÖNETICILERIN uygulamaları USB üzerinden yerel cihazlara hızlıca yüklemesini sağlayan özel veya iş kolu uygulamaları yüklemenize imkan tanır.</span><span class="sxs-lookup"><span data-stu-id="bd35d-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="bd35d-136">Bu yükleme, bir internet bağlantısı ve herhangi bir kimlik türü olmadan yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="bd35d-137">Sağlama paketleri aracılığıyla yükleme şunları için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="bd35d-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="bd35d-138">Iş kolu/kendi kendine geliştirilmiş (ortak olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="bd35d-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="bd35d-139">Ortak uygulamalar (çevrimdışı yükleyici varsa)</span><span class="sxs-lookup"><span data-stu-id="bd35d-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="bd35d-140">Yalnızca USB dışarıdan yükleme</span><span class="sxs-lookup"><span data-stu-id="bd35d-140">USB side-loading only</span></span>
* <span data-ttu-id="bd35d-141">Otomatik güncelleştirme yok (sağlama paketi aracılığıyla el ile güncelleştirmeler gerektirir)</span><span class="sxs-lookup"><span data-stu-id="bd35d-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="bd35d-142">uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="bd35d-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="bd35d-143">[Uygulama yükleyicisi](app-deploy-app-installer.md) kullanıcılarının kullanılması, yerel cihazlara uygulama yüklemek veya bir uygulamayı, Hololens diğer uygulama yükleme yöntemlerini bilmediğiniz başka biriyle paylaşmak için basit bir deneyimle sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="bd35d-144">Bu işlem, geliştirici modunun etkinleştirilmesi veya cihaz portalı kullanılması gerekmeden yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="bd35d-145">Bu, tamamen oluşturulmuş bir uygulamayı dağıtmanın basit bir yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="bd35d-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="bd35d-146">uygulamanızı yalnızca bir HoloLens başka bir kullanıcıya tanıtıyor veya uygulamanızı dağıtmak istediğinizde, bu yöntem kolayca işe yarar.</span><span class="sxs-lookup"><span data-stu-id="bd35d-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="bd35d-147">Uygulama yükleyicisi aracılığıyla yükleme şunları için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="bd35d-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="bd35d-148">Iş kolu/kendi kendine geliştirilmiş (ortak olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="bd35d-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="bd35d-149">Yalnızca dışarıdan yükleme</span><span class="sxs-lookup"><span data-stu-id="bd35d-149">Side-load only</span></span>
* <span data-ttu-id="bd35d-150">Geliştirici modu veya cihaz portalı gerektirmez</span><span class="sxs-lookup"><span data-stu-id="bd35d-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="bd35d-151">Son kullanıcının yüklemesi kolay</span><span class="sxs-lookup"><span data-stu-id="bd35d-151">Easy for end user to install</span></span>
