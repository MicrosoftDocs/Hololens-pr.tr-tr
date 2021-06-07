---
title: Cloud connected HoloLens 2 with Remote Assist'e genel bakış
description: Dynamics 365 Remote Assist kullanarak Bir Bulut Bağlantılı ağ üzerinden HoloLens 2 cihazlarını kaydetmeyi öğrenin.
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378958"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Dağıtım Kılavuzu – Remote Assist ile buluta bağlı HoloLens 2 – Genel Bakış

Bu kılavuz, BT uzmanlarının dynamics 365 Remote Assist ile buluta bağlı olan cihazları dynamics 365 remote Assist ile genel olarak kullanma amacını kullanarak Microsoft HoloLens 2 cihazları planlamalarına ve kuruluşlarına dağıtmalarına yardımcı olur. Bunun, çeşitli HoloLens 2 kullanım örnekleri genelinde kuruluşa yapılan kavram kanıtı dağıtımları için bir model olarak görev yapacaktır.

Kılavuz sırasında cihaz yönetiminize cihaz yönetimine cihaz kaydetmeyi, gerektiğinde lisansları uygulamayı ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulamayı da kapsıyoruz. Bunu yapmak için, HoloLens 2 ile büyük ölçekte dağıtıma ulaşmak için gerekli olan önemli altyapı parçalarının üzerinden geçeceğiz.

[![Buluta bağlı senaryo ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>Bu Kılavuzda

Bu kılavuzda, HoloLens cihazlarınız üzerinde kuruluş içinde Remote Assist'i ayarlamaya yönelik belirli bir hedef vardır. Bu hedefe ulaşmak için gerekli olan gerekliliklere yer veacağız. Bu hedefe odaklanmak amacıyla, bu dağıtım için iyileştirme yapmak veya yapılandırmak için gereken öğeleri azaltmak amacıyla belirli hazırlıklar ve yapılandırmalar önceden seçilir. Bu seçenekler size bildirecek ve dağıtımınızı iş gereksinimlerinize göre özelleştirebilirsiniz.

Bu, senaryo [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)Bulut bağlantısı cihazlarına dağıtmaya benzer bir kurulumdur. Bu, şunları içerecek birçok Kavram Kanıtı dağıtımı için iyi bir seçenektir:

- Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır
- MDM Otomatik Kaydı ile Azure AD'ye Katılma -- MDM (Intune) Yönetilen
- Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
  - Desteklenen cihaz başına tek veya birden çok kullanıcı
- Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır



Bu kılavuzda başka hiçbir cihaz kısıtlaması veya yapılandırma uygulanmaz, ancak bitirdikten sonra bu seçenekleri keşfetmeniz teşvik edilecektir.

## <a name="learn-about-remote-assist"></a>Remote Assist hakkında bilgi

Remote Assist işbirliğine dayalı bakım ve onarım, uzaktan incelemenin yanı sıra bilgi paylaşımı ve eğitim sağlar. Remote Assist kullanan bir teknisyen farklı rollerdeki ve konumlarda bulunan insanları bağlayarak Microsoft Teams'de bir uzak ortak çalışanla bağlantı kurabilirsiniz. Aynı konumda olmayan sorunları gerçek zamanlı olarak çözmek için video, ekran&#39;ek açıklamaları bir araya ekleyebilirler. Uzak ortak çalışanlar, HoloLens üzerinde çalışırken şemaya başvurmak için teknisyenin fiziksel&#39;referans görüntüleri, şemalar ve diğer yararlı bilgiler ekler.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Bu kılavuzda şunların için:

Hazırlamak:

> [!div class="checklist"]
> - [HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinebilirsiniz.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Azure AD hakkında daha fazla bilgi edinin ve yoksa&#39;ayarlayın.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.](hololens2-cloud-connected-prepare.md#identity-management)
> - [MDM hakkında daha fazla bilgi edinmek ve henüz hazır&#39;Intune ile ayarlama.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Remote Assist'in ağ gereksinimleri hakkında bilgi edinebilirsiniz.](hololens2-cloud-connected-prepare.md#network)
> - [İsteğe bağlı: Kuruluş kaynaklarına bağlanmak için VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Yapılandırmak:

> [!div class="checklist"]
> - [Kullanıcılar ve Gruplar oluşturma.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Azure AD'de Otomatik kayıt ayarlama.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Uygulama lisanslarınızı atama.](hololens2-cloud-connected-configure.md#application-licenses)

Dağıt:

> [!div class="checklist"]
> - [HoloLens 2'nizi ayarlayın ve kaydı doğrular.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Remote Assist çağrısı yapmak için bir doğrulama.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Korumak:

> [!div class="checklist"]
> - [Microsoft Store uygulamasını kullanarak Remote Assist'i güncelleştirme.](hololens2-cloud-connected-maintain.md#updates)
> - [Destek planı yapma.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Geliştirme planı.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Hazırlama](hololens2-cloud-connected-prepare.md)

