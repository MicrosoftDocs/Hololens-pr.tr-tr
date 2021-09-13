---
title: Güncelleştirme HoloLens 2
description: Derleme numaranızı denetlemeyi, HoloLens güncelleştirmeleri takip etmeyi, Insiders Programına katılmayı ve güncelleştirmeleri geri alma hakkında bilgi alın.
keywords: nasıl güncelleştirmesi, geri alma, geri alma, HoloLens, derlemeyi denetleme, derleme numarası
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033822"
---
# <a name="update-hololens-2"></a>Güncelleştirme HoloLens 2

## <a name="overview"></a>Genel Bakış

Her zaman yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri üzerinde çalışıyoruz. Bu güncelleştirmeler hazır olduğunda size bildirilecek.

Tercihlerinize bağlı olarak, HoloLens, İnternet'e bağlı ve hatta beklemede olduğunda sistem güncelleştirmelerini otomatik olarak indirir ve yükleyebilir.

Cihazınızın her HoloLens güncelleştirilmiş olduğundan emin olmak için, onu yanında gelen aletin takılı bırakın. Ayrıca, ağ HoloLens İnternet'e bağlanmalarını da istiyor. Bu şekilde sistem güncelleştirmeleri otomatik olarak indirilir ve yüklenir. 

Güncelleştirme Windows ile, güncelleştirme işleminin hangi cihazların hangi güncelleştirmeleri hangi zamanda alalı olduğu gibi birden çok yönü denetlemeniz gerekir. Bu denetim, güncelleştirmeleri test etmek için belirli cihazların bir alt kümesine HoloLens yardımcı olur. Ardından, kalanlara güncelleştirmeleri dışarı alın. Veya farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

## <a name="types-of-updates"></a>Güncelleştirme türleri

Bu HoloLens iki tür güncelleştirmeyi otomatik olarak yönetsiniz. 

- Özellik güncelleştirmeleri: yılda iki kez yayınlandı.
- Kalite güncelleştirmeleri: Kritik güvenlik güncelleştirmelerini dahil edin. Bunlar aylık olarak veya gerektiğinde yayımlar.

Güncelleştirmeleri  / tarama, indirme ve yükleme işlemini yönetmek için **AllowAutoUpdate** Güncelleştirmesini kullanın. 

## <a name="scheduling-updates"></a>Güncelleştirmeleri zamanlama

Ayrıca bir güncelleştirme zamanlaması da ayarlayın. Belirli bir günde veya her gün belirli bir zamanda olabilir. Örneğin, saat 17:00'de veya etkin saatlerin dışında.

Son olarak, güncelleştirme stratejinizi planlama hakkında birkaç sözcük. Güncelleştirme ertelemelerini destekliyoruz. Bu nedenle, Microsoft bu güncelleştirmeyi cihazlara yüklemek için bir güncelleştirme yayınladikten sonra ne kadar bekleyeceğinizi siz de karar veebilirsiniz.

Bazen bir şirket, her şeyin çalışır olduğundan emin olmak için önce tüm yeni özellikleri denemek ve destek ekibinin hazırlıklı olmak için yeni güncelleştirmeleri tanımayı dener. Her şey iyi olduğunu onaylandıktan sonra güncelleştirmeleri şirketin tamamına iletir. Cihaz kümelerinizi farklı erteleme ilkeleriyle (güncelleştirme halkaları olarak bilinir) bağ bağarak, bir güncelleştirmenin kuruluşa yönelik bir rollout stratejisini koordine edin.

## <a name="hololens-update-tools"></a>HoloLens güncelleştirme araçları

Bu bölüm, şu araçlar için HoloLens adım adım size yol sunar:

- güncelleştirmeleri denetleme
- el ile güncelleştirme HoloLens
- geçerli işletim sistemi sürümüm (derleme numarası) görüntüleme
- daha eski bir güncelleştirmeye geri dönme

### <a name="check-for-updates-and-manually-update"></a>Güncelleştirmeleri denetleme ve el ile güncelleştirme

Ayarlarda dilediğiniz zaman güncelleştirmeleri kontrol edebilirsiniz.  Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri kontrol etmek için:

