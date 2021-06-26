---
title: HoloLens için Kullanıcı kimliğini ve oturum açmayı yönetme
description: HoloLens cihazları için Kullanıcı kimliği, çoklu Kullanıcı desteği, güvenlik, kurumsal kimlik doğrulama ve oturum açma yönetimi hakkında bilgi edinin.
keywords: HoloLens, Kullanıcı, hesap, AAD, Azure AD, ADFS, Microsoft hesabı, MSA, kimlik bilgileri, başvuru
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
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924426"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>HoloLens için Kullanıcı kimliğini ve oturum açmayı yönetme

> [!NOTE]
> Bu makale, BT profesyonelleri ve teknoloji meraklıları için teknik bir başvurudur. HoloLens ayarlama yönergelerini arıyorsanız, "[HoloLens 'Nizi ayarlama](hololens1-start.md)" veya "[HoloLens 2](hololens2-start.md)' yi ayarlama" konusunu okuyun.

Diğer Windows cihazları gibi, HoloLens her zaman bir kullanıcı bağlamı altında çalışır. Her zaman bir kullanıcı kimliği vardır. HoloLens, diğer Windows 10 cihazlarıyla aynı şekilde kimliği neredeyse aynı şekilde davranır. Bu makale, HoloLens üzerindeki kimlik için derin bir başvurudur ve HoloLens 'in diğer Windows 10 cihazlarından farklı olduğu konusunda odaklanır.

HoloLens çeşitli kullanıcı kimliklerinin türlerini destekler. Oturum açmak için bir veya daha fazla kullanıcı hesabı kullanabilirsiniz. HoloLens üzerindeki kimlik türleri ve kimlik doğrulama seçeneklerine genel bakış aşağıda verilmiştir:

