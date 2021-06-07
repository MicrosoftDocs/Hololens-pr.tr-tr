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
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="77ea1-104">HoloLens 2 ' yi yeniden başlatın, sıfırlayın veya kurtarın</span><span class="sxs-lookup"><span data-stu-id="77ea1-104">Restart, reset, or recover HoloLens 2</span></span>

## <a name="charge-the-device"></a><span data-ttu-id="77ea1-105">Cihazı ücretlendirme</span><span class="sxs-lookup"><span data-stu-id="77ea1-105">Charge the device</span></span>

>[!IMPORTANT]
> <span data-ttu-id="77ea1-106">Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="77ea1-107">Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="77ea1-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="77ea1-108">Cihazınızın ücretlendirmenin en iyi yolu olan HoloLens 2 ile birlikte gelen [cihazınızın şarj cihazına ve USB Type-C kablosunu](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kullanın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-108">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="77ea1-109">Cihazınızın şarj cihazına, 18W gücü (2a 'da 9V) sağlar.</span><span class="sxs-lookup"><span data-stu-id="77ea1-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="77ea1-110">HoloLens 2 cihazları sağlanan duvar karağını kullanarak, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendiriyolabilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="77ea1-111">Bu aksesuarlar yoksa, mevcut olan cihazınızın şarj cihazına 'ın en az 15W güç desteğine sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="77ea1-112">Mümkünse, cihazı USB üzerinden ücretlendirilecek bir BILGISAYAR kullanmaktan kaçının, bu da yavaş olur.</span><span class="sxs-lookup"><span data-stu-id="77ea1-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="77ea1-113">Cihaz doğru şekilde önyüklendiğinde ve çalışıyorsa, pil ücreti düzeyini denetlemek için üç yol vardır:</span><span class="sxs-lookup"><span data-stu-id="77ea1-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="77ea1-114">HoloLens cihaz Kullanıcı arabiriminin ana menüsünde.</span><span class="sxs-lookup"><span data-stu-id="77ea1-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="77ea1-115">Güç düğmesine ışığı (%40 oranında bir ücret için) görüntüleyin ve en az iki katı LED görmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="77ea1-116">Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.</span><span class="sxs-lookup"><span data-stu-id="77ea1-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="77ea1-117">Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="77ea1-118">HoloLens 'niz açık olduğunda, pil göstergesi pil düzeyini beş artışlarla görüntüler.</span><span class="sxs-lookup"><span data-stu-id="77ea1-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="77ea1-119">Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.</span><span class="sxs-lookup"><span data-stu-id="77ea1-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="77ea1-120">Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.</span><span class="sxs-lookup"><span data-stu-id="77ea1-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="77ea1-121">Ana bilgisayarınızda, **Dosya Gezgini** 'ni açın ve **Bu bilgisayarın** sol tarafında bulunan HoloLens 2 cihazınızı bulun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="77ea1-122">Cihaza sağ tıklayın ve **Özellikler**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="77ea1-123">Bir iletişim kutusu, pil ücreti düzeyini gösterir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 özellikleri ekranı, pil değişim düzeyini gösterir](images/ResetRecovery2.png)

