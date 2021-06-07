---
title: Pil ve Ücretlendirme
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380296"
---
# <a name="battery-and-charging"></a><span data-ttu-id="44427-103">Pil ve Ücretlendirme</span><span class="sxs-lookup"><span data-stu-id="44427-103">Battery and Charging</span></span>

<span data-ttu-id="44427-104">Bu sayfada HoloLens 2'nin ücretlendirmesi ve dış pil paketlerinin kullanımıyla ilgili ayrıntılar yer almaktadır.</span><span class="sxs-lookup"><span data-stu-id="44427-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="44427-105">Dahil EdilenLer</span><span class="sxs-lookup"><span data-stu-id="44427-105">Included Charger</span></span>

<span data-ttu-id="44427-106">HoloLens 2'ye dahil edilen güç, 2A (18W) ile en fazla 9V sağlar.</span><span class="sxs-lookup"><span data-stu-id="44427-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="44427-107">Mümkün olduğunda, dahil edilen cihazın kullanılması kesinlikle önerilir.</span><span class="sxs-lookup"><span data-stu-id="44427-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="44427-108">Belirtimler</span><span class="sxs-lookup"><span data-stu-id="44427-108">Specifications</span></span>

<span data-ttu-id="44427-109">HoloLens 2, USB Güç Teslim kaynakları [tarafından](https://www.usb.org/usb-charger-pd) 27 Watt'a kadar ücretlendir olabilir.</span><span class="sxs-lookup"><span data-stu-id="44427-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="44427-110">Kaynak en az 10 Watt tedarikebiliyorsa HoloLens çalışma süresi uzatılabilir (bazı iş yükleri için süresiz olabilir).</span><span class="sxs-lookup"><span data-stu-id="44427-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="44427-111">USB-A ile USB-C arasında bir ücretlendirme kablosu kullanmak, ücreti 7,5 Watt ile sınırlar.</span><span class="sxs-lookup"><span data-stu-id="44427-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="44427-112">Çalışma süresi yine de uzatılır, ancak USB-C'den C'ye kullanım süresi kadar uzatılabilir.</span><span class="sxs-lookup"><span data-stu-id="44427-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="44427-113">HoloLens bekleme modundayken dahili pil için maksimum ücret oranına ulaşmak için 18 Watt yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="44427-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="44427-114">HoloLens kullanımda olduğunda, HoloLens ücretlendirmeye öncelik verdiklerinden ücretlendirme oranı azaltabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44427-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44427-115">HoloLens 2'nin en az 5V/1,5A ücretlendirmiş olması önerilir.</span><span class="sxs-lookup"><span data-stu-id="44427-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="44427-116">En az 5V/1.5A kaynağına sahip olara kullanılmamalı.</span><span class="sxs-lookup"><span data-stu-id="44427-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="44427-117">Dış Pil Paketleri</span><span class="sxs-lookup"><span data-stu-id="44427-117">External Battery Packs</span></span>

<span data-ttu-id="44427-118">Yukarıdaki belirtimlere uygun pil paketleri HoloLens 2 ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="44427-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="44427-119">Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden güç sağlay dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="44427-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="44427-120">Bu pil paketlerinin TRY uygulaması [önemlidir. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) holoLens yerine HoloLens'i ücretlendirmelerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="44427-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="44427-121">Isı Yönetimi</span><span class="sxs-lookup"><span data-stu-id="44427-121">Managing Heat</span></span>

<span data-ttu-id="44427-122">Tüm cihazlarda olduğu gibi HoloLens'in ücretlendirmesi ısı üretir.</span><span class="sxs-lookup"><span data-stu-id="44427-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="44427-123">Ücret ne kadar hızlısa ısı da o kadar fazla olur.</span><span class="sxs-lookup"><span data-stu-id="44427-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="44427-124">Ayrıca, daha düşük bir pil düzeyinde bir ücrete başlayarak, pil çoğunlukla dolu olduğunda bir ücretin başlatılamayacak kadar ısı üretir.</span><span class="sxs-lookup"><span data-stu-id="44427-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="44427-125">HoloLens'i sıcak ortamlarda uzun süre çalıştırmak isteyen müşteriler aşağıdaki teknikleri kullanabilir:</span><span class="sxs-lookup"><span data-stu-id="44427-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="44427-126">Dahili pil tamamen dolu olsa bile HoloLens 2'nin harici bir güç kaynağına bağlanması sorun değil.</span><span class="sxs-lookup"><span data-stu-id="44427-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="44427-127">Dış pil tükenmiş olduğunda HoloLens dahili pille çalışmaya devam eder.</span><span class="sxs-lookup"><span data-stu-id="44427-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="44427-128">Yukarıdaki adımların ardından ısı sorunu devam ediyorsa, ücretlendirmeyi 1,5A ile sınırlayan bir pil veya pil paketi kullanmayı göz önünde bulundurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44427-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="44427-129">İç pil yavaş yavaş tükenene kadar bu seçeneğin o kadar fazla çalışma süresi sağlamaycaz.</span><span class="sxs-lookup"><span data-stu-id="44427-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="44427-130">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="44427-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="44427-131">HoloLens, Harici Pil Ücretleri</span><span class="sxs-lookup"><span data-stu-id="44427-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="44427-132">HoloLens 2, bu pille ücretlendiril yerine bir dış pile ücret uygulanması pilin TRY uygulamadığını [gösterir. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="44427-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="44427-133">Bu sorunu çözmek için önerilen yöntem daha yeni bir pil paketine geçmektir, ancak alternatif olarak USB-A'ya USB-C kablosuna geçmeyi denemeyi abilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="44427-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="44427-134">Bu, ücretlendirme oranını 7,5 watt ile sınırlar.</span><span class="sxs-lookup"><span data-stu-id="44427-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
