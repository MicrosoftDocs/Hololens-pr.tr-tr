---
title: Lisans gereksinimleri
description: mobil cihaz yönetimi, HoloLens ve uzaktan yardım için ihtiyacınız olan tüm lisans gereksinimleri ve yönergeleriyle güncel tutun.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640296"
---
# <a name="license-requirements"></a>Lisans gereksinimleri

## <a name="hololens-2-device-managed"></a>HoloLens 2 cihaz (yönetilen)

[Azure AD hesabı](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) HoloLens cihazlarını yönetmek için kullanılamaz.

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) veya başka bir MDM.
- [HoloLens 2 için Windows Autopilot](hololens2-autopilot.md)-hem bt yöneticileri hem de son kullanıcılar için sağlama deneyimini basitleştirir. bt yöneticileri HoloLens 2 ilkeyi önceden yapılandırabilir ve ilk önyükleme sonrasında cihazlar, sıfır son kullanıcı etkileşimi ile iş için kullanıma yönelik duruma dağıtılır. 

  > [!NOTE]
  > Windows Autopilot, önce [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) ve [otomatik kayıt](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 'nin düşük dokunma Autopilot akışı ve cihaz dağıtımı için yapılandırılmasını gerektirir. 

### <a name="business-use-case"></a>İş kullanım örneği: 

- [Dağıtım senaryosu A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) -kavram kanıtı veya pilot dağıtım.

- [Dağıtım senaryosu B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) -ölçekli dağıtım.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 cihaz-yalnızca (yönetilmeyen)

Bir Microsoft hesabı (MSA) veya yerel hesap kullanırken bu hesaplar için ek lisans gerekmez.

[Yerel hesap](/windows/security/identity-protection/access-control/local-accounts)

- bu hesabın Windows yapılandırma tasarımcısı (wcd) ile bir süre önce [sağlanması](hololens-provisioning.md#provisioning-package-hololens-wizard) gerekir.

[Microsoft hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Bu hesaplardan birini kullanan bir cihaz için birden fazla kullanıcı desteklenmez.

### <a name="business-use-case"></a>İş kullanım örneği: 

- [Dağıtım senaryosu C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -çevrimdışı veya güvenli dağıtım.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 lisanslama ve gereksinimleri

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 uzaktan yardım 

#### <a name="admin"></a>Yönetici

- Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
- [Uzaktan Yardım aboneliği](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 uzaktan yardım kullanıcısı

- Azure AD hesabı

- Uzaktan Yardım lisansı 

  > [!NOTE]
  > Microsoft Teams, uzaktan yardım ile paketlenmiştir

- Ağ bağlantısı

#### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Azure AD hesabı

- Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free).

- Ağ bağlantısı

Bu [çapraz kiracı senaryosunu](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir. Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.

### <a name="dynamics-365-guides"></a>Dynamics 365 kılavuzlar 

#### <a name="admin"></a>Yönetici

- Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
- Dynamics 365 [Kılavuzlar aboneliği veya ücretsiz deneme](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Kılavuzlar yazarı

1. Azure AD hesabı
1. [Dynamics 365 kılavuzlar lisansı](/dynamics365/mixed-reality/guides/requirements)
1. Bir PC 'de veya HoloLens yüklü olan Dynamics 365 kılavuzlar uygulaması
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (analiz panosunu görüntülemek için kullanılır)
1. Yazar rolü (kılavuz oluşturmak için)
1. Ağ bağlantısı

#### <a name="guides-user"></a>Kılavuzlar kullanıcısı

1. Azure AD hesabı
1. [Dynamics 365 kılavuzlar lisansı](/dynamics365/mixed-reality/guides/requirements)
1. Dynamics 365 kılavuzlar uygulaması HoloLens yüklendi
1. İşleç rolü (test etmek veya kılavuzlar kullanmak için)
1. Ağ bağlantısı
