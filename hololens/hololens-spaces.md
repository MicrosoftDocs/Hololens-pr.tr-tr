---
title: Fiziksel alanları HoloLens ile eşleme
description: HoloLens, bir alanın zaman içinde nasıl göründüğünü öğrenir. Kullanıcılar, HoloLens 'i alana göre belirli yollarla taşıyarak bu süreci kolaylaştırabilir.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: Hololens, Windows Mixed Reality, tasarım, uzamsal eşleme, HoloLens, yüzey yeniden oluşturma, kafes, baş izleme, eşleme
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380219"
---
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="b1dc6-105">Fiziksel alanları HoloLens ile eşleme</span><span class="sxs-lookup"><span data-stu-id="b1dc6-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="b1dc6-106">HoloLens ile fiziksel dünyayı hologramlar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="b1dc6-107">Bunu yapmak için, HoloLens 'in sizin çevresindeki fiziksel dünyayı öğreni ve bu alana hologragram yerleştirdiğinizden emin olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="b1dc6-108">Zaman içinde, HoloLens, gördüğü ortamın *uzamsal haritasını* oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="b1dc6-109">HoloLens, ortamı değiştiği için Haritayı güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="b1dc6-110">Oturum açtığınız ve cihaz açık olduğu sürece, HoloLens, uzamsal haritalarınızı oluşturur ve güncelleştirir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="b1dc6-111">Cihaza bir boşluk işaret eden kameraları varsa veya bu cihazı aşdıysanız, HoloLens alanı eşlemeyi dener.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="b1dc6-112">HoloLens zaman içinde bir alanı öğrenirken, HoloLens 'in alanınızı daha hızlı ve verimli bir şekilde eşlemesine yardımcı olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="b1dc6-113">HoloLens 'niz alanınızı eşleyemiyorum veya ayar dışında, HoloLens sınırlı mod girebilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="b1dc6-114">Sınırlı modda, hologramlar elde edemeyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="b1dc6-115">Bu makalede, HoloLens 'in alanları nasıl eşleştiği, uzamsal eşlemenin nasıl geliştirilmesi ve HoloLens 'in topladığı uzamsal verilerin nasıl yönetileceği açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="b1dc6-116">Alanı seçme ve ayarlama</span><span class="sxs-lookup"><span data-stu-id="b1dc6-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="b1dc6-117">Ortamınızdaki özellikler, HoloLens 'in bir alanı yorumlamasını zorlaştırır.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="b1dc6-118">Hafif düzeyler, boşluk içindeki malzemeler, nesnelerin düzeni ve daha fazlası, HoloLens 'in bir alanı nasıl eşlediğini etkiler.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="b1dc6-119">HoloLens, belirli ortam türlerinde en iyi şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="b1dc6-120">En iyi uzamsal Haritayı oluşturmak için, yeterli ışığı ve çok fazla alanı olan bir oda seçin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="b1dc6-121">Büyük ve yarı saydam yüzeylere (örneğin, yansıtmalar veya gauzy CURTAINS) sahip olan karanlık boşluklar ve odalar kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="b1dc6-122">HoloLens, ınkapılı kullanım için iyileştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="b1dc6-123">Uzamsal eşleme Ayrıca Wi-Fi açıldığında en iyi şekilde çalışıyor, ancak bir ağa bağlı olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="b1dc6-124">HoloLens bağlı veya kimliği doğrulanmamış olsa bile Wi-Fi erişim noktalarını alabilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="b1dc6-125">HoloLens işlevselliği, erişim noktalarının internet 'e bağlı mi yoksa yalnızca intranet/yerel mi olduğunu değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="b1dc6-126">HoloLens 'i yalnızca kasa olmayan güvenli yerlerde kullanın.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="b1dc6-127">[Daha fazla güvenlik](https://support.microsoft.com/help/4023454/safety-information).</span><span class="sxs-lookup"><span data-stu-id="b1dc6-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="b1dc6-128">Alanınızı eşleme</span><span class="sxs-lookup"><span data-stu-id="b1dc6-128">Mapping your space</span></span>

<span data-ttu-id="b1dc6-129">Şimdi yedek dosyanızı eşleştirmeye başlamaya hazırsınız.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="b1dc6-130">HoloLens, kisörlerinizi eşleştirmeye başladığında, alanın üzerine yayıldığı bir kafes grafik görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="b1dc6-131">Karma Gerçeklik ana sayfasında, eşlenmiş bir yüzey üzerinde seçim yaparak Haritayı gösterecek şekilde tetikleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="b1dc6-132">Harika bir uzamsal harita oluşturmaya yönelik yönergeler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="b1dc6-133">Alanla ilgili senaryoları anlayın</span><span class="sxs-lookup"><span data-stu-id="b1dc6-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="b1dc6-134">Haritanın ilgili ve tamamlanmış olması için HoloLens 'in kullanıldığı en çok zaman harcamanız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="b1dc6-135">Örneğin, HoloLens için bir Kullanıcı senaryosu A noktası A 'dan B 'ye geçmeyi içeriyorsa, taşırken tüm yönlere bakarak bu yolu üç kez iki kez gözden getirin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="b1dc6-136">Alanı etrafında yavaşça ilerleme</span><span class="sxs-lookup"><span data-stu-id="b1dc6-136">Walk slowly around the space</span></span>

<span data-ttu-id="b1dc6-137">Alan etrafında çok hızlı bir şekilde gezinirken, HoloLens 'in eşleme alanlarının kaçırılması olasıdır.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="b1dc6-138">Her 5-8 metrede elde edeceğiniz şekilde, her yerden daha fazla hareket edin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="b1dc6-139">Düzgün hareketler, HoloLens eşlemenin daha verimli bir şekilde sağlanmasına da yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="b1dc6-140">Tüm yönergelere bakın</span><span class="sxs-lookup"><span data-stu-id="b1dc6-140">Look in all directions</span></span>

<span data-ttu-id="b1dc6-141">Siz eşleme yaparken, alanı, noktaların birbirlerine göreli olduğu yerde, HoloLens 'e daha fazla veri verir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="b1dc6-142">Örneğin, HoloLens, bir odanın nerede olduğunu bilmiyor olabilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="b1dc6-143">Alanı eşleştirdiğinizde zemin üzerinde görünmemenizi unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="b1dc6-144">Anahtar bölgelerini birden çok kez Kapla</span><span class="sxs-lookup"><span data-stu-id="b1dc6-144">Cover key areas multiple times</span></span>

<span data-ttu-id="b1dc6-145">Bir alandan çok kez geçiş yapmak, ilk yönergede kaçırmış olabilecek özellikleri çekmeye yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="b1dc6-146">İdeal bir harita oluşturmak için bir alandan üç kez geçiş yapmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="b1dc6-147">Mümkünse, bu taşımaları tekrarlarken, bir yönde bir alandan yürüyerek harcama süresini geri çevirip, daha sonra da bulunduğunuz şekilde geri dönün.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="b1dc6-148">Alanı eşleştirmeye göre zamandan yararlanın</span><span class="sxs-lookup"><span data-stu-id="b1dc6-148">Take your time mapping the area</span></span>

<span data-ttu-id="b1dc6-149">HoloLens 'in tamamen eşlenme ve kendini kendi ilerleyebilir olarak ayarlaması için 15 ila 20 dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="b1dc6-150">HoloLens kullanmayı planladığınız bir alanınız varsa, alanı eşlemek için bu sürenin önüne geçmek daha sonra sorunları önleyebilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="b1dc6-151">Uzamsal haritada olası hatalar</span><span class="sxs-lookup"><span data-stu-id="b1dc6-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="b1dc6-152">Uzamsal eşleme verilerinde hatalar birkaç kategoride yer almalıdır:</span><span class="sxs-lookup"><span data-stu-id="b1dc6-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="b1dc6-153">*Delik*: uzamsal eşleme verilerinde gerçek dünyada yüzeyler yok.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="b1dc6-154">*Hallucinations*: gerçek dünyada mevcut olmayan uzamsal eşleme verilerinde yüzeyler var.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="b1dc6-155">*Solucan delikleri*: HoloLens ', bir haritanın farklı bir bölümünde olduğunu düşünerek uzamsal haritanın parçasını kaybeder.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="b1dc6-156">*Sapma*: uzamsal eşleme verilerinde yüzeyler, gerçek dünya yüzeyleriyle birlikte gönderilir ya da kullanıma alınır.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="b1dc6-157">Bu hatalardan herhangi birini görürseniz lütfen geri bildirim göndermek için [Feedbackhub ' ı](hololens-feedback.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="b1dc6-158">Uzamsal veriler için güvenlik ve depolama</span><span class="sxs-lookup"><span data-stu-id="b1dc6-158">Security and storage for spatial data</span></span>

<span data-ttu-id="b1dc6-159">Microsoft HoloLens için Windows 10 sürüm 1803 güncelleştirmesi ve üzeri, eşleme verilerini yerel (cihazda) bir veritabanında depolar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="b1dc6-160">Cihaz bir BILGISAYARA takılıyken veya dosya Gezgini uygulaması kullanılırken bile, HoloLens kullanıcıları harita veritabanına doğrudan erişemez.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="b1dc6-161">HoloLens 'te BitLocker etkinleştirildiğinde, depolanan harita verileri de tüm birimle birlikte şifrelenir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="b1dc6-162">HoloLens 'ten harita verilerini ve bilinen boşlukları kaldırma</span><span class="sxs-lookup"><span data-stu-id="b1dc6-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="b1dc6-163">**Ayarlar > sistem > Hologragram**'da harita verilerini silmeye yönelik iki seçenek vardır:</span><span class="sxs-lookup"><span data-stu-id="b1dc6-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="b1dc6-164">Yakın hologramlar silmek için **yakın Hologragram kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="b1dc6-165">Bu komut, harita verilerini ve geçerli alana ait bağlantılı hologramlar temizler.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="b1dc6-166">Aynı alanda cihazı kullanmaya devam ederseniz, silinen bilgileri değiştirmek için yepyeni bir harita oluşturur ve depolar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1dc6-167">"Yakındaki" hologramlar, geçerli alanın aynı eşleme bölümünde sabitlenmiş hologramlar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="b1dc6-168">Örneğin, bu seçeneği, ana ilgili harita verilerini etkilemeden iş ile ilgili harita verilerini temizlemek için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="b1dc6-169">Tüm hologramlar silmek için **Tüm hologramlar 'ı kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="b1dc6-170">Bu komut, cihazda depolanan tüm harita verilerini ve tüm bağlantılı hologramlar temizler.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="b1dc6-171">Herhangi bir hologragram açıkça yerleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="b1dc6-172">Daha önce yerleştirdiğiniz hologramlar yeniden keşfedemeyeceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="b1dc6-173">Yakın veya tüm hologramlar kaldırıldıktan sonra, HoloLens hemen taramaya ve geçerli alanı eşleştirmeye başlar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="b1dc6-174">Uzamsal eşlemlerdeki verileri Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b1dc6-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="b1dc6-175">HoloLens, hologram konumlarının ve bilinen boşlukların HoloLens veritabanı içinde depolanan eşleme bölümlerinin ilişkilendirilmesi için Wi-Fi özellikleri depolar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="b1dc6-176">Wi-Fi özellikleriyle ilgili bilgiler, kullanıcılar tarafından erişilemez ve bulut kullanılarak veya telemetri kullanılarak Microsoft 'a gönderilmez.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="b1dc6-177">Wi-Fi etkinleştirildiği sürece, HoloLens, verileri yakın Wi-Fi erişim noktalarıyla eşler.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="b1dc6-178">Bir ağın bağlı olup olmadığı veya yakın bir şekilde algılanıp algılanmadığı davranıştaki bir farklılık yoktur.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="b1dc6-179">Wi-Fi devre dışıysa, HoloLens hala boşluğu arar.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="b1dc6-180">Ancak, HoloLens 'in, alanlar veritabanında daha fazla harita verisi araması yapması gerekir ve hologramlar bulmak için daha fazla zaman gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="b1dc6-181">Wi-Fi bilgisi olmadan, HoloLens, haritanın doğru kısmını bulmak için etkin taramaları tüm hologram tutturucularını ve cihazda depolanan bölümleri eşlemek zorunda değildir.</span><span class="sxs-lookup"><span data-stu-id="b1dc6-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1dc6-182">İlgili konular</span><span class="sxs-lookup"><span data-stu-id="b1dc6-182">Related topics</span></span>

- [<span data-ttu-id="b1dc6-183">Uzamsal eşleme tasarımı</span><span class="sxs-lookup"><span data-stu-id="b1dc6-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
