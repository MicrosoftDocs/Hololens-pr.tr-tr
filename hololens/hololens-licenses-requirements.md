---
title: Lisans gereksinimleri
description: Mobil cihaz yönetimi, HoloLens ve Uzaktan Yardım için ihtiyacınız olan tüm lisans gereksinimleri ve yönergeleriyle güncel tutun.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380233"
---
# <a name="license-requirements"></a><span data-ttu-id="ff140-103">Lisans gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="ff140-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="ff140-104">Mobil cihaz yönetimi (MDM) lisans Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="ff140-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="ff140-105">HoloLens cihazlarınızı yönetmeyi planlıyorsanız Azure AD 'ye ve MDM 'ye ihtiyacınız olacaktır.</span><span class="sxs-lookup"><span data-stu-id="ff140-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="ff140-106">Active Director (AD), HoloLens cihazlarını yönetmek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ff140-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="ff140-107">Intune dışında bir MDM kullanmayı planlıyorsanız [Azure Active Directory bir lisans](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) gerekir.</span><span class="sxs-lookup"><span data-stu-id="ff140-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="ff140-108">MDM 'niz olarak Intune kullanmayı planlıyorsanız, Intune lisanslarını içeren [paketler listesini](https://docs.microsoft.com/intune/fundamentals/licenses) okuyun.</span><span class="sxs-lookup"><span data-stu-id="ff140-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="ff140-109">**Azure AD 'nin bu paketlerin çoğunluğuna dahil edildiğini lütfen unutmayın.**</span><span class="sxs-lookup"><span data-stu-id="ff140-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="ff140-110">Senaryonuz ve ürünleriniz için gereken lisansları belirler</span><span class="sxs-lookup"><span data-stu-id="ff140-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="ff140-111">HoloLens (1. Genel) lisans gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="ff140-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="ff140-112">HoloLens (1. gen) cihazınızı Windows holographic for Business 'a yükseltmeniz gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="ff140-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="ff140-113">(Yükseltmeniz gerekip gerekmediğini öğrenmek için bkz. [HoloLens ticari özellikleri](holoLens-commercial-features.md#feature-comparison-between-editions) ).</span><span class="sxs-lookup"><span data-stu-id="ff140-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="ff140-114">Bu durumda, şunları yapmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="ff140-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="ff140-115">HoloLens Kurumsal Lisans XML dosyası alma</span><span class="sxs-lookup"><span data-stu-id="ff140-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="ff140-116">XML dosyasını HoloLens 'e uygulayın.</span><span class="sxs-lookup"><span data-stu-id="ff140-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="ff140-117">Bunu bir [sağlama paketi](hololens-provisioning.md) veya [Mobil Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) aracılığıyla yapabilirsiniz</span><span class="sxs-lookup"><span data-stu-id="ff140-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="ff140-118">Uzaktan Yardım lisans gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="ff140-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="ff140-119">Gerekli lisanslama ve cihaza sahip olduğunuzdan emin olun. Bu, [gereksinimler](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) belgelerini iade edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ff140-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="ff140-120">Uzaktan Yardım lisansı</span><span class="sxs-lookup"><span data-stu-id="ff140-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="ff140-121">Ya da bir [Uzaktan Yardım denemesi](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist) deneyin</span><span class="sxs-lookup"><span data-stu-id="ff140-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="ff140-122">Ekipler Freemıum/takımlar</span><span class="sxs-lookup"><span data-stu-id="ff140-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="ff140-123">Azure Active Directory (Azure AD) lisansı</span><span class="sxs-lookup"><span data-stu-id="ff140-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="ff140-124">**[Bu çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir.</span><span class="sxs-lookup"><span data-stu-id="ff140-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="ff140-125">Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için lütfen [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.</span><span class="sxs-lookup"><span data-stu-id="ff140-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="ff140-126">Kılavuzlar lisans gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="ff140-126">Guides License Requirements</span></span>

<span data-ttu-id="ff140-127">[Güncelleştirilmiş lisanslama ve cihaz gereksinimlerine](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)göz atın.</span><span class="sxs-lookup"><span data-stu-id="ff140-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="ff140-128">Azure Active Directory (Azure AD) lisansı</span><span class="sxs-lookup"><span data-stu-id="ff140-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="ff140-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="ff140-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="ff140-130">Guides</span><span class="sxs-lookup"><span data-stu-id="ff140-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
