---
title: HoloLens 2 uygulama ve yönetilen cihaz sorunlarını giderme
description: Enterprise ortamında 2 cihazda HoloLens sorunlarını giderme
author: beelia
ms.author: v-beehanson
ms.date: 6/22/2021
ms.topic: article
keywords: sorun giderme
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 2e997514be5d067ce5e9bd7f3611b464d19a6fad
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364601"
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
1. Wi-Fi profilinin doğru ayarlara sahip olduğunu doğrulayın:
    - EAP türünü doğru şekilde yapılandırın. Genel EAP türleri EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).
    - Wi-Fi SSID adını denetleyin ve ONALTıLıK dizeyle eşleşip eşleşmediğini görüntüleyin.
    - EAP-TLS, TrustedRootCA için sunucunun Güvenilen kök CA sertifikasının SHA-1 karmasını içerdiğinden emin olun. Windows PC 'de "certutil.exe-dump cert_file_name" komutu bir sertifikanın SHA-1 karma dizesini gösterir.
2. EAP oturumunun nerede başarısız olduğunu öğrenmek için erişim noktası veya denetleyici ya da AAA sunucusu günlüklerinde ağ paketi yakalamayı toplayın.
    - HoloLens tarafından sağlanan EAP kimliği beklenmiyorsa, kimliğin Wi-Fi profil veya istemci sertifikası aracılığıyla doğru şekilde sağlanıp sağlanmadığını denetleyin.
    - sunucu HoloLens istemci sertifikasını reddederse, cihazda gerekli istemci sertifikasının sağlanıp sağlanmadığını denetleyin.
    - sunucu sertifikasını reddederse HoloLens, HoloLens üzerinde sunucu kök CA sertifikasının sağlanıp sağlanmadığını denetleyin.
3. kurumsal profile Wi-Fi sağlama paketiyle sağlanmışsa, sağlama paketini bir Windows 10 bilgisayara uygulamayı düşünün. Windows 10 PC 'de de başarısız olursa, Windows client 802.1 x authentication sorun giderme kılavuzunu izleyin.
4. Geri Bildirim Hub 'ı aracılığıyla bize geri bildirim gönderin.

