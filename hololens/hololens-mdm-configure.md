---
title: Microsoft 'un HoloLens cihazlarını yönetmek için ıntune Endpoint Manager kullanma
description: ıntune 'u kullanarak, CSP 'yi kullanarak CSP 'yi, ilkeyi yapılandırmayı ve HoloLens karma gerçeklik cihazlarını yönetmeyi öğrenin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640295"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft 'un HoloLens cihazlarını yönetmek için ıntune Endpoint Manager kullanma

MDM aracılığıyla yönetebileceğiniz çok sayıda farklı ayar vardır. Intune cihazlarının kullanılması birlikte gruplanabilir ve bu kullanıcı veya cihaz gruplarına yapılandırma dağıtılabilir. Uygulamalar da dağıtılabilir ve yönetilebilir, ağınıza bağlanacak cihazları ayarlayabilir ve güncelleştirme halkasının gerekli olduğu sırada gerçekleşecek şekilde yapılandırılabilir. 

## <a name="how-to-manage-via-intune"></a>Intune aracılığıyla yönetme

### <a name="device-categories-and-groups"></a>Cihaz kategorileri ve gruplar
Intune 'u kullanarak, mühendisler, tıp, geliştiriciler vb. gibi, oluşturduğunuz kategorilere göre otomatik olarak gruplara cihaz eklemek için cihaz kategorileri oluşturabilirsiniz. Burada amaç, Windows Holographic for Business çalıştıran cihazlarınızı yönetmeyi kolaylaştırmaktır.
Daha fazla bilgi: [cihazları gruplar halinde kategorilere ayırma](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Cihaz yapılandırma profilleri
Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. örneğin, Windows Holographic for Business çalıştıran cihazlarınızda Cortana veren veya Microsoft Defender akıllı ekranını kullanan bir profil oluşturabilirsiniz.
Profillerinizde bazı ayarları özelleştirmek, cihaz kısıtlamaları oluşturmak ve sanal özel ağ (VPN) ve Wi-Fi yapılandırmak için OMA-URI kullanabilirsiniz.
[Yapılandırma profilleri ile çalışmaya](/mem/intune/configuration/device-profiles)başlayın ve [profile genel bakış](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Nelerin yönetilebilecek ve yapılandırılabileceğini örnekler

Cihazları yönetmek için MDM kullanılması, seçilebileceği geniş bir öğe dizisi sağlar. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi ayarları](/mem/intune/configuration/wi-fi-settings-configure), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınızda, kullanıcılar, kendi kendini yapılandırmak zorunda kalmadan kurumsal Wi-Fi erişim sahibi olur.
[Ağınızı HoloLens için yapılandırma](hololens-commercial-infrastructure.md) hakkında daha fazla bilgi edinin

### <a name="certificates"></a>Sertifikalar
Sertifikalar, Web içeriğinin hesap kimlik doğrulaması, Wi-Fi kimlik doğrulaması, VPN şifrelemesi ve SSL şifrelemesi sağlayarak güvenliği artırmaya yardımcı olur. Yöneticiler, cihazlarda cihazları sağlama paketleri aracılığıyla el ile yönetebilse de, bu sertifikaları tüm yaşam döngülerinde (yenileme ve iptal etme yoluyla) yönetmek için MDM sisteminizi kullanmak en iyi uygulamadır. MDM sisteminiz, cihaz kaydolduktan sonra bu sertifikaları cihazların sertifika depolarına otomatik olarak dağıtabilir (MDM sistemi Basit Sertifika Kayıt Protokolü (SCEP) veya ortak anahtar şifreleme standartlarını #12 (PKCS # 12)). MDM, kayıtlı istemci sertifikalarını sorgulayabilir ve silebilir ya da geçerli sertifikanın süre dolmadan önce yeni bir kayıt isteği tetikleyebilirsiniz. 

### <a name="proxy"></a>Ara sunucu
Çoğu kurumsal intranet ağlarının iç trafiği yönetmek için bir proxy 'den faydalanır. HoloLens 2 ile, ethernet ve Wi-Fi bağlantıları için bir proxy sunucu yapılandırabilirsiniz. Bu ayarlar VPN bağlantıları için geçerlidir. Windows 10 ara sunucu ayarları hakkında daha fazla bilgi için bkz. [networkproxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Kuruluşlar, şirket intranetindeki uygulamalara ve kaynaklara erişimi denetlemek için genellikle bir VPN kullanır. HoloLens 2, Microsoft Store indirilebilir bir eklenti gerektiren ve tercih ettiğiniz VPN satıcısına özgü olan SSL VPN bağlantılarını destekler. 
- [HoloLens üzerindeki VPN](hololens-network.md#vpn)hakkında daha fazla bilgi edinin.
- VPN profilleri hakkında daha fazla bilgi için bkz. [VPNV2 CSP](/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Uygulamaları dağıtma ve yönetme
Intune kullanarak Windows Holographic for Business çalıştıran cihazlarınıza uygulama ekleyebilirsiniz. Bir MDM çözümü, BT karar mekanizmalarının ve yöneticilerin şirket içi, iş kolu uygulamalarını veya mağaza aracılığıyla uygulama satın almasını (bir Kullanıcı grubu için) sağlar. Uygulama dağıtmanın pek çok yolu vardır, örneğin:
-   [ıntune ve Şirket Portalı]( app-deploy-intune.md)
-   [İş İçin Microsoft Store]( app-deploy-store-business.md)

Intune ile uygulama yönetimi hakkında daha fazla bilgi edinin.
-   [Intune’a uygulama ekleme](/mem/intune/apps/apps-add)
-   [Microsoft Store uygulamaları ekleme](/mem/intune/apps/store-apps-windows)
-   [Oluşturduğunuz uygulamaları ekleme](/mem/intune/apps/lob-apps-windows)
- [Gruplara uygulama ekleme](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Yazılım güncelleştirmeleri
Intune’da Windows 10 cihazlar için güncelleştirme halkaları adı verilen bir özellik vardır. Bu güncelleştirme halkaları, güncelleştirmelerin nasıl yüklendiğini belirleyen bir grup ayar barındırır. Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz. Güncelleştirme halkası, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.
[HoloLens güncelleştirmelerini yönetme](hololens-updates.md) ve [yazılım güncelleştirmelerini ıntune aracılığıyla yönetme](/mem/intune/protect/windows-update-for-business-configure)hakkında daha fazla bilgi edinin.

### <a name="configure-kiosk-mode"></a>Bilgi noktası modunu yapılandırma
Intune’un paylaşılan veya misafir bilgisayar özelliklerini kullanarak Windows Holographic for Business cihazları bilgi noktası olarak çalışacak şekilde yapılandırabilirsiniz. Bu cihazlar, tek uygulama (tekli uygulama bilgi noktası modu) veya birden fazla uygulama (çoklu uygulama bilgi noktası modu) çalıştırabilir. Bilgi noktası modu, hangi kimliklerin varsayılan olarak hangi uygulamalara erişebileceğini denetleyen bir kullanıcı arabirimi.
[bilgi noktası olarak HoloLens ayarlamayı]( hololens-kiosk.md) öğrenin

