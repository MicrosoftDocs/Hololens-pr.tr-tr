---
title: Dağıtım Kılavuzu – Remote Assist ile büyük ölçekte buluta bağlı HoloLens 2 dağıtımı - Hazırlama
description: Azure Active Directory ve kimlik yönetimi kullanarak Bir Bulut Bağlantılı ağ üzerinden HoloLens cihazlarını kaydetmeye hazırlanmayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379019"
---
# <a name="prepare---cloud-connected-guide"></a>Hazırlama - Buluta bağlı Kılavuz

Bu makalenin sonunda Azure AD, MDM'i ayarlayacak ve Azure AD hesaplarını ve ağ gereksinimlerini kullanma hakkında daha fazla bilgi edinebilirsiniz. Kılavuzun bu bölümü, siz ve kuruluş olarak Buluta HoloLens 2'yi dağıtmaya ve Dynamics 365 Remote Assist'i kullanmaya hazırlıklı olunmanıza yardımcı olur. Bu, altyapınızı her bir parçasının öneminin üzerine gider ve gerektiğinde bu parçaları ayarlamanıza yardımcı olacak kılavuzlara bağlantılar sağlar.

## <a name="infrastructure-essentials"></a>Altyapı TemelLeri

Hem kişisel hem de kurumsal dağıtım senaryolarında MDM sistemi, cihazlarınızı dağıtmak ve yönetmek için gereken Windows 10 Holographic altyapıdır. Azure AD premium aboneliği bir kimlik sağlayıcısı olarak önerilir ve belirli özellikleri desteklemek için gereklidir.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya Intune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: Ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)sürümleri.) Tüm sürümler Azure AD cihaz kaydını destekler, ancak MDM otomatik kaydını etkinleştirmek için Premium P1 gereklidir. Bunu daha sonra bu kılavuzda kullanacağız.

> [!IMPORTANT]
> HoloLens cihazları şirket Azure Active Directory AD'ye katılmayı desteklemeyebilirsiniz. Henüz bir&#39;ayar Azure Active Directory için bu bağlantıda yer alan yönergeleri izleyerek 'de yeni bir kiracı [oluşturun Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Kimlik Yönetimi

Çalışanlar, bir cihazı başlatmak için yalnızca bir hesap&#39;önce hangi hesabın etkinleştirildikten sonra kuruluşun denetime sahip olduğunu kontrol eder. Seçilen hesap, cihazı kimin kontrol altında olduğunu belirler ve yönetim özelliklerinizi etkiler.

Bu kılavuzda, kullanılan Kimlik [](https://docs.microsoft.com/hololens/hololens-identity) için Azure AD hesaplarını veya Azure Active Directory seçtik. Azure AD hesaplarının çeşitli avantajları vardır, örneğin:

- Çalışanlar, cihazı Azure AD'ye kaydetmek ve MDM çözümü olan kuruluşa otomatik olarak kaydetmek için Azure AD&#39;hesabını kullanır (Azure AD+MDM – Azure AD Premium).
- Azure AD hesapları Çoklu [Oturum Açma desteği sunar.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Bir kullanıcı Remote Assist'te oturum açsa, oturum açmış Olan Azure AD kullanıcıdan gelen kimliği tanınır ve kullanıcı kolaylaştırılmış bir deneyim için uygulamada oturum alır.
- Azure AD hesaplarının, kimlik doğrulaması [aracılığıyla ek kimlik](https://docs.microsoft.com/hololens/hololens-identity) [İş İçin Windows Hello.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris oturum açma kullanıcılarına ek olarak başka bir cihazdan oturum açabilirsiniz veya FIDO güvenlik anahtarlarını kullanabilirler.

### <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi

Enterprise Mobility + Security'nin bir parçası olan Microsoft [Intune,](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Office 365'te olduğu gibi, Intune da kimlik yönetimi için Azure AD kullanır. Bu nedenle, çalışanlar, Office 365'te oturum atırken kullandığı cihazları Intune'a kaydetmek için aynı kimlik bilgilerini kullanır. Intune, eksiksiz bir MDM çözümü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları da destekler. Bu kılavuzun amaçları doğrultusunda, HoloLens 2&#39;uygun ölçekte bulut dağıtımını etkinleştirmek için Intune'u kullanmaya odaklanmış oluruz.

> [!IMPORTANT]
> Mobile Cihaz Yönetimi. Henüz ayarlamadı&#39;bu kılavuzu izleyin ve [Intune ile Kullanmaya başlayın izleyin.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Birden çok MDM sistemi, Windows 10 ve çoğu da kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. Şu anda bu hizmetleri Windows 10 Holographic MDM sağlayıcıları şunlardır: AirWatch, MobileIron ve diğerleri. Sektör lideri MDM satıcılarının çoğu Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure AD'ye destek olan MDM satıcılarını [Azure Market.](https://azure.microsoft.com/marketplace/)

## <a name="network"></a>Ağ

Bu kurulumda, tüm açık ağlardan İnternet'e bağlanan HoloLens 2 cihazlarının Wi-Fi öngörülmektedir. Bir kullanıcının konuma göre ağ bağlantısını değiştirmesi gerekene için [HoloLens cihazlarını Wi-Fi'a bağlamayı öğrenmesi gerekir.](https://docs.microsoft.com/hololens/hololens-network)

Dynamics 365 Remote Assist için bant genişliği, gecikme süresi, değişim ve paket kaybı gibi video arama deneyiminizi etkileebilecek çeşitli ağ koşulları vardır. Bant genişliği azaltılmış ortamlarda ses ve video çağrıları mümkün olsa da, özellikte düşüşle karşılayabilirsiniz. HoloLens'te Dynamics 365 Remote Assist kullanırken aşağıdaki ağ gereksinimlerine göz ayın:

**En** düşük: Eşler arası HD kalite video çağrısı için 30mbps'de HD 1080p çözünürlüğünde 1,5 Mb/sn yukarı/aşağı gerekir.

**En iyi:** HD 1080p çözünürlüğüne sahip eşler arası HD kalite video çağrısı için 4-5 Mb/sn'nin yukarı/aşağı doğru olması beklenir.

Daha fazla bilgi:

- [Ağ gereksinimleri](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Ağ iyileştirme önerileri](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>İsteğe bağlı: HoloLens'inizi VPN'ye bağlama

Bu kılavuza bağlanan cihazlar ve dış bulut ağı üzerinden ağa bağlanacak. Cihazlarınızı VPN üzerinden bağlamanız&#39;şirket kaynaklarına erişmek için bu olabilir. Cihazlarınızı VPN'ye bağlamak için hem son kullanıcının cihaz kullanıcı arabirimini kullanarak bağlananın hem de cihazların VPN profilini bir PPKG veya MDM'den yönettirebilir ve aldırabilirsiniz. VPN'in nasıl&#39;bu makalede ele&#39;vpn protokolleri veya VPN'i yönetme yolları hakkında daha fazla bilgi edinmek için [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) ve VPN hakkında bilgi edinmek için bu kılavuzları ziyaret edin.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Yapılandırma](hololens2-cloud-connected-configure.md)
