---
title: HoloLens 2 Platform Modunu Taşıma
description: Taşıma platformlarında HoloLens kullanma
keywords: taşıma platformları, dinamik hareket, hololens, hareketli platform modu
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
ms.openlocfilehash: 81b3231827fce9a2ae2d5e3105800685fedb917b
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036396"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Düşük Dinamik Hareket Hareketli Platformlarında Platform Modunu Taşıma

**Insider 20348.1411** derlemesinde, HoloLens 2'de düşük dinamik hareket hareketli platformlarında izlemeye yönelik beta desteği ekledik. Derlemeyi yükleyerek Ve Taşıma Platformu Modu'na etkinleştirdikten sonra, HoloLens 2'nizi büyük gemiler ve büyük deniz gemileri gibi daha önce erişilemeyen ortamlarda kullanabilirsiniz. Şu anda bu özellik yalnızca bu hareketli platformların etkinleştirilmesini hedeflemektedir. Özelliği başka ortamlarda kullanmaya çalışmanıza engel olan bir şey yoktur ancak özellik önce bu ortamlar için destek eklemeye odaklanmaktadır.

> [!NOTE]
> Bu özellik şu anda yalnızca Windows [Insiders aracılığıyla kullanılabilir.](hololens-insider.md)

![Taşıma platformu örneği.](./images/mpm-compare.gif)

Bu makale şunları kapsar:

1. [Taşıma Platformu Neden Gereklidir?](#why-moving-platform-mode-is-necessary)
1. [Platform Modunu Taşımayı Etkinleştirme](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Platform Modunu Taşıma Neden Gereklidir?

HoloLens hologramları göstermek için [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) derece serbestlik (X, Y, Z, çeviri ve roll, pitch, yaw rotasyon) ile baş pozisyonunu izleyebiliyor olması gerekir. Bunu yapmak için HoloLens farklı kaynaklardan iki benzer bilgi parçası izlersiniz:

1. Görünür ışık kameraları: Ortamı takip eder( örneğin, fiziksel oda) HoloLens
1. Inertial Measurement Unit (IMU) : Dünya'ya göre baş hareketlerinizi ve yönünizi takip eden bir ivmeölçer, jiroscope ve ölçerden oluşan bir inertial Measurement Unit (IMU)

Bu iki kaynağın bilgileri, sorunsuz hologramlar işlemek için düşük gecikme süresinde ve yeterince yüksek sıklıkta baş konumunuz izlemek için bileşiktir.

Ancak, bu yaklaşım kritik bir varsayıma dayanır; ortam (kameralar tarafından izlendi) Dünya'ya göre sabit kalır (bu, IMU'ya göre ölçümler yapmak için kullanılır). Böyle bir durumla karşılamayacaksa, tıpkı suların içinde yer alan bir deniz üzerinde her iki kaynakta yer alan bilgiler çakışabilir ve izleyicinin kaybolabilir. Bu çakışma yanlış konum bilgileri üretir ve bunun sonucunda hologramlarım yüzer ve hatta kaybı takip edin.

Platform Modu'na taşıma bu sorunu çözümler. Hareketli Platform Modu'na etkinleştirerek izleyicimize algılayıcı girişlerimizi kullanarak her zaman tamamen aynı görüşe sahip olamayabilirsiniz. Bunun yerine, IMU girişini kullanamadan önce görsel izlemeye daha fazla güvenmemiz, tutarsız verimsel olmayan verileri hızla tanımlamamız ve buna uygun şekilde filtrelememiz gerekir.

## <a name="supported-environments-and-known-limitations"></a>Desteklenen Ortamlar ve Bilinen Sınırlamalar

Taşıma Platformu Modu, veri çakışması ve veri çakışması durumlarını akıllı bir şekilde işlemek için geliştirilmişken, şu anda düşük dinamik hareketle karşılaşan büyük deniz kuvvetlerinin kapsamına girer. Bu, kesinlikle sınırlamalar ve desteklenmeyen senaryolar olduğu anlamına gelir.

### <a name="known-limitations"></a>Bilinen Sınırlamalar

- Hareketli Platform Modu(MPM) için desteklenen tek ortamlar, düşük dinamik hareketle karşılaşan büyük deniz gemileridir. Başka bir deyişle, birçok yaygın  ortam/durum henüz yüksek frekanslı hareket ve yüksek hızlanma ve ivme düzeyleri nedeniyle [desteklenmemektedir.](https://en.wikipedia.org/wiki/Jerk_(physics)) Örneğin: düzlemler, trenler, arabalar, bisikletler, otobüsler, küçük asansörler, vb.
- Hologramlar MPM etkinleştirildiğinde, özellikle de dalgalı sularda biraz sallanıyor olabilir.
- Hiçbir şey, kullanıcıların desteklenmeyen ortamlarda MPM kullanmaya denemesini önlese de, cihaz desteklenmeyen alanda izlemeyi sürdürebilirse kullanıcılar istenmeyen yan etkilerle karşılanabilir. Örneğin MPM ile kullanıcılar, kat değiştirirken bir asansörde kullanmanın mümkün olduğunu, ancak bu daha önce mümkün değildi. Ne yazık ki MPM, cihazın izlemesini sürdürmesini sağlar ancak şu anda harita yönetimini işlemez. Kullanıcılar, bir asansörde zeminlerin değiştirilmesinin cihazın üst ve alt katları karıştırmasını ve harita kalitesini olumsuz yönde etkileyeceğini bulur.

## <a name="prerequisites"></a>Önkoşullar

Platform Modunu Taşıma için beta desteği yalnızca birkaç önkoşul gerektirir:

1. Arc aracılığıyla en son [Insiders](hololens-insider.md#ffu-download-and-flash-directions) derlemesini ya da cihazınızı kaydederek ve güncelleştirerek derleme 20348.1411 [veya daha yenisini yükleyin.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Bu derleme şu anda yalnızca [Insider Dev Channel'da kullanılabilir.](hololens-insider.md#start-receiving-insider-builds)

2. Geliştirici [Modunu ve Cihaz Portalı](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Platform Modunu Taşımayı Etkinleştirme

Taşıma Platformu modunu etkinleştirmek için önce ['yi Cihaz Portalı.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Sol **menüden** Sistem uyumu'nı seçin

   ![İlk görüntü.](.\images\mpm-01.png)

2. Platform **Modunu Taşıma sayfasını** seçin ve Platform Modunu **Taşıma onay** kutusunu işaretleyin

    ![İkinci görüntü.](.\images\mpm-02.png)

3. Uyarı istendiğinde Tamam'ı **seçin**

   ![Üçüncü görüntü.](.\images\mpm-03.png)

4. Cihazınızı yeniden başlatın. Bu işlemi sağ üst Cihaz Portalı **Power** menüsü aracılığıyla veya aşağıdaki ses komutuyla cihazı yeniden başlatıp &quot; &quot; Evet'i &quot; seçerek gerçekleştirebilirsiniz. &quot;

   ![Dördüncü görüntü.](.\images\mpm-04.png)

Platform Modunu Taşıma seçeneğini Cihaz Portalı, büyük olasılıkla henüz düzgün derlemede olmadığınız anlamına gelir. [Önkoşullar bölümüne](#prerequisites) bakın.

## <a name="reporting-issues"></a>Raporlama Sorunları

Yukarıda da belirtildiği gibi, bu özellik yalnızca Geliştirici Modu'da kullanılabilen bir beta özelliğidir ve bu da sorunlarıyla karşılanabilirsiniz. Böyle bir durumda ürünü araştırarak geliştirin, lütfen

1. Hologram doğruluğu, [Geri Bildirim Merkezi](hololens-feedback.md) güvenilirlik kategorisine göre sorun bildirme **ve** şunları içerir:
    1. Beklenen davranış ve deneyime ilişkin davranış da dahil olmak üzere sorunun açıklaması
    1. Sorunun Karma Gerçeklik [video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) yakalaması
2.  adresine bir destek durumu açın ve Geri Bildirim Merkezi URL'sini paylaşın; böylece takip sorularına [https://aka.ms/hlsupport](https://aka.ms/hlsupport) ulaşabilirsiniz