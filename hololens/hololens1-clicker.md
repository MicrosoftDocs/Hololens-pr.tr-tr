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
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379159"
---
# <a name="use-the-hololens-1st-gen-clicker"></a><span data-ttu-id="4bde0-104">HoloLens (1. gen) Click kullanın</span><span class="sxs-lookup"><span data-stu-id="4bde0-104">Use the HoloLens (1st gen) clicker</span></span>

<span data-ttu-id="4bde0-105">Click, HoloLens (1. gen) için özel olarak tasarlanmıştır ve hologramlar ile etkileşime geçmek için size başka bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="4bde0-105">The clicker was designed specifically for HoloLens (1st gen) and gives you another way to interact with holograms.</span></span> <span data-ttu-id="4bde0-106">HoloLens (1. gen) ile birlikte, ayrı bir kutuya gelir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-106">It comes with HoloLens (1st gen), in a separate box.</span></span>

<span data-ttu-id="4bde0-107">Uygulamaları seçmek, kaydırmak, taşımak ve yeniden boyutlandırmak için el hareketleri yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-107">Use it in place of hand gestures to select, scroll, move, and resize apps.</span></span>

## <a name="clicker-hardware-and-pairing"></a><span data-ttu-id="4bde0-108">Donanımı ve eşlemeyi kapatıp</span><span class="sxs-lookup"><span data-stu-id="4bde0-108">Clicker hardware and pairing</span></span>

<span data-ttu-id="4bde0-109">HoloLens (1. gen) Click, saklamayı kolaylaştırmak için bir Finger döngüsüne sahiptir ve bir gösterge ışığı içerir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-109">The HoloLens (1st gen) clicker has a finger loop to make it easier to hold, and an indicator light.</span></span>

