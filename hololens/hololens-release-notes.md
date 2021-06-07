---
title: HoloLens 2 sürüm notları
description: Yeni HoloLens 2 yayınlarının tüm güncelleştirmelerini takip edin.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379120"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarında üretken bir deneyim yaşamanızı sağlamak için özellik, hata ve güvenlik güncelleştirmelerini yayınlaya devam edeceğiz. Bu sayfada HoloLens'in her ayki yenilerini görebilirsiniz. En son HoloLens 2 güncelleştirmesini [](hololens-update-hololens.md#check-for-updates-and-manually-update) almak için güncelleştirmeleri kontrol edebilirsiniz ve el ile güncelleştirebilir veya Advanced Recovery Companion aracılığıyla cihazınızın flash sürümünü almak için Tam Flash Güncelleştirmeyi (FFU) [edinebilirsiniz.](hololens-recovery.md#clean-reflash-the-device) İndirme [güncel](https://aka.ms/hololens2download) tutulur ve genel kullanıma açık en son derlemeyi sağlar.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, sürüm 21H1
- Derleme 20346.1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihaz üzerinde herkes tarafından kullanılan özellikler ve IT Yöneticileri tarafından yapılandırılan yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda her hedef kitleyle ilgili özellikler açıklanmıştır. BIR IT Yöneticisiyseniz lütfen IT Yöneticisi - Güncelleştirme Denetim [Listesi'ne göz atın.](#it-admin---update-checklist)
>[!IMPORTANT]
>Bu derlemeye güncelleştirmek için HoloLens 2 cihazlarında Şu anda Şubat 2021 güncelleştirmesi (derleme 19041.1136) veya daha yeni bir sürümü çalıştırıyor olması gerekir. Bu özellik güncelleştirmesini görmüyorsanız lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>Bugün Microsoft HoloLens 2, aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmeleri) destekler:
>- Windows Holographic, sürüm 20H2 (Derleme 19041.1128+)
>- Windows Holographic, sürüm 2004 (Derleme 19041.1103+)
>- Windows Holographic, sürüm 1903 (Derleme 18362+) 
>
> Windows Holographic sürüm 21H1'in tanıtımıyla, **Windows Holographic sürüm 1903** için aylık bakım güncelleştirmelerini sonlandırıyoruz. Bu sayede daha yeni sürümlere odaklanarak değerli geliştirmeler yapmaya devam edeceğiz. 


