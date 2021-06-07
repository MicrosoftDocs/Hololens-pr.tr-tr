---
title: HoloLens 'te 3B görüntüleyici Beta kullanma (1. Genel)
description: HoloLens (1. gen) üzerinde 3D görüntüleyicisinin desteklediği dosya ve özellik türlerini ve uygulamayı nasıl kullanacağınızı ve sorun giderebileceğinizi açıklar.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380178"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="61b2f-103">HoloLens 'te 3B görüntüleyici Beta kullanma (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="61b2f-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="61b2f-104">3B görüntüleyici Beta, HoloLens 'te 3B modelleri görüntülemenize olanak sağlar (1. Genel).</span><span class="sxs-lookup"><span data-stu-id="61b2f-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="61b2f-105">*Desteklenen* . fbx dosyalarını Microsoft Edge, OneDrive ve diğer uygulamalardan açabilir ve görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="61b2f-106">Bu makale,. fbx dosyalarını destekleyen ve yalnızca HoloLens (1. gen) üzerinde kullanılabilen, modern Unity **3B görüntüleyici Beta** uygulaması için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="61b2f-107">HoloLens 2 ' deki önceden yüklenmiş **3B görüntüleyici** uygulaması, karma gerçeklik ana bilgisayarında özel. GLB 3D modellerini açmayı destekler (daha fazla bilgi için [varlık gereksinimlerine genel bakış](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="61b2f-108">3B görüntüleyici Beta, HoloLens (1. gen) için Microsoft Store kullanılabilir kalacağından, artık etkin bir geliştirme aşamasındadır ve artık desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="61b2f-109">3B görüntüleyici beta sürümünde bir 3B modeli açmada sorun yaşıyorsanız veya 3B modelinizin bazı özellikleri desteklenmiyorsa, aşağıdaki [desteklenen içerik belirtimleri](#supported-content-specifications) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="61b2f-110">3B Viewer Beta ile kullanım için 3B modelleri derlemek veya iyileştirmek için bkz. aşağıdaki [3B Viewer Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta) .</span><span class="sxs-lookup"><span data-stu-id="61b2f-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="61b2f-111">HoloLens üzerinde 3B model açmak için iki yol vardır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="61b2f-112">Daha fazla bilgi için bkz. aşağıdaki [HoloLens 'TE FBX dosyalarını görüntüleme](#viewing-fbx-files-on-hololens) .</span><span class="sxs-lookup"><span data-stu-id="61b2f-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="61b2f-113">Bu konuları okuduktan sonra sorun yaşıyorsanız, aşağıdaki [sorun giderme](#troubleshooting) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="61b2f-114">Desteklenen içerik belirtimleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="61b2f-115">Dosya biçimi</span><span class="sxs-lookup"><span data-stu-id="61b2f-115">File format</span></span>

- <span data-ttu-id="61b2f-116">FBX biçimi</span><span class="sxs-lookup"><span data-stu-id="61b2f-116">FBX format</span></span>
- <span data-ttu-id="61b2f-117">Maksimum FBX sürümü 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="61b2f-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="61b2f-118">Dosya boyutu</span><span class="sxs-lookup"><span data-stu-id="61b2f-118">File size</span></span>

- <span data-ttu-id="61b2f-119">En az 5 KB</span><span class="sxs-lookup"><span data-stu-id="61b2f-119">Minimum 5 KB</span></span>
- <span data-ttu-id="61b2f-120">Maksimum 500 MB</span><span class="sxs-lookup"><span data-stu-id="61b2f-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="61b2f-121">Geometri</span><span class="sxs-lookup"><span data-stu-id="61b2f-121">Geometry</span></span>

- <span data-ttu-id="61b2f-122">Yalnızca Çokgen modeller.</span><span class="sxs-lookup"><span data-stu-id="61b2f-122">Polygonal models only.</span></span> <span data-ttu-id="61b2f-123">Alt bölme yüzeyleri veya NURBs yok</span><span class="sxs-lookup"><span data-stu-id="61b2f-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="61b2f-124">Sağ elli koordinat sistemi</span><span class="sxs-lookup"><span data-stu-id="61b2f-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="61b2f-125">Dönüştürme matrislerini kırpma desteklenmiyor</span><span class="sxs-lookup"><span data-stu-id="61b2f-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="61b2f-126">Dokular</span><span class="sxs-lookup"><span data-stu-id="61b2f-126">Textures</span></span>

- <span data-ttu-id="61b2f-127">Doku haritaları FBX dosyasına katıştırılmalıdır</span><span class="sxs-lookup"><span data-stu-id="61b2f-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="61b2f-128">Desteklenen görüntü biçimleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-128">Supported image formats</span></span>
  - <span data-ttu-id="61b2f-129">JPEG ve PNG görüntüleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="61b2f-130">BMP görüntüleri (24 bit RGB True-Color)</span><span class="sxs-lookup"><span data-stu-id="61b2f-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="61b2f-131">TGA görüntüleri (24 bit RGB ve 32-bit RGBQ gerçek renk)</span><span class="sxs-lookup"><span data-stu-id="61b2f-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="61b2f-132">Maksimum dok48x2048 doku çözünürlüğü</span><span class="sxs-lookup"><span data-stu-id="61b2f-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="61b2f-133">Her ağ için en fazla bir dağıtılmış harita, bir normal harita ve bir yansıma küpü Haritası</span><span class="sxs-lookup"><span data-stu-id="61b2f-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="61b2f-134">Dağıtma dokularıyla alfa kanalı, %50 altındaysa piksellerin atılmasına neden olur</span><span class="sxs-lookup"><span data-stu-id="61b2f-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="61b2f-135">Animasyon</span><span class="sxs-lookup"><span data-stu-id="61b2f-135">Animation</span></span>

- <span data-ttu-id="61b2f-136">Ayrı nesnelerde ölçek/döndürme/çeviri animasyonu</span><span class="sxs-lookup"><span data-stu-id="61b2f-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="61b2f-137">Kaplama ile iskelet (Rigged) animasyonu</span><span class="sxs-lookup"><span data-stu-id="61b2f-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="61b2f-138">Köşe başına en fazla 4 etkiler</span><span class="sxs-lookup"><span data-stu-id="61b2f-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="61b2f-139">Malzemeler</span><span class="sxs-lookup"><span data-stu-id="61b2f-139">Materials</span></span>

- <span data-ttu-id="61b2f-140">Lambda ve Phong malzemeleri, ayarlanabilir parametrelerle desteklenir</span><span class="sxs-lookup"><span data-stu-id="61b2f-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="61b2f-141">Lambert için desteklenen malzeme özellikleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="61b2f-142">Ana doku (RGB + Alfa testi)</span><span class="sxs-lookup"><span data-stu-id="61b2f-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="61b2f-143">Dağıtma rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="61b2f-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="61b2f-144">Çevresel renk (RGB)</span><span class="sxs-lookup"><span data-stu-id="61b2f-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="61b2f-145">Phong için desteklenen malzeme özellikleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="61b2f-146">Ana doku (RGB + Alfa testi)</span><span class="sxs-lookup"><span data-stu-id="61b2f-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="61b2f-147">Dağıtma rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="61b2f-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="61b2f-148">Çevresel renk (RGB)</span><span class="sxs-lookup"><span data-stu-id="61b2f-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="61b2f-149">Yansımalı renk (RGB)</span><span class="sxs-lookup"><span data-stu-id="61b2f-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="61b2f-150">Parlaklık</span><span class="sxs-lookup"><span data-stu-id="61b2f-150">Shininess</span></span>
  - <span data-ttu-id="61b2f-151">Reflectivity</span><span class="sxs-lookup"><span data-stu-id="61b2f-151">Reflectivity</span></span>
- <span data-ttu-id="61b2f-152">Özel malzemeler desteklenmez</span><span class="sxs-lookup"><span data-stu-id="61b2f-152">Custom materials are not supported</span></span>
- <span data-ttu-id="61b2f-153">Her ağ için en fazla bir malzeme</span><span class="sxs-lookup"><span data-stu-id="61b2f-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="61b2f-154">En fazla bir malzeme katmanı</span><span class="sxs-lookup"><span data-stu-id="61b2f-154">Maximum of one material layer</span></span>
- <span data-ttu-id="61b2f-155">Dosya başına en fazla 8 malzeme</span><span class="sxs-lookup"><span data-stu-id="61b2f-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="61b2f-156">Dosya ve model sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="61b2f-156">File and model limitations</span></span>

<span data-ttu-id="61b2f-157">3B görüntüleyici Beta 'da eşzamanlı olarak kullanılabilecek model, köşe ve kafeslerin sayısını ve dosya boyutunda sabit sınırlar vardır:</span><span class="sxs-lookup"><span data-stu-id="61b2f-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="61b2f-158">model başına 500 MB en büyük dosya boyutu</span><span class="sxs-lookup"><span data-stu-id="61b2f-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="61b2f-159">Köşeler: 600.000 tüm açık modellerde birleştirilmiş</span><span class="sxs-lookup"><span data-stu-id="61b2f-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="61b2f-160">Kafesler: 1.600 tüm açık modellerde birleştirilmiş</span><span class="sxs-lookup"><span data-stu-id="61b2f-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="61b2f-161">Tek seferde en fazla 40 Model açık</span><span class="sxs-lookup"><span data-stu-id="61b2f-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="61b2f-162">3B Görüntüleyicisi Beta için 3B modellerini iyileştirme</span><span class="sxs-lookup"><span data-stu-id="61b2f-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="61b2f-163">Özel Konular</span><span class="sxs-lookup"><span data-stu-id="61b2f-163">Special considerations</span></span>

- <span data-ttu-id="61b2f-164">Doku haritalarının siyah malzemelerinden veya siyah alanlarından kaçının.</span><span class="sxs-lookup"><span data-stu-id="61b2f-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="61b2f-165">Hologragram hafif yapılır, bu nedenle HoloLens, saydam olarak siyah (ışık yokluğu) oluşturur.</span><span class="sxs-lookup"><span data-stu-id="61b2f-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="61b2f-166">Oluşturma aracınızdan FBX 'e vermeden önce tüm geometrinin göründüğünden ve kilidinin açık olduğundan ve geometri içeren katmanların kapalı veya şablonlu olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="61b2f-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="61b2f-167">Görünürlük dikkate alınmıyor.</span><span class="sxs-lookup"><span data-stu-id="61b2f-167">Visibility is not respected.</span></span>
- <span data-ttu-id="61b2f-168">Düğümler arasında çok büyük çeviri uzaklıklarını önleyin (örneğin, 100.000 birim).</span><span class="sxs-lookup"><span data-stu-id="61b2f-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="61b2f-169">Bu, modelin taşınmakta/ölçeklendirildiğinde/döndürüldüğünde değişmesine neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="61b2f-170">Performansı en iyi duruma getirme</span><span class="sxs-lookup"><span data-stu-id="61b2f-170">Performance optimization</span></span>

<span data-ttu-id="61b2f-171">En iyi sonuçlar için yazma işlemi sırasında HoloLens 'teki 3B görüntüleyici Beta uygulamasında içerik yazarken ve doğrulama yaparken performansı göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="61b2f-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="61b2f-172">3B görüntüleyici Beta, içeriğin gerçek zamanlı ve performansa göre HoloLens donanım özelliklerine tabidir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="61b2f-173">3B modelde performansı etkileyebilecek birçok değişken vardır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="61b2f-174">150.000 ' den fazla köşe veya 400 ' den fazla yer varsa 3B görüntüleyici Beta, yükleme sırasında bir uyarı gösterir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="61b2f-175">Animasyonların diğer açık modellerin performansına etkisi olabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="61b2f-176">Ayrıca, 3B görüntüleyici Beta 'da eşzamanlı olarak açabilme toplam sayı modelleri, köşeleri ve kafeslerde de sabit sınırlar vardır (bkz. [dosya ve model sınırlamaları](#file-and-model-limitations)).</span><span class="sxs-lookup"><span data-stu-id="61b2f-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="61b2f-177">Model karmaşıklığı nedeniyle 3B model iyi çalışmıyorsa şunları göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="61b2f-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="61b2f-178">Çokgen sayısını azaltma</span><span class="sxs-lookup"><span data-stu-id="61b2f-178">Reducing polygon count</span></span>
- <span data-ttu-id="61b2f-179">Rigged animasyonunda kemik sayısını azaltma</span><span class="sxs-lookup"><span data-stu-id="61b2f-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="61b2f-180">Kendinden occlusiyon</span><span class="sxs-lookup"><span data-stu-id="61b2f-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="61b2f-181">Çift taraflı işleme, 3B görüntüleyici beta sürümünde desteklenir, ancak performans nedenleriyle varsayılan olarak devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="61b2f-182">Bu, **Ayrıntılar** sayfasındaki **çift taraflı** düğme aracılığıyla açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="61b2f-183">En iyi performansı elde etmek için içeriğinizdeki çift taraflı işleme gereksinimini önleyin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="61b2f-184">3B modeliniz doğrulanıyor</span><span class="sxs-lookup"><span data-stu-id="61b2f-184">Validating your 3D model</span></span>

<span data-ttu-id="61b2f-185">HoloLens üzerinde 3B görüntüleyici Beta 'da açarak modelinizi doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="61b2f-186">Modelinizin özelliklerini ve desteklenmeyen içerik (varsa) uyarılarını görüntülemek için **Ayrıntılar** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="61b2f-187">Gerçek-ömür boyutları ile 3B modeller işleme</span><span class="sxs-lookup"><span data-stu-id="61b2f-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="61b2f-188">Varsayılan olarak, 3B görüntüleyici Beta, 3B modellerini kullanıcıya göre rahat bir boyutta ve konumda görüntüler.</span><span class="sxs-lookup"><span data-stu-id="61b2f-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="61b2f-189">Ancak, gerçek-yaşam ölçümlerine sahip bir 3B modelin işlenmesi önemliyse (örneğin, bir odada mobilya modellerini değerlendirirken), içerik Oluşturucu bu modelin hem uygulama hem de Kullanıcı tarafından yeniden boyutlandırılmasına engel olmak için dosyanın meta verileri içinde bir bayrak ayarlayabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="61b2f-190">Modelin ölçeklendirilmesini engellemek için, Microsoft_DisableScale adlı sahnedeki herhangi bir nesneye bir Boole özel özniteliği ekleyin ve bunu true olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="61b2f-191">daha sonra 3B görüntüleyici Beta, FBX dosyasına bakmış olan FbxSystemUnit bilgilerine göre değişir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="61b2f-192">3B görüntüleyici beta sürümündeki ölçek, FBX birimi başına 1 ölçüm 'tir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="61b2f-193">HoloLens 'te FBX dosyalarını görüntüleme</span><span class="sxs-lookup"><span data-stu-id="61b2f-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="61b2f-194">Microsoft Edge 'den bir FBX dosyası açın</span><span class="sxs-lookup"><span data-stu-id="61b2f-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="61b2f-195">FBX dosyaları, HoloLens üzerinde Microsoft Edge kullanılarak doğrudan bir Web sitesinden açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="61b2f-196">Microsoft Edge 'de, görüntülemek istediğiniz FBX dosyasını içeren Web sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="61b2f-197">İndirilecek dosyayı seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-197">Select the file to download it.</span></span>
1. <span data-ttu-id="61b2f-198">İndirme işlemi tamamlandığında, dosyayı 3B görüntüleyici Beta 'da açmak için Microsoft Edge 'de **Aç** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="61b2f-199">İndirilen dosyaya daha sonra Microsoft Edge 'de Indirmeler kullanılarak erişilebilir ve bu dosya açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="61b2f-200">Bir 3B modeli kaydetmek ve erişmeye devam etmek için, dosyayı bilgisayarınızda indirin ve OneDrive hesabınıza kaydedin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="61b2f-201">Daha sonra dosya, HoloLens üzerinde OneDrive uygulamasından açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="61b2f-202">İndirilebilir FBX modelleriyle bazı Web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar.</span><span class="sxs-lookup"><span data-stu-id="61b2f-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="61b2f-203">3B görüntüleyici Beta, ZIP dosyalarını doğrudan açamaz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="61b2f-204">Bunun yerine, PC 'nizi kullanarak FBX dosyasını ayıklayın ve OneDrive hesabınıza kaydedin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="61b2f-205">Daha sonra dosya, HoloLens üzerinde OneDrive uygulamasından açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="61b2f-206">OneDrive 'dan bir FBX dosyası açın</span><span class="sxs-lookup"><span data-stu-id="61b2f-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="61b2f-207">FBX dosyaları, HoloLens üzerinde OneDrive uygulaması kullanılarak OneDrive 'dan açılabilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="61b2f-208">HoloLens üzerinde Microsoft Store uygulamasını kullanarak OneDrive 'ı yüklediğinizden ve FBX dosyasını BILGISAYARıNıZDA OneDrive 'a zaten yüklemiş olduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="61b2f-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="61b2f-209">OneDrive 'daki bir kez, FBX dosyaları 3B görüntüleyici Beta kullanılarak HoloLens 'te iki şekilde açılabilir:</span><span class="sxs-lookup"><span data-stu-id="61b2f-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="61b2f-210">HoloLens üzerinde OneDrive 'ı başlatın ve bunu 3B görüntüleyici Beta 'da açmak için FBX dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="61b2f-211">3B görüntüleyici Beta 'yı başlatın, AIR ' e dokunarak araç çubuğunu görüntüleyin ve **Dosya Aç**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="61b2f-212">OneDrive başlatılır ve bir FBX dosyası seçmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="61b2f-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="61b2f-213">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="61b2f-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="61b2f-214">3B model açtığımda bir uyarı görüyorum</span><span class="sxs-lookup"><span data-stu-id="61b2f-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="61b2f-215">3B görüntüleyici Beta tarafından desteklenmeyen özellikler içeren bir 3B modeli açmaya çalışırsanız veya model çok karmaşıksa ve performans etkileniyorsa bir uyarı görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="61b2f-216">3B görüntüleyici Beta, 3B modeli yüklemeye devam eder, ancak performans veya görsel uygunluk tehlikeye girebilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="61b2f-217">Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve 3B [Görüntüleyici Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="61b2f-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="61b2f-218">Bir uyarı görüyorum ve 3B model yüklenmiyor</span><span class="sxs-lookup"><span data-stu-id="61b2f-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="61b2f-219">3B görüntüleyici Beta, karmaşıklık veya dosya boyutu nedeniyle veya FBX dosyası bozuksa veya geçersiz olduğunda bir 3B modeli Yükleyememesinin ardından bir hata mesajı görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="61b2f-220">Ayrıca, aynı anda açabilme toplam model, köşe veya kafes sayısı sınırına ulaştıysanız bir hata iletisi görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="61b2f-221">Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve [dosya ve model sınırlamaları](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="61b2f-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="61b2f-222">3B modelim yükleniyor, ancak beklendiği gibi görünmüyor</span><span class="sxs-lookup"><span data-stu-id="61b2f-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="61b2f-223">3B modeliniz, 3B görüntüleyici Beta 'da beklenildiği gibi görünmüyorsa, AIR ' e dokunarak araç çubuğunu görüntüleyin ve **Ayrıntılar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="61b2f-224">Dosyanın 3B görüntüleyici Beta tarafından desteklenmeyen yönleri, uyarı olarak vurgulanır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="61b2f-225">Büyük olasılıkla FBX dosyasına gömülü olmadıklarından, görebileceğiniz en yaygın sorunun dokuları eksik.</span><span class="sxs-lookup"><span data-stu-id="61b2f-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="61b2f-226">Bu durumda, model beyaz görünür.</span><span class="sxs-lookup"><span data-stu-id="61b2f-226">In this case, the model will appear white.</span></span> <span data-ttu-id="61b2f-227">Bu sorun, oluşturma aracınızdan, dokuları Ekle seçeneği belirlenmiş olarak FBX 'e dışarı aktararak oluşturma sürecinde çözülebilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="61b2f-228">Daha fazla bilgi için bkz. [desteklenen içerik belirtimleri](#supported-content-specifications) ve 3B [Görüntüleyici Beta Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="61b2f-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="61b2f-229">3B modelmi görüntülerken Performans düşmem deneyimim</span><span class="sxs-lookup"><span data-stu-id="61b2f-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="61b2f-230">Bir 3B modeli yükleme ve görüntüleme performansı, modelin karmaşıklığına, eşzamanlı olarak açık olan model sayısına veya etkin animasyonlarla model sayısına göre etkilenebilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="61b2f-231">Daha fazla bilgi için bkz. 3B görüntüleyici Beta ve [dosya ve model sınırlamaları](#file-and-model-limitations) [Için 3B modellerini iyileştirme](#optimizing-3d-models-for-3d-viewer-beta) .</span><span class="sxs-lookup"><span data-stu-id="61b2f-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="61b2f-232">HoloLens 'te bir FBX dosyası açtığımda, bu, 3B görüntüleyici beta sürümünde açılmaz</span><span class="sxs-lookup"><span data-stu-id="61b2f-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="61b2f-233">3B görüntüleyici Beta, yüklendiğinde. FBX dosya uzantısıyla otomatik olarak ilişkilendirilir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="61b2f-234">Bir FBX dosyası açmaya çalışırsanız ve Microsoft Store yönlendiren bir iletişim kutusu görürseniz, şu anda HoloLens üzerinde. FBX dosya uzantısıyla ilişkili bir uygulamanız yok.</span><span class="sxs-lookup"><span data-stu-id="61b2f-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="61b2f-235">3B görüntüleyici Beta 'nın yüklü olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="61b2f-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="61b2f-236">Yüklü değilse, HoloLens üzerinde Microsoft Store indirin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="61b2f-237">3B görüntüleyici beta sürümü zaten yüklüyse, 3B Görüntüleyicisi Beta 'yı başlatın ve sonra dosyayı açmayı yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="61b2f-238">Sorun devam ederse, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="61b2f-239">Bu işlem,. FBX dosya uzantısını 3B görüntüleyici Beta ile yeniden ilişkilendirir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="61b2f-240">Bir FBX dosyasını açmaya çalışmak, 3B görüntüleyici beta dışında bir uygulama açarsa, bu uygulama büyük olasılıkla 3B görüntüleyici beta sürümünden sonra yüklenmiş ve. FBX dosya uzantısıyla ilişkilendirmeyi gerçekleştirmiştir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="61b2f-241">3B görüntüleyici Beta 'nın. FBX dosya uzantısıyla ilişkilendirilmesini tercih ediyorsanız, 3B Görüntüleyicisi Beta 'yı kaldırın ve yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="61b2f-242">3B görüntüleyici Beta 'daki Dosya Aç düğmesi bir uygulama başlatamaz</span><span class="sxs-lookup"><span data-stu-id="61b2f-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="61b2f-243">**Dosya Aç** düğmesi, Hololens üzerinde dosya seçici işleviyle ilişkili uygulamayı açar.</span><span class="sxs-lookup"><span data-stu-id="61b2f-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="61b2f-244">OneDrive yüklüyse, **Dosya Aç** düğmesi OneDrive 'ı başlatacaktır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="61b2f-245">Ancak şu anda, HoloLens 'te yüklü dosya seçici işleviyle ilişkili bir uygulama yoksa Microsoft Store yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="61b2f-246">**Dosya Aç** düğmesi OneDrive dışında bir uygulama başlatırsa, bu uygulama OneDrive 'dan sonra büyük olasılıkla yüklenmiş ve dosya seçici işleviyle ilişkilendirmeyi gerçekleştirmiştir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="61b2f-247">3B görüntüleyici Beta 'da **Dosya Aç** düğmesini seçerken OneDrive 'ın başlatılmasını tercih ediyorsanız, OneDrive 'ı kaldırın ve yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="61b2f-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="61b2f-248">**Dosya Aç** düğmesi etkin değilse, 3B görüntüleyici Beta 'da tek seferde açık olabilecek modellerin sınırına ulaşmış olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="61b2f-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="61b2f-249">3B görüntüleyici Beta 'da 40 modelleriniz varsa, ek modeller açabilmek için önce bazılarını kapatmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="61b2f-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61b2f-250">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="61b2f-250">Additional resources</span></span>

- <span data-ttu-id="61b2f-251">[Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) -yalnızca arşivleme amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="61b2f-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="61b2f-252">Bu forum artık etkin değil.</span><span class="sxs-lookup"><span data-stu-id="61b2f-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="61b2f-253">Üçüncü taraf bildirimleri</span><span class="sxs-lookup"><span data-stu-id="61b2f-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
