---
title: HoloLens 2 Pil ve Ücretlendirme
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
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923593"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Pil ve Ücretlendirme

Bu sayfada HoloLens 2'nin ücretlendirmesi ve dış pil paketlerinin kullanımıyla ilgili ayrıntılar yer almaktadır.

## <a name="charging-the-device"></a>Cihazı ücretlendirme

Cihazınızı [ücretlendirecek en](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) iyi yol olan HoloLens 2 ile birlikte gelen USB Type-C kablosunu kullanın. HoloLens 2'ye dahil edilen güç, 2A (18W) ile en fazla 9V sağlar. Sağlanan duvar cihazıyla birlikte HoloLens 2 cihazları, cihaz beklemedeyken pilin 65 dakikadan kısa bir süre içinde dolup dolymayabilirsiniz. Bu aksesuarlar mevcut değilse, kullanılabilir olan aletin en az 15W gücü destekleyene sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlandırarak yavaş olan bir bilgisayar kullanmaktan kaçının.

## <a name="checking-the-battery-charge-level"></a>Pil ücreti düzeyini denetleme
Cihaz doğru şekilde önyüklüp çalışıyorsa, pil ücreti düzeyini denetlemenin üç yolu vardır:

- HoloLens cihazı kullanıcı arabiriminin ana menüsünden.
- LED'i güç düğmesinin yakınında görüntüle (yüzde 40 ücret için en az iki katı LED görüyor gerekir).
    - Cihaz ücretlendirmeye devam edin. Pil göstergesi, geçerli ücret düzeyini belirtmek için yanıp söner.  Son ışık, etkin ücretlendirmeyi göstermek için belirecek ve sönecek.
    - HoloLens'iniz etkin olduğunda pil göstergesi beş artımlı olarak pil düzeyini görüntüler.
    - Beş ışığın yalnızca biri açık olduğunda pil düzeyi yüzde 20'nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmayı denersiniz, bir ışık kısa bir süre yanıp söner ve sonra gider.
- Konak bilgisayarınızda bu **Dosya Gezgini** açın ve Sol tarafta Bu bilgisayar altında HoloLens 2 **cihazınızı açın.** Cihaza sağ tıklayın ve Özellikler'i **seçin.** Bir iletişim kutusu pil ücreti düzeyini gösterir.

   ![HoloLens 2 özellikler ekranı pil değişikliği düzeyini gösterir](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatif ücretlendirme belirtimleri

HoloLens 2, USB Güç Teslim kaynakları [tarafından](https://www.usb.org/usb-charger-pd) 27 Watt'a kadar ücretlendir olabilir. Kaynak en az 10 Watt tedarikebiliyorsa HoloLens çalışma süresi uzatılabilir (bazı iş yükleri için süresiz olabilir). 

> [!NOTE]
> USB-A ile USB-C arasında bir ücretlendirme kablosu kullanmak, ücreti 7,5 Watt ile sınırlar. Çalışma süresi yine de uzatılır, ancak USB-C'den C'ye kullanım süresi kadar uzatılabilir.

HoloLens bekleme modundayken dahili pil için maksimum ücret oranına ulaşmak için 18 Watt yeterlidir. HoloLens kullanımda olduğunda, HoloLens ücretlendirmeye öncelik verdiklerinden ücretlendirme oranı azaltabilirsiniz.

> [!IMPORTANT]
> HoloLens 2'nin en az 5V/1,5A ücretlendirmiş olması önerilir. En az 5V/1.5A kaynağına sahip olara kullanılmamalı. 

### <a name="external-battery-packs"></a>Dış Pil Paketleri

Yukarıdaki belirtimlere uygun pil paketleri HoloLens 2 ile kullanılabilir. Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden güç sağlay dikkat edin. Bu pil paketlerinin TRY uygulaması [önemlidir. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) holoLens yerine HoloLens'i ücretlendirmelerini sağlar. 

### <a name="managing-heat"></a>Isı Yönetimi

Tüm cihazlarda olduğu gibi HoloLens'i ücretlendirmek de ısı üretir. Ücret ne kadar hızlı olursa ısı da o kadar fazla olur. Ayrıca, daha düşük bir pil düzeyinde bir ücrete başlayarak, pil çoğunlukla dolu olduğunda bir ücretin başlatılamayacak kadar ısı üretir. HoloLens'i sıcak ortamlarda uzun süre çalıştırmak isteyen müşteriler aşağıdaki teknikleri kullanabilir:

- Dahili pil tamamen dolu olsa bile HoloLens 2'nin harici bir güç kaynağına bağlanması sorun değil.
- Dış pil tükenmiş olduğunda HoloLens dahili pille çalışmaya devam eder.    
- Yukarıdaki adımların ardından ısı sorunu devam ediyorsa, ücretlendirmeyi 1,5A ile sınırlayan bir pil veya pil paketi kullanmayı göz önünde bulundurabilirsiniz. İç pil yavaş yavaş tükenene kadar bu seçeneğin o kadar fazla çalışma süresi sağlamaycaz.

## <a name="troubleshooting"></a>Sorun giderme


### <a name="hololens-charges-external-battery"></a>HoloLens, Harici Pil Ücretleri
HoloLens 2, bu pille ücretlendiril yerine bir dış pile ücret uygulanması pilin TRY uygulamadığını [gösterir. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Bu sorunu çözmek için önerilen yöntem daha yeni bir pil paketine geçmektir, ancak alternatif olarak USB-A'ya USB-C kablosuna geçmeyi denemeyi abilirsiniz. Bu, ücretlendirme oranını 7,5 watt ile sınırlar.
