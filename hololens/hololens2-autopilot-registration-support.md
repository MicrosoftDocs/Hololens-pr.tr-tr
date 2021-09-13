---
title: Windows HoloLens 2 için Autopilot Kayıt Desteği
description: HoloLens 2 cihazlarda Autopilot için kayıt desteği nasıl alın hakkında bilgi alın.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Otopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036492"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Autopilot için Kayıt Desteği

Müşteriler ve Microsoft Bulut Çözümü Sağlayıcıları (CSP'ler) artık HoloLens 2 cihaza doğrudan istek göndererek Microsoft Desteği. Bu sayfada, aşağıdaki desteklenen Autopilot kayıt senaryoları için gereksinimler özetlemektedir:

- **HoloLens 2 Cihaz Autopilot Kaydı**. 2 cihaz için HoloLens Autopilot'a Windows isteği gönderme.
- **HoloLens 2 Cihaz Donanım Karması İsteği.** Müşterilerin veya CSP'Microsoft Desteği cihazları Microsoft Intune veya Microsoft İş Ortağı Merkezi aracılığıyla kendi kendine kaydetmek için kullanabileceği donanım karmalarını sağlamak için Microsoft Intune'a istek İş Ortağı Merkezi.
- **HoloLens 2 Device Autopilot Deregistration**. Normalde cihaz sonu senaryolarında kullanılan Windows Autopilot'tan cihaz silme isteği göndermektedir.

Aşağıdaki tabloda, kayıt isteklerini Microsoft Desteği'a göndermeden önce toplamanız gereken bilgiler ve Microsoft Desteği. 

| Gerekli Bilgiler | Description | Autopilot Kaydı  | Donanım Karması İsteği | Autopilot KayıtSızLığı |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Kiracı Kimliği    |    Kiracı Azure Active Directory kimliğiniz, kuruluş adınızdan veya etki alanınıza göre farklı genel olarak benzersiz bir tanımlayıcıdır (GUID).    Kiracı kimliğinizi bulmak için [Azure Portal'da oturum açın.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Etki Alanı Adı    |   Üst düzey etki alanı adınız; Örneğin, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Sahiplik Kanıtı    |   Özgün satış faturasını veya faturayı PDF biçiminde karşıya yükerek sahiplik kanıtını doğrulayın. Ekran görüntüleri kabul edilemez. Satış faturası veya fatura şunları içermeli: Cihaz seri numaraları. Şirket adı.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Cihaz seri numaraları    |   Upload Excel bir satırda her cihaz seri numarasıyla CSV biçiminde bir dosya yazın.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Destek istekleri gönderme

> [!div class="nextstepaction"]
> [HoloLens 2 için Autopilot Kayıt Desteği Gönderme](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
