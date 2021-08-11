---
title: Dağıtım Kılavuzu – Dynamics 365 kılavuzları HoloLens 2 ile kurumsal bağlantılı HoloLens - Hazırlama
description: Dynamics 365 Kılavuzları ile HoloLens bağlı bir ağ üzerinden 2 cihaz kaydetmeye hazırlanmayı öğrenin.
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
ms.openlocfilehash: 76513c2f2458119785b64d8cccac4e42c2957b5af966dfdb0c165ebeda12e069
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660086"
---
# <a name="prepare---corporate-connected-guide"></a>Hazırlama - Kurumsal Bağlantılı Kılavuz
## <a name="infrastructure-essentials"></a>Altyapı TemelLeri
Hem kişisel hem de kurumsal dağıtım senaryolarında Mobil Cihaz Yönetimi (MDM) sistemi, özellikle de Windows 10 2'yi dağıtmak ve yönetmek için gereken temel HoloLens sistemidir. Bir [Azure AD Premium,](/azure/active-directory/fundamentals/active-directory-get-started-premium) kimlik sağlayıcısı olarak önerilir ve **belirli özellikleri** desteklemek için gereklidir.

> [!NOTE]
> 2 HoloLens mobil cihaz gibi dağıtılıyor ve yönetiliyor olsa da, genellikle çok sayıda kullanıcı arasında paylaşılan bir cihaz olarak kullanılır.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya Intune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: Ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tüm sürümler Azure AD cihaz kaydını destekler, ancak Premium P1'in MDM otomatik kaydını etkinleştirmek için gerekli olması ve bunu daha sonra bu kılavuzda kullanacağız.
> [!Important]
> Şirket içi AD'ye katılmayı destekleme HoloLens azure AD'ye sahip olmak önemlidir. Henüz bir Azure AD ayarlamadıysanız, çalışmaya başlama yönergelerini izleyin ve azure'da [yeni bir kiracı Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Kimlik Yönetimi
Bu kılavuzda kullanılan [kimlik](/hololens/hololens-identity) Azure AD hesaplarıdır. Azure AD hesaplarının çeşitli avantajları vardır, örneğin:

- Çalışanlar, cihazı Azure AD'ye kaydetmek için Azure AD hesabını kullanır ve cihazı kuruluşun MDM çözümüne otomatik olarak kaydedebiliyor (Azure AD+MDM– bir Azure AD Premium [aboneliği gerektirir).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Azure AD hesaplarının İş için [Windows Hello](/hololens/hololens-identity) [kimlik doğrulaması seçenekleri vardır.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris oturum açmanın yanı sıra, kullanıcılar başka bir cihazdan oturum açabilirsiniz veya FIDO güvenlik anahtarlarını kullanabilir.

> [!WARNING] 
> Çalışanlar bir cihazı başlatmak için yalnızca bir hesap kullanabilir. Bu nedenle, önce hangi hesabın **etkinleştirildiğinden kuruluşta denetime sahip olması gerekir.** Seçilen hesap, cihazı kimin kontrol altında olduğunu belirler ve yönetim özelliklerinizi etkiler.

## <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi
Microsoft Intune bir Enterprise Mobility + Security, kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Intune Office 365 da olduğu gibi, çalışanlar da kimlik yönetimi için Azure AD'i kullanır. Bu nedenle, çalışanlar, intune'da oturum aken kullandığı cihazları intune'a kaydetmek için Office 365. Intune, eksiksiz bir MDM çözümü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları da destekler. Bu kılavuzun amaçları doğrultusunda, HoloLens 2 ile iç ağınıza dağıtım sağlamak için Intune'HoloLens odaklanıyoruz.
> [!Important] 
> Mobile Cihaz Yönetimi. Henüz ayarlamadısanız bu kılavuzu izleyin ve Intune ile Kullanmaya başlayın izleyin.

> [!Important]
> Kılavuzları kullanmak için bir Azure AD hesabı gerekir.

> [!Note] 
> Birden çok MDM sistemi, Windows 10 ve çoğu da kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. Bu hizmeti destekleyen MDM Windows 10 Holographic şunlardır: AirWatch, MobileIron ve diğerleri. Sektör lideri MDM satıcılarının çoğu Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure AD'i destekleyen MDM satıcılarının en güncel listesini [Azure Market.](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps)

