---
title: Dağıtım Kılavuzu – Dynamics 365 Kılavuzları ile kurumsal bağlantılı HoloLens 2 - Bakım
description: Dynamics 365 Kılavuzları ile kurumsal bir Bağlı ağ üzerinden HoloLens 2 cihazlarının bakımını yapmayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379056"
---
# <a name="maintain---corporate-connected-guide"></a>Bakım - Kurumsal Bağlantılı Kılavuz

## <a name="update-hololens"></a>HoloLens'i güncelleştirme

Microsoft İş İçin Windows Update, GÜNCELLEŞTIRMEleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemeye Windows Update bakım pencereleri tanımlama gibi ek Windows Update odaklı yönetim özellikleri sağlayacak şekilde tasarlanmıştır.

Güncelleştirmeleri yönetmenin popüler yöntemlerinden biri, 30 günlük bir özellik ertelemesi yapmaktır. Bu, Yöneticilerin yeni özellikleri güncelleştirmesine ve önizlemesine olanak sağlar, ilk el ile bilgi edinerek ve destek masanıza yeni değişiklikler hakkında bilgi verir.

[HoloLens güncelleştirmelerini](https://docs.microsoft.com/hololens/hololens-updates)yönetmeyi (zamanlanan günler, zamanlanan saat ve cihazda etkin saatleri ayarlama dahil) öğrenin; böylece cihaz çalışma saatleri dışında güncelleştirmesi yapılacaktır.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 Kılavuzlarını (ve diğer mağaza uygulamalarını) güncelleştirme

Dynamics 365 Kılavuzları, In-Box bir uygulamadır ve Microsoft Store güncelleştirilebilir. Uygulama aracılığıyla indirilen tüm uygulamalar Microsoft Store uygulamanın [kendisi aracılığıyla Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) güncelleştirilir.

## <a name="how-to-update-lob-apps"></a>LOB uygulamalarını güncelleştirme

LOB uygulamaları, Intune'a eklendikleri şekilde güncelleştirilebilir. Intune'da uygulamalar, mevcut Uygulama yapılandırmasına daha yüksek bir sürüm numarasıyla yeni uygulama yükleniyor şekilde güncelleştirilebilir. Cihaz Intune'a eşitlenirken, daha yeni bir uygulama sürümü olduğunu ve daha yeni bir uygulamanın indirilir ve eski uygulamanın yerini alır.

1. Yeni uygulamayı karşıya yüklemek için [MEM portalı](https://endpoint.microsoft.com/#home)Uygulamalar -> Tüm uygulamalar  ->     ->  *TheNameOfApp Properties'e*  ->  **gidin.**
2. Uygulama bilgileri'nin yanındaki Düzenle'yi **seçin.**
3. Güncelleştirilen dosya &quot; seç değerinin &quot; değeri olarak dosyanızı seçin.
4. Buradan bağlam menüsünü kullanarak dosya gezgininizi açın ve LOB uygulamasının yeni sürümünü karşıya yükleyin. Gerektiğinde bağımlılıkları dahil etmek için emin olmak.

Daha fazla bilgi: [HoloLens için Intune Uygulama Dağıtımı](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Geliştirme Planı

Cihazınız başarıyla kaydedildi. Artık cihazlarınıza daha fazla LOB uygulaması dağıtmaya hazır olursanız. Bu Kılavuz süresince bir örnek uygulama kullanıyoruz, ancak büyük olasılıkla, kuruluş ihtiyaçlarına göre özel uygulamalar kullanmak istemeniz daha olasıdır.

Zaten bir LOB uygulamanız varsa, uygulamanızı [MDM aracılığıyla dağıtmaya hazır olursanız.](https://docs.microsoft.com/hololens/app-deploy-intune) Farklı bir yöntem tercih ediyorsanız, LOB uygulamanızı cihazlarınıza dağıtmaya yönelik daha fazla yöntem hakkında daha fazla bilgi edinmek için [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) için uygulama dağıtımına genel bakış'ı gözden geçirebilirsiniz.

Henüz kendi LOB uygulamanızı oluşturmadıysanız veya hala oluşturma aşamasındaysanız karma gerçeklik geliştirme belgelerimizi gözden geçirerek karma gerçeklik geliştirmeyle çalışmaya başlamak için temel kavramları tasarlamaya ve bunun için [protokasyona](https://docs.microsoft.com/windows/mixed-reality/design/design) başlamaya veya temel kavramları öğrenmeye [başlayabilirsiniz.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Destek Planı

Destek planı, hazır olmak için harika bir şeydir. HoloLens cihazlarında kayıt sürecinde sorun giderme konusunda eğitilmiş birinin veya bir grubun olması ve ayrıca hololens cihazlarının kuruluş içindeki genel kullanımı yararlı olur. Kullanıcılarının sorunlarının daha hızlı çözüme sahip olmasına olanak vermek için, yükseltme işleminizin bu sırayla benzer şekilde ele uygulanmasını öneririz:

1. Destek masanız.
2. HoloLens Uzman takımınız
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [HoloLens Sorun Giderme Belgeleri](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [De destekle iletişime geçin](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Aygıt Yönetimi

Bu kılavuzda, Mobile Cihaz Yönetimi (MDM) ayarlama hakkında bilgi verildi ve bu kılavuzda bazı cihaz yapılandırmaları ayarlamak ve sertifikalar ve ara sunucu açısından erişime izin vermek Wi-Fi ayarları uygulamak için kullanıldı. Ancak, CSP'ler ve İlkeler aracılığıyla cihaz kısıtlamaları uygulamak için MDM de kullanılabilir.

Çoğu durumda cihazların Bluetooth, VPN, USB gibi bağlantı kısıtlamaları olabilir, hatta kameraya veya mikrofona erişimi kapatabilirsiniz. Bu sorunlardan herhangi biri sizi ilgilendirmeye devam ediyorsa, yaygın cihaz [kısıtlamaları sayfamızı okumanız için sizi teşvik etmektir.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları da vardır. Örneğin:

- [AyarlarSayfavisibility](https://docs.microsoft.com/hololens/settings-uri-list)kullanarak Ayarlar uygulamasında görüntülenecek sayfaları sınırlama, kullanıcıların yalnızca ayarlamaları gereken ayarlara erişmesine izin verir, örneğin kendi bağlantılarını Wi-Fi sağlar.
- Bir [cihazda kullanıcılara](https://docs.microsoft.com/hololens/hololens-kiosk) sunulan kullanıcı arabirimini sınırlamak için Bilgi Noktası modunu kullanın. Bilgi Noktası'nın tek bir uygulamayı veya özel başlangıç sayfası olan birden çok uygulamayı gösterecek şekilde ayarlaması gerekir. Bilgi noktası, farklı kullanıcılara farklı deneyimler de sunabilirsiniz.
- Belirli uygulamaların veya işlemlerin tamamen başlatılmasını tutmak için Windows Uygulama Denetimi [(WDAC).](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

Ek cihaz yönetimi yöntemleri veya cihaz kısıtlamaları hakkında bilgi edinmek için bir sonraki adıma geçin ve Genel Bakış [makalemizi Cihaz Yönetimi okuyun.](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





