---
title: ıntune ve Şirket Portalı
description: Intune, mobil cihaz yönetimi ve şirket portalı ile rahat bir kullanıcı deneyimi ayarlamayı, atamayı ve oluşturmayı öğrenin.
keywords: Intune, uygulama yönetimi, uygulama, Şirket portalı, Portal, Hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427191"
---
# <a name="intune--company-portal"></a>ıntune & Şirket Portalı

mobil cihaz yönetimi (MDM) ile, doğrudan HoloLens cihazlarınıza dağıtmak için [Microsoft Endpoint Manager (ıntune)](/intune/windows-holographic-for-business) aracılığıyla kendi özel uygulamalarınızı kullanabilirsiniz. Microsoft Intune, mobil cihaz yönetimine (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir. ıntune, Microsoft 'un [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)'e dahil edilmiştir ve kuruluşunuzun verilerinin korunmasını sağlarken kullanıcıların üretken olmalarını sağlar. Intune hakkında daha fazla bilgi edinmek için [Intune](/mem/intune/fundamentals/what-is-intune)'u okuyun.

## <a name="setup"></a>Kurulum

1. bir iş kolu için uygulama Upload veya özel bir uygulamayı ıntune kiracınıza yükleyin. ayrıca bkz: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).

2. [Uygulamanızı bir gruba atayın](/mem/intune/apps/apps-deploy). Seçtiğiniz atama türüne göre uygulama otomatik olarak teslim edilebilir veya bir uygulama seçiminiz varsa, kolayca kullanıma sunulabilir.

> [!NOTE]
> Appx paketlerinizi oluştururken, dağıttığınız cihazların mimarisini dahil etmek için hesap yaptığınızdan emin olun. HoloLens 2 ARM64, HoloLens (1. Gen) ise x86. Karma cihazlar ortamı bulundurmaktan karşılaşıyorsanız, her ikisini de tek bir appx paketine dahil edebilirsiniz.

## <a name="assignment-types"></a>Atama türleri

Uygulamanızın kayıt sonrasında cihaza otomatik olarak yüklenmesini sağlamak için, bu gruplar için **gerekli** ' ı seçmeniz gerekir.
Uygulamanızı Şirket portalı üzerinden kaydedilmiş cihazlara indirilebilir hale getirmek için, **Kayıtlı cihazlar Için kullanılabilir**' ı seçin.

## <a name="end-user-experience"></a>End-User deneyim

Intune 'da yapılandırmayı ayarladıktan sonra, son kullanıcıların seçili uygulamalarınızı almasına hazırlanın.

Uygulamanızı otomatik olarak almak için aşağıdaki adımları izleyin:

1. Cihazınızı kiracınızla kaydedin.
2. Cihazınızın kaydı tamamladıktan sonra, uygulamayı cihazınızda almalısınız.
3. uygulamanızı hemen görmüyorsanız, **Ayarlar**  >  **hesapları**  >  **çalışıyor**' a gidin veya  >  *hesap* bilgilerinizi okul yapın ve yüklü uygulama durumu hakkındaki bilgileri görmek için aşağı kaydırın.

Şirket Portalı aracılığıyla uygulamalara nasıl ulaşırsanız:

1. **Başlat menüsünü** açın ve **Microsoft Store**' yi seçin.
2. **Şirket Portalı** arayın ve uygulamayı indirin.
3. Hesabınızda oturum açın.
4. Almak istediğiniz uygulamayı seçin ve indirin.

> [!Tip]
> [Şirket Portalı otomatik olarak yükleme](/mem/intune/apps/company-portal-app) ve [ıntune 'da uygulamaları dağıtma ve yönetme](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)hakkında daha fazla bilgi edinin.