## <a name="network-access"></a>Ağ Erişimi 
Dynamics 365 Kılavuzları, bulut tabanlı bir uygulamadır. Ağ yöneticinizin bir onaylama listesi varsa, Dynamics 365 sunucularına bağlanmak için gereken IP adreslerini ve/veya uç noktaları eklemesi gerekebilir. [IP adreslerinin ve URL'lerin engelini kaldırma hakkında daha fazla bilgi.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Sertifikalar
Sertifikalar, hesap kimlik doğrulaması, kimlik doğrulaması, VPN Wi-Fi ve web içeriğinin SSL şifrelemesi sağlayarak güvenliğin iyileştirilmesine yardımcı olur. Yöneticiler, sağlama paketleri aracılığıyla cihazlardaki sertifikaları el ile yönetese de, kayıttan yenileme ve iptale kadar tüm yaşam döngüsü boyunca bu sertifikaları yönetmek için MDM sisteminizi kullanmak en iyi uygulamadır. 

MDM sisteminiz, bu sertifikaları kaydettikten sonra cihazların sertifika depolarına otomatik olarak dağıtabilirsiniz (MDM sisteminiz **Basit Sertifika Kayıt Protokolü (SCEP)** veya Ortak Anahtar Şifreleme Standartları'#12 **(PKCS #12) desteklediği sürece).** [ile birlikte kullanabileceğiniz sertifika türleri ve profilleri hakkında bilgi Microsoft Intune.](/mem/intune/protect/certificates-configure) MDM ayrıca kayıtlı istemci sertifikalarını sorgular ve silebilir veya geçerli sertifikanın süresi dolmadan önce yeni bir kayıt isteği tetikler.

MDM sistemleriniz sertifikalar için zaten yapılandırılmışsa, HoloLens 2 cihazlarınız için sertifikaları ve profilleri dağıtmaya başlamak üzere [HoloLens 2](/hololens/hololens-certificates-network) için sertifikaları ve ağ profillerini hazırlama HoloLens bakın.

## <a name="scep"></a>SCEP

Web Sunucusu dışında SCEP dağıtımı için aşağıdaki hizmetler Uygulama Ara Sunucusu.

- [Sertifika Yetkilisi](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [NDES Sunucusu rolü](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Microsoft Intune Bağlayıcı](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Ayrıca NDES URL'nizi Azure AD uygulama ara sunucusu veya sunucu ara sunucusu kullanarak [şirket Web Erişimi yayımlamanız gerekir.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Tercihen başka bir ters ara sunucu da kullanabilirsiniz.

![SCEP veri akışı](./images/hololens2-scep-info-flow.png)

Ağınız zaten SCEP'yi desteklemezse veya ağın Intune ile SCEP için doğru ayar olup olmadığını emin değilseniz,  [Altyapıyı Intune ile SCEP'yi](/mem/intune/protect/certificates-scep-configure)destekleyecek şekilde yapılandırma'ya başvurun.

Altyapınız zaten SCEP'yi destekliyorsa, [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) HoloLens 2'nin kullanabileceği her SCEP sertifikası için bir profil oluşturmanız gerekir. [](/mem/intune/protect/certificates-profile-scep) SCEP ile ilgili sorunlarınız varsa, sertifikalar için [SCEP](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles)sertifika profillerini kullanarak sertifika sağlama sorunlarını Microsoft Intune.

## <a name="pkcs"></a>PKCS
Intune, özel ve ortak anahtar çifti (PKCS) sertifikalarının kullanımını da destekler. Daha [fazla bilgi için özel ve ortak anahtar Microsoft Intune](/mem/intune/protect/certificates-pfx-configure) kullanın.

## <a name="proxy"></a>Ara sunucu
Çoğu kurumsal intranet ağı dış trafiği yönetmek için bir ara sunucudan faydalanmaktadır. 2 HoloLens ethernet, ağ ve VPN bağlantıları için Wi-Fi sunucu yapılandırabilirsiniz.

Birkaç farklı ara sunucu türü ve ara sunucu yapılandırmanın yolları vardır. Bu kılavuzun amaçları doğrultusunda Wi-Fi ara sunucusunu seçmeyi, PAC URL'si aracılığıyla ayarlamayı ve **MDM aracılığıyla dağıtılmasını tercih ediyoruz.** Bu, MDM aracılığıyla otomatik olarak dağıtılmasının, sunucu:bağlantı noktası yapılandırması yerine PAC dosyasını güncelleştirenin ve son olarak ara sunucuyu yalnızca tek bir Wi-Fi bağlantısına uygulanacak şekilde yapılandırmak için Wi-Fi proxy'sini kullanarak cihazların başka bir konumda bağlı olması durumda hala kullanılmaktadır.

Windows 10 proxy ayarları hakkında daha fazla bilgi için Wi-Fi bkz. Microsoft Intune - Azure'da cihazlar için [Microsoft Intune profili oluşturma.](/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>İş Hattı Uygulamaları 
Microsoft Store aracılığıyla birkaç uygulama yüklenene kadar, büyük olasılıkla karma gerçeklikte kullanmak için özel olarak oluşturduğunuz kendi özel uygulamanız vardır. İşletmeniz için kuruluş genelinde dağıtılan bu özel uygulamalara İş Hattı (LOB) uygulamaları denir.
  
2 cihaza uygulama dağıtmanın birden HoloLens yolu vardır. Uygulamalar doğrudan MDM, İş İçin Microsoft Store (MSfB) aracılığıyla dağıtılabilir veya Sağlama Paketi aracılığıyla yan yüklenebilir. Bu kılavuz için, gerekli uygulama yüklemesini kullanarak uygulamaları MDM aracılığıyla dağıtıyor oluruz. Bu, iş lob uygulamalarınızı kayıt tamamlar ve HoloLens cihazlarınıza otomatik olarak indirilir.

Kendi LOB'niz yoksa, bu dağıtım akışını test etmek için bir örnek uygulama sağlariz. Bu uygulama [MRTK Örnekleri](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) uygulaması olacak ve kavram kanıtı test etmek için önceden oluşturulmuş ve paketlenmiştir.

Uygulama dağıtımıyla ilgili diğer ayrıntılar Uygulama [Yönetimi: Genel Bakış'a bakın.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 yalnızca UWP ARM64 uygulamalarının çalıştırmayı destekler.

## <a name="guides-playbook"></a>Kılavuzlar Playbook
Kılavuzlar, Kılavuzlar uygulamalarınız için veri deposu olarak bir Microsoft Dataverse ortamı kullanır. Dataverse ortamının Kılavuzlar uygulamalarınız ve kiracınız ile nasıl etkileşim kurduğuyla ilgili daha büyük bir resmi anlamak önemlidir. Bu kılavuzda veri tersinizi nasıl yöneteceklerini açıklamıyoruz ama [lütfen Dynamics 365 Kılavuzları - Dynamics 365 Karma](/dynamics365/mixed-reality/guides/admin-deployment-playbook)Gerçeklik'i dağıtmak için temel kavramları gözden geçirin.

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Yapılandırma](hololens2-corp-connected-configure.md)