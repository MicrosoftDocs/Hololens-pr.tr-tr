---
title: dağıtım kılavuzu – buluta bağlı HoloLens 2 dağıtım, uzaktan yardım ile devam eden bir ölçekte.
description: bulut bağlantılı ağ üzerinden HoloLens cihazları sürdürmek ve desteklemek için ipuçlarımızla güncel kalın.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033534"
---
# <a name="maintain---cloud-connected-guide"></a>Bakım-bulut bağlantılı Kılavuzu

## <a name="updates"></a>Güncelleştirmeler

Microsoft, bt yöneticilerine, cihaz gruplarına güncelleştirme dağıtma ve güncelleştirme yüklemeye yönelik bakım pencerelerini tanımlama gibi ek Windows Update merkezli yönetim özellikleri sağlamak için Windows Update tasarlamıştır.

zamanlanan günler ve zamanlanan süre dahil [HoloLens güncelleştirmelerinin nasıl yönetileceğini](/hololens/hololens-updates) ve çalışma saatleri dışında güncelleştirilecek şekilde cihazdaki etkin saatleri ayarlamayı öğrenin.

uzaktan yardım, bir In-Box uygulamasıdır ve Microsoft Store uygulama aracılığıyla güncelleştirebilir. Microsoft Store aracılığıyla indirilen tüm uygulamalar için Microsoft Store uygulamasının kendisiyle el ile [güncelleştirilebilirler](/hololens/holographic-store-apps#update-apps) .

## <a name="support-plan"></a>Destek Planı

Bir destek planı, uygun olan harika bir şeydir. HoloLens cihazlarda kayıt işlemini sorun gidermeye ve ayrıca kuruluşunuzda HoloLens cihazının genel kullanımına yönelik bir kullanıcı veya bir grup olma. Kullanıcılarınızın sorunlarından daha hızlı çözümlenmesine izin vermek için, yükseltme işleminizin bu sırayla benzer bir şekilde işlenmesini öneririz:

1. Destek masanıza başvurun.
2. HoloLens uzman ekibiniz
3. [HoloLens Docs](/hololens/)  /  [HoloLens sorunlarını giderme belgeleri](/hololens/hololens-troubleshooting)
4. [Desteğe başvurun](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Geliştirme planı

Cihazınız başarıyla kaydedildikten sonra, cihazlarınıza Iş kolu uygulamaları (LOB uygulamaları) dağıtmaya hazırsınız demektir. Bunlar, kuruluşunuz&#39;ihtiyaçları için oluşturulmuş özel uygulamalardır.

Zaten bir iş kolu uygulamanız varsa, [UYGULAMANıZı MDM aracılığıyla dağıtmaya](/hololens/app-deploy-intune)başlamaya&#39;. farklı bir yöntemi tercih&#39;, daha sonra LOB uygulamanızı cihazlarınıza dağıtma hakkında daha fazla bilgi edinmek için [HoloLens 2 için uygulama dağıtımına genel bakış](/hololens/app-deploy-overview) konusunu gözden geçirin.

Kendi LOB uygulamanızı oluşturmanız veya hala oluşturma süreciyle karşılaşırsanız, karma gerçeklik geliştirme belgelerimizi inceleyerek [karma gerçeklik geliştirmesini](/windows/mixed-reality/discover/get-started-with-mr) kullanmaya başlamak için temel kavramları gözden geçirin [veya öğrenin](/windows/mixed-reality/design/design) .&#39;

## <a name="device-management"></a>Aygıt Yönetimi 

Bu kılavuz, mobil cihaz yönetimi (MDM) ayarlama hakkında konuşurken cihaz kısıtlamalarını uygulamak için işe yaramadı veya cihazlara uygulandı. Cihaz yönetimi, sertifikaları ileterek erişime izin vermek veya çeşitli cihaz kısıtlamalarıyla erişimi kısıtlamak için kullanılabilir. 

çoğu durumda, cihazlar Bluetooth, VPN, USB gibi bağlantı kısıtlamalarına sahip olabilir ve hatta kameraya veya mikrofona erişimi devre dışı bırakır. Bu ilgi alanlarından herhangi biri bundan sonra [ortak cihaz kısıtlamaları sayfasını](hololens-common-device-restrictions.md)okumanızı öneririz.

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları vardır. Örneğin:

- [settingspagevisibility](settings-uri-list.md)' ı kullanarak Ayarlar uygulamasında görüntülenebilen sayfaları sınırlandırma, kullanıcıların yalnızca Wi-Fi bağlantılarını değiştirme gibi ayarlanması için ihtiyaç duydukları ayarlara erişmesine izin verir.
- Bir cihazdaki kullanıcılara sunulan kullanıcı arabirimini sınırlamak için [bilgi noktası modunu](hololens-kiosk.md) kullanın. Kiosks 'i tek bir uygulama veya bir özel başlangıç sayfası ile birden çok uygulama gösterecek şekilde ayarlayabilirsiniz. Kiosks, farklı kullanıcılara farklı deneyimler de sunabilir.  
- belirli uygulamaların veya işlemlerin tamamen başlatılmasını sağlamak için [uygulama denetimi (WDAC) Windows](windows-defender-application-control-wdac.md) .

Cihaz yönetimi veya cihaz kısıtlamalarının daha farklı yöntemleri hakkında daha fazla bilgi edinmek istiyorsanız, sonraki adıma geçin ve cihaz yönetimine genel bakış konusunu okuyun.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [CSP 'Leri ve cihaz yönetimine genel bakış](hololens-csp-policy-overview.md)