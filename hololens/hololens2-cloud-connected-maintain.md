---
title: Dağıtım Kılavuzu – Remote Assist ile buluta HoloLens 2 dağıtım - Bakım
description: Buluta Bağlı ağ üzerinden cihazları korumak ve desteklemek için HoloLens ipuçlarımızı takip edin.
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635169"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="d477f-104">Bakım - Buluta bağlı Kılavuz</span><span class="sxs-lookup"><span data-stu-id="d477f-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="d477f-105">Güncelleştirmeler</span><span class="sxs-lookup"><span data-stu-id="d477f-105">Updates</span></span>

<span data-ttu-id="d477f-106">Microsoft, Windows güncelleştirmeleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemek için bakım pencerelerini tanımlama gibi ek Windows Güncelleştirme odaklı yönetim özellikleri sağlamak için İş için Güncelleştirme'yi tasarladı.</span><span class="sxs-lookup"><span data-stu-id="d477f-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="d477f-107">Zamanlanan gün [sayısı HoloLens zamanlanmış saat](/hololens/hololens-updates) dahil olmak üzere cihaz güncelleştirmelerini yönetmeyi ve cihazda etkin saatleri çalışma saatleri dışında güncelleştirilecek şekilde ayarlamayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="d477f-107">Learn how to [manage HoloLens updates](/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="d477f-108">Remote Assist, In-Box bir uygulamadır ve bu uygulama aracılığıyla Microsoft Store olabilir.</span><span class="sxs-lookup"><span data-stu-id="d477f-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="d477f-109">Uygulama aracılığıyla indirilen tüm uygulamalar Microsoft Store uygulamanın [kendisi aracılığıyla Microsoft Store](/hololens/holographic-store-apps#update-apps) güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="d477f-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="d477f-110">Destek Planı</span><span class="sxs-lookup"><span data-stu-id="d477f-110">Support Plan</span></span>

<span data-ttu-id="d477f-111">Destek planı, hazır olmak için harika bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="d477f-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="d477f-112">Bir kişinin veya grubun, HoloLens cihazlarda kayıt işlemiyle ilgili sorun giderme konusunda eğitilmiş olması ve HoloLens cihazın genel olarak kullanımı yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="d477f-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="d477f-113">Kullanıcılarının sorunlarının daha hızlı çözüme sahip olmasına olanak vermek için, yükseltme işleminizin bu sırayla benzer şekilde ele uygulanmasını öneririz:</span><span class="sxs-lookup"><span data-stu-id="d477f-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="d477f-114">Destek masanız.</span><span class="sxs-lookup"><span data-stu-id="d477f-114">Your Support desk.</span></span>
2. <span data-ttu-id="d477f-115">HoloLens Uzman takımınız</span><span class="sxs-lookup"><span data-stu-id="d477f-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="d477f-116">[HoloLens Docs](/hololens/)  /  [HoloLens Sorun Giderme Belgeleri](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="d477f-116">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="d477f-117">De destekle iletişime geçin</span><span class="sxs-lookup"><span data-stu-id="d477f-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="d477f-118">Geliştirme Planı</span><span class="sxs-lookup"><span data-stu-id="d477f-118">Development Plan</span></span>

<span data-ttu-id="d477f-119">Cihazınız başarıyla kaydedildi. Artık cihazlarınıza İş Hattı uygulamalarını (LOB uygulamaları) dağıtmaya hazır olursanız.</span><span class="sxs-lookup"><span data-stu-id="d477f-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="d477f-120">Bunlar, kuruluşun ihtiyaçlarına uygun olarak&#39;uygulamalardır.</span><span class="sxs-lookup"><span data-stu-id="d477f-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="d477f-121">Zaten bir iş hattı uygulamanız varsa,&#39;[MDM aracılığıyla dağıtmaya hazır olursanız.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="d477f-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="d477f-122">Farklı&#39;tercih ediyorsanız, LOB uygulamanızı cihazlarınıza [dağıtmanın daha fazla yöntemini öğrenmek için HoloLens 2](/hololens/app-deploy-overview) için uygulama dağıtımına genel bakış'ı gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d477f-122">If you&#39;d prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="d477f-123">Henüz&#39;lob uygulamanızı oluşturmadıysanız veya hala oluşturma aşamasındaysanız karma gerçeklik geliştirme belgelerimizi gözden geçirerek karma gerçeklik geliştirmeyle çalışmaya başlamak için temel kavramları tasarlamaya ve bunun için [protokasyona](/windows/mixed-reality/design/design) başlamaya veya temel kavramları öğrenmeye [başlayabilirsiniz.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="d477f-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="d477f-124">Aygıt Yönetimi</span><span class="sxs-lookup"><span data-stu-id="d477f-124">Device Management</span></span> 

<span data-ttu-id="d477f-125">Bu kılavuzda Mobile Cihaz Yönetimi (MDM) ayarlama konusundan söz ediliyordu ancak cihazlara cihaz kısıtlamalarını veya ilkelerini uygulamak için uygulanmadı.</span><span class="sxs-lookup"><span data-stu-id="d477f-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="d477f-126">Cihaz yönetimi, sertifikalar ile erişime izin vermek veya çeşitli cihaz kısıtlamalarıyla erişimi kısıtlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d477f-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="d477f-127">Çoğu durumda cihazlarda Bluetooth, VPN, USB veya kameraya ya da mikrofona erişimi kapatma gibi bağlantı kısıtlamaları olabilir.</span><span class="sxs-lookup"><span data-stu-id="d477f-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="d477f-128">Bu ilgi alanlarına sahip olursanız, yaygın cihaz kısıtlamaları [sayfamızı okumanız teşvik edilecektir.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="d477f-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="d477f-129">Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları da vardır.</span><span class="sxs-lookup"><span data-stu-id="d477f-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="d477f-130">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="d477f-130">Such as:</span></span>

- <span data-ttu-id="d477f-131">Ayarlar uygulamasında görüntülenecek sayfaları, [AyarlarSayfaVisibility](settings-uri-list.md)kullanarak sınırlandırarak, kullanıcıların yalnızca kendi bağlantılarını değiştirme gibi ayarlamaları gereken ayarlara erişmesine Wi-Fi sağlar.</span><span class="sxs-lookup"><span data-stu-id="d477f-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="d477f-132">Bir [cihazda kullanıcılara](hololens-kiosk.md) sunulan kullanıcı arabirimini sınırlamak için Bilgi Noktası modunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="d477f-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="d477f-133">Bilgi Noktası'nın tek bir uygulamayı veya özel başlangıç sayfası olan birden çok uygulamayı gösterecek şekilde ayarlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d477f-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="d477f-134">Bilgi noktası, farklı kullanıcılara farklı deneyimler de sunabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d477f-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="d477f-135">[Windows veya işlemlerin tamamen başlatılmasını](windows-defender-application-control-wdac.md) tutmak için Uygulama Denetimi'ne (WDAC) tıklayın.</span><span class="sxs-lookup"><span data-stu-id="d477f-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="d477f-136">Farklı cihaz yönetimi veya cihaz kısıtlama yöntemleri hakkında daha fazla bilgi edinmek için bir sonraki adıma geçin ve Genel Bakış makalemizi Cihaz Yönetimi okuyun.</span><span class="sxs-lookup"><span data-stu-id="d477f-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="d477f-137">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="d477f-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d477f-138">CSP'leri ve Cihaz Yönetimi Genel Bakış'Cihaz Yönetimi okuyun</span><span class="sxs-lookup"><span data-stu-id="d477f-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)