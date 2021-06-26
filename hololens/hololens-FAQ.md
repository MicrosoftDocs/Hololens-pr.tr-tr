---
title: HoloLens cihazları ve hologramları hakkında sık sorulan sorular
description: HoloLens veya hologramlarla etkileşim kurma hakkında hızlı bir sorunun mu var?  Bu makale hızlı bir yanıt ve daha fazla kaynak sağlar.
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
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924035"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramlar ve etkileşim sorunlarını giderme

Bu makalede hologram yerleştirme, boşluklarla çalışma ve hologramlarla ilgili sorunları bildirme ile ilgili sorunlar giderilir.

Her soruna sahip olduğunuz her zaman şu sorunlardan emin olun:
- Bunun [bir şeyi düzeltip](hololens-restart-recover.md) düzeltmey olmadığını görmek için yeniden başlatmayı deneyin.
- Sorun gidermeden önce HoloLens'in [ücretlendir (en az](hololens2-charging.md) bir saat ücretlendir) olduğundan emin olur. 


Sorun hakkında bize bilgi göndermek için Lütfen Geri Bildirim uygulamasını kullanın. Geri Bildirim uygulamasını Başlat menüsünde [  bulabilirsiniz.](holographic-home.md) 

HoloLens'inizi nasıl takacakları hakkında ipuçları için bkz. [Fit Ayarlama.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Yeni alanlar oluşturulamıyor](#new-spaces-cant-be-created)
- [Boşluklar tanımlenemiyor veya yüklenemiyor](#spaces-cant-be-identified-or-loaded)
- [Nasıl yaparım? alanları mı silebilirsiniz?](#how-do-i-delete-all-spaces)
- [Hologramlar doğru görünmüyor veya hareket ediyor](#holograms-dont-look-right-or-are-moving-around)
- ["Yer bulma" iletisi](#finding-your-space-message)
- [Beklenen hologramlar alanımda gösterlenmiyor](#expected-holograms-arent-showing-in-my-space)
- [Hologram yerleştirilemleri veya önceden yerleştirilmiş hologramları göremiyorum](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramlar duvarın diğer tarafında görünüyor](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Uygulamalar, taşımadan sonra çok yakın görünüyor](#apps-appear-too-close-after-moving-them)
- [Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Yeni alanlar oluşturulamıyor

En olası sorun, depolama alanı az olmasıdır. [Biraz disk alanı boşaltın](hololens-troubleshooting.md#low-disk-space-error) ve sonra yeniden deneyin.

[Listeye dön](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Boşluklar tanımlenemiyor veya yüklenemiyor

HoloLens'iniz otomatik olarak içinde yer alan alanı belirleyeye ve yükleyenene kadar aşağıdaki faktörleri kontrol edin:

- Wi-Fi'a bağlı olduğunuzdan emin Wi-Fi
- Odada bol miktarda ışık olduğundan emin olun
- Çevresinde önemli bir değişiklik olmadığını emin olun.

Ayrıca, Ayarlar Sistem Alanları'nın 'a gidip el ile bir alan yükleyebilirsiniz **veya**  >  **alanlarınızı**  >  **yönetebilirsiniz.**

[Listeye dön](#list)

## <a name="how-do-i-delete-all-spaces"></a>Nasıl yaparım? alanları mı silebilirsiniz?

*Çok yakında*

[Listeye dön](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramlar doğru görünmüyor veya hareket ediyor

Hologramlar doğru görünmüyorsa (örneğin, bu hologramlar hareket ediyor veya shaky veya bunların üzerinde siyah düzeltme ekleri görüyorsanız) şu düzeltmelerden birini deneyin:

- [Cihazınızın güvenlik kameralarını temizleyin](hololens1-hardware.md#care-and-cleaning) ve algılayıcıları engelleyen bir şey olmadığını emin olun.
- Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.
- HoloLens'in bunları tamamen tarayana kadar etrafınıza bakarak çevrenizi incelemeyi deneyin.
- Çok sayıda hologram yerleştirilse, bazı hologramları kaldırmayı deneyin.

Sorun devam ediyorsanız, Ayarlama uygulamasını çalıştırmayı deniyorum. Bu uygulama, hologramlarınızı en iyi şekilde tutmaya yardımcı olmak için HoloLens'inizi sizin için ayarlar. Bunu yapmak için Ayarlar Sistem Yardımcı  >    >  **Programları'nı seçin.** **Ayarlama'nın** altında Açık **Ayar'ı seçin.**

[Listeye dön](#list)

## <a name="finding-your-space-message"></a>"Yer bulma" iletisi

HoloLens bir alanı öğrenerek veya yüklerken "Yerlerinizi bulma" ifadesinin yer alır. Bu ileti birkaç saniyeden uzun süre görüntülenirse, uygulamanın altında "Hala alanınızı Başlat menüsü" ifadesinin yer alan başka bir iletiyle de karşınıza vardır.

Bu iletiler HoloLens'in alanınızı eşleme konusunda sorun içinde olduğu anlamına geliyor. Bu durumda uygulamaları açabilirsiniz ancak ortamınıza hologramlar yer açabilirsiniz.

Bu iletileri sık görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Çok fazla doğrudan erişime sahip olmayan, iyi bir şekilde ışık alan bir odaya sahip olduğundan emin olun.
- Cihaz mengenenizin temiz olduğundan emin olun. [Mengenenizi temizlemeyi öğrenin.](hololens1-hardware.md#care-and-cleaning)
- Güçlü bir sinyale sahip Wi-Fi olun. Sanal sinyal veya zayıf sinyal Wi-Fi yeni bir Wi-Fi girersiniz HoloLens alanınızı bulamaz. Ayarlar Ağ Wi-Fi   >  Wi-Fi'a **gidip &amp;**  >  **bağlantınızı kontrol edin.**
- Daha yavaş ilerlemeyi deneyin.

[Listeye dön](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Beklenen hologramlar alanımda gösterlenmiyor

Yerleştir beklediğiniz hologramları görmüyorsanız veya beklediğiniz hologramları görüyorsanız aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Birkaç lambayı açın. HoloLens en iyi şekilde iyi ışık alan bir alanda çalışır.
- Ayarlar Sistem Hologramları Yakındaki hologramları kaldır'a gidip ihtiyacınız olan  >    >    >  **hologramları kaldırın.** Veya gerekirse Tüm **hologramları kaldır'ı seçin.**

  > [!NOTE]
  > Alanınızdaki düzen veya aydınlatma önemli ölçüde değişiyorsa, cihazınız alanınızı tanımlama ve hologramlarınızı gösterme konusunda sorun olabilir.

[Listeye dön](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Hologram yerleştirilemleri veya önceden yerleştirilmiş hologramları göremiyorum

HoloLens alanınızı eşleyene veya yükleyenene kadar Sınırlı moda girer ve hologram yerleştiresiniz veya yerleştirmiş olduğunuz hologramları göresiniz. İşte deneyebileceğiniz bazı çözümler:

- HoloLens'in alanı görene ve eşleyene kadar ortamınız için yeterli ışık olduğundan emin olun.
- Hologramı yapmaya çalıştığın yerden bir ile üç metre arasında dur.
- Hologramları siyah veya yansıtıcı yüzeylere yerleştirin.
- Bir ağ bağlantısına bağlı olduğunuzdan emin Wi-Fi olun. Wi-Fi'a bağlı değilsanız HoloLens bilinen bir alanı tanım tanımp yükleyememektedir.
- HoloLens'in çevrenizi yeniden görene kadar odaları dolaşabilirsiniz. Nelerin taranmış olduğunu görmek için havadan dokunarak eşleme ağı grafiğini ortaya çıkarabilirsiniz.
- Yeni bir alan oluşturmanız gerekirse Wi-Fi'a bağlanın ve HoloLens'inizi yeniden başlatın.
- Doğru boşluğun etkin olup olmadığını görmek veya el ile bir alan yüklemek için Ayarlar Sistem  >  **Alanları'ne**  >  **gidin.**
- Doğru alan yüklü ise ve sorun devam ediyorsanız, alan bozuk olabilir. Bu sorunu çözmek için alanı seçin ve **kaldır'ı seçin.** Siz alanı kaldırdikten sonra HoloLens, çevrenizi eşlemeye ve yeni bir alan oluşturmaya başlar.

[Listeye dön](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramlar kaybolur veya diğer hologramlara veya nesnelere olur

Bir holograma çok yaklaşmanız, hologramı geri yüklemek için geçici olarak &mdash; kaybolur, yalnızca bundan uzaklaşabilirsiniz. Ayrıca, birkaç hologramı birbirine yakın yerleştirilse de bazıları kaybolabilir. Birkaç tane kaldırmayı deneyin.

Hologramlar ayrıca diğer hologramlar veya duvar gibi nesneler tarafından engellenmiş veya kapatılmalıdır. Bu durumda aşağıdaki düzeltmelerden birini deneyin:

- Hologram başka bir hologramda yer alan bir hologram ise, büyük harfli hologramı başka bir konuma taşıma. Bunu yapmak için **Ayarla'ya ve** ardından dokunarak basılı tutun ve konuma getirin.
- Hologram bir duvara monte edilirse Ayarla'ya tıklayın **ve** ardından hologram görünene kadar duvara doğru inin. Dokunun ve basılı tutun, sonra hologramı duvardan ileri ve dışarı çekin.
- Hareketleri kullanarak hologramı hareket ettire biliyorsanız sesinizi kullanarak kaldırın. Holograma bakarak "Kaldır" diyelim. Ardından hologramı yeniden açın ve yeni bir konuma yer açın.

[Listeye dön](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramlar duvarın diğer tarafında görünüyor

Duvara çok yakınsanız veya HoloLens henüz duvarı taramamışsa, bir sonraki odada yer alan hologramları görebilir. Duvarı taramak için duvardan bir ile üç metre arasında durur ve duvara bakar.

HoloLens duvarı taramaya çalıştığında, duvarın yakınındaki siyah veya yansıtıcı bir nesne (örneğin, siyah bir buzdolabı veya çelik buzdolabı) sorunlara neden olabilir. Böyle bir nesne varsa duvarın diğer tarafını tarayın.

[Listeye dön](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Bir duvara hologram yerleştirdikten sonra kayan bir hologram gibi görünüyor

Duvara yer alan hologram genellikle duvardan bir inç uzakta gibi görünür. Daha uzakta görünüyorsa aşağıdaki düzeltmelerden birini veya daha fazlasını deneyin:

- Bir duvara hologramı yerken duvardan bir ile üç metre arasında durur ve duvarın doğrudan üzerinde durur.
- Eşleme ağı grafiğini ortaya çıkarmak için duvara havadan dokunun. Örgün duvarla hizalı olduğundan emin olun. Yoksa hologramı kaldırın, duvarı yeniden deneyin ve yeniden deneyin.
- Sorun devam ederse Ayarlama uygulamasını çalıştırın. Bunu Ayarlar Sistem Yardımcı **Programları**  >  **sayfasında**  >  **bulabilirsiniz.**

[Listeye dön](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Uygulamalar, taşımadan sonra çok yakın görünüyor

HoloLens'in alanı farklı açılardan taraması için uygulamayı yerleştirmiş olduğu alanı incelemeyi deneyin. [Cihaz mengenenizin temizlenmesi](hololens1-hardware.md#care-and-cleaning) de yardımcı olabilir.

[Listeye dön](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Kararsız veya değişken olmayan hologramlarla ilgili sorunları bildirme
 
1. Lütfen sorunun Karma Gerçeklik Yakalama [videosunu](holographic-photos-and-videos.md#capture-a-mixed-reality-video) ve bir videosunu izleyin. Bu video daha sonra dosya Geri Bildirim Merkezi dosya olarak karşıya yükleyebilirsiniz.  
1. Geri bildirim için  Ayarlar uygulaması -> Gizlilik Tanılaması & telemetrisini etkinleştirin ve İsteğe bağlı tanılama verileri altında iki durumlu düğmenin Açık olarak ayarlanmış olduğundan  ->   emin **olun** 
1. En son [Windows Holographic OS'ye (20H2](hololens-release-notes.md#windows-holographic-version-20h2)veya daha yüksek) güncelleştirerek en son hologram ölçek ve kararlılık düzeltmelerini elde etmek. Güncelleştirdikten sonra aşağıdaki işlemleri gerçekleştirin:
    1. Ayarlar uygulaması **->** **System** Hologramları -> tüm Hologramları kaldır'ı seçerek  ->   **tüm Hologramları** kaldır'ı seçin ve yeni bir haritayla çalışmaya başlayabilirsiniz.
    1. HoloLens'i takarak ve odanızı dolaşarak ve uzaydaki tüm alanlara ve yüzeylere bakarak yeni bir alan haritası oluşturun. Bunu 2-3 dakika için yap.
    1. IPD ayarlaması gerçekleştirin. Ayarlar Sistem **Yardımcı**  >    >  **Programları'nı seçin.** **Ayarlama'nın** altında Açık **Ayar'ı seçin.**
    1. Senaryoyu yeniden test eder ve hala devam eder mi diye bakın.
1. Güncelleştirme sorunu çözene kadar sorunu [Geri Bildirim Merkezi.](hololens-feedback.md) Geri bildirimi doldurduktan sonra, destek **ekibiyle** iletişime geçerek gönderebilirsiniz. Paylaş düğmesini kullanarak kolayca paylaşabilirsiniz.

[Listeye dön](#list)