---
title: HoloLens 2 sürüm notları
description: Her yeni sürüm ve 2 yayında yapılan tüm HoloLens güncel kalın.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/8/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f27a469e76df1ccf29a2823b48f3640bdf414050
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033840"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

Yeni cihazlarınızı kullanarak üretken bir deneyim HoloLens için özellik, hata ve güvenlik güncelleştirmelerini yayınlaya devam edeceğiz. Bu sayfada, her ay yeni HoloLens görebilirsiniz. En son HoloLens 2 güncelleştirmesini almak için [](hololens-update-hololens.md#check-for-updates-and-manually-update) güncelleştirmeleri kontrol edebilirsiniz ve el ile güncelleştirebilir veya Tam Flash Güncelleştirme'yi (FFU) Gelişmiş Kurtarma Yardımcı'sı aracılığıyla cihazınızı flash olarak [gönderebilirsiniz.](hololens-recovery.md#clean-reflash-the-device) İndirme [güncel](https://aka.ms/hololens2download) tutulur ve genel kullanıma açık en son derlemeyi sağlar.

> [!NOTE]
> Son 11 Windows duyurusu, 11'in pc sürümüne Windows. Kısa süre [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) önce Mayıs 2021'de HoloLens 2 için önemli bir işletim sistemi güncelleştirmesi başlattık ve bu düşüş için müşteri geri bildirimlerine dayanarak gelecek bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)derlememizde Remote Assist kullanıcılarını etkileyen bilinen bir sorun nedeniyle, Windows Holographic sürüm 21H1 güncelleştirmelerinin tekliflerini geçici olarak duraklatıldık. Ayrıca varsayılan Gelişmiş Kurtarma Yardımcı (ARC) derlemesini [Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi olarak değiştirdik.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) ARC derlemesi artık 21H1 derlemeyi hedeflemeye devam edecek.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, sürüm 21H1 - Ağustos 2021 Güncelleştirmesi

- Derleme 20348.1014

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Xbox denetleyicilerinin denetleyici desteğine sahip çevreleyici uygulamalarda çalışmasını engelleyen bir sorun düzeltildi.
- Cihaz güncelleştirme hataları için geliştirilmiş tanılama.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, sürüm 20H2 - Ağustos 2021 Güncelleştirmesi

- Derleme 19041.1161

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1 - Temmuz 2021 Güncelleştirmesi

- Derleme 20348.1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi Ayarlar -Wi-Fi > **Ağ & İnternet -> Durumu ->** Özellikler'den başlatılamadığına ilişkin bir sorun düzeltildi.
- ESIM sertifikalarının işletim sistemi güncelleştirmeleri arasında kaldırılmasıyla ilgili bir sorun giderildi. Bu düzeltme, 21H1 sürümüne güncelleştirmeden önce eSIM sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- Önceden yüklenmiş uygulamaları işletim sistemi sıfırlamaları arasında etkileyen bir sorun düzeltildi.
- Artan CPU yüklemesi ile ücretlendirme sırasında çalışma zamanını artırmak için pil ücretlendirme performansı ayarlanmıştır. 2 HoloLens cihazı ücretlendirme sırasında, cihazın sıcak olarak çalıştırlı olduğu algılanırsa iç pil daha yavaş ücretlendirmek için ısıyı azaltır. Olumlu bir takas, bir cihazın termal sorun nedeniyle kapanma ihtimalinin düşük olması ve bunun etkisi cihazın daha uzun süre çalışma olasılığıdır. Cihaz cool çalışıyorsa, ücret oranı etkilenmez.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – Temmuz 2021 Güncelleştirmesi

- Derleme 19041.1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1 - Haziran 2021 Güncelleştirmesi

- Derleme 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive veya okul kameralarını karşıya yükleme

HoloLens 2 Ayarlar uygulamasına, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın Pictures > Camera Roll klasöründen iş veya okul için ilgili OneDrive klasörüne otomatik olarak yüklemelerini sağlayan yeni bir özellik ekledik. Bu özellik, [](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) OneDrive HoloLens 2'de OneDrive uygulamasındaki bir özellik açığına yöneliktir. Bu, yalnızca müşterinin kişisel hesabına (iş veya okul hesabı değil) otomatik Kamera Microsoft hesabı yüklemesini destekler.

**Nasıl çalışır?**

- "Kamera **Ayarlar >"> etkinleştirmek için System > Mixed Reality Camera'ı** ziyaret edin.
- Bu özellik Açık  konuma ayarlanır ve cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları otomatik olarak iş veya okul hesabı için > fotoğraf makinenizin Pictures > Camera Roll klasörüne OneDrive kuyruğa eklenir.
    >[!NOTE]
    >Bu özellik etkinleştirilmeden önce yakalanan fotoğraflar ve videolar *karşıya* yükleme için kuyruğa yüklenmez ve yine de el ile karşıya yüklenmeleri gerekir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yüklenmeyi bekleyen dosyaların sayısını görüntüler (veya bekleyen tüm dosyalar karşıya OneDrive "güncel" olarak görünür).
