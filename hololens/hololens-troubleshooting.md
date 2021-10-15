---
title: HoloLens Cihaz Sorunlarını Giderme
description: Cihaz sorunlarını ve sorun giderme tekniklerini en HoloLens çözümlerini takip edin.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: sorunlar, hata, sorun giderme, düzeltme, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: 5c79e119352146ac249ef02ab888141391c9cea1
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034204"
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
- [Microsoft Store kodu 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge başlatamaz](#microsoft-edge-fails-to-start-the-microphone)
- [**Düzeltildi** - Remote Assist videosu 20 dakika sonra donuyor](#remote-assist-video-freezes-after-20-minutes)
- [Otomatik oturum açma, oturum açma bilgilerini sorar](#auto-login-asks-for-log-in)
- [Microsoft Edge başlatıla](#microsoft-edge-fails-to-launch)
- [Klavye özel karakterlere geçiş değil](#keyboard-doesnt-switch-to-special-characters)
- [**Düzeltildi** - Kilitli dosyalar indirildi hatası göster değil](#downloading-locked-files-doesnt-error)
- [**Düzeltildi** - Cihaz Portalı/indirme zamanları dışında](#device-portal-file-uploaddownload-times-out)
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

Cihaz %18 pile ulaştığında beklenmedik şekilde kapanması bilinen bir sorundur. Bu bir donanım veya pil sorunu değil yazılım sorunudur, bu nedenle lütfen cihaz değişimini yapma. Sorunda bu hatayla eş olup olmadığınız konusunda emin değilseniz lütfen:

1. Cihazlarınızı isteğe bağlı tanılamanın etkinleştirildiğinden emin olun
1. Sorunu yeniden oluşturma
1. Sorun [Geri Bildirim Merkezi](hololens-feedback.md) gönderme
1. Geri bildirim sorunu URL'sini paylaşma
1. [Desteğe başvurun](https://aka.ms/hololenssupport)

[Listeye dön](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP uygulaması Azure AD kullanıcıları için çalışmıyor

Azure AD hesabınızla OneDrive İş Için İş'i kullanıyorsanız, gelen kutunuzda oturum a OneDrive karşılaşmış olabilirsiniz. OneDrive uygulamasında oturum OneDrive, Kamera uygulaması tarafından yakalanan görüntülerin ve videoların otomatik karşıya yüklemelerini etkilemez. Dosyalarınız yine de kaydedilebilir ve bulut depolama OneDrive İş erişilebilir. Ekipler OneDrive HoloLens bu sorun üzerinde çalışıyor.

### <a name="workarounds"></a>Geçici Çözümler

Önkoşul: Müşteriler Microsoft Edge ve cihaz işletim sistemi bir Windows Holographic, 21H1 veya daha yeni bir sürüme güncelleştirildi olarak kullanabilir.

Bu sorunla karşılaşıyorsanız, aşağıdakilerden birini deneyin:

- Kullanıcılar, OneDrive for Business'a Microsoft Edge tarayıcılarından kendi dosyalarıyla etkileşimde bulunabilir.
- Kullanıcılar, OneDrive PWA uygulamasını HoloLens indirerek Microsoft Edge. Bu, kullanıcıların cihazda dosyaları yeniden görüntülemesine ve yönetmesine olanak sağlar. OneDrive PWA uygulamasını [uygulamanıza yüklemek için bu yönergeleri okuyun ve HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Listeye dön](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot sırasında neden 0x80180014 görüyorum?

Bu hata genellikle cihaz sıfırlama ve yeniden kullanım sırasında bir HoloLens Autopilot'ın üzerinden en az bir kez geçerek gider. Bu sorunu çözmek için lütfen autopilot akışını tamamlamak [Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) cihazı cihazdan silin ve yeniden sıfırlayın.

Daha fazla bilgi için lütfen otomatik [pilot sayfasındaki sorun giderme adımlarına bakın.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store hata kodu 0x80131500

Bazı kullanıcılar bu Microsoft Store beklendiği gibi çalışmayabilirsiniz ve hata kodunu 0x80131500. Bu, kümede ayarlanmış olan bölgenin HoloLens uygulamanın Microsoft Store mevcut HoloLens. Hata kodu hatasıyla karşılaşırsanız 0x80131500 geçici çözüm olarak lütfen:

1. Time Ayarlar > Language & Region > Country > region (Ülke veya bölge) için aşağıdakilerden birini ayarlayın:
    - Birleşik Devletler, Japonya, Çin, Almanya, Kanada, Birleşik Krallık, İrlanda, Fransa, Avustralya, Yeni Zelanda.
1. Mağaza uygulamasını yeniden başlatın.
1. Cihazın tamamının değişikliği yansıtması için cihazın yeniden başlatılması gerekir.

HoloLens ekibi, daha fazla bölge için destek eklemeye çalışıyor.

[2. abd için satın alma HoloLens bakın.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge başlatamaz

Kullanıcılar Microsoft Edge mikrofon başlatılanamayabilir, bu nedenle HoloLens'da Edge ile etkileşim kurmak HoloLens. Bu bilinen sorun, Microsoft Edge uygulamasının sürümüyle ilgilidir. Lütfen cihazınızı önceki bir sürüme ters eğik çizgiyle eğik çizgiyle uygulamayın. Bu sorun bu sorunu çözmez.

### <a name="who-is-affected"></a>Who etkileniyor mu?

Sürüm 93 Microsoft Edge 94 veya 95'e sahip kullanıcılar.
Microsoft Store uygulamasını kullanarak sahip Microsoft Edge sürümünü kontrol edin, ardından ... ile temsil edilen "Daha fazla gör" düğmesini ve ardından **İndirmeler** ve **güncelleştirmeler'i seçin.**

### <a name="work-around"></a>Çalışma

Geçerli düzeltme, Microsoft Edge Insiders'a kaydolan kullanıcılar tarafından kullanılabilen 96. sürümdedir. Bu, cihazınızı Windows Insider olarak kaydetmekten farklıdır. [Edge'in insider](hololens-new-edge.md#microsoft-edge-insider-channels) programına kaydolma hakkında ayrıntılı bilgi için bu yönergeleri okuyun.

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist videosu 20 dakika sonra donuyor

> [!NOTE]
> Remote Assist'in bu sorun için bir düzeltmesi olan daha yeni bir sürümü vardır. Bu [sorunu önlemek için lütfen Remote Assist'i](holographic-store-apps.md#update-apps) en son sürüme güncelleştirin.

> [!NOTE]
> Bu Bilinen Sorunun önem derecesi nedeniyle Holographic sürüm 21H1'in Windows geçici olarak duraklatıldı. 21H1 derlemesi artık yeniden kullanılabilir, bu nedenle cihazlar bir kez daha en son 21H1 derlemeye güncelleştirilebilir.

[Windows Holographic sürüm 21H1'in](hololens-release-notes.md#windows-holographic-version-21h1)en son sürümünde, Remote Assist'in bazı kullanıcıları 20 dakikadan fazla arama sırasında video donma durumuyla karşılandı. Bu bilinen bir **sorundur.**

### <a name="workarounds"></a>Geçici Çözümler

Remote Assist'i daha yeni bir derlemeye güncelleştiremiyorsanız aşağıdaki adımları deneyin.

#### <a name="restart-in-between-calls"></a>Çağrılar arasında içinde yeniden başlatma

Çağrılarınız 20 dakikadan uzun sürüyorsa ve bu sorunla karşılaşıyorsanız cihazınızı yeniden başlatmayı deneyin. Cihazınızı Remote Assist çağrıları arasında yeniden başlatmak cihazınızı yeniler ve iyi bir durum haline geri döner.

Holographic'te bir cihazı Windows şekilde yeniden başlatmak için [sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1) başlat menüsünü açın ve kullanıcı simgesini ve ardından Yeniden Başlat'ı **seçin.**

[Listeye dön](#list)

## <a name="auto-login-asks-for-log-in"></a>Otomatik oturum açma, oturum açma bilgilerini sorar

HoloLens 2 cihazı, **Ayarlar**  ->  **hesapları**  ->  **oturum açma seçenekleri** -> aracılığıyla otomatik olarak oturum açmak üzere yapılandırılabilir ve değeri **hiçbir** şekilde olarak ayarlamak **gerekir** . Bir cihaz, özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştirilirken cihazda oturum açmak için bazı kullanıcılar gerekebilir. Bu bilinen bir **sorundur**.

Bunun gerçekleşebileceğini örnek:

- Windows Holographic 'den bir cihaz güncelleştiriliyor, sürüm 2004 (derleme 19041. xxxx) Windows Holographic, sürüm 21h1 (derleme 20346. xxxx)
- bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004 Windows Holographic, sürüm 20h2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bunun sırasında gerçekleşmemelidir:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerin etrafında çalışın:

- PIN, parola, Iris, Web kimlik doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN kodu hatırlanamaz ve diğer kimlik doğrulama yöntemleri kullanılabilir değilse, bir Kullanıcı [el ile yerleştirme modunu](hololens-recovery.md#manual-flashing-mode-procedure)kullanabilir.

[Listeye geri dön](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatılamadı

> [!NOTE]
> bu sorun başlangıçta Microsoft Edge 'nin sevkiyat sürümü ile oluşturulmuştur. Bu sorun [yeni Microsoft Edge](hololens-new-edge.md)çözülebilir. Aksi takdirde, lütfen geri bildirimde bulunun.

birkaç müşteri Microsoft Edge başlatamayacağı bir sorun bildirdi. bu müşteriler için, sorun yeniden başlatma ile devam etmez ve Windows veya uygulama güncelleştirmeleriyle çözümlenmez. bu sorunla karşılaşıyorsanız ve [Windows güncel olduğunu](hololens-updates.md#manually-check-for-updates)onayladıysanız, lütfen aşağıdaki kategori ve alt kategori ile [geri bildirim merkezi](hololens-feedback.md) uygulamasından bir hata bildirin: Windows Update yükleme ve güncelleştirme > indirme, yükleme ve yapılandırma.

Sorunun şu ana kadar köke neden olmadığı bilinen bir geçici çözüm yoktur. Geri Bildirim Hub 'ı aracılığıyla bir hata dosyalama araştırmasına yardımcı olacak! Bu bilinen bir **sorundur**.

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
- Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey göremiyorsanız, [cihazın kalıcı olarak sıfırlanması](hololens-recovery.md#hard-restart-procedure)gerekir.

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

Ayrıca, [görüntü renk veya parlaklık sorun giderme](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) için ilgili bilgiler bölümüne bakın.

göz konumları sistem tarafından hesaplandığından ıpd 'nin ayarlanması HoloLens 2 için geçerli değildir. 

[Listeye geri dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor

Cihazı daha [ **yanıp sönen moda** yerleştirebilir ve Gelişmiş kurtarma Yardımcısı 'nı kullanarak](hololens-recovery.md#clean-reflash-the-device) cihazı kurtarabilirsiniz.

[Listeye geri dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.
- unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.

[Listeye geri dön](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Cihaz portalı düzgün çalışmıyor

- Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.

- Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir. Bunların kullanılması hiçbir etkiye sahip olmayacaktır. Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.

- Ayarlar geliştirici modunu etkinleştirdikten sonra, cihaz portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.

[Listeye geri dön](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator çalışmıyor

HoloLens öykünücüsü hakkındaki bilgiler geliştirici belgelerimizde bulunur.  [HoloLens öykünücüsünün sorunlarını giderme](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)hakkında daha fazla bilgi edinin.


- Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir. Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.
- Emulator PC web kamerasını kullanamazsınız.
- Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz. Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.

[Listeye geri dön](#list)

## <a name="voice-commands-arent-working"></a>Sesli komutlar çalışmıyor

Cortana sesli komutlarınıza yanıt vermiyorsa Cortana açık olduğundan emin olun. tüm uygulamalar listesinde,   >    >  değişiklikler yapmak için Cortana menü **not defteri**  >  **Ayarlar** ' ni seçin. Ne söyleyebilirim hakkında daha fazla bilgi edinmek için bkz. [HoloLens sesinizi kullanma](hololens-cortana.md).

HoloLens (1. gen) üzerinde, yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açıktır. HoloLens 2 ' de, cihaz kurulumu sırasında hem konuşma tanımayı hem de Cortana açıp kullanmayacağınızı seçebilirsiniz.

HoloLens 2 sesinize yanıt vermiyorsa, konuşma tanımanın açık olduğundan emin olun.   >  **Ayarlar**  >  **gizlilik**  >  **konuşmayı** başlat ' a gidin ve **konuşma tanımayı** açın.

[Listeye geri dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

HoloLens kendi ellerinizi görememesini sağlamak için, bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik ana sayfası, kollarınızın ne zaman izleneceğini bilmenizi sağlayan geri bildirim sağlar.  HoloLens farklı sürümlerinde geri bildirim farklıdır:

- HoloLens (1. genel) ' de, gaze imleci bir noktadan halka arasında değişir
- HoloLens 2 ' de, elinizdeki bir kurşun kalem 'e yakın olduğunda parmak izi imleci görünür ve sla 'lar daha fazla olduğunda bir el ray görünür

Birçok modern uygulama, karma gerçeklik ana 'ya benzer giriş desenlerine uyar.  [HoloLens (1. gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) ve [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)' de el girişi kullanma hakkında daha fazla bilgi edinin.

Birlikte çalışırken, bazı araç türlerinin el ile izleme ile çalışmadığına göz önünde bulundurun.  Yaygın olarak kullanılan bir örnek, artışlarını devralarak kızılötesi ışınına eğilen ve derinlik kamerası tarafından alınmayan siyah bir örnektir.  Çalışmanız lastik içeriyorsa, mavi veya gri gibi daha açık bir renk denemeyi öneririz.  Diğer bir örnek de büyük ölçekli bir örnektir ve bu, elinizin şeklinin gizlenmesi anlamına gelir. En iyi sonuçlar için mümkün olduğunca form sığdırma olarak bulunan gloonları kullanmanızı öneririz.

vizörü ' in parmak izleri veya kullanım alanları varsa, HoloLens ile birlikte gelen mikro fiber temizleme havsını kullanarak, vizörü 'yi temizleyin.

[Listeye geri dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi bağlanılamıyor

HoloLens Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:

- Wi-Fi açık olduğundan emin olun. bunu denetlemek için başlangıç hareketini kullanın, ardından **Ayarlar**  >  **Network &amp; ınternet**  >  **Wi-Fi** öğesini seçin. Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Wi-Fi yönlendiricinizi yeniden başlatın ve [HoloLens yeniden başlatın](hololens-recovery.md). Bağlanmayı yeniden deneyin.
- Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye geri dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazlar eşleştirmiyor

[Bluetooth bir cihazla eşleştirme](hololens-connect-devices.md)sorunları yaşıyorsanız, aşağıdakileri deneyin:

- **Ayarlar**  >  **cihazlar**' a gidin ve Bluetooth açık olduğundan emin olun. Varsa, devre dışı bırakın ve tekrar açın.
- Bluetooth cihazınızın tam olarak ücretlendirildiğini veya yeni pillere sahip olduğundan emin olun.
- Hala bağlanamıyorsanız [HoloLens yeniden başlatın](hololens-recovery.md).

[Listeye geri dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C mikrofonu çalışmıyor

Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. bu mikrofonlardan birini HoloLens içine takarken, ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.

![USB-C mikrofonları sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Ayarlar kullanılabilir olarak listelenen cihazlar çalışmıyor

HoloLens (1. gen) Bluetooth ses profillerini desteklemez. hoparlörler ve kulaklıklar gibi Bluetooth ses cihazları HoloLens ayarlarında kullanılabilir olarak görünebilir, ancak desteklenmez.

HoloLens 2, stereo kayıttan yürütme için Bluetooth A2DP ses profilini destekler. Bluetooth, Bluetooth çevresel bilgisayardan mikrofon yakalamaya izin veren ücretsiz profil HoloLens 2 ' de desteklenmez.

Bluetooth bir cihaz kullanırken sorun yaşıyorsanız, desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar şunları içerir:

- ingilizce-dil QWERTY Bluetooth klavyeler (bunları holographic klavyesini kullandığınız her yerde kullanabilirsiniz).
- Bluetooth fareler.
- [HoloLens click](hololens1-clicker.md).

diğer Bluetooth hıd ve gatt cihazlarını HoloLens ile birlikte eşleştirin. ancak, cihazları gerçekten kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.

[Listeye geri dön](#list)
