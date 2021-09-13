---
title: Genel Bakış - Uygulama Yönetimi
description: Kullanmaya başlayın cihaz yönetimi, iş için Microsoft Mağazası ve paket sağlama ile karma gerçeklik uygulama yönetimine genel bir bakış sunar.
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033067"
---
# <a name="app-management-overview"></a>Uygulama Yönetimi: Genel Bakış

Uygulamaları dört farklı yola dağıtabilirsiniz: **Mobil Cihaz Yönetimi (MDM)**, **İş İçin Microsoft Store**, **Microsoft Store** veya Sağlama aracılığıyla **yükleyerek.**

## <a name="mobile-device-management-mdm"></a>Mobil Cihaz Yönetimi (MDM)

MDM çözümü, IT kararlarını verenlerin ve yöneticilerin bir grup kullanıcı için mağaza üzerinden kendi kendi iş hattı uygulamalarını özel olarak otomatik olarak yüklemesini (yüklemesini) veya uygulama satın almalarını sağlar. HoloLens cihazlar uygulama yönetimi için Microsoft Endpoint Manager (Intune) ile [en iyi şekilde çalışır.](app-deploy-intune.md) Intune ayrıca kullanıcılara indirilebilir deneyim aracılığıyla IT tarafından yönetilen uygulamalar üzerinde daha Şirket Portalı denetim sunar.

> [!NOTE]
> Aşağıdaki yönergeler, uygulamalarını Intune ile yönetmek isteyen kullanıcılara ilişkindir. Microsoft, uygulama ve cihaz yönetimi için Intune'un kullanılması önerilir.

Mobil Cihaz Yönetimi (MDM) şu uygulamalar için geçerlidir:

* Dağıtılan MDM + Şirket Portalı
* İş Hattı (genel olmayan) uygulamalar
* Şirket Portalı aracılığıyla kullanılabilir uygulamaların el ile yüklenmesi
* MDM ilkesi aracılığıyla yönetici anında iletme
* MDM aracılığıyla otomatik güncelleştirme

## <a name="microsoft-store-for-business"></a>İş İçin Microsoft Store

Bu [İş İçin Microsoft Store,](app-deploy-store-business.md) işletmelerde ücretsiz ve ücretli uygulamaları bulmaları, edinmeleri, yönetmeleri ve dağıtmaları için IŞLETMELERDE KARAR VERENLER ve yöneticiler sağlar. IT yöneticileri, Microsoft Store uygulamaları ve özel iş hattı uygulamalarını tek bir envanterde yönetebilir ve gerektiğinde lisansları atap yeniden kullanabilir. Daha fazla bilgi için [önkoşullar'ı ziyaret edin ve İş İçin Microsoft Store.](/microsoft-store/prerequisites-microsoft-store-for-business)

Aşağıdaki İş İçin Microsoft Store için geçerlidir:

* Genel veya İş Hattı uygulamaları
* MDM ilişkilendirmesi aracılığıyla gerekli uygulamaların otomatik olarak yüklenmesi
* Kullanıcı uygulamaları el ile indirir
* Otomatik Güncelleştirme

## <a name="microsoft-store-apps"></a>Microsoft Mağazası uygulamaları

Bu Microsoft Store, genel uygulamaları bulmaları, edinmeleri, yönetmeleri ve dağıtmaları için işletmelerde IŞ kararlarını veren kullanıcılara ve yöneticilere sağlar.

Bu Microsoft Store şu için geçerlidir:

* Yalnızca genel uygulamalar
* Kullanıcı uygulamaları el ile indirir
* İnternet'e bağlı ise otomatik güncelleştirme

Daha fazla bilgi için [Holographic Store Apps'i ziyaret edin.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Paketleri Sağlama yoluyla yükleme

[Paketleri Sağlama,](app-deploy-provisioning-package.md) özel veya İş Hattı uygulamalarını yüklemenize olanak sağlayarak, IT profesyonellerinin ve yöneticilerin USB aracılığıyla uygulamaları yerel bir cihaza hızla yüklemesine olanak sağlar. Bu yükleme bir İnternet bağlantısı olmadan ve herhangi bir kimlik türü için yapılabilir.

Sağlama Paketleri aracılığıyla yükleme şu için geçerlidir:

* İş Hattı / Kendi kendine geliştirilen (genel olmayan) uygulamalar
* Genel uygulamalar (çevrimdışı yükleyici varsa)
* Yalnızca USB tarafı yükleme
* Otomatik güncelleştirme yok (Sağlama Paketi aracılığıyla el ile güncelleştirme gerektirir)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama Yükleyicisi aracılığıyla HoloLens 2.Uygulama Yükleyicisi

Bu [Uygulama Yükleyicisi](app-deploy-app-installer.md) kullanıcılar, uygulamaları yerel cihazlara yüklemek veya uygulama üzerinde diğer uygulama yükleme yöntemlerine yabancı olan başka bir kullanıcıyla paylaşmak için basit bir deneyim HoloLens. Bu, Geliştirici Modunu etkinleştirmeye veya bu modu kullanmaya gerek kalmadan Cihaz Portalı. Bu, tamamen yerleşik bir uygulamayı dağıtmanın basit bir yöntemidir. Uygulamanızı yalnızca bir kullanıcıya bir HoloLens veya uygulamanızı dağıtmak istediğinizden bağımsız olarak bu yöntem kolayca çalışır.

Uygulama Yükleyicisi yüklemesi şu için geçerlidir:

* İş Hattı / Kendi geliştirdiği (genel olmayan) uygulamalar
* Yalnızca yan yükleme
* Geliştirici modu veya Cihaz portalı gerektirmez
* Son kullanıcının yüklemesi kolay
