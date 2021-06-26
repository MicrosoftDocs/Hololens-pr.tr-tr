---
title: HoloLens 2 uygulaması ve yönetilen cihaz sorunlarını giderme
description: Enterprise ortamında HoloLens 2 cihazlarının sorunlarını giderme
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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961647"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Uygulama ve yönetilen cihaz sorunlarını giderme 

Bu makalede HoloLens 2'nin uygulanması ve yönetimiyle ilgili çeşitli sorunların nasıl çözülecek veya soruların nasıl yanıtlandır soruları açıklanmıştır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun. Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.


<a id="list"></a>
- [EAP Sorunlarını Giderme](#eap-troubleshooting)
- [Wi-Fi Sorunlarını Giderme](#wi-fi-troubleshooting)
- [Ağ Sorunlarını Giderme](#network-troubleshooting)
- [Daha önce kurulumu yapılan HoloLens cihazında oturum açma işlemi tamamlanmıyor](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Windows Holographic 21H1'e güncelleştirdikten sonra oturum açılam](#cant-login-after-updating-to-windows-holographic-21h1)
- [Autopilot Sorunlarını Giderme](#autopilot-troubleshooting)
- [Yönetilen HoloLens Cihazları hakkında SSS](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>EAP Sorunlarını Giderme
1. Profilde doğru Wi-Fi bir kez daha kontrol edin:
    - EAP türü doğru yapılandırıldı, yaygın EAP türleri: EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).
    - Wi-Fi SSID adı doğru ve HEX dizesiyle eşler.
    - EAP-TLS için TrustedRootCA, sunucunun güvenilen kök CA sertifikasının SHA-1 karması içerir. Windows bilgisayar "certutil.exe -dump cert_file_name" komutu bir sertifikanın SHA-1 karma dizesini gösterir.
2. EAP oturumunun nerede başarısız olduğunu bulmak için Erişim Noktası, Denetleyici veya AAA sunucu günlüklerinde ağ paketi yakalamayı toplayın.
    - HoloLens tarafından sağlanan EAP kimliği beklenlenmiyorsa, kimliğin bir profil veya istemci sertifikası aracılığıyla Wi-Fi sağ olup olmadığını denetleyin.
    - Sunucu HoloLens istemci sertifikasını reddederse, gerekli istemci sertifikasının cihazda sağlandı olup olmadığını kontrol edin.
    - HoloLens sunucu sertifikasını reddederse, sunucu kök CA sertifikasının HoloLens'de sağlandı olup olduğunu kontrol edin.
3. Kurumsal profil bir sağlama paketi Wi-Fi sağlanıyorsa, sağlama paketini Windows 10 bilgisayarınızda uygulamayı göz önünde bulundurabilirsiniz. Bilgisayarınızda da başarısız Windows 10 Windows istemcisi 802.1X kimlik doğrulaması sorun giderme kılavuzunu izleyin.
4. Bize geri bildirim göndererek Geri Bildirim Merkezi.

[Listeye dön](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi Giderme

HoloLens'inizi bir sanal ağ bağlantısı kuramıyorsanız deneyecek Wi-Fi:

1. Bu Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketini kullanın ve ardından Wi-Fi ile > Ağ & İnternet >'ı seçin. Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
2. Yönlendiriciye veya erişim noktasına yaklaşın.
3. Sanal yönlendiricinizi Wi-Fi ve ardından HoloLens'i yeniden başlatın. Yeniden bağlanmayı deneyin.
4. Bunlardan hiçbiri çalışmıyorsa, yönlendiricinizin en son üretici yazılımını kullanmaya devam edin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

Cihazda bir kuruluş veya kuruluş hesabında oturum asanız, ilkeNIN IT yöneticiniz tarafından yapılandırılması Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) ilkesi de uygulanabilir.

## <a name="network-troubleshooting"></a>Ağ Sorunlarını Giderme
Ağ sorunları, HoloLens 2'yi başarıyla dağıtmanızı ve bunu kullanmayı engellerse, fiddler ve Wireshark gibi bilinen iki ağ tanılama aracının sorunları taramanıza, tanılamanıza ve tanımlamanıza nasıl yardımcı olduğunu öğrenin. Diğer ayrıntılar için [bu bloga](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) göz atabilirsiniz.

[Listeye dön](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Daha önce kurulumu yapılan HoloLens cihazında oturum açma işlemi tamamlanmıyor

Cihazınız daha önce bir istemci için veya eski bir çalışan için başka biri için ayarlanmışsa ve cihazın kilidini açmak için parolanız yoksa, cihazı uzaktan silmek için Intune kullanabilirsiniz. [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) Ardından cihaz kendisini yeniden yanıp söner.  
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
- Cihaz, işlem dışı olduğu için Azure AD kiracıdan kaldırıldı. Verimli bir şekilde yönetilen bir ortam için, GENELLIKLE, IT yöneticilerinin eski, etkin olmayan cihazları [Azure AD kiracılarından kaldırmasını öneririz.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

Etkilene bir cihaz silindikten sonra Azure AD kiracısına yeniden iletişim kurma girişiminde bulunsa, Azure AD ile kimlik doğrulaması başarısız olur. PIN aracılığıyla önbelleğe alınan oturum açma işlemi kullanıcının oturum açmasına izin vermeye devam ettiği için bu etki genellikle cihaz kullanıcısı tarafından görünmez.

### <a name="mitigation"></a>Risk azaltma
Şu anda silinmiş bir HoloLens cihazı Azure AD'ye geri eklemenin hiçbir yolu yoktur. Etkilenen cihazların cihazına ters eğik çizgiyle başvurulma yönergelerini izleyerek [temiz bir şekilde yeniden bayrakları gerekir.](hololens-recovery.md#clean-reflash-the-device)

## <a name="autopilot-troubleshooting"></a>Autopilot Sorunlarını Giderme

Aşağıdaki makaleler daha fazla bilgi edinmek ve Autopilot Sorunlarını gidermek için kullanışlı bir kaynak olabilir, ancak bu makalelerin Windows 10 Desktop'a dayandırılana kadar tüm bilgilerin HoloLens için geçerli olmadığını unutmayın:

- [Windows Autopilot - bilinen sorunlar](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Microsoft Intune'de Windows cihaz kaydı sorunlarını giderme](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - İlke Çakışmaları](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Yönetilen HoloLens Cihazları hakkında SSS

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>HoloLens System Center Yapılandırma Yöneticisi yönetmek için System Center Yapılandırma Yöneticisi (SCCM) kullanabilir miyim?

Hayır. HoloLens cihazlarını yönetmek için bir MDM sistemi kullanmak zorundasiniz.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>HoloLens kullanıcı Active Directory Domain Services (AD DS) kullanabilir miyim?

Hayır. HoloLens cihazlarına Azure Active Directory hesaplarını yönetmek için Azure Active Directory (Azure AD) kullanasınız.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>HoloLens Otomatik Veri Yakalama Sistemleri (ADCS) otomatik kayıt özelliğine sahip mi?

Hayır.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>HoloLens, sanal Tümleşik Windows Kimlik Doğrulaması?

Hayır.

### <a name="does-hololens-support-branding"></a>HoloLens markayı destekliyor mu?

Hayır. Ancak, aşağıdaki yaklaşımlardan birini kullanarak bu soruna yönelik bir çalışma yapabilirsiniz:

- Özel bir uygulama oluşturun ve bilgi [noktası modunu etkinleştirin.](hololens-kiosk.md) Özel uygulama markaya sahip olabilir ve diğer uygulamaları (Remote Assist gibi) başlatabilirsiniz.  
- Azure AD'de tüm kullanıcı profili resimlerini şirket logonuzu olarak değiştirme. Ancak, tüm senaryolar için bu tercih edilmeyebilir.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>HoloLens 2 hangi günlük özelliklerini sunuyor?

Günlüğe kaydetme, geliştirme veya sorun giderme senaryolarında yakalanacak izlemeler veya cihazların Microsoft sunucularına göndermekte olduğu telemetri verileriyle sınırlıdır.

## <a name="questions-about-securing-hololens-devices"></a>HoloLens cihazlarının güvenliğini sağlamayla ilgili sorular

[HoloLens 2 güvenlik bilgilerimize bakın.](security-overview.md)
HoloLens 1. Nesil cihazlar için lütfen bu SSS [bölümünü gözden geçirin.](hololens1-faq-security.md)

[Listeye dön](#list)
