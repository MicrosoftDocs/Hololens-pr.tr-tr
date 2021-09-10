---
title: Sağlama paketi
description: HoloLens cihazlar için uygulama paketleme, sağlama, dağıtım ve kurumsal uygulama dağıtımı hakkında bilgi edinin.
keywords: uygulama, uygulama dağıtımı, kurumsal uygulama dağıtımı, sağlama
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427647"
---
# <a name="provisioning-package"></a>Sağlama paketi

Sağlama paketleri, uç nokta yönetimine erişim olmadan bir ortamdaki cihazları hazırlamak ve yapılandırmak için kullanılabilir. Ayrıca, kullanıcının kimliği, kayıt durumu, kutudan Out deneyimi (OOBE) sırasında veya [Kurulum sırasında bir sağlama paketi uygulanarak](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)bir cihaza da dağıtılabilir.

## <a name="provisioning-packages-considerations"></a>Paketleri sağlama konuları

* Genel olmayan uygulamalar
* Yalnızca USB dışarıdan yükleme
* Otomatik güncelleştirme yok (PPKGs aracılığıyla el ile güncelleştirme gerektirir)

Bir sağlama paketi aracılığıyla yüklenen uygulamalar, yerel makine deposundaki bir sertifika tarafından imzalanmış olmalıdır. Sağlama paketleri yalnızca cihaz (yerel makine) deposuna sertifika yükleyebilir. Bu nedenle, bir uygulama ve sertifika aynı sağlama paketi ile yüklenebilir. Sertifikanızı MDM 'den dağıtıyorsanız veya [Sertifika Yöneticisi](certificate-manager.md)aracılığıyla yüklüyorsanız, bu şekilde yüklenen uygulamaları imzalamak için sertifikayı yerel makine deposuna dağıttığınızdan emin olun.

HoloLens cihazları için sağlama paketi oluşturma hakkında temel bilgileri öğrenmek için [HoloLens sağlamayı](/hololens/hololens-provisioning)ziyaret edin. Bir uygulamayı dağıtmak için, gelişmiş sağlama ile başlamanız gerekir.

> [!NOTE]
> HoloLens (1. gen), bir sağlama paketi kullanarak uygulamaları (**üniversalappinstall**) yüklemeye yönelik sınırlı desteğe sahiptir. HoloLens (1. gen) cihazlar yalnızca yalnızca OOBE ve yalnızca kullanıcı bağlamı yüklemeleri ile ppkg aracılığıyla uygulama yüklemeyi destekler.

## <a name="setup"></a>Kurulum

[Windows yapılandırma tasarımcısı](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 'nda aşağıdaki dört adımı uygulayın.

1. ApplicationManagement/AllowAllTrustedApps 'Yi "Yes" olarak ayarlayın. Bkz: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. **Üniversalappınstall**  >  **usercontextapp** öğesine giderek **PackageFamilyName** girin. Bkz. [Üniversalappınstall](/windows/configuration/wcd/wcd-universalappinstall).

   Cihaz portalını, uygulamanızı zaten yüklemiş olduğunuz bir cihazda kullanabilirsiniz. Uygulamalar sayfasını ziyaret edin ve "!" öncesindeki tüm bilgileri, Packagerelativeıd satırına bakın. **PackageFamilyName**.

3. Daha sonra yeni bir bölüm olan **ApplicationFile** olduğunu görürsünüz. Appx paketlerinizi karşıya yüklemek için bu alanı kullanın.

4. Uygulamanızı satın aldıysanız veya kendi LOB uygulamanızı oluşturduysanız, lisans dosyasını veya güvenlik sertifikasını yüklemeniz gerekir.

    - Lisans dosyası için: **üniversalappınstall**  >  **usercontextapplicence** ' a gidin ve lisans ürün kimliğinizi girin. Yeni bir bölüm <b>licenseproductıd:</b><i>yourlicenseproductıd</i> oluşturulacak, bu yeni bölümü seçin ve lisansınızın bulunduğu konuma gidip karşıya yükleyin.
        - Bkz. [Usercontextapplicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Güvenlik dosyası için, **Sertifikalar** ' a gidin ve. appx paketinizin yanına yüklemek için sertifikanızı seçin.

Projenizi güvenli bir konuma kaydettiğinizden emin olun. Daha sonra bir **sağlama paketi** olarak **dışarı aktarın** .  

Ayrıca bkz: [HoloLens için sağlama paketinizi uygulama](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
