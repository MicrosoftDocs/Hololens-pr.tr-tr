---
title: Dış Istemciler dağıtım kılavuzu
description: dış istemciler için HoloLens 2 için dağıtım kılavuzu (örnek olarak uzaktan yardım ile)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659903"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>uzaktan yardım ile dış istemcilere HoloLens 2 dağıtma

bu kılavuz, bt uzmanlarının kuruluşunda Microsoft HoloLens 2 cihaz dağıtmalarına yardımcı olur:

1. bulut connect HoloLens 2 cihaz
1. 2 cihazdan kullanıma yönelik HoloLens, dış istemcilere kullanım için kredi
1. Güvenli ödünç verilen cihazlar

bu kılavuzda, çoğu HoloLens 2 dağıtım senaryosu ve müşterilerin dışarıdan kullanım için uzaktan yardım dağıttığı [yaygın sorunlar](#common-concerns) için geçerli olan [genel HoloLens 2 dağıtım önerileri](#general-deployment-recommendations-and-instructions) sağlanır.

## <a name="scenario-description"></a>Senaryo Açıklaması

Contoso şirketi, bu belgenin amacı doğrultusunda, kısa vadeli veya uzun vadeli kullanım için harici bir istemcinin tesisine HoloLens 2 bir cihaz göndermek istemektedir. istemci, hizmet verme hizmetlerine ihtiyaç duyduğunda, contoso şirketi tarafından sunulan kimlik bilgilerini kullanarak HoloLens 2 cihazında oturum açıp contoso şirketinin uzmanlarıyla iletişim kurmak için uzaktan yardım 'ı kullanır.

[Burada](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)uzaktan yardım hakkında daha fazla bilgi edinin.

### <a name="requirements-for-this-scenario"></a>Bu senaryo için gereksinimler

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. [Intune](/mem/intune/fundamentals/free-trial-sign-up) gibi mobil Device Manager
1. Uzaktan Yardım lisansı
    1. [Uzaktan Yardım satın alın](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Deneme uzaktan yardım](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Yaygın sorunlar

- [Dış istemcilerin birbirleriyle iletişim kurma yeteneğine sahip olmamasını sağlama](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [İstemcilerin şirket kaynaklarına erişiminin olmadığından emin olun](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Uygulamaları kısıtlama](#how-to-restrict-apps)
- [Parolaları yönetme](#how-to-manage-passwords)
- [İstemcilerin sohbet geçmişine erişiminin olmadığından emin olun](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Dış istemcilerin birbirleriyle iletişim kurma yeteneğine sahip olmamasını sağlama

HoloLens çağrılarına yönelik uzaktan yardım HoloLens desteklenmediğinden, istemciler birbirleriyle iletişim kurabiliyor, ancak yapamaz. İstemcilerin arayabileceği ve çağırabileceğini daha fazla kısıtlamak için  [bilgi engelleri](/microsoft-365/compliance/information-barriers) , bir istemcinin ile iletişim kurabildiğini kısıtlayabilir. Dikkate alınması gereken başka bir seçenek de [kapsamlı Dizin arama](/MicrosoftTeams/teams-scoped-directory-search) kullanmaktır

 > [!NOTE]
> Çoklu oturum açma etkin olduğundan, bu tarayıcıyı [**WDAC**](/hololens/windows-defender-application-control-wdac)kullanarak devre dışı bırakmanız önemlidir. bir dış istemci tarayıcıyı açarsa ve Teams web sürümünü kullanıyorsa, istemcinin çağrı/sohbet geçmişine erişimi olur.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>İstemcilerin şirket kaynaklarına erişiminin olmadığından emin olun

Göz önünde bulundurmanız gereken iki seçenek vardır.

İlk seçenek çok katmanlı bir yaklaşımdır:

1. Yalnızca kullanıcının gerektirdiği lisansları atayın. kullanıcıya OneDrive, Outlook, SharePoint, Yammer vb. atamadıysanız, bu kaynaklara erişimi olmayacaktır. Kullanıcıların başlaması gereken tek lisans uzak yardım, Intune ve AAD lisanslarına sahip olur.
1. İstemcilerin erişmesini istemediğiniz uygulamaları (örneğin, e-posta) engelleyin (bkz. [uygulamaları kısıtlama](#how-to-restrict-apps)).
1. Kullanıcı adlarını ve parolayı istemcilerle paylaşmayın. HoloLens 2 ' de oturum açmak için bir e-posta ve sayısal pın gereklidir.

İkinci seçenek, istemcileri barındıran ayrı bir kiracı oluşturmaktır (bkz. görüntü 1,1).

**Görüntü 1,1**

![Hizmet kiracı görüntüsü](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Uygulamaları kısıtlama

[bilgi noktası modu](/hololens/hololens-kiosk) ve/veya [WDAC (Windows Defender uygulama denetimi)](/hololens/windows-defender-application-control-wdac) , uygulamaları kısıtlamak için seçeneklerdir.

### <a name="how-to-manage-passwords"></a>Parolaları yönetme

1. Parola kullanım süresini kaldırın. Ancak bu, bir hesabın tehlikeye düşmesi olasılığını artırır. NıST parola önerisi her 30-90 günde bir parola değiştirir.
1. HoloLens 2 cihazlarının parola kullanım süresini 90 gün olacak şekilde genişletin.
1. Parolaları değiştirmek için cihazların contoso 'ya döndürülmesi gerekir. Ancak, cihazların 90 + gün boyunca istemcinin tesislerinde olması bekleniyorsa, bu sorun ortaya çıkarabilir.  
1. Birden çok istemciye gönderilen cihazlar için, cihazı istemcilere teslim etmeden önce parolaları sıfırlayın.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>İstemcilerin sohbet geçmişine erişiminin olmadığından emin olun

Uzaktan Yardım, her oturum sonrasında sohbet geçmişini temizler. ancak, sohbet geçmişi Microsoft Teams kullanıcı tarafından kullanılabilir.

> [!NOTE]
> Çoklu oturum açma etkin olduğundan, bu tarayıcıyı [**WDAC**](/hololens/windows-defender-application-control-wdac)kullanarak devre dışı bırakmanız önemlidir. bir dış istemci tarayıcıyı açarsa ve Teams web sürümünü kullanıyorsa, istemcinin çağrı/sohbet geçmişine erişimi olur.

## <a name="general-deployment-recommendations-and-instructions"></a>genel dağıtım Öneriler ve yönergeleri

HoloLens 2 dağıtım adımı için aşağıdakiler önerilir:

1. [en son HoloLens işletim sistemi sürümünü](https://aka.ms/hololens2download) temel yapı olarak kullanın.
1. Kullanıcı tabanlı veya cihaz tabanlı lisanslar atama:
    1. Kullanıcı tabanlı ve cihaz tabanlı lisanslar, her ikisi de aşağıdaki adımları izler:
        1. [AAD 'de bir grup oluşturun ve](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/ra kullanıcıları için üye ekleyin.
        1. Bu gruba [cihaz tabanlı veya Kullanıcı tabanlı lisanslar atayın](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) .
        1. Seçim MDM ilkeleri için grupları hedefleyebilirsiniz.

1. Cihazların kiracınıza katılması, [otomatik olarak kaydolmaları](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)ve [Otomatik pilot](/hololens/hololens2-autopilot)aracılığıyla yapılandırılması gerekir.
    1. Lütfen cihazdaki ilk kullanıcının cihaz sahibi olacağını unutmayın.
    1. Cihaz AAD 'ye katılırsa, katılmayı gerçekleştiren kullanıcının cihaz sahibi olduğunu lütfen unutmayın.
    1. Daha fazla bilgi için bkz. [cihaz sahibi](/hololens/security-adminless-os#device-owner).
1. Kiracı, yalnızca kiracınıza katılebilecek şekilde cihazı [kilitler](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) .
    1. **Ek bağlantı:** [kiracı kilidi CSP](/windows/client-management/mdm/tenantlockdown-csp).
1. [Buraya](/hololens/hololens-global-assigned-access-kiosk)genel atanan erişimi kullanarak bilgi noktası yapılandırın.
1. İzleme (isteğe bağlı) yeteneklerini devre dışı bırakmayı öneririz:
    1. Cihazı geliştirici moduna [buraya](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)koyabilme olanağı.
    1. HoloLens bir bilgisayara bağlamak için USB ' i [devre dışı bırakma özelliği USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > USB 'yi devre dışı bırakmak istemiyor, ancak USB kullanarak cihaza sağlama paketi uygulama olanağı istiyorsanız [**burada**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)listelenen yönergeleri izleyin.

1. HoloLens 2 cihazında uygulamalara izin vermek veya bunları engellemek için [WDAC](/hololens/windows-defender-application-control-wdac) kullanın.
1. Kurulumun bir parçası olarak uzak yardım 'ı en son sürüme güncelleştirin. Bunu yapmak için iki seçenek vardır:
    1. bu, Windows **Microsoft Store--> uzaktan yardım--> ve uygulamayı güncelleştir '** e giderek yapılabilir.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -otomatik uygulama güncelleştirmelerine izin veren-varsayılan olarak etkindir. Güncelleştirmeleri almak için cihazı prize takılı tutun.
1. Kullanıcıların istemci sitelerindeki Konuk ağlara bağlanmasına izin vermek için ağ ayarları dışında [Tüm ayarlar sayfalarını devre dışı bırakın](/hololens/settings-uri-list) .
1. [HoloLens güncelleştirmelerini yönetme](/hololens/hololens-updates)
    1. [İşletim sistemi güncelleştirmelerini denetleme](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) veya ücretsiz olarak akışa izin verme seçeneği.
1. [Ortak cihaz kısıtlamaları](/hololens/hololens-common-device-restrictions).
