---
title: HoloLens 2 sürüm notu
description: Her yeni sürüm ve 2 yayında yapılan tüm HoloLens takip edin.
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
ms.openlocfilehash: 1de9687174bf9c1de2e2b15ee03aa841254b0b82
ms.sourcegitcommit: 2988afb1d7792c9e4bae15485cd52d6eff7e27c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2021
ms.locfileid: "113685057"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notu

Yeni cihazlarınızı kullanarak verimli bir deneyim HoloLens için özellik, hata ve güvenlik güncelleştirmelerini yayınlaya devam edeceğiz. Bu sayfada, her ay yeni HoloLens görebilirsiniz. En son HoloLens 2 güncelleştirmesini almak için, güncelleştirmeleri kontrol edebilirsiniz ve el ile güncelleştirebilir veya Tam Flash Güncelleştirme'yi (FFU) Gelişmiş Kurtarma Yardımcı'sı aracılığıyla cihazınızı [](hololens-update-hololens.md#check-for-updates-and-manually-update) söntebilir. [](hololens-recovery.md#clean-reflash-the-device) İndirme [güncel](https://aka.ms/hololens2download) tutulur ve genel kullanıma açık en son derlemeyi sağlar.

> [!NOTE]
> Son Windows 11 duyurusu, 11'in bilgisayar sürümüne Windows. Kısa süre [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) önce Mayıs 2021'de HoloLens 2'ye büyük bir işletim sistemi güncelleştirmesi başlattık ve bu düşüş için müşteri geri bildirimlerine dayanarak gelecek bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)derlememizde Remote Assist kullanıcılarını etkileyen bilinen bir sorun nedeniyle, Windows Holographic sürüm 21H1 güncelleştirmelerinin tekliflerini geçici olarak duraklatıldık. Ayrıca varsayılan Gelişmiş Kurtarma Yardımcı (ARC) derlemesini [Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi olarak değiştirdik.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) ARC derlemesi artık 21H1 derlemeyi hedeflemeye devam edecek.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1 - Temmuz 2021 Güncelleştirmesi
- Derleme 20348.1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Hem tümleşik hem de ayrık grafik bağdaştırıcıları olan bir pc üzerinde HoloLens 2 Emulator kullanırken öykünücü çoğu durumda daha az güçlü tümleşik bağdaştırıcıyı kullansa da çoğu durumda donanım grafik hızlandırmasını etkinleştirecek.  Daha önce donanım hızlandırma etkinleştirilmediyse, genellikle Kod 43 ile bir grafik hatası bildiriliyor.  Bazı durumlarda öykünücü başarıyla önyüklanmaz, ancak şimdi önyükler.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi Ayarlar -Wi-Fi > Ağ & İnternet **-> Durumu ->** Özellikler'den başlatılamadığına ilişkin bir sorun düzeltildi.
- ESIM sertifikalarının işletim sistemi güncelleştirmeleri arasında kaldırılmasıyla ilgili bir sorun giderildi. Bu düzeltme, 21H1 sürümüne güncelleştirmeden önce eSIM sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- Önceden yüklenmiş uygulamaları işletim sistemi sıfırlamaları arasında etkileyen bir sorun düzeltildi. 
- Artan CPU yüklemesi ile ücretlendirme sırasında çalışma zamanını artırmak için pil ücretlendirme performansı ayarlanmıştır.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – Temmuz 2021 Güncelleştirmesi
- Derleme 19041.1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır. 
- Hem tümleşik hem de ayrık grafik bağdaştırıcıları olan bir pc üzerinde HoloLens 2 Emulator kullanırken öykünücü çoğu durumda daha az güçlü tümleşik bağdaştırıcıyı kullansa da çoğu durumda donanım grafik hızlandırmasını etkinleştirecek.  Daha önce donanım hızlandırma etkinleştirilmediyse, genellikle Kod 43 ile bir grafik hatası bildiriliyor.  Bazı durumlarda öykünücü başarıyla önyüklanmaz, ancak şimdi önyükler.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1 - Haziran 2021 Güncelleştirmesi
- Derleme 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive veya okul kameralarını karşıya yükleme

HoloLens 2 Ayarlar uygulamasına, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın Pictures > Camera Roll klasöründen iş veya okul için ilgili OneDrive klasörüne otomatik olarak yüklemelerini sağlayan yeni bir özellik ekledik. Bu özellik, HoloLens 2'de [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) uygulamasındaki bir özellik boşluğuna yöneliktir. Bu, yalnızca müşterinin kişisel hesabına (iş veya okul hesabı değil) otomatik Kamera Microsoft hesabı yüklemesini destekler.

**Nasıl çalışır?**

- "Kamera **Ayarlar >" > için System > Mixed Reality Camera'ı** ziyaret edin.
- Bu özellik Açık  konuma ayarlanır ve cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları otomatik olarak iş veya okul hesabı için > fotoğraf makinenizin Pictures > Camera Roll klasörüne OneDrive kuyruğa eklenir.
    >[!NOTE]
    >Bu özellik etkinleştirilmeden önce yakalanan fotoğraflar ve *videolar karşıya* yükleme için kuyruğa yüklenmez ve yine de el ile karşıya yüklenmeleri gerekir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yüklenmeyi bekleyen dosyaların sayısını görüntüler (veya bekleyen tüm dosyalar karşıya OneDrive "güncel" olarak görünür).
- Bant genişliği konusunda endişe ediyorsanız veya herhangi bir nedenle karşıya yüklemeyi "duraklatmak" için özelliği Kapalı konuma **geçebilirsiniz.** Özelliği geçici olarak devre dışı bırakmak, Kamera Roll klasörüne yeni dosya ekleyinceye kadar karşıya yükleme kuyruğunda artış devam eder, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmez.
- En yeni dosyalar ilk olarak karşıya yüklensin (son, ilk çıkar).
- Hesap OneDrive sorunları varsa (örneğin, parolanız değiştikten  sonra) Yeni bir düzeltme düğmesi Ayarlar görüntülenir.
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklemesi daha uzun sürer (özellikle karşıya yükleme bant genişliğiniz kısıtlanmışsa). Büyük bir dosya karşıya yükleme sırasında karşıya yüklemeyi "duraklatır" veya kapatırsanız, kısmi karşıya yükleme korunur. Karşıya yükleme "duraklatıldı" veya devre dışı bırakıldıklarından birkaç saat içinde yeniden etkinleştirilirse, karşıya yükleme bıraktığı yerden devam eder. Ancak, karşıya yükleme birkaç saat sonra yeniden etkinleştirilirse, büyük dosyanın karşıya yüklemesi en baştan yeniden başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayar, geçerli bant genişliği kullanımına göre yerleşik azaltmaya sahip değil. Başka bir senaryo için bant genişliğini en üst düzeye çıkarmanız gerekirse ayarı el ile kapatın. Upload duraklatılır, ancak özellik Yeni eklenen dosyaları Kamera Roll'e izlemeye devam eder. Devam etmek için hazır olduğunda karşıya yüklemeyi yeniden etkinleştirin.
- Bu özellik cihaza her kullanıcı hesabı için etkinleştirilmelidir ve yalnızca o anda cihazda oturum açık olan kullanıcı için dosyaları etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasında karşıya yükleme sayısını izlerken fotoğraf veya video sürüyorsanız, geçerli dosya karşıya yükleme tamamlanana kadar bekleyen dosya sayısı değişmez.
- Upload uykuda düşerse veya kapalı olursa, cihaz duraklatılır. Bekleyen karşıya yüklemelerin tamamlandığından emin olmak için, Ayarlar sayfası "OneDrive güncel" olana kadar cihazı etkin bir şekilde kullanın veya **Power & ayarlarını** yapın.
### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri artık 2. HoloLens desteklemektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx, uygulamanın Telemetri ve davranış üzerinde tam denetime sahip Ayarlar kullanılmalıdır.

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Renk ayarlama ile videonun büyük bozulmalarını düzeltir.
- Power menüsünde metnin kesilmesine neden olan bir sorunu gidermek.
- RequirePrivateStoreOnly ilkesi için destek sağlar.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi
- Derleme 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri artık 2. HoloLens desteklemektedir:
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx, uygulamanın Telemetri ve davranış üzerinde tam denetime sahip Ayarlar kullanılmalıdır.

Holographic sürüm 21H1'Windows en son derlememizi denemeyi teşvik ederiz.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, sürüm 1903 - Haziran 2021 Güncelleştirmesi
- Derleme 18362.1116

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

>[!IMPORTANT]
> Bu derleme artık hizmette olmayacaktır.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, sürüm 21H1
- Derleme 20346.1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihaz üzerinde herkes tarafından kullanılan özellikler ve IT Yöneticileri tarafından yapılandırılan yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda her hedef kitleyle ilgili özellikler açıklanmıştır. BIR IT Yöneticisiyseniz lütfen IT Yöneticisi - Güncelleştirme Denetim [Listesi'ne göz atın.](#it-admin---update-checklist)
>[!IMPORTANT]
>Bu derlemeye güncelleştirmek için HoloLens 2 cihazın Şubat 2021 güncelleştirmesini (derleme 19041.1136) veya daha yenisini çalıştıracak olması gerekir. Bu özellik güncelleştirmesini görmüyorsanız lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>Bugün Microsoft HoloLens 2, aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmeleri) destekler:
>- Windows Holographic, sürüm 20H2 (Derleme 19041.1128+)
>- Windows Holographic, sürüm 2004 (Derleme 19041.1103+)
>- Windows Holographic, sürüm 1903 (Derleme 18362+) 
>
> Windows Holographic sürüm 21H1'in tanıtımıyla, Windows Holographic sürüm **1903** için aylık bakım güncelleştirmelerini sonlandırıyoruz. Bu sayede daha yeni sürümlere odaklanarak değerli geliştirmeler yapmaya devam edeceğiz. 


| Özellik Adı                                              | Kısa açıklama                                                                      | Hedef kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | yeni Chromium tabanlı Microsoft Edge artık HoloLens 2 ' de kullanılabilir. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyicisi](#webxr-and-360-viewer) | Modern Web deneyimleri ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
[yeni Ayarlar uygulaması](#new-settings-app) | eski Ayarlar uygulaması, yeni özellikler ve ayarlarla güncelleştirilmiş bir sürüm ile değiştiriliyor. | Son Kullanıcı |
[Ekran renk ayarı](#display-color-calibration) | HoloLens 2 görüntü için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama birimi denetimi başına](#per-app-volume-control) | Uygulama düzeyi birimini sistem biriminden bağımsız olarak denetleyin. | Son Kullanıcı |
[Web uygulamalarını yükler](#install-web-apps) | web uygulamalarını, yeni Microsoft Edge tarayıcıyla Microsoft Office gibi HoloLens 2 ' ye yükler. | Son Kullanıcı |
[Türe göre kaydırın](#swipe-to-type) | Holographic klavyesinde "çekme" kelimelerinizin ucunu kullanın. | Son Kullanıcı |
[Başlangıç menüsünde güç menüsü](#power-menu-from-start) | başlat menüsünde HoloLens cihazı yeniden başlatın ve kapatın. | Son Kullanıcı |
[Oturum açma ekranında birden çok Kullanıcı listelendi](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüleyin. | Son Kullanıcı |
[USB-C dış mikrofon desteği](#usb-c-external-microphone-support) | Uygulamalar ve/veya uzaktan yardım için USB-C mikrofonlar kullanın. | Son Kullanıcı |
[Kiosks için ziyaretçi otomatik oturum açması](#visitor-auto-logon-for-kiosks) | Bilgi noktası modlarında kullanılacak ziyaretçi hesaplarında otomatik oturum açmayı sağlar. | BT Yöneticisi |
[Bilgi noktası modundaki yeni uygulamalar için yeni AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | yeni Ayarlar ve Edge uygulamaları için aumıds. | BT Yöneticisi |
[Geliştirilmiş bilgi noktası modu hata teslim](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlangıç menüsünden önce Global olarak atanan erişimi arar. | BT Yöneticisi |
[sayfa Ayarlar görünürlüğü için yeni settingsurin](#new-settings-uris-for-page-settings-visibility) | 20 + yeni settingsurin Ayarlar/pagevisibilitylist ilkesi içindir. | BT Yöneticisi |
[Geri dönüş tanılamayı yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Ayarlar uygulamasında geri dönüş tanılama davranışı ayarlanıyor. | BT Yöneticisi |
[Yakındaki cihazlarla şeyleri paylaşma](#share-things-with-nearby-devices) | dosya veya url 'leri bir HoloLens bilgisayara paylaşabilirsiniz. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | işletim sistemi güncelleştirmelerine yönelik Ayarlar yeni sorun giderici. | BT Yöneticisi |
[Teslim Iyileştirme önizlemesi](#delivery-optimization-preview) | birden çok HoloLens cihazdan yüklemeler için bant genişliği tüketimini azaltma. | BT Yöneticisi |

İlgili sürüm notlarını gözden geçirin:

- [HoloLens Emulator arşivini ziyaret edin](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 uzaktan yardım](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 kılavuzlar](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge tanıtımı

![eski Microsoft Edge logosunun yeni Microsoft Edge logoa animasyonu](images/new-edge.gif)

yeni Microsoft Edge, müşteriler için daha iyi uyumluluk ve web geliştiricileri için web 'in daha az parçalanması oluşturmak üzere [Chromium açık kaynaklı projeyi benimsemektedir](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) .

> [!IMPORTANT]
> bu yeni Microsoft Edge, yeni sürümlerde [artık desteklenmeyen](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) eski Microsoft Edge otomatik olarak değiştirir.

![yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni Microsoft Edge başlatılıyor

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil girdap simgesiyle gösterilir) Başlat menüsü sabitlenmiştir ve bir web bağlantısını etkinleştirdiğinizde otomatik olarak başlatılır.

> [!NOTE]
> yeni Microsoft Edge HoloLens 2 ' de ilk kez başlattığınızda, ayarlarınız ve verileriniz eski Microsoft Edge içeri aktarılır. yeni Microsoft Edge başlattıktan sonra eski Microsoft Edge kullanmaya devam ederseniz, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge eşitlenmeyecektir.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni Microsoft Edge ilke ayarlarını yapılandırma

yeni Microsoft Edge, bt yöneticilerine HoloLens 2 ' de eski Microsoft Edge ile daha geniş bir tarayıcı ilkeleri kümesi sunar.

Yeni Microsoft Edge ilke ayarlarını yönetme hakkında daha fazla bilgi edinmek için bazı yararlı kaynaklar aşağıda verilmiştir:

- [Microsoft Intune ile Microsoft Edge ilkesi ayarlarını yapılandırma](/deployedge/configure-edge-with-intune)
- [Microsoft Edge ilke eşlemesine Microsoft Edge'in eski sürümü](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Microsoft Edge ilke eşleme için Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- tam [Microsoft Edge Enterprise belgeleri](/deployedge/)

> [!IMPORTANT]
> yeni Microsoft Edge tarafından desteklenen tarayıcı ilkelerinin hacmi nedeniyle, takımımız her yeni ilkenin HoloLens 2 ' de çalıştığından emin olamaz. ancak, daha önce HoloLens 2 ' de desteklenen her bir eski Microsoft Edge ilkesinin Microsoft Edge denk olarak sınanmış ve onayladık. HoloLens 2 ile kullandığınız her bir eski Microsoft Edge tarayıcı ilkesinin yeni Microsoft Edge eşdeğerini bulmak için [Microsoft Edge ilke eşlemesine Microsoft Edge'in eski sürümü](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) bakın.
>
> HoloLens 2 *ile çalışabildiğinizi* bildiğiniz en az iki yeni Microsoft Edge ilkesi vardır:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL 'Si

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 ' de yeni Microsoft Edge bekleneceğiniz

yeni Microsoft Edge yeni bir uwp bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan, bu, yalnızca HoloLens 2 gibi UWP cihazlarda çalışmasına izin vererek bazı özellikler hemen kullanılamayabilir. Önümüzdeki aylarda yeni senaryolar ve Özellikler destekliyoruz, bu nedenle bu alanı güncel bilgiler için denetleyin.

**Çalışması beklenen senaryolar ve Özellikler:**
- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri, beklendiği gibi işlenmeli ve davranmalıdır
- Çoğu tarayıcı işlevinin (Sık Kullanılanlar, geçmiş, vb.) beklenen şekilde çalışması gerekir
- Koyu mod
- Cihaza Web uygulamaları yükleme
- uzantılar yükleniyor (lütfen HoloLens 2 ' de düzgün çalışmayan uzantıları kullanıyorsanız bize bildirin)
- PDF 'YI görüntüleme ve işaretleme
- Tek bir tarayıcı penceresinden uzamsal ses
- Tarayıcının otomatik ve el ile güncelleştirilmesi
- PDF 'YI yazdırma menüsünden kaydetme ("PDF 'ye Kaydet" seçeneğini kullanarak)
- WebXR ve 360 Viewer uzantısı
- Ortamınıza yerleştirilmiş birden çok pencere arasında gezinerek, doğru pencereye içerik geri yükleme

**Çalışması beklenen senaryolar ve Özellikler:**
- Eşzamanlı ses akışları ile birden çok pencere arasındaki uzamsal ses
- "Görüntüleyin, söyleyin"
- Yazdırma

**Bilinen en iyi tarayıcı sorunları:**

- Yeni Microsoft Edge için holographic klavyesindeki Büyüteç önizlemesi devre dışı bırakıldı. Büyütme doğru şekilde çalışmaya başladıktan sonra bu özelliği gelecekteki bir güncelleştirmede yeniden etkinleştirmek isteriz.
- Başka bir tarayıcı penceresi açık ve etkin olduğunda ses yanlış tarayıcı penceresinden oynayabilir. Ses oynatılması beklenen diğer etkin pencereyi kapatarak Bu soruna geçici bir çözüm bulabilirsiniz.
- ["Beni takip etme" modunda](hololens2-basic-usage.md#follow-me-stop-following)bir tarayıcı penceresinden ses çalarken, "beni izle" modunu devre dışı bıraktığınızda ses çalmaya devam edecektir. "Beni Izle" modunu devre dışı bırakmadan veya **X** düğmesi ile pencereyi kapatarak bu sorunu geçici olarak çözebilirsiniz.
- active Microsoft Edge windows ile etkileşim kurmak, diğer 2b uygulama pencerelerinin beklenmedik şekilde etkin olmasına neden olabilir. Bu pencereleri yeniden etkileşimde bulunarak tekrar etkinleştirebilirsiniz.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Microsoft Edge ekibi, Edge ınsider community için üç önizleme kanalı sağlar: Beta, Dev ve canary. önizleme kanalının yüklenmesi, HoloLens 2 ' Microsoft Edge yayınlanan sürümünü kaldırmaz ve aynı anda birden fazla yükleyebilirsiniz. 

Edge ınsider community hakkında daha fazla bilgi edinmek için [Microsoft Edge ınsider giriş sayfasını](https://www.microsoftedgeinsider.com) ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve kullanmaya başlamak için [Edge Insider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.

Microsoft Edge ınsider kanallarını HoloLens 2 ' ye yüklemek için kullanabileceğiniz birkaç yöntem vardır:

**Cihaza doğrudan yüklemek (Şu anda yalnızca yönetilmeyen cihazlar için kullanılabilir)**
  1. HoloLens 2 ' de [Edge ınsider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.
  1. yüklemek istediğiniz Edge ınsider kanalı için **HoloLens 2 için indir** düğmesini seçin.
  1. İndirilmiş. msix dosyasını Edge indirme kuyruğundan veya cihazınızın "Indirmeler" klasöründen (Dosya Gezgini 'ni kullanarak) başlatın.
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatılır.
  1. **Install** düğmesini seçin.
  1. başarılı bir yüklemeden sonra, Başlat menüsü **tüm uygulamalar** listesinde Microsoft Edge Beta, Dev veya canary ' ı ayrı bir giriş olarak bulacaksınız.

**Windows cihaz portalı ile bilgisayar aracılığıyla yükler (HoloLens 2 ' de [geliştirici modunun](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) etkinleştirilmesini gerektirir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.
  1. yüklemek istediğiniz Edge ınsider kanalının "Windows 10 için indir" düğmesinin yanındaki **açılan ok düğmesini** seçin.
  1. açılan menüden **HoloLens 2** ' yi seçin.
  1. . Msix dosyasını BILGISAYARıNıZıN "Indirmeler" klasörüne (veya kolayca bulabileceğinizi bir klasöre) kaydedin.
  1. HoloLens 2 ' ye indirilen. msix dosyasını yüklemek için bilgisayarınızda [Windows cihaz portalı](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 'nı kullanın.
  1. başarılı bir yüklemeden sonra, Başlat menüsü **tüm uygulamalar** listesinde Microsoft Edge Beta, Dev veya canary ' ı ayrı bir giriş olarak bulacaksınız.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni Microsoft Edge engellemek için WDAC kullanma

bt yöneticileri için, yeni Microsoft Edge uygulamasını engelleyecek bir [WDAC ilkesini](windows-defender-application-control-wdac.md) güncelleştirmek isteyen bt yöneticileri için, aşağıdaki ilkeyi ilkenize eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni Microsoft Edge için uç noktaları yönetme

Bazı ortamların, dikkate alınması açısından hesaba yönelik ağ kısıtlamaları olabilir. Yeni kenara sorunsuz bir deneyim sağlamak için lütfen [Bu Microsoft uç noktalarını etkinleştirin.](/deployedge/microsoft-edge-security-endpoints)

HoloLens için şu anda kullanılabilir [uç noktalar](hololens-offline.md)hakkında daha fazla bilgi edinin.

### <a name="install-web-apps"></a>Web uygulamalarını yükler
 > [!Note]
>[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)itibariyle, Office web uygulaması artık önceden yüklenmeyecektir.

yeni kenarı, Microsoft Store uygulamalarla birlikte web uygulamaları yüklemek için kullanabilirsiniz. örneğin, SharePoint veya OneDrive barındırılan dosyaları görüntülemek ve düzenlemek için Microsoft Office web uygulamasını yükleyebilirsiniz. Office web uygulamasını yüklemek için, https://www.office.com adres çubuğuna **uygulama kullanılabilir** veya **Office** düğmesini seçin. Onaylamak için **yüklemeyi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca, HoloLens 2 etkin bir internet bağlantısına sahip olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyicisi

yeni Microsoft Edge, derinlikli web deneyimleri (webvr 'yi değiştirme) oluşturmaya yönelik yeni standart olan webxr için destek içerir. birçok modern web deneyimi, VR ile birlikte tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler HoloLens 2 tarafından da desteklenir. WebXR standardı, fiziksel ortamınızı kullanan genişletilmiş ve karma gerçeklik derinlikli web deneyimlerini de sunar. geliştiriciler webxr ile daha fazla zaman harcadığında, yeni genişleticilerin ve karma gerçeklik derinlikli deneyimlerin HoloLens 2 müşteri tarafından denemeye ulaştığını öneririz!

360 görüntüleyici uzantısı, webxr üzerinde oluşturulmuştur ve HoloLens 2 ' deki yeni Microsoft Edge birlikte otomatik olarak yüklenir. Bu web uzantısı size 360 derecelik videolarda araçlarındaki yeniliklere dalabilirsiniz olanağı sağlar. YouTube, 360 videoların en büyük seçimini sunarak, buradan başlamanız önerilir.

#### <a name="how-to-use-webxr"></a>WebXR kullanma

1. WebXR desteğiyle bir Web sitesine gidin.
1. Web sitesindeki **VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel temsili Web sitesi başına değişebilir, ancak şuna benzer olabilir:

    ![VR düğmesi örneği girin](images/75px-enter-vr.png)

1. Belirli bir etki alanında bir WebXR deneyimini ilk kez başlatmaya çalıştığınızda, tarayıcı bir derinlikli görünüm girip **Izin ver**' i seçeceğiz.
1. deneyimi işlemek için [HoloLens 2 hareketlerini](hololens2-basic-usage.md#the-hand-tracking-frame) kullanın.
1. Deneyimde **Çıkış** düğmesi yoksa, giriş geri döndürmek için [Başlangıç hareketini](hololens2-basic-usage.md#start-gesture) kullanın.

**Önerilen WebXR örnekleri**
- 360 Görüntüleyici (sonraki bölüme bakın)
- [XR Dinoı](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 görüntüleyicisini kullanma

1. YouTube 'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde, karma gerçeklik kulaklık düğmesini seçin:

    ![360 görüntüleyicisini etkinleştirmek için düğme](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyici 'yi ilk kez başlattığınızda, tarayıcı bir tam ekran görünümü girmeye izin ister. **Izin ver**' i seçin.
1. Kayıttan yürütme denetimlerini görüntülemek için [AIR 'e dokunun](hololens2-basic-usage.md#select-using-air-tap) . [El ışınları ve AIR ' i dokunarak](hololens2-basic-usage.md#select-using-air-tap) Oynat/Duraklat, ileri/geri atla, açıklamalı alt yazıları aç/kapat veya deneyimi Durdur (tam ekran görünümünden çıkar). Kayıttan yürütme denetimleri birkaç saniyelik işlem yapılmadan sonra kaybolacaktır.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Popüler WebXR ve 360 Görüntüleyicisi bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak, kare hızı kesilebilir veya stutter.
- WebXR 'deki ifade eden her bir el ile yönelik destek, varsayılan olarak etkin değildir. Geliştiriciler, `edge://flags` "WebXR el girişi" ni etkinleştirerek aracılığıyla desteğini etkinleştirebilir.
- YouTube dışındaki Web sitelerinden 360 video, beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Viewer hakkında geri bildirim sağlama

Lütfen yeni Microsoft Edge **geri bildirim gönder** özelliği aracılığıyla ekibimize geri bildirim ve hata paylaşabilirsiniz.

### <a name="new-settings-app"></a>yeni Ayarlar uygulaması

bu sürümle birlikte Ayarlar uygulamasının yeni bir sürümünü sunuyoruz. yeni Ayarlar uygulaması aşağıdaki alanlarda HoloLens 2 için yeni özellikleri ve genişletilmiş ayarları içerir: ses, güç & sleep, ağ & ınternet, uygulamalar, hesaplar, erişim kolaylığı ve daha fazlası.

> [!NOTE]
> yeni Ayarlar uygulaması eski Ayarlar uygulamasından farklı olduğu için, daha önce ortamınıza yerleştirdiğiniz tüm Ayarlar pencereleri güncelleştirme sonrasında kaldırılır.

![yeni Ayarlar uygulama giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- arama Ayarlar: anahtar sözcükler veya ayarın adı kullanılarak Ayarlar giriş sayfasından ayarları arayın.
- Sistem > sesi:
  - giriş ve çıkış ses cihazları: bağımsız olarak giriş ve çıkış ses cihazlarınızı seçin (örneğin, Bluetooth kulaklık aracılığıyla ses dinleyin veya ses girişi için bir USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar HoloLens 2 tarafından desteklenmez.
  - Uygulama hacmi: her uygulamanın birimini bağımsız olarak ayarlayın. Bkz. [uygulama birimi denetimi başına](#per-app-volume-control).
- System > güç & uyku: bir süre işlem yapılmadan sonra cihazın uyku moduna geçmesi gerektiğini seçin.
- Sistem > pili: pil tasarrufu modunu el ile etkinleştirin veya nokta pil tasarrufu modunun otomatik olarak etkinleştirileceği bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık uçak modunu 2. HoloLens etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Daha önce Ayarlar pencereleri kaldırılacak (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden Ayarlar. IT yöneticileri, HoloLens 2 cihaz adı şablonu [için Windows Autopilot'ı](hololens2-autopilot.md) veya MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme bek gerekmmektedir).

#### <a name="display-color-calibration"></a>Renk ayarlamayı görüntüleme



Bu yeni ayarla, 2 ekran görüntüsü için alternatif bir renk HoloLens seçebilirsiniz. Bu, renklerin özellikle daha düşük ekran parlaklığı düzeylerinde daha doğru görünmesine yardımcı olabilir. Ekran rengi ayarı, sistem Ayarlar Sayfasındaki > bulunabilir.

> [!NOTE]
> Bu ayar görüntü üretici yazılımınıza yeni bir renk profili kaydedeci, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Görüntü rengi ayarlamayı kullanma

1. Ayarlar uygulamasını **başlatarak** **System > Birimi'ne gidin.**
1. Renk **ayarı görüntüle'nin** altında Renk **görüntüleme düzenini çalıştır düğmesini** seçin.
1. Ekran rengi ayarlama deneyimi başlatacak ve sizi, mengenenizin doğru konumda olduğundan emin olmak için teşvik eder.
1. Yönerge iletişim kutularına devam ettikten sonra, ekranınız otomatik olarak %30 parlaklığa soluk görüntülenir.
    > [!TIP]
    > Ortamınız soluk sahneyi görme konusunda sorun taşıyorsanız, cihazın sol tarafındaki parlaklığı düğmeleri kullanarak HoloLens 2'nin parlaklığını el ile ayarlayabilirsiniz.
1. Her renk profilini anında denemek için 1-6 düğmelerini seçin ve en iyi görüneni bulun (bu genellikle sahnenin en nötr görünmesine yardımcı olan profil anlamına gelir ve gri tonlama deseni ve ten rengi beklendiği gibi görünür.)

    ![Renk ayarı sahneyi görüntüleme](images/color-cal-ui.png)
    
1. Seçilen profilden memnun değilken Kaydet ve Çıkış **&** seçin
1. Değişiklik yapmamayı tercih ederseniz, İptal et **düğmesini & ve** değişiklikleriniz geri döndürülecek

> [!TIP]
> Burada, görüntü rengi ayarıyla ilgili bazı yararlı ipuçlarına göz ayın:
> - Ekran renk renklerini istediğiniz Ayarlar yeniden çalıştırarak
> - Cihaz üzerinde herhangi biri renk profillerini değiştirmek için daha önce bu ayarı kullandısa, en son değişikliğin tarih/saat ayarı Ayarlar yansıtılandır
> - Görüntü rengi ayarlamayı yeniden çalıştırarak daha önce kaydedilen renk profili vurgulanır ve Profil 0 görünmez (Profil 0, ekranın özgün renk profilini temsil ettiği için)
> - Ekranın özgün renk profiline geri dönmek için bu işlemi Ayarlar sayfasından (bkz. renk profilini [sıfırlama)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama 

HoloLens 2'nize kaydedilen özel renk profili sizi memnun HoloLens cihazın özgün renk profilini geri yükleyebilirsiniz:
1. Ayarlar uygulamasını **başlatarak** **System > Birimi'ne gidin.**
1. Renk **ayarı görüntüle altında** Varsayılan renk **profiline sıfırla düğmesini** seçin.
1. İletişim kutusu açıldığında, 2. **sunucuya** yeniden başlatmaya ve değişikliklerinizi HoloLens Yeniden Başlat'ı seçin.

#### <a name="top-display-color-calibration-known-issues"></a>Bilinen en çok görünen renk ayarı sorunları

- Bu Ayarlar, renk profilinin en son ne zaman değiştirdiğini size söyleyen durum dizesi, ilgili sayfayı yeniden yükleyene kadar güncel Ayarlar.
    - Geçici çözüm: Başka Ayarlar sayfası seçin ve Sonra Dalı sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirdiğinde veya birden fazla yüklü uygulamayla bir dosya türünü (destekleyen) açsanız, hangi yüklü uygulamanın dosya veya bağlantı türünü işlemesi gerektiğini seçmenizi istediğiniz yeni bir pencere açılır. Bu pencerede, seçilen uygulamanın dosyayı işlemesi veya "Bir kez" ya da "Her zaman" bağlantı türünü de seçmeyi seçebilirsiniz.

"Always" (Her Zaman) ifadesini seçerseniz ancak daha sonra hangi uygulamanın belirli bir dosyayı veya bağlantı türünü işleyeni değiştirmek istediğiniz varsa, Ayarlar > **Apps'te kaydedilmiş varsayılanlarınızı sıfırlayabilirsiniz.** Sayfanın en altına kaydırın ve  "Dosya türleri için varsayılan uygulamalar" ve/veya "Bağlantı türleri için varsayılan uygulamalar" altındaki Temizle düğmesini seçin. Masaüstü bilgisayarlardaki benzer ayarın aksine, tek tek dosya türü varsayılanlarını sıfırlayabilirsiniz.

#### <a name="per-app-volume-control"></a>Uygulama başına birim denetimi

Artık bu Windows kullanıcılar her uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duyan uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha iyi duymasını sağlar. Örneğin, başka bir uygulamada uzaktan yardım için başka bir kişiyi çağırırken bir uygulamanın hacmini kapatma ihtiyacı.

Tek bir uygulamanın hacmini ayarlamak için Ayarlar **Ses'e** gidin ve Gelişmiş ses seçenekleri altında Uygulama hacmi ve cihaz  ->    ->   **tercihleri'ne tıklayın.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe doğru çekme

Bazı müşteriler, kullanmakta olduğu sözcüğün şeklini değiştirerek sanal klavyelerde "yazma" özelliğini daha hızlı bulabilir ve holografik klavye için bu özelliğin önizlemesini sunuyoruz. Holografik klavyenin düzlemi üzerinden parmak ucunu atarak, sözcüğün şeklini çekerek ve sonra klavyenin düzlemi üzerinden parmakınızın ucunu çekerek tek tek kaydırabilirsiniz. Sözcüklerin arasındaki klavyeden parmaklarınızı kaldırarak boşluk çubuğuna basmanıza gerek kalmadan sözcükleri takip etmeye devam edin. Klavyede parmak hareketini takip eden bir çekme izi görüyorsanız özelliğin çalıştığını bilirsiniz.

Lütfen unutmayın; bu özelliğin kullanımı ve ana kaynak kullanımı, parmak izinize karşı direnç hissetmeyebilirsiniz (cep telefonu görüntüsü aksine) holografik klavyenin yapısı nedeniyle karmaşık olabilir. 

### <a name="power-menu-from-start"></a>Başlat'tan Güç menüsü

Kullanıcının oturum kapatmasını, kapatmasını ve cihazı yeniden başlatmasını sağlayan yeni bir menü. Sistem güncelleştirmesini HoloLens Başlangıç ekranı gösteren bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. Başlangıç HoloLens Başlangıç ekranı veya ["Başla"ya](hololens2-basic-usage.md#start-gesture) "Git" ifadesini kullanarak ilgili ifadeyi açın.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkat edilir:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Ellerinizi kullanarak kullanıcı profili resmini veya "Power" sesli komutunu seçin.

4. Cihazı kapatma, Yeniden Başlatma veya Kapatma seçeneklerinin yer alan bir menü görüntülenir:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Oturum kapatmak, yeniden başlatmak veya hizmetinizi kapatmak için menü seçeneklerini HoloLens. Cihaz tek bir Microsoft Hesabı [(MSA)](hololens-identity.md)veya yerel hesap için ayarlanmışsa, Oturum açma seçeneği kullanılamıyor olabilir.

6. Başka bir yere dokunarak veya Başlat hareketiyle Başlat menüsü menüyü kapatabilirsiniz.

#### <a name="update-indicator"></a>Göstergeyi güncelleştirme

Bir güncelleştirme kullanılabilir olduğunda, yeniden başlatmanın güncelleştirmeyi yükley hazır olduğunu belirtmek için üç nokta simgesi yanacak Menü seçenekleri güncelleştirmenin varlığını yansıtacak şekilde de değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında listelenen birden çok kullanıcı

Daha önce Oturum Açma ekranında yalnızca en son oturum açık olan kullanıcının yanı sıra 'Diğer kullanıcı' giriş noktası da gösteri. Cihazda birden çok kullanıcı oturum amışsa bunun yeterli olmadığını ifade etmek için müşteri geri bildirimi aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekmektedir.

Bu derlemede Windows, PIN giriş  alanı sağ tarafta bulunan Diğer kullanıcı'ya seçerek Oturum açma ekranında daha önce cihazda oturum açmamış birden çok kullanıcı görüntülenir. Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Cihaza hesap ekle düğmesi aracılığıyla bu Diğer kullanıcılar sayfasından da yeni bir **kullanıcı eklenebilir.**

Diğer kullanıcılar menüsünde, Diğer kullanıcılar düğmesi cihazda oturum açtıran son kullanıcı görüntülenir. Bu kullanıcının Oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C Dış Mikrofon Desteği

> [!IMPORTANT]
> BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.** Bir USB-C klavyesi kümesine takan kullanıcılar, mikrofonlu cihazın sesinin otomatik olarak mikrofonlara yönlendirilmesine neden olduğunu gözlemler ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazlarından yüksek önceliklendirmektedir. **USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**

Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz. USB-C mikrofonları arama, kayıt vb. için kullanılabilir.

Ayarlar'yi açın ve **Sistem Sesi'ne**   >  **seçin.**

![Ses Ayarlar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.
>
> Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.** **Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.
>
> İletişim **Varsayılanı'nın** seçerek dış mikrofon Remote Assist ve diğer iletişim uygulamaları için kullanılacak ancak HoloLens mikrofon dizisi diğer görevler için de kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlama](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mikrofon desteği Bluetooth ne olacak?

Ne Bluetooth mikrofonlar hala 2. HoloLens desteklenmiyor.

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

Ziyaretçi otomatik oturum açma, [özel OMA-URI](/mem/intune/configuration/custom-settings-windows-10) ilkesi aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon

| İlke  | Description   | Yapılandırmalar  |
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

Daha eski derlemelerde, bir cihazın bir bilgi noktası yapılandırması varsa ve bu, hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişimin bir birleşimi ise, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "[hiçbir şey gösterilmez](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)" menüsünü görür.

bu Windows sürümden itibaren, bilgi noktası deneyimi AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="new-settings-uris-for-page-settings-visibility"></a>sayfa Ayarlar görünürlüğü için yeni Ayarlar urı 'leri

[Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) ' de, Ayarlar uygulama içinde görülen sayfaları kısıtlamak için [Ayarlar/pagevisibilitylist ilkesini](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ekledik. pagevisibilitylist, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

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

Bu özellik, [bağlantı/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)aracılığıyla yönetilebilir.

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmelerine yönelik yeni Ayarlar uygulamasının eklenmesiyle birlikte yeni bir sorun giderici eklenmiştir. **Ayarlar**  ->  **güncelleştirme &amp; güvenliği**  >  **sorun giderme**  >  **Windows Update** gidin ve **başlat**' ı seçin. Bu, BT veya destek ile ilgili sorun giderme konusunda daha iyi yardımcı olması için işletim sistemi güncelleştirmeleriyle ilgili sorunları yeniden oluştururken izlemeleri toplamanıza olanak tanır.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

bu HoloLens güncelleştirme ile, Windows Holographic for Business birden çok HoloLens cihazdan indirilen bant genişliği tüketimini azaltmak için teslim iyileştirme ayarlarının kullanılmasına olanak sağlar. önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri için teslim iyileştirmesi](/windows/deployment/update/waas-delivery-optimization).

Aşağıdaki ayarlar yönetim yüzeyinin bir parçası olarak etkinleştirilir [ve Intune'dan yalıtabilirsiniz:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarı:

- HoloLens desteği bu önizlemede yalnızca işletim sistemi güncelleştirmeleri ile sınırlıdır.
- Windows Holographic for Business yalnızca bir Microsoft Bağlı Önbellek uç noktasına http indirme [modlarını ve indirmelerini destekler;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Eşler arası indirme modları ve grup atamaları şu anda HoloLens cihazlar için desteklenmiyor.
- HoloLens, Sunucu Güncelleştirme Hizmetleri uç noktaları için Windows veya teslim iyileştirmesini desteklemez.
- Sorun giderme işlemi, Bağlı Önbellek sunucusunda tanılama gerektirir veya HoloLens'da HoloLens'de Ayarlar   >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update .**

### <a name="it-admin---update-checklist"></a>IT Yöneticisi - Güncelleştirme Denetim Listesi

Bu denetim listesi, geçerli cihaz yönetimi yapılandırmalarınızı veya kullanmaya başlamak istediğiniz yeni özellikleri etkileyebilecek bu özellik güncelleştirmesinde eklenen yeni öğeleri size yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi Noktası modundaki güncelleştirmeler

✔️ Bilgi [**Noktası modunda yeni uygulamalar için Yeni AUMID'ler oluşturun:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Daha önce Ayarlar uygulamasını veya Microsoft Edge Bilgi Noktası'Microsoft Edge kullanıyorsanız, bu uygulamaları farklı bir Uygulama Kimliği kullanan yeni uygulamalarla değiştiririz. Aşağıdaki Bilgi Noktası modundaki [yeni uygulamalar için Yeni AUMID'leri okumanız önemle](#use-the-new-settings-and-edge-apps-in-kiosk-modes) tavsiye edilecektir. Bu, bilgi noktası uygulamanıza sahip olmaya devam Ayarlar veya yeni uygulama uygulamanıza Microsoft Edge sağlar. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirmede daha sorunsuz bir geçişe olanak tanır.

✔️ Bilgi [**Noktası için Ziyaretçi Otomatik Oturum Açma:**](#visitor-auto-logon-for-kiosks) 

Ziyaretçiler artık bir Bilgi Noktası'nde otomatik olarak oturum açabilirsiniz. Bu davranış varsayılan olarak açıktır, ancak yönetilebilir ve devre dışı bırakılabilir.

✔️ [**Bilgi Noktası modu hatası teslimi:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Oturum açmış AAD kullanıcılarının AAD grup üyeliği başarıyla belirlenene kadar, başlat menüsü (varsa) için genel bilgi noktası yapılandırması kullanılır, aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınızı bilgilendiren bir işlem olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ve Görünürlük Ayarlar Güncelleştirmeleri

✔️ [**Görünürlüğü Ayarlar Için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarlar [Görünürlüğü](settings-uri-list.md) kullanıyorsanız, izin verilen veya engellenen mevcut URI'ler üzerinde ayarlamalar yapmak iyi olabilir.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler
✔️ WDAC aracılığıyla Microsoft Edge önceden engelliyorsanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme
✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, yeni uygulama için bu yeni uç noktaları Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere toplayıp toymayy ve kimlerin toplay olduğunu yapılandırmış oluruz.

✔️ Cihazları[yakın cihazlarla paylaşma:](#share-things-with-nearby-devices)Yakındaki yeni paylaşım özelliğini devre dışı abilirsiniz.

✔️ için [ilke ayarlarını yapılandırma: Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)için kullanılabilir olan yeni yapılandırmaları Microsoft Edge.

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
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, sürüm 1903 - Mayıs 2021 Güncelleştirmesi
- Derleme 18362.1110

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. **Bu derleme artık aylık hizmet güncelleştirmelerini almayacak.** Holographic sürüm 21H1'Windows en son derlememizi denemeyi teşvik ederiz.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, sürüm 20H2 - Nisan 2021 Güncelleştirmesi
- Derleme 19041.1144

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İş hattı uygulaması yükleme durumu raporlaması ile ilgili bir sorunu düzeltir.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, sürüm 1903 - Nisan 2021 Güncelleştirmesi
- Derleme 18362.1108

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Yerel bir hesap Ayarlar parola değiştirmeye çalışırken uygulamanın kilitlenmesi sorununa yol açıyor.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, sürüm 20H2 - Mart 2021 Güncelleştirmesi
- Derleme 19041.1140

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 ile fotoğraf yakalamak için AdvancedPhotoCapture veya LowLagPhotoCapture kullanan müşteriler artık fotoğraf kaydedildikten 3 saniye sonra kamera pozunu alabilir.
- Cihaz Portalı Service'te bellek sızıntısına neden olan sorun, hizmet tarafından belleklerin daha fazla bellek kullanımına neden olması ve diğer uygulamaların bellekte yer alamalarına neden olmasıyla ilgili düzeltme.
- Aşamalı Rollout'a kaydolan kullanıcıların cihazda oturum alamama sorunu düzeltildi.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, sürüm 1903 - Mart 2021 Güncelleştirmesi
- Derleme 18362.1102

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı Service'te bellek sızıntısına neden olan sorun, hizmet tarafından belleklerin daha fazla bellek kullanımına neden olması ve diğer uygulamaların bellekte yer alamalarına neden olmasıyla ilgili düzeltme.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, sürüm 20H2 - Şubat 2021 Güncelleştirmesi
- Derleme 19041.1136

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İlk cihaz kurulumu ve mağaza uygulama güncelleştirmeleri ile ilgili bir sorunu düzeltir.
- Sonraki sürümler için yükseltme ve uçuş ile ilgili HoloLens gidermek.
- eSIM kök depolamadan kullanılmayan önceden yüklenmiş sertifikalar, HoloLens kaldırıldı.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, sürüm 1903 - Şubat 2021 Güncelleştirmesi
- Derleme 18362.1098

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, sürüm 20H2 - Ocak 2021 Güncelleştirmesi
- Derleme 19041.1134

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihazda çok sayıda kullanıcı olduğunda başlatma, sürdürme ve kullanıcı değiştirme sırasında performans geliştirildi.
- Araştırma Modu için arm32 [desteği eklendi.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, sürüm 1903 - Ocak 2021 Güncelleştirmesi
- Derleme 18362.1091

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesi
- Derleme 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama Yükleyicisi aracılığıyla HoloLens 2'ye Uygulama Yükleyicisi

Uygulamaları 2 **cihaza daha sorunsuz Uygulama Yükleyicisi için** yeni bir özellik (HoloLens) ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazlar için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:
- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin (USB üzerinden veya Edge üzerinden) cihazınıza indirerek Dosya Gezgini Appx Paketi'ne gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğu gibi, uygulamaların [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) da İmza [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce imzalamak için kullanılan sertifikanın HoloLens cihazı tarafından güvenilir olması gerekir.

**Uygulama yükleme yönergeleri.**

1.  Cihazınızın yönetilen olarak kabul edilen bir şey olduğundan emin olun
1.  HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1.  HoloLens 2 cihazında oturum HoloLens olun
1.  Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads dizinine kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1.  2 HoloLens Başlat Menüsünü açın, Başlat'ı Tüm uygulamalar seçin ve Dosya Gezgini açın.
1.  İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1.  yourapp.appxbundle dosyasını seçin.
1.  Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Örnekleri GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamaları bulabilirsiniz.

HoloLens [2'de uygulama yükleme](app-deploy-app-installer.md)işleminin Uygulama Yükleyicisi.  

![UYGULAMA YÜKLEYICISI aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek el ile yalnızca konum güncelleştirilirken diğer ortaklar önceki bir poza göre ertelenmektedir.  Bu değişiklik; tırslama, atma, kırpma ve kırpma gibi hareketlerde izleme tutarlılığının iyileştirilmesine yardımcı olur.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El joint'ler inferred olduğunda, her [bir ortak](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi
- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesini ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz teşvik ederiz.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2
- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve 2 kullanıcı ve BT HoloLens yeni özellikler sunar. Otomatik Göz Konumlandırmadan Sertifika Yöneticisi'ne Ayarlar Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine. Bu yeni güncelleştirme, IT ekiplerinin cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip HoloLens ve kullanıcılara daha sorunsuz holografik deneyimler sunar. 

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler ekllmektedir. Ana derleme numarası aynı kalır ve Windows Güncelleştirmesi 2004 (derleme 19041) sürümünün aylık sürümünü belirtecek. En son 19041.1128+ derlemesinde olduğunu onaylamak için Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. Güncelleştirmeleri yönetme hakkında daha fazla bilgi için HoloLens güncelleştirmelerini [yönetme HoloLens ziyaret edin.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic sürüm 20H2'daki yeniler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik Göz Konumu Desteği](hololens-release-notes.md#auto-eye-position-support) | Kullanıcıların Göz İzleme ayarına girmeden göz konumlarını etkin bir şekilde hesaplama.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Yeni basit yöntemlerin sertifika yükleme ve kaldırma yöntemlerinin Ayarlar sağlar.     |
| [USB'den sağlamayı otomatik başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerinde paketlerin sağlanması, otomatik olarak OOBE'de sağlama sayfasına sorılır.                                                         |
| [OOBE'de sağlama paketlerini otomatik olarak onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve otomatik onaylamayı birlikte birleştirme. |
| [Autopilot'ı Wi-Fi kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısına gerek kalmadan Wi-Fi otomatik pilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlanır veya yeniden yanıp söner. |
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli olacak şekilde çoklu uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens Koşullarıdır](hololens-release-notes.md#hololens-policies)                                    | Yeni ilkeler HoloLens.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların kaç gün boyunca çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz HoloLens ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Uygulamanın içinde hangi sayfaların görül Ayarlar.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2'de Araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikayı geçmeyecek. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

2 HoloLens de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve geliştirilmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcı cihazı bağlı olduğu andan itibaren otomatik olarak arka planda çalışmaya başlar. Kullanıcının daha önce göz izleme ayarı yoksa Otomatik Göz Konumu, işlem süresi 20 -30 saniyenin ardından kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve bu nedenle kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, kalibre edilmemiş bir Kullanıcı, cihazda daha önce gelen göz izleme ayarlama işleminden geçmiş bir kişiye başvurur.

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

[Tenantlockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. tenantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer yeniden yanıp sönse, işletim sistemi güncelleştirmeleri, vb. için cihazda kalır. 

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

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır? 
1. Yukarıda HoloLens 2 olan cihaz 2'nin daha önce atanmış olduğu cihaz yapılandırmasını kaldırın. 

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin. OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Autopilot profili bir HoloLens OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilebini süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir. 

![Cihazda ilkenin ne zaman zorlanan cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık [Tenantlockdown CSP](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)ve Autopilot altında Autopilot'ın geri kalanıyla birlikte bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel Atanan Erişim – Bilgi Noktası Modu
- Bilgi noktası modunu sistem düzeyinde geçerli olan yeni Bilgi Noktası yöntemi etkinleştirerek Bilgi Noktası için Azaltılmış Kimlik Yönetimi.

Bu yeni özellik, BIR IT Yöneticisinin sistem düzeyinde geçerli olan, sistem üzerinde herhangi bir kimliğe benzeşimleri olan ve cihazda oturum açabilen herkes için geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırmasını sağlar. Bu yeni özellik hakkında daha fazla bilgi için genel [HoloLens bilgi noktası üzerinden bilgi alın.](hololens-global-assigned-access-kiosk.md)

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
| MixedReality\BrightnessButtonDisabled              | Parlaklığa sahip düğmelerin devre dışı bırakılarak parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı bırakılarak birimi değiştirmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\MicrophoneDisabled                    | 2.0'da ses kaydı mümkün HoloLens devre dışıdır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin ne zaman toplanabilir davranışını kontrol eder.                               | 0 Devre Dışı, 1 Cihaz Sahipleri için Etkin, 2 Herkes için Etkin (Varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD gruplarını hedef alan Bilgi Noktası için Azure AD grup üyeliği önbelleğinin kaç gün süreyle kullanıl olduğunu kontrol eder. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın
- 60 gün boyunca AAD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılacazın. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi halde kullanılmaz.  

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
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni kod Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> [RemoteLock ile ilgili olarak,](/windows/client-management/mdm/remotelock-csp)HoloLens yalnızca ./Vendor/MSFT/RemoteLock/Lock yapılandırmasını destekler. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırmalar desteklenmiyor.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri
- Güç ilkeleri aracılığıyla HoloLens veya kilitlenirken daha fazla seçenek. 

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumları denetlemesine olanak sağlar. Her ilke hakkında daha fazla bilgi için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery ve DisplayOffTimeoutPluggedIn için bu iki yeni ilk, Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> HoloLens 2 ' de tutarlı deneyim için, lütfen hem displayofftimeoutonpili hem de standbytimeoutonpili değerlerinin aynı değer olarak ayarlandığından emin olun. Aynı, Displayofftimeoutpluggedın ve Standbytimeoutpluggedın için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için [bkz. ekran, uyku ve hazırda bekleme boşta zamanlayıcılar](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens için yeni etkinleştirilmiş güncelleştirme ilkeleri
- Güncelleştirmelerin yüklenmesi için daha fazla seçenek veya güncelleştirme için güncelleştirmeleri Duraklat düğmesini devre dışı bırakma.

bu güncelleştirme ilkeleri artık HoloLens 2 cihazlarda etkinleştirilmiştir:
-   [Güncelleştirme/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Güncelleştirme/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Güncelleştirme/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Güncelleştirme/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

bu güncelleştirme ilkelerine ilişkin tüm ayrıntılar ve bunların HoloLens cihazları için nasıl kullanılacağı, [HoloLens güncelleştirmelerini yönetme](hololens-updates.md)bölümünde buradan okunabilir.

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 için Ayarlar sayfa görünürlüğü etkinleştirildi
- Ayarlar uygulamasındaki artan uı denetimi, sınırlı sayıda sayfa seçimini göstermek için karışacaktır.

artık, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkeyi etkinleştirdik. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 ' de özelleştirebileceğiniz sayfa ayarlarını öğrenmek için lütfen [Ayarlar urı](settings-uri-list.md)'larımızı ziyaret edin. 
 
![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu
araştırma modundayken, HoloLens 2, bilgisayar vision Research için bir pokatlanmış araç haline gelir. önceki sürümlere kıyasla, HoloLens 2 için araştırma modu aşağıdaki avantajları içerir:
-   HoloLens (1. gen) araştırma modunda sunulan sensörlerden ek olarak, artık bir ivme ölçer, jroscope ve manyetik tometre dahil olmak üzere imu algılayıcı erişimi sağlıyoruz.
-   HoloLens 2, araştırma moduyla birlikte kullanılabilecek yeni yetenekler sağlar. Özellikle, daha zengin bir denemeleri kümesini sunabilme ve göz önünde bulundurun.

araştırmacılar artık, bu dış kullanıma açık ham görüntü algılayıcı akışlarına erişmek için HoloLens cihazlarında araştırma modunu etkinleştirme seçeneğine sahiptir. HoloLens 2 için araştırma modu, ivometer, jroscope ve manyetik tometer okumaları için de erişim sağlar. Kullanıcıların gizliliğini korumak için, ham göz izleme kamera görüntüleri araştırma modu aracılığıyla kullanılamaz, ancak var olan API 'Ler aracılığıyla göz korunun yönü mevcuttur.

Daha fazla teknik ayrıntı için [araştırma modu belgelerine](/windows/mixed-reality/research-mode) göz atın.

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
- cihaz [tek uygulama bilgi noktası](hololens-kiosk.md)olarak ayarlandığında, bir HoloLens cihazının medya aktarım protokolü (MTP) üzerinden dosya gezgini 'nde gösterilmesini önleyen bir sorun ele alınmalıdır. MTP (genel olarak USB bağlantısının), [Allowusbconnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ilkesi kullanılarak hala devre dışı bırakılabileceğini unutmayın.
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
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses **hatalarını** ortadan kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, bir web tarayıcısı geçersiz sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı bu durumla devam etmek mümkün değildir. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş girişlerinden tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- Piksel biçimlerini, HoloLens işleyicisinde siyah olarak işilecek şekilde değiştiren uygulamaların HoloLens düzeltildi.
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
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
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
|       El izleme geliştirmeleri                 |          El izleme geliştirmeleri düğmeleri ve 2D sayfalı etkileşimleri daha doğru hale ediyor                        |
|       Kalite geliştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik geliştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot desteği

Windows HoloLens 2 için Autopilot, cihaz satış kanalının Intune kiracınıza HoloLens önceden kaydolmasına olanak sağlar. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazır olur. Kendi kendine dağıtımdan yararlanmak için cihazın kurulumun ilk ekranı sırasında USB-C-Ethernet kullanarak bir ağa bağlanması gerekir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başladıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme.
1. Cihazı Microsoft Intune (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.
1. Cihaz hedefli ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlama.
1. Oturum açma ekranı kullanıcıya gösterilir.

[HoloLens 2 değerlendirme Windows Autopilot'ta daha fazla bilgi edinin.](hololens2-autopilot.md)

*Şimdi AutoPilot önizlemeye katılmak için Hesap Yöneticinize ulaşın. Autopilot'a hazır cihazlar yakında gönderime başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar, HoloLens veya okul ortamındaki diğer kullanıcılarla bir cihaz paylaşır. Bu nedenle, kullanıcıların uzun kullanıcı adları ve parolalar yazmadan kolayca ulaşabiliyorları önemlidir. Fast Identity Online (FIDO), bir kullanıcı adı veya parola girmeden, kuruluşta (Azure AD kiracısı) HoloLens oturum açmasına olanak sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktöründe getirilebilir, standartlara dayalı bir parolasız kimlik doğrulama yöntemidir. FIDO, parolasız kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kaynaklarında kullanıcı adı veya parola olmadan oturum açmalarına olanak sağlar. Bunun yerine bir dış güvenlik anahtarı veya cihazda yerleşik olarak yer alan bir platform anahtarı kullanırlar.

Çalışmaya başlama için [bkz. Parolasız güvenlik anahtarı oturum açmasını etkinleştirme.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Paketleri sağlama, HoloLens deneyimi yerine yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamayı sağlar. Daha önce, sağlama paketlerinin şirket içi belleğe HoloLens vardı. Artık bir USB sürücüde olabilir, böylece birden çok cihaz üzerinde daha kolay HoloLens cihazları paralel olarak silebilirsiniz. Paket sağlama artık cihaz yönetimine kaydolmak için bir alanı da desteklemektedir, bu nedenle sağlama sonrasında el ile kurulum yoktur.

Denemek için:

1. Windows Windows Configuration Designer'ın en son sürümünü Windows bilgisayarınıza indirin.
1. 2 **HoloLens Cihazları Sağlama**  >  **HoloLens'yi seçin.**
2. Yapılandırma profilinizi oluşturun. Ardından, oluşturulan tüm dosyaları bir USB-C depolama cihazına kopyalayın.
3. USB-C cihazını herhangi bir yeniden flaşla HoloLens bağlayın. Ardından,   +  sağlama paketinizi uygulamak için ses **tasarrufu** düğmelerine basın.

### <a name="line-of-business-application-install-status"></a>İş kolu uygulaması yüklemesi durumu

İş kolu uygulamaları için MDM uygulama dağıtımı ve yönetimi HoloLens açısından önemlidir. Yöneticiler ve kullanıcıların, denetim ve Tanılama için uygulama yüklemesi durumunu görüntülemesi gerekir. bu sürümde, **Ayarlar**  >  **hesaplarına**  >  **erişim iş veya okul**  >  **hesabına hesap**  >  **bilgilerinize** tıkladığımızda daha fazla ayrıntı ekledik.

### <a name="additional-csps-and-policies"></a>Ek CSP 'Ler ve ilkeler

Bir [yapılandırma hizmeti sağlayıcısı (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) bir cihazdaki yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. bu sürümde, denetim yöneticilerinin dağıtılan HoloLens cihazlara sahip olmasını sağlamak için daha fazla ilke desteği ekleyeceğiz. HoloLens tarafından desteklenen csp 'ler listesi için bkz. [networkqospolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Bu sürümdeki yenilikler:

**İlke CSP 'si** 

ilke yapılandırma hizmeti sağlayıcısı, kuruluşun Windows cihazlarda ilkeleri yapılandırmasına olanak sağlar. bu sürümde, burada listelenen HoloLens için yeni ilkeler ekledik. daha fazla bilgi için bkz. [HoloLens 2 tarafından desteklenen ilke csp 'leri](/windows/client-management/mdm/policies-supported-by-hololens2).  

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

NetworkQoSPolicy yapılandırma hizmeti sağlayıcısı, ağ hizmet kalitesi (QoS) ilkeleri oluşturur. QoS ilkesi, bir dizi eşleşen koşulu temel alarak ağ trafiği üzerinde bir dizi eylem gerçekleştirir. Daha fazla bilgi için bkz. [Networkqospolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE tethered cihazları için genişletilmiş USB Ethernet desteği

5 g/LTE telefonlar ve Wi-Fi etkin noktalar gibi belirli mobil geniş bant cihazlarının USB üzerinden HoloLens 2 ' ye tethered oldukları durumlarda etkinleştirilmesi için destek eklenmiştir. Bu cihazlar artık farklı bir Ethernet bağlantısı olarak **ağ ayarlarında** görüntülenmektedir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmez.) Bu işlevsellik Wi-Fi kullanılabilir olmadığında yüksek bant genişliğine sahip bağlantılara izin verebilir ve Wi-Fi internet paylaşımı yeterince iyi değildir. desteklenen USB cihazları hakkında daha fazla bilgi edinmek için bkz. [Bağlan Bluetooth ve USB-C cihazları](hololens-connect-devices.md).  

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

Artık, cihazdaki herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için bkz. [HoloLens çalıştırmak için sesinizi kullanma](hololens-cortana.md). ayrıca [HoloLens 2 için desteklenen diller](hololens2-language-support.md)bölümüne bakın.  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

güncelleştirilmiş uygulama, cihazlarınız arasında daha fazla işlem yapmanıza yardımcı olmak için Microsoft 365 ile tümleşir (şu anda yalnızca US-English). HoloLens 2 ' de, Cortana birimi ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklememektedir. Bu seçenekler artık yeni sistem ses komutları tarafından desteklenmektedir. [blogumuza](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)yeni Cortana uygulaması hakkında daha fazla bilgi edinin.

### <a name="quality-improvements-and-fixes"></a>Kalite iyileştirmeleri ve düzeltmeleri

Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:  
- Etkin bir görüntüleme ayarlama sistemi sunuldu. Bu özellik hologragram kararlılığını ve hizalamasını geliştirir. Başlarınızı yan yana hareket ettirmek için artık yerinde kalabilirler.
- Wi-Fi akışının HoloLens düzenli aralıklarla kesintiye uğradığından hata düzeltildi. Bir uygulama düşük gecikmeli akış için ihtiyacı olduğunu gösteriyorsa, [Setsocketmediastreamingmode işlevini](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)çağırarak bu çözümü uygulayın.
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
- Bir derinlik MF örneğine eklenen koordinat sisteminin ortak belgelerle tutarlı olmasını sağlar.
- Müşterilerin cihaz portalı üzerinden büyük miktarlarda metin yapıştırmasını sağlayarak geliştirilmiş geliştirici verimliliği.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, sürüm 1903-Şubat 2020 güncelleştirme 
- Derleme 18362,1053

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamaları için HolographicSpace. Uservarlığına yönelik API geçici olarak devre dışı bırakıldı. Bu değişiklik, "arka planda çalıştır" ayarı etkinleştirilmiş olsa bile, bazı uygulamaların, vizörü çevrildikten sonra duraklamasını engelleyen bir sorunu önler.
- Kullanıcının bir kullanıcı arabirimi dontığı ve birkaç saniye sonra kabuğa geri dönmesi fark eden, izlenen bir rastgele kilitlenme çökme düzeltildi.
- Gelişmiş izleme, Dizin parmağınızla yer ayırdığınızda, o parmağınızla büyük bir kısmı beklenmedik şekilde eğilerek daha az olabilir.
- Baş izlemenin, uzamsal eşlemenin ve diğer çalışma zamanlarının güvenilirliği geliştirildi.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, sürüm 1903-Ocak 2020 güncelleştirme 
- Derleme 18362,1043
 
Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 öykünücüsü ile çalışırken özel uygulamalar için iyileştirilmiş kararlılık.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, sürüm 1903-Aralık 2019 güncelleştirme 
- Derleme 18362,1042

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Son aşama üretilmesi (LSR) düzeltmeleri tanıtılmıştır. Daha kararlı ve daha doğru bir şekilde hesaba göre daha kararlı ve net bir şekilde görüntülenmesi için hologragram geliştirilmiş görsel işleme. Bu belirti, uygulamalar hologragram derinliğini doğru şekilde ayarlamazsanız bu güncelleştirmeden sonra daha belirgin olacaktır.
- Özel uygulamaların ve özel uygulamalar arasında gezinmesinin sabit kararlılığı.
- Karma Gerçeklik yakalamanın birkaç gün boyunca bekleme durumunda olduktan sonra video kaydedemediği bir sorun çözüldü.
- İyileştirilmiş hologram kararlılığı.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, sürüm 1903-Kasım 2019 güncelleştirme 
- Derleme 18362,1039

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- En-CA ve en-AU için ilk kurulum sırasında sesli komut **seçme** işlevlerinin sabit işlevselliği.
- En son Unity ve karma gerçeklik araç seti (MRTK) sürümlerine daha fazla yerleştirilmiş olan nesnelerin geliştirilmiş görsel kalitesi.
- Başlat menüsü açılıp kapanana kadar başlangıçta durdurulmuş bir durumda takılarak holographic uygulamalarla ilgili sorunlar düzeltildi.
- HoloLens 2 ve öykünücü için openxr çalışma zamanı uyumluluk düzeltmeleri ve geliştirmeleri.
