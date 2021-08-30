---
title: HoloLens Cihaz sorunlarını giderme
description: cihaz sorunlarını ve sorun giderme tekniklerini HoloLens en yaygın çözümlerin güncel kalmasını sağlar.
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
ms.openlocfilehash: 6ac86acf85e8e4fc1b97473732ea358d3d612d12
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190030"
---
# <a name="device-troubleshooting"></a>Cihaz sorunlarını giderme

bu makalede, birkaç yaygın HoloLens sorunu çözme açıklanmaktadır.

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

HoloLens 2 cihazı, **Ayarlar**  ->  **hesapları**  ->  **oturum açma seçenekleri** -> aracılığıyla otomatik olarak oturum açmak üzere yapılandırılabilir ve değeri **hiçbir** şekilde olarak ayarlamak **gerekir** . Bir cihaz, özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştirilirken cihazda oturum açmak için bazı kullanıcılar gerekebilir. Bu bilinen bir **sorundur**.

Bunun gerçekleşebileceğini örnek:

- Windows Holographic 'den bir cihaz güncelleştiriliyor, sürüm 2004 (derleme 19041. xxxx) Windows Holographic, sürüm 21h1 (derleme 20346. xxxx)
- bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004 Windows Holographic, sürüm 20h2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bunun sırasında gerçekleşmemelidir:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerin etrafında çalışın:

- PIN, parola, Iris, Web kimlik doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN kodu hatırlanamaz ve diğer kimlik doğrulama yöntemleri kullanılabilir değilse, bir Kullanıcı [el ile yerleştirme modunu](hololens-recovery.md#manual-procedure)kullanabilir.

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

Bu HoloLens (1. nesil) yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açık. 2 HoloLens de, cihaz kurulumu sırasında hem konuşma tanımayı hem de Cortana açıp açmayabilirsiniz.

HoloLens 2'niz sesinize yanıt vermiyorsa Konuşma tanıma'nın açık olduğundan emin olun. Gizlilik **Konuşmasında**  >    >    >  **Ayarlar'a gidin** ve Konuşma **tanıma'ya gidin.**

[Listeye dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

Bu HoloLens emin olmak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik Giriş, ellerinizi takip etmek için size geri bildirim sağlar.  Geri bildirim, farklı sürümlerde farklı HoloLens:
- Genel HoloLens (1. nesil) üzerinde bakış imleci bir noktadan halkaya değişir
- 2. HoloLens imleç, elimle bir görüntüye yaklaşacaksa bir el imleç görünür ve kayıntılar daha uzak olduğunda bir el imleç görünür

Birçok çevreleyici uygulama, Karma Gerçeklik Giriş'e benzer giriş desenlerini takip eder.  HoloLens [(1. nesil) ve 2. nesil'de](hololens1-basic-usage.md#use-hololens-with-your-hands) el HoloLens [daha fazla bilgi.](hololens2-basic-usage.md#the-hand-tracking-frame)

Maske takıyorsanız, bazı maske türlerinin el izleme ile çalışmay olduğunu unutmayın.  Yaygın olarak kullanılan bir örnek de, derin kamera tarafından alınmayacak olan siyah renkli silikonlardır.  Çalışmalarınız silikon silikon içeriyorsa mavi veya gri gibi daha açık bir renkle çalışmanızı öneririz.  Bir diğer örnek de, el şeklinizi karartma eğiliminde olan büyük baggy eldivenleridir. En iyi sonuçlar için mümkün olduğunca forma uygun olan eldivenler kullanılması önerilir.

Mengenenizin parmak izi veya muzlaları varsa, havayla birlikte gelen mikrofiber temizleme HoloLens ile birlikte kullanın.

[Listeye dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi'a bağlanamıyor

Aşağıdakiler, HoloLens ağınıza bağlanamıyorsanız denemeniz Wi-Fi:

- Bu Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketini kullanın ve ağ **Ayarlar**  >  **&amp; Wi-Fi'ı**  >  **seçin.** Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Wi-Fi yönlendiricinizi yeniden başlatın ve ardından [ile HoloLens.](hololens-recovery.md) Yeniden bağlanmayı deneyin.
- Bunlardan hiçbiri çalışmıyorsa, yönlendiricinizin en son üretici yazılımını kullanmaya devam edin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazlar eşlenmli değil

Bir Bluetooth cihazı [eşleştirmeyle ilgili sorun](hololens-connect-devices.md)Bluetooth aşağıdakini deneyin:

- Cihazlar Ayarlar a   >  **gidin** ve Bluetooth emin olun. Varsa, tekrar kapatın ve tekrar açma.
- Cihaz cihazınızın tamamen Bluetooth veya yeni pillere sahip olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens.](hololens-recovery.md)

[Listeye dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C Mikrofon çalışmıyor
Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili değil mikrofonla ilgili HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Sistem   ->  **Ayarlar'de** yerleşik konuşmacıları (Analog Özellik Ses  ->   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor

HoloLens (1. nesil) ses profillerinin Bluetooth desteklemez. Bluetooth ve mikrofonlu HoloLens gibi görünebilir, ancak bunlar desteklenmiyor.

HoloLens 2, stereo Bluetooth için A2DP ses profilini destekler. 2 Bluetooth bir çevre biriminden mikrofon yakalamayı Bluetooth Ücretsiz HoloLens profili desteklenmiyor.

Bluetooth cihazı kullanırken sorun Bluetooth desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar aşağıdakileri içerir:

- İngilizce dilinde QWERTY Bluetooth klavyeleri kullanır (bunları holografik klavyeyi her yerde kullanabilirsiniz).
- Bluetooth fareler.
- HoloLens [tıklayın.](hololens1-clicker.md)

DIĞER cihazlarınızı BLUETOOTH GATT cihazlarıyla kendi cihazlarınızı HoloLens. Ancak, cihazları gerçekten kullanmak için ilgili yardımcı uygulamaları Microsoft Store uygulamaları yüklemeniz gerekir.

[Listeye dön](#list)
