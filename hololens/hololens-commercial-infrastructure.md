---
title: HoloLens için Altyapı Yönergeleri
description: Kablosuz ağ desteği, uzaktan yardım HoloLens mobil cihaz yönetimi dahil olmak üzere cihaz yönetimi için altyapı yönergeleri hakkında bilgi edinebilirsiniz.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e23bd458e26668f1f4a9a361ffaadf8fc377933e
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189078"
---
# <a name="configure-your-network-for-hololens"></a>Ağınızı ağ için HoloLens

Belgenin bu bölümü için aşağıdaki kişiler gerekir:

1. Ara sunucuda/güvenlik duvarında değişiklik yapma izinlerine sahip Ağ Yöneticisi
2. Azure Active Directory Yönetici
3. Mobil Cihaz Yöneticisi Yöneticisi

## <a name="infrastructure-requirements"></a>Altyapı Gereksinimleri

HoloLens, azure ile tümleştirilmiş Windows bir mobil cihazdır.  En iyi, kablosuz ağ kullanılabilirliği (wi-fi) ve kablosuz ağ erişimi olan ticari ortamlarda Microsoft hizmetleri.

Kritik bulut hizmetleri şunlardır:

- Azure active directory (Azure AD)
- Windows Güncelleştirme (WU)

Ticari müşterilerin büyük ölçekteki cihazları yönetmek için kurumsal mobilite yönetimi (EMM) veya mobil cihaz yönetimi (MDM) HoloLens gerekir.  Bu [kılavuzda, Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) microsoft ilkesi desteğine sahip tüm sağlayıcılar bu hizmet için HoloLens.  Mobil cihaz yönetimi sağlayıcınıza 2. cihaz yönetimi HoloLens sorun.

HoloLens sınırlı bir bulut bağlantısız deneyimi destekler.

### <a name="wireless-network-eap-support"></a>Kablosuz ağ EAP desteği

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Belirli Ağ Gereksinimleri

Ağ güvenlik [duvarında bu](hololens-offline.md) uç nokta listesine izin verili olduğundan emin olun. Bu, HoloLens çalışmasını sağlar.

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist'e Özgü Ağ Gereksinimleri

