---
title: Genel Bakış - Uygulama Yönetimi
description: Kullanmaya başlayın cihaz yönetimi, iş için Microsoft Mağazası ve paket sağlama ile karma gerçeklik uygulama yönetimine genel bir bakış sunar.
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379002"
---
# <a name="app-management-overview"></a><span data-ttu-id="941e0-104">Uygulama Yönetimi: Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="941e0-104">App Management: Overview</span></span>

<span data-ttu-id="941e0-105">Uygulamaları dört farklı yola dağıtabilirsiniz: **Mobil Cihaz Yönetimi (MDM)**, **İş İçin Microsoft Store**, **Microsoft Store** veya Sağlama aracılığıyla **yükleyerek.**</span><span class="sxs-lookup"><span data-stu-id="941e0-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="941e0-106">Mobil Cihaz Yönetimi (MDM)</span><span class="sxs-lookup"><span data-stu-id="941e0-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="941e0-107">MDM çözümü, IT kararlarını verenlerin ve yöneticilerin bir grup kullanıcı için mağaza üzerinden kendi kendi iş hattı uygulamalarını özel olarak otomatik olarak yüklemesini (yüklemesini) veya uygulama satın almalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="941e0-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="941e0-108">HoloLens cihazları, uygulama yönetimi için microsoft Endpoint Manager (Intune) ile [en iyi şekilde çalışır.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="941e0-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="941e0-109">Intune ayrıca kullanıcılara indirilebilir deneyim aracılığıyla, IT tarafından yönetilen uygulamalar üzerinde daha Şirket Portalı denetim sunar.</span><span class="sxs-lookup"><span data-stu-id="941e0-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="941e0-110">Aşağıdaki yönergeler, uygulamalarını Intune ile yönetmek isteyen kullanıcılara ilişkindir.</span><span class="sxs-lookup"><span data-stu-id="941e0-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="941e0-111">Microsoft, uygulama ve cihaz yönetimi için Intune'un kullanılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="941e0-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="941e0-112">Mobil Cihaz Yönetimi (MDM) şu uygulamalar için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="941e0-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="941e0-113">Dağıtılan MDM + Şirket Portalı</span><span class="sxs-lookup"><span data-stu-id="941e0-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="941e0-114">İş Hattı (genel olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="941e0-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="941e0-115">Kullanılabilir uygulamaların Şirket Portalı aracılığıyla el ile yüklenmesi</span><span class="sxs-lookup"><span data-stu-id="941e0-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="941e0-116">MDM ilkesi aracılığıyla yönetici anında iletme</span><span class="sxs-lookup"><span data-stu-id="941e0-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="941e0-117">MDM aracılığıyla otomatik güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="941e0-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="941e0-118">İş İçin Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="941e0-118">Microsoft Store for Business</span></span>

