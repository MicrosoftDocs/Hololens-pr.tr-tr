---
title: dağıtım kılavuzu – Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-hazırlama
description: Dynamics 365 kılavuzlarıyla kurumsal bağlantılı bir ağ üzerinden HoloLens 2 cihaz kaydetmeye hazırlanma hakkında bilgi edinin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033409"
---
# <a name="prepare---corporate-connected-guide"></a>Hazırlama-kurumsal bağlantılı kılavuz
## <a name="infrastructure-essentials"></a>Altyapı temelleri
hem kişisel hem de kurumsal dağıtım senaryolarında, bir mobil cihaz yönetimi (MDM) sistemi, Windows 10 cihazları dağıtmak ve yönetmek için gerekli olan, özellikle de HoloLens 2 ' dir. bir [Azure AD Premium abonelik](/azure/active-directory/fundamentals/active-directory-get-started-premium) , kimlik sağlayıcısı olarak önerilir ve belirli özellikleri desteklemek için **gereklidir** .

> [!NOTE]
> HoloLens 2 bir mobil cihaz gibi dağıtılıp yönetilse de, genellikle birçok kullanıcı arasında paylaşılan bir cihaz olarak kullanılır.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya ıntune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri](https://azure.microsoft.com/documentation/articles/active-directory-editions)). tüm sürümler Azure AD cihaz kaydını destekler, ancak bu kılavuzda daha sonra kullanabilmemiz için MDM otomatik kaydını etkinleştirmek üzere Premium P1 gerekir.
> [!Important]
> HoloLens cihazlar şirket içi AD birleştirmeyi desteklemediğinden Azure ad 'nin olması önemlidir. Henüz bir Azure AD kurulumu yoksa, kullanmaya başlamak ve [Azure Active Directory yeni bir kiracı oluşturmak](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)için yönergeleri izleyin.

## <a name="identity-management"></a>Kimlik Yönetimi
Bu kılavuzda, kullanılan [kimlik](/hololens/hololens-identity) Azure AD hesapları olacaktır. Azure AD hesaplarının çeşitli avantajları vardır, örneğin:

- çalışanlar, cihazı azure ad 'ye kaydetmek için azure ad hesabını kullanır ve bunu kuruluşun MDM çözümüne otomatik olarak kaydedebilir (Azure AD + MDM – bir [Azure AD Premium aboneliği](/azure/active-directory/fundamentals/active-directory-get-started-premium)gerektirir).
- Azure AD hesapları, [iş için Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)ek [kimlik doğrulama seçeneklerine](/hololens/hololens-identity) sahiptir. Iris oturum açma 'ya ek olarak, kullanıcılar başka bir cihazdan oturum açabilir veya FIDO güvenlik anahtarlarını kullanabilir.

> [!WARNING] 
> Çalışanlar, bir cihazı başlatmak için yalnızca bir hesap kullanabilir, böylece **Kuruluşunuz öncelikle hangi hesabın etkinleştirildiğini denetliyorsa zorunludur**. Seçilen hesap, cihazı kimin denetlediğini ve yönetim olanaklarınızı etkilediğini belirleyecek.

## <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi
Microsoft Intune, Enterprise Mobility + Security bir parçası, kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Office 365 gibi, ıntune kimlik yönetimi için Azure AD 'yi kullanır, bu nedenle çalışanlar, ıntune 'a Office 365 oturum açmak için kullandıkları cihazları kaydetmek için aynı kimlik bilgilerini kullanır. Intune Ayrıca, tüm MDM çözümünü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları destekler. bu kılavuzun amaçları doğrultusunda, HoloLens 2 ile iç ağınıza bir dağıtımı etkinleştirmek için ıntune 'u kullanmaya odaklanacağız.
> [!Important] 
> Mobil cihaz yönetiminin olması önemlidir. Henüz ayarlanmamışsa, bu kılavuzu izleyin ve Intune ile çalışmaya başlayın.

> [!Important]
> Kılavuzların kullanılabilmesi için bir Azure AD hesabı gereklidir.

> [!Note] 
> birden çok MDM sistemi Windows 10 destekler ve çoğu kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. Windows 10 Holographic destekleyen MDM sağlayıcıları şunlardır: airwatch, mobileıron ve diğerleri. Sektörde önde gelen MDM satıcıları, Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure [Market](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)'TE Azure AD 'yi destekleyen en güncel MDM satıcıları listesini bulabilirsiniz.

## <a name="network-access"></a>Ağ erişimi 
Dynamics 365 kılavuzlar, bulut tabanlı bir uygulamadır. Ağ yöneticinizin bir onay listesi varsa, Dynamics 365 sunucularına bağlanmak için gereken IP adreslerini ve/veya uç noktaları eklemesi gerekebilir. [IP adreslerinin ve URL 'lerin engellemesini kaldırma hakkında daha fazla bilgi edinin](/power-platform/admin/online-requirements#ip-addresses-and-urls).

## <a name="certificates"></a>Sertifikalar
Sertifikalar, Web içeriğinin hesap kimlik doğrulaması, Wi-Fi kimlik doğrulaması, VPN şifrelemesi ve SSL şifrelemesi sağlayarak güvenliği artırmaya yardımcı olur. Yöneticiler, cihazlarda cihazları sağlama paketleri aracılığıyla el ile yönetebilse de, bu sertifikaları tüm yaşam döngülerinde (yenileme ve iptal etme yoluyla) yönetmek için MDM sisteminizi kullanmak en iyi uygulamadır. 

MDM sisteminiz, kaydolduktan sonra bu sertifikaları cihazların sertifika depolarına otomatik olarak dağıtabilir (MDM sisteminiz **basit sertifika kayıt Protokolü (SCEP)** veya **ortak anahtar şifreleme STANDARTLARıNı #12 (PKCS # 12)**) destekler. [Microsoft Intune ile kullandığınız sertifika türleri ve profiller hakkında bilgi edinin](/mem/intune/protect/certificates-configure). MDM, kayıtlı istemci sertifikalarını sorgulayabilir ve silebilir ya da geçerli sertifikanın süre dolmadan önce yeni bir kayıt isteği tetikleyebilirsiniz.

MDM sistemleriniz zaten sertifikalar için yapılandırılmışsa, HoloLens 2 cihazlarınıza yönelik sertifikaları ve profilleri dağıtmaya başlamak için [HoloLens 2 için sertifika hazırlama ve ağ profilleri](/hololens/hololens-certificates-network) başvurusu yapın.

## <a name="scep"></a>SCEP

Web uygulaması ara sunucusu dışında, SCEP dağıtımı için aşağıdaki hizmetler gereklidir.

- [Sertifika Yetkilisi](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES sunucusu rolü](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Bağlayıcısı](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Ayrıca, [Azure AD uygulama proxy 'sini veya Web erişimi proxy](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application)'yi kullanarak, şirket AĞıNıZA AIT NDES URL 'nizi de yayımlamanız gerekir. Seçtiğiniz başka bir ters proxy de kullanabilirsiniz.

![SCEP veri akışı.](./images/hololens2-scep-info-flow.png)

Ağınız zaten SCEP desteklemiyorsa veya ağınızın Intune ile SCEP için doğru şekilde ayarlandığından emin değilseniz, başvuru  [için altyapıyı Intune Ile SCEP destekleyecek şekilde yapılandırın](/mem/intune/protect/certificates-scep-configure).

altyapınız zaten SCEP destekliyorsa, HoloLens 2 ' nin kullanacağı her bir SCEP sertifikası için bir [profil](/mem/configmgr/protect/deploy-use/create-certificate-profiles) [oluşturmanız](/mem/intune/protect/certificates-profile-scep) gerekir. SCEP ile ilgili sorun yaşıyorsanız, [Microsoft Intune sertifikaları sağlamak IÇIN SCEP Sertifika profillerinin kullanımıyla Ilgili sorunları giderin](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)' i kullanın.

## <a name="pkcs"></a>PKCS
Intune Ayrıca özel ve ortak anahtar çifti (PKCS) sertifikalarının kullanımını da destekler. başvuru daha fazla bilgi için [Microsoft Intune özel ve ortak anahtar sertifikaları kullanın](/mem/intune/protect/certificates-pfx-configure) .

## <a name="proxy"></a>Ara sunucu
Çoğu kurumsal intranet ağı dış trafiği yönetmek için bir proxy 'den yararlanır. HoloLens 2 ' de, ethernet, Wi-Fi ve VPN bağlantıları için bir proxy sunucu yapılandırabilirsiniz.

Birkaç farklı proxy türü ve proxy 'yi yapılandırmaya yönelik yollar vardır. Bu kılavuzun amaçları doğrultusunda, **Wi-Fi proxy 'si seçme, Pac URL 'si aracılığıyla ayarlama ve MDM aracılığıyla dağıtılan** bir işlem yaptık. Bu, MDM aracılığıyla dağıtılmasının avantajları ile birlikte sunucu: bağlantı noktası yapılandırması yerine PAC dosyasını güncelleştirebilmekte ve son olarak yalnızca tek bir Wi-Fi bağlantı için kullanılmak üzere proxy 'yi yapılandırmak için Wi-Fi proxy kullanarak, cihazların hala başka bir konuma bağlanması durumunda kullanılmasına izin verir.

Windows 10 ara sunucu ayarları hakkında daha fazla bilgi için bkz. [Microsoft Intune-Azure 'da cihazlar için Wi-Fi profili oluşturma](/mem/intune/configuration/wi-fi-settings-configure).

## <a name="line-of-business-apps"></a>Iş kolu uygulamaları 
Microsoft Store aracılığıyla birkaç uygulama yüklenebilmesine karşın, büyük olasılıkla karma gerçeklik 'te kullanmak için oluşturduğunuz özel uygulamanız olabilir. İşletmeniz için kuruluşunuz genelinde dağıtılan bu özel uygulamalar, Iş kolu (LOB) uygulamaları olarak adlandırılır.
  
HoloLens 2 cihazlara uygulama dağıtmanın birden çok yolu vardır. uygulamalar doğrudan MDM, İş İçin Microsoft Store (msfb) veya bir sağlama paketi aracılığıyla yüklenen dışarıdan dağıtılabilir. Bu kılavuzun sau için, gerekli uygulama yüklemesi aracılığıyla uygulamaları MDM aracılığıyla dağıtacağız. bu, kayıt tamamlandıktan sonra LOB uygulamalarınızın HoloLens cihazlarınıza otomatik olarak yüklenmesine olanak sağlar.

Kendi LOB 'ınızla olmayan, bu dağıtım akışını test etmek için örnek bir uygulama sunuyoruz. Bu uygulama [mrtk örnekleri](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) uygulaması olacak ve zaten önceden oluşturulmuş ve kavram kanıtı için test edecek şekilde paketlenmiş.

Uygulama dağıtımı ile ilgili daha fazla ayrıntı için [uygulama yönetimi: genel bakış](/hololens/app-deploy-overview).

> [!NOTE]
> HoloLens 2, yalnızca UWP ARM64 uygulamalarının çalıştırılmasını destekler.

## <a name="guides-playbook"></a>Kılavuzlar PlayBook
Kılavuzlar, kılavuzlar uygulamalarınız için veri deposu olarak bir Microsoft veri deposu ortamı kullanır. Veri deposu ortamınızın kılavuzlarınız ve kiracınız ile nasıl etkileşime gireceğini daha büyük bir resmin anlaşılması önemlidir. Bu kılavuzda veri kapsayıtlarınızın nasıl yönetileceğini kapsamayacağız, ancak lütfen [dynamics 365 kılavuzlarını dağıtmaya yönelik temel kavramları gözden geçirin-dynamics 365 karma gerçeklik](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantı dağıtımı-yapılandırma](hololens2-corp-connected-configure.md)