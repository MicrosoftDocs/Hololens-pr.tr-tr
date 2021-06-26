---
title: HoloLens cihazları ve hologramları hakkında sık sorulan sorular
description: HoloLens veya hologramlarla etkileşim kurma hakkında hızlı bir sorunun mu var?  Bu makale hızlı bir yanıt ve daha fazla kaynak sağlar.
keywords: hololens, s, bilinen sorun, yardım
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924035"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="f51c8-105">Hologramlar ve etkileşim sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="f51c8-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="f51c8-106">Bu makalede hologram yerleştirme, boşluklarla çalışma ve hologramlarla ilgili sorunları bildirme ile ilgili sorunlar giderilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="f51c8-107">Her soruna sahip olduğunuz her zaman şu sorunlardan emin olun:</span><span class="sxs-lookup"><span data-stu-id="f51c8-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="f51c8-108">Bunun [bir şeyi düzeltip](hololens-restart-recover.md) düzeltmey olmadığını görmek için yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="f51c8-109">Sorun gidermeden önce HoloLens'in [ücretlendir (en az](hololens2-charging.md) bir saat ücretlendir) olduğundan emin olur.</span><span class="sxs-lookup"><span data-stu-id="f51c8-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="f51c8-110">Sorun hakkında bize bilgi göndermek için Lütfen Geri Bildirim uygulamasını kullanın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="f51c8-111">Geri Bildirim uygulamasını Başlat menüsünde [  bulabilirsiniz.](holographic-home.md)</span><span class="sxs-lookup"><span data-stu-id="f51c8-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="f51c8-112">HoloLens'inizi nasıl takacakları hakkında ipuçları için bkz. [Fit Ayarlama.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="f51c8-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="f51c8-113">Yeni alanlar oluşturulamıyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="f51c8-114">Boşluklar tanımlenemiyor veya yüklenemiyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="f51c8-115">Nasıl yaparım? alanları mı silebilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="f51c8-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="f51c8-116">Hologramlar doğru görünmüyor veya hareket ediyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="f51c8-117">"Yer bulma" iletisi</span><span class="sxs-lookup"><span data-stu-id="f51c8-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="f51c8-118">Beklenen hologramlar alanımda gösterlenmiyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="f51c8-119">Hologram yerleştirilemleri veya önceden yerleştirilmiş hologramları göremiyorum</span><span class="sxs-lookup"><span data-stu-id="f51c8-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="f51c8-120">Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur</span><span class="sxs-lookup"><span data-stu-id="f51c8-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="f51c8-121">Hologramlar duvarın diğer tarafında görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="f51c8-122">Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="f51c8-123">Uygulamalar, taşımadan sonra çok yakın görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="f51c8-124">Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme</span><span class="sxs-lookup"><span data-stu-id="f51c8-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="f51c8-125">Yeni alanlar oluşturulamıyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-125">New spaces can't be created</span></span>

<span data-ttu-id="f51c8-126">En olası sorun, depolama alanı az olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="f51c8-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="f51c8-127">[Biraz disk alanı boşaltın](hololens-troubleshooting.md#low-disk-space-error) ve sonra yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="f51c8-128">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="f51c8-129">Boşluklar tanımlenemiyor veya yüklenemiyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="f51c8-130">HoloLens'iniz otomatik olarak içinde yer alan alanı belirleyeye ve yükleyenene kadar aşağıdaki faktörleri kontrol edin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="f51c8-131">Wi-Fi'a bağlı olduğunuzdan emin Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f51c8-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="f51c8-132">Odada bol miktarda ışık olduğundan emin olun</span><span class="sxs-lookup"><span data-stu-id="f51c8-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="f51c8-133">Çevresinde önemli bir değişiklik olmadığını emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="f51c8-134">Ayrıca, Ayarlar Sistem Alanları'nın 'a gidip el ile bir alan yükleyebilirsiniz **veya**  >  **alanlarınızı**  >  **yönetebilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="f51c8-135">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="f51c8-136">Nasıl yaparım? alanları mı silebilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="f51c8-136">How do I delete all spaces?</span></span>

<span data-ttu-id="f51c8-137">*Çok yakında*</span><span class="sxs-lookup"><span data-stu-id="f51c8-137">*Coming soon*</span></span>

