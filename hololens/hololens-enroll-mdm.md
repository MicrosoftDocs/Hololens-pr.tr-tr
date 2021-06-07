---
title: HoloLens'i MDM'ye kaydetme
description: Birden çok cihazın daha kolay yönetimi için HoloLens'i mobil cihaz yönetimine (MDM) kaydetmeyi öğrenin.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379102"
---
# <a name="enroll-hololens-in-mdm"></a>HoloLens'i MDM'ye kaydetme

birden çok Microsoft HoloLens cihazları aynı anda yönetmek için [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business) Ayarları yönetecek, yükecek uygulamaları seçecek ve güvenlik yapılandırmalarını, kuruluş gereksinimlerine göre ayarlayabileceksiniz. Bkz. [Windows Holographic](https://docs.microsoft.com/intune/windows-holographic-for-business)çalıştıran cihazları Microsoft Intune, Windows Holographic'te desteklenen yapılandırma hizmeti sağlayıcıları [(CSP'ler)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> VPN, Bitlocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM), yalnızca [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Gereksinimler

 HoloLens cihazlarını yönetmek için Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) ayarlanmıştır. MDM sağlayıcınız microsoft Microsoft Intune Microsoft MDM API'lerini kullanan üçüncü taraf bir sağlayıcı olabilir.
 
## <a name="different-ways-to-enroll"></a>Kaydetmenin farklı yolları

OOBE sırasında veya [oturum](hololens-identity.md) açma sonrası sırasında seçilen kimlik türüne bağlı olarak, farklı kayıt yöntemleri vardır.

- Kimlik Azure AD ise OOBE veya Ayarlar Uygulama Erişimi **İş veya** Okul Bağlantısı  ->    ->  **düğmesi sırasında.**
    - Azure AD için, [otomatik MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD kayıt URL'leri ile yapılandırılmışsa gerçekleşir.
     
- Kimlik Azure AD ise ve cihaz, belirli bir yapılandırma profili atanmış intune MDM sunucusuna önceden kaydedilmişse, OOBE sırasında Azure AD-Join ve [otomatik MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) kaydı gerçekleşir.
    - Autopilot [akışı olarak da adlandırılan](hololens2-autopilot.md) Bu akış [19041.1103+derlemelerde kullanılabilir.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Kimlik MSA ise, Ayarlar Uygulama Erişimi **İş veya**  ->  **Okul Bağlantısı**  ->  **düğmesini** kullanın.
    - İş Hesabı Ekle (AWA) akışı olarak da adlandırılan.
- Kimlik Yerel Kullanıcı ise, Ayarlar Uygulama Erişimi **İş veya** Okul  ->  **Kaydı'nın** yalnızca cihaz yönetimi  ->  **bağlantısında kullanın.**
    - Saf MDM kayıt akışı olarak da adlandırılan.

Cihaz MDM sunucunuza kaydedilenin ardından, Ayarlar uygulaması artık cihazın cihaz yönetimine kayded olduğunu yansıtacak.

## <a name="auto-enrollment-in-mdm"></a>MDM'de otomatik kayıt

Kurumda bir [Azure Premium](https://azure.microsoft.com/overview/)aboneliği varsa, Azure Active Directory (Azure AD) kullanıyorsa ve kimlik doğrulaması için Azure AD belirteci kabul eden bir MDM çözümü kullanıyorsa (şu anda yalnızca Microsoft Intune ve AirWatch'da de desteklemektedir), KULLANıCı Azure AD hesabıyla oturum atıktan sonra Azure AD'yi otomatik olarak MDM kaydına izin verecek şekilde yapılandırabilirsiniz. [Azure AD kaydı yapılandırmayı öğrenin.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Otomatik kayıt etkinleştirildiğinde ek el ile kayıt gerekmez. Kullanıcı bir Azure AD hesabıyla oturum açınca, ilk çalıştırma deneyimi tamamladıktan sonra cihaz MDM'ye kaydolacak.

Bir cihaz Azure AD'ye Katılmış olduğunda, cihaz sahibi olarak kabul [edilenleri etkileyebilir.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Intune'dan HoloLens'in kaydı

Kayıt yöntemine bağlı olarak, cihazınızın kaydı silinene kadar kullanılabilir olabilir.

Cihazınız bir Azure AD hesabına veya Autopilot'a kaydedildiyse, Intune'dan kayıttan silinamaz. HoloLens'e Azure AD'den katılmayı veya Azure AD kiracılarından farklı bir kiracıya yeniden katılmayı isterseniz cihazı [sıfırlamanız/ters eğik](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) çizgiyle sıfırlamanız gerekir.

Cihazınız iş hesabı ekli bir MSA hesabından veya yalnızca cihaz yönetimine kayıtlı bir Yerel hesaptan kayıtlı ise, cihazın kaydını sebilirsiniz. Uygulamayı açın Başlat menüsü Ayarlar Uygulama Erişimi İş **veya** Okul YourAccount Bağlantısını  ->  **Kes**  ->    ->  **düğmesini** seçin.