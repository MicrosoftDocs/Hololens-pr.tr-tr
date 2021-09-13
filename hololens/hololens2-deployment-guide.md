---
title: buluta bağlı HoloLens 2 ' nin dış istemcilere dağıtımını yapın
description: dış istemciler için HoloLens 2 için dağıtım kılavuzu (örnek olarak uzaktan yardım ile)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033408"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>buluta bağlı HoloLens 2 ' nin dış istemcilere dağıtımını yapın

Bu kılavuz, [buluta bağlı dağıtım kılavuzu](hololens2-cloud-connected-overview.md)için bir ektir. bu, kuruluşunuzun kısa veya uzun süreli kullanım için bir dış istemcinin tesisine HoloLens 2 cihaz göndermek istediği durumlarda kullanılır. dış istemci, kuruluşunuz tarafından belirtilen kimlik bilgilerini kullanarak HoloLens 2 cihazında oturum açacak ve uzmanlarınıza başvurmak için [uzaktan yardım](/dynamics365/mixed-reality/remote-assist/ra-overview) 'ı kullanacaktır. bu kılavuz, çoğu harici HoloLens 2 dağıtım senaryosu ve müşterilerin dışarıdan kullanım için uzaktan yardım dağıttığı [yaygın sorunlar](#common-external-client-deployment-concerns) için geçerli olan [genel HoloLens 2 dağıtım önerileri](#general-deployment-recommendations) sağlar. 

## <a name="prerequisites"></a>Önkoşullar

HoloLens 2 ' nin dışarıdan dağıtılması için, [bulut bağlantılı dağıtım kılavuzu 'na](hololens2-cloud-connected-overview.md) aşağıdaki altyapının yerinde olması gerekir.

- MDM otomatik kaydı ile Azure AD katılımı — MDM tarafından yönetilen (Intune)
- Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
    - Cihaz başına tek veya birden çok Kullanıcı desteklenir.

### <a name="remote-assist-licensing-and-requirements"></a>Uzaktan Yardım lisanslama ve gereksinimler

