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
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664015"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Bilgi HoloLens bilgi noktası olarak ayarlama

Bir HoloLens, cihazı bilgi noktası modunda çalıştırılacak şekilde yapılandırarak, bilgi noktası olarak da adlandırılan sabit amaçlı bir cihaz olarak işleve sahip olacak şekilde yapılandırabilirsiniz. Bilgi noktası modu, cihazda kullanılabilen uygulamaları (veya kullanıcıları) sınırlar. Bilgi noktası modu, bir HoloLens cihazı iş uygulamalarına ayırma veya HoloLens uygulama tanıtımda kullanma için kullanabileceğiniz kullanışlı bir özelliktir.

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

Bilgi noktası modunu kullanmak HoloLens 2 cihazı yapılandırabilirsiniz.

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
|Tek uygulamalı bilgi noktası | Azure Active Directory (Azure AD) veya yerel hesapta Microsoft Hesabı (MSA) |Yes |Hayır |
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
|Azure Active Directory (Azure AD) kullanarak dağıtma  | Gerekli değil            | Gerekli değil                   | Gerekli  |
|Otomatik olarak dağıtma      | Hayır            | Hayır                   | Yes  |
|Dağıtım hızı            | Hızlı       | Hızlı                 | Yavaş |
|Büyük ölçekte dağıtma | Önerilmez    | Önerilen        | Önerilen |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Tek Microsoft Intune veya çoklu uygulama bilgi noktası ayarlamak için Microsoft Intune veya diğer MDM'leri kullanma

Bilgi noktası modunu başka bir MDM Microsoft Intune kullanarak ayarlamak için aşağıdaki adımları izleyin.

