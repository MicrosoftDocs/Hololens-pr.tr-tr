---
title: Dış istemcilere bulut HoloLens 2 dağıtma
description: Dış İstemciler için HoloLens 2 için dağıtım kılavuzu (örnek olarak Uzaktan yardım ile)
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190336"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Dış istemcilere bulut HoloLens 2 dağıtma

Bu kılavuz, Bulut Bağlantılı Dağıtım [Kılavuzu'nın bir ekidir.](hololens2-cloud-connected-overview.md) Bu, kuruluşta kısa veya uzun süreli kullanım için HoloLens 2 cihazı bir dış istemcinin tesisine sevk etmek istediği durumlarda kullanılır. Dış istemci, HoloLens 2 cihazında oturum açmak için, kuruluş tarafından sağlanan kimlik bilgilerini kullanır ve [Remote Assist'i](/dynamics365/mixed-reality/remote-assist/ra-overview) kullanarak uzmanlarınıza ulaşabilirsiniz. Bu kılavuz, [HoloLens 2](#general-deployment-recommendations) dağıtım senaryosunun çoğu için geçerli olan 2 dağıtım [](#common-external-client-deployment-concerns) önerisi ve müşterilerin dış kullanım için Remote Assist dağıtırken sahip olduğu yaygın endişeler HoloLens 2 dağıtım önerisi sağlar. 

## <a name="prerequisites"></a>Önkoşullar

HoloLens 2'yi harici [olarak dağıtmak](hololens2-cloud-connected-overview.md) için Bulut Bağlantılı Dağıtım Kılavuzu'HoloLens yerinde olması gerekir.

- MDM Otomatik Kaydı ile Azure AD'ye Katılma— MDM ile yönetilen (Intune)
- Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
    - Cihaz başına tek veya birden çok kullanıcı de destekler.

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist lisanslama ve gereksinimleri

- Azure AD hesabı (aboneliği satın almak ve lisans atamak için gereklidir)
- [Remote Assist aboneliği](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (veya [Remote Assist Deneme sürümü)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Bkz. [Remote Assist hakkında daha fazla bilgi.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist kullanıcısı

- Remote Assist lisansı
- Ağ Bağlantısı

### <a name="microsoft-teams-user"></a>Microsoft Teams kullanıcı

- Microsoft Teams veya [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Ağ bağlantısı

## <a name="general-deployment-recommendations"></a>Genel dağıtım önerileri

Dış dağıtım 2 dağıtımı için HoloLens adımları öneririz:

1. Temel [derlemeniz olarak HoloLens işletim sistemi](https://aka.ms/hololens2download) sürümünü kullanın.
1. Aşağıdaki adımları kullanarak kullanıcı tabanlı veya cihaz tabanlı lisanslar attayın:
    1. [AAD'de bir grup oluşturun ve HoloLens/RA](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) kullanıcıları için üye ekleyin.
    1. [Bu gruba cihaz tabanlı veya kullanıcı tabanlı lisanslar](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) attayın.
    1. (İsteğe bağlı) Mobil cihaz yönetimi [(MDM) ilkeleri için hedef](hololens-enroll-mdm.md) gruplar.

1. AAD cihazlarını kiracınıza katarak otomatik [olarak kaydetme ve](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm) [Autopilot aracılığıyla yapılandırma.](/hololens/hololens2-autopilot) Daha fazla bilgi için bkz. [cihaz sahibi.](/hololens/security-adminless-os#device-owner)
    1. Cihaza ilk kullanıcı cihaz sahibi olur.
    1. Cihaz AAD'ye katılmışsa, birleştirmeyi yapan kullanıcı cihaz sahibi yapılır.
    
1. [Kiracı,](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) yalnızca kiracınız tarafından birleştirilene kadar cihazı kilitler.
    1. Ayrıca [bkz. Kiracı kilidi CSP.](/windows/client-management/mdm/tenantlockdown-csp)

1. [Genel olarak atanan erişimi kullanarak Bilgi Noktası modunu yapılandırma.](/hololens/hololens-global-assigned-access-kiosk)

1. Aşağıdaki (isteğe bağlı) özellikleri devre dışı bırak:
    1. Cihazı burada geliştirici moduna [alabilme.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Tarihi kopyalamak için HoloLens USB'yi devre dışı bırakmak için bilgisayara [bağlanabilme.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > USB'yi devre dışı bırakmak istemiyor ancak USB kullanarak cihaza sağlama paketi uygulama olanağını kullanmak için, sağlama paketi yüklemesine izin [verme yönergelerini izleyin.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Windows Defender [2 cihazında uygulamalara izin](/hololens/windows-defender-application-control-wdac) vermek veya bu uygulamaları engellemek için HoloLens Denetimi(WDAC) kullanın.
1. Kurulumun bir parçası olarak Remote Assist'i en son sürüme güncelleştirin. Aşağıdaki iki seçeneği göz önünde kullanın:
    1. **--Windows Microsoft Store Remote Assist --> --> ve Uygulamayı Güncelleştir'e gidin.**
    1. [Otomatik uygulama güncelleştirmelerine izin veren ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) varsayılan olarak etkindir. Güncelleştirmeleri almak için cihazı bağlı durumda tutma.
1. [Kullanıcıların istemci sitelerinden konuk](/hololens/settings-uri-list) ağlara bağlanmasına izin vermek için ağ ayarları dışındaki tüm ayarlar sayfalarını devre dışı bırak.
1. [Güncelleştirmeleri HoloLens yönetme](/hololens/hololens-updates)
    1. Işletim sistemi [güncelleştirmelerini denetleme veya serbest](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) akışa izin verme seçeneği.
1. Yaygın [cihaz kısıtlamalarını ayarlayın.](/hololens/hololens-common-device-restrictions)

Artık dış istemcileriniz kendi 2. HoloLens hazırdır.

## <a name="common-external-client-deployment-concerns"></a>Yaygın dış istemci dağıtımı sorunları

- [İstemcilerin birbirleriyle iletişim kuramalarını sağlama](#ensure-that-external-clients-cant-communicate-with-one-another)
- [İstemcilerin şirket kaynaklarına erişemaylarını sağlama](#ensure-that-clients-wont-have-access-to-company-resources)
- [Uygulamaları gizleme veya kısıtlama](#hidden-or-restricted-apps)
- [İstemcileriniz için parolaları yönetme](#password-management-for-your-clients) 
- [İstemcilerin sohbet geçmişine erişemalarını sağlama](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Dış istemcilerin birbirleriyle iletişim kuramaylarından emin olmak

Uzaktan HoloLens HoloLens için uzaktan yardım desteği desteklenmiyor. İstemciler araysa da birbirleriyle iletişim kuramalarına neden olur. [Bir istemcinin Microsoft 365](/microsoft-365/compliance/information-barriers) arayabilin ve arayabilesini kısıtlayan bilgiler engeli. Bir diğer seçenek de kapsamlı [dizin Microsoft Teams kullanmaktır.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Çoklu oturum açma etkinleştirildiğinden, Uygulama Denetimi [(WDAC)](/hololens/windows-defender-application-control-wdac)Windows Defender tarayıcıyı devre dışı bırakmak önemlidir. Bir dış istemci tarayıcıyı açar ve Teams web sürümünü kullanırsa, istemci sohbet geçmişinize erişime sahip olur.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>İstemcilerin şirket kaynaklarına erişimi olmayacaktır

Göz önünde bulundurarak iki seçenek vardır.

İlk seçenek çok katmanlı bir yaklaşımdır:

1. Yalnızca kullanıcının gerektirdiği lisansları attay. OneDrive, Outlook, SharePoint, Yammer vb. atamayacaksanız, kullanıcının bu kaynaklara erişimi olmaz. Kullanıcıların ihtiyacı olacak tek lisans, başlamak için Remote Assist, Intune ve AAD lisanslarıdır.
1. İstemcilerin erişmelerini istemiyorsanız uygulamaları (e-posta gibi) engelle [(Bkz. Uygulamalar gizlenir veya kısıtlanır).](#apps are hidden or restricted)
1. kullanıcı adlarını veya parolaları istemcilerle paylaşmayın. HoloLens 2'de oturum açmak için bir e-posta ve sayısal PIN gereklidir.

İkinci seçenek, istemcileri barındıran ayrı bir kiracı oluşturmaktır (bkz. Görüntü 1.1).

**Görüntü 1.1**

![Hizmet Kiracısı Görüntüsü.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Gizli veya kısıtlanmış uygulamalar

[Bilgi noktası](/hololens/hololens-kiosk) modu ve/Windows Defender [Uygulama Denetimi (WDAC),](/hololens/windows-efender-application-control-wdac) uygulamaları gizlemeye ve/veya kısıtlamaya yönelik seçeneklerdir.

### <a name="password-management-for-your-clients"></a>İstemcileriniz için parola yönetimi

1. Parola süre sonu'ları kaldırın. Ancak, bu seçenek bir hesabın tehlikeye atılmış olma şansını artırabilir. NIST parola önerisi, parolaları 30-90 günde bir değiştirmektir.
1. 2 cihaz için parola HoloLens süresini 90 günü aşacak şekilde uzatabilirsiniz.
1. Cihazların parolaları değiştirmesi için kuruluşa döndürülleri gerekir. Ancak, cihazların 90'dan fazla gün boyunca istemcinin tesisinde olması bekleniyorsa bu seçenek soruna neden olabilir.  
1. Birden çok istemciye gönderilen cihazlar için, cihazı istemcilere göndermeden önce parolaları sıfırlayın.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>İstemcilerin sohbet geçmişine erişene sahip olmayacaklarını emin olmak

Remote Assist her oturumdan sonra sohbet geçmişini temizler. Ancak, sohbet geçmişi kullanıcıların Microsoft Teams kullanılabilir.

> [!NOTE]
> Çoklu oturum açma etkinleştirildiğinden, Uygulama Denetimi [(WDAC)](/hololens/windows-defender-application-control-wdac)Windows Defender tarayıcıyı devre dışı bırakmak önemlidir.  Bir dış istemci tarayıcıyı açar ve Teams web sürümünü kullanırsa, istemcinin çağrı/sohbet geçmişine erişimi olur.
