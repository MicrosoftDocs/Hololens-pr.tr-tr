---
title: Dağıtım Kılavuzu – Dynamics 365 HoloLens 2 ile kurumsal bağlantılı bağlantı - Bakım
description: Dynamics 365 kılavuzları HoloLens bağlı bir ağ üzerinden 2 cihazı nasıl koruyabilirsiniz?
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428102"
---
# <a name="maintain---corporate-connected-guide"></a>Bakım - Kurumsal Bağlantılı Kılavuz

## <a name="update-hololens"></a>Güncelleştirme HoloLens

Microsoft, Windows güncelleştirmeleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemek için bakım pencerelerini tanımlama gibi ek Windows Güncelleştirme odaklı yönetim özellikleri sağlamak için İş için Güncelleştirme'yi tasarladı.

Güncelleştirmeleri yönetmenin popüler yöntemlerinden biri, 30 günlük bir özellik ertelemesi yapmaktır. Bu, Yöneticilerin yeni özellikleri güncelleştirmesine ve önizlemesine olanak sağlar, ilk el ile bilgi edinerek ve destek masanıza yeni değişiklikler hakkında bilgi verir.

Cihazda [zamanlanan HoloLens,](/hololens/hololens-updates)zamanlanmış saat ve etkin saatleri ayarlama dahil olmak üzere cihaz güncelleştirmelerini yönetmeyi öğrenin; böylece cihaz çalışma saatleri dışında güncelleştirmesi yapılacaktır.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Dynamics 365 Kılavuzlarını (ve diğer mağaza uygulamalarını) güncelleştirme

Dynamics 365 Kılavuzları, In-Box bir uygulamadır ve Microsoft Store güncelleştirilir. Uygulama aracılığıyla indirilen tüm uygulamalar Microsoft Store uygulamanın [kendisi aracılığıyla Microsoft Store](/hololens/holographic-store-apps#update-apps) güncelleştirilir.

## <a name="how-to-update-lob-apps"></a>LOB uygulamalarını güncelleştirme

LOB uygulamaları, Intune'a eklendikleri şekilde güncelleştirilebilir. Yeni uygulama, mevcut Uygulama yapılandırmasına daha yüksek bir sürüm numarasıyla yükleniyor ve Intune'da güncelleştirilebilir. Cihaz Intune'a eşitlenirken, daha yeni bir uygulama sürümü olduğunu ve daha yeni bir uygulamanın indirilir ve eski uygulamanın yerini alır.

1. Yeni uygulamayı karşıya yüklemek için [MEM portalı](https://endpoint.microsoft.com/#home)Uygulamalar -> Tüm uygulamalar  ->     ->  *TheNameOfApp Properties'e*  ->  **gidin.**
2. Uygulama bilgileri'nin yanındaki Düzenle'yi **seçin.**
3. Güncelleştirilen dosya &quot; seç değerinin &quot; değeri olarak dosyanızı seçin.
4. Buradan bağlam menüsünü kullanarak dosya gezgininizi açın ve LOB uygulamasının yeni sürümünü karşıya yükleyin. Gerektiğinde bağımlılıkları dahil etmek için emin olmak.

Daha fazla bilgi: [HoloLens için Intune Uygulama Dağıtımı](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Geliştirme Planı

Cihazınız başarıyla kaydedildi. Artık cihazlarınıza daha fazla LOB uygulaması dağıtmaya hazır olursanız. Bu Kılavuz süresince bir örnek uygulama kullanıyoruz, ancak büyük olasılıkla, kuruluş ihtiyaçlarına göre özel uygulamalar kullanmak istemeniz daha olasıdır.

Zaten bir LOB uygulamanız varsa, uygulamanızı [MDM aracılığıyla dağıtmaya hazır olursanız.](/hololens/app-deploy-intune) Farklı bir yöntem tercih ediyorsanız, LOB uygulamanızı cihazlarınıza dağıtmaya yönelik [daha fazla HoloLens için HoloLens 2'ye](/hololens/app-deploy-overview) yönelik uygulama dağıtımına genel bakış'ı gözden geçirebilirsiniz.

Henüz kendi LOB uygulamanızı oluşturmadıysanız veya hala oluşturma aşamasındaysanız karma gerçeklik geliştirme belgelerimizi gözden geçirerek karma gerçeklik geliştirmeyle çalışmaya başlamak için tasarım ve [protokasyon](/windows/mixed-reality/design/design) yapmaya veya temel kavramları öğrenmeye [başlayabilirsiniz.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Destek Planı

Destek planı, hazır olmak için harika bir şeydir. Bir kişinin veya grubun, HoloLens cihazlarda kayıt işlemiyle ilgili sorun giderme konusunda eğitilmiş olması ve HoloLens cihazın da genel olarak kullanımı yararlı olur. Kullanıcılarının sorunlarının daha hızlı çözüme sahip olmasına olanak vermek için, yükseltme işleminizin bu sırayla benzer şekilde ele uygulanmasını öneririz:

1. Destek masanız.
2. HoloLens Uzman takımınız
3. [HoloLens Docs](/hololens/)  /  [HoloLens Sorun Giderme Belgeleri](/hololens/hololens-troubleshooting)
4. [De destekle iletişime geçin](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Aygıt Yönetimi

Bu kılavuzda Mobile Cihaz Yönetimi (MDM) ayarlama hakkında bilgi edinildi ve bu kılavuzda bazı cihaz yapılandırmaları ayarlamak ve sertifikalar ve ara sunucu açısından erişime izin vermek Wi-Fi ayarları uygulamak için kullanıldı. Ancak MDM, CSP'ler ve İlkeler aracılığıyla cihaz kısıtlamaları uygulamak için de kullanılabilir.

Çoğu durumda cihazların bağlantı kısıtlamaları olabilir; örneğin Bluetooth, VPN, USB, hatta kameraya veya mikrofona erişimi kapatma. Bu sorunlardan herhangi biri sizi ilgilendirmeye devam ediyorsa, yaygın cihaz kısıtlamaları [sayfamızı okumanız teşvik edilecektir.](/hololens/hololens-common-device-restrictions)

Kullanabileceğiniz başka karmaşık cihaz kısıtlamaları da vardır. Örneğin:

- Ayarlar uygulamasında görüntülenecek sayfaları, [AyarlarSayfaVisibility](/hololens/settings-uri-list)kullanarak sınırlandırarak, kullanıcıların yalnızca kendi bağlantılarını değiştirme gibi ayarlamaları gereken ayarlara erişmesine Wi-Fi sağlar.
- Bir [cihazda kullanıcılara](/hololens/hololens-kiosk) sunulan kullanıcı arabirimini sınırlamak için Bilgi Noktası modunu kullanın. Bilgi Noktası'nın tek bir uygulamayı veya özel başlangıç sayfası olan birden çok uygulamayı gösterecek şekilde ayarlaması gerekir. Bilgi noktası, farklı kullanıcılara farklı deneyimler de sunabilirsiniz.
- [Windows veya işlemlerin tamamen başlatılmasını](/hololens/windows-defender-application-control-wdac) tutmak için Uygulama Denetimi'ne (WDAC) tıklayın.

Ek cihaz yönetimi veya cihaz kısıtlama yöntemleri hakkında bilgi edinmek için bir sonraki adıma geçin ve Genel Bakış [makalemizi Cihaz Yönetimi okuyun.](/hololens/hololens-csp-policy-overview)