1. [Cihazları kaydetmek için hazırlayın.](#mdmenroll)
1. [Bilgi noktası yapılandırma profili oluşturun.](#mdmprofile)
1. Bilgi noktası yapılandırma.
   - [Tek uygulamalı bilgi noktası için ayarları yapılandırma.](#mdmconfigsingle)
   - [Çoklu uygulama bilgi noktası için ayarları yapılandırma.](#mdmconfigmulti)
1. [Bilgi noktası yapılandırma profilini bir grubuna attayabilirsiniz.](#mdmassign)
1. Cihazları dağıtın.
   - [Tek uygulamalı bilgi noktası dağıtın.](#mdmsingledeploy)
   - [Çoklu uygulama bilgi noktası dağıtın.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, &ndash; 1. adım Cihazları kaydetmeye hazırlanma

MDM sisteminizi, kullanıcı ilk kez oturum HoloLens veya kullanıcıların cihazları el ile kaydetmelerini silen cihazları otomatik olarak kaydeden şekilde yapılandırabilirsiniz. Ayrıca cihazların Azure AD etki alanınıza katılmaları ve uygun gruplara atanmaları gerekir.

Cihazları kaydetme hakkında daha fazla bilgi için bkz. [MDM'HoloLens](hololens-enroll-mdm.md) kaydetme ve cihazları kaydetmek için [Intune Windows yöntemleri.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, 2. adım &ndash; Bilgi noktası yapılandırma profili oluşturma

1. Azure [portalını](https://portal.azure.com/) açın ve Intune yöneticisi açın.
1. Cihaz **Microsoft Intune**  >  **- Profiller Profil**  >  **oluştur'a tıklayın.**
1. Profil adı girin.
1. Platform **uygulaması**  >  **Windows 10 ve sonrası'na** tıklayın ve ardından Profil türü Cihaz   > **kısıtlamaları'na tıklayın.**
1. Bilgi **Noktası**  >  **Yapılandır'ı** ve ardından aşağıdakilerden birini seçin:
   - Tek uygulamalı bilgi noktası oluşturmak için Bilgi Noktası **Modu Tek uygulama bilgi**  >  **noktası'ı seçin.**
   - Çoklu uygulama bilgi noktası oluşturmak için Bilgi Noktası Modu Çoklu **uygulama**  >  **bilgi noktası'ı seçin.**
1. Bilgi noktası yapılandırmaya başlamak için Ekle'yi **seçin.**

Sonraki adımlarınız, istediğiniz bilgi noktası türüne bağlı olarak farklılık gösterir. Daha fazla bilgi için aşağıdaki seçeneklerden birini belirleyin:  

- [Tek uygulamalı bilgi noktası](#mdmconfigsingle)
- [Çoklu uygulama bilgi noktası](#mdmconfigmulti)

Bilgi noktası yapılandırma profili oluşturma hakkında daha fazla bilgi için bkz. Windows 10 ve [Windows Holographic for Business intune](/intune/configuration/kiosk-settings)kullanarak ayrılmış bilgi noktası olarak çalıştırılacak şekilde yapılandırma.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, 3. adım (tek uygulama) &ndash;  Tek uygulamalı bilgi noktası ayarlarını yapılandırma

Bu bölümde tek uygulamalı bilgi noktası için gereken ayarlar özetlenmiştir. Diğer ayrıntılar için aşağıdaki makalelere bakın:

- Intune'da bilgi noktası yapılandırma profilini yapılandırma hakkında bilgi için [bkz.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)Bilgi Noktası Modunu Microsoft Intune.
- Intune'da tek uygulama bilgi noktası için kullanılabilir ayarlar hakkında daha fazla bilgi için [bkz. Tek tam ekran uygulama bilgi noktası](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Diğer MDM hizmetleri için yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinize bilgi noktası ayarlamak için özel BIR XML yapılandırması kullanmak zorundaysanız, bilgi noktası yapılandırmasını tanımlayan [bir XML dosyası oluşturun.](#ppkioskconfig)

1. Kullanıcı **oturum açma türü** Yerel kullanıcı hesabı'yı seçin ve ardından bilgi noktası üzerinde oturum açabilirsiniz yerel (cihaz) hesabı veya Microsoft Hesabı  >  (MSA) kullanıcı adını girin.
   > [!NOTE]  
   > **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.
1. Uygulama **türü Mağaza**  >  **uygulaması'ı** seçin ve ardından listeden bir uygulama seçin.

Sonraki adımınız profili [bir](#mdmassign) gruba atamaktır.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, 3. adım (çoklu uygulama) &ndash; Çoklu uygulama bilgi noktası ayarlarını yapılandırma

Bu bölümde, çoklu uygulama bilgi noktası için gereken ayarlar özetlenmiştir. Daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- Intune'da bilgi noktası yapılandırma profilini yapılandırma hakkında bilgi için [bkz.](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)Bilgi Noktası Modunu Microsoft Intune.
- Intune'da çoklu uygulama bilgi noktası için kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. Çoklu uygulama [bilgi noktası](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Diğer MDM hizmetleri için yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinize bilgi noktası ayarlamak için özel BIR XML yapılandırması kullanıyorsanız, bilgi noktası yapılandırmasını tanımlayan [bir XML dosyası oluşturun.](#ppkioskconfig) BIR XML dosyası kullanıyorsanız Başlangıç düzenini dahil etmek [için emin olun.](#start-layout-for-hololens)  
- İsteğe bağlı olarak Intune veya diğer MDM hizmetleriyle özel bir Başlangıç düzeni kullanabilirsiniz. Daha fazla bilgi için [bkz. MDM için düzen dosyasını başlatma (Intune ve diğerleri)](#start-layout-file-for-mdm-intune-and-others).

1. **S modu cihazlarında Windows 10'ı seçin**  >  **Hayır.**  
>[!NOTE]  
> S modu, Windows Holographic for Business.

1. Kullanıcı **oturum açma türü** Azure AD kullanıcı veya  >  **grubu'HoloLens** kullanıcı oturum açma türü'HoloLens seçin ve ardından bir veya  >  daha fazla kullanıcı grubu veya hesap ekleyin.  

   Bilgi noktası deneyimini yalnızca Kullanıcı oturum açma türü'nde belirttiğiniz **gruplara veya hesaplara** ait kullanıcılar kullanabilir.

1. Aşağıdaki seçenekleri kullanarak bir veya daha fazla uygulama seçin:
   - Karşıya yüklenen bir iş hattı uygulaması eklemek için Mağaza uygulaması **ekle'yi ve** ardından istediğiniz uygulamayı seçin.
   - Bir uygulamayı AUMID'sini belirterek eklemek için **AUMID'ye** göre ekle'yi seçin ve uygulamanın AUMID'sini girin. [Kullanılabilir AUMID'ler listesine bakın](#aumids)

Sonraki adımınız profili [bir](#mdmassign) gruba atamaktır.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, &ndash; 4. adım Bilgi noktası yapılandırma profilini bir gruba atama

Bilgi **noktası yapılandırmasının** dağıtılacak yeri ayarlamak için bilgi noktası yapılandırma profilinin Atamalar sayfasını kullanın. En basit durumda, bilgi noktası yapılandırma profilini cihaz MDM'ye kayded HoloLens cihazı içeren bir gruba atarsanız.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5. adım (tek uygulama) &ndash; Tek uygulama bilgi noktası dağıtma

Bir MDM sistemi kullanıyorsanız, OOBE sırasında cihazı MDM'ye kaydedebilirsiniz. OOBE tamamlanmasının ardından cihazda oturum kolayca oturum açın.

OOBE sırasında şu adımları izleyin:

1. Bilgi noktası yapılandırma profilinde belirttiğiniz hesabı kullanarak oturum açın.
1. Cihazı kaydedin. Cihazın bilgi noktası yapılandırma profilinin atandığı gruba eklendiklerine emin olun.
1. Mağaza uygulamasının indirip yüklemesi ve ilkelerin uygulanması için OOBE'nin bitip bitmesini bekleyin. Ardından cihazı yeniden başlatın.

Cihazda bir sonraki oturum açmada bilgi noktası uygulamasının otomatik olarak başlaması gerekir.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız atama [durumunu kontrol edin.](/intune/configuration/device-profile-monitor)

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5. adım (çoklu uygulama) &ndash; Çok uygulamalı bilgi noktası dağıtma

Bir MDM sistemi kullanıyorsanız, cihazı Azure AD kiracınıza katarak OOBE sırasında cihazı MDM'ye kaydedebilirsiniz. Uygunsa, OOBE işlemi sırasında kullanılabilir olması için kullanıcılara kayıt bilgilerini sağlar.

> [!NOTE]  
> Bilgi noktası yapılandırma profilini kullanıcıları içeren bir gruba atadıysanız, bu kullanıcı hesaplarından birinin cihazda oturum açmanın ilk hesabı olduğundan emin olun.

OOBE sırasında şu adımları izleyin:

1. Kullanıcı oturum açma türü grubuna ait hesabı **kullanarak oturum** açın.
1. Cihazı kaydedin.
1. Bilgi noktası yapılandırma profilinin parçası olan tüm uygulamaların indirip yüklemelerini bekleyin. Ayrıca, ilkelerin uygulanmasını bekleyin.  
1. OOBE bittikten sonra, Microsoft Mağazası 'ndan veya dışarıdan yükleme yoluyla ek uygulamalar yükleyebilirsiniz. Cihazın otomatik olarak yüklenmesi için [gerekli uygulamalar](/mem/intune/apps/apps-deploy#assign-an-app) .
1. Yükleme bittikten sonra, cihazı yeniden başlatın.

Bir sonraki sefer, **Kullanıcı oturum açma türüne** ait bir hesabı kullanarak cihazda oturum açtığınızda, bilgi noktası uygulamasının otomatik olarak başlatılması gerekir.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız, [atama durumunu kontrol](/intune/configuration/device-profile-monitor)edin.

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için bir sağlama paketi kullanın

Sağlama paketini kullanarak bilgi noktası modunu ayarlamak için aşağıdaki adımları izleyin.

1. [Başlangıç düzeni](#start-layout-for-hololens)dahil olmak üzere [bilgi noktası YAPıLANDıRMASıNı tanımlayan bir XML dosyası oluşturun](#ppkioskconfig).
2. [XML dosyasını bir sağlama paketine ekleyin.](#ppconfigadd)
3. [HoloLens için sağlama paketini uygulayın.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Paketi sağlama, 1. adım &ndash; bilgi noktası YAPıLANDıRMASı XML dosyası oluşturma

aşağıdakiler dışında [Windows masaüstü için bir bilgi noktası yapılandırması XML dosyası oluşturmak üzere genel yönergeleri](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)izleyin:

- klasik Windows uygulamaları (Win32) eklemeyin. HoloLens bu uygulamaları desteklemez.
- HoloLens için [Başlangıç DÜZENI XML yer tutucusunu](#start-layout-for-hololens) kullanın.
- İsteğe bağlı: bilgi noktası yapılandırmasına konuk erişimi ekleme

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>İsteğe bağlı: bilgi noktası yapılandırmasına konuk erişimi ekleme

[XML dosyasının **configs** bölümünde](/windows/configuration/lock-down-windows-10-to-specific-apps#configs), konukların bilgi noktası kullanmasına izin vermek için **ziyaretçi** adlı özel bir grup yapılandırabilirsiniz. Bilgi noktası **ziyaretçi** özel grubunu destekleyecek şekilde yapılandırıldığında, oturum açma sayfasına bir "**Konuk**" seçeneği eklenir. **Konuk** hesabı bir parola gerektirmez ve hesap oturumu kapattığında hesapla ilişkili tüm veriler silinir.

**Konuk** hesabı 'nı etkinleştirmek için, bilgi noktası yapılandırma XML 'nize aşağıdaki kod parçacığını ekleyin:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Ziyaretçi otomatik oturum açmayı etkinleştir

derlemeler [Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonraki sürümler:
- AAD ve ADD olmayan yapılandırmaların her ikisi de, bilgi noktası modları için otomatik oturum açma özelliği etkinleştirilmiş ziyaretçi hesaplarını destekler.

##### <a name="non-aad-configuration"></a>AAD olmayan yapılandırma

1. Şu şekilde bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için çalışma zamanı ayarlarını/Atananı yapılandırır.
    1. İsteğe bağlı olarak, cihazı daha sonra yönetilebilmesi için MDM 'de (çalışma zamanı ayarları/çalışma alanı/kayıtlar) kaydeder.
    1. Yerel hesap oluşturma
2. [Sağlama paketini uygulayın](hololens-provisioning.md).

##### <a name="aad-configuration"></a>AAD yapılandırması

Bilgi noktası modu için yapılandırılmış AAD 'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak bir ziyaretçi hesabında oturum açabilir. Ziyaretçi hesabında oturum açtıktan sonra, ziyaretçi başlangıç menüsünde açıkça oturum açana veya cihaz yeniden başlatılana kadar cihaz yeniden oturum açmayı istemez.

Ziyaretçi otomatik oturum açma, [özel OMA-URI ilkesi](/mem/intune/configuration/custom-settings-windows-10)aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon


| İlke |Description |Yapılandırmalar 
| --------------------------- | ------------- | -------------------- |
| MixedReality/Visitooyutologon | Bir ziyaretçinin bir bilgi noktasında otomatik olarak oturum açmasına olanak tanır. | 1 (Evet), 0 (Hayır, varsayılan.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens için yer tutucu başlangıç düzeni

Birden çok uygulama bilgi noktası yapılandırmak için bir [sağlama paketi](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) kullanıyorsanız, yordam başlangıç düzeni gerektirir. Başlangıç düzeni özelleştirmesi Windows Holographic for Business desteklenmiyor. Bu nedenle, bir yer tutucu başlangıç düzeni kullanmanız gerekir.

> [!NOTE]  
> tek uygulama bilgi noktası, bir kullanıcı oturum açtığında bilgi noktası uygulamasını başlattığı için bir Başlat menüsü kullanmaz ve bir başlangıç düzenine sahip olmak zorunda değildir.

> [!NOTE]  
> Birden çok uygulama bilgi noktası ayarlamak için [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) kullanıyorsanız, isteğe bağlı olarak bir başlangıç düzeni kullanabilirsiniz. Daha fazla bilgi için bkz. [MDM Için yer tutucu başlangıç düzeni dosyası (Intune ve diğerleri)](#start-layout-file-for-mdm-intune-and-others).

Başlangıç düzeni için, aşağıdaki **Startlayout** bölümünü bilgi noktası sağlama XML dosyasına ekleyin:

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM için yer tutucu başlangıç düzeni dosyası (Intune ve diğerleri)

Aşağıdaki örneği bir XML dosyası olarak kaydedin. bu dosyayı, Microsoft Intune (veya bilgi noktası profili sağlayan başka bir MDM hizmetinde) birden çok uygulama bilgi noktası yapılandırdığınızda kullanabilirsiniz.

> [!NOTE]
> MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanmanız gerekiyorsa, [bir sağlama paketi Için Başlangıç düzeni yönergelerini](#start-layout-for-hololens)kullanın.

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. paket, adım 2 &ndash; bir sağlama paketine bilgi noktası yapılandırma XML dosyasını ekleme

1. [Windows yapılandırma tasarımcısını](https://www.microsoft.com/store/apps/9nblggh4tx22)açın.
1. **Gelişmiş sağlama**' yı seçin, projeniz için bir ad girin ve ardından **İleri**' yi seçin.
1. **Windows 10 Holographic**' yi seçin ve ardından **ileri**' yi seçin.
1. **Son**'u seçin. Paketinizin çalışma alanı açılır.
1. **Çalışma zamanı ayarları**  >  **Atananı**  >  **multiappassignedaccesssettings**' i seçin.
1. Orta bölmede, oluşturduğunuz bilgi noktası yapılandırması XML dosyasını bulmak ve seçmek için **Araştır** ' ı seçin.

   ![Windows yapılandırma tasarımcısında multiappassignedaccesssettings alanının ekran görüntüsü](./images/multiappassignedaccesssettings.png)

1. **Isteğe bağlı**. (Sağlama paketini cihazın ilk kurulumundan sonra uygulamak isterseniz ve bilgi noktası cihazında zaten bir yönetici kullanıcı varsa, bu adımı atlayın.) **Çalışma zamanı ayarları** &gt; **hesaplar** &gt; **Kullanıcılar**' ı seçin ve ardından bir kullanıcı hesabı oluşturun. Bir Kullanıcı adı ve parola girip **UserGroup**  >  **Administrators**' ı seçin.  
  
     Bu hesabı kullanarak, sağlama durumunu ve günlükleri görüntüleyebilirsiniz.  
1. **Isteğe bağlı**. (Bilgi noktası cihazında yönetici olmayan bir hesabınız zaten varsa, bu adımı atlayın.) **Çalışma zamanı ayarları** &gt; **hesaplar** &gt; **Kullanıcılar**' ı seçin ve ardından bir yerel kullanıcı hesabı oluşturun. Yapılandırma XML dosyasında belirttiğiniz hesapla Kullanıcı adının aynı olduğundan emin olun. **UserGroup**  >  **standart kullanıcıları**' nı seçin.
1. **Dosya**  >  **Kaydet**' i seçin.
1.   >  **Sağlama paketini** dışarı aktar ' ı seçin ve ardından **sahip**  >  **BT Yöneticisi**' ni seçin. Bu, bu sağlama paketinin bu cihaza diğer kaynaklardan uygulanan sağlama paketlerinden daha yüksek önceliğini ayarlar.
1. **İleri**’yi seçin.
1. **Paket güvenliğini sağlama** sayfasında, bir güvenlik seçeneği belirleyin.
   > [!IMPORTANT]  
   > **Paket IMZALAMAYı etkinleştir**' i seçerseniz, paketi imzalamak için kullanılacak geçerli bir sertifika seçmeniz da gerekir. Bunu yapmak için, **Araştır** ' ı seçin ve paketi imzalamak için kullanmak istediğiniz sertifikayı seçin.
   
   > [!CAUTION]  
   > **Paket şifrelemeyi etkinleştir**' i seçmeyin. HoloLens cihazlarda, bu ayar sağlamanın başarısız olmasına neden olur.
1. **İleri**’yi seçin.
1. Sağlama paketinin oluşturulduğunda gitmesini istediğiniz çıkış konumunu belirtin. varsayılan olarak, Windows Configuration Designer, proje klasörünü çıkış konumu olarak kullanır. Çıkış konumunu değiştirmek istiyorsanız, **Araştır**' ı seçin. İşiniz bittiğinde **İleri**' yi seçin.
1. Paketi oluşturmaya başlamak için **Oluştur** ' u seçin. Sağlama paketinin derlemesi uzun sürmez. Yapı sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Paketi sağlama, adım 3 ' te &ndash; sağlama paketini uygulama HoloLens

"sağlama paketi kullanarak HoloLens yapılandırma" makalesi, aşağıdaki koşullarda sağlama paketini uygulamak için ayrıntılı yönergeler sağlar:

- başlangıçta, [kurulum sırasında HoloLens bir sağlama paketi uygulayabilirsiniz](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- ayrıca, [kurulumdan sonra HoloLens için bir sağlama paketi uygulayabilirsiniz](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>tek uygulama bilgi noktası ayarlamak için Windows cihaz portalını kullanma

Windows cihaz portalını kullanarak bilgi noktası modunu ayarlamak için aşağıdaki adımları izleyin.

1. [HoloLens cihazı Windows cihaz portalını kullanacak şekilde ayarlayın](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). cihaz portalı, HoloLens bilgisayarınızdaki bir web tarayıcısından bağlantı kurmak için kullanabileceğiniz bir web sunucusudur.

    > [!CAUTION]
    > cihaz portalını kullanmak için HoloLens ayarlarken, cihazda geliştirici modunu etkinleştirmeniz gerekir. Windows Holographic for Business bir cihazda geliştirici modu, uygulamaları dışarıdan yükleyebilmenizi sağlar. Ancak, bu ayar, bir kullanıcının Microsoft Store tarafından sertifikasız uygulamaları yükleyebir risk oluşturur. Yöneticiler, [Ilke CSP](/windows/client-management/mdm/policy-configuration-service-provider)'Deki **ApplicationManagement/allowdeveloper unlock** ayarını kullanarak Geliştirici modunu etkinleştirebilme özelliğini engelleyebilir. [Geliştirici modu hakkında daha fazla bilgi edinin.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. bir bilgisayarda [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) veya [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)kullanarak HoloLens bağlanın.

1. Aşağıdakilerden birini yapın:
   - Windows cihaz portalına ilk kez bağlanıyorsanız, [bir kullanıcı adı ve parola oluşturun](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Daha önce ayarladığınız Kullanıcı adını ve parolayı girin.

    > [!TIP]
    > Tarayıcıda bir sertifika hatası görürseniz, [Bu sorun giderme adımlarını](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)izleyin.

1. Windows cihaz portalında **bilgi noktası modu**' nu seçin.

1. **Bilgi noktası modunu etkinleştir**' i seçin, cihaz başlatıldığında çalıştırılacak bir uygulama seçin ve ardından **Kaydet**' i seçin.

    ![Bilgi noktası modu](images/kiosk.png)
1. HoloLens yeniden başlatın. Hala cihaz portalı sayfanız açıksa sayfanın en üstünde **Yeniden Başlat** ' ı seçebilirsiniz.

> [!NOTE]
> Bilgi noktası modu, bir gerekli sorgu dizesi parametresi ("true&quot; veya &quot;false&quot; değeri olan &quot;Kıoskmodeenabled") ve bir isteğe bağlı parametre ("startupApp" bir paket adı ile) ile/api/holographic/kioskmode/Settings ile bir POST işlemi yaparak Device Portal 'ın REST API aracılığıyla ayarlanabilir. Lütfen cihaz portalının yalnızca geliştiricilere yönelik olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmeyeceğini aklınızda bulundurun. REST API gelecek güncelleştirmelerde/sürümlerde değişebilir.

## <a name="more-information"></a>Daha fazla bilgi

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sağlama paketini kullanarak bir bilgi noktası yapılandırmayı izleyin.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Genel atanan erişim – bilgi noktası modu
- Bilgi noktası için, sistem düzeyinde bilgi noktası modu uygulayan yeni bilgi noktası yöntemi etkinleştirilerek kimlik yönetimi azaltıldı.

bu yeni özellik, bir bt yöneticisinin sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için bir HoloLens 2 cihazı yapılandırmasına izin verir, sistemde hiçbir kimlikle benzeşim yoktur ve cihazda oturum açan herkese uygulanır. bu yeni özellik hakkında daha fazla bilgi için bkz. [genel atanan erişim bilgi noktası belgeleri HoloLens](hololens-global-assigned-access-kiosk.md) .

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Birden çok uygulama bilgi noktası modunda bir uygulamayı otomatik olarak başlatma 
- Otomatik uygulama başlatma ile odaklanmış deneyim, bilgi noktası modu deneyimleri için seçilen kullanıcı arabirimi ve uygulama seçimlerini daha da artırır.

Yalnızca birden çok uygulama bilgi noktası modu için geçerlidir ve atanan erişim yapılandırmasında aşağıda vurgulanan öznitelik kullanılarak otomatik başlatılacak şekilde yalnızca 1 uygulama belirlenebilir. 

Uygulama, Kullanıcı oturum açtığında otomatik olarak başlatılır. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri
Bilgi noktası modunu uygularken hatalarla karşılaşmadan aşağıdaki davranış görünür:

- Windows Holographic ' den önce, 20h2 sürümü HoloLens, Başlat menüsü tüm uygulamaları gösterir.
- Windows Holographic, sürüm 20H2-bir cihazda hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişim birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "başlangıç bölümünde gösterilmez" menüsünü görür.

![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )


- [Windows Holographic sürümünden itibaren, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1), bilgi noktası modu boş bir başlangıç menüsünü göstermeden önce genel atanan erişimi arar. Bilgi noktası deneyimi, AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bir bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma

- Bilgi noktası modu hatalarında kullanılabilir uygulamaları ortadan kaldırarak daha güvenli bilgi noktası modu.
- 60 güne kadar Azure AD grupları ile birlikte kullanılacak çevrimdışı kiosks 'leri etkinleştirdi.

Bu ilke, kaç gün boyunca Azure AD grup üyeliği önbelleğinin oturum açmış kullanıcı için Azure AD gruplarını hedefleyen atanan erişim yapılandırmalarında kullanılmasına izin verileceğini denetler. Bu ilke değeri 0 ' dan büyük bir değere ayarlandıktan sonra, önbellek kullanılır.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az-0 gün  
Maksimum 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedefleyen bilgi noktası için bir cihaz yapılandırma profili oluşturun ve HoloLens cihazlara atayın. 
1. bu ilke değerini istenen gün sayısına (> 0) ayarlayan ve HoloLens cihazlara atayan özel bir OMA urı tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri, OMA-URI metin kutusunda./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilmelidir
    1. Değer, izin verilen Min/Max arasında olabilir.
1. HoloLens cihazları kaydedin ve her iki yapılandırmanın cihaza uygulandığını doğrulayın. 
1. Internet 'in kullanılabildiği Azure AD User 1 oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. artık Azure AD kullanıcı 1, HoloLens çevrimdışına alabilir ve ilke değeri X gün sayısı için izin verdiği sürece bilgi noktası modu için kullanabilir. 
1. 4 ve 5. adım, diğer tüm Azure AD kullanıcıları için yinelenebilir. burada anahtar noktası, herhangi bir Azure AD kullanıcısının Internet 'i kullanarak cihaza oturum açması gerekir. bu sayede, bilgi noktası yapılandırmasının hedeflediği Azure AD grubuna üye olduklarını belirleyebiliriz. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilene kadar "bağlantısı kesik" ortamlarda bahsedilen hata davranışı ile karşılaşırsınız. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens için XML bilgi noktası kodu örnekleri

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Bir Azure AD grubunu hedefleyen birden çok uygulama bilgi noktası modu. 
bu bilgi noktası, Azure AD grubundaki kullanıcılar için bir bilgi noktası dağıttığında, 3 uygulamayı içeren bir bilgi noktası (Ayarlar, uzaktan yardım ve geri bildirim Hub 'ı) içerir. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan GUID 'yi kendi Azure AD grubuyla eşleşecek şekilde değiştirdiğinizden emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD hesabını hedefleyen birden çok uygulama bilgi noktası modu.
bu bilgi noktası tek bir kullanıcı için bir bilgi noktası dağıttığında, 3 uygulamayı içeren bir bilgi noktası etkin olur: Ayarlar, uzaktan yardım ve geri bildirim Hub 'ı. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan hesabı kendi Azure AD hesabıyla eşleşecek şekilde değiştirdiğinizden emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

