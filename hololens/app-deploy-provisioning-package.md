---
title: Sağlama Paketi
description: Cihazlar için uygulama paketleme, sağlama, dağıtım ve kurumsal uygulama dağıtımı HoloLens öğrenin.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033083"
---
# <a name="provisioning-package"></a>Sağlama Paketi

Paketleri sağlama, uç nokta yönetimine erişimi olmayan bir ortamda cihazları hazırlamak ve yapılandırmak için kullanılabilir. Ayrıca kullanıcı kimliği, kayıt durumu, İlk Kullanım Deneyimi (OOBE) sırasında veya kurulum sırasında bir sağlama paketi uygulanarak bir cihaza [dağıtılabilir.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Sağlama Paketleri ile ilgili dikkat edilmesi gerekenler

* Genel Olmayan uygulamalar
* Yalnızca USB yan yüklemesi
* Otomatik güncelleştirme yok (PPKG'ler aracılığıyla el ile güncelleştirme gerektirir)

Sağlama paketi aracılığıyla yüklenmiş uygulamalar, yerel makine mağazasındaki bir sertifika tarafından imzalanacak. Sağlama paketleri yalnızca cihaz (yerel makine) deposuna sertifika yükleyebilir. Bu nedenle, aynı sağlama paketi aracılığıyla bir uygulama ve sertifika yükleyebilirsiniz. Sertifikanızı MDM'den dağıtıyor veya Sertifika [](certificate-manager.md)Yöneticisi aracılığıyla yüklüyorsanız, bu şekilde yüklü uygulamaları imzalamak için sertifikayı yerel makine deposuna dağıtın.

Cihazlarınız için Sağlama Paketi oluşturmanın temellerini öğrenmek HoloLens [sağlama'HoloLens ziyaret edin.](/hololens/hololens-provisioning) Bir uygulamayı dağıtmak için gelişmiş sağlama ile başlamalısiniz.

> [!NOTE]
> HoloLens (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).** HoloLens (1. nesil) cihazlar yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.

## <a name="setup"></a>Kurulum

Yapılandırma [Windows'nin içinde](https://www.microsoft.com/store/productId/9NBLGGH4TX22) dört adımı izleyin.

1. ApplicationManagement/AllowAllTrustedApps'i "Evet" olarak ayarlayın. Bkz. [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. **UniversalAppInstall**  >  **UserContextApp'e gidin** ve **PackageFamilyName girin.** Bkz. [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Daha önce Cihaz Portalı bir cihazda bu bilgileri kullanabilirsiniz. Uygulamalar sayfasını ziyaret edin ve PackageRelativeID satırına ve "!" **PackageFamilyName dosyanız mı?**

3. Ardından ApplicationFile yeni bir bölümünüz **olduğunu göreceğiz.** Appx paketinizi karşıya yüklemek için bu alanı kullanın.

4. Uygulama satın aldı veya kendi LOB uygulamasını yaptınıza bağlı olarak, lisans dosyasını veya güvenlik sertifikasını karşıya yüklemeniz gerekir.

    - Lisans dosyası için: **UniversalAppInstall**  >  **UserContextAppLicence'a gidin** ve lisans ürün kimliğinizi girin. Yeni bir <b>LicenseProductID bölümü</b>oluşturulur:licenseproductid öğesiniz oluşturulur, bu yeni bölümü seçin ve lisansınız konumunu göz atarak yükleyin.<i></i>
        - Bkz. [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - Güvenlik dosyası için Sertifikalar'a **gidin** ve .appx paketinizin yanı sıra yüklemek istediğiniz sertifikayı seçin.

Projenizi güvenli bir konuma kaydetmeyi emin olun. Ardından **Bunu** Sağlama Paketi **olarak dışarı aktarın.**  

Ayrıca bkz. [Sağlama paketinizi HoloLens.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
