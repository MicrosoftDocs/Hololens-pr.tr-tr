---
title: HoloLens 'de 3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)
description: HoloLens (1. Nesil) üzerinde Beta 3B Görüntüleyici tarafından desteklene dosya ve özellik türlerini ve uygulamanın nasıl kullan ve sorun giderilenlerini açıklar.
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
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635492"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="c9001-103">HoloLens 'de 3B Görüntüleyici Beta'HoloLens kullanma (1. nesil)</span><span class="sxs-lookup"><span data-stu-id="c9001-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="c9001-104">3B Görüntüleyici Beta, 3D modelleri HoloLens (1. nesil) görüntülemenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="c9001-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="c9001-105">Desteklenen .fbx *dosyalarını Microsoft Edge,* OneDrive ve diğer uygulamalardan açabilir ve görüntüebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c9001-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="c9001-106">Bu makale, .fbx **dosyalarını destekleyen** ve yalnızca HoloLens (1. nesil) olan tam kapsamlı Unity 3B Görüntüleyici Beta uygulaması için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="c9001-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="c9001-107">HoloLens 2'de önceden yüklenmiş **3B Görüntüleyici** uygulaması, karma gerçeklik giriş bölmesinde özel .glb 3B [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) modellerin açılmasını destekler (diğer ayrıntılar için bkz. Varlık gereksinimlerine genel bakış.</span><span class="sxs-lookup"><span data-stu-id="c9001-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9001-108">3B Görüntüleyici Beta, Microsoft Store (1. nesil HoloLens için sürümde kullanılabilir durumda kalsa da, artık etkin geliştirme aşamasında değildir ve artık desteklemektedir.</span><span class="sxs-lookup"><span data-stu-id="c9001-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="c9001-109">3B Görüntüleyici Beta'da 3D modeli açma konusunda sorun varsa veya 3D modelinizin bazı özellikleri desteklenmiyorsa, aşağıdaki Desteklenen içerik [belirtimleri'ne](#supported-content-specifications) bakın.</span><span class="sxs-lookup"><span data-stu-id="c9001-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="c9001-110">3D modelleri 3B Görüntüleyici Beta ile kullanmak üzere derlemek veya iyileştirmek için aşağıdaki [3D](#optimizing-3d-models-for-3d-viewer-beta) modelleri 3B Görüntüleyici Beta için iyileştirme.</span><span class="sxs-lookup"><span data-stu-id="c9001-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="c9001-111">Bu modelde 3D modeli açmanın iki HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="c9001-112">Daha [fazla bilgi için aşağıdaki FBX HoloLens FBX](#viewing-fbx-files-on-hololens) dosyalarını görüntüleme.</span><span class="sxs-lookup"><span data-stu-id="c9001-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="c9001-113">Bu konuları okuduktan sonra sorun ediyorsanız aşağıdaki Sorun [giderme'ye](#troubleshooting) bakın.</span><span class="sxs-lookup"><span data-stu-id="c9001-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="c9001-114">Desteklenen içerik belirtimleri</span><span class="sxs-lookup"><span data-stu-id="c9001-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="c9001-115">Dosya biçimi</span><span class="sxs-lookup"><span data-stu-id="c9001-115">File format</span></span>

- <span data-ttu-id="c9001-116">FBX biçimi</span><span class="sxs-lookup"><span data-stu-id="c9001-116">FBX format</span></span>
- <span data-ttu-id="c9001-117">En yüksek FBX sürümü 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="c9001-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="c9001-118">Dosya boyutu</span><span class="sxs-lookup"><span data-stu-id="c9001-118">File size</span></span>

- <span data-ttu-id="c9001-119">En az 5 KB</span><span class="sxs-lookup"><span data-stu-id="c9001-119">Minimum 5 KB</span></span>
- <span data-ttu-id="c9001-120">En fazla 500 MB</span><span class="sxs-lookup"><span data-stu-id="c9001-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="c9001-121">Geometri</span><span class="sxs-lookup"><span data-stu-id="c9001-121">Geometry</span></span>

- <span data-ttu-id="c9001-122">Yalnızca çokgen modeller.</span><span class="sxs-lookup"><span data-stu-id="c9001-122">Polygonal models only.</span></span> <span data-ttu-id="c9001-123">Alt bölüm yüzeyleri veya BESB'ler yok</span><span class="sxs-lookup"><span data-stu-id="c9001-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="c9001-124">Sağ el ile koordinat sistemi</span><span class="sxs-lookup"><span data-stu-id="c9001-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="c9001-125">Dönüştürme matrislerini yalıtma desteklenmiyor</span><span class="sxs-lookup"><span data-stu-id="c9001-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="c9001-126">Dokular</span><span class="sxs-lookup"><span data-stu-id="c9001-126">Textures</span></span>

- <span data-ttu-id="c9001-127">Doku eşlemeleri FBX dosyasına ekli olmalı</span><span class="sxs-lookup"><span data-stu-id="c9001-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="c9001-128">Desteklenen görüntü biçimleri</span><span class="sxs-lookup"><span data-stu-id="c9001-128">Supported image formats</span></span>
  - <span data-ttu-id="c9001-129">JPEG ve PNG görüntüleri</span><span class="sxs-lookup"><span data-stu-id="c9001-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="c9001-130">BMP görüntüleri (24 bit RGB gerçek renk)</span><span class="sxs-lookup"><span data-stu-id="c9001-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="c9001-131">TGA görüntüleri (24 bit RGB ve 32 bit RGBQ gerçek renk)</span><span class="sxs-lookup"><span data-stu-id="c9001-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="c9001-132">2048x2048 en yüksek doku çözünürlüğü</span><span class="sxs-lookup"><span data-stu-id="c9001-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="c9001-133">En fazla bir eşlemli harita, bir normal harita ve mesh başına bir yansıma küpü haritası</span><span class="sxs-lookup"><span data-stu-id="c9001-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="c9001-134">Doku dokularında alfa kanal, piksellerin %50'nin altına inerse atılır</span><span class="sxs-lookup"><span data-stu-id="c9001-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="c9001-135">Animasyon</span><span class="sxs-lookup"><span data-stu-id="c9001-135">Animation</span></span>

- <span data-ttu-id="c9001-136">Tek tek nesnelerde ölçeklendirme/döndürme/çeviri animasyonu</span><span class="sxs-lookup"><span data-stu-id="c9001-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="c9001-137">Deri ile Cilde (sıkı) animasyon</span><span class="sxs-lookup"><span data-stu-id="c9001-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="c9001-138">Köşe başına en fazla 4 etki</span><span class="sxs-lookup"><span data-stu-id="c9001-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="c9001-139">Malzemeler</span><span class="sxs-lookup"><span data-stu-id="c9001-139">Materials</span></span>

- <span data-ttu-id="c9001-140">Lambert ve Piser malzemeleri, ayarlanabilir parametrelerle birlikte de desteklendi</span><span class="sxs-lookup"><span data-stu-id="c9001-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="c9001-141">Lambert için desteklenen malzeme özellikleri</span><span class="sxs-lookup"><span data-stu-id="c9001-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="c9001-142">Ana Doku (RGB + Alfa Testi)</span><span class="sxs-lookup"><span data-stu-id="c9001-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="c9001-143">Yayma Rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="c9001-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="c9001-144">Ortam Rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="c9001-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="c9001-145">Piser için desteklenen malzeme özellikleri</span><span class="sxs-lookup"><span data-stu-id="c9001-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="c9001-146">Ana Doku (RGB + Alfa Testi)</span><span class="sxs-lookup"><span data-stu-id="c9001-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="c9001-147">Yayma Rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="c9001-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="c9001-148">Ortam Rengi (RGB)</span><span class="sxs-lookup"><span data-stu-id="c9001-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="c9001-149">Specular Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="c9001-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="c9001-150">Hazır olma</span><span class="sxs-lookup"><span data-stu-id="c9001-150">Shininess</span></span>
  - <span data-ttu-id="c9001-151">Yansıtma</span><span class="sxs-lookup"><span data-stu-id="c9001-151">Reflectivity</span></span>
- <span data-ttu-id="c9001-152">Özel malzemeler desteklenmiyor</span><span class="sxs-lookup"><span data-stu-id="c9001-152">Custom materials are not supported</span></span>
- <span data-ttu-id="c9001-153">Örgü başına en fazla bir malzeme</span><span class="sxs-lookup"><span data-stu-id="c9001-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="c9001-154">En fazla bir malzeme katmanı</span><span class="sxs-lookup"><span data-stu-id="c9001-154">Maximum of one material layer</span></span>
- <span data-ttu-id="c9001-155">Dosya başına en fazla 8 malzeme</span><span class="sxs-lookup"><span data-stu-id="c9001-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="c9001-156">Dosya ve model sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="c9001-156">File and model limitations</span></span>

<span data-ttu-id="c9001-157">Dosya boyutunun yanı sıra beta sürümünde aynı anda açabilirsiniz model, köşe ve tire sayısı için sabit 3B Görüntüleyici:</span><span class="sxs-lookup"><span data-stu-id="c9001-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="c9001-158">Model başına en fazla 500 MB dosya boyutu</span><span class="sxs-lookup"><span data-stu-id="c9001-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="c9001-159">Köşeler: Tüm açık modellerde 600.000 birleşik</span><span class="sxs-lookup"><span data-stu-id="c9001-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="c9001-160">Tireler: Tüm açık modellerde 1.600 birleşik</span><span class="sxs-lookup"><span data-stu-id="c9001-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="c9001-161">Aynı anda en fazla 40 model açılır</span><span class="sxs-lookup"><span data-stu-id="c9001-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="c9001-162">3B Görüntüleyici Beta için 3D 3B Görüntüleyici iyileştirme</span><span class="sxs-lookup"><span data-stu-id="c9001-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="c9001-163">Dikkat edilmesi gereken özel noktalar</span><span class="sxs-lookup"><span data-stu-id="c9001-163">Special considerations</span></span>

- <span data-ttu-id="c9001-164">Doku eşlemelerinde siyah malzemelerden veya siyah alanlardan kaçının.</span><span class="sxs-lookup"><span data-stu-id="c9001-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="c9001-165">Hologramlar, bu nedenle HoloLens siyahı (ışık yokluğu) saydam olarak işler.</span><span class="sxs-lookup"><span data-stu-id="c9001-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="c9001-166">Oluşturma aracınızı FBX'e aktarmadan önce, tüm geometrinin görünür ve açık olduğundan ve geometri içeren hiçbir katmanın kapalı veya şablona sahip olmadığını emin olun.</span><span class="sxs-lookup"><span data-stu-id="c9001-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="c9001-167">Görünürlüğün kabul edilene bir şey olmadığını.</span><span class="sxs-lookup"><span data-stu-id="c9001-167">Visibility is not respected.</span></span>
- <span data-ttu-id="c9001-168">Düğümler arasında çok büyük çeviri uzaklıklarından kaçının (örneğin, 100.000 birim).</span><span class="sxs-lookup"><span data-stu-id="c9001-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="c9001-169">Bu, modelin taşınırken/ölçeklendirirken/döndürülürken hareket uzemesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="c9001-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="c9001-170">Performansı en iyi duruma getirme</span><span class="sxs-lookup"><span data-stu-id="c9001-170">Performance optimization</span></span>

<span data-ttu-id="c9001-171">en iyi sonuçları elde etmek için içerik yazma sırasında performansı göz 3B Görüntüleyici ve HoloLens beta uygulamasında doğrular.</span><span class="sxs-lookup"><span data-stu-id="c9001-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="c9001-172">3B Görüntüleyici Beta, içeriği gerçek zamanlı olarak işler ve performans, HoloLens özelliklerine tabi olur.</span><span class="sxs-lookup"><span data-stu-id="c9001-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="c9001-173">3D modelde performansı etkileyen birçok değişken vardır.</span><span class="sxs-lookup"><span data-stu-id="c9001-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="c9001-174">3B Görüntüleyici Beta, 150.000'den fazla köşe veya 400'den fazla meshes varsa yükte bir uyarı gösterir.</span><span class="sxs-lookup"><span data-stu-id="c9001-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="c9001-175">Animasyonların diğer açık modellerin performansı üzerinde etkisi olabilir.</span><span class="sxs-lookup"><span data-stu-id="c9001-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="c9001-176">Ayrıca, Beta sürümünde aynı anda açabilirsiniz toplam sayı modelleri, köşeleri ve meshes için de sabit sınırlar 3B Görüntüleyici (bkz. [Dosya ve model sınırlamaları).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="c9001-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="c9001-177">Model karmaşıklığı nedeniyle 3D modeli iyi çalışmıyorsa şunları göz önünde bulundurarak:</span><span class="sxs-lookup"><span data-stu-id="c9001-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="c9001-178">Çokgen sayısını azaltma</span><span class="sxs-lookup"><span data-stu-id="c9001-178">Reducing polygon count</span></span>
- <span data-ttu-id="c9001-179">Zorlu animasyonda yer alan yerlerin sayısını azaltma</span><span class="sxs-lookup"><span data-stu-id="c9001-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="c9001-180">Kendi kendine kapanmayı önleme</span><span class="sxs-lookup"><span data-stu-id="c9001-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="c9001-181">Beta sürümünde çift taraflı işleme 3B Görüntüleyici, ancak performans nedeniyle varsayılan olarak kapalıdır.</span><span class="sxs-lookup"><span data-stu-id="c9001-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="c9001-182">Bu, Ayrıntılar sayfasındaki **Çift Taraflı** düğme aracılığıyla **açık** olabilir.</span><span class="sxs-lookup"><span data-stu-id="c9001-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="c9001-183">En iyi performans için içeriğinize çift taraflı işlemeye gerek yok.</span><span class="sxs-lookup"><span data-stu-id="c9001-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="c9001-184">3D modelinizi doğrulama</span><span class="sxs-lookup"><span data-stu-id="c9001-184">Validating your 3D model</span></span>

<span data-ttu-id="c9001-185">Modelinizi, 3B Görüntüleyici Beta'da açarak HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="c9001-186">Modelinizin  desteklenmeyen içerikle ilgili özelliklerini ve uyarılarını (varsa) görüntülemek için Ayrıntılar düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="c9001-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="c9001-187">Gerçek hayattaki boyutlara sahip 3B modelleri işleme</span><span class="sxs-lookup"><span data-stu-id="c9001-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="c9001-188">Varsayılan olarak, 3B Görüntüleyici Beta 3D modelleri kullanıcıya göre uygun boyutta ve konumda görüntüler.</span><span class="sxs-lookup"><span data-stu-id="c9001-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="c9001-189">Ancak gerçek hayattan yaşam ölçümleriyle 3B modelin işlemesi önemlidir (örneğin, bir oda içindeki evlerin modellerini değerlendirirken), içerik oluşturucu bu modelin hem uygulama hem de kullanıcı tarafından yeniden boyutlandırmasını önlemek için dosyanın meta verilerinde bir bayrak ayarlayan bir bayrak olabilir.</span><span class="sxs-lookup"><span data-stu-id="c9001-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="c9001-190">Modelin ölçeklendirimsini önlemek için, sahnenin Microsoft_DisableScale adlı herhangi bir nesnesine boole özel özniteliği ekleyin ve true olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="c9001-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="c9001-191">3B Görüntüleyici Beta, FBX dosyasına ek olarak FbxSystemUnit bilgilerini dikkate alar.</span><span class="sxs-lookup"><span data-stu-id="c9001-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="c9001-192">Beta'3B Görüntüleyici ölçeği FBX birimi başına 1 ölçüm olarak ölçeklendirin.</span><span class="sxs-lookup"><span data-stu-id="c9001-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="c9001-193">FBX dosyalarını HoloLens</span><span class="sxs-lookup"><span data-stu-id="c9001-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="c9001-194">Dosyadan FBX Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c9001-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="c9001-195">FBX dosyaları doğrudan bir web sitesinden, Microsoft Edge üzerinden HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="c9001-196">Bu Microsoft Edge, görüntülemek istediğiniz FBX dosyasını içeren web sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="c9001-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="c9001-197">İndirilen dosyayı seçin.</span><span class="sxs-lookup"><span data-stu-id="c9001-197">Select the file to download it.</span></span>
1. <span data-ttu-id="c9001-198">İndirme işlemi tamamlandığında, dosyayı **Beta'da** açmak Microsoft Edge aç düğmesini 3B Görüntüleyici seçin.</span><span class="sxs-lookup"><span data-stu-id="c9001-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="c9001-199">İndirilen dosyaya daha sonra dosyada İndirilenler kullanılarak erişilebilir ve Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c9001-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="c9001-200">3D modeli kaydetmek ve sürekli erişim sağlamak için dosyayı bilgisayarınıza indirin ve OneDrive kaydedin.</span><span class="sxs-lookup"><span data-stu-id="c9001-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="c9001-201">Dosya daha sonra OneDrive uygulamasından HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="c9001-202">İndirilebilir FBX modellerine sahip bazı web siteleri bunları sıkıştırılmış ZIP biçiminde sağlar.</span><span class="sxs-lookup"><span data-stu-id="c9001-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="c9001-203">3B Görüntüleyici Beta ZIP dosyalarını doğrudan açamaz.</span><span class="sxs-lookup"><span data-stu-id="c9001-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="c9001-204">Bunun yerine, FBX dosyasını ayıklamak için bilgisayarınızı kullanın ve dosyayı OneDrive kaydedin.</span><span class="sxs-lookup"><span data-stu-id="c9001-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="c9001-205">Dosya daha sonra OneDrive uygulamasından HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="c9001-206">Dosyadan FBX OneDrive</span><span class="sxs-lookup"><span data-stu-id="c9001-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="c9001-207">FBX dosyaları, OneDrive üzerinde OneDrive kullanılarak HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="c9001-208">HoloLens'de OneDrive Microsoft Store uygulamasını kullanarak FBX dosyasını bilgisayarınıza yüklemiş OneDrive emin olun.</span><span class="sxs-lookup"><span data-stu-id="c9001-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="c9001-209">FBX OneDrive iki farklı şekilde HoloLens Beta 3B Görüntüleyici açılabilir:</span><span class="sxs-lookup"><span data-stu-id="c9001-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="c9001-210">OneDrive'HoloLens FBX dosyasını seçerek Beta'da 3B Görüntüleyici açın.</span><span class="sxs-lookup"><span data-stu-id="c9001-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="c9001-211">Beta 3B Görüntüleyici'yi açın, araç çubuğunu göstermek için havadan dokunun ve Dosya **Aç'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="c9001-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="c9001-212">OneDrive, bir FBX dosyası seçmenize olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="c9001-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c9001-213">Sorun giderme</span><span class="sxs-lookup"><span data-stu-id="c9001-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="c9001-214">3D modeli açtım bir uyarı görüyorum</span><span class="sxs-lookup"><span data-stu-id="c9001-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="c9001-215">3B Görüntüleyici Beta tarafından desteklenen özellikler içeren bir 3D modeli açmaya çalışırken veya model çok karmaşıksa ve performans etkilenebilirse bir uyarıyla karşınız olur.</span><span class="sxs-lookup"><span data-stu-id="c9001-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="c9001-216">3B Görüntüleyici Beta 3D modeli yüklemeye devam eder, ancak performans veya görsel uygunluk tehlikeye girebilir.</span><span class="sxs-lookup"><span data-stu-id="c9001-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="c9001-217">Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="c9001-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="c9001-218">Bir uyarı görüyorum ve 3D modeli yüklenemedi</span><span class="sxs-lookup"><span data-stu-id="c9001-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="c9001-219">3B Görüntüleyici Beta, karmaşıklık veya dosya boyutu nedeniyle 3B modeli yükleyene kadar ya da FBX dosyası bozuk veya geçersiz olduğunda bir hata iletisiyle karşınız.</span><span class="sxs-lookup"><span data-stu-id="c9001-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="c9001-220">Toplam model, köşe veya tire sayısı sınırına ulaştınız ve aynı anda açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c9001-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="c9001-221">Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve [Dosya ve model sınırlamaları.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="c9001-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="c9001-222">3D modelim yüklenmiyor ama beklendiği gibi görünmüyor</span><span class="sxs-lookup"><span data-stu-id="c9001-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="c9001-223">3D modeliniz Beta sürümünde beklendiği gibi 3B Görüntüleyici, araç çubuğunu göstermek için havadan dokunun ve Ayrıntılar'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="c9001-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="c9001-224">3B Görüntüleyici Beta tarafından 3B Görüntüleyici dosyanın yönleri uyarı olarak vurgulanır.</span><span class="sxs-lookup"><span data-stu-id="c9001-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="c9001-225">Gördüğünüz en yaygın sorun, eksik dokular olabilir çünkü bunlar FBX dosyasına ekli değildir.</span><span class="sxs-lookup"><span data-stu-id="c9001-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="c9001-226">Bu durumda model beyaz görünür.</span><span class="sxs-lookup"><span data-stu-id="c9001-226">In this case, the model will appear white.</span></span> <span data-ttu-id="c9001-227">Oluşturma aracınızı doku ekleme seçeneği seçiliyken FBX'e aktararak bu sorun oluşturma işlemiyle çözülebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c9001-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="c9001-228">Daha fazla bilgi için [bkz. Desteklenen içerik belirtimleri](#supported-content-specifications) ve Beta için [3D 3B Görüntüleyici iyileştirme.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="c9001-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="c9001-229">3D modelimi görüntülerken performans düşüşleri yaşanıyor</span><span class="sxs-lookup"><span data-stu-id="c9001-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="c9001-230">3D modeli yüklerken ve görüntülerken performans, modelin karmaşıklığından, aynı anda açık olan model sayısından veya etkin animasyonlarla model sayısından etkilenebilir.</span><span class="sxs-lookup"><span data-stu-id="c9001-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="c9001-231">Daha fazla bilgi için bkz. Beta ve Dosya ve model [3B Görüntüleyici için 3D](#optimizing-3d-models-for-3d-viewer-beta) [modelleri iyileştirme.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="c9001-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="c9001-232">HoloLens'da FBX dosyasını 3B Görüntüleyici beta sürümünde açılmaz</span><span class="sxs-lookup"><span data-stu-id="c9001-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="c9001-233">3B Görüntüleyici Beta, yüklenirken .fbx dosya uzantısıyla otomatik olarak ilişkilendirilır.</span><span class="sxs-lookup"><span data-stu-id="c9001-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="c9001-234">Bir FBX dosyası açmaya ve sizi Microsoft Store'a yönlendiren bir iletişim kutusu görmeye devam ediyorsanız, şu anda dosya üzerinde .fbx dosya uzantısıyla ilişkilendirilmiş bir HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="c9001-235">Beta'3B Görüntüleyici yüklü olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="c9001-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="c9001-236">Yüklü değilse, dosyanın Microsoft Store'HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="c9001-237">Beta 3B Görüntüleyici yüklüyse Beta'3B Görüntüleyici açın ve dosyayı yeniden açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="c9001-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="c9001-238">Sorun devam ederse Beta sürümünü kaldırıp 3B Görüntüleyici yükleyin.</span><span class="sxs-lookup"><span data-stu-id="c9001-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="c9001-239">Bu, .fbx dosya uzantısını beta sürümüyle 3B Görüntüleyici eder.</span><span class="sxs-lookup"><span data-stu-id="c9001-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="c9001-240">FBX dosyası açılmaya çalışıldıktan sonra 3B Görüntüleyici Beta dışında bir uygulama açılırsa, bu uygulama büyük olasılıkla 3B Görüntüleyici Beta'dan sonra yüklenmiştir ve .fbx dosya uzantısıyla ilişkilendirmeyi ele almış olur.</span><span class="sxs-lookup"><span data-stu-id="c9001-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="c9001-241">Beta'3B Görüntüleyici .fbx dosya uzantısıyla ilişkilendirilmeyi tercih ediyorsanız, Beta'3B Görüntüleyici yükleyin.</span><span class="sxs-lookup"><span data-stu-id="c9001-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="c9001-242">3B Görüntüleyici Beta'da Dosya Aç düğmesi uygulama başlatamıyor</span><span class="sxs-lookup"><span data-stu-id="c9001-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="c9001-243">Dosya **Aç düğmesi,** dosya seçici işleviyle ilişkili uygulamayı HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c9001-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="c9001-244">Yüklü OneDrive, Dosya Aç **düğmesinin** dosya açma OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c9001-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="c9001-245">Ancak, şu anda dosya seçici işleviyle ilişkilendirilmiş bir uygulama HoloLens, dosya seçici işlevine Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="c9001-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="c9001-246">Dosya **Aç düğmesi** OneDrive dışında bir uygulama başlatıyorsa, bu uygulama büyük olasılıkla OneDrive yüklendikten ve dosya seçici işleviyle ilişkilendirmeyi ele aldı.</span><span class="sxs-lookup"><span data-stu-id="c9001-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="c9001-247">Beta'OneDrive Dosya Aç düğmesini seçerek  başlatmayı tercih ediyorsanız, 3B Görüntüleyici'yi kaldırın ve OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c9001-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="c9001-248">Dosya **Aç düğmesi** etkin durumda değilse, tek bir anda Beta sürümünde açabilirsiniz 3B Görüntüleyici sınırına ulaştınız.</span><span class="sxs-lookup"><span data-stu-id="c9001-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="c9001-249">Beta sürümünde 40 modeli 3B Görüntüleyici, ek modeller açabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="c9001-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9001-250">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="c9001-250">Additional resources</span></span>

- <span data-ttu-id="c9001-251">[Destek forumları](http://forums.hololens.com/categories/3d-viewer-beta) - Yalnızca arşivleme amacıyla.</span><span class="sxs-lookup"><span data-stu-id="c9001-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="c9001-252">Bu forum artık etkin değil.</span><span class="sxs-lookup"><span data-stu-id="c9001-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="c9001-253">Üçüncü taraf bildirimler</span><span class="sxs-lookup"><span data-stu-id="c9001-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
