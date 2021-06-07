---
title: Intune ve Şirket Portalı
description: Intune, mobil cihaz yönetimi ve şirket portalı ile rahat bir kullanıcı deneyimi ayarlamayı, atamayı ve oluşturmayı öğrenin.
keywords: intune, uygulama yönetimi, uygulama, şirket portalı, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379105"
---
# <a name="intune--company-portal"></a><span data-ttu-id="e5cc3-104">Intune & Şirket Portalı</span><span class="sxs-lookup"><span data-stu-id="e5cc3-104">Intune & Company Portal</span></span>

<span data-ttu-id="e5cc3-105">Mobil Cihaz Yönetimi (MDM) ile, doğrudan HoloLens cihazlarınıza dağıtmak için [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) aracılığıyla kendi özel uygulamalarınızı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="e5cc3-106">Microsoft Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="e5cc3-107">Intune, Microsoft'un [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)paketine dahildir ve kullanıcıların üretken bir şekilde çalışmalarına olanak sağlar ve kuruluş verilerinizin korunmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="e5cc3-108">Intune hakkında daha fazla bilgi edinmek için [Intune nedir? makalelerini okuyun.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="e5cc3-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="e5cc3-109">Kurulum</span><span class="sxs-lookup"><span data-stu-id="e5cc3-109">Setup</span></span>

1. <span data-ttu-id="e5cc3-110">Bir İş Hattına uygulama yükleme veya Intune kiracınıza özel bir uygulama yükleme.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="e5cc3-111">Ayrıca bkz. [Kurumsal uygulama yönetimi.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="e5cc3-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="e5cc3-112">[Uygulamalarınızı bir gruba attayabilirsiniz.](https://docs.microsoft.com/mem/intune/apps/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="e5cc3-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="e5cc3-113">Seçtiğiniz atama türüne bağlı olarak, uygulama otomatik olarak teslim edilir veya bir uygulama seçiminiz varsa çekme için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="e5cc3-114">Appx paketinizi hazırlarken, dağıtmakta olduğunuz cihaz mimarilerini dahil etmek için hesaba katyın.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="e5cc3-115">HoloLens 2 ARM64, HoloLens (1. Nesil) ise x86'dır.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="e5cc3-116">Karma cihaz ortamına sahip olmak planlıyorsanız her ikisini de tek bir appx paketine dahil edersiniz.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="e5cc3-117">Atama türleri</span><span class="sxs-lookup"><span data-stu-id="e5cc3-117">Assignment types</span></span>

<span data-ttu-id="e5cc3-118">Kayıt sonrasında uygulamanın cihaza otomatik olarak yüklenmiş olması  için, bu gruplarda Gerekli'yi seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="e5cc3-119">Uygulamanın şirket portalı üzerinden kayıtlı cihazlara indirilsin mi? için Kayıtlı cihazlar için **kullanılabilir'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="e5cc3-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="e5cc3-120">End-User Deneyimi</span><span class="sxs-lookup"><span data-stu-id="e5cc3-120">End-User Experience</span></span>

<span data-ttu-id="e5cc3-121">Intune'da yapılandırmayı ayardikten sonra, son kullanıcıların seçili uygulamalarınızı almaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="e5cc3-122">Uygulamalarınızı otomatik olarak almak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="e5cc3-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="e5cc3-123">Cihazınızı kiracınıza kaydetme.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="e5cc3-124">Cihazınız kaydı tamamlandıktan sonra uygulamayı cihazınıza alasınız.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="e5cc3-125">Uygulamayı hemen görmüyorsanız Ayarlar Hesapları İş veya Okul hesabınıza ilişkin Bilgiler'e gidin ve yüklü uygulama durumuyla ilgili bilgileri görmek  >    >    >   için aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="e5cc3-126">Aşağıdakiler aracılığıyla uygulamalara Şirket Portalı:</span><span class="sxs-lookup"><span data-stu-id="e5cc3-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="e5cc3-127">Başlat **Menüsü'yü açın** **ve** Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="e5cc3-128">Uygulamayı **Şirket Portalı** ve indirin.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="e5cc3-129">Hesabınızla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-129">Sign into your account.</span></span>
4. <span data-ttu-id="e5cc3-130">Almak istediğiniz uygulamayı seçin ve indirin.</span><span class="sxs-lookup"><span data-stu-id="e5cc3-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="e5cc3-131">[Intune'da uygulamaları Şirket Portalı](https://docs.microsoft.com/mem/intune/apps/company-portal-app) ve yönetme hakkında daha fazla bilgi [edinin.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="e5cc3-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
