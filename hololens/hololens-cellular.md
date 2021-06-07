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
# <a name="connect-to-cellular-and-5g"></a>Hücresel ve 5G'ye bağlanma

HoloLens 2, hücresel ve 5G ağlarına bağlanmak için iki yöntemi destekler:

- Hücresel cihaz tarafından sağlanan ve yaygın olarak "Etkin Nokta" olarak adlandırılan geçici bir WiFi ağı
- USB-C bağlantısı olan cihazlar için sınırlı destek

## <a name="hotspot-wifi"></a>Etkin Nokta (WiFi)

Hücresel bağlantı ihtiyaçlarının çoğu etkin noktayla karşı kullanılabilir. HoloLens 2 WiFi, en yaygın kullanım örnekleri için gereken bant genişliği ve gecikme süresi gereksinimlerini sağlayabiliyor olan 802.11ac'ı destekler. WiFi ayrıca kablo bağlantısızdır ve en fazla hücresel cihazla uyumluluk sunar.

### <a name="connecting-to-a-hotspot"></a>Etkin Nokta'ya bağlanma

1. Etkin nokta modunu etkinleştirme hakkında cihazınızın el kitabına başvurun.
1. Etkin nokta modunu etkinleştirerek ağ için bir ad ve bilinen bir parola girin.
1. HoloLens 2 Ağ ayarlarında, 2. adımda oluşturulan WiFi ağına gidin ve ağa katılın.

## <a name="usb-c-tethering"></a>USB-C Tethering

USB-C bağlantısı, ihtiyacı olan gelişmiş iş yükleri için daha düşük gecikme süresi sağlar. [Azure Remote Rendering,](https://azure.microsoft.com/services/remote-rendering)örneğin, tethering'den yararlanabilir. Hücresel cihazla HoloLens arasında kablo bağlantısı olması ve sınırlı sayıda cihazla kablo bağlantısına ihtiyaç olduğunu unutmayın.

### <a name="usb-c-compatibility"></a>USB-C uyumluluğu

Kendilerini Ethernet uyarıcı olarak sunan sınırlı sayıda cihaz, Windows Holographic sürüm 2004 ve sonrası ile kullanılabilir.

Kendilerini ethernet bağdaştırıcısı olarak sun olmayan cihazların genel Microsoft [RNDIS sürücüsünü desteklemesi](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) gerekir. Ancak bu cihazların yalnızca sınırlı bir sayısı HoloLens 2 ile uyumludur. Genel Microsoft RNDIS sürücüsünü destekleyip destekleme konusunda ayrıntılı bilgi için lütfen cihazınızın üreticisine başvurun.

RNDIS uyumlu olmayan veya bir sürücü ya da uygulamanın yüklü olması gereken cihazlar desteklanmaz.

Microsoft uyumlu cihazların listesini korumasa da, burada konuyla ilgili bir topluluk [tartışması vardır.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Bağlı bir cihaza bağlanma

1. USB üzerinden veri paylaşımını etkinleştirme hakkında cihazınızın kılavuzuna başvurun. Bu ayar genellikle "USB Paylaşımı", "Veri Paylaşımı" veya "USB Modem" olarak adlandırılır.
1. USB üzerinden veri paylaşımını etkinleştirin.
1. Cihazınızı HoloLens USB-C bağlantı noktasına bağlayın.
1. HoloLens 2 Ağ ayarlarında cihaz otomatik olarak Ethernet bağlantısı olarak görünür.
