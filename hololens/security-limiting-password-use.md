---
title: Parola kullanımını sınırlandırma
description: HoloLens için parola kullanımını sınırlandırma
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Güvenlik, Hololens, parola kullanımını sınırlandırma, parola, Hololens parola, oturum açma, oturum açma, Windows Hello, Merhaba, Windows hesap yöneticisi, FIDO2 oturum açma, FIDO 2, WEBAUTHN, yerel hesap, Hololens güvenliği
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a4ceaa1a741ec63153cd9112d04547165b46b0fa72c32ee7f9580f15368a2f88
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665491"
---
# <a name="limiting-password-use"></a>Parola kullanımını sınırlandırma

Günümüzde çoğu bilgisayar sistemi, Kullanıcı tarafından oluşturulan ve Kullanıcı tarafından oluşturulan parolalara bağımlı hale getirme güvenliği için temel olarak Kullanıcı kimlik bilgilerini kullanır. Bu, parolaların hesap güvenliğinin aşılmasına ve veri ihlallerinin en yaygın nedenlerine neden oldu. Buna örnek olarak, parolalar bir sunucudan iletilmek veya çalınarak (sızdırma veya parola püskürtme saldırılarına karşı) ve bir kullanıcı hesabına erişim sağlamak için güvenliği tehlikeye girebilir.

güvenlik ve hesap korumasını artırmak için, HoloLens 2 cihaz oturum açma için güçlü, donanım tarafından desteklenen "parola-daha az" kimlik bilgilerini (Windows Hello dahil) etkinleştirme yeteneğine sahiptir ve Microsoft bulutuna sorunsuz erişim sunar.

## <a name="signing-in-from-another-device"></a>Başka bir cihazdan oturum açma

HoloLens 2, ilk cihaz kurulumu sırasında Azure Active Directory iş hesapları için uzak cihaz oturum açma seçenekleri sunar ve kullanıcı oturum açarak karmaşık parola yazma ihtiyacını azaltır ve kimlik bilgileri olarak parola ihtiyacını en aza indirir. kimlik doğrulaması için akıllı kartlar kullanan kullanıcılar ve kuruluşlar, HoloLens 2 gibi cihazlarda bu kimlik bilgilerini kullanmada zorluk göstermektedir ve genellikle kuruluşlar, sorunu geçici olarak çözmek için karmaşık sistemler ve maliyetli süreçler geliştirir. bu sorunu çözmek için, Azure AD HoloLens 2 ' de parola-daha az oturum açma için iki seçenek sunar.

ilk kimlik doğrulama yöntemi, bir cihaza bağlı kullanıcı kimlik bilgilerini sağlayan anahtar tabanlı kimlik doğrulaması sağlamak için Microsoft Authenticator uygulamasındaki yeni özellikleri kullanır. yönetici tarafından kiracı üzerinde etkinleştirildikten sonra kullanıcılara, HoloLens cihaz kurulumu sırasında bir ileti gösterilir. daha sonra kimlik doğrulayıcı uygulamasındaki numarayla eşleşmesi gerekir, onayla ' yı seçin, pın 'ini veya bir biyometri ve HoloLens kurulum işleminin devam edebilmesi için bir biyometrik ve kimlik doğrulamasını sağlayın. Bu, [parolasız oturum açma](/azure/active-directory/authentication/howto-authentication-passwordless-phone)bölümünde daha ayrıntılı olarak açıklanmıştır.

