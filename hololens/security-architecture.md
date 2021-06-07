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
# <a name="security-overview-and-architecture"></a>Güvenliğe genel bakış ve mimari

HoloLens 2 güvenlik mimarisi, sıfırdan küçük bir saldırı yüzeyi oluşturulurken eski güvenlik sorunlarından ücretsiz olarak tasarlanıp oluşturulmuştur. Bu yeni ve yenilikçi mimari, güvenli depolama konumları ve gelişmiş güvenlik öğeleri sunarak, olası tehditler ve güvenlik açıklarına karşı koruma işletim sistemleri yapabilen mekanizmalar sağlar.

HoloLens 2, en iyi deneyimi sunmak için donanım, yazılım, ağ ve Hizmetleri birleştirerek uçtan uca güvenlik sağlar. HoloLens 2 sayesinde, güvenlik özelliklerinin büyük bir bölümü otomatik olarak açıktır ve işletim sistemini doğru şekilde ayarlamak ve yapılandırmak için gereken çabayı en aza indirir.

Windows HoloLens 2 ve işletim sistemi mimarisi şu yenilikçi güvenlik özelliklerini sunmaktadır:

  * **Durum ayrımı ve yalıtım**: Bu yeni mimari, Hololens 2 işletim sisteminin kritik bölümlerini, çekirdek işletim sisteminin güvenilir bir duruma önyüklemesinde gerekli olanlar gibi değişiklikten korur. Yalıtım teknolojisi, bir sandbox alanındaki güvenilmeyen uygulamaları sınırlamak için kullanılır ve sistem güvenliğini etkileyemeyeceğinden emin olur. Tüm işletim sistemi, her bir bölüm farklı güvenlik teknolojilerinin bir birleşimiyle korunarak güvenli bölümlere bölündü.
  
  * **Veri koruma**: bir kullanıcının cihazı kaybolduysa veya çalınırsa, Hololens 2 yetkisiz uygulamaların, verilerin BitLocker şifrelemesine bağlı olarak gizli bilgileri okumasını önler. 
  
  * **Parola-daha az işletim sistemi**: daha eski, parola tabanlı işletim sistemleri, kullanıcıları yanlışlıkla kimlik avı tehditleri halinde açığa çıkarır ve genellikle güvenliği aşılmış hesaplardan sorumludur. Windows holographic for Business, MSA ve Azure AD oturum açma için parola kullanımını ortadan kaldırır ve Kullanıcı kimliği korumasını Windows Hello™ ve FIDO2 oturum açma ile güçlendirir. 
  
    > [!NOTE]
    > FIDO2 desteği sağlamak için, cihazın 19041 veya üzeri bir sürüme sahip olması gerekir. 

  * **Ağ güvenliği**: HoloLens 2, gelişmiş protokoller ve varsayılan ayarlar aracılığıyla kullanıcının artan ağ güvenliğini sağlar.
