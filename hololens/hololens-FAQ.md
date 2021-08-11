---
title: HoloLens cihazlar ve hologramlar hakkında sık sorulan sorular
description: HoloLens veya hologramlar ile etkileşim kurma hakkında hızlı bir sorunuz mu var?  Bu makale, hızlı bir yanıt ve daha fazla kaynak sağlar.
keywords: Hololens, SSS, bilinen sorun, yardım
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664630"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramlar ve etkileşimler sorunlarını giderme

Bu makalede hologramlar yerleştirme, boşluklarla çalışma ve hologramlar ile sorunları bildirme konularında sorunlar sorunu giderir.

Her zaman sorun yaşadığınızdan emin olun:
- Bunun düzeltme yapıp yapamadığını görmek için [yeniden başlatmayı](hololens-restart-recover.md) deneyin.
- sorun gidermeye başlamadan önce HoloLens [ücretlendirildiğinden](hololens2-charging.md) emin olun (en az bir saat ücretlendirilir). 


Sorun hakkında bize bilgi göndermek için lütfen geri bildirim uygulamasını kullanın. Geri bildirim uygulamasını [ **Başlangıç** menüsünde](holographic-home.md)bulabilirsiniz. 

HoloLens nasıl aşılabilecek hakkında ipuçları için bkz. [sığdırma](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Yeni boşluklar oluşturulamıyor](#new-spaces-cant-be-created)
- [Boşluk tanımlanamıyor veya yüklenemiyor](#spaces-cant-be-identified-or-loaded)
- [Tüm boşluklar silinsin mi Nasıl yaparım??](#how-do-i-delete-all-spaces)
- [Hologramlar sağa bakmayın veya hareket ettirmeyin](#holograms-dont-look-right-or-are-moving-around)
- ["Alanınızı bulma" iletisi](#finding-your-space-message)
- [Beklenen hologram boşluk içinde gösterilmiyor](#expected-holograms-arent-showing-in-my-space)
- [Hologragram yerleştirilemez veya daha önce yerleştirilmiş hologramlar bölümüne bakın](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramlar kaybolur veya diğer hologramlar ya da nesnelerde kullanılır](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramlar, bir duvar 'nin diğer tarafında görünür](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Bir duvarda bir hologram yerleştirdikten sonra float görünüyor](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Uygulamalar, taşıdıktan sonra çok yakın görünüyor](#apps-appear-too-close-after-moving-them)
- [Kararsız veya kesin hologramlar ile ilgili sorunları bildirme](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Yeni boşluklar oluşturulamıyor

En olası sorun, depolama alanını azaldığımyız. [Disk alanını boşaltın](hololens-troubleshooting.md#low-disk-space-error) ve sonra yeniden deneyin.

[Listeye geri dön](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Boşluk tanımlanamıyor veya yüklenemiyor

HoloLens, otomatik olarak kullandığınız alanı tanımlayamıyor ve yükleyemezseniz aşağıdaki faktörleri kontrol edin:

- Wi-Fi bağlı olduğunuzdan emin olun
- Odada birçok ışık olduğundan emin olun
- Büyük bir değişiklik olmadığından emin olun.

ayrıca, **Ayarlar**  >  **sistem**  >  **alanları**' na giderek bir alanı el ile yükleyebilir veya boşluklardan yönetebilirsiniz.

[Listeye geri dön](#list)

## <a name="how-do-i-delete-all-spaces"></a>Tüm boşluklar silinsin mi Nasıl yaparım??

*Çok yakında*

[Listeye geri dön](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramlar sağa bakmayın veya hareket ettirmeyin

Hologramlar doğru görünmüyorsa (örneğin, jeklik veya titremesi veya üzerine siyah düzeltme ekleri görürseniz), bu düzeltmelerden birini deneyin:

- [Cihaz vizörü](hololens1-hardware.md#care-and-cleaning) ' nı temizleyin ve sensörlerden herhangi bir şeyin engellenmediğinden emin olun.
- Çok sayıda doğrudan güneş olmayan, iyi bir odakla olduğunuzdan emin olun.
- HoloLens, bunları daha fazla tarayabilmesi için katarlarınızın etrafında yürüme ve gatayı deneyin.
- Birçok hologragram yerleştirdiyseniz, bazılarını kaldırmayı deneyin.

Hala sorun yaşıyorsanız, ayarlama uygulamasını çalıştırmaya çalışılıyor. bu uygulama, hologradıklarınızın en iyi şekilde bakmasına yardımcı olmak için HoloLens yalnızca sizin için uygun şekilde ayarlayabilirsiniz. bunu yapmak için **Ayarlar**  >  **sistem**  >  **yardımcı programlarına** gidin. **Ayar**' ın altında, **ayarlamayı aç**' ı seçin.

[Listeye geri dön](#list)

## <a name="finding-your-space-message"></a>"Alanınızı bulma" iletisi

HoloLens bir alanı öğrenirken veya yüklerken, "alanınızı bulma" ifadesini belirten kısa bir ileti görebilirsiniz. bu ileti birkaç saniyeden uzun bir süre görüntülüyorsa, "hâlâ alanınızı arıyor" yazan Başlat menüsü altında başka bir ileti görürsünüz.

bu iletiler HoloLens alanınızı eşlerken sorun yaşadığını ifade eden anlamına gelir. Bu durumda, uygulamaları açabilirsiniz, ancak ortamınızda hologragram yerleştirebilirsiniz.

Bu iletileri sık görüyorsanız, aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Çok sayıda doğrudan güneş olmayan, iyi bir odakla olduğunuzdan emin olun.
- Cihazınızın vizörü 'in temiz olduğundan emin olun. [Vizörü ' inizi temizlemeyi öğrenin](hololens1-hardware.md#care-and-cleaning).
- Güçlü bir Wi-Fi sinyaliniz olduğundan emin olun. Wi-Fi veya zayıf Wi-Fi sinyali olmayan yeni bir ortam girerseniz, HoloLens alanınızı bulamayacaktır.   >  **ağ &amp; ınternet**  >  **Wi-Fi** Ayarlar giderek Wi-Fi bağlantınızı denetleyin.
- Daha yavaş geçmeyi deneyin.

[Listeye geri dön](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Beklenen hologram boşluk içinde gösterilmiyor

Yerleştirdiğiniz hologratonları görmüyorsanız veya beklemediğinizi belirten bir veya daha fazla düzeltmeyi deneyin:

- Bazı ışıkları açın. HoloLens, doğru bir alanda en iyi şekilde işe yarar.
- **Ayarlar**  >  **sistem**  >  **Hologramlar**  >  **yakın hologragram kaldırmak** için ihtiyacınız olmayan hologragram 'yi kaldırın. Ya da gerekirse **Tüm hologramlar kaldır**' ı seçin.

  > [!NOTE]
  > Alanınızdaki düzen veya aydınlatma önemli ölçüde değişiyorsa, cihazınız alanınızı tanımlama ve hologramlar gösterme konusunda sorun yaşıyor olabilir.

[Listeye geri dön](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Hologragram yerleştirilemez veya daha önce yerleştirilmiş hologramlar bölümüne bakın

HoloLens alanınızı eşleyebilir veya yükleyemediği takdirde, sınırlı moda girer ve yerleştirdiğiniz hologramlar yapamaz veya yerleştirdiğiniz hologramlar göremez. İşte deneyebileceğiniz bazı çözümler:

- HoloLens, ortamınızda, alanı görebilmesi ve eşlemek için yeterli ışık olduğundan emin olun.
- Hologram yerleştirmeyi denediğiniz bir ve üç ölçüm arasında stand.
- Siyah veya yansıtıcı yüzeylere hologramlar yerleştirmeyin.
- Wi-Fi ağa bağlı olduğunuzdan emin olun. Wi-Fi ' y e bağlı değilseniz, HoloLens bilinen bir alanı tanımlayamıyor ve yükleyemez.
- HoloLens, sallarınızı yeniden taramak için odalar etrafında kılavuzluk eder. Zaten taranmış olan öğeleri görmek için, eşleşen kafes grafiğinin görüntülenmesini sağlamak üzere AIR ' e dokunun.
- Yeni bir alan oluşturmanız gerekiyorsa Wi-Fi ' y e bağlanın ve ardından HoloLens yeniden başlatın.
- doğru alanın etkin olup olmadığını görmek veya bir alanı el ile yüklemek için **Ayarlar**  >  **sistem**  >  **alanları**' na gidin.
- Doğru alan yüklenirse ve sorun yaşamaya devam ediyorsanız, alan bozuk olabilir. Bu sorunu onarmak için alanı seçip **Kaldır**' ı seçin. alanı kaldırdıktan sonra HoloLens, kisörlerinizi eşlemeye ve yeni bir alan oluşturmaya başlar.

[Listeye geri dön](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramlar kaybolur veya diğer hologramlar ya da nesnelerde kullanılır

Bir hologram için çok daha yakın bir işlem yaparsanız, bu, &mdash; hologram geri yüklemek için geçici olarak kaybolacaktır, bundan uzaklaşmanız yeterlidir. Ayrıca, birkaç hologragram birlikte yakındıysanız, bazıları kaybolabilir. Birkaçını kaldırmayı deneyin.

Hologramlar ayrıca, diğer hologramlar veya duvarlar gibi nesneler tarafından engellenebilir. Bu durumda, aşağıdaki düzeltmelerden birini deneyin:

- Hologram başka bir hologram içinde kullanılıyorsa, bu hologram başka bir konuma taşıyın. Bunu yapmak için **Ayarla**' yı seçin, sonra da konumlandırın ve tutun.
- Hologram bir duvarta kullanılıyorsa, **Ayarla**' yı seçin ve ardından hologram görünene kadar duvara yaklaşın. Dokunup basılı tutarak, daha sonra hologram ileri ve çıkış dışına çekin.
- Hareketleri kullanarak hologram taşıyamıyorum, bunu kaldırmak için sesinizi kullanın. Hologram sırasında, "Kaldır" deyin. Sonra, hologram yeniden açın ve yeni bir konuma yerleştirin.

[Listeye geri dön](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramlar, bir duvar 'nin diğer tarafında görünür

bir duvara çok yakınsanız veya HoloLens henüz duvarı taramamışsa, sonraki odada bulunan hologragram ' u görebilirsiniz. Duvar taramak için, duvardan bir ve üç ölçüm arasında tek tek ve BT 'nin aralarındaki

bir siyah veya yansıtıcı nesne (örneğin, bir siyah küçük ya da bir veya daha az çelik soğutma), HoloLens duvar taramasını denediğinde soruna neden olabilir. Böyle bir nesne varsa, duvarın diğer tarafını tarayın.

[Listeye geri dön](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Bir duvarda bir hologram yerleştirdikten sonra float görünüyor

Bir duvara yerleştirdiğiniz bir hologram, genellikle duvardan bir inç veya daha fazla şekilde görünür. Daha fazla görünüyorsa, aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Bir duvardaki bir hologram yerleştirirken, duvardan bir ve üç ölçüm arasında tek tek ve duvardan doğrudan açık olarak yer alır.
- Harita kafes grafiğini göstermek için duvara dokunun. Kafesin duvarda hizalandığından emin olun. Aksi takdirde, hologram 'yi kaldırın, duvarı yeniden tarayın ve tekrar deneyin.
- Sorun devam ederse, ayarlama uygulamasını çalıştırın. **Ayarlar**  >  **sistem**  >  **yardımcı programlarında** bulacaksınız.

[Listeye geri dön](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Uygulamalar, taşıdıktan sonra çok yakın görünüyor

HoloLens, uygulamayı farklı açılardan tarayabilmesi için uygulamayı yerleştirmekte olduğunuz alana bakmaya çalışın. [Cihazınızı Temizleme](hololens1-hardware.md#care-and-cleaning) işlemi de yardımcı olabilir.

[Listeye geri dön](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Kararsız veya kesin hologramlar ile ilgili sorunları bildirme
 
1. Lütfen bu sorunun bir [karma gerçeklik yakalama videosunu](holographic-photos-and-videos.md#capture-a-mixed-reality-video) kaydedin. Bu video daha sonra ekli bir dosya olarak geri bildirim hub 'ı aracılığıyla karşıya yüklenebilir.  
1. **Ayarlar** app-> **gizlilik**  ->  **tanılama & geri bildirimi** aracılığıyla tam telemetriyi etkinleştirin ve **isteğe bağlı tanılama verileri** altında, geçiş seçeneğinin **açık** olarak ayarlandığından emin olun
1. en son [Windows Holographic işletim sistemine (20h2 veya üzeri)](hololens-release-notes.md#windows-holographic-version-20h2)güncelleştirerek en son hologram ölçeğini ve kararlılık düzeltmelerini alın. Güncelleştirme sonrasında şunları yapın:
    1. tüm Hologramlar **Ayarlar** app-> **sistemi** aracılığıyla kaldırın  ->  **Hologramlar** ->, **tüm hologragram kaldır** ' ı seçin ve yeni bir eşleme ile başlayın.
    1. HoloLens oluşturup odaızın etrafında gezinerek ve alandaki tüm alanları ve yüzeyleri arayarak yeriniz için yeni bir harita oluşturun. Bunu 2-3 dakika boyunca yapın.
    1. IPD ayarlaması gerçekleştirin. **Ayarlar**  >  **sistem**  >  **yardımcı programlarına** gidin. **Ayar**' ın altında, **ayarlamayı aç**' ı seçin.
    1. Senaryoyu yeniden test edin ve hala devam edip etmediğini görüntüleyin.
1. Güncelleştirme sorunu gidermezse, lütfen bir [geri bildirim merkezi sorunu](hololens-feedback.md)bildirin. Geri bildirimi doldurduktan sonra, destek ile iletişim kurulurken gönderilebilecek kolay bir bağlantı oluşturmak için **Share (paylaşma** ) düğmesini kullanabilirsiniz.

[Listeye geri dön](#list)