- Bant genişliği konusunda endişe ediyorsanız veya herhangi bir nedenle karşıya yüklemeyi "duraklatmak" için özelliği Kapalı konuma **geçebilirsiniz.** Özelliği geçici olarak devre dışı bırakmak, Kamera Roll klasörüne yeni dosya ekleyinceye kadar karşıya yükleme kuyruğunda artış devam eder, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmez.
- En yeni dosyalar ilk olarak karşıya yüklensin (son, ilk çıkar).
- Hesap OneDrive sorunları varsa (örneğin, parolanız değiştikten sonra) Yeni bir düzeltme düğmesi Ayarlar görüntülenir. 
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklemesi daha uzun sürer (özellikle karşıya yükleme bant genişliğiniz kısıtlanmışsa). Büyük bir dosya karşıya yükleme sırasında karşıya yüklemeyi "duraklatır" veya kapatırsanız, kısmi karşıya yükleme korunur. Karşıya yükleme "duraklatıldı" veya devre dışı bırakıldı. Birkaç saat içinde yeniden etkinleştirilirse, karşıya yükleme, bıraktığı yerden devam eder. Ancak, karşıya yükleme birkaç saat sonra yeniden etkinleştirilirse, büyük dosyanın karşıya yüklemesi en baştan yeniden başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayar, geçerli bant genişliği kullanımına göre yerleşik azaltmaya sahip değil. Başka bir senaryo için bant genişliğini en üst düzeye çıkarmanız gerekirse, ayarı el ile kapatın. Upload duraklatılır, ancak özellik Yeni eklenen dosyaları Kamera Roll'e izlemeye devam eder. Devam etmek için hazır olduğunda karşıya yüklemeyi yeniden etkinleştirin.
- Bu özellik cihaza her kullanıcı hesabı için etkinleştirilmelidir ve yalnızca o anda cihazda oturum açık olan kullanıcının dosyalarını etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasındaki karşıya yükleme sayısını izlerken fotoğraf veya video sürüyorsanız, geçerli dosya karşıya yükleme tamamlanana kadar bekleyen dosya sayısı değişmeyebilirsiniz.
- Upload uykuda düşerse veya kapalı olursa bu süre duraklatılır. Bekleyen karşıya yüklemelerin tamamlandığından emin olmak için, Ayarlar sayfası "OneDrive güncel" olana kadar cihazı etkin bir şekilde kullanın veya **Power & ayarlarını** yapın.

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri artık 2. HoloLens desteklemektedir:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx, uygulamanın Telemetri ve davranış üzerinde tam denetime sahip Ayarlar kullanılmalıdır.

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Renk ayarlama ile videonun önemli bozulmalarını düzeltir.
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
> Bu derlemeye artık hizmet ve olmayacaktır.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, sürüm 21H1
- Derleme 20346.1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihaz üzerinde herkes tarafından kullanılan özellikler ve IT Yöneticileri tarafından yapılandırılan yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda her hedef kitleyle ilgili özellikler gösterilmiştir. BIR IT Yöneticisiyseniz lütfen IT Yöneticisi - Güncelleştirme Denetim [Listesi'ne göz atın.](#it-admin---update-checklist)
>[!IMPORTANT]
>Bu derlemeye güncelleştirmek için HoloLens 2 cihazın Şubat 2021 güncelleştirmesini (derleme 19041.1136) veya daha yenisini çalıştıracak olması gerekir. Bu özellik güncelleştirmesini görmüyorsanız lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>Bugün Microsoft HoloLens 2, aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmeleri) destekler:
>- Windows Holographic, sürüm 20H2 (Derleme 19041.1128+)
>- Windows Holographic, sürüm 2004 (Derleme 19041.1103+)
>- Windows Holographic, sürüm 1903 (Derleme 18362+)
>
> Windows Holographic sürüm 21H1'in tanıtımıyla, Windows Holographic sürüm 1903 için aylık bakım **güncelleştirmelerini sonlandırıyoruz.** Bu sayede daha yeni sürümlere odaklanarak değerli geliştirmeler yapmaya devam edeceğiz.


