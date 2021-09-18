---
title: MDM'HoloLens kayıt
description: Birden çok cihazın daha HoloLens için mobil cihaz yönetimine (MDM) nasıl kayıt olduğunu öğrenin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904353"
---
# <a name="enroll-hololens-in-mdm"></a>MDM'HoloLens kayıt

birden çok Microsoft HoloLens cihazları aynı anda yönetmek için [Microsoft Intune.](/intune/windows-holographic-for-business) Ayarları yönetecek, yükecek uygulamaları seçecek ve güvenlik yapılandırmalarını, kuruluş gereksinimlerine göre ayarlayabileceksiniz. Bkz. [Microsoft Intune ile Windows Holographic](/intune/windows-holographic-for-business)çalıştıran cihazları yönetme, Windows Holographic'te desteklenen yapılandırma hizmeti sağlayıcıları [(CSP'ler)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)

> [!NOTE]
> VPN, Bitlocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM), yalnızca [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Gereksinimler

 Bu cihazları yönetmek için, Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) HoloLens gerekir. MDM sağlayıcınız microsoft Microsoft Intune Microsoft MDM API'lerini kullanan üçüncü taraf bir sağlayıcı olabilir.

## <a name="different-ways-to-enroll"></a>Kaydetmenin farklı yolları

OOBE sırasında veya [oturum](hololens-identity.md) açma sonrası sırasında seçilen kimlik türüne bağlı olarak, farklı kayıt yöntemleri vardır.

- Kimlik Azure AD ise, OOBE sırasında veya Ayarlar **App**  ->  **Access work veya School**  ->  **Bağlan** düğmesi.
    - Azure AD için, [otomatik MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD kayıt URL'leriyle yapılandırılmışsa gerçekleşir.

- Kimlik Azure AD ise ve cihaz, belirli bir yapılandırma profili atanmış intune MDM sunucusuna önceden kaydedilmişse, OOBE sırasında Azure AD-Join ve otomatik [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) kaydı gerçekleşir.
    - Autopilot [akışı olarak da adlandırılan](hololens2-autopilot.md) Bu akış [19041.1103+derlemelerde kullanılabilir.](hololens-release-notes.md#windows-holographic-version-2004)


- Kimlik MSA ise Uygulama Erişimi **Ayarlar veya Okul** Yönetimi düğmesini  ->    ->  **Bağlan** kullanın.
    - İş Hesabı Ekle (AWA) akışı olarak da adlandırılan.
- Kimlik Yerel Kullanıcı ise, Uygulama **Erişimi Ayarlar** veya Okul Kaydı'nın yalnızca cihaz  ->    ->  **yönetimi bağlantısında kaydını** kullanın.
    - Saf MDM kayıt akışı olarak da adlandırılan.

Cihaz MDM sunucunuza kaydolan Ayarlar uygulama artık cihazın cihaz yönetimine kayded olduğunu yansıtacak.

## <a name="auto-enrollment-in-mdm"></a>MDM'de otomatik kayıt

Kurumda bir [Azure Premium](https://azure.microsoft.com/overview/)aboneliği varsa, kimlik doğrulaması için Azure AD belirteci kabul eden bir MDM çözümü (şu anda yalnızca Microsoft Intune ve AirWatch'da desteklemektedir) Azure Active Directory (Azure AD) kullanıyorsa, IT yöneticiniz Azure AD'yi, kullanıcı Azure AD hesabıyla oturum atıktan sonra MDM kaydına otomatik olarak izin verecek şekilde yapılandırabilirsiniz. [Azure AD kaydı yapılandırmayı öğrenin.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Otomatik kayıt etkinleştirildiğinde ek el ile kayıt gerekmez. Kullanıcı bir Azure AD hesabıyla oturum açınca, ilk çalıştırma deneyimi tamamladıktan sonra cihaz MDM'ye kaydolacak.

Bir cihaz Azure AD'ye Katılmış olduğunda, cihaz sahibi olarak kabul [edenleri etkileyebilir.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Intune'HoloLens kaydı silenler

Kayıt yöntemine bağlı olarak, cihazınızın kaydı silinene kadar kullanılabilir olabilir.

Cihazınız bir Azure AD hesabına veya Autopilot'a kaydedildiyse, Intune'dan kayıttan silinamaz. Azure AD'den HoloLens veya Azure AD kiracılarından farklı bir kiracıya yeniden katılmayı isterseniz cihazı [sıfırlamanız/ters eğik](hololens-recovery.md#reset-the-device) çizgiyle sıfırlamanız gerekir.

Cihazınız iş hesabı ekli bir MSA hesabından veya yalnızca cihaz yönetimine kayıtlı bir Yerel hesaptan kayıtlı ise, cihazın kaydını sebilirsiniz. Uygulama erişim Başlat menüsü açın ve ardından App Access **Ayarlar veya** School YourAccount Bağlantısını Kes  ->    ->    ->  **düğmesini** seçin.

## <a name="enrollment-troubleshooting"></a>Kayıt sorunlarını giderme

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Kullanıcıya geçerli lisansın atan olduğundan emin olun

Özellikle aşağıdaki [bölümlerde Windows](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) cihaz Microsoft Intune sorunlarını giderme( örneğin, Cihaz [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) türü kısıtlamalarını denetleme ve Kullanıcıya geçerli bir [lisans atama) bakın.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Tüm cihazlarda MDM kaydı engellenmiş Windows olun

Kaydın başarılı olması için, cihazlarınızı kaydede HoloLens emin olun. Bu HoloLens bir Windows olduğu için, dağıtımınızı engellecek bir kayıt kısıtlaması olması gerekir. [Bu kısıtlama listesini gözden geçirin](/mem/intune/enrollment/enrollment-restrictions-set) ve cihazlarınızı kaydedesiniz.