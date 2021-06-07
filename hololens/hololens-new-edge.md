---
title: Yeni Microsoft Edge
description: Yeni Edge uygulaması hakkında bilgi
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, internet, tarayıcı
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: aefb414deb68376ea45e792f21a929fac7cf3969
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380292"
---
# <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge logosunu yeni Microsoft Edge animasyonu](images/new-edge.gif)

Yeni Microsoft Edge, müşteriler için daha iyi uyumluluk ve web geliştiricileri için web'in daha az parçalanması oluşturmak için [Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) açık kaynak projesini benimser.

[Windows Holographic sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile yeni Microsoft Edge HoloLens 2 müşterileri tarafından ilk kez kullanılabilir! Lütfen yeni çalışmadaki Geri Bildirim  Gönder özelliği aracılığıyla veya Microsoft Edge aracılığıyla [Geri Bildirim Merkezi.](hololens-feedback.md)

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde artık Microsoft Edge eski [sürümler'in](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) yerini otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Yeni uygulamayı Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil bir swirl simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski sanal Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

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

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de yeni Microsoft Edge beklenilenler

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
- "Beni takip et" modundaki bir tarayıcı penceresinden ses çalma sırasında, "Beni takip et" modunu devre dışı bıraksanız da ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu atlayabilirsiniz.
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerinde beklenmedik bir şekilde devre dışı bırakılamaları olabilir. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Bu Microsoft Edge Edge Insider topluluğu tarafından kullanılabilen üç önizleme kanalı vardır: Beta, Dev ve Canary. Önizleme kanalını yüklemek, HoloLens 2'nize Microsoft Edge sürümünü kaldırmaz ve aynı anda birden fazla yükleme işlemi de yükleyebilirsiniz. 

Edge Insider Microsoft Edge daha fazla bilgi edinmek için Microsoft Edge [Insider](https://www.microsoftedgeinsider.com) giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamak için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Microsoft Edge Insider kanallarını HoloLens 2'ye yüklemek için kullanılabilen birkaç yöntem vardır:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetlanmamış cihazlar tarafından kullanılabilir)**
  1. HoloLens 2'niz için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge Insider kanalı için **HoloLens 2** için indir düğmesini seçin.
  1. İndirilen .msix dosyasını Edge indirme kuyruğundan veya cihazınızın "İndirmeler" klasöründen (Dosya Gezgini).
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

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) uygulama Microsoft Edge güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

[HoloLens](hololens-offline.md)için şu anda kullanılabilir olan uç noktalar hakkında daha fazla bilgi okuyun.

## <a name="install-web-apps"></a>Web uygulamalarını yükleme
 > [!Note]
> Windows [Holographic sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)sonra Office web uygulaması artık önceden yüklenmez. 

Yeni Edge'i kullanarak web uygulamalarının yanı sıra yeni Microsoft Store yükleyebilirsiniz. Örneğin, SharePoint veya OneDrive Microsoft Office dosyaları görüntülemek ve düzenlemek için web uygulamasını yükleyebilirsiniz. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya  **Office'i** Yükle düğmesini ziyaret edin ve seçin. Onaylamak **için Yükle'yi** seçin.
> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca HoloLens 2'nizin etkin bir İnternet bağlantısı olduğunda kullanılabilir.

## <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici


Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR ile tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler HoloLens 2 tarafından da de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimlerini de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak HoloLens 2 müşterilerinin denemesi için yeni artırılmış ve karma gerçeklik çevreleyici deneyimler edinecek!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve HoloLens 2'deki yeni Microsoft Edge otomatik olarak yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

### <a name="how-to-use-webxr"></a>WebXR kullanma

1. WebXR desteği olan bir web sitesine gidin.
1. Web sitesindeki **VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel temsili Web sitesi başına değişebilir, ancak şuna benzer olabilir:

    ![VR düğmesi örneği girin](images/75px-enter-vr.png)

1. Belirli bir etki alanında bir WebXR deneyimini ilk kez başlatmaya çalıştığınızda, tarayıcı bir derinlikli görünüm girip **Izin ver**' i seçeceğiz.
1. Deneyimi işlemek için [HoloLens 2 hareketlerini](hololens2-basic-usage.md#the-hand-tracking-frame) kullanın.
1. Deneyimde **Çıkış** düğmesi yoksa, giriş geri döndürmek için [Başlangıç hareketini](hololens2-basic-usage.md#start-gesture) kullanın.

**Önerilen WebXR örnekleri**
- 360 Görüntüleyici (sonraki bölüme bakın)
- [XR Dinoı](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>360 görüntüleyicisini kullanma

1. YouTube 'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde, karma gerçeklik kulaklık düğmesini seçin:

    ![360 görüntüleyicisini etkinleştirmek için düğme](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyici 'yi ilk kez başlattığınızda, tarayıcı bir tam ekran görünümü girmeye izin ister. **Izin ver**' i seçin.
1. Kayıttan yürütme denetimlerini görüntülemek için [AIR 'e dokunun](hololens2-basic-usage.md#select-using-air-tap) . [El ışınları ve AIR ' i dokunarak](hololens2-basic-usage.md#select-using-air-tap) Oynat/Duraklat, ileri/geri atla, açıklamalı alt yazıları aç/kapat veya deneyimi Durdur (tam ekran görünümünden çıkar). Kayıttan yürütme denetimleri birkaç saniyelik işlem yapılmadan sonra kaybolacaktır.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Popüler WebXR ve 360 Görüntüleyicisi bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak, kare hızı kesilebilir veya stutter.
- WebXR 'deki ifade eden her bir el ile yönelik destek, varsayılan olarak etkin değildir. Geliştiriciler, "WebXR el girişi" ni etkinleştirerek edge://flags aracılığıyla desteği etkinleştirebilir.
- YouTube dışındaki Web sitelerinden 360 video, beklendiği gibi çalışmayabilir.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Viewer hakkında geri bildirim sağlama

Lütfen yeni Microsoft Edge 'deki **geri bildirim gönder** özelliği aracılığıyla ekibimize geri bildirim ve hata paylaşabilirsiniz.
