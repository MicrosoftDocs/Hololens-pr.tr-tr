---
title: Yeni Microsoft Edge
description: Yeni Edge uygulaması hakkında bilgi
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, uç, İnternet, tarayıcı
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 41978c626328903cf480a3315d56841f187bc123
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640194"
---
# <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge logosunu yeni Microsoft Edge animasyonu](images/new-edge.gif)

Yeni [Microsoft Edge, müşteriler için daha Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) uyumluluk ve web geliştiricileri için web'in daha az parçalanması için yeni bir açık kaynak proje benimsemektedir.

[Holographic Windows sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile, yeni Microsoft Edge ilk kez HoloLens 2 müşteri tarafından kullanılabilir! Lütfen yeni çalışmadaki Geri Bildirim  Gönder özelliği aracılığıyla veya Microsoft Edge ile [Geri Bildirim Merkezi.](hololens-feedback.md)

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde Microsoft Edge eski sürümlerin [yerini](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Yeni Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi](images/new_edge_logo.png) (mavi ve yeşil bir kısma simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, ÖNCEKI 2. HoloLens'da ESKI Microsoft Edge'da mevcut olandan çok daha geniş bir tarayıcı Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Enterprise belgeleri](/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge, ekibimiz her yeni ilkenin 2. bir ilke üzerinde HoloLens garanti HoloLens. Ancak, daha önce Microsoft Edge 2'de desteklenen her eski Microsoft Edge ilkenin eşdeğerini test ettik ve HoloLens doğruladık. 2 [Microsoft Edge'in eski sürümü Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski Microsoft Edge tarayıcı ilkesine eşdeğer yeni Microsoft Edge bulmak için bkz. HoloLens eşlemesi.
>
> 2. Microsoft Edge en az iki yeni *ilke* ilke HoloLens:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de Microsoft Edge yeni HoloLens beklenilenler

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
- "Beni takip et" modundaki bir tarayıcı penceresinden ses çalma sırasında, "Beni takip et" modunu devre dışı bıraksanız da ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu atlayabilirsiniz.
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerinde beklenmedik bir şekilde devre dışı bırakılamayacak şekilde etkileşebilirsiniz. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

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

**Windows Cihaz Portalı ile pc üzerinden yükleme [](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (2. HoloLens geliştirici modunun etkinleştirilmesi gerekir)**
  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki açılan ok düğmesini seçin.
  1. Açılan **HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) dosyasını Windows Cihaz Portalı 2'ye yüklemek için bilgisayarınızda HoloLens kullanın.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) Microsoft Edge engellemek için güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](/deployedge/microsoft-edge-security-endpoints)

için kullanılabilir olan uç noktalar hakkında [daha fazla bilgi HoloLens.](hololens-offline.md)

## <a name="install-web-apps"></a>Web uygulamalarını yükleme
 > [!Note]
> Holographic [Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)sürümünden Office web uygulaması artık önceden yüklenmez. 

Yeni Edge'i kullanarak yeni uygulamalarla birlikte web Microsoft Store yükleyebilirsiniz. Örneğin, Microsoft Office veya SharePoint barındırılan dosyaları görüntülemek ve düzenlemek için OneDrive. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya Office düğmesini seçin.   Onaylamak **için Yükle'yi** seçin.
> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca 2. HoloLens etkin bir İnternet bağlantısı olduğunda kullanılabilir.

## <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici


Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR'nin (görünüm alanınızı bir sanal ortamla değiştirir) ile tasarlanmıştır, ancak bu deneyimler 2. HoloLens de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimlerini de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak 2 müşterinin denemesi için yeni artırılmış ve karma gerçeklik HoloLens deneyimler gelmesini bekliyor!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve 2. Microsoft Edge yeni HoloLens yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

### <a name="how-to-use-webxr"></a>WebXR'i kullanma

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

### <a name="how-to-use-360-viewer"></a>360 Görüntüleyici kullanma

1. YouTube'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde karma gerçeklik başlığı düğmesini seçin:

    ![360 Görüntüleyiciyi etkinleştirme düğmesi](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyiciyi ilk kez başlatmaya çalışırsanız tarayıcı, çevreleyici bir görünüm girmek için onay sorar. İzin **Ver'i seçin.**
1. [Kayıttan yürütme](hololens2-basic-usage.md#select-using-air-tap) denetimlerini açmak için havadan dokunma. El [işleyicileri](hololens2-basic-usage.md#select-using-air-tap) ve havadan dokunarak oynatma/duraklatma, ileri/geri atlama, açıklamalı alt yazıları açma/kapatma veya deneyimi durdurma (çevreleyici görünümden çıkar) için kullanın. Kayıttan yürütme denetimleri birkaç saniyelik bir sürenin ardından kaybolur.

### <a name="top-webxr-and-360-viewer-known-issues"></a>En önemli WebXR ve 360 Görüntüleyici bilinen sorunları
- WebXR deneyiminin karmaşıklığına bağlı olarak kare hızı düşerek veya düşerek düşebilirsiniz.
- WebXR'de ifadeli el ortakları için destek varsayılan olarak etkin değildir. Geliştiriciler "WebXR El Edge://flags" ayarını etkinleştirerek destek hizmetleri aracılığıyla destek etkinleştirerek destek sağ kullanabilir.
- YouTube dışında web sitelerinden 360 video beklendiği gibi çalışmayabilir.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici hakkında geri bildirim sağlama

Lütfen yeni çalışmadaki Geri Bildirim Gönder özelliği **aracılığıyla geri bildirimi ve** hataları ekibimizle Microsoft Edge.