| Kimlik türü | Cihaz başına hesaplar | Kimlik doğrulaması seçenekleri |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Azure Web kimlik bilgileri sağlayıcısı</li><li>Azure Authenticator uygulaması</li><li>Biyometrik (Iris) &ndash; HoloLens 2 yalnızca<sup>2</sup> </li><li>HoloLens &ndash; (1. gen) için isteğe bağlı olarak sabitle, Hololens 2 için gereklidir</li><li>Parola</li></ul> |
| [Microsoft hesabı (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biyometrik (Iris) &ndash; HoloLens 2</li><li>HoloLens &ndash; (1. gen) için isteğe bağlı olarak sabitle, Hololens 2 için gereklidir</li><li>Parola</li></ul> |
| [Yerel hesap](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Parola |

Buluta bağlı hesaplar (Azure AD ve MSA), Azure hizmetleri 'ni kullanabileceğinden daha fazla özellik sunmaktadır.  
> [!IMPORTANT]
> 1-Azure AD Premium cihazda oturum açmak için gerekli değildir. Ancak, otomatik kayıt ve Autopilot gibi, düşük dokunmalı bir bulut tabanlı dağıtımın diğer özellikleri için gereklidir.

> [!NOTE]
> 2-bir HoloLens 2 cihazı en fazla 64 Azure AD hesabını destekleyebileceği için, bu hesapların yalnızca 10 ' u Iris kimlik doğrulamasında kayıt olabilir. Bu, [iş Için Windows Hello 'ya yönelik diğer biyometrik kimlik doğrulama seçenekleriyle](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)hizalanır.

## <a name="setting-up-users"></a>Kullanıcıları ayarlama

Yeni bir kullanıcı oluşturmanın en yaygın yolu, HoloLens 'in kullanıma hazır deneyimi (OOBE) sırasında yapılır. Kurulum sırasında, HoloLens bir kullanıcının cihazda kullanmak istedikleri hesabı kullanarak oturum açmasını ister. Bu hesap, bir tüketici Microsoft hesabı veya Azure 'da yapılandırılmış bir kurumsal hesap olabilir. Bkz. [HoloLens 'Nizi ayarlama (1. Genel)](hololens1-start.md) veya [HoloLens 2](hololens2-start.md).

Diğer cihazlarda Windows gibi, kurulum sırasında oturum açmak cihazda bir kullanıcı profili oluşturur. Kullanıcı profili, uygulamaları ve verileri depolar. Aynı hesap, Windows hesap Yöneticisi API 'Lerini kullanarak kenar veya Microsoft Store gibi uygulamalarda çoklu oturum açma olanağı da sağlar.  

HoloLens 'te oturum açmak için bir kurumsal veya kurumsal hesap kullanıyorsanız, HoloLens kuruluşun BT altyapısına kaydeder. Bu kayıt, BT yöneticinizin mobil cihaz yönetimini (MDM), HoloLens uygulamanıza Grup ilkeleri gönderecek şekilde yapılandırmasını sağlar.

Varsayılan olarak, diğer Windows 10 cihazlarında olduğu gibi, HoloLens yeniden başlatıldığında veya bekleme modundan devam ettiğinde yeniden oturum açmanız gerekir. Bu davranışı değiştirmek için Ayarlar uygulamasını kullanabilir veya davranış Grup İlkesi tarafından denetlenebilir.

### <a name="linked-accounts"></a>Bağlı hesaplar

Windows 'un masaüstü sürümünde olduğu gibi, HoloLens hesabınıza ek web hesabı kimlik bilgileri bağlayabilirsiniz. Bu tür bağlama, kaynaklara veya uygulamalara (mağaza gibi) veya kişisel ve iş kaynaklarına erişimi birleştirmeye daha kolay bir şekilde erişmenizi sağlar. Cihaza bir hesabı bağladığınızda, her uygulamada tek tek oturum açmanıza gerek kalmaması için cihazı uygulamalara kullanma izni verebilirsiniz.

Bağlantı hesapları, cihazda oluşturulan görüntü veya indirme gibi kullanıcı verilerini ayıramaz.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Çoklu Kullanıcı desteğini ayarlama (yalnızca Azure AD)

HoloLens aynı Azure AD kiracısından birden çok kullanıcıyı destekler. Bu özelliği kullanmak için, cihazı kurmak üzere kuruluşunuza ait bir hesabı kullanmanız gerekir. Daha sonra, aynı kiracının diğer kullanıcıları, oturum açma ekranından veya Başlat panelindeki Kullanıcı kutucuğuna dokunarak cihazda oturum açabilir. Tek seferde yalnızca bir Kullanıcı oturum açabilir. Bir Kullanıcı oturum açtığında, HoloLens önceki Kullanıcı oturumunu kapatır. Cihazdaki ilk Kullanıcı cihaz sahibi olarak kabul edilir. Bu durumda, Azure AD katılımı söz konusu olduğunda [cihaz sahipleri hakkında daha fazla bilgi edinebilirsiniz](security-adminless-os.md#device-owner).

Tüm kullanıcılar cihazda yüklü olan uygulamaları kullanabilir. Ancak, her bir kullanıcının kendi uygulama verileri ve tercihleri vardır. Bir uygulamayı cihazdan kaldırma, tüm kullanıcılar için kaldırır.  

Azure AD hesapları ile ayarlanan cihazlar cihazda Microsoft hesabıyla oturum açmaya izin vermez. Kullanılan tüm sonraki hesaplar, cihazla aynı kiracıdan Azure AD hesapları olmalıdır. Bunu destekleyen [uygulamalar için bir Microsoft hesabı kullanarak oturum](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) açabilirsiniz (örneğin, Microsoft Store). Azure AD hesaplarını cihazda oturum açmak için Microsoft hesapları kullanmaya geçiş yapmak için, [cihazı yeniden Flash](hololens-recovery.md#clean-reflash-the-device)etmeniz gerekir.

> [!NOTE]
> **HoloLens (1. gen)** , Windows [holographic for Business](hololens-upgrade-enterprise.md)'ın bir parçası olarak [Windows 10 Nisan 2018 güncelleştirmesinde](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) birden çok Azure AD kullanıcısı desteklemeye başladı.

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok Kullanıcı listelendi

Daha önce oturum açma ekranında yalnızca en son oturum açan kullanıcının yanı sıra ' diğer Kullanıcı ' giriş noktası gösteriliyordu. Cihazda birden çok kullanıcı oturum açmışsa, bu yeterli olmayan müşteri geri bildirimi aldık. Yine de bunların Kullanıcı adını yeniden yazması gerekiyordu.

[Windows holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)' de TANıTıLAN, PIN girişi alanının sağında bulunan **başka bir Kullanıcı** seçilirken, oturum açma ekranında daha önce cihazda oturum açan birden çok Kullanıcı görüntülenir. Bu, kullanıcıların kullanıcı profillerini seçmesini ve sonra Windows Hello kimlik bilgilerini kullanarak oturum açmasını sağlar. Bu diğer kullanıcılar sayfasından, **Hesap Ekle** düğmesi aracılığıyla cihaza yeni bir kullanıcı da eklenebilir.

Diğer kullanıcılar menüsünde, diğer kullanıcılar düğmesi cihazda oturum açan son kullanıcıyı görüntüler. Bu Kullanıcı için oturum açma ekranına geri dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı](./images/multiusers2.jpg)

## <a name="removing-users"></a>Kullanıcılar kaldırılıyor

**Ayarlar**  >  **hesaplar**  >  **diğer kişiler**' e giderek bir kullanıcıyı cihazdan kaldırabilirsiniz. Bu eylem Ayrıca, söz konusu kullanıcının tüm uygulama verilerini cihazdan kaldırarak da boş alan geri kazanır.  

## <a name="using-single-sign-on-within-an-app"></a>Uygulama içinde çoklu oturum açma kullanma

Uygulama geliştiricisi olarak, diğer Windows cihazlarında olduğu gibi, [Windows hesap Yöneticisi API 'lerini](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)kullanarak HoloLens 'teki bağlantılı kimliklerden yararlanabilirsiniz. Bu API 'Ler için bazı kod örnekleri GitHub 'da kullanılabilir: [Web hesabı yönetim örneği](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Uygulama bir kimlik doğrulama belirteci istediğinde, hesap bilgileri, iki öğeli kimlik doğrulama vb. için Kullanıcı onayı isteme gibi olabilecek hesap kesintileri ele alınmalıdır.

Uygulamanız daha önce bağlanmayan belirli bir hesap türü gerektiriyorsa, uygulamanız kullanıcıdan bir tane eklemesini isteyebilir. Bu istek, uygulamanızın kalıcı bir alt öğesi olarak başlatılacak hesap ayarları bölmesini tetikler. 2B uygulamalar için bu pencere, doğrudan uygulamanızın merkezine göre oluşturulur. Unity uygulamaları için bu istek, Kullanıcı alt pencereyi oluşturmak için holographic uygulamanızın dışına çıkar. Bu bölmedeki komutları ve eylemleri özelleştirme hakkında daha fazla bilgi için bkz. [Webaccountcommand sınıfı](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Kuruluş ve diğer kimlik doğrulama

Uygulamanız NTLM, temel veya Kerberos gibi diğer kimlik doğrulama türlerini kullanıyorsa, kullanıcının kimlik bilgilerini toplamak, işlemek ve depolamak için [Windows kimlik bilgisi Kullanıcı arabirimini](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) kullanabilirsiniz. Bu kimlik bilgilerini toplamaya yönelik kullanıcı deneyimi, diğer bulut odaklı hesap kesintileri için çok benzerdir ve 2B uygulamanızın üzerinde bir alt uygulama olarak görünür veya Kullanıcı arabirimini göstermek için bir Unity uygulamasını kısaca askıya alır.

## <a name="deprecated-apis"></a>Kullanım dışı API 'Ler

HoloLens için geliştirmenin, masaüstü için geliştirmekten farklı olarak, [Onlineidavıd Cator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API 'sinin tam olarak desteklenmesinin bir yoludur. Birincil hesap iyi durumda olduğunda API bir belirteç döndürse de, bu makalede açıklananlar gibi kesintiler Kullanıcı için herhangi bir kullanıcı ARABIRIMI görüntülemez ve hesabın kimliğini doğru şekilde doğrulayamamaktadır.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>HoloLens 'te desteklenen Iş için Windows Hello (1. gen)?

Iş için Windows Hello (oturum açmak için PIN kullanılmasını destekler), HoloLens (1. gen) için desteklenir. HoloLens 'te Iş için Windows Hello PIN 'inin oturum açmasını sağlamak için:

1. HoloLens cihazının [MDM tarafından yönetilmesi](hololens-enroll-mdm.md)gerekir.
1. Cihaz için Iş için Windows Hello 'Yu etkinleştirmeniz gerekir. ([Microsoft Intune yönelik yönergelere bakın.](https://docs.microsoft.com/intune/windows-hello))
1. HoloLens 'te, Kullanıcı daha sonra,   >  PIN 'i ayarlamak için PIN Ekle **oturum açma seçeneklerini** kullanabilir  >   .

> [!NOTE]
> Microsoft hesabı kullanarak oturum açan kullanıcılar, **Ayarlar**  >  **oturum açma seçeneklerinde**  >  **PIN Ekle**' de bir PIN de ayarlayabilir. Bu PIN Windows Hello [for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)yerine [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)ile ilişkilendirilir.

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Bir Iris biyometrik kimlik doğrulaması, HoloLens 2 ' de nasıl uygulanır?

HoloLens 2 Iris kimlik doğrulamasını destekler. Iris, Windows Hello teknolojisini temel alır ve hem Azure Active Directory hem de Microsoft hesapları tarafından kullanılmak üzere desteklenir. Iris diğer Windows Hello teknolojileriyle aynı şekilde uygulanır ve Biyometri güvenliğine en fazla 1/100 KB erişir.

Daha fazla bilgi için bkz. [Windows Hello için biyometrik gereksinimler ve Özellikler](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) ve [Iş için Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)hakkında daha fazla bilgi edinin. 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Hesap türü, oturum açma davranışını nasıl etkiler?

Oturum açma için ilkeler uygularsanız, ilke her zaman uygulanır. Oturum açma için herhangi bir ilke uygulanmadığından, bunlar her hesap türü için varsayılan davranışlardır:

- **Azure AD**: varsayılan olarak kimlik doğrulaması Ister ve **ayarlarla** yapılandırılabilir olarak kimlik doğrulaması iste.
- **Microsoft hesabı**: kilit davranışı otomatik kilit açmaya izin vermek için farklıdır, ancak yeniden başlatma sırasında oturum açma kimlik doğrulaması hala gereklidir.
- **Yerel hesap**: her zaman, **ayarlarda** yapılandırılabilir değil, bir parola biçiminde kimlik doğrulaması ister

> [!NOTE]
> Etkinlik dışı zamanlayıcılar Şu anda desteklenmiyor. Bu, **AllowIdleReturnWithoutPassword** ilkesinin yalnızca cihaz bekleme moduna geçtiğinde dikkate alındığı anlamına gelir.

## <a name="additional-resources"></a>Ek kaynaklar

[Windows 10 güvenlik ve kimlik belgelerinin](https://docs.microsoft.com/windows/security/identity-protection/)Kullanıcı kimlik koruması ve kimlik doğrulaması hakkında daha fazla bilgi edinin.

[Azure hibrit kimlik belgelerinin](https://docs.microsoft.com/azure/active-directory/hybrid/)kapsamlı karma kimlik altyapısını ayarlama hakkında daha fazla bilgi edinin.
