---
title: Parola kullanımını sınırlama
description: parola kullanımını HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: güvenlik, hololens, parola kullanımını sınırlama, parola, hololens parolası, oturum açma, oturum açma, windows hello, hello, Windows hesap yöneticisi, FIDO2 oturum açma, FIDO 2, WEBAUTHN, yerel hesap, hololens güvenliği
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124429020"
---
# <a name="limiting-password-use"></a>Parola kullanımını sınırlama

Günümüzde çoğu bilgisayar sistemi, güvenliğin temeli olarak kullanıcı kimlik bilgilerini kullanır ve bunları yeniden kullanılabilir, kullanıcı tarafından oluşturulan parolalara bağımlı hale gelir. Bu durum, parolaların hesap güvenliğinin ihlal ve veri ihlallerinin en yaygın nedeni haline de neden oldu. Buna örnek olarak, parolalar iletimde kesilebilir veya bir sunucudan çalınarak (kimlik avı veya parola spreyi saldırıları tarafından) ve bir kullanıcı hesabına erişim elde etmek için ele geçirilebilir.

Güvenlik ve hesap korumasını geliştirmek için HoloLens 2, cihaz oturum açma için güçlü, donanım tarafından desteklene "parolasız" kimlik bilgilerini (Windows Hello dahil) etkinleştirme özelliğine sahiptir ve Microsoft bulutuna sorunsuz erişim sunar.

## <a name="signing-in-from-another-device"></a>Başka bir cihazdan oturum açma

HoloLens 2, karmaşık parolalar yazma ve kimlik bilgileri olarak parola ihtiyacının en aza indirilmesi için ilk cihaz kurulumu sırasında Azure Active Directory iş hesapları ve kullanıcı oturum açma bilgileri için uzak cihaz oturum açma seçenekleri sunar. Kimlik doğrulaması için akıllı kart kullanan kullanıcılar ve kuruluşlar, HoloLens 2 gibi cihazlarda bu kimlik bilgilerini kullanmada zorlukla karşılar ve kuruluşlar genellikle soruna çözüm bulmak için karmaşık sistemler ve maliyetli süreçler geliştirir. Bu sorunu çözmek için Azure AD, 2. veya 2. oturum açmada parolasız oturum HoloLens sunar.

