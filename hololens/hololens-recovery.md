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
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923644"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="bc360-104">HoloLens 2 ' yi yeniden başlatın, sıfırlayın veya kurtarın</span><span class="sxs-lookup"><span data-stu-id="bc360-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bc360-105">Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="bc360-106">Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="bc360-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="bc360-107">Cihazınızın ücretlendirmenin en iyi yolu olan HoloLens 2 ile birlikte gelen [cihazınızın şarj cihazına ve USB Type-C kablosunu](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kullanın.</span><span class="sxs-lookup"><span data-stu-id="bc360-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="bc360-108">Cihazınızın şarj cihazına, 18W gücü (2a 'da 9V) sağlar.</span><span class="sxs-lookup"><span data-stu-id="bc360-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="bc360-109">HoloLens 2 cihazları sağlanan duvar karağını kullanarak, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendiriyolabilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="bc360-110">Bu aksesuarlar yoksa, mevcut olan cihazınızın şarj cihazına 'ın en az 15W güç desteğine sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="bc360-111">Mümkünse, cihazı USB üzerinden ücretlendirilecek bir BILGISAYAR kullanmaktan kaçının, bu da yavaş olur.</span><span class="sxs-lookup"><span data-stu-id="bc360-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="bc360-112">Cihaz doğru şekilde önyüklendiğinde ve çalışıyorsa, pil ücreti düzeyini denetlemek için üç yol vardır:</span><span class="sxs-lookup"><span data-stu-id="bc360-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="bc360-113">HoloLens cihaz Kullanıcı arabiriminin ana menüsünde.</span><span class="sxs-lookup"><span data-stu-id="bc360-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="bc360-114">Güç düğmesine ışığı (%40 oranında bir ücret için) görüntüleyin ve en az iki katı LED görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="bc360-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="bc360-115">Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.</span><span class="sxs-lookup"><span data-stu-id="bc360-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="bc360-116">Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.</span><span class="sxs-lookup"><span data-stu-id="bc360-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="bc360-117">HoloLens 'niz açık olduğunda, pil göstergesi pil düzeyini beş artışlarla görüntüler.</span><span class="sxs-lookup"><span data-stu-id="bc360-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="bc360-118">Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.</span><span class="sxs-lookup"><span data-stu-id="bc360-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="bc360-119">Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.</span><span class="sxs-lookup"><span data-stu-id="bc360-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="bc360-120">Ana bilgisayarınızda, **Dosya Gezgini** 'ni açın ve **Bu bilgisayarın** sol tarafında bulunan HoloLens 2 cihazınızı bulun.</span><span class="sxs-lookup"><span data-stu-id="bc360-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="bc360-121">Cihaza sağ tıklayın ve **Özellikler**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="bc360-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="bc360-122">Bir iletişim kutusu, pil ücreti düzeyini gösterir.</span><span class="sxs-lookup"><span data-stu-id="bc360-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 özellikleri ekranı, pil değişim düzeyini gösterir](images/ResetRecovery2.png)

<span data-ttu-id="bc360-124">Cihaz başlangıç menüsüne önyükleme yapamıyor, ana bilgisayar bilgisayarındaki açık görünüm ve cihaz numaralandırması konusuna göz önünde barının.</span><span class="sxs-lookup"><span data-stu-id="bc360-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="bc360-125">Ardından [sorun giderme kılavuzunu](hololens-troubleshooting.md)izleyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="bc360-126">Cihazın durumu, sorun giderme kılavuzunda listelenen durumlardan hiçbiriyle eşleşmezse, ana bilgisayar bilgisayarınıza değil güç kaynağına bağlı cihazla [sabit sıfırlama yordamını](hololens-recovery.md#hard-reset-procedure) gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="bc360-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="bc360-127">Cihazın ücreti için en az bir saat bekleyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="bc360-128">Cihazı sıfırlama</span><span class="sxs-lookup"><span data-stu-id="bc360-128">Reset the device</span></span>

<span data-ttu-id="bc360-129">Belirli koşullarda, yazılım Kullanıcı arabirimini kullanmadan cihazı el ile sıfırlamanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="bc360-130">Standart yordam</span><span class="sxs-lookup"><span data-stu-id="bc360-130">Standard procedure</span></span>

