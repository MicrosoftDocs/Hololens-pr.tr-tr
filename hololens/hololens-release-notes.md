---
title: HoloLens 2 sürüm notları
description: Her yeni HoloLens 2 sürümündeki tüm güncelleştirmelerle güncel kalın.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 16aec0e60fde40f0a2bffefa871a7a3774b1eb2e
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924545"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarınızla üretken bir deneyiminizin olduğundan emin olmak için özellik, hata ve güvenlik güncelleştirmelerini serbest bırakmaya devam ediyoruz. Bu sayfada, her ay HoloLens yenilikleri hakkında bilgi alabilirsiniz. En son HoloLens 2 güncelleştirmesini almak için güncelleştirmeleri denetleyebilir ve [Gelişmiş kurtarma Yardımcısı aracılığıyla cihazınızı Flash](hololens-recovery.md#clean-reflash-the-device) [ile el Ile güncelleştirebilir](hololens-update-hololens.md#check-for-updates-and-manually-update) veya tam Flash Güncelleştirmesi (FFU) alabilirsiniz. [İndirme](https://aka.ms/hololens2download) güncel tutulur ve en son genel kullanıma sunulan derlemeyi sağlar.

> [!NOTE]
> Son Windows 11 duyurusu Windows 'un bılgısayar sürümüne odaklanmıştır. Kısa süre önce 2021 Mayıs 'ta HoloLens 2 ' de [önemli bir işletim sistemi güncelleştirmesi](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) başlattık ve bu sonbahar müşteri geri bildirimlerine bağlı olarak yaklaşan bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21 H1 deremizdeki, uzaktan yardım kullanıcılarını etkileyen bilinen bir sorun](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)nedeniyle, şu anda Windows holographic, sürüm 21H1 güncelleştirmelerinin sunumunu durakladık. Ayrıca, varsayılan Gelişmiş kurtarma yardımcı derlemesini, en son 20H2 sürümü olan [Windows holographic, sürüm 20H2 – haziran 2021 güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)olacak şekilde değiştirdik.
>
> Bu sorunun etkisini azaltmak için 21H1 kullanılabilirliğini azalttık, ancak bazı müşterilerin 21 H1 ' e güncelleştirmek için hala sorun olabileceğini anladık. 21 H1 olarak güncelleştirmek isteyen müşteriler için iki farklı yol mevcuttur:
>
> - [Cihazınızı Windows Insider 'lar olarak kaydedin](hololens-insider.md#start-receiving-insider-builds) ve **Beta kanalını** seçin. Bu, bu cihazların 21 H1 ' e güncelleştirilmesini sağlar ve güvenilir yapılara sahip olur.
> - Bilgisayarınızda [en son FFU 'Yi indirin](https://aka.ms/hololens2download) ve ardından [Gelişmiş kurtarma Yardımcısı aracılığıyla cihazınızı Flash](hololens-recovery.md#clean-reflash-the-device)yapın.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows holographic, sürüm 21H1-Haziran 2021 güncelleştirmesi
- Derleme 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive iş veya okul kamerayı alma yüklemesi

HoloLens 2 Ayarlar uygulamasına yeni bir özellik ekledik. Bu, müşterilerin, karma gerçeklik fotoğraflarını ve videoları cihazın resimlerini > kamera rulosu klasöründen ilgili OneDrive iş veya okul klasörüne otomatik olarak yüklemesine olanak tanır. Bu özellik, bir müşterinin kişisel Microsoft hesabı (iş veya okul hesabına değil) yalnızca otomatik kamera alma 'yı destekleyen HoloLens 2 üzerinde [OneDrive uygulamasında bir özellik boşluğu](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) ele alır.

**Nasıl çalışır?**

- "Kamerayı karşıya yükleme" özelliğini etkinleştirmek için **> karma gerçeklik kamerasını > ayarları** ziyaret edin.
- Bu özelliği **Açık** konuma ayarlayarak, cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları, OneDrive iş veya okul hesabınızın kamera rulosu klasörüne yüklenmek üzere otomatik olarak > kuyruğa alınır.
    >[!NOTE]
    >Bu özelliği etkinleştirmeden önce yakalanan fotoğraflar ve Videolar karşıya *yüklenmek üzere* sıraya alınır ve yine de el ile karşıya yüklenmelidir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yükleme bekleyen dosya sayısını görüntüler (veya tüm bekleyen dosyalar karşıya yüklendiğinde "OneDrive güncel" sayfasını okur).
- Bant genişliği hakkında endişeleriniz varsa veya herhangi bir nedenle "duraklatma" yapmak istiyorsanız, özelliği **kapalı** konuma geçirebilirsiniz. Özelliği geçici olarak devre dışı bırakmak, kamera rulosu klasörüne yeni dosyalar eklerken karşıya yükleme sırasının artmaya devam etmesini sağlar, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmeyecektir.
- En yeni dosyalar önce karşıya yüklenir (son, ilk çıkar).
- OneDrive hesabınızda sorunlar varsa (örneğin, Parolanız değiştirildikten sonra) ayarlar sayfasında **Şimdi bir düzelme** düğmesi görünür.
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklenmesi daha uzun sürdüğüne (özellikle karşıya yükleme bant genişliğiniz kısıtlı ise) göz atalım. Büyük bir dosya karşıya yüklenirken "duraklatabilir" veya karşıya yüklemeyi kapatırsanız kısmi karşıya yükleme korunur. Karşıya yükleme işlemi birkaç saat içinde "duraklatıldı" veya devre dışı bırakıldığında, karşıya yükleme kaldığınız yerden devam eder. Ancak karşıya yükleme işlemi birkaç saat sonra yeniden etkinleştirildiyse, büyük dosyanın karşıya yüklemesi baştan başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayarın geçerli bant genişliği kullanımına bağlı olarak yerleşik azaltma yoktur. Başka bir senaryo için bant genişliğini en iyi duruma getirmeniz gerekiyorsa, ayarı el ile kapatın. Karşıya yükleme duraklatılır, ancak özellik yeni eklenen dosyaları kamera rulonuza izlemeye devam edecektir. Devam etmek için hazırsanız karşıya yüklemeyi yeniden etkinleştirin.
- Bu özelliğin cihazdaki her kullanıcı hesabı için etkinleştirilmesi gerekir ve yalnızca cihazda oturum açmış olan kullanıcı için dosyaları etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasında gerçek zamanlı karşıya yükleme sayısını izlerken fotoğraf veya video çekiyorsunuz, geçerli dosyanın karşıya yüklenmesi tamamlanana kadar bekleyen dosya sayısının değişebileceğini unutmayın.
- Cihazınız uyku modunda kalırsa veya kapatılmışsa karşıya yükleme duraklatılır. Bekleyen karşıya yüklemelerinizin tamamlanmasını sağlamak için, ayarlar sayfası "OneDrive güncel değil" olarak okunana kadar aygıtı etkin bir şekilde kullanın veya **güç & uyku** ayarlarınızı yapın.
### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri, HoloLens 2 ' de artık desteklenmektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- Allowdevicenameındiagnokdata
- Feedbackhubalwayssavediagnosticsyerel

Hem System\allowtelemetri hem de System\ConfigureTelemetryOptInSettingsUx, Ayarlar uygulamasındaki telemetri ve davranışta denetim sağlamak için birlikte kullanılmalıdır.

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Renk ayarlama ile büyük video bozukluğunu düzeltir.
- Güç menüsünde metnin kesilmiş olabileceği bir sorunu giderir.
- RequirePrivateStoreOnly ilkesi için desteği sunar.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows holographic, sürüm 20H2 – Haziran 2021 güncelleştirmesi
- Derleme 19041,1154

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri, HoloLens 2 ' de artık desteklenmektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- Allowdevicenameındiagnokdata
- Feedbackhubalwayssavediagnosticsyerel

Hem System\allowtelemetri hem de System\ConfigureTelemetryOptInSettingsUx, Ayarlar uygulamasındaki telemetri ve davranışta denetim sağlamak için birlikte kullanılmalıdır.

En son derleme, Windows holographic, sürüm 21H1 sürümünü denemenizi öneririz.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows holographic, sürüm 1903-Haziran 2021 güncelleştirme
- Derleme 18362,1116

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son derleme, Windows holographic, sürüm 21H1 sürümünü denemenizi öneririz.

>[!IMPORTANT]
> Bu derleme artık servise alınmaz.

## <a name="windows-holographic-version-21h1"></a>Windows holographic, sürüm 21H1
- Derleme 20346,1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihazdaki herkes tarafından kullanılabilen özellikler ve BT yöneticileri tarafından yapılandırılabilen yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda, her bir hedef kitle ile ilgili özellikler belirtilir. BT yöneticisiyseniz lütfen [BT yöneticimize göz atın-güncelleştirme denetim listesini](#it-admin---update-checklist)inceleyin.
>[!IMPORTANT]
>Bu yapıya güncelleştirmek için, HoloLens 2 cihazlarının Şubat 2021 Güncelleştirmesi (derleme 19041,1136) veya daha yeni bir sürümü çalıştırıyor olması gerekir. Bu özellik güncelleştirmesini görmüyorsanız, lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>Günümüzde, Microsoft HoloLens 2 aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmelerini) destekler:
>- Windows holographic, sürüm 20H2 (derleme 19041.1128 +)
>- Windows holographic, sürüm 2004 (derleme 19041.1103 +)
>- Windows holographic, sürüm 1903 (derleme 18362 +) 
>
> Windows holographic sürüm 21H1 ' in kullanıma sunulmasıyla birlikte, **Windows holographic sürüm 1903 için aylık bakım güncelleştirmelerine devam ediyoruz**. Bu, daha yeni sürümlere odaklanmamızı ve değerli geliştirmeler sunmaya devam etmenizi sağlar. 


| Özellik adı                                              | Kısa açıklama                                                                      | Hedef kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | Yeni, Kmuum tabanlı Microsoft Edge, HoloLens 2 ' de kullanıma sunulmuştur. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyicisi](#webxr-and-360-viewer) | Modern Web deneyimleri ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
[Yeni ayarlar uygulaması](#new-settings-app) | Eski ayarlar uygulaması, yeni özellikler ve ayarlarla güncelleştirilmiş bir sürüm ile değiştiriliyor. | Son Kullanıcı |
[Ekran renk ayarı](#display-color-calibration) | HoloLens 2 ekran için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama birimi denetimi başına](#per-app-volume-control) | Uygulama düzeyindeki birimi sistem biriminden bağımsız olarak denetleme. | Son Kullanıcı |
[Web uygulamalarını yükleme](#install-web-apps) | Yeni Microsoft Edge tarayıcısıyla HoloLens 2 Microsoft Office gibi web Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekme](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde HoloLens cihazı yeniden başlatın ve kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve /veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında otomatik oturum açma özelliğinin Bilgi Noktası modları için kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni Ayarlar ve Edge uygulamaları için AUMID'ler. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlat menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
[Sayfa Ayarları Görünürlüğü için Yeni AyarlarURI'leri](#new-settings-uris-for-page-settings-visibility) | Ayarlar/PageVisibilityList ilkesi için 20'den fazla yeni SettingsURIs. | BT Yöneticisi |
[Geri Dönüş Tanılamasını Yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Ayarlar Uygulamasında Geri Dönüş Tanılama Davranışını Ayarlama. | BT Yöneticisi |
[Yakındaki cihazlarla paylaşım](#share-things-with-nearby-devices) | HoloLens'den bir bilgisayara dosya veya URL'leri paylaşma. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | Işletim sistemi güncelleştirmeleri için Ayarlar'da yeni sorun giderici. | BT Yöneticisi |
[Teslim İyileştirme Önizleme](#delivery-optimization-preview) | Birden çok HoloLens cihazına yapılan indirmeler için bant genişliği tüketimini azaltma. | BT Yöneticisi |

İlgili sürüm notlarına göz at:

- [HoloLens Öykünücüsü arşivini ziyaret edin](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Kılavuzları](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge logosunu yeni Microsoft Edge animasyonu](images/new-edge.gif)

Yeni Microsoft Edge, müşteriler için daha iyi uyumluluk ve web geliştiricileri için web'in daha az parçalanması oluşturmak için [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) açık kaynak projesini benimser.

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde artık Microsoft Edge eski [sürümler'in](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) yerini otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni uygulamayı Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil bir kısma simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski sanal Microsoft Edge. Yeni Microsoft Edge başlattıktan sonra eski verileri kullanmaya devam eder Microsoft Edge, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, DAHA önce eski sanal ağlarda kullanılabilenden çok daha geniş bir HoloLens 2 tarayıcı Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Kurumsal belgeleri](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge ekibimiz, her yeni ilkenin HoloLens 2'de çalıştığını garantileyememiyor. Ancak, daha önce HoloLens 2'de Microsoft Edge eski Microsoft Edge ilkenin eşdeğerini test ettik ve onayladık. HoloLens [2 Microsoft Edge'in eski sürümü Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski tarayıcı Microsoft Edge eşdeğerini bulmak için bkz. Microsoft Edge ilke eşlemesi.
>
> HoloLens 2 Microsoft Edge en *az* iki yeni ilke vardır:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de yeni Microsoft Edge beklenilenler

Yeni Microsoft Edge, yeni bir UWP bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan, HoloLens 2 gibi yalnızca UWP cihazlarında çalışmasına izin verir, bazı özellikler hemen kullanılabilir olabilir. Önümüzdeki aylarda yeni senaryoları ve özellikleri destekley edeceğimiz için bu alanı güncel bilgiler için kontrol edin.

**Çalışması beklenen senaryolar ve özellikler:**
- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri beklendiği gibi işlemeli ve davranabilir
- Çoğu tarayıcı işlevi (Sık Kullanılanlar, Geçmiş vb.) beklendiği gibi çalışmalı
- Koyu mod
- Cihaza web uygulamaları yükleme
- Uzantıları yükleme (HoloLens 2'de düzgün çalışmayan uzantılar kullanıyorsanız lütfen bize haber ver)
- PDF'yi görüntüleme ve işaretleme
- Tek bir tarayıcı penceresinden uzamsal ses
- Tarayıcıyı otomatik ve el ile güncelleştirme
- Yazdır menüsünden PDF kaydetme ("PDF'ye Kaydet" seçeneğini kullanarak)
- WebXR ve 360 Görüntüleyici uzantısı
- Ortamınıza yerleştirilen birden çok pencereye göz atarak doğru pencereye içerik geri yükleme

**Çalışması beklenilen senaryolar ve özellikler:**
- Eşzamanlı ses akışlarıyla birden çok pencereden uzamsal ses
- "Gör, söyle"
- Yazdırma

**Bilinen en önemli tarayıcı sorunları:**

- Holografik klavyede büyüteç önizlemesi yeni Microsoft Edge. Bu özelliği, büyütme doğru şekilde çalışmaya başladıktan sonra gelecekteki bir güncelleştirmede yeniden kullanılabilir hale gelecektir.
- Başka bir tarayıcı penceresi açık ve etkinse ses yanlış tarayıcı penceresinden oynatılmış olabilir. Ses çalması gereken diğer etkin pencereyi kapatarak bu soruna bir son ve sonra bakabilirsiniz.
- "Beni takip et" modunda bir tarayıcı penceresinden ses çalma sırasında , "Beni takip [et"](hololens2-basic-usage.md#follow-me-stop-following)modunu devre dışı bıraksanız da ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu **atlayabilirsiniz.**
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerinde beklenmedik bir şekilde etkin olmayan bir şekilde etkileşime geçmenizi sağlar. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Bu Microsoft Edge Edge Insider topluluğu tarafından kullanılabilen üç önizleme kanalı vardır: Beta, Dev ve Canary. Önizleme kanalını yüklemek, HoloLens 2'nize Microsoft Edge sürümünü kaldırmaz ve aynı anda birden fazla yükleme işlemi de yükleyebilirsiniz. 

Edge [Insider Microsoft Edge daha fazla bilgi](https://www.microsoftedgeinsider.com) edinmek için Microsoft Edge Insider giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamanız için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Microsoft Edge Insider kanallarını HoloLens 2'ye yüklemek için kullanılabilen birkaç yöntem vardır:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetlanmamış cihazlar tarafından kullanılabilir)**
  1. HoloLens 2'niz için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge Insider kanalı için **HoloLens 2** için indir düğmesini seçin.
  1. İndirilen .msix dosyasını Edge indirme kuyruğundan veya cihazınızın "İndirmeler" klasöründen (Dosya Gezgini).
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatacak.
  1. Yükle **düğmesini** seçin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'i, uygulamanın Tüm uygulamalar ayrı **bir** giriş olarak Başlat menüsü.

**Windows Cihaz Portalı ile PC üzerinden yükleme [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (HoloLens 2'de geliştirici modunun etkinleştirilmesi gerekir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki aşağı ok düğmesini seçin.
  1. Açılan **menüden HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) Windows Cihaz Portalı HoloLens 2'ye yüklemek için bilgisayarınıza bir dosya yükleyin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'i, uygulamanın Tüm uygulamalar ayrı **bir** giriş olarak Başlat menüsü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) uygulama Microsoft Edge güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

[HoloLens](hololens-offline.md)için şu anda kullanılabilir olan uç noktalar hakkında daha fazla bilgi okuyun.

### <a name="install-web-apps"></a>Web uygulamalarını yükleme
 > [!Note]
>Windows [Holographic sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)sonra Office web uygulaması artık önceden yüklenmez.

Yeni Edge'i kullanarak web uygulamalarının yanı sıra yeni Microsoft Store yükleyebilirsiniz. Örneğin, SharePoint veya OneDrive Microsoft Office dosyaları görüntülemek ve düzenlemek için web uygulamasını yükleyebilirsiniz. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya  **Office'i** Yükle düğmesini ziyaret edin ve seçin. Onaylamak **için Yükle'yi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca HoloLens 2'nizin etkin bir İnternet bağlantısı olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici

Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR ile tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler HoloLens 2 tarafından da de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimlerini de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak HoloLens 2 müşterilerinin denemesi için yeni artırılmış ve karma gerçeklik çevreleyici deneyimler edinecek!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve HoloLens 2'deki yeni Microsoft Edge otomatik olarak yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

#### <a name="how-to-use-webxr"></a>WebXR'i kullanma

1. WebXR desteği olan bir web sitesine gidin.
1. Web **sitesinde VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel gösterimi web sitesi başına farklılık gösterebilir ancak aşağıdakine benzer olabilir:

    ![VR düğmesi örneğini girin](images/75px-enter-vr.png)

1. Belirli bir etki alanında WebXR deneyimini ilk kez başlatmayı deneyci, çevreleyici bir görünüm girmek için onay sorar ve İzin Ver'i **seçer.**
1. Deneyimi [değiştirmek için HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame) hareketlerini kullanın.
1. Deneyimin Çıkış düğmesi **yoksa, girişe** dönmek [için Başlat](hololens2-basic-usage.md#start-gesture) hareketini kullanın.

**Önerilen WebXR örnekleri**
- 360 Görüntüleyici (sonraki bölüme bakın)
- [XR Yenileri](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 Görüntüleyici kullanma

1. YouTube'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde karma gerçeklik başlığı düğmesini seçin:

    ![360 Görüntüleyiciyi etkinleştirme düğmesi](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyiciyi ilk kez başlatmaya çalışırsanız tarayıcı, çevreleyici bir görünüm girmek için onay sorar. İzin **Ver'i seçin.**
1. [Kayıttan yürütme](hololens2-basic-usage.md#select-using-air-tap) denetimlerini açmak için havadan dokunma. El [işleyicileri](hololens2-basic-usage.md#select-using-air-tap) ve havadan dokunarak oynatma/duraklatma, ileri/geri atlama, açıklamalı alt yazıları açma/kapatma veya deneyimi durdurma (çevreleyici görünümden çıkar) için kullanın. Kayıttan yürütme denetimleri birkaç saniyelik bir sürenin ardından kaybolur.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>En önemli WebXR ve 360 Görüntüleyici bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak kare hızı düşerek veya düşerek düşebilirsiniz.
- WebXR'de ifadeli el ortakları için destek varsayılan olarak etkin değildir. Geliştiriciler `edge://flags` "WebXR El Girişi"ni etkinleştirerek desteği etkinleştirerek.
- YouTube dışında web sitelerinden 360 video beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici hakkında geri bildirim sağlama

Lütfen yeni çalışmadaki Geri Bildirim Gönder özelliği **aracılığıyla geri bildirimi ve** hataları ekibimizle Microsoft Edge.

### <a name="new-settings-app"></a>Yeni Ayarlar uygulaması

Bu sürümle birlikte, Ayarlar uygulamasının yeni bir sürümünü tanıtabilirsiniz. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni Ayarlar uygulaması eski Ayarlar uygulamasından ayrı olduğundan, daha önce ortamınıza yerleştirilen tüm Ayarlar pencereleri güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar uygulaması giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarlar araması: Anahtar sözcükleri veya ayarın adını kullanarak Ayarlar giriş sayfasından ayarlar için arama yapın.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, Bluetooth mikrofonları aracılığıyla ses dinleme veya ses girişi için USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonları HoloLens 2 tarafından desteklenmiyor.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Uygulama [başına birim denetimine bakın.](#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktanın otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık HoloLens 2'de uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Daha önce yerleştirilen Ayarlar pencereleri kaldırılır (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden adlandıramazsiniz. IT yöneticileri [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) için Windows Autopilot şablonu veya MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme bek gerekmmektedir).

#### <a name="display-color-calibration"></a>Renk ayarlamayı görüntüleme



Bu yeni ayar ile HoloLens 2 ekranınız için alternatif bir renk profili seçebilirsiniz. Bu, renklerin özellikle daha düşük ekran parlaklığı düzeylerinde daha doğru görünmesine yardımcı olabilir. Renk düzeltmeyi görüntüleme, Ayarlar uygulamasında, Sistem Ve Ayar > bulunabilir.

> [!NOTE]
> Bu ayar görüntü üretici yazılımınıza yeni bir renk profili kaydedeci, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Görüntü rengi ayarlamayı kullanma

1. Ayarlar uygulamasını **başlatarak** System > **Olarak Değiştirin.**
1. Renk **ayarı görüntüle'nin** altında Renk **görüntüleme düzenini çalıştır düğmesini** seçin.
1. Ekran rengi ayarlama deneyimi başlatacak ve sizi, mengenenizin doğru konumda olduğundan emin olmak için teşvik eder.
1. Yönerge iletişim kutularına devam ettikten sonra, ekranınız otomatik olarak %30 parlaklığa soluk görüntülenir.
    > [!TIP]
    > Ortamınız soluk sahneyi görme konusunda sorun taşıyorsanız cihazın sol tarafındaki parlaklığı düğmeleri kullanarak HoloLens 2'nin parlaklığını el ile ayarlayabilirsiniz.
1. Her renk profilini anında denemek için 1-6 düğmelerini seçin ve en iyi görüneni bulun (bu genellikle sahnenin en nötr görünmesine yardımcı olan profil anlamına gelir ve gri tonlama deseni ve ten rengi beklendiği gibi görünür.)

    ![Renk ayarı sahneyi görüntüleme](images/color-cal-ui.png)
    
1. Seçilen profilden memnun değilken Kaydet ve Çıkış **&** seçin
1. Değişiklik yapmamayı tercih ederseniz, İptal et **düğmesini & ve** değişiklikleriniz geri döndürülecek

> [!TIP]
> Burada, görüntü rengi ayarıyla ilgili bazı yararlı ipuçlarına göz ayın:
> - Ekran rengi ayarlamayı Ayarlar'dan istediğiniz zaman yeniden çalıştırabilirsiniz
> - Cihaz üzerinde herhangi biri renk profillerini değiştirmek için daha önce bu ayarı kullandı ise, en son değişikliğin tarihi/saati Ayarlar sayfasına yansıtıldı
> - Görüntü rengi ayarlamayı yeniden çalıştırarak daha önce kaydedilen renk profili vurgulanır ve Profil 0 görünmez (Profil 0, ekranın özgün renk profilini temsil ettiği için)
> - Ekranın özgün renk profiline geri dönmek için Ayarlar sayfasından bunu yapabilirsiniz (renk profilini [sıfırlamaya bakın)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama 

HoloLens 2'nize kaydedilen özel renk profili sizi üzecekse cihazın özgün renk profilini geri yükleyebilirsiniz:
1. Ayarlar uygulamasını **başlatarak** System > **Olarak Değiştirin.**
1. Renk **ayarı görüntüle altında** Varsayılan renk **profiline sıfırla düğmesini** seçin.
1. HoloLens 2'yi **yeniden başlatmaya** ve değişikliklerinizi uygulamaya hazırsanız iletişim kutusu açıldığında Yeniden Başlat'ı seçin.

#### <a name="top-display-color-calibration-known-issues"></a>Bilinen en çok görünen renk ayarı sorunları

- Ayarlar sayfasında, renk profilinin en son ne zaman değiştirdiğini size söyleyen durum dizesi, Ayarlar sayfasını yeniden yükleyene kadar güncel olmayacaktır.
    - Geçici çözüm: Başka bir Ayarlar sayfası seçin ve sonra Ayarlama sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirdiğinde veya birden fazla yüklü uygulamayla bir dosya türünü a açarsanız, hangi yüklü uygulamanın dosya veya bağlantı türünü işlemesi gerektiğini seçmenizi istediğiniz yeni bir pencere açılır. Bu pencerede, seçilen uygulamanın dosyayı işlemesi veya "Bir kez" ya da "Her zaman" bağlantı türünü de seçmeyi seçebilirsiniz.

"Her Zaman"ı seçerseniz ancak daha sonra belirli bir dosyayı veya bağlantı türünü hangi uygulamanın işleyeni değiştirmek istiyorsanız, Ayarlar ve Uygulamalar'da kayıtlı **varsayılanlarınızı > edebilirsiniz.** Sayfanın en altına kaydırın ve  "Dosya türleri için varsayılan uygulamalar" ve/veya "Bağlantı türleri için varsayılan uygulamalar" altındaki Temizle düğmesini seçin. Masaüstü bilgisayarlardaki benzer ayarın aksine, tek tek dosya türü varsayılanlarını sıfırlayabilirsiniz.

#### <a name="per-app-volume-control"></a>Uygulama başına birim denetimi

Artık bu Windows derlemesinde kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duyan uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha iyi duymasını sağlar. Örneğin, başka bir uygulamada uzaktan yardım için başka bir kişiyi çağırırken bir uygulamanın hacmini kapatmak gibi.

Tek bir uygulamanın hacmini ayarlamak için Ayarlar Sistem Sesi'ne gidin ve Gelişmiş ses seçenekleri altında Uygulama birimi  ->    ->  ve **cihaz tercihleri'ne tıklayın.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe doğru çekme

Bazı müşteriler, kullanmakta olduğu sözcüğün şeklini değiştirerek sanal klavyelerde "yazma" özelliğini daha hızlı bulabilir ve holografik klavye için bu özelliğin önizlemesini sunuyoruz. Holografik klavyenin düzlemi üzerinden parmak ucunu atarak, sözcüğün şeklini çekerek ve ardından klavyenin düzlemi üzerinden parmak ucunu çekerek tek tek çekerek tek bir sözcük çekebilirsiniz. Sözcüklerin arasındaki klavyeden parmaklarınızı kaldırarak boşluk çubuğuna basmanıza gerek kalmadan sözcükleri takip etmek için kaydırabilirsiniz. Klavyede parmak hareketini takip eden bir çekme izi görüyorsanız özelliğin çalıştığını bilirsiniz.

Lütfen unutmayın; bu özelliğin kullanımı ve ana kaynak kullanımı, parmak izinize karşı direnç hissetmeyebilirsiniz (cep telefonu görüntüsü aksine) holografik klavyenin yapısı nedeniyle karmaşık olabilir. 

### <a name="power-menu-from-start"></a>Başlat'tan Güç menüsü

Kullanıcının oturum kapatmasını, kapatmasını ve cihazı yeniden başlatmasını sağlayan yeni bir menü. HoloLens Başlangıç ekranı güncelleştirmenin ne zaman kullanılabilir olduğunu gösteren bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. Başlangıç hareketini veya "Başlangıç ekranı [Git" ifadesini](hololens2-basic-usage.md#start-gesture) kullanarak HoloLens Başlangıç ekranı'i açın.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkatin:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Ellerinizi kullanarak kullanıcı profili resmini veya "Power" sesli komutunu seçin.

4. Cihazı kapatma, Yeniden Başlatma veya Kapatma seçeneklerinin yer alan bir menü görüntülenir:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. HoloLens'inizi kapatmak, yeniden başlatmak veya kapatmak için menü seçeneklerini belirleyin. Cihaz tek bir Microsoft Hesabı [(MSA)](hololens-identity.md)veya yerel hesap için ayarlanmışsa, Oturum açma seçeneği kullanılamıyor olabilir.

6. Başka bir yere dokunarak veya Başlat hareketiyle Başlat menüsü menüyü kapatabilirsiniz.

#### <a name="update-indicator"></a>Göstergeyi güncelleştirme

Bir güncelleştirme kullanılabilir olduğunda, yeniden başlatmanın güncelleştirmeyi yükley hazır olduğunu belirtmek için üç nokta simgesi yanacak Menü seçenekleri güncelleştirmenin varlığını yansıtacak şekilde de değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında listelenen birden çok kullanıcı

Daha önce Oturum Açma ekranında yalnızca en son oturum açık olan kullanıcının yanı sıra 'Diğer kullanıcı' giriş noktası gösteri. Cihazda birden çok kullanıcı oturum açınsa bunun yeterli olmadığını ifade etmek için müşteri geri bildirimi aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekmektedir.

Bu Windows derlemesinde tanıtılan,  PIN girişi alanında sağ tarafta bulunan Diğer kullanıcı'nın seçili olduğu oturum açma ekranında daha önce cihazda oturum açmamış birden çok kullanıcı görüntülenir. Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Cihaza hesap ekle düğmesi aracılığıyla bu Diğer kullanıcılar sayfasından yeni bir kullanıcı **da eklenebilir.**

Diğer kullanıcılar menüsünde, Diğer kullanıcılar düğmesi cihazda oturum açmış olan son kullanıcı görüntülenir. Bu kullanıcının Oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C Dış Mikrofon Desteği

> [!IMPORTANT]
> BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.** Bir USB-C cihazına takan kullanıcılar, mikrofonlu cihazın sesinin otomatik olarak mikrofonlara yönlendirilmesine neden olduğunu gözlemler ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazının üzerinde öncelik sırasına göre hazırlar. **USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**

Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz. USB-C mikrofonları arama, kayıt vb. için kullanılabilir.

Ayarlar uygulamasını **açın** ve Sistem **Sesi'ne**  >  **tıklayın.**

![Ses Ayarları](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.
>
> Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.** **Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.
>
> İletişim **Varsayılanı'nın** seçimi, dış mikrofonun Remote Assist ve diğer iletişim uygulamaları için kullanılamayacak, ancak HoloLens mikrofon dizisi diğer görevler için hala kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlama](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği ne olacak?

Ne yazık ki HoloLens 2'de Bluetooth mikrofonları hala desteklenmiyor.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofon sorunlarını giderme

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, HoloLens ile değil mikrofonla ilgili bir sorundur. Bu mikrofonlardan birini HoloLens'e takarak ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Ayarlar   ->  **Sistem**  ->  **Sesi'nin** içinde yerleşik konuşmacıları (Analog Özellik Ses **Sürücüsü) Varsayılan** cihaz olarak açıkça **ayarlayın.** HoloLens, mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlaması gerekir.

![USB-C mikrofon sorunlarını giderme](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma

Bu yeni özellik, Ziyaretçi hesaplarında otomatik oturum açma özelliğinin Bilgi Noktası modları için kullanılmaktadır.

AAD olmayan bir yapılandırma için, bir cihazı ziyaretçinin otomatik oturum açması için yapılandırmak üzere:

1. Şunları içeren bir sağlama paketi oluşturun:
    1. Ziyaretçi **hesaplarına izin vermek için Çalışma Zamanı ayarlarını/AssignedAccess'i** yapılandırıyor.
    1. İsteğe bağlı olarak, daha sonra yönetilsin diye cihazı MDM'ye (Çalışma zamanı **ayarları/Çalışma Alanı/Kayıtlar)** kaydediyor.
    1. Yerel hesap oluşturma
1. [Sağlama paketini uygulama.](hololens-provisioning.md)

AAD yapılandırmasında kullanıcılar bu değişiklik olmadan bugün buna benzer bir şey elde ediyor olabilir. Bilgi noktası modu için yapılandırılan AAD'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak Ziyaretçi hesabında oturum açmasını sağlar. Ziyaretçi hesabında oturum açıldıktan sonra, ziyaretçi başlat menüsünden açıkça oturum açıncaya veya cihaz yeniden başlatana kadar cihaz yeniden oturum açma isteminde olmayacaktır.

Ziyaretçi Otomatik oturum açma işlemi özel [OMA-URI ilkesi aracılığıyla](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) yönetilebilir:

- URI değeri: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| İlke  | Açıklama   | Yapılandırmalar  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Bir Ziyaretçinin Bilgi Noktası'da otomatik olarak oturum açmasını sağlar   | 1 (Evet), 0 (Hayır, varsayılan.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Bilgi Noktası modlarında yeni Ayarlar ve Edge uygulamalarını kullanma

Uygulamaları Bilgi [Noktası'ne](hololens-kiosk.md)eklerken, BIR IT Yöneticisi genellikle uygulamayı Bilgi Noktası'nın yerine Uygulama Kullanıcı Modeli Kimliği'ni (AUMID) kullanarak ekler. Hem Ayarlar uygulaması hem de Microsoft Edge uygulaması yeni uygulamalar olarak kabul edilir ve bu uygulamalar için AUMID kullanan eski uygulamalar bilgi noktası bilgi noktası yeni AUMID'yi kullanmak üzere güncelleştirilmelidir.

Bilgi Noktası'nın yeni uygulamaları içerecek şekilde değiştirilmesini sağlarken, yeni AUMID'ye eklemenizi ve eskisini bırakmanız önerilir. Bu, kullanıcılar işletim sistemi güncelleştirecek ve Bilgi Noktası'nın hedeflenen şekilde kullanmaya devam etmek için yeni ilkeler almaları gerekmayacak olduğunda kolay bir geçiş sağlar.

| Uygulama                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Eski Ayarlar Uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Yeni Ayarlar Uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri

Eski derlemelerde, bir cihazın hem genel atanan erişimin hem de AAD grup üyesi tarafından atanan erişimin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğinin başarısız olduğu belirlenirse kullanıcı["](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)başlat " menüsünde hiçbir şey gösterilmez.

Bu Windows yayından başlayarak, AAD grup bilgi noktası modu sırasında hata olması durumunda bilgi noktası deneyimi genel bilgi noktası yapılandırmasına (varsa) geri dönüş sağlar.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Sayfa Ayarları Görünürlüğü için Yeni Ayarlar URL'leri

[Windows Holographic sürüm 20H2'de](hololens-release-notes.md#windows-holographic-version-20h2) Ayarlar uygulamasında görülen sayfaları kısıtlamak için [Ayarlar/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ilkesi ekledik. PageVisibilityList, IT Yöneticilerinin Sistem Ayarları uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkedir.

Sayfa Ayarları [Görünürlüğü sayfasını ziyaret ediyorsanız,](settings-uri-list.md)bu CSP'yi kullanma yönergelerini ve önceki sürümlerde kullanılabilen URL'lerin listesini bulabilirsiniz.

IT Yöneticilerinin yönettikleri kullanılabilir Ayarlar URL'lerinin listesini genişletiyoruz. Bu URL'lerden bazıları, yeni Ayarlar uygulamasındaki yeni kullanılabilir alanlara göre oluşturulmuştur. Ayarlar/PageVisibilityList ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

> [!NOTE]
> **Kullanım dışı: ms-settings:network-proxy**
>
> Bu yeni derlemelerde bir ayarlar sayfası kullanım dışıdır. Eski **Ağ &**  >  **İnternet Ara** Sunucusu sayfası artık genel ayar olarak kullanılamaz. Yeni bağlantı başına ara sunucu ayarları, İnternet   >  **Wi-Fi** Özellikleri & Ağ Bağlantısı Özellikleri veya İnternet Ethernet Özellikleri altında  >   **&**  >    >  **bulunabilir.**

<br>

| Ayarlar sayfası                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Uygulamalar > Apps & özellikleri                               | `ms-settings:appsfeatures`                         |
| Uygulamalar > Gelişmiş & uygulamalar > özellikleri          | `ms-settings:appsfeatures-app`                     |
| Uygulamalar > Çevrimdışı haritalar                                  | `ms-settings:maps`                                 |
| Uygulamalar > Çevrimdışı haritalar > Haritaları indirme                  | `ms-settings:maps-downloadmaps`                    |
| Cihazlar > Fare                                      | `ms-settings:mouse`                                |
| Usb > cihazlar                                        | `ms-settings:usb`                                  |
| İnternet & Uçak > ağ bağlantısı                   | `ms-settings:network-airplanemode`                 |
| Gizlilik > Genel                                    | `ms-settings:privacy-general`                      |
| Gizlilik > Mürekkep & kişiselleştirme             | `ms-settings:privacy-speechtyping`                 |
| Gizlilik > Motion                                     | `ms-settings:privacy-motion`                       |
| Gizlilik > Ekran görüntüsü kenarlıkları                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Gizlilik > Ekran görüntüleri ve uygulamalar                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Sistem > Pil                                     | `ms-settings:batterysaver`                         |
| Sistem > Pil                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| Sistem > Ses > Uygulama birimi ve cihaz tercihleri | `ms-settings:apps-volume`                          |
| System > Sound > Ses cihazlarını yönetme              | `ms-settings:sound-devices`                        |
| Sistem > Depolama > Yapılandırma Akıllı Depolama         | `ms-settings:storagepolicies`                      |
| Saat & Dili > Tarih & saat                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Güncelleştirme & Güvenlik > Sıfırlama & kurtarma               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Güncelleştirilmiş URL'ler

Daha önce aşağıdaki iki URL, bir kullanıcıyı doğrudan belirtilen sayfalara götürmürken yalnızca ana güncelleştirmeler sayfasını engelledi. Aşağıdaki öğeler sayfalarına yönlendirecek şekilde güncelleştirilmiştir:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Ayarlar uygulaması aracılığıyla Geri Dönüş Tanılamasını yapılandırma

Artık Ayarlar Uygulamasında, bir kullanıcı Geri Dönüş [Tanılaması'nın davranışını yapılandırabilirsiniz.](hololens-diagnostic-logs.md) Bu ayarı yapılandırmak için Ayarlar **uygulamasında**  ->  **Gizlilik Sorunlarını** Giderme sayfasına gidin.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, kullanıcı bu davranışı geçersiz k aşağıdaki gibi davranamayacaktır.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla paylaşım

Hem bilgisayarlar hem de diğer HoloLens 2 cihazları dahil olmak Windows 10 yakın cihazlarla paylaşımda bulundurabilirsiniz. HoloLens'den **bir** pc'ye dosya veya URL'leri paylaşmak için Ayarlar  ->    ->   Sistem Paylaşılan Deneyimleri'ne gidin. Diğer ayrıntılar için, [Windows 10'de yakındaki cihazlarla şeyler paylaşma hakkında daha fazla bilgi Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Bu özellik [Bağlantı/AllowConnectedDevices aracılığıyla yönetilebilir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, yeni işletim sistemi güncelleştirmeleri için Ayarlar uygulamasının da ek olarak yeni bir sorun giderici eklendi. Ayarlar Güncelleştirme **Güvenliği**  ->  **Sorunlarını &amp; Giderme'ye**  >    >  **Windows Update** başlat'ı **seçin.** Bu sayede, SORUN GİDERme veya destekle ilgili sorun giderme konusunda daha iyi yardımcı olmak için işletim sistemi güncelleştirmeleriyle sorunlarınızı yeniden üretirken izlemeleri toplamanıza olanak sağlar.

### <a name="delivery-optimization-preview"></a>Teslim İyileştirme Önizleme

Bu HoloLens güncelleştirmesi sayesinde Windows Holographic for Business cihaz indirmeleri için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarına olanak tanır. Bu işlevin daha ayrıntılı bir açıklaması ve önerilen ağ yapılandırması burada mevcuttur: [güncelleştirmeleri Teslim İyileştirme için Windows 10 kullanılabilir.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Aşağıdaki ayarlar yönetim yüzeyinin bir parçası olarak etkinleştirilir [ve Intune'dan yalıtabilirsiniz:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarı:

- HoloLens desteği bu önizlemede yalnızca işletim sistemi güncelleştirmeleri ile sınırlıdır.
- Windows Holographic for Business yalnızca bir Microsoft Bağlı Önbellek uç noktasına http indirme [modlarını ve indirmelerini destekler;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Şu anda HoloLens cihazları için eşler arası indirme modları ve grup atamaları desteklenmiyor.
- HoloLens, Windows Server Update Services uç noktaları için dağıtım veya teslim iyileştirmesini desteklemez.
- Sorun giderme işlemi için Bağlı Önbellek sunucusunda tanılama gerekir veya Ayarlar Güncelleştirmesi ve Güvenlik Sorunlarını Giderme sayfasından HoloLens üzerinde HoloLens  >  **üzerinde &**  >   **izleme**  >   **Windows Update.**

### <a name="it-admin---update-checklist"></a>IT Yöneticisi - Güncelleştirme Denetim Listesi

Bu denetim listesi, geçerli cihaz yönetimi yapılandırmalarınızı veya kullanmaya başlamak istediğiniz yeni özellikleri etkileyebilecek bu özellik güncelleştirmesinde eklenen yeni öğeleri size yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi Noktası modundaki güncelleştirmeler

✔️ Bilgi [**Noktası modunda yeni uygulamalar için Yeni AUMID'ler oluşturun:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Daha önce Bir Bilgi Noktası'Microsoft Edge ayarlar uygulamasını kullandıysanız, bu uygulamaları farklı bir Uygulama Kimliği kullanan yeni uygulamalarla değiştiririz. Aşağıdaki Bilgi Noktası modundaki [yeni uygulamalar için Yeni AUMID'leri okumanız önemle](#use-the-new-settings-and-edge-apps-in-kiosk-modes) tavsiye edilecektir. Bu, Bilgi Noktası'nıza Ayarlar uygulamasına sahip olmaya devam edin veya yeni uygulama Microsoft Edge sağlar. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirmede daha sorunsuz bir geçişe olanak tanır.

✔️ Bilgi [**Noktası için Ziyaretçi Otomatik Oturum Açma:**](#visitor-auto-logon-for-kiosks) 

Ziyaretçiler artık bir Bilgi Noktası'nde otomatik olarak oturum açabilirsiniz. Bu davranış varsayılan olarak açıktır, ancak yönetilebilir ve devre dışı bırakılabilir.

✔️ [**Bilgi Noktası modu hatası teslimi:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Oturum açmış AAD kullanıcılarının AAD grup üyeliği başarıyla belirlenene kadar, başlat menüsü (varsa) için genel bilgi noktası yapılandırması kullanılır, aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınıza bildirmeniz gereken bir şey olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ayarları Görünürlüğü güncelleştirmeleri

✔️ Ayarları [**Görünürlüğü için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarları [Görünürlüğü kullanıyorsanız,](settings-uri-list.md) izin verilen veya engellenen mevcut URI'lerde ayarlamalar yapmak yapabilirsiniz.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler
✔️ WDAC aracılığıyla Microsoft Edge engelleme yaptıysanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme
✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, yeni uygulama için bu yeni uç noktaları Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere uzer ve kim tarafından toplay olduğunu yapılandırmış oluruz.

✔️ Cihazları[yakın cihazlarla paylaşma:](#share-things-with-nearby-devices)Yakındaki yeni paylaşım özelliğini devre dışı abilirsiniz.

✔️ için [ilke ayarlarını yapılandırma: Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)için kullanılabilen yeni yapılandırmaları Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Yeni tanılama aracı

✔️[yeni işletim sistemi tanılama izlemeleri:](#new-os-diagnostic-traces)Işletim Sistemi Güncelleştirmeleri ile ilgili günlükleri toplayın.

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- [Çevrimdışı tanılama,](hololens-diagnostic-logs.md#offline-diagnostics) seri numarası ve işletim sistemi sürümü için ek cihaz bilgileri de içerir.
- Çalışma zamanı sağlama paketleri aracılığıyla iş hattı uygulamalarının dağıtımıyla ilgili bir sorunu düzeltir.
- İş hattı uygulaması yükleme durumu raporlaması ile ilgili bir sorunu düzeltir.
- Cihaz sıfırlamalarında yeni uygulama paketlerinin kalıcılığıyla ilgili bir sorunu düzeltir.
- Japonca müşteriler için Edge'de yanlış sembollerin yaz yaz 2019'a neden olmasıyla ilgili bir sorun düzeltildi.
- Edge gibi önceden yüklenmiş uygulamalarla ilgili işletim sistemi güncelleştirmelerinin daha yüksek bir şekilde kullanılabilirlik sağlar. 
- Güncelleştirmenin yüklemesini etkileyen bir güncelleştirme güvenilirliğini Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, sürüm 20H2 – Mayıs 2021 Güncelleştirmesi
- Derleme 19041.1146

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic sürüm 21H1'i denemeniz gerekir.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, sürüm 1903 - Mayıs 2021 Güncelleştirmesi
- Derleme 18362.1110

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. **Bu derleme artık aylık hizmet güncelleştirmelerini almayacak.** En son Windows Holographic sürüm 21H1'i denemeniz için sizi teşvik ederiz.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, sürüm 20H2 - Nisan 2021 Güncelleştirmesi
- Derleme 19041.1144

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İş hattı uygulaması yükleme durumu raporlaması ile ilgili bir sorunu düzeltir.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, sürüm 1903 - Nisan 2021 Güncelleştirmesi
- Derleme 18362.1108

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Yerel bir hesap için parola değiştirmeye çalışırken Ayarlar uygulamasının kilitlenmesi sorunu gidermek.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, sürüm 20H2 - Mart 2021 Güncelleştirmesi
- Derleme 19041.1140

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 ile fotoğraf çekmek için AdvancedPhotoCapture veya LowLagPhotoCapture kullanan müşteriler artık fotoğraf kaydedildikten 3 saniye sonra kamera pozunu alabilir.
- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.
- Aşamalı Rollout'a kaydolan kullanıcıların cihazda oturum alamama sorunu düzeltildi.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, sürüm 1903 - Mart 2021 Güncelleştirmesi
- Derleme 18362.1102

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, sürüm 20H2 - Şubat 2021 Güncelleştirmesi
- Derleme 19041.1136

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İlk cihaz kurulumu ve mağaza uygulama güncelleştirmeleri ile ilgili bir sorunu düzeltir.
- Sonraki HoloLens yayınlarında yükseltme ve uçuş ile ilgili bir sorunu gidermek.
- HoloLens cihazlarından eSIM kök depolamadan kullanılmayan önceden yüklenmiş sertifikalar kaldırıldı.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, sürüm 1903 - Şubat 2021 Güncelleştirmesi
- Derleme 18362.1098

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, sürüm 20H2 - Ocak 2021 Güncelleştirmesi
- Derleme 19041.1134

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihazda çok sayıda kullanıcı olduğunda başlatma, sürdürme ve kullanıcı değiştirme sırasında performans geliştirildi.
- Araştırma Modu için arm32 [desteği eklendi.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, sürüm 1903 - Ocak 2021 Güncelleştirmesi
- Derleme 18362.1091

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesi
- Derleme 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama Yükleyicisi aracılığıyla HoloLens 2'ye Uygulama yükleme

HoloLens 2 cihazlarınıza daha Uygulama Yükleyicisi uygulamaları yüklemenize olanak sağlayan yeni bir özellik **(Uygulama Yükleyicisi)** ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazları için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:
- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin (USB üzerinden veya Edge üzerinden) cihazınıza indirerek Dosya Gezgini Appx Paketi'ne gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğunuz uygulamalar gibi, uygulamaların [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) da İmza Aracı ile dijital olarak imzalandırılacağı ve uygulamanın dağıtılablan önce HoloLens cihazı tarafından güvenilmeleri gerekir. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Uygulama yükleme yönergeleri.**

1.  Cihazınızın yönetilen olarak kabul edilen bir şey olduğundan emin olun
1.  HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1.  HoloLens 2 cihazında oturum açın
1.  Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Storage\Downloads klasörüne kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1.  HoloLens 2 cihazınızdan Başlat menüsünü açın, tüm uygulamalar ' ı seçin ve dosya Gezgini uygulamasını başlatın.
1.  Indirmeler klasörüne gidin. Uygulamanın sol panelinde bu cihazı önce seçin, sonra Indirmeler ' a gidin.
1.  Yourapp. appxpaket dosyasını seçin.
1.  Uygulama yükleyicisi başlatılır. Uygulamanızı yüklemek için Install (Çalıştır) düğmesini seçin.
Yükleme tamamlandıktan sonra yüklenen uygulama otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) üzerinde örnek uygulamalar bulabilirsiniz.

[Uygulama yükleyicisiyle HoloLens 2 ' ye uygulama yükleme](app-deploy-app-installer.md)işleminin tam süreci hakkında bilgi edinin.  

![Uygulama yükleyicisi aracılığıyla MRTK örnekleri yükleme](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El ile izleme artık, izlemenin daha önce kaybedildiği birçok yeni durumda izlemeyi korur.  Bu yeni durumların bazılarında, yalnızca Palm konumu kullanıcının gerçek adına göre güncelleştirilmeye devam ederken, diğer yandan da önceki bir poza göre çıkarılır.  Bu değişiklik, taşıma, oluşturma, scoing ve hareketli hale alma gibi hareket halinde izlemenin tutarlılığını artırmaya yardımcı olur.  Ayrıca, el 'nin bir yüzeye yakın veya bir nesneyi tutan durumlarda da yardımcı olur.  Bu yandan, her ne kadar [ortak doğruluk](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) değeri "yüksek" yerine "yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamasının bir hata göstereceği bir sorun düzeltildi "bir sorun oluştu.
- Kullanıcılar, ayarlar uygulaması, Yeni Kullanıcı veya bildirim bildirimi ' ni başlatırken, kullanıcıların çok daha az önyükleme sonrası OOBE kilitlenmelerini görmelidir.
- Kullanıcıların, OOBE 'den gelen doğru saat dilimi olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows holographic, sürüm 1903 – Aralık 2020 güncelleştirme
- Derleme 18362,1088

Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son Windows holographic, sürüm 20H2 – Aralık 2020 güncelleştirme ve yapıya eklenen yeni uygulama yükleyicisi özelliğini denemenizi öneririz.


## <a name="windows-holographic-version-20h2"></a>Windows holographic, sürüm 20H2
- Derleme 19041,1128

Windows holographic, sürüm 20H2 artık kullanıma sunuldu ve HoloLens 2 kullanıcılarına ve BT uzmanlarına harika yeni özellikler sunuyor. Otomatik göz konumlandırmayı, Ayarlar ' da Sertifika Yöneticisi ' ne, gelişmiş bilgi noktası modu işlevselliğine ve yeni Autopilot kurulum özelliklerine sahip. Bu yeni güncelleştirme, BT ekiplerinin HoloLens cihazlarını yapılandırmaya ve yönetmeye yönelik daha ayrıntılı denetim almasını sağlar ve kullanıcılara daha sorunsuz holographic deneyimleri sunar. 

Bu en son sürüm 2004 sürümüne yönelik aylık bir güncelleştirmedir, ancak bu kez yeni özellikler de ekledik. Ana yapı numarası aynı kalacaktır ve Windows Update Sürüm 2004 ' e yönelik aylık bir yayın olduğunu belirtecektir (derleme 19041). En son kullanılabilir derleme 19041.1128 + üzerinde olduğunu onaylamak için, ayarlarınızda derleme numaranızı > ekran hakkında izleyebilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, güncelleştirme & güvenliği ' ne gidin ve güncelleştirmeleri denetle ' ye dokunun. HoloLens güncelleştirmelerinin nasıl yönetileceği hakkında daha fazla bilgi için [Bu sayfayı](https://docs.microsoft.com/hololens/hololens-updates)ziyaret edin.

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows holographic, sürüm 20H2 ' deki yenilikler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik göz konumu desteği](hololens-release-notes.md#auto-eye-position-support) | Göz önünde bulunmadan, göz önünde bulunmadan önce gözle yer işareti olarak hesaplar.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Yeni daha basit yöntemlerin Ayarlar uygulamasından sertifika yüklemesine ve kaldırmasına izin verir.     |
| [Sağlamayı USB 'den otomatik olarak başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerdeki sağlama paketleri otomatik olarak OOBE 'de sağlama sayfasına istem.                                                         |
| [OOBE 'de sağlama paketlerini otomatik onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimi kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve birlikte otomatik onaylama işlemlerini birleştirme. |
| [Wi-Fi bağlantısı ile Autopilot kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısı için gerek olmadan cihaz Wi-Fi Autopilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlandığında veya yeniden flaışınızda bu kiracıya kaydedilebilir. |
| [Genel atanan erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Birden çok uygulama bilgi noktası modu için yeni yapılandırma yöntemi, sistem düzeyinde bilgi noktası uygular ve bu durum, tümü için geçerli hale getirir.                  |
| [Çoklu uygulama bilgi noktasında uygulamayı otomatik olarak başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Bir uygulamayı birden çok uygulama bilgi noktası modunda oturum açarken otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüş içeriyor.                                                                                                |
| [HoloLens Ilkeleri](hololens-release-notes.md#hololens-policies)                                    | HoloLens için yeni ilkeler.     |
| [Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların, gün sayısını ayarlamak için bilgi noktası modunu çevrimdışı kullanması için Grup üyeliği önbelleğini kullanmasına izin verir.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilmiş cihaz yönetimi ilkeleri etkinleştirildi.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [Güncelleştirme Ilkeleri](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için etkinleştirilmiş ayarlar sayfası görünürlüğü](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Ayarlar uygulamasında hangi sayfaların görüldüğünü seçme ilkesi.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2 üzerinde araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikaya geçmiyor. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik göz konumu desteği

HoloLens 2 ' de, göz pozisyonları doğru hologram konumlandırmayı, rahat görüntüleme deneyimini ve geliştirilmiş görüntü kalitesini sağlar. Göz konumları, göz izleme hesaplamasının bir parçası olarak dahili olarak hesaplanır. Bununla birlikte, bu durum, deneyim göz önünde olmayan giriş gerektirmese de, her bir kullanıcının göz önünde geçiş ayarlaması için geçmesi gerekir.

**Otomatik göz konumu (AEP)** , bu senaryolara Kullanıcı için göz önünde bekleyen bir yol sağlar. Otomatik göz konumu, kullanıcının cihazı üzerine koyduğu andan itibaren otomatik olarak çalışmaya başlar. Kullanıcının önceki bir göz izleme ayarı yoksa, otomatik gözle, 20-30 saniyelik bir işlem zamanından sonra, ekran sistemine kullanıcının göz konumlarını sağlamaya başlayacaktır. Kullanıcı verileri cihazda kalıcı değil ve bu nedenle kullanıcı devre dışı bırakılırsa veya cihaz yeniden başlatıldığında veya uyku modundan çıktığında bu işlem yinelenir.

Kalibre edilmemiş bir Kullanıcı cihaza geçiş yaparken otomatik gözle konum özelliği olan birkaç sistem davranışı değişikliği vardır. Bu bağlamda, kalibre edilmemiş bir Kullanıcı, cihazda daha önce gelen göz izleme ayarlama işleminden geçmiş bir kişiye başvurur.

| Etkin uygulama | Önceki davranış | Windows holographic, sürüm 20H2 güncelleştirme davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Gaze etkin olmayan uygulama veya holographic kabuğu |Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Hiçbir istem gösterilmez. |
| Etkin uygulama | Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz önünde akışa eriştiğinde görüntülenir. |

Kullanıcı, Gaze olmayan bir uygulamadan, Gaze verilerine erişen bir uygulamaya geçiş yaptığında ayarlama istemi görüntülenir. 

Geçerli kullanıcının etkin bir göz izleme ayarlaması olmadığında, diğer tüm sistem davranışları ile benzerdir. Örneğin, tek elli başlangıç hareketi etkinleştirilmeyecektir. İlk kurulum için hazır olmayan deneyimle ilgili hiçbir değişiklik olmayacaktır.

Veri veya çok kesin hologram konumlandırmayı gerektiren deneyimler için, kalibre izleme ayarlamayı çalıştırmak için kalibre edilmemiş kullanıcıları öneririz. Göz izleme ayarlama isteminden veya ayarlar uygulamasını başlangıç menüsünden başlatarak ve ardından **sistem > ayarlama > gözle ayarlama > Çalıştır**' ı seçerek erişilebilir.

Bu bilgiler, daha sonra [diğer ayarlama bilgileriyle](hololens-calibration.md#auto-eye-position-support)bulunabilir. 

### <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama araçları. Bu özellik, ticari ortamlarda sertifikalarınızı bir ölçekte dağıtmanıza, gidermenize ve doğrulamanıza olanak sağlar.

Windows holographic Version 20H2 ' de, HoloLens 2 Ayarlar uygulamasına bir sertifika yöneticisi ekliyoruz. **Ayarlar > güncelleştirme & güvenlik > sertifikaları**' na gidin. Bu özellik, cihazınızdaki sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için daha fazla denetim, tanılama ve doğrulama araçları geliştirmiştir. 

-   **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığını doğrulama veya uygun şekilde kaldırıldığını doğrulama özelliği. 
-   **Tanılama:** Sorun ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulamak zaman kazandırır ve sorun gidermeye yardımcı olur. 
-   **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğu doğrulanıyor, özellikle de daha büyük ölçekte sertifika dağıtmadan önce ticari ortamlarda önemli bir zaman kazandırabilir.

Listedeki belirli bir sertifikayı hızlı bir şekilde bulmak için ada, depoya veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar ayrıca bir sertifikayı doğrudan arayabilir. Ayrı sertifika özelliklerini görüntülemek için sertifikayı seçin ve **bilgi**'ye tıklayın. 

Sertifika yüklemesi şu anda. cer ve. CRT dosyalarını desteklemektedir. Cihaz sahipleri, sertifikaları yerel makineye ve geçerli kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca geçerli kullanıcıya yüklenebilir. Kullanıcılar yalnızca doğrudan ayarlar kullanıcı arabiriminden yüklenmiş sertifikaları kaldırabilir. Bir sertifika başka yollarla yüklendiyse aynı mekanizmaya de kaldırılmalıdır.

#### <a name="to-install-a-certificate"></a>Bir sertifika yüklemek için: 

1.  HoloLens 2 ' 'nizi bir BILGISAYARA bağlayın.
1.  Yüklemek istediğiniz sertifika dosyasını HoloLens 2 ' de bir konuma yerleştirin.
1.  **Ayarlar uygulaması > güncelleştirme & güvenlik > sertifikaları**' na gidin ve sertifika yüklemeyi seçin.
1.  **Dosyayı Içeri aktar** ' a tıklayın ve sertifikayı kaydettiğiniz konuma gidin.
1.  **Depo konumunu** seçin.
1.  **Sertifika deposunu** seçin.
1.  **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklü olması gerekir.

#### <a name="to-remove-a-certificate"></a>Bir sertifikayı kaldırmak için: 
1. **Ayarlar uygulama > güncelleştirme ve güvenlik > sertifikaları '** na gidin.
1. Arama kutusunda Sertifikayı ada göre arayın.
1. Sertifikayı seçin.
1. **Kaldır** 'a tıklayın
1. Onay sorulduğunda **Evet** ' i seçin.

![Ayarlar uygulamasındaki sertifika Görüntüleyicisi](images/certificate-viewer-device.jpg)

![Sertifika Kullanıcı arabiriminin bir sertifikayı yüklemek için nasıl kullanılacağını gösteren resim](images/certificate-device-install.jpg)

Bu bilgiler, daha sonra [Yeni bir Sertifika Yöneticisi sayfasında](certificate-manager.md)bulunabilir.

### <a name="auto-launch-provisioning-from-usb"></a>Sağlamayı USB 'den otomatik olarak başlatma

- Otomatik süreçler, sağlama paketleri içeren USB sürücüleri OOBE sırasında kullanıldığında daha az kullanıcı etkileşimine izin verir.

Bu sürümden önce, bir düğme bileşimini kullanarak sağlamak için kullanıcıların, OOBE sırasında sağlama ekranını el ile başlatması gerekiyordu. Artık kullanıcılar, USB depolama sürücüsünde bir sağlama paketi kullanarak düğme bileşimini atlayabilir. 

1. OOBE 'nin ilk ınteractable 'ı sırasında sağlama paketiyle USB sürücüsünü takın
1. Cihaz sağlanmaya hazır olduğunda, isteği sağlama sayfasıyla otomatik olarak açar. 

Note: cihaz önyüklenirken bir USB sürücü takıldıysa, OOBE mevcut USB depolama cihazını numaralandırır ve takılmakta olan ek için izleme de yapılır.

OOBE sırasında sağlama paketleri uygulama hakkında daha fazla bilgi için, [HoloLens sağlama](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) belgelerini ziyaret edin.

[BIR USB 'den otomatik başlatma sağlama ile](hololens-provisioning.md#auto-launch-provisioning-from-usb) ilgili ek bilgiler, Hololens sağlama belgelerinde bulunabilir.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE 'de sağlama paketlerini otomatik onaylama
- Otomatik süreç daha az kullanıcı etkileşimine izin verirken, sağlama paketi sayfası görüntülendiğinde, listelenen tüm paketleri otomatik olarak uygular.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerinin uygulanması için OOBE 'nin otomatik olarak başlatılması için önce 10 saniye geçmesi gerekir. Kullanıcılar, bekledikleri paketleri doğruladıktan sonra bu 10 saniye içinde yine de [onaylama veya iptal](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) edebilir.

### <a name="automatic-provisioning-without-using-ui"></a>Kullanıcı arabirimi kullanmadan otomatik sağlama
- Sağlama için azaltılmış cihaz etkileşimleri için otomatik süreçler birleştirildi. 

Bir Kullanıcı, USB cihazlarından sağlamanın otomatik olarak başlatılmasını ve sağlama paketlerinin otomatik onayını birleştirerek, cihazın kullanıcı arabirimini kullanmadan veya hatta cihazı takmadan HoloLens 2 cihazlarını otomatik olarak sağlayabilir. Birden çok cihaz için aynı USB sürücüsünü ve sağlama paketini kullanmaya devam edebilirsiniz. Bu, aynı alanda aynı anda birden çok cihazı dağıtmak için yararlıdır. 

1. [Windows yapılandırma Tasarımcısı](https://www.microsoft.com/store/productId/9NBLGGH4TX22)'nı kullanarak [bir sağlama paketi oluşturun](hololens-provisioning.md) . 
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ' ye [19041,1361 veya daha yeni bir derleme](https://aka.ms/hololens2previewdownload)yapın. 
1. [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın yanıp sönmesi TAMAMLANDıĞıNDA, USB-C kablonuzu sökün. 
1. USB sürücünüzü cihaza takın.
1. HoloLens 2 cihazı OOBE 'de önyüklendiğinde, USB sürücüsünde sağlama paketini otomatik olarak algılayacak ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz, sağlama paketini otomatik olarak uygular. 

Cihazınız artık yapılandırıldı ve [sağlama başarılı ekranı görüntülenir](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Wi-Fi bağlantısı ile Autopilot kullanma
- Wi-Fi bağlı cihazlarda Autopilot çalışmasını etkinleştirerek, USB-C bağdaştırıcılarının Ethernet ile donanım ihtiyaçlarını azaltmaya gereksinimi ortadan kaldırılmıştır.

Artık OOBE sırasında, HoloLens 2 ' yi Wi-Fi ile bağladığınızda, OOBE cihaz için bir Autopilot profili denetlecektir. Bir tane bulunursa AAD JOIN ve kayıt akışının geri kalanını tamamlayacak şekilde kullanılacaktır. Diğer bir deyişle, Ethernet ile USB-C veya Wi-Fi USB-C adaptörünün kullanılması artık bir gereksinim değildir, ancak OOBE 'nin başlangıcında sağlanmışsa çalışmaya devam ederler. [HoloLens 2 cihazları Için Autopilot](hololens2-autopilot.md)hakkında daha fazla bilgi edinin.

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot
- Cihaz sıfırlama veya refflash aracılığıyla bile, cihazı kiracıya kilitleyerek kuruluşun kiracısındaki cihazları tutar. , Sağlama yoluyla içinde hesap oluşturmayı engelleyerek daha fazla güvenlik ile. 

HoloLens 2 cihazları artık [Windows holographic sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2)Itibariyle TenantLockdown CSP 'yi desteklemektedir. 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. Bir ınantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer yeniden yanıp sönmeye karşın, işletim sistemi güncelleştirmeleri, vb. cihazda kalır. 

Bir TenantLockdown CSP 'Ler, HoloLens 2 üzerinde true olarak ayarlandığında, ağ bağlantısından sonra OOBE, Autopilot profilinin başarıyla indirilip uygulanmasını bekler. 

Bir TenantLockdown CSP 'Ler, HoloLens 2 üzerinde true olarak ayarlandığında, OOBE 'de aşağıdaki işlemlere izin verilmez: 
- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD JOIN işlemi gerçekleştiriliyor 
- Cihaza kimin sahip olduğunu OOBE deneyiminde seçme 

#### <a name="how-to-set-this-using-intune"></a>Bu Intune kullanılarak nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe düğümü için true değerini belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla kiracı kilidi ayarlanıyor](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın. 

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandıktan sonra, TenantLockdown etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune 'u kullanarak HoloLens 2 üzerinde TenantLockdown 'ın talep ırenetworkınoobe ayarı nasıl yapılır? 
1. Yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2 ' i kaldırın. 

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe için false belirtin. OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![Intune 'da OMA URI aracılığıyla talep ırenetworkınoobe ayarının false olarak ayarlanmasına yönelik ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın. 

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandıktan sonra, TenantLockdown etkileri devre dışı bırakılır. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Autopilot profili, maantlockdown true olarak ayarlandıktan sonra bir HoloLens üzerinde atanmazsa, OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilmek için süresiz olarak bekler ve aşağıdaki iletişim kutusu sunulacaktır. TenantLockdown 'in etkilerini kaldırmak için, önce Autopilot yalnızca bir cihaz özgün kiracısına kaydedilmelidir ve eski adımda açıklandığı gibi, TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önce bu, önkoşul olarak ayarlanmalıdır. 

![Cihazda ilke uygulandığında cihaz içi görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık, [Tenantlockdown CSP ve Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)altında Autopilot 'in geri kalanının yanı sıra bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel atanan erişim – bilgi noktası modu
- Bilgi noktası için, sistem düzeyinde bilgi noktası modu uygulayan yeni bilgi noktası yöntemi etkinleştirilerek kimlik yönetimi azaltıldı.

Bu yeni özellik, bir BT yöneticisinin sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için bir HoloLens 2 cihazı yapılandırmasını sağlar, sistemde herhangi bir kimlikle hiçbir benzeşim yoktur ve cihazda oturum açan herkese uygulanır. [HoloLens Global atanan erişim bilgi noktasında](hololens-global-assigned-access-kiosk.md)bu yeni özellik hakkında ayrıntılı bilgi edinin.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Birden çok uygulama bilgi noktası modunda bir uygulamayı otomatik olarak başlatma 
- Otomatik uygulama başlatma ile odaklanmış deneyim, bilgi noktası modu deneyimleri için seçilen kullanıcı arabirimi ve uygulama seçimlerini daha da artırır.

Yalnızca birden çok uygulama bilgi noktası modu için geçerlidir ve atanan erişim yapılandırmasında aşağıda vurgulanan öznitelik kullanılarak otomatik başlatılacak şekilde yalnızca 1 uygulama belirlenebilir. 

Uygulama, Kullanıcı oturum açtığında otomatik olarak başlatılır. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri
- Bilgi noktası modu hatalarında kullanılabilir uygulamaları ortadan kaldırarak daha güvenli bilgi noktası modu. 

Bilgi noktası modu ' nda hatalarla karşılaşmadan önce, HoloLens, Başlat menüsündeki tüm uygulamaları göstermek için kullanılır. Artık Windows holographic Version 20H2 sürümünde, başlangıç menüsünde aşağıdaki şekilde hiçbir uygulama gösterilmez: 

![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Ilkeleri
- Cihazı yönetmek için özel olarak HoloLens için oluşturulan cihaz yönetim seçenekleri. 

Windows holographic Version 20H2 ' de HoloLens 2 cihazları için yeni karma gerçeklik ilkeleri oluşturulmuştur. Yeni denetlenebilir ayarlar şunlardır: parlaklık ayarlanıyor, birim ayarlama, karma gerçeklik halinde ses kaydı devre dışı bırakma, tanılama toplandığında ayarlama ve AAD grup üyeliği önbelleği.  

| Yeni HoloLens ilkesi                                | Açıklama                                                                               | Notlar                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Mixedreality\parlatnessbuttondisabled              | Parlaklık düğmelerinin devre dışı olmasına izin verir ve bu sayede parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı olmasına izin verir, böylece birim değişmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| Mixedreality\mikro phonedisabled                    | HoloLens 2 ' de ses kaydı mümkün olmayacak şekilde Mikrofonu devre dışı bırakır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin toplanabilmesi için davranışını denetler.                               | 0 devre dışı, 1 cihaz sahipleri için etkin, 2 tümü için etkin (varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD gruplarını hedefleyen bilgi noktası için Azure AD grup üyeliği önbelleğinin kaç gün kullandığını denetler. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma
- 60 gün boyunca AAD gruplarıyla birlikte kullanılacak çevrimdışı bilgi paketleri etkinleştirildi.

Bu ilke, kaç gün boyunca Azure AD grup üyeliği önbelleğinin oturum açmış kullanıcı için Azure AD gruplarını hedefleyen atanan erişim yapılandırmalarında kullanılmasına izin verileceğini denetler. Bu ilke değeri 0 ' dan büyük bir değere ayarlandıktan sonra, önbellek kullanılır.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az-0 gün  
Maksimum 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedefleyen bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bunu HoloLens cihazlarına atayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayarlayan ve HoloLens cihazlarına atayan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri, OMA-URI metin kutusunda./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilmelidir
    1. Değer, izin verilen Min/Max arasında olabilir.
1. HoloLens cihazlarını kaydedin ve her iki yapılandırmanın cihaza uygulandığını doğrulayın. 
1. Internet 'in kullanılabildiği Azure AD User 1 oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. Artık Azure AD Kullanıcı 1, HoloLens 'i çevrimdışı alabilir ve ilke değeri X gün sayısı için izin verdiği sürece bilgi noktası modu için kullanabilir. 
1. 4 ve 5. adım, diğer tüm Azure AD kullanıcıları için yinelenebilir. burada anahtar noktası, herhangi bir Azure AD kullanıcısının Internet 'i kullanarak cihaza oturum açması gerekir. bu sayede, bilgi noktası yapılandırmasının hedeflediği Azure AD grubuna üye olduklarını belirleyebiliriz. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilene kadar "bağlantısı kesik" ortamlarda bahsedilen hata davranışı ile karşılaşırsınız. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri
- Kullanıcıların, sağlama paketleri ekleme veya kaldırma gibi belirli cihaz yönetim ilkelerini yönetmesine olanak tanır.

HoloLens 2 cihazlarının daha fazla yönetim seçeneklerine izin veren yeni etkinleştirilen ilkeler. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni ilke [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

> [!NOTE]
> Bu, [Remotelock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)ile ilgili olarak, Hololens yalnızca./Vendor/MSFT/RemoteLock/Lock yapılandırmasını destekleyecektir. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırma desteklenmez.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri
- HoloLens 'in güç ilkeleriyle uyku moduna geçme veya kilitlenme sırasında daha fazla seçenek. 

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumlarını denetlemesine olanak tanır. Her ilke hakkında daha fazla bilgi edinmek için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [Displayofftimeoutonpili](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [Displayofftimeoutpluggedın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [Enerji Gysaverbatteryıthresholdonpili](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                             |
|     [Enerji Gysaverbatteryıthresholdpluggedın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                          |
|     [Standbytimeoutonpili](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [Standbytimeoutpluggedın](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Bu iki yeni ilke Displayofftimeoutonpili ve Displayofftimeoutpluggedın [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

> [!NOTE]
> HoloLens 2 ' de tutarlı deneyim için lütfen Displayofftimeoutonpili ve Standbytimeoutonpili değerlerinin aynı değer olarak ayarlandığından emin olun. Aynı, Displayofftimeoutpluggedın ve Standbytimeoutpluggedın için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için [bkz. ekran, uyku ve hazırda bekleme boşta zamanlayıcılar](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens için yeni etkinleştirilen güncelleştirme ilkeleri
- Güncelleştirmelerin yüklenmesi için daha fazla seçenek veya güncelleştirme için güncelleştirmeleri Duraklat düğmesini devre dışı bırakma.

Bu güncelleştirme ilkeleri artık HoloLens 2 cihazlarında etkinleştirilmiştir:
-   [Güncelleştirme/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Güncelleştirme/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Güncelleştirme/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Güncelleştirme/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Bu güncelleştirme ilkelerine ilişkin tüm ayrıntılar ve HoloLens cihazları için bunları kullanma, [HoloLens güncelleştirmelerini yönetme](hololens-updates.md)bölümünde buradan okunabilir.

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 için etkinleştirilmiş ayarlar sayfası görünürlüğü
- Ayarlar uygulamasında artırılan, sınırlı sayıda sayfanın gösterilmesi için karışan UI denetimi.

Artık, BT yöneticilerinin sistem ayarları uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalar için yapılmasına izin veren bir ilkeyi etkinleştirdik. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 ' de özelleştirebileceğiniz sayfa ayarlarını öğrenmek için lütfen [ayarlar Uri 'leri sayfasını](settings-uri-list.md)ziyaret edin. 
 
![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu
Araştırma modundayken, HoloLens 2 bilgisayar Vision Research için bir pokatlanmış araç haline gelir. Önceki sürümlere kıyasla, HoloLens 2 araştırma modunun aşağıdaki avantajları vardır:
-   HoloLens (1. gen) araştırma modunda sunulan sensörlerden ek olarak, artık bir ivme ölçer, jroscope ve manyetik tometre dahil olmak üzere IMU algılayıcı erişimi sağlıyoruz.
-   HoloLens 2, araştırma moduyla birlikte kullanılabilecek yeni yetenekler sağlar. Özellikle, daha zengin bir denemeleri kümesini sunabilme ve göz önünde bulundurun.

Araştırmacılar artık, bu dış kullanıma yönelik Ham görüntü algılayıcı akışlarına erişmek için HoloLens cihazlarında araştırma modunu etkinleştirme seçeneğine sahiptir. HoloLens 2 için araştırma modu, ivometer, jroscope ve manyetik tometer okumaları için de erişim sağlar. Kullanıcıların gizliliğini korumak için, ham göz izleme kamera görüntüleri araştırma modu aracılığıyla kullanılamaz, ancak var olan API 'Ler aracılığıyla göz korunun yönü mevcuttur.

Daha fazla teknik ayrıntı için [araştırma modu belgelerine](https://docs.microsoft.com/windows/mixed-reality/research-mode) göz atın.

### <a name="recording-length-increased"></a>Kayıt uzunluğu artırıldı
Müşteri geri bildirimi nedeniyle, [karma gerçeklik yakalamalarından](holographic-photos-and-videos.md)oluşan kayıt uzunluğunu artırdık. Karma Gerçeklik yakalamaları artık varsayılan olarak 5 dakikaya göre sınırlandırılamaz, bunun yerine kullanılabilir disk alanına göre en fazla kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanının %80 ' suna kadar kullanılabilir disk alanına göre maksimum video kaydetme süresini tahmin edecektir.

> [!NOTE]
> HoloLens, aşağıdakilerden biri gerçekleşirse varsayılan video kayıt uzunluğunu (5 dakika) kullanır:
> - Tahmini en fazla kayıt süresi varsayılan 5 dakikadan daha küçüktür.
> - Kullanılabilir disk alanı, toplam disk alanının %20 ' inden daha az.

Tüm gereksinimleri [holographic fotoğraflarınız ve videolar](holographic-photos-and-videos.md#maximum-recording-length) belgelerimizde bulabilirsiniz. 

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- OOBE 'deki daha fazla ekran artık koyu modda.
- Daha fazla bilgi edinin çevrimiçi gizlilik bildirimine en son çevrimiçi işaret etmelidir.
- Kullanıcıların, sağlama paketleri aracılığıyla VPN profilleri sağlayabildiği bir sorun oluştu.
- VPN bağlantısı için sabit proxy yapılandırması sorunu.
- AllowUsbConnection için NCM için MDM aracılığıyla USB işlevlerinin numaralandırılmasını devre dışı bırakma ilkesi güncelleştirildi.
- Cihaz [tek uygulama bilgi noktası](hololens-kiosk.md)olarak ayarlandığında, bir HoloLens cihazının Medya Aktarım Protokolü (MTP) üzerinden dosya Gezgini 'nde gösterilmesini engelleyen bir sorun oluştu. MTP (genel olarak USB bağlantısının), [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ilkesi kullanılarak hala devre dışı bırakılabileceğini unutmayın.
- Başlangıç menüsündeki simgelerin bilgi noktası modunda doğru şekilde ölçeklendirdiği bir sorun düzeltildi.
- Azure AD gruplarına hedeflenmiş bilgi noktası modu 'na engel olan HTTP önbelleklemesi nedeniyle bir sorun düzeltildi.
- Kullanıcıların, Geliştirici modunu devre dışı bırakmadığı ve yeniden etkinleştirmedikleri takdirde, sağlama paketleri ile Geliştirici modunu etkinleştirdikten sonra çift bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows holographic, sürüm 1903-Kasım 2020 güncelleştirme
- Derleme 18362,1085

Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son özellik yayın derlemesi Windows holographic, sürüm 20H2 ' yi denemenizi öneririz.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows holographic, sürüm 2004-Ekim 2020 güncelleştirme
- Derleme 19041,1124
 
Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çalışma zamanı sistem hatasına neden olan gereksiz bir denetim kaldırıldı.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows holographic, sürüm 1903-Ekim 2020 güncelleştirme
- Derleme 18362,1081

Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows holographic, sürüm 2004-Eylül 2020 güncelleştirme
- Derleme 19041,1117

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Appxmanifest 'de SupportsMultipleInstances = "true" olduğunda Visual Studio 'Nun bir uygulamada hata ayıklamasını engelleyen bir sorunu giderir.
- Bu sürüm, ağ proxy 'si üzerinden başarısız olan Internet algılamayı ele almak için NCSı proxy algılama düzeltmesini içerir. NCSı, Internet bağlantısı algılaması için makine ara sunucusunu ve profil başına proxy 'yi kullanabilir. Kullanıcı başına proxy, gelecek sürümde NCSı tarafından desteklenecektir.
- Çoğu Windows Mixed Reality cihazlarında, kullanıcının başı ileri doğru görünen bir bağımsız konumda olduğunda, ileri yönlü vektör, zemin için paraleldir. Ancak, HoloLens 2 ' nin önceki sürümleri, vektör, ideal yönlendirmeye göre birkaç derece aşağı doğru bir şekilde aşağı hizalanmış şekilde, Görüntü panellerinin dikey olmasını sağlar. HoloLens 2 ' nin daha yeni sürümleri, form faktörleri arasında anlam tutarlılığı sağlamak için bunu düzeltmelidir.
- Belirli senaryolarda daha az izleme kaybına neden olacak gelişmiş ve izleme sağlamlık.
- Bu sürümde, video yakalama sorunlarına katkıda bulunan ses zaman damgası kalitesini geliştirmek için bir çözüm bulunur.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows holographic, sürüm 1903-Eylül 2020 güncelleştirme
- Derleme 18362,1079

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çoğu Windows Mixed Reality cihazlarında, kullanıcının başı ileri doğru görünen bir bağımsız konumda olduğunda, ileri yönlü vektör, zemin için paraleldir. Ancak, HoloLens 2 ' nin önceki sürümleri, vektör, ideal yönlendirmeye göre birkaç derece aşağı doğru bir şekilde aşağı hizalanmış şekilde, Görüntü panellerinin dikey olmasını sağlar. HoloLens 2 ' nin daha yeni sürümleri, form faktörleri arasında anlam tutarlılığı sağlamak için bunu düzeltmelidir.
- Belirli senaryolarda daha az izleme kaybına neden olacak gelişmiş ve izleme sağlamlık.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows holographic, sürüm 2004-Ağustos 2020 güncelleştirme
- Derleme 19041,1113

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Ayarlar uygulaması artık kullanıcıyı Iris kayıt veya göz Izleme ayarlaması deneyimlerine göre takip edemeyecektir.
- Bir sağlama paketinin, cihazı yeniden adlandıran ve diğer eylemleri gerçekleştiren (bir ağa bağlanma gibi) bir hata düzeltildi, yeniden adlandırma nedeniyle cihaz yeniden başlatıldıktan sonra diğer eylemleri gerçekleştiremeyebilir.
- Görsel kaliteyi artırmak için ilk cihaz kurulumu akışlarının değiştirilen renk şeması.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows holographic, sürüm 1903-Ağustos 2020 güncelleştirme
- Derleme 18362,1074

Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows holographic, sürüm 2004-Haziran 2020 güncelleştirme
- Derleme 19041,1109

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Geliştiriciler artık cihaz portalının etkinleştirilmesi veya devre dışı bırakılması arasında güvenli bir bağlantı yapılmasını tercih edebilir.
- Uygulama, işletim sistemi güncelleştirmelerinden sonra başlatıldığında geliştirildi.
- Varsayılan gelen kutusu parlaklığı yüzde 100 olarak değiştirildi.
- HoloLens 2 ' de Windows cihaz portalı için HTTPS iletimi hakkında bir sorun oluştu.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows holographic, sürüm 1903-Haziran 2020 güncelleştirme
- Derleme 18362,1071

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İzlemeyi kaybetmekte veya geri alma sırasında Unity uygulamalarında hologramlar ortadan silinmesine neden olabilecek bir sorun düzeltildi.
- Özel HoloLens uygulamalarına, bazı cihazlarda donanım hızlandırmasından oluşan HoloLens öykünücüsünü kullanırken kabuğa geri çökmesine neden olan bir sorun düzeltildi.
- HoloLens 2 ' de Windows cihaz portalı için HTTPS iletmeyle ilgili bir sorun oluştu.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows holographic, sürüm 2004-Haziran 2020 güncelleştirme
- Derleme 19041,1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC video etkisi*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (modern kulaklık))
  - *MRC ses efekti* üzerinde:
    - Loopgeri kazanç (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "uygulama sesi kazancı" değeri)
    - Mikro Phonekazancı (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "MIC ses kazancı" değeri)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmak için bir hata düzeltildi. Özellikle, bu onarım, **Başlat** menüsü görüntülenirken kayıtta ses bozuklubir şekilde ortadan kaldırmalıdır.
- Kayıtlı videolarda, iyileştirilmiş hologram kararlılığı.
- Cihaz, birden çok gün için bekleme durumunda kapatıldıktan sonra karma gerçeklik yakalamanın video kaydedemediği bir sorun çözüldü.
- HolographicSpace. Uservarlığına yönelik API genellikle Unity uygulamaları için devre dışıdır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilmiş olsa bile, bazı uygulamaların, vizörü çevrildikten sonra duraklamasını engelleyen bir sorunu önler. API artık 2018.4.18 ve üzeri ve 2019.3.4 ve üzeri Unity sürümleri için etkinleştirilmiştir.
- Cihaz portalına bir Wi-Fi bağlantısı üzerinden eriştiğinizde, bir Web tarayıcısı geçersiz bir sertifika nedeniyle erişimini engelleyebilir. Tarayıcı, daha önce güvenilir olsa bile "ERR_SSL_PROTOCOL_ERROR," gibi bir hata bildirebilir. Bu durumda, güvenlik uyarılarını yok saymaya yönelik bir seçenek olmadığından cihaz portalına ilerleyemiyorum. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası önceden indirildiyse ve tarayıcı güvenliği uyarılarını kaldırmak için bir PC 'de güvenilir ise ve SSL hatası oluşursa, tarayıcı güvenliği uyarılarını karşılamak için yeni sertifikanın indirilip güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilme çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **sistem**  >  **hologragram** ' de, cihazların cihaz kapandığında karma gerçeklik ana 'dan tüm hologramlar otomatik olarak kaldırılmasına olanak sağlayan bir ayar eklendi.
- HoloLens öykünücüsünde siyah işlemek için piksel biçimini değiştiren HoloLens uygulamalarına neden olan bir sorun düzeltildi.
- Iris oturum açma sırasında kilitlenmeye neden olan bir hata düzeltildi.
- Zaten mevcut uygulamalar için yinelenen mağaza indirmeleri hakkında bir sorun düzeltildi.
- Modern uygulamaların Microsoft Edge 'i sürekli açmasını önleyen bir hata düzeltildi.
- 1903 sürümünden güncelleştirmeden sonra ilk önyüklemesinde Fotoğraflar uygulamasının başlatıldığında bir sorun düzeltildi.
- İyileştirilmiş performans ve güvenilirlik.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows holographic, sürüm 1903-Haziran 2020 güncelleştirme
- Derleme 18362,1064

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydediciler belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC video etkisi*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (modern kulaklık))
  - *MRC ses efekti* üzerinde:
    - Loopgeri kazanç (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "uygulama sesi kazancı" değeri)
    - Mikro Phonekazancı (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "MIC ses kazancı" değeri)
- HolographicSpace. Uservarlığına yönelik API genellikle Unity uygulamaları için devre dışıdır. Bu davranış, arka planda çalıştırılacak ayar etkin olsa bile, bazı uygulamaların, vizörü çevrilirse duraklamasına neden olan bir sorunu önler. Artık, 2018.4.18 ve üzeri, 2019.3.4 ve üzeri Unity sürümleri için API etkinleştirilmiştir.
- HoloLens öykünücüsünde siyah işlemek için piksel biçimini değiştiren HoloLens uygulamalarına neden olan bir sorun düzeltildi.
- 1903 sürümünden güncelleştirmeden sonra ilk önyüklemeler bölümünde Fotoğraflar uygulamasının ortaya çıkmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows holographic, sürüm 2004  
- Derleme-19041,1103

HoloLens 2, *Windows holographic, sürüm 2004* için Mayıs 2020 ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5 g/LTE etkin noktaları Için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni yeteneklerin bir konağını içerir. En son sürüme güncelleştirmek için **Ayarlar**   uygulamasını açın, **güncelleştirme & güvenliği**' ne gidin ve  **Güncelleştirmeleri denetle**   düğmesini seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak üretim için yeni cihazları önceden yapılandırma ve sorunsuz şekilde ayarlama                 |
|       FıDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamayı etkinleştirmek üzere FIDO2 güvenlik anahtarlarına yönelik destek            |
|       Geliştirilmiş sağlama                      |          Bir USB sürücüsünden HoloLens uygulamanıza sorunsuz bir sağlama paketi uygulama                              |
|       Uygulama yüklemesi durumu                 |          Uygulamalar için Ayarlar uygulamasında yüklenecek durum denetimi MDM aracılığıyla HoloLens 2 ' ye gönderildi               |
|       Yapılandırma hizmeti sağlayıcıları (CSP)   |          Yönetici denetim yeteneklerini iyileştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği, 5G/LTE desteğini sunar                                    |
|       Koyu uygulama modu                              |          Koyu ve hafif modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir, görüntüleme deneyimini geliştirir        |
|       Sesli komutlar                             |          HoloLens eller ücretsiz olarak denetlemek için ek sistem ses komutları desteği                           |
|       İzleme geliştirmeleri                 |          İzleme geliştirmeleri, düğmeleri ve 2B kurşun etkileşimini daha doğru hale getirir                        |
|       Kalite iyileştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik iyileştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot için destek

HoloLens 2 için Windows Autopilot cihaz satış kanalının, HoloLens 'i Intune kiracınıza önceden kaydetmelerini sağlar. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazırsınız demektir. Self-Deployment 'ın avantajlarından yararlanmak için, cihazın bir USB-C-Ethernet kullanarak kurulum 'daki ilk ekran sırasında ağa bağlanması gerekir.

Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin.
1. Cihazı Microsoft Intune (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.
1. Cihaza yönelik ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlayın.
1. Kullanıcıya oturum açma ekranını sunun.

[Windows Autopilot for HoloLens 2 değerlendirme kılavuzunda](https://docs.microsoft.com/hololens/hololens2-autopilot)daha fazla bilgi edinin.

*AutoPilot önizlemesini şimdi katmak için hesap yöneticinize başvurun. Autopilot için kullanıma sunulan cihazlar yakında gönderim yapmaya başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar bir HoloLens cihazını iş veya okul ortamındaki diğer kullanıcılarla paylaşır. Bu nedenle, kullanıcıların uzun Kullanıcı adlarını ve parolalarını yazmadan kolayca kolayca olanak sağlamak önemlidir. Hızlı kimlik çevrimiçi (FIDO), kuruluşunuzdaki herkesin (Azure AD kiracısı) Kullanıcı adı veya parola girmeden sorunsuz bir şekilde oturum açmasını sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktörüyle gelebilmesi için bir "unphishable" standartlara dayalı bir kimlik doğrulama yöntemidir. FıDO, passwordless kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kendi kaynaklarında Kullanıcı adı veya parola olmadan oturum açmasına olanak tanır. Bunun yerine, bir dış güvenlik anahtarı veya bir cihazda yerleşik bir platform anahtarı kullanırlar.

Başlamak için bkz. [passwordless güvenlik anahtarı oturum açma 'Yı etkinleştirme](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Sağlama paketleri, Hololens 'in hazır deneyim yerine bir yapılandırma dosyası aracılığıyla HoloLens yapılandırmasını ayarlamanıza olanak sağlar. Daha önce, sağlama paketlerinin HoloLens iç belleğine kopyalanması gerekiyordu. Artık bir USB sürücüde olabilir, böylece birden çok HoloLens cihazlarda yeniden kullanılması kolaylaşır ve cihazları paralel olarak sağlayabilirsiniz. Sağlama paketleri artık cihaz yönetimine kaydolmak için bir alanı destekledikten sonra, sağlamadan sonra el ile kurulum gerektirmez.

Denemek için:

1. Windows Mağazası 'ndan Windows yapılandırma Tasarımcısı 'nın en son sürümünü bilgisayarınıza indirin.
1. HoloLens **cihazlarının** sağlamasını  >  **HoloLens 2 cihazları** sağla ' yı seçin.
2. Yapılandırma profilinizi oluşturun. Ardından, bir USB-C depolama cihazına oluşturulan tüm dosyaları kopyalayın.
3. USB-C cihazını herhangi bir isteğe tam flaşlı HoloLens 'e takın. Ardından,   +  sağlama paketinizi uygulamak için ses **tasarrufu** düğmelerine basın.

### <a name="line-of-business-application-install-status"></a>İş kolu uygulaması yüklemesi durumu

İş kolu uygulamaları için MDM uygulama dağıtımı ve yönetimi, HoloLens için kritik öneme sahiptir. Yöneticiler ve kullanıcıların, denetim ve Tanılama için uygulama yüklemesi durumunu görüntülemesi gerekir. Bu sürümde, **Ayarlar**  >  **hesaplarına**  >  **erişim iş veya okul**  >  **hesabınıza hesap bilgilerinize tıklama hakkında**  >  daha fazla ayrıntı ekledik.

### <a name="additional-csps-and-policies"></a>Ek CSP 'Ler ve ilkeler

Bir [yapılandırma hizmeti sağlayıcısı (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) bir cihazdaki yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu sürümde, denetim yöneticilerinin dağıtılan HoloLens cihazlarına sahip olmasını artıracak daha fazla ilke desteği ekledik. HoloLens tarafından desteklenen CSP 'lerin listesi için bkz. [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

Bu sürümdeki yenilikler:

**İlke CSP 'si** 

Ilke yapılandırma hizmeti sağlayıcısı, kuruluşun Windows cihazlarda ilkeleri yapılandırmasına olanak sağlar. Bu sürümde, HoloLens için burada listelenen yeni ilkeler ekledik. Daha fazla bilgi için bkz. [HoloLens 2 tarafından desteklenen Ilke CSP 'leri](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

NetworkQoSPolicy yapılandırma hizmeti sağlayıcısı, ağ hizmet kalitesi (QoS) ilkeleri oluşturur. QoS ilkesi, bir dizi eşleşen koşulu temel alarak ağ trafiği üzerinde bir dizi eylem gerçekleştirir. Daha fazla bilgi için bkz. [Networkqospolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE tethered cihazları için genişletilmiş USB Ethernet desteği

5G/LTE telefonları ve Wi-Fi etkin noktalar gibi bazı mobil geniş bant cihazlarını USB üzerinden HoloLens 2 ' ye olduklarında etkinleştirmek için destek eklenmiştir. Bu cihazlar artık farklı bir Ethernet bağlantısı olarak **ağ ayarlarında** görüntülenmektedir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmez.) Bu işlevsellik Wi-Fi kullanılabilir olmadığında yüksek bant genişliğine sahip bağlantılara izin verebilir ve Wi-Fi internet paylaşımı yeterince iyi değildir. Desteklenen USB cihazları hakkında daha fazla bilgi edinmek için bkz. [Bluetooth ve USB-C cihazlarına bağlanma](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>İzleme geliştirmeleri

Bu sürüm çeşitli izleme geliştirmeleri içerir:

- **İşaret pozu kararlılığı:** Sistem artık, Palm tarafından occlukal aldığında Dizin parmak yerini geri alır. Bu değişiklik, düğmeleri gönderdiğinizde, içerik yazarken ve daha fazlasını yaparken doğruluğu artırır! 
- **Azaltılmış, yanlışlıkla hava dokunmalar:** Hava dokunma hareketini algılamayı geliştirdik. Artık birkaç yaygın senaryoda (örneğin, ellerinizi yüzlerinizi bıraktığınızda) daha az yanlışlıkla etkinleştirme vardır.
- **Kullanıcı anahtarı güvenilirliği:** Bir cihaz paylaştığınızda el ile sistem boyutunu güncelleştirmek daha hızlı ve daha güvenilirdir.
- **Azaltılmış el çalma:** Sensörlerden ikiden fazla elinin bulunduğu durumların işlenmesini geliştirdik. Birden çok kişi birlikte çalışıyorsa, izlenen kişinin kullanıcıdan sahnedeki başka birinin adına "atlayacağı" bir şansınız daha düşüktür.
- **Sistem güvenilirliği:** Cihaz yüksek yük altında olduğunda bir yandan izlemenin çalışmayı durdurmasına neden olan bir sorun düzeltildi.

### <a name="dark-mode"></a>Koyu mod

Birçok Windows uygulaması artık koyu ve hafif modları desteklemektedir. HoloLens 2 kullanıcıları, her ikisini de destekleyen uygulamalar için varsayılan modu seçebilirler. Güncelleştirme sonrasında, varsayılan uygulama modu "koyu" olur, ancak bu ayarı kolayca değiştirebilirsiniz: **Ayarlar**  >  **sistem** renkleri ' ne gidin  >    >  **Varsayılan uygulama modunu seçin**. 

Bu "yerleşik" uygulamalar koyu modunu destekler: 

- Ayarlar 
- Microsoft Store 
- Posta 
- Takvim 
- Dosya Gezgini 
- Geribildirim Merkezi 
- OneDrive 
- Fotoğraflar 
- 3B görüntüleyici 
- TV & Filmler 

![Koyu modda Windows döşeli](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Sistem ses komutları

Artık, cihazdaki herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için bkz. [HoloLens 'i çalıştırmak için sesinizi kullanma](https://docs.microsoft.com/hololens/hololens-cortana). Ayrıca, [HoloLens 2 Için desteklenen diller](https://docs.microsoft.com/hololens/hololens2-language-support)bölümüne bakın.  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

Güncelleştirilmiş uygulama, cihazlarınız arasında daha fazla işlem yapmanıza yardımcı olmak için Microsoft 365 ile tümleşir (Şu anda yalnızca US-English). HoloLens 2 ' de Cortana, birim ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklememektedir. Bu seçenekler artık yeni sistem ses komutları tarafından desteklenmektedir. [Blogumuza](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)yeni Cortana uygulaması hakkında daha fazla bilgi edinin.

### <a name="quality-improvements-and-fixes"></a>Kalite iyileştirmeleri ve düzeltmeleri

Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:  
- Etkin bir görüntüleme ayarlama sistemi sunuldu. Bu özellik hologragram kararlılığını ve hizalamasını geliştirir. Başlarınızı yan yana hareket ettirmek için artık yerinde kalabilirler.
- HoloLens 'e Wi-Fi akışının düzenli aralıklarla kesintiye uğradığından oluşan hata düzeltildi. Bir uygulama düşük gecikmeli akış için ihtiyacı olduğunu gösteriyorsa, [Setsocketmediastreamingmode işlevini](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)çağırarak bu çözümü uygulayın.
- Araştırma modunda akış sırasında oluşan bir cihaz askıda kalması düzeltildi.
- Bir oturum sürdürülürken, bazı durumlarda oturum açma ekranında doğru kullanıcının görüntülenmediğini bir hata düzeltildi.
- Kullanıcıların MDM günlüklerini **ayarlarla** dışarı aktarmasında bir sorun düzeltildi.
- Hazır kurulum 'un doğruluk izlemenin bekleninden daha düşük olması nedeniyle oluşan bir sorun düzeltildi.
- Göz izleme alt sisteminin belirli koşullar altında başlatma veya ayarlama yapma işleminin başarısız olduğu bir sorun düzeltildi.
- Zaten kalibre edilmiş bir kullanıcı için göz ayarlamaya sorulacak bir sorun düzeltildi.
- Bir sürücünün göz ayarlama sırasında çöktüğünde bir sorun düzeltildi.
- Yinelenen güç düğmesi bastığı bir sorun düzeltildi, 60 saniyelik bir sistem zaman aşımı ve kabuk kilitlenmesine neden olabilir.
- Derinlik arabellekleri için iyileştirilmiş kararlılık.
- Geri bildirim merkezinde, kullanıcıların daha kolay geri bildirimde bulunmak için bir **paylaşma** düğmesi eklendi.
- Roboryardım 'ın doğru şekilde yüklendiği bir hata düzeltildi.

### <a name="known-issues"></a>Bilinen sorunlar

- Zh-CN sistem diliyle ilgili bir sorun, sesli komutların karma gerçeklik yakalama almasını veya cihaz IP adresini görüntülemesini engeller.
- Bir sorun, cihaza "Hey Cortana" ses etkinleştirmesini kullanmak üzere başlattıktan sonra Cortana uygulamasını başlatmanız gerekir. Bir 18362 yapıdan güncelleştirdiyseniz, artık **Başlangıç** aşamasında çalışmamış olan Cortana uygulamasının önceki sürümü için ikinci bir uygulama kutucuğu görebilirsiniz.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows holographic, sürüm 1903-Mayıs 2020 güncelleştirme 
- Derleme 18362,1061

Bu aylık kalite güncelleştirmesi, daha önce açıklandığı gibi, takım Windows holographic sürüm 2004 Güncelleştirmesi üzerinde çalıştığı için herhangi bir önemli değişikliği içermez.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows holographic, sürüm 1903-Nisan 2020 güncelleştirme
- Derleme 18362,1059

**Desteklenen uygulamalar için koyu mod** 

Birçok Windows uygulaması koyu ve hafif modunu destekler. HoloLens 2 müşterileri artık, her iki renk şemasını destekleyen uygulamalar için varsayılan modu seçebilirler. Müşteri geri bildirimlerine göre, varsayılan uygulama modunu "koyu" olarak ayarlarız, ancak bu ayarı dilediğiniz zaman kolayca değiştirebilirsiniz: **"varsayılan uygulama modunu seçme"** bulmak için **ayarlar > sistem > renkler** ' e gidin.

Bu "yerleşik" uygulamalar koyu modunu destekler:
- Ayarlar
- Microsoft Store
- Posta
- Takvim
- Dosya Gezgini
- Geribildirim Merkezi
- OneDrive
- Fotoğraflar
- 3B görüntüleyici
- TV & Filmler

**Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:** 
- Kabuk Yerpaylaşımları karma gerçeklik yakalamalarına dahil edilmiştir.
- Gerçek olmayan geliştiriciler artık cihaz portalındaki 3B görünüm sayfasını kullanarak uygulamalarını test edebilir ve hatalarını ayıklamanıza olanak sağlar.
- *Holographicdepthreprojectionbir yöntemi DepthReprojection* algoritması kullanıldığında karma gerçeklik yakalamadaki iyileştirilmiş hologram kararlılığı.
- 32-bit ARM uygulamalarında "WinRT ıstreamsocketlistener API sınıfı kaydedilemedi" hatası düzeltildi.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows holographic, sürüm 1903-Mart 2020 güncelleştirme 
- Derleme 18362.1056

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- *HolographicDepthReprojectionMethod AutoPlanar* algoritması kullanılırken karma gerçeklik yakalamada geliştirilmiş hologram kararlılığı.
- Derinlik MF örneğine bağlı koordinat sisteminin genel belgelerle tutarlı olduğundan emin olun.
- Müşterilerin cihaz portalı üzerinden büyük miktarlarda metin yapıştırmalarına olanak sağlayarak geliştirici üretkenliği geliştirildi.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, sürüm 1903 - Şubat 2020 Güncelleştirmesi 
- Derleme 18362.1053

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamaları için HolographicSpace.UserPresence API'sini geçici olarak devre dışı bırakıldı. Bu değişiklik, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler.
- Kullanıcı birkaç saniye sonra kullanıcı arabiriminin donması ve tekrar kabukta kilitlenmesi nedeniyle oluşan rastgele BIR HUP kilitlenmesi düzeltildi.
- Dizin parmaklarınızı sıktınız ve bu şekilde el izleme iyileştirildi. Bu nedenle, bu parmak büyük kısmının beklenmedik şekilde curl olma olasılığı daha düşüktü.
- Baş izleme, uzamsal eşleme ve diğer çalışma zamanlarının güvenilirliği geliştirildi.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, sürüm 1903 - Ocak 2020 Güncelleştirmesi 
- Derleme 18362.1043
 
Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 öykünücüsü ile çalışırken özel uygulamalar için geliştirilmiş kararlılık.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, sürüm 1903 - Aralık 2019 Güncelleştirmesi 
- Derleme 18362.1042

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Son aşama yeniden üretme (LSR) düzeltmeleri tanıtıldı. Hologramların görsel işlemesi, derinliğini daha doğru bir şekilde hesaparak daha kararlı ve daha yavaş görünecek şekilde iyileştirildi. Uygulamalar hologram derinliğini doğru ayarlamazsa bu belirti bu güncelleştirmeden sonra daha fark edilir.
- Özel uygulamaların kararlılığı ve özel uygulamalar arasında gezinme düzeltildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- Geliştirilmiş hologram kararlılığı.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, sürüm 1903 - Kasım 2019 Güncelleştirmesi 
- Derleme 18362.1039

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- en-CA **ve** en-AU için ilk kurulum sırasında Select voice komutlarının işlevselliği düzeltildi.
- En son Unity ve Karma Gerçeklik Araç Seti (MRTK) sürümlerinde uzak yerleştirilen nesnelerin görsel kalitesi geliştirildi.
- Holografik uygulamaların başlangıçta duraklatılmış durumda takılı kalarak çalışma Başlat menüsü sonra kapatılana kadar giderildi.
- HoloLens 2 ve öykünücü için OpenXR çalışma zamanı uyumluluk düzeltmeleri ve geliştirmeleri.
