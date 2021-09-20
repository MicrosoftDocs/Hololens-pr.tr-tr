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
ms.date: 9/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f9d012540cf29b7ed7ffd4033681c58767d78db
ms.sourcegitcommit: e8a4714c7b16720819c7aaebefb7cfd21fc29c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2021
ms.locfileid: "127985639"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarınızla üretken bir deneyiminizin olduğundan emin olmak için özellik, hata ve güvenlik güncelleştirmelerini serbest bırakmaya devam ediyoruz. bu sayfada, her ay HoloLens yenilikleri görebilirsiniz. en son HoloLens 2 güncelleştirmesini almak için güncelleştirmeleri denetleyebilir ve [gelişmiş kurtarma yardımcısı aracılığıyla cihazınızı flash](hololens-recovery.md#clean-reflash-the-device) [ile el ile güncelleştirebilir](hololens-update-hololens.md#check-for-updates-and-manually-update) veya tam flash güncelleştirmesi (ffu) alabilirsiniz. [İndirme](https://aka.ms/hololens2download) güncel tutulur ve en son genel kullanıma sunulan derlemeyi sağlar.

> [!NOTE]
> son Windows 11 duyurusu, Windows bilgisayar sürümüne odaklanmıştı. kısa süre önce 2021 mayıs ' de HoloLens 2 ' ye [büyük bir işletim sistemi güncelleştirmesi](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) başlattık ve bu fall için müşteri geri bildirimlerine bağlı olarak yaklaşan bir sürüm üzerinde çalışıyoruz.

> [!IMPORTANT]
> [21 h1 deremizdeki, uzaktan yardım kullanıcılarını etkileyen bilinen bir sorun](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)nedeniyle, Windows Holographic, sürüm 21h1 güncelleştirmelerinin sunumunu zamana bağlı duraklattık. ayrıca, varsayılan gelişmiş kurtarma yardımcısı (ARC) derlemesini [Windows Holographic, sürüm 20h2 – haziran 2021 güncelleştirmesine](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)değiştirdik. Şimdi yay derlemesi, 21H1 derlemesini hedeflemeyi sürdürecek.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, sürüm 21H1-Eylül 2021 güncelleştirmesi

- Derleme 20348,1018

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem saatinin beklenmedik şekilde geçebileceği sorunu gidermeye yönelik düzeltmeler.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, sürüm 20H2-Eylül 2021 güncelleştirmesi

- Derleme 19041,1165

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem saatinin beklenmedik şekilde geçebileceği sorunu gidermeye yönelik düzeltmeler.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, sürüm 21H1-Ağustos 2021 güncelleştirmesi

- Derleme 20348,1014

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Xbox denetleyicilerinin, denetleyici desteğiyle Modern uygulamalarda çalışmasını engelleyen bir sorun düzeltildi.
- Cihaz güncelleştirme hatalarıyla ilgili tanılama geliştirildi.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, sürüm 20H2-Ağustos 2021 güncelleştirmesi

- Derleme 19041,1161

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows Holographic, sürüm 21h1 olan en son derlemeyi denemenizi öneririz.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1-Temmuz 2021 güncelleştirmesi

- Derleme 20348,1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Dosya Gezgini kilitli dosyaları açarken sorunlarla karşılaştığında, cihaz portalı, müşteriye bildirimde bulunmak için geliştirilmiş yöntemlere sahiptir.
- Dosya yükleme, indirme, yeniden adlandırma ve silme artık desteklenen tüm tarayıcılarda https kullanılırken düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi **Ayarlar > ağ & Internet > durum > özelliklerinden** başlatıldığında Wi-Fi proxy 'nin kaydedilebileceği sorun düzeltildi.
- Esım sertifikalarının işletim sistemi güncelleştirmeleri üzerinde kaldırılmasına yönelik bir sorun oluştu. Bu çözüm, 21 H1 sürümüne güncelleştirme yaparken esım sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- İşletim sistemi sıfırlamaları üzerinde önceden yüklenmiş uygulamaları etkileyen bir sorun düzeltildi.
- Artan CPU yüklemesiyle ücretlendirmesi sırasında çalışma zamanını artırmak için pil şarj performansı ayarlandı. HoloLens 2 cihaz şarj edilirken, cihazın sık çalıştığı algılanırsa, iç pil, ısı azaltmayı daha yavaş ücretlendirir. Pozitif zorunluluğunu getirir, bir cihazın ısı sorunları nedeniyle kapanmasına daha az olma olasılığı vardır ve bu da cihazın daha uzun süre çalışmasına neden olur. Cihaz seyrek erişimli çalışıyorsa, ücretlendirme ücreti etkilenmez.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – 2021 Temmuz güncelleştirmesi

- Derleme 19041,1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Dosya Gezgini kilitli dosyaları açarken sorunlarla karşılaştığında, cihaz portalı, müşteriye bildirimde bulunmak için geliştirilmiş yöntemlere sahiptir.
- Dosya yükleme, indirme, yeniden adlandırma ve silme artık desteklenen tüm tarayıcılarda https kullanılırken düzeltildi.

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
>
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

![eski Microsoft Edge logosunun yeni Microsoft Edge logoa animasyonu.](images/new-edge.gif)

yeni Microsoft Edge, müşteriler için daha iyi uyumluluk ve web geliştiricileri için web 'in daha az parçalanması oluşturmak üzere [Chromium açık kaynaklı projeyi benimsemektedir](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) .

> [!IMPORTANT]
> bu yeni Microsoft Edge, yeni sürümlerde [artık desteklenmeyen](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) eski Microsoft Edge otomatik olarak değiştirir.

![yeni Microsoft Edge ekran görüntüsü.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni Microsoft Edge başlatılıyor

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi.](images/new_edge_logo.png) (mavi ve yeşil girdap simgesiyle gösterilir) Başlat menüsü sabitlenmiştir ve bir web bağlantısını etkinleştirdiğinizde otomatik olarak başlatılır.

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
>
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
>
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

tek bir uygulamanın hacmini ayarlamak için **Ayarlar**  >  **sistem**  >  **sesi**' ne gidin ve gelişmiş ses seçenekleri altında **uygulama birimi ve cihaz tercihleri**' ni seçin.<br/><br/>

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

**Ayarlar**  >  **sistem**  >  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.

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

bt yöneticilerinin yönetebileceği kullanılabilir Ayarlar urı 'leri listesini genişlettik. bu urı 'lerden bazıları yeni Ayarlar uygulamasındaki yeni kullanılabilir alanlara yöneliktir. Ayarlar/pagevisibilitylist ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

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

artık Ayarlar uygulamada, bir kullanıcı [geri dönüş tanılamaları](hololens-diagnostic-logs.md)davranışını yapılandırabilir. Ayarlar uygulama,   >  bu ayarı yapılandırmak için gizlilik **sorunlarını giderme** sayfasına gidin.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, Kullanıcı bu davranışı geçersiz kılayamaz.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla şeyleri paylaşma

hem bilgisayarlar hem de diğer HoloLens 2 cihazları dahil olmak üzere Windows 10 cihazları ile neredeyse her şeyi paylaşabilirsiniz.   >    >  dosya veya url 'leri bir bilgisayara HoloLens paylaşmak için Ayarlar sistem **paylaşılan deneyimleriyle** deneyebilirsiniz. Daha fazla ayrıntı için [Windows 10 ' de Yakındaki cihazlarla şeyler paylaşma](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)hakkında daha fazla bilgi edinin.

