---
title: güncelleştirme HoloLens 2
description: HoloLens yapı numaranızı nasıl denetleyeceğinizi, cihaz güncelleştirmeleriyle güncel tutmaya, ınsiders programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl yapılır, güncelleştirme, geri alma, HoloLens, denetimi oluşturma, derleme numarası
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427911"
---
# <a name="update-hololens-2"></a>güncelleştirme HoloLens 2

## <a name="overview"></a>Genel Bakış

Her zaman yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri üzerinde çalışıyoruz. Bu güncelleştirmeler hazırlandığı zaman size bildirilir.

tercihinize bağlı olarak, HoloLens güç, Internet 'e bağlı her seferinde ve hatta bekleme durumunda sistem güncelleştirmelerini otomatik olarak indirip yükler.

HoloLens her zaman güncelleştirildiğinden emin olmak için, onunla birlikte gelen cihazınızın şarj cihazına ile prize takılı bırakın. HoloLens internet 'e bağlanmasını da istiyorsunuz. Bu şekilde, sistem güncelleştirmeleri otomatik olarak indirilir ve yüklenir. 

Windows Update hizmeti ile, hangi cihazların hangi cihazlarda hangilerinin alınacağını gösteren güncelleştirme işleminin birden çok yönünü denetlersiniz. bu denetim, test için HoloLens cihazların bir alt kümesine yönelik güncelleştirmeleri kullanıma sunabileceğinden yararlıdır. Ardından, kalan güncelleştirmelere yönelik güncelleştirmeleri alın. Ya da farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

## <a name="types-of-updates"></a>Güncelleştirme türleri

HoloLens için, iki güncelleştirme türünü otomatik olarak yönetebilirsiniz. 

- Özellik güncelleştirmeleri: yılda iki kez serbest bırakıldı.
- Kalite güncelleştirmeleri: kritik güvenlik güncelleştirmelerini dahil edin. Aylık olarak veya gerektiği şekilde serbest bırakılıyordu.

 / Güncelleştirmeleri taramayı, indirmeyi ve yüklemeyi yönetmek için **allowupdate** güncelleştirme ' yi kullanın. 

## <a name="scheduling-updates"></a>Güncelleştirmeleri zamanlama

Ayrıca, bir güncelleştirme zamanlaması da ayarlayabilirsiniz. Belirli bir günde veya her gün, belirli bir zamanda olabilir. Örneğin, 5 p.m. veya etkin saatlerin dışında.

Son olarak, güncelleştirme stratejinizi planlamaya yönelik birkaç sözcük. Güncelleştirme ertelemeyi destekliyoruz. Bu nedenle, Microsoft 'un bu güncelleştirmeyi cihazlara yüklemek için bir güncelleştirme yayınladıktan sonra ne kadar bekleneceğini seçebilirsiniz.

Bazen, bir şirket her şeyin çalıştığından emin olmak için tüm yeni özellikleri denemek ve destek ekibinin hazırlanabilmesi için yeni güncelleştirmeler hakkında bilgi sahibi olmaları gerekir. Bunların tümünün iyi olduğunu onayladıktan sonra, tüm şirketteki güncelleştirmeleri kullanıma sunırlar. Güncelleştirme halkaları olarak bilinen farklı erteleme ilkeleriyle cihazlarınızın alt kümelerini ilişkilendirerek, kuruluşunuz için bir güncelleştirme dağıtımı stratejisini koordine edebilirsiniz.

## <a name="hololens-update-tools"></a>HoloLens güncelleştirme araçları

bu bölüm, için HoloLens araçları konusunda size kılavuzluk eder:

- Güncelleştirmeler denetleniyor
- HoloLens el ile güncelleştirme
- geçerli işletim sistemi sürümünüzü görüntüleme (derleme numarası)
- daha eski bir güncelleştirmeye geri dönme

### <a name="check-for-updates-and-manually-update"></a>Güncelleştirmeleri denetle ve el ile Güncelleştir

Ayarlar ' da dilediğiniz zaman güncelleştirmeleri denetleyebilirsiniz.  Kullanılabilir güncelleştirmeleri görmek ve yeni güncelleştirmeleri denetlemek için:

1. **Ayarlar** uygulamasını başlatın.
1. **& güvenlik**  >  **Windows Update** güncelleştirme bölümüne gidin.
1. **Güncelleştirmeleri denetle**’yi seçin.

Bir güncelleştirme varsa, yeni sürümü indirmeye başlayacaktır. İndirme işlemi tamamlandıktan sonra yüklemeyi tetiklemek için **Şimdi yeniden Başlat** düğmesini seçin. Cihazınız %40 ' in altında ve takılı değilse, yeniden başlatma güncelleştirmeyi yüklemeye başlamacaktır.

HoloLens güncelleştirmeyi yüklerken, dönen gears ve ilerleme göstergesi görüntülenir. bu süre boyunca HoloLens kapatmayın. Yüklemeyi tamamladıktan sonra otomatik olarak yeniden başlatılır.

HoloLens tek seferde bir güncelleştirme uygular.  HoloLens en son arka planda birden çok sürümdaysanız, tam olarak güncel olması için güncelleştirme işlemini birden çok kez çalıştırmanız gerekebilir.

### <a name="check-your-operating-system-version-build-number"></a>İşletim sistemi sürümünüzü denetleyin (derleme numarası)

**Ayarlar** açıp **sistem** hakkında ' yı seçerek sistem sürüm numarasını (derleme numarası) doğrulayabilirsiniz  >  .

### <a name="go-back-to-a-previous-version"></a>Önceki bir sürüme geri dön

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
    1. Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve ardından adım 4 ' te sıkıştırmışın klasörde bulunan yükleme dosyasını seçin. (Uzantıya sahip bir dosya bulun `.ffu` .)
    1. **Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

Ayrıca, şu anda yüklü olan yayında kalmak isterseniz, güncelleştirmeleri el ile de [duraklatabilirsiniz](hololens-updates.md#pause-updates-via-device). Bu, mühendisliğe sorunu çözmesi için mühendislik ekibi zamanına verecektir.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens Insider programı

HoloLens en son özellikleri görmek mi istiyorsunuz?  bu durumda Windows ınsider programına katın; HoloLens yazılım güncelleştirmelerinin önizleme yapılarına genel kullanıma açık olmadan önce erişim alacaksınız.

[Microsoft HoloLens için Windows ınsider önizlemesi alın](hololens-insider.md).