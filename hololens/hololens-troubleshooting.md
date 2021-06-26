---
title: HoloLens cihaz sorunlarını giderme
description: HoloLens cihaz sorunları ve sorun giderme teknikleri için en yaygın çözümlerin güncel kalmasını sağlar.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: sorunlar, hata, sorun giderme, çözüm, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924630"
---
# <a name="device-troubleshooting"></a>Cihaz sorunlarını giderme

Bu makalede, birkaç yaygın HoloLens sorununa nasıl çözüm yapılacağı açıklanır.

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun. Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.

<a id="list"></a>

**Bilinen Sorunlar**
- [Uzaktan Yardım Videosu 20 dakikadan sonra donuyor](#remote-assist-video-freezes-after-20-minutes)
- [Oturum açma için otomatik oturum açma sorulur](#auto-login-asks-for-log-in)
- [Microsoft Edge başlatılamadı](#microsoft-edge-fails-to-launch)
- [Klavye özel karakterlere geçmez](#keyboard-doesnt-switch-to-special-characters)
- [Kilitli dosyaların indirilmesi hata göstermiyor](#downloading-locked-files-doesnt-error)
- [Cihaz portalı dosya yükleme/indirme zaman aşımı](#device-portal-file-uploaddownload-times-out)
- [Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive resimleri otomatik olarak karşıya yüklememez](#onedrive-doesnt-automatically-upload-pictures)

**Genel**
- [HoloLens yanıt vermiyor veya başlamıyor](#hololens-is-unresponsive-or-wont-start)
- ["Yetersiz disk alanı" hatası](#low-disk-space-error)
- [Ayarlama başarısız](#calibration-fails)
- [HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity çalışmıyor](#unity-isnt-working)
- [Windows cihaz portalı düzgün çalışmıyor](#windows-device-portal-isnt-working-correctly)
- [HoloLens öykünücüsü çalışmıyor](#the-hololens-emulator-isnt-working)

**Giriş**
- [Sesli komutlar çalışmıyor](#voice-commands-arent-working)
- [El girişi çalışmıyor](#hand-input-isnt-working)

**Bağlantı**
- [Wi-Fi ' a bağlanılamıyor](#cant-connect-to-wi-fi)

**Dış cihazlar** 
- [Bluetooth cihazları eşleştirme yok](#bluetooth-devices-arent-pairing)
- [USB-C mikrofonu çalışmıyor](#usb-c-microphone-isnt-working)
- [Ayarlarda kullanılabilir olarak listelenen cihazlar çalışmıyor](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Uzaktan Yardım Videosu 20 dakikadan sonra donuyor

> [!NOTE]
> Bu bilinen sorunun önem derecesine bağlı olarak, şu anda Windows holographic, sürüm 21H1 kullanılabilirliğini duraklattık. Cihazlarınızı 21 H1 ' e güncelleştirmek istiyorsanız lütfen [sayfanın en üstündeki sürüm Notlarımızda bulunan yönergelere bakın.](hololens-release-notes.md)

[Windows holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)' in en son sürümünde, uzaktan yardım 'ın bazı kullanıcıları 20 dakikadan fazla çağrı sırasında video donduruyor demektir. Bu bilinen bir **sorundur**.

### <a name="workarounds"></a>Geçici Çözümler

#### <a name="restart-in-between-calls"></a>Çağrılar arasında yeniden Başlat

Çağrılarınızın uzunluğu 20 dakikadan fazla olursa ve bu sorunu yaşıyorsanız cihazınızı yeniden başlatmayı deneyin. Cihazınızı uzaktan yardım çağrıları arasında yeniden başlatmak cihazınızı yenileyip iyi bir duruma geri yerleştirecek.

Windows holographic 'de bir cihazı hızlı bir şekilde yeniden başlatmak için [, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) Başlat menüsünü açın ve Kullanıcı simgesini seçin, sonra **Yeniden Başlat**' ı seçin.

#### <a name="revert-to-an-older-build"></a>Eski bir yapıya dön

Bazı müşteriler daha önceki bir işletim sistemi sürümüne geri dönüldükten sonra bu sorunla karşılaşmamıştır. Cihazlarınızın bu sorunla karşılaşdığını buldıysanız, şu adımları deneyin:


Geçici çözümler:

- İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir. İş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması, çift oturum açma desteği sağlar). OneDrive 'daki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.

- Fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz. Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun. Düğmeyi seçip **+** **karşıya yükle**' yi seçin. **Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun. Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.


1. [Windows holographic, sürüm 20H2 – Mayıs 2021 güncelleştirmesi için derlemeyi indirin](https://aka.ms/hololens2download/10.0.19041.1146)
1. [Önceki bir işletim sistemi sürümüne geri dönme yönergelerini](hololens-update-hololens.md#go-back-to-a-previous-version) izleyin
1. [Cihazdaki işletim sistemi güncelleştirmelerini el ile duraklatın](hololens-updates.md#pause-updates-via-device) ya da birçok CIHAZ için [MDM aracılığıyla erteleme](hololens-updates.md#configure-an-update-deferral-policy)kullanın.

[Listeye geri dön](#list)

## <a name="auto-login-asks-for-log-in"></a>Oturum açma için otomatik oturum açma sorulur

Bir HoloLens 2 cihazı, **Ayarlar**  ->  **hesabı**  ->  **oturum açma seçenekleri** -> aracılığıyla otomatik olarak oturum açmak üzere yapılandırılabilir ve değer **gerekli** ayarı **hiçbir** şekilde ayarlanamaz. Bir cihaz, özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştirilirken cihazda oturum açmak için bazı kullanıcılar gerekebilir. Bu bilinen bir **sorundur**.

Bunun gerçekleşebileceğini örnek:

- Windows holographic, sürüm 2004 ' den (derleme 19041. xxxx) Windows holographic, sürüm 21H1 (derleme 20346. xxxx) ile cihaz güncelleştirme
- Bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örn. Windows holographic, sürüm 2004, Windows holographic, sürüm 20H2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bunun sırasında gerçekleşmemelidir:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerin etrafında çalışın:

- PIN, parola, Iris, Web kimlik doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN kodu hatırlanamaz ve diğer kimlik doğrulama yöntemleri kullanılabilir değilse, bir Kullanıcı [el ile yerleştirme modunu](hololens-recovery.md#manual-procedure)kullanabilir.

[Listeye geri dön](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatılamadı

> [!NOTE]
> Bu sorun başlangıçta Microsoft Edge 'in sevkiyat sürümü göz önünde bulundurularak oluşturulmuştur. Bu sorun [Yeni Microsoft Edge](hololens-new-edge.md)'de çözülebilir. Aksi takdirde, lütfen geri bildirimde bulunun.

Birkaç müşteri, Microsoft Edge 'in başlatamayacağı bir sorun raporladı. Bu müşteriler için, sorun yeniden başlatma ile devam etmez ve Windows veya uygulama güncelleştirmeleriyle çözümlenmez. Bu sorunla karşılaşıyorsanız ve [Windows 'un güncel olduğunu](hololens-updates.md#manually-check-for-updates)onayladıysanız, lütfen aşağıdaki kategori ve alt kategori Ile [geri bildirim merkezi](hololens-feedback.md) uygulamasından bir hata bildirin: Windows Update indirme, yükleme ve yapılandırma > yükleme ve güncelleştirme.

Sorunun şu ana kadar köke neden olmadığı bilinen bir geçici çözüm yoktur. Geri Bildirim Hub 'ı aracılığıyla bir hata dosyalama araştırmasına yardımcı olacak! Bu bilinen bir **sorundur**.

[Listeye geri dön](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klavye özel karakterlere geçmez

Kullanıcı bir iş veya okul hesabı seçtiği ve parolasını girerken, OOBE sırasında, &123 düğmesine dokunarak klavye üzerindeki özel karakterlere geçiş yapmaya çalışırken, özel karakterlere değişmediğinden, OOBE sırasında bir sorun vardır. Bu bilinen bir **sorundur**.

Work-arounds:
-   Klavyeyi kapatın ve metin alanına dokunarak yeniden açın.
-   Parolanızı yanlış girin. Klavye bir dahaki sefer çalışırken beklendiği gibi çalışır.
- Web kimlik doğrulaması, klavyeyi kapatın ve **başka bir cihazdan oturum aç**' ı seçin.
-   Yalnızca sayı girilirse, bir kullanıcı genişletilmiş bir menü açmak için belirli tuşları basılı tutabilir.
-   USB klavye kullanma.

Bu, şunları etkilemez:
- Kişisel hesap kullanmayı seçen kullanıcılar.

[Listeye geri dön](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Kilitli dosyaların indirilmesi hatası yok
> ! Bu, Windows Insider Build, sürüm 20348,1403 ' de düzeltilen **bilinen bir sorundur** .


Önceki Windows holographic Derlemeleriyle, kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olur. Windows holographic, sürüm 21H1 güncelleştirmesinde, kilitli bir dosyayı indirmeye çalışmak, hiçbir şey görünmediğine neden olmaz; dosya indirilmez ve hata vermez. 

[Listeye geri dön](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Cihaz portalı dosya yükleme/indirme zaman aşımı
> ! Bu, Windows Insider Build, sürüm 20348,1403 ' de düzeltilen **bilinen bir sorundur** . Geçici çözümün bir parçası olarak SSL bağlantısını devre dışı bırakırsanız, yeniden etkinleştirmenizi kesinlikle öneririz.


Bazı müşteriler, dosyaları karşıya yüklemeye veya indirmeye çalışırken, işlem askıda kalabilir ve sonra zaman aşımına uğrar veya hiç tamamlanmayabilir. Bu, '[dosya kilitli ' bilinen sorundan](#downloading-locked-files-doesnt-error) ayrıdır. Bu, Windows holographic, sürüm 2004, 20H2 ve 21 H1 Pazar sürümlerini etkiler. Sorun, cihaz portalının belirli isteklerin işlenmesinde oluşan bir hataya yol açtı ve varsayılan değer olan https kullanılırken en tutarlı şekilde isabet ediyor. 

### <a name="workaround"></a>Geçici çözüm

Wi-Fi ve UsbNcm 'ye eşit olarak uygulanan bu geçici çözüm, "SSL bağlantısı" altında "gerekli" seçeneğinin devre dışı bırakılması. Bunu yapmak için cihaz portalı, **sistem**' e gidin ve **Tercihler** sayfasını seçin. **Cihaz güvenliği** bölümünde, **SSL bağlantısı**' nı bulun ve **gerekli**' ı devre dışı bırakmak için işaretini kaldırın.

Daha sonra Kullanıcı, https://(IP adresi) değil http://, dosya yükleme ve indirme gibi özellikler için de çalışır.

[Listeye geri dön](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran

Bu, bir Insider Preview derlemesinde bulunan kullanıcıları etkiler, HoloLens 2 ' yi yeni bir Insider Preview derlemesi ile ve ardından Insider programından kaydını kaldırmış olan kullanıcıları etkiler. Bu bilinen bir **sorundur**.

Bu, şunları etkilemez:
- Windows Insider 'da kayıtlı olmayan kullanıcılar 
- Insiders
    - Insider derlemeleri sürüm 18362. x olduğundan bir cihaz kaydedildiyse
    - Insider 'a imzalanmış bir 19041. x derlemesini düzder ve Insider programı 'nda kayıtlı kal

Geçici iş: 
- Sorunu önleyin 
    - Insider olmayan bir derlemeyi yakıp söndür. Normal aylık güncelleştirmelerden biri.
    - Insider Preview 'da kalın
- Cihazı kırın

    1. Bağlama sırasında, Hololens 2 ' ye tamamen kapatarak el ile [yanıp sönme moduna](hololens-recovery.md) koyun. Ardından, hacmi tutarken, güç düğmesine dokunun.
    
    1. BILGISAYARA bağlanın ve Gelişmiş kurtarma Yardımcısı ' nı açın.
    
    1. HoloLens 2 ' ye varsayılan yapıya Flash.

[Listeye geri dön](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive resimleri otomatik olarak karşıya yüklememez

HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez. Bu bilinen bir **sorundur**.

Geçici çözümler:

- İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir. İş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması, çift oturum açma desteği sağlar). OneDrive 'daki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.

- Fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz. Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun. Düğmeyi seçip **+** **karşıya yükle**' yi seçin. **Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun. Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.

[Listeye geri dön](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens yanıt vermiyor veya başlamıyor

HoloLens 'niz başlamazsa:

- Güç düğmesinin yanındaki LED 'ler soluk veya yalnızca bir tane daha yanıp sönüyor değilse, [HoloLens 'nizi ücretlemeniz gerekebilir.](hololens2-charging.md#charging-the-device)
- Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey göremiyorsanız, [cihazın kalıcı olarak sıfırlanması](hololens-recovery.md#hard-reset-procedure)gerekir.

HoloLens 'niz dondurulmuş veya yanıt vermiyorsa:

- Bir LED 'in beş bir kısmını devre dışı bırakır veya LED 'ler yanıt vermiyorsa 15 saniye boyunca güç düğmesine basarak HoloLens 'nizi kapatın. HoloLens 'nizi başlatmak için, Power düğmesine yeniden basın.

Bu adımlar çalışmazsa, [HoloLens 2 cihazınızı](hololens-recovery.md) veya [HoloLens (1. gen) cihazınızı](hololens1-recovery.md) kurtarmayı deneyebilirsiniz.

[Listeye geri dön](#list)

## <a name="low-disk-space-error"></a>"Yetersiz disk alanı" hatası

Aşağıdakilerden birini veya birkaçını yaparak depolama alanını boşaltmanız gerekir:

- Kullanılmayan bazı boşlukları silin. **Ayarlar**  >  **sistem**  >  **alanları**' na gidin, artık ihtiyacınız olmayan bir alan seçin ve ardından **Kaldır**' ı seçin.
- Yerleştirdiğiniz hologramlar bölümünü kaldırın.
- Fotoğraflar uygulamasındaki bazı resimleri ve videoları silin.
- HoloLens 'ınızdan bazı uygulamaları kaldırın. **Tüm uygulamalar** listesinde, kaldırmak istediğiniz uygulamayı ve ardından **Kaldır**' ı seçin.

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

Tüm yönergeleri izlediyseniz ve ayarlama hala başarısız olursa, Ayarlar ' da ayarlama isteğini devre dışı bırakabilirsiniz. Ayrıca, [geri bildirim merkezinde](hololens-feedback.md)geri bildirimde bulunarak bize bilgi verin.

Ayrıca, [görüntü renk veya parlaklık sorun giderme](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) için ilgili bilgiler bölümüne bakın.

Gözle ayar konumları sistem tarafından hesaplandığından, ıPD ayarı HoloLens 2 için geçerli değildir. 

[Listeye geri dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor

Cihazı daha [ **yanıp sönen moda** yerleştirebilir ve Gelişmiş kurtarma Yardımcısı 'nı kullanarak](hololens-recovery.md#clean-reflash-the-device) cihazı kurtarabilirsiniz.

[Listeye geri dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar, [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.

[Listeye geri dön](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows cihaz portalı düzgün çalışmıyor

- Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.

- Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir. Bunların kullanılması hiçbir etkiye sahip olmayacaktır. Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.

- Ayarlar bölümünde Geliştirici modunu etkinleştirdikten sonra, cihaz Portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.

[Listeye geri dön](#list)

## <a name="emulator"></a>Öykünücü
### <a name="the-hololens-emulator-isnt-working"></a>HoloLens öykünücüsü çalışmıyor

HoloLens öykünücüsü hakkındaki bilgiler geliştirici belgelerimizde bulunur.  [HoloLens öykünücüsünün sorunlarını giderme](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)hakkında daha fazla bilgi edinin.


- Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir. Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.
- Öykünücüsünde PC web kamerasını kullanamazsınız.
- Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz. Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.

[Listeye geri dön](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>HoloLens 2 öykünücüsünü yazmak için klavyeyi bulamıyorum veya kullanmıyorum

*Çok yakında*

[Listeye geri dön](#list)

## <a name="voice-commands-arent-working"></a>Sesli komutlar çalışmıyor

Cortana, sesli komutlarınıza yanıt vermiyorsa Cortana 'Nın açık olduğundan emin olun. Tüm uygulamalar listesinde,   >    >  değişiklikler yapmak için Cortana menü **Not defteri**  >  **ayarları** ' nı seçin. Ne söyleyebilirim hakkında daha fazla bilgi edinmek için bkz. [HoloLens ile sesinizi kullanma](hololens-cortana.md).

HoloLens 'te (1. Genel), yerleşik konuşma tanıma özelliği yapılandırılamaz. Her zaman açıktır. HoloLens 2 ' de, cihaz kurulumu sırasında hem konuşma tanıma hem de Cortana 'yı açıp kullanmayacağınızı seçebilirsiniz.

HoloLens 2 sesinize yanıt vermiyorsa, konuşma tanımanın açık olduğundan emin olun.   >  **Ayarlar**  >  **Gizlilik**  >  **konuşmayı** Başlat ' a gidin ve **konuşma tanımayı** açın.

[Listeye geri dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

HoloLens 'in ellerinizi görmesini sağlamak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik ana sayfası, kollarınızın ne zaman izleneceğini bilmenizi sağlayan geri bildirim sağlar.  Geri bildirim, HoloLens 'in farklı sürümlerinde farklıdır:
- HoloLens 'te (1. Genel), Gaze imleci bir noktadan halkaya dönüşür
- HoloLens 2 ' de, elinizdeki bir kurşun kalem 'e yakın olduğunda parmak izi imleci görünür ve SLA 'lar daha fazla olduğunda bir el Ray görünür

Birçok modern uygulama, karma gerçeklik ana 'ya benzer giriş desenlerine uyar.  HoloLens 'te el girişi kullanma hakkında daha fazla bilgi edinin [(1. Genel)](hololens1-basic-usage.md#use-hololens-with-your-hands) ve [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Birlikte çalışırken, bazı araç türlerinin el ile izleme ile çalışmadığına göz önünde bulundurun.  Yaygın olarak kullanılan bir örnek, artışlarını devralarak kızılötesi ışınına eğilen ve derinlik kamerası tarafından alınmayan siyah bir örnektir.  Çalışmanız lastik içeriyorsa, mavi veya gri gibi daha açık bir renk denemeyi öneririz.  Diğer bir örnek de büyük ölçekli bir örnektir ve bu, elinizin şeklinin gizlenmesi anlamına gelir. En iyi sonuçlar için mümkün olduğunca form sığdırma olarak bulunan gloonları kullanmanızı öneririz.

Vizörü ' in parmak izleri veya kullanım alanları varsa, vizörü 'nizi temizlemek için HoloLens ile birlikte gelen mikro fiber Temizleme havsını kullanın.

[Listeye geri dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi bağlanılamıyor

HoloLens 'nizi bir Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:

- Wi-Fi açık olduğundan emin olun. Denetlemek için başlangıç hareketini kullanın, ardından **Ayarlar**  >  **Ağ &amp; Internet**  >  **Wi-Fi**' ı seçin. Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Wi-Fi yönlendiricinizi yeniden başlatın ve [HoloLens 'i yeniden başlatın](hololens-recovery.md). Yeniden bağlanmayı deneyin.
- Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye geri dön](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazları eşleştirme yok

[Bluetooth cihazını eşleştirmenize](hololens-connect-devices.md)sorun yaşıyorsanız aşağıdakileri deneyin:

- **Ayarlar**  >  **cihazlar**' a gidin ve Bluetooth 'un açık olduğundan emin olun. Varsa, devre dışı bırakın ve tekrar açın.
- Bluetooth cihazınızın tam olarak ücretlendirildiğini veya yeni pillere sahip olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens 'i yeniden başlatın](hololens-recovery.md).

[Listeye geri dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C mikrofonu çalışmıyor
Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. Bu mikrofonlardan birini HoloLens 'e takarken ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde yerleşik hoparlörleri **(analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. Mikrofon kaldırılıp daha sonra yeniden bağlansa, HoloLens bu ayarı unutmalıdır.

![USB-C mikrofonları sorunlarını giderme](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Ayarlarda kullanılabilir olarak listelenen cihazlar çalışmıyor

HoloLens (1. gen) Bluetooth ses profillerini desteklemez. Hoparlörler ve kulaklıklar gibi Bluetooth ses cihazları, HoloLens ayarlarında kullanılabilir olarak görünebilir, ancak desteklenmez.

HoloLens 2, stereo kayıttan yürütme için Bluetooth A2DP ses profilini destekler. Bluetooth çevresel bir bilgisayardan mikrofon yakalamaya izin veren Bluetooth BT ücretsiz profili, HoloLens 2 ' de desteklenmez.

Bluetooth cihazını kullanırken sorun yaşıyorsanız, desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar şunları içerir:

- İngilizce-dil QWERTY Bluetooth klavyeleri (bunları, Holographic Klavyesini kullandığınız her yerde kullanabilirsiniz).
- Bluetooth fareler.
- [HoloLens](hololens1-clicker.md).

Diğer Bluetooth HID ve GATT cihazlarını, HoloLens 'larınızla birlikte eşleştirin. Ancak, cihazları gerçekten kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.

[Listeye geri dön](#list)
