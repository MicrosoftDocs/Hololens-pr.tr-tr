---
title: Dosyanızı HoloLens kişi ile paylaşma
description: Birden çok HoloLens hesabı veya tek bir Azure Active Directory birden çok kullanıcı tarafından paylaşılacak şekilde yapılandırabilirsiniz.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428200"
---
# <a name="share-your-hololens-with-multiple-people"></a>Dosyanızı HoloLens kişi ile paylaşma

## <a name="overview"></a>Genel Bakış
İşletmeler genellikle birçok paylaşılan cihaza HoloLens yatırımlar. Uygulama gereksinimlerinize HoloLens bağlı olarak yönetim kurulu genelinde esnektir. Çok kullanıcılı deneyimlere örnek olarak aşağıdaki örneklerden biri: 

- Ücret alınan ve Dynamics 365 Kılavuzlarına sahip olan ve çalışanlarının Wi-Fi'da ayarlama yapmak için Ayarlar uygulamasını açmasına olanak sağlayan cihazlar, ancak Sayfa Ayarlar Görünürlük ilkesi, Ayarlar uygulamasında kullanılabilir sayfa miktarını sınırlamak için etkinleştirilir.
- Remote Assist'e ve diğer şirketlere kiralanan iş hattı uygulamanıza uygun cihazlar. Bu cihazlarda yalnızca sizin ve Remote Assist'in yer alan Bilgi Noktası vardır. WDAC, uygulamanın Ayarlar ve Microsoft Edge için kullanılır. Kiralama hizmetine dahil edilen USB-C pil paketi, birden fazla vardiyada cihazları tam ücret ödemeye devam ediyor.
- Tüm cihazlarınız Autopilot için ayarlanır ve tüm şirket uygulamalarınızı indirir. Farklı Azure AD gruplarını hedef alan birkaç farklı Bilgi Noktası profili ayarlayabilirsiniz. Her kullanıcı FIDO2 anahtarlarını HoloLens kendi Azure AD hesabında oturum açtığında oturum açtığında özel bir deneyim sunar.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Her biri kendi hesabını kullanarak birden çok kişi ile paylaşma

Önkoşul: HoloLens cihazın 1803 Windows 10 sonraki bir sürümde çalışıyor olması gerekir.  HoloLens (1. nesil) de [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Kendi Azure Active Directory (Azure AD) hesaplarını kullanan kullanıcıların her biri cihazda kendi kullanıcı ayarlarını ve kullanıcı verilerini tutabilirsiniz.

Birden çok kişinin kendi hesaplarını kendi hesaplarınızı HoloLens emin olmak için aşağıdaki adımları izleyin:

1. Cihazın 1803 veya Windows 10 çalıştırıla olduğundan emin olun.
   > [!IMPORTANT]
   > HoloLens (1. nesil) cihazı kullanıyorsanız, [cihazı](hololens1-upgrade-enterprise.md)Windows Holographic for Business.
1. Cihazı ayarsanız, cihazı iş veya okul **sahibim'i seçin ve** bir Azure AD hesabı kullanarak oturum açın.
1. Kurulumu tamamladikten sonra, hesap ayarlarının **(Ayarlar** Hesapları ) Diğer kullanıcılar  >  olduğundan **emin olun.**

Bu HoloLens için her kullanıcı şu adımları izler:

1. Cihazı başka bir kullanıcı kullanıyorsa aşağıdaki seçeneklerden birini belirleyin:
   - Bekleme moduna dönmek için güç düğmesine bir kez basın ve ardından kilit ekranına dönmek için güç düğmesine tekrar basın
   - HoloLens 2 kullanıcı, geçerli kullanıcının oturumlarını Başlat menüsü kullanıcı kutucuğunu seçerek kullanıcı kutucuğunu seçenin.

1. Cihazda oturum açma için Azure AD hesabı kimlik bilgilerinizi kullanın.  
    Cihazı ilk kez kullandıysanız, cihazı kendi HoloLens [](hololens-calibration.md) ayarlamanız gerekir.

Cihaz kullanıcılarının listesini görmek veya bir kullanıcıyı cihazdan kaldırmak için Ayarlar  >  **Diğer kullanıcılar'a**  >  **gidin.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Hepsi aynı hesabı kullanarak birden çok kişi ile paylaşma

Ayrıca, tek bir kullanıcı HoloLens birden çok kullanıcı bir cihaz paylaşabilir.

**HoloLens 2'de,** yeni bir kullanıcı cihazı ilk kez başına koyarken (aynı hesabın oturum açık olduğu sırada), cihaz yeni kullanıcıdan görüntüleme deneyimini hızla ayarlamasını ve kişiselleştirmesini istenir. Cihaz, gelecekte her kullanıcının görüntüleme deneyiminin kalitesini ve rahatsını otomatik olarak iyileştirecek şekilde, ayar bilgilerini depolar. Kullanıcıların cihazı yeniden ayarlaması gerek değildir.

**Bir HoloLens (1. nesil)** kullanıcıları, hesap paylaşım uygulamasında yeniden ölçeklendirme Ayarlar gerekir.  Ayarlama hakkında daha fazla [bilgi edinin.](hololens-calibration.md)