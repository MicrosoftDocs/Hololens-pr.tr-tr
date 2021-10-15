---
title: güncelleştirme HoloLens 2
description: HoloLens yapı numaranızı nasıl denetleyeceğinizi, cihaz güncelleştirmeleriyle güncel tutmaya, ınsiders programına katılmayı ve güncelleştirmeleri geri almayı öğrenin.
keywords: nasıl yapılır, güncelleştirme, geri alma, HoloLens, denetimi oluşturma, derleme numarası
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
ms.openlocfilehash: 49036135ba13a93d2e8be97a7f3a95d50785c5c5
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034272"
---
# <a name="update-hololens-2"></a>güncelleştirme HoloLens 2

## <a name="overview"></a>Genel Bakış

Her zaman yeni özellikler, hata düzeltmeleri ve güvenlik güncelleştirmeleri üzerinde çalışıyoruz. Bu güncelleştirmeler hazırlandığı zaman size bildirilir.

tercihinize bağlı olarak HoloLens, Internet 'e bağlı her seferinde ve hatta bekleme durumunda sistem güncelleştirmelerini otomatik olarak indirip yükler.

HoloLens her zaman güncelleştirildiğinden emin olmak için, onunla birlikte gelen cihazınızın şarj cihazına ile prize takılı bırakın. HoloLens internet 'e bağlanmasını da istiyorsunuz. Bu şekilde, sistem güncelleştirmeleri otomatik olarak indirilir ve yüklenir. 

Windows Update hizmeti ile, hangi cihazların hangi cihazlarda hangilerinin alınacağını gösteren güncelleştirme işleminin birden çok yönünü denetlersiniz. bu denetim, test için HoloLens cihazların bir alt kümesine yönelik güncelleştirmeleri kullanıma sunabileceğinden yararlıdır. Ardından, kalan güncelleştirmelere yönelik güncelleştirmeleri alın. Ya da farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

## <a name="types-of-updates"></a>Güncelleştirme türleri

HoloLens için, iki güncelleştirme türünü otomatik olarak yönetebilirsiniz.

- Özellik güncelleştirmeleri: yılda iki kez serbest bırakıldı.
- Kalite güncelleştirmeleri: kritik güvenlik güncelleştirmelerini dahil edin. Aylık olarak veya gerektiği şekilde serbest bırakılıyordu.

 / Güncelleştirmeleri taramayı, indirmeyi ve yüklemeyi yönetmek için **allowupdate** güncelleştirme ' yi kullanın. 

## <a name="scheduling-updates"></a>Güncelleştirmeleri zamanlama

Ayrıca, bir güncelleştirme zamanlaması da ayarlayabilirsiniz. Belirli bir günde veya her gün, belirli bir zamanda olabilir. Örneğin, 5 p.m. veya etkin saatlerin dışında.

Son olarak, güncelleştirme stratejinizi planlamaya yönelik birkaç sözcük. Güncelleştirme erteleme 'yi destekliyoruz, bu nedenle Microsoft 'un bu güncelleştirmeyi cihazlara yüklemek için bir güncelleştirme yayınladıktan sonra ne kadar bekleneceğini seçebilirsiniz.

Bazen bir şirket her şeyin çalıştığından emin olmak için tüm yeni özellikleri denemek ve destek ekibinin hazırlanabilmesi için yeni güncelleştirmeler hakkında bilgi sahibi olmaları gerekir. Bunların tümünün iyi olduğunu onayladıktan sonra, tüm şirketteki güncelleştirmeleri kullanıma sunırlar. Güncelleştirme halkaları olarak bilinen farklı erteleme ilkeleriyle cihazlarınızın alt kümelerini ilişkilendirerek, kuruluşunuz için bir güncelleştirme dağıtımı stratejisini koordine edebilirsiniz.

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
    1. [Dosyada geri bildirimde](hololens-feedback.md) bulunmak mümkün olduğunca açıklayıcı olmalıdır. Bu başlığı izleyin veya hesabınızı destekle paylaşmak için paylaşma özelliğini kullanın.
    1. [Desteğe](https://aka.ms/hlsupport)başvurun. Sorununuzun önceki bir sürüme dönerek çözülmesi gereken bir sorun varsa, cihazınızı Flash için sizin için bir tane sağlayabilirsiniz.

1. bu işe çalışmadıysanız, [gelişmiş kurtarma yardımcısı ile HoloLens 2](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

Ayrıca, şu anda yüklü olan yayında kalmak isterseniz, güncelleştirmeleri el ile de [duraklatabilirsiniz](hololens-updates.md#pause-updates-via-device). Bu, mühendisliğe sorunu çözmesi için mühendislik ekibi zamanına verecektir.

## <a name="windows-insider-program-on-hololens"></a>Windows HoloLens Insider programı

HoloLens en son özellikleri görmek mi istiyorsunuz?  bu durumda Windows ınsider programına katın; HoloLens yazılım güncelleştirmelerinin önizleme yapılarına genel kullanıma açık olmadan önce erişim alacaksınız.

[Microsoft HoloLens için Windows ınsider önizlemesi alın](hololens-insider.md).