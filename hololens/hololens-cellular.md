---
title: Hücresel ve 5G'ye bağlanma
description: HoloLens karma gerçeklik cihazlarından hücresel ağlara bağlanma.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380159"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="5415b-103">Hücresel ve 5G'ye bağlanma</span><span class="sxs-lookup"><span data-stu-id="5415b-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="5415b-104">HoloLens 2, hücresel ve 5G ağlarına bağlanmak için iki yöntemi destekler:</span><span class="sxs-lookup"><span data-stu-id="5415b-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="5415b-105">Hücresel cihaz tarafından sağlanan ve yaygın olarak "Etkin Nokta" olarak adlandırılan geçici bir WiFi ağı</span><span class="sxs-lookup"><span data-stu-id="5415b-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="5415b-106">USB-C bağlantısı olan cihazlar için sınırlı destek</span><span class="sxs-lookup"><span data-stu-id="5415b-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="5415b-107">Etkin Nokta (WiFi)</span><span class="sxs-lookup"><span data-stu-id="5415b-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="5415b-108">Hücresel bağlantı ihtiyaçlarının çoğu etkin noktayla karşı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5415b-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="5415b-109">HoloLens 2 WiFi, en yaygın kullanım örnekleri için gereken bant genişliği ve gecikme süresi gereksinimlerini sağlayabiliyor olan 802.11ac'ı destekler.</span><span class="sxs-lookup"><span data-stu-id="5415b-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="5415b-110">WiFi ayrıca kablo bağlantısızdır ve en fazla hücresel cihazla uyumluluk sunar.</span><span class="sxs-lookup"><span data-stu-id="5415b-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="5415b-111">Etkin Nokta'ya bağlanma</span><span class="sxs-lookup"><span data-stu-id="5415b-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="5415b-112">Etkin nokta modunu etkinleştirme hakkında cihazınızın el kitabına başvurun.</span><span class="sxs-lookup"><span data-stu-id="5415b-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="5415b-113">Etkin nokta modunu etkinleştirerek ağ için bir ad ve bilinen bir parola girin.</span><span class="sxs-lookup"><span data-stu-id="5415b-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="5415b-114">HoloLens 2 Ağ ayarlarında, 2. adımda oluşturulan WiFi ağına gidin ve ağa katılın.</span><span class="sxs-lookup"><span data-stu-id="5415b-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="5415b-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="5415b-115">USB-C Tethering</span></span>

<span data-ttu-id="5415b-116">USB-C bağlantısı, ihtiyacı olan gelişmiş iş yükleri için daha düşük gecikme süresi sağlar.</span><span class="sxs-lookup"><span data-stu-id="5415b-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="5415b-117">[Azure Remote Rendering,](https://azure.microsoft.com/services/remote-rendering)örneğin, tethering'den yararlanabilir.</span><span class="sxs-lookup"><span data-stu-id="5415b-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="5415b-118">Hücresel cihazla HoloLens arasında kablo bağlantısı olması ve sınırlı sayıda cihazla kablo bağlantısına ihtiyaç olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="5415b-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="5415b-119">USB-C uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="5415b-119">USB-C compatibility</span></span>

<span data-ttu-id="5415b-120">Kendilerini Ethernet uyarıcı olarak sunan sınırlı sayıda cihaz, Windows Holographic sürüm 2004 ve sonrası ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5415b-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="5415b-121">Kendilerini ethernet bağdaştırıcısı olarak sun olmayan cihazların genel Microsoft [RNDIS sürücüsünü desteklemesi](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) gerekir.</span><span class="sxs-lookup"><span data-stu-id="5415b-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="5415b-122">Ancak bu cihazların yalnızca sınırlı bir sayısı HoloLens 2 ile uyumludur.</span><span class="sxs-lookup"><span data-stu-id="5415b-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="5415b-123">Genel Microsoft RNDIS sürücüsünü destekleyip destekleme konusunda ayrıntılı bilgi için lütfen cihazınızın üreticisine başvurun.</span><span class="sxs-lookup"><span data-stu-id="5415b-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="5415b-124">RNDIS uyumlu olmayan veya bir sürücü ya da uygulamanın yüklü olması gereken cihazlar desteklanmaz.</span><span class="sxs-lookup"><span data-stu-id="5415b-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="5415b-125">Microsoft uyumlu cihazların listesini korumasa da, burada konuyla ilgili bir topluluk [tartışması vardır.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="5415b-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="5415b-126">Bağlı bir cihaza bağlanma</span><span class="sxs-lookup"><span data-stu-id="5415b-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="5415b-127">USB üzerinden veri paylaşımını etkinleştirme hakkında cihazınızın kılavuzuna başvurun.</span><span class="sxs-lookup"><span data-stu-id="5415b-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="5415b-128">Bu ayar genellikle "USB Paylaşımı", "Veri Paylaşımı" veya "USB Modem" olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="5415b-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="5415b-129">USB üzerinden veri paylaşımını etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="5415b-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="5415b-130">Cihazınızı HoloLens USB-C bağlantı noktasına bağlayın.</span><span class="sxs-lookup"><span data-stu-id="5415b-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="5415b-131">HoloLens 2 Ağ ayarlarında cihaz otomatik olarak Ethernet bağlantısı olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="5415b-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