1. **Ayarlar** uygulamasını başlatın.
1. Update **& Security**  >  **Windows Update 'e gidin.**
1. **Güncelleştirmeleri denetle**’yi seçin.

Bir güncelleştirme varsa, yeni sürümü indirmeye başlar. İndirme işlemi tamamlandıktan sonra, yüklemeyi **tetiklemek için** Şimdi Yeniden Başlat düğmesini seçin. Cihazınız %40'ın altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamaz.

Güncelleştirme HoloLens çalışırken dönen dişliler ve ilerleme göstergesi görüntülenir. Bu süre boyunca HoloLens kapatabilirsiniz. Yükleme tamamlandıktan sonra otomatik olarak yeniden başlatılır.

HoloLens bir güncelleştirme uygular.  En HoloLens sürümün arkasında birden fazla sürüm varsa, güncelleştirme işlemini tamamen güncel hale almak için birden çok kez çalıştırmanız gerekir.

### <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünizi (derleme numarası) denetleme

Sistem sürüm numarasını (derleme numarası) doğrulamak için, Ayarlar **sistem** **hakkında'ı**  >  **seçin.**

### <a name="go-back-to-a-previous-version"></a>Geri dön önceki bir sürüme

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek HoloLens. Önerilen adımlar:

1. Sorunlarınızı düzeltebilirler mi diye görmek için Destek'e başvurun.
    1. İsteğe **Bağlı** veya **Tam** telemetri'nin etkinleştirildiğinden emin olun. Bu, hatanızı daha eyleme değiştirilebilir ve mühendislerin tanılamasını kolaylaştırır.
    1. [Dosya Geri Bildirimi](hololens-feedback.md) mümkün olduğunca açıklayıcıdır. Hatanızı Destek ile paylaşabilirsiniz.
    1. De [destekle iletişime geçin.](https://aka.ms/hlsupport) Sorun önceki bir sürüme dönerek çözülmesi gereken bir sorunsa, cihazınızı yanıp söndürecek FFU'ları sağlar.

1. Bu işe çalışmıyorsa, Gelişmiş Kurtarma Yardımcısı ile [HoloLens 2'nizi sıfırlayın veya ters eğik çizgiyle silin.](hololens-recovery.md)
    1. Bilgisayarınızda, dosyadan [Gelişmiş Kurtarma Yardımcı'Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)
    1. Bilgisayarınıza takılı telefon veya Windows emin olun.
    1. Hangi sürüme flash yapmak istediğinizi seçin:
        1. En son [2 sürümü HoloLens indirebilirsiniz.](https://aka.ms/hololens2download)
        1. ARC konakları için varsayılan derlemeyi kullanabilirsiniz. (Bu seçeneği seçerseniz sonraki adımı atlayabilirsiniz.)
        1. Size sağlanan bir derleme Desteği kullanabilirsiniz.
    1. Bu indirmeleri tamamladikten sonra İndirmeler **Dosya Gezgini**  >  **açın.** İndirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.
    1. Bağlan USB-HoloLens USB-C kablosu kullanarak bilgisayarınıza bağlanın. (Bağlantınızı bağlamak için başka kablolar kullansanız bile HoloLens bu en iyi şekilde çalışır.)
    1. Gelişmiş Kurtarma Yardımcısı, kullanıcılarınızı otomatik olarak HoloLens. Yeni **kutucuğu Microsoft HoloLens** seçin.
    1. Sonraki ekranda El ile paket **seçimi'ne** tıklayın ve ardından 4. adımda sıkıştırmayı açmak istediğiniz klasörde bulunan yükleme dosyasını seçin. (Uzantılı bir dosya `.ffu` bulun.)
    1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

Ayrıca, o anda yüklü olan sürümüne devam etmek için güncelleştirmeleri el ile [duraklatabilirsiniz.](hololens-updates.md#pause-updates-via-device) Bu, Mühendislik Ekibine sorunu çözmesi için zaman ve verecek.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Programı üzerinde HoloLens

HoloLens'daki en son özellikleri görmek HoloLens?  Öyleyse, Windows Insider Programı; Yazılım güncelleştirmelerinin genel erişime açık HoloLens önizleme derlemelerine erişin.

[Windows için Insider önizlemesini Microsoft HoloLens.](hololens-insider.md)