| Özellik Adı                                              | Kısa açıklama                                                                      | Hedef Hedef Kitle | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | Yeni Chromium tabanlı Microsoft Edge Artık HoloLens 2'de kullanılabilir. | Son Kullanıcı | 
[WebXR ve 360 Görüntüleyici](#webxr-and-360-viewer) | Tam ekran web deneyimlerini ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı | 
[Yeni Ayarlar uygulaması](#new-settings-app) | Eski Ayarlar uygulaması, yeni özellikler ve ayarlarla güncelleştirilmiş bir sürümle değiştir ediliyor. | Son Kullanıcı |
[Renk ayarlamayı görüntüleme](#display-color-calibration) | HoloLens 2 ekranınız için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama başına birim denetimi](#per-app-volume-control) | Uygulama düzeyindeki birimi sistem biriminden bağımsız olarak denetleme. | Son Kullanıcı |
[Web uygulamalarını yükleme](#install-web-apps) | Yeni Microsoft Edge tarayıcısıyla HoloLens 2 Microsoft Office gibi web Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekme](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde HoloLens cihazı yeniden başlatın ve kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve / veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında otomatik oturum açmanın Bilgi Noktası modları için kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni Ayarlar ve Edge uygulamaları için AUMID'ler. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlatma menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
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
> Bu yeni Microsoft Edge, yeni sürümlerde Microsoft Edge eski [sürümlerin yerini](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni uygulamayı Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil bir kısma simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski sanal Microsoft Edge. Yeni Microsoft Edge başlattıktan sonra eski verileri kullanmaya devam eder Microsoft Edge, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, DAHA önce eski sanal ağlarda kullanılabilenden çok daha geniş bir Dizi HoloLens 2 tarayıcı Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Kurumsal belgeleri](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge ekibimiz, her yeni ilkenin HoloLens 2'de çalıştığını garantileyememiyor. Ancak, daha önce HoloLens 2'de Microsoft Edge eski Microsoft Edge ilkenin eşdeğerini test ettik ve onayladık. HoloLens [2 Microsoft Edge'in eski sürümü Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski tarayıcı Microsoft Edge eşdeğeri olan yeni Microsoft Edge ilke eşlemesini bulmak için bkz. İlke eşlemesi.
>
> HoloLens 2 Microsoft Edge en az iki  yeni ilke vardır:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de yeni Microsoft Edge beklemeleri gerekenler

Yeni Microsoft Edge, yeni bir UWP bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan, HoloLens 2 gibi yalnızca UWP cihazlarında çalışmasına izin verir, bazı özellikler hemen kullanılabilir olmayacaktır. Önümüzdeki aylarda yeni senaryoları ve özellikleri destekley edeceğimiz için bu alanı güncel bilgiler için kontrol edin.

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

Edge Insider Microsoft Edge daha fazla bilgi edinmek için Microsoft Edge [Insider](https://www.microsoftedgeinsider.com) giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamak için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Microsoft Edge Insider kanallarını HoloLens 2'ye yüklemek için kullanılabilen birkaç yöntem vardır:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetemeyen cihazlar tarafından kullanılabilir)**
  1. HoloLens 2'nizin [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge Insider kanalı için **HoloLens 2** için indir düğmesini seçin.
  1. İndirilen .msix dosyasını Edge indirme kuyruğundan veya cihazınızın "İndirmeler" klasöründen (Dosya Gezgini.
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatacak.
  1. Yükle **düğmesini** seçin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

**Windows Cihaz Portalı ile PC üzerinden yükleme [](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (HoloLens 2'de geliştirici modunun etkinleştirilmesi gerekir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki aşağı ok düğmesini seçin.
  1. Açılan **menüden HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) Windows Cihaz Portalı HoloLens 2'ye yüklemek için bilgisayarınıza bir dosya yükleyin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

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

#### <a name="how-to-use-webxr"></a>WebXR kullanma

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

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Popüler WebXR ve 360 Görüntüleyicisi bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak, kare hızı kesilebilir veya stutter.
- WebXR 'deki ifade eden her bir el ile yönelik destek, varsayılan olarak etkin değildir. Geliştiriciler, `edge://flags` "WebXR el girişi" ni etkinleştirerek aracılığıyla desteğini etkinleştirebilir.
- YouTube dışındaki Web sitelerinden 360 video, beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Viewer hakkında geri bildirim sağlama

Lütfen yeni Microsoft Edge 'deki **geri bildirim gönder** özelliği aracılığıyla ekibimize geri bildirim ve hata paylaşabilirsiniz.

### <a name="new-settings-app"></a>Yeni ayarlar uygulaması

Bu sürümle birlikte ayarlar uygulamasının yeni bir sürümünü sunuyoruz. Yeni ayarlar uygulaması, aşağıdaki alanlarda HoloLens 2 için yeni özellikleri ve genişletilmiş ayarları içerir: ses, güç & Sleep, ağ & Internet, uygulamalar, hesaplar, erişim kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni ayarlar uygulaması eski Ayarlar uygulamasından farklı olduğu için, daha önce ortamınıza yerleştirdiğiniz tüm ayarlar pencereleri güncelleştirme sonrasında kaldırılır.

![Yeni ayarlar uygulama giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarları arama: anahtar sözcük veya ayar adı kullanarak ayarlar giriş sayfasından ayarları arayın.
- Sistem > sesi:
  - Giriş ve çıkış ses cihazları: bağımsız olarak giriş ve çıkış ses cihazlarınızı seçin (örneğin, Bluetooth kulaklıklar aracılığıyla ses dinleyin veya ses girişi için bir USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar, HoloLens 2 tarafından desteklenmez.
  - Uygulama hacmi: her uygulamanın birimini bağımsız olarak ayarlayın. Bkz. [uygulama birimi denetimi başına](#per-app-volume-control).
- System > güç & uyku: bir süre işlem yapılmadan sonra cihazın uyku moduna geçmesi gerektiğini seçin.
- Sistem > pili: pil tasarrufu modunu el ile etkinleştirin veya nokta pil tasarrufu modunun otomatik olarak etkinleştirileceği bir pil eşiği ayarlayın.
- USB > cihazlar: varsayılan olarak USB bağlantılarını devre dışı bırakabilirsiniz.
- Internet & ağı:
  - USB-C Ethernet bağdaştırıcıları artık ağ & Internet 'te görüntülenir.
  - USB-C Ethernet bağdaştırıcısı ayarları, IP adresi dahil artık kullanılabilir.
  - Artık, HoloLens 2 ' de uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için bkz. [Varsayılan uygulama Seçicisi](#default-app-picker).
- Hesaplar diğer kullanıcılar >: cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilir, cihaz sahiplerini standart kullanıcılara indirgeyebilirler ve kullanıcıları kaldırabilir.
- Erişim kolaylığı: metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Önceden yerleştirilmiş ayarlar penceresi kaldırılır (Yukarıdaki nota bakın).
- Artık cihazınızı ayarlar uygulamasıyla yeniden adlandıramazsınız. BT yöneticileri [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) cihaz adı ŞABLONUNU veya MDM [devdetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) ext/Microsoft/dnscomputername düğümünü kullanarak cihazları yeniden adlandırabilirler.
- Ethernet sayfasında her zaman sanal bir Ethernet aygıtı ("UsbNcm") gösterilir.
- Yeni Microsoft Edge için pil kullanımı doğru olmayabilir, çünkü doğası, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 Masaüstü uygulaması olarak (yakında düzeltilmez).

#### <a name="display-color-calibration"></a>Ekran renk ayarı



Bu yeni ayarla, HoloLens 2 ekran için alternatif bir renk profili seçebilirsiniz. Bu, özellikle daha düşük ekran parlaklığı düzeylerinde renklerin daha doğru görünmesine yardımcı olabilir. Ekran renk ayarlaması, Ayarlar uygulamasında sistem > ayarlama sayfasında bulunabilir.

> [!NOTE]
> Bu ayar, görüntüleme bellenimine yeni bir renk profili kaydederken bu, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Ekran renk ayarı 'nı kullanma

1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında, **görüntü renk ayarlama Çalıştır** düğmesini seçin.
1. Ekran renk ayarlama deneyimi başlatılır ve bu işlem, vizörü ' inizin doğru konumda olduğundan emin olmanızı sağlar.
1. Yönerge iletişim kutularında ilerledikten sonra, ekran otomatik olarak %30 oranında gri olacak.
    > [!TIP]
    > Ortamınızdaki soluk sahneyi görmekte sorun yaşıyorsanız, cihazın sol tarafındaki parlaklık düğmelerini kullanarak HoloLens 2 ' nin parlaklık düzeyini el ile ayarlayabilirsiniz.
1. Her renk profilini hemen denemek ve gözlerinize en iyi şekilde bakmak için düğmeler 1-6 ' i seçin (Bu, genellikle sahnenin gri tonlamalı bir şekilde görünmesine yardımcı olan profil ve beklenen şekilde görünür.)

    ![Renk ayarlama sahnesini görüntüle](images/color-cal-ui.png)
    
1. Seçili profille memnun olduğunuzda **kaydet & çıkış** düğmesini seçin
1. Değişiklik yapmayı tercih ediyorsanız, **iptal & çıkış** düğmesini seçin ve değişiklikleriniz geri döndürülecek

> [!TIP]
> Görüntü renk ayarlama ayarını kullanırken göz önünde bulundurmanız gereken bazı yararlı ipuçları aşağıda verilmiştir:
> - İstediğiniz zaman ayarlar ' da ekran renk ayarlamayı yeniden çalıştırabilirsiniz
> - Cihazdaki herkes renk profillerini değiştirme ayarını daha önce kullanmışsa, en son değişikliğin tarih/saati ayarlar sayfasında yansıtılır
> - Ekran renk ayarı 'nı yeniden çalıştırdığınızda, daha önce kaydedilen renk profili vurgulanacaktır ve profil 0 görünmez (profil 0 ' ın özgün renk profilini gösterdiği gibi)
> - Ekran özgün renk profiline geri dönmek istiyorsanız, bu ayarı Ayarlar sayfasından yapabilirsiniz (bkz. [renk profilini sıfırlama](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama 

HoloLens 2 ' ye kaydedilmiş özel renk profili varsa, cihazın özgün renk profilini geri yükleyebilirsiniz:
1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında **varsayılan renk profilini Sıfırla** düğmesini seçin.
1. İletişim kutusu açıldığında, HoloLens 2 ' yi yeniden başlatmaya hazırsanız **Yeniden Başlat** ' ı seçin ve değişikliklerinizi uygulayın.

#### <a name="top-display-color-calibration-known-issues"></a>En üstteki ekran renk ayarlaması bilinen sorunları

- Ayarlar sayfasında, bu ayar sayfasını yeniden yükleyene kadar, renk profilinin en son ne zaman değiştirildiğini söyleyen durum dizesi güncel olmayacaktır.
    - Geçici çözüm: başka bir ayarlar sayfası seçin ve ardından ayarlama sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirir veya onu destekleyen birden fazla yüklü uygulama ile bir dosya türü açtığınızda, hangi yüklü uygulamanın dosyayı veya bağlantı türünü işlemesini seçmenizi isteyen yeni bir pencere açılır. Bu pencerede, Seçilen uygulamanın "bir kez" veya "Always" dosya veya bağlantı türünü işlemesini de seçebilirsiniz.

"Always" seçeneğini belirlerseniz, daha sonra belirli bir dosyayı veya bağlantı türünü işleyen uygulamayı değiştirmek istiyorsanız, **ayarlar > uygulamalar**' da kaydedilmiş Varsayılanları sıfırlayabilirsiniz. Sayfanın alt kısmına ilerleyin ve "dosya türleri için varsayılan uygulamalar" ve/veya "bağlantı türleri için varsayılan uygulamalar" altındaki **Temizle** düğmesini seçin. Masaüstü PC 'Lerde benzer ayarların aksine, tek tek dosya türü varsayılanlarını sıfırlayamazsınız.

#### <a name="per-app-volume-control"></a>Uygulama birimi denetimi başına

Artık bu Windows derlemesinde, kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duydukları uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha fazla duymasını sağlar. Başka bir kişiyi başka bir kişiye uzak yardım için çağırırken bir uygulamanın hacminin kapatılmasının gereksinimi.

Tek bir uygulamanın birimini ayarlamak için **Ayarlar**  ->  **sistem**  ->  **sesi**' ne gidin ve gelişmiş ses seçenekleri altında **uygulama birimi ve cihaz tercihleri**' ni seçin.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe göre kaydırın

Bazı müşteriler, yazmak istediğiniz sözcüğün şeklini çekerek sanal klavyelerde "tür" ı daha hızlı bulabilir ve bu özelliği holographic klavye için önizliyoruz. Parmaklarınızın ucunu holographic klavye düzlesiyle geçirerek bir kerede tek bir sözcük çekerek, sözcüğün şeklini çekerek ve sonra, parmağınızın ucunu klavyenin düzleminden çizerek bir kez dolaşaktarabilirsiniz. Sözcüklerinizi sözcükler arasındaki klavyeden kaldırarak, daha sonra da boşluk çubuğuna basmanız gerekmeden, izleme sözcüklerini çekerek bulabilirsiniz. Parmağınızın klavye üzerindeki hareketini takip eden bir çekme izi görürseniz özelliğin çalıştığını bilirsiniz.

Lütfen bu özelliğin, parmağınızla (cep telefonundan farklı olarak) bir holographic klavye için herhangi bir zaman duymayın. 

### <a name="power-menu-from-start"></a>Başlangıç menüsünde güç menüsü

Kullanıcının oturumu kapatmasını, kapatması ve cihazı yeniden başlatmasını sağlayan yeni bir menü. HoloLens Başlangıç ekranındaki bir sistem güncelleştirmesi ne zaman kullanılabilir olduğunu gösteren bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. [Başlangıç hareketini](hololens2-basic-usage.md#start-gesture) veya "Başlangıç ekranına git" diyerek HoloLens başlangıç ekranını açın.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkat edin:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Kendi ellerinizi veya "Power" sesli komutunu kullanarak Kullanıcı profili resmini seçin.

4. Oturumu kapatma, cihazı yeniden başlatma veya kapatma seçeneklerinin bulunduğu bir menü görünür:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Oturumu kapatmak, HoloLens 'nizi yeniden başlatmak veya kapatmak için menü seçeneklerini belirleyin. Cihaz [tek bir Microsoft hesabı (MSA) veya yerel hesap](hololens-identity.md)için ayarlandıysa, oturumu Kapat seçeneği kullanılamayabilir.

6. Başka herhangi bir yere dokunarak veya Başlat menüsünü başlangıç hareketiyle kapatarak menüyü kapatın.

#### <a name="update-indicator"></a>Göstergeyi Güncelleştir

Bir güncelleştirme kullanılabilir olduğunda, bir yeniden başlatmanın güncelleştirmeyi yükleyeceğini göstermek için üç nokta simgesi de açılır. Bu seçenek, güncelleştirmenin varlığını yansıtacak şekilde değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok Kullanıcı listelendi

Daha önce oturum açma ekranında yalnızca en son oturum açan kullanıcının yanı sıra ' diğer Kullanıcı ' giriş noktası gösteriliyordu. Cihazda birden çok kullanıcı oturum açmışsa, bu yeterli olmayan müşteri geri bildirimi aldık. Yine de bunların Kullanıcı adını yeniden yazması gerekiyordu.

Bu Windows derlemesinde sunulan, PIN girişi alanının sağında bulunan **başka bir Kullanıcı** seçerken oturum açma ekranında, daha önce cihazda oturum açan birden çok Kullanıcı görüntülenir. Bu, kullanıcıların kullanıcı profillerini seçmesini ve sonra Windows Hello kimlik bilgilerini kullanarak oturum açmasını sağlar. Bu diğer kullanıcılar sayfasından, **Hesap Ekle** düğmesi aracılığıyla cihaza yeni bir kullanıcı da eklenebilir.

Diğer kullanıcılar menüsünde, diğer kullanıcılar düğmesi cihazda oturum açan son kullanıcıyı görüntüler. Bu Kullanıcı için oturum açma ekranına geri dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılanı](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C dış mikrofon desteği

> [!IMPORTANT]
> **BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**. Bir USB-C kulaklık kümesini yüklerken, kullanıcıların kulaklık sesinin otomatik olarak yeniden yönlendirildiğini gözlemleyecek, ancak HoloLens OS, iç Microphone dizisinin diğer herhangi bir giriş cihazını önceliklendirileceği. **Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**

Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir. USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.

**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.

![Ses ayarları](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.
>
> Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın. **Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.
>
> **Iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens MIC dizisi diğer görevler için hala kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği nedir?

Ne yazık ki Bluetooth mikrofonlar Şu anda HoloLens 2 ' de desteklenmemektedir.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonları sorunlarını giderme

Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. Bu mikrofonlardan birini HoloLens 'e takarken ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  ->  **sistem**  ->  **sesi**' nde yerleşik hoparlörleri **(analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. Mikrofon kaldırılıp daha sonra yeniden bağlansa, HoloLens bu ayarı unutmalıdır.

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

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Bilgi noktası modlarında yeni ayarları ve uç uygulamaları kullanın

Bilgi [noktaları](hololens-kiosk.md), bir BT Yöneticisi tarafından, büyük bir yandan uygulama kullanıcı modeli kimliği (aumıd) kullanarak uygulamayı bilgi noktasında ekler. Hem ayarlar uygulaması hem de Microsoft Edge uygulaması yeni uygulamalar olarak değerlendirildiğinden ve bu uygulamalar için AUMIDs kullanan eski uygulamalardan farklı olarak, yeni AUMıD kullanacak şekilde güncelleştirilmeleri gerekecektir.

Yeni uygulamaları dahil etmek için bir bilgi noktası değiştirirken, yeni AUMıD 'de ekleme ve eskisini bırakma önerilir. Bu, kullanıcılar işletim sistemini güncelleştirinceye kadar kolay bir geçiş oluşturur ve bilgi noktası 'nı istendiği gibi kullanmaya devam etmek için yeni ilkeler almamayı gerektirmez.

| Uygulama                    | AUMıD                                                  |
|------------------------|--------------------------------------------------------|
| Eski ayarlar uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! Uygulamanızda            |
| Yeni ayarlar uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Uygulamanızda |
| Eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri

Daha eski derlemelerde, bir cihazın bir bilgi noktası yapılandırması varsa ve bu, hem genel atanan erişim hem de AAD grup üyesi tarafından atanan erişimin bir birleşimi ise, AAD grup üyeliğini belirlemek başarısız olursa Kullanıcı "[hiçbir şey gösterilmez](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" menüsünü görür.

Bu Windows sürümünden itibaren, bilgi noktası deneyimi AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Sayfa ayarları görünürlüğü için yeni ayarlar URI 'Leri

[Windows holographic ' de, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ' de ayarlar uygulaması içinde görülen sayfaları kısıtlamak için [Ayarlar/PageVisibilityList ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ekledik. PageVisibilityList, BT yöneticilerinin sistem ayarları uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilen bu hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

[Sayfa ayarları görünürlüğünü](settings-uri-list.md)ziyaret ederseniz, bu CSP 'yi ve önceki sürümlerde bulunan URI 'lerin listesini kullanmak için yönergeler bulabilirsiniz.

BT yöneticilerinin yönetebileceği kullanılabilir ayar URI 'lerinin listesi üzerinde genişletiliyor. Bu URI 'lerden bazıları yeni ayarlar uygulamasındaki yeni kullanılabilir alanlara yöneliktir. Settings/PageVisibilityList ilkesini kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

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
| Sistem > depolama > depolama algılaması yapılandırma         | `ms-settings:storagepolicies`                      |
| Saat & Dil > Tarih & saati                        | `ms-settings:dateandtime`                          |
| & Dil > klavye                           | `ms-settings:keyboard`                             |
| Zaman & Dil > dili                           | `ms-settings:language`                             |
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

Hem bilgisayarlar hem de diğer HoloLens 2 cihazları dahil olmak Windows 10 cihazlarıyla yakın bir şekilde paylaşın. HoloLens'den **bir** pc'ye dosya veya URL'leri paylaşmak için Ayarlar  ->    ->   Sistem Paylaşılan Deneyimleri'ne gidin. Diğer ayrıntılar için, [Windows 10'de yakındaki cihazlarla şeyler paylaşma hakkında daha fazla bilgi Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Bu özellik [Bağlantı/AllowConnectedDevices aracılığıyla yönetilebilir.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, yeni işletim sistemi güncelleştirmeleri için Ayarlar uygulamasının da ek olarak yeni bir sorun giderici eklendi. Ayarlar Güncelleştirme **Güvenliği**  ->  **Sorunlarını &amp; Giderme'ye**  >    >  **Windows Update** başlat'ı **seçin.** Bu sayede, sorunlarınızı işletim sistemi güncelleştirmeleriyle yeniden üretirken, IT veya destekle ilgili sorunları gidermeye daha iyi yardımcı olmak için izlemeleri toplayabilirsiniz.

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

Oturum açmış AAD kullanıcılarının AAD grup üyeliği başarıyla belirlenene kadar, başlat menüsü için genel bilgi noktası yapılandırması kullanılır (varsa) aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınıza bildirmeniz gereken bir şey olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ayarları Görünürlüğü güncelleştirmeleri

✔️ Ayarları [**Görünürlüğü için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarları [Görünürlüğü kullanıyorsanız,](settings-uri-list.md) izin verilen veya engellenen mevcut URI'lerde ayarlamalar yapmak isterseniz.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler
✔️ WDAC aracılığıyla Microsoft Edge engelleme yaptıysanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.
#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme
✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, yeni uygulama için bu yeni uç noktaları Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere uzer ve kim tarafından toplay olduğunu yapılandırmış oluruz.

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
- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic sürüm 21H1'i denemeniz için sizi teşvik ederiz.

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

HoloLens 2 cihazlarınıza daha Uygulama Yükleyicisi uygulamaları yüklemenize olanak sağlayan yeni bir özellik **(Uygulama Yükleyicisi)** ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazlar için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:
- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin (USB üzerinden veya Edge üzerinden) cihazınıza indirerek Dosya Gezgini Appx Paketi'ne gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğunuz uygulamalar gibi, uygulamaların [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) da İmza Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce HoloLens cihazı tarafından imzalanacak sertifikaya güvenilmeleri gerekir. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Uygulama yükleme yönergeleri.**

1.  Cihazınızın yönetilen olarak kabul edilen bir cihaz olduğundan emin olun
1.  HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1.  HoloLens 2 cihazında oturum açın
1.  Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Storage\Downloads klasörüne kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1.  HoloLens 2 cihazınızın Başlat Menüsünü açın, Tüm uygulamalar'ı seçin ve Dosya Gezgini açın.
1.  İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1.  yourapp.appxbundle dosyasını seçin.
1.  Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Evrensel Örnekleri GitHub'da](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamalar bulabilirsiniz.

[holoLens 2'de uygulama yükleme işleminin tamamını okumanız Uygulama Yükleyicisi.](app-deploy-app-installer.md)  

![UYGULAMA YÜKLEYICISI aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek ele göre yalnızca konum güncelleştirilirken diğer ortaklar önceki poza göre ertelenmektedir.  Bu değişiklik, hareketlerde takip tutarlılığını artırmaya yardımcı olur; örneğin, kırpma, atma, kırpma ve kırpma.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El joint'ler inferred olduğunda, her [bir ortak](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi
- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic sürüm 20H2 – Aralık 2020 Güncelleştirmemizi ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz için sizi teşvik ederiz.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2
- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve HoloLens 2 kullanıcıları ve BT uzmanlarına harika bir dizi yeni özellik getirir. Otomatik Göz Konumlandırma'dan Ayarlar'da Sertifika Yöneticisi'ne, gelişmiş Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine. Bu yeni güncelleştirme, IT ekiplerinin HoloLens cihazlarını yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip olduğunu ve kullanıcılara daha sorunsuz holografik deneyimler sunduğuna olanak tanır. 

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler ekllmektedir. Ana derleme numarası aynı kalır ve Windows Update sürüm 2004'e (derleme 19041) göre aylık bir sürümü belirtecek. En son 19041.1128+ derlemesinde olduğunu onaylamak için Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, Güncelleştirme & Security'ye gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. HoloLens güncelleştirmelerini yönetme hakkında daha fazla bilgi için bu [sayfayı ziyaret edin.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic sürüm 20H2'daki yeniler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik Göz Konumu Desteği](hololens-release-notes.md#auto-eye-position-support) | Kullanıcıların Göz İzleme ayarına girmeden göz konumlarını etkin bir şekilde hesaplama.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Ayarlar uygulamasından sertifika yüklemek ve kaldırmak için yeni daha basit yöntemlere izin verir.     |
| [USB'den sağlamayı otomatik başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerinde paketlerin sağlanması, otomatik olarak OOBE'de sağlama sayfasına sorılır.                                                         |
| [OOBE'de sağlama paketlerini otomatik olarak onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve otomatik onaylamayı birlikte birleştirme. |
| [Autopilot'ı Wi-Fi kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısına gerek kalmadan Wi-Fi otomatik pilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlanır veya yeniden yanıp söner. |
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli hale gelen birden çok uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens İlkeleri](hololens-release-notes.md#hololens-policies)                                    | HoloLens için yeni ilkeler.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların belirli bir gün boyunca Çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz yönetimi ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Ayarlar uygulamasında hangi sayfaların görül ekli olduğunu seçmek için ilke.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2'de Araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikayı geçmeyecek. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

HoloLens 2'de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve geliştirilmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcı cihazı bağlı olduğu andan itibaren otomatik olarak arka planda çalışmaya başlar. Kullanıcının daha önce göz izleme ayarı yoksa Otomatik Göz Konumu, 20 -30 saniyelik bir işlem süresi sonra kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve bu nedenle kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, bir kullanıcı daha önce cihazda göz izleme ayarlama işleminin üzerinden geçilen birini ifade eder.

| Etkin Uygulama | Önceki Davranış | Windows Holographic sürüm 20H2 Güncelleştirmesi'nin davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Bakışın etkinleştirilmemiş uygulaması veya Holographic Shell |Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | İstem görüntülenmez. |
| Bakış özellikli uygulama | Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz bakışı akışına erişdiğinde görüntülenir. |

Kullanıcı, bakış etkin olmayan bir uygulamadan bakış verilerine erişen uygulamaya geçiş olursa, ayarlama istemi görüntülenir. 

Diğer tüm sistem davranışları, geçerli kullanıcının etkin bir göz izleme cihazına sahip olmadığının benzeridir. Örneğin Tek Elli Başlangıç hareketi etkinleştirilmez. İlk kurulumda İlk İlk Deneyimi'ne hiçbir değişiklik olmayacaktır.

Göz bakışı verileri veya çok hassas hologram konumlandırması gerektiren deneyimler için kullanıcıların göz izleme cihazlarını çalıştırmalarını öneririz. Göz izleme ayarlama isteminden veya başlangıç menüsünden Ayarlar uygulamasını başlatarak ve ardından Sistem > Ayar > Göz Ayarı'> **Çalıştır'ı seçerek erişilebilir.**

Bu bilgiler daha sonra diğer ayarlama [bilgileriyle bulunabilir.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama aracı. Bu özellik, ticari ortamlarda büyük ölçekte sertifikalarınızı dağıtmanıza, sorun gidermenize ve doğrulamanıza olanak tanır.

Windows Holographic sürüm 20H2'de, HoloLens 2 Ayarları uygulamasına bir Sertifika Yöneticisi ekliyoruz. Ayarlar ve **Güncelleştirme >'& Sertifikaları > gidin.** Bu özellik, cihazınıza sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kullanımı kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için denetim, tanılama ve doğrulama araçlarını iyileştirdi. 

-   **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığından veya uygun şekilde kaldırıldığından emin olmak için yeteneği. 
-   **Tanılama:** Sorunlar ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulama zaman kazandırır ve sorun gidermeye yardımcı olur. 
-   **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğunu doğrulamak, sertifikaları daha büyük ölçekte dağıtmadan önce özellikle ticari ortamlarda önemli ölçüde zaman tasarrufu sağlar.

Listede belirli bir sertifikayı hızla bulmak için ad, depolama veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar sertifikayı doğrudan da arayabilir. Tek tek sertifika özelliklerini görüntülemek için sertifikayı seçin ve Bilgi'ye **tıklayın.** 

Sertifika yüklemesi şu anda .cer ve .crt dosyalarını desteklemektedir. Cihaz Sahipleri Sertifikaları Yerel Makineye ve Geçerli Kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca Geçerli Kullanıcı'ya yükleyebilir. Kullanıcılar yalnızca doğrudan Ayarlar kullanıcı arabiriminden yüklü sertifikaları kaldırabilir. Bir sertifika başka bir şekilde yüklendiyse, aynı mekanizma tarafından da kaldırılmalıdır.

#### <a name="to-install-a-certificate"></a>Sertifika yüklemek için: 

1.  HoloLens 2'nizi bir bilgisayara bağlayın.
1.  Yüklemek istediğiniz sertifika dosyasını HoloLens 2'nizin bir yerine yer açın.
1.  Ayarlar Uygulama **Uygulama Güncelleştirme > Güvenlik & Sertifikalar> a gidin** ve Sertifika yükle'yi seçin.
1.  Dosyayı **İçeri Aktar'a** tıklayın ve sertifikayı kaydeden konuma gidin.
1.  Mağaza **Konumu'seçin.**
1.  Sertifika **Deposu'ları seçin.**
1.  **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklenmiş olması gerekir.

#### <a name="to-remove-a-certificate"></a>Sertifikayı kaldırmak için: 
1. Ayarlar Uygulama **Güncelleştirme > Güvenlik Ve Sertifikalar'> gidin.**
1. Arama kutusunda sertifikayı adıyla ara.
1. Sertifikayı seçin.
1. **Kaldır'a tıklayın**
1. Onay **istendiğinde** Evet'i seçin.

![Ayarlar uygulamasında sertifika görüntüleyici](images/certificate-viewer-device.jpg)

![Sertifika kullanıcı arabirimini kullanarak sertifika yüklemeyi gösteren resim](images/certificate-device-install.jpg)

Bu bilgiler daha sonra yeni [bir Sertifika Yöneticisi sayfasında bulunabilir.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>USB'den sağlamayı otomatik başlatma

- Otomatikleştirilmiş işlemler, OOBE sırasında Sağlama Paketleri ile USB Sürücüleri kullanılırken daha az kullanıcı etkileşimi sağlar.

Bu sürümden önce kullanıcılar, bir düğme birleşimi kullanarak sağlama yapmak için OOBE sırasında sağlama ekranı el ile başlatmak zorunda kaldı. Artık kullanıcılar USB depolama sürücüsünde Sağlama Paketi kullanarak düğme birleşimini atlar. 

1. OOBE'nin ilk etkileşime açık anları sırasında USB sürücüyü sağlama paketiyle takın
1. Cihaz hazır olduğunda, sağlama sayfasıyla otomatik olarak istemi açar. 

Not: Cihaz önyüklerken bir USB sürücü takılı bırakıldı ise OOBE mevcut USB depolama cihazını numaralandıracak ve eklerinin takılı olduğunu izler.

OOBE sırasında sağlama paketlerini uygulama hakkında daha fazla bilgi için [HoloLens sağlama belgelerini ziyaret](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) edin.

[USB'den otomatik başlatma sağlama hakkında ek](hololens-provisioning.md#auto-launch-provisioning-from-usb) bilgileri HoloLens sağlama belgelerinde bulabilirsiniz.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE'de sağlama paketlerini otomatik onaylama
- Daha az kullanıcı etkileşimi sağlayan otomatik işlem, Sağlama Paketi sayfası görüntülendiğinde listelenen tüm paketleri otomatik olarak uygulayacaktır.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerini otomatik olarak uygulamaya başlamadan önce OOBE 10 saniye geri sayar. Kullanıcılar, [beklendikten sonra bu](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 10 saniye içinde onaylayabilir veya iptal edebilir.

### <a name="automatic-provisioning-without-using-ui"></a>Kullanıcı arabirimini kullanmadan otomatik sağlama
- Sağlama için azaltılmış cihaz etkileşimleri için birleşik otomatik işlemler. 

Kullanıcı, USB cihazlardan sağlamanın otomatik başlatılmasını ve paketlerin otomatik olarak onayını birleştirerek HoloLens 2 cihazlarını cihazın kullanıcı arabirimini kullanmadan ve hatta cihazı takmadan otomatik olarak sunar. Birden çok cihaz için aynı USB sürücü ve sağlama paketini kullanmaya devam edersiniz. Bu, aynı alanda aynı anda birden çok cihaz dağıtmak için kullanışlıdır. 

1. [Windows Yapılandırma Tasarımcısı'ı kullanarak](hololens-provisioning.md) [Sağlama Paketi oluşturun.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [HoloLens 2'nizi](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361'e veya daha yeni bir derlemeye flash olarak söner.](https://aka.ms/hololens2previewdownload) 
1. Gelişmiş [Kurtarma Yardımcı,](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın usb-C kablolarını çıkarın ve yanıp sönerek tamamlandıktan sonra. 
1. USB sürücülerinizi cihaza takın.
1. HoloLens 2 cihazı OOBE'de ilk kez başlatılırken, USB sürücüsünde sağlama paketini otomatik olarak algılar ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz sağlama paketini otomatik olarak uygulayacaktır. 

Cihazınız artık yapılandırıldı ve Sağlama [Başarılı ekranı görüntülenir.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Autopilot'ı Wi-Fi kullanma
- Autopilot'ın bağlı cihazlarda çalışmasına olanak sağlayarak Ethernet'e USB-C bağdaştırıcıları ihtiyacı Wi-Fi kaldırıldı.

Artık OOBE sırasında, HoloLens 2'yi Wi-Fi ile bağ devredtikte OOBE, cihaz için bir Autopilot profili olup olamayacak. Bir tane bulunursa, AAD'ye katılma ve kayıt akışının geri kalanını tamamlamak için kullanılır. Başka bir deyişle, USB-C'ye ethernet veya USB-C bağdaştırıcısına Wi-Fi artık gerekli değildir, ancak OOBE'nin başında sağlanıyorsa çalışmaya devam eder. [HoloLens 2 cihazları için Autopilot hakkında daha fazla bilgi edinebilirsiniz.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot
- Cihaz sıfırlama veya ters eğik çizgi ile bile cihazları kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar. Sağlama yoluyla içinde hesap oluşturulmasına izin ve daha fazla güvenlikle. 

HoloLens 2 cihazları artık Windows Holographic sürüm 20H2'den sonra TenantLockdown [CSP'yi desteklemektedir.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değere ayarlandıktan sonra bu değer yeniden yanıp sönmeye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır. 

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra OOBE, Ağ bağlantısı sonrasında Autopilot profilinin başarıyla indirilme ve uygulanması için süresiz olarak bekler. 

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra OOBE'de aşağıdaki işlemlere izin verilmiyor: 
- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme 
- OOBE deneyiminde cihazın sahibini seçme 

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesi yapma ve eşitlemeyi tetikleme.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak HoloLens 2'de TenantLockdown'ın RequireNetworkInOOBE'lerinin kümesi nasıl geri alır? 
1. Yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2'i kaldırın. 

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin. OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesi yapma ve eşitlemeyi tetikleme.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Bir HoloLens'te Autopilot profili atanmamışsa OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilebini süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir. 

![İlkenin cihazda ne zaman zorlandıkları için cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık [Tenantlockdown CSP](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)ve Autopilot altında Autopilot'ın geri kalanıyla birlikte bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel Atanan Erişim – Bilgi Noktası Modu
- Bilgi noktası modunu sistem düzeyinde geçerli olan yeni Bilgi Noktası yöntemi etkinleştirerek Bilgi Noktası için Azaltılmış Kimlik Yönetimi.

Bu yeni özellik, BIR IT Yöneticisinin bir HoloLens 2 cihazı sistem düzeyinde geçerli olan, sistem üzerinde hiçbir kimliğe benzeşimleri olan ve cihazda oturum açabilen herkes için geçerli olan birden çok uygulama bilgi noktası modu için yapılandırmasını sağlar. Bu yeni özellik hakkında daha fazla bilgi için [HoloLens genel olarak atanan erişim bilgi noktası makalesine bakabilirsiniz.](hololens-global-assigned-access-kiosk.md)

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

Daha önce bilgi noktası modunda hatalarla karşılaşan HoloLens, başlat menüsündeki tüm uygulamaları göstermek için kullanılmıştı. Hata durumunda Windows Holographic sürüm 20H2'de, başlangıç menüsünde aşağıdaki gibi hiçbir uygulama gösterilmez: 

![Bilgi Noktası modunun artık başarısız olduğunda ne gibi göründüğünün resmi.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens İlkeleri
- Cihazı yönetmek için oluşturulan HoloLens için cihaz yönetimi seçenekleri. 

Windows Holographic sürüm 20H2'de HoloLens 2 cihazları için yeni karma gerçeklik ilkeleri oluşturulmuştur. Yeni kontrol edilebilir ayarlar şunlardır: parlaklığı ayarlama, birimi ayarlama, karma gerçeklik yakalamalarında ses kaydını devre dışı bırakma, tanılamanın ne zaman toplanabilir olduğunu ayarlama ve AAD grup üyeliği önbelleği.  

| Yeni HoloLens ilkesi                                | Açıklama                                                                               | Notlar                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Parlaklığı düğmelerinin devre dışı bırakılarak parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı bırakılarak birimi değiştirmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\MicrophoneDisabled                    | HoloLens 2'de ses kaydı mümkün olmak için mikrofonu devre dışı bıraktır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin ne zaman toplanabilir olduğunu kontrol eder.                               | 0 Devre Dışı, 1 Cihaz Sahipleri için Etkin, 2 Herkes için Etkin (Varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD grup üyeliği önbelleğinin Azure AD gruplarını hedeflemek için kaç gün boyunca Bilgi Noktası'nın kullanılacı olduğunu kontrol eder. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın
- 60 gün boyunca AAD gruplarıyla birlikte kullanılacak Çevrimdışı Bilgi Noktası etkinleştirildi.

Bu ilke, oturum açık kullanıcı için Azure AD gruplarını hedef alan Atanan Erişim yapılandırmaları için Azure AD grup üyeliği önbelleğinin kaç gün boyunca kullanılana kadar süreyle kullanılacazın. Bu ilke değeri yalnızca 0'dan büyük değere ayarlanırsa önbellek aksi takdirde kullanılmaz.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az - 0 gün  
En fazla - 60 gün 

Bu ilkeyi doğru kullanma adımları: 
1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bunu HoloLens cihazlarında attayın. 
1. Bu ilke değerini istenen gün sayısına (> 0) ayar alan ve HoloLens cihazlarında atayın özel bir OMA URI tabanlı cihaz yapılandırması oluşturun. 
    1. URI değeri OMA-URI metin kutusuna ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilebilir
    1. Değer izin verilen en az / en yüksek değer arasında olabilir.
1. HoloLens cihazlarını kaydetme ve her iki yapılandırmanın da cihaza uygulandığını doğrulama. 
1. İnternet kullanılabilir olduğunda Azure AD 1 kullanıcısı oturum açmasına izin ver. Kullanıcı oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur. 
1. Artık Azure AD 1 kullanıcısı HoloLens'i çevrimdışı duruma alıp ilke değeri X gün sayısına izin olduğu sürece bilgi noktası modunda kullanabilir. 
1. 4. ve 5. adımlar diğer Tüm Azure AD kullanıcılarının N. Önemli noktası, bilgi noktası yapılandırmasının hedeflene Azure AD grubuna üye olup olmadığını belirleyecek şekilde herhangi bir Azure AD kullanıcılarının internet kullanarak cihazda oturum açması gerektir. 
 
> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilinceye kadar "bağlantısız" ortamlarda belirtilen hata davranışıyla karşılana kadar. 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri
- Kullanıcıların, sağlama paketleri eklemeyi veya kaldırmayı engelleme gibi belirli cihaz yönetimi ilkelerini yönetmesine izin verir.

HoloLens 2 cihazlarının daha fazla yönetim seçeneğine olanak sağlayan yeni etkinleştirilen ilkeler. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni kod Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

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

- Ayarlar uygulaması artık kullanıcının Iris Kaydı veya Göz İzleme Ayarlama deneyimlerine uymaz.
- OOBE sırasında cihazı yeniden adlandıran ve diğer eylemleri (ağa bağlanma gibi) gerçekleştiren sağlama paketinin yeniden adlandırma nedeniyle cihaz yeniden başlatıldıktan sonra diğer eylemleri gerçekleştirememe hatası düzeltildi.
- Görsel kalitesini geliştirmek için ilk cihaz kurulumu akışlarının renk düzeni değiştirildi.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, sürüm 1903 - Ağustos 2020 Güncelleştirmesi
- Derleme 18362.1074

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, sürüm 2004 - Temmuz 2020 Güncelleştirmesi
- Derleme 19041.1109

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Geliştiriciler artık güvenli bir bağlantı gerektiren bir uygulamanın etkinleştirilmesi Cihaz Portalı devre dışı bırakılması arasında seçim olabilir.
- Uygulamanın işletim sistemi güncelleştirmeleri sonrasında başlatılması için güvenilirlik artırıldı.
- Varsayılan gelen kutusu parlaklığı yüzde 100 olarak değiştirildi.
- HoloLens 2'de sanal Windows Cihaz Portalı HTTPS iletmeyle ilgili bir sorun giderildi.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, sürüm 1903 - Temmuz 2020 Güncelleştirmesi
- Derleme 18362.1071

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- unity uygulamalarında izleme kaybı veya yeniden izleme elde edilirken hologramların kaybolmasına neden olan bir sorun düzeltildi.
- Belirli cihazlarda donanım hızlandırma ile HoloLens Öykünücüsü kullanılırken özel HoloLens uygulamalarının kabukta kilitlenmesine neden olan bir sorun düzeltildi.
- HoloLens 2'de sanal Windows Cihaz Portalı HTTPS iletmeyle ilgili bir sorun giderildi.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, sürüm 2004 - Haziran 2020 Güncelleştirmesi
- Derleme 19041.1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirli özellikler belirtilmezse yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses **hatalarını** ortadan kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, bir web tarayıcısı geçersiz sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı bu durumla devam etmek mümkün değildir. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- Ayarlar Sistem   >  **Hologramları'nın ayarı,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş sayfasından tüm hologramları otomatik  >   olarak kaldırmasını sağlayan bir ayar eklendi.
- HoloLens öykünücüsünün piksel biçimini siyah olarak değiştiren HoloLens uygulamalarının neden olduğu bir sorun düzeltildi.
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
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, arka planda çalıştıracak ayar etkinleştirilse bile, bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- HoloLens Emulator'da piksel biçimini siyah olarak değiştiren HoloLens uygulamalarının neden olduğu bir sorun düzeltildi.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, sürüm 2004  
- Derleme - 19041.1103

HoloLens 2, Windows Holographic sürüm *2004* için Mayıs 2020 ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5G/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni özellikler içerir. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, Güncelleştirme &    **Güvenlik'e gidin** ve Güncelleştirmeleri **Kontrol Edin düğmesini**   seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak yeni cihazları üretim için önceden yapılandırma ve sorunsuz bir şekilde ayarlama                 |
|       FIDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamasını etkinleştirmek için FIDO2 Güvenlik Anahtarları desteği            |
|       Geliştirilmiş sağlama                      |          Usb sürücüden HoloLens'inize sorunsuz bir şekilde sağlama paketi uygulama                              |
|       Uygulama yükleme durumu                 |          Uygulamalar için Ayarlar uygulamasında MDM aracılığıyla HoloLens 2'ye gönderilmiş yükleme durumunu denetleme               |
|       Yapılandırma hizmeti sağlayıcıları (CSP'ler)   |          Yönetici denetimi özelliklerini geliştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği 5G/LTE desteği sağlar                                    |
|       Koyu uygulama modu                              |          Hem koyu hem de açık modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir ve görüntüleme deneyimini geliştirin        |
|       Sesli komutlar                             |          HoloLens'i uygulamalı olarak kontrol etmek için ek sistem ses komutları desteği                           |
|       El izleme geliştirmeleri                 |          El izleme geliştirmeleri düğmeleri ve 2D sayfalı etkileşimleri daha doğru hale sağlar                        |
|       Kalite geliştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik geliştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot desteği

Windows Autopilot holoLens 2 için bir uygulama, cihaz satış kanalının HoloLens'i Intune kiracınıza önceden kaydetmesine olanak sağlar. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazır olur. Kendi kendine dağıtımdan yararlanmak için cihazın kurulumun ilk ekranı sırasında USB-C-Ethernet kullanarak bir ağa bağlanması gerekir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başladıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme.
1. Cihazı Microsoft Intune (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.
1. Cihaz hedefli ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlama.
1. Oturum açma ekranı kullanıcıya gösterilir.

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
- Derleme 18362,1056

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- *Holographicdepthreprojection, oto planar* algoritması kullanıldığında karma gerçeklik yakalamadaki iyileştirilmiş hologram kararlılığı.
- Bir derinlik MF örneğine eklenen koordinat sisteminin ortak belgelerle tutarlı olmasını sağlar.
- Müşterilerin cihaz portalı üzerinden büyük miktarlarda metin yapıştırmasını sağlayarak geliştirilmiş geliştirici verimliliği.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows holographic, sürüm 1903-Şubat 2020 güncelleştirme 
- Derleme 18362,1053

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamaları için HolographicSpace. Uservarlığına yönelik API geçici olarak devre dışı bırakıldı. Bu değişiklik, "arka planda çalıştır" ayarı etkinleştirilmiş olsa bile, bazı uygulamaların, vizörü çevrildikten sonra duraklamasını engelleyen bir sorunu önler.
- Kullanıcının bir kullanıcı arabirimi dontığı ve birkaç saniye sonra kabuğa geri dönmesi fark eden, izlenen bir rastgele kilitlenme çökme düzeltildi.
- Gelişmiş izleme, Dizin parmağınızla yer ayırdığınızda, o parmağınızla büyük bir kısmı beklenmedik şekilde eğilerek daha az olabilir.
- Baş izlemenin, uzamsal eşlemenin ve diğer çalışma zamanlarının güvenilirliği geliştirildi.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows holographic, sürüm 1903-Ocak 2020 güncelleştirme 
- Derleme 18362,1043
 
Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 öykünücüsü ile çalışırken özel uygulamalar için iyileştirilmiş kararlılık.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows holographic, sürüm 1903-Aralık 2019 güncelleştirme 
- Derleme 18362,1042

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Son aşama üretilmesi (LSR) düzeltmeleri tanıtılmıştır. Daha kararlı ve daha doğru bir şekilde hesaba göre daha kararlı ve net bir şekilde görüntülenmesi için hologragram geliştirilmiş görsel işleme. Bu belirti, uygulamalar hologragram derinliğini doğru şekilde ayarlamazsanız bu güncelleştirmeden sonra daha belirgin olacaktır.
- Özel uygulamaların ve özel uygulamalar arasında gezinmesinin sabit kararlılığı.
- Karma Gerçeklik yakalamanın birkaç gün boyunca bekleme durumunda olduktan sonra video kaydedemediği bir sorun çözüldü.
- İyileştirilmiş hologram kararlılığı.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows holographic, sürüm 1903-Kasım 2019 güncelleştirme 
- Derleme 18362,1039

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- En-CA ve en-AU için ilk kurulum sırasında sesli komut **seçme** işlevlerinin sabit işlevselliği.
- En son Unity ve karma gerçeklik araç seti (MRTK) sürümlerine daha fazla yerleştirilmiş olan nesnelerin geliştirilmiş görsel kalitesi.
- Başlangıç menüsü açılıp kapanana kadar başlangıçta duraklatılmış durumda takılarak holographic uygulamalarıyla ilgili sorunları düzeltildi.
- HoloLens 2 ve öykünücü için OpenXR çalışma zamanı uyumluluk düzeltmeleri ve geliştirmeleri.
