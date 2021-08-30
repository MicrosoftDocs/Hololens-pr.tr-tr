---
title: sağlama paketi kullanarak HoloLens yapılandırma (HoloLens)
description: Windows sağlama, bt yöneticilerinin son kullanıcı cihazlarını ımaging olmadan yapılandırmasını kolaylaştırır.
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189010"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>sağlama paketi kullanarak HoloLens yapılandırma

[Windows sağlama](/windows/configuration/provisioning-packages/provisioning-packages) , bt yöneticilerinin son kullanıcı cihazlarını ımaging olmadan yapılandırmasını kolaylaştırır. Windows Yapılandırma Tasarımcısı, daha sonra sağlama paketlerine yerleşik olarak bulunan resimleri ve çalışma zamanı ayarlarını yapılandırmaya yönelik bir araçtır.

bir sağlama paketinde uygulayabileceğiniz HoloLens yapılandırmalarından bazıları şunlardır:

- [Windows Holographic for Business](hololens1-upgrade-enterprise.md) yükseltin
- Yerel hesap ayarlama
- Wi-Fi bağlantısını ayarlama
- Cihaza sertifika uygulama
- Geliştirici modunu etkinleştir
- [Ayrıntılı yönergelerinizi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)Izleyerek bilgi noktası modunu yapılandırın.

## <a name="provisioning-package-hololens-wizard"></a>paketi HoloLens sağlama sihirbazı

HoloLens sihirbazı, bir sağlama paketinde aşağıdaki ayarları yapılandırmanıza yardımcı olur:

- Enterprise sürümüne yükseltme

    > [!NOTE]
    > bu yalnızca HoloLens 1. gen cihazları için kullanılmalıdır. bir sağlama paketindeki Ayarlar yalnızca, sağlama paketi Windows Holographic for Business sürümüne bir sürüm yükseltme lisansı içeriyorsa veya [cihaz zaten Windows Holographic for Business sürümüne yükseltildiyse](hololens1-upgrade-enterprise.md)uygulanır.

- HoloLens ilk deneyimi yapılandırın (OOBE)
- Wi-Fi ağını yapılandırma
- cihazı Azure Active Directory kaydetme veya yerel hesap oluşturma
- Sertifika ekle
- Geliştirici modunu etkinleştir
- [Ayrıntılı yönergeleri](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)izleyerek bilgi noktası modunu yapılandırın.

> [!WARNING]
> sihirbazları kullanarak Azure Active Directory kaydını yapılandırmak için Windows 10 üzerinde Windows Configuration Designer ' i çalıştırmanız gerekir.

Sağlama paketleri yönetim yönergelerini ve ilkelerini, özel ağ bağlantılarını ve ilkeleri ve daha fazlasını içerebilir.

> [!TIP]
> Ortak ayarlarla bir paket oluşturmak için masaüstü Sihirbazı 'nı kullanın, ardından diğer ayarları, uygulamaları, ilkeleri vb. eklemek için gelişmiş düzenleyiciye geçiş yapın.

## <a name="steps-for-creating-provisioning-packages"></a>Sağlama paketleri oluşturma adımları

