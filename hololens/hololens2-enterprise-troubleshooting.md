---
title: HoloLens 2 uygulama ve yönetilen cihaz sorunlarını giderme
description: Enterprise ortamında 2 cihazda HoloLens sorunlarını giderme
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: sorun giderme
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636886"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Uygulama ve yönetilen cihazlar sorunlarını giderme 

bu makalede, HoloLens 2 ' nin uygulanması ve yönetimiyle ilgili birçok sorunu nasıl giderebileceğinizi veya soruların nasıl yanıtlanabileceği açıklanır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun. Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.


<a id="list"></a>
- [EAP sorunlarını giderme](#eap-troubleshooting)
- [Wi-Fi sorunlarını giderme](#wi-fi-troubleshooting)
- [Ağ sorunlarını giderme](#network-troubleshooting)
- [daha önce bir kurulum HoloLens cihazda oturum açılamıyor](#cant-sign-in-to-a-previously-setup-hololens-device)
- [güncelleştirme sonrasında oturum açılamıyor Windows Holographic 21h1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot sorunlarını giderme](#autopilot-troubleshooting)
- [yönetilen HoloLens cihazları sss](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP sorunlarını giderme
1. Çift denetim Wi-Fi profilinde doğru ayarlar var:
    - EAP türü doğru yapılandırılmış, ortak EAP türleri: EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).
    - Wi-Fi SSID adı doğru ve ONALTıLıK dizeyle eşleşiyor.
    - EAP-TLS için TrustedRootCA sunucunun Güvenilen kök CA sertifikasının SHA-1 karmasını içerir. Windows PC "certutil.exe-döküm cert_file_name" komutu, bir sertifikanın SHA-1 karma dizesini gösterir.
2. EAP oturumunun nerede başarısız olduğunu öğrenmek için erişim noktası veya denetleyici ya da AAA sunucusu günlüklerinde ağ paketi yakalamayı toplayın.
    - HoloLens tarafından sağlanan EAP kimliği beklenmiyorsa, kimliğin Wi-Fi profil veya istemci sertifikası aracılığıyla doğru şekilde sağlanıp sağlanmadığını denetleyin.
    - sunucu HoloLens istemci sertifikasını reddederse, cihazda gerekli istemci sertifikasının sağlanıp sağlanmadığını denetleyin.
    - HoloLens sunucu sertifikasını reddederse, sunucu kök CA sertifikasının HoloLens sağlanıp sağlanmadığını denetleyin.
3. kurumsal profile Wi-Fi sağlama paketiyle sağlanmışsa, sağlama paketini bir Windows 10 bilgisayara uygulamayı düşünün. Windows 10 PC 'de de başarısız olursa, Windows client 802.1 x authentication sorun giderme kılavuzunu izleyin.
4. Geri Bildirim Hub 'ı aracılığıyla bize geri bildirim gönderin.

[Listeye geri dön](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi sorunlarını giderme

HoloLens Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:

1. Wi-Fi açık olduğundan emin olun. bunu denetlemek için başlangıç hareketini kullanın, Ayarlar > ağ & ınternet > Wi-Fi ' ı seçin. Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.
2. Yönlendiriciye veya erişim noktasına yaklaşın.
3. Wi-Fi yönlendiricinizi yeniden başlatın ve HoloLens yeniden başlatın. Yeniden bağlanmayı deneyin.
4. Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

Cihazdaki bir kuruluşta veya kurumsal hesapta oturum açtığınızda, ilke BT yöneticiniz tarafından yapılandırılmışsa mobil cihaz yönetimi (MDM) ilkesi de uygulayabilir.

[Listeye geri dön](#list)

## <a name="network-troubleshooting"></a>Ağ sorunlarını giderme
ağ sorunları, kuruluşunuzda HoloLens 2 ' yi başarıyla dağıtmaya ve kullanmaya yönelik bir obstayor ise, fiddler ve/veya Wireshark 'yi, HTTP/HTTPS trafiğini yakalamak ve analiz etmek için yapılandırın. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>HTTP trafiğini yakalamak için Fiddler 'ı yapılandırma
Fiddler, Web hata ayıklama proxy 'si ve HTTP (S) sorunlarını gidermek için kullanılır. Bilgisayarın yaptığı tüm HTTP isteklerini yakalar ve onunla ilişkili her şeyi kaydeder. HTTPS uygulamalarınız için son kullanıcı kimlik doğrulama sorunlarını kapsaunın, hedef HoloLens 2 kullanım örnekleri için daha fazla üretkenlik ve verimlilik sağlayın. 

#### <a name="prerequisites"></a>Önkoşullar
 
- HoloLens 2 cihaz ve bilgisayarınızın aynı ağda olması gerekir
- BILGISAYARıNıZıN IP adresini aklınızda

#### <a name="install-and-configure-fiddler"></a>Fiddler 'i yükleyip yapılandırma

1. Bilgisayarınızda, Fiddler 'ı [yükleyip](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) başlatın.  
1. Bilgisayarınızda, uzak bilgisayarların bağlanmasına izin vermek için Fiddler 'ı yapılandırın.
    1. fiddler Ayarlar-> bağlantılarına git
    1. Fiddler için dinleme bağlantı noktasını aklınızda (varsayılan 8866)
    1. Uzak bilgisayarların bağlanmasına Izin ver ' i işaretleyin
    1. Kaydet’e tıklayın.
3. HoloLens 2 – ara sunucu olarak fiddler 'ı yapılandırın<sup>1</sup>:
    1. Başlat menüsü açın ve Ayarlar seçin
    1. Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin
    1. Aşağı doğru ara sunucu kurulumuna gidin ve üzerinde bir proxy sunucusu kullan ' a geçiş yapın
    1. Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin
    1. Yukarıda belirtilen bağlantı noktası numarasını girin (varsayılan değer 8866 ' dir)
    1. Kaydet’e tıklayın.

<sup>1</sup> derlemeler 20279.1006 + (Insiders ve yaklaşan sürüm) için, proxy 'yi yapılandırmak için aşağıdaki adımları kullanın:
1. Başlat menüsü açın ve Wi-Fi ağınızın özellikler sayfasına gidin 
1. Aşağı kaydırarak ara sunucu
1. El Ile kuruluma geçiş yapın
1. Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin
1. Yukarıda belirtilen bağlantı noktası numarasını girin. (varsayılan değer 8866 ' dir)
1. Uygula ' ya tıklayın
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>HoloLens 2 ' den HTTPS trafiğinin şifresini çözün

1. Bilgisayarınızda – Fiddler sertifikasını dışarı aktarın.
    1. fıddler Ayarlar-> HTTPS 'ye gidin ve gelişmiş Ayarlar genişletin
    2. Fiddler sertifikasını dışarı aktar ' a tıklayın. Masaüstünüze kaydedilecek
    3. sertifikayı HoloLens 2 ' deki indirilenler klasörüne taşıyın

2.  HoloLens 2-fiddler sertifikasını içeri aktarın.
    1. Ayarlar > güncelleştirme ve güvenlik-> sertifikalarına gidin
    2. Sertifika yüklensin ' e tıklayın, Indirmeler klasörüne gidin ve Fiddler sertifikasını seçin
    3. Depo konumunu yerel makineye Değiştir
    4. Sertifika deposunu köke Dönüştür
    5. Yüklemeyi seçin
    6. Sertifikanın sertifika listesinde görüntülendiğini doğrulayın. Aksi takdirde, yukarıdaki adımları tekrarlayın

#### <a name="inspect-https-sessions"></a>HTTP (S) oturumlarını İncele

bilgisayarınızda, fiddler 'ın HoloLens 2 ' nin canlı HTTP oturumlarını göstermesi gerekir. Fiddler 'daki Inspectors paneli, HTTP (S) istek/yanıtını farklı görünümlerde gösterebilir. Örneğin, "RAW" görünümü ham isteği veya yanıtı düz metin olarak gösterir. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Ağ trafiğini yakalamak için Wireshark 'ı yapılandırma
Wireshark bir ağ protokol çözümleyicisidir ve TCP/UDP trafiğini HoloLens 2 cihazınızdan denetlemek için kullanılır. bu, ağınızı HoloLens 2 ' ye hangi trafiğin, ne kadarının, ne kadar sıklıkla olduğunu, belirli atlamaları arasında ne kadar gecikme olduğunu ve bu şekilde olduğunu belirlemeyi kolaylaştırır.

#### <a name="prerequisites"></a>Ön koşullar:
- BILGISAYAR Internet erişimine sahip olmalı ve Wi-Fi üzerinde Internet paylaşımını desteklemelidir

#### <a name="install-and-configure-wireshark"></a>Wireshark 'yi yükleyip yapılandırın
1. Bilgisayarınızda [Wireshark](https://www.wireshark.org/#download) 'i yükledikten sonra 
1. Bilgisayarınızda, Wi-Fi ' r e Internet bağlantınızı paylaşmak için mobil etkin noktayı etkinleştirin.
1. Bilgisayarınızı başlatın Wireshark ve mobil etkin nokta arabiriminden trafiği yakalayın. 
1. HoloLens 2: Wi-Fi ağını bilgisayarın mobil etkin olmadan değiştirin. HoloLens 2 ıp trafiği Wireshark ' de görünür.

#### <a name="analyze-wireshark-logs"></a>Wireshark günlüklerini çözümleme
Wireshark filtreleri, ilgilendiğiniz paketlerin filtrelemesine yardımcı olabilir. 

Özgün [bloga](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)göz atın.

[Listeye geri dön](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>daha önce bir kurulum HoloLens cihazda oturum açılamıyor

Cihazınız daha önce bir istemcisi ya da bir önceki çalışan için daha önce ayarlandıysa ve cihazın kilidini açmak için bir parola yoksa, [cihazı uzaktan silmek](/intune/remote-actions/devices-wipe) için Intune 'u kullanabilirsiniz. Cihaz daha sonra kendisini yeniden yanıp sönmelidir.  
> [!IMPORTANT]
> Cihazı sildiğinizde, **kayıt durumunu ve Kullanıcı hesabını** işaretlenmemiş olarak bırakın ' ın işaretini kaldırın.

[Listeye geri dön](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>güncelleştirme sonrasında oturum açılamıyor Windows Holographic 21h1

### <a name="symptoms"></a>Belirtiler
- Doğru PIN girildikten sonra, oturum açma için PIN kullanılması başarısız olur.
- Web sayfasında başarıyla oturum açıldıktan sonra Web oturum açma yönteminin kullanılması başarısız olur.
- cihaz, [Azure portal](https://portal.azure.com/) > Azure Active Directory-> cihazlarda "Azure AD 'ye katılmış" olarak listelenmez.

### <a name="cause"></a>Nedeni
Etkilenen cihaz Azure AD kiracısından silinmiş olabilir. Örneğin, bu durum oluşabilir:

- Yönetici veya Kullanıcı Azure portal cihazı veya PowerShell 'i kullanarak sildi.
- Cihaz, etkinlik dışı nedenlerle Azure AD kiracısından kaldırıldı. Etkin bir şekilde yönetilen bir ortamda, genellikle BT yöneticilerinin [Azure AD kiracısından eski, etkin olmayan cihazları kaldırmasını](/azure/active-directory/devices/manage-stale-devices)öneririz.

Etkilenen bir cihaz silindikten sonra yeniden iletişim kurmayı denediğinde Azure AD ile kimlik doğrulaması başarısız olur. Bu efekt, PIN aracılığıyla önbelleğe alınan oturum açmanın kullanıcının oturum açmasına izin vermeyi sürdüreceği için genellikle cihazın kullanıcısı tarafından görünmez.

### <a name="mitigation"></a>Risk azaltma
şu anda, silinen HoloLens cihazı Azure AD 'ye geri eklemenin bir yolu yoktur. Etkilenen cihazların, [cihazlarıyla](hololens-recovery.md#clean-reflash-the-device)ilgili yönergeleri izleyerek Temizleme sırasında Temizleme olması gerekir.

[Listeye geri dön](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot sorunlarını giderme

aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot sorunlarını gidermek için yararlı bir kaynak olabilir, ancak bu makalelerin Windows 10 masaüstüne bağlı olduğunu ve tüm bilgilerin HoloLens için uygulanabilir olabileceğini lütfen unutmayın:

- [Windows Autopilot-bilinen sorunlar](/mem/autopilot/known-issues)
- [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot-Ilke çakışmaları](/mem/autopilot/policy-conflicts)

[Listeye geri dön](#list)

## <a name="managed-hololens-devices-faqs"></a>yönetilen HoloLens cihazları sss

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>HoloLens cihazlarını yönetmek için System Center Configuration Manager (SCCM) kullanabilir miyim?

Hayır. HoloLens cihazlarını yönetmek için bir MDM sistemi kullanmanız gerekir.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>HoloLens kullanıcı hesaplarını yönetmek için Active Directory Domain Services (AD DS) kullanabilir miyim?

Hayır. HoloLens cihazların kullanıcı hesaplarını yönetmek için Azure Active Directory (Azure AD) kullanmanız gerekir.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>otomatik veri yakalama sistemleri (ADCS) otomatik kayıt özellikli HoloLens.

Hayır.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>tümleşik Windows kimlik doğrulamasına HoloLens eklenebilir mi?

Hayır.

### <a name="does-hololens-support-branding"></a>HoloLens markalamayı destekliyor mu?

Hayır. Ancak, aşağıdaki yaklaşımlardan birini kullanarak bu sorunu geçici olarak çözebilirsiniz:

- Özel bir uygulama oluşturun ve [bilgi noktası modunu etkinleştirin](hololens-kiosk.md). Özel uygulama marka içerebilir ve diğer uygulamaları başlatabilir (uzaktan yardım gibi).  
- Azure AD 'deki tüm Kullanıcı profili resimlerini şirket logonuz olacak şekilde değiştirin. Ancak, bu, tüm senaryolar için istenmeyebilir.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>2 teklif HoloLens günlük oluşturma özellikleri nelerdir?

Günlüğe kaydetme, geliştirme veya sorun giderme senaryolarında yakalanamayan izlemelerle veya cihazların Microsoft sunucularına gönderdikleri telemetri ile sınırlıdır.

## <a name="questions-about-securing-hololens-devices"></a>HoloLens cihazların güvenliğini sağlama hakkında sorular

[HoloLens 2 güvenlik bilgilerini](security-overview.md)inceleyin.
1. Gen cihaz HoloLens için lütfen [bu sss](hololens1-faq-security.yml)'yi gözden geçirin.

[Listeye geri dön](#list)
