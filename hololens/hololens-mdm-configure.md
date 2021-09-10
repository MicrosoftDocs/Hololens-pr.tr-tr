---
title: Microsoft'un Endpoint Manager Intune'u kullanarak HoloLens yönetme
description: MDM kullanarak Intune kullanarak büyük ölçekte CSP, ilke ve HoloLens ve karma gerçeklik cihazlarını yönetmeyi öğrenin.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427976"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Microsoft'un Endpoint Manager Intune'u kullanarak HoloLens yönetme

MDM aracılığıyla yönetebilirsiniz çok sayıda farklı ayar vardır. Intune cihazları birlikte gruplandırılabilir ve yapılandırmalar bu kullanıcı veya cihaz gruplarına dağıtılabilir. Uygulamalar ayrıca dağıtılabilir ve yönetilebilir, cihazları ağınıza bağlanacak şekilde ayarlamanın yanı sıra güncelleştirmeleri istenen zamanda ve gereken güncelleştirme halkası üzerinde gerçekleşmesi için yapılandırabilir. 

## <a name="how-to-manage-via-intune"></a>Intune aracılığıyla yönetme

### <a name="device-categories-and-groups"></a>Cihaz kategorileri ve gruplar
Intune'ı kullanarak cihaz kategorilerini oluşturabilir ve cihazları, Mühendislik, Tıp, Geliştiriciler gibi kategorilere göre gruplara otomatik olarak eklemek için oluşturabilirsiniz. Burada amaç, Windows Holographic for Business çalıştıran cihazlarınızı yönetmeyi kolaylaştırmaktır.
Daha fazla bilgi: [Cihazları gruplara ayırma](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Cihaz yapılandırma profilleri
Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. Örneğin, Cortana çalıştıran cihazlarınız üzerinde Microsoft Defender Akıllı Ekran'ı kullanan bir profil Windows Holographic for Business.
Profillerinizde bazı ayarları özelleştirmek, cihaz kısıtlamaları oluşturmak ve sanal özel ağ (VPN) ve Wi-Fi yapılandırmak için OMA-URI kullanabilirsiniz.
[Kullanmaya başlayın profilleri ve profiline](/mem/intune/configuration/device-profiles)genel [bakış ile ilgili bilgiler.](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Yönetil neyin yönetil ve yapılandırılana örnekleri

Cihazları yönetmek için MDM kullanmak, seçilecek çok çeşitli öğeler sağlar. 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi ayarları](/mem/intune/configuration/wi-fi-settings-configure), kullanıcılar ve cihazlar için kablosuz ağ ayarları atar. Bir Wi-Fi profili atadığınız zaman, kullanıcılar şirket Wi-Fi kendileri yapılandırmak zorunda kalmadan erişim elde ediyor.
Ağlarınızı ağ [için yapılandırma hakkında daha fazla bilgi HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Sertifikalar
Sertifikalar hesap kimlik doğrulaması, kimlik doğrulaması, VPN Wi-Fi ve web içeriğinin SSL şifrelemesi sağlayarak güvenliğin iyileştirilmesine yardımcı olur. Yöneticiler, sağlama paketleri aracılığıyla cihazlardaki sertifikaları el ile yönetese de, kayıttan yenileme ve iptale kadar tüm yaşam döngüsü boyunca bu sertifikaları yönetmek için MDM sisteminizi kullanmak en iyi uygulamadır. MDM sisteminiz, siz cihazı kaydettikten sonra bu sertifikaları cihazların sertifika depolarına otomatik olarak dağıtabilirsiniz (MDM sistemi Basit Sertifika Kayıt Protokolü (SCEP) veya Ortak Anahtar Şifreleme Standartları'#12 (PKCS #12)) desteklediği sürece). MDM ayrıca kayıtlı istemci sertifikalarını sorgular ve silebilir veya geçerli sertifikanın süresi dolmadan önce yeni bir kayıt isteği tetikler. 

### <a name="proxy"></a>Ara sunucu
Çoğu kurumsal intranet ağı, iç trafiği yönetmek için bir ara sunucudan faydalanmaktadır. 2 HoloLens ethernet ve ağ bağlantıları için bir ara sunucu Wi-Fi yapılandırabilirsiniz. Bu ayarlar VPN bağlantıları için geçerli değildir. Ağ yapılandırmaları için ara sunucu ayarları hakkında daha Windows 10 bkz. [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>VPN
Kuruluşlar genellikle şirket intraneti üzerinde uygulamalara ve kaynaklara erişimi kontrol etmek için VPN kullanır. HoloLens 2, istemciden indirilebilir bir eklenti gerektiren ve tercih Microsoft Store VPN satıcısına özgü SSL VPN bağlantılarını destekler. 
- üzerinde VPN hakkında [daha fazla bilgi HoloLens.](hololens-network.md#vpn)
- VPN profilleri hakkında daha fazla bilgi için bkz. [VPNv2 CSP.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Uygulamaları dağıtma ve yönetme
Intune kullanarak Windows Holographic for Business çalıştıran cihazlarınıza uygulama ekleyebilirsiniz. MDM çözümü, IT kararlarını verenlerin ve yöneticilerin bir grup kullanıcı için mağaza üzerinden kendi kendi iş hattı uygulamalarını özel olarak otomatik olarak yüklemesini (yüklemesini) veya uygulama satın almalarını sağlar. Uygulama dağıtmanın pek çok yolu vardır, örneğin:
-   [Intune ve Şirket Portalı]( app-deploy-intune.md)
-   [İş İçin Microsoft Store]( app-deploy-store-business.md)

Intune aracılığıyla uygulama yönetimi hakkında daha fazla bilgi edinebilirsiniz.
-   [Intune’a uygulama ekleme](/mem/intune/apps/apps-add)
-   [Microsoft Store uygulamaları ekleme](/mem/intune/apps/store-apps-windows)
-   [Oluşturduğunuz uygulamaları ekleme](/mem/intune/apps/lob-apps-windows)
- [Gruplara uygulama ekleme](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Yazılım güncelleştirmeleri
Intune’da Windows 10 cihazlar için güncelleştirme halkaları adı verilen bir özellik vardır. Bu güncelleştirme halkaları, güncelleştirmelerin nasıl yüklendiğini belirleyen bir grup ayar barındırır. Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz. Güncelleştirme halkası, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.
Intune aracılığıyla yazılım [güncelleştirmelerini HoloLens](hololens-updates.md) [ve Yazılım güncelleştirmelerini yönetme hakkında daha fazla bilgi edinin.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Bilgi noktası modunu yapılandırma
Intune’un paylaşılan veya misafir bilgisayar özelliklerini kullanarak Windows Holographic for Business cihazları bilgi noktası olarak çalışacak şekilde yapılandırabilirsiniz. Bu cihazlar, tek uygulama (tekli uygulama bilgi noktası modu) veya birden fazla uygulama (çoklu uygulama bilgi noktası modu) çalıştırabilir. Bilgi noktası modu, hangi kimliklerin varsayılan olarak hangi uygulamalara erişimi olduğunu denetlemeye bir kullanıcı arabirimidir.
Bilgi noktası [olarak HoloLens ayarlamayı öğrenin]( hololens-kiosk.md)

