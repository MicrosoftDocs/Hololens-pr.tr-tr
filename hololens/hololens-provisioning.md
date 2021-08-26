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
ms.openlocfilehash: 999e16f117e4f0838c4a0cb6d6bafcbbf72e1d5a
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859043"
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

   ![ICD başlatma seçenekleri](images/icd-create-options-1703.png)

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
> Gelişmiş sağlama'da oluşturmakta  olduğunu bir sağlama paketinin bir HoloLens (1. nesil) için başarılı bir şekilde geçerli olmak üzere Windows Holographic for Business sürümüne yükseltme lisansı içermesi gerekli değildir. [daha fazla bilgi Windows Holographic for Business için HoloLens (1. nesil)](hololens1-upgrade-enterprise.md).

1. Yapılandırma Tasarımcısı Windows sayfasında Gelişmiş **sağlama'ya tıklayın.**
2. Proje **ayrıntılarını girin penceresinde** projeniz için bir ad ve projenizin konumunu belirtin. İsteğe bağlı olarak, projenizi açıklamak için kısa bir açıklama girin.

3. **İleri**’yi seçin.

4. Görüntülemek ve **yapılandırmak için hangi ayarların yapılandırılımlarını** seçin penceresinde **Windows 10 Holographic'yi** ve ardından Sonraki'yi **seçin.**

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

    İsteğe bağlı olarak, varsayılan çıkış **konumunu** değiştirmek için Gözat'ı seçin.

14. **İleri**’yi seçin.

15. Paketi **derlemeye** başlamak için Derleme'yi seçin. Proje bilgileri derleme sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

16. Derleme tamamlandığında Son'a **seçin.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Kurulum sırasında HoloLens paketi uygulama

