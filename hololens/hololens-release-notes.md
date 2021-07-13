---
title: HoloLens 2 sürüm notları
description: her yeni HoloLens 2 sürümündeki tüm güncelleştirmelerle güncel kalın.
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
ms.openlocfilehash: e0dd7d02ad923438134f2a45812db67f73fdcd8d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637192"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarınızla üretken bir deneyiminizin olduğundan emin olmak için özellik, hata ve güvenlik güncelleştirmelerini serbest bırakmaya devam ediyoruz. bu sayfada, her ay HoloLens yenilikleri görebilirsiniz. en son HoloLens 2 güncelleştirmesini almak için güncelleştirmeleri denetleyebilir ve [gelişmiş kurtarma yardımcısı aracılığıyla cihazınızı flash](hololens-recovery.md#clean-reflash-the-device) [ile el ile güncelleştirebilir](hololens-update-hololens.md#check-for-updates-and-manually-update) veya tam flash güncelleştirmesi (ffu) alabilirsiniz. [İndirme](https://aka.ms/hololens2download) güncel tutulur ve en son genel kullanıma sunulan derlemeyi sağlar.

> [!NOTE]
> son Windows 11 duyurusu, Windows bilgisayar sürümüne odaklanmıştı. kısa süre önce 2021 mayıs ' de HoloLens 2 ' ye [büyük bir işletim sistemi güncelleştirmesi](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) başlattık ve bu fall için müşteri geri bildirimlerine bağlı olarak yaklaşan bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21 h1 deremizdeki, uzaktan yardım kullanıcılarını etkileyen bilinen bir sorun](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)nedeniyle, Windows Holographic, sürüm 21h1 güncelleştirmelerinin sunumunu zamana bağlı duraklattık. ayrıca, varsayılan gelişmiş kurtarma yardımcısı (ARC) derlemesini [Windows Holographic, sürüm 20h2 – haziran 2021 güncelleştirmesine](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)değiştirdik. Şimdi yay derlemesi, 21H1 derlemesini hedeflemeyi sürdürecek.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1-Haziran 2021 güncelleştirmesi
- Derleme 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>iş veya okul kamerayı alma için karşıya yükleme OneDrive

HoloLens 2 Ayarlar uygulamasına yeni bir özellik ekledik. bu, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın resimleri > kamera rulosu klasöründen ilgili OneDrive iş veya okul klasörüne otomatik olarak yüklemesine olanak tanır. bu özellik, yalnızca bir müşterinin kişisel Microsoft hesabı (iş veya okul hesabına değil) otomatik kamera alma 'yı destekleyen HoloLens 2 üzerindeki [OneDrive uygulamasındaki bir özellik boşluğu](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) adresleridir.

**Nasıl çalışır?**

- "kamerayı karşıya yüklemeyi" etkinleştirmek için **karma gerçeklik kamerasından Ayarlar > sistemi >** ziyaret edin.
- bu özelliği **açık** konuma ayarlayarak, cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları, OneDrive iş veya okul hesabınızın kamera rulosu klasörüne yüklenmek üzere otomatik olarak > kuyruğa alınır.
    >[!NOTE]
    >Bu özelliği etkinleştirmeden önce yakalanan fotoğraflar ve Videolar karşıya *yüklenmek üzere* sıraya alınır ve yine de el ile karşıya yüklenmelidir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yükleme bekleyen dosyaların sayısını görüntüler (veya tüm bekleyen dosyalar karşıya yüklendiğinde "OneDrive güncel olduğunu" okur).
- Bant genişliği hakkında endişeleriniz varsa veya herhangi bir nedenle "duraklatma" yapmak istiyorsanız, özelliği **kapalı** konuma geçirebilirsiniz. Özelliği geçici olarak devre dışı bırakmak, kamera rulosu klasörüne yeni dosyalar eklerken karşıya yükleme sırasının artmaya devam etmesini sağlar, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmeyecektir.
- En yeni dosyalar önce karşıya yüklenir (son, ilk çıkar).
- OneDrive hesabınızda sorunlar varsa (örneğin, parolanız değiştirildikten sonra) Ayarlar sayfasında **şimdi bir düzelme** düğmesi görünür.
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklenmesi daha uzun sürdüğüne (özellikle karşıya yükleme bant genişliğiniz kısıtlı ise) göz atalım. Büyük bir dosya karşıya yüklenirken "duraklatabilir" veya karşıya yüklemeyi kapatırsanız kısmi karşıya yükleme korunur. Karşıya yükleme işlemi birkaç saat içinde "duraklatıldı" veya devre dışı bırakıldığında, karşıya yükleme kaldığınız yerden devam eder. Ancak karşıya yükleme işlemi birkaç saat sonra yeniden etkinleştirildiyse, büyük dosyanın karşıya yüklemesi baştan başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayarın geçerli bant genişliği kullanımına bağlı olarak yerleşik azaltma yoktur. Başka bir senaryo için bant genişliğini en iyi duruma getirmeniz gerekiyorsa, ayarı el ile kapatın. Upload duraklatılır, ancak özellik yeni eklenen dosyaları kamera rulonuza izlemeye devam edecektir. Devam etmek için hazırsanız karşıya yüklemeyi yeniden etkinleştirin.
- Bu özelliğin cihazdaki her kullanıcı hesabı için etkinleştirilmesi gerekir ve yalnızca cihazda oturum açmış olan kullanıcı için dosyaları etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasındaki karşıya yükleme sayısını gerçek zamanlı olarak izlerken fotoğraf veya video çekiyorsunuz, geçerli dosyanın karşıya yüklenmesi tamamlanana kadar bekleyen dosya sayısının değişebileceğini unutmayın.
- Upload, cihazınız uyku modunda kalırsa veya kapatılmışsa duraklatılır. bekleyen karşıya yüklemelerinizin tamamlanmasını sağlamak için, Ayarlar sayfası "OneDrive güncel değil" olarak okunana kadar aygıtı etkin bir şekilde kullanın veya **güç & uyku** ayarlarınızı yapın.
### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

aşağıdaki telemetri ilkeleri artık HoloLens 2 ' de desteklenmektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- Allowdevicenameındiagnokdata
- Feedbackhubalwayssavediagnosticsyerel

hem system\allowtelemetri hem de System\ConfigureTelemetryOptInSettingsUx, Ayarlar uygulamasındaki telemetri ve davranış üzerinde tüm denetim sağlamak için birlikte kullanılmalıdır.

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Renk ayarlama ile büyük video bozukluğunu düzeltir.
- Güç menüsünde metnin kesilmiş olabileceği bir sorunu giderir.
- RequirePrivateStoreOnly ilkesi için desteği sunar.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, sürüm 20H2 – Haziran 2021 güncelleştirmesi
- Derleme 19041,1154

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

aşağıdaki telemetri ilkeleri artık HoloLens 2 ' de desteklenmektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- Allowdevicenameındiagnokdata
- Feedbackhubalwayssavediagnosticsyerel

hem system\allowtelemetri hem de System\ConfigureTelemetryOptInSettingsUx, Ayarlar uygulamasındaki telemetri ve davranış üzerinde tüm denetim sağlamak için birlikte kullanılmalıdır.

Windows Holographic, sürüm 21h1 olan en son derlemenizi denemenizi öneririz.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, sürüm 1903-Haziran 2021 güncelleştirme
- Derleme 18362,1116

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows Holographic, sürüm 21h1 olan en son derlemeyi denemenizi öneririz.

>[!IMPORTANT]
> Bu derleme artık servise alınmaz.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, sürüm 21H1
- Derleme 20346,1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihazdaki herkes tarafından kullanılabilen özellikler ve BT yöneticileri tarafından yapılandırılabilen yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda, her bir hedef kitle ile ilgili özellikler belirtilir. BT yöneticisiyseniz lütfen [BT yöneticimize göz atın-güncelleştirme denetim listesini](#it-admin---update-checklist)inceleyin.
>[!IMPORTANT]
>bu yapıya güncelleştirmek için HoloLens 2 cihazdan şu anda şubat 2021 güncelleştirmesi (derleme 19041,1136) veya daha yeni bir sürümü çalışıyor olmalıdır. Bu özellik güncelleştirmesini görmüyorsanız, lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>bugün, Microsoft HoloLens 2 aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmelerini) destekler:
>- Windows Holographic, sürüm 20H2 (derleme 19041.1128 +)
>- Windows Holographic, sürüm 2004 (derleme 19041.1103 +)
>- Windows Holographic, sürüm 1903 (derleme 18362 +) 
>
> Windows Holographic sürüm 21h1 ' i kullanıma **sunduğumuz için, Windows Holographic sürüm 1903 ' a yönelik aylık bakım güncelleştirmelerine devam ediyoruz**. Bu, daha yeni sürümlere odaklanmamızı ve değerli geliştirmeler sunmaya devam etmenizi sağlar. 


