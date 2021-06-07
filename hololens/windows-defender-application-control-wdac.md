---
title: Windows Defender uygulama denetimi-WDAC
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379033"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender uygulama denetimi-WDAC

WDAC, BT yöneticisinin cihazlarını cihazlarda uygulamaların başlatılmasını engelleyecek şekilde yapılandırmasına olanak sağlar. Bu, kullanıcının cihazdaki uygulamaları gizleyen bir kullanıcı arabirimi ile sunulduğu, ancak yine de başlatılabileceği, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır. WDAC uygulandığında, uygulamalar tüm uygulamalar listesinde görünmeye devam eder, ancak bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılabilmesini engeller.

Bir cihaza birden fazla WDAC ilkesi atanmış olabilir. Bir sistemde birden çok WDAC ilkesi ayarlandıysa, en kısıtlayıcı olanlar geçerli olur. 

> [!NOTE]
> Son kullanıcılar, WDAC tarafından engellenen bir uygulamayı başlatmayı denediklerinde, HoloLens üzerinde bu uygulamayı başlatamayan hakkında bir bildirim almaz.

Aşağıda, kullanıcıların [Microsoft Intune Ile HoloLens 2 cihazlarda uygulamalara izin vermek veya bunları engellemek IÇIN WDac ve Windows PowerShell](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)'in nasıl kullanılacağını öğrenme kılavuzu verilmiştir.

Kullanıcılar ilk örnek adımını kullanarak Windows 10 bilgisayarında yüklü olan uygulamaları ararken, sonuçları daraltmak için birkaç deneme yapması gerekebilir.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Paketin tam adını bilmiyorsanız, bulmak için ' Get-AppxPackage-Name, en iyi \* tahmin \* ' i birkaç kez çalıştırmanız gerekebilir. Ardından, adı ' $package 1 = Get-AppxPackage-adı gerçek. PackageName ' olarak çalıştırırsınız

Örneğin, Microsoft Edge için aşağıdakiler çalıştırıldığında birden fazla sonuç döndürülür, ancak bu listeden, ihtiyacınız olan tam adın Microsoft. MicrosoftEdge olduğunu belirleyebilirsiniz.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens 'teki uygulamalar için paket aile adları

Yukarıdaki kılavuzda, newPolicy.xml el ile düzenleyebilir ve yalnızca paket aile adlarıyla HoloLens 'te yüklü olan uygulamalar için kurallar ekleyebilirsiniz. Bazen, ilke eklemek istediğiniz masaüstü bilgisayarınızda olmayan, kullanmak için kullanabileceğiniz uygulamalar vardır.

HoloLens 2 cihazları için yaygın olarak kullanılan ve In-Box uygulamaların bir listesi aşağıda verilmiştir.

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
| Fotoğraflar                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Ayarlar                   | HolographicSystemSettings_cw5n1h2txyewy            |
| İpuçları                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-uygulama yükleyicisi, uygulama yükleyici uygulamasını yalnızca Microsoft Store veya MDM çözümünüzden yüklenen uygulamalar değil, uygulamaları engeller.

### <a name="how-to-find-a-package-family-name"></a>Paket aile adını bulma

Bir uygulama bu listede yoksa, bir Kullanıcı, Packagerelativeıd 'sini ve PackageFamilyName Al ' ı öğrenmek için, uygulamayı engellenme olarak yükleyen bir HoloLens 2 ' ye bağlı olan cihaz portalını kullanabilir.

1. Uygulamayı HoloLens 2 cihazınıza yüklersiniz. 
1. Ayarları aç-> güncelleştirmeler & geliştiriciler Için güvenlik-> ve **Geliştirici modunu** ve ardından **cihaz portalını** etkinleştirir. 
    1. Daha fazla ayrıntı yönergesi [cihaz portalının kurulumu ve kullanımı](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)hakkında daha fazla bilgi edinin.
1. Cihaz portalı bağlandıktan sonra, **Görünümler** ' e gidin ve ardından **uygulamalar**' a gidin. 
1. Yüklü uygulamalar panelinde, açılan listeyi kullanarak yüklü uygulamayı seçin. 
1. Packagerelativeıd öğesini bulun. 
1. Uygulama karakterlerini! önüne kopyalayın, bu karakterler PackageFamilyName olacaktır.


