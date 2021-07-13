---
title: Dağıtım Kılavuzu – Remote Assist HoloLens büyük ölçekte buluta bağlı ve 2 dağıtım - Hazırlama
description: Azure Active Directory ve kimlik HoloLens bulut bağlantılı ağ üzerinden cihaz kaydetmeye hazırlanmayı öğrenin.
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
ms.openlocfilehash: f747a2893ed3551e91a81bdbf5971deefbf6ce46
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637141"
---
# <a name="prepare---cloud-connected-guide"></a>Hazırlama - Buluta bağlı Kılavuz

Bu makalenin sonunda Azure AD, MDM'i ayarlayacak ve Azure AD hesaplarını ve ağ gereksinimlerini kullanma hakkında daha fazla bilgi edinebilirsiniz. Kılavuzun bu bölümü, hem sizin hem de kurum 2'nin buluta HoloLens ve Dynamics 365 Remote Assist'i kullanmaya hazır olunmanıza yardımcı olur. Bu, altyapınızı her bir parçasının öneminin üzerine gider ve gerektiğinde bu parçaları ayarlamanıza yardımcı olacak kılavuzlara bağlantılar sağlar.

## <a name="infrastructure-essentials"></a>Altyapı TemelLeri

Hem kişisel hem de kurumsal dağıtım senaryolarında MDM sistemi, cihazlarınızı dağıtmak ve yönetmek için gereken Windows 10 Holographic altyapıdır. Azure AD premium aboneliği bir kimlik sağlayıcısı olarak önerilir ve belirli özellikleri desteklemek için gereklidir.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Microsoft Office 365 veya Intune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: Ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri.)](https://azure.microsoft.com/documentation/articles/active-directory-editions) Tüm sürümler Azure AD cihaz kaydını destekler, ancak Premium P1'in MDM otomatik kaydını etkinleştirmek için gerekli olması ve bunu daha sonra bu kılavuzda kullanacağız.

> [!IMPORTANT]
> Şirket içi AD Azure Active Directory destekleme HoloLens bir cihaza sahip olmak önemlidir. Henüz bir&#39;ayar Azure Active Directory, Azure Active Directory'de [yeni kiracı oluşturma'ya gidin.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>Kimlik Yönetimi

Çalışanlar, bir cihazı başlatmak için yalnızca bir hesap kullanabilir&#39;önce hangi hesabın etkinleştirildikten sonra kuruluş tarafından kontrol etkinleştirilmiş olması gerekir. Seçilen hesap, cihazı kimin kontrol altında olduğunu belirler ve yönetim özelliklerinizi etkiler.

Bu kılavuzda, kullanılan Kimlik [için](/hololens/hololens-identity) Azure AD hesaplarını veya Azure Active Directory seçtik. Azure AD hesaplarının çeşitli avantajları vardır, örneğin:

- Çalışanlar, cihazı Azure AD'ye kaydetmek için Azure AD hesabını kullanır ve cihazı kuruluş&#39;MDM çözümüne otomatik olarak Azure AD Premium.
- Azure AD hesapları Çoklu [Oturum Açma desteği sunar.](/azure/active-directory/manage-apps/what-is-single-sign-on) Bir kullanıcı Remote Assist'te oturum açınca, oturum açık Olan Azure AD kullanıcıdan gelen kimliği tanınır ve kullanıcı kolaylaştırılmış bir deneyim için uygulamada oturum alır.
- Azure AD hesaplarının İş için [Windows Hello](/hololens/hololens-identity) [kimlik doğrulaması seçenekleri vardır.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Iris oturum açma kullanıcılarına ek olarak başka bir cihazdan oturum açabilirsiniz veya FIDO güvenlik anahtarlarını kullanabilirler.

### <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi

Enterprise Mobility + Security'nin bir parçası olan Microsoft [Intune,](/mem/intune/fundamentals/what-is-intune)kiracınıza bağlı cihazları yöneten bulut tabanlı bir MDM sistemidir. Intune Office 365 da olduğu gibi, çalışanlar da kimlik yönetimi için Azure AD'i kullanır. Bu nedenle, çalışanlar, intune'da oturum aken kullandığı cihazları intune'a kaydetmek için Office 365. Intune, eksiksiz bir MDM çözümü sağlamak için iOS ve Android gibi diğer işletim sistemlerini çalıştıran cihazları da destekler. Bu kılavuzun amaçları doğrultusunda,&#39;2 ile büyük ölçekte bulut dağıtımını etkinleştirmek için Intune'HoloLens odaklanabilirsiniz.

> [!IMPORTANT]
> Mobile Cihaz Yönetimi. Henüz ayarlamadı&#39;bu kılavuzu izleyin ve [Intune ile Kullanmaya başlayın izleyin.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Birden çok MDM sistemi, Windows 10 ve çoğu da kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. Şu anda bu hizmetleri destekleyen Windows 10 Holographic MDM sağlayıcıları şunlardır: AirWatch, MobileIron ve diğerleri. Sektör lideri MDM satıcılarının çoğu Azure AD ile tümleştirmeyi zaten desteklemektedir. Azure AD'i destekleyen MDM satıcılarını [Azure Market.](https://azure.microsoft.com/marketplace/)

## <a name="network"></a>Ağ

Bu kurulumda, kullanılabilir açık HoloLens ağdan İnternet'e bağlanan 2 cihaz Wi-Fi öngörülmektedir. Bir kullanıcının ağ bağlantısını konuma göre değiştirmesi gerekene için, [wi-Fi'a HoloLens nasıl bağlan gerektiğini öğrenmesi gerekir.](/hololens/hololens-network)

Dynamics 365 Remote Assist için bant genişliği, gecikme süresi, değişim ve paket kaybı gibi video arama deneyiminizi etkileebilecek çeşitli ağ koşulları vardır. Bant genişliği azaltılmış ortamlarda ses ve video çağrıları mümkün olsa da, özellikte düşüşle karşılayabilirsiniz. Dynamics 365 Remote Assist'i HoloLens ağ gereksinimleri şu şekildedir:

**En** düşük: 30mbps'de HD 1080p çözünürlükte eşler arası HD kaliteli video çağrısı için 1,5 Mb/sn yukarı/aşağı gerekir.

**En iyi:** HD 1080p çözünürlüğüne sahip eşler arası HD kalite video çağrısı için 4-5 Mb/sn'nin yukarı/aşağı doğru olması beklenir.

Daha fazla bilgi:

- [Ağ gereksinimleri](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Ağ iyileştirme önerileri](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>İsteğe bağlı: Bağlan VPN HoloLens ye bağlı olarak

Bu kılavuza bağlanan cihazlar ve dış bulut ağı üzerinden ağa bağlanacak. Cihazlarınızı VPN üzerinden bağlamanız&#39;şirket kaynaklarına erişmek için bu olabilir. Cihazlarınızı VPN'ye bağlamak için hem son kullanıcının cihaz kullanıcı arabirimini kullanarak bağlananın hem de cihazların VPN profilini ppkg ya da MDM'den yönettirebilir ve aldırabilirsiniz. VPN'in nasıl&#39;bu makalede ele&#39;, bu nedenle VPN protokolleri veya VPN'i yönetme yolları hakkında daha fazla bilgi edinmek için HoloLens ve VPN hakkında bilgi edinmek için [bu kılavuzları ziyaret edin.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Yapılandırma](hololens2-cloud-connected-configure.md)
