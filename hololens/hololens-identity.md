---
title: HoloLens için kullanıcı kimliğini ve oturum açma bilgilerini yönetme
description: HoloLens cihazları için kullanıcı kimliği, çok kullanıcı desteği, güvenlik, kurumsal kimlik doğrulaması ve oturum açma bilgilerini yönetmeyi öğrenin.
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
ms.openlocfilehash: f8dcc8619715871db0aaba306dd19d252d73ac47
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379136"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens için kullanıcı kimliğini ve oturum açma bilgilerini yönetme

> [!NOTE]
> Bu makale, IT Uzmanları ve teknoloji meraklıları için teknik bir başvuru sağlar. HoloLens ayarlama yönergelerini arıyorsanız "[HoloLens'inizi ayarlama (1. nesil)](hololens1-start.md)" veya "[HoloLens 2'nizi](hololens2-start.md)ayarlama" makalelerini okuyun.

Diğer Windows cihazları gibi HoloLens de her zaman bir kullanıcı bağlamında çalışır. Her zaman bir kullanıcı kimliği vardır. HoloLens, diğer cihazlarla neredeyse aynı şekilde Windows 10 davranır. Bu makale, HoloLens'de kimlik için derinlemesine bir başvurudur ve HoloLens'in diğer sanal cihazlardan nasıl farklı Windows 10 odaklanır.

HoloLens çeşitli kullanıcı kimliklerini destekler. Oturum açma için bir veya daha fazla kullanıcı hesabı kullanabilirsiniz. HoloLens'de kimlik türlerine ve kimlik doğrulama seçeneklerine genel bir bakış:

