---
title: Ticari özellikler
description: İşletmelerin HoloLens Microsoft HoloLens Commercial Suite yönetmelerini kolaylaştıran yeni özellikler hakkında bilgi edinebilirsiniz.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, ticari, özellikler, mdm, mobil cihaz yönetimi, bilgi noktası modu
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380153"
---
# <a name="commercial-features"></a>Ticari özellikler

HoloLens, işletmelerin HoloLens cihazlarını yönetmelerini kolaylaştıran özellikler içerir.

Her HoloLens 2 cihazın ticari özellikleri vardır.

HoloLens (1. nesil), geliştirici lisansı ve ticari lisans olmak üzere iki lisans seçeneğiyle birlikte geldi. HoloLens'in ticari özelliklerini ortaya açmak için geliştirici lisansından ticari lisansa yükseltin. Satın almak Microsoft HoloLens Commercial Suite yerel yönetici yöneticinize Microsoft hesabı.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Önemli ticari özellikler

- **Bilgi noktası modu.** Hangi uygulamaların çalıştırılaylarını sınırlamak için bilgi noktası modunu kullanarak HoloLens'i tanıtım veya gösterimi deneyimlerinde kullanabilirsiniz.

  ![HoloLens, bilgi noktası modunu kullanarak doğrudan tercih edilen uygulamada başlatılacaktır.](images/201608-kioskmode-400px.png)

- **HoloLens Cihaz Yönetimi mobil cihazlar (MDM).** IT departmanınız birden çok HoloLens cihazı aynı anda yönetmek için sanal Microsoft Intune. Ayarları yönetebilir, yüklenecek uygulamaları seçebilirsiniz ve güvenlik yapılandırmalarını, kuruluş gereksinimlerinize göre uyarlanmış olarak ayarlayın.

  ![HoloLens Cihaz Yönetimi mobil cihaz yönetimi, birden çok cihazda kurumsal sınıf cihaz yönetimi sağlar.](images/201608-enterprisemanagement-400px.png)

- **İş İçin Windows Update.** İş İçin Windows Update cihazlara denetimli işletim sistemi güncelleştirmeleri ve uzun süreli bakım kanalı için destek sağlar.
- **Veri güvenliği.** HoloLens'de BitLocker veri şifrelemesi, diğer Windows cihazlarından aynı düzeyde güvenlik koruması sağlamak için etkinleştirilir.
- **İş erişimi.** HoloLens'te sanal özel ağ (VPN) üzerinden kuruluş ağına uzaktan bağlanabilirsiniz. HoloLens ayrıca kimlik Wi-Fi ağlara da erişebilirsiniz.
- **İş İçin Microsoft Store.** AYRıCA, IT departmanınız, yalnızca kendi HoloLens kullanımınız için şirket uygulamalarını içeren bir kurumsal özel mağaza da oluşturabilir. Kurumsal yazılımınızı seçili kurumsal kullanıcı grubuna güvenli bir şekilde dağıtabilirsiniz.

## <a name="feature-comparison-between-editions"></a>Sürümler arasında özellik karşılaştırması

|Özellikler |HoloLens (1. nesil) Geliştirme Sürümü |HoloLens (1. nesil) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|Cihaz Şifrelemesi (BitLocker) | |✔️ |✔️ |
|Sanal Özel Ağ (VPN) | |✔️ |✔️ |
|[Bilgi noktası modu](hololens-kiosk.md) | |✔️ |✔️ |
|**Yönetim ve dağıtım** | | | |
|Mobil Cihaz Yönetimi (MDM) | |✔️ |✔️ |
|Kayıtsız kaydı engelleme özelliği | |✔️ |✔️ |
|Sertifika tabanlı kurumsal Wi-Fi erişimi | |✔️ |✔️ |
|Microsoft Store (Tüketici) |Tüketici |MDM kullanarak filtreleme |MDM kullanarak filtreleme |
|[İş Mağazası Portalı](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Güvenlik ve kimlik** | | | |
|Azure Active Directory (Azure AD) hesabını kullanarak oturum açın |✔️ |✔️ |✔️ |
|Microsoft Hesabı (MSA) kullanarak oturum açın |✔️ |✔️ |✔️ |
|PIN kilidi açma ile Yeni Nesil Kimlik Bilgileri |✔️ |✔️ |✔️ |
|[Güvenli önyükleme](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Bakım ve destek** | | | |
|Gelen otomatik sistem güncelleştirmeleri |✔️ |✔️ |✔️ |
|[İş İçin Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Bakım Kanalı (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Ticari özellikleri etkinleştirme

Kuruluşun IT yöneticisi İş İçin Microsoft Store, bilgi noktası modu ve kurumsal Wi-Fi gibi ticari Wi-Fi kurabilirsiniz. Bu [Microsoft HoloLens,](index.yml) cihazları kaydetmek ve bu cihazlardan uygulama yüklemek için adım adım yönergeler İş İçin Microsoft Store.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft HoloLens](index.yml)
- [Bilgi noktası modu](hololens-kiosk.md)
- [HoloLens cihazlarında desteklenen CSP'ler](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store İş ve iş hattı uygulamaları için](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [İş hattı uygulamalarıyla çalışma](/microsoft-store/working-with-line-of-business-apps)
