---
title: HoloLens Cihaz sorunlarını giderme
description: cihaz sorunlarını ve sorun giderme tekniklerini HoloLens en yaygın çözümlerin güncel kalmasını sağlar.
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
keywords: sorunlar, hata, sorun giderme, çözüm, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: 247cf9d34da723e587f6796178ad9a917b93ac08
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964573"
---
# <a name="device-troubleshooting"></a>Cihaz sorunlarını giderme

bu makalede, birkaç yaygın HoloLens sorunu çözme açıklanmaktadır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun. Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.

<a id="list"></a>

**Bilinen Sorunlar**
- [Her güç yüzde 18 ' e gittiğinde, cihaz aniden otomatik olarak kapanır](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive UWP uygulaması, Azure AD kullanıcıları için çalışmıyor](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Autopilot sırasında neden kaydedilmesi 0x80180014 görüyorum?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store hata kodu 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge mikrofonu başlatamıyor](#microsoft-edge-fails-to-start-the-microphone)
- [**Sabit** uzaktan yardım videosu 20 dakikadan sonra donuyor](#remote-assist-video-freezes-after-20-minutes)
- [Oturum açma için otomatik oturum açma sorulur](#auto-login-asks-for-log-in)
- [Microsoft Edge başlatılamadı](#microsoft-edge-fails-to-launch)
- [Klavye özel karakterlere geçmez](#keyboard-doesnt-switch-to-special-characters)
- [Kilitli dosyaların **sabit** indirilmesi hata göstermiyor](#downloading-locked-files-doesnt-error)
- [**Sabit** cihaz portalı dosya yükleme/indirme zaman aşımı](#device-portal-file-uploaddownload-times-out)
- [Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive otomatik olarak resim karşıya yüklememez](#onedrive-doesnt-automatically-upload-pictures)

**Genel**
- [HoloLens yanıt vermiyor veya başlamıyor](#hololens-is-unresponsive-or-wont-start)
- ["Yetersiz disk alanı" hatası](#low-disk-space-error)
- [Ayarlama başarısız](#calibration-fails)
- [HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity çalışmıyor](#unity-isnt-working)
- [Windows Cihaz portalı düzgün çalışmıyor](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator çalışmıyor](#the-hololens-emulator-isnt-working)

**Giriş**
- [Sesli komutlar çalışmıyor](#voice-commands-arent-working)
- [El girişi çalışmıyor](#hand-input-isnt-working)

**Bağlantı**
- [Wi-Fi ' a bağlanılamıyor](#cant-connect-to-wi-fi)

**Dış cihazlar** 
- [Bluetooth cihazlar eşleştirmiyor](#bluetooth-devices-arent-pairing)
- [USB-C mikrofonu çalışmıyor](#usb-c-microphone-isnt-working)
- [Ayarlar kullanılabilir olarak listelenen cihazlar çalışmıyor](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Her güç yüzde 18 ' e gittiğinde, cihaz aniden otomatik olarak kapanır

Cihazın %18 pil 'e ulaşması, beklenmedik bir şekilde kapatılacak bilinen bir sorun var. Bu bir donanım veya pil sorunu değildir, bu nedenle lütfen bu cihaz için yazılım alışverişi kullanmayın. Sorununuz bu hatayla eşleşiyorsa emin değilseniz, lütfen şunları yapın:

1. Cihazınızda isteğe bağlı tanılamaların etkinleştirildiğinden emin olun
1. Sorunu yeniden oluşturma
1. [Geri bildirim merkezi](hololens-feedback.md) sorunu gönderin
1. Geri bildirim sorun URL 'sini paylaşma
1. [Desteğe başvurun](https://aka.ms/hololenssupport)

[Listeye geri dön](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive UWP uygulaması, Azure AD kullanıcıları için çalışmıyor

Azure AD hesabınızı kullanarak iş için OneDrive kullanıyorsanız, gelen kutusu OneDrive uygulamanızda oturum açarken hata ile karşılaşmış olabilirsiniz. OneDrive uygulamada oturum açabilmeniz, kamera uygulaması tarafından yakalanan görüntülerin ve videoların otomatik olarak karşıya yüklenmesini etkilemez. dosyalarınız hala OneDrive İş bulut depolamadan kaydedilebilir ve erişilebilir. OneDrive ve HoloLens takımları sorun üzerinde çalışmaktadır.

### <a name="workarounds"></a>Geçici Çözümler

önkoşul: müşteriler Microsoft Edge kullanabilir ve cihaz işletim sistemi, Windows Holographic, 21h1 derlemesi veya daha yeni bir sürüme güncelleştirebilir.

Bu sorunu yaşıyorsanız, aşağıdakilerden birini deneyin:

- kullanıcılar, Microsoft Edge iş için OneDrive doğrudan erişebilir ve kendi tarayıcılarıyla web sitesiyle etkileşime geçebilir.
- kullanıcılar, HoloLens Microsoft Edge indirerek OneDrive PWA uygulamayı yükleyebilir. Bu, kullanıcıların cihazdaki dosyaları görüntülemesine ve yönetmesine izin verir. [HoloLens OneDrive PWA uygulamasını yüklemek için bu yönergeleri](holographic-store-apps.md#install-microsoft-onedrive-pwa-app) okuyun ve izleyin.

[Listeye geri dön](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot sırasında neden kaydedilmesi 0x80180014 görüyorum?

bu hata genellikle cihaz sıfırlama sırasında ve bir HoloLens cihazının en az bir kez Autopilot üzerinden gerçekleştiği akışlar yeniden kullanıldığı zaman ile karşılaşılır. bu sorunu çözmek için lütfen [cihazı Microsoft Intune silin](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) ve Autopilot akışını tamamladıktan sonra yeniden sıfırlayın.

Daha fazla bilgi için lütfen [Autopilot sayfasındaki sorun giderme adımlarına bakın.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store hata kodu 0x80131500

bazı kullanıcılar beklenmediği Microsoft Store çalışmayabilir ve 0x80131500 hata koduna bakın. bu, HoloLens Microsoft Store uygulamasında kullanılabilir olmayan HoloLens bölge kümesi nedeniyle oluşan bir sorundur. 0x80131500 hata koduyla karşılaşırsanız geçici çözüm için lütfen şunları yapın:

1. ülke veya bölge > Ayarlar > zaman & dil > bölgesini aşağıdakilerden birine ayarlayın:
    - Birleşik Devletler, Japonya, Çin, Almanya, Kanada, Birleşik Krallık, Irlanda, Fransa, Avustralya, Yeni Zelanda.
1. Mağaza uygulamasını yeniden başlatın.
1. Tüm cihazın değişikliği yansıtması için cihazın yeniden başlatılması gerekir.

HoloLens ekibi daha fazla bölge desteği eklemek için çalışmaktadır.

[ülkeler HoloLens 2 satın almak](hololens2-purchase.md) için buraya bakın.

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge mikrofonu başlatamıyor

mikrofon Microsoft Edge kullanan kullanıcılar başlayamayabilir, bu nedenle HoloLens ' de kenar ile etkileşimde bulunmak için kullanılamaz. bu bilinen sorun Microsoft Edge uygulamasının sürümü ile ilgilidir, bu sorunu çözmeyecek olduğundan cihazınızı daha önceki bir sürüme vermeyin.

### <a name="who-is-affected"></a>Who etkilendi?

93, 94 veya 95 Microsoft Edge sürümüne sahip kullanıcılar.
Microsoft Store uygulamasını kullanarak hangi Microsoft Edge sürümünü kullandığınızı denetleyebilir, ardından **.** .. tarafından temsil edilen "daha fazla bilgi" düğmesini seçin **ve ardından indirmeler ve güncelleştirmeler**' i seçin.

### <a name="work-around"></a>Geçici çözüm

geçerli çözüm, Microsoft Edge ınsiders 'e kaydolmuş kullanıcılar tarafından kullanılabilen sürüm 96 ' dir. bu, cihazınızı Windows ınsider olarak kaydetmekten farklıdır. [Edge Insider programına kaydolma](hololens-new-edge.md#microsoft-edge-insider-channels) hakkında ayrıntılı bilgi edinmek için bu yönergeleri okuyun.

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Uzaktan Yardım Videosu 20 dakikadan sonra donuyor

> [!NOTE]
> Uzak yardım 'ın bu sorun için bir düzeltmesine sahip daha yeni bir sürümü var. Bu sorundan kaçınmak için lütfen [uzak yardım](holographic-store-apps.md#update-apps) 'ı en son sürüme güncelleştirin.

> [!NOTE]
> bu bilinen sorunun önem derecesi nedeniyle, Windows Holographic, sürüm 21h1 kullanılabilirliğini geçici olarak duraklattık. 21 H1 derlemesi artık yeniden kullanılabilir, bu nedenle cihazlar yeniden en son 21H1 derlemesine güncelleştirilemeyebilir.

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)' in en son sürümünde, uzaktan yardım 'ın bazı kullanıcıları 20 dakikadan fazla çağrı sırasında video donduruyor demektir. Bu bilinen bir **sorundur**.

### <a name="workarounds"></a>Geçici Çözümler

Uzaktan Yardım 'ı daha yeni bir yapıya güncelleştireerişemiyorsanız, aşağıdaki çalışmayı deneyin.

#### <a name="restart-in-between-calls"></a>Çağrılar arasında yeniden Başlat

Çağrılarınızın uzunluğu 20 dakikadan fazla olursa ve bu sorunu yaşıyorsanız cihazınızı yeniden başlatmayı deneyin. Cihazınızı uzaktan yardım çağrıları arasında yeniden başlatmak cihazınızı yenileyip iyi bir duruma geri yerleştirecek.

Windows Holographic ' de bir cihazı hızlı bir şekilde yeniden başlatmak için [, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) başlat menüsünü açın ve kullanıcı simgesini seçin, sonra **yeniden başlat**' ı seçin.

[Listeye geri dön](#list)

## <a name="auto-login-asks-for-log-in"></a>Oturum açma için otomatik oturum açma sorulur

Bir HoloLens 2 cihazı, Ayarlar Hesapları Oturum Açma Seçenekleri **->** ve Gerekli altında değeri Hiçbir zaman olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.   Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir. Bu bilinen bir **sorundur.**

Bunun ne zaman oluştuğuna örnek:

- Bir cihazı Windows Holographic, sürüm 2004 (Derleme 19041.xxxx) ile Windows Holographic, sürüm 21H1 (Derleme 20346.xxxx) güncelleştirme
- Bir cihazı aynı büyük derlemede büyük bir güncelleştirmeyi alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'Windows Holographic, sürüm 20H2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bu durum aşağıdakiler sırasında oluşmaz:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerle ilgili çalışma:

- PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el [ile ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-procedure)

[Listeye geri dön](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatıla

> [!NOTE]
> Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş. Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md) Doğru değilse lütfen geri bildirim gönderin.

Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi. Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve uygulama güncelleştirmeleriyle Windows çözülemez. Bu sorunla karşılaşıyorsanız ve [Windows'nin](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız, [lütfen Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: > Windows Güncelleştirme'yi yükleme, yükleme ve yapılandırma.

Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur. Hatanın Geri Bildirim Merkezi dosyalamamız araştırmamıza yardımcı olacak! Bu bilinen bir **sorundur.**

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
> Bu **holographic, sürüm** [21H1 - Temmuz 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)güncelleştirmesinde Windows bilinen bir sorundur.

Windows Holographic'in önceki derlemesinde kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olurdu. Holographic Windows sürüm 21H1 güncelleştirmesinde kilitli bir dosyayı indirmeye çalışıldı. Bunun sonucunda görünür bir şey olmuyor; dosya indir olmuyor ve hata yok.

[Listeye geri dön](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Cihaz Portalı karşıya yükleme/indirme zamanları dışında
> [!NOTE]
> Bu **holographic, sürüm** [21H1 - Temmuz 2021](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)güncelleştirmesinde Windows bilinen bir sorundur. Ssl Bağlantısını daha önce geçici çözümün bir parçası olarak devre dışı bırakdıysanız, yeniden etkinleştirmenizi kesinlikle öneririz.

Bazı müşteriler dosyaları karşıya yükleme veya indirme girişiminde bulunurken işlem askıda gibi görünebilir ve sonra zaman uzar veya hiçbir zaman tamamlanmadı. Bu, bilinen 'dosya[kilitli'](#downloading-locked-files-doesnt-error) sorunundan ayrıdır; bu durum Windows Holographic, sürüm 2004, 20H2 ve 21H1 pazar için derlemeleri etkiler. Sorunun kök nedeni, belirli isteklerin işlenmesinde Cihaz Portalı bir hataya neden oldu ve en tutarlı olarak varsayılan https kullanılırken bu soruna neden oldu.

### <a name="workaround"></a>Geçici çözüm

Wi-Fi ve UsbNcm için de aynı şekilde geçerli olan bu geçici çözüm, "SSL Bağlantısı" altında "gerekli" seçeneğini devre dışı bırakmaktır. Bunu yapmak için Cihaz Portalı, **Sistem'e gidin** ve **Tercihler sayfasını** seçin. Cihaz Güvenliği bölümünde SSL **Bağlantısı'nın** **yerini bulun ve Gerekli'yi** devre dışı bırakmak için işaretini **kaldırın.**

Daha sonra kullanıcı, http:// (IP https://) değil, dosya yükleme ve indirme gibi özellikler çalışmaya devam ediyor.

[Listeye geri dön](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider derlemesi ile yanıp sönen bir cihazda Insider önizleme kaydından sonra mavi ekran

Bu, Bir Insider önizleme derlemesi olan kullanıcıları etkileyen, yeni bir insider önizleme derlemesi ile HoloLens 2'lerini yeniden yazdıran ve ardından Insider programından kaydı s olan kullanıcıları etkileyen bir sorundur. Bu bilinen bir **sorundur.**

Bu durum şunları etkilemez:

- Windows Insider'a kayıtlı Windows kullanıcılar
- Içerdekiler:
    - Insider derlemeleri 18362.x sürümünden beri bir cihaz kayıtlı ise
    - Insider imzalı bir 19041.x derlemesi sönerse VE Insider programına kayıtlı kalır

Üzerinde çalışma:

- Sorundan kaçının
    - İçinde olmayan bir derlemeyi flash iletir. Normal aylık güncelleştirmelerden biri.
    - Insider Preview'da kalın
- Cihaza ters eğik çizgi

    1. Bağlantı [HoloLens tamamen kapatarak HoloLens 2'i](hololens-recovery.md) el ile yanıp sönme moduna alın. Ardından Birim'i basılı tutarken Güç düğmesine dokunun.

    1. Bağlan ve Gelişmiş Kurtarma Yardımcı'sı'nu açın.

    1. 2. HoloLens varsayılan derlemeye yanıp söner.

[Listeye geri dön](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive otomatik olarak karşıya resim yüklemez

OneDrive için HoloLens uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez. Bu bilinen bir **sorundur.**

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama çift oturum açmayı destekler). Otomatik Microsoft hesabı profilinden OneDrive arka plan kameralı zar yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile OneDrive yükleyebilirsiniz. Bunu yapmak için, OneDrive uygulamasında iş veya okul hesabınızla oturum OneDrive olun. düğmesini seçin **+** ve seçeneğini Upload. Fotoğraf ve Kamera Rulosu'na giderek karşıya yüklemek istediğiniz **fotoğrafları veya > bulun.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

[Listeye geri dön](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens yanıt vermiyor veya başlatılmayıyor

HoloLens başlatılamayr:

- Güç düğmesinin yanındaki LED'ler yanmıyorsa veya yalnızca bir LED kısa süre yanıp sönüyorsa, güç kaynağınızı [HoloLens.](hololens2-charging.md#charging-the-device)
- Güç düğmesine bastığınızda LED'ler yansa ama ekranlarda hiçbir şey görmüyorsanız, [cihazı sabit bir şekilde sıfırlayın.](hololens-recovery.md#hard-reset-procedure)

Bu HoloLens donmuş veya yanıt vermiyorsa:

- Led'HoloLens beşi de kapatana kadar güç düğmesine basarak veya LED'ler yanıt vermiyorsa 15 saniye boyunca düğmenizi kapatın. Çalışmanızı başlatmak HoloLens tekrar güç düğmesine basın.

Bu adımlar işe çalışmıyorsa, [2.](hololens-recovery.md) nesil HoloLens veya HoloLens [(1. nesil) cihazınızı kurtarmayı denemeniz gerekir.](hololens1-recovery.md)

[Listeye geri dön](#list)

## <a name="low-disk-space-error"></a>"Düşük Disk Alanı" hatası

Aşağıdakilerden birini veya daha fazlasını yaparak biraz depolama alanı serbest bırakabilirsiniz:

- Kullanılmayan bazı alanları silin. Sistem   >  **Ayarlar'a**  >  **gidin,** artık ihtiyacınız olmayacak bir alan seçin ve kaldır'ı **seçin.**
- Yerleştiren hologramlardan bazılarını kaldırın.
- Fotoğraflar uygulamasından bazı resimleri ve videoları silin.
- Uygulamanıza bazı uygulamaları HoloLens. Uygulama **Tüm uygulamalar** kaldırmak istediğiniz uygulamaya dokunarak basılı tutun ve Kaldır'ı **seçin.**

[Listeye geri dön](#list)

## <a name="calibration-fails"></a>Hataya neden olan hata

Ayar çoğu kişi için çalışmalı, ancak ayarlamanın başarısız olduğu durumlar vardır.
  
Hatanın olası nedenlerinden bazıları şunlardır:

- Dikkat dağıtıyor ve ayartma hedeflerini takip ediyor değil
- Kirli veya karalamalı cihaz görünür ya da cihaz görünür düzgün bir şekilde konumlanmaz
- Kirli veya karalamalı gözlükler
- Bazı iletişim lensleri ve gözlük türleri (renkli iletişim lensleri, bazı toric iletişim lensleri, IR engelleyici gözlükler, bazı yüksek gözlükler, güneş gözlüğü veya benzerleri)
- Daha belirgin bir şekilde ifade edilir ve bazı kirpik uzantıları
- Cihazın sizin gözlerinizi görmesini engelliyorsa kıllar veya kalın gözlük çerçeveleri
- Dar göz, uzun kirpikler, amblyphya, nystagmus, LASIK veya diğer göz ameliyatları gibi belirli gözfiyatları, göz koşulları veya göz ameliyatı

Başarısız bir sonuç elde edilirse şunları deneyin:

- Cihaz mengenenizi temizleme
- Gözlüklerinizi temizleme
- Cihazınızın gözlerinizi mümkün olduğunca yakınına itme
- Nesneleri mengenenizin dışında (örneğin, kıllar) taşıma
- Odanıza bir ışığı açma veya doğrudan dışarı çıkma

Tüm yönergeleri izlediy ve yine de düzeltme başarısız oluyorsa, komut istemini devre dışı Ayarlar. Ayrıca, Geri Bildirim Merkezi'da geri bildirim [göndererek bize bildirin.](hololens-feedback.md)

Ayrıca görüntü rengi veya parlaklığı [sorunlarını gidermek için ilgili bilgilere bakın.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Göz pozisyonları sistem tarafından hesap HoloLens, IPD ayarı 2 için geçerli değildir. 

[Listeye geri dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Oturum aça bilmiyorum çünkü HoloLens başka biri için ayarlanmış

Cihazı [FlashIng **Mode'a yer ve cihazı** kurtarmak için Gelişmiş Kurtarma Yardımcı'sı](hololens-recovery.md#clean-reflash-the-device) kullanabilirsiniz.

[Listeye geri dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar HoloLens [Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

[Listeye geri dön](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Cihaz Portalı düzgün çalışmıyor

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Geliştirici Modu'Ayarlar etkinleştirdikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

[Listeye geri dön](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator çalışmıyor

HoloLens öykünücüsü hakkında bilgiler geliştirici belgelerimizde bulunur.  HoloLens [öykünücüsünün sorunlarını giderme hakkında daha fazla bilgi edinebilirsiniz.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Uygulamanın tüm uygulamaları Microsoft Store öykünücü ile uyumlu değildir. Örneğin, Young Conker ve Parçalar öykünücüde oynatılamaz.
- Bilgisayar web kamerasını web kamerasını Emulator.
- Canlı Önizleme özelliği Windows Cihaz Portalı öykünücü ile birlikte çalışmıyor. Karma Gerçeklik videolarını ve görüntülerini yine de yakalayabilirsiniz.

[Listeye geri dön](#list)

## <a name="voice-commands-arent-working"></a>Ses komutları çalışmıyor

Ses Cortana yanıt vermiyorsa, komutlar Cortana emin olun. Değişiklik Tüm uygulamalar menü **not**  >    >  **Cortana'ı**  >  **Ayarlar** seçin. Neler söylemeniz hakkında daha fazla bilgi edinmek için [bkz.](hololens-cortana.md)HoloLens.

Bu HoloLens (1. nesil) yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açık. 2 HoloLens de, cihaz kurulumu sırasında hem konuşma tanımayı hem de Cortana açıp açmayabilirsiniz.

HoloLens 2'niz sesinize yanıt vermiyorsa Konuşma tanıma'nın açık olduğundan emin olun. Gizlilik **Konuşmasında**  >    >    >  **Ayarlar'a gidin** ve Konuşma **tanıma'ya gidin.**

[Listeye geri dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

Bu HoloLens emin olmak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik Giriş, ellerinizi takip etmek için size geri bildirim sağlar.  Geri bildirim, farklı sürümlerde farklı HoloLens:

- Genel HoloLens (1. nesil) üzerinde bakış imleci bir noktadan halkaya değişir
- 2 HoloLens de, el bir görüntüye yaklaşacaksa parmak izi imleci görünür ve kayıntılar daha uzak olduğunda bir el imleç görünür

Birçok çevreleyici uygulama, Karma Gerçeklik Giriş'e benzer giriş desenlerini takip eder.  HoloLens [(1. nesil) ve 2. nesil'de](hololens1-basic-usage.md#use-hololens-with-your-hands) el HoloLens [daha fazla bilgi.](hololens2-basic-usage.md#the-hand-tracking-frame)

Maske takıyorsanız, bazı maske türlerinin el izleme ile çalışmay olduğunu unutmayın.  Yaygın olarak karşılaşılan bir örnek olarak, derin kamera tarafından alınmayacak olan siyah renkli silikonlar, renkli renkli ışığın içine alınarak alınma eğilimindedir.  Çalışmanız silikonla ilgili ise mavi veya gri gibi daha açık bir renkle çalışmanızı öneririz.  Bir diğer örnek de, el şeklinizi karartma eğiliminde olan büyük baggy eldivenleridir. En iyi sonuçlar için mümkün olduğunca forma uygun olan eldivenler kullanılması önerilir.

Mengenenizin parmak izleri veya burması varsa, güneşliğinizi güzelce temizlemek için HoloLens mikrofiber temizlemeyi kullanın.

[Listeye geri dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi'a bağlanamıyor

Aşağıdakiler, HoloLens ağınıza bağlanamıyorsanız Wi-Fi denemeniz gerekir:

- Bu Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketi'Ayarlar Ağ **İnterneti**  >  **&amp;**  >  **Wi-Fi 'ı seçin.** Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Ağ yönlendiricinizi Wi-Fi ve ardından [ile HoloLens.](hololens-recovery.md) Bağlanmayı yeniden deneyin.
- Bunlardan hiçbiri çalışmıyorsa, yönlendiricinizin en son üretici yazılımını kullanmaya devam edin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye geri dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazları eşleyemli değil

Bir Bluetooth cihazı [eşleştirmeyle ilgili Bluetooth](hololens-connect-devices.md)aşağıdakini deneyin:

- **Cihazlar Ayarlar a**  >  **gidin** ve Bluetooth emin olun. Varsa, tekrar kapatın ve tekrar açma.
- Cihaz cihazınızın tamamen Bluetooth veya yeni piller olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens.](hololens-recovery.md)

[Listeye geri dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C Mikrofon çalışmıyor

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili değil mikrofonla ilgili HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Sistem   ->  **Ayarlar'de** yerleşik konuşmacıları (Analog Özellik Ses  ->   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor

HoloLens (1. gen) Bluetooth ses profillerini desteklemez. hoparlörler ve kulaklıklar gibi Bluetooth ses cihazları HoloLens ayarlarında kullanılabilir olarak görünebilir, ancak desteklenmez.

HoloLens 2, stereo kayıttan yürütme için Bluetooth A2DP ses profilini destekler. Bluetooth, Bluetooth çevresel bilgisayardan mikrofon yakalamaya izin veren ücretsiz profil HoloLens 2 ' de desteklenmez.

Bluetooth bir cihaz kullanırken sorun yaşıyorsanız, desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar şunları içerir:

- ingilizce-dil QWERTY Bluetooth klavyeler (bunları holographic klavyesini kullandığınız her yerde kullanabilirsiniz).
- Bluetooth fareler.
- [HoloLens click](hololens1-clicker.md).

diğer Bluetooth hıd ve gatt cihazlarını HoloLens ile birlikte eşleştirin. ancak, cihazları gerçekten kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.

[Listeye geri dön](#list)
