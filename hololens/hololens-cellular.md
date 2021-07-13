---
title: Bağlan hücresel ve 5G'ye
description: Farklı karma gerçeklik cihazlarından hücresel HoloLens bağlanma.
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
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635849"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="7fb24-103">Bağlan hücresel ve 5G'ye</span><span class="sxs-lookup"><span data-stu-id="7fb24-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="7fb24-104">HoloLens 2, hücresel ve 5G ağlarına bağlanmak için iki yöntemi destekler:</span><span class="sxs-lookup"><span data-stu-id="7fb24-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="7fb24-105">Hücresel cihaz tarafından sağlanan ve genellikle "Etkin Nokta" olarak adlandırılan geçici bir WiFi ağı</span><span class="sxs-lookup"><span data-stu-id="7fb24-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="7fb24-106">USB-C bağlantısı olan cihazlar için sınırlı destek</span><span class="sxs-lookup"><span data-stu-id="7fb24-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="7fb24-107">Etkin Nokta (WiFi)</span><span class="sxs-lookup"><span data-stu-id="7fb24-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="7fb24-108">Hücresel bağlantı ihtiyaçlarının çoğu etkin noktayla karşı kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7fb24-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="7fb24-109">HoloLens 2 WiFi, en yaygın kullanım örnekleri için gereken bant genişliği ve gecikme süresi gereksinimlerini sağlayabiliyorsa 802.11ac'ı destekler.</span><span class="sxs-lookup"><span data-stu-id="7fb24-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="7fb24-110">WiFi ayrıca kablo bağlantısızdır ve en fazla hücresel cihazla uyumluluk sunar.</span><span class="sxs-lookup"><span data-stu-id="7fb24-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="7fb24-111">Etkin Nokta'ya bağlanma</span><span class="sxs-lookup"><span data-stu-id="7fb24-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="7fb24-112">Etkin nokta modunu etkinleştirme hakkında cihazınızın el kitabına başvurun.</span><span class="sxs-lookup"><span data-stu-id="7fb24-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="7fb24-113">Etkin nokta modunu etkinleştirerek ağ için bir ad ve bilinen bir parola girin.</span><span class="sxs-lookup"><span data-stu-id="7fb24-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="7fb24-114">2 HoloLens ayarlar sayfasında, 2. adımda oluşturulan WiFi ağına gidin ve buna katılın.</span><span class="sxs-lookup"><span data-stu-id="7fb24-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="7fb24-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="7fb24-115">USB-C Tethering</span></span>

<span data-ttu-id="7fb24-116">USB-C bağlantısı, ihtiyacı olan gelişmiş iş yükleri için daha düşük gecikme süresi sağlar.</span><span class="sxs-lookup"><span data-stu-id="7fb24-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="7fb24-117">[Azure Remote Rendering,](https://azure.microsoft.com/services/remote-rendering)örneğin, tethering'den yararlanabilir.</span><span class="sxs-lookup"><span data-stu-id="7fb24-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="7fb24-118">Kablo bağlantısı için hücresel cihaz ile cihaz arasında bir kablo HoloLens ve kablo bağlantısı sınırlı sayıda cihaz tarafından de desteklemektedir.</span><span class="sxs-lookup"><span data-stu-id="7fb24-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="7fb24-119">USB-C uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="7fb24-119">USB-C compatibility</span></span>

<span data-ttu-id="7fb24-120">Kendilerini Ethernet uyarıcı olarak sunan sınırlı sayıda cihaz, Windows Holographic sürüm 2004 ve sonraki sürümlerle kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="7fb24-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="7fb24-121">Kendilerini ethernet bağdaştırıcısı olarak sun olmayan cihazların genel Microsoft [RNDIS sürücüsünü desteklemesi](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) gerekir.</span><span class="sxs-lookup"><span data-stu-id="7fb24-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="7fb24-122">Ancak, bu cihazların yalnızca sınırlı bir sayısı HoloLens 2 ile uyumludur.</span><span class="sxs-lookup"><span data-stu-id="7fb24-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="7fb24-123">Genel Microsoft RNDIS sürücüsünü destekleyip destekleme konusunda ayrıntılı bilgi için lütfen cihazınızın üreticisine başvurun.</span><span class="sxs-lookup"><span data-stu-id="7fb24-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="7fb24-124">RNDIS uyumlu olmayan veya bir sürücü ya da uygulamanın yüklü olması gereken cihazlar desteklanmaz.</span><span class="sxs-lookup"><span data-stu-id="7fb24-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="7fb24-125">Microsoft uyumlu cihazların listesini korumasa da, burada konuyla ilgili bir topluluk [tartışması vardır.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="7fb24-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="7fb24-126">Bağlı bir cihaza bağlanma</span><span class="sxs-lookup"><span data-stu-id="7fb24-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="7fb24-127">USB üzerinden veri paylaşımını etkinleştirme hakkında cihazınızın kılavuzuna başvurun.</span><span class="sxs-lookup"><span data-stu-id="7fb24-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="7fb24-128">Bu ayar genellikle "USB Paylaşımı", "Veri Paylaşımı" veya "USB Modem" olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="7fb24-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="7fb24-129">USB üzerinden veri paylaşımını etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="7fb24-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="7fb24-130">Bağlan USB-C HoloLens cihazına bağlayın.</span><span class="sxs-lookup"><span data-stu-id="7fb24-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="7fb24-131">2 HoloLens ayarında cihaz otomatik olarak Ethernet bağlantısı olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="7fb24-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
