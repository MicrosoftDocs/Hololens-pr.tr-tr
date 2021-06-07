---
title: Dağıtım Kılavuzu – bulut bağlantılı HoloLens 2 dağıtımı, uzaktan yardım-bakım ile ölçeklendirin
description: HoloLens cihazlarını bulut bağlantılı bir ağ üzerinden sürdürmek ve desteklemek için ipuçlarımızla güncel kalın.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379116"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="fcc19-104">Bakım-bulut bağlantılı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="fcc19-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="fcc19-105">Güncelleştirmeler</span><span class="sxs-lookup"><span data-stu-id="fcc19-105">Updates</span></span>

<span data-ttu-id="fcc19-106">Microsoft, BT yöneticilerine, cihaz gruplarına güncelleştirme dağıtma ve güncelleştirme yüklemeye yönelik bakım pencerelerini tanımlama gibi ek Windows Update merkezli yönetim özellikleri sağlamak için Windows Update tasarlamıştır.</span><span class="sxs-lookup"><span data-stu-id="fcc19-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="fcc19-107">Zamanlanan günler ve zamanlanan saatler dahil olmak üzere [HoloLens güncelleştirmelerini yönetmeyi](https://docs.microsoft.com/hololens/hololens-updates) ve çalışma saatleri dışında güncelleştirilecek şekilde cihazdaki etkin saatleri ayarlamayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="fcc19-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="fcc19-108">Uzaktan Yardım, bir In-Box uygulamasıdır ve Microsoft Store uygulama aracılığıyla güncelleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="fcc19-109">Microsoft Store aracılığıyla indirilen tüm uygulamalar için Microsoft Store uygulamasının kendisiyle el ile [güncelleştirilebilirler](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .</span><span class="sxs-lookup"><span data-stu-id="fcc19-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="fcc19-110">Destek Planı</span><span class="sxs-lookup"><span data-stu-id="fcc19-110">Support Plan</span></span>

<span data-ttu-id="fcc19-111">Bir destek planı, uygun olan harika bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="fcc19-112">Bir kişinin, HoloLens cihazlarda kayıt işleminin sorunlarını giderme ve aynı zamanda kuruluşunuzun içindeki HoloLens cihazının genel kullanımı konusunda eğitilen bir grup vardır.</span><span class="sxs-lookup"><span data-stu-id="fcc19-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="fcc19-113">Kullanıcılarınızın sorunlarından daha hızlı çözümlenmesine izin vermek için, yükseltme işleminizin bu sırayla benzer bir şekilde işlenmesini öneririz:</span><span class="sxs-lookup"><span data-stu-id="fcc19-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="fcc19-114">Destek masanıza başvurun.</span><span class="sxs-lookup"><span data-stu-id="fcc19-114">Your Support desk.</span></span>
2. <span data-ttu-id="fcc19-115">HoloLens uzman ekibiniz</span><span class="sxs-lookup"><span data-stu-id="fcc19-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="fcc19-116">[HoloLens belgeleri](https://docs.microsoft.com/hololens/)  /  [HoloLens sorunlarını giderme belgeleri](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="fcc19-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="fcc19-117">Desteğe başvurun</span><span class="sxs-lookup"><span data-stu-id="fcc19-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="fcc19-118">Geliştirme planı</span><span class="sxs-lookup"><span data-stu-id="fcc19-118">Development Plan</span></span>

<span data-ttu-id="fcc19-119">Cihazınız başarıyla kaydedildikten sonra, cihazlarınıza Iş kolu uygulamaları (LOB uygulamaları) dağıtmaya hazırsınız demektir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="fcc19-120">Bunlar, kuruluşunuz&#39;ihtiyaçları için oluşturulmuş özel uygulamalardır.</span><span class="sxs-lookup"><span data-stu-id="fcc19-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="fcc19-121">Zaten bir iş kolu uygulamanız varsa, [UYGULAMANıZı MDM aracılığıyla dağıtmaya](https://docs.microsoft.com/hololens/app-deploy-intune)başlamaya&#39;.</span><span class="sxs-lookup"><span data-stu-id="fcc19-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="fcc19-122">Farklı bir yöntemi tercih&#39;, daha sonra LOB uygulamanızı cihazlarınıza dağıtma hakkında daha fazla bilgi edinmek için, [HoloLens 2 için uygulama dağıtımına genel bakış](https://docs.microsoft.com/hololens/app-deploy-overview) konusunu gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="fcc19-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="fcc19-123">Kendi LOB uygulamanızı oluşturmanız veya hala oluşturma süreciyle karşılaşırsanız, karma gerçeklik geliştirme belgelerimizi inceleyerek [karma gerçeklik geliştirmesini](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) kullanmaya başlamak için temel kavramları gözden geçirin [veya öğrenin](https://docs.microsoft.com/windows/mixed-reality/design/design) .&#39;</span><span class="sxs-lookup"><span data-stu-id="fcc19-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="fcc19-124">Aygıt Yönetimi</span><span class="sxs-lookup"><span data-stu-id="fcc19-124">Device Management</span></span> 

<span data-ttu-id="fcc19-125">Bu kılavuz, mobil cihaz yönetimi (MDM) ayarlama hakkında konuşurken cihaz kısıtlamalarını uygulamak için işe yaramadı veya cihazlara uygulandı.</span><span class="sxs-lookup"><span data-stu-id="fcc19-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="fcc19-126">Cihaz yönetimi, sertifikaları ileterek erişime izin vermek veya çeşitli cihaz kısıtlamalarıyla erişimi kısıtlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="fcc19-127">Birçok durumda, cihazlarda Bluetooth, VPN, USB veya kamera ya da mikrofona erişimi kapatma gibi bağlantı kısıtlamaları olabilir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="fcc19-128">Bu ilgi alanlarından herhangi biri bundan sonra [ortak cihaz kısıtlamaları sayfasını](hololens-common-device-restrictions.md)okumanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="fcc19-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="fcc19-129">Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları vardır.</span><span class="sxs-lookup"><span data-stu-id="fcc19-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="fcc19-130">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="fcc19-130">Such as:</span></span>

- <span data-ttu-id="fcc19-131">Settings uygulamasında görüntülenebilen sayfaları, [Settingspagevisibility](settings-uri-list.md)kullanarak, kullanıcıların yalnızca Wi-Fi bağlantılarını değiştirme gibi ayarlamak için ihtiyaç duydukları ayarlara erişmesine izin veren şekilde sınırlama.</span><span class="sxs-lookup"><span data-stu-id="fcc19-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="fcc19-132">Bir cihazdaki kullanıcılara sunulan kullanıcı arabirimini sınırlamak için [bilgi noktası modunu](hololens-kiosk.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="fcc19-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="fcc19-133">Kiosks 'i tek bir uygulama veya bir özel başlangıç sayfası ile birden çok uygulama gösterecek şekilde ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fcc19-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="fcc19-134">Kiosks, farklı kullanıcılara farklı deneyimler de sunabilir.</span><span class="sxs-lookup"><span data-stu-id="fcc19-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="fcc19-135">Belirli uygulamaların veya işlemlerin tamamen başlatılmasını sağlamak için [Windows uygulama denetimi (WDAC)](windows-defender-application-control-wdac.md) .</span><span class="sxs-lookup"><span data-stu-id="fcc19-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="fcc19-136">Cihaz yönetimi veya cihaz kısıtlamalarının daha farklı yöntemleri hakkında daha fazla bilgi edinmek istiyorsanız, sonraki adıma geçin ve cihaz yönetimine genel bakış konusunu okuyun.</span><span class="sxs-lookup"><span data-stu-id="fcc19-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="fcc19-137">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="fcc19-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fcc19-138">CSP 'Leri ve cihaz yönetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="fcc19-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)