---
title: Yönetici olmayan işletim sistemi güvenliği
description: Karma gerçeklik cihazları için yönetici olmayan işletim sistemleri, cihaz sahipleri ve HoloLens hakkında bilgi edinebilirsiniz.
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
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639412"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="7fbbd-104">Yönetici olmayan işletim sistemi</span><span class="sxs-lookup"><span data-stu-id="7fbbd-104">Admin-less operating system</span></span>

<span data-ttu-id="7fbbd-105">HoloLens 2, Yöneticiler grubu desteğini devre dışı bırakarak ve tüm üçüncü taraf UWP uygulama kodunu yalnızca AppContainer korumalı alanında standart kullanıcılar olarak yürütecek şekilde sınırlandırarak ayrıcalık yükseltme için yüzey alanı en aza indirger.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="7fbbd-106">Bu koda yalnızca, tüm AppContainers tarafından erişilebilen kaynaklara ek olarak, uygulamada açıkça bildirilen özelliklerle korunan kaynaklara erişim izni veılır.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="7fbbd-107">Bu uygulama özellikleri üç katmanlı sınıflandırma modeline sahip olmaya devam eder:</span><span class="sxs-lookup"><span data-stu-id="7fbbd-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="7fbbd-108">Genel</span><span class="sxs-lookup"><span data-stu-id="7fbbd-108">General</span></span>
  * <span data-ttu-id="7fbbd-109">Kısıtlı</span><span class="sxs-lookup"><span data-stu-id="7fbbd-109">Restricted</span></span>
  * <span data-ttu-id="7fbbd-110">Windows</span><span class="sxs-lookup"><span data-stu-id="7fbbd-110">Windows</span></span>

<span data-ttu-id="7fbbd-111">Windows bileşenleri, Sistem UWP'leri aracılığıyla AppContainer korumalı alandan da faydalanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="7fbbd-112">Universal Windows Platform (UWP) hakkında daha fazla bilgi edinmek için [UWP belgelerine bakın.](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="7fbbd-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="7fbbd-113">Ayrıca, Windows azaltma ihtiyaçları olan tüm bileşenler (tarayıcı içerik sayfaları veya ayrıştırıcılar gibi) Tüm AppContainer'lar tarafından erişilebilen kaynak kümesine erişimi azaltan Less Privileged AppContainer (LPAC) korumalı alanı kullanır.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="7fbbd-114">Cihaz sahibi</span><span class="sxs-lookup"><span data-stu-id="7fbbd-114">Device owner</span></span>

<span data-ttu-id="7fbbd-115">Son olarak, cihazı bir kiracıya veya kullanıcı yönetimine birleştirme gibi belirli cihaz genelindeki işlemlerin yürütülmesine yalnızca "cihaz sahipleri" için izin verilir.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="7fbbd-116">Bu grup, aşağıdaki adımlardan biri aracılığıyla cihaz kullanıcıları tarafından doldurulur:</span><span class="sxs-lookup"><span data-stu-id="7fbbd-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="7fbbd-117">Cihaza ilk kullanıcı her zaman Sahip olarak atanmıştır.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="7fbbd-118">Azure AD Kullanıcıları için bu kuralın istisnası, cihazın Autopilot aracılığıyla Azure AD'ye katılmış veya gerçek olmayan bir kullanıcı kullanan toplu Azure AD kaydı olduğudur.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="7fbbd-119">Bu durumda, cihazda oturum açması gereken ilk AAD kullanıcısı, cihazda "genel yönetici" veya "cihaz yöneticisi" rolü atanmadıkça cihaz sahibi Azure portal.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="7fbbd-120">Daha fazla bilgi için aşağıdaki nota bakın.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="7fbbd-121">Bir kullanıcı, cihazda başka bir Sahip tarafından Ayarlar kullanıcı deneyiminden Sahip olarak yükseltildi.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="7fbbd-122">Cihaz sahibi artık kullanılamıyorsa (şirketten ayrılıyorsa) ve cihaz Azure AD'ye katılmışsa, Kiracı Yöneticisi cihaz sahibini şirket içinde yeni bir kullanıcı Azure portal.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="7fbbd-123">Azure AD kiracılarının Genel Yöneticileri ve Cihaz Yöneticileri, önceki adımlardan herhangi birini gerektirmeden cihazda Sahip olarak açık olarak oturum açın.</span><span class="sxs-lookup"><span data-stu-id="7fbbd-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="7fbbd-124">IT yöneticileri, Hangi uygulamaların Gizlilik ilkeleri aracılığıyla [erişebilirsiniz yönetebilir.](/windows/client-management/mdm/policy-csp-privacy)</span><span class="sxs-lookup"><span data-stu-id="7fbbd-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="7fbbd-125">Azure AD'ye katılmış bir cihazda kimlerin cihaz sahibi olduğu hakkında daha fazla bilgi için "Yerel Yönetici [Atama"](/azure/active-directory/devices/assign-local-admin) belgelerine bakın (ancak 'yerel yönetici' olarak 'cihaz sahibi' olarak okuyun çünkü yönetici HoloLens).</span><span class="sxs-lookup"><span data-stu-id="7fbbd-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>