| Kimlik türü | Cihaz başına hesap sayısı | Kimlik doğrulaması seçenekleri |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD Premium gerektirir) | 64 | <ul><li>Azure web kimlik bilgileri sağlayıcısı</li><li>Azure Authenticator Uygulaması</li><li>Biyometrik (Iris) &ndash; HoloLens 2 yalnızca<sup>1</sup> </li><li>&ndash;HoloLens 2 için gereken HoloLens (1. nesil) için isteğe bağlı PIN</li><li>Parola</li></ul> |
| [Microsoft Hesabı (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Yalnızca biyometri &ndash; (Iris) HoloLens 2</li><li>&ndash;HoloLens 2 için gereken HoloLens (1. nesil) için isteğe bağlı PIN</li><li>Parola</li></ul> |
| [Yerel hesap](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Parola |

Buluta bağlı hesaplar (Azure AD ve MSA), Azure hizmetlerini kullanabileceği için daha fazla özellik sunar.  

> [!NOTE]
> 1 - HoloLens 2 cihazı en fazla 64 Azure AD hesabını destekleyene kadar, bu hesaplardan yalnızca 10'u Iris Kimlik Doğrulamasına kaydolabilirsiniz. Bu, kimlik doğrulaması için diğer [Biyometrik kimlik doğrulama seçenekleriyle İş İçin Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Kullanıcıları ayarlama

Yeni kullanıcı ayarlamanın en yaygın yolu HoloLens ilk kullanım deneyimi (OOBE) sırasındadır. Kurulum sırasında HoloLens, bir kullanıcıdan cihazda kullanmak istediğiniz hesabı kullanarak oturum açmasını ister. Bu hesap bir tüketici Microsoft hesabı azure'da yapılandırılmış bir kurumsal hesap olabilir. Bkz. [HoloLens (1. nesil) veya](hololens1-start.md) [HoloLens 2'nizi ayarlama.](hololens2-start.md)

Diğer cihazlardaki Windows'da olduğu gibi, kurulum sırasında oturum açma işlemi cihazda bir kullanıcı profili oluşturur. Kullanıcı profili, uygulamaları ve verileri depolar. Aynı hesap, Windows Hesap Yöneticisi API'lerini kullanarak Edge veya Skype gibi uygulamalar için Çoklu Oturum Açma da sağlar.  

HoloLens'te oturum a0 için bir kuruluş veya kuruluş hesabı kullanırsanız HoloLens, kuruluşun IT altyapısına kaydolr. Bu kayıt, IT Yöneticinizin HoloLens'inize grup ilkeleri Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) yapılandırmasını sağlar.

Varsayılan olarak, diğer Windows 10 cihazlarında olduğu gibi HoloLens yeniden başlatıldığında veya hazır bekleyen cihazlardan devam edince yeniden oturum açmanız gerekir. Bu davranışı değiştirmek için Ayarlar uygulamasını kullanabilirsiniz veya davranış grup ilkesi tarafından denetlenebilirsiniz.

### <a name="linked-accounts"></a>Bağlı hesaplar

Windows'un Masaüstü sürümünde olduğu gibi, HoloLens hesabınıza ek web hesabı kimlik bilgileri bağlamanız gerekir. Bu tür bir bağlantı, uygulamalar arasında veya uygulamalar içinde (Mağaza gibi) kaynaklara erişmeyi veya kişisel ve iş kaynaklarına erişimi birleştirmeyi kolaylaştırır. Cihaza bir hesap bağ verdikten sonra, her uygulamada tek tek oturum açmanız gerekmay için cihazı uygulamalara kullanma izni veebilirsiniz.

Hesapları bağlama, cihazda oluşturulan görüntüler veya indirmeler gibi kullanıcı verilerini ayırmaz.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Çok kullanıcılı desteği ayarlama (yalnızca Azure AD)

HoloLens, aynı Azure AD kiracısı için birden çok kullanıcı destekler. Bu özelliği kullanmak için, cihazı ayarlamak için, kuruluşa ait bir hesap kullansanız gerekir. Daha sonra, aynı kiracıdan diğer kullanıcılar oturum açma ekranından veya Başlat panelindeki kullanıcı kutucuğuna dokunarak cihazda oturum açın. Aynı anda yalnızca bir kullanıcı oturum adedi. Bir kullanıcı oturum aken HoloLens önceki kullanıcının oturumlarını imzalar. Cihaz sahibi olarak kabul edilen ilk kullanıcı, Azure AD'ye Katılma dışında cihaz sahipleri [hakkında daha fazla bilgi edinin.](security-adminless-os.md#device-owner)

Tüm kullanıcılar cihazda yüklü olan uygulamaları kullanabilir. Ancak her kullanıcının kendi uygulama verileri ve tercihleri vardır. Bir uygulamayı cihazdan kaldırmak tüm kullanıcılar için kaldırır.  

Azure AD hesaplarıyla ayarlanmış cihazlar microsoft hesabıyla cihazda oturum açmasına izin vermez. Sonraki tüm hesapların cihazla aynı kiracıdan Azure AD hesapları olması gerekir. Bunu destekleyen [uygulamalarda (örneğin, microsoft hesabı)](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) bir Microsoft Hesabı kullanarak oturum Microsoft Store. Cihazda oturum a0 için Azure AD hesaplarını kullanmak yerine Microsoft Hesapları olarak değiştirmek için cihaza [ters eğik çizgi uygulamanız gerekir.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. nesil),** Windows Holographic for Business kapsamında Windows 10 Nisan 2018 Güncelleştirmesi Azure [](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) AD [kullanıcılarını desteklemeye başladı.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında listelenen birden çok kullanıcı

Daha önce Oturum Açma ekranında yalnızca en son oturum açık olan kullanıcının yanı sıra 'Diğer kullanıcı' giriş noktası gösteri. Cihazda birden çok kullanıcı oturum amışsa bunun yeterli olmadığını ifade etmek için müşteri geri bildirimi aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekirdi.

[Windows Holographic sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1)tanıtılan, PIN girişi alanında sağ tarafta bulunan Diğer kullanıcı'nın seçili olduğu oturum açma ekranında daha önce cihazda oturummış birden çok kullanıcı görüntülenir.  Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Cihaza hesap ekle düğmesi aracılığıyla bu Diğer kullanıcılar sayfasından yeni bir kullanıcı **da eklenebilir.**

Diğer kullanıcılar menüsünde, Diğer kullanıcılar düğmesi cihazda oturum açtıran son kullanıcı görüntülenir. Bu kullanıcının Oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı](./images/multiusers2.jpg)

## <a name="removing-users"></a>Kullanıcıları kaldırma

Ayarlar Hesapları Diğer kişiler'e gidip   >  **cihazdan bir kullanıcı**  >  **kaldırabilirsiniz.** Bu eylem ayrıca cihazdan kullanıcının uygulama verilerini kaldırarak alan da geri alar.  

## <a name="using-single-sign-on-within-an-app"></a>Uygulama içinde çoklu oturum açma kullanma

Uygulama geliştiricisi olarak, Diğer Windows cihazlarda olduğu gibi [Windows Hesap](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)Yöneticisi API'lerini kullanarak HoloLens'te bağlı kimliklerden faydalanabilirsiniz. Bu API'ler için bazı kod örnekleri GitHub'da bulunabilir: [Web hesabı yönetimi örneği.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Uygulama bir kimlik doğrulama belirteci isteğinde olduğunda hesap bilgileri için kullanıcı onayı, iki faktörlü kimlik doğrulaması vb. talep gibi tüm hesap kesintileri iş gerekir.

Uygulamanıza daha önce bağlı değil belirli bir hesap türü gerektiriyorsa, uygulamanız sistemden kullanıcıdan bir hesap eklemesi istenir. Bu istek, hesap ayarları bölmesinin, uygulamanın kalıcı alt uygulaması olarak başlatılmasını tetikler. 2D uygulamalar için bu pencere doğrudan uygulamanın merkezinde işlemeye devam ediyor. Unity uygulamaları için bu istek, alt pencereyi işlemek için kullanıcıyı holografik uygulamanıza kısa bir süre alır. Bu bölmede komutları ve eylemleri özelleştirme hakkında bilgi için bkz. [WebAccountCommand Sınıfı.](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand)

## <a name="enterprise-and-other-authentication"></a>Kurumsal ve diğer kimlik doğrulaması

Uygulamanız NTLM, Basic veya Kerberos gibi diğer kimlik doğrulaması türlerini kullanıyorsa, kullanıcının kimlik bilgilerini toplamak, işlemek ve depolamak için [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) Kimlik Bilgileri Kullanıcı Bilgileri kullanıcı arabirimini kullanabilirsiniz. Bu kimlik bilgilerini toplamaya yönelik kullanıcı deneyimi diğer bulut tabanlı hesap kesintilerine çok benzer ve 2D uygulamanın üzerinde bir alt uygulama olarak görünür veya kullanıcı arabirimini göstermek için bir Unity uygulamasını kısaca askıya alır.

## <a name="deprecated-apis"></a>Kullanım dışı API'ler

HoloLens için geliştirmenin Desktop için geliştirmeden farklı olduğu bir yol, [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API'sini tam olarak desteklememektir. Api, birincil hesap iyi durumdaysa bir belirteç döndürse de, bu makalede açıklananlar gibi kesintiler kullanıcı için herhangi bir kullanıcı arabirimi görüntülemez ve hesabın kimliğini doğru şekilde doğrulayamaz.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens İş İçin Windows Hello (1. Nesil) için desteklenen bir destek var mı?

İş İçin Windows Hello (oturum açma için PIN kullanmayı destekler) HoloLens (1. Nesil) için de desteklemiştir. HoloLens İş İçin Windows Hello pin ile oturum açmasına izin vermek için:

1. HoloLens cihazı [MDM tarafından yönetiliyor.](hololens-enroll-mdm.md)
1. Cihaz için İş İçin Windows Hello etkinleştirmeniz gerekir. ([Bkz. Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. HoloLens'te kullanıcı daha sonra Ayarlar **Oturum** Açma Seçenekleri PIN  >  **Eklemek**  >  **için PIN'i** kullanabilir.

> [!NOTE]
> Bir uygulama kullanarak oturum Microsoft hesabı kullanıcılar, Ayarlar Oturum Açma Seçenekleri PIN Ekleme sayfasında bir PIN  >    >  **de ayarlar.** Bu PIN, Windows Hello [yerine](https://support.microsoft.com/help/17215/windows-10-what-is-hello), ile [İş İçin Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>HoloLens 2'de Iris biyometrik kimlik doğrulaması nasıl uygulanır?

HoloLens 2, Iris kimlik doğrulamasını destekler. Iris, Windows Hello teknolojisini temel almaktadır ve hem Azure Active Directory hem de Microsoft Hesapları tarafından de desteklemektedir. Iris, diğer teknolojilerle aynı şekilde Windows Hello ve 1/100.000'den uzak biyometri güvenliği sağlar.

Daha fazla [bilgi için bkz. Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) biyometrik gereksinimler ve belirtimler. daha fazla bilgi [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) ve [İş İçin Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hesap türü oturum açma davranışını nasıl etkiler?

Oturum açma için ilkeler uygulayacaksanız ilke her zaman geçerlidir. Oturum açma ilkesi uygulanmazsa, her hesap türü için varsayılan davranışlar bunlardır:

- **Azure AD:** Varsayılan olarak kimlik doğrulamasını sorar ve ayarlar tarafından **artık** kimlik doğrulaması istemeden yapılandırılabilir.
- **Microsoft hesabı:** Kilit davranışı otomatik kilidinin açılmasına izin verme yöntemi farklıdır, ancak yeniden başlatma sırasında yine de oturum açma kimlik doğrulaması gereklidir.
- **Yerel hesap:** Her zaman parola şeklinde kimlik doğrulaması istenir, Ayarlar'da **yapılandırılamaz**

> [!NOTE]
> Şu anda etkin değil süre sürelerini desteklemez, bu da **AllowIdleReturnWithoutPassword** ilkesine yalnızca cihaz StandBy'ye gittiği zaman dikkate alınmaktadır.

## <a name="additional-resources"></a>Ek kaynaklar

Kullanıcı kimlik koruması ve kimlik doğrulaması hakkında daha fazla bilgi için [Windows 10 ve kimlik belgelerine bakın.](https://docs.microsoft.com/windows/security/identity-protection/)

Karma kimlik altyapısını ayarlama hakkında daha fazla bilgi için [Azure Hibrit kimlik belgelerini inceleyin.](https://docs.microsoft.com/azure/active-directory/hybrid/)
