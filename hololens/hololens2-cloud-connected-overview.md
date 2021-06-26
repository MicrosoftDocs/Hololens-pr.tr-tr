---
title: Uzaktan Yardım ile buluta bağlı HoloLens 2 ' ye genel bakış
description: Dynamics 365 uzaktan yardım 'ı kullanarak, HoloLens 2 cihazlarını buluta bağlı bir ağ üzerinden kaydetmeyi öğrenin.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923542"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Dağıtım Kılavuzu – uzaktan yardım ile buluta bağlı HoloLens 2 – genel bakış

Bu kılavuz, BT uzmanlarının Microsoft HoloLens 2 cihazlarını kendi kuruluşlarına uzaktan yardım ile planlayıp dağıtmalarına yardımcı olur. Bu, çeşitli HoloLens 2 kullanım örnekleri genelinde kuruluşunuza yönelik kavram kanıtı dağıtımları için bir model olarak görev yapar. Kurulum, [senaryoya A 'ya benzer: bulut bağlantı cihazlarına dağıtın](https://docs.microsoft.com/hololens/common-scenarios#scenario-a). 

Kılavuz sırasında cihazlarınızı cihaz yönetimine kaydetme, gerektiğinde lisans uygulama ve son kullanıcılarınızın cihaz kurulumu üzerinde uzaktan yardım 'ı hemen kullanabildiğini doğrulama konusunda ele alınacaktır. Bunu yapmak için, ayarlama ve çalıştırma için gereken önemli parçaların üzerine giderek, HoloLens 2 ile ölçeklendirerek dağıtım elde edilmesi gerekir. Bu kılavuzda başka cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bu seçenekleri tamamladıktan sonra araştırmanızı öneririz.

## <a name="prerequisites"></a>Önkoşullar

HoloLens 2 ' nin dağıtılması için aşağıdaki altyapının olması gerekir. Aksi takdirde, Azure ve Intune kurulumu bu kılavuza dahildir:

- Wi-Fi
    - Ağlar genellikle Internet ve bulut hizmetlerine açıktır
- Azure Active Directory (Azure AD) MDM otomatik kaydıyla birleştir ([Azure AD P1 aboneliği](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) gerekir)
- MDM (Intune) yönetiliyor
    - Bir veya daha fazla uygulama MDM aracılığıyla dağıtılır.
- Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
    - Cihaz başına tek veya birden çok Kullanıcı desteklenir.

:::image type="content" alt-text="Buluta bağlı senaryo" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Uzaktan Yardım hakkında bilgi edinin

Uzaktan Yardım, işbirliğine dayalı bakım ve onarım, uzaktan denetleme ve bilgi paylaşımı ve eğitim sağlar. Kullanıcıları farklı rollerdeki ve konumlardaki uzak yardım 'ı kullanarak bir teknisyen, Microsoft ekiplerinde bulunan uzak ortak çalışan ile bağlanabilir. Bu kişiler, aynı konumda&#39;de olsa da sorunları gerçek zamanlı olarak çözümlemek için video, ekran görüntüleri ve ek açıklamaları birleştirebilirler. Uzak ortak çalışanlar, referans görüntülerini, şemaları ve diğer faydalı bilgileri, teknisyen üzerinde çalışırken kaya ve sorunsuz çalışma sırasında Şemasız bir şekilde bir araya girmek için bu kişilerin fiziksel alanı&#39;ekleyebilir.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Uzaktan Yardım lisanslama ve gereksinimler

- Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
- [Uzaktan Yardım aboneliği](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 uzaktan yardım kullanıcısı

- Uzaktan Yardım lisansı
- Ağ bağlantısı

#### <a name="microsoft-teams-user"></a>Microsoft ekipleri kullanıcısı

- Microsoft ekipleri veya [takımlar Freemıum](https://products.office.com/microsoft-teams/free).
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

