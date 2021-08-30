---
title: Remote Assist ile Buluta bağlı HoloLens 2'ye genel bakış
description: Dynamics 365 Remote Assist HoloLens bulut bağlantılı ağ üzerinden 2 cihaz kaydetmeyi öğrenin.
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189656"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Dağıtım Kılavuzu – Remote Assist ile buluta HoloLens 2 – Genel Bakış

Bu kılavuz, BT uzmanlarının Kuruluşlarına Remote Assist ile Microsoft HoloLens 2 cihazı planlamalarına ve dağıtmalarına yardımcı olur. Bu, 2 farklı kullanım örneğinde farklı kullanım örneklerinde kuruluşa yapılan kavram kanıtı dağıtımları HoloLens bir model olarak görev yapacaktır. Kurulum, Senaryo [A: Bulut bağlantısı cihazlarına dağıtma ile benzerdir.](common-scenarios.md#scenario-a) 

Kılavuz sırasında cihaz yönetiminize cihaz yönetimine cihaz kaydetmeyi, gerektiğinde lisansları uygulamayı ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulamayı da kapsıyoruz. Bunu yapmak için, kurulum ve çalışma için gereken önemli altyapı parçalarının üzerinden geçerek 2. adımla büyük ölçekte dağıtıma HoloLens. Bu kılavuzda başka hiçbir cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bitirdikten sonra bu seçenekleri keşfetmeniz teşvik edilecektir.

## <a name="prerequisites"></a>Önkoşullar

HoloLens 2'yi dağıtmak için aşağıdaki altyapının yerinde olması gerekir. Ayarlanmazsa, bu kılavuza Azure ve Intune'ları ayarlama dahildir:

Bu, Senaryo [A:](/hololens/common-scenarios#scenario-a)Bulut bağlantısı cihazlarına dağıtmaya benzer bir kurulumdur. Bu, şunları içerecek birçok Kavram Kanıtı dağıtımı için iyi bir seçenektir:

- Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır
- MDM Otomatik Kaydı ile Azure AD'ye Katılma— MDM ile yönetilen (Intune)
- Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
    - Cihaz başına tek veya birden çok kullanıcı desteği vardır.

:::image type="content" alt-text="Buluta bağlı senaryo." source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Remote Assist hakkında bilgi

Remote Assist işbirliğine dayalı bakım ve onarım, uzaktan incelemenin yanı sıra bilgi paylaşımı ve eğitim sağlar. Farklı rollerdeki ve konumlarda bulunan insanları birbirine bağlayarak Remote Assist kullanan bir teknisyen, uzaktan işbirliği yapan bir Microsoft Teams. Aynı konumda olmayan sorunları gerçek zamanlı olarak çözmek için video, ekran görüntüleri ve ek açıklamaları bir araya ekleyebilirler. Uzak ortak çalışanlar, teknisyenin fiziksel alanıyla ilgili başvuru görüntüleri, şemalar ve diğer yararlı bilgileri eklemenin bir yandan şemaya başvurarak diğer yandan çalışma sırasında kafadan ve el ile HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist Lisanslama ve Gereksinimler

- Azure AD hesabı (aboneliği satın almak ve lisans atamak için gereklidir)
- [Remote Assist aboneliği](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Remote Assist Deneme sürümü)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist kullanıcısı

- Remote Assist lisansı
- Ağ Bağlantısı

#### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Microsoft Teams veya [Teams Freemium.](https://products.office.com/microsoft-teams/free)
- Ağ bağlantısı

Bu kiracılar arası [senaryoyu uygulamayı planlıyorsanız,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)bir Bilgi Bariyerleri lisansına ihtiyacınız olabilir. Bilgi Engeli Lisansının gerekli olup olmadığını belirlemek için bkz. Satıcılar ve müşteriler [tam Dynamics 365 Remote Assist özelliklerini kullanır.](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation)

## <a name="in-this-guide-you-will"></a>Bu kılavuzda şunların için:

Hazırlamak:

> [!div class="checklist"]
> - [2 cihaz için altyapı temelleri HoloLens öğrenin.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD hakkında daha fazla bilgi edinin ve yoksa&#39;ayarlayın.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM hakkında daha fazla bilgi edinmek ve henüz hazır&#39;Intune ile ayarlama.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Remote Assist'in ağ gereksinimleri hakkında bilgi edinebilirsiniz.](hololens2-cloud-connected-prepare.md#network)
> - [İsteğe bağlı: Kuruluş kaynaklarına bağlanmak için VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Yapılandırmak:

> [!div class="checklist"]
> - [Kullanıcılar ve Gruplar oluşturma.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD'de Otomatik kayıt ayarlama.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Uygulama lisanslarınızı atama.](hololens2-cloud-connected-configure.md#application-licenses)

Dağıt:

> [!div class="checklist"]
> - [2. HoloLens ayarlama ve kaydı doğrulama.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Remote Assist çağrısı yapmak için bir doğrulama.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Korumak:

> [!div class="checklist"]
> - [Microsoft Store kullanarak Remote Assist'i güncelleştirme.](hololens2-cloud-connected-maintain.md#updates)
> - [Destek planı yapma.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Geliştirme planı.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Hazırlama](hololens2-cloud-connected-prepare.md)

