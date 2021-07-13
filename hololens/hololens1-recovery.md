---
title: Yeniden başlatma, sıfırlama veya kurtarma HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows 1. Nesil'e bir görüntü HoloLens Için Cihaz Kurtarma Aracı'nı kullanma.
keywords: nasıl yapıldığı, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, yazılım sıfırlama, güç döngüsü, HoloLens, kapatma, wdrt, Windows cihaz kurtarma aracı
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635237"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="5b85a-104">Yeniden başlatma, sıfırlama veya HoloLens (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="5b85a-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="5b85a-105">Cihaz kurtarma işlemiyle ilgili sorunlar HoloLens, yeniden başlatmayı veya sıfırlamayı veya hatta cihaz kurtarmayı kullanarak cihazı yeniden başlatmayı sınabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="5b85a-106">Bu makale, önerilen kurtarma adımlarında sırayla size yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b85a-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="5b85a-107">2. bir HoloLens kurtarmak için bkz. Bu işlem [farklı HoloLens 2](hololens-recovery.md)kurtarma.</span><span class="sxs-lookup"><span data-stu-id="5b85a-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="5b85a-108">Bu makale, cihaz ve HoloLens yazılıma odaklanır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="5b85a-109">Hologramlar doğru görünmüyorsa, hologram **[kalitesini HoloLens](hololens-environment-considerations.md)** faktörler hakkında bilgi için bkz. ortamla ilgili dikkat edilmesi gerekenler.</span><span class="sxs-lookup"><span data-stu-id="5b85a-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="5b85a-110">Yeniden başlat</span><span class="sxs-lookup"><span data-stu-id="5b85a-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="5b85a-111">Cortana kullanarak güvenli bir yeniden başlatma Cortana</span><span class="sxs-lookup"><span data-stu-id="5b85a-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="5b85a-112">HoloLens'ı yeniden başlatmanın en güvenli yolu, Cortana kullanarak yeniden başlatmanın en güvenli yoludur. Bu, genellikle HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b85a-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="5b85a-113">Cortana tüm cihazlarda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="5b85a-114">Cortana tüm HoloLens (1. Nesil) cihazlarda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="5b85a-115">Cortana, HoloLens Holograpic Sürüm 2004 güncelleştirme Windows derlemelerde 2 cihaz üzerinde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="5b85a-116">Kendi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b85a-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="5b85a-117">Kullanıcının oturum açtığından ve cihazın kilidini açmak için parola beklemey olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="5b85a-118">"Hey Cortana, yeniden başlat" veya "Hey Cortana, yeniden başlat" diyelim.</span><span class="sxs-lookup"><span data-stu-id="5b85a-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="5b85a-119">Cortana yanıt verir ve onaylamanızı istenir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="5b85a-120">Sorudan sonra bir ses çalması için bekleyin ve ardından "Evet" der.</span><span class="sxs-lookup"><span data-stu-id="5b85a-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="5b85a-121">Cihaz yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="5b85a-122">Güvenli yeniden başlatma yapmak için güç düğmesini kullanma</span><span class="sxs-lookup"><span data-stu-id="5b85a-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="5b85a-123">Cihazınızı yeniden başlatamaya devam ediyorsanız güç düğmesini kullanarak cihazı yeniden **başlatmayı** deneyin:</span><span class="sxs-lookup"><span data-stu-id="5b85a-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="5b85a-124">Güç düğmesine 5 **saniye** basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="5b85a-125">1 saniye sonra, beş LED'in hepsi yanacak ve ardından sağdan sola doğru yavaş bir şekilde kapatacak.</span><span class="sxs-lookup"><span data-stu-id="5b85a-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="5b85a-126">5 saniye sonra tüm LED'ler kapalı olur ve kapatma başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="5b85a-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="5b85a-127">Tüm LED'ler kapatıldığında düğmeye basmayı hemen durdurun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="5b85a-128">Kapatma işleminin tamamlanması için 1 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="5b85a-129">Ekranlar kapatılana kadar kapatma işlemi devam ediyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="5b85a-130">Güç düğmesine 1 saniye basılı tutarak **cihazı** yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="5b85a-131">Windows Cihaz Portalı kullanarak güvenli bir yeniden başlatma Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="5b85a-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="5b85a-132">Bu işlem için HoloLens bir geliştirici cihazı olarak yapılandırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="5b85a-133">daha fazla bilgi için [Windows Cihaz Portalı.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="5b85a-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="5b85a-134">Önceki yordam işe başlatılmazsa, Windows Cihaz Portalı kullanarak cihazı [yeniden başlatmayı deneyin.](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="5b85a-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="5b85a-135">Sağ üst köşede cihazı yeniden başlatma veya kapatma seçeneğini bulun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="5b85a-136">Güvenli olmayan bir zorlamalı yeniden başlatma yapma</span><span class="sxs-lookup"><span data-stu-id="5b85a-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="5b85a-137">Önceki yöntemler uygulamanızı yeniden başlatmadı HoloLens yeniden başlatmaya zorlar.</span><span class="sxs-lookup"><span data-stu-id="5b85a-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="5b85a-138">Bu yöntem, pilin kaldırılmasına ve yeniden yüklenmesine eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="5b85a-139">Cihazınızı bozuk durumda bırakarak tehlikeli olabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="5b85a-140">Böyle bir durumda, kendi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b85a-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="5b85a-141">Bu zararlı olabilecek bir yöntemdir ve yalnızca daha önce adedi yapılan yöntemler işemasa kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="5b85a-142">Güç düğmesine en **az** 10 saniye basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="5b85a-143">Düğmeyi 10 saniyeden uzun süre tutabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="5b85a-144">Herhangi bir LED etkinliğini yoksaymak güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="5b85a-145">Düğmeyi bırakın ve 2-3 saniye bekleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="5b85a-146">Güç düğmesine 1 **saniye** basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="5b85a-147">Sorun devam ediyorsanız,  tüm pil göstergeleri belirene ve ekran hologramları görüntülemeyi durdurana kadar güç düğmesine 4 saniye basın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="5b85a-148">1 dakika bekleyin ve ardından cihazı **açmak** için güç düğmesine tekrar basın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="5b85a-149">Geri dön bir sürüme - HoloLens (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="5b85a-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="5b85a-150">Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek HoloLens olabilir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="5b85a-151">Bunu yapmak için Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens önceki sürüme sıfırlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="5b85a-152">Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.</span><span class="sxs-lookup"><span data-stu-id="5b85a-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="5b85a-153">HoloLens 1'in önceki bir sürümüne dönmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="5b85a-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="5b85a-154">Bilgisayarınıza takılı telefon veya Windows emin olun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="5b85a-155">Bilgisayarınızda, Windows [Kurtarma Aracı'nı (WDRT) indirin.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="5b85a-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="5b85a-156">Yıldönümü [HoloLens kurtarma paketini indirin.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="5b85a-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="5b85a-157">İndirmeler tamam olduğunda Dosya Gezgini **İndirmeleri'ni**  >  **açın.**</span><span class="sxs-lookup"><span data-stu-id="5b85a-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="5b85a-158">İndirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak için **Tüm**  >  **Ayıkla'yı** seçin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="5b85a-159">Bağlan, HoloLens mikro USB kablosunu kullanarak bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="5b85a-160">(Bağlantınızı bağlamak için başka kablolar HoloLens bile bu en iyi şekilde çalışır.)</span><span class="sxs-lookup"><span data-stu-id="5b85a-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="5b85a-161">WDRT, kullanıcılarınızı otomatik olarak HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b85a-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="5b85a-162">Yeni **kutucuğu Microsoft HoloLens** seçin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="5b85a-163">Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve 4. adımda sıkıştırması açmak istediğiniz klasörde yer alan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="5b85a-164">(.ffu uzantısına sahip bir dosya bulun.)</span><span class="sxs-lookup"><span data-stu-id="5b85a-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="5b85a-165">Yazılım **yükle'yi** seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="5b85a-166">WDRT, güvenlik sorunlarınızı algılamazsa HoloLens yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="5b85a-167">Bu işe uymazsa **Cihazım** algılanmadı'yi seçin, Microsoft HoloLens'ı seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="5b85a-168">Fabrika ayarlarına sıfırlama</span><span class="sxs-lookup"><span data-stu-id="5b85a-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="5b85a-169">Pilin sıfırlanabilir olması için en az yüzde 40 ücrete ihtiyacı vardır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="5b85a-170">Çalışma HoloLens sorun devam ediyorsa fabrika durumuna sıfırlamayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="5b85a-171">Bu adım, Windows Holographic yazılımının yüklü olduğu sürümü tutar ve diğer her şeyi fabrika ayarlarına döndürür.</span><span class="sxs-lookup"><span data-stu-id="5b85a-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="5b85a-172">Cihazınızı sıfırlarsanız TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="5b85a-173">Sıfırlama yalnızca Holographic'in en son yüklü Windows yüklenir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="5b85a-174">Tüm başlatma adımlarını (ayarlama, Wi-Fi'a bağlanma, bir kullanıcı hesabı oluşturma, uygulamaları indirme vb.) tekrarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="5b85a-175">Uygulama uygulama Ayarlar ve ardından Kurtarmayı **Güncelleştir'i**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="5b85a-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="5b85a-176">Cihazı **sıfırla seçeneğini** belirleyin ve onay iletiyi okuyun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="5b85a-177">Sıfırlamayı onaylayın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-177">Confirm the reset.</span></span> <span data-ttu-id="5b85a-178">Cihaz yeniden başlatılır ve bir dizi dönen dişli ve ilerleme çubuğu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="5b85a-179">Bu sürecin tamamlanması için yaklaşık 30 dakika bekleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="5b85a-180">Bu bittiğinde, cihaz "ilk önce" deneyimine yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="5b85a-181">İşletim sistemini yeniden yükleme</span><span class="sxs-lookup"><span data-stu-id="5b85a-181">Reinstall the operating system</span></span>

