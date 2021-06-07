---
title: HoloLens güvenlik mimarisi
description: Güvenlik mimarisi
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Security, Hololens, Hololens 2, hololens2 Security, Security Overview, güvenlik mimarisi, mimari, Hololens 2 mimarisi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380183"
---
# <a name="security-overview-and-architecture"></a><span data-ttu-id="e2994-104">Güvenliğe genel bakış ve mimari</span><span class="sxs-lookup"><span data-stu-id="e2994-104">Security overview and architecture</span></span>

<span data-ttu-id="e2994-105">HoloLens 2 güvenlik mimarisi, sıfırdan küçük bir saldırı yüzeyi oluşturulurken eski güvenlik sorunlarından ücretsiz olarak tasarlanıp oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="e2994-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="e2994-106">Bu yeni ve yenilikçi mimari, güvenli depolama konumları ve gelişmiş güvenlik öğeleri sunarak, olası tehditler ve güvenlik açıklarına karşı koruma işletim sistemleri yapabilen mekanizmalar sağlar.</span><span class="sxs-lookup"><span data-stu-id="e2994-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="e2994-107">HoloLens 2, en iyi deneyimi sunmak için donanım, yazılım, ağ ve Hizmetleri birleştirerek uçtan uca güvenlik sağlar.</span><span class="sxs-lookup"><span data-stu-id="e2994-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="e2994-108">HoloLens 2 sayesinde, güvenlik özelliklerinin büyük bir bölümü otomatik olarak açıktır ve işletim sistemini doğru şekilde ayarlamak ve yapılandırmak için gereken çabayı en aza indirir.</span><span class="sxs-lookup"><span data-stu-id="e2994-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="e2994-109">Windows HoloLens 2 ve işletim sistemi mimarisi şu yenilikçi güvenlik özelliklerini sunmaktadır:</span><span class="sxs-lookup"><span data-stu-id="e2994-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="e2994-110">**Durum ayrımı ve yalıtım**: Bu yeni mimari, Hololens 2 işletim sisteminin kritik bölümlerini, çekirdek işletim sisteminin güvenilir bir duruma önyüklemesinde gerekli olanlar gibi değişiklikten korur.</span><span class="sxs-lookup"><span data-stu-id="e2994-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="e2994-111">Yalıtım teknolojisi, bir sandbox alanındaki güvenilmeyen uygulamaları sınırlamak için kullanılır ve sistem güvenliğini etkileyemeyeceğinden emin olur.</span><span class="sxs-lookup"><span data-stu-id="e2994-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="e2994-112">Tüm işletim sistemi, her bir bölüm farklı güvenlik teknolojilerinin bir birleşimiyle korunarak güvenli bölümlere bölündü.</span><span class="sxs-lookup"><span data-stu-id="e2994-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="e2994-113">**Veri koruma**: bir kullanıcının cihazı kaybolduysa veya çalınırsa, Hololens 2 yetkisiz uygulamaların, verilerin BitLocker şifrelemesine bağlı olarak gizli bilgileri okumasını önler.</span><span class="sxs-lookup"><span data-stu-id="e2994-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="e2994-114">**Parola-daha az işletim sistemi**: daha eski, parola tabanlı işletim sistemleri, kullanıcıları yanlışlıkla kimlik avı tehditleri halinde açığa çıkarır ve genellikle güvenliği aşılmış hesaplardan sorumludur.</span><span class="sxs-lookup"><span data-stu-id="e2994-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="e2994-115">Windows holographic for Business, MSA ve Azure AD oturum açma için parola kullanımını ortadan kaldırır ve Kullanıcı kimliği korumasını Windows Hello™ ve FIDO2 oturum açma ile güçlendirir.</span><span class="sxs-lookup"><span data-stu-id="e2994-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="e2994-116">FIDO2 desteği sağlamak için, cihazın 19041 veya üzeri bir sürüme sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e2994-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="e2994-117">**Ağ güvenliği**: HoloLens 2, gelişmiş protokoller ve varsayılan ayarlar aracılığıyla kullanıcının artan ağ güvenliğini sağlar.</span><span class="sxs-lookup"><span data-stu-id="e2994-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
