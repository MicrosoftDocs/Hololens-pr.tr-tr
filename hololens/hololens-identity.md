---
title: Kullanıcılar için kullanıcı kimliğini ve oturum HoloLens
description: Cihazlarınızı yönetmek için kullanıcı kimliğini, çok kullanıcı desteğini, güvenliği, kurumsal kimlik doğrulamasını ve oturum HoloLens öğrenin.
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
ms.openlocfilehash: e4c68ad6535293f916cc92c42204954110edc4fe
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189554"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Kullanıcılar için kullanıcı kimliğini ve oturum HoloLens

> [!NOTE]
> Bu makale, IT Uzmanları ve teknoloji meraklıları için teknik bir başvuru sağlar. Ayarlama yönergelerini HoloLens, " HoloLens[(1. nesil) " veya](hololens1-start.md)"[2.](hololens2-start.md)Nesil'inizi ayarlama" HoloLens okuyun.

Diğer Windows cihazlar gibi, HoloLens her zaman bir kullanıcı bağlamında çalışır. Her zaman bir kullanıcı kimliği vardır. HoloLens diğer cihazlarda olduğu gibi neredeyse aynı şekilde Windows davranır. Bu makale, HoloLens'da kimlik için derinlemesine bir başvurudur ve HoloLens diğer cihazlardan nasıl farklı Windows odaklanır.

HoloLens çeşitli kullanıcı kimliklerini destekler. Oturum açma için bir veya daha fazla kullanıcı hesabı kullanabilirsiniz. Kimlik türlerine ve kimlik doğrulama seçeneklerine genel bakış bilgileri burada HoloLens:

