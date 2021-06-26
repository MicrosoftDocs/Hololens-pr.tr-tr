---
title: Bluetooth ve USB-C cihazlarına bağlanma
description: Kullanmaya başlayın HoloLens karma gerçeklik cihazlarından Bluetooth ve USB-C cihazlarına ve donatılarına bağlanmanızı sağlar.
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
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924188"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="81c68-103">Bluetooth ve USB-C cihazlarına bağlanma</span><span class="sxs-lookup"><span data-stu-id="81c68-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="81c68-104">Bluetooth cihazlarını eşleştirme</span><span class="sxs-lookup"><span data-stu-id="81c68-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="81c68-105">HoloLens 2, aşağıdaki Bluetooth cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="81c68-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="81c68-106">[SİYAD:](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="81c68-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="81c68-107">Fare</span><span class="sxs-lookup"><span data-stu-id="81c68-107">Mouse</span></span>
    - <span data-ttu-id="81c68-108">Klavye</span><span class="sxs-lookup"><span data-stu-id="81c68-108">Keyboard</span></span>
- <span data-ttu-id="81c68-109">Ses çıkışı (A2DP) cihazları</span><span class="sxs-lookup"><span data-stu-id="81c68-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="81c68-110">HoloLens 2 aşağıdaki Bluetooth API'lerini destekler:</span><span class="sxs-lookup"><span data-stu-id="81c68-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="81c68-111">GATT [Sunucusu](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) ve [İstemcisi](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="81c68-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="81c68-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="81c68-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="81c68-113">ASLıNDA WINDOWS ve GATT cihazlarını kullanmak için Microsoft Store yardımcı uygulamaları yüklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="81c68-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="81c68-114">HoloLens (1. nesil), aşağıdaki Bluetooth cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="81c68-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="81c68-115">Fare</span><span class="sxs-lookup"><span data-stu-id="81c68-115">Mouse</span></span>
- <span data-ttu-id="81c68-116">Klavye</span><span class="sxs-lookup"><span data-stu-id="81c68-116">Keyboard</span></span>
- [<span data-ttu-id="81c68-117">HoloLens (1. nesil) tıklama</span><span class="sxs-lookup"><span data-stu-id="81c68-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="81c68-118">HoloLens ayarlarında konuşmacılar, mikrofonlu telefonlar, akıllı telefonlar ve oyun paneli gibi diğer Bluetooth cihaz türleri listelenmiş olabilir.</span><span class="sxs-lookup"><span data-stu-id="81c68-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="81c68-119">Ancak bu cihazlar HoloLens'te (1. nesil) desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="81c68-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="81c68-120">Daha fazla bilgi için [bkz. HoloLens Ayarları](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)cihazları kullanılabilir olarak listeler, ancak cihazlar çalışmıyor.</span><span class="sxs-lookup"><span data-stu-id="81c68-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="81c68-121">Bluetooth klavyesini veya faresini eşleştirme</span><span class="sxs-lookup"><span data-stu-id="81c68-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="81c68-122">Klavyenizi veya farenizi açarak keşfedilebilir hale sürükleyin.</span><span class="sxs-lookup"><span data-stu-id="81c68-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="81c68-123">Cihazın bulunabilir hale nasıl geleceklerini öğrenmek için cihazla ilgili bilgileri (veya belgelerini) inceleyin veya üreticinin web sitesini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="81c68-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="81c68-124">Başlat 'a gidip Ayarlar'ı seçmek için bloom hareketini (HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) **kullanın.**</span><span class="sxs-lookup"><span data-stu-id="81c68-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="81c68-125">**Cihazlar'ı** seçin ve Bluetooth'un açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="81c68-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="81c68-126">Cihaz adını gördüğünüzde **Eşleştir'i seçin** ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="81c68-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="81c68-127">Bluetooth'u devre dışı bırakma</span><span class="sxs-lookup"><span data-stu-id="81c68-127">Disable Bluetooth</span></span>

<span data-ttu-id="81c68-128">Bu yordam, Bluetooth radyos un RF bileşenlerini devre dışı bırakarak tüm Bluetooth işlevlerini Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="81c68-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="81c68-129">Başlat 'a gitmek için bloom hareketini (HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) kullanın ve ardından Ayarlar **Cihazları'ı**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="81c68-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="81c68-130">Bluetooth kaydırıcı anahtarını **Kapalı** **konuma** getirin.</span><span class="sxs-lookup"><span data-stu-id="81c68-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="81c68-131">HoloLens 2: USB-C cihazlarını bağlama</span><span class="sxs-lookup"><span data-stu-id="81c68-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="81c68-132">HoloLens 2, aşağıdaki USB-C cihaz sınıflarını destekler:</span><span class="sxs-lookup"><span data-stu-id="81c68-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="81c68-133">Yığın depolama cihazları (örneğin, parmak sürücüleri)</span><span class="sxs-lookup"><span data-stu-id="81c68-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="81c68-134">Ethernet bağdaştırıcıları (ethernet artı ücretlendirme dahil)</span><span class="sxs-lookup"><span data-stu-id="81c68-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="81c68-135">USB-C-3,5mm dijital ses bağdaştırıcıları</span><span class="sxs-lookup"><span data-stu-id="81c68-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="81c68-136">USB-C dijital ses başlığı (mikrofonlu bağdaştırıcılar ve ücretlendirme dahil)</span><span class="sxs-lookup"><span data-stu-id="81c68-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="81c68-137">USB-C Dış Mikrofonlar ([Windows Holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha yüksek)</span><span class="sxs-lookup"><span data-stu-id="81c68-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="81c68-138">Kablolu fare</span><span class="sxs-lookup"><span data-stu-id="81c68-138">Wired mouse</span></span>
- <span data-ttu-id="81c68-139">Kablolu klavye</span><span class="sxs-lookup"><span data-stu-id="81c68-139">Wired keyboard</span></span>
- <span data-ttu-id="81c68-140">PD hub'larını karma (USB A artı PD ücretlendirme)</span><span class="sxs-lookup"><span data-stu-id="81c68-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="81c68-141">Müşteri geri bildirimlerine yanıt olarak USB-C aracılığıyla doğrudan HoloLens'e bağlı hücresel bağlantı için sınırlı destek sağladık.</span><span class="sxs-lookup"><span data-stu-id="81c68-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="81c68-142">Daha [fazla bilgi için bkz. Hücresel ve 5G'ye](hololens-cellular.md) bağlanma.</span><span class="sxs-lookup"><span data-stu-id="81c68-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="81c68-143">USB-C Dış Mikrofon Desteği</span><span class="sxs-lookup"><span data-stu-id="81c68-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81c68-144">BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.**</span><span class="sxs-lookup"><span data-stu-id="81c68-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="81c68-145">Kullanıcılar bir USB-C kulaklık kümesine takılıyken, mikrofonlu cihazın sesinin otomatik olarak mikrofonlara yeniden yönlendirilmesine neden olduğunu gözlemler ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazlarından yüksek önceliklendirmektedir.</span><span class="sxs-lookup"><span data-stu-id="81c68-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="81c68-146">**USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**</span><span class="sxs-lookup"><span data-stu-id="81c68-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="81c68-147">Dış mikrofonlar, Windows Holographic sürüm [21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha önceki derlemelerde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="81c68-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="81c68-148">Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="81c68-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="81c68-149">USB-C mikrofonları arama, kayıt vb. için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="81c68-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="81c68-150">Ayarlar uygulamasını **açın** ve Sistem **Sesi'ne**  >  **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="81c68-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Ses Ayarları](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="81c68-152">Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="81c68-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="81c68-153">Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.**</span><span class="sxs-lookup"><span data-stu-id="81c68-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="81c68-154">**Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.</span><span class="sxs-lookup"><span data-stu-id="81c68-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="81c68-155">İletişim **Varsayılanı'nın** seçimi, dış mikrofonun Remote Assist ve diğer iletişim uygulamaları için kullanılamayacak, ancak HoloLens mikrofon dizisi diğer görevler için hala kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="81c68-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlama](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="81c68-158">Bluetooth mikrofon desteği ne olacak?</span><span class="sxs-lookup"><span data-stu-id="81c68-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="81c68-159">Ne yazık ki, HoloLens 2'de Bluetooth mikrofonları şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="81c68-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="81c68-160">USB-C Hub'ları</span><span class="sxs-lookup"><span data-stu-id="81c68-160">USB-C Hubs</span></span>

<span data-ttu-id="81c68-161">Bazı kullanıcıların aynı anda birden çok cihaza bağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="81c68-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="81c68-162">[USB-C](#usb-c-external-microphone-support) mikrofonunu başka bir bağlı cihazla birlikte kullanmak isteyen kullanıcılar için, USB-C hub'ları müşterinin ihtiyaçlarına uygun olabilir.</span><span class="sxs-lookup"><span data-stu-id="81c68-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="81c68-163">Microsoft bu cihazları test edilmemiştir ve herhangi bir marka önerilmez.</span><span class="sxs-lookup"><span data-stu-id="81c68-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="81c68-164">**USB-C hub'ı ve bağlı cihazlar için gereksinimler:**</span><span class="sxs-lookup"><span data-stu-id="81c68-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="81c68-165">Bağlı cihazların bir sürücünün yüklü olması gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="81c68-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="81c68-166">Bağlı tüm cihazların toplam güç çekimi 4,5 Watt'ın altında olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="81c68-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="81c68-167">Miracast'e bağlanma</span><span class="sxs-lookup"><span data-stu-id="81c68-167">Connect to Miracast</span></span>

<span data-ttu-id="81c68-168">Miracast'i kullanmak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="81c68-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="81c68-169">Aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="81c68-169">Do one of the following:</span></span>  

   - <span data-ttu-id="81c68-170">Başlat **menüsünü** açın ve Görüntü **simgesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="81c68-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="81c68-171">Başlat menüsüne bakarken "Bağlan" **diyelim.**</span><span class="sxs-lookup"><span data-stu-id="81c68-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="81c68-172">Görüntülenen cihaz listesinde kullanılabilir bir cihaz seçin.</span><span class="sxs-lookup"><span data-stu-id="81c68-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="81c68-173">Eşleştirmeyi tamamlar ve projeye başlar.</span><span class="sxs-lookup"><span data-stu-id="81c68-173">Complete the pairing to begin projecting.</span></span>
