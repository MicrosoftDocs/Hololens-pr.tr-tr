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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428007"
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

Ticari müşterilerin büyük ölçekteki cihazları yönetmek için kurumsal mobilite yönetimi (EMM) veya mobil cihaz yönetimi (MDM) HoloLens gerekir.  Bu kılavuzda [Microsoft Intune,](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) Microsoft İlkesi'ne tam destek veren tüm sağlayıcılar bu HoloLens.  Mobil cihaz yönetimi sağlayıcınıza 2. cihaz yönetimi HoloLens sorun.

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

1. Remote Assist'in en iyi performansı için önerilen bant genişliği 1,5 Mb/sn'dir. Daha fazla [bilgi için ayrıntılı ağ](/MicrosoftTeams/prepare-network) gereksinimlerine bakın.
**(Ağ hızınız en az 1,5 Mb/sn değilse Remote Assist'in çalışmaya devam eder. Ancak kalite düşük olabilir).**
1. Ağ güvenlik duvarında bu bağlantı noktalarına ve URL'lere izin verili olduğundan emin Microsoft Teams olun. bağlantı noktalarının en son [listesiyle güncel kalın.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

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

    1. **2. Seçenek:** Seçili kullanıcılara/gruplara cihazları Azure AD'ye katma izni verme **Yönetici olarak Azure portal'de** oturum açın Azure Active Directory Cihazlar Cihaz Ayarlar Kullanıcılar cihazları Azure AD'ye katarak Azure AD'ye katılabilir ve Azure AD'ye Katılmış Cihazların Yapılandırmasını gösteren Seçili  >    >    >    >
 **** 
 ![ Görüntüye ayarlayın.](images/azure-ad-image.png)

    1. **3. Seçenek:** Tüm kullanıcıların cihazlarını etki alanına eklemesini engelleyebilirsiniz. Bu, tüm cihazların el ile kaydolması gerektirmektedir.

## <a name="mobile-device-manager-guidance"></a>Mobil Cihaz Yöneticisi Kılavuzu

### <a name="ongoing-device-management"></a>Devam eden cihaz yönetimi

> [!NOTE]
> Bu adım yalnızca, şirketiniz şirket şirket yönetimi planlamalarında HoloLens.

Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza bağlıdır.  Çoğu genel işleve sahiptir ancak kullanıcı arabirimi büyük ölçüde değişiklik gösterebilir.

1. [CSP'ler (Yapılandırma](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Hizmeti Sağlayıcıları), ağ üzerinde cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak tanır. Başvuru için [CSP'HoloLens listesine](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) bakın.

1. [Uyumluluk ilkeleri,](/intune/device-compliance-get-started) cihazların kurumsal altyapınıza uyumlu olması için karşılaması gereken kurallar ve ayarlardır. Uyumlu olmayan cihazların şirket kaynaklarına erişimini engellemek için Koşullu Erişim ile bu ilkeleri kullanın. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

1. [Uyumluluk İlkesi oluşturun.](/intune/protect/compliance-policy-create-windows)

1. Koşullu Erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesine izin verir/bunu geri verir. CA Dağıtımınızı planlama ve En [İyi Yöntemler belgelerini yararlı](/azure/active-directory/conditional-access/plan-conditional-access) [bulabilirsiniz.](/azure/active-directory/conditional-access/best-practices)

1. [Bu makalede,](/intune/fundamentals/windows-holographic-for-business) intune'un yönetim araçları hakkında bilgi HoloLens.

1. [Cihaz profili oluşturma](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Güncelleştirmeleri yönetme

Intune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil olmak üzere Windows 10 cihazlar için güncelleştirme halkaları adlı bir özellik içerir. Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yük olduğunu belirleyen bir grup ayar içerir.

Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.  Güncelleştirmeleri güncelleştirmeye hazır olana kadar süresiz olarak duraklatmayı da seçebilirsiniz.

[Intune ile güncelleştirme halkalarını yapılandırma hakkında daha fazla bilgi okuyun.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Uygulama yönetimi

Şu HoloLens uygulamaları yönetin:

1. Microsoft Store  
  Uygulama Microsoft Store, uygulamaları uygulama dağıtım ve uygulama dağıtımları için en iyi HoloLens.  Mağazada zaten mevcut olan HoloLens bir dizi temel uygulama vardır veya kendi uygulamalarınızı [yayımlayın.](/windows/uwp/publish/)  
  Mağazada bulunan tüm uygulamalar herkese açık bir şekilde kullanılabilir, ancak kabul edilebilir değilse uygulamanın genel kullanıma İş İçin Microsoft Store.  

1. [İş İçin Microsoft Store](/microsoft-store/)  
  İş İçin Microsoft Store ve Eğitim, kurumsal ortamınız için özel bir depodur.  Bu araç, Microsoft Store uygulamaları bulmak Windows 10 HoloLens, dağıtma ve yönetmeye yardımcı olacak yerleşik uygulamaları kullanmanızı sağlar.  Ayrıca, ticari ortamınıza özgü ancak dünyaya değil, uygulamaları dağıtmanıza da olanak sağlar.

1. Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi  
  Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş hattı uygulamalarını doğrudan kayıtlı bir cihaz kümesine dağıtmak için bir yol sağlar.  [Intune uygulaması yüklemesi için bu makaleye bakın.](/intune/apps-deploy)

1. _önerilmez_ Cihaz Portalı  
  Uygulamalar doğrudan HoloLens Windows Cihaz Portalı.  Geliştirici Modunun cihaz portalını kullanmak için etkinleştirilmesi gerektirildiğinden bu önerilmez.

uygulama yükleme hakkında [daha fazla bilgi için HoloLens.](hololens-install-apps.md)

### <a name="certificates"></a>Sertifikalar

Sertifikaları MDM sağlayıcınız aracılığıyla dağıtabilirsiniz. Şirketiniz sertifika gerektiriyorsa, Intune PKCS, PFX ve SCEP'yi destekler. Hangi sertifikanın şirket için doğru olduğunu anlamak önemlidir. Hangi sertifikanın [sizin için en](/intune/protect/certificates-configure) uygun olduğunu belirlemek için lütfen sertifika yapılandırmaları belgelerini ziyaret edin. HoloLens Kimlik Doğrulaması için sertifika kullanmayı planlıyorsanız, PFX veya SCEP sizin için uygun olabilir.

SCEP kullanmak için [aşağıdaki adımlara bakın.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Holographics for Business Commercial Suite'e Yükseltme

> [!NOTE]
> Windows Holographics for Business (ticari paket), yalnızca 1. nesil HoloLens cihazlara yöneliktir. Profil 2 cihaza HoloLens uygulanmaz.

Holografik yükseltme belgelerinde ticari pakete yükseltme [yönergelerini](/intune/configuration/holographic-upgrade) bulabilirsiniz.

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Microsoft Intune Kullanarak Bilgi Noktası Modunu Yapılandırma

1. Eşitleme Microsoft Store Intune'a (Aşağıdaki yönergelere [bakın).](/intune/apps/windows-store-for-business)

1. Uygulama ayarlarınızı denetleme
    1. Microsoft Store Business hesabınızla oturum açın
    1. **> Ürün ve Hizmetleri > Uygulamaları ve Yazılımlarını Yönetme > Eşitlemek istediğiniz uygulamayı seçin > Özel Mağaza Kullanılabilirliği > "Herkes" veya "Belirli Gruplar"ı seçin**
        >[!NOTE]
        >Istediğiniz uygulamayı görmüyorsanız mağazada uygulama arayarak uygulamayı "ala"nız gerekir. **Sağ üst köşedeki "Ara"** çubuğuna tıklayın > uygulamanın adını yazın > tıklayın ve "Al" > seçin.
    1. Uygulamalarınızı Intune'da > İstemci Uygulamaları **> Uygulamalar'da görmüyorsanız,** uygulamalarınızı [yeniden eşitlemeniz gerekir.](/intune/apps/windows-store-for-business#synchronize-apps)

1. [Bilgi Noktası modu için cihaz profili oluşturma](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> "Kullanıcı oturum açma türü" olarak "Azure AD" kullanarak farklı kullanıcıları farklı Bilgi Noktası Modu deneyimleri olacak şekilde yapılandırabilirsiniz. Ancak, bu seçenek yalnızca Çoklu Uygulama bilgi noktası modunda kullanılabilir. Çoklu Uygulama bilgi noktası modu yalnızca bir uygulamayla ve birden çok uygulamayla çalışır.

![Intune'da Bilgi Noktası Modu Yapılandırmasını gösteren resim.](images/aad-kioskmode.png)

Diğer MDM hizmetleri için yönergeler için sağlayıcınızın belgelerine bakın. MDM [HoloLens bilgi](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanıyorsanız bilgi noktası yönergelerine bakın.

## <a name="certificates-and-authentication"></a>Sertifikalar ve Kimlik Doğrulaması

Sertifikalar [MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)aracılığıyla dağıtılabilir (MDM Bölümünde "sertifikalar" bölümüne bakın). Sertifikalar ayrıca paket sağlama aracılığıyla HoloLens dağıtılabilir. Daha fazla [HoloLens için lütfen bkz.](hololens-provisioning.md) HoloLens Sağlama.

### <a name="additional-intune-quick-links"></a>Ek Intune Hızlı Bağlantıları

1. [Profil Oluşturma:](/intune/configuration/device-profile-create) Profiller, kuruluşta cihazlara gelecek ayarları eklemenize ve yapılandırmanıza olanak tanır.

