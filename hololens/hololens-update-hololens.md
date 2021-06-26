---
title: HoloLens 2 güncelleştirme
description: HoloLens derleme numaranızı nasıl denetleyeceğinizi, cihaz güncelleştirmeleriyle güncel tutmanın yanı sıra Insider programı programına katılıp güncelleştirmeleri geri alma hakkında bilgi edinin.
keywords: Nasıl yapılır, güncelleştirme, geri alma, HoloLens, denetim oluşturma, derleme numarası
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924120"
---
# <a name="update-hololens-2"></a><span data-ttu-id="66066-104">HoloLens 2 güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="66066-104">Update HoloLens 2</span></span>

<span data-ttu-id="66066-105">HoloLens, diğer Windows 10 cihazlarında olduğu gibi Windows Update kullanır.</span><span class="sxs-lookup"><span data-stu-id="66066-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="66066-106">HoloLens 'niz, bekleyen bir yerde olsa bile, Internet 'e bağlıyken ve Internet 'e bağlandığında sistem güncelleştirmelerini otomatik olarak indirip yükler.</span><span class="sxs-lookup"><span data-stu-id="66066-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="66066-107">Bu makale, için HoloLens araçları aracılığıyla izlenecek:</span><span class="sxs-lookup"><span data-stu-id="66066-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="66066-108">geçerli işletim sistemi sürümünüzü görüntüleme (derleme numarası)</span><span class="sxs-lookup"><span data-stu-id="66066-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="66066-109">Güncelleştirmeler denetleniyor</span><span class="sxs-lookup"><span data-stu-id="66066-109">checking for updates</span></span>
- <span data-ttu-id="66066-110">HoloLens 'i el ile güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="66066-110">manually updating HoloLens</span></span>
- <span data-ttu-id="66066-111">daha eski bir güncelleştirmeye geri dönme</span><span class="sxs-lookup"><span data-stu-id="66066-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="66066-112">İşletim sistemi sürümünüzü denetleyin (derleme numarası)</span><span class="sxs-lookup"><span data-stu-id="66066-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="66066-113">Ayarlar uygulamasını açıp **sistem** hakkında ' yı seçerek sistem sürüm numarasını (derleme numarası) doğrulayabilirsiniz  >  .</span><span class="sxs-lookup"><span data-stu-id="66066-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="66066-114">Güncelleştirmeleri denetle ve el ile Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="66066-114">Check for updates and manually update</span></span>

<span data-ttu-id="66066-115">Ayarlarda dilediğiniz zaman güncelleştirmeleri kontrol edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="66066-116">Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri denetlemek için:</span><span class="sxs-lookup"><span data-stu-id="66066-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="66066-117">**Ayarlar** uygulamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="66066-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="66066-118">**& güvenlik**  >  **Windows Update** güncelleştirme bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="66066-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="66066-119">**Güncelleştirmeleri denetle**’yi seçin.</span><span class="sxs-lookup"><span data-stu-id="66066-119">Select **Check for updates**.</span></span>

<span data-ttu-id="66066-120">Bir güncelleştirme varsa, yeni sürümü indirmeye başlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="66066-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="66066-121">İndirme işlemi tamamlandıktan sonra yüklemeyi tetiklemek için **Şimdi yeniden Başlat** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="66066-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="66066-122">Cihazınız %40 ' in altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamacaktır.</span><span class="sxs-lookup"><span data-stu-id="66066-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="66066-123">HoloLens, güncelleştirmeyi yüklerken, dönen Gears ve ilerleme göstergesi görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="66066-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="66066-124">Bu süre boyunca HoloLens 'i kapatmayın.</span><span class="sxs-lookup"><span data-stu-id="66066-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="66066-125">Yüklemeyi tamamladıktan sonra otomatik olarak yeniden başlatılır.</span><span class="sxs-lookup"><span data-stu-id="66066-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="66066-126">HoloLens tek seferde bir güncelleştirme uygular.</span><span class="sxs-lookup"><span data-stu-id="66066-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="66066-127">HoloLens uygulamanız en son arka planda birden fazla sürümdaysanız, tam olarak güncel olması için güncelleştirme işlemini birden çok kez çalıştırmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="66066-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="66066-128">Önceki bir sürüme geri dön</span><span class="sxs-lookup"><span data-stu-id="66066-128">Go back to a previous version</span></span>

<span data-ttu-id="66066-129">Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="66066-130">Önerilen adımlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="66066-130">The recommended steps are:</span></span>