1. **Seçenek 1:** [Microsoft Store 'den](https://www.microsoft.com/store/apps/9nblggh4tx22). bu, HoloLens 2 özelliklerini içerir.
2. **seçenek 2:** [Windows 10 için Windows değerlendirme ve dağıtım seti 'nden (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Windows yapılandırma tasarımcısını Windows ADK 'den yüklerseniz, **yüklemek istediğiniz özellikleri seçin** iletişim kutusunda **yapılandırma tasarımcısı** ' nı seçin. bu seçenek, HoloLens 2 özelliklerini içermez.

> [!NOTE]
> Windows yapılandırma tasarımcısına erişmesi gereken bir çevrimdışı bilgisayar kullanacağınızı biliyorsanız, gelişmiş kurtarma yardımcısı için [offline app ınstall (hololens-recovery. md # indiriyor--app-store) yönergelerini izleyin. Windows yapılandırma tasarımcısı seçiminizi yapın. 

### <a name="2-create-the-provisioning-package"></a>2. sağlama paketini oluşturma

bir sağlama paketi oluşturmak için Windows Configuration Designer aracını kullanın.

1. Windows yapılandırma tasarımcısını açın (varsayılan olarak,%windir%\program Files (x86) \ Windows kits\10\assessment ve Deployment kit\ımaging ve Configuration Designer\x86\ICD.exe).

2. **HoloLens cihazları sağla**' yı seçin.

   ![ICD başlangıç seçenekleri.](images/icd-create-options-1703.png)

3. Projenizi adlandırın ve **son**' u seçin.

4. **Başlarken** sayfasındaki yönergeleri okuyun ve **İleri ' yi** seçin. Masaüstü sağlama sayfaları aşağıdaki adımlarda size yol gösterir.
  
> [!IMPORTANT]
> Bir sağlama paketi oluşturduğunuzda, proje dosyalarına ve sağlama paketi (. ppkg) dosyasına hassas bilgileri dahil edebilirsiniz. . Ppkg dosyasını şifreleme seçeneğiniz olsa da, proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamanız ve artık gerekli olmadığında proje dosyalarını silmeniz gerekir.

### <a name="configure-settings"></a>Ayarları yapılandırma

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>HoloLens sürümünü yükseltmek için kurumsal lisans dosyasına gidin ve seçin.</br></br>Ayrıca, ilk deneyimin parçalarını gizlemek için <strong>Evet</strong> veya <strong>Hayır</strong> ' a geçiş yapabilirsiniz.</br></br>Cihazı bir Wi-Fi ağa bağlanmaya gerek olmadan ayarlamak için, <strong>Wi-Fi kurulumunu atla</strong> ' yı <strong>Açık</strong>olarak değiştirin.</br></br>Cihazın kullanılacağı bölge ve saat dilimini seçin. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>Bu bölümde, cihazın otomatik olarak bağlanması gereken Wi-Fi kablosuz ağın ayrıntılarını girebilirsiniz. Bunu yapmak için <strong>Açık</strong>' ı SEÇIN, SSID 'yi, ağ türünü (<strong>Açık</strong> veya <strong>WPA2-Kişisel</strong>) ve ( <strong>WPA2-Kişisel</strong>) kablosuz ağın parolasını girin.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>cihazı Azure Active Directory kaydedebilir veya cihazda yerel bir hesap oluşturabilirsiniz</br></br>toplu Azure ad kaydını yapılandırmak için bir Windows Configuration Designer sihirbazı kullanmadan önce, <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">kuruluşunuzda Azure ad joın 'i ayarlayın</a>. Azure AD kiracınızdaki <strong>Kullanıcı ayarı başına en fazla cihaz sayısı</strong> , sihirbazda alacağınız toplu belirtecin kaç kez kullanılabileceğini belirler. Cihazı Azure AD 'ye kaydetmek için, bu seçeneği belirleyin ve Sihirbazı kullanarak alacağınız toplu belirteç için kolay bir ad girin. Belirteç için bir sona erme tarihi ayarlayın (en fazla, belirteci aldığınız tarihten itibaren 30 gündür). <strong>Toplu belirteç al</strong>' ı seçin. <strong>&#39;s oturum açmış olursunuz</strong> penceresinde, bir CIHAZıN Azure AD 'ye katılması ve ardından parolanın olması için izinlere sahip olan bir hesap girin. Windows yapılandırma tasarımcısına gerekli izinleri vermek için <strong>kabul et</strong> ' i seçin. </br></br>Yerel bir hesap oluşturmak için bu seçeneği belirleyin ve bir Kullanıcı adı ve parola girin. </br></br><strong>Önemli</strong> <br />(Windows 10 için yalnızca sürüm 1607) sağlama paketinde yerel bir hesap oluşturursanız, her 42 günde bir <strong>Ayarlar</strong> uygulamasını kullanarak parolayı değiştirmeniz gerekir. Bu süre içinde parola değiştirilmediyse, hesap kilitli olabilir ve oturum açılamıyor.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Cihaza bir sertifika sağlamak için <strong>sertifika ekle</strong>' ye tıklayın. Sertifika için bir ad girin ve ardından kullanılacak sertifikaya gidip seçin.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>HoloLens Geliştirici modunu etkinleştirmek için <strong>Evet</strong> veya <strong>Hayır</strong> ' a geçiş yapın. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Geliştirici modu hakkında daha fazla bilgi edinin.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Sağlama paketinizi korumak için bir parola ayarlamayın. sağlama paketi bir parolayla korunuyorsa, HoloLens cihazının sağlanması başarısız olur.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

İşiniz bittiğinde **Oluştur**' u seçin. Yalnızca birkaç saniye sürer. Paket yapılandırıldığında, paketin depolandığı konum sayfanın alt kısmında bir köprü olarak görüntülenir.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. gelişmiş sağlama kullanarak HoloLens için bir sağlama paketi oluşturma

> [!NOTE]
> **gelişmiş sağlama** bölümünde oluşturduğunuz bir sağlama paketinin, bir HoloLens (1. gen) başarıyla uygulanması için Windows Holographic for Business sürüme yükseltme lisansı eklemesi gerekmez. [HoloLens için Windows Holographic for Business daha fazla bilgi (1. genel)](hololens1-upgrade-enterprise.md).

1. Windows yapılandırma tasarımcısı başlangıç sayfasında, **gelişmiş sağlama**' yı seçin.
2. **Proje ayrıntılarını girin** penceresinde, projeniz için bir ad ve projenizin konumu belirtin. İsteğe bağlı olarak, projenizi açıklayan kısa bir açıklama girin.

3. **İleri**’yi seçin.

4. görüntülenecek **ve yapılandırılacak ayarları seçin** penceresinde **Windows 10 Holographic**' yi seçin ve ardından **ileri**' yi seçin.

5. **Son**'u seçin.

6. **Çalışma zamanı ayarları** ' nı genişletin ve [Bu makalenin ilerleyen kısımlarında açıklanan](#what-you-can-configure)ayarlardan birini kullanarak paketi özelleştirin.

    > [!IMPORTANT]
    > (Windows 10 için yalnızca sürüm 1607) sağlama paketinde yerel bir hesap oluşturursanız, her 42 günde bir **Ayarlar** uygulamasını kullanarak parolayı değiştirmeniz gerekir. Bu süre içinde parola değiştirilmediyse, hesap kilitli olabilir ve oturum açılamıyor. Kullanıcı hesabı kilitliyse, [tam bir cihaz kurtarması gerçekleştirmeniz](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)gerekir.

7. **Dosya**  >  **Kaydet**' i seçin.

8. Proje dosyalarının hassas bilgileri içerebileceğini belirten uyarıyı okuyun ve **Tamam**' ı seçin.

    > [!IMPORTANT]
    > Bir sağlama paketi oluşturduğunuzda, proje dosyalarına ve sağlama paketi (. ppkg) dosyasına hassas bilgileri dahil edebilirsiniz. . Ppkg dosyasını şifreleme seçeneğiniz olsa da, proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamanız ve artık gerekli olmadığında proje dosyalarını silmeniz gerekir.

9. Sağlama **paketini dışarı aktar**' ı seçin  >  .

10. **Sahibi** **BT Yöneticisi** olarak değiştirin. Bu, sağlama paketinin bu cihaza uygulanan sağlama paketlerinden daha yüksek önceliğini diğer kaynaklardan belirler. **İleri**’yi seçin.

11. **Paket sürümü** için bir değer ayarlayın.

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilir ve sürüm numarasını daha önce uygulanan paketleri güncelleştirecek şekilde değiştirebilirsiniz.

12. **Sağlama paketinin güvenlik ayrıntılarını seçin** sayfasında **İleri**' yi seçin.

    > [!WARNING]
    > sağlama paketini şifrelerseniz HoloLens cihazının sağlanması başarısız olur.  

13. Oluşturulduktan sonra sağlama paketinin gitmesini istediğiniz çıkış konumunu belirtmek için **İleri ' yi** seçin. varsayılan olarak, Windows Configuration Designer, proje klasörünü çıkış konumu olarak kullanır.

    İsteğe bağlı olarak, varsayılan çıkış **konumunu** değiştirmek için Gözat'ı seçin.

14. **İleri**’yi seçin.

15. Paketi **derlemeye** başlamak için Derleme'yi seçin. Proje bilgileri derleme sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

16. Derleme tamamlandığında Son'a **seçin.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Kurulum sırasında HoloLens paketi uygulama

Windows HoloLens Holographic sürüm 2004 veya derleme [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki sürümler üzerinde 2 cihaz, sağlama paketi uygulamak için USB sürücüsü kullanabilir. .ppkg dosyasını USB sürücünün köküne kopyalamanız gerekir. Sağlama paketleri yalnızca USB sürücünün kökünde yer alan paketler için uygulanır. Mevcut birden çok sağlama paketi sırayla uygulanır.

HoloLens [Holographic sürüm 20H2 Windows veya sonraki](hololens-release-notes.md#windows-holographic-version-20h2) sürümlerde 2 cihaz, bu işlemi kolaylaştırmanıza ve kolaylaştırmanıza yardımcı olmak için daha yeni özelliklere sahiptir. Lütfen aşağıdaki bölümleri gözden geçirebilirsiniz:

- [USB'den sağlamayı otomatik başlatma](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [OOBE'de sağlama paketlerini otomatik onaylama](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Cihazı bir bilgisayara (veya yukarıda belirtildiği gibi HoloLens 2 için USB sürücüsüne) bağlamak için USB kablosunu kullanın ve ardından cihazı başlatabilirsiniz. OOBE'nin **İlk etkileşime geçilebilir an** sayfasını geçerek devam edin.
    - Bu HoloLens (1. nesil) sayfasında mavi bir kutu vardır.
    - Bu HoloLens 2. sayfada yer alan kuş kuşlarını içerir.

2. Ses Düzeyi Kapalı ve Güç **düğmelerine aynı anda** **kısa bir süre basın** ve bırakın.

3. HoloLens, bilgisayarınızda bir Dosya Gezgini olarak gösterir.

4. Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.

5. OOBE'nin **İlk etkileşime değiştirilebilir** an sayfasındayken, Ses Düzeyi Kapalı ve Güç düğmelerine aynı anda kısa bir süre basın ve bırakın.  

6. Cihaz, pakete güvenmiyorsanız ve bunu uygulamak mı isterse sorar. Pakete güvenen bir onaylayın.

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

Bir kullanıcı, USB cihazlarından sağlamanın otomatik başlatılmasını ve paketlerin otomatik olarak onayını birleştirerek, HoloLens 2 cihazı cihazın kullanıcı arabirimini kullanmadan, hatta cihazı takmadan otomatik olarak sunar. Birden çok cihaz için aynı USB sürücü ve sağlama paketini kullanmaya devam edersiniz. Bu, aynı alanda aynı anda birden çok cihaz dağıtmak için kullanışlıdır. 

1. [Windows](hololens-provisioning.md) [Configuration Designer'ı kullanarak Sağlama Paketi oluşturun.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [2 HoloLens](hololens-insider.md#ffu-download-and-flash-directions) [19041.1361 veya daha yeni bir sürümü derlemeye flash olarak söner.](https://aka.ms/hololens2previewdownload) 
1. Gelişmiş [Kurtarma Yardımcı,](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın usb-C kablolarını çıkarın ve yanıp sönmeyi tamamlandıktan sonra. 
1. USB sürücülerinizi cihaza takın.
1. 2 HoloLens cihaz OOBE'de ilk kez başlatılırsa, USB sürücüsünde sağlama paketini otomatik olarak algılar ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz sağlama paketini otomatik olarak uygulayacaktır. 

Cihazınız artık yapılandırılmıştır ve Sağlama Başarılı ekranı görüntülenir.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Kurulumdan sonra bir sağlama paketini HoloLens/kaldırma

> [!NOTE]
> Bu adımlar Holographic, HoloLens 1809 ve üzeri HoloLens (1. nesil) cihazları ve Windows 2. nesil cihazlar için geçerlidir.

Bilgisayarınızda şu adımları izleyin:
1. HoloLens sihirbazını kullanarak bir sağlama paketi oluşturma konusunda açıklandığı [gibi bir HoloLens oluşturun.](hololens-provisioning.md)
2. Bağlan HoloLens USB kablosu kullanarak bir bilgisayara bağlayın. HoloLens, bilgisayarınızda bir Dosya Gezgini olarak gösterir.
3. Sağlama paketini sürükleyip uygulamanın Belgeler klasörüne HoloLens.

Aşağıdaki HoloLens adımları izleyin:
1. Hesaplara **Ayarlar**  >  **İş veya** okula  >  **erişme'ye gidin.** 
2. İlgili **Ayarlar'de** Sağlama **paketi ekle veya kaldır'ı seçin.**
3. Sonraki sayfada Paket **ekle'yi seçerek** dosya seçiciyi açın ve sağlama paketinizi seçin. Klasör boşsa Bu Cihaz'ı ve belgeler'i **seçin.** 

Paketiniz uygulandıktan sonra Yüklü paketler listesinde **görünür.** Paket ayrıntılarını görüntülemek veya paketi cihazdan kaldırmak için listelenen paketi seçin.

## <a name="what-you-can-configure"></a>Yapılandırabileceğiniz ayarlar

Paket sağlama, yapılandırma hizmeti sağlayıcılarından (CSP) kullanılır. CSP'ler hakkında bilgi sahibi değilsanız bkz. IT profesyonelleri için yapılandırma hizmeti [sağlayıcılarına (CSP'ler) giriş.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

Windows Yapılandırma Tasarımcısı'nda, Windows Holographic için bir sağlama paketi yapılandırmasını  yapılandırmasını tamamlarsanız, Kullanılabilir özelleştirmeler sayfasındaki ayarlar, Windows Holographic'te desteklenen [CSP'leri temel almaktadır.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) Aşağıdaki tabloda, uygulama için yapılandırmak istediğiniz ayarlar HoloLens.

![Uygulama için ortak çalışma zamanı HoloLens.](images/icd-settings.png)

| Ayar | Açıklama |
| --- | --- |
| **Sertifikalar** | Sertifikayı HoloLens.  |
| **ConnectivityProfiles** | Bir Wi-Fi profili HoloLens.   |
| **EditionUpgrade** | [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **İlkeler** | Uygulama üzerinde geliştirici moduna izin HoloLens. [Windows Holographic for Business tarafından desteklenen ilkeler](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Sağlama Paketi aracılığıyla uygulama yükleme

Uygulamalar, 2 cihaza paket HoloLens yükleyebilir. Bu, uygulamalarınızı dağıtmanıza yardımcı olmak için kullanabileceğiniz kolayca yeniden kullanılabilir bir paket sağlar. Sağlama Paketleri aracılığıyla uygulama [dağıtmaya ilişkin tam yönergeleri okuyun.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. nesil) bir sağlama paketi kullanarak uygulama yükleme desteği sınırlıdır (**UniversalAppInstall).** HoloLens (1. nesil) cihazlar yalnızca OOBE sırasında ve yalnızca kullanıcı bağlamı yüklemeleri sırasında PPKG aracılığıyla uygulama yüklemeyi destekler.
