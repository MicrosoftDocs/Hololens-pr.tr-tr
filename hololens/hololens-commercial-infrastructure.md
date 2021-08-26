---
title: HoloLens için altyapı yönergeleri
description: kablosuz ağ desteği, uzaktan yardım ve mobil cihaz yönetimi dahil HoloLens cihazlara yönelik altyapı yönergeleri hakkında bilgi edinin.
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
ms.openlocfilehash: 9b306b10ff82603fd238f195beacc300f1a82bf6
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859009"
---
# <a name="configure-your-network-for-hololens"></a>Ağınızı HoloLens için yapılandırma

Belgenin bu bölümü aşağıdaki kişileri gerektirecektir:

1. Ara sunucu/güvenlik duvarında değişiklik yapma izinleri olan ağ yöneticisi
2. Azure Active Directory Yöneticileri
3. Mobil Device Manager Yöneticisi

## <a name="infrastructure-requirements"></a>Altyapı gereksinimleri

HoloLens, temel tarafında Azure ile tümleştirilmiş bir mobil cihaz Windows.  kablosuz ağ kullanılabilirliği (wi-fi) ve Microsoft hizmetleri erişimi olan ticari ortamlarda en iyi şekilde çalışmaktadır.

Kritik bulut Hizmetleri şunları içerir:

- Azure Active Directory (Azure AD)
- Windows Güncelleştirme (WU)

ticari müşterilerin, HoloLens cihazları ölçekli olarak yönetmesi için enterprise mobility management (EMM) veya mobil cihaz yönetimi (MDM) altyapısına ihtiyacı vardır.  bu kılavuz bir örnek olarak [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) kullanır, ancak Microsoft Policy için tam desteğe sahip tüm sağlayıcılar HoloLens destekleyebilir.  HoloLens 2 ' i desteklediklerinde mobil cihaz yönetimi sağlayıcınızı sorun.

HoloLens, sınırlı sayıda bulut bağlantısı kesik deneyimler destekler.

### <a name="wireless-network-eap-support"></a>Kablosuz ağ EAP desteği

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Belirli ağ gereksinimleri

Ağ güvenlik duvarınız üzerinde bu uç nokta [listesine](hololens-offline.md) izin verildiğinden emin olun. bu, HoloLens düzgün çalışmasını sağlayacaktır.

### <a name="remote-assist-specific-network-requirements"></a>Belirli ağ gereksinimlerine uzak yardım

1. Uzaktan Yardım 'ın en iyi performansı için önerilen bant genişliği 1,5 MB/sn 'dir. Ek bilgi için [ayrıntılı ağ gereksinimlerine](/MicrosoftTeams/prepare-network) bakın.
**(Lütfen ağın en az 1,5 Mbps 'Lik ağ hızına sahip olmadığını, uzaktan yardım 'ın çalışmaya devam etmesi gerektiğini unutmayın. Ancak kalite zarar verebilir).**
1. Microsoft Teams çalışmasını sağlamak için bu bağlantı noktalarına ve url 'lere ağ güvenlik duvarında izin verildiğinden emin olun. [En son bağlantı noktası listesiyle](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)güncel kalın.

- [Uzaktan Yardım için belirli ağ gereksinimleri](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)hakkında daha fazla bilgi edinin. 
- [Kuruluşunuzun ağını Microsoft Teams için hazırlama](/MicrosoftTeams/prepare-network) hakkında daha fazla bilgi edinin

### <a name="guides-specific-network-requirements"></a>Belirli ağ gereksinimlerine kılavuzluk eder

Kılavuzlar yalnızca uygulamayı indirmek ve kullanmak için ağ erişimi gerektirir.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Kılavuzu

> [!NOTE]
> Bu adım yalnızca şirketiniz HoloLens yönetimini planlıyorsa gereklidir.

1. Azure AD lisansına sahip olduğunuzdan emin olun.
daha fazla bilgi için lütfen [lisans gereksinimlerini HoloLens](hololens-licenses-requirements.md) .

1. Otomatik kayıt kullanmayı planlıyorsanız, [Azure ad kaydı](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) ' nı yapılandırmanız gerekir.

