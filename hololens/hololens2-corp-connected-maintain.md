---
title: Dağıtım Kılavuzu – Dynamics 365 kılavuzları HoloLens 2 kurumsal bağlantılı bağlantı - Bakım
description: Dynamics 365 kılavuzları HoloLens bağlı bir ağ üzerinden 2 cihazı korumayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637005"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="963c0-104">Bakım - Kurumsal Bağlantılı Kılavuz</span><span class="sxs-lookup"><span data-stu-id="963c0-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="963c0-105">Güncelleştirme HoloLens</span><span class="sxs-lookup"><span data-stu-id="963c0-105">Update HoloLens</span></span>

<span data-ttu-id="963c0-106">Microsoft, Windows güncelleştirmeleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemek için bakım pencerelerini tanımlama gibi ek Windows Güncelleştirme odaklı yönetim özellikleri sağlamak için İş için Güncelleştirme'yi tasarladı.</span><span class="sxs-lookup"><span data-stu-id="963c0-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="963c0-107">Güncelleştirmeleri yönetmenin popüler yöntemlerinden biri, 30 günlük bir özellik ertelemesi yapmaktır.</span><span class="sxs-lookup"><span data-stu-id="963c0-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="963c0-108">Bu, Yöneticilerin yeni özellikleri güncelleştirmesine ve önizlemesine olanak sağlar, ilk el ile bilgi edinerek ve destek masanıza yeni değişiklikler hakkında bilgi verir.</span><span class="sxs-lookup"><span data-stu-id="963c0-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="963c0-109">Cihazda [zamanlanan HoloLens,](/hololens/hololens-updates)zamanlanmış saat ve etkin saatleri ayarlama dahil olmak üzere, cihaz çalışma saatleri dışında güncelleştirilecek şekilde güncelleştirmeleri yönetmeyi öğrenin.</span><span class="sxs-lookup"><span data-stu-id="963c0-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="963c0-110">Dynamics 365 Kılavuzlarını (ve diğer mağaza uygulamalarını) güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="963c0-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="963c0-111">Dynamics 365 Kılavuzları, In-Box bir uygulamadır ve Microsoft Store güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="963c0-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="963c0-112">Uygulama aracılığıyla indirilen tüm uygulamalar Microsoft Store uygulamanın [kendisi aracılığıyla Microsoft Store](/hololens/holographic-store-apps#update-apps) güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="963c0-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="963c0-113">LOB uygulamalarını güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="963c0-113">How to update LOB apps</span></span>

