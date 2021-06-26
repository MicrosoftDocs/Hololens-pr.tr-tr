---
title: HoloLens 2 güncelleştirme
description: HoloLens derleme numaranızı nasıl denetleyeceğinizi, cihaz güncelleştirmeleriyle güncel tutmanın yanı sıra Insider programı programına katılıp güncelleştirmeleri geri alma hakkında bilgi edinin.
keywords: Nasıl yapılır, güncelleştirme, geri alma, HoloLens, denetim oluşturma, derleme numarası
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
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924120"
---
# <a name="update-hololens-2"></a>HoloLens 2 güncelleştirme

HoloLens, diğer Windows 10 cihazlarında olduğu gibi Windows Update kullanır. HoloLens 'niz, bekleyen bir yerde olsa bile, Internet 'e bağlıyken ve Internet 'e bağlandığında sistem güncelleştirmelerini otomatik olarak indirip yükler.

Bu makale, için HoloLens araçları aracılığıyla izlenecek:

- geçerli işletim sistemi sürümünüzü görüntüleme (derleme numarası)
- Güncelleştirmeler denetleniyor
- HoloLens 'i el ile güncelleştirme
- daha eski bir güncelleştirmeye geri dönme

## <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünüzü denetleyin (derleme numarası)

Ayarlar uygulamasını açıp **sistem** hakkında ' yı seçerek sistem sürüm numarasını (derleme numarası) doğrulayabilirsiniz  >  .

## <a name="check-for-updates-and-manually-update"></a>Güncelleştirmeleri denetle ve el ile Güncelleştir

Ayarlarda dilediğiniz zaman güncelleştirmeleri kontrol edebilirsiniz.  Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri denetlemek için:

1. **Ayarlar** uygulamasını başlatın.
1. **& güvenlik**  >  **Windows Update** güncelleştirme bölümüne gidin.
1. **Güncelleştirmeleri denetle**’yi seçin.

Bir güncelleştirme varsa, yeni sürümü indirmeye başlayacaktır. İndirme işlemi tamamlandıktan sonra yüklemeyi tetiklemek için **Şimdi yeniden Başlat** düğmesini seçin. Cihazınız %40 ' in altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamacaktır.

HoloLens, güncelleştirmeyi yüklerken, dönen Gears ve ilerleme göstergesi görüntülenir. Bu süre boyunca HoloLens 'i kapatmayın. Yüklemeyi tamamladıktan sonra otomatik olarak yeniden başlatılır.

HoloLens tek seferde bir güncelleştirme uygular.  HoloLens uygulamanız en son arka planda birden fazla sürümdaysanız, tam olarak güncel olması için güncelleştirme işlemini birden çok kez çalıştırmanız gerekebilir.

## <a name="go-back-to-a-previous-version"></a>Önceki bir sürüme geri dön

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek isteyebilirsiniz. Önerilen adımlar şunlardır:

1. Sorununuzu giderip çözebilecekleri hakkında bilgi için desteğe başvurun.
    1. **Isteğe bağlı** veya **tam** telemetri etkinleştirildiğinden emin olun; bu durum, mühendislerin tanılanması için daha fazla işlem yapılabilir ve kolay hale gelir.
    1. [Dosya geri bildirimi](hololens-feedback.md) mümkün olduğunca açıklayıcı bir şekilde yapılır. Bilgilerinizi bir yere göz atın veya paylaşma özelliğini kullanarak, hatayı destek ile paylaşabilirsiniz.
    1. [Desteğe](https://aka.ms/hlsupport)başvurun. Sorununuzun önceki bir sürüme dönerek çözülmesi gereken bir sorun varsa, cihazınızı Flash için sizin için bir tane sağlayabilirsiniz.

1. Bu işe çalışmadıysanız, [HoloLens 2 ' yi Gelişmiş kurtarma Yardımcısı ile sıfırlayın veya](hololens-recovery.md)yeniden yapın.
    1. Bilgisayarınızda, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ' nı Microsoft Store indirin.
    1. Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarının olmadığından emin olun.
    1. Flash yapmak istediğiniz sürümü seçin:
        1. [En son HoloLens 2 sürümünü](https://aka.ms/hololens2download)indirebilirsiniz.
        1. YAY ana bilgisayarlarının varsayılan derlemesini kullanabilirsiniz. (Bu seçeneği belirlerseniz sonraki adımı atlayın.)
        1. Size sağlanmış olan bir yapı desteği kullanabilirsiniz.
    1. Bu İndirmeleri bitirdiğinizde **Dosya Gezgini**  >  **İndirmeleri**' ni açın. İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .
    1. USB-A-USB-C kablosu kullanarak HoloLens 'nizi bilgisayarınıza bağlayın. (HoloLens 'nizi bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)
    1. Gelişmiş kurtarma Yardımcısı, HoloLens 'nizi otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
    1. Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve ardından adım 4 ' te sıkıştırmışın klasörde bulunan yükleme dosyasını seçin. (. FFU uzantılı bir dosyayı arayın.)
    1. **Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

Ayrıca, şu anda yüklü olan yayında kalmak isterseniz, güncelleştirmeleri el ile de [duraklatabilirsiniz](hololens-updates.md#pause-updates-via-device). Bu, mühendisliğe sorunu çözmesi için mühendislik ekibi zamanına verecektir.

## <a name="windows-insider-program-on-hololens"></a>HoloLens üzerinde Windows Insider programı

HoloLens 'te en son özellikleri görmek mi istiyorsunuz?  Öyleyse, Windows Insider programına katılarak; HoloLens yazılım güncelleştirmelerinin önizleme yapılarına genel kullanıma açık olmadan önce erişim sağlayacaksınız.

[Microsoft HoloLens Için Windows Insider Preview](hololens-insider.md)' i alın.
