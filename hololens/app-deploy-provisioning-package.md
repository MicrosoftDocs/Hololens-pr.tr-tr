---
title: Sağlama Paketi
description: Mobil cihazlar için uygulama paketleme, sağlama, dağıtım ve kurumsal uygulama dağıtımı HoloLens öğrenin.
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635526"
---
# <a name="provisioning-package"></a>Sağlama Paketi

Paketleri sağlama, uç nokta yönetimine erişimi olmayan bir ortamda cihazları hazırlamak ve yapılandırmak için kullanılabilir. Ayrıca kullanıcı kimliği, kayıt durumu, İlk Kullanım Deneyimi (OOBE) sırasında veya kurulum sırasında bir sağlama paketi uygulanarak bir cihaza [dağıtılabilir.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Sağlama Paketleri ile ilgili dikkat edilmesi gerekenler:

* Genel Olmayan uygulamalar
* Yalnızca USB yan yüklemesi
* Otomatik güncelleştirme yok (PPKG'ler aracılığıyla el ile güncelleştirme gerektirir)

Sağlama paketi aracılığıyla yüklenmiş uygulamalar, yerel makine mağazasındaki bir sertifika tarafından imzalanacak. Sağlama paketleri yalnızca cihaz (yerel makine) deposuna sertifika yükleyebilir, bu nedenle aynı sağlama paketi aracılığıyla bir uygulama ve sertifika yükleyebilir. Sertifikanızı MDM'den dağıtıyor veya Sertifika [](certificate-manager.md)Yöneticisi aracılığıyla yüklüyorsanız, bu şekilde yüklü uygulamaları imzalamak için sertifikayı yerel makine deposuna dağıtın.

Cihazlarınız için Sağlama Paketi oluşturmanın temellerini öğrenmek HoloLens [sağlama'HoloLens ziyaret edin.](/hololens/hololens-provisioning) Bir uygulamayı dağıtmak için gelişmiş sağlama ile başlamalısiniz.

> [!NOTE]
> HoloLens (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).** HoloLens (1. nesil) cihazlar yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.

## <a name="setup"></a>Kurulum

Yapılandırma [Windows'nin içinde](https://www.microsoft.com/store/productId/9NBLGGH4TX22) dört adımı izleyin.

1. ApplicationManagement/AllowAllTrustedApps'i "Evet" olarak ayarlayın. Bkz. [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. **UniversalAppInstall**  >  **UserContextAppLicense'e** gidin ve **PackageFamilyName girin.** Bkz. [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Ayrıca bkz. [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Bu Cihaz Portalı önceden yüklemiş olduğunuz bir cihazda kullanabilirsiniz. Uygulamalar sayfasını ziyaret edin ve PackageRelativeID satırına ve "!" **PackageFamilyName dosyanız mı?**

3. Ardından ApplicationFile yeni bir bölümünüz **olduğunu göreceğiz.** Appx paketinizi karşıya yüklemek için bu alanı kullanın.

4. Uygulama satın aldı veya kendi LOB uygulamasını yaptınıza bağlı olarak, lisans dosyasını veya güvenlik sertifikasını karşıya yüklemeniz gerekir.

    - Lisans dosyası için: **UniversalAppInstall**  >  **UserContextAppLicence'a** gidin, lisansınızı konumunu bulun ve yükleyin.
    - Güvenlik dosyası için Sertifikalar'a **gidin** ve .appx paketinizin yanı sıra yüklemek istediğiniz sertifikayı seçin.

Projenizi güvenli bir konuma kaydetmeyi emin olun. Ardından **Bunu** Sağlama Paketi **olarak dışarı aktarın.**  

Ayrıca [bkz. Sağlama paketinizi HoloLens.](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
