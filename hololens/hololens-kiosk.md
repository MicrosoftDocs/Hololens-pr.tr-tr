---
title: Bilgi HoloLens bilgi noktası olarak ayarlama
description: Mobil cihazlardaki uygulamaları kilitlemek için bilgi noktası yapılandırması ayarlamayı ve HoloLens öğrenin.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9d9e521f3e337b3a48a60c19e52bfeb3186507af
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640364"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Bilgi HoloLens bilgi noktası olarak ayarlama

Bir HoloLens, cihazı bilgi noktası modunda çalıştırılacak şekilde yapılandırarak, sabit amaçlı bir cihaz (bilgi noktası olarak da adlandırılan) olarak işleve sahip bir cihaz yapılandırabilirsiniz. Bilgi noktası modu, cihazda kullanılabilen uygulamaları (veya kullanıcıları) sınırlar. Bilgi noktası modu, bir HoloLens cihazı iş uygulamalarına ayırma veya HoloLens uygulama tanıtımda kullanma için kullanabileceğiniz kullanışlı bir özelliktir.

Bu makalede, bilgi noktası yapılandırmasının belirli cihazlara özgü yönleri hakkında HoloLens sağlar. Farklı türlerde bilgi Windows bilgi noktası ve nasıl yapılandırılacakları hakkında genel bilgi için bkz. Masaüstü sürümlerinde [bilgi Windows yapılandırma.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Bilgi noktası modu, kullanıcı cihazda oturum açınca hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. Bir "izin verilen" uygulamanın izin verilmiyor başka bir uygulamayı açmasına engel olmaz. Uygulamaların veya işlemlerin açılmasını engellemek için uygun ilkeleri Windows Defender Uygulama [Denetimi (WDAC) CSP'lerini](/windows/client-management/mdm/applicationcontrol-csp) kullanın.
>
> Kullanıcılara 2 Microsoft hizmetleri gelişmiş güvenlik düzeyi verme hakkında daha fazla bilgi HoloLens, Durum ayrımı ve yalıtımı [- Defender korumaları hakkında](security-state-separation-isolation.md#defender-protections)daha fazla bilgi okuyun. Veya wdac ve Windows PowerShell 2 cihaz üzerinde uygulamalara izin vermek veya HoloLens engellemek [için WDAC](/mem/intune/configuration/custom-profile-hololens)ve Microsoft Intune.

Bilgi noktası modunu tek uygulamalı veya çoklu uygulama yapılandırmasında kullanabilir ve bilgi noktası yapılandırmasını ayarlamak ve dağıtmak için üç işlemden birini kullanabilirsiniz.

> [!IMPORTANT]  
> Çoklu uygulama yapılandırmasını silmek, atanan erişim özelliğinin oluşturduğu kullanıcı kilitleme profillerini kaldırır. Ancak, tüm ilke değişikliklerini geri döndürmez. Bu ilkeleri geri dönmek için cihazı fabrika ayarlarına sıfırlamanız gerekir.

## <a name="plan-the-kiosk-deployment"></a>Bilgi noktası dağıtımını planlama

Bilgi Noktasınızı planlarken aşağıdaki soruları yanıtlayabileceksiniz. Bu sayfayı okurken göz önünde bulundurulması gereken bazı kararlar ve bu sorularla ilgili dikkat edilmesi gereken bazı noktalar.
1. **Who Bilgi Noktası'nızı ve hangi [hesap türünü](hololens-identity.md) kullanacak?** Bu, büyük olasılıkla önceden aldığı ve Bilgi Noktasınız için ayar yapmamanız gereken bir karardır, ancak Bilgi Noktası'nın daha sonra nasıl atanması gerektiğini etkiler.
1. **Kullanıcı/grup başına farklı Bilgi Noktası veya bazıları için etkinleştirilmemiş bilgi noktası mı gerekiyor?** Böyle bir bilgi noktası oluşturmak için XML ile bilgi noktası oluşturmanız gerekir. 
1. **Bilgi Noktası'nıza kaç uygulama gelecek?** 1'den fazla uygulama varsa, çok uygulamalı bilgi noktası gerekir. 
1. **Bilgi Noktası'nıza hangi uygulama gelecek?** Lütfen aşağıdaki AUMID listemizi kullanarak kendi uygulamanıza In-Box uygulamalarınızı ekleyin.
1. **Bilgi Noktası'nızı nasıl dağıtmayı planlısınız?** Cihazı MDM'ye kaydedıyorsanız Bilgi Noktası'nızı dağıtmak için MDM'yi kullanmanızı öneririz. MDM kullanıyorsanız Sağlama Paketi ile dağıtım kullanılabilir.  

### <a name="kiosk-mode-requirements"></a>Bilgi noktası modu gereksinimleri

Bilgi noktası modunu kullanmak HoloLens 2 cihazdan herhangi birini yapılandırabilirsiniz.

> [!IMPORTANT]
> Bilgi noktası modu yalnızca cihazın cihaza bağlı Windows Holographic for Business. 2 HoloLens tüm cihazlar Windows Holographic for Business ve başka sürüm yoktur. Her HoloLens 2 cihaz, Bilgi Noktası modunu kutudan çıkararak çalıştırabilirsiniz.
>
> HoloLens (1. nesil) cihazların hem işletim sistemi derlemesi hem de işletim sistemi sürümü açısından yükseltilleri gerekir. Aşağıda bir HoloLens (1. nesil) sürümünü Windows Holographic for Business [edinebilirsiniz.](hololens1-upgrade-enterprise.md) Bir HoloLens (1. nesil) cihazı bilgi noktası modunu kullanmak üzere güncelleştirmek için önce cihazın Windows 10, sürüm 1803 veya sonraki bir sürümde çalıştırıla olduğundan emin olun. HoloLens (1. nesil) cihazınızı varsayılan derlemeye kurtarmak için Windows Cihaz Kurtarma Aracı'nı kullandıysanız veya en son güncelleştirmeleri yüklemişsanız, cihazınız yapılandırmaya hazırdır.

> [!IMPORTANT]  
> Bilgi noktası modunda çalıştırılacak cihazların korunmasına yardımcı olmak için USB bağlantısı gibi özellikleri kapatan cihaz yönetimi ilkeleri eklemeyi göz önünde bulundurabilirsiniz. Ayrıca, otomatik güncelleştirmelerin iş saatleri içinde oluşmay olduğundan emin olmak için güncelleştirme halkası ayarlarınızı kontrol edin.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Tek uygulamalı bilgi noktası veya çoklu uygulama bilgi noktası arasında karar verme

Tek uygulamalı bilgi noktası, kullanıcı cihazda oturum açınca belirtilen uygulamayı başlatır. Başlat menüsü olduğu gibi devre dışı Cortana. Bir HoloLens 2 cihazı Başlangıç hareketini [yanıtlamaz.](hololens2-basic-usage.md#start-gesture) Bir HoloLens (1. nesil) cihaz bloom hareketini [yanıtlamaz.](hololens1-basic-usage.md) Yalnızca bir uygulama çalıştırılana kadar kullanıcı diğer uygulamaları ekser.

Çoklu uygulama bilgi noktası, kullanıcı Başlat menüsü oturum açtırarak ilgili bilgileri görüntüler. Bilgi noktası yapılandırması, veri noktası yapılandırmasında hangi uygulamaların Başlat menüsü. Kullanıcılara yalnızca kullanmaları gereken şeyleri sunarak ve kullanmaları gerek olmayan şeyleri kaldırarak kolay anlaşılır bir deneyim sağlamak için çoklu uygulama bilgi noktası kullanabilirsiniz.

Aşağıdaki tablo, farklı bilgi noktası modlarında özellik özelliklerini listeler.

| &nbsp; |Başlat menüsü |Hızlı Eylemler menüsü |Kamera ve video |Miracast |Cortana |Yerleşik sesli komutlar |
| --- | --- | --- | --- | --- | --- | --- | 
|Tek uygulamalı bilgi noktası |Devre dışı |Devre dışı |Devre dışı |Devre dışı   |Devre dışı |Etkin<sup>1</sup> |
|Çoklu uygulama bilgi noktası |Etkin |Etkin<sup>2</sup> |Kullanılabilir<sup>2</sup> |Kullanılabilir<sup>2</sup> |Kullanılabilir<sup>2, 3</sup>  |Etkin<sup>1</sup> |

> <sup>1</sup> Devre dışı özelliklerle ilgili ses komutları çalışmaz.  
> <sup>2</sup> Bu özellikleri yapılandırma hakkında daha fazla bilgi için bkz. [Bilgi noktası uygulamalarını seçme.](#plan-kiosk-apps)  
> <sup>3</sup> Cortana devre dışı bırakılmış olsa bile, yerleşik sesli komutlar etkinleştirilir.

Aşağıdaki tabloda, farklı bilgi noktası modlarının kullanıcı desteği özellikleri liste bulunmaktadır.

| &nbsp; |Desteklenen kullanıcı türleri | Otomatik oturum açma | Birden çok erişim düzeyi |
| --- | --- | --- | --- |
|Tek uygulamalı bilgi noktası |Azure Active Directory (Azure AD) veya yerel hesapta Yönetilen Hizmet Hesabı (MSA) |Yes |Hayır |
|Çoklu uygulama bilgi noktası |Azure AD hesabı |Hayır |Yes |

Bu özellikleri kullanma örnekleri için aşağıdaki tabloya bakın.

|Aşağıdakiler için tek uygulamalı bilgi noktası kullanın: |Aşağıdakiler için çoklu uygulama bilgi noktası kullanın: |
| --- | --- |
|Yalnızca yeni çalışanlar için Dynamics 365 Kılavuzu'ları çalıştıran bir cihaz. |Bir dizi çalışan için hem Kılavuzları hem de Uzaktan Yardımı çalıştıran bir cihaz. |
|Yalnızca özel bir uygulama çalıştıran bir cihaz. |Çoğu kullanıcı için bilgi noktası işlevi (yalnızca özel bir uygulama çalıştıran) ancak belirli bir kullanıcı grubu için standart bir cihaz olarak çalışan bir cihaz. |

### <a name="plan-kiosk-apps"></a>Bilgi noktası uygulamalarını planlama

Bilgi noktası uygulamalarını seçme hakkında genel bilgi için bkz. Atanmış erişim için uygulama seçme yönergeleri [(bilgi noktası modu)](/windows/configuration/guidelines-for-assigned-access-app).

Tek uygulamalı Windows Cihaz Portalı bilgi noktası yapılandırmak için uygulamayı kullanırsanız, kurulum işlemi sırasında uygulamayı seçersiniz.  

Bilgi noktası modunu yapılandırmak için mobil Cihaz Yönetimi (MDM) sistemi veya sağlama paketi kullanıyorsanız, uygulamaları belirtmek için AssignedAccess Yapılandırma Hizmet [Sağlayıcısı'nın (CSP)](/windows/client-management/mdm/assignedaccess-csp) kullanırsınız. CSP, uygulamaları tanımlamak için Uygulama Kullanıcı Modeli Kimliklerini [(AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) kullanır. Aşağıdaki tabloda, çok uygulama bilgi noktasında kullanabileceğiniz bazı yerleşik uygulamaların Aumıd 'Leri listelenmiştir.

> [!IMPORTANT]
> Bilgi noktası modu, bir Kullanıcı cihazda oturum açtığında hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. "İzin verilen" bir uygulamanın, izin verilmeyen başka bir uygulamayı açmasını durdurmaz. bu davranışı kısıtlamadığımızda, uygulamalar hala Edge, dosya gezgini ve Microsoft Store uygulamalardan başlatılabilir. bir bilgi noktasında başlatmayı istemediğiniz belirli uygulamalar varsa, uygun ilkeler oluşturmak için [Windows Defender uygulama denetimi (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp) kullanın. 
> 
> Ayrıca, karma gerçeklik girişi bir bilgi noktası uygulaması olarak ayarlanamaz.

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
|Miracast<sup>4</sup> |&nbsp; |
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

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Kullanıcılar veya gruplar için bilgi noktası profillerini planlayın

XML dosyasını oluştururken veya bir bilgi noktası ayarlamak için Intune 'un Kullanıcı ARABIRIMINI kullanırken, bilgi noktası için kimin Kullanıcı olacağını göz önünde bulundurmanız gerekir. Bilgi noktası yapılandırması, tek bir hesap veya Azure AD gruplarıyla sınırlı olabilir. 

Genellikle kiosks, bir kullanıcı veya Kullanıcı grubu için etkinleştirilir. Ancak kendi XML bilgi noktalarınızı yazmayı planlıyorsanız, bu durumda, kimlik bilgi noktası, kimliğe bakılmaksızın cihaz düzeyinde uygulanan genel atanan erişimi düşünmek isteyebilirsiniz. Bu appeals, [genel atanan erişim Kiisleri hakkında daha fazla bilgi edinmek için.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Bir XML dosyası oluşturuyorsanız:
-   Birden çok bilgi noktası profili oluşturun ve her biri farklı kullanıcılara/gruplara atayın. Birçok uygulaması olan Azure AD grubunuz için bir bilgi noktası ve tekil bir uygulamayla birden çok uygulama bilgi noktası olan bir ziyaretçi.
-   Bilgi noktası yapılandırmanıza bir **profil kimliği** adı verilir ve bır GUID 'si eklenir.
-   Bu profili, kullanıcı türünü belirterek ve **DefaultProfile kimliği** için aynı GUID 'yi kullanarak, yapılandırmalarını bölümünde atayacaksınız.
- bir XML dosyası oluşturulabilir, ancak özel bir OMA urı cihaz yapılandırma profili oluşturularak ve bu cihaz, urı değeri kullanılarak HoloLens cihaz grubuna uygulanarak MDM aracılığıyla bir cihaza uygulanabilir:./device/vendor/msft/atandaccess/configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune 'da bir bilgi noktası oluşturuyorsanız.
-   Her cihaz yalnızca tek bir bilgi noktası profili alabilir, aksi takdirde bir çakışma oluşturur ve hiç bilgi noktası yapılandırması almaz. 
    -   Bilgi noktası yapılandırma profiliyle ilgili olmayan cihaz kısıtlamaları gibi diğer profil ve ilke türleri bilgi noktası yapılandırma profiliyle çakışmaz.
-   Bilgi noktası, Kullanıcı oturum açma türünün bir parçası olan tüm kullanıcılar için etkin olacak, bu, bir kullanıcı veya Azure AD grubuyla ayarlanır. 
-   Bilgi noktası yapılandırması ayarlandıktan ve **Kullanıcı oturum açma türü** (bilgi noktasında oturum açabilen kullanıcılar) ve uygulamalar seçiliyse, cihaz yapılandırmasının hala bir gruba atanması gerekir. Atanan gruplar, bilgi noktası cihaz yapılandırmasını hangi cihazların alacağını belirler, ancak bilgi noktası etkinse, ile etkileşime girmez. 
    - Intune 'da yapılandırma profillerinin atanmasındaki etkileri hakkında tam bir açıklama için, bkz. [Microsoft Intune kullanıcı ve cihaz profilleri atama](/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Bir dağıtım yöntemi seçin

Bilgi noktası yapılandırması dağıtmak için aşağıdaki yöntemlerden birini seçebilirsiniz:

- [Microsoft Intune veya diğer mobil cihaz yönetimi (MDM) hizmeti](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Sağlama paketi](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Cihaz portalı](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Bu yöntem, cihazda geliştirici modunun etkinleştirilmesini gerektirdiğinden, bunu yalnızca gösteriler için kullanmanızı öneririz.

Aşağıdaki tabloda, her bir dağıtım yönteminin özellikleri ve avantajları listelenmektedir.

| &nbsp; |Windows cihaz portalını kullanarak dağıtma |Sağlama paketi kullanarak dağıtma |MDM kullanarak dağıtma |
| --------------------------- | ------------- | -------------------- | ---- |
|Tek uygulama bilgi noktaları dağıtın   | Yes           | Yes                  | Yes  |
|Çoklu uygulama bilgi noktaları dağıtma    | Hayır            | Yes                  | Yes  |
|Yalnızca yerel cihazlara dağıt | Yes           | Yes                  | Hayır   |
|Geliştirici modunu kullanarak dağıtma |Gerekli       | Gerekli değil            | Gerekli değil   |
|Azure Active Directory kullanarak dağıtma (Azure AD)  | Gerekli değil            | Gerekli değil                   | Gerekli  |
|Otomatik olarak dağıt      | Hayır            | Hayır                   | Yes  |
|Dağıtım hızı            | Hızlı       | Hızlı                 | Yavaş |
|Büyük ölçekte dağıtma | Önerilmez    | Önerilen        | Önerilen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için Microsoft Intune veya diğer MDM kullanın

Microsoft Intune veya başka bir MDM sistemi kullanarak bilgi noktası modunu ayarlamak için aşağıdaki adımları izleyin.

1. [Cihazları kaydetmeyi hazırlayın](#mdmenroll).
1. [Bilgi noktası yapılandırma profili oluşturun](#mdmprofile).
1. Bilgi noktası 'nı yapılandırın.
   - [Tek uygulama bilgi noktası için ayarları yapılandırın](#mdmconfigsingle).
   - [Birden çok uygulama bilgi noktası için ayarları yapılandırın](#mdmconfigmulti).
1. [Bilgi noktası yapılandırma profilini bir gruba atayın](#mdmassign).
1. Cihazları dağıtın.
   - [Tek uygulama bilgi noktası dağıtın](#mdmsingledeploy).
   - [Birden çok uygulama bilgi noktası dağıtın](#mdmmultideploy).

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, 1 &ndash; . adım cihazları kaydetmeyi hazırlama

MDM sisteminizi, kullanıcı ilk kez oturum açtığında HoloLens cihazları otomatik olarak kaydedecek şekilde yapılandırabilir veya kullanıcıların cihazları el ile kaydetmelerini sağlayabilirsiniz. Cihazların Azure AD etki alanına katılması ve uygun gruplara atanması da gerekir.

cihazları kaydetme hakkında daha fazla bilgi için bkz. [Windows cihazlar için MDM ve ıntune kayıt yöntemlerine](/mem/intune/enrollment/windows-enrollment-methods) [kaydolma HoloLens](hololens-enroll-mdm.md) .

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, adım 2 &ndash; bilgi noktası yapılandırma profili oluşturma

1. [Azure](https://portal.azure.com/) portalını açın ve Intune yönetici hesabınızda oturum açın.
1. **Microsoft Intune**  >  **cihaz yapılandırması-profiller**  >  **profil oluştur**' u seçin.
1. Bir profil adı girin.
1. **Platform**  >  **Windows 10 ve üstünü** seçin ve ardından **profil türü**  > **cihaz kısıtlamaları**' nı seçin.
1.   >  **Bilgi noktası** Yapılandır ' ı seçin ve ardından aşağıdakilerden birini seçin:
   - Tek uygulama bilgi noktası oluşturmak için, **bilgi noktası modu**  >  **tek uygulama bilgi noktası**' nı seçin.
   - Birden çok uygulama bilgi noktası oluşturmak için **bilgi noktası modu**  >  **çoklu uygulama bilgi noktası**' nı seçin.
1. Bilgi noktası 'nı yapılandırmaya başlamak için **Ekle**' yi seçin.

Sonraki adımlarınız, istediğiniz bilgi noktası türüne göre farklılık gösterir. Daha fazla bilgi için, aşağıdaki seçeneklerden birini seçin:  

- [Tek uygulama bilgi noktası](#mdmconfigsingle)
- [Çoklu uygulama bilgi noktası](#mdmconfigmulti)

bilgi noktası yapılandırma profili oluşturma hakkında daha fazla bilgi için bkz. [Windows 10 ve Windows Holographic for Business cihaz ayarları, ıntune kullanarak adanmış bir bilgi noktası olarak çalışacak şekilde](/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, adım 3 (tek uygulama) &ndash;  tek uygulama bilgi noktası için ayarları yapılandırma

Bu bölüm, tek bir uygulama bilgi noktası gerektiren ayarları özetler. Daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- Intune 'da bir bilgi noktası yapılandırma profilini yapılandırma hakkında daha fazla bilgi için, bkz. [Microsoft Intune kullanarak bilgi noktası modunu yapılandırma](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Intune 'daki tek uygulama bilgi noktaları için kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [tek tam ekran uygulama bilgi noktaları](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir XML yapılandırması kullanmanız gerekiyorsa, [bilgi noktası yapılandırmasını tanımlayan BIR XML dosyası oluşturun](#ppkioskconfig).

1. **Kullanıcı oturum açma türü**  >  **Yerel Kullanıcı hesabı**' nı seçin ve ardından bilgi noktasında oturum açan yerel (cihaz) hesabın veya Microsoft hesabının (MSA) Kullanıcı adını girin.
   > [!NOTE]  
   > **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.
1. **Uygulama türü**  >  **depolama uygulaması**' nı seçin ve ardından listeden bir uygulama seçin.

Bir sonraki adımınız, profili bir gruba [atacaktır](#mdmassign) .

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, adım 3 (çoklu uygulama) &ndash; birden çok uygulama bilgi noktası için ayarları yapılandırma

Bu bölümde, çok uygulama bilgi noktası gerektiren ayarlar özetlenmektedir. Daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- Intune 'da bir bilgi noktası yapılandırma profilini yapılandırma hakkında daha fazla bilgi için, bkz. [Microsoft Intune kullanarak bilgi noktası modunu yapılandırma](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Intune 'da çoklu uygulama bilgi noktaları için kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [çoklu uygulama bilgi noktaları](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir XML yapılandırması kullanmanız gerekiyorsa, [bilgi noktası yapılandırmasını tanımlayan BIR XML dosyası oluşturun](#ppkioskconfig). Bir XML dosyası kullanırsanız, [Başlangıç yerleşimini](#start-layout-for-hololens)eklediğinizden emin olun.  
- İsteğe bağlı olarak, Intune veya diğer MDM hizmetleriyle özel bir başlangıç düzeni kullanabilirsiniz. Daha fazla bilgi için bkz. [MDM Için Başlangıç düzeni dosyası (Intune ve diğerleri)](#start-layout-file-for-mdm-intune-and-others).

1. **hedef Windows 10 S modunda cihazlarda**  >  **hayır**' ı seçin.  
>[!NOTE]  
> S modu Windows Holographic for Business desteklenmez.

1. **kullanıcı oturum açma türü**  >  **Azure AD kullanıcı veya grup** veya **kullanıcı oturum açma türü**  >  **HoloLens ziyaretçi**' yı seçin ve ardından bir veya daha fazla kullanıcı grubu veya hesabı ekleyin.  

   Yalnızca **Kullanıcı oturum açma türünde** belirttiğiniz gruplara veya hesaplara ait kullanıcılar bilgi noktası deneyimini kullanabilir.

1. Aşağıdaki seçenekleri kullanarak bir veya daha fazla uygulama seçin:
   - Karşıya yüklenen bir iş kolu uygulaması eklemek için **Mağaza uygulaması Ekle** ' yi seçin ve ardından istediğiniz uygulamayı seçin.
   - Kendi AUMıD 'sini belirterek bir uygulama eklemek için **aumıd tarafından Ekle** ' yi seçin ve sonra uygulamanın aumıd 'sini girin. [Kullanılabilir AUMIDs listesine bakın](#aumids)

Bir sonraki adımınız, profili bir gruba [atacaktır](#mdmassign) .

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, adım 4 &ndash; bilgi noktası yapılandırma profilini bir gruba atama

Bilgi noktası yapılandırmasının dağıtımını istediğiniz yeri ayarlamak için bilgi noktası yapılandırma profilinin **atamalar** sayfasını kullanın. en basit durumda, bilgi noktası yapılandırma profilini cihaz MDM 'ye kaydedildiğinde HoloLens cihazı içerecek bir gruba atarsınız.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5. adım (tek uygulama) &ndash; tek uygulama bilgi noktası dağıtın

Bir MDM sistemi kullandığınızda, bu cihazı OOBE sırasında MDM 'ye kaydedebilirsiniz. OOBE bittikten sonra cihazda oturum açmak kolaydır.

OOBE sırasında şu adımları izleyin:

1. Bilgi noktası yapılandırma profilinde belirttiğiniz hesabı kullanarak oturum açın.
1. Cihazı kaydedin. Cihazın, bilgi noktası yapılandırma profilinin atandığı gruba eklendiğinden emin olun.
1. Mağaza uygulamasının indirmesi ve yüklemesi ve ilkelerin uygulanması için, OOBE 'nin bitmesini bekleyin. Ardından cihazı yeniden başlatın.

Cihazda bir sonraki oturum açışınızda bilgi noktası uygulamasının otomatik olarak başlatılması gerekir.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız, [atama durumunu kontrol](/intune/configuration/device-profile-monitor)edin.

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5. adım (çoklu uygulama) &ndash; çok uygulama bilgi noktası dağıtma

Bir MDM sistemi kullandığınızda, cihazı Azure AD kiracınıza katılabilir ve bu cihazı OOBE sırasında MDM 'ye kaydedebilirsiniz. Uygunsa, OOBE işlemi sırasında kullanılabilir olmaları için kullanıcılara kayıt bilgilerini sağlayın.

> [!NOTE]  
> Bilgi noktası yapılandırma profilini Kullanıcı içeren bir gruba atadıysanız, bu kullanıcı hesaplarından birinin cihazda oturum açmak için ilk hesap olduğundan emin olun.

OOBE sırasında şu adımları izleyin:

1. **Kullanıcı oturum açma türü** grubuna ait olan hesabı kullanarak oturum açın.
1. Cihazı kaydedin.
1. Bilgi noktası yapılandırma profilinin parçası olan tüm uygulamaların indirilip yüklenmesini bekleyin. Ayrıca, ilkelerin uygulanması için bekleyin.  
1. OOBE tamam olduktan sonra, Microsoft mağazasından veya yan yükleme ile ek uygulamalar yükleyebilirsiniz. [Cihazın ait](/mem/intune/apps/apps-deploy#assign-an-app) olduğu grup için gerekli uygulamalar otomatik olarak yüklenir.
1. Yükleme tamam olduktan sonra cihazı yeniden başlatın.

Kullanıcı oturum açma türüne ait bir hesap kullanarak cihazda bir sonraki oturum açma **işlemisinde** bilgi noktası uygulaması otomatik olarak başlatılacaktır.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız atama [durumunu kontrol edin.](/intune/configuration/device-profile-monitor)

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Tek uygulamalı veya çok uygulamalı bilgi noktası ayarlamak için sağlama paketi kullanma

Bilgi noktası modunu bir sağlama paketi kullanarak ayarlamak için aşağıdaki adımları izleyin.

1. [Başlangıç düzeni de dahil olmak üzere bilgi noktası yapılandırmasını tanımlayan](#ppkioskconfig)bir XML [dosyası oluşturun.](#start-layout-for-hololens)
2. [XML dosyasını sağlama paketine ekleyin.](#ppconfigadd)
3. [Sağlama paketini HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Sağlama paketi, 1. adım &ndash; Bilgi noktası yapılandırması XML dosyası oluşturma

Aşağıdakiler [dışında, Windows](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)masaüstü için bilgi noktası yapılandırma XML dosyası oluşturmak için genel yönergeleri izleyin:

- Klasik Windows (Win32) dahil değildir. HoloLens bu uygulamaları desteklemez.
- Veri kaynağı [için Başlangıç düzeni XML'ini](#start-layout-for-hololens) HoloLens.
- İsteğe bağlı: Bilgi noktası yapılandırmasına konuk erişimi ekleme

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>İsteğe bağlı: Bilgi noktası yapılandırmasına konuk erişimi ekleme

XML [ **dosyasının Configs** bölümünde,](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)konukların bilgi noktası kullanmasına izin vermek için **Ziyaretçi** adlı özel bir grup yapılandırabilirsiniz. Bilgi noktası Ziyaretçi özel grubunu destekleyecek **şekilde** yapılandırıldığında oturum açma sayfasına **"Konuk"** seçeneği eklenir. **Konuk** hesabı için parola gerekli değildir ve hesap oturumlarını sildiğinde hesapla ilişkili tüm veriler silinir.

Konuk hesabını etkinleştirmek **için** bilgi noktası yapılandırma XML'inize aşağıdaki kod parçacığını ekleyin:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Ziyaretçi Otomatik OturumLarını Etkinleştirme

[Holographic, Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha sonra derlemelerde:
- AAD ve ADD olmayan yapılandırmalar, ziyaretçi hesaplarının Bilgi Noktası modları için otomatik oturum açma özelliğinin etkinleştirilmelerini destekler.

##### <a name="non-aad-configuration"></a>AAD dışı yapılandırma

1. Şunları içeren bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için Çalışma Zamanı ayarlarını/AssignedAccess'i yapılandırıyor.
    1. İsteğe bağlı olarak, daha sonra yönetilsin diye cihazı MDM'ye (Çalışma zamanı ayarları/Çalışma Alanı/Kayıtlar) kaydediyor.
    1. Yerel hesap oluşturma
2. [Sağlama paketini uygulama.](hololens-provisioning.md)

##### <a name="aad-configuration"></a>AAD yapılandırması

Bilgi noktası modu için yapılandırılan AAD'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak Ziyaretçi hesabında oturum açmasını sağlar. Ziyaretçi hesabında oturum açıldıktan sonra, ziyaretçi başlat menüsünden açıkça oturum açıncaya veya cihaz yeniden başlatana kadar cihaz yeniden oturum açma isteminde olmayacaktır.

Ziyaretçi Otomatik oturum açma işlemi özel [OMA-URI ilkesi aracılığıyla yönetilebilir:](/mem/intune/configuration/custom-settings-windows-10)

- URI değeri: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| İlke |Açıklama |Yapılandırmalar 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Bir Ziyaretçinin Bilgi Noktası'da otomatik olarak oturum açmasını sağlar. | 1 (Evet), 0 (Hayır, varsayılan.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens için Yer Tutucu Başlangıç düzeni

Çok uygulamalı [bilgi noktası yapılandırmak](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) için sağlama paketi kullanıyorsanız, yordam başlangıç düzeni gerektirir. Başlangıç düzeni özelleştirmesi, Windows Holographic for Business. Bu nedenle, bir yer tutucu Başlangıç düzeni kullanabilirsiniz.

> [!NOTE]  
> Tek uygulamalı bilgi noktası, bir kullanıcı oturum aken bilgi noktası uygulamasını başlatan bir Başlat menüsü kullanmaz ve Başlangıç düzenine sahip olmak zorunda değildir.

> [!NOTE]  
> Çok uygulamalı bilgi noktası ayarlamak için [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) kullanıyorsanız, isteğe bağlı olarak bir Başlangıç düzeni kullanabilirsiniz. Daha fazla bilgi için bkz. MDM için Yer Tutucu Başlangıç düzen dosyası [(Intune ve diğerleri)](#start-layout-file-for-mdm-intune-and-others).

Başlangıç düzeni için aşağıdaki **StartLayout bölümünü** bilgi noktası sağlama XML dosyasına ekleyin:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM için Yer Tutucu Başlangıç düzen dosyası (Intune ve diğerleri)

Aşağıdaki örneği bir XML dosyası olarak kaydedin. Çoklu uygulama bilgi noktası yapılandırmanız için bu dosyayı Microsoft Intune (veya bilgi noktası profili sağlayan başka bir MDM hizmeti) kullanabilirsiniz.

> [!NOTE]
> MDM hizmetinize bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanmak zorundaysanız, sağlama paketi için Başlangıç [düzeni yönergelerini kullanın.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package

1. Yapılandırma [Windows'i açın.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Gelişmiş **sağlama'yi** seçin, projeniz için bir ad girin ve İleri'yi **seçin.**
1. Öğesini **Windows 10 Holographic** ve ardından Sonraki'yi **seçin.**
1. **Son**'u seçin. Paketinizin çalışma alanı açılır.
1. Çalışma **zamanı ayarları**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings öğesini seçin.**
1. Orta bölmede **Gözat'ı seçerek** oluşturduğunuz bilgi noktası yapılandırması XML dosyasını bulun ve seçin.

   ![Yapılandırma Tasarımcısı'nda MultiAppAssignedAccessSettings Windows ekran görüntüsü](./images/multiappassignedaccesssettings.png)

1. **İsteğe bağlı**. (Cihazın ilk kurulumu sonrasında sağlama paketini uygulamak ve bilgi noktası cihazında zaten kullanılabilir bir yönetici kullanıcı varsa bu adımı atlayabilirsiniz.) Çalışma **zamanı ayarları** Hesaplar &gt;  &gt; **Kullanıcılar'ı** seçin ve ardından bir kullanıcı hesabı oluşturun. Bir kullanıcı adı ve parola girin ve ardından **UserGroup**  >  **Yöneticileri'ne tıklayın.**  
  
     Bu hesabı kullanarak sağlama durumunu ve günlüklerini görüntüleyebilirsiniz.  
1. **İsteğe bağlı**. (Bilgi noktası cihazında zaten yönetici olmayan bir hesabınız varsa bu adımı atlayabilirsiniz.) Çalışma **zamanı ayarları** Hesaplar &gt;  &gt; **Kullanıcılar'ı** seçin ve ardından yerel bir kullanıcı hesabı oluşturun. Kullanıcı adının yapılandırma XML'sinde belirttiğiniz hesapla aynı olduğundan emin olun. UserGroup **Standart**  >  **Kullanıcılar'ı seçin.**
1. Dosya **Kaydet'i**  >  **seçin.**
1. Sağlama **paketini**  >  **Dışarı Aktar'ı** ve ardından Sahip IT **Yöneticisi'ni**  >  **seçin.** Bu, bu sağlama paketinin öncelini, diğer kaynaklardan bu cihaza uygulanan sağlama paketlerinden daha yüksek ayarlar.
1. **İleri**’yi seçin.
1. Sağlama **paketi güvenliği sayfasında** bir güvenlik seçeneği belirleyin.
   > [!IMPORTANT]  
   > Paket imzalamayı **etkinleştir'i** kullanırsanız, paketi imzalamak için kullanmak üzere geçerli bir sertifika da seçmeniz gerekir. Bunu yapmak için **Gözat'ı** seçin ve paketi imzalamak için kullanmak istediğiniz sertifikayı seçin.
   
   > [!CAUTION]  
   > Paket şifrelemeyi **etkinleştir'i seçme.** Bu HoloLens, bu ayar sağlamanın başarısız olmasına neden olur.
1. **İleri**’yi seçin.
1. Hazırlama paketinin yerleşik olarak gitmek istediğiniz çıkış konumunu belirtin. Varsayılan olarak, Windows Tasarımcısı proje klasörünü çıkış konumu olarak kullanır. Çıkış konumunu değiştirmek için Gözat'ı **seçin.** Bitirdikten sonra, Sonraki'yi **seçin.**
1. Paketi **derlemeye** başlamak için Derleme'yi seçin. Sağlama paketinin derlemesi uzun zaman almaz. Derleme sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Sağlama paketi, &ndash; 3. Adım Sağlama paketini HoloLens

"Sağlama HoloLens kullanarak yapılandırma" makalesi, sağlama paketini aşağıdaki koşullarda uygulamak için ayrıntılı yönergeler sağlar:

- Başlangıçta kurulum sırasında [bir sağlama paketini HoloLens uygulayabilirsiniz.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Ayrıca [kurulumdan sonra bir sağlama paketini HoloLens uygulayabilirsiniz.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Tek Windows Cihaz Portalı bilgi noktası ayarlamak için Windows Cihaz Portalı'i kullanma

Bilgi noktası modunu Windows Cihaz Portalı ayarlamak için aşağıdaki adımları izleyin.

1. [HoloLens'i kullanmak için Windows Cihaz Portalı.](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Bu Cihaz Portalı bilgisayarınızdan bağlanabilirsiniz HoloLens sunucunuzda bir web sunucusudur.

    > [!CAUTION]
    > Bu HoloLens için Cihaz Portalı cihazda Geliştirici Modu'Cihaz Portalı etkinleştirmeniz gerekir. Uygulama yüklemesi olan bir Windows Holographic for Business Geliştirici Modu, uygulamaları yan yüklemeye olanak sağlar. Ancak bu ayar, bir kullanıcının uygulama tarafından sertifikalandırılmış uygulamaları yükleme riski Microsoft Store. Yöneticiler, İlke CSP'sinde **ApplicationManagement/AllowDeveloper Kilit** Açma ayarını kullanarak Geliştirici Modunu [etkinleştirme olanağını engelleyebilir.](/windows/client-management/mdm/policy-configuration-service-provider) [Geliştirici Modu hakkında daha fazla bilgi edinebilirsiniz.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Bir [bilgisayarda, Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) HoloLens USB kullanarak bilgisayara [bağlanın.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Aşağıdakilerden birini yapın:
   - İlk kez Windows Cihaz Portalı kullanıcı [adı ve parola oluşturun](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Daha önce ayar istediğiniz kullanıcı adını ve parolayı girin.

    > [!TIP]
    > Tarayıcıda bir sertifika hatası görüyorsanız şu sorun [giderme adımlarını izleyin.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. Bilgi noktası Windows Cihaz Portalı Bilgi Noktası **Modu'Windows Cihaz Portalı seçin.**

1. Bilgi **Noktası Modunu Etkinleştir'i** seçin, cihaz başlatıldığında çalıştırılacak bir uygulama seçin ve ardından Kaydet'i **seçin.**

    ![Bilgi Noktası Modu](images/kiosk.png)
1. Yeniden HoloLens. Uygulama sayfanız hala açık Cihaz Portalı sayfanın üst kısmından **Yeniden** Başlat'ı seçin.

> [!NOTE]
> Bilgi Noktası Modu, tek bir gerekli sorgu dizesi parametresi ("kioskModeEnabled&quot; değeri &quot;true&quot; veya &quot;false") ve isteğe bağlı bir parametre ("startupApp" ve paket adı değerine sahip startupApp") ile /api/holographic/kioskmode/settings'a POST göndererek Cihaz Portalı'ın REST API'sı aracılığıyla ayarlanabilir. Uygulamanın yalnızca Cihaz Portalı amaçlı olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmemiş olması gerektiğini unutmayın. Bu REST API gelecek güncelleştirmelerde/yayınlarda değişebilir.

## <a name="more-information"></a>Daha fazla bilgi

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sağlama paketi kullanarak bilgi noktası yapılandırmayı izleyin.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Genel Atanan Erişim – Bilgi Noktası Modu
- Bilgi noktası modunu sistem düzeyinde geçerli olan yeni Bilgi Noktası yöntemi etkinleştirerek Bilgi Noktası için Azaltılmış Kimlik Yönetimi.

Bu yeni özellik, BIR IT Yöneticisinin sistem düzeyinde geçerli olan, sistem üzerinde herhangi bir kimliğe benzeşimleri olan ve cihazda oturum açabilen herkes için geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırmasını sağlar. Bu yeni [HoloLens daha fazla ayrıntı için](hololens-global-assigned-access-kiosk.md) genel olarak atanan erişim bilgi noktası belgelerine bakın.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Bir uygulamanın çoklu uygulama bilgi noktası modunda otomatik olarak başlatılması 
- Otomatik uygulama başlatma deneyimi odaklıdır ve Bilgi Noktası modu deneyimleri için seçilen kullanıcı arabirimini ve uygulama seçimlerini daha da artırmaktadır.

Yalnızca birden çok uygulamalı bilgi noktası modu için geçerlidir ve atanan erişim yapılandırmasında aşağıdaki vurgulanmış öznitelik kullanılarak yalnızca 1 uygulama otomatik olarak başlatılacak şekilde atanabilir. 

Kullanıcı oturum başlattığında uygulama otomatik olarak başlatılır. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri
Bilgi noktası modu uygulama sırasında hatalarla karşılaşıldıktan sonra aşağıdaki davranış görüntülenir:

- Holographic Windows den önce sürüm 20H2 - HoloLens, sanal Başlat menüsü.
- Windows Holographic, sürüm 20H2 : Bir cihazda hem genel erişim hem de AAD grup üyesi tarafından atanan erişimin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliği belirlenmezse kullanıcı "başlat menüsünde hiçbir şey gösterilmez" ifadesini görebilir.

![Bilgi noktası modu artık başarısız olduğunda hangi modun göründüğünün resmi.](images/hololens-kiosk-failure-behavior.png )


- [Holographic Windows sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)başlayarak Bilgi Noktası modu, boş bir başlangıç menüsü göstermeden önce Genel Atanan Erişim'i okur. Bilgi noktası deneyimi, AAD grup bilgi noktası modu sırasında hata olması durumunda genel bilgi noktası yapılandırmasına (varsa) geri dönüş sağlar.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın

- Bilgi noktası modu hatalarda kullanılabilir uygulamaları ortadan kaldırarak daha güvenli Bilgi Noktası modu.
- 60 gün boyunca Azure AD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılacazın. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi takdirde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayaran ve bu değeri cihaz veya HoloLens atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri OMA-URI metin kutusuna ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilebilir
    1. Değer izin verilen en az / en yüksek değer arasında olabilir.
1. Cihazları HoloLens ve her iki yapılandırmanın da cihaza uygulandığını doğrulayın. 
1. İnternet kullanılabilir olduğunda Azure AD 1 kullanıcısı oturum açmasına izin ver. Kullanıcı oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. İlke değeri X gün sayısına izin HoloLens azure AD kullanıcı 1 artık çevrimdışı duruma geçer ve bilgi noktası modu için bunu kullanabilir. 
1. 4. ve 5. adımlar diğer Tüm Azure AD kullanıcılarının N. Önemli noktası, bilgi noktası yapılandırmasının hedeflene Azure AD grubuna üye olup olmadığını belirleyecek şekilde herhangi bir Azure AD kullanıcılarının internet kullanarak cihazda oturum açması gerektir. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilinceye kadar "bağlantısız" ortamlarda belirtilen hata davranışıyla karşılana kadar. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens için XML Bilgi Noktası Kod Örnekleri

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD grubunu hedef alan birden çok uygulama bilgi noktası modu. 
Bu bilgi noktası, Azure AD grubunda kullanıcılar için 3 uygulamayı içeren bir Bilgi Noktası etkinleştirilmiş olacak bir Bilgi Noktası dağıtır: Ayarlar, Remote Assist ve Geri Bildirim Merkezi. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan GUID'i kendi Azure AD Grubunuzla eşecek şekilde değiştirerek emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD hesabını hedef alan birden çok uygulama bilgi noktası modu.
Bu bilgi noktası tek bir kullanıcı için bir Bilgi Noktası dağıtır; 3 uygulamayı içeren bir Bilgi Noktası etkinleştirilir: Ayarlar, Remote Assist ve Geri Bildirim Merkezi. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan hesabı kendi Azure AD Hesabınızla eşecek şekilde değiştirerek emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

