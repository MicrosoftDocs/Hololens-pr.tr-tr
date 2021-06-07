---
title: HoloLens'i güncelleştirme
description: HoloLens derleme numaranızı denetlemeyi, cihaz güncelleştirmelerini takip etmeyi, Insiders Programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl güncelleştirmesi, geri alma, HoloLens, derlemeyi denetleme, derleme numarası
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379059"
---
# <a name="update-hololens"></a><span data-ttu-id="cc6eb-104">HoloLens'i güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-104">Update HoloLens</span></span>

<span data-ttu-id="cc6eb-105">HoloLens, Windows Update diğer cihazlarda olduğu gibi Windows 10 kullanır.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="cc6eb-106">HoloLens'iniz, hazır bekleyen durumda olsa bile, güç kaynağına takılı ve İnternet'e bağlı olduğunda sistem güncelleştirmelerini otomatik olarak indirir ve yükleyebilir.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="cc6eb-107">Bu makalede, HoloLens araçları şu adımlarda adım adım ilerler:</span><span class="sxs-lookup"><span data-stu-id="cc6eb-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="cc6eb-108">geçerli işletim sistemi sürümüm (derleme numarası) görüntüleme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="cc6eb-109">güncelleştirmeleri denetleme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-109">checking for updates</span></span>
- <span data-ttu-id="cc6eb-110">HoloLens'i el ile güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-110">manually updating HoloLens</span></span>
- <span data-ttu-id="cc6eb-111">daha eski bir güncelleştirmeye geri dönme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="cc6eb-112">İşletim sistemi sürümünizi (derleme numarası) denetleme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="cc6eb-113">Ayarlar uygulamasını açarak ve Hakkında Sistem'i seçerek sistem sürüm numarasını (derleme numarası)  >  **doğruabilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="cc6eb-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="cc6eb-114">Güncelleştirmeleri denetleme ve el ile güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="cc6eb-114">Check for updates and manually update</span></span>

<span data-ttu-id="cc6eb-115">Ayarlarda güncelleştirmeleri istediğiniz zaman kontrol edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="cc6eb-116">Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri kontrol etmek için:</span><span class="sxs-lookup"><span data-stu-id="cc6eb-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="cc6eb-117">**Ayarlar** uygulamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="cc6eb-118">Update **& Security Windows Update**  >  .</span><span class="sxs-lookup"><span data-stu-id="cc6eb-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="cc6eb-119">**Güncelleştirmeleri denetle**’yi seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-119">Select **Check for updates**.</span></span>

<span data-ttu-id="cc6eb-120">Bir güncelleştirme varsa, yeni sürümü indirmeye başlar.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="cc6eb-121">İndirme işlemi tamamlandıktan sonra, yüklemeyi **tetiklemek için** Şimdi Yeniden Başlat düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="cc6eb-122">Cihazınız %40'ın altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamaz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="cc6eb-123">HoloLens güncelleştirmeyi yüklerken dönen dişliler ve ilerleme göstergesi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="cc6eb-124">HoloLens'inizi bu süre boyunca kapatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="cc6eb-125">Yükleme tamamlandıktan sonra otomatik olarak yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="cc6eb-126">HoloLens aynı anda bir güncelleştirme uygular.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="cc6eb-127">HoloLens'iniz en son sürümün arkasında birden fazla sürüm varsa, güncelleştirme işlemini tamamen güncel hale getirmek için birden çok kez çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="cc6eb-128">Geri dön bir sürüme - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="cc6eb-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="cc6eb-129">Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek istiyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cc6eb-130">HoloLens'inizi önceki sürüme sıfırlamak için Gelişmiş Kurtarma Yardımcı'yı kullanarak bunu yapabiliriz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cc6eb-131">Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cc6eb-132">HoloLens 2'nin önceki bir sürümüne dönmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="cc6eb-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="cc6eb-133">Bilgisayarınıza takılı telefon veya Windows cihazına sahip olmadığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cc6eb-134">Bilgisayarınızda, Gelişmiş Kurtarma [Yardımcı'sı'Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="cc6eb-135">En son [HoloLens 2 yayınlarını indirin.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="cc6eb-136">Bu indirmeleri bitirdikten sonra Dosya Gezgini **İndirmeleri'ni**  >  **açın.**</span><span class="sxs-lookup"><span data-stu-id="cc6eb-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cc6eb-137">Az önce indirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cc6eb-138">HoloLens'i USB-A'den USB-C'ye kablo kullanarak bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="cc6eb-139">(HoloLens'inizi bağlamak için başka kablolar kullanıyorsanız bile bu en iyi şekilde çalışır.)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cc6eb-140">Gelişmiş Kurtarma Yardımcı, HoloLens'inizi otomatik olarak algılar.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="cc6eb-141">Yeni **kutucuğu Microsoft HoloLens** seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cc6eb-142">Sonraki ekranda El ile paket **seçimi'ne** tıklayın ve ardından 4. adımda sıkıştırmayı açmak istediğiniz klasörde yer alan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="cc6eb-143">(.ffu uzantısına sahip bir dosya bulun.)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cc6eb-144">Yazılım **yükle'yi** seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="cc6eb-145">Geri dön bir sürüme - HoloLens (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="cc6eb-146">Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek istiyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cc6eb-147">HoloLens'inizi önceki sürüme sıfırlamak için Windows Cihaz Kurtarma Aracı'nı kullanarak bunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cc6eb-148">Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cc6eb-149">HoloLens 1'in önceki bir sürümüne dönmek için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="cc6eb-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="cc6eb-150">Bilgisayarınıza takılı telefon veya Windows cihazına sahip olmadığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cc6eb-151">Bilgisayarınızda Windows Cihaz Kurtarma [Aracı'nı (WDRT) indirin.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="cc6eb-152">[HoloLens Yıldönümü Güncelleştirmesi kurtarma paketini indirin.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="cc6eb-153">İndirmeler tamam olduğunda Dosya Gezgini **İndirmeleri'ni**  >  **açın.**</span><span class="sxs-lookup"><span data-stu-id="cc6eb-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cc6eb-154">Az önce indirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cc6eb-155">HoloLens'inizi, birlikte gelen mikro USB kablosunu kullanarak bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="cc6eb-156">(HoloLens'inizi bağlamak için başka kablolar kullanıyorsanız bile bu en iyi şekilde çalışır.)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cc6eb-157">WDRT, HoloLens'inizi otomatik olarak algılar.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="cc6eb-158">Yeni **kutucuğu Microsoft HoloLens** seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cc6eb-159">Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve 4. adımda sıkıştırmayı açmak istediğiniz klasörde yer alan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="cc6eb-160">(.ffu uzantısına sahip bir dosya bulun.)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cc6eb-161">Yazılım **yükle'yi** seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="cc6eb-162">WDRT HoloLens'inizi algılamazsa bilgisayarınızı yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="cc6eb-163">Bu işe uymazsa Cihazım algılanmadı'yi **seçin,** **Microsoft HoloLens'ı** seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="cc6eb-164">HoloLens Windows Insider Programı de sanal</span><span class="sxs-lookup"><span data-stu-id="cc6eb-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="cc6eb-165">HoloLens'in en son özelliklerini görmek ister misiniz?</span><span class="sxs-lookup"><span data-stu-id="cc6eb-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="cc6eb-166">Öyleyse, aşağıdaki Windows Insider Programı; Genel kamuya açık olmadan önce HoloLens yazılım güncelleştirmelerinin önizleme derlemelerine erişeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="cc6eb-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="cc6eb-167">[Microsoft HoloLens için Windows Insider önizlemesini Microsoft HoloLens.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="cc6eb-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
