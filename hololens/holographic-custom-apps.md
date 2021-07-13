---
title: HoloLens için özel uygulamaları yönetme (1. genel)
description: cihaz portalını ve Visual Studio kullanarak HoloLens cihazlarda özel holographic uygulamalarını yüklemeyi, kaldırmayı ve dışarıdan yüklemeyi öğrenin.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: Hololens, dışarıdan yükleme, dışarıdan yükleme, dışarıdan yükleme, mağaza, UWP, uygulama, yükleme
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635917"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="1db9a-104">HoloLens için özel uygulamaları yönetme (1. genel)</span><span class="sxs-lookup"><span data-stu-id="1db9a-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="1db9a-105">HoloLens, Microsoft Store birçok mevcut uygulamayı ve özellikle HoloLens için oluşturulan yeni uygulamaları destekler.</span><span class="sxs-lookup"><span data-stu-id="1db9a-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="1db9a-106">Bu makale özel holographic uygulamalarına odaklanır.</span><span class="sxs-lookup"><span data-stu-id="1db9a-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="1db9a-107">Mağaza uygulamaları hakkında daha fazla bilgi için bkz. [Store ile uygulamaları yönetme](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="1db9a-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1db9a-108">HoloLens geliştirici sürümü olarak da adlandırılan HoloLens (1. gen) için aşağıdaki bilgiler oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="1db9a-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="1db9a-109">bu tür dışarıdan yükleme uygulamaları cihaz portalı aracılığıyla ve uygulamaları Visual Studio aracılığıyla yüklerken daha fazla yer.</span><span class="sxs-lookup"><span data-stu-id="1db9a-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="1db9a-110">Kurumsal dağıtımlar için, bu yöntemlerin her ikisinin de kullanıldığı geliştirici modunun etkinleştirilmesini önermeyiz.</span><span class="sxs-lookup"><span data-stu-id="1db9a-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="1db9a-111">Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız lütfen [uygulama yönetimizi gözden geçirin: genel bakış](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1db9a-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="1db9a-112">HoloLens 2 cihazları için uygulama yüklemesinin geliştirici yöntemini arıyorsanız lütfen şu adresine başvurun:</span><span class="sxs-lookup"><span data-stu-id="1db9a-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="1db9a-113">Cihaz Portalı: uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="1db9a-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="1db9a-114">uygulamaları dağıtmak ve hata ayıklamak için Visual Studio kullanma</span><span class="sxs-lookup"><span data-stu-id="1db9a-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="1db9a-115">Özel uygulamaları yükleme</span><span class="sxs-lookup"><span data-stu-id="1db9a-115">Install custom apps</span></span>

<span data-ttu-id="1db9a-116">cihaz portalını kullanarak veya uygulamaları Visual Studio dağıtarak, kendi uygulamalarınızı HoloLens yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1db9a-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="1db9a-117">Cihaz portalı ile uygulama paketi yükleme</span><span class="sxs-lookup"><span data-stu-id="1db9a-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="1db9a-118">[Cihaz portalından](/windows/mixed-reality/using-the-windows-device-portal) hedef HoloLens bir bağlantı kurun.</span><span class="sxs-lookup"><span data-stu-id="1db9a-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="1db9a-119">Sol gezinti bölmesinde **uygulamalar** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="1db9a-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="1db9a-120">Uygulama **paketi** altında, uygulamanızla ilişkili. appx dosyasına gidin.</span><span class="sxs-lookup"><span data-stu-id="1db9a-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1db9a-121">İlişkili tüm bağımlılık ve sertifika dosyalarına başvurduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="1db9a-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="1db9a-122">**Git**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="1db9a-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1db9a-123">![uygulama formunu Windows cihaz portalında Microsoft HoloLens üzerine yükler](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="1db9a-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="1db9a-124">Microsoft Visual Studio 2015 ' den dağıtma</span><span class="sxs-lookup"><span data-stu-id="1db9a-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="1db9a-125">uygulamanızın Visual Studio çözümünü (. sln dosyası) açın.</span><span class="sxs-lookup"><span data-stu-id="1db9a-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="1db9a-126">Projenin **özelliklerini** açın.</span><span class="sxs-lookup"><span data-stu-id="1db9a-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="1db9a-127">Aşağıdaki derleme yapılandırmasını seçin: **ana/x86/uzak makine**.</span><span class="sxs-lookup"><span data-stu-id="1db9a-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="1db9a-128">**Uzak makineyi** seçtiğinizde:</span><span class="sxs-lookup"><span data-stu-id="1db9a-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="1db9a-129">Adresin, HoloLens Wi-Fi IP adresine işaret ettiğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="1db9a-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="1db9a-130">Kimlik doğrulamasını **Evrensel (şifrelenmemiş protokol)** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1db9a-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="1db9a-131">Çözümünüzü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1db9a-131">Build your solution.</span></span>

1. <span data-ttu-id="1db9a-132">uygulamayı geliştirme bilgisayarınızdan HoloLens dağıtmak için **uzak makine**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="1db9a-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="1db9a-133">HoloLens zaten var olan bir derlemeniz varsa, bu yeni sürümü yüklemek için **evet** ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="1db9a-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio Microsoft HoloLens uygulamalar için uzak makine dağıtımı](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="1db9a-135">Uygulama, HoloLens yükleyip otomatik olarak başlatılacak.</span><span class="sxs-lookup"><span data-stu-id="1db9a-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="1db9a-136">Bir uygulamayı yükledikten sonra, bu dosyayı **tüm uygulamalar** listesinde (  >  **tüm uygulamaları** Başlat) görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="1db9a-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
