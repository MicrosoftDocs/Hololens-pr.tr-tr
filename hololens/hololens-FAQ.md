---
title: Cihaz ve hologramları HoloLens sık sorulan sorular
description: Hologramlarla etkileşim kurma veya hologramlarla etkileşim HoloLens bir sorunun mu var?  Bu makale hızlı bir yanıt ve daha fazla kaynak sağlar.
keywords: hololens, s, bilinen sorun, yardım
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
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428965"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramlar ve etkileşim sorunlarını giderme

Bu makalede hologram yerleştirme, boşluklarla çalışma ve hologramlarla ilgili sorunları bildirme ile ilgili sorunlar giderilir.

Her soruna sahip olduğunuz her zaman şu sorunlardan emin olun:
- Bunun [bir şeyi düzeltip](hololens-restart-recover.md) düzeltmey olmadığını görmek için yeniden başlatmayı deneyin.
- Sorun gidermeden önce, HoloLens [(en az bir](hololens2-charging.md) saat ücrete tabidir) kadar ücrete tabidir. 


Sorun hakkında bize bilgi göndermek için Lütfen Geri Bildirim uygulamasını kullanın. Geri Bildirim uygulamasını Başlat menüsünde [  bulabilirsiniz.](holographic-home.md) 

Kendi renklerinizi nasıl takacakları hakkında ipuçları HoloLens, bkz. [Fit Ayarlama.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Yeni alanlar oluşturulamıyor](#new-spaces-cant-be-created)
- [Boşluklar tanımlenemiyor veya yüklenemiyor](#spaces-cant-be-identified-or-loaded)
- [Nasıl yaparım? alanları mı silebilirsiniz?](#how-do-i-delete-all-spaces)
- [Hologramlar görünmüyor veya hareket ediyor](#holograms-dont-look-right-or-are-moving-around)
- ["Yer bulma" iletisi](#finding-your-space-message)
- [Beklenen hologramlar alanımda gösterlenmiyor](#expected-holograms-arent-showing-in-my-space)
- [Hologram yerleştirileyem veya önceden yerleştirilmiş hologramları göremiyorum](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramlar duvarın diğer tarafında görünür](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Uygulamalar, taşımadan sonra çok yakın görünüyor](#apps-appear-too-close-after-moving-them)
- [Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Yeni alanlar oluşturulamıyor

En olası sorun, depolama alanı az olmasıdır. [Biraz disk alanı boşaltın](hololens-troubleshooting.md#low-disk-space-error) ve sonra yeniden deneyin.

[Listeye dön](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Boşluklar tanımlenemiyor veya yüklenemiyor

Çalışma HoloLens otomatik olarak içinde yer alan alanı belirleye ve yükleyenene kadar aşağıdaki faktörleri kontrol edin:

- Wi-Fi'a bağlı olduğunuzdan emin Wi-Fi
- Odada bol miktarda ışık olduğundan emin olun
- Çevresinde önemli bir değişiklik olmadığını emin olun.

Bir alanı el ile de yükleyebilirsiniz veya Sistem Alanları'nın Ayarlar  >    >  **yönetebilirsiniz.**

[Listeye dön](#list)

## <a name="how-do-i-delete-all-spaces"></a>Nasıl yaparım? alanları mı silebilirsiniz?

*Çok yakında*

[Listeye dön](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramlar görünmüyor veya hareket ediyor

Hologramlar doğru görünmüyorsa (örneğin, bu hologramlar hareket ediyor veya shaky veya bunların üzerinde siyah düzeltme ekleri görüyorsanız) şu düzeltmelerden birini deneyin:

- [Cihazınızın güvenlik cihazınızı temizleyin ve](hololens1-hardware.md#care-and-cleaning) algılayıcıları engelleyen bir şey yoktur.
- Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.
- Çevrenizi dolaşarak ve çevrenize bakarak daha HoloLens taramayı deneyin.
- Çok sayıda hologram yerleştirilse, bazı hologramları kaldırmayı deneyin.

Sorun devam ediyorsanız, Ayarlama uygulamasını çalıştırmayı deniyorum. Bu uygulama, yalnızca HoloLens hologramlarınızı en iyi şekilde tutmaya yardımcı olmak için uygulamanızı ayarlar. Bunu yapmak için Sistem Yardımcı **Programları'Ayarlar**  >  **gidin.**  >   **Ayarlama'nın** altında Açık **Ayar'ı seçin.**

[Listeye dön](#list)

## <a name="finding-your-space-message"></a>"Yer bulma" iletisi

Bu HoloLens öğrenme veya yükleme sırasında "Yerlerinizi bulma" iletisiyle kısa bir ileti alabilirsiniz. Bu ileti birkaç saniyeden uzun süre görüntülenirse, altta "Hala alanınızı Başlat menüsü" ifadesinin yer alan başka bir iletiyle de karşınıza var.

Bu iletiler, HoloLens eşleme konusunda sorun olduğu anlamına geliyor. Bu durumda uygulamaları açabilirsiniz ancak ortamınıza hologramlar yer açabilirsiniz.

Bu iletileri sık görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.
- Cihaz mengenenizin temiz olduğundan emin olun. [Mengenenizi temizlemeyi öğrenin.](hololens1-hardware.md#care-and-cleaning)
- Güçlü bir sinyale sahip Wi-Fi olun. Herhangi bir sinyalle veya Wi-Fi zayıf Wi-Fi yeni bir ortama girer HoloLens alanınızı bulamazsınız. Ağ Wi-Fi   >  Wi-Fi'Ayarlar **&amp; bağlantısına gidip bağlantınızı**  >  **kontrol edin.**
- Daha yavaş ilerlemeyi deneyin.

[Listeye dön](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Beklenen hologramlar alanımda gösterlenmiyor

Yerleştir beklediğiniz hologramları görmüyorsanız veya beklediğiniz hologramları görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Bazı lambalar açın. HoloLens iyi bir alanda en iyi şekilde çalışır.
- System Hologramlar'ye (System   >  **Ayarlar)** gidip  >  **ihtiyacınız Hologramlar**  >  **hologramları kaldırın.** Veya gerekirse Tüm **hologramları kaldır'ı seçin.**

  > [!NOTE]
  > Alanınızdaki düzen veya aydınlatma önemli ölçüde değişiyorsa, cihazınız alanınızı tanımlama ve hologramlarınızı gösterme konusunda sorun olabilir.

[Listeye dön](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Hologram yerleştirileyem veya önceden yerleştirilmiş hologramları göremiyorum

HoloLens alanınız eşleyene veya yükleyenene kadar sınırlı moda girer ve hologram yerleştiresiniz veya yerleştirilen hologramları göresiniz. İşte deneyebileceğiniz bazı çözümler:

- Ortamınız için yeterli ışığın olduğundan emin olun. Bu HoloLens alanı görebilir ve eşlersiniz.
- Hologramı yapmaya çalıştığın yerden bir ile üç metre arasında dur.
- Hologramları siyah veya yansıtıcı yüzeylere yerleştirin.
- Bir ağ bağlantısına bağlı olduğunuzdan emin Wi-Fi olun. Wi-Fi'a bağlı değil HoloLens bilinen bir alanı belirleyeme ve yükleyemediysiniz.
- Etrafınızı yeniden HoloLens için odaları dolaşabilirsiniz. Nelerin taranmış olduğunu görmek için havadan dokunarak eşleme ağı grafiğini ortaya çıkarabilirsiniz.
- Yeni bir alan oluşturmanız gerekirse, Wi-Fi'a bağlanın ve ardından ağ HoloLens.
- Doğru alan etkin olup olmadığını görmek veya el ile bir alan yüklemek için Sistem **Alanları'Ayarlar**  >    >  **gidin.**
- Doğru alan yüklü ise ve sorun devam ediyorsanız, alan bozuk olabilir. Bu sorunu çözmek için alanı seçin ve **kaldır'ı seçin.** Alanı kaldırdikten sonra HoloLens alanı eşlemeye ve yeni bir alan oluşturmaya başlar.

[Listeye dön](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur

Bir holograma çok yaklaşmanız, hologramı geri yüklemek için geçici olarak &mdash; kaybolur, yalnızca bundan uzaklaşabilirsiniz. Ayrıca, birkaç hologramı birbirine yakın yerleştirilse de bazıları kaybolabilir. Birkaç tane kaldırmayı deneyin.

Hologramlar, diğer hologramlar veya duvar gibi nesneler tarafından da engellenmiş veya kapatılmalıdır. Bu durumda aşağıdaki düzeltmelerden birini deneyin:

- Hologram başka bir hologramda yer alan bir hologram ise, büyük harfli hologramı başka bir konuma taşıma. Bunu yapmak için **Ayarla'ya ve** ardından dokunarak basılı tutun ve konuma getirin.
- Hologram bir duvara monte edilirse Ayarla'ya tıklayın **ve** ardından hologram görünene kadar duvara doğru inin. Dokunun ve basılı tutun, sonra hologramı duvardan ileri ve dışarı çekin.
- Hareketleri kullanarak hologramı hareket ettire biliyorsanız sesinizi kullanarak kaldırın. Holograma bakarak "Kaldır" diyelim. Ardından hologramı yeniden açın ve yeni bir konuma yer açın.

[Listeye dön](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramlar duvarın diğer tarafında görünür

Duvara çok yakınsanız veya duvarda henüz HoloLens taramadıysanız bir sonraki odada yer alan hologramları görüntüln. Duvarı taramak için duvardan bir ile üç metre arasında durur ve duvara bakar.

Duvarın yakınındaki siyah veya yansıtıcı bir nesne (örneğin, siyah bir HoloLens buzdolabı) duvarı taramaya çalıştığında sorunlara neden olabilir. Böyle bir nesne varsa duvarın diğer tarafını tarayın.

[Listeye dön](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor

Duvara yer alan hologram genellikle duvardan bir inç uzakta gibi görünür. Daha uzakta görünüyorsa aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Bir duvara hologramı yerken duvardan bir ile üç metre arasında durur ve duvarın doğrudan üzerinde durur.
- Eşleme ağı grafiğini ortaya çıkarmak için duvara havadan dokunun. Örgün duvarla hizalı olduğundan emin olun. Yoksa hologramı kaldırın, duvarı yeniden deneyin ve yeniden deneyin.
- Sorun devam ederse Ayarlama uygulamasını çalıştırın. Bunu Sistem Yardımcı Programları **Ayarlar**  >    >  **bulabilirsiniz.**

[Listeye dön](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Uygulamalar, taşımadan sonra çok yakın görünüyor

Uygulamayı yerleştirerek farklı açılardan taramak için HoloLens deneyin. [Cihaz mengenenizin temizlenmesi](hololens1-hardware.md#care-and-cleaning) de yardımcı olabilir.

[Listeye dön](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme
 
1. Lütfen sorunun Karma Gerçeklik Yakalama [videosunu](holographic-photos-and-videos.md#capture-a-mixed-reality-video) ve bir videosunu izleyin. Bu video daha sonra dosya Geri Bildirim Merkezi dosya olarak karşıya yükleyebilirsiniz.  
1. **Ayarlar** -> Gizlilik Tanılaması geri bildirimi & ve İsteğe bağlı tanılama verileri altında iki durumlu düğmenin Açık olarak ayarlanmış olduğundan emin olmak için tam telemetriyi  ->   **etkinleştirin** 
1. En son [Holographic OS (20H2](hololens-release-notes.md#windows-holographic-version-20h2)veya daha yüksek) sürümüne güncelleştirerek en son hologram ölçek ve kararlılık düzeltmelerini elde Windows. Güncelleştirdikten sonra aşağıdaki işlemleri gerçekleştirin:
    1. -> Hologramlar **System** **Ayarlar ->** app -> tüm hologramları kaldır'ı seçerek tüm hologramları kaldırın ve yeni bir  ->  haritayla başlamayı seçin.**Hologramlar** 
    1. Yeni bir alan haritası oluşturmak için HoloLens odanızı dolaşın ve alanda yer alan tüm alanlara ve yüzeylere bakabilirsiniz. Bunu 2-3 dakika için yap.
    1. IPD ayarlaması gerçekleştirin. Sistem Yardımcı  >    >  **Ayarlar'ye gidin.** **Ayarlama'nın** altında Açık **Ayar'ı seçin.**
    1. Senaryoyu yeniden test eder ve hala devam eder mi diye bakın.
1. Güncelleştirme sorunu çözene kadar sorunu [Geri Bildirim Merkezi.](hololens-feedback.md) Geri bildirimi doldurduktan sonra, destek **ekibiyle** iletişime geçerek gönderebilirsiniz. Paylaş düğmesini kullanarak kolayca paylaşabilirsiniz.

[Listeye dön](#list)