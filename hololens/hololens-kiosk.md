---
title: HoloLens 'i bilgi noktası olarak ayarlama
description: HoloLens cihazlarındaki uygulamaları kilitlemek için bir bilgi noktası yapılandırması ayarlamayı ve kullanmayı öğrenin.
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
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379073"
---
# <a name="set-up-hololens-as-a-kiosk"></a>HoloLens 'i bilgi noktası olarak ayarlama

Cihaz bilgi noktası modunda çalışacak şekilde yapılandırarak bir HoloLens cihazını, *bilgi noktası* olarak da bilinen sabit amaçlı bir cihaz olarak çalışacak şekilde yapılandırabilirsiniz. Bilgi noktası modu, cihazdaki kullanılabilir uygulamaları (veya kullanıcıları) sınırlandırır. Bilgi noktası modu, HoloLens cihazını iş uygulamalarına ayırmak veya bir uygulama tanıtımında HoloLens cihazını kullanmak için kullanabileceğiniz kullanışlı bir özelliktir.

Bu makalede, HoloLens cihazlarına özel bilgi noktası yapılandırmasının yönleri hakkında bilgi sağlanır. Farklı Windows tabanlı bilgi türleri ve bunların nasıl yapılandırılacağı hakkında genel bilgiler için, bkz. [Windows masaüstü sürümlerinde bilgi noktaları ve dijital işaretleri yapılandırma](https://docs.microsoft.com/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Bilgi noktası modu, bir Kullanıcı cihazda oturum açtığında hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. "İzin verilen" bir uygulamanın, izin verilmeyen başka bir uygulamayı açmasını durdurmaz. Uygulamaların veya işlemlerin açılmasını engellemek için, uygun ilkeler oluşturmak üzere [Windows Defender uygulama denetimi (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) kullanın.
>
> Microsoft hizmetleri hakkında daha fazla bilgi edinmek için bkz. HoloLens 2 ' nin kullandığı gelişmiş bir güvenlik düzeyi sağlamak için [durum ayrımı ve yalıtım-Defender korumaları](security-state-separation-isolation.md#defender-protections)hakkında daha fazla bilgi edinin. Veya [Microsoft Intune Ile HoloLens 2 cihazlarda uygulamalara izin vermek veya bunları engellemek IÇIN WDac ve Windows PowerShell](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)'in nasıl kullanılacağını öğrenin.

Bilgi noktası modunu tek bir uygulamada veya çoklu uygulama yapılandırmasında kullanabilir ve bilgi noktası yapılandırmasını ayarlamak ve dağıtmak için üç işlemlerden birini kullanabilirsiniz.

> [!IMPORTANT]  
> Çoklu uygulama yapılandırmasının silinmesi, atanan erişim özelliğinin oluşturduğu Kullanıcı kilitleme profillerini kaldırır. Ancak, tüm ilke değişikliklerini döndürmez. Bu ilkeleri geri döndürmek için cihazı fabrika ayarlarına sıfırlamanız gerekir.

## <a name="plan-the-kiosk-deployment"></a>Bilgi noktası dağıtımını planlayın

Bilgi noktasında planlama yaparken aşağıdaki soruları yanıtlayabilmeniz gerekir. Bu sayfayı okurken ve bu sorulara bazı hususlar göz önünde bulundurmanız gereken bazı kararlar aşağıda verilmiştir.
1. **Bilgi bilgilerinizi kim kullanacak ve ne [tür bir hesap (ler)](hololens-identity.md) kullanacaksınız?** Bu, büyük olasılıkla daha önce yaptığınız bir karardır ve bilgi küteminin saına göre ayarlanmamalıdır, ancak bilgi noktası 'nın daha sonra nasıl atandığını etkileyecektir.
1. **Kullanıcı/Grup başına farklı kiosks veya bir bilgi noktası olmaması gerekir mi?** Bu durumda, XML aracılığıyla bilgi noktası oluşturmak isteyeceksiniz. 
1. **Bilgi noktasında kaç uygulama olacak?** 1 ' den fazla uygulamanız varsa, birden çok uygulama bilgi noktası gerekir. 
1. **Hangi uygulamalar bilgi noktasında olacak?** Lütfen kendinize ek olarak herhangi bir In-Box uygulaması eklemek için aşağıdaki AUMIDs listemizi kullanın.
1. **Bilgi yayınınızı nasıl dağıtmayı planlıyorsunuz?** Cihazı MDM 'ye kaydediyorsanız, bilgi noktası 'nı dağıtmak için MDM kullanmayı öneririz. MDM kullanmıyorsanız, sağlama paketiyle dağıtım kullanılabilir.  

### <a name="kiosk-mode-requirements"></a>Bilgi noktası modu gereksinimleri

Herhangi bir HoloLens 2 cihazını bilgi noktası modunu kullanacak şekilde yapılandırabilirsiniz.

> [!IMPORTANT]
> Bilgi noktası modu yalnızca cihazda Windows holographic for Business varsa kullanılabilir. Tüm HoloLens 2 cihazları Windows holographic for Business ile birlikte dağıtılır ve başka bir sürüm yoktur. Her HoloLens 2 aygıtı, bilgi noktası modunu kutudan çıkar.
>
> HoloLens (1. gen) cihazların hem işletim sistemi derlemesi hem de işletim sistemi sürümü açısından yükseltilmesi gerekir. HoloLens 'i (1. gen) [Windows holographic for Business](hololens1-upgrade-enterprise.md) sürümüne güncelleştirme hakkında daha fazla bilgi bulabilirsiniz. Bir HoloLens (1. gen) cihazını bilgi noktası modunu kullanacak şekilde güncelleştirmek için önce cihazın Windows 10, sürüm 1803 veya sonraki bir sürümü çalıştırıyor olduğundan emin olmanız gerekir. HoloLens (1. gen) cihazınızı varsayılan yapıya kurtarmak için Windows cihaz kurtarma aracı 'nı kullandıysanız veya en son güncelleştirmeleri yüklediyseniz, cihazınız yapılandırmaya hazır olur.

> [!IMPORTANT]  
> Bilgi noktası modunda çalışan cihazların korunmasına yardımcı olmak için, USB bağlantısı gibi özellikleri kapatan cihaz yönetimi ilkeleri eklemeyi göz önünde bulundurun. Ayrıca, iş saatlerinde otomatik güncelleştirmelerin gerçekleşmediğinden emin olmak için güncelleştirme halkası ayarlarınızı denetleyin.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Tek uygulama bilgi noktası veya birden çok uygulama bilgi noktası arasında karar verme

Tek uygulama bilgi noktası, Kullanıcı cihazda oturum açtığında belirtilen uygulamayı başlatır. Cortana gibi Başlat menüsü devre dışıdır. HoloLens 2 cihazı [Başlangıç](hololens2-basic-usage.md#start-gesture) hareketini yanıtlamaz. HoloLens (1. gen) cihaz [Bloom](hololens1-basic-usage.md) hareketini yanıtlamaz. Yalnızca bir uygulama çalıştırılabildiğinden, Kullanıcı diğer uygulamaları yerleştiremiyor.

Birden çok uygulama bilgi noktası, Kullanıcı cihazda oturum açtığında Başlat menüsünü görüntüler. Bilgi noktası yapılandırması, başlangıç menüsünde hangi uygulamaların kullanılabilir olduğunu belirler. Kullanıcılara yalnızca kullanması gereken şeyleri sunarak ve kullanması gerekmeyen şeyleri kaldırarak kullanıcılara kolay anlaşılır bir deneyim sağlamak için çok uygulama bilgi noktası kullanabilirsiniz.

Aşağıdaki tabloda, farklı bilgi noktası modlarında Özellik özellikleri listelenmektedir.

| &nbsp; |Başlat menüsü |Hızlı Eylemler menüsü |Kamera ve video |Miracast |Cortana |Yerleşik sesli komutlar |
| --- | --- | --- | --- | --- | --- | --- | 
|Tek uygulama bilgi noktası |Devre dışı |Devre dışı |Devre dışı |Devre dışı   |Devre dışı |Etkin<sup>1</sup> |
|Çoklu uygulama bilgi noktası |Etkin |Etkin<sup>2</sup> |Kullanılabilir<sup>2</sup> |Kullanılabilir<sup>2</sup> |Kullanılabilir<sup>2, 3</sup>  |Etkin<sup>1</sup> |

> devre dışı özelliklerle ilgili <sup>1</sup> sesli komut çalışmaz.  
> <sup>2</sup> bu özelliklerin nasıl yapılandırılacağı hakkında daha fazla bilgi için bkz. [bilgi noktası uygulamalarını seçme](#plan-kiosk-apps).  
> <sup>3</sup> Cortana devre dışı olsa bile yerleşik sesli komutlar etkinleştirilir.

Aşağıdaki tabloda, farklı bilgi noktası modlarının Kullanıcı desteği özellikleri listelenmektedir.

| &nbsp; |Desteklenen kullanıcı türleri | Otomatik oturum açma | Birden çok erişim düzeyi |
| --- | --- | --- | --- |
|Tek uygulama bilgi noktası |Azure Active Directory (Azure AD) veya yerel hesapta yönetilen hizmet hesabı (MSA) |Yes |Hayır |
|Çoklu uygulama bilgi noktası |Azure AD hesabı |Hayır |Yes |

Bu özellikleri kullanma örnekleri için aşağıdaki tabloya bakın.

|Tek uygulama bilgi noktası kullanarak şunları yapın: |İçin birden çok uygulama bilgi noktası kullanın: |
| --- | --- |
|Yeni çalışanlar için yalnızca Dynamics 365 kılavuzunu çalıştıran bir cihaz. |Bir dizi çalışan için hem kılavuzlar hem de uzaktan yardım çalıştıran bir cihaz. |
|Yalnızca özel bir uygulama çalıştıran bir cihaz. |Çoğu kullanıcı için bilgi noktası olarak işlev gören bir cihaz (yalnızca özel bir uygulama çalıştıran), ancak belirli bir Kullanıcı grubu için standart bir cihaz olarak işlevler. |

### <a name="plan-kiosk-apps"></a>Bilgi noktası uygulamalarını planlayın

Bilgi noktası uygulamalarını seçme hakkında genel bilgi için bkz. [atanan erişim için uygulama seçme yönergeleri (bilgi noktası modu)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).

Tek uygulama bilgi noktası yapılandırmak için Windows cihaz portalını kullanıyorsanız, kurulum işlemi sırasında uygulamayı seçersiniz.  

Bilgi noktası modunu yapılandırmak için bir mobil cihaz yönetimi (MDM) sistemi veya sağlama paketi kullanıyorsanız, uygulamaları belirtmek için atanan bir [yapılandırma hizmet sağlayıcısı (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanın. CSP, uygulamaları tanımlamak için [uygulama kullanıcı modeli kimliklerini (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) kullanır. Aşağıdaki tabloda, çok uygulamalı bilgi noktası içinde kullanabileceğiniz bazı in-box uygulamalarının AUMID'leri listelemektedir.

> [!IMPORTANT]
> Bilgi noktası modu, kullanıcı cihazda oturum açınca hangi uygulamaların kullanılabilir olduğunu belirler. Ancak bilgi noktası modu bir güvenlik yöntemi değildir. Bir "izin verilen" uygulamanın izin verilmiyor başka bir uygulamayı açmasına engel olmaz. Bu davranışı kısıtlayamamız nedeniyle uygulamalar Edge, Dosya Gezgini ve Microsoft Store başlatabilirsiniz. Bilgi Noktası'dan başlatılan belirli uygulamalar varsa, uygun ilkeler oluşturmak için Windows Defender Uygulama [Denetimi (WDAC) CSP'lerini](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) kullanın. 
> 
> Buna ek olarak Karma Gerçeklik Giriş, bilgi noktası uygulaması olarak ayarlanmaz.

<a id="aumids"></a>

|Uygulama Adı |AUMID |
| --- | --- |
|3B Görüntüleyici |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Takvim |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! Uygulaması |
|HoloLens'te Cihaz Seçici (1. nesil) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2'de Cihaz Seçici |Microsoft.Windows.DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows.DevicesFlowHost |
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
|Fotoğraflar |Microsoft.Windows.Photos \_ 8wekyb3d8bbwe \! Uygulaması |
|Eski Ayarlar |HolographicSystemSettings_cw5n1h2txyewy! App |
|Yeni Ayarlar |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|İpuçları |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Fotoğraf veya video yakalamayı etkinleştirmek için Kamera uygulamasını bilgi noktası uygulaması olarak etkinleştirmeniz gerekir.  
> <sup>2</sup> Kamera uygulamasını etkinleştirirken aşağıdaki koşulları takip edin:
> - Hızlı Eylemler menüsünde Fotoğraf ve Video düğmeleri bulunur.  
> - Ayrıca, resimlerle etkileşim kurarak veya resim ala bir uygulamayı (Fotoğraflar, Posta veya OneDrive gibi) etkinleştirmeniz gerekir.  
>  
> <sup>3</sup> Cortana'yı bilgi noktası uygulaması olarak etkinleştirmemiş bile olsa, yerleşik sesli komutlar etkinleştirilir. Ancak, devre dışı özelliklerle ilgili komutların hiçbir etkisi yoktur.  
> <sup>4</sup> Miracast'i doğrudan etkinleştiresiniz. Kiosk uygulaması olarak Miracast'i etkinleştirmek için Kamera uygulamasını ve Cihaz Seçici uygulamasını etkinleştirin.

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
-   Bilgi Noktası, Kullanıcı oturum açma türünün parçası olan tüm kullanıcılar için etkinleştirilir; bu ayar bir kullanıcı veya Azure AD grubuyla ayarlanır. 
-   Bilgi noktası yapılandırması ayar ve Kullanıcı oturum açma türü **(Bilgi** Noktası'nda oturum açan kullanıcılar) ve Uygulamalar seçildikten sonra, Cihaz Yapılandırması yine de bir gruba atanmalı. Atananlar, Bilgi Noktası cihaz yapılandırmasını hangi cihazların alacaklarını belirler, ancak Bilgi Noktası etkinse veya etkinleştirilmediyse ile etkileşim kurmaz. 
    - Intune'da yapılandırma profilleri atamanın etkileri hakkında tam bilgi için bkz. Intune'da kullanıcı [ve cihaz profilleri Microsoft Intune.](https://docs.microsoft.com/intune/configuration/device-profile-assign)

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

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için Microsoft Intune veya diğer MDM kullanın

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

MDM sisteminizi, Kullanıcı ilk kez oturum açtığında HoloLens cihazlarını otomatik olarak kaydedecek şekilde yapılandırabilir veya kullanıcıların cihazları el ile kaydetmelerini sağlayabilirsiniz. Cihazların Azure AD etki alanına katılması ve uygun gruplara atanması da gerekir.

Cihazları kaydetme hakkında daha fazla bilgi için bkz. [Windows cihazları IÇIN MDM ve Intune kayıt yöntemlerinde](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods) [HoloLens kaydetme](hololens-enroll-mdm.md) .

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, adım 2 &ndash; bilgi noktası yapılandırma profili oluşturma

1. [Azure](https://portal.azure.com/) portalını açın ve Intune yönetici hesabınızda oturum açın.
1. **Microsoft Intune**  >  **cihaz yapılandırması-profiller**  >  **Profil oluştur**' u seçin.
1. Bir profil adı girin.
1. **Platform**  >  **Windows 10 ve üzeri**' i seçin ve ardından **profil türü**  > **cihaz kısıtlamaları**' nı seçin.
1.   >  **Bilgi noktası** Yapılandır ' ı seçin ve ardından aşağıdakilerden birini seçin:
   - Tek uygulama bilgi noktası oluşturmak için, **bilgi noktası modu**  >  **tek uygulama bilgi noktası**' nı seçin.
   - Birden çok uygulama bilgi noktası oluşturmak için **bilgi noktası modu**  >  **çoklu uygulama bilgi noktası**' nı seçin.
1. Bilgi noktası 'nı yapılandırmaya başlamak için **Ekle**' yi seçin.

Sonraki adımlarınız, istediğiniz bilgi noktası türüne göre farklılık gösterir. Daha fazla bilgi için, aşağıdaki seçeneklerden birini seçin:  

- [Tek uygulama bilgi noktası](#mdmconfigsingle)
- [Çoklu uygulama bilgi noktası](#mdmconfigmulti)

Bilgi noktası yapılandırma profili oluşturma hakkında daha fazla bilgi için bkz. [Windows 10 ve Windows holographic for Business cihaz ayarları Intune kullanarak adanmış bir bilgi noktası olarak çalışacak şekilde](https://docs.microsoft.com/intune/configuration/kiosk-settings).

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, adım 3 (tek uygulama) &ndash;  tek uygulama bilgi noktası için ayarları yapılandırma

Bu bölüm, tek bir uygulama bilgi noktası gerektiren ayarları özetler. Daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- Intune 'da bir bilgi noktası yapılandırma profilini yapılandırma hakkında daha fazla bilgi için, bkz. [Microsoft Intune kullanarak bilgi noktası modunu yapılandırma](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Intune 'daki tek uygulama bilgi noktaları için kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [tek tam ekran uygulama bilgi noktaları](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir XML yapılandırması kullanmanız gerekiyorsa, [bilgi noktası yapılandırmasını tanımlayan BIR XML dosyası oluşturun](#ppkioskconfig).

1. **Kullanıcı oturum açma türü**  >  **Yerel Kullanıcı hesabı**' nı seçin ve ardından bilgi noktasında oturum açan yerel (cihaz) hesabın veya Microsoft hesabının (MSA) Kullanıcı adını girin.
   > [!NOTE]  
   > **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.
1. **Uygulama türü**  >  **depolama uygulaması**' nı seçin ve ardından listeden bir uygulama seçin.

Bir sonraki adımınız, profili bir gruba [atacaktır](#mdmassign) .

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, adım 3 (çoklu uygulama) &ndash; birden çok uygulama bilgi noktası için ayarları yapılandırma

Bu bölümde, çok uygulama bilgi noktası gerektiren ayarlar özetlenmektedir. Daha ayrıntılı bilgi için aşağıdaki makalelere bakın:

- Intune 'da bir bilgi noktası yapılandırma profilini yapılandırma hakkında daha fazla bilgi için, bkz. [Microsoft Intune kullanarak bilgi noktası modunu yapılandırma](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Intune 'da çoklu uygulama bilgi noktaları için kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [çoklu uygulama bilgi noktaları](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir XML yapılandırması kullanmanız gerekiyorsa, [bilgi noktası yapılandırmasını tanımlayan BIR XML dosyası oluşturun](#ppkioskconfig). Bir XML dosyası kullanırsanız, [Başlangıç yerleşimini](#start-layout-for-hololens)eklediğinizden emin olun.  
- İsteğe bağlı olarak, Intune veya diğer MDM hizmetleriyle özel bir başlangıç düzeni kullanabilirsiniz. Daha fazla bilgi için bkz. [MDM Için Başlangıç düzeni dosyası (Intune ve diğerleri)](#start-layout-file-for-mdm-intune-and-others).

1. **Hedef Windows 10 ' u S modunda cihazlar**  >  **Hayır**' ı seçin.  
>[!NOTE]  
> S modu, Windows holographic for Business üzerinde desteklenmez.

1. **Kullanıcı oturum açma türü**  >  **Azure AD Kullanıcı veya grup** veya **Kullanıcı oturum açma türü**  >  **HoloLens Visitor**' u seçin ve ardından bir veya daha fazla Kullanıcı grubu veya hesabı ekleyin.  

   Yalnızca **Kullanıcı oturum açma türünde** belirttiğiniz gruplara veya hesaplara ait kullanıcılar bilgi noktası deneyimini kullanabilir.

1. Aşağıdaki seçenekleri kullanarak bir veya daha fazla uygulama seçin:
   - Karşıya yüklenen bir iş kolu uygulaması eklemek için **Mağaza uygulaması Ekle** ' yi seçin ve ardından istediğiniz uygulamayı seçin.
   - Kendi AUMıD 'sini belirterek bir uygulama eklemek için **aumıd tarafından Ekle** ' yi seçin ve sonra uygulamanın aumıd 'sini girin. [Kullanılabilir AUMIDs listesine bakın](#aumids)

Bir sonraki adımınız, profili bir gruba [atacaktır](#mdmassign) .

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, adım 4 &ndash; bilgi noktası yapılandırma profilini bir gruba atama

Bilgi noktası yapılandırmasının dağıtımını istediğiniz yeri ayarlamak için bilgi noktası yapılandırma profilinin **atamalar** sayfasını kullanın. En basit durumda, bilgi noktası yapılandırma profilini cihaz MDM 'ye kaydedildiğinde HoloLens cihazını içerecek bir gruba atarsınız.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, 5. adım (tek uygulama) &ndash; tek uygulama bilgi noktası dağıtın

Bir MDM sistemi kullandığınızda, bu cihazı OOBE sırasında MDM 'ye kaydedebilirsiniz. OOBE bittikten sonra cihazda oturum açmak kolaydır.

OOBE sırasında şu adımları izleyin:

1. Bilgi noktası yapılandırma profilinde belirttiğiniz hesabı kullanarak oturum açın.
1. Cihazı kaydedin. Cihazın, bilgi noktası yapılandırma profilinin atandığı gruba eklendiğinden emin olun.
1. Mağaza uygulamasının indirmesi ve yüklemesi ve ilkelerin uygulanması için, OOBE 'nin bitmesini bekleyin. Ardından cihazı yeniden başlatın.

Cihazda bir sonraki oturum açışınızda bilgi noktası uygulamasının otomatik olarak başlatılması gerekir.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız, [atama durumunu kontrol](https://docs.microsoft.com/intune/configuration/device-profile-monitor)edin.

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, 5. adım (çoklu uygulama) &ndash; çok uygulama bilgi noktası dağıtma

Bir MDM sistemi kullandığınızda, cihazı Azure AD kiracınıza katılabilir ve bu cihazı OOBE sırasında MDM 'ye kaydedebilirsiniz. Uygunsa, OOBE işlemi sırasında kullanılabilir olmaları için kullanıcılara kayıt bilgilerini sağlayın.

> [!NOTE]  
> Bilgi noktası yapılandırma profilini Kullanıcı içeren bir gruba atadıysanız, bu kullanıcı hesaplarından birinin cihazda oturum açmak için ilk hesap olduğundan emin olun.

OOBE sırasında şu adımları izleyin:

1. **Kullanıcı oturum açma türü** grubuna ait olan hesabı kullanarak oturum açın.
1. Cihazı kaydedin.
1. Bilgi noktası yapılandırma profilinin parçası olan tüm uygulamaların indirilip yüklenmesini bekleyin. Ayrıca, ilkelerin uygulanmasını bekleyin.  
1. OOBE bittikten sonra, Microsoft Mağazası 'ndan veya dışarıdan yükleme yoluyla ek uygulamalar yükleyebilirsiniz. Cihazın otomatik olarak yüklenmesi için [gerekli uygulamalar](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) .
1. Yükleme bittikten sonra, cihazı yeniden başlatın.

Bir sonraki sefer, **Kullanıcı oturum açma türüne** ait bir hesabı kullanarak cihazda oturum açtığınızda, bilgi noktası uygulamasının otomatik olarak başlatılması gerekir.

Bu noktada bilgi noktası yapılandırmanızı görmüyorsanız, [atama durumunu kontrol](https://docs.microsoft.com/intune/configuration/device-profile-monitor)edin.

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için bir sağlama paketi kullanın

Sağlama paketini kullanarak bilgi noktası modunu ayarlamak için aşağıdaki adımları izleyin.

1. [Başlangıç düzeni](#start-layout-for-hololens)dahil olmak üzere [bilgi noktası YAPıLANDıRMASıNı tanımlayan bir XML dosyası oluşturun](#ppkioskconfig).
2. [XML dosyasını bir sağlama paketine ekleyin.](#ppconfigadd)
3. [Sağlama paketini HoloLens 'e uygulayın.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Paketi sağlama, 1. adım &ndash; bilgi noktası YAPıLANDıRMASı XML dosyası oluşturma

Aşağıdakiler dışında, [Windows Masaüstü için bir bilgi noktası yapılandırma XML dosyası oluşturmak üzere genel yönergeleri](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)izleyin:

- Klasik Windows uygulamaları (Win32) eklemeyin. HoloLens bu uygulamaları desteklemiyor.
- HoloLens için [yer tutucu başlangıç DÜZENI XML](#start-layout-for-hololens) 'sini kullanın.
- İsteğe bağlı: bilgi noktası yapılandırmasına konuk erişimi ekleme

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>İsteğe bağlı: bilgi noktası yapılandırmasına konuk erişimi ekleme

[XML dosyasının **configs** bölümünde](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), konukların bilgi noktası kullanmasına izin vermek için **ziyaretçi** adlı özel bir grup yapılandırabilirsiniz. Bilgi noktası **ziyaretçi** özel grubunu destekleyecek şekilde yapılandırıldığında, oturum açma sayfasına bir "**Konuk**" seçeneği eklenir. **Konuk** hesabı bir parola gerektirmez ve hesap oturumu kapattığında hesapla ilişkili tüm veriler silinir.

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

[Windows holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonraki sürümlerinde:
- AAD ve ADD olmayan yapılandırmaların her ikisi de, bilgi noktası modları için otomatik oturum açma özelliği etkinleştirilmiş ziyaretçi hesaplarını destekler.

##### <a name="non-aad-configuration"></a>AAD olmayan yapılandırma

1. Şu şekilde bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için çalışma zamanı ayarlarını/Atananı yapılandırır.
    1. İsteğe bağlı olarak, cihazı daha sonra yönetilebilmesi için MDM 'de (çalışma zamanı ayarları/çalışma alanı/kayıtlar) kaydeder.
    1. Yerel hesap oluşturma
2. [Sağlama paketini uygulayın](https://docs.microsoft.com/hololens/hololens-provisioning).

##### <a name="aad-configuration"></a>AAD yapılandırması

Bilgi noktası modu için yapılandırılmış AAD 'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak bir ziyaretçi hesabında oturum açabilir. Ziyaretçi hesabında oturum açtıktan sonra, ziyaretçi başlangıç menüsünde açıkça oturum açana veya cihaz yeniden başlatılana kadar cihaz yeniden oturum açmayı istemez.

Ziyaretçi otomatik oturum açma, [özel OMA-URI ilkesi](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon


| İlke |Açıklama |Yapılandırmalar 
| --------------------------- | ------------- | -------------------- |
| MixedReality/Visitooyutologon | Bir ziyaretçinin bir bilgi noktasında otomatik olarak oturum açmasına olanak tanır. | 1 (Evet), 0 (Hayır, varsayılan.) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens için yer tutucu başlangıç düzeni

Birden çok uygulama bilgi noktası yapılandırmak için bir [sağlama paketi](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) kullanıyorsanız, yordam başlangıç düzeni gerektirir. Başlangıç düzeni özelleştirmesi Windows holographic for Business 'da desteklenmez. Bu nedenle, bir yer tutucu başlangıç düzeni kullanmanız gerekir.

> [!NOTE]  
> Tek uygulama bilgi noktası, bir Kullanıcı oturum açtığında bilgi noktası uygulamasını başlatduğundan, bir başlangıç menüsü kullanmaz ve bir başlangıç düzenine sahip olmak zorunda değildir.

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

Aşağıdaki örneği bir XML dosyası olarak kaydedin. Bu dosyayı, Microsoft Intune (veya bilgi noktası profili sağlayan başka bir MDM hizmetinde) birden çok uygulama bilgi noktası yapılandırdığınızda kullanabilirsiniz.

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

1. [Windows yapılandırma Tasarımcısı 'nı](https://www.microsoft.com/store/apps/9nblggh4tx22)açın.
1. **Gelişmiş sağlama**' yı seçin, projeniz için bir ad girin ve ardından **İleri**' yi seçin.
1. **Windows 10 holographic**' ı seçin ve ardından **İleri**' yi seçin.
1. **Son**'u seçin. Paketinizin çalışma alanı açılır.
1. **Çalışma zamanı ayarları**  >  **Atananı**  >  **multiappassignedaccesssettings**' i seçin.
1. Orta bölmede, oluşturduğunuz bilgi noktası yapılandırması XML dosyasını bulmak ve seçmek için **Araştır** ' ı seçin.

   ![Windows yapılandırma Tasarımcısı 'nda MultiAppAssignedAccessSettings alanının ekran görüntüsü](./images/multiappassignedaccesssettings.png)

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
   > **Paket şifrelemeyi etkinleştir**' i seçmeyin. HoloLens cihazlarda bu ayar sağlamanın başarısız olmasına neden olur.
1. **İleri**’yi seçin.
1. Sağlama paketinin oluşturulduğunda gitmesini istediğiniz çıkış konumunu belirtin. Varsayılan olarak, Windows yapılandırma Tasarımcısı çıkış konumu olarak proje klasörünü kullanır. Çıkış konumunu değiştirmek istiyorsanız, **Araştır**' ı seçin. İşiniz bittiğinde **İleri**' yi seçin.
1. Paketi oluşturmaya başlamak için **Oluştur** ' u seçin. Sağlama paketinin derlemesi uzun sürmez. Yapı sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Sağlama paketi, adım 3 &ndash; sağlama paketini HoloLens 'e uygulama

"Bir sağlama paketi kullanarak HoloLens 'i yapılandırma" makalesinde, aşağıdaki koşullarda sağlama paketini uygulamak için ayrıntılı yönergeler sunulmaktadır:

- Başlangıçta [bir sağlama paketini, kurulum sırasında HoloLens 'e uygulayabilirsiniz](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Ayrıca, [kurulum sonrasında HoloLens 'e bir sağlama paketi de uygulayabilirsiniz](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Tek uygulama bilgi noktası ayarlamak için Windows cihaz portalını kullanma

Windows cihaz portalını kullanarak bilgi noktası modunu ayarlamak için aşağıdaki adımları izleyin.

1. [HoloLens cihazını Windows cihaz portalını kullanacak şekilde ayarlayın](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Cihaz portalı, HoloLens 'te bulunan ve bilgisayarınızdaki bir Web tarayıcısından bağlantı kurmak için kullanabileceğiniz bir Web sunucusudur.

    > [!CAUTION]
    > Cihaz portalını kullanmak için HoloLens 'i ayarlarken, cihazda Geliştirici modunu etkinleştirmeniz gerekir. Windows holographic for Business içeren bir cihazda geliştirici modu, uygulamaları dışarıdan yüklemeye olanak sağlar. Ancak, bu ayar, bir kullanıcının Microsoft Store tarafından sertifikasız uygulamaları yükleyebir risk oluşturur. Yöneticiler, [Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)'Deki **ApplicationManagement/allowdeveloper unlock** ayarını kullanarak Geliştirici modunu etkinleştirebilme özelliğini engelleyebilir. [Geliştirici modu hakkında daha fazla bilgi edinin.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Bir bilgisayarda, [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) veya [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)kullanarak HoloLens 'e bağlanın.

1. Aşağıdakilerden birini yapın:
   - İlk kez Windows cihaz portalına bağlanıyorsanız, [bir Kullanıcı adı ve parola oluşturun](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Daha önce ayarladığınız Kullanıcı adını ve parolayı girin.

    > [!TIP]
    > Tarayıcıda bir sertifika hatası görürseniz, [Bu sorun giderme adımlarını](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)izleyin.

1. Windows cihaz portalında **bilgi noktası modu**' nu seçin.

1. **Bilgi noktası modunu etkinleştir**' i seçin, cihaz başlatıldığında çalıştırılacak bir uygulama seçin ve ardından **Kaydet**' i seçin.

    ![Bilgi noktası modu](images/kiosk.png)
1. HoloLens 'i yeniden başlatın. Hala cihaz portalı sayfanız açıksa sayfanın en üstünde **Yeniden Başlat** ' ı seçebilirsiniz.

> [!NOTE]
> Bilgi noktası modu, bir gerekli sorgu dizesi parametresi ("true&quot; veya &quot;false&quot; değeri olan &quot;Kıoskmodeenabled") ve bir isteğe bağlı parametre ("startupApp" bir paket adı ile) ile/api/holographic/kioskmode/Settings ile bir POST işlemi yaparak Device Portal 'ın REST API aracılığıyla ayarlanabilir. Lütfen cihaz portalının yalnızca geliştiricilere yönelik olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmeyeceğini aklınızda bulundurun. REST API gelecek güncelleştirmelerde/sürümlerde değişebilir.

## <a name="more-information"></a>Daha fazla bilgi

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Sağlama paketini kullanarak bir bilgi noktası yapılandırmayı izleyin.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Genel atanan erişim – bilgi noktası modu
- Bilgi noktası için, sistem düzeyinde bilgi noktası modu uygulayan yeni bilgi noktası yöntemi etkinleştirilerek kimlik yönetimi azaltıldı.

Bu yeni özellik, bir BT yöneticisinin sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için bir HoloLens 2 cihazı yapılandırmasını sağlar, sistemde herhangi bir kimlikle hiçbir benzeşim yoktur ve cihazda oturum açan herkese uygulanır. Bu yeni özellik hakkında daha fazla bilgi için bkz. [HoloLens genel atanan erişim bilgi noktası](hololens-global-assigned-access-kiosk.md) belgeleri.

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

- Windows holographic 'den önce, 20H2 sürümü-HoloLens, Başlat menüsündeki tüm uygulamaları gösterir.
- Windows holographic, sürüm 20H2-bir cihazda hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişim birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "başlangıç bölümünde gösterilmez" menüsünü görür.

![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )


- [Windows holographic sürümünden itibaren, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1), bilgi noktası modu boş bir başlangıç menüsünü göstermeden önce genel atanan erişimi arar. Bilgi noktası deneyimi, AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bir bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma

- Bilgi noktası modu hatalarında kullanılabilir uygulamaları ortadan kaldırarak daha güvenli bilgi noktası modu.
- 60 güne kadar Azure AD grupları ile birlikte kullanılacak çevrimdışı kiosks 'leri etkinleştirdi.

Bu ilke, kaç gün boyunca Azure AD grup üyeliği önbelleğinin oturum açmış kullanıcı için Azure AD gruplarını hedefleyen atanan erişim yapılandırmalarında kullanılmasına izin verileceğini denetler. Bu ilke değeri 0 ' dan büyük bir değere ayarlandıktan sonra, önbellek kullanılır.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az-0 gün  
Maksimum 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedefleyen bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bunu HoloLens cihazlarına atayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayarlayan ve HoloLens cihazlarına atayan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri, OMA-URI metin kutusunda./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilmelidir
    1. Değer, izin verilen Min/Max arasında olabilir.
1. HoloLens cihazlarını kaydedin ve her iki yapılandırmanın cihaza uygulandığını doğrulayın. 
1. Internet 'in kullanılabildiği Azure AD User 1 oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. Artık Azure AD Kullanıcı 1, HoloLens 'i çevrimdışı alabilir ve ilke değeri X gün sayısı için izin verdiği sürece bilgi noktası modu için kullanabilir. 
1. 4 ve 5. adım, diğer tüm Azure AD kullanıcıları için yinelenebilir. burada anahtar noktası, herhangi bir Azure AD kullanıcısının Internet 'i kullanarak cihaza oturum açması gerekir. bu sayede, bilgi noktası yapılandırmasının hedeflediği Azure AD grubuna üye olduklarını belirleyebiliriz. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilene kadar "bağlantısı kesik" ortamlarda bahsedilen hata davranışı ile karşılaşırsınız. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>HoloLens için XML bilgi noktası kod örnekleri

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Bir Azure AD grubunu hedefleyen birden çok uygulama bilgi noktası modu. 
Bu bilgi noktası, Azure AD grubundaki kullanıcılar için bir bilgi noktası dağıttığında, 3 uygulamayı içeren bir bilgi noktası etkinleştirilmiş olur: ayarlar, uzaktan yardım ve geri bildirim hub 'ı. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan GUID 'yi kendi Azure AD grubuyla eşleşecek şekilde değiştirdiğinizden emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Azure AD hesabını hedefleyen birden çok uygulama bilgi noktası modu.
Bu bilgi noktası tek bir kullanıcı için bir bilgi noktası dağıtır ve 3 uygulamayı içeren bir bilgi noktası etkin olur: ayarlar, uzaktan yardım ve geri bildirim hub 'ı. Bu örneği hemen kullanılacak şekilde değiştirmek için, aşağıda vurgulanan hesabı kendi Azure AD hesabıyla eşleşecek şekilde değiştirdiğinizden emin olun. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

