---
title: Windows Defender Uygulama Denetimi (WDAC)
description: Uygulama Denetimi'Windows Defender genel bakış ve karma gerçeklik cihazlarını yönetmek için HoloLens kullanma.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427894"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Uygulama Denetimi - WDAC

## <a name="overview"></a>Genel Bakış

WDAC, uygulamaların başlatılmasını HoloLens için uygulama yapılandırmayı yapılandırmaya olanak sağlar. Bilgi noktası modundan farklıdır; burada kullanıcı arabirimi uygulamaları gizler ancak yine de başlatabilirsiniz. WDAC ile uygulamaları görebilir ancak başlatılamayabilirsiniz.

> [!NOTE]
> WdAC tarafından HoloLens engellenen bir uygulamayı başlatmaya çalışan son kullanıcılara uygulamayı başlatamamaları bildirilecek.

Bir cihaza birden fazla WDAC ilkesi atanabilir. Bir sistemde birden çok WDAC ilkeleri ayarlanırsa, en kısıtlayıcı ilkeler etkili olur. 

Aşağıda, kullanıcıların wdac ve Windows PowerShell 2 cihazlarda uygulamalara izin vermek veya uygulamaları engellemek için WDAC ve [HoloLens kullanmayı Microsoft Intune.](/mem/intune/configuration/custom-profile-hololens)

Kullanıcılar ilk örnek adımı kullanarak Windows 10 bilgisayarlarında yüklü uygulamaları araysa da sonuçları daraltmak için birkaç deneme yapmaları gerekir.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Paketin tam adını bilmiyorsanız, paketi bulmak için birkaç kez 'Get-AppxPackage -name \* YourGueGuess \* ' çalıştırmanız gerekir. Ardından adı '$package 1 = Get-AppxPackage -name Actual.PackageName' çalıştırın

Örneğin, aşağıdaki kodu Microsoft Edge birden fazla sonuç dönecektir, ancak bu listeden ihtiyacınız olan tam adın Microsoft.MicrosoftEdge olduğunu tanımlayabilirsiniz.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens'da uygulamalar için Paket HoloLens

Yukarıdaki bağlantılı kılavuzda, uygulama adlarını el newPolicy.xml ve yalnızca paket aile adlarıyla HoloLens uygulamalar için kurallar ekleyebilirsiniz. Bazen, masaüstü bilgisayarınızda ilkeye eklemek istediğiniz uygulamaları kullanmak için kullanabileceğiniz uygulamalar vardır.

2 cihaz için yaygın olarak kullanılan ve In-Box uygulamaları HoloLens listesi ve ardından.

| Uygulama Adı                   | Paket Ailesi Adı                                |
|----------------------------|----------------------------------------------------|
| 3B Görüntüleyici                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Uygulama Yükleyicisi              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Takvim                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Kamera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Kılavuzları        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Geri Bildirim Merkezi               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Dosya Gezgini              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Posta                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmler & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotoğraflar                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Ayarlar                   | HolographicSystemSettings_cw5n1h2txyewy            |
| İpuçları                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 - Uygulama Yükleyicisi engelleme yalnızca Uygulama Yükleyicisi uygulamasını engellemez; Microsoft Store veya MDM çözümünüz gibi diğer kaynaklardan yüklenmiş uygulamaları engellemez.

### <a name="how-to-find-a-package-family-name"></a>Paket Aile Adı bulma

Bir uygulama bu listede yoksa, bir kullanıcı PackageRelativeID'yi belirlemek ve buradan PackageFamilyName'i almak için, engellenmiş uygulamayı yüklemiş bir HoloLens 2'ye bağlı Cihaz Portalı kullanabilir.

1. Uygulamayı 2. HoloLens yükleyin. 
1. -Ayarlar -> Update & -> Geliştiriciler için'i açın ve Ardından Geliştirici modunu **ve** ardından **Cihaz portalı'ı etkinleştirin.** 
    1. Daha fazla ayrıntı yönergeleri için cihaz portalı [kurulumu ve kullanımı hakkında daha fazla bilgi için buraya bakın.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Bağlandıktan Cihaz Portalı Görünümler'e ve **ardından Uygulamalar'a** **gidin.** 
1. Yüklü Uygulamalar panelinde, yüklü uygulamayı seçmek için açılan liste kullanın. 
1. PackageRelativeID'i bulun. 
1. Uygulama karakterlerini 'den önce `!` kopyalayın; bu karakterler PackageFamilyName'iniz olur.

