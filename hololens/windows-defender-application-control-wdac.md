---
title: Windows Defender Uygulama Denetimi - WDAC
description: Uygulama Denetimi Windows Defender nin ne olduğu ve karma gerçeklik cihazlarını yönetmek için HoloLens genel bakış.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639939"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Uygulama Denetimi - WDAC

WDAC, bir IT Yöneticisinin cihazlarda uygulama başlatmayı engellemek için cihazlarını yapılandırmasını sağlar. Bu, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır; burada kullanıcıya cihazda uygulamaları gizleyen ancak hala başlatılana bir kullanıcı arabirimi sunulmaktadır. WDAC uygulanırken, uygulamalar Hala Tüm Uygulamalar listesinde görünür durumdadır, ancak WDAC bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılamalarını durdurur.

Bir cihaza birden fazla WDAC ilkesi atanabilir. Bir sistemde birden çok WDAC ilkeleri ayarlanırsa, en kısıtlayıcı ilkeler etkili olur. 

> [!NOTE]
> Son kullanıcılar WDAC tarafından engellenen bir uygulamayı başlatmaya HoloLens uygulamanın başlatılamayacakları konusunda bir bildirim almaz.

Aşağıda, kullanıcıların wdac ve Windows PowerShell kullanarak 2 cihaz üzerinde uygulamalara izin verme veya uygulamaları engelleme hakkında bilgi HoloLens bir [kılavuz Microsoft Intune.](/mem/intune/configuration/custom-profile-hololens)

Kullanıcılar, ilk örnek adımı kullanarak Windows 10 uygulamaları araysa da sonuçları daraltmak için birkaç deneme yapmaları gerekir.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Paketin tam adını bilmiyorsanız, paketi bulmak için birkaç kez 'Get-AppxPackage -name \* YourGueGuess \* ' çalıştırmanız gerekir. Ardından adı '$package 1 = Get-AppxPackage -name Actual.PackageName' çalıştırın

Örneğin, aşağıdakini Microsoft Edge birden fazla sonuç dönecektir, ancak bu listeden ihtiyacınız olan tam adın Microsoft.MicrosoftEdge olduğunu tanımlayabilirsiniz.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens'da uygulamalar için Paket HoloLens

Yukarıda bağlantılı kılavuzda, uygulama adlarını el newPolicy.xml ve yalnızca paket aile adlarıyla HoloLens uygulamalar için kurallar ekleyebilirsiniz. Bazen, masaüstü bilgisayarınızda ilkeye eklemek istediğiniz uygulamaları kullanmak için kullanabileceğiniz uygulamalar olabilir.

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

- 1 - Uygulama Yükleyicisi yalnızca Uygulama Yükleyicisi uygulamasını engellemez; Microsoft Store veya MDM çözümünüz gibi diğer kaynaklardan yüklenmiş uygulamaları engellemez.

### <a name="how-to-find-a-package-family-name"></a>Paket Aile Adı bulma

Bir uygulama bu listede yoksa, bir kullanıcı PackageRelativeID'yi belirlemek ve buradan PackageFamilyName'i almak için, engellenmiş uygulamayı yüklemiş bir HoloLens 2'ye bağlı Cihaz Portalı kullanabilir.

1. Uygulamayı 2. HoloLens yükleyin. 
1. -Ayarlar -> Update & -> Geliştiriciler için'i açın ve Ardından Geliştirici **modunu ve** ardından **Cihaz portalı'ı etkinleştirin.** 
    1. Daha fazla ayrıntı yönergeleri için cihaz portalı [kurulumu ve kullanımı hakkında daha fazla bilgi için buraya bakın.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Bağlandıktan Cihaz Portalı Görünümler'e ve **ardından Uygulamalar'a** **gidin.** 
1. Yüklü Uygulamalar panelinde, yüklü uygulamayı seçmek için açılan liste kullanın. 
1. PackageRelativeID'i bulun. 
1. Uygulama karakterlerini !'den önce kopyalayın; bu karakterler PackageFamilyName'iniz olur.


