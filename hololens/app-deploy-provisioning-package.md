---
title: Sağlama Paketi
description: HoloLens cihazları için uygulama paketleme, sağlama, dağıtım ve kurumsal uygulama dağıtımı hakkında bilgi edinebilirsiniz.
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379034"
---
# <a name="provisioning-package"></a>Sağlama Paketi

Paketleri sağlama, uç nokta yönetimine erişimi olmayan bir ortamda cihazları hazırlamak ve yapılandırmak için kullanılabilir. Ayrıca kullanıcı kimliği, kayıt durumu, İlk Kullanım Deneyimi (OOBE) sırasında veya kurulum sırasında bir sağlama paketi uygulanarak bir cihaza [dağıtılabilir.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Sağlama Paketleri ile ilgili dikkat edilmesi gerekenler:

* Genel Olmayan uygulamalar
* Yalnızca USB yan yüklemesi
* Otomatik güncelleştirme yok (PPKG'ler aracılığıyla el ile güncelleştirme gerektirir)

Sağlama paketi aracılığıyla yüklenmiş uygulamalar, yerel makine mağazasındaki bir sertifika tarafından imzalanacak. Sağlama paketleri yalnızca cihaz (yerel makine) deposuna sertifika yükleyebilir, bu nedenle aynı sağlama paketi aracılığıyla bir uygulama ve sertifika yükleyebilir. Sertifikanızı MDM'den dağıtıyor veya Sertifika [](certificate-manager.md)Yöneticisi aracılığıyla yüklüyorsanız, bu şekilde yüklü uygulamaları imzalamak için sertifikayı yerel makine deposuna dağıtın.

HoloLens cihazları için Sağlama Paketi oluşturmanın temellerini öğrenmek için [HoloLens Sağlama'ya ziyaret edin.](https://docs.microsoft.com/hololens/hololens-provisioning) Bir uygulamayı dağıtmak için gelişmiş sağlama ile başlamalısiniz.

> [!NOTE]
> HoloLens 'in (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).** HoloLens (1. nesil) cihazları yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.

## <a name="setup"></a>Kurulum

[Windows Yapılandırma Tasarımcısı'nın](https://www.microsoft.com/store/productId/9NBLGGH4TX22) içinde dört adımı izleyin.

1. ApplicationManagement/AllowAllTrustedApps'i "Evet" olarak ayarlayın. Bkz. [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. **UniversalAppInstall**  >  **UserContextAppLicense'e** gidin ve **PackageFamilyName girin.** Bkz. [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Ayrıca bkz. [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Bu Cihaz Portalı önceden yüklemiş olduğunuz bir cihazda kullanabilirsiniz. Uygulamalar sayfasını ziyaret edin ve PackageRelativeID satırına ve "!" **PackageFamilyName dosyanız mı?**

3. Ardından ApplicationFile yeni bir bölümünüz **olduğunu göreceğiz.** Appx paketinizi karşıya yüklemek için bu alanı kullanın.

4. Uygulama satın aldığınıza veya kendi LOB uygulamanızı 7.000'e yüklediğinize bağlı olarak, lisans dosyasını veya güvenlik sertifikasını karşıya yükleyebilirsiniz.

    - Lisans dosyası için: **UniversalAppInstall**  >  **UserContextAppLicence'a** gidin, lisansınızı konumunu bulun ve yükleyin.
    - Güvenlik dosyası için Sertifikalar'a **gidin** ve .appx paketinizin yanı sıra yüklemek istediğiniz sertifikayı seçin.

Projenizi güvenli bir konuma kaydetmeyi emin olun. Ardından **Bunu** Sağlama Paketi **olarak dışarı aktarın.**  

Ayrıca bkz. [Sağlama paketinizi HoloLens'e uygulama.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