Bu özellik, [bağlantı/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)aracılığıyla yönetilebilir.

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmelerine yönelik yeni Ayarlar uygulamasının eklenmesiyle birlikte yeni bir sorun giderici eklenmiştir. **Ayarlar**  >  **güncelleştirme &amp; güvenliği**  >  **sorun giderme**  >  **Windows Update** gidin ve **başlat**' ı seçin. Bu, BT veya destek ile ilgili sorun giderme konusunda daha iyi yardımcı olması için işletim sistemi güncelleştirmeleriyle ilgili sorunları yeniden oluştururken izlemeleri toplamanıza olanak tanır.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

bu HoloLens güncelleştirme ile, Windows Holographic for Business birden çok HoloLens cihazdan indirilen bant genişliği tüketimini azaltmak için teslim iyileştirme ayarlarının kullanılmasına olanak sağlar. önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri için teslim iyileştirmesi](/windows/deployment/update/waas-delivery-optimization).

Aşağıdaki ayarlar yönetim yüzeyi kapsamında etkinleştirilmiştir ve [Intune 'dan yapılandırılabilir](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [Dodelaycacheserverfallbackönalanı](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarılar:

- HoloLens desteği, bu önizlemede yalnızca işletim sistemi güncelleştirmeleri için sınırlıdır.
- Windows Holographic for Business yalnızca [Microsoft bağlı önbellek uç noktasından](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)HTTP indirme modlarını ve indirmeleri destekler; şu anda HoloLens cihazlarda eşler arası indirme modları ve grup atamaları desteklenmez.
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
- Çalışma zamanı sağlama paketleri aracılığıyla iş kolu uygulamalarının dağıtımıyla ilgili bir sorunu düzeltir.
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

### <a name="install-apps-on-hololens-2-via-app-installer"></a>HoloLens 2'de uygulamaları Uygulama Yükleyicisi

Uygulamaları 2 **cihaza daha sorunsuz Uygulama Yükleyicisi sağlamak için** yeni bir özellik (HoloLens) ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazları için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:

- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin (USB üzerinden veya Edge üzerinden) cihazınıza indirerek yüklemenin Dosya Gezgini appx paketine gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğu gibi, uygulamaların [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) da İmza [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) Aracı ile dijital olarak imzalanacak olması ve uygulamanın dağıtılablan önce HoloLens cihazı tarafından güvenilir olması gerekir.

**Uygulama yükleme yönergeleri.**

1. Cihazınızın yönetilen olarak kabul edilen bir şey olduğundan emin olun
1. HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1. HoloLens 2 cihazında oturum HoloLens olun
1. Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads dizinine kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1. 2 HoloLens Başlat Menüsünü açın, Başlat'ı Tüm uygulamalar seçin ve Dosya Gezgini açın.
1. İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1. yourapp.appxbundle dosyasını seçin.
1. Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Evrensel GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamaları bulabilirsiniz.

Uygulama Yükleyicisi ile HoloLens [2'ye uygulama yükleme işleminin tam Uygulama Yükleyicisi.](app-deploy-app-installer.md)  

![Uygulama Yükleyicisi aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek el ile yalnızca konum güncelleştirilirken diğer ortaklar önceki bir poza göre ertelenmektedir.  Bu değişiklik, hareketlerde takip tutarlılığını artırmaya yardımcı olur; örneğin, kırpma, atma, kırpma ve kırpma.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El joint'ler inferred olduğunda, her [bir ortak](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi

- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesini ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz teşvik ederiz.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2

- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve 2 kullanıcı ve BT HoloLens yeni özelliklerle harika bir dizi yeni özellik sunar. Otomatik Göz Konumlandırmadan Sertifika Yöneticisi'ne Ayarlar Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine. Bu yeni güncelleştirme, IT ekiplerinin cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip HoloLens ve kullanıcılara daha sorunsuz holografik deneyimler sunmaktadır.

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler eklmektedir. Ana derleme numarası aynı kalır ve Windows Update 2004 (derleme 19041) sürümüne aylık bir sürümü gösteriyor. Kullanılabilir en son derleme olan 19041.1128+'Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. Güncelleştirmeleri yönetme hakkında daha fazla bilgi için HoloLens güncelleştirmelerini [yönetme HoloLens ziyaret edin.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic sürüm 20H2'daki yeniler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik Göz Konumu Desteği](hololens-release-notes.md#auto-eye-position-support) | Kullanıcıların Göz İzleme ayarına girmeden göz konumlarını etkin bir şekilde hesaplama.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Yeni basit yöntemlerin sertifika yükleme ve uygulamadan sertifika kaldırma Ayarlar sağlar.     |
| [USB'den sağlamayı otomatik başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerinde paketlerin sağlanması, otomatik olarak OOBE'de sağlama sayfasına sorılır.                                                         |
| [OOBE'de sağlama paketlerini otomatik olarak onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve otomatik onaylamayı birlikte birleştirme. |
| [Autopilot'ı Wi-Fi kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısına gerek kalmadan Wi-Fi otomatik pilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlanır veya yeniden yanıp söner. |
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli hale gelen birden çok uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens Koşullarıdır](hololens-release-notes.md#hololens-policies)                                    | Yeni ilkeler HoloLens.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların kaç gün boyunca çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz yönetimi ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Uygulama içinde hangi sayfaların görül Ayarlar.             |
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

- **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığını doğrulama veya uygun şekilde kaldırıldığını doğrulama özelliği.
- **Tanılama:** Sorun ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulamak zaman kazandırır ve sorun gidermeye yardımcı olur.
- **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğu doğrulanıyor, özellikle de daha büyük ölçekte sertifika dağıtmadan önce ticari ortamlarda önemli bir zaman kazandırabilir.

Listedeki belirli bir sertifikayı hızlı bir şekilde bulmak için ada, depoya veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar ayrıca bir sertifikayı doğrudan arayabilir. Ayrı sertifika özelliklerini görüntülemek için sertifikayı seçin ve **bilgi**'ye tıklayın.

Sertifika yüklemesi şu anda. cer ve. CRT dosyalarını desteklemektedir. Cihaz sahipleri, sertifikaları yerel makineye ve geçerli kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca geçerli kullanıcıya yüklenebilir. kullanıcılar yalnızca Ayarlar kullanıcı arabiriminden doğrudan yüklenmiş sertifikaları kaldırabilir. Bir sertifika başka yollarla yüklendiyse aynı mekanizmaya de kaldırılmalıdır.

#### <a name="steps-to-install-a-certificate"></a>Sertifika yüklemek için gereken adımlar

1. HoloLens 2 ' 'nizi bir bilgisayara Bağlan.
1. yüklemek istediğiniz sertifika dosyasını HoloLens 2 ' deki bir konuma yerleştirin.
1. **Ayarlar App > Update & güvenlik > sertifikaları**' na gidin ve sertifika yüklemeyi seçin.
1. **Dosyayı Içeri aktar** ' a tıklayın ve sertifikayı kaydettiğiniz konuma gidin.
1. **Depo konumunu** seçin.
1. **Sertifika deposunu** seçin.
1. **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklü olması gerekir.

#### <a name="steps-to-remove-a-certificate"></a>Sertifikayı kaldırma adımları

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

Bu sürümden önce, kullanıcıların bir düğme birleşimi kullanarak sağlaması için, OOBE sırasında sağlama ekranını el ile başlatması gerekiyordu. Artık kullanıcılar, USB depolama sürücüsünde bir sağlama paketi kullanarak düğme bileşimini atlayabilir.

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

- Cihaz sıfırlama veya refflash aracılığıyla bile, cihazı kiracıya kilitleyerek kuruluşun kiracısındaki cihazları tutar. Sağlama yoluyla içinde hesap oluşturulmasına izin ve daha fazla güvenlikle.

HoloLens 2 cihaz artık [Holographic sürüm 20H2 Windows TenantLockdown CSP'yi desteklemektedir.](hololens-release-notes.md#windows-holographic-version-20h2)

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasına olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değerine ayarlandıktan sonra, bu değer yeniden yanıp sönmeye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

HoloLens 2'de TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü true olarak ayarlandıktan sonra OOBE, Autopilot profilinin ağ bağlantısı sonrasında başarıyla indirilme ve uygulanması için süresiz olarak bekler.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE'de aşağıdaki işlemlere izin verilmiyor:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme
- OOBE deneyiminde cihazın sahibini seçme

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır?

1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama.](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır?

1. Yukarıda HoloLens 2'nin daha önce atandığı cihaz yapılandırmasının atandığı cihaz grubundan 2. kümeyi kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü.](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır.

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

- Cihaz yönetimi seçenekleri HoloLens için özel olarak oluşturulur.

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

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılaca lı olduğunu kontrol eder. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi takdirde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün

Bu ilkeyi doğru kullanma adımları:

1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın.
1. Bu ilke değerini istenen gün sayısına (> 0) ayar alan ve bu değeri HoloLens cihaza atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun.
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

- Güç ilkeleri aracılığıyla uyku HoloLens veya kilitlerken daha fazla seçenek.

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
> 2. HoloLens tutarlı bir deneyim için, hem DisplayOffTimeoutOnBattery hem de StandbyTimeoutOnBattery değerlerinin aynı değer olarak ayarlanmış olduğundan emin olun. Aynı durum DisplayOffTimeoutPluggedIn ve StandbyTimeoutPluggedIn için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için Bkz. Boşta kalma [süreölçilerini](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) görüntüleme, uyku ve hazırda bekletme.

### <a name="newly-enabled-update-policies-for-hololens"></a>Yeni etkinleştirilen Güncelleştirme ilkeleri HoloLens

- Güncelleştirmelerin ne zaman yük devre dışı bırakıldığında veya güncelleştirmeleri sağlamak için Güncelleştirmeleri Duraklat düğmesinin devre dışı bırakılmasına yönelik diğer seçenekler.

Bu güncelleştirme ilkeleri artık 2 HoloLens etkinleştirildi:

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Bu güncelleştirme ilkeleriyle ilgili tüm ayrıntılar ve bu ilkelerin HoloLens cihazlar için nasıl kullanacağız? [güncelleştirmelerini yönetme HoloLens okuyabilirsiniz.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi

- Ayarlar Uygulamasında artan kullanıcı arabirimi denetimi, sınırlı sayıda sayfa göstermek için karıştırılabilir.

Artık, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkeyi etkinleştirmiş olduk. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

2. sayfada hangi sayfa ayarlarını özelleştirebileceğinizi HoloLens için lütfen Ayarlar [sayfasını ziyaret edin.](settings-uri-list.md)

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu

Araştırma Modundayken, HoloLens 2, görüntü görme araştırmalarında önemli bir araç haline gelir. Önceki sürümlere kıyasla, HoloLens 2 için Araştırma Modu aşağıdaki avantajlara sahiptir:

- HoloLens (1. Nesil) Araştırma Modu'nun kullanımına açık algılayıcılara ek olarak artık bir ivmeölçer, jiroscope ve ölçer dahil olmak üzere IMU algılayıcı erişimi de sağlarsınız.
- HoloLens 2, Araştırma Modu ile birlikte kullanılan yeni özellikler sağlar. Özellikle, daha zengin bir deneme kümesi sunan, ifade edilebilir el izleme ve göz izleme API'lerine erişim.

Araştırmacılar artık kendi cihazlarında Araştırma Modu'HoloLens dışta çalışan ham görüntü algılayıcılarının akışlarına erişmesini etkinleştirme seçeneğine sahip. HoloLens 2 için Araştırma Modu, ivmeölçer, jiroscope ve ölçer okumalarına da erişim sağlar. Kullanıcıların gizliliğini korumak için, araştırma modu aracılığıyla ham göz izleme kamera görüntüleri kullanılamaz, ancak mevcut API'ler aracılığıyla göz bakışı yönü kullanılabilir.

Diğer teknik ayrıntılar [için Araştırma Modu](/windows/mixed-reality/research-mode) belgelerine göz atabilirsiniz.

### <a name="recording-length-increased"></a>Kayıt uzunluğu artırıldı

Müşteri geri bildirimi nedeniyle karma gerçeklik yakalamalarının [kayıt uzunluğunu artırıldı.](holographic-photos-and-videos.md) Karma gerçeklik yakalamaları artık varsayılan olarak 5 dakikayla sınırlı olmayacak, bunun yerine kullanılabilir disk alanı temel alarak maksimum kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanını %80'e kadar olan kullanılabilir disk alanını temel alarak maksimum video kayıt süresini tahmin eder.

> [!NOTE]
> Aşağıdaki HoloLens biri gerçekleşirse varsayılan video kayıt uzunluğunu (5 dakika) kullanır:
>
> - Tahmini maksimum kayıt süresi, varsayılan 5 dakikadan küçüktür.
> - Kullanılabilir disk alanı toplam disk alanı %20'den azdır.

Holografik fotoğraflar ve videolar [belgemizde tüm gereksinimleri bulabilirsiniz.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Windows Holographic sürüm 20H2 güncelleştirmesinde iyileştirmeler ve düzeltmeler:

- OOBE'de daha fazla ekran artık koyu moddadır.
- Daha fazla bilgi edinmek için çevrimiçi olarak en son Gizlilik Bildirimi'ne işaret edin.
- Kullanıcıların sağlama paketleri aracılığıyla VPN profilleri sağlamama sorunu giderildi.
- VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi.
- İlke, AllowUsbConnection için NCM için MDM aracılığıyla USB işlevlerinin numaralandırıcısını devre dışı bırakmak için güncelleştirildi.
- Tek uygulamalı bilgi noktası HoloLens bir Dosya Gezgini Medya Aktarım Protokolü (MTP) üzerinden bir HoloLens cihazın medyada göstermesini engelleyen bir [sorun giderildi.](hololens-kiosk.md) MTP 'nin (ve genel olarak USB bağlantısının) [AllowUSBConnection ilkesi](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) kullanılarak devre dışı bırakılabilir olduğunu unutmayın.
- Başlat menüsü simgelerin Bilgi Noktası modunda doğru ölçeklendirilmiş olduğu bir sorun düzeltildi.
- HTTP önbelleğinin Azure AD gruplarına hedeflenen bilgi noktası moduyla engellemesi nedeniyle bir sorun düzeltildi.
- Kullanıcıların Geliştirici modunu devre dışı bırakarak geliştirici modunu yeniden etkinleştirmediği sürece paket sağlama ile Geliştirici modunu etkinleştirdikten sonra Eşleştir düğmesini kullanamadığı bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, sürüm 1903 - Kasım 2020 Güncelleştirmesi

- Derleme 18362.1085

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 20H2'de en son özellik sürümü Windows denemeniz gerekir.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, sürüm 2004 - Ekim 2020 Güncelleştirmesi

- Derleme 19041.1124

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çalışma zamanı sistem hatasına neden olan gereksiz bir denetim kaldırıldı.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, sürüm 1903 - Ekim 2020 Güncelleştirmesi

- Derleme 18362.1081

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, sürüm 2004 - Eylül 2020 Güncelleştirmesi

- Derleme 19041.1117

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Appxmanifest'Visual Studio SupportsMultipleInstances="true" olduğunda uygulamanın hata ayıklamasını engelleyen bir sorunu giderin.
- Bu sürüm, ağ ara sunucusu üzerinden başarısız İnternet algılamayı ele alan NCSI proxy algılama düzeltmesi içerir. NCSI, İnternet bağlantısı algılama için makine ara sunucusunu ve profil başına ara sunucu kullanabilir. Kullanıcı başına ara sunucu, gelecek sürümlerde NCSI tarafından desteklenecegizli olacak.
- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağıya doğru eğiktir. Daha yeni HoloLens 2, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
- Belirli senaryolarda daha az izleme kaybıyla sonuçlanacak gelişmiş el izleme sağlamlığı.
- Bu sürüm, video yakalama sorunlarına katkıda bulunarak ses zaman damgası kalitesini geliştirmeye ilişkin bir düzeltme içerir.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, sürüm 1903 - Eylül 2020 Güncelleştirmesi

- Derleme 18362.1079

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağıya doğru eğiktir. Daha yeni HoloLens 2, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
- Belirli senaryolarda daha az izleme kaybıyla sonuçlanacak gelişmiş el izleme sağlamlığı.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, sürüm 2004 - Ağustos 2020 Güncelleştirmesi

- Derleme 19041.1113

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Ayarlar uygulama artık Iris Kaydı veya Göz İzleme Ayarlama deneyimlerine kullanıcıdan takip etmemektedir.
- OOBE sırasında cihazı yeniden adlandıran ve diğer eylemleri (ağa bağlanma gibi) gerçekleştiren sağlama paketinin yeniden adlandırma nedeniyle cihaz yeniden başlatıldıktan sonra diğer eylemleri gerçekleştirememe hatası düzeltildi.
- Görsel kalitesini geliştirmek için ilk cihaz kurulumu akışlarının renk düzeni değiştirildi.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, sürüm 1903 - Ağustos 2020 Güncelleştirmesi

- Derleme 18362.1074

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, sürüm 2004 - Temmuz 2020 Güncelleştirmesi

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
- **Ayarlar**  >  **sistem**  >  **Hologramlar** bir ayar, kullanıcıların cihaz kapandığında karma gerçeklik ana 'dan tüm hologramlar otomatik olarak kaldırılmasına olanak sağlar.
- HoloLens öykünücüsünde siyah işlemek için piksel biçimini değiştiren HoloLens uygulamalara neden olan bir sorun düzeltildi.
- Iris oturum açma sırasında kilitlenmeye neden olan bir hata düzeltildi.
- Zaten mevcut uygulamalar için yinelenen mağaza indirmeleri hakkında bir sorun düzeltildi.
- modern uygulamaların Microsoft Edge tekrar tekrar açmasını önleyen bir hata düzeltildi.
- 1903 sürümünden güncelleştirmeden sonra ilk önyüklemesinde Fotoğraflar uygulamasının başlatıldığında bir sorun düzeltildi.
- İyileştirilmiş performans ve güvenilirlik.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, sürüm 1903-Haziran 2020 güncelleştirme

- Derleme 18362,1064

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydediciler belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC video etkisi*:
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1,0 (modern kulaklık))
  - *MRC ses efekti* üzerinde:
    - loopgeri kazanç (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "uygulama sesi kazancı" değeri)
    - mikro phonekazancı (Windows cihaz portalındaki karma gerçeklik yakalama sayfasındaki geçerli "mıc ses kazancı" değeri)
- HolographicSpace. Uservarlığına yönelik API genellikle Unity uygulamaları için devre dışıdır. Bu davranış, arka planda çalıştırılacak ayar etkin olsa bile, bazı uygulamaların, vizörü çevrilirse duraklamasına neden olan bir sorunu önler. Artık, 2018.4.18 ve üzeri, 2019.3.4 ve üzeri Unity sürümleri için API etkinleştirilmiştir.
- piksel biçimini değiştiren HoloLens uygulamaların HoloLens Emulator siyah olarak işlemesini neden olan bir sorun düzeltildi.
- 1903 sürümünden güncelleştirmeden sonra ilk önyüklemeler bölümünde Fotoğraflar uygulamasının ortaya çıkmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, sürüm 2004

- Derleme-19041,1103

HoloLens 2, *Windows Holographic, sürüm 2004* için mayıs 2020 ana yazılım güncelleştirmesi, Windows Autopilot, uygulama koyu modu, 5 g/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası için destek gibi heyecan verici yeni yetenekler içeren bir konak içerir. en son sürüme güncelleştirmek için **Ayarlar**   uygulamasını açın, **güncelleştirme & güvenlik**' e gidin ve  **güncelleştirmeleri denetle**   düğmesini seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak üretim için yeni cihazları önceden yapılandırın ve sorunsuz bir şekilde ayarlayın                 |
|       FıDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamayı etkinleştirmek üzere FIDO2 güvenlik anahtarlarına yönelik destek            |
|       Geliştirilmiş sağlama                      |          Bir USB sürücüsünden HoloLens sağlama paketini sorunsuz bir şekilde uygulama                              |
|       Uygulama yüklemesi durumu                 |          uygulamalar için Ayarlar uygulama, MDM aracılığıyla HoloLens 2 ' ye gönderildi               |
|       Yapılandırma hizmeti sağlayıcıları (CSP)   |          Yönetici denetim yeteneklerini iyileştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği, 5G/LTE desteğini sunar                                    |
|       Koyu uygulama modu                              |          Koyu ve hafif modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir, görüntüleme deneyimini geliştirir        |
|       Sesli komutlar                             |          HoloLens eller denetlemek için ek sistem ses komutları desteği                           |
|       İzleme geliştirmeleri                 |          İzleme geliştirmeleri, düğmeleri ve 2B kurşun etkileşimini daha doğru hale getirir                        |
|       Kalite iyileştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik iyileştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot için destek

Windows HoloLens 2 için Autopilot, cihaz satış kanalının ıntune kiracınıza HoloLens önceden kaydolmasına olanak tanır. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazırsınız demektir. Self-Deployment 'ın avantajlarından yararlanmak için, cihazın bir USB-C-Ethernet kullanarak kurulum 'daki ilk ekran sırasında ağa bağlanması gerekir.

Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin.
1. cihazı Microsoft Intune (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.
1. Cihaza yönelik ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlayın.
1. Kullanıcıya oturum açma ekranını sunun.

[Windows Autopilot for HoloLens 2 değerlendirme kılavuzunda](hololens2-autopilot.md)daha fazla bilgi edinin.

*AutoPilot önizlemesini şimdi katmak için hesap yöneticinize başvurun. Autopilot için kullanıma sunulan cihazlar yakında gönderim yapmaya başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

bazı kullanıcılar bir HoloLens cihazını iş veya okul ortamında başkalarıyla paylaşır. Bu nedenle, kullanıcıların uzun Kullanıcı adlarını ve parolalarını yazmadan kolayca kolayca olanak sağlamak önemlidir. hızlı kimlik çevrimiçi (fido), kuruluşunuzdaki herkesin (Azure AD kiracısı) kullanıcı adı veya parola girmeden HoloLens sorunsuzca oturum açmasını sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktörüyle gelebilmesi için bir "unphishable" standartlara dayalı bir kimlik doğrulama yöntemidir. FıDO, passwordless kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kendi kaynaklarında Kullanıcı adı veya parola olmadan oturum açmasına olanak tanır. Bunun yerine, bir dış güvenlik anahtarı veya bir cihazda yerleşik bir platform anahtarı kullanırlar.

Başlamak için bkz. [passwordless güvenlik anahtarı oturum açma 'Yı etkinleştirme](/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

sağlama paketleri, HoloLens kullanıma hazır deneyim yerine bir yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamanıza olanak sağlar. daha önce, sağlama paketlerinin HoloLens iç belleğe kopyalanması gerekiyordu. artık bir USB sürücüde olabilir, böylece birden çok HoloLens cihazda yeniden kullanmak daha kolay hale getiriyoruz ve cihazları paralel olarak sağlayabilirsiniz. Sağlama paketleri artık cihaz yönetimine kaydolmak için bir alanı destekledikten sonra, sağlamadan sonra el ile kurulum gerektirmez.

Denemek için:

1. Windows Configuration Designer 'ın en son sürümünü Windows mağazasından bilgisayarınıza indirin.
1. **HoloLens sağla**' yı seçin  >  **HoloLens 2 cihaz sağlayın**.
1. Yapılandırma profilinizi oluşturun. Ardından, bir USB-C depolama cihazına oluşturulan tüm dosyaları kopyalayın.
1. USB-C cihazını herhangi bir yeniden flaşla HoloLens bağlayın. Ardından,   +  sağlama paketinizi uygulamak için ses **tasarrufu** düğmelerine basın.

### <a name="line-of-business-application-install-status"></a>İş kolu uygulaması yüklemesi durumu

İş kolu uygulamaları için MDM uygulama dağıtımı ve yönetimi HoloLens için önemlidir. Yöneticiler ve kullanıcıların, denetim ve Tanılama için uygulama yüklemesi durumunu görüntülemesi gerekir. bu sürümde, **Ayarlar**  >  **hesaplarına**  >  **erişim iş veya okul**  >  **hesabına hesap**  >  **bilgilerinize** tıkladığımızda daha fazla ayrıntı ekledik.

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
