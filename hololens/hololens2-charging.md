---
title: HoloLens 2 Pil ve Ücretlendirme
description: Dış pil paketlerinizi HoloLens ve kullanma.
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
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189809"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Pil ve Ücretlendirme

Bu sayfa, 2'den HoloLens ve dış pil paketlerini kullanma hakkında ayrıntılar sunar.

## <a name="charging-the-device"></a>Cihazı ücretlendirme

Cihazınızı ücret ödemenin en iyi yolu, HoloLens 2 ile birlikte gelen USB [Type-C](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kablosunu kullanın. HoloLens 2'ye dahil edilen aletin 2A (18W) ile 9V arasında bir verisi vardır. 2 cihaz, sağlanan duvar HoloLens yanı sıra, cihaz beklemedeyken 65 dakikadan kısa bir süre içinde pilin dolup dolulmayyabilirsiniz. Bu donatılar mevcut değilse, kullanılabilir olan aletin en az 15W gücü destekleyene sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlandırarak yavaş olan bir bilgisayar kullanmaktan kaçının.

## <a name="checking-the-battery-charge-level"></a>Pil ücreti düzeyini denetleme
Cihaz doğru şekilde önyüklüp çalışıyorsa, pil ücreti düzeyini denetlemenin üç yolu vardır:

- Cihaz kullanıcı arabiriminin ana HoloLens seçin.
- LED'i güç düğmesinin yakınında görüntüle (yüzde 40 ücret için en az iki katı LED görüyor gerekir).
    - Cihaz ücretlendirmeye devam edin. Pil göstergesi, geçerli ücret düzeyini belirtmek için yanıp söner.  Son ışık, etkin ücretlendirmeyi göstermek için belirecek ve sönecek.
    - Pil HoloLens, pil düzeyini beş artımlı olarak görüntüler.
    - Beş ışığın yalnızca biri açık olduğunda pil düzeyi yüzde 20'nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmayı denersiniz, bir ışık kısa bir süre yanıp söner ve sonra gider.
- Konak bilgisayarınızda, **Dosya Gezgini** açın ve bu bilgisayar HoloLens 2 **cihazınızın sol tarafında bakın.** Cihaza sağ tıklayın ve Özellikler'i **seçin.** Bir iletişim kutusu pil ücreti düzeyini gösterir.

   ![Pil HoloLens 2 özellikler ekranında pil değişikliği düzeyi gösterilir.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatif ücretlendirme belirtimleri

HoloLens 2, [USB](https://www.usb.org/usb-charger-pd) Güç Teslim kaynakları tarafından 27 Watt'a kadar ücrete tabidir. Kaynak en az 10 Watt tedarikebiliyorsa, HoloLens çalışma süresi uzatılabilir (bazı iş yükleri için süresiz olabilir). 

> [!NOTE]
> USB-A ile USB-C arasında bir ücretlendirme kablosu kullanmak, ücreti 7,5 Watt ile sınırlar. Çalışma süresi yine de uzatılır, ancak USB-C'den C'ye kullanım süresi kadar uzatılabilir.

Bekleme HoloLens, dahili pil için maksimum ücret oranına ulaşmak için 18 Watt yeterlidir. Kullanım HoloLens, ücretlendirme üzerinden çalışma önceliklerini belirlemesi HoloLens ücretlendirme oranı azaltabilirsiniz.

> [!IMPORTANT]
> En az 5V/1,5A HoloLens 2 için ücret ödemenizi öneririz. En az 5V/1.5A kaynağına sahip olara kullanılmamalı. 

### <a name="external-battery-packs"></a>Dış Pil Paketleri

Yukarıdaki belirtimlere uygun pil paketleri, HoloLens 2 ile kullanılabilir. Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden güç sağlay dikkat edin. Bu pil paketlerinin TRY uygulaması [önemlidir. SRC'](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) den emin olmak HoloLens ücret ödemelerini src. 

### <a name="managing-heat"></a>Isı Yönetimi

Tüm cihazlarda olduğu gibi, HoloLens ısı üretir. Ücret ne kadar hızlısa ısı da o kadar fazla olur. Ayrıca, daha düşük bir pil düzeyinde bir ücrete başlayarak, pil çoğunlukla dolu olduğunda bir ücreti başlatmaya göre daha fazla ısı elde edilecektir. Sıcak ortamlarda uzun HoloLens süreler boyunca çalışma ihtiyacı olan müşteriler aşağıdaki teknikleri kullanabilir:

- Dahili pil tamamen HoloLens 2'den dış güç kaynağına bağlanmakta sorun yok.
- Dış pil tükenmiş olduğunda, HoloLens iç pilde çalışmaya devam eder.    
- Yukarıdaki adımların ardından ısı sorunu devam ediyorsa, ücretlendirmeyi 1,5A ile sınırlayan bir pil veya pil paketi kullanmayı göz önünde bulundurabilirsiniz. İç pil yavaş yavaş tükenene kadar bu seçeneğin o kadar fazla çalışma süresi sağlamaycaz.

## <a name="troubleshooting"></a>Sorun giderme


### <a name="hololens-charges-external-battery"></a>HoloLens Dış Pil Ücretleri
Bu HoloLens 2, pil tarafından ücret yerine dış pile ücret uygulanırsa, bu pilin TRY uygulamadığını [gösterir. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Bu sorunu çözmek için önerilen yöntem daha yeni bir pil paketine geçmektir, ancak alternatif olarak USB-A'ya USB-C kablosuna geçmeyi denemeyi abilirsiniz. Bu, ücretlendirme oranını 7,5 watt ile sınırlar.