Windows HoloLens Holographic sürüm 2004 veya derleme [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki sürümler üzerinde 2 cihaz, sağlama paketi uygulamak için USB sürücüsü kullanabilir. .ppkg dosyasını USB sürücünün köküne kopyalamanız gerekir. Sağlama paketleri yalnızca USB sürücünün kökünde yer alan paketler için uygulanır. Mevcut birden çok sağlama paketi sırayla uygulanır.

HoloLens Holographic sürüm [20H2 Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) veya sonraki sürümlerde 2 cihaz, bu işlemi kolaylaştırmanıza ve basitleştirmeye yardımcı olmak için daha yeni özelliklere sahiptir. Lütfen aşağıdaki bölümleri gözden geçirebilirsiniz:

- [USB'den sağlamayı otomatik başlatma](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE'de sağlama paketlerini otomatik olarak onaylama](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Cihazı bir bilgisayara (veya yukarıda belirtildiği gibi HoloLens 2 için USB sürücüsüne) bağlamak için USB kablosunu kullanın ve ardından cihazı başlatabilirsiniz. OOBE'nin **İlk etkileşime geçilebilir an** sayfasını geçerek devam edin.
    - Bu HoloLens (1. nesil) sayfasında mavi bir kutu vardır.
    - Bu HoloLens 2. sayfada yer alan kuş kuşlarını içerir.

2. Volume Down ve Power düğmelerine **aynı anda kısa** bir süre **basın** ve bırakın.

3. HoloLens, bilgisayarınızda bir Dosya Gezgini olarak gösterir.

4. Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.

5. OOBE'nin **İlk etkileşime değiştirilebilir** an sayfasındayken, Ses Düzeyi Kapalı ve Güç düğmelerine aynı anda kısa bir süre basın ve bırakın.  

6. Cihaz, pakete güvenmiyorsanız ve bunu uygulamak mı istiyorum? sorularını sorar. Pakete güvenen bir onaylayın.

7. Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir. Başarısız olursa, paketinizi düzeltebilir ve yeniden sınabilirsiniz. Başarılı olursa OOBE ile devam edin.

> [!NOTE]
> Cihaz Ağustos 2016'dan önce satın aldıysanız, Microsoft hesabı kullanarak cihazda oturum açmanız, en son işletim sistemi güncelleştirmesini almanız ve ardından sağlama paketini uygulamak için işletim sistemini sıfırlamanız gerekir.

### <a name="auto-launch-provisioning-from-usb"></a>USB'den sağlamayı otomatik başlatma

- Otomatikleştirilmiş işlemler, OOBE sırasında Sağlama Paketleri ile USB Sürücüleri kullanılırken daha az kullanıcı etkileşimi sağlar.

Bu sürümden önce kullanıcıların bir düğme birleşimi kullanarak sağlama yapmak için OOBE sırasında sağlama ekranı el ile başlatmaları gerekti. Artık kullanıcılar USB depolama sürücüsünde Sağlama Paketi kullanarak düğme birleşimini atlar.

1. OOBE'nin ilk etkileşime geçme anları sırasında USB sürücüyü sağlama paketiyle takın
1. Cihaz hazır olduğunda, sağlama sayfasıyla otomatik olarak istemi açar.

Not: Cihaz önyüklerken bir USB sürücü takılı bırakıldı ise OOBE mevcut USB depolama cihazını numaralandıracak ve eklerinin takılı olduğunu izler.

[OOBE sırasında sağlama paketlerini uygulama hakkında bilgi için okuyun.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE'de sağlama paketlerini otomatik olarak onaylama
- Daha az kullanıcı etkileşimi sağlayan otomatik işlem, Sağlama Paketi sayfası görüntülendiğinde listelenen tüm paketleri otomatik olarak uygulayacaktır.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerini otomatik olarak uygulamaya başlamadan önce OOBE 10 saniye geri sayar. Kullanıcılar, beklendikten sonra bu 10 saniye içinde onaylayabilir veya iptal edebilir.

### <a name="automatic-provisioning-without-using-ui"></a>Kullanıcı arabirimini kullanmadan otomatik sağlama
- Sağlama için azaltılmış cihaz etkileşimleri için birleşik otomatik işlemler. 

Kullanıcı, USB cihazlarından sağlamanın otomatik başlatılmasını ve paketlerin otomatik olarak onayını birleştirerek, HoloLens 2 cihazını cihazın kullanıcı arabirimini kullanmadan ve hatta cihazı takmadan otomatik olarak s sağlamayı da sağlar. Birden çok cihaz için aynı USB sürücü ve sağlama paketini kullanmaya devam edersiniz. Bu, aynı alanda aynı anda birden çok cihaz dağıtmak için kullanışlıdır. 

1. [Windows](hololens-provisioning.md) [Configuration Designer'ı kullanarak Sağlama Paketi oluşturun.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [2 HoloLens](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 veya daha yeni bir derlemeye flash olarak söner.](https://aka.ms/hololens2previewdownload) 
1. Gelişmiş [Kurtarma Yardımcı,](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın usb-C kablolarını çıkarın ve yanıp sönmeyi tamamlandıktan sonra. 
1. USB sürücülerinizi cihaza takın.
1. 2 HoloLens cihaz OOBE'de ilk kez başlatılırsa, USB sürücüsünde sağlama paketini otomatik olarak algılar ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz sağlama paketini otomatik olarak uygulayacaktır. 

Cihazınız artık yapılandırılmıştır ve Sağlama Başarılı ekranı görüntülenir.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Kurulumdan sonra bir sağlama paketini HoloLens/kaldırma

> [!NOTE]
> Bu adımlar Holographic, HoloLens 1809 ve üzeri HoloLens (1. nesil) cihazları ve Windows 2. nesil cihazlar için geçerlidir.

Bilgisayarınızda şu adımları izleyin:
1. HoloLens sihirbazını kullanarak bir sağlama paketi oluşturma sayfasında açıklandığı gibi bir HoloLens [paketi oluşturun.](hololens-provisioning.md)
2. Bağlan HoloLens USB kablosu kullanarak bir bilgisayara bağlayın. HoloLens, bilgisayarınızda bir Dosya Gezgini olarak gösterir.
3. Sağlama paketini sürükleyip dosyanın Belgeler klasörüne HoloLens.

Kendi HoloLens şu adımları izleyin:
1. Hesaplara **Ayarlar**  >  **İş veya** okula  >  **erişme'ye gidin.** 
2. İlgili **Ayarlar'de** Sağlama **paketi ekle veya kaldır'ı seçin.**
3. Sonraki sayfada Paket **ekle'yi seçerek** dosya seçiciyi açın ve sağlama paketinizi seçin. Klasör boşsa Bu Cihaz'ı ve Belgeler'i **seçin.** 

Paketiniz uygulandıktan sonra Yüklü paketler listesinde **görünür.** Paket ayrıntılarını görüntülemek veya paketi cihazdan kaldırmak için listelenen paketi seçin.

## <a name="what-you-can-configure"></a>Yapılandırabileceğiniz ayarlar

Paket sağlama, yapılandırma hizmeti sağlayıcılarından (CSP) kullanılır. CSP'ler hakkında bilgi sahibi değilsanız bkz. IT profesyonelleri için yapılandırma hizmeti [sağlayıcılarına (CSP'ler) giriş.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

Windows Yapılandırma Tasarımcısı'nda, Windows Holographic için bir sağlama paketi yapılandırmasını yapılandırmasını tamamlarsanız, Kullanılabilir özelleştirmeler sayfasındaki [ayarlar, Windows Holographic'te desteklenen CSP'leri temel almaktadır.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)  Aşağıdaki tabloda, uygulama için yapılandırmak istediğiniz ayarlar HoloLens.

![Uygulama için ortak çalışma zamanı HoloLens](images/icd-settings.png)

| Ayar | Açıklama |
| --- | --- |
| **Sertifikalar** | Sertifikayı HoloLens.  |
| **ConnectivityProfiles** | Bir Wi-Fi profili HoloLens.   |
| **EditionUpgrade** | [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **İlkeler** | Uygulama üzerinde geliştirici moduna izin HoloLens. [Windows Holographic for Business tarafından desteklenen ilkeler](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Sağlama Paketi aracılığıyla uygulama yükleme

Uygulamalar, 2 cihaza paket sağlama HoloLens yükleyebilir. Bu, uygulamalarınızı dağıtmanıza yardımcı olmak için kullanabileceğiniz kolayca yeniden kullanılabilir bir paket sağlar. Sağlama Paketleri aracılığıyla uygulama [dağıtmaya ilişkin tam yönergeleri okuyun.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).** HoloLens (1. nesil) cihazlar yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.
