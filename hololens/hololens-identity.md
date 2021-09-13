---
title: Kimlik bilgileri için kullanıcı kimliğini ve oturum HoloLens
description: Kullanıcı kimliğini, çok kullanıcılı desteği, güvenliği, kurumsal kimlik doğrulamasını yönetmeyi ve cihazlarınızı yönetmek için HoloLens öğrenin.
keywords: HoloLens, kullanıcı, hesap, AAD, Azure AD, adfs, microsoft hesabı, msa, kimlik bilgileri, başvuru
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033259"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Kimlik bilgileri için kullanıcı kimliğini ve oturum HoloLens

> [!NOTE]
> Bu makale, IT Uzmanları ve teknoloji meraklıları için teknik bir başvuru sağlar. Daha fazla bilgi HoloLens, " HoloLens[(1. nesil)](hololens1-start.md)" veya "[2.](hololens2-start.md)Nesil'inizi ayarlama" HoloLens okuyun.

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>HoloLens 2 için kullanıcı kimliğini ayarlama hakkında HoloLens.

Diğer Windows cihazlar gibi, HoloLens her zaman bir kullanıcı bağlamında çalışır. Her zaman bir kullanıcı kimliği vardır. HoloLens bir cihazla neredeyse aynı şekilde Windows 10 davranır. Kurulum sırasında oturum açma, uygulama ve veri HoloLens bir kullanıcı profili oluşturur. Aynı hesap, Microsoft Account Manager API'lerini kullanarak Edge veya Dynamics 365 Remote Assist gibi uygulamalar için çoklu Windows sağlar. 

HoloLens çeşitli kullanıcı kimliklerini destekler. Bu üç hesap türlerinden birini seçebilirsiniz, ancak cihazları yönetmek için en iyisi azure AD'yi kesinlikle öneririz. Yalnızca Azure AD hesapları birden çok kullanıcıyı destekler. 

