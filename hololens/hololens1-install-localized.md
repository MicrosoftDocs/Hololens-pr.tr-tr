---
title: HoloLens yerelleştirilmiş sürümlerini yükler
description: çince ve japonca sürümleri dahil olmak üzere HoloLens (1. gen) yerelleştirilmiş sürümlerini yüklemeyi öğrenin.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033678"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>HoloLens yerelleştirilmiş sürümlerini (1. gen) yükler

HoloLens çince veya japonca sürümüne geçiş yapmak için Windows cihaz kurtarma aracı 'nı (wdrt) kullanarak bir bilgisayardaki dilin yapısını indirip HoloLens yüklemeniz gerekir.

> [!IMPORTANT]
> HoloLens çince veya japonca derlemeleri yüklemek için wdrt kullanmak, kişisel dosyalar ve ayarlar gibi mevcut verileri HoloLens siler. 

1. bilgisayarınızda [Windows cihaz kurtarma aracı 'nı (wdrt)](https://support.microsoft.com/help/12379)indirip yükleyin.
1. Bilgisayarınıza istediğiniz dilin paketini indirin:  [Basitleştirilmiş Çince](https://aka.ms/hololensdownload-ch) veya [Japonca](https://aka.ms/hololensdownload-jp).
1. İndirme tamamlandığında **Dosya Gezgini**  >  **İndirmeleri**' ni seçin. İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .
1. HoloLens ile birlikte gelen mikro USB kablosunu kullanarak bilgisayarınıza Bağlan. (HoloLens bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)
1. araç HoloLens otomatik olarak algıladıktan sonra Microsoft HoloLens kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi**' ni seçin   ve 4. adımda sıkıştırdığı klasörde bulunan yükleme dosyasını seçin. (". FFU" uzantısına sahip bir dosyayı arayın.) 
1.  **Yazılım yüklemesi** ' ni seçin ve yönergeleri izleyin. 
1. yapı yüklendikten sonra HoloLens kurulum otomatik olarak başlatılır. Cihaza yerleştirin ve kurulum yönergelerini izleyin. 

kurulum ile işiniz bittiğinde **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı**' na gidin ve en son önizleme sürümlerini alacak şekilde yapılandırılıp yapılandırılmadığını denetleyin. ingilizce önizleme yapıları gibi Windows ınsider programı, en son önizleme derlemeleriyle güncel HoloLens çince ve japonca sürümlerini güncel tutar.

> [!NOTE]
>  
> - ingilizce, japonca ve çince arasındaki sistem dilini değiştirmek için Ayarlar uygulamasını kullanamazsınız. Yeni bir derlemeyi yanıp sönen, cihaz sistemi dilini değiştirmek için desteklenen tek yoldur.
> - basitleştirilmiş çince veya japonca metin girmek için ekran üzerindeki Pinyin klavyesini kullanabilir, ancak basitleştirilmiş çince veya japonca metin yazmak için Bluetooth bir donanım klavyesi kullanmak şu anda desteklenmez.  öte yandan, çince veya japonca HoloLens, ingilizce yazmak için bir Bluetooth klavye kullanmaya devam edebilirsiniz (bir donanım klavyesini ingilizce yazmak üzere değiştirmek için ~ tuşuna basın).
