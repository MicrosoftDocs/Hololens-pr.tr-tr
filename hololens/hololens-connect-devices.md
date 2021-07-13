---
title: Bluetooth ve USB-C cihazlarına Bağlan
description: HoloLens karma gerçeklik cihazlarınızdan Bluetooth ve USB-C cihazlarına ve donatılara bağlanma ile çalışmaya başlayın.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639106"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="653aa-103">Bluetooth ve USB-C cihazlarına Bağlan</span><span class="sxs-lookup"><span data-stu-id="653aa-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="653aa-104">Bluetooth cihazları eşleştirin</span><span class="sxs-lookup"><span data-stu-id="653aa-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="653aa-105">HoloLens 2, aşağıdaki Bluetooth cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="653aa-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="653aa-106">[HID](/windows-hardware/drivers/hid/):</span><span class="sxs-lookup"><span data-stu-id="653aa-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="653aa-107">Fare</span><span class="sxs-lookup"><span data-stu-id="653aa-107">Mouse</span></span>
    - <span data-ttu-id="653aa-108">Klavye</span><span class="sxs-lookup"><span data-stu-id="653aa-108">Keyboard</span></span>
- <span data-ttu-id="653aa-109">Ses çıkışı (A2DP) cihazları</span><span class="sxs-lookup"><span data-stu-id="653aa-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="653aa-110">HoloLens 2 aşağıdaki Bluetooth apı 'lerini destekler:</span><span class="sxs-lookup"><span data-stu-id="653aa-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="653aa-111">GATT [sunucusu](/windows/uwp/devices-sensors/gatt-server) ve [istemcisi](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="653aa-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="653aa-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="653aa-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="653aa-113">hıd ve gatt cihazlarını kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="653aa-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="653aa-114">HoloLens (1. gen), aşağıdaki Bluetooth cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="653aa-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="653aa-115">Fare</span><span class="sxs-lookup"><span data-stu-id="653aa-115">Mouse</span></span>
- <span data-ttu-id="653aa-116">Klavye</span><span class="sxs-lookup"><span data-stu-id="653aa-116">Keyboard</span></span>
- [<span data-ttu-id="653aa-117">HoloLens (1. genel) çi</span><span class="sxs-lookup"><span data-stu-id="653aa-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="653aa-118">hoparlörler, kulaklıklar, akıllı telefonlar ve oyun bölmeleri gibi diğer Bluetooth cihaz türleri HoloLens ayarlarında kullanılabilir olarak listelenebilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="653aa-119">ancak, bu cihazlar HoloLens desteklenmez (1. genel).</span><span class="sxs-lookup"><span data-stu-id="653aa-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="653aa-120">daha fazla bilgi için bkz. [HoloLens Ayarlar cihazları kullanılabilir olarak listeler, ancak cihazlar çalışmıyor](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span><span class="sxs-lookup"><span data-stu-id="653aa-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="653aa-121">Bluetooth klavye veya fareyi eşleştirme</span><span class="sxs-lookup"><span data-stu-id="653aa-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="653aa-122">Klavyenizi veya farenizi açın ve bulunabilir hale getirin.</span><span class="sxs-lookup"><span data-stu-id="653aa-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="653aa-123">Cihazı bulunabilir hale getirme hakkında bilgi edinmek için cihaz (veya belgeleri) hakkındaki bilgileri arayın veya üreticinin Web sitesini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="653aa-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="653aa-124">**başlat**' a gitmek için bloom hareketini (HoloLens (1. gen)) veya başlangıç hareketini (HoloLens 2) kullanın ve **Ayarlar**' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="653aa-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="653aa-125">**cihazlar**' ı seçin ve Bluetooth açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="653aa-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="653aa-126">Cihaz adı ' nı gördüğünüzde, **Eşleştir**' i seçin ve ardından yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="653aa-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="653aa-127">Bluetooth devre dışı bırak</span><span class="sxs-lookup"><span data-stu-id="653aa-127">Disable Bluetooth</span></span>

<span data-ttu-id="653aa-128">bu yordam Bluetooth radyoın RF bileşenlerini kapatır ve Microsoft HoloLens tüm Bluetooth işlevlerini devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="653aa-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="653aa-129">**başlat**' a gitmek için bloom hareketini (HoloLens (1. gen)) veya başlangıç hareketini (HoloLens 2) kullanın ve **Ayarlar**  >  **cihazlar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="653aa-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="653aa-130">**Bluetooth** için kaydırıcı anahtarını **kapalı** konuma taşıyın.</span><span class="sxs-lookup"><span data-stu-id="653aa-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="653aa-131">HoloLens 2: Bağlan USB-C cihazları</span><span class="sxs-lookup"><span data-stu-id="653aa-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="653aa-132">HoloLens 2, aşağıdaki USB-C cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="653aa-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="653aa-133">Yığın depolama cihazları (Thumb sürücüleri gibi)</span><span class="sxs-lookup"><span data-stu-id="653aa-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="653aa-134">Ethernet bağdaştırıcıları (Ethernet Plus dolduruluyor dahil)</span><span class="sxs-lookup"><span data-stu-id="653aa-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="653aa-135">USB-C-3,5 mm dijital ses bağdaştırıcıları</span><span class="sxs-lookup"><span data-stu-id="653aa-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="653aa-136">USB-C Dijital Ses Kulaklıklar (kulaklık bağdaştırıcıları ve şarj etme dahil)</span><span class="sxs-lookup"><span data-stu-id="653aa-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="653aa-137">USB-C dış mikrofonlar ([Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve üzeri)</span><span class="sxs-lookup"><span data-stu-id="653aa-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="653aa-138">Kablolu fare</span><span class="sxs-lookup"><span data-stu-id="653aa-138">Wired mouse</span></span>
- <span data-ttu-id="653aa-139">Kablolu klavye</span><span class="sxs-lookup"><span data-stu-id="653aa-139">Wired keyboard</span></span>
- <span data-ttu-id="653aa-140">Birleşik PD hub 'ları (USB A Plus PD doldurma)</span><span class="sxs-lookup"><span data-stu-id="653aa-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="653aa-141">müşteri geri bildirimlerine yanıt olarak, doğrudan USB-C aracılığıyla HoloLens hücresel bağlantı tethered için sınırlı destek sağlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="653aa-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="653aa-142">daha fazla bilgi için bkz. [hücresel ve 5 g 'ye Bağlan](hololens-cellular.md) .</span><span class="sxs-lookup"><span data-stu-id="653aa-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="653aa-143">USB-C dış mikrofon desteği</span><span class="sxs-lookup"><span data-stu-id="653aa-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="653aa-144">**BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**.</span><span class="sxs-lookup"><span data-stu-id="653aa-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="653aa-145">bir USB-C kulaklık kümesini takarken, kullanıcılar, kulaklık sesinin otomatik olarak kulaklıktan yeniden yönlendirildiğini gözlemleyecek ancak HoloLens OS, iç mikrofon dizisinin diğer herhangi bir giriş cihazını önceliklendirir.</span><span class="sxs-lookup"><span data-stu-id="653aa-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="653aa-146">**Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**</span><span class="sxs-lookup"><span data-stu-id="653aa-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="653aa-147">dış mikrofonlar [Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve üzeri sürümden önceki derlemelerde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="653aa-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="653aa-148">Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="653aa-149">USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="653aa-150">**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.</span><span class="sxs-lookup"><span data-stu-id="653aa-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![ses Ayarlar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="653aa-152">Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.</span><span class="sxs-lookup"><span data-stu-id="653aa-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="653aa-153">Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="653aa-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="653aa-154">**Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="653aa-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="653aa-155">**iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens mıc dizisi diğer görevler için hala kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="653aa-158">Bluetooth mikrofon desteği nedir?</span><span class="sxs-lookup"><span data-stu-id="653aa-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="653aa-159">ne yazık ki Bluetooth mikrofonlar halen HoloLens 2 ' de desteklenmemektedir.</span><span class="sxs-lookup"><span data-stu-id="653aa-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="653aa-160">USB-C hub 'Ları</span><span class="sxs-lookup"><span data-stu-id="653aa-160">USB-C Hubs</span></span>

<span data-ttu-id="653aa-161">Bazı kullanıcıların aynı anda birden çok cihaza bağlanması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="653aa-162">[USB-c mikrofonu](#usb-c-external-microphone-support) başka bir bağlı cihazla birlikte kullanmak isteyen kullanıcılar IÇIN, USB-c hub 'ları müşterinin ihtiyacı olabilir.</span><span class="sxs-lookup"><span data-stu-id="653aa-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="653aa-163">Microsoft bu cihazları test etmemiş ve belirli markaların önermediğimiz için.</span><span class="sxs-lookup"><span data-stu-id="653aa-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="653aa-164">**USB-C hub ve bağlı cihazlar için gereksinimler:**</span><span class="sxs-lookup"><span data-stu-id="653aa-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="653aa-165">Bağlı cihazların bir sürücünün yüklenmesini gerektirmemelidir.</span><span class="sxs-lookup"><span data-stu-id="653aa-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="653aa-166">Tüm bağlı cihazların toplam güç çizimi 4,5 watt 'Tan daha düşük olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="653aa-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="653aa-167">Miracast Bağlan</span><span class="sxs-lookup"><span data-stu-id="653aa-167">Connect to Miracast</span></span>

<span data-ttu-id="653aa-168">Miracast kullanmak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="653aa-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="653aa-169">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="653aa-169">Do one of the following:</span></span>  

   - <span data-ttu-id="653aa-170">**Başlat** menüsünü açın ve **görüntü** simgesini seçin.</span><span class="sxs-lookup"><span data-stu-id="653aa-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="653aa-171">**başlangıç** menüsünde "Bağlan" deyin.</span><span class="sxs-lookup"><span data-stu-id="653aa-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="653aa-172">Görüntülenen cihazların listesinde, kullanılabilir bir cihaz seçin.</span><span class="sxs-lookup"><span data-stu-id="653aa-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="653aa-173">Yansıtma başlamak için eşleştirmeyi doldurun.</span><span class="sxs-lookup"><span data-stu-id="653aa-173">Complete the pairing to begin projecting.</span></span>
