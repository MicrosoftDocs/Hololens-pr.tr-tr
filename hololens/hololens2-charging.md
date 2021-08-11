---
title: 2 pil ve şarj HoloLens
description: HoloLens ücret ödeme ve dış pil paketlerini kullanma.
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
ms.openlocfilehash: b117542704968150639a47956a8142d7232fcc66d696feb61ec4fffdaa49df59
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660583"
---
# <a name="hololens-2-battery-and-charging"></a>2 pil ve şarj HoloLens

bu sayfada, HoloLens 2 ve dış pil paketleri kullanılarak ücretlendirme hakkında ayrıntılar sunulmaktadır.

## <a name="charging-the-device"></a>Cihaz dolduruluyor

cihazınızı ücretlendirmenin en iyi yolu olan HoloLens 2 ile birlikte gelen [cihazınızın şarj cihazına ve USB Type-C kablosunu](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) kullanın. HoloLens 2 ' ye dahil edilen cihazınızın şarj cihazına, en fazla 9v @ 2a (18w) sağlar. HoloLens 2 cihaz, sağlanan duvar karaleti ile birlikte, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendirmesini sağlayabilir. Bu aksesuarlar yoksa, mevcut olan cihazınızın şarj cihazına 'ın en az 15W güç desteğine sahip olduğundan emin olun.

> [!NOTE]
> Mümkünse, cihazı USB üzerinden ücretlendirilecek bir BILGISAYAR kullanmaktan kaçının, bu da yavaş olur.

## <a name="checking-the-battery-charge-level"></a>Pil ücreti düzeyi denetleniyor
Cihaz doğru şekilde önyüklendiğinde ve çalışıyorsa, pil ücreti düzeyini denetlemek için üç yol vardır:

- HoloLens cihaz kullanıcı arabiriminin ana menüsünde.
- Güç düğmesine ışığı (%40 oranında bir ücret için) görüntüleyin ve en az iki katı LED görmeniz gerekir.
    - Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.  Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.
    - HoloLens açık olduğunda, pil göstergesi pil düzeyini beş artışlarla görüntüler.
    - Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.
    - Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.
- ana bilgisayarınızda, **dosya gezgini** 'ni açın ve **bu bilgisayarın** altındaki HoloLens 2 cihazınızı sol tarafta arayın. Cihaza sağ tıklayın ve **Özellikler**' i seçin. Bir iletişim kutusu, pil ücreti düzeyini gösterir.

   ![HoloLens 2 özellikleri ekranı, pil değişim düzeyini gösterir](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatif ücretlendirme belirtimleri

HoloLens 2 ' ye kadar, [USB güç teslimi](https://www.usb.org/usb-charger-pd) kaynakları 27 watt 'a kadar ücretlendirilir. kaynak en az 10 watt sağlayabiliyor ise, HoloLens çalışma süresi genişletilebilir (bazı iş yükleri için muhtemelen süresiz). 

> [!NOTE]
> USB-A ' y i bir USB-C doldurma kablosu kullanmak, ücreti 7,5 Watt ile sınırlandırır. Çalışma süresi yine de genişletilir, ancak USB-C ' d e n kullanıldığı sürece bu kalır.

HoloLens bekleme modundayken, 18 watt, iç pil için maksimum ücret oranına ulaşmak için yeterlidir. HoloLens kullanımda olduğunda, ücret üzerinden çalışan HoloLens önceliklendirmesinden bu yana ücret düşmeyebilir.

> [!IMPORTANT]
> HoloLens 2 ' nin en düşük 5 v/1,5 üzerinden ücretlendirildiğini öneririz. En az 5 V/1,5 A sağlayamayan karelerle kullanılmamalıdır. 

### <a name="external-battery-packs"></a>Dış pil paketleri

yukarıdaki belirtimlere uyan pil paketleri, HoloLens 2 ile kullanılabilir. Ancak, bazı USB-C pil paketlerinin aynı USB-C bağlantı noktası üzerinden yeniden şarj ve güç sunmadığını unutmayın. Bu pil paketlerinin denemeyi uygulaması önemlidir [. kaynak](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) , bundan ücret ödemektense HoloLens ücretlendirdiklerinden emin olmak için. 

### <a name="managing-heat"></a>Isı yönetimi

tüm cihazlarda olduğu gibi, ücretlendirme HoloLens ısı üretir. Ücret ne kadar hızlı, daha fazla ısı oluşturulur. Ayrıca, daha düşük bir pil düzeyinde bir ücret başlamak, pilin büyük bir kısmı dolduğunda ücreti başlatmadan daha fazla ısı üretir. etkin ortamlarda uzun süreli HoloLens çalışması gereken müşteriler aşağıdaki teknikleri kullanabilir:

- iç pil tamamen ücretlendirildiği zaman bile, HoloLens 2 ' nin bir dış güç kaynağına bağlanması tamam.
- dış bir pil boşaldığında HoloLens iç pilinin üzerinde çalışmaya devam edecektir.    
- Yukarıdaki adımları takip eden bir sorun yaşamaya devam ediyorsa, pili 1,5 a ile sınırlayan bir cihazınızın şarj cihazına veya pil paketi kullanmayı düşünün. Bu seçeneğin, iç pilin hala yavaş olduğundan çok fazla çalışma süresi sağlamayacağını unutmayın.

## <a name="troubleshooting"></a>Sorun giderme


### <a name="hololens-charges-external-battery"></a>HoloLens Dış pili ücretlendirir
HoloLens 2 ' nin ücretlendirilmesinin yerine harici bir pil ücreti varsa, bu, pilin deneme uygulamadığını gösterir [. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Daha yeni bir pil paketine geçiş yapmak, bu sorunu çözmek için önerilen yoldur, alternatif olarak, USB-A ' y a USB-A ' y e bir kabloya geçmeyi deneyebilirsiniz. Bu işlem, doldurma oranını 7,5 watt 'a sınırlayacağını aklınızda bulundurun.
