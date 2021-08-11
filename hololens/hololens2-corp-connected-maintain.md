---
title: dağıtım kılavuzu – Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-koru
description: Dynamics 365 kılavuzlarıyla kurumsal bağlantılı ağ üzerinden HoloLens 2 cihazı nasıl koruyacağınızı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660276"
---
# <a name="maintain---corporate-connected-guide"></a>Bakım-kurumsal bağlantılı kılavuz

## <a name="update-hololens"></a>Güncelleştirme HoloLens

Microsoft, bt yöneticilerine, cihaz gruplarına güncelleştirme dağıtma ve güncelleştirme yüklemeye yönelik bakım pencerelerini tanımlama gibi ek Windows Update merkezli yönetim özellikleri sağlamak için Windows Update tasarlamıştır.

Güncelleştirmeleri yönetmenin popüler bir yöntemi, 30 günlük bir özellik ertelemeyi yapmak. Bu, yöneticilerin yeni özellikleri güncelleştirmesine ve önizlemesinin yanı sıra yeni değişiklikler hakkında bilgi edinme ve destek masanıza bilgi almasına olanak tanır.

zamanlanan günler ve zamanlanan süre dahil [HoloLens güncelleştirmelerini yönetmeyi](/hololens/hololens-updates)ve cihazdaki etkin saatleri ayarlamayı öğrenin, bu nedenle çalışma saatlerinin dışında güncelleştirilir.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 kılavuzlarını (ve diğer mağaza uygulamalarını) güncelleştirme

Dynamics 365 kılavuzlar bir In-Box uygulamasıdır ve Microsoft Store uygulama aracılığıyla güncelleştirilemeyebilir. Microsoft Store aracılığıyla indirilen tüm uygulamalar için, Microsoft Store uygulamanın kendisi tarafından el ile [güncelleştirilebilecek](/hololens/holographic-store-apps#update-apps) .

## <a name="how-to-update-lob-apps"></a>LOB uygulamalarını güncelleştirme

LOB uygulamaları, Intune 'a eklendikçe aynı şekilde güncelleştirilemeyebilir. Uygulamalar, daha yüksek bir sürüm numarasına sahip yeni uygulamayı var olan uygulama yapılandırmasına yükleyerek Intune 'da güncelleştirilebilen olabilir. Cihaz Intune 'a eşitlendikten sonra, daha yeni bir uygulama sürümü olduğu ve yeni uygulamanın indirileceği ve eski uygulamayı değiştirecek olduğunu gözlemleyeceksiniz.

1. Daha yeni uygulamayı karşıya yüklemek için, [mem portalı](https://endpoint.microsoft.com/#home)  ->  **uygulamalar** -uygulama özelliklerinden > tüm **uygulamalara** gidin  ->    ->  **.**
2. Uygulama bilgileri ' nin yanındaki Düzenle ' yi seçin **.**
3. &quot;Güncelleştirilecek Dosya Seç değeri için &quot; dosyanızı seçin.
4. Buradan, dosya Gezgini 'ni açmak ve LOB uygulamasının yeni sürümünü yüklemek için bağlam menüsünü kullanın. Gerektiğinde bağımlılıkları dahil edin.

Daha fazla bilgi [için bkz. HoloLens Için Intune uygulama dağıtımı](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Geliştirme planı

Cihazınız başarıyla kaydedildikten sonra cihazlarınıza daha fazla LOB uygulaması dağıtmaya hazırsınız demektir. Bu kılavuzun süresi boyunca örnek bir uygulama kullanıyoruz, ancak kuruluşunuzun ihtiyaçlarına göre derlenmiş özel uygulamalar kullanmak isteyeceksiniz.

Zaten bir LOB uygulamanız varsa, [UYGULAMANıZı MDM aracılığıyla dağıtmaya](/hololens/app-deploy-intune)hazırsınız demektir. farklı bir yöntemi tercih ediyorsanız, LOB uygulamanızı cihazlarınıza dağıtma hakkında daha fazla bilgi edinmek için [HoloLens 2 için uygulama dağıtımına genel bakış](/hololens/app-deploy-overview) konusunu gözden geçirin.

Kendi LOB uygulamanızı oluşturmanız veya hala oluşturma süreciyle karşılaşırsanız, karma gerçeklik geliştirme belgelerimizi inceleyerek [karma gerçeklik geliştirmesini](/windows/mixed-reality/discover/get-started-with-mr) kullanmaya [başlamak için temel](/windows/mixed-reality/design/design) kavramları inceleyin.

## <a name="support-plan"></a>Destek Planı

Bir destek planı, uygun olan harika bir şeydir. birisi veya bir grup olmak üzere HoloLens cihazlarda kayıt işleminin giderilmesi ve ayrıca kuruluşunuzda HoloLens cihazının genel kullanımı yararlı olur. Kullanıcılarınızın sorunlarından daha hızlı çözümlenmesine izin vermek için, yükseltme işleminizin bu sırayla benzer bir şekilde işlenmesini öneririz:

1. Destek masanıza başvurun.
2. HoloLens uzman ekibiniz
3. [HoloLens Docs](/hololens/)  /  [HoloLens sorunlarını giderme belgeleri](/hololens/hololens-troubleshooting)
4. [Desteğe başvurun](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Aygıt Yönetimi

Bu kılavuz, mobil cihaz yönetimi (MDM) ayarlama ve bu uygulamayı, bazı cihaz yapılandırmasını ayarlamak ve Wi-Fi sertifikaları ve proxy 'nin koşullarına erişim sağlamak için ayarları uygulamak üzere kullanır. Ancak MDM, CSP ve Ilkeler aracılığıyla cihaz kısıtlamalarını uygulamak için de kullanılabilir.

birçok durumda, cihazların Bluetooth, VPN, USB gibi bağlantı kısıtlamalarına sahip olması ve hatta kameraya veya mikrofona erişimi kapatmaları olabilir. Bu ilgi alanlarından herhangi biri sizi ilgilendiren [ortak cihaz kısıtlamaları sayfasını](/hololens/hololens-common-device-restrictions)okumanızı öneririz.

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları vardır. Örneğin:

- [settingspagevisibility](/hololens/settings-uri-list)' ı kullanarak Ayarlar uygulamasında görüntülenebilen sayfaları sınırlandırma, kullanıcıların, Wi-Fi bağlantılarını değiştirme gibi yalnızca ayarlamalarına ihtiyacı olan ayarlara erişmesini sağlar.
- Bir cihazdaki kullanıcılara sunulan kullanıcı arabirimini sınırlamak için [bilgi noktası modunu](/hololens/hololens-kiosk) kullanın. Kiosks 'i tek bir uygulama veya bir özel başlangıç sayfası ile birden çok uygulama gösterecek şekilde ayarlayabilirsiniz. Kiosks, farklı kullanıcılara farklı deneyimler de sunabilir.
- belirli uygulamaların veya işlemlerin tamamen başlatılmasını sağlamak için [uygulama denetimi (WDAC) Windows](/hololens/windows-defender-application-control-wdac) .

Cihaz yönetimi veya cihaz kısıtlamalarının ek yöntemleri hakkında daha fazla bilgi edinmek istiyorsanız, sonraki adıma geçin ve [cihaz yönetimine genel bakış](/hololens/hololens-csp-policy-overview)konusunu okuyun.





