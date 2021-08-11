---
title: Windows Defender Uygulama denetimi-WDAC
description: Windows Defender uygulama denetiminin ne olduğu ve HoloLens karma gerçeklik cihazlarını yönetmek için nasıl kullanılacağı hakkında genel bakış.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665565"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Uygulama denetimi-WDAC

WDAC, BT yöneticisinin cihazlarını cihazlarda uygulamaların başlatılmasını engelleyecek şekilde yapılandırmasına olanak sağlar. Bu, kullanıcının cihazdaki uygulamaları gizleyen bir kullanıcı arabirimi ile sunulduğu, ancak yine de başlatılabileceği, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır. WDAC uygulandığında, uygulamalar tüm uygulamalar listesinde görünmeye devam eder, ancak bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılabilmesini engeller.

Bir cihaza birden fazla WDAC ilkesi atanmış olabilir. Bir sistemde birden çok WDAC ilkesi ayarlandıysa, en kısıtlayıcı olanlar geçerli olur. 

> [!NOTE]
> son kullanıcılar, WDAC tarafından engellenen bir uygulamayı başlatmayı denediklerinde, HoloLens bu uygulamayı başlatamayacağı hakkında bir bildirim almaz.

aşağıda, kullanıcıların [Microsoft Intune ile HoloLens 2 cihazlarındaki uygulamalara izin vermek veya bunları engellemek için WDAC ve Windows PowerShell kullanmayı](/mem/intune/configuration/custom-profile-hololens)öğrenme kılavuzu verilmiştir.

kullanıcılar ilk örnek adımını kullanarak Windows 10 bilgisayarında yüklü olan uygulamaları ararken, sonuçların kapsamını daraltmak için birkaç deneme yapması gerekebilir.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Paketin tam adını bilmiyorsanız, bulmak için ' Get-AppxPackage-Name, en iyi \* tahmin \* ' i birkaç kez çalıştırmanız gerekebilir. Ardından, adı ' $package 1 = Get-AppxPackage-adı gerçek. PackageName ' olarak çalıştırırsınız

örneğin, Microsoft Edge için aşağıdakini çalıştırmak birden fazla sonuç döndürür, ancak bu listeden, ihtiyacınız olan tam adın Microsoft. microsoftedge olduğunu belirleyebilirsiniz.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens uygulamalar için paket aile adları

yukarıdaki kılavuzda, newPolicy.xml el ile düzenleyebilir ve yalnızca paket aile adlarıyla HoloLens yüklü uygulamalar için kurallar ekleyebilirsiniz. Bazen, ilke eklemek istediğiniz masaüstü bilgisayarınızda olmayan, kullanmak için kullanabileceğiniz uygulamalar vardır.

aşağıda, HoloLens 2 cihazları için yaygın olarak kullanılan ve In-Box uygulamaların bir listesi verilmiştir.

| Uygulama Adı                   | Paket ailesi adı                                |
|----------------------------|----------------------------------------------------|
| 3B görüntüleyici                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Uygulama yükleyicisi              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Takvim                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 kılavuzlar        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 uzaktan yardım | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Geribildirim Merkezi               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Dosya Gezgini              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Posta                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| TV & Filmler                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotoğraflar                     | MICROSOFT. Windows. Photos_8wekyb3d8bbwe             |
| Ayarlar                   | HolographicSystemSettings_cw5n1h2txyewy            |
| İpuçları                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-uygulama yükleyicisi, uygulama yükleyici uygulamasını yalnızca Microsoft Store veya MDM çözümünüzden yüklenen uygulamalar değil, uygulamaları engeller.

### <a name="how-to-find-a-package-family-name"></a>Paket aile adını bulma

bir uygulama bu listede yoksa, bir kullanıcı, bir uygulama tarafından engellenmeyen bir HoloLens 2 ' ye bağlı, packagerelativeıd 'sini ve PackageFamilyName al.

1. uygulamayı HoloLens 2 cihazınıza yüklersiniz. 
1. Ayarlar > güncelleştirmelerini açın, geliştiriciler için güvenlik > & ve **geliştirici modunu** ve ardından **cihaz portalını** etkinleştirin. 
    1. Daha fazla ayrıntı yönergesi [cihaz portalının kurulumu ve kullanımı](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)hakkında daha fazla bilgi edinin.
1. Cihaz portalı bağlandıktan sonra, **Görünümler** ' e gidin ve ardından **uygulamalar**' a gidin. 
1. Yüklü uygulamalar panelinde, açılan listeyi kullanarak yüklü uygulamayı seçin. 
1. Packagerelativeıd öğesini bulun. 
1. Uygulama karakterlerini! önüne kopyalayın, bu karakterler PackageFamilyName olacaktır.


