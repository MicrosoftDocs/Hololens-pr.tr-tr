---
title: Fiziksel alanları HoloLens eşleme
description: HoloLens, bir alanın zaman içinde nasıl göründüğünü öğrenir. kullanıcılar, HoloLens alana belirli yollarla taşıyarak bu süreci kolaylaştırabilir.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, tasarım, uzamsal eşleme, HoloLens, yüzey yeniden oluşturma, kafes, baş izleme, eşleme
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640051"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="4ee71-105">Fiziksel alanları HoloLens eşleme</span><span class="sxs-lookup"><span data-stu-id="4ee71-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="4ee71-106">fiziksel dünyala HoloLens karışımlar hologramlar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="4ee71-107">bunu yapmak için HoloLens, dünyanın dört bir yanındaki fiziksel dünya hakkında bilgi edinmek ve bu alana hologragram yerleştirdiğinizden emin olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="4ee71-108">zaman içinde HoloLens, göründüğü ortamın *uzamsal haritasını* oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4ee71-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="4ee71-109">HoloLens, ortam değiştikçe haritayı güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="4ee71-110">oturum açtığınız ve cihaz açık olduğu sürece, HoloLens uzamsal haritalarınızı oluşturup günceller.</span><span class="sxs-lookup"><span data-stu-id="4ee71-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="4ee71-111">cihaza bir boşluk işaret eden kameraları varsa veya bu cihazı aşdıysanız, HoloLens alanı eşlemeye çalışır.</span><span class="sxs-lookup"><span data-stu-id="4ee71-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="4ee71-112">HoloLens zaman içinde bir alanı öğrenirken, alanınızı daha hızlı ve verimli bir şekilde eşlemeye HoloLens yardımcı olmak için kullanabileceğiniz yollar vardır.</span><span class="sxs-lookup"><span data-stu-id="4ee71-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="4ee71-113">HoloLens alanınızı eşleyemezsiniz veya ayarlama işlemi yapıyorsanız HoloLens sınırlı mod girebilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="4ee71-114">Sınırlı modda, hologramlar elde edemeyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="4ee71-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="4ee71-115">bu makalede, HoloLens alanları nasıl eşlediğini, uzamsal eşlemenin nasıl iyileştireceğinizi ve HoloLens tarafından toplanan uzamsal verilerin nasıl yönetileceği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4ee71-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="4ee71-116">Alanı seçme ve ayarlama</span><span class="sxs-lookup"><span data-stu-id="4ee71-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="4ee71-117">ortamınızdaki özellikler, HoloLens bir alanı yorumlamasını zorlaştırır.</span><span class="sxs-lookup"><span data-stu-id="4ee71-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="4ee71-118">hafif düzeyler, alandaki malzemeler, nesnelerin düzeni ve daha fazlası, HoloLens bir alanı nasıl eşlediğini etkiler.</span><span class="sxs-lookup"><span data-stu-id="4ee71-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="4ee71-119">HoloLens, belirli türde ortamlarda en iyi şekilde işe yarar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="4ee71-120">En iyi uzamsal Haritayı oluşturmak için, yeterli ışığı ve çok fazla alanı olan bir oda seçin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="4ee71-121">Büyük ve yarı saydam yüzeylere (örneğin, yansıtmalar veya gauzy CURTAINS) sahip olan karanlık boşluklar ve odalar kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="4ee71-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="4ee71-122">HoloLens, ınkapılı kullanım için iyileştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="4ee71-123">Uzamsal eşleme Ayrıca Wi-Fi açıldığında en iyi şekilde çalışıyor, ancak bir ağa bağlı olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="4ee71-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="4ee71-124">HoloLens, bağlı veya kimliği doğrulanmamış olsa da Wi-Fi erişim noktalarını alabilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="4ee71-125">HoloLens işlevselliği, erişim noktalarının internet 'e bağlı mi yoksa yalnızca intranet/yerel mi olduğunu değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="4ee71-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="4ee71-126">yalnızca güvenilir yerlerde HoloLens, riskleri olmadan kullanın.</span><span class="sxs-lookup"><span data-stu-id="4ee71-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="4ee71-127">[Daha fazla güvenlik](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="4ee71-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="4ee71-128">Alanınızı eşleme</span><span class="sxs-lookup"><span data-stu-id="4ee71-128">Mapping your space</span></span>