İkincisi, kullanıcılara sezgisel olan ve ek bir altyapı gerektirmeyen bir cihaz kod akışdır.  bu uzaktan oturum açma davranışı, kuruluşun tercih ettiği kimlik doğrulama mekanizmasını destekleyen başka bir güvenilen cihaza dayanır ve tamamlandığında, oturum açma veya cihaz kurulumunu tamamlayacak belirteçleri HoloLens geri gönderilir. Bu akıştaki adımlar şunlardır:

  1. OOBE 'deki ilk cihaz kurulumu veya oturum açma akışlarından geçen bir Kullanıcı, "başka bir cihazdan oturum açma" bağlantısı ve bunun üzerine dokunmasıyla sunulur. Bu, uzaktan oturum açma oturumu başlatır.
  1. Daha sonra Kullanıcı, [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Azure AD güvenli belirteç hizmeti 'nin (STS) cihaz kimlik doğrulama uç noktasını işaret eden kısa bır URI () içeren bir yoklama sayfası gösterilir. Kullanıcı aynı zamanda bulutta güvenli bir şekilde oluşturulan ve 15 dakikalık en yüksek yaşam süresine sahip bir kerelik kod ile sunulur. Azure AD, kod oluşturma ile birlikte, önceki adımda uzaktan oturum açma isteği başlatma sonrasında şifrelenmiş bir oturum oluşturur ve birlikte, uzaktan oturum açma isteğini onaylamak için URI ve kod kullanılır.
  1. daha sonra kullanıcı başka bir cihazdan urı 'ye gider ve HoloLens 2 cihazında görüntülenecek kodu girmesi istenir.
  1. kullanıcı koda girdiğinde Azure AD STS, kullanıcının uzaktan oturum açma isteğini tetiklediği ve kodun oluşturulmasını isteyen HoloLens 2 cihazını gösteren bir sayfa görüntüler. Daha sonra kullanıcının kimlik avı saldırılarını önlemeyi onaylaması istenir.
  1. Kullanıcı, görüntülenmiş ' uygulama ' üzerinde oturum açmaya devam etmeyi seçerse, Azure AD STS kullanıcıdan kimlik bilgilerini ister. Başarılı kimlik doğrulaması sırasında Azure AD STS, önbelleğe alınmış uzak oturumu bir yetkilendirme koduyla birlikte ' onaylandı ' olarak güncelleştirir.
  1. son olarak, kullanıcının HoloLens 2 cihazındaki yoklama sayfası, Azure AD 'den ' yetkilendirilmiş ' bir yanıt alır ve kullanıcı kodunu, ilişkili depolanan yetkilendirme kodunu doğrulamaya devam eder ve cihaz kurulumunu tamamlamanın istendiği şekilde OAuth belirteçleri oluşturur. Oluşturulan kimlik doğrulama belirteci 1 saat için geçerlidir ve yenileme belirtecinin ömrü 90 gün olur.

Bu akışta kullanılan kod oluşturma ve şifreleme algoritmalarının her ikisi de FIPS uyumludur. HoloLens 2 cihaz, cihaz anahtarlarının güvenliğini sağlamak ve donanım korumalı anahtarlar kullanılarak kullanıcı kimlik doğrulamasından sonra oluşturulan belirteçleri şifrelemek için TPM 'yi kullanır. HoloLens 2 ' deki belirteç güvenliği hakkında daha fazla bilgi [, birincil yenileme belirteci (prt)](/azure/active-directory/devices/concept-primary-refresh-token)ile paylaşılır.

## <a name="device-sign-in-with-windows-hello"></a>Windows Hello ile cihaz oturum açma

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) , doğrudan işletim sisteminde yerleşik olarak bulunan ve kullanıcılara ıris veya pın kullanarak cihazda oturum açmalarına izin veren parola içermeyen seçenekler sunar. PIN, her zaman bir kimlik bilgisi olarak kullanılabilir ve cihaz kurulumu için gereklidir, Iris isteğe bağlıdır ve atlanabilir. kullanıcılar, [bir parola girmeden kişisel Microsoft hesabı veya Azure Active Directory iş hesabını  ](/azure/active-directory/authentication/concept-authentication-passwordless)kullanarak cihaz HoloLens oturum açabilirler. bu teklif kullanıcıları gibi seçenekler, tam Windows deneyimine, uygulamalarına, verilerine, web sitelerine ve hizmetlerine güvenli bir şekilde erişebilir. Microsoft 'un parolasız deneyimlere yönelik stratejisi burada ayrıntılı olarak verilmiştir.

Windows Hello kimlik bilgileri oluşturulduğunda, kimlik sağlayıcısıyla güvenilir bir ilişki kurar ve kimlik doğrulaması için asimetrik bir anahtar çifti oluşturur. Windows Hello hareketi (ıris veya PIN gibi), cihazın Güvenilir Platform Modülü (TPM) yongası tarafından desteklenen özel bir anahtarın şifresini çözmek için entropi sağlar. Bu özel anahtar daha sonra kimlik doğrulama sunucusuna gönderilen isteklerin imzalanmasından ve başarıyla kimlik doğrulamasından sonra, kullanıcıya posta, resim ve diğer hesap ayarlarına erişim izni verildiği için kullanılır.

Daha fazla bilgi için aşağıdaki bilgi grafiğine bakın:

  ![Windows Hello Oturum açma](images/security-hello-sign-in.png)
  