| Kimlik türü | Cihaz başına hesap sayısı | Kimlik doğrulaması seçenekleri |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure web kimlik bilgileri sağlayıcısı</li><li>Azure Authenticator Uygulaması</li><li>Biyometri (Iris) &ndash; HoloLens 2 yalnızca<sup>2</sup> </li><li>FIDO2 Güvenlik anahtarı</li><li>PIN &ndash; İsteğe bağlı HoloLens (1. nesil), 2. nesil için HoloLens gerekir</li><li>Parola</li></ul> |
| [Microsoft Hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biyometri (Iris) &ndash; HoloLens 2</li><li>PIN &ndash; İsteğe bağlı HoloLens (1. nesil), 2. nesil için HoloLens gerekir</li><li>Parola</li></ul> |
| [Yerel hesap](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Parola |

Buluta bağlı hesaplar (Azure AD ve MSA), Azure hizmetlerini kullanabileceği için daha fazla özellik sunar.  
> [!IMPORTANT]
> 1 - Azure AD Premium oturum açması için gerekli değildir. Ancak, Auto-enrollment ve Autopilot gibi düşük temaslı bulut tabanlı dağıtımın diğer özellikleri için gereklidir.

> [!NOTE]
> 2 - HoloLens 2 cihazı en fazla 64 Azure AD hesabını destekleyene kadar, bu hesaplardan yalnızca 31'i Iris Kimlik Doğrulaması'ya kaydolabilirsiniz. Bu, İş Için İş için [diğer Biyometrik kimlik doğrulama Windows Hello ile hizalanır.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 - Bir yerel hesap yalnızca [OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)sırasında bir sağlama paketi aracılığıyla bir cihazda ayarlanıyor olabilir; bu ayar uygulamasına daha sonra ek olamaz. Zaten ayarlanmış bir cihazda yerel bir hesap kullanmak için, cihazı ters eğik [çizgiyle sıfırlamanız gerekir.](hololens-recovery.md)

## <a name="setting-up-users"></a>Kullanıcıları ayarlama

Yeni bir kullanıcı ayarlamak için iki yol vardır HoloLens. En yaygın yol, HoloLens deneyimi (OOBE) sırasındadır. Bu Azure Active Directory, diğer [kullanıcılar](#setting-up-multi-user-support-azure-ad-only) Azure AD kimlik bilgilerini kullanarak OOBE'den sonra oturum açabilirsiniz. HoloLens OOBE sırasında bir MSA veya yerel hesap ile ayarlanmış tüm cihazlar birden çok kullanıcı desteklemez. Bkz. HoloLens [(1. nesil) veya](hololens1-start.md) [2 HoloLens ayarlama.](hololens2-start.md)

Bir kuruluş veya kuruluş hesabı kullanarak HoloLens HoloLens kuruluşun IT altyapısına kaydolabilirsiniz. Bu kayıt, IT Yöneticinizin mobil uygulamanıza grup Cihaz Yönetimi (MDM) HoloLens.

Diğer Windows gibi, kurulum sırasında oturum açma işlemi cihazda bir kullanıcı profili oluşturur. Kullanıcı profili, uygulamaları ve verileri depolar. Aynı hesap, Microsoft Account Manager API'lerini kullanarak Edge veya Microsoft Store uygulamalar için Windows oturum açma da sağlar.

Varsayılan olarak, diğer Windows 10 cihazlarda olduğu gibi, yeniden başlatıldığında veya beklemeden HoloLens yeniden oturum açmanız gerekir. Ayarlar uygulamasını kullanarak bu davranışı değiştirebilirsiniz veya davranış grup ilkesi tarafından denetlenebilirsiniz.

### <a name="linked-accounts"></a>Bağlı hesaplar

Windows'nin Masaüstü sürümünde olduğu gibi, diğer web hesabı kimlik bilgilerini HoloLens ebilirsiniz. Bu tür bir bağlantı, uygulamalar arasında veya uygulamalar içinde (Mağaza gibi) kaynaklara erişmeyi veya kişisel ve iş kaynaklarına erişimi birleştirmeyi kolaylaştırır. Cihaza bir hesap bağ verdikten sonra, her uygulamada tek tek oturum açmanız gerekmay için cihazı uygulamalara kullanma izni veebilirsiniz.

Hesapları bağlama, cihazda oluşturulan görüntüler veya indirmeler gibi kullanıcı verilerini ayırmaz.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Çok kullanıcılı desteği ayarlama (yalnızca Azure AD)

HoloLens Aynı Azure AD kiracısına sahip birden çok kullanıcıyı destekler. Bu özelliği kullanmak için, cihazı ayarlamak için, kuruluşa ait bir hesap kullansanız gerekir. Daha sonra, aynı kiracıdan diğer kullanıcılar oturum açma ekranından veya Başlat panelindeki kullanıcı kutucuğuna dokunarak cihazda oturum açın. Aynı anda yalnızca bir kullanıcı oturum açık olabilir. Bir kullanıcı oturum HoloLens önceki kullanıcının oturumlarını sildi. 

>[!IMPORTANT]
> Cihaz sahibi olarak kabul edilen cihaz kullanıcısı, Azure AD Join dışında cihaz sahipleri hakkında [daha fazla bilgi edinin.](security-adminless-os.md#device-owner)

Tüm kullanıcılar cihazda yüklü olan uygulamaları kullanabilir. Ancak her kullanıcının kendi uygulama verileri ve tercihleri vardır. Bir uygulamayı cihazdan kaldırmak tüm kullanıcılar için kaldırır.  

Azure AD hesaplarıyla ayarlanmış cihazlar microsoft hesabıyla cihazda oturum açmasına izin vermez. Sonraki tüm hesapların cihazla aynı kiracıdan Azure AD hesapları olması gerekir. Bunu destekleyen [uygulamalarda (örneğin, microsoft hesabı)](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) bir Microsoft Hesabı kullanarak oturum Microsoft Store. Cihazda oturum a0 için Azure AD hesaplarının kullanımından Microsoft Hesaplarına değiştirmek için cihaza [ters eğik çizgi uygulamanız gerekir.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. nesil),** Windows Holographic for Business kapsamında Nisan [2018 Güncelleştirmesinde Windows 10](/windows/mixed-reality/release-notes-april-2018) Azure AD kullanıcılarını [desteklemeye başladı.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok kullanıcı listelenir

Daha önce oturum açma ekranında yalnızca en son oturum açık olan kullanıcı ve 'Diğer kullanıcı' giriş noktası gösteri. Cihazda birden çok kullanıcı oturum amışsa bunun yeterli olmadığının müşteri geri bildirimini aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekmektedir.

[Windows Holographic sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1)tanıtılan, PIN  giriş alanında sağ tarafta bulunan Diğer kullanıcı'ya seçerek Oturum açma ekranında daha önce cihazda oturummış birden çok kullanıcı görüntülenir. Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Bu diğer kullanıcılar sayfasından cihaza Hesap ekle **düğmesi aracılığıyla yeni** bir kullanıcı **da** eklenebilir.

Diğer kullanıcılar **menüsünde,** Diğer **kullanıcılar düğmesi** cihazda oturum açmış olan son kullanıcı görüntülenir. Bu kullanıcının oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılandır.](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Kullanıcıları kaldırma

Kullanıcı hesabı Diğer kişiler'e gidip Ayarlar  >  **cihazdan**  >  **kaldırabilirsiniz.** Bu eylem ayrıca cihazdan kullanıcının uygulama verilerini kaldırarak alan da geri alar.  

## <a name="using-single-sign-on-within-an-app"></a>Uygulama içinde çoklu oturum açma kullanma

Bir uygulama geliştiricisi olarak, HoloLens [Hesap](/uwp/api/Windows.Security.Authentication.Web.Core)Yöneticisi API'lerini kullanarak Windows hesap yöneticisi API'lerinden diğer cihazlarda olduğu gibi Windows faydalanabilirsiniz. Bu API'ler için bazı kod örnekleri GitHub: [Web hesabı yönetim örneği.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Hesap bilgileri için kullanıcı onayı, iki faktörlü kimlik doğrulaması vb. talep gibi tüm hesap kesintileri, uygulama bir kimlik doğrulama belirteci isteğinde olduğunda iş gerekir.

Uygulamanıza daha önce bağlı değil belirli bir hesap türü gerektiriyorsa, uygulamanız sistemden kullanıcıdan bir hesap eklemesi istendiğinde. Bu istek, hesap ayarları bölmesinin, uygulamanın kalıcı alt uygulaması olarak başlatılmasını tetikler. 2D uygulamalar için bu pencere doğrudan uygulamanın merkezinde işler. Unity uygulamaları için bu istek, alt pencereyi işlemek için kullanıcıyı holografik uygulamanıza kısa bir süre alır. Bu bölmede komutları ve eylemleri özelleştirme hakkında bilgi için bkz. [WebAccountCommand Sınıfı.](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise ve diğer kimlik doğrulaması

Uygulamanız NTLM, Basic veya Kerberos gibi diğer kimlik doğrulaması türlerini kullanıyorsa, kullanıcının kimlik bilgilerini toplamak, Windows ve depolamak için [Windows](/uwp/api/Windows.Security.Credentials.UI) Kimlik Bilgisi kullanıcı arabirimini kullanabilirsiniz. Bu kimlik bilgilerini toplamaya yönelik kullanıcı deneyimi diğer bulut tabanlı hesap kesintilerine benzer ve 2D uygulamanın üzerinde bir alt uygulama olarak görünür veya kullanıcı arabirimini göstermek için bir Unity uygulamasını kısaca askıya alır.

## <a name="deprecated-apis"></a>Kullanım dışı API'ler

HoloLens için geliştirmenin Desktop için geliştirmeden farklı olduğu bir yol, [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API'sini tam olarak desteklememektir. Api, birincil hesap iyi durumdaysa bir belirteç döndürse de, bu makalede açıklananlar gibi kesintiler kullanıcı için herhangi bir kullanıcı arabirimi görüntülemez ve hesabın kimliğini doğru şekilde doğrulayamaz.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>İş Windows Hello (1. Nesil) HoloLens için destek var mı?

Windows Hello için (oturum açma için PIN kullanmayı destekler) HoloLens (1. Nesil) desteklemiştir. İş pini Windows Hello oturum açmasına izin vermek için HoloLens:

1. Bu HoloLens [MDM tarafından yönetiliyor olması gerekir.](hololens-enroll-mdm.md)
1. Cihaz için Windows Hello'yi etkinleştirmeniz gerekir. ([Bkz. Microsoft Intune.](/intune/windows-hello))
1. Kullanıcı HoloLens oturum açma seçeneklerini kullanarak **Ayarlar** PIN  >    >   Ekleme'yi kullanabilir.

> [!NOTE]
> Oturum açma seçeneklerini kullanarak oturum Microsoft hesabı kullanıcılar, oturum açma seçenekleri **PIN'i Ayarlar'de** bir PIN  >    >  **de ayarlamayı da sağlar.** Bu PIN, İş için [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)değil, [Windows Hello ile ilişkilendirildi.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Iris biyometrik kimlik doğrulaması 2. HoloLens uygulanır?

HoloLens 2, Iris kimlik doğrulamasını destekler. Iris, Windows Hello teknolojisini temel almaktadır ve hem Azure Active Directory Hem de Microsoft Hesapları tarafından de desteklemektedir. Iris, diğer teknolojilerle aynı şekilde Windows Hello ve [1/100.000'den](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)uzak biyometrik güvenlik sağlar.

Daha fazla [bilgi için bkz. Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) biyometrik gereksinimler ve belirtimler. İş için [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) ve Windows Hello [hakkında daha fazla bilgi.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Iris biyometrik bilgileri nerede depolanır?

Iris biyometrik bilgileri, her bir HoloLens belirtimleri [Windows Hello depolanır.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored) Paylaşılmaz ve iki şifreleme katmanıyla korunur. Bir hesapta yönetici hesabı olduğundan, yönetici bile diğer kullanıcılar tarafından erişilemez HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Iris kimlik doğrulamasını kullanmam gerekir mi?
Hayır, kurulum sırasında bu adımı atlayabilirsiniz. 

![Iris'i ayarlama.](./images/setup-iris.png)

HoloLens 2, FIDO2 güvenlik anahtarları da dahil olmak üzere kimlik doğrulaması için birçok farklı seçenek sağlar.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Iris bilgileri bu bilgilerden kaldırılabilir HoloLens?
Evet, bunu bir kullanıcıdan el ile Ayarlar.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hesap türü oturum açma davranışını nasıl etkiler?

Oturum açma için ilkeler uygulayacaksanız ilke her zaman geçerlidir. Oturum açma ilkesi uygulanmazsa, her hesap türü için varsayılan davranışlar bunlardır:

- **Azure AD:** Varsayılan olarak kimlik doğrulamasını sorar ve Ayarlar **artık** kimlik doğrulaması istemeden yapılandırılabilir.
- **Microsoft hesabı:** Kilit davranışı otomatik kilidinin açılmasına izin verme yöntemi farklıdır, ancak yeniden başlatma sırasında yine de oturum açma kimlik doğrulaması gereklidir.
- **Yerel hesap:** Kimlik doğrulaması her zaman parola şeklinde istenir, parolayla **yapılandırılamaz Ayarlar**

> [!NOTE]
> Şu anda etkin değil süre sürelerini desteklemez, yani **AllowIdleReturnWithoutPassword** ilkesine yalnızca cihaz StandBy'ye gittiği zaman dikkate alınmaktadır.

## <a name="additional-resources"></a>Ek kaynaklar

Kullanıcı kimlik koruması ve kimlik doğrulaması hakkında daha fazla bilgi için [Windows 10 ve kimlik belgelerine bakın.](/windows/security/identity-protection/)

Karma kimlik altyapısını ayarlama hakkında daha fazla bilgi için [Azure Hibrit kimlik belgelerini inceleyin.](/azure/active-directory/hybrid/)