| Kimlik türü | Cihaz başına hesap sayısı | Kimlik doğrulaması seçenekleri |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure web kimlik bilgileri sağlayıcısı</li><li>Azure Authenticator Uygulaması</li><li>Biyometri (Iris) &ndash; HoloLens 2 yalnızca<sup>2</sup> </li><li>FIDO2 Güvenlik anahtarı</li><li>PIN &ndash; İsteğe bağlı HoloLens (1. nesil), 2. nesil için HoloLens gerekir</li><li>Parola</li></ul> |
| [Microsoft Hesabı (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biyometri (Iris) &ndash; HoloLens 2</li><li>PIN &ndash; İsteğe bağlı HoloLens (1. nesil), 2. nesil için HoloLens gerekir</li><li>Parola</li></ul> |
| [Yerel hesap](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Parola |

Buluta bağlı hesaplar (Azure AD ve MSA), Azure hizmetlerini kullanabileceği için daha fazla özellik sunar.  
> [!IMPORTANT]
> 1 - Azure AD Premium oturum açması için gerekli değildir. Ancak, Auto-enrollment ve Autopilot gibi düşük temaslı bulut tabanlı dağıtımın diğer özellikleri için gereklidir.

> [!NOTE]
> 2 - HoloLens 2 cihazı en fazla 64 Azure AD hesabını destekleyene kadar, bu hesaplardan yalnızca 31'i Iris Kimlik Doğrulaması'ya kaydolabilirsiniz. Bu, İş için güvenlik için [diğer Biyometrik kimlik doğrulama Windows Hello hizalanır.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 - Bir yerel hesap, [OOBE](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)sırasında bir sağlama paketi aracılığıyla yalnızca bir cihazda ayarlanıyor olabilir; daha sonra ayarlar uygulamasına ek olamaz. Zaten ayarlanmış bir cihazda yerel bir hesap kullanmak için, cihazı ters eğik [çizgiyle sıfırlamanız gerekir.](hololens-recovery.md)

## <a name="setting-up-users"></a>Kullanıcıları ayarlama

Yeni bir kullanıcı ayarlamak için iki yol vardır HoloLens. En yaygın yol, HoloLens deneyimi (OOBE) sırasındadır. Bu Azure Active Directory, diğer [kullanıcılar](#setting-up-multi-user-support-azure-ad-only) OOBE'den sonra Azure AD kimlik bilgilerini kullanarak oturum açabilirsiniz. HoloLens OOBE sırasında bir MSA veya yerel hesap ile ayarlanmış tüm cihazlar birden çok kullanıcı desteklemez. Bkz. HoloLens [(1. nesil) veya](hololens1-start.md) [2 HoloLens ayarlama.](hololens2-start.md)

Bir kuruluş veya kuruluş hesabı kullanarak HoloLens HoloLens kuruluşun IT altyapısına kaydolabilirsiniz. Bu kayıt, IT Yöneticinizin mobil uygulamanıza grup Cihaz Yönetimi (MDM) göndermesi için Mobile HoloLens.

Diğer Windows gibi, kurulum sırasında oturum açma işlemi cihazda bir kullanıcı profili oluşturur. Kullanıcı profili, uygulamaları ve verileri depolar. Aynı hesap, Hesap Yöneticisi API'lerini kullanarak Edge veya Microsoft Store uygulamalar için çoklu Windows sağlar.

Varsayılan olarak, diğer Windows 10 cihazlarda olduğu gibi, yeniden başlatıldığında veya beklemeden devam HoloLens yeniden oturum açmanız gerekir. Ayarlar uygulamasını kullanarak bu davranışı değiştirebilirsiniz veya davranış grup ilkesi tarafından denetlenebilirsiniz.

### <a name="linked-accounts"></a>Bağlı hesaplar

Uygulamanın Masaüstü sürümünde olduğu Windows, ek web hesabı kimlik bilgilerini HoloLens ebilirsiniz. Bu tür bir bağlantı, uygulamalar arasında veya uygulamalar içinde (Mağaza gibi) kaynaklara erişmeyi veya kişisel ve iş kaynaklarına erişimi birleştirmeyi kolaylaştırır. Cihaza bir hesap bağ verdikten sonra, her uygulamada tek tek oturum açmanız gerekmay için cihazı uygulamalara kullanma izni veebilirsiniz.

Hesapları bağlama, cihazda oluşturulan görüntüler veya indirmeler gibi kullanıcı verilerini ayırmaz.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Çok kullanıcılı desteği ayarlama (yalnızca Azure AD)

HoloLens Aynı Azure AD kiracısına sahip birden çok kullanıcıyı destekler. Bu özelliği kullanmak için, cihazı ayarlamak için, kuruluşa ait bir hesap kullansanız gerekir. Daha sonra, aynı kiracıdan diğer kullanıcılar oturum açma ekranından veya Başlat panelindeki kullanıcı kutucuğuna dokunarak cihazda oturum açın. Aynı anda yalnızca bir kullanıcı oturum açık olabilir. Bir kullanıcı oturum HoloLens önceki kullanıcının oturumlarını sildi. 

>[!IMPORTANT]
> Cihaz sahibi olarak kabul edilen cihaz kullanıcısı, Azure AD Join dışında cihaz sahipleri hakkında [daha fazla bilgi edinin.](security-adminless-os.md#device-owner)

Tüm kullanıcılar cihazda yüklü olan uygulamaları kullanabilir. Ancak her kullanıcının kendi uygulama verileri ve tercihleri vardır. Bir uygulamayı cihazdan kaldırmak tüm kullanıcılar için kaldırır.  

Azure AD hesaplarıyla ayarlanmış cihazlar microsoft hesabıyla cihazda oturum açmasına izin vermez. Sonraki tüm hesapların cihazla aynı kiracıdan Azure AD hesapları olması gerekir. Bunu destekleyen [uygulamalarda (örneğin, microsoft hesabı)](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) bir Microsoft Hesabı kullanarak oturum Microsoft Store. Cihazda oturum a0 için Azure AD hesaplarının kullanımından Microsoft Hesapları'nın kullanımına değiştirmek için cihaza [ters eğik çizgi uygulamanız gerekir.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. nesil),** Windows Holographic for Business kapsamında Nisan [2018 Güncelleştirmesinde Windows 10](/windows/mixed-reality/release-notes-april-2018) Azure AD kullanıcılarını [desteklemeye Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında listelenen birden çok kullanıcı

Daha önce Oturum Açma ekranında yalnızca en son oturum açık olan kullanıcının yanı sıra 'Diğer kullanıcı' giriş noktası da gösteri. Cihazda birden çok kullanıcı oturum amışsa bunun yeterli olmadığını ifade etmek için müşteri geri bildirimi aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekirdi.

[Windows Holographic sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1)tanıtılan, PIN  girişi alanında sağ tarafta bulunan Diğer kullanıcı'ya seçerek Oturum açma ekranında daha önce cihazda oturummış birden çok kullanıcı görüntülenir. Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Cihaza hesap ekle düğmesi aracılığıyla bu Diğer kullanıcılar sayfasından da yeni bir **kullanıcı eklenebilir.**

Diğer kullanıcılar menüsünde, Diğer kullanıcılar düğmesi cihazda oturum açmış olan son kullanıcı görüntülenir. Bu kullanıcının Oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılandır.](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Kullanıcıları kaldırma

Bir kullanıcının cihazdan kaldırması için Diğer kişiler  >  **Ayarlar'e**  >  **gidip bu kullanıcıya erişim sebilirsiniz.** Bu eylem ayrıca cihazdan kullanıcının uygulama verilerini kaldırarak alan da geri alar.  

## <a name="using-single-sign-on-within-an-app"></a>Uygulama içinde çoklu oturum açma kullanma

Bir uygulama geliştiricisi olarak, Windows [Account Manager](/uwp/api/Windows.Security.Authentication.Web.Core)API'lerini kullanarak HoloLens'da bağlı kimliklerden, diğer cihazlarda olduğu gibi Windows faydalanabilirsiniz. Bu API'ler için bazı kod örnekleri GitHub: [Web hesabı yönetim örneği.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Uygulama bir kimlik doğrulama belirteci isteğinde olduğunda hesap bilgileri için kullanıcı onayı, iki faktörlü kimlik doğrulaması vb. talep gibi tüm hesap kesintileri iş gerekir.

Uygulamanıza daha önce bağlı değil belirli bir hesap türü gerektiriyorsa, uygulamanız sistemden kullanıcıdan bir hesap eklemesi istendiğinde. Bu istek, hesap ayarları bölmesinin, uygulamanın kalıcı bir alt uygulaması olarak başlatılmasını tetikler. 2D uygulamalar için bu pencere doğrudan uygulamanın merkezinde işler. Unity uygulamaları için bu istek, alt pencereyi işlemek için kullanıcıyı holografik uygulamanıza kısa bir süre alır. Bu bölmede komutları ve eylemleri özelleştirme hakkında bilgi için bkz. [WebAccountCommand Sınıfı.](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Enterprise ve diğer kimlik doğrulaması

Uygulamanız NTLM, Basic veya Kerberos gibi diğer kimlik doğrulaması türlerini kullanıyorsa, kullanıcının kimlik bilgilerini toplamak, Windows ve depolamak için [Windows](/uwp/api/Windows.Security.Credentials.UI) Kimlik Bilgisi kullanıcı arabirimini kullanabilirsiniz. Bu kimlik bilgilerini toplamaya yönelik kullanıcı deneyimi diğer bulut tabanlı hesap kesintilerine çok benzer ve 2D uygulamanın üzerinde bir alt uygulama olarak görünür veya kullanıcı arabirimini göstermek için bir Unity uygulamasını kısaca askıya alır.

## <a name="deprecated-apis"></a>Kullanım dışı API'ler

HoloLens için geliştirmenin Desktop için geliştirmeden farklı olduğu bir yol, [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API'sini tam olarak desteklememektir. Birincil hesap iyi durumda olduğunda API bir belirteç döndürse de, bu makalede açıklananlar gibi kesintiler Kullanıcı için herhangi bir kullanıcı ARABIRIMI görüntülemez ve hesabın kimliğini doğru şekilde doğrulayamamaktadır.

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

![Iris](./images/setup-iris.png)

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
