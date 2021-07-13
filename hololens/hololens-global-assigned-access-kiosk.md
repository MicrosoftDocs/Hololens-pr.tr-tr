---
title: Genel atanan erişim
description: Intune ve Windows yapılandırma Tasarımcısı ile genel olarak atanmış erişim Kiisleri için OMA-URI ' y i kullanma kılavuzumuzu kullanmaya başlayın.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: Hololens, Hololens 2, atanan erişim, bilgi noktası
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640432"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="2ea0d-104">Genel atanan erişim – bilgi noktası</span><span class="sxs-lookup"><span data-stu-id="2ea0d-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="2ea0d-105">bu özellik, sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırır, sistemde hiçbir kimlikle benzeşim yoktur ve cihazda oturum açan herkese uygulanır.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="2ea0d-106">bu özellik şu anda yalnızca Windows ınsider derlemeleriyle kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="2ea0d-107">bu özelliği HoloLens sürümlerde genel kullanıma açılmadan önce denemek istiyorsanız lütfen [Windows ınsider](hololens-insider.md) derlemeleri hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="2ea0d-108">Intune 'da genel atanan erişim nasıl kullanılır?</span><span class="sxs-lookup"><span data-stu-id="2ea0d-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="2ea0d-109">Lütfen "<!-" ile işaretlenmiş alanlara dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="2ea0d-110">Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="2ea0d-111">aşağıdaki gibi özel bir OMA urı cihaz yapılandırma profili oluşturun ve HoloLens cihaz grubuna uygulayın:</span><span class="sxs-lookup"><span data-stu-id="2ea0d-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="2ea0d-112">URI değeri:./Device/Vendor/MSFT/atandaccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="2ea0d-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2ea0d-113">![Genel atanan Access OMA-URI 'SI Intune 'da](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="2ea0d-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="2ea0d-114">Değer için aşağıdaki içeriği güncelleştirin ve yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="2ea0d-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="2ea0d-115">Windows yapılandırma tasarımcısında genel atanan erişim nasıl kullanılır?</span><span class="sxs-lookup"><span data-stu-id="2ea0d-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="2ea0d-116">XML dosyası olarak yukarıda bahsedilen XML blobu güncelleştirin ve kaydedin.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="2ea0d-117">[Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için sağlama paketini kullanma](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)bölümündeki adımları uygulayın, özellikle de "prov.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="2ea0d-118">paket, adım 2 – bilgi noktası yapılandırması XML dosyasını bir sağlama paketine ekleyin ve önceki adımda kaydedilen XML dosyasına başvurun.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="2ea0d-119">Herkesin herkes için geçerli olduğu bir yapılandırma oluşturabilir miyim ve ayrı yapılandırma 1 Azure AD hesabı veya Azure AD grubu için geçerlidir mi?</span><span class="sxs-lookup"><span data-stu-id="2ea0d-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="2ea0d-120">Evet, aşağıdaki örnek XML blobuna bakın.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="2ea0d-121">genel atanan erişim profili, oturum açmış kullanıcı için belirli bir tane bulunamadığında HoloLens uygulanır, bu nedenle oturum açan kullanıcı için varsayılan bilgi noktası modu yapılandırması olur.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="2ea0d-122">Kullanılacak XML blobuna bir örnek aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="2ea0d-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="2ea0d-123">Lütfen ile işaretlenmiş vurgulanan alanlarla haberdar olun `<!-` .</span><span class="sxs-lookup"><span data-stu-id="2ea0d-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="2ea0d-124">Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="2ea0d-125">Genel atanan erişim profilinden DeviceOwners hariç tutma</span><span class="sxs-lookup"><span data-stu-id="2ea0d-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="2ea0d-126">bu özellik, HoloLens üzerinde "[cihaz sahibi](security-adminless-os.md)" olarak kabul edilen bir kullanıcının genel olarak atanmış erişimden dışlanması için izin verir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="2ea0d-127">Bu özellikten yararlanabilmek için, birden çok uygulama bilgi noktası yapılandırması için XML blobu içinde, vurgulanan çizgilerin eklendiğinden emin olun:</span><span class="sxs-lookup"><span data-stu-id="2ea0d-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="2ea0d-128">Ek genel atanan erişim örnekleri</span><span class="sxs-lookup"><span data-stu-id="2ea0d-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="2ea0d-129">bu, herhangi bir kullanıcı oturum açtığında Ayarlar uygulaması, geri bildirim Hub 'ı ve Microsoft Edge birden çok uygulama bilgi noktası olacağını belirten, genel olarak atanmış bir erişim bilgi noktası örneğidir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="2ea0d-130">bu örnek, cihaz sahibini dışlayan, diğer Azure AD kullanıcıları oturum açtığında Ayarlar uygulaması, geri bildirim Hub 'ı ve Microsoft Edge birden çok uygulama bilgi noktası olan genel olarak atanmış bir erişim bilgi noktası örneğidir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="2ea0d-131">Bu bilgi noktası Ayrıca, bir ziyaretçi hesabı için bir ikincil bilgi noktası yapılandırması içerir ve bu, kilit ekranında herhangi bir kişi tarafından oturum açmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="2ea0d-132">Bir Kullanıcı ziyaretçi hesabına kaydolursa, yalnızca geri bildirim hub 'ı uygulamasına sahip bir çok uygulama bilgi noktası olur.</span><span class="sxs-lookup"><span data-stu-id="2ea0d-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
