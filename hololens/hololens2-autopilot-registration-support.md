---
title: Windows HoloLens 2 için Autopilot kayıt desteği
description: HoloLens 2 cihazlarındaki Autopilot için kayıt desteğini nasıl alabileceğinizi öğrenin.
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
ms.openlocfilehash: 2304e7ec18eb531cce431fb93c7abf38f2c9a1cef30f0d6c6fcaac6c95281f8e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661783"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Autopilot için HoloLens 2 kayıt desteği

müşteriler ve Microsoft Bulut çözüm sağlayıcıları (csp 'ler), artık istekleri Microsoft Desteği doğrudan göndererek HoloLens 2 cihazları kaydedebilir. Bu sayfada, aşağıdaki desteklenen Autopilot kayıt senaryolarıyla ilgili gereksinimler özetlenmektedir:

- **HoloLens 2 cihaz Autopilot kaydı**. HoloLens 2 cihazlarını Windows Autopilot 'a kaydetme isteği gönderir.
- **2 cihaz donanım karma isteği HoloLens**. müşterilerin veya csp 'lerin cihazları Microsoft Intune veya Microsoft iş ortağı merkezi aracılığıyla kendi kendine kaydetmesi için kullanabileceği donanım karmalarını sağlamak üzere Microsoft Desteği isteği gönderir.
- **HoloLens 2 cihaz Autopilot kaydı silme**. genellikle cihaz yaşam süresi senaryolarında kullanılan Windows Autopilot 'dan cihazları silme isteği gönderir.

Aşağıdaki tabloda kayıt isteklerini Microsoft Desteği göndermeden *önce* toplamanız gereken bilgiler ayrıntılı olarak verilmiştir.

| Gerekli bilgiler | Description | Autopilot kaydı  | Donanım karması Isteği | Autopilot kaydı silme |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Kiracı KIMLIĞI    |    Azure Active Directory kiracı kimliğiniz, kuruluşunuzun adından veya etki alanından farklı olan küresel olarak benzersiz bir tanımlayıcıdır (guıd).    Kiracı KIMLIĞINIZI bulmak için [Azure portalında](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)oturum açın.    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Etki alanı adı    |   En üst düzey etki alanı adınız; Örneğin, contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Sahiplik kanıtı    |   Orijinal satış faturanızı veya faturayı PDF biçiminde karşıya yükleyerek sahiplik kanıtı 'nı doğrulayın. Ekran görüntüleri kabul edilmez. Satış faturanız veya fatura şunları içermelidir: cihaz seri numaraları. Şirket adı.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Cihaz seri numaraları    |   yeni bir satırdaki her bir cihaz seri numarası ile CSV biçiminde Excel dosya Upload.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Destek istekleri Gönder

> [!div class="nextstepaction"]
> [HoloLens 2 için Autopilot kayıt desteğini gönder](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
