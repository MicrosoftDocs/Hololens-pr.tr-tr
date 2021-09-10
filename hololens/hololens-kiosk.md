---
title: Bilgi HoloLens bilgi noktası olarak ayarlama
description: Mobil cihazlardaki uygulamaları kilitlemek için bilgi noktası yapılandırması ayarlamayı ve HoloLens öğrenin.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427075"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Bilgi HoloLens bilgi noktası olarak ayarlama

## <a name="what-is-kiosk-mode"></a>Bilgi noktası modu nedir?

Bilgi noktası modu, kullanıcı oturum aken başlat menüsünde hangi uygulamaların gösterildiğini kontrol etmek için HoloLens. Desteklenen 2 senaryo vardır:

1. **Tek uygulama bilgi noktası** modu – Başlat menüsü görüntülenmez ve kullanıcı oturum açsa tek bir uygulama otomatik olarak başlatılır. <br> *Örnek:* Yalnızca Dynamics 365 Kılavuzları uygulamasını çalıştıran bir cihaz.
2. **Birden çok uygulama bilgi** noktası modu Başlat menüsü bilgi noktası yapılandırmasında belirtilen uygulamaları gösterir. İsterseniz bir uygulamanın otomatik olarak başlatılması seçilebilir. <br> *Örnek kullanım:* Başlat menüsünde yalnızca Mağaza uygulamasını, Geri Bildirim Merkezi Ayarlar gösteren bir cihaz.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Kullanıcı oturum aken bilgi noktası modu deneyiminin açıklaması

Aşağıdaki tablo, farklı bilgi noktası modlarında özellik özelliklerini listeler.

| &nbsp; |Başlat menüsü |Hızlı Eylemler menüsü |Kamera ve video |Miracast |Cortana |Yerleşik sesli komutlar |
| --- | --- | --- | --- | --- | --- | --- |
|Tek uygulamalı bilgi noktası |Devre dışı |Devre dışı |Devre dışı |Devre dışı   |Devre dışı |Etkin* |
|Çoklu uygulama bilgi noktası |Etkin |Etkin*  |Kullanılabilir*  |Kullanılabilir* |Kullanılabilir*   |Etkin*  |

