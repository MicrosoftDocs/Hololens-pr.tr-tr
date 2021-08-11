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
ms.openlocfilehash: d9a0901a916ec33c076eeae33b680406a45f7feefe82442da1f346e78bc9b383
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663794"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>sağlama paketi kullanarak HoloLens yapılandırma

[Windows sağlama](/windows/configuration/provisioning-packages/provisioning-packages) , bt yöneticilerinin son kullanıcı cihazlarını ımaging olmadan yapılandırmasını kolaylaştırır. Windows Yapılandırma Tasarımcısı, daha sonra sağlama paketlerine yerleşik olarak bulunan resimleri ve çalışma zamanı ayarlarını yapılandırmaya yönelik bir araçtır.

bir sağlama paketinde uygulayabileceğiniz HoloLens yapılandırmalarından bazıları şunlardır:

- [Windows Holographic for Business](hololens1-upgrade-enterprise.md) yükseltin
- Yerel hesap ayarlama
- Wi-Fi bağlantısını ayarlama
- Cihaza sertifika uygulama
- Geliştirici modunu etkinleştir
- [Ayrıntılı yönergelerinizi](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)Izleyerek bilgi noktası modunu yapılandırın.

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
- [Ayrıntılı yönergeleri](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)izleyerek bilgi noktası modunu yapılandırın.

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

   ![ICD başlatma seçenekleri](images/icd-create-options-1703.png)

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

![HoloLens için ortak çalışma zamanı ayarları](images/icd-settings.png)

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
