---
title: Birden çok HoloLens kullanıcıyla dosyanızı paylaşma
description: Birden çok HoloLens hesabı veya tek bir Azure Active Directory birden çok kullanıcı tarafından paylaşılacak şekilde yapılandırabilirsiniz.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600738"
---
# <a name="share-your-hololens-with-multiple-people"></a>Birden çok HoloLens kullanıcıyla dosyanızı paylaşma

## <a name="overview"></a>Genel Bakış

İşletmeler genellikle birçok paylaşılan cihaza HoloLens yatırımlar. Uygulama gereksinimlerinize HoloLens bağlı olarak yönetim panosunda esnek bir şekilde kullanabilirsiniz. Çok kullanıcılı deneyimlere örnek olarak:

- HoloLens HoloLens 2 için Windows Autopilot aracılığıyla, her cihazda tutarlı bir şirket uygulaması portföyüyle bir HoloLens 2 cihaz filosu ayarlanır. Farklı Azure AD gruplarını hedef alan birkaç farklı Bilgi Noktası profili ayarlayabilirsiniz. Her kullanıcı FIDO2 anahtarlarını HoloLens kendi Azure AD hesabında oturum açtığında oturum açtığında özel bir deneyim sunar.
- Bağımsız bir yazılım satıcısı (ISV), D365 Remote Assist ile HoloLens 2 Cihazları ve bunların iş hattı (LOB) uygulamasını müşterinin şirketine kiralar. Bu cihazlar yalnızca lob uygulamasını ve Remote Assist'i içeren bilgi noktası için yapılandırılır ve birden çok son kullanıcı arasında paylaşılır. WDAC, uygulamanın Ayarlar başlatılmasını Microsoft Edge için kullanılır. Kiralama hizmetine dahil edilen USB-C pil paketi, birden fazla vardiyada cihazları tam ücret ödemeye devam ediyor.
- Bir kuruluşta son kullanıcı yeni bir cihaza bağlanacak şekilde cihaz Bluetooth ayarlamalar yapmaya çalışır, ancak Sayfa Ayarlar Görünürlüğü ilkesi Cihazlar sayfasının görüntülemesini sınırlamak için etkinleştirilir. Remote Assist'i aynı verilerle birden çok konumda Wi-Fi için gerektiğinde diğer sayfalara erişmelerine izin HoloLens.

## <a name="best-practices"></a>En iyi uygulamalar

Cihazlarınızı paylaşmayı planlarken, cihaz ortamınızı iş ihtiyaçlarına göre en iyi duruma getirmek için dikkat edilmesi gereken birkaç nokta vardır.

