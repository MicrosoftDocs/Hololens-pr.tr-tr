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
ms.openlocfilehash: b7ce9f94fb6d3074f8b7f517af6bd70c78462ddc
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659548"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notu

Yeni cihazlarınızı kullanarak verimli bir deneyim HoloLens için özellik, hata ve güvenlik güncelleştirmelerini yayınlaya devam edeceğiz. Bu sayfada, her ay yeni HoloLens görebilirsiniz. En son HoloLens 2 güncelleştirmesini almak için [](hololens-update-hololens.md#check-for-updates-and-manually-update) güncelleştirmeleri kontrol edebilirsiniz ve el ile güncelleştirebilir veya Tam Flash Güncelleştirme'yi (FFU) Gelişmiş Kurtarma Yardımcı'sı aracılığıyla cihazınızı söntebilir. [](hololens-recovery.md#clean-reflash-the-device) İndirme [güncel](https://aka.ms/hololens2download) tutulur ve genel kullanıma açık en son derlemeyi sağlar.

> [!NOTE]
> Son Windows 11 duyurusu, 11'in bilgisayar sürümüne Windows. Kısa süre [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) önce Mayıs 2021'de HoloLens 2'ye büyük bir işletim sistemi güncelleştirmesi başlattık ve bu düşüş için müşteri geri bildirimlerine dayanarak gelecek bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)derlememizde Remote Assist kullanıcılarını etkileyen bilinen bir sorun nedeniyle, Windows Holographic sürüm 21H1 güncelleştirmelerinin tekliflerini geçici olarak duraklatıldık. Ayrıca varsayılan Gelişmiş Kurtarma Yardımcı (ARC) derlemesini [Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi olarak değiştirdik.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) ARC derlemesi artık 21H1 derlemeyi hedeflemeye devam edecek.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1 - Temmuz 2021 Güncelleştirmesi
- Derleme 20348.1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi Ayarlar -Wi-Fi > **Ağ & İnternet -> Durumu ->** Özellikler'den başlatılamadığına ilişkin bir sorun düzeltildi.
- ESIM sertifikalarının işletim sistemi güncelleştirmeleri arasında kaldırılmasıyla ilgili bir sorun giderildi. Bu düzeltme, 21H1 sürümüne güncelleştirmeden önce eSIM sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- Önceden yüklenmiş uygulamaları işletim sistemi sıfırlamaları arasında etkileyen bir sorun düzeltildi. 
- Artan CPU yüklemesi ile ücretlendirme sırasında çalışma zamanını artırmak için pil ücretlendirme performansı ayarlanmıştır.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – Temmuz 2021 Güncelleştirmesi
- Derleme 19041.1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır. 
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1 - Haziran 2021 Güncelleştirmesi
- Derleme 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive veya okul kameralarını karşıya yükleme

HoloLens 2 Ayarlar uygulamasına, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın Resimler > Camera Roll klasöründen iş veya okul için ilgili OneDrive klasörüne otomatik olarak yüklemelerini sağlayan yeni bir özellik ekledik. Bu özellik, HoloLens 2'de [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) uygulamasındaki bir özellik açığına yöneliktir. Bu, yalnızca müşterinin kişisel hesabına (iş veya okul hesabı değil) otomatik Kamera Microsoft hesabı yüklemesini destekler.

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

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx, telemetri ve davranış üzerinde tam denetime sahip olmak için birlikte Ayarlar kullanılmalıdır.

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

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx, telemetri ve davranış üzerinde tam denetime sahip olmak için birlikte Ayarlar kullanılmalıdır.

Holographic sürüm 21H1'Windows en son derlememizi denemeyi teşvik ederiz.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, sürüm 1903 - Haziran 2021 Güncelleştirmesi
- Derleme 18362.1116

Güncelleştirmedeki geliştirmeler ve düzeltmeler:
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

>[!IMPORTANT]
> Bu derleme artık hizmette olmayacaktır.

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
> Windows Holographic sürüm 21H1'in tanıtımıyla, Windows Holographic sürüm **1903** için aylık bakım güncelleştirmelerini sonlandırıyoruz. Bu sayede daha yeni sürümlere odaklanarak değerli geliştirmeler yapmaya devam edeceğiz. 


| Özellik Adı                                              | Kısa açıklama                                                                      | Hedef Hedef Kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | Yeni, Chromium tabanlı Microsoft Edge artık 2. HoloLens kullanılabilir. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyici](#webxr-and-360-viewer) | Modern Web deneyimleri ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
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

**Bilinen en önemli tarayıcı sorunları:**

- Holografik klavyede büyüteç önizlemesi, yeni Microsoft Edge. Bu özelliği, büyütme doğru şekilde çalışmaya başladıktan sonra gelecekteki bir güncelleştirmede yeniden kullanılabilir hale gelecektir.
- Başka bir tarayıcı penceresi açık ve etkinse ses yanlış tarayıcı penceresinden oynatılmış olabilir. Ses çalması gereken diğer etkin pencereyi kapatarak bu soruna bir son ve sonra bakabilirsiniz.
- "Beni takip et" modundaki bir tarayıcı penceresinden ses çalacaksanız, "Beni takip [et"](hololens2-basic-usage.md#follow-me-stop-following)modunu devre dışı bıraksanız ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu **atlayabilirsiniz.**
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerini beklenmedik şekilde devre dışı bırakarak devam ediyor olabilir. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Microsoft Edge ekibi Edge Insider topluluğuna üç önizleme kanalı sağlar: Beta, Dev ve Canary. Bir önizleme kanalını yüklemek, Microsoft Edge 2'nize HoloLens sürümünü kaldırmaz ve aynı anda birden fazla yükleyebilirsiniz. 

Edge Insider Microsoft Edge daha fazla bilgi edinmek için Microsoft Edge [Insider](https://www.microsoftedgeinsider.com) giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamak için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Insider kanallarını 2. Microsoft Edge yüklemek için HoloLens vardır:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetemeyen cihazlar tarafından kullanılabilir)**
  1. 2. HoloLens Edge Insider indirme [sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge **Insider HoloLens 2** için İndir düğmesini seçin.
  1. İndirilen .msix dosyasını Edge indirme kuyruğundan veya cihazınızın "İndirmeler" klasöründen (Dosya Gezgini.
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatacak.
  1. Yükle **düğmesini** seçin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

**Windows Cihaz Portalı ile PC üzerinden yükleme [](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (2. HoloLens geliştirici modunun etkinleştirilmesi gerekir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki aşağı ok düğmesini seçin.
  1. Açılan **HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) dosyasını Windows Cihaz Portalı 2.0'a yüklemek için bilgisayarınızda HoloLens kullanın.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) uygulama Microsoft Edge güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](/deployedge/microsoft-edge-security-endpoints)

için kullanılabilir olan uç noktalar hakkında [daha fazla bilgi HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Web uygulamalarını yükleme
 > [!Note]
>Holographic [Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)sürümünden Office web uygulaması artık önceden yüklenmez.

Yeni Edge'i kullanarak web uygulamalarını ve diğer Microsoft Store yükleyebilirsiniz. Örneğin, Microsoft Office veya SharePoint barındırılan dosyaları görüntülemek ve düzenlemek için OneDrive. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya Office düğmesini seçin.   Onaylamak **için Yükle'yi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca 2. HoloLens etkin bir İnternet bağlantısı olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici

Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR ile tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler HoloLens 2 tarafından de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimleri de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak 2 müşterinin denemesi için yeni artırılmış ve karma gerçeklik HoloLens deneyimler gelmesini bekliyor!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve 2. Microsoft Edge yeni HoloLens yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

#### <a name="how-to-use-webxr"></a>WebXR kullanma

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

1. Belirli bir etki alanında 360 Görüntüleyiciyi ilk kez başlatmayı deneyrken tarayıcı çevreleyici bir görünüm girmek için onay sorar. İzin **Ver'i seçin.**
1. [Kayıttan yürütme](hololens2-basic-usage.md#select-using-air-tap) denetimlerini açmak için havadan dokunma. El [işleyicileri](hololens2-basic-usage.md#select-using-air-tap) ve havadan dokunarak oynatma/duraklatma, ileri/geri atlama, açıklamalı alt yazıları açma/kapatma veya deneyimi durdurma (çevreleyici görünümden çıkar) için kullanın. Kayıttan yürütme denetimleri birkaç saniyelik bir süre sonra kaybolur.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>En önemli WebXR ve 360 Görüntüleyici bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak kare hızı düşerek veya düşerek düşebilirsiniz.
- WebXR'de ifadeli el ortakları için destek varsayılan olarak etkin değildir. Geliştiriciler `edge://flags` "WebXR El Girişi"ni etkinleştirerek desteği etkinleştirerek.
- YouTube dışında web sitelerinden 360 video beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyicisi hakkında geri bildirim sağlama

Lütfen yeni çalışmadaki Geri Bildirim Gönder özelliği **aracılığıyla geri bildirimi** ve hataları ekibimizle Microsoft Edge.

### <a name="new-settings-app"></a>Yeni Ayarlar uygulaması

Bu sürümle birlikte, Ayarlar uygulamasının yeni bir sürümünü Ayarlar. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni Ayarlar eski Ayarlar uygulamasından ayrı olduğundan, Ayarlar ortamınıza yerleştiren tüm windows güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarlar: Anahtar sözcükleri veya ayarın adını Ayarlar giriş sayfasından ayarlar için arama yapın.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, ses seslerini ses Bluetooth veya ses girişi için USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar, 2. HoloLens desteklemez.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Bkz. [uygulama başına birim denetimi.](#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktanın otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık uçak modunu 2. HoloLens etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için bkz. [Varsayılan uygulama Seçicisi](#default-app-picker).
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

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma

Bu yeni özellik, Ziyaretçi hesaplarında otomatik oturum açma özelliğinin Bilgi Noktası modları için kullanılmaktadır.

AAD olmayan bir yapılandırma için, ziyaretçi otomatik oturum açma için bir cihaz yapılandırmak üzere:

1. Şunları içeren bir sağlama paketi oluşturun:
    1. Ziyaretçi **hesaplarına izin vermek için Çalışma Zamanı ayarlarını/AssignedAccess'i** yapılandırıyor.
    1. İsteğe bağlı olarak, daha sonra yönetilsin diye cihazı MDM'ye (Çalışma zamanı **ayarları/Çalışma Alanı/Kayıtlar)** kaydediyor.
    1. Yerel hesap oluşturma
1. [Sağlama paketini uygulama.](hololens-provisioning.md)

AAD yapılandırması için kullanıcılar bu değişiklik olmadan bugün buna benzer bir şey elde ediyor olabilir. Bilgi noktası modu için yapılandırılan AAD'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak Ziyaretçi hesabında oturum açmasını sağlar. Ziyaretçi hesabında oturum açıldıktan sonra, ziyaretçi başlat menüsünden açıkça oturum açıncaya veya cihaz yeniden başlatana kadar cihaz yeniden oturum açma isteminde olmayacaktır.

Ziyaretçi Otomatik oturum açma işlemi özel [OMA-URI ilkesi aracılığıyla](/mem/intune/configuration/custom-settings-windows-10) yönetilebilir:

- URI değeri: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| İlke  | Açıklama   | Yapılandırmalar  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Bir Ziyaretçinin Bilgi Noktası'da otomatik olarak oturum açmasını sağlar   | 1 (Evet), 0 (Hayır, varsayılan.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Bilgi noktası modlarında yeni Ayarlar ve Edge uygulamalarını kullanma

Uygulamaları Bilgi [Noktası'ne](hololens-kiosk.md)eklerken, BIR IT Yöneticisi genellikle uygulamayı Bilgi Noktası'nın yerine Uygulama Kullanıcı Modeli Kimliği'ni (AUMID) kullanarak ekler. Hem Ayarlar hem de Microsoft Edge uygulaması yeni uygulamalar olarak kabul edilir ve bu uygulamalar için AUMID'leri kullanan eski uygulama Bilgi Noktası'lardan farklı olduğundan, yeni AUMID'yi kullanmak için güncelleştirilmelidir.

Bilgi Noktası'nın yeni uygulamaları içerecek şekilde değiştirilmesini sağlarken, yeni AUMID'ye eklemenizi ve eskisini bırakmanız önerilir. Bu, kullanıcılar işletim sistemi güncelleştirecek ve Bilgi Noktası'nın hedeflenen şekilde kullanmaya devam etmek için yeni ilkeler almaları gerekmayacak olduğunda kolay bir geçiş sağlar.

| Uygulama                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Eski Ayarlar Uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Yeni Ayarlar Uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri

Eski derlemelerde, bir cihazın hem genel atanan erişimin hem de AAD grup üyesi tarafından atanan erişimin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğinin başarısız olduğu belirlenirse kullanıcı["](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)başlat " menüsünde hiçbir şey gösterilmez.

Bu sürümden Windows bilgi noktası deneyimi, AAD grup bilgi noktası modunda hata olması durumunda genel bilgi noktası yapılandırmasına (varsa) geri dönüş sağlar.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Sayfa Ayarlar Görünürlüğü için yeni Ayarlar URL'leri

[Holographic Windows sürüm 20H2'de,](hololens-release-notes.md#windows-holographic-version-20h2) [Ayarlar/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ilkesi eklenmiştir. Bu ilke, Ayarlar içinde görülen sayfaları kısıtlar. PageVisibilityList, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkedir.

Page [Ayarlar Visibility](settings-uri-list.md)sayfasını ziyaret ediyorsanız, bu CSP'yi kullanma yönergelerini ve önceki sürümlerde kullanılabilen URL'lerin listesini bulabilirsiniz.

IT Yöneticilerinin yönettikleri kullanılabilir URL'Ayarlar listesini genişletiyoruz. Bu URL'lerden bazıları, yeni uygulamanın içindeki yeni Ayarlar içindir. Ayarlar/PageVisibilityList ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

> [!NOTE]
> **Kullanım dışı: ms-settings:network-proxy**
>
> Bu yeni derlemelerde bir ayarlar sayfası kullanım dışıdır. Eski Ağ **&**  >  **İnternet Ara** Sunucusu sayfası artık genel ayar olarak kullanılamaz. Yeni bağlantı başına ara sunucu ayarları, İnternet   >  **Wi-Fi**& ağ bağlantısı & İnternet Ethernet  >  **Özellikleri** **altında &**  >    >  **bulunabilir.**

<br>

| Ayarlar sayfası                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Uygulamalar > Apps & özellikleri                               | `ms-settings:appsfeatures`                         |
| Uygulamalar > Gelişmiş & uygulamalar > özellikleri          | `ms-settings:appsfeatures-app`                     |
| Uygulamalar > Çevrimdışı haritalar                                  | `ms-settings:maps`                                 |
| Uygulamalar > Çevrimdışı haritalar > Haritaları indirme                  | `ms-settings:maps-downloadmaps`                    |
| Cihazlar > Fare                                      | `ms-settings:mouse`                                |
| Usb > cihazlar                                        | `ms-settings:usb`                                  |
| İnternet & Uçak > Ağ Bağlantısı                   | `ms-settings:network-airplanemode`                 |
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
| System > Depolama > Configure Depolama Sense         | `ms-settings:storagepolicies`                      |
| Saat & Dili > Tarih & saat                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Güncelleştirme & Güvenlik > Sıfırlama & kurtarma               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Güncelleştirilmiş URL'ler

Daha önce aşağıdaki iki URL, bir kullanıcıyı doğrudan belirtilen sayfalara götürmürken yalnızca ana güncelleştirmeler sayfasını engelledi. Aşağıdaki öğeler sayfalarına yönlendirecek şekilde güncelleştirilmiştir:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Geri Dönüş Tanılamasını uygulama aracılığıyla Ayarlar yapılandırma

Artık Ayarlar Uygulama'da, bir kullanıcı Geri Dönüş [Tanılaması'nın davranışını yapılandırabilirsiniz.](hololens-diagnostic-logs.md) Uygulamanın Ayarlar Gizlilik Sorunlarını **Giderme sayfasına**  ->   gidin ve bu ayarı yapılandırabilirsiniz.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, kullanıcı bu davranışı geçersiz k aşağıdaki gibi davranamayacaktır.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla paylaşım

Hem bilgisayarlar hem de diğer Windows 10 2 cihaz dahil olmak üzere neredeyse tüm HoloLens cihazlarla paylaşım. Dosya veya URL'leri **bir Ayarlar** paylaşmak için Sistem Paylaşılan Deneyimleri'HoloLens  ->    ->   deneme yapabilirsiniz. Daha fazla ayrıntı için, [Windows 10'da yakındaki cihazlarla şeyler paylaşma hakkında daha fazla bilgi Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Bu özellik [Bağlantı/AllowConnectedDevices aracılığıyla yönetilebilir.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmeleri için yeni Ayarlar eklenmiştir. Güncelleştirme Ayarlar  ->  **Sorun &amp; Giderme'ye gidin**  >  **Windows**  >  **Başlat'ı** **seçin.** Bu sayede, sorunlarınızı işletim sistemi güncelleştirmeleriyle yeniden üretirken, IT veya destekle ilgili sorunları gidermeye daha iyi yardımcı olmak için izlemeleri toplayabilirsiniz.

### <a name="delivery-optimization-preview"></a>Teslim İyileştirme Önizleme

Bu güncelleştirme HoloLens, birden Windows Holographic for Business cihaz indirmeleri için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarını HoloLens sağlar. Bu işlevin daha ayrıntılı bir açıklaması ve önerilen ağ yapılandırması burada mevcuttur: [güncelleştirmeleri Teslim İyileştirme için Windows 10 kullanılabilir.](/windows/deployment/update/waas-delivery-optimization)

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
- Sorun giderme işlemi, Bağlı Önbellek sunucusunda tanılama gerektirir veya HoloLens'da HoloLens Update **Ayarlar &**  >  **Security Troubleshooting Windows** Update aracılığıyla bir izleme  >     >   **toplamayı gerektirir.**

### <a name="it-admin---update-checklist"></a>IT Yöneticisi - Güncelleştirme Denetim Listesi

Bu denetim listesi, geçerli cihaz yönetimi yapılandırmalarınızı veya kullanmaya başlamak istediğiniz yeni özellikleri etkileyebilecek bu özellik güncelleştirmesinde eklenen yeni öğeleri size yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi Noktası modundaki güncelleştirmeler

✔️ Bilgi [**Noktası modunda yeni uygulamalar için Yeni AUMID'ler oluşturun:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Daha önce Ayarlar uygulamasını veya Microsoft Edge Bilgi Noktası'Microsoft Edge kullanıyorsanız, bu uygulamaları farklı bir Uygulama Kimliği kullanan yeni uygulamalarla değiştiririz. Aşağıdaki Bilgi Noktası modundaki [yeni uygulamalar için Yeni AUMID'leri okumanız önemle](#use-the-new-settings-and-edge-apps-in-kiosk-modes) tavsiye edilecektir. Bu, bilgi noktası uygulamanıza sahip olmaya devam Ayarlar veya yeni uygulama Microsoft Edge sağlar. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirmede daha sorunsuz bir geçişe olanak tanır.

✔️ Bilgi [**Noktası için Ziyaretçi Otomatik Oturum Açma:**](#visitor-auto-logon-for-kiosks) 

Ziyaretçiler artık bir Bilgi Noktası'nde otomatik olarak oturum açabilirsiniz. Bu davranış varsayılan olarak açıktır, ancak yönetilebilir ve devre dışı bırakılabilir.

✔️ [**Bilgi Noktası modu hatası teslimi:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Oturum açmış AAD kullanıcılarının AAD grup üyeliği başarıyla belirlenene kadar, başlat menüsü için genel bilgi noktası yapılandırması kullanılır (varsa) aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınızı bilgilendiren bir işlem olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ve Görünürlük Ayarlar Güncelleştirmeleri

✔️ [**Görünürlüğü Ayarlar Için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarlar [Görünürlüğü](settings-uri-list.md) kullanıyorsanız, izin verilen veya engellenen mevcut URI'ler üzerinde ayarlamalar yapmak iyi olabilir.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler
✔️ WDAC aracılığıyla Microsoft Edge engelliyorsanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme
✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, yeni uygulama için bu yeni uç noktaları Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere toplayıp toymayy ve kimlerin toplay olduğunu yapılandırmış oluruz.

✔️ Cihazları[yakın cihazlarla paylaşma:](#share-things-with-nearby-devices)Yakındaki yeni paylaşım özelliğini devre dışı abilirsiniz.

✔️ için [ilke ayarlarını yapılandırma Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Yeni yapılandırmalar için kullanılabilir olan yeni yapılandırmaları Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Yeni tanılama aracı

✔️[yeni işletim sistemi tanılama izlemeleri:](#new-os-diagnostic-traces)Işletim Sistemi Güncelleştirmeleri ile ilgili günlükleri toplayın.

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- [Çevrimdışı tanılama,](hololens-diagnostic-logs.md#offline-diagnostics) seri numarası ve işletim sistemi sürümü için ek cihaz bilgileri de içerir.
- Çalışma zamanı sağlama paketleri aracılığıyla iş hattı uygulamalarının dağıtımıyla ilgili bir sorunu düzeltir.
- İş hattı uygulaması yükleme durumu raporlaması ile ilgili bir sorunu düzeltir.
- Cihaz sıfırlamalarında yeni uygulama paketlerinin kalıcılığıyla ilgili bir sorunu düzeltir.
- Japonca müşteriler için Edge'de yanlış sembollerin yaz 1994'e yaznarak neden olmasıyla ilgili bir sorun düzeltildi.
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

- Yerel bir hesap Ayarlar parola değiştirmeye çalışırken uygulamanın kilitlenmesi ile ilgili bir sorunu gidermek.


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

1.  Cihazınızın yönetilen olarak kabul edilen bir cihaz olduğundan emin olun
1.  HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1.  HoloLens 2 cihazında oturum HoloLens olun
1.  Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads dizinine kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1.  2 HoloLens Başlat Menüsünü açın, Başlat'ı Tüm uygulamalar seçin ve Dosya Gezgini açın.
1.  İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1.  yourapp.appxbundle dosyasını seçin.
1.  Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Örnekleri GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamaları bulabilirsiniz.

HoloLens [2'de uygulama yükleme](app-deploy-app-installer.md)işleminin tamamını Uygulama Yükleyicisi.  

![UYGULAMA YÜKLEYICISI aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek el ile yalnızca konum güncelleştirilirken diğer ortaklar önceki bir poza göre ertelenmektedir.  Bu değişiklik; tırslama, atma, kırpma ve kırpma gibi hareketlerde izleme tutarlılığının iyileştirilmesine yardımcı olur.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El birikleri vernilen zaman, [her bir ortak](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi
- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesini ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz teşvik ederiz.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2
- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve 2 kullanıcı ve BT HoloLens yeni özellikler sunar. Otomatik Göz Konumlandırmadan Sertifika Yöneticisi'ne Ayarlar Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine. Bu yeni güncelleştirme, IT ekiplerinin cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip HoloLens ve kullanıcılara daha sorunsuz holografik deneyimler sunar. 

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler ekllmektedir. Ana derleme numarası aynı kalır ve Windows Güncelleştirmesi 2004 (derleme 19041) sürümüne aylık bir sürümü gösteriyor. En son 19041.1128+ derlemesinde olduğunu onaylamak için Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. Güncelleştirmeleri yönetme hakkında daha fazla bilgi için HoloLens güncelleştirmelerini [yönetme HoloLens ziyaret edin.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic sürüm 20H2'daki yeniler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik Göz Konumu Desteği](hololens-release-notes.md#auto-eye-position-support) | Kullanıcıların Göz İzleme ayarına girmeden göz konumlarını etkin bir şekilde hesaplama.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Yeni basit yöntemlerin sertifika yükleme ve kaldırma yöntemlerinin Ayarlar sağlar.     |
| [USB'den sağlamayı otomatik başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerinde paketlerin sağlanması, otomatik olarak OOBE'de sağlama sayfasına sorılır.                                                         |
| [OOBE'de sağlama paketlerini otomatik onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve otomatik onaylamayı birlikte birleştirme. |
| [Autopilot'ı Wi-Fi kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısına gerek kalmadan Wi-Fi otomatik pilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlanır veya yeniden yanıp söner. |
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli olacak şekilde çoklu uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens Koşullarıdır](hololens-release-notes.md#hololens-policies)                                    | Yeni ilkeler HoloLens.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların belirli bir gün boyunca Çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz HoloLens ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Uygulamanın içinde hangi sayfaların görül Ayarlar.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2'de Araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikayı geçmeyecek. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

2 HoloLens de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve geliştirilmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcı cihazı bağlı olduğu andan itibaren otomatik olarak arka planda çalışmaya başlar. Kullanıcının daha önce göz izleme ayarı yoksa Otomatik Göz Konumu, 20 -30 saniyelik bir işlem süresi sonra kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve bu nedenle kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, bir kullanıcı daha önce cihazda göz izleme ayarlama işleminin üzerinden geçilen birini ifade eder.

| Etkin Uygulama | Önceki Davranış | Windows Holographic sürüm 20H2 Güncelleştirmesi'nin davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Bakışın etkinleştirilmemiş uygulaması veya Holographic Shell |Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | Hiçbir istem gösterilmez. |
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

bilgi noktası modu ' nda hatalarla karşılaşmadan önce, başlangıç menüsündeki tüm uygulamaları göstermek için HoloLens kullanılır. artık Windows Holographic sürüm 20h2 ' de, aşağıdaki gibi başlangıç menüsünde hiçbir uygulama gösterilmez: 

![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Elerindeki
- cihazı yönetmek için HoloLens özel olarak cihaz yönetimi seçenekleri. 

HoloLens 2 cihazları için yeni karma gerçeklik ilkeleri Windows Holographic version 20h2 ' de oluşturulmuştur. Yeni denetlenebilir ayarlar şunlardır: parlaklık ayarlanıyor, birim ayarlama, karma gerçeklik halinde ses kaydı devre dışı bırakma, tanılama toplandığında ayarlama ve AAD grup üyeliği önbelleği.  

| yeni HoloLens ilkesi                                | Açıklama                                                                               | Notlar                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Mixedreality\parlatnessbuttondisabled              | Parlaklık düğmelerinin devre dışı olmasına izin verir ve bu sayede parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı olmasına izin verir, böylece birim değişmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| Mixedreality\mikro phonedisabled                    | HoloLens 2 ' de ses kaydı mümkün olmayacak şekilde mikrofonu devre dışı bırakır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
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
1. Azure AD gruplarını hedefleyen bilgi noktası için bir cihaz yapılandırma profili oluşturun ve HoloLens cihazlara atayın. 
1. bu ilke değerini istenen gün sayısına (> 0) ayarlayan ve HoloLens cihazlara atayan özel bir OMA urı tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri, OMA-URI metin kutusunda./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilmelidir
    1. Değer, izin verilen Min/Max arasında olabilir.
1. HoloLens cihazları kaydedin ve her iki yapılandırmanın cihaza uygulandığını doğrulayın. 
1. Internet 'in kullanılabildiği Azure AD User 1 oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. artık Azure AD kullanıcı 1, HoloLens çevrimdışına alabilir ve ilke değeri X gün sayısı için izin verdiği sürece bilgi noktası modu için kullanabilir. 
1. 4 ve 5. adım, diğer tüm Azure AD kullanıcıları için yinelenebilir. burada anahtar noktası, herhangi bir Azure AD kullanıcısının Internet 'i kullanarak cihaza oturum açması gerekir. bu sayede, bilgi noktası yapılandırmasının hedeflediği Azure AD grubuna üye olduklarını belirleyebiliriz. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilene kadar "bağlantısı kesik" ortamlarda bahsedilen hata davranışı ile karşılaşırsınız. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri
- Kullanıcıların, sağlama paketleri ekleme veya kaldırma gibi belirli cihaz yönetim ilkelerini yönetmesine olanak tanır.

HoloLens 2 cihazların daha fazla yönetim seçeneklerine izin veren yeni etkinleştirilen ilkeler. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni ilke [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

> [!NOTE]
> [remotelock](/windows/client-management/mdm/remotelock-csp)ile ilgili olarak HoloLens yalnızca./vendor/msft/remotelock/lock yapılandırmasını destekler. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırma desteklenmez.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri
- HoloLens, güç ilkeleri aracılığıyla uyku moduna geçme veya kilitleme için daha fazla seçenek. 

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumlarını denetlemesine olanak tanır. Her ilke hakkında daha fazla bilgi edinmek için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [Displayofftimeoutonpili](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [Displayofftimeoutpluggedın](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [Enerji Gysaverbatteryıthresholdonpili](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                             |
|     [Enerji Gysaverbatteryıthresholdpluggedın](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                          |
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
  - *MRC video etkisi*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (modern kulaklık))
  - *MRC ses efekti* üzerinde:
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses **hatalarını** ortadan kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, bir web tarayıcısı geçersiz sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı, bu durumla ilgili ilerleme kaydedesiniz. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş girişlerinden tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- Piksel biçimlerini, HoloLens işleyicisinde siyah olarak işilecek şekilde değiştiren uygulamaların HoloLens düzeltildi.
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

[HoloLens 2 değerlendirme kılavuzunun Windows Autopilot'tan daha fazla bilgi edinin.](hololens2-autopilot.md)

*Şimdi AutoPilot önizlemeye katılmak için Hesap Yöneticinize ulaşın. Autopilot'a hazır cihazlar yakında gönderime başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar, HoloLens veya okul ortamındaki diğer kullanıcılarla bir cihaz paylaşır. Bu nedenle, kullanıcıların uzun kullanıcı adları ve parolalar yazmadan kolayca ulaşabiliyorları önemlidir. Fast Identity Online (FIDO), bir kullanıcı adı veya parola girmeden, kuruluşta (Azure AD kiracısı) HoloLens oturum açmasına olanak sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktöründe getirilebilir, standartlara dayalı bir parolasız kimlik doğrulama yöntemidir. FIDO, parolasız kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kaynaklarında kullanıcı adı veya parola olmadan oturum açmalarına olanak sağlar. Bunun yerine bir dış güvenlik anahtarı veya cihazda yerleşik olarak yer alan bir platform anahtarı kullanırlar.

Çalışmaya başlama için [bkz. Parolasız güvenlik anahtarı oturum açmasını etkinleştirme.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Paketleri sağlama, ilk HoloLens deneyimi yerine yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamaya izin sağlar. Daha önce, sağlama paketlerinin şirket içi belleğe HoloLens vardı. Artık bir USB sürücüde olabilir, böylece birden çok cihaz üzerinde daha kolay HoloLens cihazları paralel olarak silebilirsiniz. Paket sağlama artık cihaz yönetimine kaydolmak için bir alanı da desteklemektedir, bu nedenle sağlama sonrasında el ile kurulum yoktur.

Denemek için:

1. Windows Windows Configuration Designer'ın en son sürümünü Windows bilgisayarınıza indirin.
1. 2 **HoloLens Cihazları Sağlama**  >  **HoloLens'yi seçin.**
2. Yapılandırma profilinizi oluşturun. Ardından, oluşturulan tüm dosyaları bir USB-C depolama cihazına kopyalayın.
3. USB-C cihazını yeni yanıp sönen herhangi bir cihaza HoloLens. Ardından, sağlama **paketinizi**  +  **uygulamak** için güç düğmesine basın.

### <a name="line-of-business-application-install-status"></a>İş yeri uygulaması yükleme durumu

İş hattı uygulamaları için MDM uygulama dağıtımı ve yönetimi, uygulama yönetimi HoloLens. Yöneticilerin ve kullanıcıların denetim ve tanılama için uygulama yükleme durumunu görüntülemesi gerekir. Bu sürümde, hesap bilgilerinize Ayarlar veya okula erişim için daha fazla ayrıntı  >    >    >    >  **ekledik.**

### <a name="additional-csps-and-policies"></a>Ek CSP'ler ve ilkeler

Yapılandırma [hizmeti sağlayıcısı (CSP),](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu sürümde, yöneticilerin cihazlara dağıtılmış ve dağıtılmış denetimlerini artırmak için daha fazla ilkeye HoloLens ekleeceğiz. HoloLens tarafından desteklenen CSP'ler listesi için bkz. [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

Bu sürümde yeni olan:

**İlke CSP'si** 

İlke yapılandırma hizmeti sağlayıcısı, kuruluşa şirket dışı cihazlarda Windows sağlar. Bu sürümde, burada listelenen HoloLens yeni ilkeler ekledik. Daha fazla bilgi için [bkz. 2. HoloLens tarafından desteklenen İlke CSP'leri.](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

NetworkQoSPolicy yapılandırma hizmeti sağlayıcısı, ağ hizmet kalitesi (QoS) ilkeleri oluşturur. QoS ilkesi, bir dizi eşleşen koşulları temel alarak ağ trafiği üzerinde bir dizi eylem gerçekleştirir. Daha fazla bilgi için bkz. [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE bağlantısı olan cihazlar için genişletilmiş USB Ethernet desteği

5G/LTE telefonlar ve Wi-Fi etkin noktaları gibi belirli mobil geniş bant cihazlarının USB aracılığıyla HoloLens 2'ye bağlanarak etkin noktaları etkinleştirme desteği eklendi. Bu cihazlar artık ağ ayarlarında **başka bir** Ethernet bağlantısı olarak görüntülenir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmiyor.) Bu işlevsellik, Wi-Fi kullanılabilir değilse ve Wi-Fi yeterli performansa sahip değilse yüksek bant genişliğine sahip bağlantılar sağlar. Desteklenen USB cihazları hakkında daha fazla bilgi edinmek için [bkz. Bağlan ve USB-C Bluetooth'ye nasıl bağlanabilirsiniz?](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>El izleme geliştirmeleri

Bu sürüm çeşitli el izleme geliştirmeleri içerir:

- **Duruş kararlılığını işaret ediyor:** Sistem artık dizin tarafından gizliyken dizin parmaklarını bağlamaya karşı koyan bir sistemdir. Bu değişiklik düğmeleri itme, yazma, içerik kaydırma ve daha fazlasının doğruluğunu artırır! 
- **Yanlışlıkla havadan dokunma azaltıldı:** Havadan dokunma hareketi algılamasını iyileştirildi. Ellerinizi yanlarına bırakmanız gibi yaygın senaryolarda artık daha az sayıda yanlışlıkla etkinleştirme vardır.
- **Kullanıcı anahtarı güvenilirliği:** Artık bir cihazı paylaşırken el boyutunu güncelleştirme konusunda sistem daha hızlı ve daha güvenilirdir.
- **Azaltılmış el çalma:** Algılayıcıların görünümünde ikiden fazla el olduğu durumların işlenmesini iyileştirildi. Birden çok kişi birbirine yakın bir şekilde çalışıyorsa, artık takip edilen el kullanıcıdan sahnede başka birinin ele "atlayıp" atlama ihtimali çok daha düşüktür.
- **Sistem güvenilirliği:** Cihaz yüksek yük altındayken el izlemenin çalışmayı durdurmasına neden olan bir sorun düzeltildi.

### <a name="dark-mode"></a>Koyu mod

Birçok Windows artık hem koyu hem de açık modlarını destekler. HoloLens 2 kullanıcı, her ikisini de destekleyen uygulamalar için varsayılan modu seçebilir. Güncelleştirmeden sonra varsayılan uygulama modu "koyu" olur, ancak bu ayarı kolayca değiştirebilirsiniz: Sistem **Renkleri'ne Ayarlar**  >    >    >  **Varsayılan uygulama modunu seçin.** 

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

![Koyu mod pencereleri kutucuklı](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Sistem ses komutları

Artık cihazda herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için [bkz. Seslerinizi kullanarak HoloLens.](hololens-cortana.md) Ayrıca [bkz. HoloLens 2 için desteklenen diller.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

Güncelleştirilmiş uygulama, cihazlarınız arasında Microsoft 365 (şu anda yalnızca US-English) yardımcı olmak için US-English tümleştirilmiştir. 2 HoloLens de, Cortana ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklemez. Bu seçenekler artık yeni sistem ses komutları tarafından de desteklemektedir. Yeni uygulama hakkında daha fazla Cortana blog sayfamızı [ziyaret edin.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Kalite geliştirmeleri ve düzeltmeleri

Güncelleştirmede de iyileştirmeler ve düzeltmeler:  
- Etkin bir ekran ayarlama sistemi tanıtıldı. Bu özellik hologramların kararlılığını ve hizalamasını artırır. Artık kafanızı yan yana taşımış olurken bunlar yerinde kalır.
- Wi-Fi akışın düzenli HoloLens kesintiye neden olduğu bir hata düzeltildi. Bir uygulama düşük gecikmeli akış gerektiğini gösteriyorsa, [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)işlevini çağırarak düzeltmeyi gerçekleştirin.
- Araştırma modunda akış sırasında bir cihazın askıda kalma süresi düzeltildi.
- Bazı durumlarda oturum devam edince oturum açma ekranında doğru kullanıcının görüntülenmey on the bug düzeltildi.
- Kullanıcıların MDM günlüklerini Ayarlar aracılığıyla dışarı **aktaramama sorunu düzeltildi.**
- İlk kurulumdan hemen sonra göz izleme doğruluğunun beklenenden daha düşük olduğu bir sorun düzeltildi.
- Göz izleme alt sisteminin belirli koşullar altında ayarlama işlemini başlatamadığı veya gerçekleştiramadığı bir sorun düzeltildi.
- Önceden ayarlanmış bir kullanıcı için göz düzeltmesi istendiğinde bir sorun düzeltildi.
- Bir sürücünün göz ayarı sırasında kilitlenmesi sorunu düzeltildi.
- Yinelenen güç düğmesi basmalarının 60 saniyelik sistem zaman aşımına ve kabuk kilitlenmeye neden olduğu bir sorun düzeltildi.
- Derinlik arabellekleri için geliştirilmiş kararlılık.
- Kullanıcıların geri **bildirimi** daha kolay paylaş Geri Bildirim Merkezi için paylaşıma bir Paylaş düğmesi eklendi.
- RoboRaid wan'ın düzgün yüklenmemiş olmasıyla ilgili bir hata düzeltildi.

### <a name="known-issues"></a>Bilinen sorunlar

- zh-CN sistem diliyle ilgili bir sorun ses komutlarının karma gerçeklik yakalamasını veya cihaz IP adresini görüntülemesini önlemektedir.
- Bir sorun, cihazı "Hey Cortana" ses etkinleştirmeyi kullanmak üzere başlattıktan sonra Cortana başlatmanız gerekir. Bir 18362 derlemesinde güncelleştirme yaptıysanız, Cortana uygulamasının önceki sürümü için Başlat'ta artık çalışmayan ikinci bir uygulama kutucuğu **da görüntüleniyor olabilir.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, sürüm 1903 - Mayıs 2020 Güncelleştirmesi 
- Derleme 18362.1061

Bu aylık kalite güncelleştirmesi, ekip daha önce açıklandığı gibi Windows Holographic sürüm 2004 Mayıs Güncelleştirmesi üzerinde çalıştığı için önemli bir değişiklik içermemektedir.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, sürüm 1903 - Nisan 2020 Güncelleştirmesi
- Derleme 18362.1059

**Desteklenen uygulamalar için koyu mod** 

Birçok Windows hem koyu hem de açık modu destekler. HoloLens 2 müşteri artık her iki renk düzenini de destekleyen uygulamalar için varsayılan modu seçebilir. Müşteri geri bildirimlerine dayanarak varsayılan uygulama modunu "koyu" olarak ayarlamış oluruz ancak bu ayarı istediğiniz zaman kolayca değiştirebilirsiniz: "Varsayılan uygulama modunu seçin" için **Ayarlar > System > Colors'a** **gidin.**

Bu "in-box" uygulamaları koyu modu destekler:
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