<span data-ttu-id="4ee71-129">Şimdi yedek dosyanızı eşleştirmeye başlamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="4ee71-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="4ee71-130">HoloLens, kisörlerinizi eşleştirmeye başladığında, alanın üzerine yayıldığı bir kafes grafik görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="4ee71-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="4ee71-131">Karma Gerçeklik ana sayfasında, eşlenmiş bir yüzey üzerinde seçim yaparak Haritayı gösterecek şekilde tetikleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4ee71-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="4ee71-132">Harika bir uzamsal harita oluşturmaya yönelik yönergeler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="4ee71-133">Alanla ilgili senaryoları anlayın</span><span class="sxs-lookup"><span data-stu-id="4ee71-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="4ee71-134">haritanın ilgili ve tamamlanmış olması için HoloLens kullandığınız en çok zaman harcamanız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="4ee71-135">örneğin, HoloLens bir kullanıcı senaryosu a noktasından B noktasına geçmeyi içeriyorsa, hareket ettirirken tüm yönlere bakarak bu yolu üç kez iki kez gözden getirin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="4ee71-136">Alanı etrafında yavaşça ilerleme</span><span class="sxs-lookup"><span data-stu-id="4ee71-136">Walk slowly around the space</span></span>

<span data-ttu-id="4ee71-137">alan etrafında çok hızlı bir şekilde gezinmenize yol, HoloLens eşleme alanlarının kaçırmasına yol gösterecektir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="4ee71-138">Her 5-8 metrede elde edeceğiniz şekilde, her yerden daha fazla hareket edin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="4ee71-139">kesintisiz hareketler HoloLens eşlemenin daha verimli bir şekilde sağlanmasına da yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4ee71-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="4ee71-140">Tüm yönergelere bakın</span><span class="sxs-lookup"><span data-stu-id="4ee71-140">Look in all directions</span></span>

<span data-ttu-id="4ee71-141">bu alanı eşleştirdiğinizde, noktaların birbirlerine göreli olduğu durumlarda HoloLens daha fazla veri verilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="4ee71-142">örneğin, HoloLens bir odadaki tavan nerede olduğunu bilmiyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="4ee71-143">Alanı eşleştirdiğinizde zemin üzerinde görünmemenizi unutmayın.</span><span class="sxs-lookup"><span data-stu-id="4ee71-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="4ee71-144">Anahtar bölgelerini birden çok kez Kapla</span><span class="sxs-lookup"><span data-stu-id="4ee71-144">Cover key areas multiple times</span></span>

<span data-ttu-id="4ee71-145">Bir alandan çok kez geçiş yapmak, ilk yönergede kaçırmış olabilecek özellikleri çekmeye yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4ee71-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="4ee71-146">İdeal bir harita oluşturmak için bir alandan üç kez geçiş yapmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="4ee71-147">Mümkünse, bu taşımaları tekrarlarken, bir yönde bir alandan yürüyerek harcama süresini geri çevirip, daha sonra da bulunduğunuz şekilde geri dönün.</span><span class="sxs-lookup"><span data-stu-id="4ee71-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="4ee71-148">Alanı eşleştirmeye göre zamandan yararlanın</span><span class="sxs-lookup"><span data-stu-id="4ee71-148">Take your time mapping the area</span></span>

