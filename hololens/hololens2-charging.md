---
title: Pil ve Ücretlendirme
description: HoloLens'inizi nasıl ücretlendirin ve dış pil paketlerini kullanın.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380296"
---
# <a name="battery-and-charging"></a>Pil ve Ücretlendirme

Bu sayfada HoloLens 2'nin ücretlendirmesi ve dış pil paketlerinin kullanımıyla ilgili ayrıntılar yer almaktadır.

## <a name="included-charger"></a>Dahil EdilenLer

HoloLens 2'ye dahil edilen güç, 2A (18W) ile en fazla 9V sağlar. Mümkün olduğunda, dahil edilen cihazın kullanılması kesinlikle önerilir.  

## <a name="specifications"></a>Belirtimler

HoloLens 2, USB Güç Teslim kaynakları [tarafından](https://www.usb.org/usb-charger-pd) 27 Watt'a kadar ücretlendir olabilir. Kaynak en az 10 Watt tedarikebiliyorsa HoloLens çalışma süresi uzatılabilir (bazı iş yükleri için süresiz olabilir). 

> [!NOTE]
> USB-A ile USB-C arasında bir ücretlendirme kablosu kullanmak, ücreti 7,5 Watt ile sınırlar. Çalışma süresi yine de uzatılır, ancak USB-C'den C'ye kullanım süresi kadar uzatılabilir.

HoloLens bekleme modundayken dahili pil için maksimum ücret oranına ulaşmak için 18 Watt yeterlidir. HoloLens kullanımda olduğunda, HoloLens ücretlendirmeye öncelik verdiklerinden ücretlendirme oranı azaltabilirsiniz.

> [!IMPORTANT]
> HoloLens 2'nin en az 5V/1,5A ücretlendirmiş olması önerilir. En az 5V/1.5A kaynağına sahip olara kullanılmamalı. 

## <a name="external-battery-packs"></a>Dış Pil Paketleri

Yukarıdaki belirtimlere uygun pil paketleri HoloLens 2 ile kullanılabilir. Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden güç sağlay dikkat edin. Bu pil paketlerinin TRY uygulaması [önemlidir. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) holoLens yerine HoloLens'i ücretlendirmelerini sağlar. 

## <a name="managing-heat"></a>Isı Yönetimi

Tüm cihazlarda olduğu gibi HoloLens'in ücretlendirmesi ısı üretir. Ücret ne kadar hızlısa ısı da o kadar fazla olur. Ayrıca, daha düşük bir pil düzeyinde bir ücrete başlayarak, pil çoğunlukla dolu olduğunda bir ücretin başlatılamayacak kadar ısı üretir. HoloLens'i sıcak ortamlarda uzun süre çalıştırmak isteyen müşteriler aşağıdaki teknikleri kullanabilir:

- Dahili pil tamamen dolu olsa bile HoloLens 2'nin harici bir güç kaynağına bağlanması sorun değil.
- Dış pil tükenmiş olduğunda HoloLens dahili pille çalışmaya devam eder.    
- Yukarıdaki adımların ardından ısı sorunu devam ediyorsa, ücretlendirmeyi 1,5A ile sınırlayan bir pil veya pil paketi kullanmayı göz önünde bulundurabilirsiniz. İç pil yavaş yavaş tükenene kadar bu seçeneğin o kadar fazla çalışma süresi sağlamaycaz.

## <a name="troubleshooting"></a>Sorun giderme


### <a name="hololens-charges-external-battery"></a>HoloLens, Harici Pil Ücretleri
HoloLens 2, bu pille ücretlendiril yerine bir dış pile ücret uygulanması pilin TRY uygulamadığını [gösterir. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Bu sorunu çözmek için önerilen yöntem daha yeni bir pil paketine geçmektir, ancak alternatif olarak USB-A'ya USB-C kablosuna geçmeyi denemeyi abilirsiniz. Bu, ücretlendirme oranını 7,5 watt ile sınırlar.
