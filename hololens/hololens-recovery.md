---
title: HoloLens 'i yeniden başlatın, sıfırlayın veya kurtarın
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Gelişmiş kurtarma Yardımcısı 'nı kullanarak bir görüntüyü HoloLens 2 ' ye yakıp söndür.
keywords: Nasıl yapılır, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, geçici sıfırlama, güç çevrimi, HoloLens, kapatma, yay, Gelişmiş kurtarma Yardımcısı
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
ms.openlocfilehash: afd782df1c68e8441b14823e0d961317914140e3
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380223"
---
# <a name="restart-reset-or-recover-hololens-2"></a>HoloLens 2 ' yi yeniden başlatın, sıfırlayın veya kurtarın

## <a name="charge-the-device"></a>Cihazı ücretlendirme

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun. Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.

Cihazınızın ücretlendirmenin en iyi yolu olan HoloLens 2 ile birlikte gelen [cihazınızın şarj cihazına ve USB Type-C kablosunu](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kullanın. Cihazınızın şarj cihazına, 18W gücü (2a 'da 9V) sağlar. HoloLens 2 cihazları sağlanan duvar karağını kullanarak, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendiriyolabilir. Bu aksesuarlar yoksa, mevcut olan cihazınızın şarj cihazına 'ın en az 15W güç desteğine sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlendirilecek bir BILGISAYAR kullanmaktan kaçının, bu da yavaş olur.

Cihaz doğru şekilde önyüklendiğinde ve çalışıyorsa, pil ücreti düzeyini denetlemek için üç yol vardır:

- HoloLens cihaz Kullanıcı arabiriminin ana menüsünde.
- Güç düğmesine ışığı (%40 oranında bir ücret için) görüntüleyin ve en az iki katı LED görmeniz gerekir.
    - Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.  Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.
    - HoloLens 'niz açık olduğunda, pil göstergesi pil düzeyini beş artışlarla görüntüler.
    - Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.
- Ana bilgisayarınızda, **Dosya Gezgini** 'ni açın ve **Bu bilgisayarın** sol tarafında bulunan HoloLens 2 cihazınızı bulun. Cihaza sağ tıklayın ve **Özellikler**' i seçin. Bir iletişim kutusu, pil ücreti düzeyini gösterir.

   ![HoloLens 2 özellikleri ekranı, pil değişim düzeyini gösterir](images/ResetRecovery2.png)

Cihaz başlangıç menüsüne önyükleme yapamıyor, ana bilgisayar bilgisayarındaki açık görünüm ve cihaz numaralandırması konusuna göz önünde barının. Ardından [sorun giderme kılavuzunu](hololens-troubleshooting.md)izleyin. Cihazın durumu, sorun giderme kılavuzunda listelenen durumlardan hiçbiriyle eşleşmezse, ana bilgisayar bilgisayarınıza değil güç kaynağına bağlı cihazla [sabit sıfırlama yordamını](hololens-recovery.md#hard-reset-procedure) gerçekleştirin. Cihazın ücreti için en az bir saat bekleyin.

## <a name="reset-the-device"></a>Cihazı sıfırlama

Belirli koşullarda, yazılım Kullanıcı arabirimini kullanmadan cihazı el ile sıfırlamanız gerekebilir.

### <a name="standard-procedure"></a>Standart yordam

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Güç** düğmesine basın ve basılı tutun. Tüm LED 'ler kapalı olmalıdır.

3. 2-3 saniye bekleyin ve ardından **Güç** düğmesine kısa basın. Güç düğmesine yakın LED 'ler açılır ve cihaz başlatılmaya başlayacaktır.

4. Cihazı ana bilgisayara bağlayın ve sonra Device Manager açın. (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery sapve Yöneticisi](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Sabit sıfırlama prosedürü

Standart sıfırlama yordamı çalışmazsa, sabit sıfırlama yordamını kullanın:

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Ses**  +  **tasarrufu** düğmelerini basılı tutun. Cihaz otomatik olarak yeniden başlatılır.

4. Cihazı ana bilgisayara bağlayın.

5. Device Manager açın (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve sonra **Device Manager**' i seçin). Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery Cihaz Yöneticisi 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Cihazı Temizleme-yeniden yansıtma

Olağandışı durumlarda, HoloLens 2 ' yi "temizlemek-Flash" yapmanız gerekebilir. Lütfen temizleme-refflash 'un aşağıdaki sorunları etkilemesini beklenmediğini unutmayın:
- [Renk dağılımı görüntüleme](hololens2-display.md)
- Sesle önyükleme, ancak görüntüleme çıktısı yok
- [1-3-5-LED desenli](hololens2-setup.md#lights-to-indicate-problems)
- [Aşırı ısınmasını](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- İşletim sistemi kilitlenmeleri (uygulama kilitlenmelerinden farklı)

Cihazı kırmanın iki yolu vardır. Her ikisi için, önce [Windows Mağazası 'Ndan Gelişmiş kurtarma Yardımcısı 'nı yüklemeniz](https://www.microsoft.com/store/productId/9P74Z35SFRS8)gerekir.

>[!WARNING]
>Cihazınızı Kırdıysanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.

Varsayılan olarak, Gelişmiş kurtarma Yardımcısı en son özellik yayın derlemesini indirmek üzere ayarlanmıştır, en son özellik sürümü hakkında bilgi edinmek için [Sürüm notlarımızı](hololens-release-notes.md#) okumak üzere buraya bakın. Cihazınızı Gelişmiş kurtarma Yardımcısı aracılığıyla yeniden Flash 'a aktarmak üzere en son HoloLens 2 tam Flash Güncelleştirmesi (FFU) paketini almak için, [en son aylık HoloLens 2 görüntüsünü indirmek üzere buraya tıklayın](https://aka.ms/hololens2download). Bu sürüm, genel olarak kullanılabilir olan en son yapıya sahiptir.

Refflash yordamını çalıştırmadan önce, uygulamanın Windows 10 PC 'nizde yüklü ve çalışır durumda olduğundan ve cihazı algılamaya hazırlandığınızdan emin olun. Ayrıca, HoloLens 'nizin en az %40 oranında ücretlendirildiğinden emin olun.

![HoloLens 2 temiz kırflash ekran görüntüsü](images/ARC1.png)

### <a name="normal-procedure"></a>Normal yordam

1. HoloLens cihazı çalışırken, daha önce Gelişmiş kurtarma yardımcısı uygulamasını açtığınız Windows 10 BILGISAYARıNA bağlayın.
 
   Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:

   ![HoloLens 2 Temizleme refflash başlangıç ekranı](images/ARC2.png)

3. Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve yönergeleri izleyerek, yeniden doldurun.

### <a name="manual-procedure"></a>El ile yordam

HoloLens 2 doğru başlamazsa veya Gelişmiş kurtarma Yardımcısı cihazı algılayamazsa, cihazı kurtarma moduna almanız gerekebilir:

1. Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.

2. 15 saniye boyunca **Güç** düğmesine basın ve basılı tutun. Tüm LED 'Leri kapatması gerekir.

3. **Birim yukarı** düğmesine basarken, cihazı başlatmak için **Güç** düğmesine basın ve bırakın. 15 saniye bekleyin ve ardından **birim yukarı** düğmesini serbest bırakın. Yalnızca beş LED 'in ortasının ışığı açılır.

4. Cihazı ana bilgisayara bağlayın ve Device Manager açın. (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın Microsoft HoloLens olarak doğru şekilde numaralandıryazıldığından emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:

   ![HoloLens 2 Temizleme refflash ekranı](images/ARC2.png)

6. Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve ardından yönergeleri izleyerek refflash 'u tamamlayın.

## <a name="troubleshoot-advanced-recovery-companion"></a>Gelişmiş kurtarma Yardımcısı sorunlarını giderme

1. Flash 'ı denemeden önce cihazınızın %40 veya daha fazla bir ücret aldığından emin olun.

2. Cihazınızın kilidinin açık olup olmadığını denetleyin.

3. ARC cihazınızı algılamazsa, bilgisayarınızda dosya Gezgini aracılığıyla cihazınıza bağlanabildiğinizden emin olun. Bunu yaparsanız;

    1.  Cihazınızın bu bağlantıyı devre dışı bırakan USB ilkeleri olabilir. Öyleyse, [El Ile yanıp sönen modu](hololens-recovery.md#manual-procedure)deneyin.
    2.  İlke yoksa, farklı bir USB kablosu deneyin.

1. Cihazınızın [1-3-5 yönlü bir model GÖRÜNTÜLEMEMIŞ](hololens2-setup.md#lights-to-indicate-problems)olduğunu denetleyin.

## <a name="download-arc-without-using-the-app-store"></a>Uygulama mağazasını kullanmadan YAYı indirin

BT ortamı Windows Mağazası uygulamasının kullanımını engelliyorsa veya perakende mağazası 'na erişimi sınırlayıp, BT Yöneticisi bu uygulamayı "çevrimdışı" bir dağıtım yolu aracılığıyla kullanılabilir hale getirir.

 >[!NOTE]
 > - BT yöneticileri Ayrıca bu uygulamayı System Center Configuration Manager (SCCM) veya Intune aracılığıyla dağıtabilir.
 > - Bu kılavuz, Gelişmiş kurtarma Yardımcısı 'na odaklanmaktadır, ancak işlem diğer "çevrimdışı" uygulamalar için de kullanılabilir.

Dağıtım yolunu etkinleştirmek için şu adımları izleyin:

1. [İş Microsoft Store](https://businessstore.microsoft.com) gidin ve bir Azure Active Directory kimliği kullanarak oturum açın.

1. **Yönet – ayarlar**' a gidin. **Alışveriş deneyimi** altında **çevrimdışı uygulamaları göster** ' i açın.

1. **Grubum için mağaza**' a gidin ve [**_Gelişmiş kurtarma Yardımcısı_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)' nı arayın.

1. **Lisans türünü** **_çevrimdışı_*_ olarak değiştirin ve _ Yönet ' i seçin***.

1. **Çevrimdışı kullanım için paketi indirin** altında Ikinci mavi **İndir** düğmesini seçin. Dosya uzantısının *. appxdemeti* olduğundan emin olun.

    - Bu aşamada, masaüstü BILGISAYARıN internet erişimi varsa, uygulamayı yüklemek için pakete çift tıklayın.

    - Hedef bılgısayarda internet bağlantısı yoksa, şu adımları izleyin:
       1. Kodlanamayan lisansı seçin ve ardından **Lisans oluştur**' u seçin.
       2. **Gerekli çerçeveler** altında **İndir**' i seçin.
       3. Paketi bağımlılık ve lisansa uygulamak için DıSM 'yi kullanın. Yönetici komut isteminden aşağıdaki komutu çalıştırın:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Bu kod örnekteki sürüm numarası, mevcut olan sürümle eşleşmeyebilir. Ayrıca, örnekteki farklı bir indirme konumu seçmiş olabilirsiniz. Gerektiğinde komutta herhangi bir değişiklik yapın.

> [!TIP]
> Çevrimdışı bir FFU yüklemek için Gelişmiş kurtarma Yardımcısı kullanmayı planlarken, Flash görüntünüzü indirmek faydalı olabilir. [**HoloLens 2 için geçerli görüntüyü indirin**](https://aka.ms/hololens2download).


Diğer kaynaklar:
- [Çevrimdışı uygulamaları dağıtma](/microsoft-store/distribute-offline-apps) 
- [DıSM uygulama paketi (. appx veya. appxdemeti) komut satırı seçeneklerini sunma](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