[<span data-ttu-id="f51c8-138">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="f51c8-139">Hologramlar doğru görünmüyor veya hareket ediyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="f51c8-140">Hologramlar doğru görünmüyorsa (örneğin, bu hologramlar hareket ediyor veya shaky veya bunların üzerinde siyah düzeltme ekleri görüyorsanız) şu düzeltmelerden birini deneyin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="f51c8-141">[Cihazınızın güvenlik kameralarını temizleyin](hololens1-hardware.md#care-and-cleaning) ve algılayıcıları engelleyen bir şey olmadığını emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="f51c8-142">Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="f51c8-143">HoloLens'in bunları tamamen tarayana kadar etrafınıza bakarak çevrenizi incelemeyi deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="f51c8-144">Çok sayıda hologram yerleştirilse, bazı hologramları kaldırmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="f51c8-145">Sorun devam ediyorsanız, Ayarlama uygulamasını çalıştırmayı deniyorum.</span><span class="sxs-lookup"><span data-stu-id="f51c8-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="f51c8-146">Bu uygulama, hologramlarınızı en iyi şekilde tutmaya yardımcı olmak için HoloLens'inizi sizin için ayarlar.</span><span class="sxs-lookup"><span data-stu-id="f51c8-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="f51c8-147">Bunu yapmak için Ayarlar Sistem Yardımcı  >    >  **Programları'nı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="f51c8-148">**Ayarlama'nın** altında Açık **Ayar'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="f51c8-149">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="f51c8-150">"Yer bulma" iletisi</span><span class="sxs-lookup"><span data-stu-id="f51c8-150">"Finding your space" message</span></span>

<span data-ttu-id="f51c8-151">HoloLens bir alanı öğrenerek veya yüklerken "Yerlerinizi bulma" ifadesinin yer alır.</span><span class="sxs-lookup"><span data-stu-id="f51c8-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="f51c8-152">Bu ileti birkaç saniyeden uzun süre görüntülenirse, uygulamanın altında "Hala alanınızı Başlat menüsü" ifadesinin yer alan başka bir iletiyle de karşınıza vardır.</span><span class="sxs-lookup"><span data-stu-id="f51c8-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="f51c8-153">Bu iletiler HoloLens'in alanınızı eşleme konusunda sorun içinde olduğu anlamına geliyor.</span><span class="sxs-lookup"><span data-stu-id="f51c8-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="f51c8-154">Bu durumda uygulamaları açabilirsiniz ancak ortamınıza hologramlar yer açabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="f51c8-155">Bu iletileri sık görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="f51c8-156">Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="f51c8-157">Cihaz mengenenizin temiz olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="f51c8-158">[Mengenenizi temizlemeyi öğrenin.](hololens1-hardware.md#care-and-cleaning)</span><span class="sxs-lookup"><span data-stu-id="f51c8-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="f51c8-159">Güçlü bir sinyale sahip Wi-Fi olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="f51c8-160">Sanal sinyal veya zayıf sinyal Wi-Fi yeni bir Wi-Fi girersiniz HoloLens alanınızı bulamaz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="f51c8-161">Ayarlar Ağ Wi-Fi   >  Wi-Fi'a **gidip &amp;**  >  **bağlantınızı kontrol edin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="f51c8-162">Daha yavaş ilerlemeyi deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-162">Try moving more slowly.</span></span>

[<span data-ttu-id="f51c8-163">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="f51c8-164">Beklenen hologramlar alanımda gösterlenmiyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="f51c8-165">Yerleştir beklediğiniz hologramları görmüyorsanız veya beklediğiniz hologramları görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="f51c8-166">Birkaç lambayı açın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-166">Turn on some lights.</span></span> <span data-ttu-id="f51c8-167">HoloLens en iyi şekilde iyi ışık alan bir alanda çalışır.</span><span class="sxs-lookup"><span data-stu-id="f51c8-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="f51c8-168">Ayarlar Sistem Hologramları Yakındaki hologramları kaldır'a gidip ihtiyacınız olan  >    >    >  **hologramları kaldırın.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="f51c8-169">Veya gerekirse Tüm **hologramları kaldır'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f51c8-170">Alanınızdaki düzen veya aydınlatma önemli ölçüde değişiyorsa, cihazınız alanınızı tanımlama ve hologramlarınızı gösterme konusunda sorun olabilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="f51c8-171">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="f51c8-172">Hologram yerleştirilemleri veya önceden yerleştirilmiş hologramları göremiyorum</span><span class="sxs-lookup"><span data-stu-id="f51c8-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="f51c8-173">HoloLens alanınızı eşleyene veya yükleyenene kadar Sınırlı moda girer ve hologram yerleştiresiniz veya yerleştirmiş olduğunuz hologramları göresiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="f51c8-174">İşte deneyebileceğiniz bazı çözümler:</span><span class="sxs-lookup"><span data-stu-id="f51c8-174">Here are some things to try:</span></span>

- <span data-ttu-id="f51c8-175">HoloLens'in alanı görene ve eşleyene kadar ortamınız için yeterli ışık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="f51c8-176">Hologramı yapmaya çalıştığın yerden bir ile üç metre arasında dur.</span><span class="sxs-lookup"><span data-stu-id="f51c8-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="f51c8-177">Hologramları siyah veya yansıtıcı yüzeylere yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="f51c8-178">Bir ağ bağlantısına bağlı olduğunuzdan emin Wi-Fi olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="f51c8-179">Wi-Fi'a bağlı değilsanız HoloLens bilinen bir alanı tanım tanımp yükleyememektedir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="f51c8-180">HoloLens'in çevrenizi yeniden görene kadar odaları dolaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="f51c8-181">Nelerin taranmış olduğunu görmek için havadan dokunarak eşleme ağı grafiğini ortaya çıkarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="f51c8-182">Yeni bir alan oluşturmanız gerekirse Wi-Fi'a bağlanın ve HoloLens'inizi yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="f51c8-183">Doğru boşluğun etkin olup olmadığını görmek veya el ile bir alan yüklemek için Ayarlar Sistem  >  **Alanları'ne**  >  **gidin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="f51c8-184">Doğru alan yüklü ise ve sorun devam ediyorsanız, alan bozuk olabilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="f51c8-185">Bu sorunu çözmek için alanı seçin ve **kaldır'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="f51c8-186">Siz alanı kaldırdikten sonra HoloLens, çevrenizi eşlemeye ve yeni bir alan oluşturmaya başlar.</span><span class="sxs-lookup"><span data-stu-id="f51c8-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="f51c8-187">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="f51c8-188">Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur</span><span class="sxs-lookup"><span data-stu-id="f51c8-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="f51c8-189">Bir holograma çok yaklaşmanız, hologramı geri yüklemek için geçici olarak &mdash; kaybolur, yalnızca bundan uzaklaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="f51c8-190">Ayrıca, birkaç hologramı birbirine yakın yerleştirilse de bazıları kaybolabilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="f51c8-191">Birkaç tane kaldırmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-191">Try removing a few.</span></span>

<span data-ttu-id="f51c8-192">Hologramlar ayrıca diğer hologramlar veya duvar gibi nesneler tarafından engellenmiş veya kapatılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="f51c8-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="f51c8-193">Bu durumda aşağıdaki düzeltmelerden birini deneyin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="f51c8-194">Hologram başka bir hologramda yer alan bir hologram ise, büyük harfli hologramı başka bir konuma taşıma.</span><span class="sxs-lookup"><span data-stu-id="f51c8-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="f51c8-195">Bunu yapmak için **Ayarla'ya ve** ardından dokunarak basılı tutun ve konuma getirin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="f51c8-196">Hologram bir duvara monte edilirse Ayarla'ya tıklayın **ve** ardından hologram görünene kadar duvara doğru inin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="f51c8-197">Dokunun ve basılı tutun, sonra hologramı duvardan ileri ve dışarı çekin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="f51c8-198">Hareketleri kullanarak hologramı hareket ettire biliyorsanız sesinizi kullanarak kaldırın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="f51c8-199">Holograma bakarak "Kaldır" diyelim.</span><span class="sxs-lookup"><span data-stu-id="f51c8-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="f51c8-200">Ardından hologramı yeniden açın ve yeni bir konuma yer açın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="f51c8-201">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="f51c8-202">Hologramlar duvarın diğer tarafında görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="f51c8-203">Duvara çok yakınsanız veya HoloLens henüz duvarı taramamışsa, bir sonraki odada yer alan hologramları görebilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="f51c8-204">Duvarı taramak için duvardan bir ile üç metre arasında durur ve duvara bakar.</span><span class="sxs-lookup"><span data-stu-id="f51c8-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="f51c8-205">HoloLens duvarı taramaya çalıştığında, duvarın yakınındaki siyah veya yansıtıcı bir nesne (örneğin, siyah bir buzdolabı veya çelik buzdolabı) sorunlara neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="f51c8-206">Böyle bir nesne varsa duvarın diğer tarafını tarayın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="f51c8-207">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="f51c8-208">Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="f51c8-209">Duvara yer alan hologram genellikle duvardan bir inç uzakta gibi görünür.</span><span class="sxs-lookup"><span data-stu-id="f51c8-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="f51c8-210">Daha uzakta görünüyorsa aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="f51c8-211">Bir duvara hologramı yerken duvardan bir ile üç metre arasında durur ve duvarın doğrudan üzerinde durur.</span><span class="sxs-lookup"><span data-stu-id="f51c8-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="f51c8-212">Eşleme ağı grafiğini ortaya çıkarmak için duvara havadan dokunun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="f51c8-213">Örgün duvarla hizalı olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="f51c8-214">Yoksa hologramı kaldırın, duvarı yeniden deneyin ve yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="f51c8-215">Sorun devam ederse Ayarlama uygulamasını çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="f51c8-216">Bunu Ayarlar Sistem Yardımcı **Programları**  >  **sayfasında**  >  **bulabilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="f51c8-217">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="f51c8-218">Uygulamalar, taşımadan sonra çok yakın görünüyor</span><span class="sxs-lookup"><span data-stu-id="f51c8-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="f51c8-219">HoloLens'in alanı farklı açılardan taraması için uygulamayı yerleştirmiş olduğu alanı incelemeyi deneyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="f51c8-220">[Cihaz mengenenizin temizlenmesi](hololens1-hardware.md#care-and-cleaning) de yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="f51c8-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="f51c8-221">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="f51c8-222">Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme</span><span class="sxs-lookup"><span data-stu-id="f51c8-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="f51c8-223">Lütfen sorunun Karma Gerçeklik Yakalama [videosunu](holographic-photos-and-videos.md#capture-a-mixed-reality-video) ve bir videosunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="f51c8-224">Bu video daha sonra dosya Geri Bildirim Merkezi dosya olarak karşıya yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="f51c8-225">Geri bildirim için  Ayarlar uygulaması -> Gizlilik Tanılaması & telemetrisini etkinleştirin ve İsteğe bağlı tanılama verileri altında iki durumlu düğmenin Açık olarak ayarlanmış olduğundan  ->   emin **olun** </span><span class="sxs-lookup"><span data-stu-id="f51c8-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="f51c8-226">En son [Windows Holographic OS'ye (20H2](hololens-release-notes.md#windows-holographic-version-20h2)veya daha yüksek) güncelleştirerek en son hologram ölçek ve kararlılık düzeltmelerini elde etmek.</span><span class="sxs-lookup"><span data-stu-id="f51c8-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="f51c8-227">Güncelleştirdikten sonra aşağıdaki işlemleri gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="f51c8-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="f51c8-228">Ayarlar uygulaması **->** **System** Hologramları -> tüm Hologramları kaldır'ı seçerek  ->   **tüm Hologramları** kaldır'ı seçin ve yeni bir haritayla çalışmaya başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="f51c8-229">HoloLens'i takarak ve odanızı dolaşarak ve uzaydaki tüm alanlara ve yüzeylere bakarak yeni bir alan haritası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="f51c8-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="f51c8-230">Bunu 2-3 dakika için yap.</span><span class="sxs-lookup"><span data-stu-id="f51c8-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="f51c8-231">IPD ayarlaması gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="f51c8-231">Perform IPD calibration.</span></span> <span data-ttu-id="f51c8-232">Ayarlar Sistem **Yardımcı**  >    >  **Programları'nı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="f51c8-233">**Ayarlama'nın** altında Açık **Ayar'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="f51c8-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="f51c8-234">Senaryoyu yeniden test eder ve hala devam eder mi diye bakın.</span><span class="sxs-lookup"><span data-stu-id="f51c8-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="f51c8-235">Güncelleştirme sorunu çözene kadar sorunu [Geri Bildirim Merkezi.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="f51c8-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="f51c8-236">Geri bildirimi doldurduktan sonra, destek **ekibiyle** iletişime geçerek gönderebilirsiniz. Paylaş düğmesini kullanarak kolayca paylaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f51c8-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="f51c8-237">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="f51c8-237">Back to list</span></span>](#list)