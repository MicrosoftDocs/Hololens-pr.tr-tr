---
title: HoloLens için özel uygulamaları yönetme (1. Genel)
description: Cihaz portalı ve Visual Studio kullanarak özel holographic uygulamalarını HoloLens cihazlarına yüklemeyi, kaldırmayı ve dışarıdan yüklemeyi öğrenin.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379009"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="ca8c1-104">HoloLens için özel uygulamaları yönetme (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="ca8c1-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="ca8c1-105">HoloLens, Microsoft Store mevcut birçok uygulamayı ve özellikle HoloLens için oluşturulmuş yeni uygulamaları destekler.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="ca8c1-106">Bu makale özel holographic uygulamalarına odaklanır.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="ca8c1-107">Mağaza uygulamaları hakkında daha fazla bilgi için bkz. [Store ile uygulamaları yönetme](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ca8c1-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca8c1-108">HoloLens (1. gen) için, aynı zamanda HoloLens geliştirici sürümü olarak da adlandırılan aşağıdaki bilgiler oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="ca8c1-109">Bu tür dışarıdan yükleme uygulamaları cihaz portalı aracılığıyla ve uygulamaları Visual Studio aracılığıyla yüklerken normal daha sonra.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="ca8c1-110">Kurumsal dağıtımlar için, bu yöntemlerin her ikisinin de kullanıldığı geliştirici modunun etkinleştirilmesini önermeyiz.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="ca8c1-111">Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız lütfen [uygulama yönetimizi gözden geçirin: genel bakış](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca8c1-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="ca8c1-112">HoloLens 2 cihazları için uygulama yüklemesinin geliştirici yöntemini arıyorsanız lütfen şu adresine başvurun:</span><span class="sxs-lookup"><span data-stu-id="ca8c1-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="ca8c1-113">Cihaz Portalı: uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="ca8c1-113">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="ca8c1-114">Uygulamaları dağıtmak ve hatalarını ayıklamak için Visual Studio 'Yu kullanma</span><span class="sxs-lookup"><span data-stu-id="ca8c1-114">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="ca8c1-115">Özel uygulamaları yükleme</span><span class="sxs-lookup"><span data-stu-id="ca8c1-115">Install custom apps</span></span>

<span data-ttu-id="ca8c1-116">Cihaz portalını kullanarak ya da uygulamaları Visual Studio 'dan dağıtarak, kendi uygulamalarınızı HoloLens 'te yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="ca8c1-117">Cihaz portalı ile uygulama paketi yükleme</span><span class="sxs-lookup"><span data-stu-id="ca8c1-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="ca8c1-118">[Cihaz portalından](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) hedef HoloLens 'e bir bağlantı kurun.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-118">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="ca8c1-119">Sol gezinti bölmesinde **uygulamalar** sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="ca8c1-120">Uygulama **paketi** altında, uygulamanızla ilişkili. appx dosyasına gidin.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ca8c1-121">İlişkili tüm bağımlılık ve sertifika dosyalarına başvurduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="ca8c1-122">**Git**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ca8c1-123">![Microsoft HoloLens 'te Windows cihaz portalında uygulama formu yüklemesi](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="ca8c1-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="ca8c1-124">Microsoft Visual Studio 2015 ' den dağıtma</span><span class="sxs-lookup"><span data-stu-id="ca8c1-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="ca8c1-125">Uygulamanızın Visual Studio çözümünü (. sln dosyası) açın.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="ca8c1-126">Projenin **özelliklerini** açın.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="ca8c1-127">Aşağıdaki derleme yapılandırmasını seçin: **ana/x86/uzak makine**.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="ca8c1-128">**Uzak makineyi** seçtiğinizde:</span><span class="sxs-lookup"><span data-stu-id="ca8c1-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="ca8c1-129">Adresin, HoloLens sitenizin Wi-Fi IP adresine işaret ettiğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="ca8c1-130">Kimlik doğrulamasını **Evrensel (şifrelenmemiş protokol)** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="ca8c1-131">Çözümünüzü oluşturun.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-131">Build your solution.</span></span>

1. <span data-ttu-id="ca8c1-132">Uygulamayı geliştirme BILGISAYARıNıZDAN HoloLens 'e dağıtmak için **uzak makine**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="ca8c1-133">HoloLens üzerinde zaten var olan bir derlemeniz varsa, bu yeni sürümü yüklemek için **Evet** ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio 'da uygulamalar için uzak makine dağıtımı Microsoft HoloLens](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="ca8c1-135">Uygulama, HoloLens 'te yüklenir ve otomatik olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="ca8c1-136">Bir uygulamayı yükledikten sonra, bu dosyayı **tüm uygulamalar** listesinde (  >  **tüm uygulamaları** Başlat) görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="ca8c1-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
