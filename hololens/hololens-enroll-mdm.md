---
title: MDM 'ye HoloLens kaydetme
description: birden çok cihazın daha kolay yönetilmesi için mobil cihaz yönetimi 'ne (MDM) HoloLens kaydetmeyi öğrenin.
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
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032939"
---
# <a name="enroll-hololens-in-mdm"></a>MDM 'ye HoloLens kaydetme

[Microsoft Intune](/intune/windows-holographic-for-business)gibi çözümleri kullanarak birden çok Microsoft HoloLens cihazı eşzamanlı olarak yönetebilirsiniz. Ayarları yönetebileceksiniz, yüklenecek uygulamaları seçerek kuruluşunuzun ihtiyacı olarak uyarlanmış güvenlik yapılandırması ayarlayabilirsiniz. bkz. [Windows Holographic çalıştıran cihazları Microsoft Intune](/intune/windows-holographic-for-business), [Windows Holographic 'de desteklenen yapılandırma hizmeti sağlayıcılarını (csp)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business tarafından desteklenen ilkeleri](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)yönetme.

> [!NOTE]
> VPN, BitLocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM) yalnızca [Windows holographic for Business sürümüne yükselttiğinizde](hololens1-upgrade-enterprise.md)kullanılabilir.

## <a name="requirements"></a>Gereksinimler

 kuruluşunuzun HoloLens cihazları yönetmek için mobil cihaz yönetimi (MDM) ayarlamış olması gerekir. mdm sağlayıcınız Microsoft Intune veya Microsoft MDM apı 'leri kullanan bir 3. taraf sağlayıcı olabilir.

## <a name="different-ways-to-enroll"></a>Farklı kayıt yolları

OOBE ya da oturum açma sonrası seçilen [kimliğin](hololens-identity.md) türüne bağlı olarak farklı kayıt yöntemleri vardır.

- kimlik Azure AD ise, OOBE sırasında ya da **uygulama**  ->  **erişimi iş veya okul**  ->  **Bağlan** düğmesini Ayarlar.
    - Azure AD 'de, [OTOMATIK MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD, kayıt URL 'leriyle yapılandırıldıysa oluşur.

- Kimlik Azure AD ise ve cihaz kendisine atanmış belirli yapılandırma profiline sahip Intune MDM sunucusuna önceden kaydedilmişse, Azure AD-Join ve [OTOMATIK MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) OOBE sırasında gerçekleşir.
    - [19041.1103 + yapılarında](hololens-release-notes.md#windows-holographic-version-2004)bulunan [Autopilot Flow](hololens2-autopilot.md) da denir.


- kimlik MSA ise **Ayarlar uygulama**  ->  **erişimi iş veya okul**  ->  **Bağlan** düğmesini kullanarak.
    - Iş hesabı ekle (AWA) akışı da denir.
- kimlik yerel kullanıcı ise, **Ayarlar uygulama**  ->  **erişimi iş veya okul**  ->  **kayıt yalnızca cihaz yönetimi bağlantısı '** nı kullanarak.
    - Saf MDM kayıt akışı da denir.

cihaz MDM sunucunuza kaydedildikten sonra Ayarlar uygulama cihazın cihaz yönetimine kaydedildiğini yansıtır.

## <a name="auto-enrollment-in-mdm"></a>MDM 'de otomatik kayıt

kuruluşunuzun [azure Premium aboneliği](https://azure.microsoft.com/overview/)varsa, kimlik doğrulaması için bir azure ad belirtecini kabul eden Azure Active Directory (Azure AD) ve mdm çözümü (şu anda yalnızca Microsoft Intune ve airwatch 'da desteklenir) kullanılıyorsa, bt yöneticiniz azure ad 'yi kullanıcı azure ad hesabıyla oturum açtıktan sonra MDM kaydına otomatik olarak izin verecek şekilde yapılandırabilir. [Azure AD kaydı 'nı yapılandırmayı öğrenin.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Otomatik kayıt etkinleştirildiğinde, ek bir el ile kayıt gerekmez. Kullanıcı bir Azure AD hesabıyla oturum açtığında, ilk çalıştırma deneyimini tamamladıktan sonra cihaz MDM 'ye kaydedilir.

Bir cihaz Azure AD 'ye katıldığında, [cihaz sahibini](security-adminless-os.md#device-owner)kabul eden kişiyi etkileyebilir.

## <a name="unenroll-hololens-from-intune"></a>HoloLens kaydını ıntune 'dan kaldırma

Kayıt yöntemine bağlı olarak, cihazınızın kaydının kaldırılması kullanılamayabilir.

Cihazınız bir Azure AD hesabı veya Autopilot kaydedildiyse, Intune kaydı geri alınamaz. HoloLens azure ad 'den katılmayı veya azure ad kiracısıyla farklı bir şekilde yeniden katmak isterseniz, cihazı [sıfırlamanız/refflash](hololens-recovery.md#reset-the-device) yapmanız gerekir.

Cihazınız, bir iş hesabı veya yalnızca cihaz yönetimine kaydolmuş yerel bir hesaptan eklenen bir MSA hesabından kaydedildiyse, cihazın kaydını geri alabilirsiniz. Başlat menüsü açın ve sonra **uygulama**  ->  **erişimi iş veya okul**  ->  *hesabınız*  ->  **bağlantısını kes** düğmesine Ayarlar seçin.

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Windows cihazlar için MDM kaydının engellenmediğinden emin olun

kayıt işleminin başarılı olabilmesi için HoloLens cihazlarınızın kaydedebileceği emin olmanız gerekir. HoloLens Windows bir cihaz olarak değerlendirildiğinden, dağıtımınızı engelleyebilen bir kayıt kısıtlaması olmaması gerekir. [Bu kısıtlamalar listesini gözden geçirin](/mem/intune/enrollment/enrollment-restrictions-set) ve cihazlarınızı kaydedeceksiniz emin olun.