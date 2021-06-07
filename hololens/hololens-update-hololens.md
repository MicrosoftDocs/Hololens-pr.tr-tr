---
title: HoloLens'i güncelleştirme
description: HoloLens derleme numaranızı denetlemeyi, cihaz güncelleştirmelerini takip etmeyi, Insiders Programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl güncelleştirmesi, geri alma, HoloLens, derlemeyi denetleme, derleme numarası
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379059"
---
# <a name="update-hololens"></a>HoloLens'i güncelleştirme

HoloLens, Windows Update diğer cihazlarda olduğu gibi Windows 10 kullanır. HoloLens'iniz, hazır bekleyen durumda olsa bile, güç kaynağına takılı ve İnternet'e bağlı olduğunda sistem güncelleştirmelerini otomatik olarak indirir ve yükleyebilir.

Bu makalede, HoloLens araçları şu adımlarda adım adım ilerler:

- geçerli işletim sistemi sürümüm (derleme numarası) görüntüleme
- güncelleştirmeleri denetleme
- HoloLens'i el ile güncelleştirme
- daha eski bir güncelleştirmeye geri dönme

## <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünizi (derleme numarası) denetleme

Ayarlar uygulamasını açarak ve Hakkında Sistem'i seçerek sistem sürüm numarasını (derleme numarası)  >  **doğruabilirsiniz.**

## <a name="check-for-updates-and-manually-update"></a>Güncelleştirmeleri denetleme ve el ile güncelleştirme

Ayarlarda güncelleştirmeleri istediğiniz zaman kontrol edebilirsiniz.  Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri kontrol etmek için:

1. **Ayarlar** uygulamasını başlatın.
1. Update **& Security Windows Update**  >  .
1. **Güncelleştirmeleri denetle**’yi seçin.

Bir güncelleştirme varsa, yeni sürümü indirmeye başlar. İndirme işlemi tamamlandıktan sonra, yüklemeyi **tetiklemek için** Şimdi Yeniden Başlat düğmesini seçin. Cihazınız %40'ın altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamaz.

HoloLens güncelleştirmeyi yüklerken dönen dişliler ve ilerleme göstergesi görüntülenir. HoloLens'inizi bu süre boyunca kapatabilirsiniz. Yükleme tamamlandıktan sonra otomatik olarak yeniden başlatılır.

HoloLens aynı anda bir güncelleştirme uygular.  HoloLens'iniz en son sürümün arkasında birden fazla sürüm varsa, güncelleştirme işlemini tamamen güncel hale getirmek için birden çok kez çalıştırmanız gerekir.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Geri dön bir sürüme - HoloLens 2

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek istiyor olabilir. HoloLens'inizi önceki sürüme sıfırlamak için Gelişmiş Kurtarma Yardımcı'yı kullanarak bunu yapabiliriz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

HoloLens 2'nin önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows cihazına sahip olmadığınızdan emin olun.
1. Bilgisayarınızda, Gelişmiş Kurtarma [Yardımcı'sı'Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)
1. En son [HoloLens 2 yayınlarını indirin.](https://aka.ms/hololens2download)
1. Bu indirmeleri bitirdikten sonra Dosya Gezgini **İndirmeleri'ni**  >  **açın.** Az önce indirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.
1. HoloLens'i USB-A'den USB-C'ye kablo kullanarak bilgisayarınıza bağlayın. (HoloLens'inizi bağlamak için başka kablolar kullanıyorsanız bile bu en iyi şekilde çalışır.)
1. Gelişmiş Kurtarma Yardımcı, HoloLens'inizi otomatik olarak algılar. Yeni **kutucuğu Microsoft HoloLens** seçin.
1. Sonraki ekranda El ile paket **seçimi'ne** tıklayın ve ardından 4. adımda sıkıştırmayı açmak istediğiniz klasörde yer alan yükleme dosyasını seçin. (.ffu uzantısına sahip bir dosya bulun.)
1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Geri dön bir sürüme - HoloLens (1. Nesil)

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek istiyor olabilir. HoloLens'inizi önceki sürüme sıfırlamak için Windows Cihaz Kurtarma Aracı'nı kullanarak bunu kullanabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

HoloLens 1'in önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows cihazına sahip olmadığınızdan emin olun.
1. Bilgisayarınızda Windows Cihaz Kurtarma [Aracı'nı (WDRT) indirin.](https://support.microsoft.com/help/12379)
1. [HoloLens Yıldönümü Güncelleştirmesi kurtarma paketini indirin.](https://aka.ms/hololensrecovery)
1. İndirmeler tamam olduğunda Dosya Gezgini **İndirmeleri'ni**  >  **açın.** Az önce indirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.
1. HoloLens'inizi, birlikte gelen mikro USB kablosunu kullanarak bilgisayarınıza bağlayın. (HoloLens'inizi bağlamak için başka kablolar kullanıyorsanız bile bu en iyi şekilde çalışır.)
1. WDRT, HoloLens'inizi otomatik olarak algılar. Yeni **kutucuğu Microsoft HoloLens** seçin.
1. Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve 4. adımda sıkıştırmayı açmak istediğiniz klasörde yer alan yükleme dosyasını seçin. (.ffu uzantısına sahip bir dosya bulun.)
1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

> [!NOTE]
> WDRT HoloLens'inizi algılamazsa bilgisayarınızı yeniden başlatmayı deneyin. Bu işe uymazsa Cihazım algılanmadı'yi **seçin,** **Microsoft HoloLens'ı** seçin ve yönergeleri izleyin.

## <a name="windows-insider-program-on-hololens"></a>HoloLens Windows Insider Programı de sanal

HoloLens'in en son özelliklerini görmek ister misiniz?  Öyleyse, aşağıdaki Windows Insider Programı; Genel kamuya açık olmadan önce HoloLens yazılım güncelleştirmelerinin önizleme derlemelerine erişeceksiniz.

[Microsoft HoloLens için Windows Insider önizlemesini Microsoft HoloLens.](hololens-insider.md)
