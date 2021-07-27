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
ms.openlocfilehash: 25227184ec33b134215dbd1f42f7b920b26dc29c
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659599"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Bilgi HoloLens bilgi noktası olarak ayarlama

Bir HoloLens, cihazı bilgi noktası modunda çalıştırılacak şekilde yapılandırarak, bilgi noktası olarak da adlandırılan sabit amaçlı bir cihaz olarak işleve sahip olacak şekilde yapılandırabilirsiniz. Bilgi noktası modu, cihazda kullanılabilen uygulamaları (veya kullanıcıları) sınırlar. Bilgi noktası modu, bir HoloLens cihazı iş uygulamalarına ayırma veya HoloLens uygulama tanıtımda kullanma için kullanabileceğiniz kullanışlı bir özelliktir.

Bu makalede, bilgi noktası yapılandırmasının belirli cihazlara özgü yönleri hakkında HoloLens sağlar. Farklı türlerde bilgi Windows bilgi noktası ve nasıl yapılandırılacakları hakkında genel bilgi için bkz. Masaüstü sürümlerinde [bilgi Windows yapılandırma.](/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Bilgi noktası modu, kullanıcı cihazda oturum açınca hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. Bir "izin verilen" uygulamanın izin verilmiyor başka bir uygulama açmasına engel olmaz. Uygulamaların veya işlemlerin açılmasını engellemek için uygun ilkeleri Windows Defender Uygulama [Denetimi (WDAC) CSP'lerini](/windows/client-management/mdm/applicationcontrol-csp) kullanın.
>
> Kullanıcılara 2 Microsoft hizmetleri gelişmiş güvenlik düzeyi verme hakkında daha fazla bilgi HoloLens, Durum ayrımı ve yalıtımı [- Defender korumaları hakkında](security-state-separation-isolation.md#defender-protections)daha fazla bilgi okuyun. Veya wdac ve Windows PowerShell 2 cihaz üzerinde uygulamalara izin vermek veya HoloLens engellemek [için WDAC](/mem/intune/configuration/custom-profile-hololens)ve Microsoft Intune.

Bilgi noktası modunu tek uygulamalı veya çoklu uygulama yapılandırmasında kullanabilir ve bilgi noktası yapılandırmasını ayarlamak ve dağıtmak için üç işlemden birini kullanabilirsiniz.

> [!IMPORTANT]  
> Çoklu uygulama yapılandırmasını silmek, atanan erişim özelliğinin oluşturduğu kullanıcı kilitleme profillerini kaldırır. Ancak, tüm ilke değişikliklerini geri döndürmez. Bu ilkeleri geri dönmek için cihazı fabrika ayarlarına sıfırlamanız gerekir.

## <a name="plan-the-kiosk-deployment"></a>Bilgi noktası dağıtımını planlama

Bilgi Noktasınızı planlarken aşağıdaki soruları yanıtlayabileceksiniz. Bu sayfayı okurken göz önünde bulundurulması gereken bazı kararlar ve bu sorularla ilgili dikkat edilmesi gereken bazı noktalar.
1. **Who Bilgi Noktası'nızı ve [hangi hesap türünü](hololens-identity.md) kullanacak?** Bu, büyük olasılıkla önceden aldığı ve Bilgi Noktasınız için ayar yapmamanız gereken bir karardır, ancak Bilgi Noktası'nın daha sonra nasıl atanması gerektiğini etkiler.
1. **Kullanıcı/grup başına farklı Bilgi Noktası veya bazıları için etkinleştirilmemiş bilgi noktası mı gerekiyor?** Bu şekilde bilgi noktası oluşturmak için XML ile bilgi noktası oluşturmanız gerekir. 
1. **Bilgi Noktası'nıza kaç uygulama gelecek?** 1'den fazla uygulama varsa çoklu uygulama bilgi noktası gerekir. 
1. **Bilgi Noktası'nıza hangi uygulama gelecek?** Lütfen aşağıdaki AUMID listemizi kullanarak kendi uygulamanıza In-Box uygulamalarınızı ekleyin.
1. **Bilgi Noktası'nızı nasıl dağıtmayı planlısınız?** Cihazı MDM'ye kaydedıyorsanız Bilgi Noktası'nızı dağıtmak için MDM'yi kullanmanızı öneririz. MDM kullanıyorsanız Sağlama Paketi ile dağıtım kullanılabilir.  

### <a name="kiosk-mode-requirements"></a>Bilgi noktası modu gereksinimleri

Bilgi noktası modunu kullanmak HoloLens 2 cihazı yapılandırabilirsiniz.

> [!IMPORTANT]
> Bilgi noktası modu yalnızca cihazın cihaza bağlı Windows Holographic for Business. 2 HoloLens tüm cihazlar Windows Holographic for Business ve başka sürüm yoktur. Her HoloLens 2 cihaz, Bilgi Noktası modunu kutudan çıkararak çalıştırabilirsiniz.
>
> HoloLens (1. nesil) cihazların hem işletim sistemi derlemesi hem de işletim sistemi sürümü açısından yükseltilleri gerekir. Aşağıda, bir HoloLens (1. nesil) sürümünü Windows Holographic for Business [edinebilirsiniz.](hololens1-upgrade-enterprise.md) Bir HoloLens (1. nesil) cihazı bilgi noktası modunu kullanmak üzere güncelleştirmek için öncelikle cihazın Windows 10, sürüm 1803 veya sonraki bir sürümde çalıştırıla olduğundan emin olun. HoloLens (1. nesil) cihazınızı varsayılan derlemeye kurtarmak için Windows Cihaz Kurtarma Aracı'nı kullandıysanız veya en son güncelleştirmeleri yüklemişsanız, cihazınız yapılandırmaya hazırdır.

> [!IMPORTANT]  
> Bilgi noktası modunda çalıştırılacak cihazların korunmasına yardımcı olmak için USB bağlantısı gibi özellikleri kapatan cihaz yönetimi ilkeleri eklemeyi göz önünde bulundurabilirsiniz. Ayrıca, otomatik güncelleştirmelerin iş saatleri içinde oluşmay olduğundan emin olmak için güncelleştirme halkası ayarlarınızı kontrol edin.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Tek uygulamalı bilgi noktası veya çoklu uygulama bilgi noktası arasında karar verme

Tek uygulamalı bilgi noktası, kullanıcı cihazda oturum açınca belirtilen uygulamayı başlatır. Başlat menüsü olduğu gibi devre dışı Cortana. Bir HoloLens 2 cihazı Başlangıç hareketini [yanıtlamaz.](hololens2-basic-usage.md#start-gesture) Bir HoloLens (1. nesil) cihaz bloom hareketini [yanıtlamaz.](hololens1-basic-usage.md) Yalnızca bir uygulama çalıştırılaya sahip olduğundan, kullanıcı diğer uygulamaları ekamaz.

Çok uygulamalı bilgi noktası Başlat menüsü cihazda oturum açtırarak ilgili bilgileri görüntüler. Bilgi noktası yapılandırması, veri noktası yapılandırmasında hangi uygulamaların Başlat menüsü. Kullanıcılara yalnızca kullanmaları gereken şeyleri sunarak ve kullanmaları gerek olmayan şeyleri kaldırarak kolay anlaşılır bir deneyim sağlamak için çoklu uygulama bilgi noktası kullanabilirsiniz.

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

Bilgi noktası modunu yapılandırmak için mobil Cihaz Yönetimi (MDM) sistemi veya sağlama paketi kullanıyorsanız, uygulamaları belirtmek için AssignedAccess Yapılandırma Hizmet [Sağlayıcısı'nın (CSP)](/windows/client-management/mdm/assignedaccess-csp) kullanırsınız. CSP, uygulamaları tanımlamak için Uygulama Kullanıcı Modeli Kimliklerini [(AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) kullanır. Aşağıdaki tabloda, çok uygulamalı bilgi noktası içinde kullanabileceğiniz bazı in-box uygulamalarının AUMID'leri listelemektedir.

> [!IMPORTANT]
> Bilgi noktası modu, kullanıcı cihazda oturum açınca hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. Bir "izin verilen" uygulamanın izin verilmiyor başka bir uygulama açmasına engel olmaz. Bu davranışı kısıtlayamamız nedeniyle uygulamalar Edge, Dosya Gezgini ve Microsoft Store başlatabilirsiniz. Bilgi Noktası'dan başlatılan belirli uygulamalar varsa, uygun ilkeler oluşturmak Windows Defender Uygulama [Denetimi (WDAC) CSP'lerini](/windows/client-management/mdm/applicationcontrol-csp) kullanın. 
> 
> Buna ek olarak Karma Gerçeklik Giriş, bilgi noktası uygulaması olarak ayarlanmaz.

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
|Miracast<sup>4</sup> |&nbsp; |
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

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Kullanıcılar veya gruplar için bilgi noktası profilleri planlama

Xml dosyasını oluştururken veya Bilgi Noktası ayarlamak için Intune kullanıcı arabirimini kullanırken Bilgi Noktası'nın kullanıcı adını göz önünde bulundurabilirsiniz. Bilgi noktası yapılandırması tek bir hesapla veya Azure AD gruplarıyla sınırlı olabilir. 

Bilgi noktası genellikle bir kullanıcı veya kullanıcı grubu için etkinleştirilir. Ancak kendi XML Bilgi Noktası yazmayı planlıyorsanız, Bilgi Noktası'nın Kimlik'e bakılmaksızın cihaz düzeyinde uygulandığı Genel Atanan Erişimi göz önünde bulundurabilirsiniz. Bu size cazip olursa Genel [Atanan Erişim Bilgi Noktası hakkında daha fazla bilgi okuyun.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>BIR XML dosyası oluşturuyorsanız:
-   Çok sayıda Bilgi Noktası profili oluşturabilir ve her bir profili farklı kullanıcılara/gruplara atabilirsiniz. Azure AD Grubunuz için birçok uygulama içeren bir Bilgi Noktası ve tek bir uygulama içeren birden çok uygulama bilgi noktası olan bir Ziyaretçi gibi.
-   Bilgi noktası yapılandırmanız Profil Kimliği **olarak çağrılır ve** GUID'ye sahip olur.
-   Kullanıcı türünü belirterek ve DefaultProfile Id için aynı GUID'i kullanarak bu Profili **yapılandırmalar bölümünde atayabilirsiniz.**
- Özel bir OMA URI cihaz yapılandırma profili oluşturularak ve URI değeri kullanılarak HoloLens cihaz grubuna uygulanarak bir XML dosyası oluşturulabilir, ancak yine de MDM aracılığıyla cihaza uygulanabilir: ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Intune'da bilgi noktası oluşturuyorsanız.
-   Her cihaz yalnızca tek bir Bilgi Noktası profili alır, aksi takdirde bir çakışma oluşturabilir ve Bilgi Noktası yapılandırmaları almaz. 
    -   Bilgi noktası yapılandırma profiliyle ilgili cihaz kısıtlamaları gibi diğer profil ve ilke türleri bilgi noktası yapılandırma profiliyle çakışmaz.
-   Bilgi Noktası, Kullanıcı oturum açma türünün parçası olan tüm kullanıcılar için etkinleştirilir; bu bir kullanıcı veya Azure AD grubuyla ayarlanır. 
-   Bilgi noktası yapılandırması ayar ve Kullanıcı oturum açma türü **(Bilgi** Noktası'nda oturum açan kullanıcılar) ve Uygulamalar seçildikten sonra, Cihaz Yapılandırması yine de bir gruba atanmalı. Atananlar, Bilgi Noktası cihaz yapılandırmasını hangi cihazların alacaklarını belirler, ancak Bilgi Noktası etkinse veya etkinleştirilmediyse ile etkileşim kurmaz. 
    - Intune'da yapılandırma profilleri atamanın etkileri hakkında tam bilgi için bkz. Intune'da kullanıcı [ve cihaz profilleri Microsoft Intune.](/intune/configuration/device-profile-assign)

### <a name="select-a-deployment-method"></a>Dağıtım yöntemi seçme

Bilgi noktası yapılandırmalarını dağıtmak için aşağıdaki yöntemlerden birini kullanabilirsiniz:

- [Microsoft Intune veya diğer mobil cihaz yönetimi (MDM) hizmeti](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Sağlama paketi](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Cihaz Portalı](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Bu yöntem cihazda Geliştirici Modunun etkinleştirilmesi gerektirdiği için, bunu yalnızca tanıtımlar için kullanmanız önerilir.

Aşağıdaki tabloda, dağıtım yöntemlerinin her bir özelliği ve avantajları liste almaktadır.

| &nbsp; |Windows Cihaz Portalı kullanarak dağıtma |Sağlama paketi kullanarak dağıtma |MDM kullanarak dağıtma |
| --------------------------- | ------------- | -------------------- | ---- |
|Tek uygulamalı bilgi noktası dağıtma   | Yes           | Yes                  | Yes  |
|Çok uygulamalı bilgi noktası dağıtma    | Hayır            | Yes                  | Yes  |
|Yalnızca yerel cihazlara dağıtma | Yes           | Yes                  | Hayır   |
|Geliştirici Modunu kullanarak dağıtma |Gerekli       | Gerekli değil            | Gerekli değil   |
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
1. Bilgi noktası yapılandırma profilinin parçası olan tüm uygulamaların indirilip yüklenmesini bekleyin. Ayrıca, ilkelerin uygulanmasını bekleyin.  
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


| İlke |Açıklama |Yapılandırmalar 
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
    > cihaz portalını kullanmak için HoloLens ayarlarken, cihazda geliştirici modunu etkinleştirmeniz gerekir. Windows Holographic for Business bir cihazda geliştirici modu, uygulamaları dışarıdan yükleyebilmenizi sağlar. Ancak, bu ayar, bir kullanıcının Microsoft Store tarafından sertifikasız uygulamaları yükleyebir risk oluşturur. Yöneticiler, [Ilke CSP](/windows/client-management/mdm/policy-configuration-service-provider)'Deki **ApplicationManagement/allowdeveloper unlock** ayarını kullanarak Geliştirici modunu etkinleştirebilme özelliğini engelleyebilir. [Geliştirici Modu hakkında daha fazla bilgi edinebilirsiniz.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Bir bilgisayarda, [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) HoloLens USB kullanarak bilgisayara [bağlanın.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Aşağıdakilerden birini yapın:
   - İlk kez Windows Cihaz Portalı kullanıcı [adı ve parola oluşturun](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Daha önce ayar istediğiniz kullanıcı adını ve parolayı girin.

    > [!TIP]
    > Tarayıcıda bir sertifika hatası görüyorsanız şu sorun [giderme adımlarını izleyin.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. Bilgi noktası Windows Cihaz Portalı Bilgi Noktası **Modu'Windows Cihaz Portalı seçin.**

1. Bilgi **Noktası Modunu Etkinleştir'i** seçin, cihaz başlatıldığında çalıştırılacak bir uygulama seçin ve kaydet'i **seçin.**

    ![Bilgi Noktası Modu](images/kiosk.png)
1. Yeniden HoloLens. Uygulama sayfanız açık Cihaz Portalı sayfanın üst kısmından **Yeniden** Başlat'ı seçin.

> [!NOTE]
> Bilgi Noktası Modu, tek bir gerekli sorgu dizesi parametresi ("kioskModeEnabled" ve "true" veya "false" değeriyle) ve isteğe bağlı bir parametre ("paket adı değerine sahip startupApp" ) ile /api/holographic/kioskmode/settings'a POST göndererek Cihaz Portalı'nin REST API'leri aracılığıyla ayarlanabilir. Uygulamanın yalnızca Cihaz Portalı amaçlı olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmemiş olması gerektiğini unutmayın. Bu REST API gelecek güncelleştirmelerde/yayınlarda değişebilir.

## <a name="more-information"></a>Daha fazla bilgi

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sağlama paketi kullanarak bilgi noktası yapılandırmayı izleyin.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Genel Atanan Erişim – Bilgi Noktası Modu
- Bilgi noktası modunu sistem düzeyinde uygulanan yeni Bilgi Noktası yöntemi etkinleştirerek Bilgi Noktası için azaltılmış Kimlik yönetimi.

Bu yeni özellik, bir IT Yöneticisinin sistem düzeyinde geçerli olan, sistem üzerinde herhangi bir kimliğe benzeşimleri olan ve cihazda oturum açabilen herkes için geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırmasını sağlar. Bu yeni [HoloLens genel atanan erişim bilgi noktası](hololens-global-assigned-access-kiosk.md) belgelerine bakın.

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
Bilgi noktası modunda hatalarla karşılaşıldıktan sonra aşağıdaki davranış görüntülenir:

- Holographic Windows den önce sürüm 20H2 - HoloLens, sanal Başlat menüsü.
- Windows Holographic, sürüm 20H2 : Bir cihazda hem genel erişim hem de AAD grup üyesi tarafından atanan erişimin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğinin başarısız olduğu belirlenirse kullanıcı "başlat menüsünde hiçbir şey gösterilmez" menüsünü görebilir.

![Bilgi Noktası modunun artık başarısız olduğunda ne gibi göründüğünün resmi.](images/hololens-kiosk-failure-behavior.png )


- [Holographic Windows sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)başlayarak Bilgi Noktası modu, boş bir başlangıç menüsü göstermeden önce Genel Atanan Erişim'i gösterir. Bilgi noktası deneyimi, AAD grup bilgi noktası modu sırasında hata olması durumunda genel bilgi noktası yapılandırmasına (varsa) geri dönüş sağlar.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın

- Bilgi noktası modu hatalarda kullanılabilir uygulamaları ortadan kaldırarak daha güvenli Bilgi Noktası modu.
- 60 gün boyunca Azure AD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılabilir olduğunu kontrol eder. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi halde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayar alan ve bu değeri cihaz veya HoloLens atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri OMA-URI metin kutusuna ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilebilir
    1. Değer izin verilen en az / en yüksek değer arasında olabilir.
1. Cihazları HoloLens ve her iki yapılandırmanın da cihaza uygulandığını doğrulayın. 
1. İnternet kullanılabilir olduğunda Azure AD 1 kullanıcısı oturum açmasına izin ver. Kullanıcı oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. İlke değeri X gün sayısına izin HoloLens azure AD kullanıcı 1 artık çevrimdışı duruma geçer ve bilgi noktası modu için bunu kullanabilir. 
1. 4. ve 5. adımlar diğer Azure AD kullanıcılarının N. Önemli noktası, bilgi noktası yapılandırmasını hedef alan Azure AD grubuna üye olup olmadığını belirleyecek en az bir kez İnternet kullanarak tüm Azure AD kullanıcılarının cihazda oturum açması gerektir. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilinceye kadar "bağlantısız" ortamlarda belirtilen hata davranışıyla karşılana kadar. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens için XML Bilgi Noktası Kod Örnekleri

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Azure AD grubunu hedef alan birden çok uygulama bilgi noktası modu. 
Bu bilgi noktası, Azure AD grubunda kullanıcılar için 3 uygulamayı içeren bir Bilgi Noktası etkinleştirilmiş olacak bir Bilgi Noktası dağıtır: Ayarlar, Remote Assist ve Geri Bildirim Merkezi. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan GUID'i kendi Azure AD Grubunuzla eşecek şekilde değiştirerek emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD hesabını hedef alan birden çok uygulama bilgi noktası modu.
Bu bilgi noktası, tek bir kullanıcı için bilgi noktası dağıtır. Bu bilgi noktası, Ayarlar, Remote Assist ve Geri Bildirim Merkezi olmak Geri Bildirim Merkezi. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan hesabı kendi Azure AD Hesabınızla eşecek şekilde değiştirerek emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

