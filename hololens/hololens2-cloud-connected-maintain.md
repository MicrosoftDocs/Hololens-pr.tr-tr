---
title: Dağıtım Kılavuzu – Remote Assist ile buluta HoloLens 2 dağıtım - Bakım
description: Buluta Bağlı ağ üzerinden cihazların bakımını ve destekle HoloLens ipuçlarımızı takip edin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428036"
---
# <a name="maintain---cloud-connected-guide"></a>Bakım - Buluta bağlı Kılavuz

## <a name="updates"></a>Güncelleştirmeler

Microsoft, Windows güncelleştirmeleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemek için bakım pencerelerini tanımlama gibi ek Windows Güncelleştirme odaklı yönetim özellikleri sağlamak için İş için Güncelleştirme'yi tasarladı.

Zamanlanan [gün, HoloLens dahil olmak](/hololens/hololens-updates) üzere cihaz güncelleştirmelerini yönetmeyi ve cihazda etkin saatleri çalışma saatleri dışında güncelleştirilecek şekilde ayarlamayı öğrenin.

Remote Assist, In-Box bir uygulamadır ve bu uygulama aracılığıyla Microsoft Store olabilir. Uygulama aracılığıyla indirilen tüm uygulamalar Microsoft Store uygulamanın [kendisi aracılığıyla Microsoft Store](/hololens/holographic-store-apps#update-apps) güncelleştirilir.

## <a name="support-plan"></a>Destek Planı

Destek planı, hazır olmak için harika bir şeydir. Bir kişinin veya grubun, HoloLens cihazlarda kayıt işlemiyle ilgili sorun giderme konusunda eğitilmiş olması ve HoloLens cihazın genel olarak kullanımı yararlı olur. Kullanıcılarının sorunlarının daha hızlı çözüme sahip olmasına olanak vermek için, yükseltme işleminizin bu sırayla benzer şekilde ele uygulanmasını öneririz:

1. Destek masanız.
2. HoloLens Uzman takımınız
3. [HoloLens Docs](/hololens/)  /  [HoloLens Sorun Giderme Belgeleri](/hololens/hololens-troubleshooting)
4. [De destekle iletişime geçin](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Geliştirme Planı

Cihazınız başarıyla kaydedildi. Artık cihazlarınıza İş Hattı uygulamalarını (LOB uygulamaları) dağıtmaya hazır olursanız. Bunlar, kendi ihtiyaçlarına uygun olarak,&#39;uygulamalardır.

Zaten bir iş hattı uygulamanız varsa,&#39;MDM aracılığıyla dağıtmaya [hazır olursanız.](/hololens/app-deploy-intune) Farklı&#39;tercih ediyorsanız, LOB uygulamanızı cihazlarınıza dağıtmaya yönelik daha fazla yöntem hakkında daha fazla bilgi edinmek [için HoloLens 2](/hololens/app-deploy-overview) için uygulama dağıtımına genel bakış'ı gözden geçirebilirsiniz.

Henüz&#39;lob uygulamanızı oluşturmadıysanız veya hala oluşturma aşamasındaysanız karma gerçeklik geliştirme belgelerimizi gözden geçirerek karma gerçeklik geliştirmeyle çalışmaya başlamak için tasarım ve [protokasyon](/windows/mixed-reality/design/design) yapmaya veya temel kavramları öğrenmeye [başlayabilirsiniz.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Aygıt Yönetimi 

Bu kılavuzda Mobile Cihaz Yönetimi (MDM) ayarlamadan söz ediliyordu ancak cihazlara cihaz kısıtlamalarını veya ilkelerini uygulamak için uygulanmadı. Cihaz yönetimi, sertifikalar ile erişime izin vermek veya çeşitli cihaz kısıtlamalarıyla erişimi kısıtlamak için kullanılabilir. 

Çoğu durumda cihazlarda Bluetooth, VPN, USB, hatta kameraya veya mikrofona erişimi kapatma gibi bağlantı kısıtlamaları olabilir. Bu ilgi alanlarına sahip olursanız, yaygın cihaz kısıtlamaları [sayfamızı okumanız teşvik edilecektir.](hololens-common-device-restrictions.md)

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları da vardır. Örneğin:

- Ayarlar uygulamasında görüntülenecek sayfaları, [AyarlarSayfaVisibility](settings-uri-list.md)kullanarak sınırlandırarak, kullanıcıların yalnızca kendi bağlantılarını değiştirme gibi ayarlamaları gereken ayarlara erişmesine Wi-Fi sağlar.
- Bir [cihazda kullanıcılara](hololens-kiosk.md) sunulan kullanıcı arabirimini sınırlamak için Bilgi Noktası modunu kullanın. Bilgi Noktası'nın tek bir uygulamayı veya özel başlangıç sayfası olan birden çok uygulamayı gösterecek şekilde ayarlaması gerekir. Bilgi noktası, farklı kullanıcılara farklı deneyimler de sunabilirsiniz.  
- Windows uygulama veya işlemlerin tamamen başlatılmasını tutmak için Uygulama Denetimi'ne [(WDAC)](windows-defender-application-control-wdac.md) tıklayın.

Farklı cihaz yönetimi veya cihaz kısıtlama yöntemleri hakkında daha fazla bilgi edinmek için bir sonraki adıma geçin ve Genel Bakış makalemizi Cihaz Yönetimi okuyun.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [CSP'leri ve Cihaz Yönetimi Genel Bakış'Cihaz Yönetimi okuyun](hololens-csp-policy-overview.md)