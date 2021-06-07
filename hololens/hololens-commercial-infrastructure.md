---
title: HoloLens için Altyapı Yönergeleri
description: Kablosuz ağ desteği, uzaktan yardım ve mobil cihaz yönetimi dahil olmak üzere HoloLens cihazları için altyapı yönergeleri hakkında bilgi edinebilirsiniz.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380157"
---
# <a name="configure-your-network-for-hololens"></a>HoloLens için Anızı Yapılandırma

Belgenin bu bölümü için aşağıdaki kişiler gerekir:

1. Ara sunucuda/güvenlik duvarında değişiklik yapma izinlerine sahip Ağ Yöneticisi
2. Azure Active Directory Yöneticisi
3. Mobil Cihaz Yöneticisi Yöneticisi

## <a name="infrastructure-requirements"></a>Altyapı Gereksinimleri

HoloLens, temel olarak Azure ile tümleştirilmiş bir Windows mobil cihazıdır.  En iyi, kablosuz ağ kullanılabilirliği (wi-fi) ve kablosuz ağ erişimi olan ticari ortamlarda Microsoft hizmetleri.

Kritik bulut hizmetleri şunlardır:

- Azure active directory (Azure AD)
- Windows Update (WU)

Ticari müşterilerin HoloLens cihazlarını büyük ölçekte yönetmek için kurumsal mobilite yönetimi (EMM) veya mobil cihaz yönetimi (MDM) altyapısına ihtiyacı olacaktır.  Bu kılavuzda [örnek olarak Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) ancak Microsoft İlkesi'ne tam destek veren tüm sağlayıcılar HoloLens'i destekleyene kadar her sağlayıcıyı destekler.  Mobil cihaz yönetimi sağlayıcınıza HoloLens 2'ye destek olup olduklarını sorun.

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

### <a name="hololens-specific-network-requirements"></a>HoloLens'e Özgü Ağ Gereksinimleri

Ağ güvenlik [duvarında bu](hololens-offline.md) uç nokta listesine izin verili olduğundan emin olun. Bu, HoloLens'in düzgün çalışmasını sağlar.

### <a name="remote-assist-specific-network-requirements"></a>Remote Assist'e Özgü Ağ Gereksinimleri

