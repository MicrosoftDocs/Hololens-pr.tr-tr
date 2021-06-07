---
title: HoloLens 1'i yeniden başlatma, sıfırlama veya kurtarma
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens 1. Nesil'e görüntü gösterme.
keywords: nasıl yapıldığı, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, yazılım sıfırlaması, güç döngüsü, HoloLens, kapatma, wdrt, Windows cihaz kurtarma aracı
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379030"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="eb18c-104">HoloLens'i yeniden başlatma, sıfırlama veya kurtarma (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="eb18c-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="eb18c-105">HoloLens'iniz ile ilgili sorunlar yaşıyorsanız yeniden başlatmayı, sıfırlamayı veya hatta cihaz kurtarmayı kullanarak cihazı ters eğik çizgiyle sıfırlamayı sınabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="eb18c-106">Bu makale, önerilen kurtarma adımlarında sırayla size yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="eb18c-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="eb18c-107">Bir HoloLens 2'nin kurtarılma sürecini arıyorsanız, bu işlem farklı olduğu için bkz. [HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)kurtarma.</span><span class="sxs-lookup"><span data-stu-id="eb18c-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="eb18c-108">Bu makale HoloLens cihazına ve yazılımına odaklanır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="eb18c-109">Hologramlar doğru görünmüyorsa hologram kalitesini geliştiren faktörler hakkında bilgi için **[HoloLens](hololens-environment-considerations.md)** ortamıyla ilgili dikkat edilmesi gerekenler'e bakın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="eb18c-110">Yeniden başlat</span><span class="sxs-lookup"><span data-stu-id="eb18c-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="eb18c-111">Cortana'yı kullanarak güvenli bir yeniden başlatma işlemi yapma</span><span class="sxs-lookup"><span data-stu-id="eb18c-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="eb18c-112">HoloLens'i yeniden başlatmanın en güvenli yolu Cortana'yı kullanmaktır. HoloLens ile ilgili bir sorun yaşamanız genellikle ilk denemedir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="eb18c-113">Cortana tüm cihazlarda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="eb18c-114">Cortana tüm HoloLens (1. Nesil) cihazlarda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="eb18c-115">Cortana, Windows Holograpic Sürüm 2004 güncelleştirmeden önceki derlemelerde HoloLens 2 cihazlarında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="eb18c-116">HoloLens'inizi açma.</span><span class="sxs-lookup"><span data-stu-id="eb18c-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="eb18c-117">Kullanıcının oturum açtığından ve cihazın kilidini açmak için parola beklemey olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="eb18c-118">"Hey Cortana, yeniden başlat" veya "Hey Cortana, yeniden başlat" de.</span><span class="sxs-lookup"><span data-stu-id="eb18c-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="eb18c-119">Cortana yanıt verir ve onaylamanızı istenir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="eb18c-120">Sorudan sonra bir ses çalması için bekleyin ve ardından "Evet" der.</span><span class="sxs-lookup"><span data-stu-id="eb18c-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="eb18c-121">Cihaz yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="eb18c-122">Güvenli yeniden başlatma yapmak için güç düğmesini kullanma</span><span class="sxs-lookup"><span data-stu-id="eb18c-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="eb18c-123">Cihazınızı yeniden başlatamaya devam ediyorsanız güç düğmesini kullanarak cihazı yeniden **başlatmayı** deneyin:</span><span class="sxs-lookup"><span data-stu-id="eb18c-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="eb18c-124">Güç düğmesine 5 **saniye** basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="eb18c-125">1 saniye sonra beş LED'in hepsi yavaş yavaş kapatılarak sağdan sola doğru tek tek devre dışı bırakılarak.</span><span class="sxs-lookup"><span data-stu-id="eb18c-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="eb18c-126">5 saniye sonra tüm LED'ler kapalı olur ve kapatma başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="eb18c-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="eb18c-127">Tüm LED'ler kapatıldığında düğmeye basmayı hemen durdurun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="eb18c-128">Kapatma işleminin tamamlanması için 1 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="eb18c-129">Ekranlar kapatılana kadar kapatma işlemi devam ediyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="eb18c-130">Güç düğmesine 1 saniye basılı tutarak **cihazı** yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="eb18c-131">Windows Cihaz Portalı kullanarak güvenli bir yeniden başlatma Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="eb18c-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="eb18c-132">Bu işlem için HoloLens'in bir geliştirici cihazı olarak yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="eb18c-133">daha fazla bilgi için [Windows Cihaz Portalı.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="eb18c-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="eb18c-134">Önceki yordam işe başlatılmazsa, Windows Cihaz Portalı kullanarak [cihazı yeniden başlatmayı deneyin.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="eb18c-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="eb18c-135">Sağ üst köşede cihazı yeniden başlatma veya kapatma seçeneğini bulun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="eb18c-136">Güvenli olmayan bir zorlamalı yeniden başlatma yapma</span><span class="sxs-lookup"><span data-stu-id="eb18c-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="eb18c-137">Önceki yöntemler HoloLens'inizi yeniden başlatmamışsa yeniden başlatmaya zorlar.</span><span class="sxs-lookup"><span data-stu-id="eb18c-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="eb18c-138">Bu yöntem, pilin kaldırılmasına ve yeniden yüklenmesine eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="eb18c-139">Cihazınızı bozuk durumda bırakarak tehlikeli olabilir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="eb18c-140">Böyle bir durumda HoloLens'inizi flash iletirsiniz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="eb18c-141">Bu zararlı olabilecek bir yöntemdir ve yalnızca daha önce adedi yapılan yöntemler işemasa kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="eb18c-142">Güç düğmesine en **az** 10 saniye basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="eb18c-143">Düğmeyi 10 saniyeden uzun süre tutabilir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="eb18c-144">Herhangi bir LED etkinliğini yoksaymak güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="eb18c-145">Düğmeyi bırakın ve 2-3 saniye bekleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="eb18c-146">Güç düğmesine 1 **saniye** basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="eb18c-147">Sorun devam ediyorsa,  tüm pil göstergeleri belirene ve ekran hologramları görüntülemeyi durdurana kadar güç düğmesine 4 saniye basın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="eb18c-148">1 dakika bekleyin ve ardından cihazı **açmak** için güç düğmesine tekrar basın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="eb18c-149">Fabrika ayarlarına sıfırlama</span><span class="sxs-lookup"><span data-stu-id="eb18c-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="eb18c-150">Pilin sıfırlanabilir olması için en az yüzde 40 ücrete ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="eb18c-151">HoloLens'iniz hala sorun yaşıyorsa fabrika durumuna sıfırlamayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="eb18c-152">Bu adım, windows Holographic yazılımının yüklü olduğu sürümü tutar ve diğer her şeyi fabrika ayarlarına döndürür.</span><span class="sxs-lookup"><span data-stu-id="eb18c-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="eb18c-153">Cihazınızı sıfırlarsanız TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="eb18c-154">Sıfırlama yalnızca Windows Holographic'in en son yüklü sürümünü yükleyecek.</span><span class="sxs-lookup"><span data-stu-id="eb18c-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="eb18c-155">Tüm başlatma adımlarını (ayarlama, Wi-Fi'a bağlanma, bir kullanıcı hesabı oluşturma, uygulamaları indirme vb.) tekrarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="eb18c-156">Ayarlar uygulamasını açın ve Kurtarmayı **Güncelleştir'i**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="eb18c-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="eb18c-157">Cihazı **sıfırla seçeneğini** belirleyin ve onay iletiyi okuyun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="eb18c-158">Sıfırlamayı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-158">Confirm the reset.</span></span> <span data-ttu-id="eb18c-159">Cihaz yeniden başlatılır ve bir dizi dönen dişli ve ilerleme çubuğu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="eb18c-160">Bu sürecin tamamlanması için yaklaşık 30 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="eb18c-161">Bu bittiğinde, cihaz "ilk önce" deneyimine yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="eb18c-162">İşletim sistemini yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="eb18c-162">Reinstall the operating system</span></span>