1. Şirketinizin kullanıcılarının Azure Active Directory (Azure AD) olduğundan emin olun.
Kullanıcıları eklemek için aşağıdaki [yönergelere](/azure/active-directory/fundamentals/add-users-azure-active-directory) bakın.

1. Benzer lisanslara ihtiyaç duyan kullanıcıların aynı gruba eklenmesini öneririz.
    1. [Grup oluşturma](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Gruplara kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Şirketinizin kullanıcılarına (veya kullanıcı grubuna) gerekli lisansların atandığından emin olun.
Lisans atamanız gerekiyorsa, bu [yönergeleri](/azure/active-directory/fundamentals/license-users-groups)izleyin.

1. bu adımı yalnızca kullanıcıların HoloLens/mobil cihazını size kaydetmesi bekleniyorsa (üç seçenek bulunur), bu adımlar, şirketinizin kullanıcılarının (veya bir kullanıcı grubunun) cihaz ekleyebileceği şekilde emin olmanızı sağlar.
    1. **Seçenek 1:** Tüm kullanıcılara cihazları Azure AD 'ye ekleme izni verin.
**Azure Portal yönetici**  >  olarak oturum açın **Azure Active Directory**  >  **Cihazlar**  >  **cihaz Ayarlar**  >
 **Kullanıcıları, cihazları Azure AD 'ye *Tüm* kullanıcılara birleştirebileceği şekilde ayarla**

    1. **Seçenek 2:** seçili kullanıcılara/gruplara cihazları azure ad 'ye eklemek için yönetici Azure Active Directory cihaz cihazı **olarak Azure portal oturum açma** izni verin  >    >    >  **Ayarlar**  >
 **kullanıcılar cihazları azure ad 'ye,** 
 ![ azure ad 'ye katılmış cihazların yapılandırmasını gösteren seçili görüntüye katabilir](images/azure-ad-image.png)

    1. **Seçenek 3:** Tüm kullanıcıların cihazlarını etki alanına katılmasını engelleyebilirsiniz. Bu, tüm cihazların el ile kaydedilmesi gerektiği anlamına gelir.

## <a name="mobile-device-manager-guidance"></a>Mobil Device Manager Kılavuzu

### <a name="ongoing-device-management"></a>Devam eden cihaz yönetimi

> [!NOTE]
> Bu adım yalnızca şirketiniz HoloLens yönetmeyi planlıyorsa gereklidir.

Devam eden cihaz yönetimi, mobil cihaz yönetimi altyapınıza göre değişir.  Çoğu genel işlevselliğe sahiptir ancak kullanıcı arabirimi yaygın olarak farklılık gösterebilir.

1. [CSP 'ler (yapılandırma hizmeti sağlayıcıları)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) ağınızdaki cihazlar için yönetim ayarları oluşturmanıza ve dağıtmanıza olanak sağlar. başvuru için [HoloLens csp 'lerin listesine](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) bakın.

1. [Uyumluluk ilkeleri](/intune/device-compliance-get-started) , cihazların kurumsal altyapınızda uyumlu olması için uyması gereken kural ve ayarlardır. Uyumlu olmayan cihazlarda şirket kaynaklarına erişimi engellemek için bu ilkeleri koşullu erişimle birlikte kullanın. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

1. [Uyumluluk Ilkesi oluşturun](/intune/protect/compliance-policy-create-windows).

1. Koşullu erişim, mobil cihazların ve mobil uygulamaların şirket kaynaklarına erişmesini sağlar/reddeder. Yararlı bulabileceğiniz iki belge, CA dağıtımınızı ve [En Iyi uygulamalarınızı](/azure/active-directory/conditional-access/best-practices) [planlıyor](/azure/active-directory/conditional-access/plan-conditional-access) .

1. [Bu makalede](/intune/fundamentals/windows-holographic-for-business) , ıntune 'un HoloLens için yönetim araçları ele alım.

1. [Cihaz profili oluşturma](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Güncelleştirmeleri yönetme

ıntune, HoloLens 2 ve HoloLens v1 (Holographic for Business ile) dahil Windows 10 cihazları için güncelleştirme halkaları adlı bir özellik içerir. Güncelleştirme halkaları, güncelleştirmelerin nasıl ve ne zaman yükleneceğini tespit eden bir grup ayar içerir.

Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz.  Güncelleştirmeleri, güncelleştirmeye hazırsanız süresiz olarak duraklatıp de seçebilirsiniz.

[Intune ile güncelleştirme halkalarını yapılandırma](/intune/windows-update-for-business-configure)hakkında daha fazla bilgi edinin.

### <a name="application-management"></a>Uygulama yönetimi

HoloLens uygulamalarını yönetme:

1. Microsoft Store  
  Microsoft Store, uygulamaları HoloLens dağıtmak ve kullanmak için en iyi yoldur.  mağazada zaten bulunan harika bir çekirdek HoloLens uygulamalar kümesi vardır veya [kendi kendinize yayımlayabilirsiniz](/windows/uwp/publish/).  
  depodaki tüm uygulamalar herkese açık olarak kullanılabilir, ancak kabul edilebilir değilse İş İçin Microsoft Store kullanıma alın.  

1. [İş İçin Microsoft Store](/microsoft-store/)  
  İş İçin Microsoft Store ve eğitim, kurumsal ortamınız için özel bir depodır.  kuruluşunuzun uygulamalarını bulmak, almak, dağıtmak ve yönetmek için Windows 10 ve HoloLens yerleşik Microsoft Store kullanmanıza olanak sağlar.  Ayrıca ticari ortamınıza özgü olan ancak dünyayı olmayan uygulamaları dağıtmanıza imkan tanır.

1. Intune veya başka bir mobil cihaz yönetimi çözümü aracılığıyla uygulama dağıtımı ve yönetimi  
  Intune dahil olmak üzere çoğu mobil cihaz yönetimi çözümü, iş kolu uygulamalarını doğrudan bir kayıtlı cihaz kümesine dağıtmanın bir yolunu sağlar.  [Intune uygulama yüklemesi](/intune/apps-deploy)için bu makaleye bakın.

1. _önerilmez_ Cihaz portalı  
  uygulamalar, Windows cihaz portalı kullanılarak doğrudan HoloLens de yüklenebilir.  Bu, geliştirici modunun cihaz portalını kullanmak için etkinleştirilmesi gerektiğinden önerilmez.

[HoloLens uygulamalar yükleme](hololens-install-apps.md)hakkında daha fazla bilgi edinin.

### <a name="certificates"></a>Sertifikalar

Sertifika, MDM sağlayıcınız aracılığıyla dağıtabilirsiniz. Şirketiniz sertifika gerektiriyorsa Intune, PKCS, PFX ve SCEP 'yi destekler. Şirketiniz için hangi sertifikanın doğru olduğunu anlamak önemlidir. Size en uygun sertifikayı öğrenmek için lütfen [sertifika yapılandırması](/intune/protect/certificates-configure) belgelerini ziyaret edin. HoloLens kimlik doğrulaması için sertifika kullanmayı planlıyorsanız PFX veya SCEP sizin için uygun olabilir.

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

![Intune 'da bilgi noktası modunun yapılandırılmasını gösteren resim](images/aad-kioskmode.png)

Diğer MDM Hizmetleri için, yönergeler için sağlayıcınızın belgelerine bakın. MDM hizmetinizde bir bilgi noktası ayarlamak için özel bir ayar ve tam XML yapılandırması kullanmanız gerekiyorsa [HoloLens bilgi noktası](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) yönergelerine bakın.

## <a name="certificates-and-authentication"></a>Sertifikalar ve kimlik doğrulama

Sertifikalar, MDM aracılığıyla dağıtılabilir ( [MDM bölümünde](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)"Sertifikalar" konusuna bakın). sertifikalar, paket sağlama aracılığıyla HoloLens da dağıtılabilir. lütfen daha fazla bilgi için [HoloLens sağlama](hololens-provisioning.md) konusuna bakın.

### <a name="additional-intune-quick-links"></a>Ek Intune hızlı bağlantıları

1. [Profil oluşturma:](/intune/configuration/device-profile-create) Profiller, kuruluşunuzdaki cihazlara gönderilecek ayarları eklemenize ve yapılandırmanıza olanak tanır.