- [Kimlik ve Kimlik Doğrulama](#identity-and-authentication)
- [Cihaz Yönetimi](#device-management)
- [Gelişmiş cihaz yönetimi - Bilgi noktası ve WDAC](#advanced-device-management---kiosk-and-wdac)
- [Fiziksel Yönetim](#physical-management)

### <a name="identity-and-authentication"></a>[Kimlik ve Kimlik Doğrulama](hololens-identity.md)

Cihazda birden çok hesap olması plansanız tüm kimlik doğrulama modlarına sahip Azure AD hesaplarınız olur. Bu kimlik doğrulama yöntemleri, Iris ve [FIDO2 Windows Hello](/windows-hardware/design/device-experiences/windows-hello)dahil olmak üzere temel alınan kimlik doğrulama yöntemlerine dayalıdır.

- FIDO 2 Birden çok cihazınız, çok sayıda kullanıcınız varsa veya sürekli olarak yeni cihazlar kullanıyorsanız güvenlik anahtarları mükemmeldir.
- 10 veya daha az kullanıcınız varsa Iris, aynı cihazda daha önce oturum açmış olan kullanıcıların oturum açması için hızlı bir çözümdür.

### <a name="device-management"></a>[Cihaz Yönetimi](hololens-csp-policy-overview.md)

Cihazlar kullanıcılar arasında paylaşılıyorsa, büyük olasılıkla cihaz kısıtlamalarını kullanmak istersiniz. Cihaz yönetimini kullanarak, kullanıcılarının cihazı kullanmalarını, güncelleştirmeleri yönetmelerini veya cihazın neler yapalarını sınırlamalarını daha iyi sağlayacak bazı ilkeler kullanabilirsiniz. Yaygın cihaz kısıtlamalarımızı gözden [geçirmeniz ve bu](hololens-common-device-restrictions.md)önerilerin kuruluşa uygun görünp görünmediğinize bakabilirsiniz. Hangi ilkeleri kullanmak istediğinize karar verdiktan sonra, [bunları Microsoft'un Endpoint Manager (MDM) veya](hololens-mdm-configure.md) sağlama paketleri aracılığıyla uygulayabilirsiniz.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Gelişmiş cihaz yönetimi - [Bilgi noktası](hololens-kiosk.md) ve [WDAC](windows-defender-application-control-wdac.md)

Bazı durumlarda, son kullanıcılar tarafından erişilebilen uygulamaları sınırlamak istemeyebilirsiniz. Başlangıç menüsünde Bilgi Noktası modunu kullanarak kullanıcıların hangi uygulamalarla karşıldırılacaklarını [sınırlandırıyor olabilirsiniz.](hololens-kiosk.md) Bilgi noktası kullanıcı, Azure grupları veya özel kullanıcı türlerine göre farklı başlangıç menüleri sunmak üzere yalıtabilirsiniz; bu tür ziyaretçiler veya cihaz sahipleri hariç tutulmalıdır. Birden çok uygulama veya yalnızca tek bir uygulama seçebilirsiniz. Çoklu uygulama bilgi noktası bir uygulamanın başka bir uygulamayı başlatmayı durdurmaz, bu nedenle mağaza veya başka bir uygulama kullanılabilirse kullanıcılar yine de başka bir uygulama başlatabilirsiniz.

Ayrıca, uygulamaları kısıtlamak için Uygulama Denetimi ['ne (WDAC) Windows Defender](windows-defender-application-control-wdac.md) uygulama veya hizmetlerin başlatılmasını tamamen durdurmak da istemeyebilirsiniz. WDAC, Bilgi Noktası'nın kullanıcı arabirimini değiştirmeytiği HoloLens engellenen bir uygulamanın başlatılmasına izin vermeytiği için farklıdır.

[Sayfa Ayarlar Görünürlüğü,](settings-uri-list.md) bir cihaza kısıtlama eklemenin başka bir yolu olabilir. Kullanıcılara Ayarlar uygulamasındaki bazı sayfalara erişim izni verebilirsiniz ancak erişimi sınırlamak için Sayfa Ayarlar Görünürlüğü'sini kullanabilirsiniz. Bu, örneğin, kullanıcılarının Wi-Fi'ı değiştirmesi gerekirse, ancak Hesaplar sayfasına erişmesini istemiyorsanız kullanışlıdır.

### <a name="physical-management"></a>Fiziksel Yönetim

Cihazı birden çok kullanıcı arasında paylaştığınızda dikkat edilmesi gereken bazı fiziksel noktalar vardır.

- Cihazların vardiyalar arasında ücretlendirmesi olduğundan emin olun.
- Bir cihaz vardiya için gerekli ise ve birden çok vardiyaya devam etmek gerekirse, cihazın ısı yön yönetimine göre önemli bir ücreti varken, vardiyanın başında bir dış pil [kullanmayı göz önünde bulundurabilirsiniz.](hololens2-charging.md#managing-heat)
- Cihazları depolarken, cihazları ağa takılı ve bağlı olarak tutabilirsiniz. Bu, işletim sistemi ve uygulama güncelleştirmelerini sağlamak için en iyi yol.
- Cihazı kullanıcılar arasında nasıl [temizlemeyi planlayabilirsiniz.](hololens2-maintenance.md)
- Tek bir kullanıcı için paylaşılan PIN/parola kullanıyorsanız, tek bir paylaşılan kullanıcıya sahip bir cihaz için, PIN'i/parolayı cihazın tarafına koymayın.
- Tek bir paylaşılan kullanıcıya sahip birden çok cihaz için çeşitli PIN'ler/parolalar kullanın.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Her biri kendi hesabını kullanarak birden çok kişi ile paylaşma

Bireysel Azure Active Directory (Azure AD) hesapları, 2 kullanıcı için tercih edilen ve en HoloLens kimlik kullanım durumudır. Kendi Azure AD hesaplarını kullanırken, birden çok kullanıcı cihazda kendi kullanıcı ayarlarını ve kullanıcı verilerini saklayabilirsiniz. Aynı anda yalnızca bir kullanıcı oturum açık olabilir. Bir kullanıcı oturum HoloLens önceki kullanıcının oturumlarını sildi.

Birden çok kişinin kendi hesaplarını kendi hesaplarınızı HoloLens emin olmak için aşağıdaki adımları izleyin:

1. Cihazı [ayarsanız, cihazı iş](hololens2-start.md)veya okul **sahibim'i seçin ve** bir Azure AD hesabı kullanarak oturum açın.
1. Kurulumu tamamladikten sonra, hesap ayarlarının (Ayarlar > Hesapları) Diğer kullanıcılar olduğundan **emin olun.**

> [!NOTE]
> Cihazınız bir Azure AD hesabıyla ayarlanmamışsa sıfırlanmış [](hololens-recovery.md) veya yeniden bayrakla ayarlanmış olmalıdır.

Bu HoloLens için her kullanıcı şu adımları izler:

1. Cihazı başka bir kullanıcı kullanıyorsa aşağıdaki seçeneklerden birini belirleyin:
   - Bekleme moduna dönmek için güç düğmesine bir kez basın ve ardından kilit ekranına dönmek için güç düğmesine tekrar basın
   - Kullanıcı kutucuğunu seçerek **Başlat menüsü** veya Geçerli kullanıcının oturumlarını silmek için **Power** menüsünden oturum aç'ı seçin.

1. Cihazda oturum açma için Azure AD hesabı kimlik bilgilerinizi kullanın.  
    - Cihazı ilk kez kullandıysanız, cihazı kendi göz HoloLens [](hololens-calibration.md) ayarlamanızı sorar.
    - Cihazı daha önce kullandıysanız:
        - [Windows Holographic sürüm 20H2, derleme 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) veya daha yüksek bir sürümde görüntü kalitesi ve rahat bir görüntüleme deneyimi için sorunsuz bir şekilde ayarlanır.
        - Önceki derlemelerde gözlerinizi ayarlamak için el ile düzeltme gerekir.

> [!TIP]
> Kullanıcı cihazda oturum açmamışsa daha hızlı oturum açma için şu iki yöntemden birini deneyin:
>
> - **FIDO 2 Güvenlik anahtarı:** FIDO2 güvenlik anahtarınız otomatik olarak tanınır ve kullanıcının kullanıcı kimlik bilgilerini yazması veya MFA kullanması gerektirlanmaz. Bu, yeni bir cihazda oturum açmanın en hızlı yöntemidir.
> - **Web kimlik** doğrulaması: Yeni bir cihazda oturum asanız, başka bir cihazdan Oturum açma bağlantısını seçerek [aka.ms/devicelogin'de 9](https://login.microsoftonline.com/common/oauth2/deviceauth) karakterlik bir kod yazarak cihazda kullanıcı olarak oturum açın veya size kolaylık sağlamak için klavye kullanarak kullanıcı adı ve parolanızı yazın. 

Cihaz kullanıcılarının listesini görmek veya cihazdan bir kullanıcı kaldırmak için, Ayarlar  >  **Hesapları Diğer**  >  **kullanıcılar'a gidin.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Hepsi aynı hesabı kullanarak birden çok kişi ile paylaşma

Birden çok kullanıcı tek bir kullanıcı HoloLens bir cihazı da paylaşabilir. Kullanıcıların cihazda tek HoloLens (Azure AD hesapları) ile oturum açması tercih edilse de, bu bazı kuruluşlarda bir seçenek değildir.

İki paylaşılan cihaz yöntemi vardır:

- **1 cihaz paylaşan birden çok** son kullanıcı - HoloLens bir cihaz, herhangi bir çalışanın cihazı kullanabileceği belirlenen bir alana ayrılır. Temiz bir oda veya ameliyat paketi buna örnek olarak verilmiştir.

- **Birden çok cihaz paylaşan birden çok** son HoloLens - tüm cihazlar, çalışanların herhangi bir cihazı kullanabileceği paylaşılan bir depolama alanı içindedir. Petrol platformu veya otomatik bayilik/galeri buna örnek olarak verilmiştir.

Aynı hesabın oturum açık olduğu sırada yeni bir kullanıcı cihazı ilk kez cihaza koyarsa, cihaz kullanıcıdan görüntüleme deneyimini hızla ayarlamasını ve kişiselleştirmesini istenir. Cihaz, her kullanıcının görüntüleme deneyiminin kalitesini ve rahatsını otomatik olarak iyileştirmek için ayar bilgilerini depolar. Kullanıcıların cihazı yeniden ayarlaması gerek olmayacaktır.