1. Remote Assist'in en iyi performansı için önerilen bant genişliği 1,5 Mb/sn'dir. Ek bilgi [için ayrıntılı ağ](/MicrosoftTeams/prepare-network) gereksinimlerine bakın.
**(Ağ hızınız en az 1,5 Mb/sn değilse Remote Assist'in çalışmaya devam eder. Ancak kalite düşük olabilir).**
1. Ağ güvenlik duvarında bu bağlantı noktalarının ve URL'lerin çalışmasına izin Microsoft Teams emin olun. bağlantı noktalarının en son [listesiyle güncel kalın.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Remote Assist için belirli Ağ [Gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Kuruluş ağına ağ [hazırlama hakkında daha fazla bilgi Microsoft Teams](/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Kılavuzlar Belirli Ağ Gereksinimleri

Kılavuzlar yalnızca uygulamayı indirmek ve kullanmak için ağ erişimi gerektirir.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Rehber -lik

> [!NOTE]
> Bu adım yalnızca, şirketiniz şirket yönetim planınız HoloLens.

1. Azure AD Lisansına sahip olduğundan emin olmak.
Daha [HoloLens için lütfen Lisans Gereksinimleri'ne](hololens-licenses-requirements.md) bakın.

1. Otomatik Kayıt kullanmayı planlıyorsanız Azure AD kaydı [yapılandırmanız gerekir.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Şirket kullanıcılarının şirket içinde (Azure AD) Azure Active Directory emin olmak.
Kullanıcı eklemek için [aşağıdaki](/azure/active-directory/fundamentals/add-users-azure-active-directory) yönergelere bakın.

1. Benzer lisanslara ihtiyacı olan kullanıcıların aynı gruba eklenmelerini öneririz.
    1. [Grup Oluşturma](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Gruplara kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Şirket kullanıcılarının (veya kullanıcı grubunun) gerekli lisanslara atanmalarını sağlar.
Lisans atamanız gerekirse şu yönergeleri [izleyin.](/azure/active-directory/fundamentals/license-users-groups)

1. Bu adımı yalnızca kullanıcıların HoloLens/Mobil cihazlarını size kaydetmesi bekleniyorsa uygulayın (Üç seçenek vardır) Bu adımlar, şirket kullanıcılarının (veya bir kullanıcı grubunun) cihaz ekleyeci olmasını sağlar.
    1. **1. Seçenek:** Tüm kullanıcılara cihazları Azure AD'ye katma izni verme.
**Yönetici olarak Azure portal oturum açın**  >  **Azure Active Directory**  >  **Cihazlar**  >  **Cihaz Ayarlar**  >
 **Kullanıcılar cihazları Azure AD'ye katabilirsiniz'i All olarak *ayarlayın***

    1. **2. Seçenek:** Seçili kullanıcılara/gruplara cihazları Azure AD'ye katma izni verme **Yönetici olarak Azure portal'da** oturum açın Azure Active Directory Cihazlar Cihazı Ayarlar Kullanıcıları Azure AD'ye katarak Cihazları Azure AD'ye Katarak Azure  >    >    >    >
 **AD'ye** 
 Katılmış Cihazların Yapılandırmasını gösteren Seçili Görüntüye ![ Ayarlayın.](images/azure-ad-image.png)

    1. **3. Seçenek:** Tüm kullanıcıların cihazlarını etki alanına eklemesini engelleyebilirsiniz. Bu, tüm cihazların el ile kaydolması gerektirmektedir.

## <a name="mobile-device-manager-guidance"></a>Mobil Cihaz Yöneticisi Kılavuzu

### <a name="ongoing-device-management"></a>Devam eden cihaz yönetimi

> [!NOTE]
> Bu adım yalnızca, şirket şirket yönetimi planlamalarında HoloLens.

Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza bağlıdır.  Çoğu genel işleve sahiptir ancak kullanıcı arabirimi büyük ölçüde değişiklik gösterebilir.

1. [CSP'ler (Yapılandırma](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Hizmeti Sağlayıcıları), ağ üzerinde cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak tanır. Başvuru için [CSP'HoloLens listesine](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) bakın.

1. [Uyumluluk ilkeleri,](/intune/device-compliance-get-started) cihazların kurumsal altyapınıza uyum sağlamak için karşılaması gereken kurallar ve ayarlardır. Uyumlu olmayan cihazların şirket kaynaklarına erişimini engellemek için Koşullu Erişim ile bu ilkeleri kullanın. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

1. [Uyumluluk İlkesi oluşturun.](/intune/protect/compliance-policy-create-windows)

1. Koşullu Erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesine izin verir/bunu geri verir. CA Dağıtımınızı planlama ve En İyi [Yöntemler belgelerini yararlı](/azure/active-directory/conditional-access/plan-conditional-access) [bulabilirsiniz.](/azure/active-directory/conditional-access/best-practices)

1. [Bu makalede,](/intune/fundamentals/windows-holographic-for-business) intune'un yönetim araçları hakkında bilgi HoloLens.

1. [Cihaz profili oluşturma](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Güncelleştirmeleri yönetme

Intune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil olmak üzere Windows 10 cihazlar için güncelleştirme halkaları adlı bir özellik içerir. Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yük olduğunu belirleyen bir grup ayar içerir.

Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.  Güncelleştirmeleri güncelleştirmeye hazır olana kadar süresiz olarak duraklatmayı da seçebilirsiniz.

[Intune ile güncelleştirme halkalarını yapılandırma hakkında daha fazla bilgi okuyun.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Uygulama yönetimi

Uygulama HoloLens yönetme:

1. Microsoft Store  
  Bu Microsoft Store, uygulamaları uygulama dağıtım ve uygulama dağıtımları için en iyi HoloLens.  Mağazada zaten mevcut olan HoloLens bir dizi temel uygulama vardır veya kendi uygulamalarınızı [yayımlayın.](/windows/uwp/publish/)  
  Mağazada bulunan tüm uygulamalar herkese açık bir şekilde kullanılabilir, ancak kabul edilebilir değilse uygulamanın genel kullanıma İş İçin Microsoft Store.  

1. [İş İçin Microsoft Store](/microsoft-store/)  
  İş İçin Microsoft Store ve Eğitim, kurumsal ortamınız için özel bir depodur.  Bu araç, Microsoft Store uygulamaları bulmak Windows 10 HoloLens, dağıtma ve yönetmeye yardımcı olacak şekilde yerleşik olarak kullanmanızı sağlar.  Ayrıca, ticari ortamınıza özgü ancak dünyaya değil, uygulamaları dağıtmanıza da olanak sağlar.

1. Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi  
  Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş hattı uygulamalarını doğrudan kayıtlı bir cihaz kümesine dağıtmak için bir yol sağlar.  [Intune uygulaması yüklemesi için bu makaleye bakın.](/intune/apps-deploy)

1. _önerilmez_ Cihaz Portalı  
  Uygulamalar, doğrudan HoloLens kullanılarak Windows Cihaz Portalı.  Geliştirici Modunun cihaz portalını kullanmak için etkinleştirilmesi gerektirildiğinden bu önerilmez.

Uygulama yükleme hakkında [daha fazla bilgi için HoloLens.](hololens-install-apps.md)

### <a name="certificates"></a>Sertifikalar

Sertifikaları MDM sağlayıcınız aracılığıyla dağıtabilirsiniz. Şirketiniz sertifika gerektiriyorsa, Intune PKCS, PFX ve SCEP'yi destekler. Hangi sertifikanın şirket için doğru olduğunu anlamak önemlidir. Hangi sertifikanın [sizin için en](/intune/protect/certificates-configure) uygun olduğunu belirlemek için lütfen sertifika yapılandırmaları belgelerini ziyaret edin. HoloLens kimlik doğrulaması için sertifika kullanmayı planlıyorsanız PFX veya SCEP sizin için uygun olabilir.

[SCEP](/intune/protect/certificates-profile-scep)kullanımı için aşağıdaki adımlara bakın.

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Business Commercial Suite için holografik 'e yükseltme

> [!NOTE]
> Windows iş için holografik (ticari paket) yalnızca 1. gen cihaz HoloLens yöneliktir. profil HoloLens 2 cihaza uygulanmaz.

[Holographic Upgrade](/intune/configuration/holographic-upgrade) belgelerindeki Commercial Suite 'e yükseltme yönergelerini bulabilirsiniz.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Microsoft Intune kullanarak bilgi noktası modunu yapılandırma

1. Microsoft Store ıntune 'a eşitleyin (aşağıdaki [yönergelere](/intune/apps/windows-store-for-business)bakın).

1. Uygulama ayarlarınızı denetleyin
    1. Microsoft Store iş hesabınızda oturum açın
    1. **> ürünlerini ve hizmetlerini > uygulama ve yazılım > yönetme > özel mağaza kullanılabilirliği eşitlemek istediğiniz uygulamayı seçin > "Herkes" veya "belirli gruplar" ı seçin**
        >[!NOTE]
        >İstediğiniz uygulamayı görmüyorsanız, uygulamanız için depoyu arayarak uygulamayı "almanız" gerekir. **Sağ üst köşedeki "ara" çubuğuna tıklayın > uygulamanın adını yazın > uygulamaya tıklayın > "Al" seçeneğini belirleyin**.
    1. Uygulamalarınızı **ıntune > Istemci uygulamaları > uygulamalar** ' da görmüyorsanız uygulamalarınızı yeniden [eşitlemeniz](/intune/apps/windows-store-for-business#synchronize-apps) gerekebilir.

1. [Bilgi noktası modu için bir cihaz profili oluşturma](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Farklı kullanıcıları, "Kullanıcı oturum açma türü" olarak "Azure AD" kullanarak farklı bilgi noktası modu deneyimleri olacak şekilde yapılandırabilirsiniz. Ancak, bu seçenek yalnızca çok uygulama bilgi noktası modunda kullanılabilir. Çoklu uygulama bilgi noktası modu, birden çok uygulama ile yalnızca bir uygulamayla birlikte çalışır.

![Intune 'da bilgi noktası modunun yapılandırılmasını gösteren resim.](images/aad-kioskmode.png)

Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanmanız gerekiyorsa [HoloLens bilgi noktası](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) yönergelerine bakın.

## <a name="certificates-and-authentication"></a>Sertifikalar ve kimlik doğrulama

Sertifikalar, MDM aracılığıyla dağıtılabilir ( [MDM bölümünde](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)"Sertifikalar" konusuna bakın). sertifikalar, paket sağlama aracılığıyla HoloLens da dağıtılabilir. lütfen daha fazla bilgi için [HoloLens sağlama](hololens-provisioning.md) konusuna bakın.

### <a name="additional-intune-quick-links"></a>Ek Intune hızlı bağlantıları

1. [Profil oluşturma:](/intune/configuration/device-profile-create) Profiller, kuruluşunuzdaki cihazlara gönderilecek ayarları eklemenize ve yapılandırmanıza olanak tanır.

