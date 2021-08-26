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
ms.openlocfilehash: daab30a8ea5200ca145b6b0234b8bd060b8cec5f
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859229"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Bilgi HoloLens bilgi noktası olarak ayarlama

## <a name="what-is-kiosk-mode"></a>Bilgi noktası modu nedir?

Bilgi noktası modu, bir kullanıcı oturum aken başlat menüsünde hangi uygulamaların gösterildiğini kontrol HoloLens. Desteklenen 2 senaryo vardır:

1. **Tek uygulama bilgi noktası** modu – Başlat menüsü görüntülenmez ve kullanıcı oturum açsa tek bir uygulama otomatik olarak başlatılır. <br> *Örnek:* Yalnızca Dynamics 365 Kılavuzları uygulamasını çalıştıran bir cihaz.
2. **Birden çok uygulama bilgi** noktası Başlat menüsü – yalnızca bir kullanıcı oturum aken bilgi noktası yapılandırmasında belirtilen uygulamaları gösterir. İsterseniz bir uygulamanın otomatik olarak başlatılması seçilebilir. <br> *Örnek olarak:* Başlat menüsünde yalnızca Mağaza uygulamasını, Geri Bildirim Merkezi ve Ayarlar gösteren bir cihaz.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Kullanıcı oturum aken bilgi noktası modu deneyiminin açıklaması

Aşağıdaki tablo, farklı bilgi noktası modlarında özellik özelliklerini listeler.

| &nbsp; |Başlat menüsü |Hızlı Eylemler menüsü |Kamera ve video |Miracast |Cortana |Yerleşik sesli komutlar |
| --- | --- | --- | --- | --- | --- | --- |
|Tek uygulamalı bilgi noktası |Devre dışı |Devre dışı |Devre dışı |Devre dışı   |Devre dışı |Etkin* |
|Çoklu uygulama bilgi noktası |Etkin |Etkin*  |Kullanılabilir*  |Kullanılabilir* |Kullanılabilir*   |Etkin*  |

