---
title: HoloLens 2 Pil ve Ücretlendirme
description: HoloLens'inizi nasıl ücretlendirin ve dış pil paketlerini kullanın.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923593"
---
# <a name="hololens-2-battery-and-charging"></a><span data-ttu-id="f77a4-103">HoloLens 2 Pil ve Ücretlendirme</span><span class="sxs-lookup"><span data-stu-id="f77a4-103">HoloLens 2 Battery and Charging</span></span>

<span data-ttu-id="f77a4-104">Bu sayfada HoloLens 2'nin ücretlendirmesi ve dış pil paketlerinin kullanımıyla ilgili ayrıntılar yer almaktadır.</span><span class="sxs-lookup"><span data-stu-id="f77a4-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="charging-the-device"></a><span data-ttu-id="f77a4-105">Cihazı ücretlendirme</span><span class="sxs-lookup"><span data-stu-id="f77a4-105">Charging the device</span></span>

<span data-ttu-id="f77a4-106">Cihazınızı [ücretlendirecek en](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) iyi yol olan HoloLens 2 ile birlikte gelen USB Type-C kablosunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="f77a4-106">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="f77a4-107">HoloLens 2'ye dahil edilen güç, 2A (18W) ile en fazla 9V sağlar.</span><span class="sxs-lookup"><span data-stu-id="f77a4-107">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="f77a4-108">Sağlanan duvar cihazıyla birlikte HoloLens 2 cihazları, cihaz beklemedeyken pilin 65 dakikadan kısa bir süre içinde dolup dolymayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f77a4-108">Along with the supplied wall charger, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="f77a4-109">Bu aksesuarlar mevcut değilse, kullanılabilir olan aletin en az 15W gücü destekleyene sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f77a4-109">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="f77a4-110">Mümkünse, cihazı USB üzerinden ücretlandırarak yavaş olan bir bilgisayar kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="f77a4-110">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

## <a name="checking-the-battery-charge-level"></a><span data-ttu-id="f77a4-111">Pil ücreti düzeyini denetleme</span><span class="sxs-lookup"><span data-stu-id="f77a4-111">Checking the battery charge level</span></span>
<span data-ttu-id="f77a4-112">Cihaz doğru şekilde önyüklüp çalışıyorsa, pil ücreti düzeyini denetlemenin üç yolu vardır:</span><span class="sxs-lookup"><span data-stu-id="f77a4-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="f77a4-113">HoloLens cihazı kullanıcı arabiriminin ana menüsünden.</span><span class="sxs-lookup"><span data-stu-id="f77a4-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="f77a4-114">LED'i güç düğmesinin yakınında görüntüle (yüzde 40 ücret için en az iki katı LED görüyor gerekir).</span><span class="sxs-lookup"><span data-stu-id="f77a4-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="f77a4-115">Cihaz ücretlendirmeye devam edin. Pil göstergesi, geçerli ücret düzeyini belirtmek için yanıp söner.</span><span class="sxs-lookup"><span data-stu-id="f77a4-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="f77a4-116">Son ışık, etkin ücretlendirmeyi göstermek için belirecek ve sönecek.</span><span class="sxs-lookup"><span data-stu-id="f77a4-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="f77a4-117">HoloLens'iniz etkin olduğunda pil göstergesi beş artımlı olarak pil düzeyini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="f77a4-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="f77a4-118">Beş ışığın yalnızca biri açık olduğunda pil düzeyi yüzde 20'nin altında olur.</span><span class="sxs-lookup"><span data-stu-id="f77a4-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="f77a4-119">Pil düzeyi kritik düzeyde düşükse ve cihazı açmayı denersiniz, bir ışık kısa bir süre yanıp söner ve sonra gider.</span><span class="sxs-lookup"><span data-stu-id="f77a4-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="f77a4-120">Konak bilgisayarınızda bu **Dosya Gezgini** açın ve Sol tarafta Bu bilgisayar altında HoloLens 2 **cihazınızı açın.**</span><span class="sxs-lookup"><span data-stu-id="f77a4-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="f77a4-121">Cihaza sağ tıklayın ve Özellikler'i **seçin.**</span><span class="sxs-lookup"><span data-stu-id="f77a4-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="f77a4-122">Bir iletişim kutusu pil ücreti düzeyini gösterir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-122">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 özellikler ekranı pil değişikliği düzeyini gösterir](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a><span data-ttu-id="f77a4-124">Alternatif ücretlendirme belirtimleri</span><span class="sxs-lookup"><span data-stu-id="f77a4-124">Alternative charging specifications</span></span>