| Özellik Adı                                              | Kısa açıklama                                                                      | Hedef Hedef Kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | Yeni, Chromium tabanlı Microsoft Edge artık 2. HoloLens kullanılabilir. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyici](#webxr-and-360-viewer) | Tam ekran web deneyimlerini ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
[Yeni Ayarlar uygulaması](#new-settings-app) | Eski Ayarlar, güncelleştirilmiş bir sürümle yeni özellikler ve ayarlarla değiştir ediliyor. | Son Kullanıcı |
[Renk ayarlamayı görüntüleme](#display-color-calibration) | HoloLens 2 ekranınız için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama başına birim denetimi](#per-app-volume-control) | Uygulama düzeyindeki birimi sistem biriminden bağımsız olarak denetleme. | Son Kullanıcı |
[Web uygulamalarını yükleme](#install-web-apps) | Yeni Microsoft Office tarayıcısıyla HoloLens 2.Microsoft Office web Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekin](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde cihazı yeniden başlatın ve HoloLens kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve /veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında bilgi noktası modları için otomatik oturum açma özelliğinin kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni Ayarlar Edge uygulamaları için AUMID'ler. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlat menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
[Sayfa Görünürlüğü için Yeni SettingsURIs Ayarlar Ayarları](#new-settings-uris-for-page-settings-visibility) | Ayarlar/PageVisibilityList ilkesi için 20'den fazla yeni SettingsURIs. | BT Yöneticisi |
[Geri Dönüş Tanılamasını Yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Uygulamanın Geri Dönüş Tanılama Davranışını Ayarlar ayarlama. | BT Yöneticisi |
[Yakındaki cihazlarla paylaşım](#share-things-with-nearby-devices) | Dosya veya URL'leri bir HoloLens bilgisayara paylaşın. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | Işletim sistemi güncelleştirmeleri Ayarlar yeni sorun giderici. | BT Yöneticisi |
[Teslim İyileştirme Önizleme](#delivery-optimization-preview) | Birden çok farklı cihazdan yapılan indirmeler için bant HoloLens düşürebilirsiniz. | BT Yöneticisi |

İlgili sürüm notlarına göz at:

- [HoloLens Emulator arşivini ziyaret edin](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Kılavuzları](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge yeni Microsoft Edge animasyonu.](images/new-edge.gif)

Yeni [Microsoft Edge, müşteriler için daha Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) uyumluluk ve web geliştiricileri için web'in daha az parçalanması için yeni açık kaynak projesini benimsemektedir.

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde Microsoft Edge [eski](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) sürümler'in yerini otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni uygulamayı Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi.](images/new_edge_logo.png) (mavi ve yeşil bir swirl simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski Microsoft Edge. Yeni Microsoft Edge başlattıktan sonra eski verileri kullanmaya devam eder Microsoft Edge, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, ÖNCEKI 2. HoloLens'da, ESKI Microsoft Edge'da mevcut olandan çok daha geniş bir tarayıcı Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Enterprise belgeleri](/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge HoloLens ekibimiz her yeni ilkenin 2. Ancak, daha önce HoloLens 2'de desteklenen her eski Microsoft Edge Microsoft Edge ilkenin eşdeğerini test ettik ve HoloLens doğruladık. 2 Microsoft Edge'in eski sürümü [Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski Microsoft Edge tarayıcı ilkesine eşdeğer olan yeni Microsoft Edge eşlemeyi bulmak için bkz. HoloLens eşlemesi.
>
> 2. Microsoft Edge en az iki *yeni ilke* HoloLens:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'Microsoft Edge yeni HoloLens bekliyor

Yeni Microsoft Edge, yeni bir UWP bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan ve bu uygulamanın yalnızca UWP 2 gibi UWP cihazlarda çalışmasına izin HoloLens bazı özellikler hemen kullanılabilir olabilir. Önümüzdeki aylarda yeni senaryoları ve özellikleri destekley edeceğimiz için bu alanı güncel bilgiler için kontrol edin.

**Çalışması beklenen senaryolar ve özellikler:**
- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri beklendiği gibi işlemeli ve davranabilir
- Çoğu tarayıcı işlevi (Sık Kullanılanlar, Geçmiş vb.) beklendiği gibi çalışmalı
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

    ![VR düğmesi örneği girin.](images/75px-enter-vr.png)

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

    ![360 görüntüleyicisini etkinleştirme düğmesi.](images/enter-360-viewer.jpg)

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

![yeni uygulama giriş sayfası Ayarlar.](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- arama Ayarlar: anahtar sözcükler veya ayarın adı kullanılarak Ayarlar giriş sayfasından ayarları arayın.
- Sistem > sesi:
  - giriş ve çıkış ses cihazları: bağımsız olarak giriş ve çıkış ses cihazlarınızı seçin (örneğin, Bluetooth kulaklık aracılığıyla ses dinleyin veya ses girişi için bir USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar HoloLens 2 tarafından desteklenmez.
  - Uygulama hacmi: her uygulamanın birimini bağımsız olarak ayarlayın. Bkz. [uygulama birimi denetimi başına](#per-app-volume-control).
- System > güç & uyku: bir süre işlem yapılmadan sonra cihazın uyku moduna geçmesi gerektiğini seçin.
- Sistem > pili: pil tasarrufu modunu el ile etkinleştirin veya nokta pil tasarrufu modunun otomatik olarak etkinleştirileceği bir pil eşiği ayarlayın.
- USB > cihazlar: varsayılan olarak USB bağlantılarını devre dışı bırakabilirsiniz.
- Internet & ağı:
  - USB-C Ethernet bağdaştırıcıları artık ağ & Internet 'te görüntülenir.
  - USB-C Ethernet bağdaştırıcısı ayarları, IP adresi dahil artık kullanılabilir.
  - artık HoloLens 2 üzerinde uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için bkz. [Varsayılan uygulama Seçicisi](#default-app-picker).
- Hesaplar diğer kullanıcılar >: cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilir, cihaz sahiplerini standart kullanıcılara indirgeyebilirler ve kullanıcıları kaldırabilir.
- Erişim kolaylığı: metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- daha önce yerleştirilmiş Ayarlar pencereleri kaldırılır (yukarıdaki nota bakın).
- cihazınızı artık Ayarlar uygulamayla yeniden adlandıramazsınız. bt yöneticileri, HoloLens 2 cihaz adı şablonu veya MDM [devdetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername düğümü [için Windows Autopilot](hololens2-autopilot.md) kullanarak cihazları yeniden adlandırabilirler.
- Ethernet sayfasında her zaman sanal bir Ethernet aygıtı ("UsbNcm") gösterilir.
- yeni Microsoft Edge pil kullanımı, bir UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak doğası nedeniyle doğru olmayabilir (kısa süre önce düzeltilmez).

#### <a name="display-color-calibration"></a>Ekran renk ayarı



bu yeni ayarla, HoloLens 2 görüntü için alternatif bir renk profili seçebilirsiniz. Bu, özellikle daha düşük ekran parlaklığı düzeylerinde renklerin daha doğru görünmesine yardımcı olabilir. ekran renk ayarlaması, Ayarlar uygulamasında, sistem > ayarlama sayfasında bulunabilir.

> [!NOTE]
> Bu ayar, görüntüleme bellenimine yeni bir renk profili kaydederken bu, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Ekran renk ayarı 'nı kullanma

1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında, **görüntü renk ayarlama Çalıştır** düğmesini seçin.
1. Ekran renk ayarlama deneyimi başlatılır ve bu işlem, vizörü ' inizin doğru konumda olduğundan emin olmanızı sağlar.
1. Yönerge iletişim kutularında ilerledikten sonra, ekran otomatik olarak %30 oranında gri olacak.
    > [!TIP]
    > ortamınızdaki soluk sahneyi görmekte sorun yaşıyorsanız, cihazın sol tarafındaki parlaklık düğmelerini kullanarak HoloLens 2 ' nin parlaklık düzeyini el ile ayarlayabilirsiniz.
1. Her renk profilini hemen denemek ve gözlerinize en iyi şekilde bakmak için düğmeler 1-6 ' i seçin (Bu, genellikle sahnenin gri tonlamalı bir şekilde görünmesine yardımcı olan profil ve beklenen şekilde görünür.)

    ![Renk ayarlama sahneyi görüntüleyin.](images/color-cal-ui.png)
    
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

![Varsayılan oturum açma ekranı.](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C dış mikrofon desteği

> [!IMPORTANT]
> **BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**. bir USB-C kulaklık kümesini yüklerken, kullanıcıların kulaklık sesinin otomatik olarak yeniden yönlendirildiğini gözlemleyeceksiniz, ancak HoloLens OS iç microphone dizisinin diğer herhangi bir giriş cihazını önceliklendirilecektir. **Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**

Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir. USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.

**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.

![ses Ayarlar.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.
>
> Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın. **Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.
>
> **iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens mıc dizisi diğer görevler için hala kullanılabilir.

![Ses aygıtlarını yönetin.](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği nedir?

ne yazık ki Bluetooth mikrofonlar halen HoloLens 2 ' de desteklenmemektedir.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonları sorunlarını giderme

Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. bu mikrofonlardan birini HoloLens içine takarken, ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.

![USB-C mikrofonları sorunlarını giderme.](images/usbc-mic-4.png)

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

Daha eski derlemelerde, bir cihazın bir bilgi noktası yapılandırması varsa ve bu, hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişimin bir birleşimi ise, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "[hiçbir şey gösterilmez](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)" menüsünü görür.

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

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmeleri için yeni Ayarlar eklenmiştir. Güncelleştirme Ayarlar  ->  **Sorun &amp; Giderme'ye gidin**  >  **Windows**  >  **Başlat'ı** **seçin.** Bu sayede, IŞLETIM sistemi güncelleştirmeleriyle sorunlarınızı yeniden üretirken, IT veya destekle ilgili sorun giderme konusunda daha iyi yardımcı olmak için izlemeleri toplamanıza olanak sağlar.

### <a name="delivery-optimization-preview"></a>Teslim İyileştirme Önizleme

Bu güncelleştirme HoloLens, birden Windows Holographic for Business cihazlardan indirmeler için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarını HoloLens sağlar. Bu işlevin daha ayrıntılı bir açıklaması ve önerilen ağ yapılandırması burada mevcuttur: [güncelleştirmeleri Teslim İyileştirme için Windows 10 kullanılabilir.](/windows/deployment/update/waas-delivery-optimization)

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
- Windows Holographic for Business http indirme modlarını ve bir Microsoft Bağlı Önbellek [uç noktasını destekler;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Eşler arası indirme modları ve grup atamaları şu anda HoloLens cihazlar için desteklenmiyor.
- HoloLens, Sunucu Güncelleştirme Hizmetleri uç noktaları için Windows veya teslim iyileştirmesini desteklemez.
- Sorun giderme işlemi, Bağlı Önbellek sunucusunda tanılama gerektirir veya HoloLens'de HoloLens'de Ayarlar   >  **Update & Security**  >   **Troubleshooting** Windows Update aracılığıyla  >   **bir izleme toplamayı gerektirir.**

### <a name="it-admin---update-checklist"></a>IT Yöneticisi - Güncelleştirme Denetim Listesi

Bu denetim listesi, geçerli cihaz yönetimi yapılandırmalarınızı veya kullanmaya başlamak istediğiniz yeni özellikleri etkileyebilecek bu özellik güncelleştirmesinde eklenen yeni öğeleri size yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi Noktası modundaki güncelleştirmeler

✔️ Bilgi [**Noktası modunda yeni uygulamalar için Yeni AUMID'ler oluşturun:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Daha önce Ayarlar uygulamasını veya Microsoft Edge Bilgi Noktası'Microsoft Edge kullanıyorsanız, bu uygulamaları farklı bir Uygulama Kimliği kullanan yeni uygulamalarla değiştiririz. Aşağıdaki Bilgi Noktası modundaki [yeni uygulamalar için Yeni AUMID'leri okumanız önemle](#use-the-new-settings-and-edge-apps-in-kiosk-modes) tavsiye edilecektir. Bu, bilgi noktası uygulamanıza sahip olmaya devam Ayarlar veya yeni uygulama uygulamanıza Microsoft Edge sağlar. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirmede daha sorunsuz bir geçişe olanak tanır.

✔️ Bilgi [**Noktası için Ziyaretçi Otomatik Oturum Açma:**](#visitor-auto-logon-for-kiosks) 

Ziyaretçiler artık bir Bilgi Noktası'nde otomatik olarak oturum açabilirsiniz. Bu davranış varsayılan olarak açıktır, ancak yönetilebilir ve devre dışı bırakılabilir.

✔️ Bilgi [**Noktası modu hatası teslimi:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Oturum açmış AAD kullanıcılarının AAD grup üyeliği başarıyla belirlenene kadar, başlat menüsü (varsa) için genel bilgi noktası yapılandırması kullanılır, aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınıza bildirmeniz gereken bir şey olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ve Ayarlar Güncelleştirmeleri

✔️ [**Görünürlüğü Ayarlar Için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarlar [Görünürlük](settings-uri-list.md) kullanıyorsanız, izin verilen veya engellenen mevcut URI'ler üzerinde ayarlamalar yapmak iyi olabilir.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler
✔️ WDAC aracılığıyla Microsoft Edge engelleme yaptıysanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme
✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa lütfen yeni uygulama için bu yeni uç Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere toplayıp toymayy ve kimlerin toplaymzı olduğunu yapılandırmış oluruz.

✔️ Cihazları[yakın cihazlarla paylaşma:](#share-things-with-nearby-devices)Yakındaki yeni paylaşım özelliğini devre dışı abilirsiniz.

✔️ [yeni uygulama için ilke ayarlarını yapılandırma: Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)için kullanılabilen yeni yapılandırmaları Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Yeni tanılama aracı

✔️ yeni[işletim sistemi tanılama izlemeleri:](#new-os-diagnostic-traces)Işletim Sistemi Güncelleştirmeleri ile ilgili günlükleri toplayın.

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
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'Windows en son derlememizi denemeniz için sizi teşvik ederiz.

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

- Yerel bir hesap Ayarlar parola değiştirmeye çalışırken uygulamanın kilitlenmesi ile ilgili bir sorunu gidermek.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, sürüm 20H2 - Mart 2021 Güncelleştirmesi
- Derleme 19041.1140

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 ile fotoğraf yakalamak için AdvancedPhotoCapture veya LowLagPhotoCapture kullanan müşteriler artık fotoğraf kaydedildikten 3 saniye sonra kamera pozunu alabilir.
- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.
- Aşamalı Rollout'a kaydolan kullanıcıların cihazda oturum alamama sorunu düzeltildi.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, sürüm 1903 - Mart 2021 Güncelleştirmesi
- Derleme 18362.1102

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, sürüm 20H2 - Şubat 2021 Güncelleştirmesi
- Derleme 19041.1136

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İlk cihaz kurulumu ve mağaza uygulaması güncelleştirmeleri ile ilgili bir sorunu düzeltir.
- Sonraki sürümler için yükseltme ve uçuş ile ilgili HoloLens gidermek.
- eSIM kök depolamadan kullanılmayan önceden yüklenmiş sertifikalar, HoloLens kaldırıldı.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, sürüm 1903 - Şubat 2021 Güncelleştirmesi
- Derleme 18362.1098

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, sürüm 20H2 - Ocak 2021 Güncelleştirmesi
- Derleme 19041.1134

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihazda çok sayıda kullanıcı olduğunda başlatma, sürdürme ve kullanıcı değiştirme sırasında performans geliştirildi.
- [Araştırma modu](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)için ARM32 desteği eklendi.

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

Artık Geliştirici modunu etkinleştirmek veya cihaz portalını kullanmak gerekmeden uygulama yükleyebilirsiniz.  Cihazınıza appx paketini indirmeniz (USB veya-Edge üzerinden) ve yüklemeyi başlatma istenmeden dosya Gezgini 'ndeki appx grubuna gitmeniz yeterlidir.  Alternatif olarak, [bir Web sayfasından bir yüklemeyi başlatabilirsiniz](/windows/msix/app-installer/installing-windows10-apps-web).  MDM 'nin LOB uygulaması dağıtım özelliğini kullanarak Microsoft Store veya dışarıdan yüklemeden yüklediğiniz uygulamalar gibi uygulamalar, [imza aracı](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) ile dijital olarak imzalanmalıdır ve uygulama dağıtılmadan önce [imzalamak için kullanılan sertifikaya HoloLens cihaz tarafından güvenilmesi gerekir](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) .

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

![Uygulama yükleyicisi aracılığıyla MRTK örnekleri yükleniyor.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El ile izleme artık, izlemenin daha önce kaybedildiği birçok yeni durumda izlemeyi korur.  Bu yeni durumların bazılarında, yalnızca Palm konumu kullanıcının gerçek adına göre güncelleştirilmeye devam ederken, diğer yandan da önceki bir poza göre çıkarılır.  Bu değişiklik, taşıma, oluşturma, scoing ve hareketli hale alma gibi hareket halinde izlemenin tutarlılığını artırmaya yardımcı olur.  Ayrıca, el 'nin bir yüzeye yakın veya bir nesneyi tutan durumlarda da yardımcı olur.  Bu yandan, her ne kadar [ortak doğruluk](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) değeri "yüksek" yerine "yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamasının bir hata göstereceği bir sorun düzeltildi "bir sorun oluştu.
- Kullanıcılar, ayarlar uygulaması, Yeni Kullanıcı veya bildirim bildirimi ' ni başlatırken, kullanıcıların çok daha az önyükleme sonrası OOBE kilitlenmelerini görmelidir.
- Kullanıcıların, OOBE 'den gelen doğru saat dilimi olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 güncelleştirme
- Derleme 18362,1088

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son Windows Holographic, sürüm 20h2 – aralık 2020 güncelleştirme ve yapıya eklenen yeni uygulama yükleyicisi özelliğini denemenizi öneririz.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2
- Derleme 19041,1128

Windows Holographic, 20h2 sürümü artık kullanılabilir ve 2 kullanıcı ve bt uzmanlarına HoloLens harika yeni özellikler sunuyor. otomatik göz konumlandırmayı, Ayarlar ' deki sertifika yöneticisi 'ne, gelişmiş bilgi noktası modu işlevselliğine ve yeni Autopilot kurulum özelliklerine sahip. bu yeni güncelleştirme, bt ekiplerinin HoloLens cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetim almasını sağlar ve kullanıcılara daha sorunsuz holographic deneyimleri sunar. 

Bu en son sürüm 2004 sürümüne yönelik aylık bir güncelleştirmedir, ancak bu kez yeni özellikler de ekledik. ana yapı numarası aynı kalacaktır ve Windows Update sürüm 2004 ' e yönelik aylık bir yayın olduğunu belirtecektir (derleme 19041). en son kullanılabilir derleme 19041.1128 + ' de olduğunu onaylamak için Ayarlar > ekranında yapı numaranızı görebilirsiniz. en son sürüme güncelleştirmek için Ayarlar uygulamasını açın, güncelleştirme & güvenlik ' e gidin ve güncelleştirmeler için denetle ' ye dokunun. HoloLens güncelleştirmelerinin nasıl yönetileceği hakkında daha fazla bilgi için, [HoloLens güncelleştirmelerini yönet](hololens-updates.md)' e gidin.

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

![Ayarlar uygulamasındaki sertifika görüntüleyicisi.](images/certificate-viewer-device.jpg)

![Sertifika Kullanıcı arabiriminin bir sertifikayı yüklemek için nasıl kullanılacağını gösteren resim.](images/certificate-device-install.jpg)

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
- OOBE deneyiminde cihazın sahibini seçme 

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama.](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır? 
1. Yukarıda HoloLens 2'nin daha önce atandığı cihaz yapılandırmasının atandığı cihaz grubundan 2. kümeyi kaldırın. 

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin. OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü.](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Autopilot profili bir HoloLens OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilene kadar süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için, cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir.

![Cihazda ilkenin ne zaman zorlanan cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık [Tenantlockdown CSP](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)ve Autopilot altında Autopilot'ın geri kalanıyla birlikte bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel Atanan Erişim – Bilgi Noktası Modu
- Bilgi noktası modunu sistem düzeyinde geçerli olan yeni Bilgi Noktası yöntemi etkinleştirerek Bilgi Noktası için Azaltılmış Kimlik Yönetimi.

Bu yeni özellik, bir IT Yöneticisinin sistem düzeyinde geçerli olan, sistem üzerinde herhangi bir kimliğe benzeşimleri olan ve cihazda oturum açabilen herkes için geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırmasını sağlar. Bilgi noktası modunda bu yeni özellik hakkında [HoloLens okuyun.](hololens-kiosk.md)

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
| MixedReality\MicrophoneDisabled                    | 2. görüntüde ses kaydının mümkün HoloLens devre dışıdır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin ne zaman toplanabilir davranışını kontrol eder.                               | 0 Devre Dışı, 1 Cihaz Sahipleri için Etkin, 2 Herkes için Etkin (Varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD gruplarını hedef alan Bilgi Noktası için Azure AD grup üyeliği önbelleğinin kaç gün süreyle kullanıl olduğunu kontrol eder. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın
- 60 gün boyunca AAD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılaca lı olduğunu kontrol eder. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi takdirde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayaran ve bu değeri HoloLens cihaza atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
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
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                          |
|     [Standbytimeoutonpili](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [Standbytimeoutpluggedın](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Bu iki yeni ilke Displayofftimeoutonpili ve Displayofftimeoutpluggedın [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

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
 
![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü.](images/hololens-page-visibility-list.jpg)

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

- Unity uygulamalarında izleme kaybı veya yeniden izleme elde edilirken hologramların kaybolmasına neden olan bir sorun düzeltildi.
- Belirli cihazlarda donanım hızlandırma ile HoloLens sırasında özel uygulama uygulamalarının kabukta kilitlenmesi HoloLens Emulator bir sorun düzeltildi.
- HoloLens 2'de, Windows Cihaz Portalı için HTTPS iletmeyle ilgili bir HoloLens giderildi.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, sürüm 2004 - Haziran 2020 Güncelleştirmesi
- Derleme 19041.1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirli özellikler belirtilmezse yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Sesi Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses hatalarını **ortadan** kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, web tarayıcısı geçersiz bir sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı bu durumla devam etmek mümkün değildir. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş girişlerinden tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- HoloLens öykünücüsünü siyah olarak işlemek için piksel biçimlerini değiştirmeye neden olan HoloLens düzeltildi.
- Iris oturum açma sırasında kilitlenmeye neden olan bir hata düzeltildi.
- Zaten geçerli olan uygulamalar için yinelenen mağaza indirmeleri ile ilgili bir sorun düzeltildi.
- Çevreleyici uygulamaların arka arkaya uygulama açmasını engelleyen Microsoft Edge düzeltildi.
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
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Sesi Kazancı" Windows Cihaz Portalı)
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, arka planda çalıştıracak ayar etkinleştirilse bile, bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Piksel biçimlerini siyah HoloLens olarak değiştiren uygulamalara neden olan bir sorun HoloLens Emulator.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, sürüm 2004  
- Derleme - 19041.1103

HoloLens 2, Windows Holographic için Mayıs *2020* ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5G/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni özellikler içerir. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve   Güncelleştirmeleri **Kontrol Edin düğmesini** ****   seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak yeni cihazları üretim için önceden yapılandırma ve sorunsuz bir şekilde ayarlama                 |
|       FIDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamasını etkinleştirmek için FIDO2 Güvenlik Anahtarları desteği            |
|       Geliştirilmiş sağlama                      |          Usb sürücüden uygulamanıza sorunsuz bir şekilde bir sağlama paketi HoloLens                              |
|       Uygulama yükleme durumu                 |          MDM aracılığıyla Ayarlar 2'ye HoloLens uygulamanın yükleme durumunu denetleme               |
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

[Windows autopilot for HoloLens 2 değerlendirme kılavuzundan daha fazla bilgi edinin.](hololens2-autopilot.md)

*Şimdi AutoPilot önizlemeye katılmak için Hesap Yöneticinize ulaşın. Autopilot'a hazır cihazlar yakında gönderime başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar, HoloLens veya okul ortamındaki diğer kullanıcılarla bir cihaz paylaşır. Bu nedenle, kullanıcıların uzun kullanıcı adları ve parolalar yazmadan kolayca ulaşabiliyorları önemlidir. Fast Identity Online (FIDO), bir kullanıcı adı veya parola girmeden, kuruluşta (Azure AD kiracısı) HoloLens oturum açmasına olanak sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktöründe getirilebilir, standartlara dayalı bir parolasız kimlik doğrulama yöntemidir. FIDO, parolasız kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kaynaklarında kullanıcı adı veya parola olmadan oturum açmalarına olanak sağlar. Bunun yerine bir dış güvenlik anahtarı veya cihazda yerleşik olarak yer alan bir platform anahtarı kullanırlar.

Çalışmaya başlama için [bkz. Parolasız güvenlik anahtarı oturum açmasını etkinleştirme.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Paketleri sağlama, HoloLens deneyimi yerine bir yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamaya izin sağlar. Daha önce, sağlama paketlerinin iç belleğe kopya HoloLens vardı. Artık bir USB sürücüde olabilir, böylece birden çok cihaz veya HoloLens cihazları paralel olarak silebilirler. Sağlama paketleri artık cihaz yönetimine kaydolmak için bir alanı destekledikten sonra, sağlamadan sonra el ile kurulum gerektirmez.

Denemek için:

1. Windows Configuration Designer 'ın en son sürümünü Windows mağazasından bilgisayarınıza indirin.
1. **HoloLens sağla**' yı seçin  >  **HoloLens 2 cihaz sağlayın**.
2. Yapılandırma profilinizi oluşturun. Ardından, bir USB-C depolama cihazına oluşturulan tüm dosyaları kopyalayın.
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

![Koyu modda Windows döşeli.](images/DarkMode.jpg)

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

Bu aylık kalite güncelleştirmesi, ekip daha önce açıklandığı gibi Windows Holographic sürüm 2004 Mayıs Güncelleştirmesi üzerinde çalıştığı için önemli bir değişiklik içermemektedir.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, sürüm 1903 - Nisan 2020 Güncelleştirmesi
- Derleme 18362.1059

**Desteklenen uygulamalar için koyu mod** 

Birçok Windows hem koyu hem de açık modu destekler. HoloLens 2 müşteri artık her iki renk düzenini de destekleyen uygulamalar için varsayılan modu seçebilir. Müşteri geri bildirimlerine dayanarak varsayılan uygulama modunu "koyu" olarak ayarlamış oluruz ancak bu ayarı istediğiniz zaman kolayca değiştirebilirsiniz: "Varsayılan uygulama modunu seçin" Ayarlar > **System > Colors'a** **gidin.**

Bu "in-box" uygulamaları koyu modu destekler:
- Ayarlar
- Microsoft Store
- Posta
- Takvim
- Dosya Gezgini
- Geri Bildirim Merkezi
- OneDrive
- Fotoğraflar
- 3B Görüntüleyici
- Filmler & TV

**Güncelleştirmede yapılan geliştirmeler ve düzeltmeler:** 
- Kabuk katmanlarının karma gerçeklik yakalamalarına dahil olduğundan emin olmak.
- Unreal geliştiricileri artık uygulamalarını test etmek ve hata ayıklamak için Cihaz Portalı 3B Görünüm sayfasını kullanabilir.
- *HolographicDepthReprojectionMethod DepthReprojection* algoritması kullanılırken karma gerçeklik yakalamada geliştirilmiş hologram kararlılığı.
- 32 bit ARM uygulamaları üzerinde "WinRT IStreamSocketListener API Sınıfı kayıtlı değil" hatası düzeltildi.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, sürüm 1903 - Mart 2020 Güncelleştirmesi 
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
- Holografik uygulamaların başlangıçta duraklatılmış durumda takılı kalan ve sonra kapatılana kadar Başlat menüsü sorunları düzeltildi.
- OpenXR çalışma zamanı uyumluluk düzeltmeleri ve HoloLens 2 ve öykünücü için geliştirmeler.
