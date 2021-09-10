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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428527"
---
# <a name="connect-to-cellular-and-5g"></a>Bağlan hücresel ve 5G'ye

HoloLens 2, hücresel ve 5G ağlarına bağlanmak için iki yöntemi destekler:

- Hücresel cihaz tarafından sağlanan ve genellikle "Etkin Nokta" olarak adlandırılan geçici bir WiFi ağı
- USB-C bağlantısı olan cihazlar için sınırlı destek

## <a name="hotspot-wifi"></a>Etkin Nokta (WiFi)

Hücresel bağlantı ihtiyaçlarının çoğu etkin noktayla karşı kullanılabilir. HoloLens 2 WiFi 802.11ac'ı destekler ve bu da en yaygın kullanım örnekleri için gereken bant genişliği ve gecikme süresi gereksinimlerini sağlar. WiFi ayrıca kablo bağlantısızdır ve en fazla hücresel cihazla uyumluluk sunar.

### <a name="connecting-to-a-hotspot"></a>Etkin Nokta'ya bağlanma

1. Etkin nokta modunu etkinleştirme hakkında cihazınızın el kitabına başvurun.
1. Etkin nokta modunu etkinleştirerek ağ için bir ad ve bilinen bir parola girin.
1. 2 HoloLens ayarlar sayfasında, 2. adımda oluşturulan WiFi ağına gidin ve buna katılın.

## <a name="usb-c-tethering"></a>USB-C Tethering

USB-C bağlantısı, ihtiyacı olan gelişmiş iş yükleri için daha düşük gecikme süresi sağlar. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), örneğin, tethering'den yararlanabilir. Kablo bağlantısı için hücresel cihazla cihaz arasında bir kablo HoloLens ve sınırlı sayıda cihaz tarafından tethering desteğine sahip olduğunu unutmayın.

### <a name="usb-c-compatibility"></a>USB-C uyumluluğu

Kendilerini Ethernet uyarıcı olarak sunan sınırlı sayıda cihaz, Windows Holographic sürüm 2004 ve sonraki sürümlerle kullanılabilir.

Kendilerini bir Ethernet bağdaştırıcısı olarak sun olmayan cihazların genel Microsoft [RNDIS sürücüsünü desteklemesi](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) gerekir. Ancak, bu cihazların yalnızca sınırlı bir sayısı HoloLens 2 ile uyumludur. Genel Microsoft RNDIS sürücüsünü destekleyip destekleme konusunda ayrıntılı bilgi için lütfen cihazınızın üreticisine başvurun.

RNDIS uyumlu olmayan veya bir sürücü ya da uygulamanın yüklü olması gereken cihazlar desteklanmaz.

Microsoft uyumlu cihazların listesini korumasa da, burada konuyla ilgili bir topluluk tartışması [vardır.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Bağlı bir cihaza bağlanma

1. USB üzerinden veri paylaşımını etkinleştirme hakkında cihazınızın kılavuzuna başvurun. Bu ayar genellikle "USB Paylaşımı", "Veri Paylaşımı" veya "USB Modem" olarak adlandırılır.
1. USB üzerinden veri paylaşımını etkinleştirin.
1. Bağlan USB-C HoloLens cihazına bağlayın.
1. 2 HoloLens ayarında cihaz otomatik olarak Ethernet bağlantısı olarak görünür.
