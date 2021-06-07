---
title: Dağıtım Kılavuzu – Dynamics 365 Kılavuzları ile kurumsal bağlantılı HoloLens 2 - Hazırlama
description: Dynamics 365 Kılavuzları ile kurumsal bağlantılı bir ağ üzerinden HoloLens 2 cihazlarını kaydetmeye hazırlanmayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379054"
---
# <a name="prepare---corporate-connected-guide"></a>Hazırlama - Kurumsal Bağlantılı Kılavuz
## <a name="infrastructure-essentials"></a>Altyapı TemelLeri
Hem kişisel hem de kurumsal dağıtım senaryolarında Mobil Cihaz Yönetimi (MDM) sistemi, özellikle HoloLens 2 olmak üzere Windows 10 cihazları dağıtmak ve yönetmek için gereken temel altyapıdır. Bir [Azure AD Premium bir](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) kimlik sağlayıcısı olarak önerilir ve belirli **özellikleri** desteklemek için gereklidir.

> [!NOTE]
> HoloLens 2 bir mobil cihaz gibi dağıtılıyor ve yönetiliyor olsa da, genellikle birçok kullanıcı arasında paylaşılan bir cihaz olarak kullanılır.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya Intune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: Ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tüm sürümler Azure AD cihaz kaydını destekler, ancak MDM otomatik kaydını etkinleştirmek için Premium P1 gereklidir. Bunu daha sonra bu kılavuzda kullanacağız.
> [!Important]
> HoloLens cihazları şirket içi AD'ye katılmayı desteklemez. Azure AD'ye sahip olmak önemlidir. Henüz bir Azure AD ayarlamadıysanız, çalışmaya başlama yönergelerini izleyin ve azure'da [yeni bir kiracı Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Kimlik Yönetimi
Bu kılavuzda kullanılan [kimlik](https://docs.microsoft.com/hololens/hololens-identity) Azure AD hesaplarıdır. Azure AD hesaplarının çeşitli avantajları vardır, örneğin:
- Çalışanlar, cihazı Azure AD'ye kaydetmek için Azure AD hesabını kullanır ve cihazı kuruluşun MDM çözümüne otomatik olarak kaydedebiliyor (Azure AD+MDM– bir Azure AD Premium [aboneliği gerektirir).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD hesaplarının, kimlik doğrulaması [aracılığıyla ek kimlik](https://docs.microsoft.com/hololens/hololens-identity) [İş İçin Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris oturum açmanın yanı sıra, kullanıcılar başka bir cihazdan oturum açabilirsiniz veya FIDO güvenlik anahtarlarını kullanabilir.

> [!WARNING] 
> Çalışanlar bir cihazı başlatmak için yalnızca bir hesap kullanabilir. Bu nedenle, önce hangi hesabın **etkinleştirildiğinden kuruluşta denetime sahip olması gerekir.** Seçilen hesap, cihazı kimin kontrol altında olduğunu belirler ve yönetim özelliklerinizi etkiler.

## <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi
Microsoft Intune bir Enterprise Mobility + Security, kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Office 365'te olduğu gibi, Intune da kimlik yönetimi için Azure AD kullanır. Bu nedenle, çalışanlar, Office 365'te oturum atırken kullandığı cihazları Intune'a kaydetmek için aynı kimlik bilgilerini kullanır. Intune, eksiksiz bir MDM çözümü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları da destekler. Bu kılavuzun amaçları doğrultusunda, HoloLens 2 ile iç ağınıza dağıtım yapmak için Intune'u kullanmaya odaklanmış oluruz.
> [!Important] 
> Mobile Cihaz Yönetimi. Henüz ayarlamadıysanız bu kılavuzu izleyin ve Intune ile Kullanmaya başlayın izleyin.

> [!Important]
> Kılavuzları kullanmak için bir Azure AD hesabı gerekir.

> [!Note] 
> Birden çok MDM sistemi, Windows 10 ve çoğu da kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. Bu hizmeti destekleyen MDM Windows 10 Holographic şunlardır: AirWatch, MobileIron ve diğerleri. Sektör lideri MDM satıcılarının çoğu Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure AD'i destekleyen MDM satıcılarının en güncel listesini [Azure Market.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Ağ Erişimi 
Dynamics 365 Kılavuzları, bulut tabanlı bir uygulamadır. Ağ yöneticinizin bir onaylama listesi varsa, Dynamics 365 sunucularına bağlanmak için gereken IP adreslerini ve/veya uç noktaları eklemesi gerekebilir. [IP adreslerinin ve URL'lerin engelini kaldırma hakkında daha fazla bilgi.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Sertifikalar
Sertifikalar, web içeriğinin hesap kimlik doğrulaması, Wi-Fi, VPN şifrelemesi ve SSL şifrelemesi sağlayarak güvenliğin iyileştirilmesine yardımcı olur. Yöneticiler, sağlama paketleri aracılığıyla cihazlardaki sertifikaları el ile yönetese de, kayıttan yenileme ve iptale kadar tüm yaşam döngüsü boyunca bu sertifikaları yönetmek için MDM sisteminizi kullanmak en iyi uygulamadır. 

MDM sisteminiz, bu sertifikaları kaydettikten sonra cihazların sertifika depolarına otomatik olarak dağıtabilirsiniz (MDM sisteminiz **Basit Sertifika Kayıt Protokolü (SCEP)** veya Ortak Anahtar Şifreleme Standartları #12 **(PKCS #12) destekler).** [ile birlikte kullanabileceğiniz sertifika türleri ve profilleri hakkında bilgi Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-configure) MDM ayrıca kayıtlı istemci sertifikalarını sorgular ve silebilir veya geçerli sertifikanın süresi dolmadan önce yeni bir kayıt isteği tetikler.
 
MDM sistemleriniz sertifikalar için zaten yapılandırılmışsa HoloLens 2 cihazlarınız için sertifika ve profil dağıtmaya başlamak üzere [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) için sertifikaları ve ağ profillerini hazırlama'ya bakın.

## <a name="scep"></a>SCEP

Web Sunucusu dışında SCEP dağıtımı için aşağıdaki hizmetler Uygulama Ara Sunucusu.
- [Sertifika Yetkilisi](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES Sunucusu rolü](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Bağlayıcısı](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Ayrıca NDES URL'nizi Azure AD uygulama ara sunucusu veya sunucu ara sunucusu kullanarak [şirket Web Erişimi yayımlamanız gerekir.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Ayrıca, tercihen başka bir ters ara sunucu da kullanabilirsiniz.

![SCEP veri akışı](./images/hololens2-scep-info-flow.png)

Ağınız zaten SCEP'yi desteklemezse veya ağın Intune ile SCEP için doğru ayar olup olmadığını emin değilseniz,  [Altyapıyı Intune ile SCEP'yi](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)destekleyecek şekilde yapılandırma'ya başvurun.

Altyapınız zaten SCEP'yi destekliyorsa, [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) HoloLens 2'nin kullanabileceği her SCEP sertifikası için bir profil oluşturmanız gerekir. [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) SCEP ile ilgili sorunlarınız varsa, sertifikalar için [SCEP](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)sertifika profillerini kullanarak sertifika sağlama sorunlarını Microsoft Intune.

## <a name="pkcs"></a>PKCS
Intune, özel ve ortak anahtar çifti (PKCS) sertifikalarının kullanımını da destekler. Daha [fazla bilgi için özel ve ortak anahtar Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) kullanın.

## <a name="proxy"></a>Ara sunucu
Çoğu kurumsal intranet ağı dış trafiği yönetmek için bir ara sunucudan faydalanmaktadır. HoloLens 2 ile Ethernet, sanal ağ ve VPN bağlantıları için Wi-Fi sunucu yapılandırabilirsiniz.

Birkaç farklı ara sunucu türü ve ara sunucu yapılandırmanın yolları vardır. Bu kılavuzun amaçları doğrultusunda Wi-Fi ara sunucusunu seçmeyi, PAC URL'si aracılığıyla ayarlamayı ve **MDM aracılığıyla dağıtılmasını tercih ediyoruz.** Bu, MDM aracılığıyla otomatik olarak dağıtılmasının, sunucu:bağlantı noktası yapılandırması yerine PAC dosyasını güncelleştirenin ve son olarak ara sunucuyu yalnızca tek bir Wi-Fi bağlantısına uygulanacak şekilde yapılandırmak için Wi-Fi proxy'sini kullanarak cihazların başka bir konumda bağlı olması durumda hala kullanılmaktadır. 


Windows 10 proxy ayarları hakkında daha fazla bilgi için bkz. Microsoft Intune - Azure'da cihazlar için [Wi-Fi profili oluşturma.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>İş Hattı Uygulamaları 
Microsoft Store aracılığıyla birkaç uygulama yüklenene kadar, karma gerçeklikte kullanmak için özel olarak oluşturduğunuz kendi özel uygulamanız olabilir. İşletmeniz için kuruluş genelinde dağıtılan bu özel uygulamalara İş Hattı (LOB) uygulamaları denir.
  
HoloLens 2 cihazlarına uygulama dağıtmanın birden çok yolu vardır. Uygulamalar doğrudan MDM, İş İçin Microsoft Store (MSfB) aracılığıyla dağıtılabilir veya Sağlama Paketi aracılığıyla yüklenebilir. Bu kılavuz için, gerekli uygulama yüklemesini kullanarak uygulamaları MDM aracılığıyla dağıtacak. Bu, LOB uygulamalarınızı kaydetmeyi bitirdikten sonra HoloLens cihazlarınıza otomatik olarak indirmenizi sağlar.

Kendi LOB'niz yoksa, bu dağıtım akışını test etmek için bir örnek uygulama sağlariz. Bu uygulama [MRTK Örnekleri](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) uygulaması olacak ve kavram kanıtı test etmek için önceden oluşturulmuş ve paketlenmiştir.
 
Uygulama dağıtımıyla ilgili diğer ayrıntılar Uygulama [Yönetimi: Genel Bakış'a bakın.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 yalnızca UWP ARM64 uygulamalarının çalıştırmayı destekler.

## <a name="guides-playbook"></a>Kılavuzlar Playbook
Kılavuzlar, Kılavuzlar uygulamalarınız için veri deposu olarak bir Microsoft Dataverse ortamı kullanır. Dataverse ortamının Kılavuzlar uygulamalarınız ve kiracınız ile nasıl etkileşim kurduğuyla ilgili daha büyük bir resmi anlamak önemlidir. Bu kılavuzda veri tersinizi nasıl yöneteceklerini açıklamıyoruz ama [lütfen Dynamics 365 Kılavuzları - Dynamics 365 Karma](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)Gerçeklik'i dağıtmak için temel kavramları gözden geçirin.

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Yapılandırma](hololens2-corp-connected-configure.md)