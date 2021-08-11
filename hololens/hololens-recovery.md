---
title: Yeniden başlatma, sıfırlama veya kurtarma HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Advanced Recovery Companion'ı kullanarak HoloLens 2'ye görüntü gösterme.
keywords: nasıl yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, yazılım sıfırlaması, güç döngüsü, HoloLens, kapatma, arc, gelişmiş kurtarma yardımcı
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
ms.openlocfilehash: 7d8f2f8bf6aaaeb7f6f0ddbd339d428dad9335faeb99bfca48a19e68929921ed
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663010"
---
# <a name="restart-reset-or-recover-hololens-2"></a>2' de yeniden başlatma, sıfırlama HoloLens kurtarma

>[!IMPORTANT]
> Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun. Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.

Cihazınızı ücret [ödemenin en iyi yolu,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) HoloLens 2 ile birlikte gelen USB Type-C kablosunu kullanın. Malzeme 18W güç sağlar (2A'da 9V). Sağlanan duvar duvarını kullanarak HoloLens 2 cihaz bekleme durumundayken pilin 65 dakikadan kısa bir sürede dolup dolulyabilirsiniz. Bu aksesuarlar mevcut değilse, kullanılabilir olan aletin en az 15W gücü destekleyene sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlandırarak yavaş olan bir bilgisayar kullanmaktan kaçının.

Cihaz doğru şekilde önyüklüp çalışıyorsa, pil ücreti düzeyini denetlemenin üç yolu vardır:

- Cihaz kullanıcı arabiriminin ana HoloLens seçin.
- LED'i güç düğmesinin yakınında görüntüle (yüzde 40 ücret için en az iki katı LED görüyor gerekir).
    - Cihaz ücretlendirmeye devam edin. Pil göstergesi, geçerli ücret düzeyini belirtmek için yanıp söner.  Son ışık, etkin ücretlendirmeyi göstermek için belirecek ve sönecek.
    - Pil HoloLens, pil göstergesi beş artımlı olarak pil düzeyini görüntüler.
    - Beş ışığın yalnızca biri açık olduğunda pil düzeyi yüzde 20'nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmayı denersiniz, bir ışık kısa bir süre yanıp söner ve sonra gider.
- Konak bilgisayarınızda, **Dosya Gezgini** açın ve sol tarafta Bu bilgisayar altında HoloLens 2 cihazınızı **kontrol edin.** Cihaza sağ tıklayın ve Özellikler'i **seçin.** Bir iletişim kutusu pil ücreti düzeyini gösterir.

   ![Pil HoloLens 2 özellikler ekranı pil değişikliği düzeyini gösterir](images/ResetRecovery2.png)

Cihaz başlangıç menüsüne önyükleyene, ana bilgisayar üzerinde LED görünümünü ve cihaz numaralandırıcıyı not edin. Ardından sorun giderme [kılavuzunu izleyin.](hololens-troubleshooting.md) Cihazın durumu sorun giderme kılavuzunda listelenen durumlardan herhangi biri ile [](hololens-recovery.md#hard-reset-procedure) eşlenemezse, cihaz ana bilgisayarınıza değil güç kaynağına bağlı olarak sabit sıfırlama yordamını gerçekleştirin. Cihazın ücret ödemesi için en az bir saat bekleyin.

## <a name="reset-the-device"></a>Cihazı sıfırlama

Belirli durumlarda, yazılım kullanıcı arabirimini kullanmadan cihazı el ile sıfırlamanız gerekebilir.

### <a name="standard-procedure"></a>Standart yordam

1. Cihazın güç kaynağından veya konak pc'den bağlantısını kesmek için Type-C kablosunu çıkarın.

2. Güç düğmesine 15 **saniye** basılı tutun. Tüm LED'ler kapalıdır.

3. 2-3 saniye bekleyin ve güç düğmesine kısa **basın.** Güç düğmesine yakın LED'ler yanacak ve cihaz çalışmaya başlayacaktır.

4. Bağlan konak bilgisayara bağlayın ve Ardından Cihaz Yöneticisi'ni açın. (Windows 10 için, **Windows** tuşuna ve **X** tuşuna basın ve ardından Cihaz **Yöneticisi'ni** seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın doğru şekilde Microsoft HoloLens *emin* olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery geliştirme yöneticisi](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Sabit sıfırlama yordamı

Standart sıfırlama yordamı çalışmıyorsa, sabit sıfırlama yordamını kullanın:

1. Cihazın güç kaynağından veya konak pc'den bağlantısını kesmek için Type-C kablosunu çıkarın.

2. Güç **düğmelerini**  +   15 saniye basılı tutun. Cihaz otomatik olarak yeniden başlatılır.

4. Bağlan konak bilgisayara bağlayın.


5. Cihaz Yöneticisi'ni açın (Windows 10 anahtarına **Windows** **X** tuşuna basın ve Ardından Cihaz Yöneticisi'ni **seçin).** Aşağıdaki görüntüde gösterildiği gibi cihazın doğru şekilde Microsoft HoloLens *emin* olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery cihaz maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Cihazı temizleme

Olağanüstü durumlarda, HoloLens 2'de "temizleme" HoloLens olabilir. Clean-reflash'in aşağıdaki sorunları etkilemesi beklenmiyor:
- [Renk tekdüzlüklerini görüntüleme](hololens2-display.md)
- Ses ile önyükleniyor ama görüntü çıkışı yok
- [1-3-5-LED deseni](hololens2-setup.md#lights-to-indicate-problems)
- [Aşırı ısınma](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Işletim sistemi kilitleniyor (uygulama kilitlenmelerinden farklıdır)

Cihaza ters eğik çizginin iki yolu vardır. Her ikisi için de, önce [Gelişmiş Kurtarma Yardımcı'sı'Windows yüklemeniz gerekir.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>Cihazınıza başvurursanız TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.

Varsayılan olarak, Gelişmiş Kurtarma Yardımcısı en son özellik sürümü derlemeyi [](hololens-release-notes.md#) indirmek için ayarlanmıştır. En son özellik sürümü hakkında bilgi edinmek için Sürüm notlarımızı okumak için buraya göz ekleyin. En son HoloLens 2 Tam Flash Güncelleştirme (FFU) paketini Gelişmiş Kurtarma Yardımcısı aracılığıyla cihazınıza ters eğik çizgiyle almak için, en son aylık HoloLens [2 görüntüsünü indirmek için buraya tıklayın.](https://aka.ms/hololens2download) Bu sürüm, genel kullanıma açık en son derlemedir.

Reflash yordamına başlamadan önce, uygulamanın bilgisayarınızda yüklü ve Windows 10 ve cihazı algılamaya hazır olduğundan emin olun. Ayrıca, HoloLens en az %40 ücrete tabi olduğundan emin olmak.

![HoloLens 2 temiz ters eğik çizgi ekran](images/ARC1.png)

### <a name="normal-procedure"></a>Normal yordam

1. Cihaz HoloLens çalışırken, daha önce Gelişmiş Kurtarma Windows 10 uygulamasını açtığınız bilgisayarla bağlantı kurabilirsiniz.
 
   Cihaz otomatik olarak algılanır ve Gelişmiş Kurtarma Yardımcı uygulama kullanıcı arabirimi güncelleştirme işlemini başlatacaktır:

   ![HoloLens 2 temiz reflash ilk ekranı](images/ARC2.png)

3. Gelişmiş Kurtarma HoloLens kullanıcı arabiriminde 2.02. kullanıcı arabirimini seçin ve yönergeleri izleyerek ters eğik çizgiyi uygulayın.

### <a name="manual-procedure"></a>El ile yordam

HoloLens 2 düzgün başlanmasa veya Gelişmiş Kurtarma Yardımcı cihazı algılayamasa, cihazı kurtarma moduna koymanız gerekir:

1. Cihazın güç kaynağından veya konak pc'den bağlantısını kesmek için Type-C kablosunu çıkarın.

2. Güç düğmesine 15 **saniye** basılı tutun. Tüm LED'ler kapalıdır.

3. Ses düzeyi **yukarı düğmesine basarken,** cihazı başlatmak **için güç** düğmesine basın ve bırakın. 15 saniye bekleyin ve ardından birimi **yukarı bırakın.** Yalnızca beş LED'in ortadaki LED ışığı yanacak.

4. Bağlan konak bilgisayara bağlayın ve Cihaz Yöneticisi'ni açın. (Windows 10 Tuşuna **Windows** ve **ardından X** tuşuna basın ve Ardından Cihaz **Yöneticisi'ni** seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın doğru şekilde Microsoft HoloLens emin olun:

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Cihaz otomatik olarak algılanır ve Gelişmiş Kurtarma Yardımcı uygulama kullanıcı arabirimi güncelleştirme işlemini başlatacaktır:

   ![HoloLens 2 temiz ters eğik çizgi ekranı](images/ARC2.png)

6. Gelişmiş HoloLens Yardımcı uygulama kullanıcı arabiriminde 2. kullanıcı arabirimini seçin ve ardından yönergeleri izleyerek ters eğik çizgiyi uygulayın.

## <a name="troubleshoot-advanced-recovery-companion"></a>Gelişmiş Kurtarma Yardımcı sorunlarını giderme

1. Flash denemeden önce cihazınızın %40 veya daha fazla ücrete bağlı olduğundan emin olun.

2. Cihazınızın kilidinin açık olup olduğunu kontrol edin.

1. Cihazınızın hub'a değil doğrudan konak bilgisayara takılı olup olmadığını kontrol edin.

1. Cihazınız Evrensel Seri Veri HoloLens Sürücüleri altında HoloLens/HoloLens Kurtarma cihazı olarak görünmüyorsa şunları kontrol edin:
    1. **Bağlantı** noktaları, Qualcomm HS-USB cihazı olarak
    1.   **Diğer Cihazlar**, QUSB_BULK cihaz olarak - konak bilgisayarınızda, cihazlarınızı algılamak için gerekli HoloLens. Sağ tıklayın ve Sürücüyü Güncelleştir'i seçin ve çevrimiçi sürücü araması yapın veya Güncelleştirme ayarları'Windows [İsteğe Bağlı Güncelleştirmeler'i kontrol edin.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674) Sürücü indirildikten sonra ARC tarafından algılanabilir.
 
1. ARC cihazınızı algılamazsa, bilgisayarınıza bağlanmak için bilgisayarınızdan Dosya Gezgini emin olun. Bunu yoksa;

    1.  Cihazınızın bağlantıyı devre dışı bırakan USB ilkeleri olabilir. Öyleyse, El İle [Yanıp Sönme modunu deneyin.](hololens-recovery.md#manual-procedure)
    2.  İlke yoksa farklı bir USB kablosu deneyin.

1. Cihazınızın [1-3-5-LED deseni görüntülemez.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Uygulama mağazalarını kullanmadan ARC'ı indirme

IT ortamı, Windows Store uygulamasının kullanımını önlese veya perakende mağazasına erişimi sınırlarsa, IT yöneticisi bu uygulamayı bir "çevrimdışı" dağıtım yolu aracılığıyla kullanılabilir hale getirmesini sağlar.

 >[!NOTE]
 > - AYRıCA, BU uygulama, SYSTEM CENTER CONFIGURATION MANAGER (SCCM) veya Intune aracılığıyla da dağıtabilirsiniz.
 > - Bu kılavuz Gelişmiş Kurtarma Yardımcı'ya odaklanır, ancak işlem diğer "çevrimdışı" uygulamalar için de kullanılabilir.

Dağıtım yolunu etkinleştirmek için şu adımları izleyin:

1. [İş İçin Microsoft Store'a](https://businessstore.microsoft.com) gidin ve Azure Active Directory oturum açma.

1. Yönet **– Ayarlar.** Alışveriş deneyimi altında Çevrimdışı uygulamaları **göster'i açma.** 

1. Grubum **için alışverişe gidin ve** Advanced Recovery Companion araması yapmak için [**_._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

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
          > Bu kod örneğinde sürüm numarası şu anda kullanılabilir olan sürümle eşleşmez. Ayrıca örnekten farklı bir indirme konumu seçmiş de olabilirsiniz. Gerektiğinde komutta herhangi bir değişiklik yapın.

> [!TIP]
> Çevrimdışı FFU yüklemek için Gelişmiş Kurtarma Yardımcı'sı kullanmayı planlasanız, flash görüntü indirebilirsiniz. [**HoloLens 2 için geçerli görüntüyü indirin.**](https://aka.ms/hololens2download)


Diğer kaynaklar:
- [Çevrimdışı uygulamaları dağıtma](/microsoft-store/distribute-offline-apps) 
- [DISM uygulama paketi (.appx veya .appxbundle) hizmet komut satırı seçenekleri](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
