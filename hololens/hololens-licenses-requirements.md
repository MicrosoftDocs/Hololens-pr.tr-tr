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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: bd55edcc855e20d6709c7e535573f43785155d41
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114661721"
---
# <a name="license-requirements"></a>Lisans gereksinimleri

## <a name="overview"></a>Genel Bakış
bu sayfa, kuruluşunuzda hem yönetilen hem de yönetilmeyen HoloLens 2 cihazlarını dağıtmak için gereken lisanslarına ve hesaplara ilişkin üst düzey bir genel bakış sağlar. Ayrıca, Dynamics 365 [Uzaktan Yardım](#dynamics-365-remote-assist) ve [kılavuzların](#dynamics-365-guides)lisanslanması hakkındaki bilgileri de içerir.

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 lisans ve hesap gereksinimleri

 
|       &nbsp;      | Yönetilen HoloLens | Yönetilmeyen HoloLens |
|-------------------|-----------------|---------------------|
| **İş kullanım örneği** | | |
| [Buluta bağlı cihazlara dağıtma-kavram kanıtı/pilot dağıtımı](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Kuruluşunuzun ağ dağıtımı içinde uygun ölçekte dağıtın](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Güvenli çevrimdışı ortamda dağıtın](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Lisanslar** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> veya <sup>2</sup>) | ✔️  | |
| **Hesaplar** |  | |
| Azure AD yönetici hesabı | ✔️ |  |
| Azure AD Kullanıcı hesabı | ✔️ | |
| [Microsoft hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Yerel hesap](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- Azure Active Directory kaydeden ve birleştiren ve cihazın ıntune ile yönetilmesine izin veren ilk cihaz kurulumu sırasında <sup>1</sup> [otomatik kayıt](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) .
- <sup></sup> [HoloLens 2 için 2 Windows Autopilot](hololens2-autopilot.md) , hem bt yöneticileri hem de son kullanıcılar için sağlama deneyimini basitleştirir. bt yöneticileri HoloLens 2 ilkeyi önceden yapılandırabilir ve ilk önyükleme sonrasında cihazlar, sıfır son kullanıcı etkileşimi ile iş için kullanıma yönelik duruma dağıtılır.
- <sup>3</sup> bu hesabın Windows yapılandırma tasarımcısı (wcd) ile bir süre önce [sağlanması](hololens-provisioning.md#provisioning-package-hololens-wizard) gerekir.

> [!IMPORTANT]
> Active Directory (AD) HoloLens cihazlarını yönetmek için kullanılamaz.
 
> [!WARNING]
> Bir cihaz için MSA veya yerel hesap kullanan birden çok kullanıcı desteklenmez.

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

- Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free)

- Ağ bağlantısı

Bu [çapraz kiracı senaryosunu](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir. Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için [Bu makaleye](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.

### <a name="dynamics-365-guides"></a>Dynamics 365 kılavuzlar 

#### <a name="admin"></a>Yönetici

1. Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
2. Dynamics 365 [Kılavuzlar aboneliği veya ücretsiz deneme](/dynamics365/mixed-reality/guides/setup-step-one)

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
