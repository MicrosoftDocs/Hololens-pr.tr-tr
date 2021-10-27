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
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351774"
---
# <a name="device-troubleshooting"></a>Cihaz Sorunlarını Giderme

Bu makalede çeşitli yaygın sorun giderme sorunlarının HoloLens açıklanmıştır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun. Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.

<a id="list"></a>

**Bilinen Sorunlar**
- [Insider düzeltmesi - Güç her yüzde 18'e inse cihaz aniden otomatik olarak kapanır](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
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
- [Bluetooth cihazlar eşlenmli değil](#bluetooth-devices-arent-pairing)
- [USB-C Mikrofon çalışmıyor](#usb-c-microphone-isnt-working)
- [Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Güç yüzde 18'e her gittiği zaman cihaz aniden otomatik olarak kapanır

> [!NOTE]
> Windows Insiders'da bu [soruna Windows vardır.](hololens-insider.md)

Cihaz %18 pile ulaştığında beklenmedik şekilde kapanması bilinen bir sorundur. Bu bir donanım veya pil sorunu değil yazılım sorunudur, bu nedenle lütfen cihaz değişimini yapma. Sorunda bu hatayla eş olup olmadığınız konusunda emin değilseniz lütfen:

1. Cihazlarınızı isteğe bağlı tanılamanın etkinleştirildiğinden emin olun
1. Sorunu yeniden oluşturma
1. Sorun [Geri Bildirim Merkezi](hololens-feedback.md) gönderme
1. Geri bildirim sorunu URL'sini paylaşma
1. [Desteğe başvurun](https://aka.ms/hololenssupport)

[Listeye geri dön](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP uygulaması Azure AD kullanıcıları için çalışmıyor

Azure AD hesabınızla OneDrive İş Için İş'i kullanıyorsanız, gelen kutunuzda oturum a OneDrive karşılaşmış olabilirsiniz. OneDrive uygulamasında oturum OneDrive, Kamera uygulaması tarafından yakalanan görüntülerin ve videoların otomatik karşıya yüklemelerini etkilemez. Dosyalarınız yine de kaydedilebilir ve bulut depolama OneDrive İş erişilebilir. Ekipler OneDrive HoloLens bu sorun üzerinde çalışıyor.

### <a name="workarounds"></a>Geçici Çözümler

Önkoşul: Müşteriler Microsoft Edge ve cihaz işletim sistemi bir Holographic, 21H1 Windows veya daha yeni bir sürüme güncelleştirildi olarak kullanabilir.

Bu sorunla karşılaşıyorsanız, aşağıdakilerden birini deneyin:

- Kullanıcılar OneDrive for Business'a Microsoft Edge tarayıcılarından kendi dosyalarıyla etkileşimde bulunabilir.
- Kullanıcılar, OneDrive PWA uygulamasını HoloLens indirerek Microsoft Edge. Bu, kullanıcıların cihazda dosyaları yeniden görüntülemesine ve yönetmesine olanak sağlar. OneDrive PWA uygulamasını [uygulamanıza yüklemek için bu yönergeleri okuyun ve HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Listeye geri dön](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot sırasında neden 0x80180014 görüyorum?

Bu hata genellikle cihaz sıfırlama ve yeniden kullanım sırasında bir HoloLens Autopilot'ın üzerinden en az bir kez geçerek gider. Bu sorunu çözmek için lütfen cihazı Microsoft Intune autopilot [akışını](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) tamamlamak için yeniden sıfırlayın.

Daha fazla bilgi için lütfen otomatik [pilot sayfasındaki sorun giderme adımlarına bakın.](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store kodu 0x80131500

Bazı kullanıcılar bu Microsoft Store beklendiği gibi çalışmayabilirsiniz ve hata kodunu 0x80131500. Bu, kümede ayarlanmış olan bölgenin HoloLens uygulamanın Microsoft Store mevcut HoloLens. Hata kodu hatasıyla karşılaşırsanız 0x80131500 için lütfen:

1. Time Ayarlar > Language & Region > > Country veya region & birini aşağıdakilerden biri olarak ayarlayın:
    - Birleşik Devletler, Japonya, Çin, Almanya, Kanada, Birleşik Krallık, İrlanda, Fransa, Avustralya, Yeni Zelanda.
1. Mağaza uygulamasını yeniden başlatın.
1. Cihazın tamamının değişikliği yansıtması için cihazın yeniden başlatılması gerekir.

HoloLens ekibi, daha fazla bölge için destek eklemeye çalışıyor.

[2. ülke satın alacak ülkeler için HoloLens bakın.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge başlatamaz

Mikrofon kullanan Microsoft Edge, mikrofon başlatılamayabilir, bu nedenle HoloLens'da Edge ile etkileşim kurmak HoloLens. Bu bilinen sorun, Microsoft Edge uygulamasının sürümüyle ilgilidir. Lütfen cihazınızı önceki bir sürüme ters eğik çizgiyle uygulamayın. Bu sorun bu sorunu çözmez.

### <a name="who-is-affected"></a>Who etkileniyor mu?

Sürüm 93 Microsoft Edge 94 veya 95'e sahip kullanıcılar.
Microsoft Store uygulamasını kullanarak sahip Microsoft Edge sürümünü kontrol edin, ardından ... ile temsil edilen "Daha fazla gör" düğmesini ve ardından **İndirmeler** ve **güncelleştirmeler'i seçin.**

### <a name="work-around"></a>Çalışma

Geçerli düzeltme, Microsoft Edge Insiders'a kaydolan kullanıcılar tarafından kullanılabilen 96. sürümdedir. Bu, cihazınızı bir Windows Insider olarak kaydetmekten farklıdır. [Edge'in insider](hololens-new-edge.md#microsoft-edge-insider-channels) programına kaydolma hakkında ayrıntılı bilgi için bu yönergeleri okuyun.

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

Holographic'te bir cihazı Windows şekilde yeniden başlatmak için [sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1) başlat menüsünü açın ve kullanıcı simgesini ve ardından Yeniden Başlat'ı **seçin.**

[Listeye geri dön](#list)

## <a name="auto-login-asks-for-log-in"></a>Otomatik oturum açma, oturum açma bilgilerini sorar

Bir HoloLens 2 cihaz, Ayarlar Hesapları Oturum Açma Seçenekleri **->** ve Gerekli altında değeri Asla olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.   Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir. Bu bilinen bir **sorundur.**

Bunun ne zaman oluştuğuna örnek:

- Bir cihazı Windows Holographic, sürüm 2004 (Derleme 19041.xxxx) ile Windows Holographic, sürüm 21H1 (Derleme 20346.xxxx) güncelleştirme
- Bir cihazı aynı büyük derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'Windows Holographic, sürüm 20H2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bu durum aşağıdakiler sırasında oluşmaz:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerle ilgili çalışma:

- PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el ile [ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-flashing-mode-procedure)

[Listeye geri dön](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatıla

> [!NOTE]
> Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş. Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md) Doğru değilse lütfen geri bildirim gönderin.

Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi. Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve uygulama güncelleştirmeleriyle Windows çözülemez. Bu sorunla karşılaşıyorsanız ve [Windows'nin](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız lütfen [Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: > Windows Güncelleştirme'yi yükleme, yükleme ve yapılandırma.

Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur. Geri Bildirim Merkezi aracılığıyla hata Geri Bildirim Merkezi araştırmamıza yardımcı olacak! Bu bilinen bir **sorundur.**

[Listeye geri dön](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klavye özel karakterlere geçiş değil

OOBE sırasında, kullanıcı bir iş veya okul hesabı seçtikten ve parolasını girdikten sonra &123 düğmesine dokunarak klavyedeki özel karakterlere geçmeye çalışırken özel karakterlere geçmemeye çalıştığı bir sorun vardır. Bu bilinen bir **sorundur.**

Çalışma:

- Metin alanına dokunarak klavyeyi kapatın ve yeniden açın.
- Parolanızı yanlış girin. Klavye bir sonraki sefer yeniden edilse beklendiği gibi çalışacaktır.
- Web Kimlik Doğrulaması'nın klavyesini kapatın ve başka **bir cihazdan Oturum açın'ı seçin.**
- Yalnızca sayı giriliyorsa, kullanıcı belirli tuşlara basarak ve basılı tutarak genişletilmiş menüyü açabilir.
- USB klavyesi kullanma.

Bu durum şunları etkilemez:

- Kişisel hesap kullanmayı seçen kullanıcılar.

[Listeye geri dön](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Kilitli dosyaları indirme hatası yok

> [!NOTE]
> Bu, Holographic **sürüm** [21H1 - Temmuz 2021 Güncelleştirmesi'Windows düzeltilmiştir.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)

Önceki Windows Holographic derlemesinde kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olurdu. Holographic Windows sürüm 21H1 güncelleştirmesinde kilitli bir dosyayı indirmeye çalışıldı ve herhangi bir şey görünmüyor. Dosya indirilemeyebilir ve hata yoktur.

[Listeye geri dön](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Cihaz Portalı karşıya yükleme/indirme zamanları dışında
> [!NOTE]
> Bu, Holographic **sürüm** [21H1 - Temmuz 2021 Güncelleştirmesi'Windows düzeltilmiştir.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Ssl Bağlantısını daha önce geçici çözümün bir parçası olarak devre dışı bırakdıysanız, yeniden etkinleştirmenizi kesinlikle öneririz.

Bazı müşteriler dosyaları karşıya yükleme veya indirme girişiminde bulunurken işlem askıda gibi görünebilir ve sonra zaman uzar veya hiçbir zaman tamamlanmadı. Bu, bilinen 'dosya[kilitli'](#downloading-locked-files-doesnt-error) sorunundan ayrıdır; bu durum Windows Holographic, sürüm 2004, 20H2 ve 21H1 pazar için derlemeleri etkiler. Sorunun kök nedeni, Cihaz Portalı isteklerin işlenmesinde oluşan bir hatadır ve varsayılan https kullanılırken en tutarlı şekilde bu soruna neden olur.

### <a name="workaround"></a>Geçici çözüm

Wi-Fi ve UsbNcm'ye eşit şekilde uygulanan bu geçici çözüm, "SSL Bağlantısı" altında "gerekli" seçeneğini devre dışı bırakmaktır. Bunu yapmak için Cihaz Portalı, **Sistem'e gidin** ve **Tercihler sayfasını** seçin. Cihaz Güvenliği bölümünde SSL **Bağlantısı'nın** **yerini bulun ve Gerekli'yi** devre dışı bırakmak için işaretini **kaldırın.**

Kullanıcı daha sonra http:// (IP adresi) https:// dosya yükleme ve indirme gibi özellikler çalışmaya devam ediyor.

[Listeye geri dön](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider derlemesi ile yanıp sönen bir cihazda Insider önizleme kaydından sonra mavi ekran

Bu, Bir Insider önizleme derlemesi olan kullanıcıları etkileyen, yeni bir insider önizleme derlemesi ile HoloLens 2'lerini yeniden yazdıran ve insider programından kaydı s olan kullanıcıları etkileyen bir sorundur. Bu bilinen bir **sorundur.**

Bu durum şunları etkilemez:

- Windows Insider'a kayıtlı olan kullanıcılar
- Içerdekiler:
    - Insider derlemeleri 18362.x sürümünden beri bir cihaz kayıtlı ise
    - Insider imzalı bir 19041.x derlemesi sönerse VE Insider programına kayıtlı kalır

Üzerinde çalışma:

- Sorundan kaçının
    - İçinde olmayan bir derlemeyi flash iletir. Normal aylık güncelleştirmelerden biri.
    - Insider Preview'da kalın
- Cihaza ters eğik çizgi

    1. Bağlantı [HoloLens kapatarak](hololens-recovery.md) el ile 2'nin yanıp sönme moduna alın. Ardından Birim'i basılı tutarken Güç düğmesine dokunun.

    1. Bağlan ve Gelişmiş Kurtarma Yardımcı'sı'nu açın.

    1. HoloLens 2'den varsayılan derlemeye flash iletir.

[Listeye geri dön](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive resimleri otomatik olarak karşıya yüklemez

OneDrive için HoloLens uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez. Bu bilinen bir **sorundur.**

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama çift oturum açmayı destekler). Otomatik Microsoft hesabı profilinden OneDrive arka plan kameralı zar yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile OneDrive yükleyebilirsiniz. Bunu yapmak için, OneDrive uygulamasında iş veya okul hesabınızla oturum OneDrive olun. düğmesini seçin **+** ve ardından seçeneğini **Upload.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları Bulmak için Resimler ve Kamera > **yolunu izleyin.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

[Listeye geri dön](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens yanıt vermiyor veya başlatılmayıyor

Çalışma HoloLens başlatılamayr:

- Güç düğmesinin yanındaki LED'ler yanmıyorsa veya yalnızca bir LED kısa süre yanıp sönüyorsa, güç kaynağınızı [HoloLens.](hololens2-charging.md#charging-the-device)
- Güç düğmesine bastığınızda LED'ler yansa ama ekranlarda hiçbir şey görmüyorsanız, [cihazı sabit bir şekilde sıfırlayın.](hololens-recovery.md#hard-restart-procedure)

Bu HoloLens donmuş veya yanıt vermiyorsa:

- Led'HoloLens beşi de kapatana kadar güç düğmesine basarak veya LED'ler yanıt vermiyorsa 15 saniye boyunca güç düğmenizi kapatın. Çalışmanızı başlatmak HoloLens tekrar güç düğmesine basın.

Bu adımlar işe çalışmıyorsa, HoloLens [2](hololens-recovery.md) cihazınızı veya HoloLens [(1. nesil) cihazınızı kurtarmayı denemeniz gerekir.](hololens1-recovery.md)

[Listeye geri dön](#list)

## <a name="low-disk-space-error"></a>"Düşük Disk Alanı" hatası

Aşağıdakilerden birini veya daha fazlasını yaparak biraz depolama alanı serbest bırakabilirsiniz:

- Kullanılmayan bazı alanları silin. Sistem   >  **Ayarlar'a**  >  **gidin,** artık ihtiyacınız olmayacak bir alan seçin ve ardından **Kaldır'ı seçin.**
- Yerleştiren hologramlardan bazılarını kaldırın.
- Fotoğraflar uygulamasından bazı resimleri ve videoları silin.
- Uygulamanıza bazı uygulamaları HoloLens. Uygulama **Tüm uygulamalar** kaldırmak istediğiniz uygulamaya dokunarak basılı tutun ve Kaldır'ı **seçin.**

[Listeye dön](#list)

## <a name="calibration-fails"></a>Hataya neden olan hata

Ayar çoğu kişi için işe yaramazsa, ancak ayarlamanın başarısız olduğu durumlar vardır.
  
Hatanın olası nedenlerinden bazıları şunlardır:

- Dikkati dağıldı ve dalıntı hedeflerini takip edede
- Kirli veya karalamalı cihaz görünür ya da cihaz görünür düzgün bir şekilde konumlanmaz
- Kirli veya karalamalı gözlükler
- Bazı kişi lensleri ve gözlük türleri (renkli iletişim lensleri, bazı toric iletişim lensleri, IR engelleyici gözlükler, bazı yüksek gözlükler, güneş gözlüğü veya benzerleri)
- Daha belirgin bir şekilde ifade edilir ve bazı kirpik uzantıları
- Cihazın sizin gözlerinizi görmesini engelliyorsa kıllar veya kalın gözlük çerçeveleri
- Dar göz, uzun kirpikler, amblyphya, nystagmus, LASIK veya diğer göz ameliyatları gibi belirli gözfiyatları, göz koşulları veya göz ameliyatı

Başarısız bir sonuç elde edilirse şunları deneyin:

- Cihaz mengenenizi temizleme
- Gözlüklerinizi temizleme
- Cihazınızın gözlerinizi mümkün olduğunca yakınına itme
- Nesnelerini mengenenizin dışında (örneğin, kıllar) taşıma
- Odanıza bir ışığı açma veya doğrudan dışarı çıkma

Tüm yönergeleri izlediy ve yine de düzeltme başarısız oluyorsa, komut istemini devre dışı Ayarlar. Ayrıca, Geri Bildirim Merkezi'da geri bildirim [göndererek bize bildirin.](hololens-feedback.md)

Ayrıca görüntü rengi veya parlaklığı [sorunlarını gidermek için ilgili bilgilere bakın.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

IpD ayarı, sistem tarafından HoloLens 2 için geçerli değildir. 

[Listeye dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Oturum aça bilmiyorum çünkü HoloLens başka biri için ayarlanmış

Cihazı [FlashIng **Mode'a yer ve cihazı** kurtarmak için Gelişmiş Kurtarma Yardımcı'sı](hololens-recovery.md#clean-reflash-the-device) kullanabilirsiniz.

[Listeye dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar, Unity [forumlarında HoloLens belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

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

Ses Cortana yanıt vermiyorsa, komutlar Cortana emin olun. Değişiklik Tüm uygulamalar menü **not**  >    >  **Cortana'ı**  >  **Ayarlar** seçin. Neler söylemeniz hakkında daha fazla bilgi edinmek için [bkz. HoloLens.](hololens-cortana.md)

Bu HoloLens (1. nesil) yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açık. 2 HoloLens de, cihaz kurulumu sırasında hem konuşma tanımayı hem de Cortana açıp açmayabilirsiniz.

HoloLens 2'niz sesinize yanıt vermiyorsa Konuşma tanıma'nın açık olduğundan emin olun. Gizlilik **Konuşmasında**  >    >    >  **Ayarlar'a gidin** ve Konuşma **tanıma'ya gidin.**

[Listeye dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

Bu HoloLens emin olmak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik Giriş, ellerinizi takip etmek için size geri bildirim sağlar.  Geri bildirim, farklı sürümlerde farklı HoloLens:

- Genel HoloLens (1. nesil) üzerinde bakış imleci bir noktadan halkaya değişir
- Bu HoloLens 2'de, el bir görüntüye yaklaşacaksa parmak izi imleç görünür ve kayıntılar daha uzak olduğunda bir el imleç görünür

Birçok çevreleyici uygulama, Karma Gerçeklik Giriş'e benzer giriş desenlerini takip eder.  HoloLens [(1. nesil) ve 2. nesil'de](hololens1-basic-usage.md#use-hololens-with-your-hands) el HoloLens [daha fazla bilgi.](hololens2-basic-usage.md#the-hand-tracking-frame)

Maske takıyorsanız, bazı maske türlerinin el izleme ile çalışmay olduğunu unutmayın.  Yaygın olarak kullanılan bir örnek de, derin kamera tarafından alınmayacak olan siyah renkli silikonlardır.  Çalışmalarınız silikon silikon içeriyorsa mavi veya gri gibi daha açık bir renkle çalışmanızı öneririz.  Bir diğer örnek de, el şeklinizi karartma eğiliminde olan büyük baggy eldivenleridir. En iyi sonuçlar için mümkün olduğunca forma uygun olan eldivenlerin kullanılması önerilir.

Mengenenizin parmak izleri veya muzlaları varsa, mengenenizi hafifçe temizlemek için HoloLens ile birlikte gelen mikrofiber temizleme izini kullanın.

[Listeye dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi'a bağlanamıyor

Ağ bağlantınızı bir ağ HoloLens bağlanamıyorsanız deneyebilirsiniz Wi-Fi:

- Bu Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketini kullanın ve ağ **Ayarlar**  >  **&amp; Wi-Fi'ı**  >  **seçin.** Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Ağ yönlendiricinizi Wi-Fi ve ardından [ile HoloLens.](hololens-recovery.md) Bağlanmayı yeniden deneyin.
- Bunlardan hiçbiri çalışmıyorsa yönlendiricinizin en son bellenim sürümünü kullana olduğundan emin olun. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazları eşleyemli değil

Bir Bluetooth cihazı [eşleştirmeyle ilgili Bluetooth](hololens-connect-devices.md)aşağıdakini deneyin:

- **Cihazlar'Ayarlar**  >  **gidin** ve Bluetooth emin olun. Varsa, tekrar kapatın ve tekrar açma.
- Cihaz cihazınızın tamamen Bluetooth veya yeni piller olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens.](hololens-recovery.md)

[Listeye dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C Mikrofon çalışmıyor

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili bir sorundur ve mikrofonla HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Sistem   ->  **Ayarlar'de** yerleşik konuşmacıları (Analog Özellik Ses  ->   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor

HoloLens (1. nesil) ses profillerinin Bluetooth desteklemez. Bluetooth ve mikrofonlu HoloLens kullanılabilir ancak bunlar desteklenmiyor.

HoloLens 2, stereo kayıttan Bluetooth A2DP ses profilini destekler. 2 Bluetooth bir çevre biriminden mikrofon yakalamayı Bluetooth Sağlayan HoloLens profili.

Bluetooth cihazı kullanırken sorun Bluetooth desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar aşağıdakileri içerir:

- İngilizce dilinde QWERTY Bluetooth klavyeleri kullanır (bunları holografik klavyeyi her yerde kullanabilirsiniz).
- Bluetooth fareler.
- HoloLens [tıklayın.](hololens1-clicker.md)

DIĞER cihazlarınızı BLUETOOTH GATT cihazlarıyla kendi cihazlarınız ile HoloLens. Ancak, cihazları gerçekten kullanmak için ilgili yardımcı uygulamaları Microsoft Store uygulamaları yüklemeniz gerekir.

[Listeye dön](#list)
