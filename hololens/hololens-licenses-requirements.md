---
title: Lisans gereksinimleri
description: Mobil cihaz yönetimi, cihaz yönetimi ve Remote Assist için ihtiyacınız olan tüm lisans gereksinimleri ve yönergeleri HoloLens takip edin.
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
ms.openlocfilehash: aae4e1dbbf28906c1f93ac7f29620260023f596bb96fc23a3ee78442e70585fa
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663300"
---
# <a name="license-requirements"></a>Lisans gereksinimleri

## <a name="overview"></a>Genel Bakış
Bu sayfa, hem yönetilen hem de yönetilemeyen cihazları HoloLens 2 cihazı dağıtmak için gereken lisanslara ve hesaplara üst düzey bir genel bakış sağlar. Ayrıca Dynamics 365 Remote Assist ve [Kılavuzları lisanslama hakkında bilgiler](#dynamics-365-remote-assist) de [içerir.](#dynamics-365-guides)

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 lisans ve hesap gereksinimleri

 
|       &nbsp;      | Yönetilen HoloLens | Unmanaged HoloLens |
|-------------------|-----------------|---------------------|
| **İş Kullanım Durumu** | | |
| [Buluta bağlı cihazlara dağıtma - kavram kanıtı/pilot dağıtım](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Kuruluş ağı içinde dağıtma - büyük ölçekte dağıtım](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Güvenli çevrimdışı ortamda dağıtma](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Lisanslar** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> veya <sup>2</sup>) | ✔️  | |
| **Hesaplar** |  | |
| Azure AD Yönetici hesabı | ✔️ |  |
| Azure AD Kullanıcı hesabı | ✔️ | |
| [Microsoft Hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Yerel Hesap](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup> [İlk cihaz kurulumu](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) sırasında otomatik kayıt, cihaza kaydolarak Azure Active Directory ve cihazın Intune ile yönetiliyor olması için izin verir.
- <sup></sup> [Windows 2 için Autopilot HoloLens 2,](hololens2-autopilot.md) hem IT yöneticileri hem de son kullanıcılar için sağlama deneyimini basitleştiriyor. IT yöneticileri 2 ilke HoloLens önceden yapılandırılabilir ve ilk önyüklemeden sonra cihazlar sıfır son kullanıcı etkileşimiyle iş için hazır durumda dağıtılır.
- <sup>3</sup> Bu hesabın, [Windows](hololens-provisioning.md#provisioning-package-hololens-wizard) Configuration Designer (WCD) ile sağlanması gerekir.

> [!IMPORTANT]
> Active Directory (AD), cihazları yönetmek HoloLens kullanılamaz.
 
> [!WARNING]
> MSA veya yerel hesap kullanan bir cihaz için birden çok kullanıcı desteklenmiyor.

## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 Lisanslama ve Gereksinimler

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Yönetici

- Azure AD hesabı (aboneliği satın almak ve lisans atamak için gereklidir)
- [Remote Assist aboneliği](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Remote Assist Deneme sürümü)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist kullanıcısı

- Azure AD hesabı

- Remote Assist lisansı 

  > [!NOTE]
  > Microsoft Teams Remote Assist ile birlikte paketlenmiştir

- Ağ Bağlantısı

#### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Azure AD hesabı

- Microsoft Teams veya [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Ağ bağlantısı

Bu kiracılar arası [senaryoyu uygulamayı planlıyorsanız,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)bir Bilgi Bariyerleri lisansına ihtiyacınız olabilir. Bilgi [Engeli](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) Lisansının gerekli olup olmadığını belirlemek için bu makaleye bakın.

### <a name="dynamics-365-guides"></a>Dynamics 365 Kılavuzları 

#### <a name="admin"></a>Yönetici

1. Azure AD hesabı (aboneliği satın almak ve lisans atamak için gereklidir)
2. Dynamics 365 [Kılavuzları aboneliği veya ücretsiz deneme](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Kılavuz yazarı

1. Azure AD hesabı
1. [Dynamics 365 Kılavuzları lisansı](/dynamics365/mixed-reality/guides/requirements)
1. Bir bilgisayara veya bilgisayara yüklü Dynamics 365 Kılavuzları uygulaması HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Analytics panosu görüntülemek için kullanılır)
1. Yazar rolü (kılavuz oluşturmak için)
1. Ağ Bağlantısı

#### <a name="guides-user"></a>Kılavuzlar Kullanıcı

1. Azure AD hesabı
1. [Dynamics 365 Kılavuzları lisansı](/dynamics365/mixed-reality/guides/requirements)
1. Bir uygulamaya yüklenmiş Dynamics 365 Kılavuzları HoloLens
1. İşleç rolü (test veya kullanma kılavuzları için)
1. Ağ Bağlantısı
