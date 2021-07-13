---
title: dağıtım kılavuzu – buluta bağlı HoloLens 2 dağıtım, uzaktan yardım hazırlama ile uygun ölçekte
description: azure active directory ve kimlik yönetimi kullanarak bir buluta bağlı ağ üzerinden HoloLens cihazları kaydetmek için hazırlanma hakkında bilgi edinin.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639667"
---
# <a name="prepare---cloud-connected-guide"></a>Bulut ile bağlantılı Kılavuzu hazırlama

Bu makalenin sonuna kadar Azure AD 'yi, MDM 'yi ayarladıktan sonra Azure AD hesaplarını ve ağ gereksinimlerini kullanma hakkında daha fazla bilgi sahibi olmanız gerekir. kılavuzun bu bölümü, sizin ve kuruluşunuzun buluta HoloLens 2 ' ye dağıtmayı ve Dynamics 365 uzaktan yardım 'ı kullanmasını sağlamaya yardımcı olur. Bu, altyapınızın her parçasının önem derecesine giderek, bu parçaları gerektiği gibi ayarlamanıza yardımcı olacak kılavuzlara bağlantılar sağlar.

## <a name="infrastructure-essentials"></a>Altyapı temelleri

hem kişisel hem de kurumsal dağıtım senaryolarında, bir MDM sistemi Windows 10 Holographic cihazları dağıtmak ve yönetmek için gerekli olan temel altyapısıdır. Bir Azure AD Premium aboneliği, kimlik sağlayıcısı olarak önerilir ve belirli özellikleri desteklemek için gereklidir.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya ıntune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri](https://azure.microsoft.com/documentation/articles/active-directory-editions).) tüm sürümler Azure AD cihaz kaydını destekler, ancak bu kılavuzda daha sonra kullanabilmemiz için MDM otomatik kaydını etkinleştirmek üzere Premium P1 gerekir.

> [!IMPORTANT]
> HoloLens cihazlar şirket içi AD birleştirmeyi desteklemediğinden Azure Active Directory olması önemlidir. zaten bir Azure Active Directory ayarlamış&#39;, [Azure Active Directory yeni bir kiracı oluşturma](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)bölümüne gidin.

## <a name="identity-management"></a>Kimlik Yönetimi

Çalışanlar, bir cihazı başlatmak için yalnızca bir hesap kullanabilir, böylece kuruluşunuzun öncelikle hangi hesabın etkin olduğunu denetlemelerine&#39;. Seçilen hesap, cihazı kimin denetlediğini ve yönetim olanaklarınızı etkilediğini belirleyecek.

bu kılavuzda, Azure AD hesapları kullandığımız [kimlik](/hololens/hololens-identity) veya Azure Active Directory hesaplarını seçtik. Azure AD hesaplarının kullanmak istediğimiz birkaç avantajı vardır, örneğin:

- Çalışanlar, cihazı Azure AD 'ye kaydetmek ve kuruluş&#39;s MDM çözümüne otomatik olarak kaydetmek için Azure AD hesabını kullanır (Azure AD + MDM – Azure AD Premium gerektirir).
- Azure AD hesapları [Çoklu oturum açmayı](/azure/active-directory/manage-apps/what-is-single-sign-on)destekler. Bir Kullanıcı Uzaktan Yardım oturumu açtığında, oturum açan Azure AD kullanıcısının kimliği tanınacaktır ve Kullanıcı, kolaylaştırılmış bir deneyim için uygulamada oturum açar.
- Azure AD hesapları, [iş için Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification)ek [kimlik doğrulama seçeneklerine](/hololens/hololens-identity) sahiptir. Iris oturum açma 'ya ek olarak, kullanıcılar başka bir cihazdan oturum açabilir veya FIDO güvenlik anahtarlarını kullanabilir.

### <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi

Enterprise Mobility + Security bir parçası olan Microsoft [ıntune](/mem/intune/fundamentals/what-is-intune), kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Office 365 gibi, ıntune kimlik yönetimi için Azure AD 'yi kullanır, bu nedenle çalışanlar, ıntune 'a Office 365 oturum açmak için kullandıkları cihazları kaydetmek için aynı kimlik bilgilerini kullanır. Intune Ayrıca, tüm MDM çözümünü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları destekler. bu kılavuzun amaçları doğrultusunda, HoloLens 2 ile ölçekli bir bulut dağıtımını etkinleştirmek için ıntune 'u kullanmaya odaklanıyoruz&#39;.

> [!IMPORTANT]
> Mobil cihaz yönetiminin olması önemlidir. Zaten bir&#39;ayarladıysanız, bu kılavuzu izleyin ve [Intune ile çalışmaya](/mem/intune/fundamentals/free-trial-sign-up)başlayın.

> [!NOTE]
> birden çok MDM sistemi Windows 10 destekler ve çoğu kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. şu anda Windows 10 Holographic destekleyen MDM sağlayıcıları şunlardır: airwatch, mobileıron ve diğerleri. Sektörde önde gelen MDM satıcıları, Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure [Market](https://azure.microsoft.com/marketplace/)'TE Azure AD 'YI destekleyen MDM satıcıları bulabilirsiniz.

## <a name="network"></a>Ağ

bu kurulumda, kullanılabilir açık Wi-Fi ağından Internet 'e bağlanan HoloLens 2 cihaz olduğunu tahmin ediyoruz. bir kullanıcının konuma göre ağ bağlantısını değiştirmesi gerektiğinden, [HoloLens cihazlarını Wi-Fi ' y e nasıl bağlayacağınızı](/hololens/hololens-network) öğrenmelidir.

Dynamics 365 uzak yardım için bant genişliği, gecikme süresi, değişim ve paket kaybı da dahil olmak üzere, video çağırma deneyiminizi etkileyebilecek çeşitli ağ koşulları vardır. Ses ve video çağrıları, azaltılmış bant genişliğine sahip ortamlarda mümkün olsa da, özellik performansında düşüş yaşayabilirsiniz. Dynamics 365 uzaktan yardım 'ı kullanırken HoloLens göz önünde bulundurmanız gereken ağ gereksinimleri şunlardır:

**En az** : 1,5 Mbps artırma/azaltma, HD 1080p 'in 30 fps 'de çözümlenimiyle, eşler arası HD kalitesinde video çağrısı için gereklidir.

**En iyi:** HD 1080p çözünürlüklü eşler arası HD kalitesinde video çağrısı için 4-5 Mbps up/azaltma beklenmelidir.

Daha fazla bilgi:

- [Ağ gereksinimleri](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Ağ iyileştirme önerileri](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>isteğe bağlı: HoloLens VPN 'ye Bağlan

Bu kılavuza bağlanan cihazlar, ve dış bulut ağı aracılığıyla ağa bağlanır. Cihazları VPN aracılığıyla bağlamak için gereken&#39;, şirket kaynaklarına erişmek için bu olabilir. Cihazlarınızı VPN 'e bağlamak için kullanabileceğiniz birkaç farklı yol vardır, her ikisi de son kullanıcının cihaz Kullanıcı arabirimini kullanarak bağlanıp VPN profilini bir PPKG veya MDM 'den alabilir. vpn kazanıldı&#39;t 'yi ayarlama bu makalede ele alınmıştır. bu nedenle, farklı vpn protokolleri veya vpn 'yi yönetme yolları hakkında daha fazla bilgi edinmek için d&#39;, [HoloLens ve vpn hakkında bilgi için bu kılavuzlardan birini](/hololens/hololens-network#vpn) ziyaret edin.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım-yapılandırma](hololens2-cloud-connected-configure.md)
