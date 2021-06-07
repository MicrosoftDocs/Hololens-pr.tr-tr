---
title: Sağlama Paketi
description: HoloLens cihazları için uygulama paketleme, sağlama, dağıtım ve kurumsal uygulama dağıtımı hakkında bilgi edinebilirsiniz.
keywords: uygulama, uygulama dağıtımı, kurumsal uygulama dağıtımı, sağlama
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379034"
---
# <a name="provisioning-package"></a><span data-ttu-id="2bd7c-104">Sağlama Paketi</span><span class="sxs-lookup"><span data-stu-id="2bd7c-104">Provisioning Package</span></span>

<span data-ttu-id="2bd7c-105">Paketleri sağlama, uç nokta yönetimine erişimi olmayan bir ortamda cihazları hazırlamak ve yapılandırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="2bd7c-106">Ayrıca kullanıcı kimliği, kayıt durumu, İlk Kullanım Deneyimi (OOBE) sırasında veya kurulum sırasında bir sağlama paketi uygulanarak bir cihaza [dağıtılabilir.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2bd7c-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="2bd7c-107">Sağlama Paketleri ile ilgili dikkat edilmesi gerekenler:</span><span class="sxs-lookup"><span data-stu-id="2bd7c-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="2bd7c-108">Genel Olmayan uygulamalar</span><span class="sxs-lookup"><span data-stu-id="2bd7c-108">Non-Public apps</span></span>
* <span data-ttu-id="2bd7c-109">Yalnızca USB yan yüklemesi</span><span class="sxs-lookup"><span data-stu-id="2bd7c-109">USB side-load only</span></span>
* <span data-ttu-id="2bd7c-110">Otomatik güncelleştirme yok (PPKG'ler aracılığıyla el ile güncelleştirme gerektirir)</span><span class="sxs-lookup"><span data-stu-id="2bd7c-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="2bd7c-111">Sağlama paketi aracılığıyla yüklenmiş uygulamalar, yerel makine mağazasındaki bir sertifika tarafından imzalanacak.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="2bd7c-112">Sağlama paketleri yalnızca cihaz (yerel makine) deposuna sertifika yükleyebilir, bu nedenle aynı sağlama paketi aracılığıyla bir uygulama ve sertifika yükleyebilir.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="2bd7c-113">Sertifikanızı MDM'den dağıtıyor veya Sertifika [](certificate-manager.md)Yöneticisi aracılığıyla yüklüyorsanız, bu şekilde yüklü uygulamaları imzalamak için sertifikayı yerel makine deposuna dağıtın.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="2bd7c-114">HoloLens cihazları için Sağlama Paketi oluşturmanın temellerini öğrenmek için [HoloLens Sağlama'ya ziyaret edin.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="2bd7c-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="2bd7c-115">Bir uygulamayı dağıtmak için gelişmiş sağlama ile başlamalısiniz.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="2bd7c-116">HoloLens 'in (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).**</span><span class="sxs-lookup"><span data-stu-id="2bd7c-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="2bd7c-117">HoloLens (1. nesil) cihazları yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="2bd7c-118">Kurulum</span><span class="sxs-lookup"><span data-stu-id="2bd7c-118">Setup</span></span>

<span data-ttu-id="2bd7c-119">[Windows Yapılandırma Tasarımcısı'nın](https://www.microsoft.com/store/productId/9NBLGGH4TX22) içinde dört adımı izleyin.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="2bd7c-120">ApplicationManagement/AllowAllTrustedApps'i "Evet" olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="2bd7c-121">Bkz. [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="2bd7c-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="2bd7c-122">**UniversalAppInstall**  >  **UserContextAppLicense'e** gidin ve **PackageFamilyName girin.**</span><span class="sxs-lookup"><span data-stu-id="2bd7c-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="2bd7c-123">Bkz. [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="2bd7c-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="2bd7c-124">Ayrıca bkz. [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="2bd7c-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="2bd7c-125">Bu Cihaz Portalı önceden yüklemiş olduğunuz bir cihazda kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="2bd7c-126">Uygulamalar sayfasını ziyaret edin ve PackageRelativeID satırına ve "!" **PackageFamilyName dosyanız mı?**</span><span class="sxs-lookup"><span data-stu-id="2bd7c-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="2bd7c-127">Ardından ApplicationFile yeni bir bölümünüz **olduğunu göreceğiz.**</span><span class="sxs-lookup"><span data-stu-id="2bd7c-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="2bd7c-128">Appx paketinizi karşıya yüklemek için bu alanı kullanın.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="2bd7c-129">Uygulama satın aldığınıza veya kendi LOB uygulamanızı 7.000'e yüklediğinize bağlı olarak, lisans dosyasını veya güvenlik sertifikasını karşıya yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="2bd7c-130">Lisans dosyası için: **UniversalAppInstall**  >  **UserContextAppLicence'a** gidin, lisansınızı konumunu bulun ve yükleyin.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="2bd7c-131">Güvenlik dosyası için Sertifikalar'a **gidin** ve .appx paketinizin yanı sıra yüklemek istediğiniz sertifikayı seçin.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="2bd7c-132">Projenizi güvenli bir konuma kaydetmeyi emin olun.</span><span class="sxs-lookup"><span data-stu-id="2bd7c-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="2bd7c-133">Ardından **Bunu** Sağlama Paketi **olarak dışarı aktarın.**</span><span class="sxs-lookup"><span data-stu-id="2bd7c-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="2bd7c-134">Ayrıca bkz. [Sağlama paketinizi HoloLens'e uygulama.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2bd7c-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