<span data-ttu-id="f77a4-125">HoloLens 2, USB Güç Teslim kaynakları [tarafından](https://www.usb.org/usb-charger-pd) 27 Watt'a kadar ücretlendir olabilir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-125">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="f77a4-126">Kaynak en az 10 Watt tedarikebiliyorsa HoloLens çalışma süresi uzatılabilir (bazı iş yükleri için süresiz olabilir).</span><span class="sxs-lookup"><span data-stu-id="f77a4-126">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="f77a4-127">USB-A ile USB-C arasında bir ücretlendirme kablosu kullanmak, ücreti 7,5 Watt ile sınırlar.</span><span class="sxs-lookup"><span data-stu-id="f77a4-127">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="f77a4-128">Çalışma süresi yine de uzatılır, ancak USB-C'den C'ye kullanım süresi kadar uzatılabilir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-128">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="f77a4-129">HoloLens bekleme modundayken dahili pil için maksimum ücret oranına ulaşmak için 18 Watt yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-129">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="f77a4-130">HoloLens kullanımda olduğunda, HoloLens ücretlendirmeye öncelik verdiklerinden ücretlendirme oranı azaltabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f77a4-130">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f77a4-131">HoloLens 2'nin en az 5V/1,5A ücretlendirmiş olması önerilir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-131">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="f77a4-132">En az 5V/1.5A kaynağına sahip olara kullanılmamalı.</span><span class="sxs-lookup"><span data-stu-id="f77a4-132">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

### <a name="external-battery-packs"></a><span data-ttu-id="f77a4-133">Dış Pil Paketleri</span><span class="sxs-lookup"><span data-stu-id="f77a4-133">External Battery Packs</span></span>

<span data-ttu-id="f77a4-134">Yukarıdaki belirtimlere uygun pil paketleri HoloLens 2 ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-134">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="f77a4-135">Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden güç sağlay dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="f77a4-135">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="f77a4-136">Bu pil paketlerinin TRY uygulaması [önemlidir. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) holoLens yerine HoloLens'i ücretlendirmelerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="f77a4-136">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

### <a name="managing-heat"></a><span data-ttu-id="f77a4-137">Isı Yönetimi</span><span class="sxs-lookup"><span data-stu-id="f77a4-137">Managing Heat</span></span>

<span data-ttu-id="f77a4-138">Tüm cihazlarda olduğu gibi HoloLens'i ücretlendirmek de ısı üretir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-138">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="f77a4-139">Ücret ne kadar hızlı olursa ısı da o kadar fazla olur.</span><span class="sxs-lookup"><span data-stu-id="f77a4-139">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="f77a4-140">Ayrıca, daha düşük bir pil düzeyinde bir ücrete başlayarak, pil çoğunlukla dolu olduğunda bir ücretin başlatılamayacak kadar ısı üretir.</span><span class="sxs-lookup"><span data-stu-id="f77a4-140">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="f77a4-141">HoloLens'i sıcak ortamlarda uzun süre çalıştırmak isteyen müşteriler aşağıdaki teknikleri kullanabilir:</span><span class="sxs-lookup"><span data-stu-id="f77a4-141">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="f77a4-142">Dahili pil tamamen dolu olsa bile HoloLens 2'nin harici bir güç kaynağına bağlanması sorun değil.</span><span class="sxs-lookup"><span data-stu-id="f77a4-142">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="f77a4-143">Dış pil tükenmiş olduğunda HoloLens dahili pille çalışmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="f77a4-143">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="f77a4-144">Yukarıdaki adımların ardından ısı sorunu devam ediyorsa, ücretlendirmeyi 1,5A ile sınırlayan bir pil veya pil paketi kullanmayı göz önünde bulundurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f77a4-144">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="f77a4-145">İç pil yavaş yavaş tükenene kadar bu seçeneğin o kadar fazla çalışma süresi sağlamaycaz.</span><span class="sxs-lookup"><span data-stu-id="f77a4-145">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f77a4-146">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="f77a4-146">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="f77a4-147">HoloLens, Harici Pil Ücretleri</span><span class="sxs-lookup"><span data-stu-id="f77a4-147">HoloLens Charges External Battery</span></span>
<span data-ttu-id="f77a4-148">HoloLens 2, bu pille ücretlendiril yerine bir dış pile ücret uygulanması pilin TRY uygulamadığını [gösterir. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="f77a4-148">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="f77a4-149">Bu sorunu çözmek için önerilen yöntem daha yeni bir pil paketine geçmektir, ancak alternatif olarak USB-A'ya USB-C kablosuna geçmeyi denemeyi abilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f77a4-149">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="f77a4-150">Bu, ücretlendirme oranını 7,5 watt ile sınırlar.</span><span class="sxs-lookup"><span data-stu-id="f77a4-150">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
