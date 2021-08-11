---
title: Genel Bakış-uygulama yönetimi
description: Mobil cihaz yönetimi, iş için Microsoft Mağazası ve sağlama paketleri ile karma gerçeklik uygulama yönetimine genel bir bakış ile çalışmaya başlayın.
keywords: HoloLens, kullanıcı, hesap, uygulama, uygulama yönetimi,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 019700c7e35f31c234c9fe69870cae54b3364b631253c37a17d8eaa0fe3053bd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665242"
---
# <a name="app-management-overview"></a>Uygulama Yönetimi: genel bakış

farklı yollarla uygulama dağıtabilirsiniz: **mobil cihaz yönetimi (MDM)**, **İş İçin Microsoft Store**, **Microsoft Store** veya **sağlama** aracılığıyla yükleyebilirsiniz.

## <a name="mobile-device-management-mdm"></a>Mobil cihaz yönetimi (MDM)

Bir MDM çözümü, BT karar mekanizmalarının ve yöneticilerin şirket içi, iş kolu uygulamalarını veya mağaza aracılığıyla uygulama satın almasını (bir Kullanıcı grubu için) sağlar. HoloLens cihazlar [uygulama yönetimi](app-deploy-intune.md)için en iyi Microsoft Endpoint Manager (ıntune) ile çalışır. ıntune ayrıca, Şirket Portalı indirilebilir deneyim aracılığıyla kullanıcılara, bt tarafından yönetilen uygulamalar üzerinde daha ayrıntılı denetim sağlar.

> [!NOTE]
> Aşağıdaki yönergeler, uygulamalarını Intune ile yönetmek isteyen kullanıcılar içindir. Microsoft, uygulama ve cihaz yönetimi için Intune kullanmayı önerir.

Mobil cihaz yönetimi (MDM) şunları için geçerlidir:

* MDM dağıtılan + Şirket Portalı
* Iş kolu (genel olmayan) uygulamalar
* Şirket Portalı aracılığıyla kullanılabilir uygulamaların el ile yüklenmesi
* MDM ilkesi aracılığıyla yönetici gönderimi
* MDM üzerinden otomatik güncelleştirme

## <a name="microsoft-store-for-business"></a>İş İçin Microsoft Store

[İş İçin Microsoft Store](app-deploy-store-business.md) , bt karar mekanizmalarının ve işletmelerin ücretsiz ve ücretli uygulamaları bulmasını, almalarını, yönetmesi ve dağıtmalarını sağlar. bt yöneticileri, Microsoft Store uygulamalarını ve özel iş kolu uygulamalarını tek bir envanterde yönetebilir, ayrıca gerektiğinde lisansları atayabilir ve yeniden kullanabilirsiniz. daha fazla bilgi için [İş İçin Microsoft Store kullanmaya yönelik önkoşulları](/microsoft-store/prerequisites-microsoft-store-for-business)ziyaret edin.

İş İçin Microsoft Store için geçerlidir:

* Kamu veya Iş kolu uygulamaları
* MDM ilişkilendirmesi aracılığıyla gerekli uygulamaların otomatik yüklemesi
* Kullanıcı uygulamaları el ile indirir
* Otomatik güncelleştirme

## <a name="microsoft-store-apps"></a>Microsoft Mağazası uygulamaları

Microsoft Store, bt karar mekanizmalarının ve işletmelerin ortak uygulamaları bulmasını, almalarını, yönetmesini ve dağıtmasını sağlar.

bu Microsoft Store için geçerlidir:

* Yalnızca ortak uygulamalar
* Kullanıcı uygulamaları el ile indirir
* Internet 'e bağlıysa otomatik güncelleştirme

Daha fazla bilgi için [holographic Store Apps](/hololens/holographic-store-apps)sayfasını ziyaret edin.

## <a name="install-via-provisioning-packages"></a>Sağlama paketleri aracılığıyla yüklemesi

[Sağlama paketleri](app-deploy-provisioning-package.md) , BT uzmanlarının ve YÖNETICILERIN uygulamaları USB üzerinden yerel cihazlara hızlıca yüklemesini sağlayan özel veya iş kolu uygulamaları yüklemenize imkan tanır. Bu yükleme, bir internet bağlantısı ve herhangi bir kimlik türü olmadan yapılabilir.

Sağlama paketleri aracılığıyla yükleme şunları için geçerlidir:

* Iş kolu/kendi kendine geliştirilmiş (ortak olmayan) uygulamalar
* Ortak uygulamalar (çevrimdışı yükleyici varsa)
* Yalnızca USB dışarıdan yükleme
* Otomatik güncelleştirme yok (sağlama paketi aracılığıyla el ile güncelleştirmeler gerektirir)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme

[Uygulama yükleyicisi](app-deploy-app-installer.md) kullanıcılarının kullanılması, yerel cihazlara uygulama yüklemek veya bir uygulamayı, Hololens diğer uygulama yükleme yöntemlerini bilmediğiniz başka biriyle paylaşmak için basit bir deneyimle sahip olabilir. Bu işlem, geliştirici modunun etkinleştirilmesi veya cihaz portalı kullanılması gerekmeden yapılabilir. Bu, tamamen oluşturulmuş bir uygulamayı dağıtmanın basit bir yöntemidir. uygulamanızı yalnızca bir HoloLens başka bir kullanıcıya tanıtıyor veya uygulamanızı dağıtmak istediğinizde, bu yöntem kolayca işe yarar.

Uygulama yükleyicisi aracılığıyla yükleme şunları için geçerlidir:

* Iş kolu/kendi kendine geliştirilmiş (ortak olmayan) uygulamalar
* Yalnızca dışarıdan yükleme
* Geliştirici modu veya cihaz portalı gerektirmez
* Son kullanıcının yüklemesi kolay
