---
title: CSP 'Leri ve cihaz yönetimine genel bakış
description: Mobil cihaz yönetimi ve sağlama paketleri kullanarak CSP 'Leri, ilkeyi ve cihaz yönetimini yapılandırmayı öğrenin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379103"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="db3df-103">CSP 'Leri ve cihaz yönetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="db3df-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="db3df-104">BT yöneticileri, HoloLens 2 ' de ilke ayarlarını tanımlayabilir ve uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="db3df-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="db3df-105">Kullandığınız yapılandırma ayarları dağıtım senaryosuna göre farklılık gösterir ve şirket cihazları bu en geniş denetim aralığını sunar.</span><span class="sxs-lookup"><span data-stu-id="db3df-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="db3df-106">Windows 10 ' da yapılandırma hizmeti sağlayıcıları (CSP), cihazdaki yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="db3df-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="db3df-107">Bu ayarlar kayıt defteri anahtarları veya dosyalarıyla eşlenir.</span><span class="sxs-lookup"><span data-stu-id="db3df-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="db3df-108">Bazı yapılandırma hizmeti sağlayıcıları WAP biçimini, bazı destek SyncML ' i ve her ikisini de destekler.</span><span class="sxs-lookup"><span data-stu-id="db3df-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="db3df-109">Windows 10 holographic cihaz yönetimi CSP 'Leri hakkında daha fazla bilgi için, [HoloLens cihazlarında desteklenen CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)'lerin tam listesine bakın.</span><span class="sxs-lookup"><span data-stu-id="db3df-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="db3df-110">BT yöneticileri cihazlarda Ilke CSP 'sini de yönetebilir, [HoloLens 2 tarafından desteklenen Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)'lerin tam listesine bakın.</span><span class="sxs-lookup"><span data-stu-id="db3df-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="db3df-111">Yapılandırma yöntemleri</span><span class="sxs-lookup"><span data-stu-id="db3df-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="db3df-112">MDM ile yapılandırma</span><span class="sxs-lookup"><span data-stu-id="db3df-112">Configure with MDM</span></span>

<span data-ttu-id="db3df-113">CSP 'Ler ve Ilkeler, bir MDM sistemine kayıtlı tüm kişisel veya şirket cihazlarından kolayca yönetilebilir.</span><span class="sxs-lookup"><span data-stu-id="db3df-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="db3df-114">Bir cihaz MDM çözümünüze kaydedildikten sonra bu cihazı veya cihaz yapılandırması kullanarak cihaz kümesini yönetebileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="db3df-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="db3df-115">[HoloLens CIHAZLARıNıZı MDM aracılığıyla yönetme](hololens-mdm-configure.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="db3df-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="db3df-116">Sağlama paketleriyle yapılandırma</span><span class="sxs-lookup"><span data-stu-id="db3df-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="db3df-117">HoloLens 2 Ayrıca, özel sağlama paketleri aracılığıyla HoloLens 2 cihazları için sınırlı sayıda CSP yapılandırması ayarlamayı destekler.</span><span class="sxs-lookup"><span data-stu-id="db3df-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="db3df-118">Sağlama paketleri genellikle MDM olmayan yönetilen cihazlar için yararlanılabilir ve her cihaza el ile uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db3df-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="db3df-119">[HoloLens için özel sağlama paketleri](https://docs.microsoft.com/hololens/hololens-provisioning)oluşturma hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="db3df-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="db3df-120">Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="db3df-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="db3df-121">Ortak cihaz kısıtlamaları</span><span class="sxs-lookup"><span data-stu-id="db3df-121">Common device restrictions</span></span>

<span data-ttu-id="db3df-122">Bazı cihaz kısıtlamaları basittir ve bir işlevi veya cihazla bağlantıyı devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="db3df-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="db3df-123">Bu konuda daha fazla bilgi edinmek için [ortak cihaz kısıtlamaları](hololens-common-device-restrictions.md) hakkında daha fazla bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="db3df-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="db3df-124">Bilgi noktası modları</span><span class="sxs-lookup"><span data-stu-id="db3df-124">Kiosk modes</span></span>

<span data-ttu-id="db3df-125">Hangi kimliklerin varsayılan olarak hangilerinin erişebileceğini denetlemek için bilgi noktası modunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="db3df-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="db3df-126">Kiosks, tek bir uygulama veya birden çok uygulama kullanıcı arabirimi deneyimi için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db3df-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="db3df-127">Bilgi noktası yapılandırmalarının, cihazı kullanan herkes için tek bir uygulamadan farklı gruplar için farklı uygulama seçimleriyle aralığı vardır.</span><span class="sxs-lookup"><span data-stu-id="db3df-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="db3df-128">Bilgi noktası modu, "izin verilen uygulamaların" diğer uygulamaları başlatmasını engellemez ve hiçbir zaman amaçlanmamıştır.</span><span class="sxs-lookup"><span data-stu-id="db3df-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="db3df-129">Bilgi [noktası modlarını ve bunların nasıl kullanılacağını okuyarak](hololens-kiosk.md)daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="db3df-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="db3df-130">Ayarlar sayfası görünürlüğü</span><span class="sxs-lookup"><span data-stu-id="db3df-130">Settings Page Visibility</span></span>

<span data-ttu-id="db3df-131">Ayarlara hangi kimliklerin varsayılan olarak erişebileceğini denetlemek için ayarlar uygulama ilkesi ' ni kullanın.</span><span class="sxs-lookup"><span data-stu-id="db3df-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="db3df-132">Bu ilkeyi kullanarak, ayarlar uygulaması yalnızca seçim sayfalarını gösterecek şekilde veya seçili tüm sayfaları gizleyecek şekilde yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="db3df-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="db3df-133">[Kullanılabilir sayfaları yapılandırma hakkında bilgi edinin](settings-uri-list.md).</span><span class="sxs-lookup"><span data-stu-id="db3df-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="db3df-134">Bu özellik şu anda yalnızca [Windows Insider Derlemeleriyle](hololens-insider.md)kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db3df-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="db3df-135">İçin bu özelliği kullanmayı düşündüğünüz cihazların Build 19041.1349 + konumunda olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="db3df-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="db3df-136">Ung</span><span class="sxs-lookup"><span data-stu-id="db3df-136">WDAC</span></span>

<span data-ttu-id="db3df-137">Sistemin bilgi noktası modunda olup olmadığı ne olursa olsun, hangi uygulamaların/işlemlerin çalıştırılmasına izin verildiğini/izin verileceğini denetlemek için WDAC yapılandırmasını kullanın.</span><span class="sxs-lookup"><span data-stu-id="db3df-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="db3df-138">WDAC için genel bakış bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="db3df-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
