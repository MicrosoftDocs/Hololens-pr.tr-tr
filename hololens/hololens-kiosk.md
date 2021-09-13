---
title: bilgi noktası olarak HoloLens ayarlama
description: HoloLens cihazlardaki uygulamaları kilitlemek için bir bilgi noktası yapılandırması ayarlamayı ve kullanmayı öğrenin.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033196"
---
# <a name="set-up-hololens-as-a-kiosk"></a>bilgi noktası olarak HoloLens ayarlama

## <a name="what-is-kiosk-mode"></a>Bilgi noktası modu nedir?

Bilgi noktası modu, Kullanıcı HoloLens oturum açtığında başlangıç menüsünde hangi uygulamaların gösterildiğini denetleyebileceğiniz bir özelliktir. 2 desteklenen senaryo vardır:

1. **Tek uygulama bilgi noktası modu** – başlangıç menüsü gösterilmez ve Kullanıcı oturum açtığında tek bir uygulama otomatik olarak başlatılır. <br> *Örnek kullanımları*: yalnızca Dynamics 365 kılavuzlar uygulamasını çalıştıran bir cihaz.
2. **birden çok uygulama bilgi noktası modu** – Başlat menüsü, yalnızca bir kullanıcı oturum açtığında bilgi noktası yapılandırmasında belirtilen uygulamaları gösterir. Bir uygulama, istenirse otomatik olarak başlatılacak şekilde seçilebilir. <br> *örnek kullanımları*: başlangıç menüsünde yalnızca mağaza uygulamasını, geri bildirim merkezini ve Ayarlar uygulamayı gösteren bir cihaz.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Kullanıcı oturum açtığında bilgi noktası modu deneyiminin açıklaması

Aşağıdaki tabloda, farklı bilgi noktası modlarında Özellik özellikleri listelenmektedir.

| &nbsp; |Başlat menüsü |Hızlı Eylemler menüsü |Kamera ve video |Miracast |Cortana |Yerleşik sesli komutlar |
| --- | --- | --- | --- | --- | --- | --- |
|Tek uygulama bilgi noktası |Devre dışı |Devre dışı |Devre dışı |Devre dışı   |Devre dışı |Etkinletir |
|Çoklu uygulama bilgi noktası |Etkin |Etkinletir  |Kullanılabileceğini  |Kullanılabileceğini |Kullanılabileceğini   |Etkinletir  |

\*devre dışı bırakılan özelliklerin nasıl etkinleştirileceği veya ses komutlarının devre dışı özelliklerle nasıl etkileşim kurduğu hakkında daha fazla bilgi için, Cortana [uygulamalar için HoloLens aumıds](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)bölümüne bakın.

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Bilgi noktası modunu yapılandırmadan önce önemli genel konular