<span data-ttu-id="4ee71-149">HoloLens tamamen eşlenme ve kendini kendi ilerleyebilir olarak ayarlaması için 15 ila 20 dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="4ee71-150">en sık bir HoloLens kullanmayı planladığınız bir alanınız varsa, bu zaman, alanı eşlemek için en öne çıkan sorunları daha sonra engelleyebilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="4ee71-151">Uzamsal haritada olası hatalar</span><span class="sxs-lookup"><span data-stu-id="4ee71-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="4ee71-152">Uzamsal eşleme verilerinde hatalar birkaç kategoride yer almalıdır:</span><span class="sxs-lookup"><span data-stu-id="4ee71-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="4ee71-153">*Delik*: uzamsal eşleme verilerinde gerçek dünyada yüzeyler yok.</span><span class="sxs-lookup"><span data-stu-id="4ee71-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="4ee71-154">*Hallucinations*: gerçek dünyada mevcut olmayan uzamsal eşleme verilerinde yüzeyler var.</span><span class="sxs-lookup"><span data-stu-id="4ee71-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="4ee71-155">*solucan delikleri*: HoloLens ', uzamsal haritanın bir parçasını, gerçekten de haritanın farklı bir bölümünde olduğunu düşünerek, ' kaybeder '.</span><span class="sxs-lookup"><span data-stu-id="4ee71-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="4ee71-156">*Sapma*: uzamsal eşleme verilerinde yüzeyler, gerçek dünya yüzeyleriyle birlikte gönderilir ya da kullanıma alınır.</span><span class="sxs-lookup"><span data-stu-id="4ee71-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="4ee71-157">Bu hatalardan herhangi birini görürseniz lütfen geri bildirim göndermek için [Feedbackhub ' ı](hololens-feedback.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="4ee71-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="4ee71-158">Uzamsal veriler için güvenlik ve depolama</span><span class="sxs-lookup"><span data-stu-id="4ee71-158">Security and storage for spatial data</span></span>

<span data-ttu-id="4ee71-159">Microsoft HoloLens ve sonraki sürümleri için Windows 10 sürüm 1803 güncelleştirmesi, yerel (cihazdaki) bir veritabanında eşleme verilerini depolar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="4ee71-160">HoloLens kullanıcılar, cihaz bir bilgisayara takılıyken veya dosya gezgini uygulaması kullanılırken bile harita veritabanına doğrudan erişemez.</span><span class="sxs-lookup"><span data-stu-id="4ee71-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="4ee71-161">BitLocker HoloLens etkinleştirildiğinde, depolanan harita verileri de tüm birimle birlikte şifrelenir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="4ee71-162">Harita verilerini ve bilinen boşlukları HoloLens kaldır</span><span class="sxs-lookup"><span data-stu-id="4ee71-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="4ee71-163">**Ayarlar > sistemi > Hologramlar** eşleme verilerini silmeye yönelik iki seçenek vardır:</span><span class="sxs-lookup"><span data-stu-id="4ee71-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="4ee71-164">Yakın hologramlar silmek için **yakın Hologragram kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="4ee71-165">Bu komut, harita verilerini ve geçerli alana ait bağlantılı hologramlar temizler.</span><span class="sxs-lookup"><span data-stu-id="4ee71-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="4ee71-166">Aynı alanda cihazı kullanmaya devam ederseniz, silinen bilgileri değiştirmek için yepyeni bir harita oluşturur ve depolar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4ee71-167">"Yakındaki" hologramlar, geçerli alanın aynı eşleme bölümünde sabitlenmiş hologramlar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="4ee71-168">Örneğin, bu seçeneği, ana ilgili harita verilerini etkilemeden iş ile ilgili harita verilerini temizlemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4ee71-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="4ee71-169">Tüm hologramlar silmek için **Tüm hologramlar 'ı kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4ee71-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="4ee71-170">Bu komut, cihazda depolanan tüm harita verilerini ve tüm bağlantılı hologramlar temizler.</span><span class="sxs-lookup"><span data-stu-id="4ee71-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="4ee71-171">Herhangi bir hologragram açıkça yerleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="4ee71-172">Daha önce yerleştirdiğiniz hologramlar yeniden keşfedemeyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="4ee71-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="4ee71-173">yakın veya tüm hologramlar kaldırıldıktan sonra, HoloLens hemen taramaya ve geçerli alanı eşleştirmeye başlar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="4ee71-174">Uzamsal eşlemlerdeki verileri Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="4ee71-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="4ee71-175">HoloLens, hologram konumlarını ve bilinen boşlukların HoloLens veritabanı içinde depolanan eşleme bölümlerini ilişkilendirmenize yardımcı olmak için Wi-Fi özelliklerini depolar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="4ee71-176">Wi-Fi özellikleriyle ilgili bilgiler, kullanıcılar tarafından erişilemez ve bulut kullanılarak veya telemetri kullanılarak Microsoft 'a gönderilmez.</span><span class="sxs-lookup"><span data-stu-id="4ee71-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="4ee71-177">Wi-Fi etkinleştirildiği sürece HoloLens harita verilerini yakın Wi-Fi erişim noktalarıyla ilişkilendirir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="4ee71-178">Bir ağın bağlı olup olmadığı veya yakın bir şekilde algılanıp algılanmadığı davranıştaki bir farklılık yoktur.</span><span class="sxs-lookup"><span data-stu-id="4ee71-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="4ee71-179">Wi-Fi devre dışıysa, HoloLens hala alanı arar.</span><span class="sxs-lookup"><span data-stu-id="4ee71-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="4ee71-180">ancak, HoloLens alanlar veritabanında daha fazla harita verisi aramak ve hologramlar bulmak için daha fazla zaman gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="4ee71-181">Wi-Fi bilgisi olmadan, HoloLens, haritanın doğru kısmını bulmak için etkin taramaları tüm hologram tutturucularını ve cihazda depolanan bölümleri eşlemek için gerekir.</span><span class="sxs-lookup"><span data-stu-id="4ee71-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ee71-182">İlgili konular</span><span class="sxs-lookup"><span data-stu-id="4ee71-182">Related topics</span></span>

- [<span data-ttu-id="4ee71-183">Uzamsal eşleme tasarımı</span><span class="sxs-lookup"><span data-stu-id="4ee71-183">Spatial mapping design</span></span>](/windows/mixed-reality/spatial-mapping)
