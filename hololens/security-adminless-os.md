---
title: Yönetici olmayan işletim sistemi güvenliği
description: HoloLens karma gerçeklik cihazlarından yönetici olmayan işletim sistemleri, cihaz sahipleri ve güvenlik hakkında bilgi edinebilirsiniz.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380197"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="78bad-104">Yönetici olmayan işletim sistemi</span><span class="sxs-lookup"><span data-stu-id="78bad-104">Admin-less operating system</span></span>

<span data-ttu-id="78bad-105">HoloLens 2, Yöneticiler grubu desteğini devre dışı bırakarak ve tüm üçüncü taraf UWP uygulama kodunu yalnızca AppContainer korumalı alanında standart kullanıcılar olarak yürütecek şekilde sınır kullanarak ayrıcalık yükseltme için yüzey alanı en aza indirger.</span><span class="sxs-lookup"><span data-stu-id="78bad-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="78bad-106">Bu koda yalnızca, tüm AppContainers tarafından erişilebilen kaynaklara ek olarak, uygulamada açıkça bildirilen özelliklerle korunan kaynaklara erişim izni veılır.</span><span class="sxs-lookup"><span data-stu-id="78bad-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="78bad-107">Bu uygulama özellikleri üç katmanlı sınıflandırma modeline sahip olmaya devam eder:</span><span class="sxs-lookup"><span data-stu-id="78bad-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="78bad-108">Genel</span><span class="sxs-lookup"><span data-stu-id="78bad-108">General</span></span>
  * <span data-ttu-id="78bad-109">Kısıtlı</span><span class="sxs-lookup"><span data-stu-id="78bad-109">Restricted</span></span>
  * <span data-ttu-id="78bad-110">Windows</span><span class="sxs-lookup"><span data-stu-id="78bad-110">Windows</span></span>

<span data-ttu-id="78bad-111">Windows bileşenleri, Sistem UWP'leri aracılığıyla AppContainer korumalı alandan da faydalanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78bad-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="78bad-112">Evrensel Windows Platformu (UWP) hakkında daha fazla bilgi edinmek için [UWP belgelerine bakın.](https://docs.microsoft.com/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="78bad-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="78bad-113">Ayrıca, daha fazla ayrıcalık azaltma ihtiyacı olan Windows bileşenleri (tarayıcı içerik sayfaları veya ayrıştırıcılar gibi) Tüm AppContainer'lar tarafından erişilebilen kaynak kümesine erişimi azaltan Less Privileged AppContainer (LPAC) korumalı alanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="78bad-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="78bad-114">Cihaz sahibi</span><span class="sxs-lookup"><span data-stu-id="78bad-114">Device owner</span></span>

<span data-ttu-id="78bad-115">Son olarak, cihazı bir kiracıya veya kullanıcı yönetimine birleştirme gibi belirli cihaz genelindeki işlemlerin yürütülmesine yalnızca "cihaz sahipleri" için izin verilir.</span><span class="sxs-lookup"><span data-stu-id="78bad-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="78bad-116">Bu grup, aşağıdaki adımlardan biri aracılığıyla cihaz kullanıcıları tarafından doldurulur:</span><span class="sxs-lookup"><span data-stu-id="78bad-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="78bad-117">Cihaza ilk kullanıcı her zaman Sahip olarak atanmıştır.</span><span class="sxs-lookup"><span data-stu-id="78bad-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="78bad-118">Azure AD Kullanıcıları için bu kuralın istisnası, cihazın Autopilot aracılığıyla Azure AD'ye katılmış veya gerçek olmayan bir kullanıcı kullanan toplu Azure AD kaydı olduğudur.</span><span class="sxs-lookup"><span data-stu-id="78bad-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="78bad-119">Bu durumda, cihazda oturum açması gereken ilk AAD kullanıcısı, cihazda "genel yönetici" veya "cihaz yöneticisi" rolü atanmadıkça cihaz sahibi Azure portal.</span><span class="sxs-lookup"><span data-stu-id="78bad-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="78bad-120">Daha fazla bilgi için aşağıdaki nota bakın.</span><span class="sxs-lookup"><span data-stu-id="78bad-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="78bad-121">Bir kullanıcı, cihaza başka bir Sahip tarafından Ayarlar UX'den Sahip olarak yükseltilene.</span><span class="sxs-lookup"><span data-stu-id="78bad-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="78bad-122">Cihaz sahibi artık kullanılamıyorsa (şirketten ayrılıyorsa) ve cihaz Azure AD'ye katılmışsa, Kiracı Yöneticisi cihaz sahibini şirket içinde yeni bir kullanıcı Azure portal.</span><span class="sxs-lookup"><span data-stu-id="78bad-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="78bad-123">Azure AD kiracılarının Genel Yöneticileri ve Cihaz Yöneticileri, önceki adımlardan herhangi birini gerektirmeden cihazda Sahip olarak açık olarak oturum açın.</span><span class="sxs-lookup"><span data-stu-id="78bad-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="78bad-124">IT yöneticileri, Hangi uygulamaların Gizlilik ilkeleri aracılığıyla [erişebilirsiniz yönetebilir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)</span><span class="sxs-lookup"><span data-stu-id="78bad-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="78bad-125">Azure AD'ye katılmış bir cihazda kimlerin cihaz sahibi olduğu hakkında daha fazla bilgi için "Yerel Yönetici [Atama"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) belgelerine bakın (ancak HoloLens'de yönetici mevcut değil, 'yerel yönetici' olarak 'cihaz sahibi' olarak okuyun).</span><span class="sxs-lookup"><span data-stu-id="78bad-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>