1. Remote Assist'in en iyi performansı için önerilen bant genişliği 1,5 Mb/sn'dir. Ek bilgi [için ayrıntılı ağ](https://docs.microsoft.com/MicrosoftTeams/prepare-network) gereksinimlerine bakın.
**(Ağ hızınız en az 1,5 Mb/sn değilse Remote Assist'in çalışmaya devam eder. Ancak kalite düşük olabilir).**
1. Microsoft Teams'in çalışmasını sağlamak için ağ güvenlik duvarında bu bağlantı noktalarına ve URL'lere izin verili olduğundan emin olun. bağlantı noktalarının en son [listesiyle güncel kalın.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Remote Assist için belirli Ağ [Gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Microsoft Teams için kuruluş [ağına hazırlanma hakkında daha fazla bilgi](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Kılavuzlar Belirli Ağ Gereksinimleri

Kılavuzlar yalnızca uygulamayı indirmek ve kullanmak için ağ erişimi gerektirir.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Kılavuzu

> [!NOTE]
> Bu adım yalnızca, şirketiniz HoloLens'i yönetmeyi planlıyorsa gereklidir.

1. Azure AD Lisansına sahip olduğundan emin olmak.
Ek [bilgi için lütfen HoloLens](hololens-licenses-requirements.md) Lisans Gereksinimleri.

1. Otomatik Kayıt kullanmayı planlıyorsanız Azure AD kaydı [yapılandırmanız gerekir.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Şirket kullanıcılarının şirket içinde (Azure AD) Azure Active Directory emin olmak.
Kullanıcı eklemek için [aşağıdaki](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) yönergelere bakın.

1. Benzer lisanslara ihtiyacı olan kullanıcıların aynı gruba eklenmelerini öneririz.
    1. [Grup Oluşturma](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Gruplara kullanıcı ekleme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Şirket kullanıcılarının (veya kullanıcı grubunun) gerekli lisanslara atanmalarını sağlar.
Lisans atamanız gerekirse şu yönergeleri [izleyin.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)

1. Bu adımı yalnızca kullanıcıların HoloLens/Mobile cihazlarını size kaydetmesi bekleniyorsa uygulayın (Üç seçenek vardır) Bu adımlar, şirket kullanıcılarının (veya bir kullanıcı grubunun) cihaz ekleyeci olmasını sağlar.
    1. **1. Seçenek:** Tüm kullanıcılara cihazları Azure AD'ye katma izni verme.
**Yönetici olarak Azure portal oturum açın**  >  **Azure Active Directory**  >  **Cihazlar**  >  **Cihaz Ayarları**  >
 **Kullanıcılar cihazları Azure AD'ye katabilirsiniz'i All olarak *ayarlayın***

    1. **2. Seçenek:** Seçili kullanıcılara/gruplara cihazları Azure AD'ye katma izni verme **Yönetici olarak Azure portal'da** oturum açma Azure Active Directory Cihazları Cihaz Ayarları Kullanıcılar cihazları Azure AD'ye katarak  >    >    >    >
 **Azure AD'ye** 
 ![ katılabilir](images/azure-ad-image.png)

    1. **3. Seçenek:** Tüm kullanıcıların cihazlarını etki alanına eklemesini engelleyebilirsiniz. Bu, tüm cihazların el ile kaydolması gerektirmektedir.

## <a name="mobile-device-manager-guidance"></a>Mobil Cihaz Yöneticisi Kılavuzu

### <a name="ongoing-device-management"></a>Devam eden cihaz yönetimi

> [!NOTE]
> Bu adım yalnızca, şirket HoloLens'i yönetmeyi planlıyorsa gereklidir.

Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza bağlıdır.  Çoğu genel işleve sahiptir ancak kullanıcı arabirimi büyük ölçüde değişiklik gösterebilir.

1. [CSP'ler (Yapılandırma](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Hizmeti Sağlayıcıları), ağ üzerinde cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak tanır. Başvuru için [HoloLens CSP'leri](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) listesine bakın.

1. [Uyumluluk ilkeleri,](https://docs.microsoft.com/intune/device-compliance-get-started) cihazların kurumsal altyapınıza uyumlu olması için karşılaması gereken kurallar ve ayarlardır. Uyumlu olmayan cihazların şirket kaynaklarına erişimini engellemek için Koşullu Erişim ile bu ilkeleri kullanın. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

1. [Uyumluluk İlkesi oluşturun.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. Koşullu Erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesine izin verir/erişimini geri verir. CA Dağıtımınızı planlama ve En İyi [Yöntemler belgelerini yararlı](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) [bulabilirsiniz.](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)

1. [Bu makalede,](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) Intune'un HoloLens için yönetim araçları hakkında bilgi edinebilirsiniz.

1. [Cihaz profili oluşturma](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Güncelleştirmeleri yönetme

Intune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil olmak üzere Windows 10 cihazlar için güncelleştirme halkaları adlı bir özellik içerir. Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yük olduğunu belirleyen bir grup ayar içerir.

Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.  Güncelleştirmeleri güncelleştirmeye hazır olana kadar süresiz olarak duraklatmayı da seçebilirsiniz.

[Intune ile güncelleştirme halkalarını yapılandırma hakkında daha fazla bilgi okuyun.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Uygulama yönetimi

HoloLens uygulamalarını yönetmek için:

1. Microsoft Store  
  Bu Microsoft Store, HoloLens'de uygulamaları dağıtmanın ve tüketmenin en iyi yolu.  Mağazada zaten bulunan çok çeşitli temel HoloLens uygulamaları vardır veya kendi uygulamalarınızı [yayımlayın.](https://docs.microsoft.com/windows/uwp/publish/)  
  Mağazada bulunan tüm uygulamalar herkese açık bir şekilde kullanılabilir, ancak kabul edilebilir değilse uygulamanın genel kullanıma İş İçin Microsoft Store.  

1. [İş İçin Microsoft Store](https://docs.microsoft.com/microsoft-store/)  
  İş İçin Microsoft Store ve Eğitim, kurumsal ortamınız için özel bir depodur.  Bu araç, Microsoft Store ve HoloLens Windows 10 de yerleşik olarak yer alan uygulamaları kullanarak, uygulamaları bulmanızı, edinmenizi, dağıtmanızı ve yönetmenizi sağlar.  Ayrıca, ticari ortamınıza özgü ancak dünyaya değil, uygulamaları dağıtmanıza da olanak sağlar.

1. Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi  
  Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş hattı uygulamalarını doğrudan kayıtlı bir cihaz kümesine dağıtmak için bir yol sağlar.  [Intune uygulaması yüklemesi için bu makaleye bakın.](https://docs.microsoft.com/intune/apps-deploy)

1. _önerilmez_ Cihaz Portalı  
  Uygulamalar doğrudan HoloLens'e de doğrudan sanal Windows Cihaz Portalı.  Geliştirici Modunun cihaz portalını kullanmak için etkinleştirilmesi gerektirildiğinden bu önerilmez.

[HoloLens'e uygulama yükleme hakkında daha fazla bilgi edinin.](https://docs.microsoft.com/hololens/hololens-install-apps)

### <a name="certificates"></a>Sertifikalar

Sertifikaları MDM sağlayıcınız aracılığıyla dağıtabilirsiniz. Şirketiniz sertifika gerektiriyorsa, Intune PKCS, PFX ve SCEP'yi destekler. Hangi sertifikanın şirket için doğru olduğunu anlamak önemlidir. Hangi sertifikanın [sizin için en](https://docs.microsoft.com/intune/protect/certificates-configure) uygun olduğunu belirlemek için lütfen sertifika yapılandırmaları belgelerini ziyaret edin. HoloLens Kimlik Doğrulaması için sertifika kullanmayı planlıyorsanız, PFX veya SCEP sizin için uygun olabilir.

SCEP kullanmak için [aşağıdaki adımlara bakın.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Holographics for Business Commercial Suite'e Yükseltme

> [!NOTE]
> Windows Holographics for Business (ticari paket), yalnızca HoloLens 1. nesil cihazlara yöneliktir. Profil HoloLens 2 cihazlarına uygulanmaz.

Holografik yükseltme belgelerinde ticari pakete yükseltme [yönergelerini](https://docs.microsoft.com/intune/configuration/holographic-upgrade) bulabilirsiniz.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Microsoft Intune Kullanarak Bilgi Noktası Modunu Yapılandırma

1. Eşitleme Microsoft Store Intune'a (Aşağıdaki yönergelere [bakın).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Uygulama ayarlarınızı denetleme
    1. Microsoft Store Business hesabınızla oturum açın
    1. **> Ürün ve Hizmetleri > Uygulamaları ve Yazılımlarını Yönetme > Eşitlemek istediğiniz uygulamayı seçin > Özel Mağaza Kullanılabilirliği > "Herkes" veya "Belirli Gruplar"ı seçin**
        >[!NOTE]
        >Istediğiniz uygulamayı görmüyorsanız mağazada uygulama arayarak uygulamayı "ala" gerekir. **Sağ üst köşedeki "Ara"** çubuğuna tıklayın > uygulamanın adını yazın ve > tıklayın ve "Al" > seçin.
    1. Uygulamalarınızı Intune'da > İstemci Uygulamaları **> Uygulamalar'da görmüyorsanız,** uygulamalarınızı [yeniden eşitlemeniz gerekir.](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)

1. [Bilgi Noktası modu için cihaz profili oluşturma](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> "Kullanıcı oturum açma türü" olarak "Azure AD" kullanarak farklı kullanıcıları farklı Bilgi Noktası Modu deneyimleri olacak şekilde yapılandırabilirsiniz. Ancak, bu seçenek yalnızca Çoklu Uygulama bilgi noktası modunda kullanılabilir. Çoklu Uygulama bilgi noktası modu yalnızca bir uygulamayla ve birden çok uygulamayla çalışır.

![Intune'da Bilgi Noktası Modu Yapılandırmasını gösteren resim](images/aad-kioskmode.png)

Diğer MDM hizmetleri için yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinize bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanıyorsanız [HoloLens](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) bilgi noktası yönergelerine bakın.

## <a name="certificates-and-authentication"></a>Sertifikalar ve Kimlik Doğrulaması

Sertifikalar MDM'ler aracılığıyla dağıtılabilir (MDM Bölümünde "sertifikalar" [bölümüne bakın).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Sertifikalar, paket sağlama aracılığıyla HoloLens'e de dağıtılabilir. Daha fazla [bilgi için lütfen bkz. HoloLens](hololens-provisioning.md) Sağlama.

### <a name="additional-intune-quick-links"></a>Ek Intune Hızlı Bağlantıları

1. [Profil Oluşturma:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiller, kuruluşta cihazlara gelecek ayarları eklemenize ve yapılandırmanıza olanak tanır.

