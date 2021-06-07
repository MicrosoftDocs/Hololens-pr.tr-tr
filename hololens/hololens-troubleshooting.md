---
title: Sorun giderme
description: HoloLens cihaz sorunları ve sorun giderme teknikleri için en yaygın çözümlerin güncel kalmasını sağlar.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: sorunlar, hata, sorun giderme, çözüm, yardım, destek, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379060"
---
# <a name="troubleshoot-common-issues"></a>Yaygın sorunları giderme

Bu makalede, birkaç yaygın HoloLens sorununa nasıl çözüm yapılacağı açıklanır.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens My yanıt vermiyor veya başlamıyor

HoloLens 'niz başlamazsa:

- Güç düğmesinin yanındaki LED 'ler soluk veya yalnızca bir tane daha yanıp sönüyor değilse, [HoloLens 'nizi ücretlemeniz gerekebilir.](hololens-recovery.md#charge-the-device)
- Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey görmüyorsanız, [cihazın sabit bir şekilde sıfırlanmasını öngörün](hololens-recovery.md#hard-reset-procedure).

HoloLens 'niz dondurulmuş veya yanıt vermiyorsa:

- Bir LED 'in beş bir kısmını devre dışı bırakır veya LED 'ler yanıt vermiyorsa 15 saniye boyunca güç düğmesine basarak HoloLens 'nizi kapatın. HoloLens 'nizi başlatmak için, Power düğmesine yeniden basın.

Bu adımlar çalışmazsa, [HoloLens 2 cihazınızı](hololens-recovery.md) veya [HoloLens (1. gen) cihazınızı](hololens1-recovery.md) kurtarmayı deneyebilirsiniz.

## <a name="holograms-dont-look-good"></a>Hologragram iyi görünmeyin

Hologramlar kararsız, doğru bir şekilde görünmüyorsa, şunu deneyin:

- HoloLens 'nizin önünde cihaz vizörü ve algılayıcı çubuğunuzu Temizleme.
- Odadaki ışığı artırma.
- HoloLens 'te gezinerek daha fazla tarama yapabilirsiniz.
- HoloLens 'nizi, gözleriniz için ayarlama. **Ayarlar**  >  **sistem**  >  **yardımcı programları**' na gidin. **Ayar**' ın altında, **ayarlamayı aç**' ı seçin.
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Hologram dengesiz veya doğru olmayan sorunları bildirme
 
1. Lütfen bu sorunun bir [karma gerçeklik yakalama videosunu](holographic-photos-and-videos.md#capture-a-mixed-reality-video) kaydedin. Bu video daha sonra ekli bir dosya olarak geri bildirim hub 'ı aracılığıyla karşıya yüklenebilir.  
1. **Ayarlar** App-> **Gizlilik**  ->  **Tanılama & geri bildirimi** ve **isteğe bağlı Tanılama verileri** altında, geçiş seçeneğinin **Açık** olarak ayarlandığından emin olun.
1. En son [Windows holographic işletim sistemine (20H2 veya üzeri)](hololens-release-notes.md#windows-holographic-version-20h2)güncelleştirerek en son hologram ölçeğini ve kararlılık düzeltmelerini alın. Güncelleştirme sonrasında şunları yapın:
    1. **Ayarlar** App-> **System** hologram aracılığıyla tüm hologragram 'leri kaldırın  ->   -> **ardından tüm hologramlar kaldır** ' ı seçin ve yeni bir eşleme ile başlayın.
    1. HoloLens 'i düzenleyerek ve odaızın etrafında gezinerek ve alandaki tüm alanlara ve yüzeylere bakarak boşluktan yeni bir harita oluşturun. Bunu 2-3 dakika boyunca yapın.
    1. IPD ayarlaması gerçekleştirin. **Ayarlar**  >  **sistem**  >  **yardımcı programları**' na gidin. **Ayar**' ın altında, **ayarlamayı aç**' ı seçin.
    1. Senaryoyu yeniden test edin ve hala devam edip etmediğini görüntüleyin.
1. Güncelleştirme sorunu gidermezse, lütfen bir [geri bildirim merkezi sorunu](hololens-feedback.md)bildirin. Geri bildirimi doldurduktan sonra, destek ile iletişim kurulurken gönderilebilecek kolay bir bağlantı oluşturmak için **Share (paylaşma** ) düğmesini kullanabilirsiniz.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens, el girişine yanıt vermiyor

HoloLens 'in ellerinizi görmesini sağlamak için bunları hareket çerçevesinde tutmanız gerekir.  Karma Gerçeklik ana sayfası, kollarınızın ne zaman izleneceğini bilmenizi sağlayan geri bildirim sağlar.  Geri bildirim, HoloLens 'in farklı sürümlerinde farklıdır:
- HoloLens 'te (1. Genel), Gaze imleci bir noktadan halkaya dönüşür
- HoloLens 2 ' de, elinizdeki bir kurşun kalem 'e yakın olduğunda parmak izi imleci görünür ve SLA 'lar daha fazla olduğunda bir el Ray görünür

Birçok modern uygulama, karma gerçeklik ana 'ya benzer giriş desenlerine uyar.  HoloLens 'te el girişi kullanma hakkında daha fazla bilgi edinin [(1. Genel)](hololens1-basic-usage.md#use-hololens-with-your-hands) ve [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Birlikte çalışırken, bazı araç türlerinin el ile izleme ile çalışmadığına göz önünde bulundurun.  Yaygın olarak kullanılan bir örnek, artışlarını devralarak kızılötesi ışınına eğilen ve derinlik kamerası tarafından alınmayan siyah bir örnektir.  Çalışmanız lastik içeriyorsa, mavi veya gri gibi daha açık bir renk denemeyi öneririz.  Diğer bir örnek de büyük ölçekli bir örnektir ve bu, elinizin şeklinin gizlenmesi anlamına gelir. En iyi sonuçlar için mümkün olduğunca form sığdırma olarak bulunan gloonları kullanmanızı öneririz.

Vizörü ' in parmak izleri veya kullanım alanları varsa, vizörü 'nizi temizlemek için HoloLens ile birlikte gelen mikro fiber Temizleme havsını kullanın.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens, sesli komutlarıma yanıt vermiyor

Cortana, sesli komutlarınıza yanıt vermiyorsa Cortana 'Nın açık olduğundan emin olun. Tüm uygulamalar listesinde,   >    >  değişiklikler yapmak için Cortana menü **Not defteri**  >  **ayarları** ' nı seçin. Ne söyleyebilirim hakkında daha fazla bilgi edinmek için bkz. [HoloLens ile sesinizi kullanma](hololens-cortana.md).

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Hologramlar yerleştiremiyorum veya daha önce yerleştirdiğim hologragram göremez

HoloLens alanınızı eşleyebilir veya yükleyemediği takdirde, sınırlı moda girer ve yerleştirdiğiniz hologramlar yerleştirebilir ya da yerleştirdiğiniz hologramlar kullanamazsınız. İşte deneyebileceğiniz bazı çözümler:

- HoloLens 'in alanı görmesini ve eşlemesini sağlamak için ortamınızda yeterince ışık olduğundan emin olun.
- Wi-Fi ağa bağlı olduğunuzdan emin olun. Wi-Fi ' y e bağlı değilseniz, HoloLens bilinen bir alanı tanımlayamıyor ve yükleyemez.
- Yeni bir alan oluşturmanız gerekiyorsa, Wi-Fi ' y e bağlanın ve HoloLens 'nizi yeniden başlatın.
- Doğru alanın etkin olup olmadığını görmek veya bir alanı el ile yüklemek için **Ayarlar**  >  **sistem**  >  **alanları**' na gidin.
- Doğru alan yüklenirse ve sorun yaşamaya devam ediyorsanız, alan bozuk olabilir. Bu sorunu onarmak için alanı seçip **Kaldır**' ı seçin. Alanı kaldırdıktan sonra, HoloLens, kisörlerinizi eşlemeye ve yeni bir alan oluşturmaya başlar.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>HoloLens My hangi boşluğa ihtiyacım olduğunu söyleyebilir

HoloLens 'niz otomatik olarak kullandığınız alanı tanımlayamıyor ve yükleyemezseniz aşağıdaki faktörleri kontrol edin:

- Wi-Fi bağlı olduğunuzdan emin olun
- Odada birçok ışık olduğundan emin olun
- Büyük bir değişiklik olmadığından emin olun.

Ayrıca **Ayarlar**  >  **sistem**  >  **alanları**' na giderek bir alanı el ile yükleyebilir veya alanları yönetebilirsiniz.

## <a name="im-getting-a-low-disk-space-error"></a>"Yetersiz disk alanı" hatası alıyorum

Aşağıdakilerden birini veya birkaçını yaparak depolama alanını boşaltmanız gerekir:

- Kullanılmayan bazı boşlukları silin. **Ayarlar**  >  **sistem**  >  **alanları**' na gidin, artık ihtiyacınız olmayan bir alan seçin ve ardından **Kaldır**' ı seçin.
- Yerleştirdiğiniz hologramlar bölümünü kaldırın.
- Fotoğraflar uygulamasındaki bazı resimleri ve videoları silin.
- HoloLens 'ınızdan bazı uygulamaları kaldırın. **Tüm uygulamalar** listesinde, kaldırmak istediğiniz uygulamayı ve ardından **Kaldır**' ı seçin.

## <a name="my-hololens-cant-create-a-new-space"></a>HoloLens My yeni bir boşluk oluşturamıyor

En olası sorun, depolama alanını azaldığımyız. Bir disk alanını boşaltmak için [önceki ipuçlarından](#im-getting-a-low-disk-space-error) birini deneyin.

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens öykünücüsü çalışmıyor

HoloLens öykünücüsü hakkındaki bilgiler geliştirici belgelerimizde bulunur.  [HoloLens öykünücüsünün sorunlarını giderme](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)hakkında daha fazla bilgi edinin.