<span data-ttu-id="77ea1-125">Cihaz başlangıç menüsüne önyükleme yapamıyor, ana bilgisayar bilgisayarındaki açık görünüm ve cihaz numaralandırması konusuna göz önünde barının.</span><span class="sxs-lookup"><span data-stu-id="77ea1-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="77ea1-126">Ardından [sorun giderme kılavuzunu](hololens-troubleshooting.md)izleyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-126">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="77ea1-127">Cihazın durumu, sorun giderme kılavuzunda listelenen durumlardan hiçbiriyle eşleşmezse, ana bilgisayar bilgisayarınıza değil güç kaynağına bağlı cihazla [sabit sıfırlama yordamını](hololens-recovery.md#hard-reset-procedure) gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="77ea1-128">Cihazın ücreti için en az bir saat bekleyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-128">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="77ea1-129">Cihazı sıfırlama</span><span class="sxs-lookup"><span data-stu-id="77ea1-129">Reset the device</span></span>

<span data-ttu-id="77ea1-130">Belirli koşullarda, yazılım Kullanıcı arabirimini kullanmadan cihazı el ile sıfırlamanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="77ea1-131">Standart yordam</span><span class="sxs-lookup"><span data-stu-id="77ea1-131">Standard procedure</span></span>

1. <span data-ttu-id="77ea1-132">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="77ea1-133">15 saniye boyunca **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="77ea1-134">Tüm LED 'ler kapalı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="77ea1-135">2-3 saniye bekleyin ve ardından **Güç** düğmesine kısa basın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="77ea1-136">Güç düğmesine yakın LED 'ler açılır ve cihaz başlatılmaya başlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="77ea1-137">Cihazı ana bilgisayara bağlayın ve sonra Device Manager açın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="77ea1-138">(Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="77ea1-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery sapve Yöneticisi](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="77ea1-140">Sabit sıfırlama prosedürü</span><span class="sxs-lookup"><span data-stu-id="77ea1-140">Hard-reset procedure</span></span>

<span data-ttu-id="77ea1-141">Standart sıfırlama yordamı çalışmazsa, sabit sıfırlama yordamını kullanın:</span><span class="sxs-lookup"><span data-stu-id="77ea1-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="77ea1-142">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="77ea1-143">15 saniye boyunca **Ses**  +  **tasarrufu** düğmelerini basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="77ea1-144">Cihaz otomatik olarak yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="77ea1-145">Cihazı ana bilgisayara bağlayın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-145">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="77ea1-146">Device Manager açın (Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve sonra **Device Manager**' i seçin).</span><span class="sxs-lookup"><span data-stu-id="77ea1-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="77ea1-147">Aşağıdaki görüntüde gösterildiği gibi cihazın *Microsoft HoloLens* olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="77ea1-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery Cihaz Yöneticisi 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="77ea1-149">Cihazı Temizleme-yeniden yansıtma</span><span class="sxs-lookup"><span data-stu-id="77ea1-149">Clean-reflash the device</span></span>

<span data-ttu-id="77ea1-150">Olağandışı durumlarda, HoloLens 2 ' yi "temizlemek-Flash" yapmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="77ea1-151">Lütfen temizleme-refflash 'un aşağıdaki sorunları etkilemesini beklenmediğini unutmayın:</span><span class="sxs-lookup"><span data-stu-id="77ea1-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="77ea1-152">Renk dağılımı görüntüleme</span><span class="sxs-lookup"><span data-stu-id="77ea1-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="77ea1-153">Sesle önyükleme, ancak görüntüleme çıktısı yok</span><span class="sxs-lookup"><span data-stu-id="77ea1-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="77ea1-154">1-3-5-LED desenli</span><span class="sxs-lookup"><span data-stu-id="77ea1-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="77ea1-155">Aşırı ısınmasını</span><span class="sxs-lookup"><span data-stu-id="77ea1-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="77ea1-156">İşletim sistemi kilitlenmeleri (uygulama kilitlenmelerinden farklı)</span><span class="sxs-lookup"><span data-stu-id="77ea1-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="77ea1-157">Cihazı kırmanın iki yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="77ea1-158">Her ikisi için, önce [Windows Mağazası 'Ndan Gelişmiş kurtarma Yardımcısı 'nı yüklemeniz](https://www.microsoft.com/store/productId/9P74Z35SFRS8)gerekir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="77ea1-159">Cihazınızı Kırdıysanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="77ea1-160">Varsayılan olarak, Gelişmiş kurtarma Yardımcısı en son özellik yayın derlemesini indirmek üzere ayarlanmıştır, en son özellik sürümü hakkında bilgi edinmek için [Sürüm notlarımızı](hololens-release-notes.md#) okumak üzere buraya bakın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="77ea1-161">Cihazınızı Gelişmiş kurtarma Yardımcısı aracılığıyla yeniden Flash 'a aktarmak üzere en son HoloLens 2 tam Flash Güncelleştirmesi (FFU) paketini almak için, [en son aylık HoloLens 2 görüntüsünü indirmek üzere buraya tıklayın](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="77ea1-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="77ea1-162">Bu sürüm, genel olarak kullanılabilir olan en son yapıya sahiptir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="77ea1-163">Refflash yordamını çalıştırmadan önce, uygulamanın Windows 10 PC 'nizde yüklü ve çalışır durumda olduğundan ve cihazı algılamaya hazırlandığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="77ea1-164">Ayrıca, HoloLens 'nizin en az %40 oranında ücretlendirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-164">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![HoloLens 2 temiz kırflash ekran görüntüsü](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="77ea1-166">Normal yordam</span><span class="sxs-lookup"><span data-stu-id="77ea1-166">Normal procedure</span></span>

1. <span data-ttu-id="77ea1-167">HoloLens cihazı çalışırken, daha önce Gelişmiş kurtarma yardımcısı uygulamasını açtığınız Windows 10 BILGISAYARıNA bağlayın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-167">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="77ea1-168">Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:</span><span class="sxs-lookup"><span data-stu-id="77ea1-168">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 Temizleme refflash başlangıç ekranı](images/ARC2.png)

3. <span data-ttu-id="77ea1-170">Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve yönergeleri izleyerek, yeniden doldurun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-170">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="77ea1-171">El ile yordam</span><span class="sxs-lookup"><span data-stu-id="77ea1-171">Manual procedure</span></span>

<span data-ttu-id="77ea1-172">HoloLens 2 doğru başlamazsa veya Gelişmiş kurtarma Yardımcısı cihazı algılayamazsa, cihazı kurtarma moduna almanız gerekebilir:</span><span class="sxs-lookup"><span data-stu-id="77ea1-172">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="77ea1-173">Cihazın güç kaynağı veya konak bılgısayar bağlantısını kesmek için Type-C kablosunu çıkarın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-173">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="77ea1-174">15 saniye boyunca **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-174">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="77ea1-175">Tüm LED 'Leri kapatması gerekir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-175">All LEDs should turn off.</span></span>

3. <span data-ttu-id="77ea1-176">**Birim yukarı** düğmesine basarken, cihazı başlatmak için **Güç** düğmesine basın ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-176">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="77ea1-177">15 saniye bekleyin ve ardından **birim yukarı** düğmesini serbest bırakın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-177">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="77ea1-178">Yalnızca beş LED 'in ortasının ışığı açılır.</span><span class="sxs-lookup"><span data-stu-id="77ea1-178">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="77ea1-179">Cihazı ana bilgisayara bağlayın ve Device Manager açın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-179">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="77ea1-180">(Windows 10 için **Windows** tuşuna ve sonra **X** tuşuna basın ve ardından **Device Manager**' ı seçin.) Aşağıdaki görüntüde gösterildiği gibi cihazın Microsoft HoloLens olarak doğru şekilde numaralandıryazıldığından emin olun:</span><span class="sxs-lookup"><span data-stu-id="77ea1-180">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="77ea1-182">Cihaz otomatik olarak algılanır ve Gelişmiş kurtarma yardımcı uygulaması kullanıcı arabirimi güncelleştirme işlemini başlatır:</span><span class="sxs-lookup"><span data-stu-id="77ea1-182">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 Temizleme refflash ekranı](images/ARC2.png)

6. <span data-ttu-id="77ea1-184">Gelişmiş kurtarma yardımcı uygulama kullanıcı arabiriminde HoloLens 2 cihazını seçin ve ardından yönergeleri izleyerek refflash 'u tamamlayın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-184">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="77ea1-185">Gelişmiş kurtarma Yardımcısı sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="77ea1-185">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="77ea1-186">Flash 'ı denemeden önce cihazınızın %40 veya daha fazla bir ücret aldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-186">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="77ea1-187">Cihazınızın kilidinin açık olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-187">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="77ea1-188">ARC cihazınızı algılamazsa, bilgisayarınızda dosya Gezgini aracılığıyla cihazınıza bağlanabildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-188">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="77ea1-189">Bunu yaparsanız;</span><span class="sxs-lookup"><span data-stu-id="77ea1-189">If you cannot;</span></span>

    1.  <span data-ttu-id="77ea1-190">Cihazınızın bu bağlantıyı devre dışı bırakan USB ilkeleri olabilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-190">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="77ea1-191">Öyleyse, [El Ile yanıp sönen modu](hololens-recovery.md#manual-procedure)deneyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-191">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="77ea1-192">İlke yoksa, farklı bir USB kablosu deneyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-192">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="77ea1-193">Cihazınızın [1-3-5 yönlü bir model GÖRÜNTÜLEMEMIŞ](hololens2-setup.md#lights-to-indicate-problems)olduğunu denetleyin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-193">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="77ea1-194">Uygulama mağazasını kullanmadan YAYı indirin</span><span class="sxs-lookup"><span data-stu-id="77ea1-194">Download ARC without using the app store</span></span>

<span data-ttu-id="77ea1-195">BT ortamı Windows Mağazası uygulamasının kullanımını engelliyorsa veya perakende mağazası 'na erişimi sınırlayıp, BT Yöneticisi bu uygulamayı "çevrimdışı" bir dağıtım yolu aracılığıyla kullanılabilir hale getirir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-195">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="77ea1-196">BT yöneticileri Ayrıca bu uygulamayı System Center Configuration Manager (SCCM) veya Intune aracılığıyla dağıtabilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-196">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="77ea1-197">Bu kılavuz, Gelişmiş kurtarma Yardımcısı 'na odaklanmaktadır, ancak işlem diğer "çevrimdışı" uygulamalar için de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-197">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="77ea1-198">Dağıtım yolunu etkinleştirmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="77ea1-198">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="77ea1-199">[İş Microsoft Store](https://businessstore.microsoft.com) gidin ve bir Azure Active Directory kimliği kullanarak oturum açın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-199">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="77ea1-200">**Yönet – ayarlar**' a gidin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-200">Go to **Manage – Settings**.</span></span> <span data-ttu-id="77ea1-201">**Alışveriş deneyimi** altında **çevrimdışı uygulamaları göster** ' i açın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-201">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="77ea1-202">**Grubum için mağaza**' a gidin ve [**_Gelişmiş kurtarma Yardımcısı_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)' nı arayın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-202">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="77ea1-203">**Lisans türünü** \**_çevrimdışı_*_ olarak değiştirin ve _ Yönet ' i seçin\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="77ea1-203">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="77ea1-204">**Çevrimdışı kullanım için paketi indirin** altında Ikinci mavi **İndir** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-204">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="77ea1-205">Dosya uzantısının *. appxdemeti* olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="77ea1-205">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="77ea1-206">Bu aşamada, masaüstü BILGISAYARıN internet erişimi varsa, uygulamayı yüklemek için pakete çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-206">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="77ea1-207">Hedef bılgısayarda internet bağlantısı yoksa, şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="77ea1-207">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="77ea1-208">Kodlanamayan lisansı seçin ve ardından **Lisans oluştur**' u seçin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-208">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="77ea1-209">**Gerekli çerçeveler** altında **İndir**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="77ea1-209">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="77ea1-210">Paketi bağımlılık ve lisansa uygulamak için DıSM 'yi kullanın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-210">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="77ea1-211">Yönetici komut isteminden aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="77ea1-211">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="77ea1-212">Bu kod örnekteki sürüm numarası, mevcut olan sürümle eşleşmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-212">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="77ea1-213">Ayrıca, örnekteki farklı bir indirme konumu seçmiş olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="77ea1-213">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="77ea1-214">Gerektiğinde komutta herhangi bir değişiklik yapın.</span><span class="sxs-lookup"><span data-stu-id="77ea1-214">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="77ea1-215">Çevrimdışı bir FFU yüklemek için Gelişmiş kurtarma Yardımcısı kullanmayı planlarken, Flash görüntünüzü indirmek faydalı olabilir.</span><span class="sxs-lookup"><span data-stu-id="77ea1-215">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="77ea1-216">[**HoloLens 2 için geçerli görüntüyü indirin**](https://aka.ms/hololens2download).</span><span class="sxs-lookup"><span data-stu-id="77ea1-216">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="77ea1-217">Diğer kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="77ea1-217">Other resources:</span></span>
- [<span data-ttu-id="77ea1-218">Çevrimdışı uygulamaları dağıtma</span><span class="sxs-lookup"><span data-stu-id="77ea1-218">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="77ea1-219">DıSM uygulama paketi (. appx veya. appxdemeti) komut satırı seçeneklerini sunma</span><span class="sxs-lookup"><span data-stu-id="77ea1-219">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
