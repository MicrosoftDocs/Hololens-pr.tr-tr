---
title: ıntune ve Şirket Portalı
description: Intune, mobil cihaz yönetimi ve şirket portalı ile rahat bir kullanıcı deneyimi ayarlamayı, atamayı ve oluşturmayı öğrenin.
keywords: Intune, uygulama yönetimi, uygulama, Şirket portalı, Portal, Hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635509"
---
# <a name="intune--company-portal"></a><span data-ttu-id="8097e-104">ıntune & Şirket Portalı</span><span class="sxs-lookup"><span data-stu-id="8097e-104">Intune & Company Portal</span></span>

<span data-ttu-id="8097e-105">mobil cihaz yönetimi (MDM) ile, doğrudan HoloLens cihazlarınıza dağıtmak için [Microsoft Endpoint Manager (ıntune)](/intune/windows-holographic-for-business) aracılığıyla kendi özel uygulamalarınızı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8097e-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="8097e-106">Microsoft Intune, mobil cihaz yönetimine (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir.</span><span class="sxs-lookup"><span data-stu-id="8097e-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="8097e-107">ıntune, Microsoft 'un [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)'e dahil edilmiştir ve kuruluşunuzun verilerinin korunmasını sağlarken kullanıcıların üretken olmalarını sağlar.</span><span class="sxs-lookup"><span data-stu-id="8097e-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="8097e-108">Intune hakkında daha fazla bilgi edinmek için [Intune](/mem/intune/fundamentals/what-is-intune)'u okuyun.</span><span class="sxs-lookup"><span data-stu-id="8097e-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="8097e-109">Kurulum</span><span class="sxs-lookup"><span data-stu-id="8097e-109">Setup</span></span>

1. <span data-ttu-id="8097e-110">bir iş kolu için uygulama Upload veya özel bir uygulamayı ıntune kiracınıza yükleyin.</span><span class="sxs-lookup"><span data-stu-id="8097e-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="8097e-111">ayrıca bkz: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span><span class="sxs-lookup"><span data-stu-id="8097e-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="8097e-112">[Uygulamanızı bir gruba atayın](/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="8097e-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="8097e-113">Seçtiğiniz atama türüne göre uygulama otomatik olarak teslim edilebilir veya bir uygulama seçiminiz varsa, kolayca kullanıma sunulabilir.</span><span class="sxs-lookup"><span data-stu-id="8097e-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="8097e-114">Appx paketlerinizi oluştururken, dağıttığınız cihazların mimarisini dahil etmek için hesap yaptığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="8097e-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="8097e-115">HoloLens 2 ARM64, HoloLens (1. Gen) ise x86.</span><span class="sxs-lookup"><span data-stu-id="8097e-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="8097e-116">Karma cihazlar ortamı bulundurmaktan karşılaşıyorsanız, her ikisini de tek bir appx paketine dahil edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="8097e-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="8097e-117">Atama türleri</span><span class="sxs-lookup"><span data-stu-id="8097e-117">Assignment types</span></span>

<span data-ttu-id="8097e-118">Uygulamanızın kayıt sonrasında cihaza otomatik olarak yüklenmesini sağlamak için, bu gruplar için **gerekli** ' ı seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="8097e-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="8097e-119">Uygulamanızı Şirket portalı üzerinden kaydedilmiş cihazlara indirilebilir hale getirmek için, **Kayıtlı cihazlar Için kullanılabilir**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="8097e-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="8097e-120">End-User deneyim</span><span class="sxs-lookup"><span data-stu-id="8097e-120">End-User Experience</span></span>

<span data-ttu-id="8097e-121">Intune 'da yapılandırmayı ayarladıktan sonra, son kullanıcıların seçili uygulamalarınızı almasına hazırlanın.</span><span class="sxs-lookup"><span data-stu-id="8097e-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="8097e-122">Uygulamanızı otomatik olarak almak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="8097e-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="8097e-123">Cihazınızı kiracınızla kaydedin.</span><span class="sxs-lookup"><span data-stu-id="8097e-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="8097e-124">Cihazınızın kaydı tamamladıktan sonra, uygulamayı cihazınızda almalısınız.</span><span class="sxs-lookup"><span data-stu-id="8097e-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="8097e-125">uygulamanızı hemen görmüyorsanız, **Ayarlar**  >  **hesapları**  >  **çalışıyor**' a gidin veya  >  *hesap* bilgilerinizi okul yapın ve yüklü uygulama durumu hakkındaki bilgileri görmek için aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="8097e-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="8097e-126">Şirket Portalı aracılığıyla uygulamalara nasıl ulaşırsanız:</span><span class="sxs-lookup"><span data-stu-id="8097e-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="8097e-127">**Başlat menüsünü** açın ve **Microsoft Store**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="8097e-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="8097e-128">**Şirket Portalı** arayın ve uygulamayı indirin.</span><span class="sxs-lookup"><span data-stu-id="8097e-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="8097e-129">Hesabınızda oturum açın.</span><span class="sxs-lookup"><span data-stu-id="8097e-129">Sign into your account.</span></span>
4. <span data-ttu-id="8097e-130">Almak istediğiniz uygulamayı seçin ve indirin.</span><span class="sxs-lookup"><span data-stu-id="8097e-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="8097e-131">[Şirket Portalı otomatik olarak yükleme](/mem/intune/apps/company-portal-app) ve [ıntune 'da uygulamaları dağıtma ve yönetme](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="8097e-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