Yukarıda sunulan grafikte, nonce 'in "bir kez sayı" olduğunu ve rastgele veya yarı rastgele oluşturulmuş bir sayı olduğunu unutmayın. Windows Hello biyometri veya pın kimlik bilgileri kurulduktan sonra, üzerinde sağlanmakta olan cihazdan ayrılmayın. kullanıcının Windows Hello pın 'i çalınsa bile, bir kimlik avı saldırısında olduğu gibi, [kullanıcının fiziksel cihazı olmadan](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)bu kullanılamaz.

ek güvenlik için Windows Hello kimlik bilgileri Güvenilir Platform Modülü (TPM) tarafından korunmaktadır. bu kimlik bilgileri, birden fazla hatalı girişe karşı korumalı koruma korumalarının yanı sıra kötü amaçlı yazılım koruması ve pozlamayı engellemek için kötü amaçlı yazılımdan koruma sağlar. Tek Sign-On (SSO) hakkında daha fazla bilgi için, [SSO yöntemlerine genel bakış](/azure/active-directory/manage-apps/what-is-single-sign-on)konusunu okuyun.

Iris kimlik doğrulaması, PIN 'e geri döner. Cihazda yeni bir PIN (güçlü bir kimlik doğrulayıcı) ayarlamak için, kullanıcının işlemi tamamlaması için yakın zamanda [çok faktörlü Authentication (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) üzerinden geçmiş olması gerekir.

## <a name="single-sign-on-with-web-account-manager"></a>Web hesabı Yöneticisi ile çoklu oturum açma