<span data-ttu-id="eb18c-163">Yeniden başlatma ve sıfırlama sonrasında cihaz sorun devam ediyorsa, HoloLens işletim sistemini ve üretici yazılımını yeniden yüklemek için bilgisayarınızda bir kurtarma aracı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="eb18c-164">HoloLens'in sıfırlama için ihtiyacı olan veriler bir .iso, .wim veya .vhd dosyasına benzer bir Tam Flash Güncelleştirme (FFU) içinde paketlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="eb18c-165">FFU görüntü dosyası biçimleri hakkında bilgi edinmek için.</span><span class="sxs-lookup"><span data-stu-id="eb18c-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="eb18c-166">Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens'inize (1. nesil) yeni bir işletim sistemi yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="eb18c-167">Bu aracı kullanmadan önce HoloLens'inizi yeniden başlatmanın veya sıfırlamanın sorunu düzeltup düzeltmesine bakın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="eb18c-168">Kurtarma işlemi biraz zaman alır.</span><span class="sxs-lookup"><span data-stu-id="eb18c-168">The recovery process may take a while.</span></span> <span data-ttu-id="eb18c-169">Bu bittiğinde, Windows Holographic yazılımının en son sürümü yüklenir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="eb18c-170">Aracı kullanmak için en az 4 GB boş Windows 10 veya sonraki bir bilgisayarda çalışmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="eb18c-171">Bu aracı bir sanal makinede çalıştıraabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="eb18c-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="eb18c-172">HoloLens'inizi kurtarma</span><span class="sxs-lookup"><span data-stu-id="eb18c-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="eb18c-173">[Bilgisayarınıza Windows Cihaz Kurtarma Aracı'nı](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) indirin ve yükleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="eb18c-174">HoloLens'iniz ile birlikte gelen Micro USB kablosunu kullanarak HoloLens'i (1. nesil) bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="eb18c-175">Windows Cihaz Kurtarma Aracı'nı açın ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="eb18c-176">HoloLens (1. nesil) otomatik olarak algılanmazsa Cihazım **algılanmadı seçeneğini seçin.**</span><span class="sxs-lookup"><span data-stu-id="eb18c-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="eb18c-177">Ardından yönergeleri izleyerek cihazı kurtarma moduna alın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="eb18c-178">El ile flashing modu</span><span class="sxs-lookup"><span data-stu-id="eb18c-178">Manual flashing mode</span></span>

<span data-ttu-id="eb18c-179">Cihazınız algılanmazsa, cihazı yanıp sönme moduna koymak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="eb18c-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="eb18c-180">Cihazı herhangi bir güç kaynağından çıkarın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="eb18c-181">Cihaz açıksa, tamamen **kapatana** kadar güç düğmesini basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="eb18c-182">Birimi **yukarı doğru** tutun ve güç düğmesine kısa **bir süre** dokunun.</span><span class="sxs-lookup"><span data-stu-id="eb18c-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="eb18c-183">Cihazın başlaması ve yalnızca ortadaki LED'i görüntülemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="eb18c-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="eb18c-184">Cihazı bilgisayarınıza takın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="eb18c-185">Windows Cihaz Kurtarma Aracı'nı açın.</span><span class="sxs-lookup"><span data-stu-id="eb18c-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="eb18c-186">Cihazım **algılanmadı'yi ve ardından** **HoloLens'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="eb18c-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="eb18c-187">Cihazınızı kurtarmak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="eb18c-187">Follow the instructions to recover your device.</span></span>