Devre dışı bırakılmış özellikleri etkinleştirme veya ses komutlarının devre dışı bırakılmış özelliklerle ve Cortana etkileşim kurma hakkında daha fazla bilgi HoloLens bkz. uygulamalar için [AUMID'ler.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Bilgi noktası modunu yapılandırmadan önce dikkat edilmesi gereken önemli genel noktalar

1. Ortamınız içinde Hololens'te oturum açmanın ne tür bir kullanıcı hesabı olduğunu belirleme : HoloLens (AAD) Azure Active Directory, Microsoft Hesapları (MSA) ve Yerel hesapları destekler. Ayrıca, geçici olarak oluşturulan konuk/ziyaretçi adı verilen hesaplar da de desteklemektedir (yalnızca AAD'ye katılma cihazları için). Daha fazla bilgi [için daha fazla bilgi için kullanıcı kimliğini yönetme ve HoloLens.](hololens-identity.md)
2. Bilgi noktası modu deneyiminin hedeflerini belirleme : bunun herkes, tek bir kullanıcı, belirli kullanıcılar veya AAD gruplarının üyesi olan kullanıcılar vb. olup olmadığını belirleme.
3. Birden çok uygulama bilgi noktası modu için, başlat menüsünde gösterılacak uygulamaları belirleyin. Her uygulama için [uygulamanın Uygulama Kullanıcı Modeli Kimliği (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) gerekir.
4. Bilgi noktası modunun çalışma zamanı sağlama paketleri HoloLens Mobile Cihaz Yönetimi (MDM) sunucusu aracılığıyla Cihaz Yönetimi olup olmadığını belirler.

## <a name="security-considerations"></a>Güvenlik konuları

Bilgi noktası modu bir güvenlik yöntemi olarak değil, kullanıcı oturum açma deneyiminde başlangıç deneyimini denetlemenin bir yöntemi olarak düşünülmelidir. Güvenlikle ilgili belirli ihtiyaçlar varsa bilgi noktası modu deneyimini aşağıda belirtilen seçeneklerle birleştirebilirsiniz:

- Bir Ayarlar bilgi noktası modunda gösterilecek şekilde yapılandırıldığında ve Ayarlar uygulamasında hangi sayfaların göster Ayarlar [bakın](settings-uri-list.md)
- Belirli uygulamalar için kamera, Bluetooth vb. gibi belirli donanım özelliklerine erişimi kontrol etmek istediğiniz durumlarda, HoloLens 2 - Windows İstemci Yönetimi tarafından desteklenen İlke [CSP'leri'ne bakın.](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2) Fikirler için Ortak [cihaz kısıtlamalarımızı](hololens-common-device-restrictions.md) gözden geçirebilirsiniz.
- Bilgi noktası modu, bir uygulamanın (bilgi noktası deneyiminin bir parçası olarak yapılandırılan) diğer uygulamaların başlatılmasını engellemez. HoloLens'da belirli uygulamaların /işlemlerin başlatılmasını tamamen engellemek için bkz. Microsoft Intune - Azure'da HoloLens 2 cihaz üzerinde Windows Defender Uygulama [Denetimi'Microsoft Intune kullanma](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Bilgi Noktası modu için önemli teknik konular HoloLens

Yalnızca çalışma zamanı sağlama paketlerini kullanmayı veya bilgi noktası yapılandırmalarını kendiniz oluşturmayı planlıyorsanız geçerlidir. Bilgi noktası modu yapılandırması XML tabanlı hiyerarşik bir yapı kullanır:

- Atanan erişim profili, bilgi noktası modunda başlat menüsünde hangi uygulamaların görüntülenmiyor olduğunu tanımlar. Daha sonra başvurulabilecek aynı XML yapısında birden çok profil tanımlayabilirsiniz.
- Atanan erişim yapılandırması, belirli bir kullanıcı veya AAD grubu ya da ziyaretçi gibi bir profilin profiline ve hedef kullanıcılarına başvurur. Kullanım senaryolarının karmaşıklığına bağlı olarak aynı XML yapısında birden çok yapılandırma tanımlayabilirsiniz (aşağıdaki desteklenen senaryolar bölümüne bakın).
- Daha fazla bilgi edinmek için [bkz. AssignedAccess CSP.](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Kimlik türüne göre bilgi noktası modu için desteklenen senaryolar

> [!NOTE]
> Bilgi noktası yapılandırması oluşturmak için XML'i yalnızca Intune'un kullanıcı arabirimini kullanmazsanız kullanın.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Yerel hesap veya MSA olarak oturum alan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları**  | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum alan her kullanıcı bilgi noktası deneyimine sahip olur. | [Birden çok uygulamanın Genel Atanan Erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Oturum alıkan belirli bir kullanıcı bilgi noktası deneyimine sahip olur.  | [Belirli bir kullanıcının adını belirterek tek veya birden çok uygulama tarafından atanan erişim profilini (gerektiğinde) yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Aşağıdaki desteklenen seçeneklere bakın.](#steps-in-configuring-kiosk-mode-for-hololens) | Tek uygulama bilgi noktası modu için, yalnızca yerel kullanıcı hesabı veya MSA hesabı HoloLens. <br> Birden çok uygulama bilgi noktası modu için yalnızca MSA hesabı veya AAD hesabı HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>AAD hesabı olarak oturum alan kullanıcılar için

| **İstenen bilgi noktası deneyimi** | **Önerilen bilgi noktası yapılandırması** | **Yapılandırma yolları** | **Açıklamalar** |
| --- | --- | --- | --- |
| Oturum alan her kullanıcı bilgi noktası deneyimine sahip olur. | [Birden çok uygulamanın Genel Atanan Erişim profilini yapılandırma](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Oturum alan her kullanıcı, belirli kullanıcılar dışında bilgi noktası deneyimine sahip olur. | [Belirli kullanıcıları (cihaz sahibi olması gerekenler) dışlayarak birden çok uygulamanın Genel Atanan Erişim profilini yapılandırabilirsiniz.](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Genel atanan erişim için [20H2 ve daha yeni derlemeler gerekir](hololens-release-notes.md#windows-holographic-version-20h2) |
| Her AAD kullanıcısı, o kullanıcıya özgü ayrı bilgi noktası deneyimine sahip olur. | [AAD hesap adını belirten her kullanıcı için atanmış erişim yapılandırmasını yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Farklı AAD gruplarında bulunan kullanıcılar yalnızca kendi gruplarına özel bilgi noktası moduyla deneyimler. | [İstenen her AAD grubu için atanan erişim yapılandırmasını yapılandırma.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Bir kullanıcı oturum HoloLens İnternet'e bağlandığında, bu kullanıcının bilgi noktası yapılandırmasının bulunduğu AAD grubunun üyesi olduğu bulunursa, kullanıcı bu AAD grubu için bilgi noktası deneyimine sahip olur. <br> • Kullanıcı oturum aken İnternet yoksa, kullanıcı hata [modu davranışıyla HoloLens deneyimletir.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Kullanıcının oturum aça ve AAD grubu tabanlı bilgi noktası kullanması gerekirken İnternet kullanılabilirliği garanti [edilemezse, AADGroupMembershipCacheValidityInDayspolicy kullanmayı göz önünde bulundurabilirsiniz.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) |
| Geçici amaçlar için HoloLens kullanıcılar bilgi noktası deneyimi elde edin. | [Ziyaretçiler için atanan erişim yapılandırmasını yapılandırma](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Çalışma zamanı sağlama - Tek uygulama](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Geçici kullanıcı hesabı, oturum HoloLens tarafından otomatik olarak oluşturulur ve geçici kullanıcı oturumları kapanırsa kaldırılır. <br> • Ziyaretçi otomatik oturum [açma ilkesi etkinleştirmeyi düşünün.](#how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Bilgi noktası modunu yapılandırma adımları HoloLens

Bilgi noktası yapılandırmaları aşağıdaki yollarla oluşturulabilir ve uygulanabilir:

1. MDM sunucusunun kullanıcı arabirimi ile, örneğin Intune'un bilgi noktası şablonları veya özel OMA-URI yapılandırmaları , daha sonra bu yapılandırmalara uzaktan HoloLens.
2. Çalışma zamanı sağlama paketleriyle, bu paketler daha sonra doğrudan HoloLens.

Yapılandırmak için aşağıdaki yöntemlerden birini kullanabilirsiniz. Kullanmak istediğiniz işlemle eşleşen sekmeyi seçin.

1. [Microsoft Intune uygulama bilgi noktası şablonu](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune uygulama bilgi noktası şablonu oluşturma](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune şablon oluşturma](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Çalışma zamanı sağlama - Çoklu uygulama](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Çalışma zamanı sağlama - Tek uygulama](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Sık Sorulan Sorular

### <a name="how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience"></a>Ziyaretçi hesapları bilgi noktası deneyimine otomatik olarak nasıl oturum açabilirsiniz?

[Holographic,Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha sonra derlemelerde:

- Hem AAD hem de ADD olmayan yapılandırmalar, ziyaretçi hesaplarının Bilgi Noktası modları için otomatik olarak etkinleştirilmelerini destekler.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Bilgi noktası deneyimi Hololens'te (1. nesil) destek sunuyor mu?

Bilgi noktası modu yalnızca cihazın cihaza bağlı Windows Holographic for Business. 2 HoloLens tüm cihazlar Windows Holographic for Business ve başka sürüm yoktur. Her HoloLens 2 cihaz, Bilgi Noktası modunu kutudan çıkararak çalıştırabilirsiniz.

HoloLens (1. nesil) cihazların hem işletim sistemi derlemesi hem de işletim sistemi sürümü açısından yükseltilleri gerekir. Bir sürümü (1. nesil) HoloLens güncelleştirme hakkında daha fazla bilgi [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edinebilirsiniz. Bir HoloLens (1. nesil) cihazı bilgi noktası modunu kullanmak üzere güncelleştirmek için öncelikle cihazın Windows 10, sürüm 1803 veya sonraki bir sürümde çalıştırıla olduğundan emin olun. HoloLens (1. nesil) cihazınızı varsayılan derlemeye kurtarmak için Windows Cihaz Kurtarma Aracı'nı kullandıysanız veya en son güncelleştirmeleri yüklemişsanız, cihazınız yapılandırmaya hazırdır.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Üretim dışı ortamlarda bilgi noktası yapılandırmak için cihaz portalını kullanma

[HoloLens'i kullanmak için Windows Cihaz Portalı.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) Bu Cihaz Portalı, bilgisayarınızdan bir web HoloLens bağlanabilirsiniz.

 > [!CAUTION]
 > Bu HoloLens için ayar Cihaz Portalı cihazda Geliştirici Modu'Cihaz Portalı etkinleştirmeniz gerekir. Uygulama yüklemesi olan bir Windows Holographic for Business Geliştirici Modu, uygulamaları yan yüklemeye olanak sağlar. Ancak bu ayar, bir kullanıcının uygulama tarafından sertifikalandırılmış uygulamaları yükleme riski Microsoft Store. Yöneticiler, İlke CSP'sinde **ApplicationManagement/AllowDeveloper Kilit** Açma ayarını kullanarak Geliştirici Modunu [etkinleştirme olanağını engelleyebilir.](/windows/client-management/mdm/policy-configuration-service-provider) [Geliştirici Modu hakkında daha fazla bilgi edinebilirsiniz.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Bilgi Noktası Modu, REST API Cihaz Portalı tek bir gerekli sorgu dizesi parametresi ("kioskModeEnabled" ve "true" veya "false" değeriyle) ve isteğe bağlı bir parametre ("paket adı değerine sahip startupApp" ) ile /api/holographic/kioskmode/settings'a post işlemi gerçekleştirilebilir. Uygulamanın yalnızca Cihaz Portalı amaçlı olduğunu ve geliştirici olmayan cihazlarda etkinleştirilmemiş olması gerektiğini unutmayın. Bu REST API gelecek güncelleştirmelerde/yayınlarda değişebilir.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Sorun - Bilgi noktası modunda başlat menüsünde hiçbir uygulama gösterilmez mi?

**Belirtiler**

Bilgi noktası modu uygulama sırasında hatalarla karşılaşıldıktan sonra aşağıdaki davranış görüntülenir:

- Holographic Windows den önce sürüm 20H2 - HoloLens, sanal Başlat menüsü.
- Windows Holographic, sürüm 20H2 : Bir cihazda hem genel erişim hem de AAD grup üyesi tarafından atanan erişimin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliği belirlenmezse kullanıcı "başlat menüsünde hiçbir şey gösterilmez" menüsünü görebilir.

    ![Bilgi noktası modu artık başarısız olduğunda hangi modun göründüğünün resmi.](images/hololens-kiosk-failure-behavior.png )

- [Holographic Windows sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)başlayarak Bilgi Noktası modu, boş bir başlangıç menüsü göstermeden önce Genel Atanan Erişim'i okur. Bilgi noktası deneyimi, AAD grup bilgi noktası modunda hatalar olması durumunda genel bilgi noktası yapılandırmasına (varsa) geri döner.

**Sorun giderme adımları**

- Uygulamanın AUMID'lerinin doğru şekilde belirtilmiş olduğunu ve sürümler içere olmadığını doğrulayın. Örnekler için [HoloLens gelen kutusu uygulamaları için AUMID'ler'e](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) bakın.
- Uygulamanın bu kullanıcı için cihazda yüklü olduğundan emin olun.
- Bilgi noktası yapılandırması AAD gruplarını temel aldısa lütfen AAD kullanıcısı oturum aken İnternet bağlantısının mevcut olduğundan emin olun. İsterseniz, [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) ilkesi yapılandırarak bu ilkenin internet olmadan da çalışmasına izin veresiniz.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Sorun - Bilgi noktası moduyla paket yapılamadı

**Belirtiler**

Aşağıdakine benzer bir iletişim kutusu gösterilir.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Sorun giderme adımları**

1. Yukarıdaki iletişim kutusunda gösterildiği gibi hiper bağlantıya tıklayın.
1. ICD.log dosyasını bir metin düzenleyicisinde açın ve içeriğinin hatayı belirt olması gerekir.

> [!NOTE]
> Birkaç deneme yaptıysanız, günlükte zaman damgalarını kontrol edin. Bu, yalnızca geçerli sorunları denetlemeye yardımcı olur.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Sorun – Sağlama paketi başarıyla oluşturuldu ama uygulanamadı.

**Belirtiler**

Hololens'e sağlama paketi uygularken hata gösteriliyor

**Sorun giderme adımları**

1. Çalışma zamanı sağlama paketi için Windows Yapılandırma Tasarımcısı projesinin bulunduğu klasöre gidin.
1. ICD.log dosyasını açın ve sağlama paketini hazırlarken günlükte hata olmadığını denetleyin. Derleme sırasında bazı hatalar gösternsin ama ICD.log dosyasına yine de kaydedilir

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Sorun – AAD grubuna birden çok uygulama tarafından atanan erişim çalışmıyor

**Belirtiler**

AAD kullanıcı oturum açmada cihaz bilgi noktası moduna giri

**Sorun giderme adımları**

- Atanan Erişim yapılandırma XML'inde, oturum açan kullanıcının üyesi olduğu AAD grubunun GUID'inin AAD kullanıcı guid'inin değil, üyesi olduğunu onaylayın.
- Intune portalında AAD kullanıcılarının hedeflenen AAD grubunun üyesi olarak gösterildiğini onaylayın.