Çoklu oturum açma (SSO), kullanıcıların kişisel hesabını veya iş veya okul hesabını kullanarak cihazda oturum açmasına olanak tanır. Kullanıcı, [Web hesabı Yöneticisi API 'leri](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)aracılığıyla tüm tümleşik uygulamalarda ve hizmetlerde SSO ile otomatik olarak yetkilendirilir.

Bir uygulama aracılığıyla bir kimlik eklendikten sonra, kullanıcı onayı ile sistem düzeyi tümleştirme kullanılarak tüm uygulamalar ve hizmetler için kullanılabilir hale gelir. Bu, uygulama oturum açma yükünü önemli ölçüde azaltır ve kullanıcılara sorunsuz bir kimlik deneyimi sağlar.

Web hesabı Yöneticisi API 'Leri uygulama hakkında daha fazla bilgi için, [Web hesabı Yöneticisi API 'Leri uygulama](/windows/uwp/security/web-account-manager)' ya gidin.

  ![Güvenlik API 'SI](images/security-api-img.png)
  
Özelleştirilmiş kimlik doğrulama gereksinimlerine sahip uygulama paketleri için, web hesabı Yöneticisi (WAM) çerçevesi özel kimlik sağlayıcılarına göre genişletilebilir. kullanıcılar, bu kimlik sağlayıcısıyla tümleştirilmiş diğer uygulamalarda SSO 'yu etkinleştirmek için, Microsoft Store Evrensel Windows Platformu (UWP) uygulaması olarak paketlenmiş özel kimlik sağlayıcısını indirebilir.

Özel WAM kimlik sağlayıcıları uygulama hakkında daha fazla bilgi için bkz. [özel WAM kimlik sağlayıcısı API başvurusu](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello ve FIDO2 ile oturum açma

HoloLens 2, web 'de Microsoft Edge ve WebAuthn 'yi destekleyen web siteleri aracılığıyla güvenli bir şekilde oturum açmak için parola-daha az kullanıcı kimlik bilgilerini (Windows Hello veya FIDO2 güvenlik anahtarları gibi) kullanabilir. FIDO2, Kullanıcı kimlik bilgilerinin çevrimiçi hizmetler kimlik doğrulaması için standartlara dayalı cihazlardan yararlanmasını sağlar.

> [!Note]
> [WebAuthn](https://www.w3.org/TR/webauthn/) ve FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) özellikleri, hizmetler 'e uygulanır. WebAuthn ve FIDO2 tarafından belirtilen imzalı meta veriler, kullanıcının mevcut olup olmadığı gibi bilgileri sağlar ve yerel hareket aracılığıyla kimlik doğrulamasını doğrular.

Windows Hello olduğu gibi, kullanıcı bir FIDO2 kimlik bilgisi oluşturup kaydettiğinde cihaz (HoloLens 2 veya FIDO2 güvenlik anahtarı), cihazda özel ve ortak bir anahtar oluşturur. Özel anahtar cihazda güvenli bir şekilde depolanır ve yalnızca bir biyometri veya PIN gibi yerel bir hareket kullanılarak kilidi açıldıktan sonra kullanılabilir. Özel anahtar depolandığında, ortak anahtar buluttaki Microsoft hesabı sistemine gönderilir ve ilişkili kullanıcı hesabına kaydedilir.

bir MSA ve Azure AD hesabıyla oturum açtıktan sonra, sistem HoloLens 2 veya FIDO2 cihazına bir üretilen sayı veya veri değişkeni gönderir. HoloLens 2 veya cihaz, tanımlamayı imzalamak için özel anahtarı kullanır. İmzalı tanımlama ve meta veriler Microsoft hesabı sistemine geri gönderilir ve ortak anahtar kullanılarak doğrulanır.

Windows Hello ve FIDO2 cihazları, özel olarak yerleşik Güvenilir Platform Modülü güvenli şifreleme gibi HoloLens cihaza göre kimlik bilgilerini uygular. TPM şifrelemesi özel anahtarı depolar ve kilidini açmak için bir biyometri ya da PIN gerektirir. Benzer şekilde, FIDO2 güvenlik anahtarı, özel anahtarı depolayan ve bir biyometri veya PIN 'in kilidini açmak için bir yerleşik güvenli kuşatma içeren küçük bir dış aygıttır.

Her iki seçenek de iki öğeli kimlik doğrulamayı tek bir adımda sunar, hem kayıtlı bir cihazın hem de bir biyometri veya PIN 'in başarıyla oturum açmasını gerektirir. Daha fazla bilgi için, aşağıdaki FIDO2 güvenlik anahtarı grafiği ve işlemiyle güçlü kimlik doğrulaması konusuna bakın.

### <a name="strong-authentication-with-fido2-security-key"></a>FIDO2 güvenlik anahtarıyla güçlü kimlik doğrulaması

  ![FıDO img](images/security-fido2-whfb-smaller.png)

1. kullanıcı FIDO2 güvenlik anahtarını HoloLens 2 ' ye takar
1. Windows FIDO2 güvenlik anahtarını algılar
1. HoloLens auth isteği gönderir
1. Azure AD, geri nonce gönderir
1. Kullanıcı güvenlik anahtarının güvenli şifreliğine özel anahtar depolarının kilidini açma hareketini tamamlar
1. FIDO2 güvenlik anahtarı, anahtar nonce 'yi özel anahtarla imzalar
1. İmzalı nonce ile PRT belirteci isteği Azure AD 'ye gönderiliyor
1. Azure AD, FIDO anahtarını doğrular
1. Azure AD, kaynaklara erişimi etkinleştirmek için PRT ve TGT 'yi döndürür

MSA ve Azure AD, WebAuthn 'yi uygulayarak parola daha az kimlik doğrulamasını destekleyen ilk bağlı olan taraflardır.

Uygulama ve/veya SDK 'Lar ile WebAuthn kullanma hakkında daha fazla bilgi için, [Windows 10 üzerinde parola açısından daha az kimlik doğrulama Için WebAuthn API 'lerine](/windows/security/identity-protection/hello-for-business/webauthnapis)gidin.

HoloLens 2, FIDO2 Azure Active Directory ' ye uygulanan ve [passwordless oturum açma-FIDO2 güvenlik anahtarlarının](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) desteklenmesinin gerekli olduğu gereksinimleri karşılayan güvenlik cihazlarını destekler.

## <a name="local-accounts"></a>Yerel hesaplar

Tek bir yerel hesap, çevrimdışı mod dağıtımları için yapılandırılabilir. Yerel hesaplar varsayılan olarak etkin değildir ve cihaz sağlama sırasında yapılandırılması gerekir. parola kullanarak oturum açması gerekir ve alternatif kimlik doğrulama yöntemlerini ( [örneğin Windows Hello iş](/windows/security/identity-protection/hello-for-business/hello-overview) veya [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)) desteklemezler.

HoloLens kullanıcı hesapları hakkında daha fazla ayrıntı [HoloLens kimlik](hololens-identity.md)üzerinde bulunabilir.

BT yöneticileri, kullanıcının e-posta ile ilgili olmayan bağlantı kimlik doğrulaması ve hizmetleri için [Allowmicrosoftaccountconnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection)aracılığıyla bir MSA hesabı kullanmasına izin verilip verilmeyeceğini ayarlar. Parola yapılandırma ilkeleri, sayaç oluşturma ilkeleri ve kilit ekranı ilkeleri için bkz. [cihaz kilitleme](/windows/client-management/mdm/policy-csp-devicelock).
