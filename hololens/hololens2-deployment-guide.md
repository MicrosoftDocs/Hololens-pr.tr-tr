---
title: Dış Istemciler dağıtım kılavuzu
description: Dış Istemciler için HoloLens 2 için dağıtım kılavuzu (örnek olarak uzaktan yardım ile)
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379016"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Uzaktan Yardım ile, HoloLens 2 ' ye dış Istemcilere dağıtım

Bu kılavuz, BT uzmanlarının kuruluşlarındaki Microsoft HoloLens 2 cihazlarını dağıtmalarına yardımcı olur:

1. Cloud Connect HoloLens 2 cihazları
1. Kullanım için, HoloLens 2 cihazlarını dış istemcilere ödünç verme
1. Güvenli ödünç verilen cihazlar

Bu kılavuzda, birçok HoloLens 2 dağıtım senaryosu ve müşterilerin dışarıdan kullanım için uzaktan yardım dağıttığı [yaygın sorunlar](#common-concerns) için geçerli olan [genel HoloLens 2 dağıtım önerileri](#general-deployment-recommendations-and-instructions) sağlanır.

## <a name="scenario-description"></a>Senaryo Açıklaması

Contoso şirketi, bu belgenin amacı doğrultusunda, kısa vadeli veya uzun vadeli kullanım için bir dış istemcinin tesisine bir HoloLens 2 cihazı göndermek istemektedir. İstemci, hizmet verme makinelerimizde, contoso şirketi tarafından sunulan kimlik bilgilerini kullanarak HoloLens 2 cihazında oturum açıp contoso şirketinin uzmanlarıyla iletişim kurmak için uzaktan yardım 'ı kullanır.

[Burada](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)uzaktan yardım hakkında daha fazla bilgi edinin.

### <a name="requirements-for-this-scenario"></a>Bu senaryo için gereksinimler

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up) gibi mobil Device Manager
1. Uzaktan Yardım lisansı
    1. [Uzaktan Yardım satın alın](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Deneme uzaktan yardım](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Yaygın sorunlar

- [Dış istemcilerin birbirleriyle iletişim kurma yeteneğine sahip olmamasını sağlama](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [İstemcilerin şirket kaynaklarına erişiminin olmadığından emin olun](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Uygulamaları kısıtlama](#how-to-restrict-apps)
- [Parolaları yönetme](#how-to-manage-passwords)
- [İstemcilerin sohbet geçmişine erişiminin olmadığından emin olun](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Dış istemcilerin birbirleriyle iletişim kurma yeteneğine sahip olmamasını sağlama

HoloLens 'e yönelik HoloLens çağrılarına uzak yardım desteklenmediğinden, istemciler birbirleriyle iletişim kurabilir, ancak yapamaz. İstemcilerin arayabileceği ve çağırabileceğini daha fazla kısıtlamak için  [bilgi engelleri](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) , bir istemcinin ile iletişim kurabildiğini kısıtlayabilir. Dikkate alınması gereken başka bir seçenek de [kapsamlı Dizin arama](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search) kullanmaktır

 > [!NOTE]
> Çoklu oturum açma etkin olduğundan, bu tarayıcıyı [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)kullanarak devre dışı bırakmanız önemlidir. Bir dış istemci tarayıcıyı açarsa ve takımlar Web sürümünü kullanıyorsa, istemci, çağrı/sohbet geçmişine erişim sahibi olur.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>İstemcilerin şirket kaynaklarına erişiminin olmadığından emin olun

Göz önünde bulundurmanız gereken iki seçenek vardır.

İlk seçenek çok katmanlı bir yaklaşımdır:

1. Yalnızca kullanıcının gerektirdiği lisansları atayın. Kullanıcıya OneDrive, Outlook, SharePoint, Yammer, vb. atayamazsınız, bu kaynaklara erişimi olmayacaktır. Kullanıcıların başlaması gereken tek lisans uzak yardım, Intune ve AAD lisanslarına sahip olur.
1. İstemcilerin erişmesini istemediğiniz uygulamaları (örneğin, e-posta) engelleyin (bkz. [uygulamaları kısıtlama](#how-to-restrict-apps)).
1. Kullanıcı adlarını ve parolayı istemcilerle paylaşmayın. HoloLens 2 ' de oturum açmak için bir e-posta ve sayısal PIN gerekir.

İkinci seçenek, istemcileri barındıran ayrı bir kiracı oluşturmaktır (bkz. görüntü 1,1).

**Görüntü 1,1**

![Hizmet kiracı görüntüsü](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Uygulamaları kısıtlama

[Bilgi noktası modu](https://docs.microsoft.com/hololens/hololens-kiosk) ve/veya [WDac (Windows Defender uygulama denetimi)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) , uygulamaları kısıtlamak için seçeneklerdir.

### <a name="how-to-manage-passwords"></a>Parolaları yönetme

1. Parola kullanım süresini kaldırın. Ancak bu, bir hesabın tehlikeye düşmesi olasılığını artırır. NıST parola önerisi her 30-90 günde bir parola değiştirir.
1. HoloLens 2 cihazlarının parola kullanım süresini 90 gün olacak şekilde genişletin.
1. Parolaları değiştirmek için cihazların contoso 'ya döndürülmesi gerekir. Ancak, cihazların 90 + gün boyunca istemcinin tesislerinde olması bekleniyorsa, bu sorun ortaya çıkarabilir.  
1. Birden çok istemciye gönderilen cihazlar için, cihazı istemcilere teslim etmeden önce parolaları sıfırlayın.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>İstemcilerin sohbet geçmişine erişiminin olmadığından emin olun

Uzaktan Yardım, her oturum sonrasında sohbet geçmişini temizler. Ancak sohbet geçmişi, Microsoft ekipleri kullanıcısı için de kullanılabilir.

> [!NOTE]
> Çoklu oturum açma etkin olduğundan, bu tarayıcıyı [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)kullanarak devre dışı bırakmanız önemlidir. Bir dış istemci tarayıcıyı açarsa ve takımlar Web sürümünü kullanıyorsa, istemci, çağrı/sohbet geçmişine erişim sahibi olur.

## <a name="general-deployment-recommendations-and-instructions"></a>Genel dağıtım önerileri ve yönergeleri

HoloLens 2 dağıtım adımları için aşağıdakiler önerilir:

1. [En son HoloLens IŞLETIM sistemi sürümünü](https://aka.ms/hololens2download) temel yapı olarak kullanın.
1. Kullanıcı tabanlı veya cihaz tabanlı lisanslar atama:
    1. Kullanıcı tabanlı ve cihaz tabanlı lisanslar, her ikisi de aşağıdaki adımları izler:
        1. [AAD 'de bir grup oluşturun ve](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/ra kullanıcıları için üye ekleyin.
        1. Bu gruba [cihaz tabanlı veya Kullanıcı tabanlı lisanslar atayın](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) .
        1. Seçim MDM ilkeleri için grupları hedefleyebilirsiniz.

1. Cihazların kiracınıza katılması, [otomatik olarak kaydolmaları](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)ve [Otomatik pilot](https://docs.microsoft.com/hololens/hololens2-autopilot)aracılığıyla yapılandırılması gerekir.
    1. Lütfen cihazdaki ilk kullanıcının cihaz sahibi olacağını unutmayın.
    1. Cihaz AAD 'ye katılırsa, katılmayı gerçekleştiren kullanıcının cihaz sahibi olduğunu lütfen unutmayın.
    1. Daha fazla bilgi için bkz. [cihaz sahibi](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).
1. Kiracı, yalnızca kiracınıza katılebilecek şekilde cihazı [kilitler](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) .
    1. **Ek bağlantı:** [kiracı kilidi CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. [Buraya](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)genel atanan erişimi kullanarak bilgi noktası yapılandırın.
1. İzleme (isteğe bağlı) yeteneklerini devre dışı bırakmayı öneririz:
    1. Cihazı geliştirici moduna [buraya](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)koyabilme olanağı.
    1. Bir bilgisayara HoloLens 'i bağlamak için bir bilgisayara bağlantı verme özelliği [USB 'yi devre dışı bırakın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > USB 'yi devre dışı bırakmak istemiyor, ancak USB kullanarak cihaza sağlama paketi uygulama olanağı istiyorsanız [**burada**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)listelenen yönergeleri izleyin.

1. HoloLens 2 cihazında uygulamalara izin vermek veya bunları engellemek için [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) kullanın.
1. Kurulumun bir parçası olarak uzak yardım 'ı en son sürüme güncelleştirin. Bunu yapmak için iki seçenek vardır:
    1. Bu işlem, Windows **Microsoft Store--> uzaktan yardım--> ve güncelleştirme uygulaması** aracılığıyla yapılabilir.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -otomatik uygulama güncelleştirmelerine izin veren-varsayılan olarak etkindir. Güncelleştirmeleri almak için cihazı prize takılı tutun.
1. Kullanıcıların istemci sitelerindeki Konuk ağlara bağlanmasına izin vermek için ağ ayarları dışında [Tüm ayarlar sayfalarını devre dışı bırakın](https://docs.microsoft.com/hololens/settings-uri-list) .
1. [HoloLens güncelleştirmelerini yönetme](https://docs.microsoft.com/hololens/hololens-updates)
    1. [İşletim sistemi güncelleştirmelerini denetleme](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) veya ücretsiz olarak akışa izin verme seçeneği.
1. [Ortak cihaz kısıtlamaları](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
