---
title: hücresel ve 5 g 'ye Bağlan
description: HoloLens karma gerçeklik cihazlarınızdan hücresel ağlara bağlanma.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036316"
---
# <a name="connect-to-cellular-and-5g"></a>hücresel ve 5 g 'ye Bağlan

HoloLens 2, hücresel ve 5 g ağlarına bağlanmak için iki yöntemi destekler:

- Hücresel cihaz tarafından sunulan, yaygın olarak "etkin nokta" olarak adlandırılan bir geçici WiFi ağı
- USB-C tethered cihazları için sınırlı destek

## <a name="hotspot-wifi"></a>Etkin nokta (WiFi)

En fazla hücresel bağlantı ihtiyaçları bir etkin nokta ile karşılanabileceği. HoloLens 2 WiFi, en yaygın kullanım durumları için gereken bant genişliği ve gecikme süresi gereksinimlerini sağlayabilen 802.11 ac 'yi destekler. WiFi ayrıca kablo ücretsizdir ve en fazla hücresel cihaz sayısıyla uyumluluk sağlar.

### <a name="connecting-to-a-hotspot"></a>Bir sıcak noktaya bağlanma

1. Etkin nokta modunu nasıl etkinleştireceğinizi öğrenmek için cihazınızın kılavuzuna bakın.
1. Bilinen bir parolanın yanı sıra ağ için bir ad sağlayarak etkin nokta modunu etkinleştirin.
1. HoloLens 2 ağ ayarları ' nda 2. adımda oluşturulan WiFi ağını bulun ve bu gruba katın.

## <a name="usb-c-tethering"></a>USB-C Internet paylaşımı

USB-C internet paylaşımı, gerekli olan gelişmiş iş yükleri için daha düşük gecikme süresi sağlayabilir. Örneğin, [Azure uzaktan işleme](https://azure.microsoft.com/services/remote-rendering), internet paylaşımı 'ten faydalanabilir. internet paylaşımı, hücresel cihaz ile HoloLens arasında bir kablo gerektirdiğini ve internet paylaşımı sınırlı sayıda cihaz tarafından desteklendiğini unutmayın.

### <a name="usb-c-compatibility"></a>USB-C uyumluluğu

kendisini ethernet bağdaştırıcısı olarak sunan sınırlı sayıda cihaz, Windows Holographic sürüm 2004 ve üzeri sürümlerle kullanılabilir.

Kendisini bir Ethernet bağdaştırıcısı olarak sunan cihazların genel Microsoft [rndis](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) sürücüsünü desteklemesi gerekir. ancak, bu cihazların yalnızca sınırlı sayıda HoloLens 2 ile uyumlu olması gerekir. Genel Microsoft RNDIS sürücüsünü destekleyip desteklemediğini öğrenmek için lütfen cihazınızın üreticisine başvurun.

RNDIS uyumlu olmayan veya bir sürücü ya da uygulamanın yüklenmesini gerektiren cihazlar desteklenmez.

Microsoft, uyumlu cihazların bir listesini koruurken [, konu başlığı](https://aka.ms/HLCommunityCell)altında bir topluluk tartışması vardır.

### <a name="connecting-to-a-tethered-device"></a>Bir tethered cihazına bağlanma

1. USB üzerinden veri paylaşımını etkinleştirme konusunda cihazınızın kılavuzuna bakın. Bu ayar genellikle "USB Internet paylaşımı", "veri paylaşımı" veya "USB Modem" olarak adlandırılır.
1. USB üzerinden veri paylaşımını etkinleştirin.
1. cihazınızı HoloLens USB-C bağlantı noktasına Bağlan.
1. HoloLens 2 ağ ayarlarında, cihaz otomatik olarak Ethernet bağlantısı olarak görünür.
