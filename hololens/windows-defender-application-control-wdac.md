---
title: Windows Defender Uygulama denetimi (WDAC)
description: Windows Defender uygulama denetiminin ne olduğu ve HoloLens karma gerçeklik cihazlarını yönetmek için nasıl kullanılacağı hakkında genel bakış.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033966"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Uygulama denetimi-WDAC

## <a name="overview"></a>Genel Bakış

WDAC, uygulamaların başlatılmasını engellemek için HoloLens yapılandırmanıza olanak tanır. Bu, Kullanıcı arabiriminin uygulamaları gizlemediği ancak yine de başlatılabileceği bilgi noktası modundan farklıdır. WDAC ile uygulamaları görebilirsiniz, ancak bunlar başlatılamaz.

> [!NOTE]
> son kullanıcılar HoloLens üzerinde WDAC tarafından engellenen bir uygulamayı başlatmayı denediklerinde, uygulamayı başlatamayamıyorum hakkında bilgilendirilmeyecektir.

Bir cihaza birden fazla WDAC ilkesi atanmış olabilir. Bir sistemde birden çok WDAC ilkesi ayarlandıysa, en kısıtlayıcı olanlar geçerli olur. 

aşağıda, kullanıcıların [Microsoft Intune ile HoloLens 2 cihazlarındaki uygulamalara izin vermek veya bunları engellemek için WDAC ve Windows PowerShell kullanmayı](/mem/intune/configuration/custom-profile-hololens)öğrenme kılavuzu verilmiştir.

kullanıcılar ilk örnek adımını kullanarak Windows 10 bilgisayarında yüklü olan uygulamaları ararken, sonuçların kapsamını daraltmak için birkaç deneme yapması gerekebilir.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Paketin tam adını bilmiyorsanız, bulmak için ' Get-AppxPackage-Name, en iyi \* tahmin \* ' i birkaç kez çalıştırmanız gerekebilir. Ardından, adı ' $package 1 = Get-AppxPackage-adı gerçek. PackageName ' olarak çalıştırırsınız

örneğin, Microsoft Edge için aşağıdaki kodu çalıştıran bir sonuç döndürür, ancak bu listeden, ihtiyacınız olan tam adın Microsoft. microsoftedge olduğunu belirleyebilirsiniz.

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
1. Uygulama karakterlerini kopyalama öncesinde `!` , bu karakterlerin PackageFamilyName olması gerekir.