<span data-ttu-id="5b85a-182">Yeniden başlatma ve sıfırlama sonrasında cihaz sorun devam ediyorsa, bilgisayarınızda bir kurtarma aracı kullanarak işletim sistemini ve üretici yazılımını HoloLens yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="5b85a-183">Sıfırlama için HoloLens veriler bir .iso, .wim veya .vhd dosyasına benzer bir Tam Flash Güncelleştirme (FFU) içinde paketlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="5b85a-184">FFU görüntü dosyası biçimleri hakkında bilgi edinmek için.</span><span class="sxs-lookup"><span data-stu-id="5b85a-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="5b85a-185">Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens (1. nesil) bilgisayarınıza yeni bir işletim sistemi yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="5b85a-186">Bu aracı kullanmadan önce yeniden başlatma veya sıfırlama HoloLens düzeltin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="5b85a-187">Kurtarma işlemi biraz zaman alır.</span><span class="sxs-lookup"><span data-stu-id="5b85a-187">The recovery process may take a while.</span></span> <span data-ttu-id="5b85a-188">Bu bittiğinde, Windows Holographic yazılımının en son sürümü yüklenir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="5b85a-189">Aracı kullanmak için en az 4 GB boş Windows 10 veya sonraki bir bilgisayarda çalışmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="5b85a-190">Bu aracı bir sanal makinede çalıştıraabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5b85a-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="5b85a-191">HoloLens</span><span class="sxs-lookup"><span data-stu-id="5b85a-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="5b85a-192">Windows Cihaz [Kurtarma Aracı'nı indirip](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) bilgisayarınıza yükleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="5b85a-193">Bağlan HoloLens mikro USB kablosunu kullanarak bilgisayarınıza (1. nesil) HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5b85a-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="5b85a-194">Windows Kurtarma Aracı'nı açın ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="5b85a-195">Cihaz HoloLens (1. nesil) otomatik olarak algılanmazsa Cihazım **algılanmadı seçeneğini seçin.**</span><span class="sxs-lookup"><span data-stu-id="5b85a-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="5b85a-196">Ardından yönergeleri izleyerek cihazı kurtarma moduna alın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="5b85a-197">El ile flashing modu</span><span class="sxs-lookup"><span data-stu-id="5b85a-197">Manual flashing mode</span></span>

<span data-ttu-id="5b85a-198">Cihazınız algılanmazsa, cihazı yanıp sönme moduna koymak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="5b85a-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="5b85a-199">Cihazı herhangi bir güç kaynağından çıkarın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="5b85a-200">Cihaz açıksa, tamamen **kapatana** kadar güç düğmesini basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="5b85a-201">**Ses** düğmesini basılı tutun ve **Power** düğmesine kısaca dokunun.</span><span class="sxs-lookup"><span data-stu-id="5b85a-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="5b85a-202">Cihazın başlaması ve yalnızca ortadaki ışığı görüntülemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="5b85a-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="5b85a-203">Cihazı bilgisayarınıza takın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="5b85a-204">Windows cihaz kurtarma aracını açın.</span><span class="sxs-lookup"><span data-stu-id="5b85a-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="5b85a-205">**Cihazımı** seçin ve **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="5b85a-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="5b85a-206">Cihazınızı kurtarmak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="5b85a-206">Follow the instructions to recover your device.</span></span>
