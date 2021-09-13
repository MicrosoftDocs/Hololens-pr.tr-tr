---
title: HoloLens bilgi noktası başvuru bilgileri
description: HoloLens cihazlarda bilgi ve örnekler.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033211"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Bilgi noktası başvuru bilgileri

bu sayfa HoloLens cihazınızın bilgi noktası modunu ayarlamaya yönelik yararlı bilgiler içerir. Bu başvurular, gelen kutusu uygulamaları için AUMIDs ve sizinkiler ve bilgi noktası modu için birkaç XML örneği içerir. Bu, birkaç farklı senaryo için kullanıma hazırlanmasının dışında yalnızca birkaç düzenleme vardır. Bilgi noktası ayarlama hakkında daha fazla bilgi için bilgi [noktası ayarlama sayfasını okuyun.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Uygulama kullanıcı modeli kimlikleri (AUMIDs)  

Bilgi noktası uygulamalarını seçme hakkında genel bilgi için bkz. [atanan erişim için uygulama seçme yönergeleri (bilgi noktası modu)](/windows/configuration/guidelines-for-assigned-access-app).

Bilgi noktası modunu yapılandırmak için bir mobil cihaz yönetimi (MDM) sistemi veya sağlama paketi kullanıyorsanız, uygulamaları belirtmek için atanan bir [yapılandırma hizmet sağlayıcısı (CSP)](/windows/client-management/mdm/assignedaccess-csp) kullanın. CSP, uygulamaları tanımlamak için [uygulama kullanıcı modeli kimliklerini (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) kullanır. Aşağıdaki tabloda, çok uygulama bilgi noktasında kullanabileceğiniz bazı yerleşik uygulamaların Aumıd 'Leri listelenmiştir.

<a id="aumids"></a>

|Uygulama Adı |AUMıD |
| --- | --- |
|3B görüntüleyici |Microsoft. Microsoft3DViewer \_ 8wekrivb3d8bbwe \! . Microsoft3DViewer |
|Takvim |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! holokamera |
|Cortana<sup>3</sup> |Microsoft. 549981C3F5F10 \_ 8wekyıb3d8bbwe \! uygulaması |
|HoloLens cihaz seçicisi (1. genel) |HoloDevicesFlow \_ cw5n1h2txyewy \! holodevicesflow |
|HoloLens 2 üzerinde cihaz seçicisi |MICROSOFT. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Dynamics 365 kılavuzlar |Microsoft. Dynamics365. guides \_ 8wekrivb3d8bbwe \! |
|Dynamics 365 uzaktan yardım |Microsoft. Microsoftremoteyardım \_ 8wekrivb3d8bbwe \! Microsoft. remoteyardım |
|Geribildirim &nbsp; Merkezi |Microsoft. WindowsFeedbackHub \_ 8wekyıb3d8bbwe \! uygulaması |
|Dosya Gezgini |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! Uygulamanızda |
|Posta |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. Mail |
|Eski Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Yeni Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! Uygulamanızda |
|Miracast<sup>4</sup> | &nbsp; |
|TV & Filmler |Microsoft. ZuneVideo \_ 8wekrivb3d8bbwe, \! Microsoft. ZuneVideo |
|OneDrive |Microsoft. MicrosoftSkyDrive \_ 8wekrivb3d8bbwe \! uygulaması |
|Fotoğraflar |MICROSOFT. Windows. Foto \_ 8wekrivb3d8bbwe \! uygulaması |
|eski Ayarlar |HolographicSystemSettings_cw5n1h2txyewy! Uygulamanızda |
|yeni Ayarlar |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Uygulamanızda |
|İpuçları |Microsoft. HoloLensTips \_ 8wekrivb3d8bbwe \! holomerstips |

> <sup>1</sup> fotoğraf veya video yakalamayı etkinleştirmek Için, Kamera uygulamasını bir bilgi noktası uygulaması olarak etkinleştirmeniz gerekir.  
> <sup>2</sup> Kamera uygulamasını etkinleştirdiğinizde aşağıdaki koşullara dikkat edin:
> - Hızlı Eylemler menüsü, fotoğraf ve video düğmelerini içerir.
> - ayrıca, resimlerle etkileşime girebilen veya bu resimleri alabileceğiniz bir uygulamayı (fotoğraflar, posta veya OneDrive) de etkinleştirmeniz gerekir.  
>  
> <sup>3</sup> Cortana bir bilgi noktası uygulaması olarak etkinleştiremeseniz bile, yerleşik sesli komutlar etkinleştirilir. Ancak, devre dışı özelliklerle ilgili komutların etkisi yoktur.  
> <sup>4</sup> Miracast doğrudan etkinleştiremezsiniz. Miracast bir bilgi noktası uygulaması olarak etkinleştirmek için Kamera uygulamasını ve cihaz seçici uygulamasını etkinleştirin.

Ayrıca, karma gerçeklik girişi bir bilgi noktası uygulaması olarak ayarlanamaz.

[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

## <a name="kiosk-xml-code-samples"></a>Bilgi noktası XML kodu örnekleri

1. [Birden çok uygulama genel atanmış erişim profili](#multiple-app-global-assigned-access-profile)
1. [Cihaz sahipleri hariç birden çok uygulama genel atanmış erişim profili](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Yerel bir hesap veya AAD Kullanıcı hesabı için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [İki AAD kullanıcısı veya daha fazlası için birden çok uygulama için erişim profili atandı](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Bir AAD grubu için birden çok uygulama atanmış erişim profili](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [İki AAD grubu veya daha fazlası için birden çok uygulamayla atanmış erişim profili](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Bir AAD hesabı ve bir AAD grubu için birden çok uygulama atanmış erişim profili](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Ziyaretçiler için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> YAPıLACAKLAR eylemlerini gereksinimlerinize göre değiştirin.

### <a name="multiple-app-global-assigned-access-profile"></a>Birden çok uygulama genel atanmış erişim profili

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Cihaz sahipleri hariç birden çok uygulama genel atanmış erişim profili

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Yerel bir hesap veya AAD Kullanıcı hesabı için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>İki AAD kullanıcısı veya daha fazlası için birden çok uygulama için erişim profili atandı

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Bir AAD grubu için birden çok uygulama atanmış erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>İki AAD grubu veya daha fazlası için birden çok uygulamayla atanmış erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Bir AAD hesabı ve bir AAD grubu için birden çok uygulama atanmış erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Ziyaretçiler için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Listeye geri dön](#kiosk-xml-code-samples) <br>
[Kimlik türünü temel alan bilgi noktası modu Için desteklenen senaryolara](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type) geri dön
