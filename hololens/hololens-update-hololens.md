---
title: güncelleştirme HoloLens 2
description: HoloLens yapı numaranızı nasıl denetleyeceğinizi, cihaz güncelleştirmeleriyle güncel tutmaya, ınsiders programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl yapılır, güncelleştirme, geri alma, HoloLens, denetimi oluşturma, derleme numarası
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662842"
---
# <a name="update-hololens-2"></a>güncelleştirme HoloLens 2

HoloLens, diğer Windows 10 cihazlarda olduğu gibi Windows Update kullanır. HoloLens, bir kez prize takılıyken ve Internet 'e bağlıyken, bekleme durumunda olsa da sistem güncelleştirmelerini otomatik olarak indirip yükleyecek.

bu makalede, için HoloLens araçları izlenecek yol gösterilecektir:

- geçerli işletim sistemi sürümünüzü görüntüleme (derleme numarası)
- Güncelleştirmeler denetleniyor
- HoloLens el ile güncelleştirme
- daha eski bir güncelleştirmeye geri dönme

## <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünüzü denetleyin (derleme numarası)

Ayarlar uygulamasını açıp **sistem** hakkında ' yı seçerek sistem sürüm numarasını (derleme numarası) doğrulayabilirsiniz  >  .

## <a name="check-for-updates-and-manually-update"></a>Güncelleştirmeleri denetle ve el ile Güncelleştir

Ayarlarda dilediğiniz zaman güncelleştirmeleri kontrol edebilirsiniz.  Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri denetlemek için:

1. **Ayarlar** uygulamasını başlatın.
1. **& güvenlik**  >  **Windows Update** güncelleştirme bölümüne gidin.
1. **Güncelleştirmeleri denetle**’yi seçin.

Bir güncelleştirme varsa, yeni sürümü indirmeye başlayacaktır. İndirme işlemi tamamlandıktan sonra yüklemeyi tetiklemek için **Şimdi yeniden Başlat** düğmesini seçin. Cihazınız %40 ' in altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamacaktır.

HoloLens güncelleştirmeyi yüklerken, dönen gears ve ilerleme göstergesi görüntülenir. bu süre boyunca HoloLens kapatmayın. Yüklemeyi tamamladıktan sonra otomatik olarak yeniden başlatılır.

HoloLens tek seferde bir güncelleştirme uygular.  HoloLens en son arka planda birden çok sürümdaysanız, tamamen güncel hale getirmek için güncelleştirme işlemini birden çok kez çalıştırmanız gerekebilir.

## <a name="go-back-to-a-previous-version"></a>Önceki bir sürüme geri dön

bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek isteyebilirsiniz. Önerilen adımlar şunlardır:

1. Sorununuzu giderip çözebilecekleri hakkında bilgi için desteğe başvurun.
    1. **Isteğe bağlı** veya **tam** telemetri etkinleştirildiğinden emin olun; bu durum, mühendislerin tanılanması için daha fazla işlem yapılabilir ve kolay hale gelir.
    1. [Dosya geri bildirimi](hololens-feedback.md) mümkün olduğunca açıklayıcı bir şekilde yapılır. Bilgilerinizi bir yere göz atın veya paylaşma özelliğini kullanarak, hatayı destek ile paylaşabilirsiniz.
    1. [Desteğe](https://aka.ms/hlsupport)başvurun. Sorununuzun önceki bir sürüme dönerek çözülmesi gereken bir sorun varsa, cihazınızı Flash için sizin için bir tane sağlayabilirsiniz.

1. bu işe çalışmadıysanız, [gelişmiş kurtarma yardımcısı ile HoloLens 2 ' yi sıfırlayın veya flash](hololens-recovery.md)'u yeniden yapın.
    1. Bilgisayarınızda, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ' nı Microsoft Store indirin.
    1. bilgisayarınıza takılı telefonlarınızın veya Windows cihazların olmadığından emin olun.
    1. Flash yapmak istediğiniz sürümü seçin:
        1. [en son HoloLens 2 sürümü](https://aka.ms/hololens2download)indirebilirsiniz.
        1. YAY ana bilgisayarlarının varsayılan derlemesini kullanabilirsiniz. (Bu seçeneği belirlerseniz sonraki adımı atlayın.)
        1. Size sağlanmış olan bir yapı desteği kullanabilirsiniz.
    1. Bu İndirmeleri bitirdiğinizde **Dosya Gezgini**  >  **İndirmeleri**' ni açın. İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .
    1. usb-a-usb-C kablosu kullanarak bilgisayarınızı bilgisayarınıza HoloLens Bağlan. (HoloLens bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)
    1. Gelişmiş kurtarma Yardımcısı HoloLens otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
    1. Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve ardından adım 4 ' te sıkıştırmışın klasörde bulunan yükleme dosyasını seçin. (. FFU uzantılı bir dosyayı arayın.)
    1. **Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

Ayrıca, şu anda yüklü olan yayında kalmak isterseniz, güncelleştirmeleri el ile de [duraklatabilirsiniz](hololens-updates.md#pause-updates-via-device). Bu, mühendisliğe sorunu çözmesi için mühendislik ekibi zamanına verecektir.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens Insider programı

HoloLens en son özellikleri görmek mi istiyorsunuz?  bu durumda Windows ınsider programına katın; HoloLens yazılım güncelleştirmelerinin önizleme yapılarına genel kullanıma açık olmadan önce erişim alacaksınız.

[Microsoft HoloLens için Windows ınsider önizlemesi alın](hololens-insider.md).
