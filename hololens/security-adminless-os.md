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
# <a name="admin-less-operating-system"></a>Yönetici olmayan işletim sistemi

HoloLens 2, Yöneticiler grubu desteğini devre dışı bırakarak ve tüm üçüncü taraf UWP uygulama kodunu yalnızca AppContainer korumalı alanında standart kullanıcılar olarak yürütecek şekilde sınır kullanarak ayrıcalık yükseltme için yüzey alanı en aza indirger. Bu koda yalnızca, tüm AppContainers tarafından erişilebilen kaynaklara ek olarak, uygulamada açıkça bildirilen özelliklerle korunan kaynaklara erişim izni veılır.
Bu uygulama özellikleri üç katmanlı sınıflandırma modeline sahip olmaya devam eder:
  * Genel
  * Kısıtlı
  * Windows

Windows bileşenleri, Sistem UWP'leri aracılığıyla AppContainer korumalı alandan da faydalanabilirsiniz. Evrensel Windows Platformu (UWP) hakkında daha fazla bilgi edinmek için [UWP belgelerine bakın.](https://docs.microsoft.com/windows/uwp/) Ayrıca, daha fazla ayrıcalık azaltma ihtiyacı olan Windows bileşenleri (tarayıcı içerik sayfaları veya ayrıştırıcılar gibi) Tüm AppContainer'lar tarafından erişilebilen kaynak kümesine erişimi azaltan Less Privileged AppContainer (LPAC) korumalı alanı kullanır.

## <a name="device-owner"></a>Cihaz sahibi

Son olarak, cihazı bir kiracıya veya kullanıcı yönetimine birleştirme gibi belirli cihaz genelindeki işlemlerin yürütülmesine yalnızca "cihaz sahipleri" için izin verilir. Bu grup, aşağıdaki adımlardan biri aracılığıyla cihaz kullanıcıları tarafından doldurulur:
  * Cihaza ilk kullanıcı her zaman Sahip olarak atanmıştır. 
> [!IMPORTANT]
>Azure AD Kullanıcıları için bu kuralın istisnası, cihazın Autopilot aracılığıyla Azure AD'ye katılmış veya gerçek olmayan bir kullanıcı kullanan toplu Azure AD kaydı olduğudur. Bu durumda, cihazda oturum açması gereken ilk AAD kullanıcısı, cihazda "genel yönetici" veya "cihaz yöneticisi" rolü atanmadıkça cihaz sahibi Azure portal. Daha fazla bilgi için aşağıdaki nota bakın.  

  * Bir kullanıcı, cihaza başka bir Sahip tarafından Ayarlar UX'den Sahip olarak yükseltilene.
  * Cihaz sahibi artık kullanılamıyorsa (şirketten ayrılıyorsa) ve cihaz Azure AD'ye katılmışsa, Kiracı Yöneticisi cihaz sahibini şirket içinde yeni bir kullanıcı Azure portal. Azure AD kiracılarının Genel Yöneticileri ve Cihaz Yöneticileri, önceki adımlardan herhangi birini gerektirmeden cihazda Sahip olarak açık olarak oturum açın.  

 IT yöneticileri, Hangi uygulamaların Gizlilik ilkeleri aracılığıyla [erişebilirsiniz yönetebilir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) 

> [!NOTE]
> Azure AD'ye katılmış bir cihazda kimlerin cihaz sahibi olduğu hakkında daha fazla bilgi için "Yerel Yönetici [Atama"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) belgelerine bakın (ancak HoloLens'de yönetici mevcut değil, 'yerel yönetici' olarak 'cihaz sahibi' olarak okuyun).