1. ortamınızda HoloLens oturum açan kullanıcı hesabı türünü belirleme-HoloLens Azure Active Directory (AAD) hesaplarını, Microsoft hesaplarını (MSA) ve yerel hesapları destekler. Ayrıca, Konuk/ziyaretçi adlı geçici olarak oluşturulan hesaplar da desteklenir (yalnızca AAD 'ye yönelik ekleme cihazları için). [Kullanıcı kimliğini yönetme ve HoloLens için oturum açma](hololens-identity.md)hakkında daha fazla bilgi edinin.
2. Bilgi noktası modu deneyiminin hedeflerini (herkes, tek bir Kullanıcı, belirli kullanıcılar veya AAD gruplarına üye olan kullanıcılar vb.) belirtir.
3. Birden çok uygulama bilgi noktası modu için, başlangıç menüsünde gösterilecek uygulamaları (öğeleri) saptayın. Her uygulama için, [uygulama Kullanıcı MODELI kimliği (AUMıD)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) gerekecektir.
4. bilgi noktası modunun, çalışma zamanı sağlama paketleri ya da mobil cihaz yönetimi (MDM) sunucusu aracılığıyla HoloLens uygulanacağını belirleme.

## <a name="security-considerations"></a>Güvenlik konuları

Bilgi noktası modu bir güvenlik yöntemi olarak düşünülmemelidir, ancak kullanıcı oturum açma bölümünde başlatma deneyimini denetlemek için bir yol olarak. Bilgi noktası modu deneyimini aşağıda belirtilen seçeneklerle birleştirerek, güvenlikle ilgili belirli gereksinimler vardır:

- Ayarlar uygulaması bilgi noktası modunda gösterilecek şekilde yapılandırıldığında ve Ayarlar uygulamada hangi sayfaların gösterileceğini denetlemek istiyorsanız, [sayfa Ayarlar görünürlük](settings-uri-list.md) bölümüne bakın
- belirli donanım özelliklerine erişimi denetlemek istediğinizde (örneğin, kamera, Bluetooth vb.), bazı uygulamalar için, vb. [HoloLens 2-Windows istemci yönetimi tarafından desteklenen ilke CSP 'deki ilkelere](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)bakın. Fikirler için [ortak cihaz kısıtlamalarımızı](hololens-common-device-restrictions.md) gözden geçirebilirsiniz.
- Bilgi noktası modu, bir uygulamayı (bilgi noktası deneyiminin bir parçası olarak yapılandırılmış) diğer uygulamaların başlatılmasını engellemez. HoloLens üzerinde belirli uygulamaların/işlemlerin başlatılmasını tamamen engellemek istediğinizde, [Microsoft Intune Azure 'da HoloLens 2 cihazlarda Windows Defender uygulama denetimini kullanma](/mem/intune/configuration/custom-profile-hololens) konusuna bakın.

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>HoloLens bilgi noktası modu için önemli teknik konular

Yalnızca çalışma zamanı sağlama paketlerini kullanmayı planlıyor veya el ile bilgi noktası yapılandırması oluşturmayı planlıyorsanız geçerlidir. Bilgi noktası modu yapılandırması, XML tabanlı hiyerarşik bir yapı kullanır:

- Atanan erişim profili, başlangıç menüsünde bilgi noktası modunda hangi uygulamaların görüntüleneceğini tanımlar. Birden çok profili, daha sonra başvurulabilen aynı XML yapısında tanımlayabilirsiniz.
- Atanan erişim yapılandırması, bu profilin bir profiline ve hedef kullanıcısına (örneğin, belirli bir kullanıcıya veya AAD grubuna veya ziyaretçiye vb.) başvurur. Kullanım senaryolarınızın karmaşıklığına göre aynı XML yapısında birden çok yapılandırma tanımlayabilirsiniz (aşağıdaki desteklenen senaryolar bölümüne bakın).
- Daha fazla bilgi edinmek için [atanan](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Kimlik türünü temel alan bilgi noktası modu için desteklenen senaryolar

Kopyalama yapıştırmadan önce gerekli olan senaryonuz ve güncelleştirmeniz temel alınarak örneklere yönelik [başvuru bağlantılarına](hololens-kiosk-reference.md#kiosk-xml-code-samples) bakın.

> [!NOTE]
> Yalnızca, bilgi noktası yapılandırması oluşturmak için Intune 'un Kullanıcı arabirimini kullanmıyorsanız, XML kullanın.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Yerel hesap veya MSA olarak oturum açan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları**  | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum açan her kullanıcı bilgi noktası deneyimini alır. | [Birden çok uygulama genel atanmış erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global atanan erişim [20 H2 ve daha yeni derlemeler](hololens-release-notes.md#windows-holographic-version-20h2) gerektirir |
| Oturum açan belirli bir kullanıcı bilgi noktası deneyimini alır.  | [Belirli bir kullanıcının adını belirterek, tek veya birden çok uygulama tarafından atanan erişim profilini (gerekli olduğu gibi) yapılandırın.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Aşağıdaki desteklenen seçeneklere bakın.](#steps-in-configuring-kiosk-mode-for-hololens) | Tek uygulama bilgi noktası modu için HoloLens yalnızca yerel kullanıcı hesabı veya MSA hesabı desteklenir. <br> Birden çok uygulama bilgi noktası modu için HoloLens yalnızca MSA hesabı veya AAD hesabı desteklenir. |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD hesabı olarak oturum açan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları** | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum açan her kullanıcı bilgi noktası deneyimini alır. | [Birden çok uygulama genel atanmış erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global atanan erişim [20 H2 ve daha yeni derlemeler](hololens-release-notes.md#windows-holographic-version-20h2) gerektirir |
| Oturum açan her Kullanıcı, belirli kullanıcılar hariç bilgi noktası deneyimini alır. | [Bazı kullanıcıları (cihaz sahipleri olması gereken) dışlayarak birden çok uygulama genel atanmış erişim profilini yapılandırın](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners). | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Global atanan erişim [20 H2 ve daha yeni derlemeler](hololens-release-notes.md#windows-holographic-version-20h2) gerektirir |
| Her AAD kullanıcısı, bu kullanıcıya özgü ayrı bilgi noktası deneyimi alır. | [Her Kullanıcı için AAD hesap adını belirten atanan erişim yapılandırmasını yapılandırın.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Farklı AAD gruplarındaki kullanıcılar, yalnızca grupları için bilgi noktası modunda deneyim yaşar. | [Her istenen AAD grubu için atanan erişim yapılandırmasını yapılandırın.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • bir kullanıcı oturum açtığında ve HoloLens Internet 'e bağlıyken, bu kullanıcının bilgi noktası yapılandırması var olan bir aad grubunun üyesi olduğu bulunursa, kullanıcı bu aad grubu için bilgi noktası deneyimi yaşar. <br> • [kullanıcı oturum açtığında bir internet yoksa, kullanıcı HoloLens hata modu davranışına karşı çalışır.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Kullanıcı oturum açtığında ve AAD grubu tabanlı bilgi noktası kullanılması gerektiğinde internet kullanılabilirliği garanti edilmediği takdirde, [AADGroupMembershipCacheValidityInDayspolicy kullanmayı göz önünde bulundurun](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • Oturum açma sırasında AAD gruplarıyla ilgili en iyi deneyim için [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) kullanma önerisi |
| geçici amaçlar için HoloLens kullanması gereken kullanıcılar bilgi noktası deneyimi alın. | [Ziyaretçiler için atanan erişim yapılandırması yapılandırma](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama-tek uygulama](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • geçici kullanıcı hesabı, oturum açma sırasında HoloLens tarafından otomatik olarak oluşturulur ve geçici kullanıcı oturumu kapattığında kaldırılır. <br> • [Ziyaretçi otomatik oturum açma ilkesini](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)etkinleştirmeyi düşünün. |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>HoloLens için bilgi noktası modunu yapılandırma adımları

Bilgi noktası yapılandırması aşağıdaki yollarla oluşturulup uygulanabilir:

1. MDM sunucusunun kullanıcı arabirimi ile, örneğin, Intune 'un bilgi noktası şablonları veya bu, HoloLens için uzaktan uygulanan özel OMA-URI yapılandırması.
2. Çalışma zamanı sağlama paketleri ile, daha sonra HoloLens doğrudan uygulanan.

Aşağıdaki şekilde yapılandırmak için, kullanmak istediğiniz işlemle eşleşen sekmeyi seçin.

1. [tek uygulama bilgi noktası şablonu Microsoft Intune](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [birden çok uygulama bilgi noktası şablonu Microsoft Intune](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [özel şablon Microsoft Intune](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Çalışma zamanı sağlama-çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Çalışma zamanı sağlama-tek uygulama](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Ziyaretçi hesapları bilgi noktası deneyimine otomatik olarak nasıl oturum açabilir?

derlemeler [Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonraki sürümler:

- AAD ve ADD olmayan yapılandırmaların her ikisi de bilgi noktası modları için otomatik oturum açma özellikli ziyaretçi hesaplarını destekler.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>bilgi noktası deneyimi HoloLens (1. gen) destekleniyor mu?

Bilgi noktası modu yalnızca cihazda Windows Holographic for Business varsa kullanılabilir. tüm HoloLens 2 cihazları Windows Holographic for Business ile birlikte dağıtılır ve başka bir sürüm yoktur. her HoloLens 2 cihaz, bilgi noktası modunu kutudan dışarı çalıştırabilir.

HoloLens (1. gen) cihazların hem işletim sistemi derlemesi hem de işletim sistemi sürümü açısından yükseltilmesi gerekir. HoloLens (1. gen) [Windows Holographic for Business](hololens1-upgrade-enterprise.md) sürümüne güncelleştirme hakkında daha fazla bilgi bulabilirsiniz. HoloLens (1. gen) cihazı bilgi noktası modunu kullanacak şekilde güncelleştirmek için önce cihazın Windows 10, sürüm 1803 veya sonraki bir sürümü çalıştırmasını sağlamalısınız. HoloLens (1. gen) cihazınızı varsayılan yapıya kurtarmak için Windows cihaz kurtarma aracını kullandıysanız veya en son güncelleştirmeleri yüklediyseniz, cihazınız yapılandırmaya hazır olur.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Üretim dışı ortamlarda bilgi noktası yapılandırmak için cihaz portalını kullanma

[HoloLens cihazı Windows cihaz portalını kullanacak şekilde](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)ayarlayın. cihaz portalı, HoloLens bilgisayarınızdaki bir web tarayıcısından bağlantı kurmak için kullanabileceğiniz bir web sunucusudur.

 > [!CAUTION]
 > cihaz portalını kullanmak için HoloLens ayarlarken, cihazda geliştirici modunu etkinleştirmeniz gerekir. Windows Holographic for Business bir cihazda geliştirici modu, uygulamaları dışarıdan yükleyebilmenizi sağlar. Ancak, bu ayar, bir kullanıcının Microsoft Store tarafından sertifikasız uygulamaları yükleyebir risk oluşturur. Yöneticiler, [Ilke CSP](/windows/client-management/mdm/policy-configuration-service-provider)'Deki **ApplicationManagement/allowdeveloper unlock** ayarını kullanarak Geliştirici modunu etkinleştirebilme özelliğini engelleyebilir. [Geliştirici modu hakkında daha fazla bilgi edinin.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Bilgi noktası modu, bir gerekli sorgu dizesi parametresi ("true" veya "false" değeri olan "Kıoskmodeenabled") ve bir isteğe bağlı parametre ("startupApp" bir paket adı ile) ile/api/holographic/kioskmode/Settings ile bir POST işlemi yaparak Device Portal 'ın REST API aracılığıyla ayarlanabilir. Cihaz portalının yalnızca geliştiricilere yönelik olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmeyeceğini aklınızda bulundurun. REST API gelecek güncelleştirmelerde/sürümlerde değişebilir.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Sorun-başlangıç menüsünde bilgi noktası modunda hiçbir uygulama gösterilmez

**Belirtiler**

Bilgi noktası modu uygulanırken hatalardan karşılaşıldığında, aşağıdaki davranış görünür:

- Windows Holographic ' den önce, 20h2 sürümü HoloLens, Başlat menüsü tüm uygulamaları gösterir.
- Windows Holographic, sürüm 20H2-bir cihazın bir bilgi noktası yapılandırması varsa ve bu, genel olarak atanmış erişime ve AAD grubu üyesine atanmış erişime sahip ise, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "başlangıç bölümünde gösterilmez" menüsünü görür.

    ![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )

- [Windows Holographic sürümünden itibaren, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1), bilgi noktası modu boş bir başlangıç menüsünü göstermeden önce genel atanan erişimi arar. AAD grubu bilgi noktası modu sırasında oluşan bilgi noktası deneyimi, genel bilgi noktası yapılandırmasına (varsa) geri dönecek.

**Sorun giderme adımları**

- Uygulamanın AUMıD 'nin doğru şekilde belirtildiğinden ve sürüm içermediğinden emin olun. örnekler için gelen kutusu uygulamalarına yönelik [HoloLens aumıds](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) bölümüne bakın.
- Uygulamanın bu kullanıcı için cihazda yüklü olduğundan emin olun.
- Bilgi noktası yapılandırması AAD gruplarını temel alıyorsa, AAD kullanıcısı oturum açtığında internet bağlantısının mevcut olduğundan emin olun. İsterseniz [Mixedreality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) ilkesini yapılandırıp bu, internet olmadan da çalışabilir.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Sorun-bilgi noktası moduna sahip bir paket oluşturma başarısız oldu

**Belirtiler**

Aşağıdaki gibi bir iletişim kutusu gösterilir.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Sorun giderme adımları**

1. Yukarıdaki iletişim kutusunda gösterildiği gibi, hiper bağlantı ' ya tıklayın.
1. ITıD. log ' i bir metin düzenleyicisinde açın ve içeriği hatayı göstermelidir.

> [!NOTE]
> Birkaç deneme yaptıysanız, günlükteki zaman damgalarına bakın. Bu, yalnızca geçerli sorunları kontrol etmenize yardımcı olur.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Sorun – sağlama paketi başarıyla oluşturuldu ancak uygulanamadı.

**Belirtiler**

HoloLens 'te sağlama paketi uygulanırken hata gösterilir

**Sorun giderme adımları**

1. çalışma zamanı sağlama paketinin mevcut olduğu Windows Configuration Designer projesinin bulunduğu klasöre gidin.
1. ICD. log ' i açın ve sağlama paketini oluştururken günlükte hata olmadığından emin olun. Bazı hatalar derleme sırasında gösterilmiyor, ancak hala ICD. log dosyasında günlüğe kaydediliyor

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Sorun: AAD grubuna birden çok uygulama atanmış erişim çalışmıyor

**Belirtiler**

AAD Kullanıcı oturum açtığında, cihaz bilgi noktası moduna geçmiyor

**Sorun giderme adımları**

- Atanan erişim yapılandırması XML ' nda, oturum açan kullanıcının bir üyesi olduğu AAD grubunun GUID 'sinin, AAD kullanıcısının GUID 'SI değil, kullanıldığını ve kullanılacağını onaylayın.
- Intune portalında AAD kullanıcısının hedeflenen AAD grubunun üyesi olarak gösterildiğini doğrulayın.