| Özellik adı                                              | Kısa açıklama                                                                      | Hedef kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | yeni Chromium tabanlı Microsoft Edge artık HoloLens 2 ' de kullanılabilir. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyicisi](#webxr-and-360-viewer) | Modern Web deneyimleri ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
[yeni Ayarlar uygulaması](#new-settings-app) | eski Ayarlar uygulaması, yeni özellikler ve ayarlarla güncelleştirilmiş bir sürüm ile değiştiriliyor. | Son Kullanıcı |
[Ekran renk ayarı](#display-color-calibration) | HoloLens 2 görüntü için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama birimi denetimi başına](#per-app-volume-control) | Uygulama düzeyi birimini sistem biriminden bağımsız olarak denetleyin. | Son Kullanıcı |
[Web uygulamalarını yükler](#install-web-apps) | Microsoft Office gibi HoloLens 2. Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekme](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde cihazı yeniden başlatın ve HoloLens kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve /veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında otomatik oturum açma özelliğinin Bilgi Noktası modları için kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni Ayarlar Edge uygulamaları için AUMID'ler. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlat menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
[Sayfa Görünürlüğü için Yeni SettingsURIs Ayarlar Ayarları](#new-settings-uris-for-page-settings-visibility) | Ayarlar/PageVisibilityList ilkesi için 20'den fazla yeni SettingsURIs. | BT Yöneticisi |
[Geri Dönüş Tanılamasını Yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Ayarlar Uygulamasında Geri Dönüş Tanılama Davranışını Ayarlama. | BT Yöneticisi |
[Yakındaki cihazlarla paylaşım](#share-things-with-nearby-devices) | Dosya veya URL'leri bir HoloLens bilgisayara paylaşma. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | Işletim sistemi güncelleştirmeleri Ayarlar yeni sorun giderici. | BT Yöneticisi |
[Teslim İyileştirme Önizleme](#delivery-optimization-preview) | Birden çok mobil cihazdan yapılan indirmeler için bant HoloLens düşürebilirsiniz. | BT Yöneticisi |

İlgili sürüm notlarına göz at:

- [HoloLens Emulator arşivini ziyaret edin](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Kılavuzları](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge logosunu yeni Microsoft Edge animasyonu](images/new-edge.gif)

Yeni [Microsoft Edge, müşteriler için daha Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) uyumluluk ve web geliştiricileri için web'in daha az parçalanması için yeni bir açık kaynak proje benimsemektedir.

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde Microsoft Edge eski sürümlerin [yerini](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil bir kısma simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski Microsoft Edge. Yeni Microsoft Edge başlattıktan sonra eski Microsoft Edge kullanmaya devam edersanız, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, ÖNCEKI 2. HoloLens'da ESKI Microsoft Edge'da mevcut olandan çok daha geniş bir tarayıcı Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Enterprise belgeleri](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge, ekibimiz her yeni ilkenin 2. bir ilke üzerinde HoloLens garanti HoloLens. Ancak, daha önce Microsoft Edge 2'de desteklenen her eski Microsoft Edge ilkenin eşdeğerini test ettik ve HoloLens doğruladık. 2 [Microsoft Edge'in eski sürümü Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski Microsoft Edge tarayıcı ilkesine eşdeğer yeni Microsoft Edge bulmak için bkz. HoloLens eşlemesi.
>
> 2. Microsoft Edge en az iki yeni *ilke* ilke HoloLens:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de Microsoft Edge yeni HoloLens beklenilenler

Yeni Microsoft Edge, yeni bir UWP bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan ve bu uygulamanın yalnızca UWP 2 gibi UWP cihazlarda çalışmasına izin HoloLens bazı özellikler hemen kullanılabilir olabilir. Önümüzdeki aylarda yeni senaryoları ve özellikleri destekley edeceğimiz için bu alanı güncel bilgiler için kontrol edin.

**Çalışması beklenen senaryolar ve özellikler:**
- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri beklendiği gibi işlemeli ve davranabilir
- Çoğu tarayıcı işlevi (Sık Kullanılanlar, Geçmiş vb.) beklendiği gibi çalışmalı
- Koyu mod
- Cihaza web uygulamaları yükleme
- Uzantıları yükleme (2. veya 2. gün içinde düzgün çalışmayan uzantılar kullanıyorsanız HoloLens bize haber ver)
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

- Holografik klavyede büyüteç önizlemesi, yeni Microsoft Edge. Bu özelliği, büyütme doğru şekilde çalışmaya başladıktan sonra gelecekteki bir güncelleştirmede yeniden kullanılabilir hale gelecektir.
- Başka bir tarayıcı penceresi açık ve etkinse ses yanlış tarayıcı penceresinden oynatılmış olabilir. Ses çalması gereken diğer etkin pencereyi kapatarak bu soruna bir son ve sonra bakabilirsiniz.
- "Beni takip et" modunda bir tarayıcı penceresinden ses çalma sırasında , "Beni takip [et"](hololens2-basic-usage.md#follow-me-stop-following)modunu devre dışı bıraksanız da ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu **atlayabilirsiniz.**
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerinde beklenmedik bir şekilde devre dışı bırakılamayacak şekilde etkileşebilirsiniz. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Microsoft Edge ekibi Edge Insider topluluğuna üç önizleme kanalı sağlar: Beta, Dev ve Canary. Önizleme kanalının yüklü olması, Microsoft Edge 2'nize HoloLens sürümünü kaldırmaz ve aynı anda birden fazla yükleyebilirsiniz. 

Edge Insider Microsoft Edge daha fazla bilgi edinmek için Microsoft Edge [Insider](https://www.microsoftedgeinsider.com) giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamanız için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Microsoft Edge Insider kanallarını 2'ye yüklemek için HoloLens vardır:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetlanmamış cihazlar tarafından kullanılabilir)**
  1. 2. HoloLens Edge Insider indirme [sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge **Insider HoloLens 2** için İndir düğmesini seçin.
  1. İndirilen .msix dosyasını Edge indirme kuyruğundan veya cihazınızın "İndirmeler" klasöründen (Dosya Gezgini).
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatacak.
  1. Yükle **düğmesini** seçin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

**Windows Cihaz Portalı ile pc üzerinden yükleme [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (2. HoloLens geliştirici modunun etkinleştirilmesi gerekir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki açılan ok düğmesini seçin.
  1. Açılan **HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) dosyasını Windows Cihaz Portalı 2'ye yüklemek için bilgisayarınızda HoloLens kullanın.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) Microsoft Edge engellemek için güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

için kullanılabilir olan uç noktalar hakkında [daha fazla bilgi HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Web uygulamalarını yükleme
 > [!Note]
>Holographic [Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)sürümünden Office web uygulaması artık önceden yüklenmez.

Yeni Edge'i kullanarak yeni uygulamalarla birlikte web Microsoft Store yükleyebilirsiniz. Örneğin, Microsoft Office veya SharePoint barındırılan dosyaları görüntülemek ve düzenlemek için OneDrive. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya Office düğmesini seçin.   Onaylamak **için Yükle'yi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca 2. HoloLens etkin bir İnternet bağlantısı olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici

Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR'nin (görünüm alanınızı bir sanal ortamla değiştirir) ile tasarlanmıştır, ancak bu deneyimler 2. HoloLens de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimlerini de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak 2 müşterinin denemesi için yeni artırılmış ve karma gerçeklik HoloLens deneyimler gelmesini bekliyor!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve 2. Microsoft Edge yeni HoloLens yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

#### <a name="how-to-use-webxr"></a>WebXR'i kullanma

1. WebXR desteği olan bir web sitesine gidin.
1. Web **sitesinde VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel gösterimi web sitesi başına farklılık gösterebilir ancak aşağıdakine benzer olabilir:

    ![VR düğmesi örneğini girin](images/75px-enter-vr.png)

1. Belirli bir etki alanında WebXR deneyimini ilk kez başlatmayı deneyci, çevreleyici bir görünüm girmek için onay sorar ve İzin Ver'i **seçer.**
1. Deneyimi [HoloLens için 2 hareket](hololens2-basic-usage.md#the-hand-tracking-frame) kullanın.
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

Bu sürümle birlikte, Ayarlar uygulamasının yeni bir sürümünü Ayarlar. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni Ayarlar eski Ayarlar uygulamasından ayrı olduğundan, Ayarlar ortamınıza yerleştiren tüm windows güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarlar: Anahtar sözcükleri veya ayarın adını Ayarlar giriş sayfasından ayarları arama.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, ses seslerini ses Bluetooth veya ses girişi için USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar, 2. HoloLens desteklemez.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Uygulama [başına birim denetimine bakın.](#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktanın otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık uçak modunu 2. HoloLens etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Daha önce Ayarlar pencereler kaldırılır (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden Ayarlar. IT yöneticileri, HoloLens 2 cihaz adı şablonu [için Windows Autopilot'ı](https://docs.microsoft.com/hololens/hololens2-autopilot) veya MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme bek gerekmmektedir).

#### <a name="display-color-calibration"></a>Renk ayarlamayı görüntüleme



Bu yeni ayarla, 2 ekran görüntüsü için alternatif bir renk HoloLens seçebilirsiniz. Bu, renklerin özellikle daha düşük ekran parlaklığı düzeylerinde daha doğru görünmesine yardımcı olabilir. Ekran rengi ayarı, sistem Ayarlar Sayfasındaki > bulunabilir.

> [!NOTE]
> Bu ayar görüntü üretici yazılımınıza yeni bir renk profili kaydedeci, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Görüntü rengi ayarlamayı kullanma

1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında, **görüntü renk ayarlama Çalıştır** düğmesini seçin.
1. Ekran renk ayarlama deneyimi başlatılır ve bu işlem, vizörü ' inizin doğru konumda olduğundan emin olmanızı sağlar.
1. Yönerge iletişim kutularında ilerledikten sonra, ekran otomatik olarak %30 oranında gri olacak.
    > [!TIP]
    > ortamınızdaki soluk sahneyi görmekte sorun yaşıyorsanız, cihazın sol tarafındaki parlaklık düğmelerini kullanarak HoloLens 2 ' nin parlaklık düzeyini el ile ayarlayabilirsiniz.
1. Her renk profilini hemen denemek ve gözlerinize en iyi şekilde bakmak için düğmeler 1-6 ' i seçin (Bu, genellikle sahnenin gri tonlamalı bir şekilde görünmesine yardımcı olan profil ve beklenen şekilde görünür.)

    ![Renk ayarlama sahnesini görüntüle](images/color-cal-ui.png)
    
1. Seçili profille memnun olduğunuzda **kaydet & çıkış** düğmesini seçin
1. Değişiklik yapmayı tercih ediyorsanız, **iptal & çıkış** düğmesini seçin ve değişiklikleriniz geri döndürülecek

> [!TIP]
> Görüntü renk ayarlama ayarını kullanırken göz önünde bulundurmanız gereken bazı yararlı ipuçları aşağıda verilmiştir:
> - istediğiniz zaman Ayarlar ekran renk ayarlamayı yeniden çalıştırabilirsiniz
> - cihazdaki herkes renk profillerini değiştirme ayarını daha önce kullanmışsa, en son değişikliğin tarih/saati Ayarlar sayfasında yansıtılır
> - Ekran renk ayarı 'nı yeniden çalıştırdığınızda, daha önce kaydedilen renk profili vurgulanacaktır ve profil 0 görünmez (profil 0 ' ın özgün renk profilini gösterdiği gibi)
> - görüntüleme özgün renk profiline geri dönmek istiyorsanız, Ayarlar sayfasından bunu yapabilirsiniz (bkz. [renk profilini sıfırlama](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama 

HoloLens 2 ' ye kaydedilmiş özel renk profili yoksa, cihazın özgün renk profilini geri yükleyebilirsiniz:
1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında **varsayılan renk profilini Sıfırla** düğmesini seçin.
1. iletişim kutusu açıldığında, HoloLens 2 ' yi yeniden başlatmaya hazırsanız **yeniden başlat** ' ı seçin ve değişikliklerinizi uygulayın.

#### <a name="top-display-color-calibration-known-issues"></a>En üstteki ekran renk ayarlaması bilinen sorunları

- Ayarlar sayfasında, bu Ayarlar sayfasını yeniden yükleyene kadar, renk profilinin en son ne zaman değiştirildiğini söyleyen durum dizesi güncel olmayacaktır.
    - geçici çözüm: başka bir Ayarlar sayfası seçin ve ardından ayarlama sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirir veya onu destekleyen birden fazla yüklü uygulama ile bir dosya türü açtığınızda, hangi yüklü uygulamanın dosyayı veya bağlantı türünü işlemesini seçmenizi isteyen yeni bir pencere açılır. Bu pencerede, Seçilen uygulamanın "bir kez" veya "Always" dosya veya bağlantı türünü işlemesini de seçebilirsiniz.

"Always" seçeneğini belirlerseniz, daha sonra belirli bir dosyayı veya bağlantı türünü hangi uygulamanın işlediğini değiştirmek istiyorsanız, **Ayarlar > Apps**' te kaydedilmiş varsayılanları sıfırlayabilirsiniz. Sayfanın alt kısmına ilerleyin ve "dosya türleri için varsayılan uygulamalar" ve/veya "bağlantı türleri için varsayılan uygulamalar" altındaki **Temizle** düğmesini seçin. Masaüstü PC 'Lerde benzer ayarların aksine, tek tek dosya türü varsayılanlarını sıfırlayamazsınız.

#### <a name="per-app-volume-control"></a>Uygulama birimi denetimi başına

artık bu Windows derlemede, kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duydukları uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha fazla duymasını sağlar. Başka bir kişiyi başka bir kişiye uzak yardım için çağırırken bir uygulamanın hacminin kapatılmasının gereksinimi.

tek bir uygulamanın hacmini ayarlamak için **Ayarlar**  ->  **sistem**  ->  **sesi**' ne gidin ve gelişmiş ses seçenekleri altında **uygulama birimi ve cihaz tercihleri**' ni seçin.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe göre kaydırın

Bazı müşteriler, yazmak istediğiniz sözcüğün şeklini çekerek sanal klavyelerde "tür" ı daha hızlı bulabilir ve bu özelliği holographic klavye için önizliyoruz. Parmaklarınızın ucunu holographic klavye düzlesiyle geçirerek bir kerede tek bir sözcük çekerek, sözcüğün şeklini çekerek ve sonra, parmağınızın ucunu klavyenin düzleminden çizerek bir kez dolaşaktarabilirsiniz. Sözcüklerinizi sözcükler arasındaki klavyeden kaldırarak, daha sonra da boşluk çubuğuna basmanız gerekmeden, izleme sözcüklerini çekerek bulabilirsiniz. Parmağınızın klavye üzerindeki hareketini takip eden bir çekme izi görürseniz özelliğin çalıştığını bilirsiniz.

Lütfen bu özelliğin, parmağınızla (cep telefonundan farklı olarak) bir holographic klavye için herhangi bir zaman duymayın. 

### <a name="power-menu-from-start"></a>Başlangıç menüsünde güç menüsü

Kullanıcının oturumu kapatmasını, kapatması ve cihazı yeniden başlatmasını sağlayan yeni bir menü. bir sistem güncelleştirmesi ne zaman kullanılabilir olduğunu gösteren HoloLens başlangıç ekranında bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. [başlangıç hareketini](hololens2-basic-usage.md#start-gesture) kullanarak HoloLens başlangıç ekranını açın veya "başlangıç ekranına git" diyorum.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkat edin:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Kendi ellerinizi veya "Power" sesli komutunu kullanarak Kullanıcı profili resmini seçin.

4. Oturumu kapatma, cihazı yeniden başlatma veya kapatma seçeneklerinin bulunduğu bir menü görünür:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Oturumu kapatmak, HoloLens yeniden başlatmak veya kapatmak için menü seçeneklerini belirleyin. Cihaz [tek bir Microsoft hesabı (MSA) veya yerel hesap](hololens-identity.md)için ayarlandıysa, oturumu Kapat seçeneği kullanılamayabilir.

6. başka herhangi bir yere dokunarak veya başlangıç hareketiyle Başlat menüsü kapatarak menüyü kapatın.

#### <a name="update-indicator"></a>Göstergeyi Güncelleştir

Bir güncelleştirme kullanılabilir olduğunda, bir yeniden başlatmanın güncelleştirmeyi yükleyeceğini göstermek için üç nokta simgesi de açılır. Bu seçenek, güncelleştirmenin varlığını yansıtacak şekilde değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok Kullanıcı listelendi

Daha önce oturum açma ekranında yalnızca en son oturum açan kullanıcının yanı sıra ' diğer Kullanıcı ' giriş noktası gösteriliyordu. Cihazda birden çok kullanıcı oturum açmışsa, bu yeterli olmayan müşteri geri bildirimi aldık. Yine de bunların Kullanıcı adını yeniden yazması gerekiyordu.

bu Windows derlemesinde tanıtılan, pın girişi alanının sağında bulunan **başka bir kullanıcı** seçerken oturum açma ekranında, daha önce cihazda oturum açmış birden çok kullanıcı görüntülenir. bu, kullanıcıların kullanıcı profillerini seçmesini ve ardından Windows Hello kimlik bilgilerini kullanarak oturum açmasını sağlar. Bu diğer kullanıcılar sayfasından, **Hesap Ekle** düğmesi aracılığıyla cihaza yeni bir kullanıcı da eklenebilir.

Diğer kullanıcılar menüsünde, diğer kullanıcılar düğmesi cihazda oturum açan son kullanıcıyı görüntüler. Bu Kullanıcı için oturum açma ekranına geri dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C dış mikrofon desteği

> [!IMPORTANT]
> **BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**. bir USB-C kulaklık kümesini yüklerken, kullanıcıların kulaklık sesinin otomatik olarak yeniden yönlendirildiğini gözlemleyeceksiniz, ancak HoloLens OS iç microphone dizisinin diğer herhangi bir giriş cihazını önceliklendirilecektir. **Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**

Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir. USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.

**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.

![ses Ayarlar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.
>
> Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın. **Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.
>
> **iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens mıc dizisi diğer görevler için hala kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği nedir?

ne yazık ki Bluetooth mikrofonlar halen HoloLens 2 ' de desteklenmemektedir.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonları sorunlarını giderme

Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. bu mikrofonlardan birini HoloLens içine takarken, ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.

![USB-C mikrofonları sorunlarını giderme](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Kiosks için ziyaretçi otomatik oturum açma

Bu yeni özellik, ziyaretçi hesaplarında otomatik oturum açmanın bilgi noktası modları için kullanılmasını sağlar.

AAD olmayan bir yapılandırma için, bir cihazı ziyaretçi otomatik oturum açmaya yönelik olarak yapılandırmak için:

1. Şu şekilde bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için **çalışma zamanı ayarlarını/Atananı** yapılandırır.
    1. İsteğe bağlı olarak, cihazı daha sonra yönetilebilmesi için MDM 'de **(çalışma zamanı ayarları/çalışma alanı/kayıtlar)** kaydeder.
    1. Yerel hesap oluşturma
1. [Sağlama paketini uygulayın](hololens-provisioning.md).

AAD yapılandırmasında, kullanıcılar bu değişiklik yapılmadan bugün buna benzer bir şey elde edebilir. Bilgi noktası modu için yapılandırılmış AAD 'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak bir ziyaretçi hesabında oturum açabilir. Ziyaretçi hesabında oturum açtıktan sonra, ziyaretçi başlangıç menüsünde açıkça oturum açana veya cihaz yeniden başlatılana kadar cihaz yeniden oturum açmayı istemez.

Ziyaretçi otomatik oturum açma, [özel OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) ilkesi aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon

| İlke  | Açıklama   | Yapılandırmalar  |
|---|---|---|
| MixedReality/Visitooyutologon  | Bir ziyaretçinin bir bilgi noktasında otomatik olarak oturum açmasına izin verir   | 1 (Evet), 0 (Hayır, varsayılan.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>yeni Ayarlar ve uç uygulamalarını bilgi noktası modlarında kullanın

Bilgi [noktaları](hololens-kiosk.md), bir BT Yöneticisi tarafından, büyük bir yandan uygulama kullanıcı modeli kimliği (aumıd) kullanarak uygulamayı bilgi noktasında ekler. Ayarlar uygulaması ve Microsoft Edge uygulamasının her ikisi de yeni uygulamalar olarak değerlendirildiğinden ve bu uygulamalar için aumıds kullanan eski uygulamalardan farklı olduğundan, yeni aumıd kullanmak üzere güncelleştirilmeleri gerekecektir.

Yeni uygulamaları dahil etmek için bir bilgi noktası değiştirirken, yeni AUMıD 'de ekleme ve eskisini bırakma önerilir. Bu, kullanıcılar işletim sistemini güncelleştirinceye kadar kolay bir geçiş oluşturur ve bilgi noktası 'nı istendiği gibi kullanmaya devam etmek için yeni ilkeler almamayı gerektirmez.

| Uygulama                    | AUMıD                                                  |
|------------------------|--------------------------------------------------------|
| eski Ayarlar uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! Uygulamanızda            |
| yeni Ayarlar uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Uygulamanızda |
| eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri

Daha eski derlemelerde, bir cihazın bir bilgi noktası yapılandırması varsa ve bu, hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişimin bir birleşimi ise, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "[hiçbir şey gösterilmez](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" menüsünü görür.

bu Windows sürümden itibaren, bilgi noktası deneyimi AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="new-settings-uris-for-page-settings-visibility"></a>sayfa Ayarlar görünürlüğü için yeni Ayarlar urı 'leri

[Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) ' de, Ayarlar uygulama içinde görülen sayfaları kısıtlamak için [Ayarlar/pagevisibilitylist ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ekledik. pagevisibilitylist, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

[sayfa Ayarlar görünürlüğünü](settings-uri-list.md)ziyaret ederseniz, bu CSP 'yi ve önceki sürümlerde bulunan urı 'lerin listesini kullanmak için yönergeler bulabilirsiniz.

bt yöneticilerinin yönetebileceği kullanılabilir Ayarlar urı 'lerinin listesi üzerinde genişletiliyor. bu urı 'lerden bazıları yeni Ayarlar uygulamasındaki yeni kullanılabilir alanlara yöneliktir. Ayarlar/pagevisibilitylist ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

> [!NOTE]
> **Kullanım dışı: MS-Settings: Network-proxy**
>
> Bu yeni derlemelerde bir ayarlar sayfası kullanımdan kaldırılmıştır. Eski **ağ & Internet**  >  **proxy** sayfası artık genel ayar olarak kullanılamıyor. Yeni bağlantı başına proxy ayarları, **İnternet & Internet**  >  **Wi-Fi**  >  **özellikleri** veya **ağ & Internet**  >  **Ethernet**  >  **özellikleri** altında bulunabilir.

<br>

| Ayarlar sayfası                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Uygulamalar > uygulamalar & Özellikler                               | `ms-settings:appsfeatures`                         |
| Uygulamalar > uygulamalar & özellikler > Gelişmiş Seçenekler          | `ms-settings:appsfeatures-app`                     |
| Çevrimdışı haritalar > uygulamalar                                  | `ms-settings:maps`                                 |
| Uygulamalar > çevrimdışı haritalar > Indirme haritaları                  | `ms-settings:maps-downloadmaps`                    |
| > fare cihazları                                      | `ms-settings:mouse`                                |
| USB > cihazlar                                        | `ms-settings:usb`                                  |
| Ağ & Internet > Uçak modu                   | `ms-settings:network-airplanemode`                 |
| Gizlilik > genel                                    | `ms-settings:privacy-general`                      |
| Gizlilik > mürekkep & yazma kişiselleştirmesi             | `ms-settings:privacy-speechtyping`                 |
| Gizlilik > hareketi                                     | `ms-settings:privacy-motion`                       |
| Gizlilik > ekran görüntüsü kenarlıkları                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Gizlilik > ekran görüntüleri ve uygulamalar                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Sistem > pili                                     | `ms-settings:batterysaver`                         |
| Sistem > pili                                     | `ms-settings:batterysaver-settings`                |
| Sistem > sesi                                       | `ms-settings:sound`                                |
| System > Sound > uygulama hacmi ve cihaz tercihleri | `ms-settings:apps-volume`                          |
| System > Sound > ses cihazlarını yönetme              | `ms-settings:sound-devices`                        |
| sistem > Depolama > Depolama Sense yapılandırma         | `ms-settings:storagepolicies`                      |
| Saat & Dil > Tarih & saati                        | `ms-settings:dateandtime`                          |
| & Dil > klavye                           | `ms-settings:keyboard`                             |
| Zaman & Dil > dili                           | `ms-settings:language`                             |
| Zaman & Dil > dili                           | `ms-settings:regionlanguage-languageoptions`       |
| Güncelleştirme & güvenlik > sıfırlama & kurtarma               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Güncelleştirilmiş URI 'Ler

Daha önce aşağıdaki iki URI, belirtilen sayfalara doğrudan bir Kullanıcı almaz, ancak yalnızca ana güncelleştirmeler sayfasını engelledi. Aşağıdaki öğeler sayfalarına yönlendirecek şekilde güncelleştirildi:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Ayarlar uygulama aracılığıyla geri dönüş tanılamayı yapılandırma

artık Ayarlar uygulamada, bir kullanıcı [geri dönüş tanılamaları](hololens-diagnostic-logs.md)davranışını yapılandırabilir. Ayarlar uygulama,   ->  bu ayarı yapılandırmak için gizlilik **sorunlarını giderme** sayfasına gidin.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, Kullanıcı bu davranışı geçersiz kılayamaz.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla şeyleri paylaşma

hem bilgisayarlar hem de diğer HoloLens 2 cihazları dahil olmak üzere Windows 10 cihazları ile neredeyse her şeyi paylaşabilirsiniz.   ->    ->  dosya veya url 'leri bir bilgisayara HoloLens paylaşmak için Ayarlar sistem **paylaşılan deneyimleriyle** deneyebilirsiniz. Daha fazla ayrıntı için [Windows 10 ' de Yakındaki cihazlarla şeyler paylaşma](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)hakkında daha fazla bilgi edinin.

Bu özellik, [bağlantı/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)aracılığıyla yönetilebilir.

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmelerine yönelik yeni Ayarlar uygulamasının eklenmesiyle birlikte yeni bir sorun giderici eklenmiştir. **Ayarlar**  ->  **güncelleştirme &amp; güvenliği**  >  **sorun giderme**  >  **Windows Update** gidin ve **başlat**' ı seçin. Bu, BT veya destek ile ilgili sorun giderme konusunda daha iyi yardımcı olması için işletim sistemi güncelleştirmeleriyle ilgili sorunları yeniden oluştururken izlemeleri toplamanıza olanak tanır.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

bu HoloLens güncelleştirme ile, Windows Holographic for Business birden çok HoloLens cihazdan indirilen bant genişliği tüketimini azaltmak için teslim iyileştirme ayarlarının kullanılmasına olanak sağlar. önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Aşağıdaki ayarlar yönetim yüzeyi kapsamında etkinleştirilmiştir ve [Intune 'dan yapılandırılabilir](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [Dodelaycacheserverfallbackönalanı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarılar:

- HoloLens desteği, bu önizlemede yalnızca işletim sistemi güncelleştirmeleri için sınırlıdır.
- Windows Holographic for Business yalnızca [Microsoft bağlı önbellek uç noktasından](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)HTTP indirme modlarını ve indirmeleri destekler; şu anda HoloLens cihazlarda eşler arası indirme modları ve grup atamaları desteklenmez.
- HoloLens, Windows Server Update Services uç noktaları için dağıtımı veya teslim iyileştirmeyi desteklemez.
- sorun giderme, bağlı önbellek sunucusunda tanılama gerektirir veya **Ayarlar**  >  **güncelleştirme & güvenlik**  >   **sorun giderme**  >   **Windows Update** aracılığıyla HoloLens HoloLens bir izleme topluyor.

### <a name="it-admin---update-checklist"></a>BT Yöneticisi-güncelleştirme denetim listesi

Bu denetim listesi, bu özellik güncelleştirmesinde eklenmekte olan yeni öğeleri, geçerli cihaz yönetimi yapılandırmalarından veya kullanmaya başlamak isteyebileceğiniz yeni özelliklerden haberdar etmenize yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi noktası moduna güncelleştirmeler

[**bilgi noktası modunda yeni uygulamalar Için yeni AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️:

daha önce bir bilgi noktasında Ayarlar uygulamasını veya Microsoft Edge uygulamasını kullanıyorsanız, bu uygulamaları farklı bir uygulama kimliği kullanan yeni uygulamalarla değiştirdik. [Yeni uygulamalar için yeni Aumıd 'Leri bilgi noktası modunda](#use-the-new-settings-and-edge-apps-in-kiosk-modes) okumanız önemle tavsiye ederiz. bu, Ayarlar uygulamanızın bilgi noktasında olmasına devam edebilir ya da yeni Microsoft Edge uygulamasını dahil etmeye devam eder. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirme sırasında daha yumuşak bir geçişe izin verebilir.

[**kiosks Için ziyaretçi otomatik oturum açma**](#visitor-auto-logon-for-kiosks)✔️: 

Ziyaretçiler artık bir bilgi noktasında otomatik olarak oturum açabilir. Bu davranış varsayılan olarak açık olmakla kalmaz, yönetilebilir ve devre dışı bırakılabilir.

✔️ [**Gelişmiş bilgi noktası modu hata teslim**](#kiosk-mode-behavior-changes-for-handling-of-failures)etme:

Oturum açan AAD kullanıcısının AAD grup üyeliği başarıyla saptanmamışsa, bu durumda Başlat menüsü (varsa) için genel bilgi noktası yapılandırması kullanılır, aksi takdirde Kullanıcı boş Başlat menüsüyle sunulur. Boş başlangıç menüsü, doğrudan ayarlayabileceğiniz bir yapılandırma olmadığından, bu yeni işleme, sizin yapılandırmanıza uygulanabilecek veya atanan erişim yapılandırmalarınıza yeni ayarlamalar yapmak isteyebileceğiniz için, bilgi noktaları kullanıyorsanız, destek bölümünüze bildirmek için bir şey olabilir.

#### <a name="updates-to-page-settings-visibility"></a>sayfa Ayarlar görünürlüğü için güncelleştirmeler

[**sayfa Ayarlar görünürlüğü için yeni Ayarlar urı** ✔️](#new-settings-uris-for-page-settings-visibility)

şu anda [sayfa Ayarlar görünürlüğü](settings-uri-list.md) kullanıyorsanız, var olan veya engellenen mevcut urı 'lerinizin ayarlamalarını yapmak isteyebilirsiniz.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkenize yönelik güncelleştirmeler
✔️ daha önce Microsoft Edge wdac aracılığıyla bloke ediyorsanız, wdac ilkenizi güncellemek isteyeceksiniz. Lütfen aşağıdakileri gözden geçirin ve belirtilen örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Uç için yeni uç noktaları etkinleştir
✔️ ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, lütfen yeni Microsoft Edge uygulaması için bu yeni uç noktaları etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

[geri dönüş tanılamayı yapılandırma](#configuring-fallback-diagnostics-via-settings-app)✔️: geri dönüş tanılamayı toplayıp toplayacağını yapılandırıp yönetemeyebilirsiniz.

[Yakındaki cihazlarla her şeyi paylaşmak](#share-things-with-nearby-devices)✔️: yeni yakın paylaşım özelliğini devre dışı bırakabilirsiniz.

[yeni Microsoft Edge ilke ayarlarını yapılandırma](#configuring-policy-settings-for-the-new-microsoft-edge)✔️: Microsoft Edge için kullanılabilen yeni konfigürasyonları inceleyin.

#### <a name="new-diagnostic-tool"></a>Yeni Tanılama Aracı

[yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces)✔️: Işletim sistemi güncelleştirmeleriyle ilgili günlükleri toplayın.

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics) , seri numarası ve işletim sistemi sürümü için ek cihaz bilgileri de içerir.
- Çalışma zamanı sağlama paketleri aracılığıyla iş kolu uygulamalarının dağıtımı etrafında bir sorunu düzeltir.
- İş kolu uygulama yüklemesi durum raporlama etrafında bir sorunu düzeltir.
- Cihaz sıfırlamaları genelinde yeni uygulama paketlerinin kalıcılığını aşmak için bir sorunu düzeltir.
- Japonca müşteriler için Edge 'de yanlış simgelere yol açabilecek bir sorunu düzeltir.
- , Uç gibi önceden yüklenmiş uygulamalar etrafında işletim sistemi güncelleştirmelerinin dayanıklılığını geliştirir. 
- Microsoft Edge yüklemesini etkileyen bir güncelleştirme güvenilirliğini giderir. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, sürüm 20H2 – Mayıs 2021 güncelleştirmesi
- Derleme 19041,1146

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows Holographic, sürüm 21h1 olan en son derlemeyi denemenizi öneririz.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, sürüm 1903-Mayıs 2021 güncelleştirme
- Derleme 18362,1110

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermiyor. **Bu derleme artık aylık hizmet güncelleştirmelerini almamayacaktır**. Windows Holographic, sürüm 21h1 olan en son derlemenizi denemenizi öneririz.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, sürüm 20H2-Nisan 2021 güncelleştirmesi
- Derleme 19041,1144

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İş kolu uygulama yüklemesi durum raporlama etrafında bir sorunu düzeltir.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, sürüm 1903-Nisan 2021 güncelleştirme
- Derleme 18362,1108

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- bir yerel hesabın parolasını değiştirmeye çalışırken Ayarlar uygulamasının çöktüğü bir sorunu giderir.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, sürüm 20H2-Mart 2021 güncelleştirmesi
- Derleme 19041,1140

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 ile fotoğraf yakalamak için advancedphotocapture veya lowgphotocapture kullanan müşteriler artık fotoğraf yakalandıktan sonra kamerayı 3 saniyeye alabilir.
- Cihaz portalı hizmetinde bellek sızıntısı için, sorun diğer uygulamaların bellek ayırmayı başarısız olmasına neden olan hizmet tarafından daha fazla bellek kullanımına neden oldu.
- Hazırlanmış dağıtıma kayıtlı olan kullanıcıların cihazda oturum açabildiği bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, sürüm 1903-Mart 2021 güncelleştirme
- Derleme 18362,1102

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz portalı hizmetinde bellek sızıntısı için, sorun diğer uygulamaların bellek ayırmayı başarısız olmasına neden olan hizmet tarafından daha fazla bellek kullanımına neden oldu.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, sürüm 20H2-Şubat 2021 güncelleştirmesi
- Derleme 19041,1136

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İlk cihaz kurulumu ve uygulama güncelleştirmelerini depolama etrafında bir sorunu düzeltir.
- daha sonraki HoloLens sürümler için yükseltmeler ve fışıklardan oluşan bir sorunu giderir.
- kullanılmayan önceden yüklenmiş sertifikalar HoloLens cihazlarından esım kök deposundan kaldırıldı.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, sürüm 1903-Şubat 2021 güncelleştirme
- Derleme 18362,1098

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez Windows Holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, sürüm 20H2-Ocak 2021 güncelleştirmesi
- Derleme 19041,1134

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihazda çok sayıda kullanıcı olduğunda başlangıç, özgeçmişler ve Kullanıcı geçişi sırasında performans geliştirildi.
- [Araştırma modu](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)için ARM32 desteği eklendi.

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, sürüm 1903-Ocak 2021 güncelleştirme
- Derleme 18362,1091

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez Windows Holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, sürüm 20H2 – Aralık 2020 güncelleştirme
- Derleme 19041,1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme

HoloLens 2 cihazlarınıza **daha sorunsuz bir şekilde uygulama yüklemenize olanak tanımak için yeni bir özellik (App ınstaller) ekliyoruz** . Özelliği, **yönetilmeyen cihazlar için varsayılan olarak açık** olacaktır. Kurumların kesintiye uğramasını önlemek için, uygulama yükleyicisi Şu anda **Yönetilen cihazlarda kullanılamayacak** .  

**Aşağıdakilerden biri doğruysa** bir cihaz "yönetilen" olarak değerlendirilir:
- MDM [kaydı](hololens-enroll-mdm.md) yapılmış
- [Sağlama paketiyle](hololens-provisioning.md) yapılandırıldı
- Kullanıcı [kimliği](hololens-identity.md) Azure AD

Artık Geliştirici modunu etkinleştirmek veya cihaz portalını kullanmak gerekmeden uygulama yükleyebilirsiniz.  Cihazınıza appx paketini indirmeniz (USB veya-Edge üzerinden) ve yüklemeyi başlatma istenmeden dosya Gezgini 'ndeki appx grubuna gitmeniz yeterlidir.  Alternatif olarak, [bir Web sayfasından bir yüklemeyi başlatabilirsiniz](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  MDM 'nin LOB uygulaması dağıtım özelliğini kullanarak Microsoft Store veya dışarıdan yüklemeden yüklediğiniz uygulamalar gibi uygulamalar, [imza aracı](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) ile dijital olarak imzalanmalıdır ve uygulama dağıtılmadan önce [imzalamak için kullanılan sertifikaya HoloLens cihaz tarafından güvenilmesi gerekir](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) .

**Uygulama yüklemesi yönergeleri.**

1.  Cihazınızın yönetilen olarak değerlendirilmediğinden emin olun
1.  HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1.  HoloLens 2 cihazında oturum açtığınızdan emin olun
1.  bilgisayarınızda özel uygulamanıza gidin ve app. appxpaketi ' ni devicename\ınternal Depolama \downloadcopy dizinine kopyalayın.   Dosyanızı kopyalamayı tamamladıktan sonra cihazınızın bağlantısını kesebilirsiniz
1.  HoloLens 2 cihazınızdan başlat menüsünü açın, tüm uygulamalar ' ı seçin ve dosya gezgini uygulamasını başlatın.
1.  Indirmeler klasörüne gidin. Uygulamanın sol panelinde bu cihazı önce seçin, sonra Indirmeler ' a gidin.
1.  Yourapp. appxpaket dosyasını seçin.
1.  Uygulama yükleyicisi başlatılır. Uygulamanızı yüklemek için Install (Çalıştır) düğmesini seçin.
Yükleme tamamlandıktan sonra yüklenen uygulama otomatik olarak başlatılır.

bu akışı test etmek için, [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) üzerinde örnek uygulamalar bulabilirsiniz.

[uygulama yükleyicisiyle HoloLens 2 ' ye uygulama yükleme](app-deploy-app-installer.md)işleminin tam süreci hakkında bilgi edinin.  

![Uygulama yükleyicisi aracılığıyla MRTK örnekleri yükleme](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El ile izleme artık, izlemenin daha önce kaybedildiği birçok yeni durumda izlemeyi korur.  Bu yeni durumların bazılarında, yalnızca Palm konumu kullanıcının gerçek adına göre güncelleştirilmeye devam ederken, diğer yandan da önceki bir poza göre çıkarılır.  Bu değişiklik, taşıma, oluşturma, scoing ve hareketli hale alma gibi hareket halinde izlemenin tutarlılığını artırmaya yardımcı olur.  Ayrıca, el 'nin bir yüzeye yakın veya bir nesneyi tutan durumlarda da yardımcı olur.  Bu yandan, her ne kadar [ortak doğruluk](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) değeri "yüksek" yerine "yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamasının bir hata göstereceği bir sorun düzeltildi "bir sorun oluştu.
- Kullanıcılar, ayarlar uygulaması, Yeni Kullanıcı veya bildirim bildirimi ' ni başlatırken, kullanıcıların çok daha az önyükleme sonrası OOBE kilitlenmelerini görmelidir.
- Kullanıcıların, OOBE 'den gelen doğru saat dilimi olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 güncelleştirme
- Derleme 18362,1088

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son Windows Holographic, sürüm 20h2 – aralık 2020 güncelleştirme ve yapıya eklenen yeni uygulama yükleyicisi özelliğini denemenizi öneririz.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2
- Derleme 19041,1128

Windows Holographic, 20h2 sürümü artık kullanılabilir ve 2 kullanıcı ve bt uzmanlarına HoloLens harika yeni özellikler sunuyor. otomatik göz konumlandırmayı, Ayarlar ' deki sertifika yöneticisi 'ne, gelişmiş bilgi noktası modu işlevselliğine ve yeni Autopilot kurulum özelliklerine sahip. bu yeni güncelleştirme, bt ekiplerinin HoloLens cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetim almasını sağlar ve kullanıcılara daha sorunsuz holographic deneyimleri sunar. 

Bu en son sürüm 2004 sürümüne yönelik aylık bir güncelleştirmedir, ancak bu kez yeni özellikler de ekledik. ana yapı numarası aynı kalacaktır ve Windows Update sürüm 2004 ' e yönelik aylık bir yayın olduğunu belirtecektir (derleme 19041). en son kullanılabilir derleme 19041.1128 + ' de olduğunu onaylamak için Ayarlar > ekranında yapı numaranızı görebilirsiniz. en son sürüme güncelleştirmek için Ayarlar uygulamasını açın, güncelleştirme & güvenlik ' e gidin ve güncelleştirmeler için denetle ' ye dokunun. HoloLens güncelleştirmelerinin nasıl yönetileceği hakkında daha fazla bilgi için [bu sayfayı](https://docs.microsoft.com/hololens/hololens-updates)ziyaret edin.

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20h2 ' deki yenilikler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik göz konumu desteği](hololens-release-notes.md#auto-eye-position-support) | Göz önünde bulunmadan, göz önünde bulunmadan önce gözle yer işareti olarak hesaplar.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | yeni daha basit yöntemlerin Ayarlar uygulamasına sertifika yüklemeye ve kaldırmasına izin verir.     |
| [Sağlamayı USB 'den otomatik olarak başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerdeki sağlama paketleri otomatik olarak OOBE 'de sağlama sayfasına istem.                                                         |
| [OOBE 'de sağlama paketlerini otomatik onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimi kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve birlikte otomatik onaylama işlemlerini birleştirme. |
| [Wi-Fi bağlantısı ile Autopilot kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısı için gerek olmadan cihaz Wi-Fi Autopilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlandığında veya yeniden flaışınızda bu kiracıya kaydedilebilir. |
| [Genel atanan erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Birden çok uygulama bilgi noktası modu için yeni yapılandırma yöntemi, sistem düzeyinde bilgi noktası uygular ve bu durum, tümü için geçerli hale getirir.                  |
| [Çoklu uygulama bilgi noktasında uygulamayı otomatik olarak başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Bir uygulamayı birden çok uygulama bilgi noktası modunda oturum açarken otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüş içeriyor.                                                                                                |
| [HoloLens Elerindeki](hololens-release-notes.md#hololens-policies)                                    | HoloLens için yeni ilkeler.     |
| [Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların, gün sayısını ayarlamak için bilgi noktası modunu çevrimdışı kullanması için Grup üyeliği önbelleğini kullanmasına izin verir.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz yönetimi ilkeleri etkinleştirildi.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [Güncelleştirme Ilkeleri](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfa görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Ayarlar uygulamasında hangi sayfaların görüldüğünü seçme ilkesi.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2 üzerinde araştırma modu kullanılıyor. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikaya geçmiyor. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik göz konumu desteği

HoloLens 2 ' de, göz pozisyonları doğru hologram konumlandırmayı, rahat görüntüleme deneyimini ve geliştirilmiş görüntü kalitesini sağlar. Göz konumları, göz izleme hesaplamasının bir parçası olarak dahili olarak hesaplanır. Bununla birlikte, bu durum, deneyim göz önünde olmayan giriş gerektirmese de, her bir kullanıcının göz önünde geçiş ayarlaması için geçmesi gerekir.

**Otomatik göz konumu (AEP)** , bu senaryolara Kullanıcı için göz önünde bekleyen bir yol sağlar. Otomatik göz konumu, kullanıcının cihazı üzerine koyduğu andan itibaren otomatik olarak çalışmaya başlar. Kullanıcının önceki bir göz izleme ayarı yoksa, otomatik gözle, 20-30 saniyelik bir işlem zamanından sonra, ekran sistemine kullanıcının göz konumlarını sağlamaya başlayacaktır. Kullanıcı verileri cihazda kalıcı değil ve bu nedenle kullanıcı devre dışı bırakılırsa veya cihaz yeniden başlatıldığında veya uyku modundan çıktığında bu işlem yinelenir.

Kalibre edilmemiş bir Kullanıcı cihaza geçiş yaparken otomatik gözle konum özelliği olan birkaç sistem davranışı değişikliği vardır. Bu bağlamda, kalibre edilmemiş bir Kullanıcı, cihazda daha önce gelen göz izleme ayarlama işleminden geçmiş bir kişiye başvurur.

| Etkin uygulama | Önceki davranış | Windows Holographic, sürüm 20h2 güncelleştirme davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Gaze etkin olmayan uygulama veya holographic kabuğu |Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Hiçbir istem gösterilmez. |
| Etkin uygulama | Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz önünde akışa eriştiğinde görüntülenir. |

Kullanıcı, Gaze olmayan bir uygulamadan, Gaze verilerine erişen bir uygulamaya geçiş yaptığında ayarlama istemi görüntülenir. 

Geçerli kullanıcının etkin bir göz izleme ayarlaması olmadığında, diğer tüm sistem davranışları ile benzerdir. Örneğin, tek elli başlangıç hareketi etkinleştirilmeyecektir. İlk kurulum için hazır olmayan deneyimle ilgili hiçbir değişiklik olmayacaktır.

Veri veya çok kesin hologram konumlandırmayı gerektiren deneyimler için, kalibre izleme ayarlamayı çalıştırmak için kalibre edilmemiş kullanıcıları öneririz. göz izleme ayarlaması isteminden veya başlangıç menüsünden Ayarlar uygulama başlatarak ve ardından **sistem > ayarlama > göz ayarlama > çalıştır**' ı seçerek göz önünde erişilebilir.

Bu bilgiler, daha sonra [diğer ayarlama bilgileriyle](hololens-calibration.md#auto-eye-position-support)bulunabilir. 

### <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama araçları. Bu özellik, ticari ortamlarda sertifikalarınızı bir ölçekte dağıtmanıza, gidermenize ve doğrulamanıza olanak sağlar.

Windows Holographic sürümü 20h2 ' de, HoloLens 2 Ayarlar uygulamasına bir sertifika yöneticisi ekliyoruz. **Ayarlar > güncelleştirme & güvenlik > sertifikaları**' na gidin. Bu özellik, cihazınızdaki sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için daha fazla denetim, tanılama ve doğrulama araçları geliştirmiştir. 

-   **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığını doğrulama veya uygun şekilde kaldırıldığını doğrulama özelliği. 
-   **Tanılama:** Sorun ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulamak zaman kazandırır ve sorun gidermeye yardımcı olur. 
-   **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğu doğrulanıyor, özellikle de daha büyük ölçekte sertifika dağıtmadan önce ticari ortamlarda önemli bir zaman kazandırabilir.

Listedeki belirli bir sertifikayı hızlı bir şekilde bulmak için ada, depoya veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar ayrıca bir sertifikayı doğrudan arayabilir. Ayrı sertifika özelliklerini görüntülemek için sertifikayı seçin ve **bilgi**'ye tıklayın. 

Sertifika yüklemesi şu anda. cer ve. CRT dosyalarını desteklemektedir. Cihaz sahipleri, sertifikaları yerel makineye ve geçerli kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca geçerli kullanıcıya yüklenebilir. kullanıcılar yalnızca Ayarlar kullanıcı arabiriminden doğrudan yüklenmiş sertifikaları kaldırabilir. Bir sertifika başka yollarla yüklendiyse aynı mekanizmaya de kaldırılmalıdır.

#### <a name="to-install-a-certificate"></a>Bir sertifika yüklemek için: 

1.  HoloLens 2 ' 'nizi bir bilgisayara Bağlan.
1.  yüklemek istediğiniz sertifika dosyasını HoloLens 2 ' deki bir konuma yerleştirin.
1.  **Ayarlar App > Update & güvenlik > sertifikaları**' na gidin ve sertifika yüklemeyi seçin.
1.  **Dosyayı Içeri aktar** ' a tıklayın ve sertifikayı kaydettiğiniz konuma gidin.
1.  **Depo konumunu** seçin.
1.  **Sertifika deposunu** seçin.
1.  **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklü olması gerekir.

#### <a name="to-remove-a-certificate"></a>Bir sertifikayı kaldırmak için: 
1. **Ayarlar App > Update ve Security > sertifikalarına** gidin.
1. Arama kutusunda Sertifikayı ada göre arayın.
1. Sertifikayı seçin.
1. **Kaldır** 'a tıklayın
1. Onay sorulduğunda **Evet** ' i seçin.

![Ayarlar uygulamasındaki sertifika görüntüleyicisi](images/certificate-viewer-device.jpg)

![Sertifika Kullanıcı arabiriminin bir sertifikayı yüklemek için nasıl kullanılacağını gösteren resim](images/certificate-device-install.jpg)

Bu bilgiler, daha sonra [Yeni bir Sertifika Yöneticisi sayfasında](certificate-manager.md)bulunabilir.

### <a name="auto-launch-provisioning-from-usb"></a>Sağlamayı USB 'den otomatik olarak başlatma

- Otomatik süreçler, sağlama paketleri içeren USB sürücüleri OOBE sırasında kullanıldığında daha az kullanıcı etkileşimine izin verir.

Bu sürümden önce, bir düğme bileşimini kullanarak sağlamak için kullanıcıların, OOBE sırasında sağlama ekranını el ile başlatması gerekiyordu. Artık kullanıcılar, USB depolama sürücüsünde bir sağlama paketi kullanarak düğme bileşimini atlayabilir. 

1. OOBE 'nin ilk ınteractable 'ı sırasında sağlama paketiyle USB sürücüsünü takın
1. Cihaz sağlanmaya hazır olduğunda, isteği sağlama sayfasıyla otomatik olarak açar. 

Note: cihaz önyüklenirken bir USB sürücü takıldıysa, OOBE mevcut USB depolama cihazını numaralandırır ve takılmakta olan ek için izleme de yapılır.

OOBE sırasında sağlama paketleri uygulama hakkında daha fazla bilgi için [HoloLens sağlama](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) belgelerini ziyaret edin.

[bir USB 'den otomatik başlatma sağlamaya](hololens-provisioning.md#auto-launch-provisioning-from-usb) yönelik ek bilgiler HoloLens sağlama belgelerinde bulunabilir.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE 'de sağlama paketlerini otomatik onaylama
- Otomatik süreç daha az kullanıcı etkileşimine izin verirken, sağlama paketi sayfası görüntülendiğinde, listelenen tüm paketleri otomatik olarak uygular.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerinin uygulanması için OOBE 'nin otomatik olarak başlatılması için önce 10 saniye geçmesi gerekir. Kullanıcılar, bekledikleri paketleri doğruladıktan sonra bu 10 saniye içinde yine de [onaylama veya iptal](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) edebilir.

### <a name="automatic-provisioning-without-using-ui"></a>Kullanıcı arabirimi kullanmadan otomatik sağlama
- Sağlama için azaltılmış cihaz etkileşimleri için otomatik süreçler birleştirildi. 

bir kullanıcı, USB cihazlarından sağlamanın otomatik olarak başlatılmasını ve sağlama paketlerinin otomatik onayını birleştirerek, cihazın kullanıcı arabirimini kullanmadan veya hatta cihazı takmadan HoloLens 2 cihaz otomatik olarak sağlayabilir. Birden çok cihaz için aynı USB sürücüsünü ve sağlama paketini kullanmaya devam edebilirsiniz. Bu, aynı alanda aynı anda birden çok cihazı dağıtmak için yararlıdır. 

1. [Windows yapılandırma tasarımcısı](https://www.microsoft.com/store/productId/9NBLGGH4TX22)'nı kullanarak [bir sağlama paketi oluşturun](hololens-provisioning.md) . 
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ' ye [19041,1361 veya daha yeni bir derleme](https://aka.ms/hololens2previewdownload)yapın. 
1. [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın yanıp sönmesi TAMAMLANDıĞıNDA, USB-C kablonuzu sökün. 
1. USB sürücünüzü cihaza takın.
1. HoloLens 2 cihazı OOBE 'de önyüklendiğinde, USB sürücüsünde sağlama paketini otomatik olarak algılayacak ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz, sağlama paketini otomatik olarak uygular. 

Cihazınız artık yapılandırıldı ve [sağlama başarılı ekranı görüntülenir](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Wi-Fi bağlantısı ile Autopilot kullanma
- Wi-Fi bağlı cihazlarda Autopilot çalışmasını etkinleştirerek, USB-C bağdaştırıcılarının Ethernet ile donanım ihtiyaçlarını azaltmaya gereksinimi ortadan kaldırılmıştır.

artık oobe sırasında, HoloLens 2 ' yi Wi-Fi ile bağlandıktan sonra, oobe cihaz için bir Autopilot profilini denetlecektir. Bir tane bulunursa AAD JOIN ve kayıt akışının geri kalanını tamamlayacak şekilde kullanılacaktır. Diğer bir deyişle, Ethernet ile USB-C veya Wi-Fi USB-C adaptörünün kullanılması artık bir gereksinim değildir, ancak OOBE 'nin başlangıcında sağlanmışsa çalışmaya devam ederler. [HoloLens 2 cihazları için Autopilot](hololens2-autopilot.md)hakkında daha fazla bilgi edinin.

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot
- Cihaz sıfırlama veya refflash aracılığıyla bile, cihazı kiracıya kilitleyerek kuruluşun kiracısındaki cihazları tutar. , Sağlama yoluyla içinde hesap oluşturmayı engelleyerek daha fazla güvenlik ile. 

HoloLens 2 cihaz artık [Windows Holographic sürümü 20h2](hololens-release-notes.md#windows-holographic-version-20h2)itibariyle tenantlockdown CSP 'yi destekliyor. 

[Tenantlockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. tenantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer yeniden yanıp sönse, işletim sistemi güncelleştirmeleri, vb. için cihazda kalır. 

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, ağ bağlantısından sonra OOBE, Autopilot profilinin başarıyla indirilip uygulanmasını bekler. 

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, OOBE 'de aşağıdaki işlemlere izin verilmez: 
- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD JOIN işlemi gerçekleştiriliyor 
- Cihaza kimin sahip olduğunu OOBE deneyiminde seçme 

#### <a name="how-to-set-this-using-intune"></a>Bu Intune kullanılarak nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe düğümü için true değerini belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla kiracı kilidi ayarlanıyor](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın. 

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla geçerliyse, tenantlockdown etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>ıntune 'u kullanarak HoloLens 2 üzerinde tenantlockdown 'ın talep ırenetworkınoobe ayarı nasıl yapılır? 
1. yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2 ' i kaldırın. 

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe için false belirtin. OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![Intune 'da OMA URI aracılığıyla talep ırenetworkınoobe ayarının false olarak ayarlanmasına yönelik ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın. 

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandıktan sonra, tenantlockdown 'ın etkileri devre dışı bırakılır. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Autopilot profili, maantlockdown true olarak ayarlandıktan sonra bir HoloLens için atanmazsa, OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilmek için süresiz olarak bekler ve aşağıdaki iletişim kutusu sunulacaktır. TenantLockdown 'in etkilerini kaldırmak için, önce Autopilot yalnızca bir cihaz özgün kiracısına kaydedilmelidir ve eski adımda açıklandığı gibi, TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önce bu, önkoşul olarak ayarlanmalıdır. 

![Cihazda ilke uygulandığında cihaz içi görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık, [Tenantlockdown CSP ve Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)altında Autopilot 'in geri kalanının yanı sıra bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel atanan erişim – bilgi noktası modu
- Bilgi noktası için, sistem düzeyinde bilgi noktası modu uygulayan yeni bilgi noktası yöntemi etkinleştirilerek kimlik yönetimi azaltıldı.

bu yeni özellik, bir bt yöneticisinin sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için bir HoloLens 2 cihazı yapılandırmasına izin verir, sistemde hiçbir kimlikle benzeşim yoktur ve cihazda oturum açan herkese uygulanır. [HoloLens genel atanan erişim bilgi noktasında](hololens-global-assigned-access-kiosk.md)bu yeni özellik hakkında ayrıntılı bilgi edinin.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Bir uygulamanın çoklu uygulama bilgi noktası modunda otomatik olarak başlatılması 
- Otomatik uygulama başlatma deneyimi odaklıdır ve Bilgi Noktası modu deneyimleri için seçilen kullanıcı arabirimini ve uygulama seçimlerini daha da artırmaktadır.

Yalnızca birden çok uygulamalı bilgi noktası modu için geçerlidir ve atanan erişim yapılandırmasında aşağıdaki vurgulanmış öznitelik kullanılarak yalnızca 1 uygulama otomatik olarak başlatılacak şekilde atanabilir. 

Kullanıcı oturum başlattığında uygulama otomatik olarak başlatılır. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri
- Bilgi noktası modu hatalarda kullanılabilir uygulamaları ortadan kaldırarak daha güvenli Bilgi Noktası modu. 

Bilgi noktası modu uygulama sırasında hatalarla karşılaşmanın HoloLens başlat menüsündeki tüm uygulamaları göstermek için kullanılırdı. Holographic Windows 20H2'de hata olması durumunda başlat menüsünde aşağıdaki gibi hiçbir uygulama gösterilmez: 

![Bilgi noktası modu artık başarısız olduğunda hangi modun göründüğünün resmi.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Koşullarıdır
- Cihaz yönetimi seçenekleri, HoloLens için özel olarak oluşturulur. 

Holographic sürüm 20H2'de HoloLens 2 cihaz için Windows karma gerçeklik ilkeleri oluşturulmuştur. Yeni kontrol edilebilir ayarlar şunlardır: parlaklığı ayarlama, birimi ayarlama, karma gerçeklik yakalamalarında ses kaydını devre dışı bırakma, tanılamanın ne zaman toplanabilir olduğunu ayarlama ve AAD grup üyeliği önbelleği.  

| Yeni HoloLens ilkesi                                | Açıklama                                                                               | Notlar                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Parlaklığı düğmelerinin devre dışı bırakılarak parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı bırakılarak birimi değiştirmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\MicrophoneDisabled                    | 2. görüntüde ses kaydının mümkün HoloLens devre dışıdır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin ne zaman toplanabilir davranışını kontrol eder.                               | 0 Devre Dışı, 1 Cihaz Sahipleri için Etkin, 2 Herkes için Etkin (Varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD gruplarını hedef alan Bilgi Noktası için Azure AD grup üyeliği önbelleğinin kaç gün süreyle kullanıl olduğunu kontrol eder. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın
- 60 gün boyunca AAD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılacazın. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi takdirde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayaran ve bu değeri cihaz veya HoloLens atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri OMA-URI metin kutusuna ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilebilir
    1. Değer izin verilen en az / en yüksek değer arasında olabilir.
1. Cihazları HoloLens ve her iki yapılandırmanın da cihaza uygulandığını doğrulayın. 
1. İnternet kullanılabilir olduğunda Azure AD 1 kullanıcısı oturum açmasına izin ver. Kullanıcı oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. İlke değeri X gün sayısına izin HoloLens azure AD kullanıcı 1 artık çevrimdışı duruma geçer ve bilgi noktası modu için bunu kullanabilir. 
1. 4. ve 5. adımlar diğer Tüm Azure AD kullanıcılarının N. Önemli noktası, bilgi noktası yapılandırmasının hedeflene Azure AD grubuna üye olup olmadığını belirleyecek şekilde herhangi bir Azure AD kullanıcılarının internet kullanarak cihazda oturum açması gerektir. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilinceye kadar "bağlantısız" ortamlarda belirtilen hata davranışıyla karşılana kadar. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri
- Kullanıcıların, sağlama paketleri eklemeyi veya kaldırmayı engelleme gibi belirli cihaz yönetimi ilkelerini yönetmesine izin verir.

2 cihaz için daha fazla yönetim seçeneğine izin HoloLens ilkeler. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni kod Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> [RemoteLock ile ilgili olarak,](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)HoloLens yalnızca ./Vendor/MSFT/RemoteLock/Lock yapılandırmasını destekler. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırmalar desteklenmiyor.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri
- Güç ilkeleri aracılığıyla HoloLens veya kilitlenirken daha fazla seçenek. 

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumları denetlemesine olanak sağlar. Her ilke hakkında daha fazla bilgi için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery ve DisplayOffTimeoutPluggedIn için bu iki yeni ilk, Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> 2. HoloLens tutarlı bir deneyim için, hem DisplayOffTimeoutOnBattery hem de StandbyTimeoutOnBattery değerlerinin aynı değer olarak ayarlanmış olduğundan emin olun. Aynı durum DisplayOffTimeoutPluggedIn ve StandbyTimeoutPluggedIn için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için Bkz. Boşta kalma [süreölçilerini](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) görüntüleme, uyku ve hazırda bekletme.

### <a name="newly-enabled-update-policies-for-hololens"></a>Yeni etkinleştirilen Güncelleştirme ilkeleri HoloLens
- Güncelleştirmelerin ne zaman yük devre dışı bırakıldığında veya güncelleştirmeleri sağlamak için Güncelleştirmeleri Duraklat düğmesinin devre dışı bırakılmasına yönelik diğer seçenekler.

Bu güncelleştirme ilkeleri artık 2 HoloLens etkinleştirilmiştir:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Bu güncelleştirme ilkeleriyle ilgili tüm ayrıntılar ve bu ilkelerin HoloLens cihazlar için nasıl kullanacağız? [güncelleştirmelerini yönetme HoloLens okuyabilirsiniz.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi
- Ayarlar Uygulamasında artan kullanıcı arabirimi denetimi, sınırlı sayıda sayfa göstermek için karıştırılabilir.

Artık, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkeyi etkinleştirmiş olduk. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

2. sayfada hangi sayfa ayarlarını özelleştirebileceğinizi HoloLens için lütfen Ayarlar [sayfasını ziyaret edin.](settings-uri-list.md) 
 
![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu
Araştırma Modundayken, HoloLens 2, görüntü görme araştırmalarında önemli bir araç haline gelir. Önceki sürümlere kıyasla, HoloLens 2 için Araştırma Modu aşağıdaki avantajlara sahiptir:
-   HoloLens (1. gen) araştırma modunda sunulan sensörlerden ek olarak, artık bir ivme ölçer, jroscope ve manyetik tometre dahil olmak üzere imu algılayıcı erişimi sağlıyoruz.
-   HoloLens 2, araştırma moduyla birlikte kullanılabilecek yeni yetenekler sağlar. Özellikle, daha zengin bir denemeleri kümesini sunabilme ve göz önünde bulundurun.

araştırmacılar artık, bu dış kullanıma açık ham görüntü algılayıcı akışlarına erişmek için HoloLens cihazlarında araştırma modunu etkinleştirme seçeneğine sahiptir. HoloLens 2 için araştırma modu, ivometer, jroscope ve manyetik tometer okumaları için de erişim sağlar. Kullanıcıların gizliliğini korumak için, ham göz izleme kamera görüntüleri araştırma modu aracılığıyla kullanılamaz, ancak var olan API 'Ler aracılığıyla göz korunun yönü mevcuttur.

Daha fazla teknik ayrıntı için [araştırma modu belgelerine](https://docs.microsoft.com/windows/mixed-reality/research-mode) göz atın.

### <a name="recording-length-increased"></a>Kayıt uzunluğu artırıldı
Müşteri geri bildirimi nedeniyle, [karma gerçeklik yakalamalarından](holographic-photos-and-videos.md)oluşan kayıt uzunluğunu artırdık. Karma Gerçeklik yakalamaları artık varsayılan olarak 5 dakikaya göre sınırlandırılamaz, bunun yerine kullanılabilir disk alanına göre en fazla kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanının %80 ' suna kadar kullanılabilir disk alanına göre maksimum video kaydetme süresini tahmin edecektir.

> [!NOTE]
> aşağıdakilerden biri gerçekleşirse HoloLens varsayılan video kayıt uzunluğunu (5 dakika) kullanacaktır:
> - Tahmini en fazla kayıt süresi varsayılan 5 dakikadan daha küçüktür.
> - Kullanılabilir disk alanı, toplam disk alanının %20 ' inden daha az.

Tüm gereksinimleri [holographic fotoğraflarınız ve videolar](holographic-photos-and-videos.md#maximum-recording-length) belgelerimizde bulabilirsiniz. 

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- OOBE 'deki daha fazla ekran artık koyu modda.
- Daha fazla bilgi edinin çevrimiçi gizlilik bildirimine en son çevrimiçi işaret etmelidir.
- Kullanıcıların, sağlama paketleri aracılığıyla VPN profilleri sağlayabildiği bir sorun oluştu.
- VPN bağlantısı için sabit proxy yapılandırması sorunu.
- AllowUsbConnection için NCM için MDM aracılığıyla USB işlevlerinin numaralandırılmasını devre dışı bırakma ilkesi güncelleştirildi.
- cihaz [tek uygulama bilgi noktası](hololens-kiosk.md)olarak ayarlandığında, bir HoloLens cihazının medya aktarım protokolü (MTP) üzerinden dosya gezgini 'nde gösterilmesini önleyen bir sorun ele alınmalıdır. MTP (genel olarak USB bağlantısının), [Allowusbconnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ilkesi kullanılarak hala devre dışı bırakılabileceğini unutmayın.
- Başlat menüsü simgelerin bilgi noktası modunda doğru şekilde ölçeklendirdiği bir sorun düzeltildi.
- Azure AD gruplarına hedeflenmiş bilgi noktası modu 'na engel olan HTTP önbelleklemesi nedeniyle bir sorun düzeltildi.
- Kullanıcıların, Geliştirici modunu devre dışı bırakmadığı ve yeniden etkinleştirmedikleri takdirde, sağlama paketleri ile Geliştirici modunu etkinleştirdikten sonra çift bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, sürüm 1903-Kasım 2020 güncelleştirme
- Derleme 18362,1085

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermiyor; Holographic, sürüm 20h2 olan en son özellik yayın Windows derlemesini denemenizi öneririz.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, sürüm 2004-Ekim 2020 güncelleştirme
- Derleme 19041,1124
 
Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çalışma zamanı sistem hatasına neden olan gereksiz bir denetim kaldırıldı.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, sürüm 1903-Ekim 2020 güncelleştirme
- Derleme 18362,1081

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez Windows Holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, sürüm 2004-Eylül 2020 güncelleştirme
- Derleme 19041,1117

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- appxmanifest 'de SupportsMultipleInstances = "true" olduğunda Visual Studio bir uygulamada hata ayıklamayı önleyen bir sorunu giderir.
- Bu sürüm, ağ proxy 'si üzerinden başarısız olan Internet algılamayı ele almak için NCSı proxy algılama düzeltmesini içerir. NCSı, Internet bağlantısı algılaması için makine ara sunucusunu ve profil başına proxy 'yi kullanabilir. Kullanıcı başına proxy, gelecek sürümde NCSı tarafından desteklenecektir.
- çoğu Windows Mixed Reality cihazda, kullanıcının başı ileri doğru görünen bir bağımsız konumda olduğunda, ileri yönlü vektör, başa paraleldir. ancak, HoloLens 2 ' nin önceki sürümleri, bir yandan, ideal yönlendirmeye göre birkaç derece aşağı doğru bir şekilde aşağı doğru bir şekilde aşağı hizalanmış şekilde, vektör 'yi görüntüleme paneline dikey olacak şekilde hizalı HoloLens 2 ' nin daha yeni sürümleri, form faktörleri arasında anlam tutarlılığı sağlamak için bunu düzeltmedi.
- Belirli senaryolarda daha az izleme kaybına neden olacak gelişmiş ve izleme sağlamlık.
- Bu sürümde, video yakalama sorunlarına katkıda bulunan ses zaman damgası kalitesini geliştirmek için bir çözüm bulunur.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, sürüm 1903-Eylül 2020 güncelleştirme
- Derleme 18362,1079

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- çoğu Windows Mixed Reality cihazda, kullanıcının başı ileri doğru görünen bir bağımsız konumda olduğunda, ileri yönlü vektör, başa paraleldir. ancak, HoloLens 2 ' nin önceki sürümleri, bir yandan, ideal yönlendirmeye göre birkaç derece aşağı doğru bir şekilde aşağı doğru bir şekilde aşağı hizalanmış şekilde, vektör 'yi görüntüleme paneline dikey olacak şekilde hizalı HoloLens 2 ' nin daha yeni sürümleri, form faktörleri arasında anlam tutarlılığı sağlamak için bunu düzeltmedi.
- Belirli senaryolarda daha az izleme kaybına neden olacak gelişmiş ve izleme sağlamlık.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, sürüm 2004-Ağustos 2020 güncelleştirme
- Derleme 19041,1113

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Ayarlar uygulama artık kullanıcıyı ıris kayıt veya göz izleme ayarlaması deneyimlerine göre takip edemeyecektir.
- Bir sağlama paketinin, cihazı yeniden adlandıran ve diğer eylemleri gerçekleştiren (bir ağa bağlanma gibi) bir hata düzeltildi, yeniden adlandırma nedeniyle cihaz yeniden başlatıldıktan sonra diğer eylemleri gerçekleştiremeyebilir.
- Görsel kaliteyi artırmak için ilk cihaz kurulumu akışlarının değiştirilen renk şeması.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, sürüm 1903-Ağustos 2020 güncelleştirme
- Derleme 18362,1074

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez Windows Holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, sürüm 2004-2020 Temmuz güncelleştirmesi
- Derleme 19041,1109

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Geliştiriciler artık cihaz portalının etkinleştirilmesi veya devre dışı bırakılması arasında güvenli bir bağlantı yapılmasını tercih edebilir.
- Uygulama, işletim sistemi güncelleştirmelerinden sonra başlatıldığında geliştirildi.
- Varsayılan gelen kutusu parlaklığı yüzde 100 olarak değiştirildi.
- HoloLens 2 ' de Windows cihaz portalı için HTTPS iletimi hakkında bir sorun oluştu.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, sürüm 1903-2020 Temmuz güncelleştirmesi
- Derleme 18362,1071

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İzlemeyi kaybetmekte veya geri alma sırasında Unity uygulamalarında hologramlar ortadan silinmesine neden olabilecek bir sorun düzeltildi.
- özel HoloLens uygulamalarının, bazı cihazlarda donanım hızlandırmaya sahip HoloLens Emulator kullanırken kabuğa geri çökmesine neden olan bir sorun düzeltildi.
- HoloLens 2 ' de Windows cihaz portalı için HTTPS iletmeyle ilgili bir sorun oluştu.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, sürüm 2004-Haziran 2020 güncelleştirme
- Derleme 19041,1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC video etkisi*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (modern kulaklık))
  - *MRC ses efekti* üzerinde:
    - loopgeri kazanç (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "uygulama sesi kazancı" değeri)
    - mikro phonekazancı (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "mıc ses kazancı" değeri)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmak için bir hata düzeltildi. Özellikle, bu onarım, **Başlat** menüsü görüntülenirken kayıtta ses bozuklubir şekilde ortadan kaldırmalıdır.
- Kayıtlı videolarda, iyileştirilmiş hologram kararlılığı.
- Cihaz, birden çok gün için bekleme durumunda kapatıldıktan sonra karma gerçeklik yakalamanın video kaydedemediği bir sorun çözüldü.
- HolographicSpace. Uservarlığına yönelik API genellikle Unity uygulamaları için devre dışıdır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilmiş olsa bile, bazı uygulamaların, vizörü çevrildikten sonra duraklamasını engelleyen bir sorunu önler. API artık 2018.4.18 ve üzeri ve 2019.3.4 ve üzeri Unity sürümleri için etkinleştirilmiştir.
- Cihaz portalına bir Wi-Fi bağlantısı üzerinden eriştiğinizde, bir Web tarayıcısı geçersiz bir sertifika nedeniyle erişimini engelleyebilir. Tarayıcı, daha önce güvenilir olsa bile "ERR_SSL_PROTOCOL_ERROR," gibi bir hata bildirebilir. Bu durumda, güvenlik uyarılarını yok saymaya yönelik bir seçenek olmadığından cihaz portalına ilerleyemiyorum. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası önceden indirildiyse ve tarayıcı güvenliği uyarılarını kaldırmak için bir PC 'de güvenilir ise ve SSL hatası oluşursa, tarayıcı güvenliği uyarılarını karşılamak için yeni sertifikanın indirilip güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilme çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların Karma Gerçeklik giriş girişlerinden tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- Piksel biçimlerini, HoloLens işleyicisinde siyah olarak işilecek şekilde değiştiren uygulamalara neden HoloLens düzeltildi.
- Iris oturum açma sırasında kilitlenmeye neden olan bir hata düzeltildi.
- Zaten geçerli olan uygulamalar için yinelenen mağaza indirmeleri ile ilgili bir sorun düzeltildi.
- Çevreleyici uygulamaların arka arkaya yeniden açılmasını engelleyen Microsoft Edge düzeltildi.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.
- Geliştirilmiş performans ve güvenilirlik.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, sürüm 1903 - Haziran 2020 Güncelleştirmesi
- Derleme 18362.1064

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri, belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MicrophoneGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, arka planda çalıştıracak ayar etkinleştirilse bile, bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Piksel biçimlerini, HoloLens olarak siyah olarak değiştiren uygulamalara neden olan bir sorun HoloLens Emulator.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, sürüm 2004  
- Derleme - 19041.1103

HoloLens 2, Windows Holographic için Mayıs *2020* ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5G/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni özellikler içerir. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve   Güncelleştirmeleri **Kontrol Edin düğmesini** ****   seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak yeni cihazları üretim için önceden yapılandırma ve sorunsuz bir şekilde ayarlama                 |
|       FIDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamasını etkinleştirmek için FIDO2 Güvenlik Anahtarları desteği            |
|       Geliştirilmiş sağlama                      |          Usb sürücüden uygulamanıza sorunsuz bir şekilde bir sağlama paketi HoloLens                              |
|       Uygulama yükleme durumu                 |          Uygulamalar için uygulamanın MDM Ayarlar 2'ye HoloLens yükleme durumunu denetleme               |
|       Yapılandırma hizmeti sağlayıcıları (CSP'ler)   |          Yönetici denetimi özelliklerini geliştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği 5G/LTE desteği sağlar                                    |
|       Koyu uygulama modu                              |          Hem koyu hem de açık modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir ve görüntüleme deneyimini geliştirin        |
|       Sesli komutlar                             |          Uygulamalı ses denetimi için ek sistem HoloLens desteği                           |
|       El izleme geliştirmeleri                 |          El izleme geliştirmeleri düğmeleri ve 2D sayfalı etkileşimleri daha doğru hale sağlar                        |
|       Kalite geliştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik geliştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot desteği

Windows HoloLens 2 için Autopilot, cihaz satış kanalının Intune kiracınıza HoloLens önceden kaydolmasına olanak sağlar. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazır olur. Kendi kendine dağıtımdan yararlanmak için cihazın kurulumun ilk ekranı sırasında USB-C-Ethernet kullanarak bir ağa bağlanması gerekir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başladıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme.
1. Cihazı Microsoft Intune (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.
1. Cihaz hedefli ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlama.
1. Oturum açma ekranı kullanıcıya gösterilir.

[HoloLens 2 değerlendirme Windows Autopilot'ta daha fazla bilgi edinin.](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Şimdi AutoPilot önizlemeye katılmak için Hesap Yöneticinize ulaşın. Autopilot'a hazır cihazlar yakında gönderime başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar, HoloLens veya okul ortamındaki diğer kullanıcılarla bir cihaz paylaşır. Bu nedenle, kullanıcıların uzun kullanıcı adları ve parolalar yazmadan kolayca ulaşabiliyorları önemlidir. Hızlı Kimlik Çevrimiçi (FIDO), bir kullanıcı adı veya parola girmeden, kuruluşta (Azure AD kiracısı) HoloLens oturum açmasına olanak sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktöründe getirilebilir, standartlara dayalı bir parolasız kimlik doğrulama yöntemidir. FIDO, parolasız kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kaynaklarında kullanıcı adı veya parola olmadan oturum açmalarına olanak sağlar. Bunun yerine bir dış güvenlik anahtarı veya cihazda yerleşik olarak yer alan bir platform anahtarı kullanırlar.

Çalışmaya başlama için [bkz. Parolasız güvenlik anahtarı oturum açmasını etkinleştirme.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Paketleri sağlama, HoloLens deneyimi yerine yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamayı sağlar. Daha önce, sağlama paketlerinin şirket içi belleğe HoloLens vardı. Artık bir USB sürücüde olabilir, böylece birden çok cihaz üzerinde daha kolay HoloLens ve cihazları paralel olarak silebilirsiniz. Paket sağlama artık cihaz yönetimine kaydolmak için bir alanı da desteklemektedir, bu nedenle sağlama sonrasında el ile kurulum yoktur.

Denemek için:

1. Windows Windows Configuration Designer'ın en son sürümünü Windows bilgisayarınıza indirin.
1. 2 **HoloLens Cihazları**  >  **Sağlama'HoloLens'yi seçin.**
2. Yapılandırma profilinizi oluşturun. Ardından, oluşturulan tüm dosyaları bir USB-C depolama cihazına kopyalayın.
3. USB-C cihazını yeni yanıp sönen herhangi bir cihaza HoloLens. Ardından, sağlama **paketinizi**  +  **uygulamak** için güç düğmesine basın.

### <a name="line-of-business-application-install-status"></a>İş yeri uygulaması yükleme durumu

İş hattı uygulamaları için MDM uygulama dağıtımı ve yönetimi, uygulama yönetimi HoloLens. Yöneticilerin ve kullanıcıların denetim ve tanılama için uygulama yükleme durumunu görüntülemesi gerekir. Bu sürümde, hesap bilgilerinize Ayarlar veya okula erişim için daha fazla ayrıntı  >    >    >    >  **ekledik.**

### <a name="additional-csps-and-policies"></a>Ek CSP'ler ve ilkeler

Yapılandırma [hizmeti sağlayıcısı (CSP),](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu sürümde, yöneticilerin cihazlara dağıtılmış ve dağıtılmış denetimlerini artırmak için daha fazla ilkeye HoloLens ekleeceğiz. HoloLens tarafından desteklenen CSP'ler listesi için bkz. [NetworkQoSPolicy CSP.](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Bu sürümde yeni olan:

**İlke CSP'si** 

İlke yapılandırma hizmeti sağlayıcısı, kuruluşa cihazlarda ilke yapılandırma Windows sağlar. Bu sürümde, burada listelenen HoloLens için yeni ilkeler ekledik. Daha fazla bilgi için [bkz. 2. HoloLens tarafından desteklenen İlke CSP'leri.](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessAccessAccesseInput 
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

5 g/LTE telefonlar ve Wi-Fi etkin noktalar gibi belirli mobil geniş bant cihazlarının USB üzerinden HoloLens 2 ' ye tethered oldukları durumlarda etkinleştirilmesi için destek eklenmiştir. Bu cihazlar artık farklı bir Ethernet bağlantısı olarak **ağ ayarlarında** görüntülenmektedir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmez.) Bu işlevsellik Wi-Fi kullanılabilir olmadığında yüksek bant genişliğine sahip bağlantılara izin verebilir ve Wi-Fi internet paylaşımı yeterince iyi değildir. desteklenen USB cihazları hakkında daha fazla bilgi edinmek için bkz. [Bağlan Bluetooth ve USB-C cihazları](https://docs.microsoft.com/hololens/hololens-connect-devices).  

### <a name="hand-tracking-improvements"></a>İzleme geliştirmeleri

Bu sürüm çeşitli izleme geliştirmeleri içerir:

- **İşaret pozu kararlılığı:** Sistem artık, Palm tarafından occlukal aldığında Dizin parmak yerini geri alır. Bu değişiklik, düğmeleri gönderdiğinizde, içerik yazarken ve daha fazlasını yaparken doğruluğu artırır! 
- **Azaltılmış, yanlışlıkla hava dokunmalar:** Hava dokunma hareketini algılamayı geliştirdik. Artık birkaç yaygın senaryoda (örneğin, ellerinizi yüzlerinizi bıraktığınızda) daha az yanlışlıkla etkinleştirme vardır.
- **Kullanıcı anahtarı güvenilirliği:** Bir cihaz paylaştığınızda el ile sistem boyutunu güncelleştirmek daha hızlı ve daha güvenilirdir.
- **Azaltılmış el çalma:** Sensörlerden ikiden fazla elinin bulunduğu durumların işlenmesini geliştirdik. Birden çok kişi birlikte çalışıyorsa, izlenen kişinin kullanıcıdan sahnedeki başka birinin adına "atlayacağı" bir şansınız daha düşüktür.
- **Sistem güvenilirliği:** Cihaz yüksek yük altında olduğunda bir yandan izlemenin çalışmayı durdurmasına neden olan bir sorun düzeltildi.

### <a name="dark-mode"></a>Koyu mod

birçok Windows uygulama artık koyu ve hafif modları desteklemektedir. HoloLens 2 kullanıcı, her ikisini de destekleyen uygulamalar için varsayılan modu seçebilirler. güncelleştirme sonrasında, varsayılan uygulama modu "koyu" olur, ancak bu ayarı kolayca değiştirebilirsiniz: **Ayarlar**  >  **sistem** renkleri ' ne gidin  >    >  **varsayılan uygulama modunu seçin**. 

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

Artık, cihazdaki herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için bkz. [HoloLens çalıştırmak için sesinizi kullanma](https://docs.microsoft.com/hololens/hololens-cortana). ayrıca [HoloLens 2 için desteklenen diller](https://docs.microsoft.com/hololens/hololens2-language-support)bölümüne bakın.  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

güncelleştirilmiş uygulama, cihazlarınız arasında daha fazla işlem yapmanıza yardımcı olmak için Microsoft 365 ile tümleşir (şu anda yalnızca US-English). HoloLens 2 ' de, Cortana birimi ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklememektedir. Bu seçenekler artık yeni sistem ses komutları tarafından desteklenmektedir. [blogumuza](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)yeni Cortana uygulaması hakkında daha fazla bilgi edinin.

### <a name="quality-improvements-and-fixes"></a>Kalite iyileştirmeleri ve düzeltmeleri

Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:  
- Etkin bir görüntüleme ayarlama sistemi sunuldu. Bu özellik hologragram kararlılığını ve hizalamasını geliştirir. Başlarınızı yan yana hareket ettirmek için artık yerinde kalabilirler.
- Wi-Fi akışının HoloLens düzenli aralıklarla kesintiye uğradığından hata düzeltildi. Bir uygulama düşük gecikmeli akış için ihtiyacı olduğunu gösteriyorsa, [Setsocketmediastreamingmode işlevini](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)çağırarak bu çözümü uygulayın.
- Araştırma modunda akış sırasında oluşan bir cihaz askıda kalması düzeltildi.
- Bir oturum sürdürülürken, bazı durumlarda oturum açma ekranında doğru kullanıcının görüntülenmediğini bir hata düzeltildi.
- kullanıcıların MDM günlüklerini **Ayarlar** aracılığıyla dışarı aktarmadık bir sorun düzeltildi.
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
- bir sorun, cihazı "Hey Cortana" ses etkinleştirmesini kullanacak şekilde başlattıktan sonra Cortana uygulamasını başlatmanız gerekir. bir 18362 yapıdan güncelleştirdiyseniz, artık **başlangıç** aşamasında çalışmamış Cortana uygulamasının önceki sürümü için ikinci bir uygulama kutucuğu görebilirsiniz.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, sürüm 1903-Mayıs 2020 güncelleştirme 
- Derleme 18362,1061

bu aylık kalite güncelleştirmesi, daha önce açıklandığı gibi, takım Windows Holographic sürüm 2004 ' de çalıştığı için herhangi bir önemli değişikliği içermez.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, sürüm 1903-Nisan 2020 güncelleştirme
- Derleme 18362,1059

**Desteklenen uygulamalar için koyu mod** 

birçok Windows uygulama hem koyu hem de hafif modunu destekler. HoloLens 2 müşteri artık hem renk düzenlerini destekleyen uygulamalar için varsayılan modu seçebilirler. müşteri geri bildirimlerine bağlı olarak, varsayılan uygulama modunu "koyu" olarak ayarlarız, ancak bu ayarı dilediğiniz zaman kolayca değiştirebilirsiniz: **"varsayılan uygulama modunu seçin"** bulmak için **Ayarlar > sistem > rengine** gidin.

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

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, sürüm 1903-Mart 2020 güncelleştirme 
- Derleme 18362,1056

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- *Holographicdepthreprojection, oto planar* algoritması kullanıldığında karma gerçeklik yakalamadaki iyileştirilmiş hologram kararlılığı.
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
- Sanal uygulama açılana ve kapatılana kadar holografik uygulamaların başlangıçta duraklatılmış durumda Başlat menüsü sorunları düzeltildi.
- OpenXR çalışma zamanı uyumluluk düzeltmeleri ve HoloLens 2 ve öykünücü için geliştirmeler.