\*Devre dışı bırakılmış özellikleri etkinleştirme veya ses komutlarının devre dışı bırakılmış özelliklerle ve Cortana etkileşim kurma hakkında daha fazla bilgi HoloLens bkz. uygulamalar için [AUMID'ler.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Bilgi noktası modunu yapılandırmadan önce dikkat edilmesi gereken önemli genel noktalar

1. Ortamınız içinde HoloLens oturum açmanın HoloLens belirleme - HoloLens (AAD) Azure Active Directory, Microsoft Hesapları (MSA) ve Yerel hesapları destekler. Ayrıca, geçici olarak oluşturulan konuk/ziyaretçi adı verilen hesaplar da de desteklemektedir (yalnızca AAD'ye katılma cihazları için). Daha fazla bilgi [için daha fazla bilgi için kullanıcı kimliğini yönetme ve HoloLens.](hololens-identity.md)
2. Bilgi noktası modu deneyiminin hedeflerini belirleme : bunun herkes, tek bir kullanıcı, belirli kullanıcılar veya AAD gruplarının üyesi olan kullanıcılar vb. olup olmadığını belirleme.
3. Birden çok uygulama bilgi noktası modu için, başlat menüsünde gösterılacak uygulamaları belirleyin. Her uygulama için [uygulamanın Uygulama Kullanıcı Modeli Kimliği (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) gerekir.
4. Bilgi noktası modunun çalışma zamanı sağlama paketleri HoloLens Mobile Cihaz Yönetimi (MDM) sunucusu aracılığıyla Cihaz Yönetimi olup olmadığını belirler.

## <a name="security-considerations"></a>Güvenlik konuları

Bilgi noktası modu bir güvenlik yöntemi olarak değil, kullanıcı oturum açma deneyiminde başlangıç deneyimini denetlemenin bir yöntemi olarak düşünülmelidir. Güvenlikle ilgili belirli ihtiyaçlar varsa bilgi noktası modu deneyimini aşağıda belirtilen seçeneklerle birleştirebilirsiniz:

- Bir Ayarlar bilgi noktası modunda gösterilecek şekilde yapılandırıldığında ve uygulamanın hangi sayfaların Ayarlar kontrol etmek istediğiniz zaman Sayfa Ayarlar [Görünürlüğü'ne bakın](settings-uri-list.md)
- Belirli uygulamalar için kamera, Bluetooth vb. gibi belirli donanım özelliklerine erişimi kontrol etmek istediğiniz durumlarda, HoloLens 2 - Windows İstemci Yönetimi tarafından desteklenen İlke [CSP'leri'ne bakın.](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2) Fikirler için Ortak [cihaz kısıtlamalarımızı](hololens-common-device-restrictions.md) gözden geçirebilirsiniz.
- Bilgi noktası modu, bir uygulamanın (bilgi noktası deneyiminin bir parçası olarak yapılandırılan) diğer uygulamaların başlatılmasını engellemez. HoloLens'da belirli uygulamaların /işlemlerin başlatılmasını tamamen engellemek için bkz. Windows Defender - [Azure'da HoloLens 2](/mem/intune/configuration/custom-profile-hololens) cihaz üzerinde Microsoft Intune Uygulama Denetimi kullanma

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Bilgi Noktası modu için önemli teknik konular HoloLens

Yalnızca çalışma zamanı sağlama paketlerini kullanmayı veya bilgi noktası yapılandırmalarını kendiniz oluşturmayı planlıyorsanız geçerlidir. Bilgi noktası modu yapılandırması XML tabanlı hiyerarşik bir yapı kullanır:

- Atanan erişim profili, bilgi noktası modunda başlat menüsünde hangi uygulamaların görüntülenmiyor olduğunu tanımlar. Daha sonra başvurulabilecek aynı XML yapısında birden çok profil tanımlayabilirsiniz.
- Atanan erişim yapılandırması, belirli bir kullanıcı veya AAD grubu ya da ziyaretçi gibi bir profilin profiline ve hedef kullanıcılarına başvurur. Kullanım senaryolarının karmaşıklığına bağlı olarak aynı XML yapısında birden çok yapılandırma tanımlayabilirsiniz (aşağıdaki desteklenen senaryolar bölümüne bakın).
- Daha fazla bilgi edinmek için [bkz. AssignedAccess CSP.](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Kimlik türüne göre bilgi noktası modu için desteklenen senaryolar

Senaryoyu [temel alan](hololens-kiosk-reference.md#kiosk-xml-code-samples) örnekler için başvuru bağlantılarına bakın ve kopyalamadan önce gerektiğinde güncelleştirin.

> [!NOTE]
> Bilgi noktası yapılandırması oluşturmak için XML'i yalnızca Intune'un kullanıcı arabirimini kullanmazsanız kullanın.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Yerel hesap veya MSA olarak oturum alan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları**  | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum alan her kullanıcı bilgi noktası deneyimine sahip olur. | [Birden çok uygulamanın Genel Atanan Erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Oturum alıkan belirli bir kullanıcı bilgi noktası deneyimine sahip olur.  | [Belirli bir kullanıcının adını belirterek tek veya birden çok uygulama tarafından atanan erişim profilini (gerektiğinde) yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Aşağıdaki desteklenen seçeneklere bakın.](#steps-in-configuring-kiosk-mode-for-hololens) | Tek uygulama bilgi noktası modu için, yalnızca yerel kullanıcı hesabı veya MSA hesabı HoloLens. <br> Birden çok uygulama bilgi noktası modu için, yalnızca MSA hesabı veya AAD hesabı HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD hesabı olarak oturum alan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları** | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum alan her kullanıcı bilgi noktası deneyimine sahip olur. | [Birden çok uygulamanın Genel Atanan Erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Oturum alan her kullanıcı, belirli kullanıcılar dışında bilgi noktası deneyimine sahip olur. | [Belirli kullanıcıları (cihaz sahibi olması gerekenler) dışlayarak birden çok uygulamanın Genel Atanan Erişim profilini yapılandırabilirsiniz.](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Her AAD kullanıcısı, o kullanıcıya özgü ayrı bilgi noktası deneyimine sahip olur. | [AAD hesap adını belirten her kullanıcı için atanmış erişim yapılandırmasını yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Farklı AAD gruplarında bulunan kullanıcılar yalnızca kendi gruplarına özel bilgi noktası moduyla deneyimler. | [İstenen her AAD grubu için atanan erişim yapılandırmasını yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Bir kullanıcı oturum HoloLens İnternet'e bağlandığında, bu kullanıcının bilgi noktası yapılandırmasının bulunduğu AAD grubunun üyesi olduğu bulunursa, kullanıcı bu AAD grubu için bilgi noktası deneyimine sahip olur. <br> • Kullanıcı oturum aken İnternet yoksa, kullanıcı hata [modu davranışıyla HoloLens deneyimiyle karşılar.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Kullanıcı oturum açtığında ve AAD grubu tabanlı bilgi noktası kullanılması gerektiğinde internet kullanılabilirliği garanti edilmediği takdirde, [AADGroupMembershipCacheValidityInDayspolicy kullanmayı göz önünde bulundurun](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • Oturum açma sırasında AAD gruplarıyla ilgili en iyi deneyim için [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) kullanma önerisi |
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
