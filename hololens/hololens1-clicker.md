---
title: HoloLens 'i kullanma
description: Bu makalede,, Click, dolduruluyor ve kurtarma gibi HoloLens Click 'in nasıl kullanılacağı özetlenmektedir.
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 83e5a746b6900c547778c71a0855426563458032
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924069"
---
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="052b6-104">HoloLens (1. gen) Click kullanın</span><span class="sxs-lookup"><span data-stu-id="052b6-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="052b6-105">Click, HoloLens (1. gen) için özel olarak tasarlanmıştır ve hologramlar ile etkileşime geçmek için size başka bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="052b6-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="052b6-106">HoloLens (1. gen) ile birlikte, ayrı bir kutuya gelir.</span><span class="sxs-lookup"><span data-stu-id="052b6-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="052b6-107">Uygulamaları seçmek, kaydırmak, taşımak ve yeniden boyutlandırmak için el hareketleri yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="052b6-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="052b6-108">Donanımı ve eşlemeyi kapatıp</span><span class="sxs-lookup"><span data-stu-id="052b6-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="052b6-109">HoloLens (1. gen) Click, saklamayı kolaylaştırmak için bir Finger döngüsüne sahiptir ve bir gösterge ışığı içerir.</span><span class="sxs-lookup"><span data-stu-id="052b6-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens çi](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="052b6-111">Çi gösterge ışıkları</span><span class="sxs-lookup"><span data-stu-id="052b6-111">Clicker indicator lights</span></span>

<span data-ttu-id="052b6-112">Bu, Click 'teki ışıkların anlamı aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="052b6-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="052b6-113">**Yanıp sönen beyaz**.</span><span class="sxs-lookup"><span data-stu-id="052b6-113">**Blinking white**.</span></span> <span data-ttu-id="052b6-114">Click, eşleştirme modundadır.</span><span class="sxs-lookup"><span data-stu-id="052b6-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="052b6-115">**Hızlı yanıp sönen beyaz**.</span><span class="sxs-lookup"><span data-stu-id="052b6-115">**Fast-blinking white**.</span></span> <span data-ttu-id="052b6-116">Eşleştirme başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="052b6-116">Pairing was successful.</span></span>
- <span data-ttu-id="052b6-117">**Düz beyaz**.</span><span class="sxs-lookup"><span data-stu-id="052b6-117">**Solid white**.</span></span> <span data-ttu-id="052b6-118">Bu işlemi doldurma.</span><span class="sxs-lookup"><span data-stu-id="052b6-118">The clicker is charging.</span></span>
- <span data-ttu-id="052b6-119">**Yanıp sönen** bir bu.</span><span class="sxs-lookup"><span data-stu-id="052b6-119">**Blinking amber**.</span></span> <span data-ttu-id="052b6-120">Pil düşüktür.</span><span class="sxs-lookup"><span data-stu-id="052b6-120">The battery is low.</span></span>
- <span data-ttu-id="052b6-121">**Solid** bir.</span><span class="sxs-lookup"><span data-stu-id="052b6-121">**Solid amber**.</span></span> <span data-ttu-id="052b6-122">Click bir hatayla karşılaştı ve yeniden başlatmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="052b6-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="052b6-123">Eşleştirme düğmesine basıldığında 15 saniye boyunca tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="052b6-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="052b6-124">Holomerceği ile (1. Genel) Click 'i eşleştirin</span><span class="sxs-lookup"><span data-stu-id="052b6-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="052b6-125">**Başlat**' a gitmek için Bloom hareketini kullanın, ardından **Ayarlar**  >  **cihazlar** ' ı seçin ve Bluetooth 'un açık olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="052b6-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="052b6-126">Bu durumda, durum ışığı yanıp sönene kadar eşleştirme düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="052b6-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="052b6-127">Eşleştirme ekranında, Click öğesini seçin   >  .</span><span class="sxs-lookup"><span data-stu-id="052b6-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="052b6-128">Click 'i ücretlendirin</span><span class="sxs-lookup"><span data-stu-id="052b6-128">Charge the clicker</span></span>

<span data-ttu-id="052b6-129">Click pili azaldığında, pil göstergesi, bu işlem için,</span><span class="sxs-lookup"><span data-stu-id="052b6-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="052b6-130">Cihazı ücretlendirmeden mikro USB kablosunu USB güç kaynağına takın.</span><span class="sxs-lookup"><span data-stu-id="052b6-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="052b6-131">HoloLens ile bir Click kullanın (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="052b6-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="052b6-132">Click 'i beklet</span><span class="sxs-lookup"><span data-stu-id="052b6-132">Hold the clicker</span></span>

<span data-ttu-id="052b6-133">Click 'e koymak için, mikro USB bağlantı noktasının bilek 'nize doğru olması için döngüyü halkaya da orta parmağınızla kaydırın.</span><span class="sxs-lookup"><span data-stu-id="052b6-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="052b6-134">Parmak izi girintiye geri kalanını.</span><span class="sxs-lookup"><span data-stu-id="052b6-134">Rest your thumb in the indentation.</span></span>

![Click 'i tutma](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="052b6-136">Click hareketleri</span><span class="sxs-lookup"><span data-stu-id="052b6-136">Clicker gestures</span></span>

<span data-ttu-id="052b6-137">Merçi hareketleri, HoloLens el hareketleri için kullanılan daha büyük taşımaları değil küçük bilek dönüşlerdir.</span><span class="sxs-lookup"><span data-stu-id="052b6-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="052b6-138">HoloLens, [hareket çerçevesinin](hololens1-basic-usage.md)dışında olsa bile hareketlerinizi ve tıklamalarını algılar. böylece, bu işlemi sizin için en rahat olan konumda tutabilmenizi sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="052b6-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="052b6-139">Öğesini **seçin**.</span><span class="sxs-lookup"><span data-stu-id="052b6-139">**Select**.</span></span> <span data-ttu-id="052b6-140">Bir hologram, düğme ya da başka bir öğe seçmek için, bunu seçin ve ardından öğesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="052b6-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="052b6-141">**Tıklayın ve basılı tutun**.</span><span class="sxs-lookup"><span data-stu-id="052b6-141">**Click and hold**.</span></span> <span data-ttu-id="052b6-142">Bir hologram taşıma veya yeniden boyutlandırma gibi, dokunmanıza ve tutmaya yönelik aynı şeylerden bazılarını yapmak için düğme üzerindeki parmak izi ' ne tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="052b6-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="052b6-143">**Kaydırın**.</span><span class="sxs-lookup"><span data-stu-id="052b6-143">**Scroll**.</span></span> <span data-ttu-id="052b6-144">Uygulama çubuğunda, **kaydırma aracı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="052b6-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="052b6-145">Tıklayın ve basılı tutun, ardından solu aşağı, aşağı, sola veya sağa döndürün.</span><span class="sxs-lookup"><span data-stu-id="052b6-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="052b6-146">Daha hızlı kaydırmak için, kaydırma aracının merkezinden uzaklaştırın.</span><span class="sxs-lookup"><span data-stu-id="052b6-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="052b6-147">**Yakınlaştırın**.</span><span class="sxs-lookup"><span data-stu-id="052b6-147">**Zoom**.</span></span> <span data-ttu-id="052b6-148">Uygulama çubuğunda **Yakınlaştırma aracı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="052b6-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="052b6-149">Düğmesine tıklayın ve basılı tutun, ardından aşağı doğru yakınlaştırmak veya uzaklaştırmak için aşağı döndürün.</span><span class="sxs-lookup"><span data-stu-id="052b6-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="052b6-150">Microsoft Edge 'i kullanarak yakınlaştırmak veya uzaklaştırmak için bir sayfada Gaze ve çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="052b6-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="im-having-problems-using-the-hololens-clicker"></a><span data-ttu-id="052b6-151">HoloLens 'i kullanarak sorun yaşıyorum</span><span class="sxs-lookup"><span data-stu-id="052b6-151">I'm having problems using the HoloLens clicker</span></span>

<span data-ttu-id="052b6-152">Hologragram seçme, kaydırma, taşıma ve yeniden boyutlandırma için [Click](hololens1-clicker.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="052b6-152">Use the [clicker](hololens1-clicker.md) to select, scroll, move, and resize holograms.</span></span> <span data-ttu-id="052b6-153">Ayrı uygulamalar, ek Click hareketlerini destekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="052b6-153">Individual apps may support additional clicker gestures.</span></span>

<span data-ttu-id="052b6-154">Click ile ilgili sorun yaşıyorsanız, bunun ücretlendirildiği ve HoloLens ile eşleştirilmiş olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="052b6-154">If you're having trouble using the clicker, make sure that it's charged and paired with your HoloLens.</span></span> <span data-ttu-id="052b6-155">Pil düşükse, gösterge açık yanıp sönme.</span><span class="sxs-lookup"><span data-stu-id="052b6-155">If the battery is low, the indicator light blinks amber.</span></span> <span data-ttu-id="052b6-156">Click 'in eşleştirildiğini doğrulamak için, **Ayarlar**  >  **cihazlar** ' a gidin ve burada görünür olup olmadığını görün.</span><span class="sxs-lookup"><span data-stu-id="052b6-156">To verify that the clicker is paired, go to **Settings** > **Devices** and see if it shows up there.</span></span> <span data-ttu-id="052b6-157">Daha fazla bilgi için, bkz. [Click 'ı eşleştirme](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="052b6-157">For more information, see [Pair the clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="052b6-158">Click 'e ücretlendirildikten ve eşlenmeye devam ediyorsanız ve sorun yaşıyorsanız, ana düğmeyi ve eşleştirme düğmesini 15 saniye basılı tutarak sıfırlayın.</span><span class="sxs-lookup"><span data-stu-id="052b6-158">If the clicker is charged and paired and you're still having problems, reset it by holding down the main button and the pairing button for 15 seconds.</span></span> <span data-ttu-id="052b6-159">Ardından, bir daha sonra Holomeryi bir kez daha eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="052b6-159">Then pair the clicker with your HoloLens again.</span></span>

<span data-ttu-id="052b6-160">Click 'in sıfırlanması yardım vermezse, bkz. [HoloLens 'ı yeniden başlatma veya kurtarma](hololens1-clicker.md#restart-or-recover-the-clicker).</span><span class="sxs-lookup"><span data-stu-id="052b6-160">If resetting the clicker doesn't help, see [Restart or recover the HoloLens clicker](hololens1-clicker.md#restart-or-recover-the-clicker).</span></span>
## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="052b6-161">Click 'i yeniden başlatın veya kurtarın</span><span class="sxs-lookup"><span data-stu-id="052b6-161">Restart or recover the clicker</span></span>

<span data-ttu-id="052b6-162">HoloLens, yanıt vermemeye başlarsa veya düzgün çalışmıyorsa deneyebileceğiniz bazı şeyler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="052b6-162">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="052b6-163">Click 'i yeniden başlatın</span><span class="sxs-lookup"><span data-stu-id="052b6-163">Restart the clicker</span></span>

<span data-ttu-id="052b6-164">Eşleştirme düğmesini basılı tutmak için bir kalemin ucunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="052b6-164">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="052b6-165">Aynı zamanda, 15 saniye boyunca Click düğmesine tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="052b6-165">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="052b6-166">Click, HoloLens ile zaten eşlendikten sonra yeniden başlatıldıktan sonra eşleştirilmiş olarak kalır.</span><span class="sxs-lookup"><span data-stu-id="052b6-166">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="052b6-167">Click 'i açıp yeniden başlatmazsanız, HoloLens Charger kullanarak ücretlendirme yapmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="052b6-167">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="052b6-168">Pil çok düşükse, beyaz gösterge ışığının açık olması birkaç dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="052b6-168">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="052b6-169">Click 'i yeniden eşleştirin</span><span class="sxs-lookup"><span data-stu-id="052b6-169">Re-pair the clicker</span></span>

<span data-ttu-id="052b6-170">**Ayar**  >  **cihazları** ' nı seçin ve Click ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="052b6-170">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="052b6-171">**Kaldır**' ı seçin, birkaç saniye bekleyin ve sonra yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="052b6-171">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="052b6-172">Click 'i kurtarma</span><span class="sxs-lookup"><span data-stu-id="052b6-172">Recover the clicker</span></span>

<span data-ttu-id="052b6-173">Yeniden başlatma ve yeniden eşleştirmeniz sorunu gidermezse, Windows cihaz kurtarma aracı bunu kurtarmanıza yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="052b6-173">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="052b6-174">Kurtarma işlemi biraz zaman alabilir ve bu, Click yazılımının en son sürümünü yükler.</span><span class="sxs-lookup"><span data-stu-id="052b6-174">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="052b6-175">Aracı kullanmak için, en az 4 GB boş depolama alanı olan Windows 10 veya sonraki bir sürümünü çalıştıran bir bilgisayara ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="052b6-175">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="052b6-176">Click 'i kurtarmak için:</span><span class="sxs-lookup"><span data-stu-id="052b6-176">To recover the clicker:</span></span>

1. <span data-ttu-id="052b6-177">[Windows cihaz kurtarma aracı](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) 'nı bilgisayarınıza indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="052b6-177">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="052b6-178">HoloLens 'nizle birlikte gelen mikro USB kablosunu kullanarak, bilgisayarınızı bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="052b6-178">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="052b6-179">Windows cihaz kurtarma aracı 'nı çalıştırın ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="052b6-179">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="052b6-180">Click otomatik olarak algılanmazsa **cihazımın algılanmadığını** seçin ve cihazınızı kurtarma moduna almak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="052b6-180">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