- Azure AD hesabı (aboneliğin satın alınması ve lisans atanması için gereklidir)
- [Uzaktan Yardım aboneliği](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Uzaktan Yardım deneme sürümü](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Bkz. [Uzaktan Yardım hakkında daha fazla bilgi edinin](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 uzaktan yardım kullanıcısı

- Uzaktan Yardım lisansı
- Ağ bağlantısı

### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Microsoft Teams veya [Teams freemıum](https://products.office.com/microsoft-teams/free)
- Ağ bağlantısı

## <a name="general-deployment-recommendations"></a>Genel dağıtım önerileri

dış HoloLens 2 dağıtımı için aşağıdaki adımları öneririz:

1. [en son HoloLens işletim sistemi sürümünü](https://aka.ms/hololens2download) temel yapı olarak kullanın.
1. Aşağıdaki adımları izleyerek Kullanıcı tabanlı veya cihaz tabanlı lisanslar atayın:
    1. [AAD 'de bir grup oluşturun ve](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/ra kullanıcıları için üye ekleyin.
    1. Bu gruba [cihaz tabanlı veya Kullanıcı tabanlı lisanslar atayın](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) .
    1. Seçim [Mobil cihaz yönetimi (MDM)](hololens-enroll-mdm.md) ilkeleri için hedef gruplar.

1. AAD cihazlarını kiracınıza ekleyin, [Otomatik kaydedin](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)ve [Autopilot](/hololens/hololens2-autopilot)aracılığıyla yapılandırın. Daha fazla bilgi için bkz. [cihaz sahibi](/hololens/security-adminless-os#device-owner).
    1. Cihazdaki ilk Kullanıcı, cihaz sahibi olacaktır.
    1. Cihaz AAD 'ye katılırsa, katılmayı gerçekleştiren kullanıcıya cihaz sahibi yapılır.
    
1. [Kiracı](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) , cihazı yalnızca kiracınız tarafından birleştirilebilecek şekilde kilitler.
    1. Ayrıca bkz. [kiracı KILIDI CSP](/windows/client-management/mdm/tenantlockdown-csp).

1. [Genel atanan erişimi kullanarak bilgi noktası modunu yapılandırın](/hololens/hololens-global-assigned-access-kiosk).

1. Aşağıdaki (isteğe bağlı) özellikleri devre dışı bırakın:
    1. Cihazı geliştirici moduna [buraya](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)koyabilme olanağı.
    1. HoloLens bir bilgisayara bağlamak için USB ' i [devre dışı bırakma özelliği USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > USB 'yi devre dışı bırakmak, ancak USB kullanarak cihaza bir sağlama paketi uygulamak istiyorsanız, [paketi yüklemeye izin verme yönergelerini](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)izleyin.

1. HoloLens 2 cihazındaki uygulamalara izin vermek veya bunları engellemek için [Windows Defender uygulama denetimi 'ni (WDAC)](/hololens/windows-defender-application-control-wdac) kullanın.
1. Kurulumun bir parçası olarak uzak yardım 'ı en son sürüme güncelleştirin. Aşağıdaki iki seçeneği göz önünde bulundurun:
    1. Windows **Microsoft Store--> uzaktan yardım--> ve uygulamayı güncelleştir '** e gidin.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -otomatik uygulama güncelleştirmelerine izin veren-varsayılan olarak etkindir. Güncelleştirmeleri almak için cihazı prize takılı tutun.
1. Kullanıcıların istemci sitelerindeki Konuk ağlara bağlanmasına izin vermek için ağ ayarları dışında [Tüm ayarlar sayfalarını devre dışı bırakın](/hololens/settings-uri-list) .
1. [HoloLens güncelleştirmelerini yönetme](/hololens/hololens-updates)
    1. [İşletim sistemi güncelleştirmelerini denetleme](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) veya ücretsiz olarak akışa izin verme seçeneği.
1. [Ortak cihaz kısıtlamalarını](/hololens/hololens-common-device-restrictions)ayarlayın.

artık dış istemcileriniz HoloLens 2 ' nin kullanıma hazır hale gelmiştir.

## <a name="common-external-client-deployment-concerns"></a>Ortak dış istemci dağıtım konuları

- [İstemcilerin birbirleriyle iletişim kuramamasını sağlama](#ensure-that-external-clients-cant-communicate-with-one-another)
- [İstemcilerin şirket kaynaklarına erişemeyeceğinden emin olma](#ensure-that-clients-wont-have-access-to-company-resources)
- [Uygulamaları gizleme veya kısıtlama](#hidden-or-restricted-apps)
- [İstemcileriniz için parolaları yönetme](#password-management-for-your-clients) 
- [İstemcilerin sohbet geçmişine erişemeyeceğinden emin olma](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Dış istemcilerin birbirleriyle iletişim kuramaamadığından emin olun

HoloLens çağrılarına HoloLens uzak yardım desteklenmez. İstemciler arayabilir, ancak birbirleriyle iletişim kuramaz. [Microsoft 365 'teki bilgi engelleri](/microsoft-365/compliance/information-barriers) , bir istemcinin arama ve çağrı yapma konusunda daha fazla kısıtlayabilir. diğer bir seçenek de [Microsoft Teams kapsamlı dizin araması](/MicrosoftTeams/teams-scoped-directory-search)kullanmaktır.

 > [!NOTE]
> çoklu oturum açma etkin olduğundan, [Windows Defender uygulama denetimi (WDAC)](/hololens/windows-defender-application-control-wdac)kullanılarak tarayıcıyı devre dışı bırakmak önemlidir. bir dış istemci tarayıcıyı açarsa ve Teams web sürümünü kullanıyorsa, istemcinin sohbet geçmişinize erişimi olur.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>İstemcilerin şirket kaynaklarına erişimi olmadığından emin olun

Göz önünde bulundurmanız gereken iki seçenek vardır.

İlk seçenek çok katmanlı bir yaklaşımdır:

1. Yalnızca kullanıcının gerektirdiği lisansları atayın. OneDrive, Outlook, SharePoint, Yammer vb. atamadıysanız, kullanıcının bu kaynaklara erişimi olmayacaktır. Kullanıcıların başlaması gereken tek lisans uzak yardım, Intune ve AAD lisanslarına sahip olur.
1. İstemcilerin erişmesini istemediğiniz uygulamaları (örneğin, e-posta) engelleyin (bkz. [uygulamalar gizli veya kısıtlanmış](#apps are hidden or restricted)).
1. Kullanıcı adlarını ve parolayı istemcilerle paylaşmayın. HoloLens 2 ' de oturum açmak için bir e-posta ve sayısal pın gereklidir.

İkinci seçenek, istemcileri barındıran ayrı bir kiracı oluşturmaktır (bkz. görüntü 1,1).

**Görüntü 1,1**

![Hizmet kiracı görüntüsü.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Gizli veya kısıtlanmış uygulamalar

[bilgi noktası modu](/hololens/hololens-kiosk) ve/veya [Windows Defender uygulama denetimi (WDAC)](/hololens/windows-efender-application-control-wdac) , uygulamaları gizleme ve/veya kısıtlama seçenekleridir.

### <a name="password-management-for-your-clients"></a>İstemcileriniz için parola yönetimi

1. Parola kullanım süresini kaldırın. Ancak, bu seçenek bir hesabın tehlikeye düşmesi olasılığını artırabilir. NıST parola önerisi her 30-90 günde bir parola değiştirir.
1. HoloLens 2 cihazlarının parola kullanım süresini 90 gün olacak şekilde genişletin.
1. Parolaları değiştirmek için cihazların kuruluşunuza döndürülmesi gerekir. Ancak, cihazların 90 + gün boyunca istemcinin tesislerinde olması bekleniyorsa, bu seçenek soruna neden olabilir.  
1. Birden çok istemciye gönderilen cihazlar için, cihazı istemcilere teslim etmeden önce parolaları sıfırlayın.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>İstemcilerin sohbet geçmişine erişiminin olmadığından emin olun

Uzaktan Yardım, her oturum sonrasında sohbet geçmişini temizler. ancak, sohbet geçmişi Microsoft Teams kullanıcılara sunulacaktır.

> [!NOTE]
> çoklu oturum açma etkin olduğundan, [Windows Defender uygulama denetimi (WDAC)](/hololens/windows-defender-application-control-wdac)kullanılarak tarayıcıyı devre dışı bırakmak önemlidir.  bir dış istemci tarayıcıyı açarsa ve Teams web sürümünü kullanıyorsa, istemcinin çağrı/sohbet geçmişine erişimi olur.