İlk kimlik doğrulama yöntemi, cihaza bağlı bir kullanıcı Microsoft Authenticator kimlik bilgilerini sağlayan anahtar tabanlı kimlik doğrulaması sağlamak için Microsoft Authenticator uygulamasındaki yeni özellikleri kullanır. Yönetici tarafından bir kiracıda etkinleştirildikten sonra, kullanıcılara cihaz kurulumu sırasında HoloLens uygulamalarında bir sayıya dokunmalarını söyleyen bir ileti gösterilir. Ardından kimlik doğrulayıcı uygulamasındaki sayıyla eşleşmesi, Onayla'nın seçilmesi, pin'ini sağlamaları veya kimlik doğrulamasının devam etmek için biyometrik HoloLens kimlik doğrulamasını sağlamaları gerekir. Bu, parolasız oturum açma [konusunda daha ayrıntılı olarak açıklanmıştır.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

İkincisi, kullanıcılar için sezgisel olan ve ek altyapı gerektirmeyen bir cihaz kodu akışıdır.  Bu uzaktan oturum açma davranışı, kuruluşun tercih edilen kimlik doğrulama mekanizmasını destekleyen başka bir güvenilir cihaza bağlı olur ve tamamlandığında, oturum açma veya cihaz kurulumunu tamamlamak için belirteçler HoloLens cihaza geri verir. Bu akışta yer alan adımlar:

  1. OOBE'de ilk cihaz kurulumu veya oturum açma akışlarını geçen bir kullanıcıya "Başka bir cihazdan oturum açma" bağlantısı ve bu bağlantıya dokunması gerekir. Bu, bir uzaktan oturum açma oturumu başlatıyor.
  1. Ardından kullanıcıya, Azure AD Güvenli Belirteç [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Hizmeti'nin (STS) cihaz kimlik doğrulama uç noktasını belirten kısa bir URI ( ) içeren bir yoklama sayfası gösterilir. Kullanıcıya bulutta güvenli bir şekilde oluşturulan ve en fazla 15 dakika ömrü olan tek kullanımlık bir kod da sunulmaktadır. Azure AD, kod oluşturmanın yanı sıra önceki adımda uzaktan oturum açma isteğinin başlatalımı ile birlikte şifrelenmiş bir oturum oluşturur ve uzaktan oturum açma isteğini onaylamak için URI ve kod kullanılır.
  1. Kullanıcı daha sonra başka bir cihazdan URI'ye gidin ve 2 cihazında görüntülenen kodu HoloLens istenir.
  1. Kullanıcı kodu girdiktan sonra Azure AD STS, kullanıcının uzaktan oturum açma isteğini tetikleyen ve kodun HoloLens 2 cihazına sahip olduğunu belirten bir sayfa görüntüler. Ardından kullanıcıdan kimlik avı saldırılarını önlemek için onay istenir.
  1. Kullanıcı görüntülenen 'uygulamada' oturum açmaya devam etmek seçerse, Azure AD STS kullanıcıdan kimlik bilgilerini istenir. Başarılı bir kimlik doğrulamasında Azure AD STS, önbelleğe alınan uzak oturumu yetkilendirme koduyla birlikte 'onaylı' olarak günceller.
  1. Son olarak, kullanıcının HoloLens 2 cihazındaki yoklama sayfası Azure AD'den bir 'Yetkili' yanıtı alır ve kullanıcı kodunu, ilişkili saklı yetkilendirme kodunu doğrulamaya devam eder ve cihaz kurulumunu tamamlamak için istenen OAuth belirteçlerini üretir. Oluşturulan kimlik doğrulama belirteci 1 saat boyunca geçerlidir ve yenileme belirtecin ömrü 90 gündür.

Bu akışta kullanılan kod oluşturma ve şifreleme algoritmalarının her ikisi de FIPS uyumludur. HoloLens 2 cihaz, cihaz anahtarlarının güvenliğini sağlamak ve donanım korumalı anahtarlar kullanarak kullanıcı kimlik doğrulaması sonrasında oluşturulan belirteçleri şifrelemek için TPM kullanır. HoloLens 2'de belirteç güvenliği hakkında daha fazla bilgi, Birincil Yenileme [Belirteci (PRT) nedir? içinde paylaşılır.](/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Windows Hello ile cihaz oturum açma

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) doğrudan işletim sisteminde yerleşik olarak bulunan ve kullanıcıların Iris veya PIN kullanarak cihazda oturum açmalarına izin verilen parolasız seçenekler sunar. PIN her zaman kimlik bilgisi olarak kullanılabilir ve cihaz kurulumu için gereklidir, Iris ise isteğe bağlıdır ve atlanabilir. Kullanıcılar, kişisel hesaplarını veya HoloLens Microsoft hesabı hesaplarını kullanarak HoloLens veya [Azure Active Directory *hesabıyla* oturum açmalarını sağlar.](/azure/active-directory/authentication/concept-authentication-passwordless) Bu tür seçenekler kullanıcılara tam güvenlik deneyimi, uygulamalar, veriler, web siteleri ve Windows hızlı ve güvenli erişim sunar. Microsoft'un parolasız deneyimlere yönelik stratejisi burada ayrıntılı olarak açık bir şekilde vemektedir.

Bir Windows Hello kimlik bilgisi oluşturulduğunda, kimlik sağlayıcısıyla güvenilir bir ilişki oluşturur ve kimlik doğrulaması için asimetrik bir anahtar çifti oluşturur. Bir Windows Hello hareketi (iris veya PIN gibi), cihazın Güvenilir Platform Modülü (TPM) yongası tarafından desteklenen bir özel anahtarın şifresini çözmek için entropi sağlar. Bu özel anahtar daha sonra kimlik doğrulama sunucusuna gönderilen istekleri imzalamak ve başarılı bir kimlik doğrulaması sonrasında kullanıcıya posta, resimler ve diğer hesap ayarlarına erişim izni vermek için kullanılır.

Daha fazla bilgi için aşağıdaki bilgi grafiğine bakın:

  ![Windows Hello Oturum açma.](images/security-hello-sign-in.png)
  
Yukarıda sunulan grafikte, nonce ifadesinin "bir kez sayı" ve rastgele veya yarı rastgele oluşturulmuş bir sayı olduğunu unutmayın. Biyometrik Windows Hello PIN kimlik bilgileri ayarlandıktan sonra, sağlandıktan sonra cihazdan asla ayrılmayacak. Kullanıcının kimlik avı Windows Hello gibi bir PIN'i çalınsa bile, kullanıcının fiziksel cihazı olmadan [kullanılamaz.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Daha fazla güvenlik için, Windows Hello kimlik bilgileri Güvenilir Platform Modülü (TPM) tarafından korunarak kimlik bilgilerinin kurcalanmaya karşı dayanıklı ve birden çok yanlış girişe karşı koruma koruması ve kötü amaçlı yazılım koruması ile eklenmiştir. TekLi Kimlik Sign-On Doğrulama (SSO) hakkında daha fazla bilgi için [SSO yöntemlerine genel bakış makalelerini okuyun.](/azure/active-directory/manage-apps/what-is-single-sign-on)

Iris kimlik doğrulaması PIN'e geri döner. Cihazda yeni bir PIN (güçlü bir kimlik doğrulayıcı) ayarlamak için, kullanıcının işlemi tamamlamak için kısa süre önce Çok Faktörlü Kimlik [Doğrulaması(MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) üzerindenmış olması gerekir.

## <a name="single-sign-on-with-web-account-manager"></a>Web Hesabı Yöneticisi ile çoklu oturum açma

Çoklu oturum açma (SSO), parolasız kullanıcıların cihazda kullanıcının kişisel hesabını veya iş ya da okul hesabını kullanarak oturum açmasını sağlar. Kullanıcı, tüm tümleşik uygulama ve hizmetlerde SSO ile otomatik olarak [Web Hesabı Yöneticisi.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Bir uygulama aracılığıyla bir kimlik eklendiktan sonra, kullanıcı onayıyla sistem düzeyinde tümleştirme kullanılarak tüm uygulama ve hizmetler için kullanılabilir hale olabilir. Bu, uygulama oturum açma yükünü önemli ölçüde azaltır ve kullanıcılara sorunsuz bir kimlik deneyimi sağlar.

Web Hesabı Yöneticisi API'lerini uygulama hakkında daha fazla bilgi için Web Hesabı Yöneticisi [api'lerini uygulama'ya gidin.](/windows/uwp/security/web-account-manager)

  ![Güvenlik API'si.](images/security-api-img.png)
  
Özel kimlik doğrulaması gereksinimleri olan uygulama paketleri için Web Hesabı Yöneticisi (WAM) çerçevesi özel kimlik sağlayıcıları tarafından genişletilebilir. Kullanıcılar, bu kimlik sağlayıcısıyla tümleştirilmiş diğer uygulamalarda SSO'Windows etkinleştirmek için Microsoft Store'dan Evrensel Windows Platformu (UWP) uygulaması olarak paketlenmiş özel kimlik sağlayıcısını indirebilir.

Özel WAM Kimlik sağlayıcıları uygulama hakkında daha fazla bilgi için [bkz. Özel WAM Kimlik Sağlayıcısı API başvurusu.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello Ve FIDO2 ile WebAuthn ile oturum açma

HoloLens 2, parolasız kullanıcı kimlik bilgilerini (Windows Hello veya FIDO2 güvenlik anahtarları gibi) kullanarak Microsoft Edge ve WebAuthn'ı destekleyen web sitelerine güvenli bir şekilde oturum açma. FIDO2, kullanıcı kimlik bilgilerinin standartlara dayalı cihazlardan faydalanarak kimlik doğrulaması çevrimiçi hizmetler.

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/) ve FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) belirtimleri hizmetlere uygulanır. WebAuthn ve FIDO2 tarafından belirtilen imzalı meta veriler, kullanıcının mevcut olup olmadığı gibi bilgiler sağlar ve yerel hareketle kimlik doğrulamasını doğrular.

Windows Hello'de olduğu gibi, kullanıcı bir FIDO2 kimlik bilgisi oluşturduğunda ve kaydettirişte cihaz (HoloLens 2 veya FIDO2 güvenlik anahtarı), cihazda özel ve ortak bir anahtar oluşturur. Özel anahtar cihazda güvenli bir şekilde depolanır ve yalnızca biyometrik veya PIN gibi yerel bir hareket kullanılarak kilidi açtırıldıktan sonra kullanılabilir. Özel anahtar depolandığı zaman, ortak anahtar buluttaki Microsoft hesabı sisteme gönderilir ve ilişkili kullanıcı hesabıyla kaydedilir.

MSA ve Azure AD hesabıyla oturum açmanın ardından sistem oluşturulan bir sayı veya veri değişkenlerini HoloLens 2 veya FIDO2 cihazına gönderir. Kimlik HoloLens 2 veya cihaz, kimliği imzalamak için özel anahtarı kullanır. İmzalı kimlik ve meta veriler, Microsoft hesabı ortak anahtar kullanılarak doğrulanır.

Windows Hello ve FIDO2 cihazları, özellikle HoloLens yerleşik ve güvenli Güvenilir Platform Modülü cihaza göre kimlik bilgilerini uygulama. TPM enclave özel anahtarı depolar ve kilidini açmak için biyometrik veya PIN gerektirir. Benzer şekilde FIDO2 güvenlik anahtarı, özel anahtarı depolar ve kilidini açmak için biyometrik veya PIN gerektiren yerleşik güvenli bir yerleşime sahip küçük bir dış cihazdır.

Her iki seçenek de bir adımda iki faktörlü kimlik doğrulaması sunar ve başarıyla oturum açması için hem kayıtlı bir cihaz hem de biyometrik veya PIN gerektirir. Daha fazla bilgi için fiDO2 güvenlik anahtarı ile güçlü kimlik doğrulaması grafiğine ve işlemine bakın.

### <a name="strong-authentication-with-fido2-security-key"></a>FIDO2 güvenlik anahtarı ile Güçlü Kimlik Doğrulaması

  ![FIDO img.](images/security-fido2-whfb-smaller.png)

1. Kullanıcı FIDO2 güvenlik anahtarını HoloLens 2'ye takıyor
1. Windows FIDO2 güvenlik anahtarını algılar
1. HoloLens isteği gönderir
1. Azure AD geri nonce gönderir
1. Kullanıcı, güvenlik anahtarının güvenli yerleşimi içinde özel anahtar depolarının kilidini açmak için hareketi tamamlar
1. FIDO2 güvenlik anahtarı özel anahtarla nonce imzalar
1. İmzalı nonce ile PRT belirteci isteği Azure AD'ye gönderilir
1. Azure AD FIDO anahtarını doğrular
1. Azure AD, kaynaklara erişimi etkinleştirmek için PRT ve TGT döndürür

MSA ve Azure AD, WebAuthn kullanarak parolasız kimlik doğrulamasını destekleyen ilk bağlı olan taraflardır.

WebAuthn'ı uygulamalar ve/veya SDK'lar ile kullanma hakkında daha fazla bilgi için, web üzerinde parolasız kimlik doğrulaması için [WebAuthn API'leri Windows 10.](/windows/security/identity-protection/hello-for-business/webauthnapis)

HoloLens 2, parolasız oturum açma - FIDO2 güvenlik anahtarları için belirtilen özellikleri ve Azure Active Directory gereksinimleri karşılamak için uygulanan [FIDO2 güvenlik](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) cihazlarını destekler.

## <a name="local-accounts"></a>Yerel hesaplar

Çevrimdışı mod dağıtımları için tek bir yerel hesap yalıtabilirsiniz. Yerel hesaplar varsayılan olarak etkin değildir ve cihaz sağlama sırasında yapılandırılması gerekir. Bir parola kullanarak oturum açmaları gerekir ve alternatif kimlik doğrulama [](/windows/security/identity-protection/hello-for-business/hello-overview) yöntemlerini desteklemezler (İş için Windows Hello veya [Windows Hello).](/windows-hardware/design/device-experiences/windows-hello)

Kullanıcı hesaplarının HoloLens daha fazla bilgi için kimlik [HoloLens bulunabilir.](hololens-identity.md)

IT yöneticileri, [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)aracılığıyla kullanıcının e-postayla ilgili olmayan bağlantı kimlik doğrulaması ve hizmetleri için bir MSA hesabı kullanmasına izin verilip kullanmasına izin verilemeyeceklerini ayarlar. Parola yapılandırma ilkeleri, kimlik değiştirme ilkeleri ve kilit ekranı ilkeleri için bkz. [Cihaz Kilidi.](/windows/client-management/mdm/policy-csp-devicelock)
