---
title: MDM'HoloLens kayıt
description: Birden çok cihazın daha HoloLens için mobil cihaz yönetimine (MDM) nasıl kayıt olduğunu öğrenin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640415"
---
# <a name="enroll-hololens-in-mdm"></a>MDM'HoloLens kayıt

birden çok Microsoft HoloLens cihazları aynı anda yönetmek için [Microsoft Intune.](/intune/windows-holographic-for-business) Ayarları yönetecek, yükecek uygulamaları seçecek ve güvenlik yapılandırmalarını, kuruluş gereksinimlerine göre ayarlayabileceksiniz. Bkz. [Microsoft Intune ile Windows Holographic](/intune/windows-holographic-for-business)çalıştıran cihazları yönetme, Windows Holographic'te desteklenen yapılandırma hizmeti sağlayıcıları [(CSP'ler)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> VPN, Bitlocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM), yalnızca [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Gereksinimler

 Mobil cihazları yönetmek için, Cihaz Yönetimi mobil cihazları (MDM) HoloLens gerekir. MDM sağlayıcınız microsoft Microsoft Intune Microsoft MDM API'lerini kullanan üçüncü taraf bir sağlayıcı olabilir.
 
## <a name="different-ways-to-enroll"></a>Kaydetmenin farklı yolları

OOBE sırasında veya [oturum](hololens-identity.md) açma sonrası sırasında seçilen kimlik türüne bağlı olarak, farklı kayıt yöntemleri vardır.

- Kimlik Azure AD ise, OOBE sırasında veya uygulama **Ayarlar App** Access work  ->  **veya School**  ->  **Bağlan** düğmesi.
    - Azure AD için, [otomatik MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD kayıt URL'leri ile yapılandırılmışsa gerçekleşir.
     
- Kimlik Azure AD ise ve cihaz, belirli bir yapılandırma profili atanmış intune MDM sunucusuna önceden kaydedilmişse, OOBE sırasında Azure AD-Join ve [otomatik MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) kaydı gerçekleşir.
    - Autopilot [akışı olarak da adlandırılan](hololens2-autopilot.md) Bu akış [19041.1103+derlemelerde kullanılabilir.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Identity MSA ise, Uygulama **Erişimi Ayarlar veya Okul** Yönetimi düğmesini  ->    ->  **Bağlan** kullanın.
    - İş Hesabı Ekle (AWA) akışı olarak da adlandırılan.
- Kimlik Yerel Kullanıcı ise, Uygulama **Erişimi Ayarlar veya** Okul Kaydı'nın yalnızca cihaz yönetimi  ->    ->  **bağlantısında kaydını** kullanın.
    - Saf MDM kayıt akışı olarak da adlandırılan.

Cihaz MDM sunucunuza kaydedile Ayarlar uygulama artık cihazın cihaz yönetimine kayded olduğunu yansıtacak.

## <a name="auto-enrollment-in-mdm"></a>MDM'de otomatik kayıt

Kurumda bir [Azure Premium](https://azure.microsoft.com/overview/)aboneliği varsa, kimlik doğrulaması için bir Azure AD belirteci kabul eden bir MDM çözümü (şu anda yalnızca Microsoft Intune ve AirWatch'da desteklemektedir) Azure Active Directory (Azure AD) kullanıyorsa, IT yöneticiniz Azure AD'yi, kullanıcı Azure AD hesabıyla oturum atıktan sonra MDM kaydına otomatik olarak izin verecek şekilde yapılandırabilirsiniz. [Azure AD kaydı yapılandırmayı öğrenin.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Otomatik kayıt etkinleştirildiğinde ek el ile kayıt gerekmez. Kullanıcı bir Azure AD hesabıyla oturum açınca, ilk çalıştırma deneyimi tamamladıktan sonra cihaz MDM'ye kaydolacak.

Bir cihaz Azure AD'ye Katılmış olduğunda, cihaz sahibi olarak kabul [edilenleri etkileyebilir.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Intune'HoloLens kaydı

Kayıt yöntemine bağlı olarak, cihazınızın kaydı silinene kadar kullanılabilir olabilir.

Cihazınız bir Azure AD hesabına veya Autopilot'a kaydedildiyse, Intune'dan kayıttan silinamaz. Azure AD'den HoloLens veya Azure AD kiracılarından farklı bir kiracıya yeniden katılmayı isterseniz cihazı [sıfırlamanız/ters eğik](hololens-recovery.md#reset-the-device) çizgiyle sıfırlamanız gerekir.

Cihazınız iş hesabı ekli bir MSA hesabından veya yalnızca cihaz yönetimine kayıtlı bir Yerel hesaptan kayıtlı ise, cihazın kaydını sebilirsiniz. Uygulamayı açın Başlat menüsü App Access work **Ayarlar**  ->  **School**  ->  *YourAccount* Disconnect düğmesini  ->   seçin.