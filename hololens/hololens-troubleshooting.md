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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427351"
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

Kullanıcı daha sonra http:// (IP adresi) https:// dosya yükleme ve indirme gibi özellikler çalışmaya devam ediyor.

[Listeye dön](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Insider derlemesi ile yanıp sönen bir cihazda Insider önizleme kaydından sonra mavi ekran

Bu, Bir Insider önizleme derlemesi olan kullanıcıları etkileyen, yeni bir insider önizleme derlemesi ile HoloLens 2'lerini yeniden yazdıran ve insider programından kaydı s olan kullanıcıları etkileyen bir sorundur. Bu bilinen bir **sorundur.**

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

    1. Bağlantı [HoloLens kapatarak el ile 2'nin](hololens-recovery.md) yanıp sönme moduna alın. Ardından Birim'i basılı tutarken Güç düğmesine dokunun.
    
    1. Bağlan ve Gelişmiş Kurtarma Yardımcı'sı'nu açın.
    
    1. 2. HoloLens varsayılan derlemeye yanıp söner.

[Listeye dön](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive resimleri otomatik olarak karşıya yüklemez

OneDrive için HoloLens uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez. Bu bilinen bir **sorundur.**

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama çift oturum açmayı destekler). Otomatik Microsoft hesabı profilinden OneDrive arka plan kameralı zar yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile OneDrive yükleyebilirsiniz. Bunu yapmak için, OneDrive uygulamasında iş veya okul hesabınızla oturum OneDrive olun. düğmesini seçin **+** ve seçeneğini Upload. Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

[Listeye dön](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens yanıt vermiyor veya başlatılmayıyor

HoloLens başlatılamaysa:

- Güç düğmesinin yanındaki LED'ler yanmıyorsa veya yalnızca bir LED kısa süre yanıp sönüyorsa, güç kaynağınızı [HoloLens.](hololens2-charging.md#charging-the-device)
- Güç düğmesine bastığınızda LED'ler yansa ama ekranlarda hiçbir şey görmüyorsanız, [cihazı sabit bir şekilde sıfırlayın.](hololens-recovery.md#hard-reset-procedure)

Bu HoloLens donmuş veya yanıt vermiyorsa:

- Led'HoloLens beşi de kapatana kadar güç düğmesine basarak veya LED'ler yanıt vermiyorsa 15 saniye boyunca kendi güç düğmenizi kapatın. Çalışmanızı başlatmak HoloLens tekrar güç düğmesine basın.

Bu adımlar işe yoksa, HoloLens [2](hololens-recovery.md) cihazınızı veya HoloLens [(1. nesil) cihazınızı kurtarmayı denemeniz gerekir.](hololens1-recovery.md)

[Listeye dön](#list)

## <a name="low-disk-space-error"></a>"Düşük Disk Alanı" hatası

Aşağıdakilerden birini veya daha fazlasını yaparak biraz depolama alanı serbest bırakabilirsiniz:

- Kullanılmayan bazı alanları silin. Sistem   >  **Ayarlar'a**  >  **gidin,** artık ihtiyacınız olmayacak bir alan seçin ve ardından Kaldır'ı **seçin.**
- Yerleştiren hologramlardan bazılarını kaldırın.
- Fotoğraflar uygulamasından bazı resimleri ve videoları silin.
- Uygulamanıza bazı uygulamaları HoloLens. Uygulama **Tüm uygulamalar** kaldırmak istediğiniz uygulamaya dokunarak basılı tutun ve Kaldır'ı **seçin.**

[Listeye dön](#list)

## <a name="calibration-fails"></a>Hataya neden olan hata

Ayar çoğu kişi için çalışmalı, ancak ayarlamanın başarısız olduğu durumlar vardır.
  
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

Tüm yönergeleri izlediy ve ayarlama hala başarısız oluyorsa, komut istemini devre dışı Ayarlar. Ayrıca, Geri Bildirim Merkezi'da geri bildirim [göndererek bize Geri Bildirim Merkezi.](hololens-feedback.md)

Ayrıca görüntü rengi veya parlaklığı [sorunlarını gidermek için ilgili bilgilere bakın.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Göz pozisyonları sistem tarafından hesap HoloLens 2 için IPD ayarı geçerli değildir. 

[Listeye dön](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Oturum aça bilmiyorum çünkü HoloLens başka biri için ayarlanmış

Cihazı [FlashIng **Mode'a yer ve cihazı** kurtarmak için Gelişmiş Kurtarma Yardımcı'sı](hololens-recovery.md#clean-reflash-the-device) kullanabilirsiniz.

[Listeye dön](#list)


## <a name="unity-isnt-working"></a>Unity çalışmıyor

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar HoloLens [Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

[Listeye dön](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Cihaz Portalı düzgün çalışmıyor

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Geliştirici Modu'Ayarlar etkinleştirildikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

[Listeye dön](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator çalışmıyor

HoloLens öykünücüsü hakkında bilgiler geliştirici belgelerimizde bulunur.  HoloLens [öykünücüsünün sorunlarını giderme hakkında daha fazla bilgi edinebilirsiniz.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Uygulamanın tüm uygulamaları Microsoft Store öykünücü ile uyumlu değildir. Örneğin, Young Conker ve Parçalar öykünücüde oynatılamaz.
- Bilgisayar web kamerasını web kamerasını Emulator.
- Canlı Önizleme özelliği Windows Cihaz Portalı öykünücü ile birlikte çalışmıyor. Karma Gerçeklik videolarını ve görüntülerini yine de yakalayabilirsiniz.

[Listeye dön](#list)

## <a name="voice-commands-arent-working"></a>Ses komutları çalışmıyor

Cortana komutlarınıza yanıt vermiyorsa, komutlar Cortana emin olun. Değişiklik Tüm uygulamalar menü **not**  >    >  **Cortana'ı**  >  **Ayarlar** seçin. Neler söylemeniz hakkında daha fazla bilgi edinmek için [bkz.](hololens-cortana.md)HoloLens.

Bu HoloLens (1. nesil) yerleşik konuşma tanıma yapılandırılabilir değildir. Her zaman açık. 2 HoloLens de, cihaz kurulumu sırasında hem konuşma tanımanın hem de Cortana açmanın gerekip gerek olmadığını seçebilirsiniz.

HoloLens 2'niz sesinize yanıt vermiyorsa Konuşma tanıma'nın açık olduğundan emin olun. Gizlilik **Konuşmasında**  >    >    >  **Ayarlar'a gidin** ve Konuşma **tanıma'ya gidin.**

[Listeye dön](#list)

## <a name="hand-input-isnt-working"></a>El girişi çalışmıyor

Bu HoloLens emin olmak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik Giriş, ellerinizi takip etmek için size geri bildirim sağlar.  Geri bildirim, farklı sürümlerde farklı HoloLens:
- Genel HoloLens (1. nesil) üzerinde bakış imleci bir noktadan halkaya değişir
- Bu HoloLens 2'de, el iziniz bir görüntüye yaklaşacaksa parmak izi imleci görünür ve kayıntılar daha uzak olduğunda bir el imleç görünür

Birçok çevreleyici uygulama, Karma Gerçeklik Giriş'e benzer giriş desenlerini takip eder.  HoloLens [(1. nesil) ve](hololens1-basic-usage.md#use-hololens-with-your-hands) [2.](hololens2-basic-usage.md#the-hand-tracking-frame)nesil'de el HoloLens daha fazla bilgi.

Maske takıyorsanız, bazı maske türlerinin el izleme ile çalışmay olduğunu unutmayın.  Yaygın olarak kullanılan bir örnek de, derin kamera tarafından alınmayacak olan siyah renkli silikonlardır.  Çalışmalarınız silikon silikon içeriyorsa mavi veya gri gibi daha açık bir renkle çalışmanızı öneririz.  Bir diğer örnek de, el şeklinizi karartma eğiliminde olan büyük baggy eldivenleridir. En iyi sonuçlar için mümkün olduğunca forma uygun olan eldivenler kullanılması önerilir.

Mengenenizin parmak izleri veya muzlaları varsa, mengenenizi hafifçe temizlemek için HoloLens ile birlikte gelen mikrofiber temizleme izini kullanın.

[Listeye dön](#list)

## <a name="cant-connect-to-wi-fi"></a>Wi-Fi'a bağlanamıyor

Ağ bağlantınıza bağlanamıyorsanız denemeniz gereken bazı HoloLens aşağıdakiler Wi-Fi:

- Yeni bir Wi-Fi emin olun. Kontrol etmek için Başlangıç hareketini kullanın ve ağ **Ayarlar**  >  **&amp; Wi-Fi'ı**  >  **seçin.** Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.
- Yönlendiriciye veya erişim noktasına yaklaşın.
- Ağ yönlendiricinizi Wi-Fi ve ardından [ile HoloLens.](hololens-recovery.md) Yeniden bağlanmayı deneyin.
- Bunlardan hiçbiri çalışmıyorsa, yönlendiricinizin en son üretici yazılımını kullanmaya devam edin. Bu bilgileri üretici web sitesinde bulabilirsiniz.

[Listeye dön](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth cihazları eşleyemli değil

Bir Bluetooth cihazı [eşleştirmeyle ilgili Bluetooth,](hololens-connect-devices.md)şunları deneyin:

- Cihazlar Ayarlar a   >  **gidin** ve Bluetooth emin olun. Varsa, tekrar kapatın ve tekrar açma.
- Cihaz cihazınızın tamamen Bluetooth veya yeni pillere sahip olduğundan emin olun.
- Hala bağlanamıyorsanız, [HoloLens.](hololens-recovery.md)

[Listeye dön](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C Mikrofon çalışmıyor
Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili bir sorundur ve mikrofonla HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Sistem   ->  **Ayarlar'de,** yerleşik konuşmacıları (Analog Özellik Ses  ->   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor

HoloLens (1. nesil) ses profillerini Bluetooth desteklemez. Bluetooth ve mikrofonlu HoloLens kullanılabilir ancak bunlar desteklenmiyor.

HoloLens 2, stereo kayıttan Bluetooth A2DP ses profilini destekler. 2 Bluetooth bir çevre biriminden mikrofon yakalamayı Bluetooth Ücretsiz HoloLens profili desteklenmiyor.

Bluetooth cihazı kullanırken sorun Bluetooth desteklenen bir cihaz olduğundan emin olun. Desteklenen cihazlar aşağıdakileri içerir:

- İngilizce dilinde QWERTY Bluetooth klavyeler (holografik klavyeyi her yerde kullanabilirsiniz).
- Bluetooth fare.
- HoloLens [tıklayın.](hololens1-clicker.md)

DIĞER BLUETOOTH VE GATT cihazlarını kendi cihazlarınız ile HoloLens. Ancak, cihazları gerçekten kullanmak için ilgili yardımcı uygulamaları Microsoft Store uygulamaları yüklemeniz gerekir.

[Listeye dön](#list)
