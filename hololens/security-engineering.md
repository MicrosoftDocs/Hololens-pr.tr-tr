---
title: Güvenlik mühendisliği
description: Güvenlik mühendisliği
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: güvenlik, hololens, Güvenlik, mühendislik
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 1c043b721590e8245f694b3e4f6e5b6ce57f1ecf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639361"
---
# <a name="security-engineering"></a><span data-ttu-id="6a82c-104">Güvenlik mühendisliği</span><span class="sxs-lookup"><span data-stu-id="6a82c-104">Security engineering</span></span>

<span data-ttu-id="6a82c-105">Microsoft, şirketin mühendislik protokollerini iyileştirmeye, uyumluluğu ele alan ve müşteri güvenini sağlamaya ayrılmış çeşitli kaynaklara ve ekiplere sahip.</span><span class="sxs-lookup"><span data-stu-id="6a82c-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="6a82c-106">Microsoft'un güvenlik mühendisliği geliştirme uygulamaları hakkında daha fazla bilgi edinmek için bkz. [Güvenlik Geliştirme Yaşam Döngüsü (SDL)](https://www.microsoft.com/securityengineering/sdl).</span><span class="sxs-lookup"><span data-stu-id="6a82c-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="6a82c-107">Microsoft ve bu HoloLens 2, müşterilerin microsoft'un Gizlilik ilkesinde daha fazla keşfedilen verilerin nasıl ve neden toplanmış ve kullanıldıkları konusunda seçim [yapmalarını sağlar.](https://privacy.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="6a82c-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="6a82c-108">[Microsoft Güvenlik Yanıt Merkezi (MSRC),](https://www.microsoft.com/msrc) etkili bir güvenlik açığı raporlama deneyimi ve güvenlik hatalarına etkili bir kategorilere ayırma ve yanıt sağlayan savunma topluluğunun bir parçası.</span><span class="sxs-lookup"><span data-stu-id="6a82c-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="6a82c-109">Güncelleştirmeler ve düzeltme ekleri</span><span class="sxs-lookup"><span data-stu-id="6a82c-109">Updates and patches</span></span>

<span data-ttu-id="6a82c-110">Güvenlik güncelleştirmeleri ve düzeltme ekleri her ayın ikinci Salı günü yayımlanıyor.</span><span class="sxs-lookup"><span data-stu-id="6a82c-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="6a82c-111">Microsoft tarafından bildirilen bir güvenlik açığına ilişkin sonraki adımları değerlendirmek için kullanılan ölçütleri anlamak için Microsoft Güvenlik Yanıt Merkezi Güvenlik Bakım Ölçütleri [sayfasına bakın.](https://www.microsoft.com/msrc/windows-security-servicing-criteria)</span><span class="sxs-lookup"><span data-stu-id="6a82c-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="6a82c-112">MDM aracılığıyla HoloLens 2 güncelleştirmelerini yönetme hakkında rehberlik için bkz. MDM [güncelleştirmelerini HoloLens yönetme.](hololens-updates.md)</span><span class="sxs-lookup"><span data-stu-id="6a82c-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](hololens-updates.md).</span></span> <span data-ttu-id="6a82c-113">HoloLens 2 için işletim sistemi güncelleştirme tempos, Windows 10; yılda iki güncelleştirme vardır, biri Spring'te, diğeri Fall'te 4 güncelleştirme 2 güncelleştirmeden biri olur.</span><span class="sxs-lookup"><span data-stu-id="6a82c-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="6a82c-114">Cihazların işletim sistemi güncelleştirmeleri sırasında nasıl güvenli hale getirildikleri hakkında daha fazla bilgi için bkz. [Durum ayrımı ve yalıtımı.](security-state-separation-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="6a82c-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="6a82c-115">IT yöneticileri, güncelleştirme ilkesi hakkında daha fazla bilgi edinmek için İlke [CSP - Güncelleştirme sayfasından bilgi edinmektedir.](/windows/client-management/mdm/policy-csp-update)</span><span class="sxs-lookup"><span data-stu-id="6a82c-115">IT admins can learn more about update policy at [Policy CSP - Update](/windows/client-management/mdm/policy-csp-update).</span></span> 
