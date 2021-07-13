---
title: CSP'leri ve Cihaz Yönetimi genel bakış
description: Mobil uygulama ve sağlama paketlerini kullanarak CSP'leri, ilkeyi ve Cihaz Yönetimi yönetimini yapılandırmayı öğrenin.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640466"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="e7e1c-103">CSP'leri ve Cihaz Yönetimi genel bakış</span><span class="sxs-lookup"><span data-stu-id="e7e1c-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="e7e1c-104">It Administrators can define and implement policy settings on HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="e7e1c-105">Hangi yapılandırma ayarlarının dağıtım senaryosuna göre farklılık gösterir ve kurumsal cihazlar, EN geniş denetim yelpazesini IT'ye sunar.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="e7e1c-106">Bu Windows 10, Yapılandırma Hizmeti Sağlayıcıları (CSP) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="e7e1c-107">Bu ayarlar kayıt defteri anahtarları veya dosyalarıyla eşler.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="e7e1c-108">Bazı yapılandırma hizmeti sağlayıcıları WAP biçimini, bazıları SyncML'yi ve bazıları da ikisini de destekler.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="e7e1c-109">Cihaz yönetimi CSP'Windows 10 Holographic hakkında daha fazla bilgi için, tüm cihazlarda desteklenen [CSP'HoloLens bakın.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="e7e1c-110">AYRıCA, IT Yöneticileri cihazlarda İlke CSP'lerini yönetebilir, 2. ile desteklenen İlke [CSP'lerinin HoloLens bakın.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="e7e1c-111">Yapılandırma yöntemleri</span><span class="sxs-lookup"><span data-stu-id="e7e1c-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="e7e1c-112">MDM ile yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e7e1c-112">Configure with MDM</span></span>

<span data-ttu-id="e7e1c-113">CSP'ler ve İlkeler, MDM sistemine kayıtlı herhangi bir kişisel veya kurumsal cihazda kolayca yönetilebilir.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="e7e1c-114">Bir cihaz MDM çözümünüze kaydolarak cihaz yapılandırmalarını kullanarak bu cihazı veya cihaz kümelerini yönetebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="e7e1c-115">[MDM aracılığıyla cihazlarınızı HoloLens hakkında daha fazla bilgi edinebilirsiniz.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="e7e1c-116">Sağlama Paketleri ile yapılandırma</span><span class="sxs-lookup"><span data-stu-id="e7e1c-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="e7e1c-117">HoloLens 2, özel Sağlama Paketleri aracılığıyla 2 cihaz için HoloLens CSP yapılandırma kümesi ayarlamayı da destekler.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="e7e1c-118">Sağlama Paketleri genellikle MDM olmayan yönetilen cihazlar için kullanılır ve her cihaza el ile uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="e7e1c-119">HoloLens için [özel Sağlama Paketleri oluşturma hakkında bilgi HoloLens.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="e7e1c-120">Yapılandırmalar</span><span class="sxs-lookup"><span data-stu-id="e7e1c-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="e7e1c-121">Yaygın cihaz kısıtlamaları</span><span class="sxs-lookup"><span data-stu-id="e7e1c-121">Common device restrictions</span></span>

<span data-ttu-id="e7e1c-122">Bazı cihaz kısıtlamaları basit ve bir işlevselliği veya cihazla bağlantıyı devre dışı bırakmak kadar kolaydır.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="e7e1c-123">Bunlar hakkında daha fazla bilgi edinmek için yaygın [cihaz kısıtlamaları hakkında daha fazla bilgi edinebilirsiniz.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="e7e1c-124">Bilgi noktası modları</span><span class="sxs-lookup"><span data-stu-id="e7e1c-124">Kiosk modes</span></span>

<span data-ttu-id="e7e1c-125">Hangi kimliklerin varsayılan olarak hangi uygulamalara erişimi olduğunu kontrol etmek için Bilgi Noktası modunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="e7e1c-126">Bilgi noktası, tek bir uygulama veya birden çok uygulama kullanıcı arabirimi deneyimi için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="e7e1c-127">Bilgi noktası yapılandırmaları, cihazı kullanan herkesin tek bir uygulamasından farklı gruplar için farklı uygulama seçimlerinden farklı seçimlere kadar değişir.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="e7e1c-128">Bilgi noktası modu, "izin verilen uygulamaların" diğer uygulamaları başlatmasına engel olmaz ve hiçbir zaman amaçlanmaz.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="e7e1c-129">Bilgi noktası modları [ve bunları kullanma hakkında daha fazla bilgi edinebilirsiniz.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="e7e1c-130">Ayarlar Sayfa Görünürlüğü</span><span class="sxs-lookup"><span data-stu-id="e7e1c-130">Settings Page Visibility</span></span>

<span data-ttu-id="e7e1c-131">Hangi Ayarlar varsayılan olarak ayarlara erişimi olduğunu kontrol etmek için bir uygulama ilkesi kullanın.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="e7e1c-132">Bu ilkeyi Ayarlar uygulama yalnızca seçili sayfaları gösterecek veya tüm seçili sayfaları gizleyecek şekilde ya da yalıtabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="e7e1c-133">[Kullanılabilir sayfaları yapılandırma hakkında bilgi edinebilirsiniz.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="e7e1c-134">Bu özellik şu anda yalnızca [Insider Windows kullanılabilir.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="e7e1c-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="e7e1c-135">Bu özelliği kullanmayı niyetli cihazların 19041.1349+ derlemede olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="e7e1c-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="e7e1c-136">WDAC</span></span>

<span data-ttu-id="e7e1c-137">WdAC yapılandırmasını, sistemin bilgi noktası modunda olup olmadığına bakılmaksızın hangi uygulamaların/işlemlerin başlatılacaklarına/izin verilmeyeceklerine göre kontrol etmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="e7e1c-138">WDAC'ye genel bakış sayfamıza bakın.</span><span class="sxs-lookup"><span data-stu-id="e7e1c-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
