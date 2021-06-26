---
title: HoloLens 1 ' i yeniden başlatın, sıfırlayın veya kurtarın
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows cihaz kurtarma aracı 'nı kullanarak bir görüntüyü HoloLens 1 gen 'a yakıp söndür.
keywords: Nasıl yapılır, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, geçici sıfırlama, güç çevrimi, HoloLens, kapatma, WDRT, Windows cihaz kurtarma aracı
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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923525"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="aa6e6-104">HoloLens 'i yeniden başlatma, sıfırlama veya kurtarma (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="aa6e6-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="aa6e6-105">HoloLens ile ilgili sorunlar yaşıyorsanız, bir yeniden başlatma veya sıfırlama ya da cihazı cihaz kurtarma kullanarak yeniden faturalandırmayı denemek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="aa6e6-106">Bu makale, önerilen kurtarma adımlarında sırasıyla size rehberlik eder.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="aa6e6-107">HoloLens 2 ' yi kurtarmak istiyorsanız, bu işlem farklı olduğundan [HoloLens 2](hololens-recovery.md)' yi kurtarma bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="aa6e6-108">Bu makale, HoloLens cihazına ve yazılımına odaklanır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="aa6e6-109">Hologramlar doğru görünmüyorsa, hologram kalitesini artıran faktörler hakkında bilgi için bkz. **[HoloLens ortam konuları](hololens-environment-considerations.md)** .</span><span class="sxs-lookup"><span data-stu-id="aa6e6-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="aa6e6-110">Yeniden başlat</span><span class="sxs-lookup"><span data-stu-id="aa6e6-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="aa6e6-111">Cortana 'Yı kullanarak güvenli bir yeniden başlatma</span><span class="sxs-lookup"><span data-stu-id="aa6e6-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="aa6e6-112">HoloLens 'i yeniden başlatmanın en güvenli yolu, genellikle HoloLens ile bir sorunla karşılaştığınızda deneyebileceğiniz ilk şey olan Cortana 'yı kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="aa6e6-113">Cortana tüm cihazlarda kullanılabilir değildir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="aa6e6-114">Cortana, tüm HoloLens (1 gen) cihazlarda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="aa6e6-115">Cortana, Windows Holograpic, sürüm 2004 güncelleştirmesinden önceki derlemelerde bulunan HoloLens 2 cihazlarında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="aa6e6-116">HoloLens 'nizi açın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="aa6e6-117">Bir kullanıcının oturum açtığından ve cihazın kilidini açmak için bir parola beklemediğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="aa6e6-118">"Hey Cortana, yeniden başlatma" veya "Hey Cortana, yeniden başlatma" deyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="aa6e6-119">Cortana yanıt verir ve onaylamanız istenir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="aa6e6-120">Sorudan sonra bir sesin çalmasını bekleyin ve sonra "Evet" deyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="aa6e6-121">Cihaz yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="aa6e6-122">Güvenli yeniden başlatma yapmak için güç düğmesini kullanın</span><span class="sxs-lookup"><span data-stu-id="aa6e6-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="aa6e6-123">Cihazınızı hala yeniden başlatmazsanız, **Güç** düğmesini kullanarak yeniden başlatmayı deneyin:</span><span class="sxs-lookup"><span data-stu-id="aa6e6-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="aa6e6-124">5 saniye boyunca **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="aa6e6-125">1 saniye sonra, beş LED 'in hepsi, bir tane, sağdan sola doğru bir şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="aa6e6-126">5 saniye sonra, başarılı kapatmayı belirten tüm LED 'ler kapalı olur.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="aa6e6-127">Tüm LED 'ler devre dışı bırakıldıktan hemen sonra düğmeye basmayı durdurun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="aa6e6-128">Kapatılma işleminin tamamlanmasını 1 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="aa6e6-129">Ekran kapatıldıktan sonra bile, kapatma devam ediyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="aa6e6-130">1 saniye boyunca **Güç** düğmesine basarak ve basılı tutarak cihazı tekrar açın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="aa6e6-131">Windows cihaz portalı 'nı kullanarak güvenli bir yeniden başlatma</span><span class="sxs-lookup"><span data-stu-id="aa6e6-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="aa6e6-132">Bu işlem için, HoloLens 'in bir geliştirici cihazı olarak yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="aa6e6-133">[Windows cihaz portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)'nda daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="aa6e6-134">Önceki yordam işe yaramazsa, [Windows cihaz portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)'nı kullanarak cihazı yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="aa6e6-135">Sağ üst köşede, cihazı yeniden başlatma veya kapatma seçeneğini bulun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="aa6e6-136">Güvenli olmayan Zorlanmış yeniden başlatma</span><span class="sxs-lookup"><span data-stu-id="aa6e6-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="aa6e6-137">Önceki yöntemler HoloLens 'nizi yeniden başlatmadıysa, yeniden başlatmaya zorlayın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="aa6e6-138">Bu yöntem, pili kaldırma ve yeniden yükleme ile eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="aa6e6-139">Cihazınızı bozulmuş bir durumda bırakabileceğinden tehlikeli olabilir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="aa6e6-140">Bu durumda, HoloLens 'nizi Flash yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="aa6e6-141">Bu, zararlı olabilecek bir yöntemdir ve yalnızca önceden alıntı yapılan Yöntemler çalışmazsa kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="aa6e6-142">En az 10 saniye için **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="aa6e6-143">Bu, düğmeyi 10 saniyeden uzun süre tutmak kadar sürer.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="aa6e6-144">Herhangi bir LED etkinliğini yoksaymak güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="aa6e6-145">Düğmeyi bırakın ve 2-3 saniye bekleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="aa6e6-146">1 saniye için **Güç** düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="aa6e6-147">Hala sorun yaşıyorsanız, tüm pil göstergeleri silinerek ve ekran hologramlar 'ı görüntülemeyi durdurana kadar, 4 saniye boyunca **Güç** düğmesine basın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="aa6e6-148">1 dakika bekleyin ve ardından cihazı açmak için **Güç** düğmesine yeniden basın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="aa6e6-149">Önceki bir sürüme geri dön-HoloLens (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="aa6e6-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="aa6e6-150">Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="aa6e6-151">Bunu, Windows cihaz kurtarma aracı 'nı kullanarak, HoloLens 'nizi önceki sürüme sıfırlamak için yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="aa6e6-152">Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="aa6e6-153">HoloLens 1 ' in önceki bir sürümüne geri dönmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="aa6e6-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="aa6e6-154">Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarının olmadığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="aa6e6-155">Bilgisayarınızda, [Windows cihaz kurtarma aracı 'nı (WDRT)](https://support.microsoft.com/help/12379)indirin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="aa6e6-156">[HoloLens yıldönümü güncelleştirme kurtarma paketini](https://aka.ms/hololensrecovery)indirin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="aa6e6-157">İndirmeler tamamlandığında, **Dosya Gezgini**  >  **İndirmeleri**' ni açın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="aa6e6-158">İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .</span><span class="sxs-lookup"><span data-stu-id="aa6e6-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="aa6e6-159">HoloLens 'nizi, ile birlikte gelen mikro USB kablosunu kullanarak bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="aa6e6-160">(HoloLens 'nizi bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)</span><span class="sxs-lookup"><span data-stu-id="aa6e6-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="aa6e6-161">WDRT, HoloLens 'nizi otomatik olarak algılar.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="aa6e6-162">**Microsoft HoloLens** kutucuğunu seçin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="aa6e6-163">Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve 4. adımda sıkıştırunın bulunduğu klasörde bulunan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="aa6e6-164">(. FFU uzantılı bir dosyayı arayın.)</span><span class="sxs-lookup"><span data-stu-id="aa6e6-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="aa6e6-165">**Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="aa6e6-166">WDRT, HoloLens 'nizi algılamazsa bilgisayarınızı yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="aa6e6-167">Bu işe yaramazsa **cihazımın algılanmadığını** seçin, **Microsoft HoloLens**' i seçin ve ardından yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="aa6e6-168">Fabrika ayarlarına sıfırla</span><span class="sxs-lookup"><span data-stu-id="aa6e6-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="aa6e6-169">Pilin sıfırlanması için en az %40 oranında bir ücret gereklidir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="aa6e6-170">HoloLens 'niz hala bir sorun içeriyorsa, fabrika durumuna sıfırlamayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="aa6e6-171">Bu adım, üzerine yüklenmiş Windows holographic yazılımının sürümünü tutar ve fabrika ayarlarına diğer her şeyi döndürür.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="aa6e6-172">Cihazınızı sıfırlarsanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="aa6e6-173">Sıfırlama yalnızca en son yüklenen Windows holographic sürümünü yükler.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="aa6e6-174">Tüm başlatma adımlarını (ayarlamak, Wi-Fi ' y e bağlanmanız, bir kullanıcı hesabı oluşturmak, uygulamaları indirmek vb.) yeniden yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="aa6e6-175">Ayarlar uygulamasını açın ve ardından kurtarmayı **Güncelleştir**' i seçin  >  .</span><span class="sxs-lookup"><span data-stu-id="aa6e6-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="aa6e6-176">**Cihazı Sıfırla** seçeneğini belirleyin ve onay iletisini okuyun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="aa6e6-177">Sıfırlamayı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-177">Confirm the reset.</span></span> <span data-ttu-id="aa6e6-178">Cihaz yeniden başlatılır ve bir dizi dönen Gears ve ilerleme çubuğu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="aa6e6-179">Bu işlemin tamamlanabilmesi için yaklaşık 30 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="aa6e6-180">İşlem tamamlandığında, cihaz "hazır olmayan" deneyimde yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="aa6e6-181">İşletim sistemini yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="aa6e6-181">Reinstall the operating system</span></span>

