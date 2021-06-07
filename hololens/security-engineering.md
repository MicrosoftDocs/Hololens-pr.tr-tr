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
ms.openlocfilehash: cecc556841033ee394f36915f4cae8839dad08df
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380196"
---
# <a name="security-engineering"></a><span data-ttu-id="a8ff8-104">Güvenlik mühendisliği</span><span class="sxs-lookup"><span data-stu-id="a8ff8-104">Security engineering</span></span>

<span data-ttu-id="a8ff8-105">Microsoft, şirketin mühendislik protokollerini iyileştirmeye, uyumluluğu ele alan ve müşteri güvenini sağlamaya ayrılmış çeşitli kaynaklara ve ekiplere sahip.</span><span class="sxs-lookup"><span data-stu-id="a8ff8-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="a8ff8-106">Microsoft'un güvenlik mühendisliği geliştirme uygulamaları hakkında daha fazla bilgi edinmek için bkz. [Güvenlik Geliştirme Yaşam Döngüsü (SDL)](https://www.microsoft.com/securityengineering/sdl).</span><span class="sxs-lookup"><span data-stu-id="a8ff8-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="a8ff8-107">Bu nedenle HoloLens 2, [Microsoft'un](https://privacy.microsoft.com/)Gizlilik ilkesinde daha fazla keşfedilen verilerin nasıl ve neden toplanmış ve kullanılmış olduğu konusunda müşterilere seçim yapma yetkisi verir.</span><span class="sxs-lookup"><span data-stu-id="a8ff8-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="a8ff8-108">[Microsoft Güvenlik Yanıt Merkezi (MSRC),](https://www.microsoft.com/msrc) etkili bir güvenlik açığı raporlama deneyimi ve güvenlik hatalarına etkili bir kategorilere ayırma ve yanıt sağlayan savunma topluluğunun bir parçası.</span><span class="sxs-lookup"><span data-stu-id="a8ff8-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="a8ff8-109">Güncelleştirmeler ve düzeltme ekleri</span><span class="sxs-lookup"><span data-stu-id="a8ff8-109">Updates and patches</span></span>

<span data-ttu-id="a8ff8-110">Güvenlik güncelleştirmeleri ve düzeltme ekleri her ayın ikinci Salı günü yayımlanıyor.</span><span class="sxs-lookup"><span data-stu-id="a8ff8-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="a8ff8-111">Microsoft tarafından bildirilen bir güvenlik açığına ilişkin sonraki adımları değerlendirmek için kullanılan ölçütleri anlamak için Microsoft Güvenlik Yanıt Merkezi Güvenlik Bakım Ölçütleri [sayfasına bakın.](https://www.microsoft.com/msrc/windows-security-servicing-criteria)</span><span class="sxs-lookup"><span data-stu-id="a8ff8-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="a8ff8-112">MDM aracılığıyla HoloLens 2 güncelleştirmelerini yönetme hakkında rehberlik için [bkz. HoloLens güncelleştirmelerini yönetme.](https://docs.microsoft.com/hololens/hololens-updates)</span><span class="sxs-lookup"><span data-stu-id="a8ff8-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates).</span></span> <span data-ttu-id="a8ff8-113">HoloLens 2 için işletim sistemi güncelleştirme temposs, sanal Windows 10; yılda iki güncelleştirme vardır, biri Spring'te, diğeri Fall'te 4 güncelleştirme 2 güncelleştirmeden biri olur.</span><span class="sxs-lookup"><span data-stu-id="a8ff8-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="a8ff8-114">Cihazların işletim sistemi güncelleştirmeleri sırasında nasıl güvenli hale getirildikleri hakkında daha fazla bilgi için bkz. [Durum ayrımı ve yalıtımı.](security-state-separation-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="a8ff8-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="a8ff8-115">IT yöneticileri İlke CSP -Güncelleştirme sayfasında güncelleştirme [ilkesi hakkında daha fazla bilgi edinmektedir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)</span><span class="sxs-lookup"><span data-stu-id="a8ff8-115">IT admins can learn more about update policy at [Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update).</span></span> 
