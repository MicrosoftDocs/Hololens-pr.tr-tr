---
title: uzaktan yardım ile buluta bağlı HoloLens 2 ' ye genel bakış
description: Dynamics 365 uzaktan yardım 'ı kullanarak bir buluta bağlı ağ üzerinden HoloLens 2 cihazı kaydetmeyi öğrenin.
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635135"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>dağıtım kılavuzu – buluta bağlı HoloLens 2 uzaktan yardım ile genel bakış

bu kılavuz, bt uzmanlarının kuruluşa uzak yardım ile Microsoft HoloLens 2 cihaz planlaması ve dağıtmalarına yardımcı olur. bu, kuruluşunuz için çeşitli HoloLens 2 kullanım durumlarında kavram kanıtı olan dağıtımlar için bir model olarak görev yapar. Kurulum, [senaryoya A 'ya benzer: bulut bağlantı cihazlarına dağıtın](https://docs.microsoft.com/hololens/common-scenarios#scenario-a). 

Kılavuz sırasında cihazlarınızı cihaz yönetimine kaydetme, gerektiğinde lisans uygulama ve son kullanıcılarınızın cihaz kurulumu üzerinde uzaktan yardım 'ı hemen kullanabildiğini doğrulama konusunda ele alınacaktır. bunu yapmak için, kurulumu ve çalışmayı sağlamak için gereken önemli parçaların üzerine gidecektir. HoloLens 2 ile uygun ölçekte dağıtım elde edin. Bu kılavuzda başka cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bu seçenekleri tamamladıktan sonra araştırmanızı öneririz.

## <a name="prerequisites"></a>Önkoşullar

HoloLens 2 ' i dağıtmak için aşağıdaki altyapının olması gerekir. Aksi takdirde, Azure ve Intune kurulumu bu kılavuza dahildir:

Bu, senaryo A 'ya benzer bir şekilde ayarlanmıştır [: bulut Connect cihazlarına dağıtma](/hololens/common-scenarios#scenario-a), bu, birçok kavram kanıtı sağlamak için iyi bir seçenektir. Bu, şunlar dahil olacaktır:

- Wi-Fi ağlar genellikle Internet ve bulut hizmetlerine tamamen açıktır
- MDM otomatik kayıt ile Azure AD katılımı--MDM (Intune) yönetilen
- Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
    - Cihaz başına tek veya birden çok Kullanıcı desteklenir.

:::image type="content" alt-text="Buluta bağlı senaryo" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Uzaktan Yardım hakkında bilgi edinin

Uzaktan Yardım, işbirliğine dayalı bakım ve onarım, uzaktan denetleme ve bilgi paylaşımı ve eğitim sağlar. Kullanıcıları farklı rollerdeki ve konumlardaki uzak yardım 'ı kullanarak bir teknisyen, Microsoft Teams üzerinde uzak ortak çalışan ile bağlanabilir. Bu kişiler, aynı konumda&#39;de olsa da sorunları gerçek zamanlı olarak çözümlemek için video, ekran görüntüleri ve ek açıklamaları birleştirebilirler. Uzak ortak çalışanlar başvuru görüntülerini, şemaları ve diğer faydalı bilgileri, HoloLens üzerinde çalışırken ve ücretsiz olarak çalışırken şemalara başvurabilmesi için&#39;fiziksel alanı ekleyebilir.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Uzaktan Yardım lisanslama ve gereksinimler

- Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
- [Uzaktan Yardım aboneliği](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 uzaktan yardım kullanıcısı

- Uzaktan Yardım lisansı
- Ağ bağlantısı

#### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free).
- Ağ bağlantısı

Bu [çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir. Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.

## <a name="in-this-guide-you-will"></a>Bu kılavuzda şunları yapmanız gerekir:

Hazırlanır

> [!div class="checklist"]
> - [HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinin.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD hakkında daha fazla bilgi edinin ve bunu&#39;ayarlayın.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM hakkında daha fazla bilgi edinin ve zaten bir tane&#39;yoksa Intune ile ayarlayın.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Uzaktan Yardım ağ gereksinimleri hakkında bilgi edinin.](hololens2-cloud-connected-prepare.md#network)
> - [İsteğe bağlı: kurumsal kaynaklara bağlanmak için VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Yapılandırma

> [!div class="checklist"]
> - [Kullanıcı ve grup oluşturma.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD 'de otomatik kayıt ayarlama.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Uygulama lisanslarınızı atama.](hololens2-cloud-connected-configure.md#application-licenses)

Dağıt:

> [!div class="checklist"]
> - [HoloLens 2 ' 'nizi ayarlayın ve kaydı doğrulayın.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Uzaktan Yardım araması yapacağınızı doğrulayın.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Korumanız

> [!div class="checklist"]
> - [Microsoft Store uygulamasını kullanarak uzaktan yardımı güncelleştirme.](hololens2-cloud-connected-maintain.md#updates)
> - [Destek planı oluşturma.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Geliştirme planı.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım-hazırlama](hololens2-cloud-connected-prepare.md)

