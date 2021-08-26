---
title: HoloLens bilgi noktası başvuru bilgileri
description: Mobil cihazlarda bilgi noktası bilgileri HoloLens örnekleri.
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
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863960"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Bilgi noktası başvuru bilgileri

Bu sayfa, cihazınızın bilgi noktası modunu HoloLens yararlı bilgiler içerir. Bu başvurular gelen kutusu uygulamaları için AUMID'leri ve sizinkileri bulmayı ve Bilgi Noktası modu için birkaç XML örneği içerir. Bu örnekler, birkaç farklı senaryo için kullanıma hazır olmaktan yalnızca birkaç düzenleme uzaktadır. Bilgi Noktası ayarlama hakkında bilgi için Bilgi [Noktası ayarlama sayfasını okuyun.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Uygulama Kullanıcı Modeli Kimlikleri (AUMIDs)  

Bilgi noktası uygulamalarını seçme hakkında genel bilgi için bkz. Atanmış erişim için uygulama seçme yönergeleri [(bilgi noktası modu)](/windows/configuration/guidelines-for-assigned-access-app).

Bilgi noktası modunu yapılandırmak için mobil Cihaz Yönetimi (MDM) sistemi veya sağlama paketi kullanıyorsanız, uygulamaları belirtmek için AssignedAccess Yapılandırma Hizmet [Sağlayıcısı'nın (CSP)](/windows/client-management/mdm/assignedaccess-csp) kullanırsınız. CSP, uygulamaları tanımlamak için Uygulama Kullanıcı Modeli Kimliklerini [(AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) kullanır. Aşağıdaki tabloda, çok uygulamalı bilgi noktası içinde kullanabileceğiniz bazı in-box uygulamalarının AUMID'leri listelemektedir.

<a id="aumids"></a>

|Uygulama Adı |AUMID |
| --- | --- |
|3B Görüntüleyici |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Takvim |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! Uygulaması |
|HoloLens (1. nesil) üzerinde Cihaz Seçici |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2'de Cihaz Seçici |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Dynamics 365 Kılavuzları |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Geri Bildirim &nbsp; Merkezi |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! Uygulaması |
|Dosya Gezgini |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Posta |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Eski Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Yeni Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmler & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! Uygulaması |
|Fotoğraflar |Microsoft. Windows. Fotoğraflar \_ 8wekyb3d8bbwe \! Uygulaması |
|Eski Ayarlar |HolographicSystemSettings_cw5n1h2txyewy! App |
|Yeni Ayarlar |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|İpuçları |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Fotoğraf veya video yakalamayı etkinleştirmek için Kamera uygulamasını bilgi noktası uygulaması olarak etkinleştirmeniz gerekir.  
> <sup>2</sup> Kamera uygulamasını etkinleştirirken aşağıdaki koşulları takip edin:
> - Hızlı Eylemler menüsünde Fotoğraf ve Video düğmeleri bulunur.
> - Ayrıca, resimlerle etkileşim kurarak veya resim ala bir uygulama (Fotoğraflar, Posta veya OneDrive gibi) etkinleştirmeniz gerekir.  
>  
> <sup>3</sup> Bilgi noktası uygulaması olarak Cortana bile yerleşik sesli komutlar etkinleştirilir. Ancak, devre dışı özelliklerle ilgili komutların hiçbir etkisi yoktur.  
> <sup>4</sup> Doğrudan Miracast etkinleştiresiniz. Bilgi noktası Miracast kamera uygulamasını ve Cihaz Seçici uygulamasını etkinleştirin.

Buna ek olarak Karma Gerçeklik Giriş, bilgi noktası uygulaması olarak ayarlanmaz.

Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Bilgi Noktası XML Kod Örnekleri

1. [Birden çok uygulama genel atanan erişim profili](#multiple-app-global-assigned-access-profile)
1. [Cihaz sahipleri hariç birden çok uygulama genel atanan erişim profili](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Yerel bir hesap veya AAD kullanıcı hesabı için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [İki AAD kullanıcısı veya daha fazlası için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Bir AAD grubu için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [İki AAD grubu veya daha fazlası için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Bir AAD hesabı ve bir AAD grubu için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Ziyaretçiler için birden çok uygulama tarafından atanan erişim profili](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> TODO eylemlerini gereksinimlerinize göre değiştirin.

### <a name="multiple-app-global-assigned-access-profile"></a>Birden çok uygulama genel atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Cihaz sahipleri hariç birden çok uygulama genel atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Yerel bir hesap veya AAD kullanıcı hesabı için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>İki AAD kullanıcısı veya daha fazlası için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Bir AAD grubu için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>İki AAD grubu veya daha fazlası için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Bir AAD hesabı ve bir AAD grubu için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Ziyaretçiler için birden çok uygulama tarafından atanan erişim profili

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Listeye dön](#kiosk-xml-code-samples) <br>
Kimlik [türüne göre bilgi noktası modu için desteklenen senaryolara geri dönme](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