1. <span data-ttu-id="bc360-131">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="bc360-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bc360-132">15 saniye boyunca **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="bc360-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bc360-133">Tüm LED 'ler kapalı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="bc360-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="bc360-134">2-3 saniye bekleyin ve ardından **Güç** düğmesine kısa basın.</span><span class="sxs-lookup"><span data-stu-id="bc360-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="bc360-135">Güç düğmesine yakın LED 'ler açılır ve cihaz başlatılmaya başlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="bc360-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="bc360-136">Cihazı ana bilgisayara bağlayın ve sonra Device Manager açın.</span><span class="sxs-lookup"><span data-stu-id="bc360-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="bc360-137">(Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="bc360-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery sapve Yöneticisi](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="bc360-139">Sabit sıfırlama prosedürü</span><span class="sxs-lookup"><span data-stu-id="bc360-139">Hard-reset procedure</span></span>

<span data-ttu-id="bc360-140">Standart sıfırlama yordamı çalışmazsa, sabit sıfırlama yordamını kullanın:</span><span class="sxs-lookup"><span data-stu-id="bc360-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="bc360-141">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="bc360-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bc360-142">15 saniye boyunca **Ses**  +  **tasarrufu** düğmelerini basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="bc360-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="bc360-143">Cihaz otomatik olarak yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="bc360-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="bc360-144">Cihazı ana bilgisayara bağlayın.</span><span class="sxs-lookup"><span data-stu-id="bc360-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="bc360-145">Device Manager açın (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve sonra **Device Manager**' i seçin).</span><span class="sxs-lookup"><span data-stu-id="bc360-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="bc360-146">Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="bc360-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery Cihaz Yöneticisi 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="bc360-148">Cihazı Temizleme-yeniden yansıtma</span><span class="sxs-lookup"><span data-stu-id="bc360-148">Clean-reflash the device</span></span>

<span data-ttu-id="bc360-149">Olağandışı durumlarda, HoloLens 2 ' yi "temizlemek-Flash" yapmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="bc360-150">Lütfen temizleme-refflash 'un aşağıdaki sorunları etkilemesini beklenmediğini unutmayın:</span><span class="sxs-lookup"><span data-stu-id="bc360-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="bc360-151">Renk dağılımı görüntüleme</span><span class="sxs-lookup"><span data-stu-id="bc360-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="bc360-152">Sesle önyükleme, ancak görüntüleme çıktısı yok</span><span class="sxs-lookup"><span data-stu-id="bc360-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="bc360-153">1-3-5-LED desenli</span><span class="sxs-lookup"><span data-stu-id="bc360-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="bc360-154">Aşırı ısınmasını</span><span class="sxs-lookup"><span data-stu-id="bc360-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="bc360-155">İşletim sistemi kilitlenmeleri (uygulama kilitlenmelerinden farklı)</span><span class="sxs-lookup"><span data-stu-id="bc360-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="bc360-156">Cihazı kırmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="bc360-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="bc360-157">Her ikisi için, önce [Windows Mağazası 'Ndan Gelişmiş kurtarma Yardımcısı 'nı yüklemeniz](https://www.microsoft.com/store/productId/9P74Z35SFRS8)gerekir.</span><span class="sxs-lookup"><span data-stu-id="bc360-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="bc360-158">Cihazınızı Kırdıysanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.</span><span class="sxs-lookup"><span data-stu-id="bc360-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="bc360-159">Varsayılan olarak, Gelişmiş kurtarma Yardımcısı en son özellik yayın derlemesini indirmek üzere ayarlanmıştır, en son özellik sürümü hakkında bilgi edinmek için [Sürüm notlarımızı](hololens-release-notes.md#) okumak üzere buraya bakın.</span><span class="sxs-lookup"><span data-stu-id="bc360-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="bc360-160">Cihazınızı Gelişmiş kurtarma Yardımcısı aracılığıyla yeniden Flash 'a aktarmak üzere en son HoloLens 2 tam Flash Güncelleştirmesi (FFU) paketini almak için, [en son aylık HoloLens 2 görüntüsünü indirmek üzere buraya tıklayın](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bc360-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="bc360-161">Bu sürüm, genel olarak kullanılabilir olan en son yapıya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="bc360-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="bc360-162">Refflash yordamını çalıştırmadan önce, uygulamanın Windows 10 PC 'nizde yüklü ve çalışır durumda olduğundan ve cihazı algılamaya hazırlandığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="bc360-163">Ayrıca, HoloLens 'nizin en az %40 oranında ücretlendirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 temiz kırflash ekran görüntüsü](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="bc360-165">Normal yordam</span><span class="sxs-lookup"><span data-stu-id="bc360-165">Normal procedure</span></span>

1. <span data-ttu-id="bc360-166">HoloLens cihazı çalışırken, daha önce Gelişmiş kurtarma yardımcısı uygulamasını açtığınız Windows 10 BILGISAYARıNA bağlayın.</span><span class="sxs-lookup"><span data-stu-id="bc360-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="bc360-167">Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:</span><span class="sxs-lookup"><span data-stu-id="bc360-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 Temizleme refflash başlangıç ekranı](images/ARC2.png)

3. <span data-ttu-id="bc360-169">Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve yönergeleri izleyerek, yeniden doldurun.</span><span class="sxs-lookup"><span data-stu-id="bc360-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="bc360-170">El ile yordam</span><span class="sxs-lookup"><span data-stu-id="bc360-170">Manual procedure</span></span>

<span data-ttu-id="bc360-171">HoloLens 2 doğru başlamazsa veya Gelişmiş kurtarma Yardımcısı cihazı algılayamazsa, cihazı kurtarma moduna almanız gerekebilir:</span><span class="sxs-lookup"><span data-stu-id="bc360-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="bc360-172">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="bc360-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="bc360-173">15 saniye boyunca **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="bc360-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="bc360-174">Tüm LED 'Leri kapatması gerekir.</span><span class="sxs-lookup"><span data-stu-id="bc360-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="bc360-175">**Birim yukarı** düğmesine basarken, cihazı başlatmak için **Güç** düğmesine basın ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="bc360-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="bc360-176">15 saniye bekleyin ve ardından **birim yukarı** düğmesini serbest bırakın.</span><span class="sxs-lookup"><span data-stu-id="bc360-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="bc360-177">Yalnızca beş LED 'in ortasının ışığı açılır.</span><span class="sxs-lookup"><span data-stu-id="bc360-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="bc360-178">Cihazı ana bilgisayara bağlayın ve Device Manager açın.</span><span class="sxs-lookup"><span data-stu-id="bc360-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="bc360-179">(Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın Microsoft HoloLens olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="bc360-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="bc360-181">Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:</span><span class="sxs-lookup"><span data-stu-id="bc360-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 Temizleme refflash ekranı](images/ARC2.png)

6. <span data-ttu-id="bc360-183">Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve ardından yönergeleri izleyerek refflash 'u tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="bc360-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="bc360-184">Gelişmiş kurtarma Yardımcısı sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="bc360-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="bc360-185">Flash 'ı denemeden önce cihazınızın %40 veya daha fazla bir ücret aldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="bc360-186">Cihazınızın kilidinin açık olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="bc360-187">ARC cihazınızı algılamazsa, bilgisayarınızda dosya Gezgini aracılığıyla cihazınıza bağlanabildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="bc360-188">Bunu yaparsanız;</span><span class="sxs-lookup"><span data-stu-id="bc360-188">If you cannot;</span></span>

    1.  <span data-ttu-id="bc360-189">Cihazınızın bu bağlantıyı devre dışı bırakan USB ilkeleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="bc360-190">Öyleyse, [El Ile yanıp sönen modu](hololens-recovery.md#manual-procedure)deneyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="bc360-191">İlke yoksa, farklı bir USB kablosu deneyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="bc360-192">Cihazınızın [1-3-5 yönlü bir model GÖRÜNTÜLEMEMIŞ](hololens2-setup.md#lights-to-indicate-problems)olduğunu denetleyin.</span><span class="sxs-lookup"><span data-stu-id="bc360-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="bc360-193">Uygulama mağazasını kullanmadan YAYı indirin</span><span class="sxs-lookup"><span data-stu-id="bc360-193">Download ARC without using the app store</span></span>

<span data-ttu-id="bc360-194">BT ortamı Windows Mağazası uygulamasının kullanımını engelliyorsa veya perakende mağazası 'na erişimi sınırlayıp, BT Yöneticisi bu uygulamayı "çevrimdışı" bir dağıtım yolu aracılığıyla kullanılabilir hale getirir.</span><span class="sxs-lookup"><span data-stu-id="bc360-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="bc360-195">BT yöneticileri Ayrıca bu uygulamayı System Center Configuration Manager (SCCM) veya Intune aracılığıyla dağıtabilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="bc360-196">Bu kılavuz, Gelişmiş kurtarma Yardımcısı 'na odaklanmaktadır, ancak işlem diğer "çevrimdışı" uygulamalar için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="bc360-197">Dağıtım yolunu etkinleştirmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="bc360-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="bc360-198">[İş Microsoft Store](https://businessstore.microsoft.com) gidin ve bir Azure Active Directory kimliği kullanarak oturum açın.</span><span class="sxs-lookup"><span data-stu-id="bc360-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="bc360-199">**Yönet – ayarlar**' a gidin.</span><span class="sxs-lookup"><span data-stu-id="bc360-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="bc360-200">**Alışveriş deneyimi** altında **çevrimdışı uygulamaları göster** ' i açın.</span><span class="sxs-lookup"><span data-stu-id="bc360-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="bc360-201">**Grubum için mağaza**' a gidin ve [**_Gelişmiş kurtarma Yardımcısı_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)' nı arayın.</span><span class="sxs-lookup"><span data-stu-id="bc360-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="bc360-202">**Lisans türünü** \**_çevrimdışı_*_ olarak değiştirin ve _ Yönet ' i seçin\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="bc360-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="bc360-203">**Çevrimdışı kullanım için paketi indirin** altında Ikinci mavi **İndir** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="bc360-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="bc360-204">Dosya uzantısının *. appxdemeti* olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc360-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="bc360-205">Bu aşamada, masaüstü BILGISAYARıN internet erişimi varsa, uygulamayı yüklemek için pakete çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="bc360-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="bc360-206">Hedef bılgısayarda internet bağlantısı yoksa, şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="bc360-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="bc360-207">Kodlanamayan lisansı seçin ve ardından **Lisans oluştur**' u seçin.</span><span class="sxs-lookup"><span data-stu-id="bc360-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="bc360-208">**Gerekli çerçeveler** altında **İndir**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="bc360-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="bc360-209">Paketi bağımlılık ve lisansa uygulamak için DıSM 'yi kullanın.</span><span class="sxs-lookup"><span data-stu-id="bc360-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="bc360-210">Yönetici komut isteminden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="bc360-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="bc360-211">Bu kod örnekteki sürüm numarası, mevcut olan sürümle eşleşmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="bc360-212">Ayrıca, örnekteki farklı bir indirme konumu seçmiş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc360-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="bc360-213">Gerektiğinde komutta herhangi bir değişiklik yapın.</span><span class="sxs-lookup"><span data-stu-id="bc360-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="bc360-214">Çevrimdışı bir FFU yüklemek için Gelişmiş kurtarma Yardımcısı kullanmayı planlarken, Flash görüntünüzü indirmek faydalı olabilir.</span><span class="sxs-lookup"><span data-stu-id="bc360-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="bc360-215">[**HoloLens 2 için geçerli görüntüyü indirin**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="bc360-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="bc360-216">Diğer kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="bc360-216">Other resources:</span></span>
- [<span data-ttu-id="bc360-217">Çevrimdışı uygulamaları dağıtma</span><span class="sxs-lookup"><span data-stu-id="bc360-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="bc360-218">DıSM uygulama paketi (. appx veya. appxdemeti) komut satırı seçeneklerini sunma</span><span class="sxs-lookup"><span data-stu-id="bc360-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