![HoloLens çi](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a><span data-ttu-id="4bde0-111">Çi gösterge ışıkları</span><span class="sxs-lookup"><span data-stu-id="4bde0-111">Clicker indicator lights</span></span>

<span data-ttu-id="4bde0-112">Bu, Click 'teki ışıkların anlamı aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-112">Here's what the lights on the clicker mean.</span></span>

- <span data-ttu-id="4bde0-113">**Yanıp sönen beyaz**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-113">**Blinking white**.</span></span> <span data-ttu-id="4bde0-114">Click, eşleştirme modundadır.</span><span class="sxs-lookup"><span data-stu-id="4bde0-114">The clicker is in pairing mode.</span></span>
- <span data-ttu-id="4bde0-115">**Hızlı yanıp sönen beyaz**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-115">**Fast-blinking white**.</span></span> <span data-ttu-id="4bde0-116">Eşleştirme başarılı oldu.</span><span class="sxs-lookup"><span data-stu-id="4bde0-116">Pairing was successful.</span></span>
- <span data-ttu-id="4bde0-117">**Düz beyaz**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-117">**Solid white**.</span></span> <span data-ttu-id="4bde0-118">Bu işlemi doldurma.</span><span class="sxs-lookup"><span data-stu-id="4bde0-118">The clicker is charging.</span></span>
- <span data-ttu-id="4bde0-119">**Yanıp sönen** bir bu.</span><span class="sxs-lookup"><span data-stu-id="4bde0-119">**Blinking amber**.</span></span> <span data-ttu-id="4bde0-120">Pil düşüktür.</span><span class="sxs-lookup"><span data-stu-id="4bde0-120">The battery is low.</span></span>
- <span data-ttu-id="4bde0-121">**Solid** bir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-121">**Solid amber**.</span></span> <span data-ttu-id="4bde0-122">Click bir hatayla karşılaştı ve yeniden başlatmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-122">The clicker ran into an error and you'll need to restart it.</span></span> <span data-ttu-id="4bde0-123">Eşleştirme düğmesine basıldığında 15 saniye boyunca tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="4bde0-123">While pressing the pairing button, click and hold for 15 seconds.</span></span>

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a><span data-ttu-id="4bde0-124">Holomerceği ile (1. Genel) Click 'i eşleştirin</span><span class="sxs-lookup"><span data-stu-id="4bde0-124">Pair the clicker with your HoloLens (1st gen)</span></span>

1. <span data-ttu-id="4bde0-125">**Başlat**' a gitmek için Bloom hareketini kullanın, ardından **Ayarlar**  >  **cihazlar** ' ı seçin ve Bluetooth 'un açık olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-125">Use the bloom gesture to go to **Start**, then select **Settings** > **Devices** and verify that Bluetooth is on.</span></span>
1. <span data-ttu-id="4bde0-126">Bu durumda, durum ışığı yanıp sönene kadar eşleştirme düğmesine basın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="4bde0-126">On the clicker, press and hold the pairing button until the status light blinks white.</span></span>
1. <span data-ttu-id="4bde0-127">Eşleştirme ekranında, Click öğesini seçin   >  .</span><span class="sxs-lookup"><span data-stu-id="4bde0-127">On the pairing screen, select **Clicker** > **Pair**.</span></span>

### <a name="charge-the-clicker"></a><span data-ttu-id="4bde0-128">Click 'i ücretlendirin</span><span class="sxs-lookup"><span data-stu-id="4bde0-128">Charge the clicker</span></span>

<span data-ttu-id="4bde0-129">Click pili azaldığında, pil göstergesi, bu işlem için,</span><span class="sxs-lookup"><span data-stu-id="4bde0-129">When the clicker battery is low, the battery indicator will blink amber.</span></span> <span data-ttu-id="4bde0-130">Cihazı ücretlendirmeden mikro USB kablosunu USB güç kaynağına takın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-130">Plug the Micro USB cable into a USB power supply to charge the device.</span></span>

## <a name="use-the-clicker-with-hololens-1st-gen"></a><span data-ttu-id="4bde0-131">HoloLens ile bir Click kullanın (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="4bde0-131">Use the clicker with HoloLens (1st gen)</span></span>

### <a name="hold-the-clicker"></a><span data-ttu-id="4bde0-132">Click 'i beklet</span><span class="sxs-lookup"><span data-stu-id="4bde0-132">Hold the clicker</span></span>

<span data-ttu-id="4bde0-133">Click 'e koymak için, mikro USB bağlantı noktasının bilek 'nize doğru olması için döngüyü halkaya da orta parmağınızla kaydırın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-133">To put on the clicker, slide the loop over your ring or middle finger so that the Micro USB port faces toward your wrist.</span></span> <span data-ttu-id="4bde0-134">Parmak izi girintiye geri kalanını.</span><span class="sxs-lookup"><span data-stu-id="4bde0-134">Rest your thumb in the indentation.</span></span>

![Click 'i tutma](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a><span data-ttu-id="4bde0-136">Click hareketleri</span><span class="sxs-lookup"><span data-stu-id="4bde0-136">Clicker gestures</span></span>

<span data-ttu-id="4bde0-137">Merçi hareketleri, HoloLens el hareketleri için kullanılan daha büyük taşımaları değil küçük bilek dönüşlerdir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-137">Clicker gestures are small wrist rotations, not the larger movements used for HoloLens hand gestures.</span></span> <span data-ttu-id="4bde0-138">HoloLens, [hareket çerçevesinin](hololens1-basic-usage.md)dışında olsa bile hareketlerinizi ve tıklamalarını algılar. böylece, bu işlemi sizin için en rahat olan konumda tutabilmenizi sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4bde0-138">And HoloLens recognizes your gestures and clicks even if the clicker is outside the [gesture frame](hololens1-basic-usage.md), so you can hold the clicker in the position that's most comfortable for you.</span></span>

- <span data-ttu-id="4bde0-139">Öğesini **seçin**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-139">**Select**.</span></span> <span data-ttu-id="4bde0-140">Bir hologram, düğme ya da başka bir öğe seçmek için, bunu seçin ve ardından öğesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-140">To select a hologram, button, or other element, gaze at it, then click.</span></span>

- <span data-ttu-id="4bde0-141">**Tıklayın ve basılı tutun**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-141">**Click and hold**.</span></span> <span data-ttu-id="4bde0-142">Bir hologram taşıma veya yeniden boyutlandırma gibi, dokunmanıza ve tutmaya yönelik aynı şeylerden bazılarını yapmak için düğme üzerindeki parmak izi ' ne tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="4bde0-142">Click and hold your thumb down on the button to do some of the same things you would with tap and hold, such as move or resize a hologram.</span></span>

- <span data-ttu-id="4bde0-143">**Kaydırın**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-143">**Scroll**.</span></span> <span data-ttu-id="4bde0-144">Uygulama çubuğunda, **kaydırma aracı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-144">On the app bar, select **Scroll Tool**.</span></span> <span data-ttu-id="4bde0-145">Tıklayın ve basılı tutun, ardından solu aşağı, aşağı, sola veya sağa döndürün.</span><span class="sxs-lookup"><span data-stu-id="4bde0-145">Click and hold, then rotate the clicker up, down, left, or right.</span></span> <span data-ttu-id="4bde0-146">Daha hızlı kaydırmak için, kaydırma aracının merkezinden uzaklaştırın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-146">To scroll faster, move your hand farther from the center of the scroll tool.</span></span>

- <span data-ttu-id="4bde0-147">**Yakınlaştırın**.</span><span class="sxs-lookup"><span data-stu-id="4bde0-147">**Zoom**.</span></span> <span data-ttu-id="4bde0-148">Uygulama çubuğunda **Yakınlaştırma aracı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-148">On the app bar, select **Zoom Tool**.</span></span> <span data-ttu-id="4bde0-149">Düğmesine tıklayın ve basılı tutun, ardından aşağı doğru yakınlaştırmak veya uzaklaştırmak için aşağı döndürün.</span><span class="sxs-lookup"><span data-stu-id="4bde0-149">Click and hold, then rotate the clicker up to zoom in, or down to zoom out.</span></span>

> [!TIP]
> <span data-ttu-id="4bde0-150">Microsoft Edge 'i kullanarak yakınlaştırmak veya uzaklaştırmak için bir sayfada Gaze ve çift tıklayın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-150">To zoom in or out when using Microsoft Edge, gaze at a page and double-click.</span></span>

## <a name="restart-or-recover-the-clicker"></a><span data-ttu-id="4bde0-151">Click 'i yeniden başlatın veya kurtarın</span><span class="sxs-lookup"><span data-stu-id="4bde0-151">Restart or recover the clicker</span></span>

<span data-ttu-id="4bde0-152">HoloLens, yanıt vermemeye başlarsa veya düzgün çalışmıyorsa deneyebileceğiniz bazı şeyler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-152">Here are some things to try if the HoloLens clicker is unresponsive or isn’t working well.</span></span>

### <a name="restart-the-clicker"></a><span data-ttu-id="4bde0-153">Click 'i yeniden başlatın</span><span class="sxs-lookup"><span data-stu-id="4bde0-153">Restart the clicker</span></span>

<span data-ttu-id="4bde0-154">Eşleştirme düğmesini basılı tutmak için bir kalemin ucunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-154">Use the tip of a pen to press and hold the pairing button.</span></span> <span data-ttu-id="4bde0-155">Aynı zamanda, 15 saniye boyunca Click düğmesine tıklayın ve basılı tutun.</span><span class="sxs-lookup"><span data-stu-id="4bde0-155">At the same time, click and hold the clicker for 15 seconds.</span></span> <span data-ttu-id="4bde0-156">Click, HoloLens ile zaten eşlendikten sonra yeniden başlatıldıktan sonra eşleştirilmiş olarak kalır.</span><span class="sxs-lookup"><span data-stu-id="4bde0-156">If the clicker was already paired with your HoloLens, it will stay paired after it restarts.</span></span>

<span data-ttu-id="4bde0-157">Click 'i açıp yeniden başlatmazsanız, HoloLens Charger kullanarak ücretlendirme yapmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-157">If the clicker won't turn on or restart, try charging it by using the HoloLens charger.</span></span> <span data-ttu-id="4bde0-158">Pil çok düşükse, beyaz gösterge ışığının açık olması birkaç dakika sürebilir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-158">If the battery is very low, it might take a few minutes for the white indicator light to turn on.</span></span>

### <a name="re-pair-the-clicker"></a><span data-ttu-id="4bde0-159">Click 'i yeniden eşleştirin</span><span class="sxs-lookup"><span data-stu-id="4bde0-159">Re-pair the clicker</span></span>

<span data-ttu-id="4bde0-160">**Ayar**  >  **cihazları** ' nı seçin ve Click ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-160">Select **Settings** > **Devices** and select the clicker.</span></span> <span data-ttu-id="4bde0-161">**Kaldır**' ı seçin, birkaç saniye bekleyin ve sonra yeniden deneyin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-161">Select **Remove**, wait a few seconds, then pair the clicker again.</span></span>

### <a name="recover-the-clicker"></a><span data-ttu-id="4bde0-162">Click 'i kurtarma</span><span class="sxs-lookup"><span data-stu-id="4bde0-162">Recover the clicker</span></span>

<span data-ttu-id="4bde0-163">Yeniden başlatma ve yeniden eşleştirmeniz sorunu gidermezse, Windows cihaz kurtarma aracı bunu kurtarmanıza yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="4bde0-163">If restarting and re-pairing the clicker don’t fix the problem, the Windows Device Recovery Tool can help you recover it.</span></span> <span data-ttu-id="4bde0-164">Kurtarma işlemi biraz zaman alabilir ve bu, Click yazılımının en son sürümünü yükler.</span><span class="sxs-lookup"><span data-stu-id="4bde0-164">The recovery process may take some time, and it will install the latest version of the clicker software.</span></span> <span data-ttu-id="4bde0-165">Aracı kullanmak için, en az 4 GB boş depolama alanı olan Windows 10 veya sonraki bir sürümünü çalıştıran bir bilgisayara ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="4bde0-165">To use the tool, you’ll need a computer running Windows 10 or later that has at least 4 GB of free storage space.</span></span>

<span data-ttu-id="4bde0-166">Click 'i kurtarmak için:</span><span class="sxs-lookup"><span data-stu-id="4bde0-166">To recover the clicker:</span></span>

1. <span data-ttu-id="4bde0-167">[Windows cihaz kurtarma aracı](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) 'nı bilgisayarınıza indirip yükleyin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-167">Download and install the [Windows Device Recovery Tool](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) on your computer.</span></span>
1. <span data-ttu-id="4bde0-168">HoloLens 'nizle birlikte gelen mikro USB kablosunu kullanarak, bilgisayarınızı bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="4bde0-168">Connect the clicker to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="4bde0-169">Windows cihaz kurtarma aracı 'nı çalıştırın ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-169">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="4bde0-170">Click otomatik olarak algılanmazsa **cihazımın algılanmadığını** seçin ve cihazınızı kurtarma moduna almak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="4bde0-170">If the clicker isn’t automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>