[Listeye geri dön](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi sorunlarını giderme

HoloLens Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:

1. Wi-Fi’ın açık olduğundan emin olun. başlangıç hareketini kullanarak doğrulayın ve Ayarlar > ağ & ınternet > Wi-Fi ' ı seçin. Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.
2. Yönlendiriciye veya erişim noktasına yaklaşın.
3. Wi-Fi yönlendiricisini yeniden başlatın ve HoloLens yeniden başlatın. Bağlanmayı yeniden deneyin.
4. Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını doğrulayın. Bu bilgileri üreticinin Web sitesinde bulabilirsiniz.

Cihazdaki bir kuruluşta veya kurumsal hesapta oturum açtığınızda, ilke BT yöneticiniz tarafından yapılandırılmışsa mobil cihaz yönetimi (MDM) ilkesi de uygulanabilir.

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
    1. fiddler Ayarlar-> bağlantılarına gidin.
    1. Fiddler için dinleme bağlantı noktasını aklınızda (varsayılan 8866).
    1. Uzak bilgisayarların bağlanmasına Izin ver ' i işaretleyin.
    1. Kaydet’e tıklayın.
3. HoloLens 2 – ara sunucu olarak fiddler 'ı yapılandırın<sup>1</sup>:
    1. Başlat menüsü açın ve Ayarlar ' i seçin.
    1. Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.
    1. , El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.
    1. Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin.
    1. Yukarıda belirtilen bağlantı noktası numarasını girin (varsayılan değer 8866 ' dir).
    1. Kaydet’e tıklayın.

<sup>1</sup> derlemeler 20279.1006 + (Insiders ve yaklaşan sürüm) için, proxy 'yi yapılandırmak için aşağıdaki adımları kullanın:
1. Başlat menüsü açın ve Wi-Fi ağınızın özellikler sayfasına gidin. 
1. Aşağı kaydırarak ara sunucu.
1. El Ile kurulum 'a geçin.
1. Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin.
1. Yukarıda belirtilen bağlantı noktası numarasını girin (varsayılan değer 8866 ' dir).
1. Uygula ' ya tıklayın.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>HoloLens 2 ' den HTTPS trafiğinin şifresini çözün

1. Bilgisayarınızda – Fiddler sertifikasını dışarı aktarın.
    1. fıddler Ayarlar-HTTPS > ve gelişmiş Ayarlar ' i genişletin.
    2. Fiddler sertifikasını dışarı aktar ' a tıklayın. Bu, masaüstünüze kaydedilir.
    3. sertifikayı HoloLens 2 ' deki indirilenler klasörüne taşıyın.

2.  HoloLens 2-fiddler sertifikasını içeri aktarın.
    1. Ayarlar > güncelleştirme ve güvenlik-> sertifikalarına gidin.
    2. Sertifika yüklensin ' e tıklayın, Indirmeler klasörüne gidin ve Fiddler sertifikasını seçin.
    3. Depo konumunu yerel makineye değiştirin.
    4. Sertifika deposunu köke değiştirin.
    5. Yükle'yi seçin.
    6. Sertifikanın sertifika listesinde görüntülendiğini doğrulayın. Aksi takdirde, bu adımları yineleyin.

#### <a name="inspect-https-sessions"></a>HTTP (S) oturumlarını İncele

bilgisayarınızda, fiddler 'ın HoloLens 2 ' nin canlı HTTP oturumlarını göstermesi gerekir. Fiddler 'daki Inspectors paneli, HTTP (S) isteği/yanıtını farklı görünümlerde gösterebilir. Örneğin, "RAW" görünümü ham isteği veya yanıtı düz metin olarak gösterir. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Ağ trafiğini yakalamak için Wireshark 'ı yapılandırma
Wireshark, HoloLens 2 cihazınızdan gelen ve giden TCP/UDP trafiğini denetlemek için kullanılan bir ağ protokol çözümleyicisidir. bu, ağı HoloLens 2 ' ye geçen trafiği (ne kadar fazla olması gerektiğini, sıklığını, belirli atlamaları arasında ne kadar gecikme süresini vb.) belirlemeyi kolaylaştırır.

#### <a name="prerequisites"></a>Ön koşullar:
- BILGISAYAR internet erişimine sahip olmalıdır ve Wi-Fi üzerinden Internet paylaşımını desteklemelidir.

#### <a name="install-and-configure-wireshark"></a>Wireshark 'yi yükleyip yapılandırın
1. Bilgisayarınızda [Wireshark](https://www.wireshark.org/#download)' i yüklemelisiniz.
1. Bilgisayarınızda, Wi-Fi ' r e Internet bağlantınızı paylaşmak için mobil etkin noktayı etkinleştirin.
1. Bilgisayarınızı başlatın Wireshark ve mobil etkin nokta arabiriminden trafiği yakalayın. 
1. HoloLens 2: Wi-Fi ağını bilgisayarın mobil etkin olmadan değiştirin. HoloLens 2 ıp trafiği Wireshark ' de görünür.

#### <a name="analyze-wireshark-logs"></a>Wireshark günlüklerini analiz etme
Wireshark filtreleri, ilgi alanı paketlerini filtrelemeye yardımcı olabilir. 

Özgün [bloguna göz atabilirsiniz.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)

[Listeye dön](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Daha önce bir cihaz kurulumunda oturum HoloLens yok

Cihazınız daha önce bir istemci için veya eski bir çalışan için başka biri için ayarlanmışsa ve cihazın kilidini açmak için parolanız yoksa, cihazı uzaktan silmek için Intune'un [kullanabilirsiniz.](/intune/remote-actions/devices-wipe) Ardından cihaz kendisini yeniden yanıp söner.  
> [!IMPORTANT]
> Cihazı silerken Kayıt durumunu ve kullanıcı hesabını **koruma işaretsiz bırakın.**

[Listeye dön](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Windows Holographic 21H1'e güncelleştirdikten sonra oturum açılam

### <a name="symptoms"></a>Belirtiler
- Doğru PIN girdikten sonra oturum açma için PIN kullanma başarısız olur.
- Web sayfasında başarıyla oturum açma işlemi sonrasında web oturum açma yönteminin kullanımı başarısız olur.
- Cihaz , [-> Azure Active Directory](https://portal.azure.com/) -> Devices Azure portal "Azure AD'ye katılmış" olarak listelenmiyor.

### <a name="cause"></a>Nedeni
Etkilene cihaz Azure AD kiracıdan silinmiş olabilir. Örneğin, bunun nedeni:

- Yönetici veya kullanıcı, cihazı cihazdan Azure portal PowerShell'i kullanarak sildi.
- Cihaz, işlem dışı olduğu için Azure AD kiracıdan kaldırıldı. Verimli bir şekilde yönetilen bir ortam için, GENELLIKLE, IT yöneticilerinin eski, etkin olmayan cihazları [Azure AD kiracılarından kaldırmasını öneririz.](/azure/active-directory/devices/manage-stale-devices)

Bu sorundan etkiilen bir cihaz silindikten sonra Azure AD kiracısı ile yeniden iletişim kurma girişiminde bulunsa, Azure AD ile kimlik doğrulaması başarısız olur. PIN aracılığıyla önbelleğe alınmış oturum açma işlemi kullanıcının oturum açmasına izin vermeye devam ettiği için bu etki genellikle cihaz kullanıcısı tarafından görünmez.

### <a name="mitigation"></a>Risk azaltma
Şu anda silinen bir cihazı Azure AD'HoloLens eklemenin hiçbir yolu yoktur. Etkilenen cihazların cihazına ters eğik çizgiyle başvurulma yönergelerini izleyerek [temiz bir şekilde yeniden bayrakları gerekir.](hololens-recovery.md#clean-reflash-the-device)

[Listeye dön](#list)

## <a name="autopilot-troubleshooting"></a>Autopilot Sorunlarını Giderme

Aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot Sorunlarını gidermek için yararlı bir kaynak olabilir. Ancak, makaleler Windows 10 Desktop'a dayalıdır ve aşağıdakiler için tüm bilgiler HoloLens:

- [Windows Autopilot - bilinen sorunlar](/mem/autopilot/known-issues)
- [Windows cihaz kaydı sorunlarını Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - İlke Çakışmaları](/mem/autopilot/policy-conflicts)

[Listeye dön](#list)

## <a name="managed-hololens-devices-faqs"></a>Yönetilen HoloLens Cihazları hakkında SSS

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Cihazlarınızı yönetmek System Center Configuration Manager (SCCM) HoloLens miyim?

Hayır. Cihazları yönetmek için bir MDM sistemi HoloLens gerekir.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Kullanıcı hesaplarını yönetmek Active Directory Domain Services (AD DS) HoloLens kullanabilir miyim?

Hayır. Azure Active Directory cihazlarının kullanıcı hesaplarını yönetmek için HoloLens (Azure AD) HoloLens gerekir.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Otomatik HoloLens Yakalama Sistemleri (ADCS) otomatik kayıt özelliğine sahip mi?

Hayır.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Tümleşik HoloLens Kimlik Doğrulaması'na Windows olabilir mi?

Hayır.

### <a name="does-hololens-support-branding"></a>Markalama HoloLens desteklesin mi?

Hayır. Ancak aşağıdaki yaklaşımlardan birini kullanarak bu soruna yönelik bir çalışma yapabilirsiniz:

- Özel bir uygulama oluşturun ve bilgi [noktası modunu etkinleştirin.](hololens-kiosk.md) Özel uygulama markaya sahip olabilir ve diğer uygulamaları (Remote Assist gibi) başlatabilirsiniz.  
- Azure AD'de tüm kullanıcı profili resimlerini şirket logonuzu olarak değiştirme. Ancak, tüm senaryolar için bu tercih edilmeyebilir.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>2. günlük HoloLens özellikleri nedir?

Günlüğe kaydetme, geliştirme veya sorun giderme senaryolarında yakalanacak izlemeler veya cihazların Microsoft sunucularına göndermekte olduğu telemetri verileriyle sınırlıdır.

## <a name="questions-about-securing-hololens-devices"></a>Cihaz güvenliğini sağlama HoloLens soruları

[2. HoloLens bilgilerimize bakın.](security-overview.md)
1. HoloLens cihazları için lütfen bu SSS [bölümünü gözden geçirin.](hololens1-faq-security.yml)

[Listeye dön](#list)
