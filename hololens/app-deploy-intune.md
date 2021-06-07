---
title: Intune ve Şirket Portalı
description: Intune, mobil cihaz yönetimi ve şirket portalı ile rahat bir kullanıcı deneyimi ayarlamayı, atamayı ve oluşturmayı öğrenin.
keywords: intune, uygulama yönetimi, uygulama, şirket portalı, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379105"
---
# <a name="intune--company-portal"></a>Intune & Şirket Portalı

Mobil Cihaz Yönetimi (MDM) ile, doğrudan HoloLens cihazlarınıza dağıtmak için [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) aracılığıyla kendi özel uygulamalarınızı kullanabilirsiniz. Microsoft Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir. Intune, Microsoft'un [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)paketine dahildir ve kullanıcıların üretken bir şekilde çalışmalarına olanak sağlar ve kuruluş verilerinizin korunmasını sağlar. Intune hakkında daha fazla bilgi edinmek için [Intune nedir? makalelerini okuyun.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Kurulum

1. Bir İş Hattına uygulama yükleme veya Intune kiracınıza özel bir uygulama yükleme. Ayrıca bkz. [Kurumsal uygulama yönetimi.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)

2. [Uygulamalarınızı bir gruba attayabilirsiniz.](https://docs.microsoft.com/mem/intune/apps/apps-deploy) Seçtiğiniz atama türüne bağlı olarak, uygulama otomatik olarak teslim edilir veya bir uygulama seçiminiz varsa çekme için kullanılabilir.

> [!NOTE]
> Appx paketinizi hazırlarken, dağıtmakta olduğunuz cihaz mimarilerini dahil etmek için hesaba katyın. HoloLens 2 ARM64, HoloLens (1. Nesil) ise x86'dır. Karma cihaz ortamına sahip olmak planlıyorsanız her ikisini de tek bir appx paketine dahil edersiniz.

## <a name="assignment-types"></a>Atama türleri

Kayıt sonrasında uygulamanın cihaza otomatik olarak yüklenmiş olması  için, bu gruplarda Gerekli'yi seçmeniz gerekir.
Uygulamanın şirket portalı üzerinden kayıtlı cihazlara indirilsin mi? için Kayıtlı cihazlar için **kullanılabilir'i seçin.**

## <a name="end-user-experience"></a>End-User Deneyimi

Intune'da yapılandırmayı ayardikten sonra, son kullanıcıların seçili uygulamalarınızı almaya hazırsınız.

Uygulamalarınızı otomatik olarak almak için şu adımları izleyin:

1. Cihazınızı kiracınıza kaydetme.
2. Cihazınız kaydı tamamlandıktan sonra uygulamayı cihazınıza alasınız.
3. Uygulamayı hemen görmüyorsanız Ayarlar Hesapları İş veya Okul hesabınıza ilişkin Bilgiler'e gidin ve yüklü uygulama durumuyla ilgili bilgileri görmek  >    >    >   için aşağı kaydırın.

Aşağıdakiler aracılığıyla uygulamalara Şirket Portalı:

1. Başlat **Menüsü'yü açın** **ve** Microsoft Store.
2. Uygulamayı **Şirket Portalı** ve indirin.
3. Hesabınızla oturum açın.
4. Almak istediğiniz uygulamayı seçin ve indirin.

> [!Tip]
> [Intune'da uygulamaları Şirket Portalı](https://docs.microsoft.com/mem/intune/apps/company-portal-app) ve yönetme hakkında daha fazla bilgi [edinin.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
