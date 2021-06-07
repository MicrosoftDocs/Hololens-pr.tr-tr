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
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380234"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="24288-104">Genel atanan erişim – bilgi noktası</span><span class="sxs-lookup"><span data-stu-id="24288-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="24288-105">Bu özellik, HoloLens 2 cihazını, sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için yapılandırır, sistemde herhangi bir kimlikle hiçbir benzeşim yoktur ve cihazda oturum açan herkese uygulanır.</span><span class="sxs-lookup"><span data-stu-id="24288-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="24288-106">Bu özellik şu anda yalnızca Windows Insider Derlemeleriyle kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="24288-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="24288-107">Bu özelliği, HoloLens sürümlerinde genel kullanıma açılmadan önce denemek istiyorsanız lütfen [Windows Insider](hololens-insider.md) derlemeleri hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="24288-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="24288-108">Intune 'da genel atanan erişim nasıl kullanılır?</span><span class="sxs-lookup"><span data-stu-id="24288-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="24288-109">Lütfen "<!-" ile işaretlenmiş alanlara dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="24288-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="24288-110">Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="24288-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="24288-111">Aşağıdaki gibi özel bir OMA URI cihaz yapılandırma profili oluşturun ve bunu HoloLens cihaz grubuna uygulayın:</span><span class="sxs-lookup"><span data-stu-id="24288-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="24288-112">URI değeri:./Device/Vendor/MSFT/atandaccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="24288-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="24288-113">![Genel atanan Access OMA-URI 'SI Intune 'da](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="24288-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="24288-114">Değer için aşağıdaki içeriği güncelleştirin ve yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="24288-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="24288-115">Windows yapılandırma Tasarımcısı 'nda genel atanan erişim nasıl kullanılır?</span><span class="sxs-lookup"><span data-stu-id="24288-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="24288-116">XML dosyası olarak yukarıda bahsedilen XML blobu güncelleştirin ve kaydedin.</span><span class="sxs-lookup"><span data-stu-id="24288-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="24288-117">[Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için sağlama paketini kullanma](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)bölümündeki adımları uygulayın, özellikle de "prov.</span><span class="sxs-lookup"><span data-stu-id="24288-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="24288-118">paket, adım 2 – bilgi noktası yapılandırması XML dosyasını bir sağlama paketine ekleyin ve önceki adımda kaydedilen XML dosyasına başvurun.</span><span class="sxs-lookup"><span data-stu-id="24288-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="24288-119">Herkesin herkes için geçerli olduğu bir yapılandırma oluşturabilir miyim ve ayrı yapılandırma 1 Azure AD hesabı veya Azure AD grubu için geçerlidir mi?</span><span class="sxs-lookup"><span data-stu-id="24288-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="24288-120">Evet, aşağıdaki örnek XML blobuna bakın.</span><span class="sxs-lookup"><span data-stu-id="24288-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="24288-121">Genel atanan erişim profili, oturum açan kullanıcı için belirli bir tane bulunamadığında HoloLens 'te uygulanır, bu nedenle oturum açan kullanıcı için varsayılan bilgi noktası modu yapılandırması vardır.</span><span class="sxs-lookup"><span data-stu-id="24288-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="24288-122">Kullanılacak XML blobuna bir örnek aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="24288-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="24288-123">Lütfen ile işaretlenmiş vurgulanan alanlarla haberdar olun `<!-` .</span><span class="sxs-lookup"><span data-stu-id="24288-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="24288-124">Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="24288-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="24288-125">Genel atanan erişim profilinden DeviceOwners hariç tutma</span><span class="sxs-lookup"><span data-stu-id="24288-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="24288-126">Bu özellik, HoloLens üzerinde "[cihaz sahibi](security-adminless-os.md)" olarak kabul edilen bir kullanıcının genel atanan erişimden dışlanması için izin verir.</span><span class="sxs-lookup"><span data-stu-id="24288-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="24288-127">Bu özellikten yararlanabilmek için, birden çok uygulama bilgi noktası yapılandırması için XML blobu içinde, vurgulanan çizgilerin eklendiğinden emin olun:</span><span class="sxs-lookup"><span data-stu-id="24288-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="24288-128">Ek genel atanan erişim örnekleri</span><span class="sxs-lookup"><span data-stu-id="24288-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="24288-129">Bu, herhangi bir Kullanıcı oturum açtığında, ayarlar uygulaması, geri bildirim merkezi ve Microsoft Edge ile birden çok uygulama bilgi noktası olacağını belirten, genel olarak atanmış bir erişim bilgi noktası örneğidir.</span><span class="sxs-lookup"><span data-stu-id="24288-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="24288-130">Bu örnek, cihaz sahibini dışlayan, diğer Azure AD kullanıcıları oturum açtığında, ayarlar uygulaması, geri bildirim hub 'ı ve Microsoft Edge ile birden çok uygulama bilgi noktası olan genel olarak atanmış bir erişim bilgi noktası örneğidir.</span><span class="sxs-lookup"><span data-stu-id="24288-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="24288-131">Bu bilgi noktası Ayrıca, bir ziyaretçi hesabı için bir ikincil bilgi noktası yapılandırması içerir ve bu, kilit ekranında herhangi bir kişi tarafından oturum açmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="24288-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="24288-132">Bir Kullanıcı ziyaretçi hesabına kaydolursa, yalnızca geri bildirim hub 'ı uygulamasına sahip bir çok uygulama bilgi noktası olur.</span><span class="sxs-lookup"><span data-stu-id="24288-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