1. <span data-ttu-id="66066-131">Sorununuzu giderip çözebilecekleri hakkında bilgi için desteğe başvurun.</span><span class="sxs-lookup"><span data-stu-id="66066-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="66066-132">**Isteğe bağlı** veya **tam** telemetri etkinleştirildiğinden emin olun; bu durum, mühendislerin tanılanması için daha fazla işlem yapılabilir ve kolay hale gelir.</span><span class="sxs-lookup"><span data-stu-id="66066-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="66066-133">[Dosya geri bildirimi](hololens-feedback.md) mümkün olduğunca açıklayıcı bir şekilde yapılır.</span><span class="sxs-lookup"><span data-stu-id="66066-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="66066-134">Bilgilerinizi bir yere göz atın veya paylaşma özelliğini kullanarak, hatayı destek ile paylaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="66066-135">[Desteğe](https://aka.ms/hlsupport)başvurun.</span><span class="sxs-lookup"><span data-stu-id="66066-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="66066-136">Sorununuzun önceki bir sürüme dönerek çözülmesi gereken bir sorun varsa, cihazınızı Flash için sizin için bir tane sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="66066-137">Bu işe çalışmadıysanız, [HoloLens 2 ' yi Gelişmiş kurtarma Yardımcısı ile sıfırlayın veya](hololens-recovery.md)yeniden yapın.</span><span class="sxs-lookup"><span data-stu-id="66066-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="66066-138">Bilgisayarınızda, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ' nı Microsoft Store indirin.</span><span class="sxs-lookup"><span data-stu-id="66066-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="66066-139">Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarının olmadığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="66066-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="66066-140">Flash yapmak istediğiniz sürümü seçin:</span><span class="sxs-lookup"><span data-stu-id="66066-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="66066-141">[En son HoloLens 2 sürümünü](https://aka.ms/hololens2download)indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="66066-142">YAY ana bilgisayarlarının varsayılan derlemesini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="66066-143">(Bu seçeneği belirlerseniz sonraki adımı atlayın.)</span><span class="sxs-lookup"><span data-stu-id="66066-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="66066-144">Size sağlanmış olan bir yapı desteği kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="66066-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="66066-145">Bu İndirmeleri bitirdiğinizde **Dosya Gezgini**  >  **İndirmeleri**' ni açın.</span><span class="sxs-lookup"><span data-stu-id="66066-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="66066-146">İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .</span><span class="sxs-lookup"><span data-stu-id="66066-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="66066-147">USB-A-USB-C kablosu kullanarak HoloLens 'nizi bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="66066-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="66066-148">(HoloLens 'nizi bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)</span><span class="sxs-lookup"><span data-stu-id="66066-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="66066-149">Gelişmiş kurtarma Yardımcısı, HoloLens 'nizi otomatik olarak algılar.</span><span class="sxs-lookup"><span data-stu-id="66066-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="66066-150">**Microsoft HoloLens** kutucuğunu seçin.</span><span class="sxs-lookup"><span data-stu-id="66066-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="66066-151">Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve ardından adım 4 ' te sıkıştırmışın klasörde bulunan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="66066-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="66066-152">(. FFU uzantılı bir dosyayı arayın.)</span><span class="sxs-lookup"><span data-stu-id="66066-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="66066-153">**Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="66066-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="66066-154">Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.</span><span class="sxs-lookup"><span data-stu-id="66066-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="66066-155">Ayrıca, şu anda yüklü olan yayında kalmak isterseniz, güncelleştirmeleri el ile de [duraklatabilirsiniz](hololens-updates.md#pause-updates-via-device).</span><span class="sxs-lookup"><span data-stu-id="66066-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="66066-156">Bu, mühendisliğe sorunu çözmesi için mühendislik ekibi zamanına verecektir.</span><span class="sxs-lookup"><span data-stu-id="66066-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="66066-157">HoloLens üzerinde Windows Insider programı</span><span class="sxs-lookup"><span data-stu-id="66066-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="66066-158">HoloLens 'te en son özellikleri görmek mi istiyorsunuz?</span><span class="sxs-lookup"><span data-stu-id="66066-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="66066-159">Öyleyse, Windows Insider programına katılarak; HoloLens yazılım güncelleştirmelerinin önizleme yapılarına genel kullanıma açık olmadan önce erişim sağlayacaksınız.</span><span class="sxs-lookup"><span data-stu-id="66066-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="66066-160">[Microsoft HoloLens Için Windows Insider Preview](hololens-insider.md)' i alın.</span><span class="sxs-lookup"><span data-stu-id="66066-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
