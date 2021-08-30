---
title: HoloLens yeniden başlatın, sıfırlayın veya kurtarın
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: HoloLens 2 ' ye görüntü flash için gelişmiş kurtarma yardımcısı 'nı kullanma.
keywords: nasıl yapılır, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, geçici sıfırlama, güç çevrimi, HoloLens, kapatma, arc, gelişmiş kurtarma yardımcısı
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: 9547545fee4b1e0c8bacf258fa9bea081dec2445
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189724"
---
# <a name="restart-reset-or-recover-hololens-2"></a>HoloLens 2 ' yi yeniden başlatın, sıfırlayın veya kurtarın

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun. Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.

cihazınızı ücretlendirmenin en iyi yolu olan HoloLens 2 ile birlikte gelen [cihazınızın şarj cihazına ve USB Type-C kablosunu](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kullanın. Cihazınızın şarj cihazına, 18W gücü (2a 'da 9V) sağlar. HoloLens 2 cihaz, izin verilen duvar karağını kullanarak, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendirmesini sağlayabilir. Bu aksesuarlar yoksa, mevcut olan cihazınızın şarj cihazına 'ın en az 15W güç desteğine sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlendirilecek bir BILGISAYAR kullanmaktan kaçının, bu da yavaş olur.

Cihaz doğru şekilde önyüklendiğinde ve çalışıyorsa, pil ücreti düzeyini denetlemek için üç yol vardır:

- HoloLens cihaz kullanıcı arabiriminin ana menüsünde.
- Güç düğmesine ışığı (%40 oranında bir ücret için) görüntüleyin ve en az iki katı LED görmeniz gerekir.
    - Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.  Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.
    - HoloLens açık olduğunda, pil göstergesi pil düzeyini beş artışlarla görüntüler.
    - Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.
- ana bilgisayarınızda, **dosya gezgini** 'ni açın ve **bu bilgisayarın** altındaki HoloLens 2 cihazınızı sol tarafta arayın. Cihaza sağ tıklayın ve **Özellikler**' i seçin. Bir iletişim kutusu, pil ücreti düzeyini gösterir.

   ![HoloLens 2 özellikleri ekranı, pil değişim düzeyini gösterir.](images/ResetRecovery2.png)

Cihaz başlangıç menüsüne önyükleme yapamıyor, ana bilgisayar bilgisayarındaki açık görünüm ve cihaz numaralandırması konusuna göz önünde barının. Ardından [sorun giderme kılavuzunu](hololens-troubleshooting.md)izleyin. Cihazın durumu, sorun giderme kılavuzunda listelenen durumlardan hiçbiriyle eşleşmezse, ana bilgisayar bilgisayarınıza değil güç kaynağına bağlı cihazla [sabit sıfırlama yordamını](hololens-recovery.md#hard-reset-procedure) gerçekleştirin. Cihazın ücreti için en az bir saat bekleyin.

## <a name="reset-the-device"></a>Cihazı sıfırlama

Belirli koşullarda, yazılım Kullanıcı arabirimini kullanmadan cihazı el ile sıfırlamanız gerekebilir.

### <a name="standard-procedure"></a>Standart yordam

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Güç** düğmesine basın ve basılı tutun. Tüm LED 'ler kapalı olmalıdır.

3. 2-3 saniye bekleyin ve ardından **Güç** düğmesine kısa basın. Güç düğmesine yakın LED 'ler açılır ve cihaz başlatılmaya başlayacaktır.

4. cihazı ana bilgisayara Bağlan ve ardından Device Manager açın. (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' yı seçin.) aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* doğru şekilde numaralandırdığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery sapve yöneticisi.](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Sabit sıfırlama prosedürü

Standart sıfırlama yordamı çalışmazsa, sabit sıfırlama yordamını kullanın:

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Ses**  +  **tasarrufu** düğmelerini basılı tutun. Cihaz otomatik olarak yeniden başlatılır.

4. cihazı ana bilgisayar bilgisayarına Bağlan.


5. Device Manager açın ( **Windows** tuşuna ve sonra **X** tuşuna Windows 10 ve ardından **Device Manager**' i seçin). aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* doğru şekilde numaralandırdığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery cihaz yöneticisi 2.](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Cihazı Temizleme-yeniden yansıtma

olağandışı durumlarda, HoloLens 2 ' yi "temizle-flash" yapmanız gerekebilir. Lütfen temizleme-refflash 'un aşağıdaki sorunları etkilemesini beklenmediğini unutmayın:
- [Renk dağılımı görüntüleme](hololens2-display.md)
- Sesle önyükleme, ancak görüntüleme çıktısı yok
- [1-3-5-LED desenli](hololens2-setup.md#lights-to-indicate-problems)
- [Aşırı ısınmasını](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- İşletim sistemi kilitlenmeleri (uygulama kilitlenmelerinden farklı)

Cihazı kırmanın iki yolu vardır. her ikisi için, önce [Windows deposundan gelişmiş kurtarma yardımcısı 'nı yüklemeniz](https://www.microsoft.com/store/productId/9P74Z35SFRS8)gerekir.

>[!WARNING]
>Cihazınızı Kırdıysanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.

Varsayılan olarak, Gelişmiş kurtarma Yardımcısı en son özellik yayın derlemesini indirmek üzere ayarlanmıştır, en son özellik sürümü hakkında bilgi edinmek için [Sürüm notlarımızı](hololens-release-notes.md#) okumak üzere buraya bakın. en son HoloLens 2 tam Flash güncelleştirmesi (ffu) paketini almak için, gelişmiş kurtarma yardımcısı aracılığıyla cihazınızı yeniden flash 'a ekleyin, [en son aylık HoloLens 2 görüntüsünü indirmek için buraya tıklayın](https://aka.ms/hololens2download). Bu sürüm, genel olarak kullanılabilir olan en son yapıya sahiptir.

refflash yordamını çalıştırmadan önce, uygulamanın Windows 10 bilgisayarınızda yüklü olduğundan ve çalıştığından emin olun ve cihazı algılamaya hazırlanın. ayrıca HoloLens en az %40 oranında ücretlendirildiğinden emin olun.

![HoloLens 2 temiz kırflash ekran görüntüsü.](images/ARC1.png)

### <a name="normal-procedure"></a>Normal yordam

1. HoloLens cihaz çalışırken, daha önce gelişmiş kurtarma yardımcısı uygulamasını açtığınız Windows 10 bilgisayara bağlayın.
 
   Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:

   ![HoloLens 2 temiz flash başlangıç ekranı.](images/ARC2.png)

3. gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve yönergeleri izleyerek, bildirimi tamamlayın.

### <a name="manual-procedure"></a>El ile yordam

HoloLens 2 doğru başlatılmazsa veya gelişmiş kurtarma yardımcısı cihazı algılayamazsa, cihazı kurtarma moduna almanız gerekebilir:

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Güç** düğmesine basın ve basılı tutun. Tüm LED 'Leri kapatması gerekir.

3. **Birim yukarı** düğmesine basarken, cihazı başlatmak için **Güç** düğmesine basın ve bırakın. 15 saniye bekleyin ve ardından **birim yukarı** düğmesini serbest bırakın. Yalnızca beş LED 'in ortasının ışığı açılır.

4. cihazı ana bilgisayara Bağlan ve Device Manager açın. (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' yı seçin.) aşağıdaki görüntüde gösterildiği gibi cihazın Microsoft HoloLens doğru şekilde numaralandırdığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery.](images/MicrosoftHoloLensRecovery.png)

   Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:

   ![HoloLens 2 temiz kırflash ekranı.](images/ARC2.png)

6. gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve ardından yönergeleri izleyerek refflash 'u tamamlayın.

## <a name="troubleshoot-advanced-recovery-companion"></a>Gelişmiş kurtarma Yardımcısı sorunlarını giderme

1. Flash 'ı denemeden önce cihazınızın %40 veya daha fazla bir ücret aldığından emin olun.

2. Cihazınızın kilidinin açık olup olmadığını denetleyin.

1. Cihazınızın hub değil, doğrudan ana bilgisayar bilgisayarına takıldığını kontrol edin.

1. cihazınız, evrensel seri veri yolu sürücüleri altında bir HoloLens/HoloLens kurtarma aygıtı olarak gösterilmiyorsa, aşağıdakileri denetleyin:
    1. **Bağlantı noktaları**, BIR Qualcomm HS-USB cihazı
    1.   QUSB_BULK cihaz olarak **diğer cihazlar**-ana bilgisayarınızda, Hololens algılamak için gereken sürücüler eksiktir. sağ tıklayıp sürücüyü güncelleştir ' i seçin ve sürücüleri çevrimiçi olarak arayın veya [Windows Update ayarlarınızda isteğe bağlı güncelleştirmeleri denetleyin](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674). Sürücü indirildikten sonra, ARC onu algılayabilmelidir.
 
1. ARC cihazınızı algılamazsa, bilgisayarınızda dosya Gezgini aracılığıyla cihazınıza bağlanabildiğinizden emin olun. Bunu yaparsanız;

    1.  Cihazınızın bu bağlantıyı devre dışı bırakan USB ilkeleri olabilir. Öyleyse, [El Ile yanıp sönen modu](hololens-recovery.md#manual-procedure)deneyin.
    2.  İlke yoksa, farklı bir USB kablosu deneyin.

1. Cihazınızın [1-3-5 yönlü bir model GÖRÜNTÜLEMEMIŞ](hololens2-setup.md#lights-to-indicate-problems)olduğunu denetleyin.

## <a name="download-arc-without-using-the-app-store"></a>Uygulama mağazasını kullanmadan YAYı indirin

bt ortamı Windows mağaza uygulamasının kullanımını engelliyorsa veya perakende mağazası 'na erişimi sınırlayıp, bt yöneticisi bu uygulamayı "çevrimdışı" bir dağıtım yolu aracılığıyla kullanılabilir hale getirir.

 >[!NOTE]
 > - AYRıCA, BU uygulama, SYSTEM CENTER CONFIGURATION MANAGER (SCCM) veya Intune aracılığıyla da dağıtabilirsiniz.
 > - Bu kılavuz Gelişmiş Kurtarma Yardımcı'ya odaklanır, ancak işlem diğer "çevrimdışı" uygulamalar için de kullanılabilir.

Dağıtım yolunu etkinleştirmek için şu adımları izleyin:

1. [İş İçin Microsoft Store'a](https://businessstore.microsoft.com) gidin ve Azure Active Directory oturum açma.

1. Yönet **– Ayarlar.** Alışveriş deneyimi altında Çevrimdışı uygulamaları **göster'i açma.** 

1. Grubum **için alışverişe gidin ve** Gelişmiş Kurtarma [**_Yardımcısı araması yapmak için ._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Lisans **Türü'sini** **_çevrimdışı _ olarak_*değiştirerek _ Yönet'i* seçin.**

1. Paketi **çevrimdışı kullanım için indir'in altında** ikinci mavi İndir **düğmesini** seçin. Dosya uzantısının *.appxbundle olduğundan emin olun.*

    - Bu aşamada, Masaüstü bilgisayar internet erişimine sahipse, uygulamayı yüklemek için pakete çift tıklayın.

    - Hedef bilgisayar İnternet bağlantısına sahip değilse şu adımları izleyin:
       1. Kodlanmamış lisansı seçin ve ardından Lisans **oluştur'a tıklayın.**
       2. Gerekli **Çerçeveler altında İndir'i** **seçin.**
       3. Paketi bağımlılık ve lisansla uygulamak için DISM kullanın. Yönetici komut isteminde aşağıdaki komutu çalıştırın:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Bu kod örneğinde yer alan sürüm numarası şu anda kullanılabilir olan sürümle eşleşmez. Ayrıca örnekten farklı bir indirme konumu seçmiş de olabilirsiniz. Gerektiğinde komutta herhangi bir değişiklik yapın.

> [!TIP]
> Çevrimdışı FFU yüklemek için Gelişmiş Kurtarma Yardımcı'sı kullanmayı planlasanız, flash görüntü indirebilirsiniz. [**HoloLens 2 için geçerli görüntüyü indirin.**](https://aka.ms/hololens2download)


Diğer kaynaklar:
- [Çevrimdışı uygulamaları dağıtma](/microsoft-store/distribute-offline-apps) 
- [DISM uygulama paketi (.appx veya .appxbundle) hizmet komut satırı seçenekleri](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
