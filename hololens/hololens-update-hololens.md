---
title: Güncelleştirme HoloLens 2
description: Derleme numaranızı denetlemeyi, HoloLens güncelleştirmeleri takip etmeyi, Insiders Programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl güncelleştirmesi, geri alma, geri alma, HoloLens, derlemeyi denetleme, derleme numarası
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151691"
---
# <a name="update-hololens-2"></a>Güncelleştirme HoloLens 2

## <a name="overview"></a>Genel Bakış

Her zaman yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri üzerinde çalışıyoruz. Bu güncelleştirmeler hazır olduğunda size bildirilecek.

Tercihlerinize bağlı olarak, HoloLens, İnternet'e bağlı ve hatta beklemede olduğunda sistem güncelleştirmelerini otomatik olarak indirir ve yükleyebilir.

Cihazınızın her HoloLens güncelleştirilmiş olduğundan emin olmak için, yanında gelen aleti takılı bırakın. Ayrıca, ağ HoloLens İnternet'e bağlanmalarını da istiyor. Bu şekilde sistem güncelleştirmeleri otomatik olarak indirilir ve yüklenir. 

Güncelleştirme Windows ile, güncelleştirme işleminin hangi cihazların hangi güncelleştirmeleri hangi zamanda alaları olduğu gibi birden çok yönü denetlemeniz gerekir. Bu denetim, güncelleştirmeleri test etmek için belirli cihazların bir alt kümesine HoloLens yardımcı olur. Ardından, kalanlara güncelleştirmeleri dışarı alın. Veya farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

## <a name="types-of-updates"></a>Güncelleştirme türleri

Daha HoloLens için iki tür güncelleştirmeyi otomatik olarak yönetabilirsiniz.

- Özellik güncelleştirmeleri: yılda iki kez yayınlandı.
- Kalite güncelleştirmeleri: Kritik güvenlik güncelleştirmelerini dahil edin. Bunlar aylık olarak veya gerektiğinde yayımlar.

Güncelleştirmeleri  / tarama, indirme ve yükleme işlemini yönetmek için **AllowAutoUpdate** Güncelleştirmesini kullanın. 

## <a name="scheduling-updates"></a>Güncelleştirmeleri zamanlama

Ayrıca bir güncelleştirme zamanlaması da ayarlayın. Belirli bir günde veya her gün belirli bir zamanda olabilir. Örneğin, saat 17:00'de veya etkin saatlerin dışında.

Son olarak, güncelleştirme stratejinizi planlama hakkında birkaç sözcük. Güncelleştirme ertelemelerini destekliyoruz, bu nedenle Microsoft'un bu güncelleştirmeyi cihazlara yüklemek için bir güncelleştirmeyi yayından sonra ne kadar bekleyeceğine karar ve ardından siz karar ve verirsiniz.

Bazen bir şirket, her şeyin çalışır olduğundan emin olmak için önce tüm yeni özellikleri denemek ve destek ekibinin hazırlıklı olmak için yeni güncelleştirmelere aşina olmak için bu özellikleri denemeyi dener. Her şey iyi olduğunu onaylandıktan sonra güncelleştirmeleri şirketin tamamına iletir. Cihaz kümelerinizi farklı erteleme ilkeleriyle (güncelleştirme halkaları olarak bilinir) bağ bağarak, bir güncelleştirmenin kuruluşa yönelik bir rollout stratejisini koordine edin.

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

Güncelleştirme HoloLens yüklerken dönen dişliler ve ilerleme göstergesi görüntülenir. Bu süre boyunca HoloLens kapatabilirsiniz. Yükleme tamamlandıktan sonra otomatik olarak yeniden başlatılır.

HoloLens bir güncelleştirme uygular.  En HoloLens sürümün arkasında birden fazla sürüm varsa, güncelleştirme işlemini tamamen güncel hale almak için birden çok kez çalıştırmanız gerekir.

### <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünizi (derleme numarası) denetleme

Sistem sürüm numarasını (derleme numarası) doğrulamak için şu Ayarlar **Sistem** **Hakkında'yi**  >  **seçin.**

### <a name="go-back-to-a-previous-version"></a>Geri dön önceki bir sürüme

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek HoloLens. Önerilen adımlar:

1. Sorunlarınızı düzeltebilirler mi diye görmek için Destek'e başvurun.
    1. İsteğe **Bağlı** veya **Tam** telemetri'nin etkinleştirildiğinden emin olun. Bu, hatanızı daha eyleme değiştirilebilir ve mühendislerin tanılamasını kolaylaştırır.
    1. Dosya [Geri Bildirimi'ne](hololens-feedback.md) mümkün olduğunca açıklayıcı olun. Başlığı not alır veya hatanızı Destek ile paylaşabilirsiniz.
    1. De [destekle iletişime geçin.](https://aka.ms/hlsupport) Sorun önceki bir sürüme dönerek çözülmesi gereken bir sorunsa, cihazınızı yanıp söndürecek FFU'ları sağlar.

1. Alternatif olarak, Gelişmiş [Kurtarma Yardımcısı ile HoloLens 2'nize ters eğik çizgi HoloLens.](hololens-recovery.md#clean-reflash-the-device)
    1.  Hangi sürüme flash yapmak istediğinizi seçin: 
        1.  En son [2 sürümü HoloLens indirebilirsiniz.](https://aka.ms/hololens2download)
        1.  ARC konakları için varsayılan derlemeyi kullanabilirsiniz.
        1.  Size sağlanan bir derleme Desteği kullanabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

Ayrıca, o anda yüklü olan sürümüne devam etmek için güncelleştirmeleri el ile [duraklatabilirsiniz.](hololens-updates.md#pause-updates-via-device) Bu, Mühendislik Ekibine sorunu çözmesi için zaman ve verecek.

## <a name="windows-insider-program-on-hololens"></a>Windows Insider Programı üzerinde HoloLens

HoloLens'daki en son özellikleri görmek HoloLens?  Öyleyse, Windows Insider Programı; Yazılım güncelleştirmelerinin genel erişime açık HoloLens önizleme derlemelerine erişin.

[Microsoft HoloLens için Windows Insider önizlemesini Microsoft HoloLens.](hololens-insider.md)