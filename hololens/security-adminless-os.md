---
title: Yönetici-daha az işletim sistemi güvenliği
description: HoloLens karma gerçeklik cihazlarındaki yönetici-daha az işletim sistemi, cihaz sahipleri ve güvenlik hakkında bilgi edinin.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Güvenlik, Hololens, adminless, yönetici-daha seyrek, işletim sistemi, yönetici-daha seyrek işletim sistemi, yönetim işletim sistemi, yönetici-daha az işletim sistemi, Hololens 2, hololens2 Security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f4fc79b7f51933418cdda8368c6b4b070e854dd0978754647ce864075c772cfd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665548"
---
# <a name="admin-less-operating-system"></a>Yönetici-daha az işletim sistemi

HoloLens 2, Administrators grubu desteğini devre dışı bırakarak ve tüm üçüncü taraf UWP uygulama kodlarını yalnızca AppContainer korumalı alanı içinde standart kullanıcı olarak yürütmek üzere, ayrıcalık yükseltme için yüzey alanını en aza indirir. Bu koda yalnızca, tüm AppContainers tarafından erişilebilen kaynaklara ek olarak, yükseltilmiş olmayan bir kullanıcı için uygulamada açıkça bildirilen yetenekler tarafından korunan kaynaklara erişim izni verilir.
Bu uygulama özellikleri üç katmanlı sınıflandırma modeline sahip olmaya devam eder:
  * Genel
  * Kısıtlı
  * Windows

Windows bileşenler, System uwps aracılığıyla AppContainer korumalı alanını da kullanabilir. Evrensel Windows Platformu (uwp) hakkında daha fazla bilgi edinmek için bkz. [UWP belgeleri](/windows/uwp/). ayrıca, daha fazla ayrıcalık azaltma ihtiyaçlarına sahip Windows bileşenleri (tarayıcı içerik sayfaları veya çözümleyicileri gibi), tüm appcontainer 'lar tarafından erişilebilen kaynak kümesine erişimi keser, daha az ayrıcalıklı AppContainer (lpac) korumalı alanı kullanır.

## <a name="device-owner"></a>Cihaz sahibi

Son olarak, cihaza bir kiracıya veya Kullanıcı yönetimine katılma gibi belirli cihaz genelinde işlemlerin yürütülmesi yalnızca "cihaz sahipleri" için izin verilir. Bu grup, aşağıdaki adımlardan biri aracılığıyla cihazdaki kullanıcılar tarafından doldurulur:
  * Cihazdaki ilk Kullanıcı her zaman bir sahip olarak atanır. 
> [!IMPORTANT]
>Azure AD kullanıcıları için, bu kuralın özel durumu, cihazın Azure AD ile Autopilot veya toplu Azure AD kaydı aracılığıyla, gerçek olmayan bir Kullanıcı kullanan bir durumdur. Bu durumda, bu kullanıcı "genel yönetici" veya "Cihaz Yöneticisi" rolüne Azure portal atanmadığı takdirde cihazda oturum açmak için ilk AAD kullanıcısı cihaz sahibini otomatik olarak yapmayabilir. Daha fazla bilgi için aşağıdaki nota bakın.  

  * bir kullanıcı cihazdaki başka bir sahibe Ayarlar UX 'ten sahip olacak şekilde yükseltildiğinde.
  * Cihaz sahibi artık kullanılabilir değilse (şirketten ayrılırsa) ve cihaz Azure AD 'ye katılırsa, kiracı yöneticisi cihaz sahibini Azure portal yeni bir kullanıcıyla değiştirebilir. Bir Azure AD kiracısının genel yöneticileri ve cihaz yöneticileri, önceki adımlardan herhangi birine gerek kalmadan, cihazdaki sahipler olarak örtülü olarak oturum açtı.  

 BT yöneticileri, hangi uygulamaların [Gizlilik](/windows/client-management/mdm/policy-csp-privacy) ilkeleriyle erişebileceğini yönetebilir. 

> [!NOTE]
> Bir Azure AD 'ye katılmış cihazda kimin cihaz sahibi yaptığını daha fazla anlamak için, bkz. ["yerel yönetici atama" belgeleri](/azure/active-directory/devices/assign-local-admin) (yönetici HoloLens olmadığı için "yerel admin' olarak ' cihaz sahibi ' olarak okunabilir).