<span data-ttu-id="963c0-114">LOB uygulamaları, Intune'a eklendikleri şekilde güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="963c0-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="963c0-115">Intune'da uygulamalar, mevcut Uygulama yapılandırmasına daha yüksek bir sürüm numarasıyla yeni uygulama yükleniyor şekilde güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="963c0-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="963c0-116">Cihaz Intune'a eşitlenirken, daha yeni bir uygulama sürümü olduğunu ve daha yeni bir uygulamanın indirilir ve eski uygulamanın yerini alır.</span><span class="sxs-lookup"><span data-stu-id="963c0-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="963c0-117">Yeni uygulamayı karşıya yüklemek için [MEM portalı](https://endpoint.microsoft.com/#home)Uygulamalar -> Tüm uygulamalar  ->     ->  *TheNameOfApp Properties'e*  ->  **gidin.**</span><span class="sxs-lookup"><span data-stu-id="963c0-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="963c0-118">Uygulama bilgileri'nin yanındaki Düzenle'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="963c0-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="963c0-119">Güncelleştirilen dosya &quot; seç değerinin &quot; değeri olarak dosyanızı seçin.</span><span class="sxs-lookup"><span data-stu-id="963c0-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="963c0-120">Buradan bağlam menüsünü kullanarak dosya gezgininizi açın ve LOB uygulamasının yeni sürümünü karşıya yükleyin.</span><span class="sxs-lookup"><span data-stu-id="963c0-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="963c0-121">Gerektiğinde bağımlılıkları dahil etmek için emin olmak.</span><span class="sxs-lookup"><span data-stu-id="963c0-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="963c0-122">Daha fazla bilgi: [HoloLens için Intune Uygulama Dağıtımı](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="963c0-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="963c0-123">Geliştirme Planı</span><span class="sxs-lookup"><span data-stu-id="963c0-123">Development Plan</span></span>

<span data-ttu-id="963c0-124">Cihazınız başarıyla kaydedildi. Artık cihazlarınıza daha fazla LOB uygulaması dağıtmaya hazır olursanız.</span><span class="sxs-lookup"><span data-stu-id="963c0-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="963c0-125">Bu Kılavuz süresince bir örnek uygulama kullanıyoruz, ancak büyük olasılıkla, kuruluş ihtiyaçlarına göre özel uygulamalar kullanmak istemeniz daha olasıdır.</span><span class="sxs-lookup"><span data-stu-id="963c0-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="963c0-126">Zaten bir LOB uygulamanız varsa, uygulamanızı [MDM aracılığıyla dağıtmaya hazır olursanız.](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="963c0-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="963c0-127">Farklı bir yöntem tercih ediyorsanız, LOB uygulamanızı cihazlarınıza dağıtmaya yönelik daha fazla yöntem hakkında daha fazla bilgi edinmek [için HoloLens 2](/hololens/app-deploy-overview) için uygulama dağıtımına genel bakış'ı gözden geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="963c0-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="963c0-128">Henüz kendi LOB uygulamanızı oluşturmadıysanız veya hala oluşturma aşamasındaysanız karma gerçeklik geliştirme belgelerimizi gözden geçirerek karma gerçeklik geliştirmeyle çalışmaya başlamak için tasarım ve [protokasyon](/windows/mixed-reality/design/design) yapmaya veya temel kavramları öğrenmeye [başlayabilirsiniz.](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="963c0-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="963c0-129">Destek Planı</span><span class="sxs-lookup"><span data-stu-id="963c0-129">Support Plan</span></span>

<span data-ttu-id="963c0-130">Destek planı, hazır olmak için harika bir şeydir.</span><span class="sxs-lookup"><span data-stu-id="963c0-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="963c0-131">Bir kişinin veya grubun, HoloLens cihazlarda kayıt işlemiyle ilgili sorun giderme konusunda eğitilmiş olması ve ayrıca HoloLens cihaz kullanımı yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="963c0-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="963c0-132">Kullanıcılarının sorunlarının daha hızlı çözüme sahip olmasına olanak vermek için, yükseltme işleminizin bu sırayla benzer şekilde ele uygulanmasını öneririz:</span><span class="sxs-lookup"><span data-stu-id="963c0-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="963c0-133">Destek masanız.</span><span class="sxs-lookup"><span data-stu-id="963c0-133">Your Support desk.</span></span>
2. <span data-ttu-id="963c0-134">HoloLens Uzman takımınız</span><span class="sxs-lookup"><span data-stu-id="963c0-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="963c0-135">[HoloLens Docs](/hololens/)  /  [HoloLens Sorun Giderme Belgeleri](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="963c0-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="963c0-136">De destekle iletişime geçin</span><span class="sxs-lookup"><span data-stu-id="963c0-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="963c0-137">Aygıt Yönetimi</span><span class="sxs-lookup"><span data-stu-id="963c0-137">Device Management</span></span>

<span data-ttu-id="963c0-138">Bu kılavuzda Mobile Cihaz Yönetimi (MDM) ayarlama hakkında bilgi edinildi ve bu kılavuzda bazı cihaz yapılandırmaları ayarlamak ve sertifikalar ve ara sunucu açısından erişime izin vermek için Wi-Fi kullanılmıştır.</span><span class="sxs-lookup"><span data-stu-id="963c0-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="963c0-139">Ancak MDM, CSP'ler ve İlkeler aracılığıyla cihaz kısıtlamaları uygulamak için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="963c0-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="963c0-140">Çoğu durumda cihazların bağlantı kısıtlamaları olabilir; örneğin Bluetooth, VPN, USB, hatta kameraya veya mikrofona erişimi kapatma.</span><span class="sxs-lookup"><span data-stu-id="963c0-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="963c0-141">Bu sorunlardan herhangi biri sizi ilgilendirmeye devam ediyorsa, yaygın cihaz kısıtlamaları [sayfamızı okumanız teşvik edilecektir.](/hololens/hololens-common-device-restrictions)</span><span class="sxs-lookup"><span data-stu-id="963c0-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="963c0-142">Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları da vardır.</span><span class="sxs-lookup"><span data-stu-id="963c0-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="963c0-143">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="963c0-143">Such as:</span></span>

- <span data-ttu-id="963c0-144">Ayarlar uygulamasında görüntülenecek sayfaları, [AyarlarSayfaVisibility](/hololens/settings-uri-list)kullanarak sınırlamak, kullanıcıların yalnızca kendi bağlantılarını değiştirme gibi yalnızca ayarlamaları gereken ayarlara erişmesine Wi-Fi sağlar.</span><span class="sxs-lookup"><span data-stu-id="963c0-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="963c0-145">Bir [cihazda kullanıcılara](/hololens/hololens-kiosk) sunulan kullanıcı arabirimini sınırlamak için Bilgi Noktası modunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="963c0-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="963c0-146">Bilgi Noktası'nın tek bir uygulamayı veya özel başlangıç sayfası olan birden çok uygulamayı gösterecek şekilde ayarlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="963c0-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="963c0-147">Bilgi noktası, farklı kullanıcılara farklı deneyimler de sunabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="963c0-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="963c0-148">[Windows veya işlemlerin tamamen başlatılmasını](/hololens/windows-defender-application-control-wdac) tutmak için Uygulama Denetimi'ne (WDAC) tıklayın.</span><span class="sxs-lookup"><span data-stu-id="963c0-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="963c0-149">Ek cihaz yönetimi veya cihaz kısıtlama yöntemleri hakkında bilgi edinmek için bir sonraki adıma geçin ve Genel Bakış [makalemizi Cihaz Yönetimi okuyun.](/hololens/hololens-csp-policy-overview)</span><span class="sxs-lookup"><span data-stu-id="963c0-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





