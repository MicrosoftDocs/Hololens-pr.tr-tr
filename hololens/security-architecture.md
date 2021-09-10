---
title: HoloLens güvenlik mimarisi
description: Güvenlik mimarisi
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428968"
---
# <a name="security-overview-and-architecture"></a>Güvene genel bakış ve mimari

En HoloLens 2 güvenlik mimarisi, en aza indirgenmiş bir saldırı yüzeyi oluştururken eski güvenlik sorunlarından uzak olacak şekilde tasarlanmış ve tasarlanmıştır. Bu yeni, yenilikçi mimari, işletim sistemlerini olası tehditlere ve güvenlik açıklarına karşı koruma özelliğine sahip mekanizmalarla güvenli depolama konumları ve gelişmiş güvenlik öğeleri sunar.

HoloLens 2, donanım, yazılım, ağ ve hizmetleri bir araya kullanarak 2. 4.000 güvenlik sunar ve kullanıcıya en iyi deneyimi sunar. HoloLens 2 ile, güvenlik özelliklerinin büyük bir çoğunluğu artık otomatik olarak açılır ve işletim sistemini doğru ayarlamak ve yapılandırmak için gereken çaba en aza indirilir.

Windows HoloLens 2 ve işletim sistemi mimarisi şu yenilikçi güvenlik özelliklerini sunar:

  * **Durum ayrımı** ve yalıtımı: Bu yeni mimari, HoloLens 2 işletim sisteminin kritik bölümlerini, çekirdek işletim sisteminin güvenilir bir durumda önyüklemesi için gerekenler gibi değişiklikten korur. Yalıtım teknolojisi, güvenilmeyen uygulamaları bir korumalı alan alanında sınırlar ve bu uygulamaların sistem güvenliğini etkilemesini engellemek için kullanılır. İşletim sisteminin tamamı güvenli bölümlere ayrılmıştır ve her bölüm farklı güvenlik teknolojilerinin bir birleşimiyle koruma altına alınmıştır.
  
  * **Veri Koruma:** Kullanıcının cihazı kaybolur veya çalınırsa, HoloLens 2, verilerin BitLocker şifrelemesini kullanarak yetkisiz uygulamaların hassas bilgileri okumasını önler. 
  
  * **Parolasız işletim sistemi:** Eski, parola tabanlı işletim sistemleri, kullanıcıların kimlik avı tehditlerine yanlışlıkla maruz kaldı ve genellikle güvenliği tehlikeye atılmış hesaplardan sorumludu. Windows Holographic for Business MSA ve Azure AD oturum açma için parola kullanımını ortadan kaldırmakta ve Windows Hello™ ve FIDO2 oturum açma ile kullanıcı kimliği korumasını güçlendirmektedir. 
  
    > [!NOTE]
    > FIDO2 desteğine sahip olmak için cihazın Derleme 19041 veya üzerinde olması gerekir. 

  * **Ağ güvenliği:** HoloLens 2, gelişmiş protokoller ve varsayılan ayarlar aracılığıyla kullanıcıya daha yüksek ağ güvenliği sunar.
