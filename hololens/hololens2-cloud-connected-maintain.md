---
title: Dağıtım Kılavuzu – bulut bağlantılı HoloLens 2 dağıtımı, uzaktan yardım-bakım ile ölçeklendirin
description: HoloLens cihazlarını bulut bağlantılı bir ağ üzerinden sürdürmek ve desteklemek için ipuçlarımızla güncel kalın.
keywords: HoloLens, yönetim, bulut bağlantılı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379116"
---
# <a name="maintain---cloud-connected-guide"></a>Bakım-bulut bağlantılı Kılavuzu

## <a name="updates"></a>Güncelleştirmeler

Microsoft, BT yöneticilerine, cihaz gruplarına güncelleştirme dağıtma ve güncelleştirme yüklemeye yönelik bakım pencerelerini tanımlama gibi ek Windows Update merkezli yönetim özellikleri sağlamak için Windows Update tasarlamıştır.

Zamanlanan günler ve zamanlanan saatler dahil olmak üzere [HoloLens güncelleştirmelerini yönetmeyi](https://docs.microsoft.com/hololens/hololens-updates) ve çalışma saatleri dışında güncelleştirilecek şekilde cihazdaki etkin saatleri ayarlamayı öğrenin.

Uzaktan Yardım, bir In-Box uygulamasıdır ve Microsoft Store uygulama aracılığıyla güncelleştirebilir. Microsoft Store aracılığıyla indirilen tüm uygulamalar için Microsoft Store uygulamasının kendisiyle el ile [güncelleştirilebilirler](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) .

## <a name="support-plan"></a>Destek Planı

Bir destek planı, uygun olan harika bir şeydir. Bir kişinin, HoloLens cihazlarda kayıt işleminin sorunlarını giderme ve aynı zamanda kuruluşunuzun içindeki HoloLens cihazının genel kullanımı konusunda eğitilen bir grup vardır. Kullanıcılarınızın sorunlarından daha hızlı çözümlenmesine izin vermek için, yükseltme işleminizin bu sırayla benzer bir şekilde işlenmesini öneririz:

1. Destek masanıza başvurun.
2. HoloLens uzman ekibiniz
3. [HoloLens belgeleri](https://docs.microsoft.com/hololens/)  /  [HoloLens sorunlarını giderme belgeleri](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Desteğe başvurun](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Geliştirme planı

Cihazınız başarıyla kaydedildikten sonra, cihazlarınıza Iş kolu uygulamaları (LOB uygulamaları) dağıtmaya hazırsınız demektir. Bunlar, kuruluşunuz&#39;ihtiyaçları için oluşturulmuş özel uygulamalardır.

Zaten bir iş kolu uygulamanız varsa, [UYGULAMANıZı MDM aracılığıyla dağıtmaya](https://docs.microsoft.com/hololens/app-deploy-intune)başlamaya&#39;. Farklı bir yöntemi tercih&#39;, daha sonra LOB uygulamanızı cihazlarınıza dağıtma hakkında daha fazla bilgi edinmek için, [HoloLens 2 için uygulama dağıtımına genel bakış](https://docs.microsoft.com/hololens/app-deploy-overview) konusunu gözden geçirin.

Kendi LOB uygulamanızı oluşturmanız veya hala oluşturma süreciyle karşılaşırsanız, karma gerçeklik geliştirme belgelerimizi inceleyerek [karma gerçeklik geliştirmesini](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr) kullanmaya başlamak için temel kavramları gözden geçirin [veya öğrenin](https://docs.microsoft.com/windows/mixed-reality/design/design) .&#39;

## <a name="device-management"></a>Aygıt Yönetimi 

Bu kılavuz, mobil cihaz yönetimi (MDM) ayarlama hakkında konuşurken cihaz kısıtlamalarını uygulamak için işe yaramadı veya cihazlara uygulandı. Cihaz yönetimi, sertifikaları ileterek erişime izin vermek veya çeşitli cihaz kısıtlamalarıyla erişimi kısıtlamak için kullanılabilir. 

Birçok durumda, cihazlarda Bluetooth, VPN, USB veya kamera ya da mikrofona erişimi kapatma gibi bağlantı kısıtlamaları olabilir. Bu ilgi alanlarından herhangi biri bundan sonra [ortak cihaz kısıtlamaları sayfasını](hololens-common-device-restrictions.md)okumanızı öneririz.

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları vardır. Örneğin:

- Settings uygulamasında görüntülenebilen sayfaları, [Settingspagevisibility](settings-uri-list.md)kullanarak, kullanıcıların yalnızca Wi-Fi bağlantılarını değiştirme gibi ayarlamak için ihtiyaç duydukları ayarlara erişmesine izin veren şekilde sınırlama.
- Bir cihazdaki kullanıcılara sunulan kullanıcı arabirimini sınırlamak için [bilgi noktası modunu](hololens-kiosk.md) kullanın. Kiosks 'i tek bir uygulama veya bir özel başlangıç sayfası ile birden çok uygulama gösterecek şekilde ayarlayabilirsiniz. Kiosks, farklı kullanıcılara farklı deneyimler de sunabilir.  
- Belirli uygulamaların veya işlemlerin tamamen başlatılmasını sağlamak için [Windows uygulama denetimi (WDAC)](windows-defender-application-control-wdac.md) .

Cihaz yönetimi veya cihaz kısıtlamalarının daha farklı yöntemleri hakkında daha fazla bilgi edinmek istiyorsanız, sonraki adıma geçin ve cihaz yönetimine genel bakış konusunu okuyun.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [CSP 'Leri ve cihaz yönetimine genel bakış](hololens-csp-policy-overview.md)