<span data-ttu-id="941e0-119">Bu [İş İçin Microsoft Store,](app-deploy-store-business.md) işletmelerde ücretsiz ve ücretli uygulamaları bulmaları, edinmeleri, yönetmeleri ve dağıtmaları için IŞLETMELERDE KARAR VERENLER ve yöneticiler sağlar.</span><span class="sxs-lookup"><span data-stu-id="941e0-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="941e0-120">IT yöneticileri, Microsoft Store uygulamaları ve özel iş hattı uygulamalarını tek bir envanterde yönetebilir ve gerektiğinde lisansları atap yeniden kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="941e0-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="941e0-121">Daha fazla bilgi için [önkoşullar'ı ziyaret edin ve İş İçin Microsoft Store.](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="941e0-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="941e0-122">Aşağıdaki İş İçin Microsoft Store için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="941e0-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="941e0-123">Genel veya İş Hattı uygulamaları</span><span class="sxs-lookup"><span data-stu-id="941e0-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="941e0-124">MDM ilişkilendirmesi aracılığıyla gerekli uygulamaların otomatik olarak yüklenmesi</span><span class="sxs-lookup"><span data-stu-id="941e0-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="941e0-125">Kullanıcı uygulamaları el ile indirir</span><span class="sxs-lookup"><span data-stu-id="941e0-125">User manually downloads apps</span></span>
* <span data-ttu-id="941e0-126">Otomatik Güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="941e0-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="941e0-127">Microsoft Mağazası uygulamaları</span><span class="sxs-lookup"><span data-stu-id="941e0-127">Microsoft Store apps</span></span>

<span data-ttu-id="941e0-128">Bu Microsoft Store, genel uygulamaları bulmaları, edinmeleri, yönetmeleri ve dağıtmaları için işletmelerde IŞ kararlarını veren kullanıcılara ve yöneticilere sağlar.</span><span class="sxs-lookup"><span data-stu-id="941e0-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="941e0-129">Bu Microsoft Store için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="941e0-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="941e0-130">Yalnızca genel uygulamalar</span><span class="sxs-lookup"><span data-stu-id="941e0-130">Public apps only</span></span>
* <span data-ttu-id="941e0-131">Kullanıcı uygulamaları el ile indirir</span><span class="sxs-lookup"><span data-stu-id="941e0-131">User manually downloads apps</span></span>
* <span data-ttu-id="941e0-132">İnternet'e bağlı ise otomatik güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="941e0-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="941e0-133">Daha fazla bilgi için [Holographic Store Uygulamaları'ı ziyaret edin.](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="941e0-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="941e0-134">Paketleri Sağlama yoluyla yükleme</span><span class="sxs-lookup"><span data-stu-id="941e0-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="941e0-135">[Paketleri Sağlama,](app-deploy-provisioning-package.md) özel veya İş Hattı uygulamalarını yüklemenize olanak sağlayarak, IT profesyonellerinin ve yöneticilerin USB aracılığıyla uygulamaları yerel bir cihaza hızla yüklemesine olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="941e0-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="941e0-136">Bu yükleme bir İnternet bağlantısı olmadan ve herhangi bir kimlik türü için yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="941e0-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="941e0-137">Sağlama Paketleri aracılığıyla yükleme şu için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="941e0-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="941e0-138">İş Hattı / Kendi kendine geliştirilen (genel olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="941e0-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="941e0-139">Genel uygulamalar (çevrimdışı yükleyici varsa)</span><span class="sxs-lookup"><span data-stu-id="941e0-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="941e0-140">Yalnızca USB tarafı yükleme</span><span class="sxs-lookup"><span data-stu-id="941e0-140">USB side-loading only</span></span>
* <span data-ttu-id="941e0-141">Otomatik güncelleştirme yok (Sağlama Paketi aracılığıyla el ile güncelleştirme gerektirir)</span><span class="sxs-lookup"><span data-stu-id="941e0-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="941e0-142">Uygulama Yükleyicisi aracılığıyla HoloLens 2'ye Uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="941e0-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="941e0-143">Bu [Uygulama Yükleyicisi,](app-deploy-app-installer.md) uygulamaları yerel cihazlara yüklemek veya HoloLens'e başka uygulama yükleme yöntemleriyle yabancı olan başka bir kullanıcıyla paylaşmak için basit bir deneyime sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="941e0-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="941e0-144">Bu, Geliştirici Modunu etkinleştirmeye veya bu modu kullanmaya gerek kalmadan Cihaz Portalı.</span><span class="sxs-lookup"><span data-stu-id="941e0-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="941e0-145">Bu, tamamen yerleşik bir uygulamayı dağıtmanın basit bir yöntemidir.</span><span class="sxs-lookup"><span data-stu-id="941e0-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="941e0-146">Uygulamanızı HoloLens ile başka bir kullanıcıya tanıtım yapmak veya uygulamanızı dağıtmak istediğinizden bağımsız olarak bu yöntem kolayca çalışır.</span><span class="sxs-lookup"><span data-stu-id="941e0-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="941e0-147">Uygulama Yükleyicisi yüklemesi şu için geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="941e0-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="941e0-148">İş Hattı / Kendi geliştirdiği (genel olmayan) uygulamalar</span><span class="sxs-lookup"><span data-stu-id="941e0-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="941e0-149">Yalnızca yan yükleme</span><span class="sxs-lookup"><span data-stu-id="941e0-149">Side-load only</span></span>
* <span data-ttu-id="941e0-150">Geliştirici modu veya Cihaz portalı gerektirmez</span><span class="sxs-lookup"><span data-stu-id="941e0-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="941e0-151">Son kullanıcının yüklemesi kolay</span><span class="sxs-lookup"><span data-stu-id="941e0-151">Easy for end user to install</span></span>
