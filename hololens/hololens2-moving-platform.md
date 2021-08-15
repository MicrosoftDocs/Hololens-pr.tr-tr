---
title: HoloLens 2 Platform taşınıyor
description: platformlar taşınıyor HoloLens kullanma
keywords: platformlar, dinamik hareket, Hololens, hareketli platform modu
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ae9090409b9c357f7d7ced8ddd477fbebea62e1e3912a9d3691d5585ad79239c
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2021
ms.locfileid: "120389213"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Düşük dinamik hareket taşıma platformları üzerine platform modunu taşıma

**ınsider build 20348,1411** ' de, HoloLens 2 ' de düşük dinamik hareket taşınan platformları izlemek için beta desteği ekledik. derlemeyi yükledikten ve platformu taşıma modunu etkinleştirdikten sonra, büyük ve büyük deniz mavisi gibi daha önce erişilemeyen ortamlarda HoloLens 2 ' yi kullanabilirsiniz. Şu anda özelliği, yalnızca bu taşıma platformlarının etkinleştirilmesini hedeflenmiştir. Başka ortamlarda özelliği kullanmayı denediğinize hiçbir şey engel olmadıysa, bu özellik önce bu ortamlar için destek eklemeye odaklanılmıştır.

> [!NOTE]
> bu özellik şu anda yalnızca Windows [ınsiders](hololens-insider.md)aracılığıyla kullanılabilir.

Bu makalede şunları ele alınmaktadır:

1. [Hareketli platformun neden gereklidir?](#why-moving-platform-mode-is-necessary)
1. [Taşıma platformu modunu etkinleştirme](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Platform modunun neden gereklidir?

HoloLens, kararlı hologramlar göstermek için [6 derece serbestlik](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, Z çevirisi ve döndürme, sıklık, yaw dönüşü) ile baş konumunuzu izleyebilmelidir. bunu yapmak için, iki ayrı kaynaktaki iki benzer bilgi parçasını takip HoloLens izler:

1. , Örneğin, HoloLens kullandığınız fiziksel Oda, ortamı izleyen görünür açık kameralar
1. Inertial ölçü birimi (ıMU),-dünya üzerindeki baş hareket ve yönlerinizi izleyen bir ivometer, jroscope ve manyetik tometreden oluşur

Bu iki kaynaktan alınan bilgiler, daha düşük bir gecikme süresi ve sorunsuz hologramlar oluşturmak için yüksek sıklıkta baş konumunuzu izlemek üzere bileşik bir şekilde yapılır.

Ancak, bu yaklaşım önemli bir varsayımına dayanır; ortam (kameralar tarafından izlenen), dünya ile (ıMU 'nin ölçüm yapabilen) sabit olarak kalır. Bu durum, su içindeki bir bot 'ta olduğu gibi, her iki kaynaktan da bulunan bilgiler birbirleriyle çakışabilir ve izleyicide kayıp oluşmasına neden olabilir. Bu çakışma, swimmy hologram veya hatta izleme kaybından yanlış konum bilgileri ve sonuçları üretir.

Platform modunun taşınması bu sorunu düzeltir. Taşıma platformu modunu etkinleştirdiğinizde, bu, izleyicimizin her zaman birbirini tamamen kabul etmesi için sensör girdilerimize güvenemiz bir ipucu olan. Bunun yerine, Visual Tracking 'e daha fazla güvenmelidir ve ıconkou inertial hareket verilerini hızlıca tanımlayabilir ve IMU girişini kullanabilmek&#39;uygun şekilde filtrelemeniz gerekir.

## <a name="supported-environments-and-known-limitations"></a>Desteklenen ortamlar ve bilinen sınırlamalar

Platform modunun taşınması, inertial ve Visual Data Conflict 'in çalışmalarını akıllıca işlemek için geliştirilmiştir. Bu, şu anda düşük dinamik hareket yaşayan büyük deniz mavisi ' tir. Yani, kesinlikle sınırlamalar ve desteklenmeyen senaryolar vardır.

### <a name="known-limitations"></a>Bilinen Sınırlamalar

- Taşıma platformu modu (MPD) için desteklenen tek ortamlar, düşük dinamik hareket yaşayan büyük deniz mavisi ortamlardır. Diğer bir deyişle, çok yaygın ortamlar/durumlar, yüksek frekanslı hareket ve yüksek hızlandırma ve [Jerk](https://en.wikipedia.org/wiki/Jerk_(physics))seviyeleri nedeniyle henüz **desteklenmemiştir** . Örneğin: düzler, traıns, Araba, Bisiklet, veri yolları, küçük Boats, yükseltme vb.
- mpb etkinleştirildiğinde, özellikle kesik kesik bir su olduğunda, Hologramlar biraz zaman alabilir.
- Hiçbir şey, kullanıcıların desteklenmeyen ortamlarda MPD kullanmayı denemelerini engeller, ancak cihaz desteklenmeyen alanda izlemeyi koruyabilmezse kullanıcılar istenmeyen yan etkilerle karşılaşabilir. Örneğin, MPD ile kullanıcılar, bu, daha önce imkansız olsa da, katları değiştirirken bir Asansör&#39;bulunabilir. Ne yazık ki MPD cihazın izlemeyi korumasını sağlar, ancak şu anda eşleme yönetimini işlemez. Böylece kullanıcılar, bir Asansör içindeki yüzlerin değiştirilmesinin, cihazın üst ve alt zeminleri karıştırabilmesini ve harita kalitesini olumsuz yönde etkilemesini sağlayacaktır.

## <a name="prerequisites"></a>Önkoşullar

Platform modunu taşımaya yönelik Beta desteği yalnızca birkaç önkoşul gerektirir:

1. [En son Insiders yapısını yay aracılığıyla](hololens-insider.md#ffu-download-and-flash-directions) veya [cihazınızı kaydederek ve güncelleştirerek](hololens-insider.md#start-receiving-insider-builds)oluşturma 20348,1411 veya daha yeni bir sürüm oluşturun.
   - Note: Bu derleme Şu anda yalnızca [Insider geliştirme kanalında](hololens-insider.md#start-receiving-insider-builds)kullanılabilir.
2. [Geliştirici modunu ve cihaz portalını](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal) etkinleştir

## <a name="enabling-moving-platform-mode"></a>Taşıma platformu modunu etkinleştirme

Platform modunu taşımayı etkinleştirmek için önce [cihaz portalını etkinleştirin](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Sol taraftaki menüde **sistem** Accordion seçin
2. **Platform modunu taşıma** sayfasını seçin ve **hareketli platform modu** onay kutusunu işaretleyin

![İlk görüntü](.\images\moving-platform-1.png) ![İkinci görüntü](.\images\moving-platform-2.png)

3. Bir uyarıyla istendiğinde **Tamam** ' ı seçin.

![Üçüncü görüntü](.\images\moving-platform-3.png)

4. Cihazınızı yeniden başlatarak, en üstteki cihaz portalı **Güç** menüsü aracılığıyla ya da aşağıdaki sesli komutu yayımlayarak &quot; cihazı yeniden başlatın &quot; ve Evet ' i seçin &quot; &quot; .

![Dördüncü görüntü](.\images\moving-platform-4.png)

Cihaz portalında hareketli platform modu seçeneğini göremiyorsanız, bu durumda henüz doğru yapıda değilsiniz demektir. [Önkoşullar](#prerequisites) bölümüne bakın.