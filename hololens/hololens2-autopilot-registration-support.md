---
title: HoloLens 2 için Windows Autopilot kayıt desteği
description: HoloLens 2 cihazlarında Autopilot için kayıt desteğini nasıl alabileceğinizi öğrenin.
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
keywords: Autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380297"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Autopilot için HoloLens 2 kayıt desteği

Müşteriler ve Microsoft Bulut çözüm sağlayıcıları (CSP 'Ler) artık, Microsoft Desteği istekleri doğrudan göndererek HoloLens 2 cihazlarını kaydedebilir. Bu sayfada, aşağıdaki desteklenen Autopilot kayıt senaryolarıyla ilgili gereksinimler özetlenmektedir:

- **HoloLens 2 cihaz Autopilot kaydı**. HoloLens 2 cihazlarını Windows Autopilot 'a kaydetme isteği gönderir.
- **HoloLens 2 cihaz donanım karması isteği**. Müşterilerin veya CSP 'Lerin cihazları Microsoft Intune veya Microsoft Iş Ortağı Merkezi aracılığıyla kendi kendine kaydetmesi için kullanabileceği donanım karmalarını sağlamak üzere Microsoft Desteği isteği gönderir.
- **HoloLens 2 cihaz Autopilot kaydı silme**. Genellikle cihaz yaşam süresi senaryolarında kullanılan Windows Autopilot cihazları silme isteği gönderir.

Aşağıdaki tabloda kayıt isteklerini Microsoft Desteği göndermeden *önce* toplamanız gereken bilgiler ayrıntılı olarak verilmiştir.

| Gerekli bilgiler | Açıklama | Autopilot kaydı  | Donanım karması Isteği | Autopilot kaydı silme |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory kiracı KIMLIĞI    |    Azure Active Directory kiracı KIMLIĞINIZ, kuruluşunuzun adından veya etki alanından farklı olan küresel olarak benzersiz bir tanımlayıcıdır (GUID).    Kiracı KIMLIĞINIZI bulmak için [Azure portalında](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)oturum açın.    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory etki alanı adı    |   En üst düzey etki alanı adınız; Örneğin, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Sahiplik kanıtı    |   Orijinal satış faturanızı veya faturayı PDF biçiminde karşıya yükleyerek sahiplik kanıtı 'nı doğrulayın. Ekran görüntüleri kabul edilmez. Satış faturanız veya fatura şunları içermelidir: cihaz seri numaraları. Şirket adı.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Cihaz seri numaraları    |   Yeni bir satırdaki her bir cihaz seri numarasıyla, Excel dosyasını CSV biçiminde karşıya yükleyin.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Destek istekleri Gönder

> [!div class="nextstepaction"]
> [HoloLens 2 için Autopilot kayıt desteğini gönder](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