<span data-ttu-id="aa6e6-182">Yeniden başlatma ve sıfırlama sonrasında cihaz sorun yaşamaya devam ediyorsa, HoloLens işletim sistemini ve üretici yazılımını yeniden yüklemek için bilgisayarınızda bir kurtarma aracı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="aa6e6-183">HoloLens 'in sıfırlama için ihtiyaç duyacağı veriler, bir. iso,. wim veya. vhd dosyasına benzer bir tam Flash Güncelleştirmesi (FFU) ile paketlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="aa6e6-184">FFU görüntü dosyası biçimleri hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="aa6e6-185">Windows cihaz kurtarma aracı 'nı kullanarak, HoloLens (1. gen) uygulamanıza yeni bir işletim sistemi yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="aa6e6-186">Bu aracı kullanmadan önce, HoloLens 'in yeniden başlatılması veya sıfırlanması sorunu düzeltir bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="aa6e6-187">Kurtarma işlemi biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-187">The recovery process may take a while.</span></span> <span data-ttu-id="aa6e6-188">İşlem tamamlandığında, Windows holographic yazılımının en son sürümü yüklenir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="aa6e6-189">Aracı kullanmak için, en az 4 GB boş depolama alanı ile Windows 10 veya sonraki bir sürümünü çalıştıran bir bilgisayara ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="aa6e6-190">Bu aracı bir sanal makinede çalıştıramazsınız.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="aa6e6-191">HoloLens 'nizi kurtarın</span><span class="sxs-lookup"><span data-stu-id="aa6e6-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="aa6e6-192">[Windows cihaz kurtarma aracı](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 'nı bilgisayarınıza indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="aa6e6-193">HoloLens 'nizle birlikte gelen mikro USB kablosunu kullanarak HoloLens 'i (1. gen) bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="aa6e6-194">Windows cihaz kurtarma aracı 'nı açın ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="aa6e6-195">HoloLens (1. gen) otomatik olarak algılanmazsa **cihazımın algılanmadığını** seçin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="aa6e6-196">Ardından, cihazı kurtarma moduna almak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="aa6e6-197">Manuel yanıp sönen mod</span><span class="sxs-lookup"><span data-stu-id="aa6e6-197">Manual flashing mode</span></span>

<span data-ttu-id="aa6e6-198">Cihazınız algılanmadıysa, bu adımları yanıp sönen moda koymak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="aa6e6-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="aa6e6-199">Cihazı herhangi bir güç kaynağından çıkarın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="aa6e6-200">Cihaz açık ise, tamamen kapanana kadar **Güç** düğmesini basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="aa6e6-201">Birimi **yukarı doğru** tutun ve güç düğmesine kısa bir **süre** dokunun.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="aa6e6-202">Cihazın başlaması ve yalnızca ortadaki LED'i görüntülemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="aa6e6-203">Cihazı bilgisayarınıza takın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="aa6e6-204">Windows Cihaz Kurtarma Aracı'nı açın.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="aa6e6-205">Cihazım **algılanmadı'yi ve ardından** **HoloLens'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="aa6e6-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="aa6e6-206">Cihazınızı kurtarmak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="aa6e6-206">Follow the instructions to recover your device.</span></span>
