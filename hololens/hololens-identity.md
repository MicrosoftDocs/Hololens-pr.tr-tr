---
title: HoloLens için Kullanıcı kimliğini yönetme ve oturum açma
description: HoloLens cihazlar için kullanıcı kimliği, çoklu kullanıcı desteği, güvenlik, kurumsal kimlik doğrulama ve oturum açma yönetimi hakkında bilgi edinin.
keywords: HoloLens, kullanıcı, hesap, AAD, Azure AD, adfs, microsoft hesabı, msa, kimlik bilgileri, başvuru
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e2c5c98eb62f9e8ec19306b2cb460004eb8ae8dd
ms.sourcegitcommit: 44d5fbee8aa0e2404137484edbeb4653437e79dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2021
ms.locfileid: "114991432"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens için Kullanıcı kimliğini yönetme ve oturum açma

> [!NOTE]
> Bu makale, BT profesyonelleri ve teknoloji meraklıları için teknik bir başvurudur. yönergeleri ayarlamak HoloLens arıyorsanız, "[HoloLens ayarlama (1. genel)](hololens1-start.md)" veya "[HoloLens 2](hololens2-start.md)' yi ayarlama" konusunu okuyun.

diğer Windows cihazları gibi HoloLens her zaman bir kullanıcı bağlamı altında çalışır. Her zaman bir kullanıcı kimliği vardır. HoloLens kimliği, diğer Windows cihazlarıyla neredeyse aynı şekilde davranır. bu makale, HoloLens kimlik için ayrıntılı bir başvurudur ve HoloLens diğer Windows cihazlarından farklı bir şekilde farklılık gösterir.

HoloLens çeşitli kullanıcı kimliklerini destekler. Oturum açmak için bir veya daha fazla kullanıcı hesabı kullanabilirsiniz. İşte HoloLens kimlik türleri ve kimlik doğrulama seçeneklerine genel bakış:

| Kimlik türü | Cihaz başına hesaplar | Kimlik doğrulaması seçenekleri |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure Web kimlik bilgileri sağlayıcısı</li><li>Azure Authenticator uygulaması</li><li>biyometrik (ıris) &ndash; HoloLens 2<sup></sup> </li><li>FIDO2 güvenlik anahtarı</li><li>&ndash;HoloLens (1. gen) için isteğe bağlı sabitle, HoloLens 2 için gereklidir</li><li>Parola</li></ul> |
| [Microsoft hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>biyometrik (ıris) &ndash; yalnızca 2 HoloLens</li><li>&ndash;HoloLens (1. gen) için isteğe bağlı sabitle, HoloLens 2 için gereklidir</li><li>Parola</li></ul> |
| [Yerel hesap](/windows/security/identity-protection/access-control/local-accounts) | 1 | Parola |

Buluta bağlı hesaplar (Azure AD ve MSA), Azure hizmetleri 'ni kullanabileceğinden daha fazla özellik sunmaktadır.  
> [!IMPORTANT]
> 1-Azure AD Premium cihazda oturum açmak için gerekli değildir. Ancak, otomatik kayıt ve Autopilot gibi, düşük dokunmalı bir bulut tabanlı dağıtımın diğer özellikleri için gereklidir.

> [!NOTE]
> 2-HoloLens 2 cihaz en fazla 64 Azure AD hesabını destekleyebileceği için, bu hesapların yalnızca 31 ' de ıris kimlik doğrulamasında kayıt olabilir. bu, [iş Windows Hello yönelik diğer biyometrik kimlik doğrulama seçenekleriyle](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)hizalanır.

## <a name="setting-up-users"></a>Kullanıcıları ayarlama

HoloLens yeni bir Kullanıcı kurmanın iki yolu vardır. en yaygın yöntem HoloLens kullanıma hazır deneyimidir (OOBE). Azure Active Directory kullanıyorsanız, diğer kullanıcılar, Azure AD kimlik bilgilerini kullanarak OOBE 'den sonra [oturum açabilirler](#setting-up-multi-user-support-azure-ad-only) . ilk olarak, OOBE sırasında bir MSA veya yerel hesapla ayarlanmış HoloLens cihazlar birden çok kullanıcıyı desteklemezler. bkz. HoloLens ayarlama [(1. genel)](hololens1-start.md) veya [HoloLens 2](hololens2-start.md).

HoloLens oturum açmak için bir kuruluş veya kuruluş hesabı kullanıyorsanız, HoloLens kuruluşun bt altyapısına kaydeder. Bu kayıt, BT yöneticinizin, mobil cihaz yönetimi 'ni (MDM) HoloLens Grup ilkeleri gönderecek şekilde yapılandırmasına olanak sağlar.

diğer cihazlarda Windows gibi, kurulum sırasında oturum açmak cihazda bir kullanıcı profili oluşturur. Kullanıcı profili, uygulamaları ve verileri depolar. aynı hesap, Windows account Manager apı 'lerini kullanarak kenar veya Microsoft Store gibi uygulamalarda çoklu oturum açma olanağı da sağlar. 

varsayılan olarak, diğer Windows 10 cihazlarda olduğu gibi, HoloLens yeniden başlatıldığında veya bekleme modundan devam ettiğinde yeniden oturum açmanız gerekir. bu davranışı değiştirmek için Ayarlar uygulamasını kullanabilirsiniz veya davranış grup ilkesi tarafından denetlenebilir.

### <a name="linked-accounts"></a>Bağlı hesaplar

Windows masaüstü sürümünde olduğu gibi, HoloLens hesabınıza ek web hesabı kimlik bilgileri bağlayabilirsiniz. Bu tür bağlama, kaynaklara veya uygulamalara (mağaza gibi) veya kişisel ve iş kaynaklarına erişimi birleştirmeye daha kolay bir şekilde erişmenizi sağlar. Cihaza bir hesabı bağladığınızda, her uygulamada tek tek oturum açmanıza gerek kalmaması için cihazı uygulamalara kullanma izni verebilirsiniz.

Bağlantı hesapları, cihazda oluşturulan görüntü veya indirme gibi kullanıcı verilerini ayıramaz.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Çoklu Kullanıcı desteğini ayarlama (yalnızca Azure AD)

HoloLens, aynı Azure AD kiracısından birden çok kullanıcıyı destekler. Bu özelliği kullanmak için, cihazı kurmak üzere kuruluşunuza ait bir hesabı kullanmanız gerekir. Daha sonra, aynı kiracının diğer kullanıcıları, oturum açma ekranından veya Başlat panelindeki Kullanıcı kutucuğuna dokunarak cihazda oturum açabilir. Tek seferde yalnızca bir Kullanıcı oturum açabilir. bir kullanıcı oturum açtığında, önceki kullanıcı oturumunu HoloLens. 

>[!IMPORTANT]
> Cihazdaki ilk Kullanıcı cihaz sahibi olarak kabul edilir. Bu durumda, Azure AD katılımı söz konusu olduğunda [cihaz sahipleri hakkında daha fazla bilgi edinebilirsiniz](security-adminless-os.md#device-owner).

Tüm kullanıcılar cihazda yüklü olan uygulamaları kullanabilir. Ancak, her bir kullanıcının kendi uygulama verileri ve tercihleri vardır. Bir uygulamayı cihazdan kaldırma, tüm kullanıcılar için kaldırır.  

Azure AD hesapları ile ayarlanan cihazlar cihazda Microsoft hesabıyla oturum açmaya izin vermez. Kullanılan tüm sonraki hesaplar, cihazla aynı kiracıdan Azure AD hesapları olmalıdır. Bunu destekleyen [uygulamalar için bir Microsoft hesabı kullanarak oturum](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) açabilirsiniz (örneğin, Microsoft Store). Azure AD hesaplarını cihazda oturum açmak için Microsoft hesapları kullanmaya geçiş yapmak için, [cihazı yeniden Flash](hololens-recovery.md#clean-reflash-the-device)etmeniz gerekir.

> [!NOTE]
> **HoloLens (1. gen)** , [Windows Holographic for Business](hololens-upgrade-enterprise.md)kapsamında [Windows 10 nisan 2018 güncelleştirmesinde](/windows/mixed-reality/release-notes-april-2018) birden çok Azure AD kullanıcısı desteklemeye başladı.

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok Kullanıcı listelendi

Daha önce oturum açma ekranında yalnızca en son oturum açan kullanıcının yanı sıra ' diğer Kullanıcı ' giriş noktası gösteriliyordu. Cihazda birden çok kullanıcı oturum açmışsa, bu yeterli olmayan müşteri geri bildirimi aldık. Yine de bunların Kullanıcı adını yeniden yazması gerekiyordu.

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)' de tanıtılan, pın girişi alanının sağında bulunan **başka bir kullanıcı** seçerken oturum açma ekranında, daha önce cihazda oturum açan birden çok kullanıcı görüntülenir. bu, kullanıcıların kullanıcı profillerini seçmesini ve ardından Windows Hello kimlik bilgilerini kullanarak oturum açmasını sağlar. Bu diğer kullanıcılar sayfasından, **Hesap Ekle** düğmesi aracılığıyla cihaza yeni bir kullanıcı da eklenebilir.

Diğer kullanıcılar menüsünde, diğer kullanıcılar düğmesi cihazda oturum açan son kullanıcıyı görüntüler. Bu Kullanıcı için oturum açma ekranına geri dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı](./images/multiusers2.jpg)

## <a name="removing-users"></a>Kullanıcılar kaldırılıyor

**Ayarlar** hesaplara giderek, bir kullanıcıyı cihazdan kaldırabilirsiniz  >    >  . Bu eylem Ayrıca, söz konusu kullanıcının tüm uygulama verilerini cihazdan kaldırarak da boş alan geri kazanır.  

## <a name="using-single-sign-on-within-an-app"></a>Uygulama içinde çoklu oturum açma kullanma

uygulama geliştiricisi olarak, diğer Windows cihazlarda olduğu gibi, [Windows Account Manager apı 'lerini](/uwp/api/Windows.Security.Authentication.Web.Core)kullanarak HoloLens bağlantılı kimliklerden yararlanabilirsiniz. bu apı 'ler için bazı kod örnekleri GitHub kullanılabilir: [Web hesabı yönetim örneği](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Uygulama bir kimlik doğrulama belirteci istediğinde, hesap bilgileri, iki öğeli kimlik doğrulama vb. için Kullanıcı onayı isteme gibi olabilecek hesap kesintileri ele alınmalıdır.

Uygulamanız daha önce bağlanmayan belirli bir hesap türü gerektiriyorsa, uygulamanız kullanıcıdan bir tane eklemesini isteyebilir. Bu istek, uygulamanızın kalıcı bir alt öğesi olarak başlatılacak hesap ayarları bölmesini tetikler. 2B uygulamalar için bu pencere, doğrudan uygulamanızın merkezine göre oluşturulur. Unity uygulamaları için bu istek, Kullanıcı alt pencereyi oluşturmak için holographic uygulamanızın dışına çıkar. Bu bölmedeki komutları ve eylemleri özelleştirme hakkında daha fazla bilgi için bkz. [Webaccountcommand sınıfı](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise ve diğer kimlik doğrulaması

uygulamanız NTLM, temel veya Kerberos gibi diğer kimlik doğrulama türlerini kullanıyorsa, kullanıcının kimlik bilgilerini toplamak, işlemek ve depolamak için [Windows kimlik bilgileri kullanıcı arabirimini](/uwp/api/Windows.Security.Credentials.UI) kullanabilirsiniz. Bu kimlik bilgilerini toplamaya yönelik kullanıcı deneyimi, diğer bulut odaklı hesap kesintileri için çok benzerdir ve 2B uygulamanızın üzerinde bir alt uygulama olarak görünür veya Kullanıcı arabirimini göstermek için bir Unity uygulamasını kısaca askıya alır.

## <a name="deprecated-apis"></a>Kullanım dışı API 'Ler

HoloLens geliştirmenin, masaüstü için geliştirmekten farklı bir şekilde, [onlineidavıd cator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) apı 'sinin tam olarak desteklenmesinin bir yoludur. Birincil hesap iyi durumda olduğunda API bir belirteç döndürse de, bu makalede açıklananlar gibi kesintiler Kullanıcı için herhangi bir kullanıcı ARABIRIMI görüntülemez ve hesabın kimliğini doğru şekilde doğrulayamamaktadır.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens (1. Gen) üzerinde desteklenen iş Windows Hello?

Windows Hello for Business (oturum açmak için pın kullanılmasını destekler) HoloLens (1. genel) için desteklenir. HoloLens üzerinde Windows Hello iş pın 'inin oturum açmasını sağlamak için:

1. HoloLens cihazın [MDM tarafından yönetilmesi](hololens-enroll-mdm.md)gerekir.
1. cihazda iş için Windows Hello etkinleştirmeniz gerekir. ([Microsoft Intune yönelik yönergelere bakın.](/intune/windows-hello))
1. HoloLens, kullanıcı daha sonra   >  pın ayarlamak için pın ekle Ayarlar **oturum açma seçeneklerini** kullanabilir  >   .

> [!NOTE]
> bir Microsoft hesabı kullanarak oturum açan kullanıcılar,   >  pın ekle Ayarlar **oturum açma seçeneklerinde** pın 'i de ayarlayabilir  >  . bu pın, [iş Windows Hello](/windows/security/identity-protection/hello-for-business/hello-overview)yerine [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)ile ilişkilidir.

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>ıris biyometrik kimlik doğrulaması HoloLens 2 ' ye nasıl uygulanır?

HoloLens 2 ıris kimlik doğrulamasını destekler. ıris Windows Hello teknolojisine dayalıdır ve hem Azure Active Directory hem de Microsoft hesapları tarafından kullanılmak üzere desteklenir. ıris diğer Windows Hello teknolojileriyle aynı şekilde uygulanır ve [biyometri güvenliğine en fazla 1/100 kb](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)erişir.

daha fazla bilgi için bkz. [Windows Hello için biyometrik gereksinimler ve özellikler](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) ve [Windows Hello iş](/windows/security/identity-protection/hello-for-business/hello-identity-verification)hakkında daha fazla bilgi edinin. 

### <a name="where-is-iris-biometric-information-stored"></a>Iris biyometrik bilgileri nerede depolanır?

ıris biyometrik bilgileri her bir HoloLens [Windows Hello belirtimleri](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored)temelinde yerel olarak depolanır. Bu, paylaşılmaz ve iki şifreleme katmanı tarafından korunur. Bir HoloLens yönetici hesabı bulunmadığından, yönetici bile diğer kullanıcılar tarafından erişilemez.

### <a name="do-i-have-to-use-iris-authentication"></a>Iris kimlik doğrulaması 'nı kullanmam gerekir mi?
Hayır, kurulum sırasında bu adımı atlayabilirsiniz. 

![Kurulum Iris](./images/setup-iris.png)

HoloLens 2, FIDO2 güvenlik anahtarları dahil olmak üzere kimlik doğrulaması için birçok farklı seçenek sağlar.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Iris bilgileri HoloLens kaldırılabilir mi?
evet, Ayarlar ' de el ile kaldırabilirsiniz.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hesap türü, oturum açma davranışını nasıl etkiler?

Oturum açma için ilkeler uygularsanız, ilke her zaman uygulanır. Oturum açma için herhangi bir ilke uygulanmadığından, bunlar her hesap türü için varsayılan davranışlardır:

- **Azure AD**: kimlik doğrulamasını varsayılan olarak sorar ve **Ayarlar** tarafından, kimlik doğrulaması için artık sorulmayacak şekilde yapılandırılabilir.
- **Microsoft hesabı**: kilit davranışı otomatik kilit açmaya izin vermek için farklıdır, ancak yeniden başlatma sırasında oturum açma kimlik doğrulaması hala gereklidir.
- **yerel hesap**: **Ayarlar** ' de yapılandırılabilir değil, her zaman bir parola biçiminde kimlik doğrulaması ister

> [!NOTE]
> Etkinlik dışı zamanlayıcılar Şu anda desteklenmiyor. Bu, **AllowIdleReturnWithoutPassword** ilkesinin yalnızca cihaz bekleme moduna geçtiğinde dikkate alındığı anlamına gelir.

## <a name="additional-resources"></a>Ek kaynaklar

[Windows 10 güvenlik ve kimlik belgelerinde](/windows/security/identity-protection/)kullanıcı kimlik koruması ve kimlik doğrulaması hakkında daha fazla bilgi edinin.

[Azure hibrit kimlik belgelerinin](/azure/active-directory/hybrid/)kapsamlı karma kimlik altyapısını ayarlama hakkında daha fazla bilgi edinin.
