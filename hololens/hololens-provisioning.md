---
title: Sağlama HoloLens kullanarak yapılandırma (HoloLens)
description: Windows sağlama, IT yöneticilerinin görüntüleme olmadan son kullanıcı cihazlarını yapılandırmalarını kolaylaştırır.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9474774b47858003cc11363a5f325f589b0732ab
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427381"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Sağlama HoloLens kullanarak yapılandırma

[Windows sağlama,](/windows/configuration/provisioning-packages/provisioning-packages) IT yöneticilerinin görüntüleme olmadan son kullanıcı cihazlarını yapılandırmalarını kolaylaştırır. Windows Yapılandırma Tasarımcısı, daha sonra sağlama paketlerinde yerleşik olarak bulunan görüntüleri ve çalışma zamanı ayarlarını yapılandırmak için kullanılan bir araçtır.

Sağlama paketinde HoloLens yapılandırmalardan bazıları şunlardır:

- [Windows Holographic for Business'a yükseltme](hololens1-upgrade-enterprise.md)
- Yerel hesap ayarlama
- Ağ bağlantısı Wi-Fi ayarlama
- Cihaza sertifika uygulama
- Geliştirici Modunu Etkinleştirme
- Ayrıntılı yönergelerimizi izleyerek Bilgi Noktası [modunu yapılandırma.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

## <a name="provisioning-package-hololens-wizard"></a>Paket sağlama HoloLens sihirbazı

HoloLens sihirbazı, bir sağlama paketinde aşağıdaki ayarları yapılandırmanıza yardımcı olur:

- Enterprise sürümüne yükseltme

    > [!NOTE]
    > Bu yalnızca 1. nesil HoloLens için kullanılmalıdır. Ayarlar paketinde yer alan tüm sürümler, yalnızca sağlama paketinin Windows Holographic for Business'ye sürüm yükseltme lisansına sahip olması veya cihazın [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

- İlk deneyimi HoloLens (OOBE) yapılandırma
- Ağ Wi-Fi yapılandırma
- Cihazı Azure Active Directory veya yerel bir hesap oluşturun
- Sertifika ekleme
- Geliştirici Modunu Etkinleştirme
- Ayrıntılı yönergeleri izleyerek bilgi noktası [modunu yapılandırma.](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)

> [!WARNING]
> Sihirbazlardan herhangi birini Windows kayıt Windows 10 yapılandırmak için Azure Active Directory Yapılandırma Tasarımcısı'nı çalıştırmanız gerekir.

Sağlama paketleri yönetim yönergelerini ve ilkelerini, özel ağ bağlantılarını ve ilkelerini ve daha fazlasını içerebilir.

> [!TIP]
> Masaüstü sihirbazını kullanarak ortak ayarlarla bir paket oluşturun ve ardından diğer ayarları, uygulamaları, ilkeleri vb. eklemek için gelişmiş düzenleyiciye geçiş yapın.

## <a name="steps-for-creating-provisioning-packages"></a>Sağlama paketleri oluşturma adımları

1. **1. Seçenek:** [Microsoft Store.](https://www.microsoft.com/store/apps/9nblggh4tx22) Bu, HoloLens 2 özelliklerini içerir.
2. **2. Seçenek:** Windows için Windows [Değerlendirme ve Dağıtım Seti'Windows 10.](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit) Windows ADK'den Windows Yapılandırma Tasarımcısı'Windows, Yüklemek  istediğiniz özellikleri seçin **iletişim kutusundan Yapılandırma Tasarımcısı'ı** seçin. Bu seçenek 2 HoloLens dahil değildir.

> [!NOTE]
> Windows Yapılandırma Tasarımcısı'nda erişmesi gereken çevrimdışı bir bilgisayar kullanmak istiyorsanız Gelişmiş Kurtarma Yardımcısı için [çevrimdışı uygulama yükleme(hololens-recovery.md#downloading-arc-without-using-the-app-store) yönergelerini izleyin. Yapılandırma Windows seçiminizi yapın. 

### <a name="2-create-the-provisioning-package"></a>2. Sağlama paketini oluşturma

Windows Configuration Designer aracını kullanarak bir sağlama paketi oluşturun.

1. Windows Yapılandırma Tasarımcısı'Windows açın (varsayılan olarak, %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Cihaz **sağlama'HoloLens seçin.**

   ![ICD başlatma seçenekleri.](images/icd-create-options-1703.png)

3. Projenize bir ad girin ve Son'a **seçin.**

4. Başlarken sayfasındaki **yönergeleri okuyun ve** Sonraki'yi **seçin.** Masaüstü sağlama sayfaları aşağıdaki adımlarda size yol sağlar.
  
> [!IMPORTANT]
> Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir. .ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.

### <a name="configure-settings"></a>Ayarları yapılandırma

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens sürümünü yükseltmek için kurumsal lisans dosyasına göz HoloLens seçin.</br></br>İlk deneyimin bölümlerini gizlemek <strong>için Evet</strong> <strong>veya</strong> Hayır'a da geçiş sabilirsiniz.</br></br>Cihazı bir ağ bağlantısına gerek kalmadan ayarlamak için Wi-Fi atla'ya Wi-Fi <strong>açık olarak</strong> <strong>ayarlayın.</strong></br></br>Cihazın kullanılacak olduğu bölgeyi ve saat dilimini seçin. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Bu bölümde, cihazın otomatik olarak bağlanması Wi-Fi kablosuz ağın ayrıntılarını girebilirsiniz. Bunu yapmak için <strong>Açık'ı</strong>seçin, SSID'yi, ağ türünü<strong>(</strong> Açık veya <strong>WPA2-Kişisel</strong>) ve kablosuz ağın parolasını girin <strong>(WPA2-Kişisel</strong>ise).</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Cihazı cihaza Azure Active Directory veya cihazda yerel bir hesap oluşturabilirsiniz</br></br>Toplu Azure AD Windows yapılandırmak için bir Yapılandırma Tasarımcısı sihirbazını kullanmadan önce, <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">azure AD'ye katılmayı kurumda ayarlayın.</a> Azure AD <strong>kiracınız için kullanıcı</strong> başına en fazla cihaz sayısı ayarı, sihirbazda kaç kez toplu belirteci kullanılacazını belirler. Cihazı Azure AD'ye kaydetmek için bu seçeneği belirleyin ve sihirbazı kullanarak elde edersiniz toplu belirteç için kolay bir ad girin. Belirteç için bir sona erme tarihi ayarlayın (belirteci almak için en fazla 30 gündür). Toplu <strong>belirteci al'ı seçin.</strong> Oturum <strong>&#39;al</strong> penceresinde, bir cihazı Azure AD'ye katma izinlerine sahip bir hesap girin ve ardından parolayı girin. Yapılandırma <strong>Tasarımcısı'nda</strong> gerekli Windows vermek için Kabul Et'i seçin. </br></br>Yerel hesap oluşturmak için bu seçeneği belirleyin ve bir kullanıcı adı ve parola girin. </br></br><strong>Önemli:</strong> <br />(Windows 10 sürüm 1607) Sağlama paketinde yerel bir hesap seniz, 42 günde bir <strong>Ayarlar</strong> uygulamayı kullanarak parolayı değiştirebilirsiniz. Parola bu süre boyunca değişmemişse hesap kilitlenmiş ve oturum açamıyor olabilir.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Cihazı bir sertifika ile sağlama için Sertifika <strong>ekle'ye tıklayın.</strong> Sertifika için bir ad girin ve ardından kullanılacak sertifikaya gidin ve sertifikayı seçin.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Uygulama üzerinde <strong>Geliştirici</strong> Modunu <strong>etkinleştirmek</strong> için Evet veya Hayır HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Geliştirici Modu hakkında daha fazla bilgi edinebilirsiniz.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Sağlama paketinizi korumak için parola ayarlamayın. Sağlama paketi bir parolayla korunuyorsa, HoloLens sağlama başarısız olur.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Bitirdikten sonra Oluştur'a **seçin.** Yalnızca birkaç saniye sürer. Paket lendiğinde, paketin depolandığı konum sayfanın alt kısmında köprü olarak görüntülenir.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Gelişmiş sağlamayı kullanarak HoloLens için sağlama paketi oluşturma

> [!NOTE]
> Gelişmiş sağlama'da oluşturmakta  olduğunu bir sağlama paketinin bir Windows Holographic for Business (1. nesil) için başarılı bir şekilde geçerli olmak için HoloLens yükseltme lisansı içermesi gerekli değildir. [daha fazla bilgi Windows Holographic for Business için HoloLens (1. nesil)](hololens1-upgrade-enterprise.md).

1. Yapılandırma Tasarımcısı Windows sayfasında Gelişmiş **sağlama'ya tıklayın.**
2. Proje **ayrıntılarını girin penceresinde** projeniz için bir ad ve projenizin konumunu belirtin. İsteğe bağlı olarak, projenizi açıklamak için kısa bir açıklama girin.

3. **İleri**’yi seçin.

4. Görüntülemek ve **yapılandırmak için hangi ayarların seç penceresinde,** **Windows 10 Holographic'ı** ve ardından Sonraki'yi **seçin.**

5. **Son**'u seçin.

6. Çalışma **zamanı ayarlarını** genişletin ve bu makalenin devamlarında açıklanan [ayarlardan herhangi birini kullanarak paketi özelleştirin.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Windows 10 sürüm 1607) Sağlama paketinde yerel bir hesap seniz, 42 günde bir **Ayarlar** uygulamayı kullanarak parolayı değiştirebilirsiniz. Parola bu süre boyunca değişmemişse hesap kilitlenmiş ve oturum açamıyor olabilir. Kullanıcı hesabı kilitliyse, tam bir cihaz [kurtarması gerçekleştirmeniz gerekir.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Dosya **Kaydet'i**  >  **seçin.**

8. Proje dosyalarının hassas bilgiler içere uyarısına bakın ve Tamam'ı **seçin.**

    > [!IMPORTANT]
    > Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir. .ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.

9. Sağlama **paketini dışarı**  >  **aktar'ı seçin.**

10. **Sahip'i** **IT Yöneticisi olarak değiştirme.** Bu, bu sağlama paketinin öncelini, diğer kaynaklardan bu cihaza uygulanan sağlama paketlerinden daha yüksek ayarlar. **İleri**’yi seçin.

11. Paket Sürümü için **bir değer ayarlayın.**

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilirsiniz ve sürüm numarasını, daha önce uygulanan paketleri güncelleştirmek için değiştirebilirsiniz.

12. Sağlama **paketi için güvenlik ayrıntılarını seçin'de, Sonraki'yi** **seçin.**

    > [!WARNING]
    > Sağlama paketini şifrelersanız, HoloLens sağlama başarısız olur.  

13. Hazır **olduktan** sonra sağlama paketinin gitmelerini istediğiniz çıkış konumunu belirtmek için Sonraki'yi seçin. Varsayılan olarak, Windows Tasarımcısı proje klasörünü çıkış konumu olarak kullanır.

    İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için **Araştır** ' ı seçebilirsiniz.

14. **İleri**’yi seçin.

15. Paketi oluşturmaya başlamak için **Oluştur** ' u seçin. Proje bilgileri yapı sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

16. Oluşturma tamamlandığında **son**' u seçin.

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>kurulum sırasında HoloLens bir sağlama paketi uygulama

Windows Holographic, sürüm 2004 veya derleme [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) ya da sonraki sürümlerde HoloLens 2 cihaz, bir sağlama paketi uygulamak için bir USB sürücü kullanabilir. . Ppkg dosyasını USB sürücünün köküne kopyalamanız yeterlidir. Sağlama paketleri, yalnızca USB sürücünün kök dizininde yer alıyorsa uygulanır. Birden çok sağlama paketi ardışık olarak uygulanacak.

[Windows Holographic sürümü 20h2](hololens-release-notes.md#windows-holographic-version-20h2) veya üzeri üzerindeki HoloLens 2 cihaz, bu işlemi otomatik hale getirmek ve basitleştirmek için daha yeni özelliklere sahiptir. Lütfen aşağıdaki bölümleri gözden geçirin:

- [Sağlamayı USB 'den otomatik olarak başlatma](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE 'de sağlama paketlerini otomatik onaylama](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Kullanıcı arabirimi kullanmadan otomatik sağlama](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. cihazı bir bilgisayara bağlamak için usb kablosunu kullanın (veya yukarıda bahsedilen HoloLens 2 için usb sürücüsü) ve ardından cihazı başlatın. OOBE 'nin **ilk ınteractable** son sayfasından devam etmez.
    - HoloLens (1. genel) sayfasında bu sayfa mavi bir kutu içerir.
    - HoloLens 2 ' de bu sayfada hummingbird bulunur.

2. **Sesi** ve **Güç** düğmelerini aynı anda bir daha bas ve serbest bırakın.

3. HoloLens, bilgisayardaki dosya gezgini 'nde bir cihaz olarak gösterilir.

4. Dosya Gezgini 'nde, sağlama paketini (. ppkg) cihaz depolamasına sürükleyin ve bırakın.

5. OOBE 'nin **ilk ınteractable anı** sayfasında, **birimi aşağı** ve **Güç** düğmelerine aynı anda tekrar basın ve serbest bırakın.

6. Cihaza güveniyorsanız ve uygulamayı uygulamak istiyorsanız bu cihaz sizi sorar. Pakete güvendiğinizden emin olun.

7. Paketin başarıyla uygulanıp uygulanmadığını görürsünüz. Başarısız olursa paketinizi düzelleyebilir ve yeniden deneyebilirsiniz. Başarılı olduysa, OOBE ile devam edin.

> [!NOTE]
> Cihaz 2016 Ağustos 'Tan önce satın alındıysa, Microsoft hesabı kullanarak cihazda oturum açmanız gerekir, en son işletim sistemi güncelleştirmesini alabilir ve ardından sağlama paketini uygulamak için işletim sistemini sıfırlayabilirsiniz.

### <a name="auto-launch-provisioning-from-usb"></a>Sağlamayı USB 'den otomatik olarak başlatma

- Otomatik süreçler, sağlama paketleri içeren USB sürücüleri OOBE sırasında kullanıldığında daha az kullanıcı etkileşimine izin verir.

Bu sürümden önce, bir düğme bileşimini kullanarak sağlamak için kullanıcıların, OOBE sırasında sağlama ekranını el ile başlatması gerekiyordu. Artık kullanıcılar, USB depolama sürücüsünde bir sağlama paketi kullanarak düğme bileşimini atlayabilir.

1. OOBE 'nin ilk ınteractable 'ı sırasında sağlama paketiyle USB sürücüsünü takın
1. Cihaz sağlanmaya hazır olduğunda, isteği sağlama sayfasıyla otomatik olarak açar.

Note: cihaz önyüklenirken bir USB sürücü takıldıysa, OOBE mevcut USB depolama cihazını numaralandırır ve takılmakta olan ek için izleme de yapılır.

[OOBE sırasında sağlama paketleri uygulama](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)hakkında bilgi edinin.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE 'de sağlama paketlerini otomatik onaylama
- Otomatik süreç daha az kullanıcı etkileşimine izin verirken, sağlama paketi sayfası görüntülendiğinde, listelenen tüm paketleri otomatik olarak uygular.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerinin uygulanması için OOBE 'nin otomatik olarak başlatılması için önce 10 saniye geçmesi gerekir. Kullanıcılar, bekledikleri paketleri doğruladıktan sonra bu 10 saniye içinde yine de onaylama veya iptal edebilir.

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

Cihazınız artık yapılandırıldı ve sağlama başarılı ekranı görüntülenir.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>kurulum sonrasında HoloLens bir sağlama paketi uygula/kaldır

> [!NOTE]
> bu adımlar, Windows Holographic, sürüm 1809 ve üzeri sürümlerde tüm HoloLens 2 cihazlara ve HoloLens (1. gen) cihazlara uygulanır.

Bilgisayarınızda şu adımları izleyin:
1. [HoloLens sihirbazını kullanarak HoloLens için sağlama paketi oluşturma](hololens-provisioning.md)bölümünde açıklandığı gibi bir sağlama paketi oluşturun.
2. bir USB kablosu kullanarak HoloLens cihazını bir bilgisayara Bağlan. HoloLens, bilgisayardaki dosya gezgini 'nde bir cihaz olarak gösterilir.
3. Sağlama paketini HoloLens Belgeler klasörüne sürükleyip bırakın.

HoloLens, aşağıdaki adımları izleyin:
1.   >    >  **işe veya okula erişim** Ayarlar hesaplara gidin. 
2. **ilgili Ayarlar**, **sağlama paketi ekle veya kaldır**' ı seçin.
3. Bir sonraki sayfada, **bir paket Ekle** ' yi seçerek dosya seçiciyi başlatın ve sağlama paketinizi seçin. Klasör boşsa, **Bu cihazı** seçtiğinizden ve **Belgeler**' i seçtiğinizden emin olun.

Paketiniz uygulandıktan sonra, **yüklü paketler** listesinde görüntülenir. Paket ayrıntılarını görüntülemek veya paketi cihazdan kaldırmak için, listelenen paketi seçin.

## <a name="what-you-can-configure"></a>Yapılandırabileceğiniz ayarlar

Sağlama paketleri yapılandırma hizmeti sağlayıcılarını (CSP) kullanır. CSP 'Ler hakkında bilgi sahibi değilseniz bkz. [BT uzmanları için yapılandırma hizmeti sağlayıcılarına (CSP 'ler) giriş](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers).

Windows yapılandırma tasarımcısı ' nda, Windows Holographic için bir sağlama paketi oluşturduğunuzda, **kullanılabilir özelleştirmelerdeki** ayarlar [Windows Holographic ' de desteklenen csp](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)'lere dayanır. Aşağıdaki tabloda HoloLens için yapılandırmak isteyebileceğiniz ayarlar açıklanmaktadır.

![HoloLens için ortak çalışma zamanı ayarları.](images/icd-settings.png)

| Ayar | Açıklama |
| --- | --- |
| **Sertifikalar** | HoloLens bir sertifika dağıtın.  |
| **ConnectivityProfiles** | HoloLens için bir Wi-Fi profili dağıtın.   |
| **EditionUpgrade** | [Windows Holographic for Business yükseltin.](hololens1-upgrade-enterprise.md)  |
| **İlkeler** | HoloLens geliştirici moduna izin verin veya bunu engelleyin. [Windows Holographic for Business tarafından desteklenen ilkeler](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Sağlama paketi aracılığıyla uygulama yüklemesi

uygulamalar, HoloLens 2 cihazda sağlama paketleri aracılığıyla yüklenebilir. Bu, uygulamalarınızı dağıtmanıza yardımcı olması için kullanabileceğiniz kolay bir şekilde yeniden kullanılabilir paket sağlar. [Sağlama paketleri aracılığıyla uygulama dağıtmaya](app-deploy-provisioning-package.md)yönelik tüm yönergeleri okuyun.  

> [!NOTE]
> HoloLens (1. gen), bir sağlama paketi kullanarak uygulamaları (**üniversalappinstall**) yüklemeye yönelik sınırlı desteğe sahiptir. HoloLens (1. gen) cihazlar yalnızca yalnızca OOBE ve yalnızca kullanıcı bağlamı yüklemeleri ile ppkg aracılığıyla uygulama yüklemeyi destekler.
