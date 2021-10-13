---
title: HoloLens Cihaz Sorunlarını Giderme
description: Cihaz sorunlarını ve sorun giderme tekniklerini en HoloLens çözümlerini takip edin.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: sorunlar, hata, sorun giderme, düzeltme, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924371"
---
# <a name="device-troubleshooting"></a>Cihaz Sorunlarını Giderme

Bu makalede çeşitli yaygın sorun giderme sorunlarının HoloLens açıklanmıştır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun. Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.

<a id="list"></a>

**Bilinen Sorunlar**
- [Güç yüzde 18'e her gittiği zaman cihaz aniden otomatik olarak kapanır](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP uygulaması Azure AD kullanıcıları için çalışmıyor](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Autopilot sırasında neden 0x80180014 görüyorum?](#why-do-i-see-0x80180014-during-autopilot)
- [Remote Assist videosu 20 dakika sonra donuyor](#remote-assist-video-freezes-after-20-minutes)
- [Otomatik oturum açma, oturum açma bilgilerini sorar](#auto-login-asks-for-log-in)
- [Microsoft Edge başlatıla](#microsoft-edge-fails-to-launch)
- [Klavye özel karakterlere geçiş değil](#keyboard-doesnt-switch-to-special-characters)
- [Kilitli dosyaları indirerek hata göster yok](#downloading-locked-files-doesnt-error)
- [Cihaz Portalı karşıya yükleme/indirme zamanları dışında](#device-portal-file-uploaddownload-times-out)
- [Insider derlemesi ile yanıp sönen bir cihazda Insider önizleme kaydından sonra mavi ekran](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive otomatik olarak karşıya resim yüklemez](#onedrive-doesnt-automatically-upload-pictures)

**Genel**
- [HoloLens yanıt vermiyor veya başlatılmayıyor](#hololens-is-unresponsive-or-wont-start)
- ["Düşük Disk Alanı" hatası](#low-disk-space-error)
- [HataYazma](#calibration-fails)
- [Oturum aça bilmiyorum çünkü HoloLens başka biri için ayarlanmış](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity çalışmıyor](#unity-isnt-working)
- [Windows Cihaz Portalı düzgün çalışmıyor](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator çalışmıyor](#the-hololens-emulator-isnt-working)

**Giriş**
- [Ses komutları çalışmıyor](#voice-commands-arent-working)
- [El girişi çalışmıyor](#hand-input-isnt-working)

**Bağlantı**
- [Wi-Fi bağlantısı kuramıyor](#cant-connect-to-wi-fi)

**Dış Cihazlar** 
- [Bluetooth cihazları eşleyemli değil](#bluetooth-devices-arent-pairing)
- [USB-C Mikrofon çalışmıyor](#usb-c-microphone-isnt-working)
- [Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Güç yüzde 18'e her gittiği zaman cihaz aniden otomatik olarak kapanır

Cihaz %18 pile ulaştığında beklenmedik şekilde kapanması bilinen bir sorundur. Bu bir donanım veya pil sorunu değil yazılım sorunudur, bu nedenle lütfen cihaz değişimini yapma. Sorunnizin bu hatayla eş olup olmadığını tam olarak emin değilseniz lütfen:

1. Cihazlarınızı isteğe bağlı tanılamanın etkinleştirildiğinden emin olun
1. Sorunu yeniden oluşturma
1. Sorun [Geri Bildirim Merkezi](hololens-feedback.md) gönderme
1. Geri bildirim sorunu URL'sini paylaşma
1. [Desteğe başvurun](https://aka.ms/hololenssupport)

[Listeye dön](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP uygulaması Azure AD kullanıcıları için çalışmıyor

Azure AD OneDrive kullanarak İş Için OneDrive kullanıyorsanız, gelen kutunuzda oturum a OneDrive karşılaşmış olabilirsiniz. OneDrive uygulamasında oturum açılamama, Kamera uygulaması tarafından yakalanan görüntülerin ve videoların otomatik karşıya yüklemesini etkilemez. Dosyalarınız yine de kaydedilebilir ve bulut depolama OneDrive İş erişilebilir. Ekipler OneDrive HoloLens bu sorun üzerinde çalışıyor.

### <a name="workarounds"></a>Geçici Çözümler

Önkoşul: Müşteriler Microsoft Edge ve cihaz işletim sistemi bir Windows Holographic, 21H1 derleme veya daha yeni bir sürüme güncelleştirildi olarak kullanabilir.

Bu sorunla karşılaşıyorsanız, aşağıdakilerden birini deneyin:

- Kullanıcılar, OneDrive for Business'a Microsoft Edge tarayıcılarından kendi dosyalarıyla etkileşimde bulunabilir.
- Kullanıcılar, OneDrive PWA uygulamasını HoloLens indirmek için Microsoft Edge. Bu, kullanıcıların cihazda dosyaları yeniden görüntülemesine ve yönetmesine olanak sağlar. OneDrive PWA uygulamasını [uygulamanıza yüklemek için bu yönergeleri okuyun ve HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Listeye dön](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot sırasında neden 0x80180014 görüyorum?

Bu hata genellikle cihaz sıfırlama ve yeniden kullanma sırasında bir HoloLens Autopilot'ın üzerinden en az bir kez geçerek gider. Bu sorunu çözmek için lütfen cihazı Microsoft Intune autopilot [akışını](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) tamamlamak için yeniden sıfırlayın.

Daha fazla bilgi için lütfen otomatik [pilot sayfasındaki sorun giderme adımlarına bakın.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist videosu 20 dakika sonra donuyor

> [!NOTE]
> Remote Assist'in bu sorun için bir düzeltmesi olan daha yeni bir sürümü vardır. Bu [sorunu önlemek için lütfen Remote Assist'i](holographic-store-apps.md#update-apps) en son sürüme güncelleştirin.

> [!NOTE]
> Bu Bilinen Sorunun önem derecesi nedeniyle Holographic sürüm 21H1'in Windows geçici olarak duraklatıldı. 21H1 derlemesi artık yeniden kullanılabilir, bu nedenle cihazlar bir kez daha en son 21H1 derlemeye güncelleştirilebilir.

[Windows Holographic sürüm 21H1'in](hololens-release-notes.md#windows-holographic-version-21h1)en son sürümünde, Remote Assist'in bazı kullanıcıları 20 dakikadan fazla arama sırasında video donma durumuyla yaşadı. Bu bilinen bir **sorundur.**

### <a name="workarounds"></a>Geçici Çözümler

Remote Assist'i daha yeni bir derlemeye güncelleştiremiyorsanız aşağıdaki adımları deneyin.

#### <a name="restart-in-between-calls"></a>Çağrılar arasında içinde yeniden başlatma

Çağrılarınız 20 dakikadan uzun sürüyorsa ve bu sorunla karşılaşıyorsanız cihazınızı yeniden başlatmayı deneyin. Cihazınızı Remote Assist çağrıları arasında yeniden başlatmak cihazınızı yeniler ve iyi bir durum haline geri döner.

Holographic'te bir cihazı Windows başlatmak için [sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1) başlat menüsünü açın ve kullanıcı simgesini ve ardından Yeniden Başlat'ı **seçin.**

[Listeye dön](#list)

## <a name="auto-login-asks-for-log-in"></a>Otomatik oturum açma, oturum açma bilgilerini sorar

HoloLens 2 cihazı, Ayarlar Hesapları Oturum Açma Seçenekleri **->** ve Gerekli altında değeri Hiçbir zaman olarak ayarlandı olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.   Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir. Bu bilinen bir **sorundur.**

Bunun ne zaman oluştuğuna örnek:

- Bir cihazı Windows Holographic, sürüm 2004 (Derleme 19041.xxxx) ile Windows Holographic, sürüm 21H1 (Derleme 20346.xxxx) güncelleştirme
- Bir cihazı aynı büyük derlemede büyük bir güncelleştirmeyi alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'Windows Holographic, sürüm 20H2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bu durum aşağıdakiler sırasında oluşmaz:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerle ilgili çalışma:

- PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el ile [ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-procedure)

[Listeye dön](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatıla

> [!NOTE]
> Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş. Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md) Doğru değilse lütfen geri bildirim gönderin.

Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi. Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve uygulama güncelleştirmeleriyle Windows çözülemez. Bu sorunla karşılaşıyorsanız ve [Windows'nin](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız, [lütfen Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: > Güncelleştirme'yi yükleme Windows, yükleme ve yapılandırma.

Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur. Geri Bildirim Merkezi aracılığıyla hata Geri Bildirim Merkezi araştırmamıza yardımcı olacak! Bu bilinen bir **sorundur**.

[Listeye geri dön](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klavye özel karakterlere geçmez

Kullanıcı bir iş veya okul hesabı seçtiği ve parolasını girerken, OOBE sırasında, &123 düğmesine dokunarak klavye üzerindeki özel karakterlere geçiş yapmaya çalışırken, özel karakterlere değişmediğinden, OOBE sırasında bir sorun vardır. Bu bilinen bir **sorundur**.

Work-arounds:

- Klavyeyi kapatın ve metin alanına dokunarak yeniden açın.
- Parolanızı yanlış girin. Klavye bir dahaki sefer çalışırken beklendiği gibi çalışır.
- Web kimlik doğrulaması, klavyeyi kapatın ve **başka bir cihazdan oturum aç**' ı seçin.
- Yalnızca sayı girilirse, bir kullanıcı genişletilmiş bir menü açmak için belirli tuşları basılı tutabilir.
- USB klavye kullanma.

Bu, şunları etkilemez:

- Kişisel hesap kullanmayı seçen kullanıcılar.

[Listeye geri dön](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Kilitli dosyaların indirilmesi hatası yok

> [!NOTE]
> bu bilinen bir **sorundur** [Windows Holographic, sürüm 21h1-temmuz 2021 güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

önceki Windows Holographic derlemeleriyle, kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olur. Windows Holographic, sürüm 21h1 güncelleştirmesi ' nde, kilitli bir dosyayı indirmeye çalışırken, hiçbir şey görünmez olmaz; dosya indirilmez ve hata yoktur.

[Listeye geri dön](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Cihaz portalı dosya yükleme/indirme zaman aşımı
> [!NOTE]
> bu bilinen bir **sorundur** [Windows Holographic, sürüm 21h1-temmuz 2021 güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Geçici çözümün bir parçası olarak SSL bağlantısını devre dışı bırakırsanız, yeniden etkinleştirmenizi kesinlikle öneririz.

Bazı müşteriler, dosyaları karşıya yüklemeye veya indirmeye çalışırken, işlem askıda kalabilir ve sonra zaman aşımına uğrar veya hiç tamamlanmayabilir. bu, '[dosya kilitli ' bilinen sorundan](#downloading-locked-files-doesnt-error) ayrıdır; bu Windows Holographic, sürüm 2004, 20h2 ve ' i etkileyen market derlemelerini etkiler. Sorun, cihaz portalının belirli isteklerin işlenmesinde oluşan bir hataya yol açtı ve varsayılan değer olan https kullanılırken en tutarlı şekilde isabet ediyor.

### <a name="workaround"></a>Geçici çözüm

Wi-Fi ve UsbNcm 'ye eşit olarak uygulanan bu geçici çözüm, "SSL bağlantısı" altında "gerekli" seçeneğinin devre dışı bırakılması. Bunu yapmak için cihaz portalı, **sistem**' e gidin ve **Tercihler** sayfasını seçin. **Cihaz güvenliği** bölümünde, **SSL bağlantısı**' nı bulun ve **gerekli**' ı devre dışı bırakmak için işaretini kaldırın.

Daha sonra Kullanıcı, https://(IP adresi) değil http://, dosya yükleme ve indirme gibi özellikler için de çalışır.

[Listeye geri dön](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran

bu, bir ınsider preview derlemesinde bulunan kullanıcıları etkiler, yeni bir ınsider preview derlemesi ile HoloLens 2 ' yi geri ve ardından ınsider programından kaydolduğunu etkileyen bir sorundur. Bu bilinen bir **sorundur**.

Bu, şunları etkilemez:

- Windows ınsider 'da kayıtlı olmayan kullanıcılar
- Insiders
    - Insider derlemeleri sürüm 18362. x olduğundan bir cihaz kaydedildiyse
    - Insider 'a imzalanmış bir 19041. x derlemesini düzder ve Insider programı 'nda kayıtlı kal

Geçici iş:

- Sorunu önleyin
    - Insider olmayan bir derlemeyi yakıp söndür. Normal aylık güncelleştirmelerden biri.
    - Insider Preview 'da kalın
- Cihazı kırın

    1. [HoloLens 2 ' ye](hololens-recovery.md) , bağlantı kurulamadı, tamamen güçleyerek manuel moduna koyun. Ardından, hacmi tutarken, güç düğmesine dokunun.

    1. bilgisayara Bağlan ve gelişmiş kurtarma yardımcısı ' nı açın.

    1. HoloLens 2 ' i varsayılan yapıya yakıp söndür.

[Listeye geri dön](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive otomatik olarak resim karşıya yüklememez

HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez. Bu bilinen bir **sorundur**.

Geçici çözümler:

- İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir. iş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama, çift oturum açma desteği sağlar). OneDrive içindeki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.

- fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza fotoğraf el ile yükleyebilirsiniz. bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun. Düğmesini seçin **+** ve **upload**' yi seçin. **Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun. Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.

[Listeye geri dön](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens yanıt vermiyor veya başlamıyor

HoloLens başlamazsa:

- Güç düğmesinin yanındaki LED 'ler soluk veya yalnızca bir tane kısa süreliğine yanıp sönse, [HoloLens ücretlendirmeniz gerekebilir.](hololens2-charging.md#charging-the-device)
- Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey göremiyorsanız, [cihazın kalıcı olarak sıfırlanması](hololens-recovery.md#hard-reset-procedure)gerekir.

HoloLens dondurulmuş hale gelirse veya yanıt vermiyorsa:

- bir led 'in beş bir kısmını devre dışı bırakır veya led 'ler yanıt vermiyorsa 15 saniye boyunca güç düğmesine basarak HoloLens kapatın. HoloLens başlatmak için, güç düğmesine yeniden basın.

bu adımlar işe yoksa, [HoloLens 2 cihazınızı](hololens-recovery.md) veya [HoloLens (1. gen) cihazınızı](hololens1-recovery.md) kurtarmayı deneyebilirsiniz.

[Listeye geri dön](#list)

## <a name="low-disk-space-error"></a>"Yetersiz disk alanı" hatası

Aşağıdakilerden birini veya birkaçını yaparak depolama alanını boşaltmanız gerekir:

- Kullanılmayan bazı boşlukları silin. **Ayarlar**  >  **sistem**  >  **alanları**' na gidin, artık ihtiyacınız olmayan bir alan seçin ve ardından **kaldır**' ı seçin.
- Yerleştirdiğiniz hologramlar bölümünü kaldırın.
- Fotoğraflar uygulamasındaki bazı resimleri ve videoları silin.
- HoloLens bazı uygulamaları kaldırın. **Tüm uygulamalar** listesinde, kaldırmak istediğiniz uygulamayı ve ardından **Kaldır**' ı seçin.

[Listeye geri dön](#list)

## <a name="calibration-fails"></a>Ayarlama başarısız

Ayarlama çoğu kişi için çalışmalıdır, ancak ayarlama işleminin başarısız olduğu durumlar vardır.
  
Ayarlama hatasının bazı olası nedenleri şunlardır:

- Ayarlama hedeflerini takip etme
- Kirli veya çizilmiş cihaz vizörü veya cihaz vizörü düzgün şekilde konumlandırılmadı
- Kirli veya çizik gözlük
- Belirli türlerde iletişim ve gözlük (renkli kişi mercekler, bazı haksız kişi mercekler, IR engelleme gözlüğü, yüksek kaliteli gözlük, güneş gözlüğü veya benzer)
- Daha fazla bilgi ve bazı eyeflash uzantıları
- Cihazın gözlerinizi görmesini engelliyorsa, saç veya kalın eyecam çerçeveler
- Dar gözler, uzun Eyelashes, amblyopia, nystagmus, bazı LASIK veya diğer gözle bazı durumlar gibi belirli gözle, göz önünde ve göz yormalileri

Ayarlama başarısız olursa, deneyin:

- Cihazınızı Temizleme vizörü
- Gözlerinizi Temizleme
- Cihazınızın vizörü ' i mümkün olduğunca yakın bir şekilde iletme
- Nesneleri (örneğin, saç) vizörü içinde hareket ettirmenin
- Odadaki bir ışığı açma veya doğrudan güneş dışına taşıma

tüm yönergeleri izlediyseniz ve ayarlama hala başarısız olursa, Ayarlar ayarlama isteğini devre dışı bırakabilirsiniz. Ayrıca, [geri bildirim merkezinde](hololens-feedback.md)geri bildirimde bulunarak bize bilgi verin.

Ayrıca görüntü rengi veya parlaklığı [sorunlarını gidermek için ilgili bilgilere bakın.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Göz pozisyonları sistem tarafından hesap HoloLens, IPD ayarı HoloLens 2 için geçerli değildir. 

[Listeye dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Oturum açam daha önce HoloLens başka biri için ayar olduğundan oturum aça bilmiyorum

Cihazı [FlashIng **Mode'a yer ve cihazı** kurtarmak için Gelişmiş Kurtarma Yardımcı'sı](hololens-recovery.md#clean-reflash-the-device) kullanabilirsiniz.

[Listeye dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar HoloLens [Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

[Listeye dön](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Cihaz Portalı düzgün çalışmıyor

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Geliştirici Modu'Ayarlar etkinleştirdikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

[Listeye dön](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator çalışmıyor

HoloLens öykünücüsü hakkında bilgiler geliştirici belgelerimizde bulunur.  HoloLens [öykünücüsünün sorunlarını giderme hakkında daha fazla bilgi edinebilirsiniz.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Uygulamanın tüm uygulamaları Microsoft Store öykünücü ile uyumlu değildir. Örneğin, Young Conker ve Parçalar öykünücüde oynatılamaz.
- Bilgisayar web kamerasını web kamerasını Emulator.
- Canlı Önizleme özelliği Windows Cihaz Portalı öykünücü ile birlikte çalışmıyor. Karma Gerçeklik videolarını ve görüntülerini yine de yakalayabilirsiniz.

[Listeye dön](#list)

## <a name="voice-commands-arent-working"></a>Ses komutları çalışmıyor

Ses Cortana yanıt vermiyorsa, komutlar Cortana emin olun. Değişiklik Tüm uygulamalar menü **not**  >    >  **Cortana'ı**  >  **Ayarlar** seçin. Neler söylemeniz hakkında daha fazla bilgi edinmek için [bkz.](hololens-cortana.md)HoloLens.

Bu HoloLens (1. nesil) yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açık. 2 HoloLens de, cihaz kurulumu sırasında hem konuşma tanımanın hem de Cortana açmanın gerekip gerek olmadığını seçebilirsiniz.

HoloLens 2'niz sesinize yanıt vermiyorsa Konuşma tanıma'nın açık olduğundan emin olun. Gizlilik **Konuşmasında**  >    >    >  **Ayarlar'a gidin** ve Konuşma **tanıma'ya gidin.**

[Listeye dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

Bu HoloLens emin olmak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik Giriş, ellerinizi takip etmek için size geri bildirim sağlar.  Geri bildirim, farklı sürümlerde farklı HoloLens:

- Genel HoloLens (1. nesil) üzerinde bakış imleci bir noktadan halkaya değişir
- 2 HoloLens de, el iziniz bir görüntüye yaklaşacaksa parmak izi imleç, kayıntılar daha uzak olduğunda ise el imleç görünür

Birçok çevreleyici uygulama, Karma Gerçeklik Giriş'e benzer giriş desenlerini takip eder.  HoloLens [(1. nesil) ve 2. nesil'de](hololens1-basic-usage.md#use-hololens-with-your-hands) el HoloLens [daha fazla bilgi.](hololens2-basic-usage.md#the-hand-tracking-frame)

Maske takıyorsanız, bazı maske türlerinin el izleme ile çalışmay olduğunu unutmayın.  Yaygın olarak kullanılan bir örnek de, derin kamera tarafından alınmayacak olan siyah renkli silikonlardır.  Çalışmanız silikonla ilgili ise mavi veya gri gibi daha açık bir renkle çalışmanızı öneririz.  Bir diğer örnek de, el şeklinizi karartma eğiliminde olan büyük baggy eldivenleridir. En iyi sonuçlar için mümkün olduğunca forma uygun olan eldivenlerin kullanılması önerilir.

Mengenenizin parmak izi veya muzlaları varsa, havayla birlikte gelen mikrofiber temizleme HoloLens ile birlikte kullanın.

[Listeye dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi'a bağlanamıyor

Ağ bağlantınızı bir ağ HoloLens Wi-Fi:

- Bu Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketi'Ayarlar Ağ **İnterneti**  >  **Wi-Fi'ı &amp;**  >  **seçin.** Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Wi-Fi yönlendiricinizi yeniden başlatın ve sonra [da HoloLens.](hololens-recovery.md) Bağlanmayı yeniden deneyin.
- Bunlardan hiçbiri çalışmıyorsa yönlendiricinizin en son bellenim sürümünü kullana olduğundan emin olun. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazları eşleyemli değil

Bir Bluetooth cihazı [eşleştirmeyle ilgili Bluetooth](hololens-connect-devices.md)aşağıdakini deneyin:

- **Cihazlar Ayarlar a**  >  **gidin** ve Bluetooth emin olun. Varsa, tekrar kapatın ve tekrar açma.
- Cihaz cihazınızın tamamen Bluetooth veya yeni piller olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens.](hololens-recovery.md)

[Listeye dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C Mikrofon çalışmıyor

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili değil mikrofonla ilgili HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

System   ->  **Ayarlar'da** yerleşik konuşmacıları (Analog Özellik Ses  ->   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor

HoloLens (1. nesil) ses profillerini Bluetooth desteklemez. Bluetooth ve mikrofonlu HoloLens gibi görünebilir, ancak bunlar desteklenmiyordur.

HoloLens 2, stereo kayıttan Bluetooth A2DP ses profilini destekler. 2 Bluetooth bir çevre biriminden mikrofon yakalamayı sağlayan Bluetooth Hands Free profili HoloLens desteklenmiyor.

Bluetooth cihazı kullanırken sorun Bluetooth desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar aşağıdakileri içerir:

- İngilizce dilinde QWERTY Bluetooth klavyeler (holografik klavyeyi her yerde kullanabilirsiniz).
- Bluetooth fare.
- HoloLens [tıklayın.](hololens1-clicker.md)

DIĞER BLUETOOTH VE GATT cihazlarını kendi cihazlarınız ile HoloLens. Ancak, cihazları gerçekten kullanmak için ilgili yardımcı uygulamaları Microsoft Store uygulamaları yüklemeniz gerekir.

[Listeye dön](#list)
