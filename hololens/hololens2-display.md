---
title: HoloLens 2 ekranları
description: HoloLens 2 için beklentiler görüntülenir. En iyi görüntü kalitesi için ekranları yapılandırmaya yönelik kılavuz.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: görüntüleme, ayarlama, rahatlık, görseller, kalite, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 71dff00ff75feea4408979d2ce69fb14bf9bf3b7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380265"
---
# <a name="hololens-2-display"></a>HoloLens 2 ekran

HoloLens 2 ekranı, waveguides ve açık projektörlerin bir birleşimidir. Kullanıcılar, kulaklık taktığında (örneğin, vizörü içindeki mercekler) dalga kılavuzlarını gözden geçirin. Hafif projektörler, Brow 'ın üzerindeki kutunun içindedir. HoloLens 2, görüntüyü aydınlatmak için lazer ışığı kullanır.

## <a name="troubleshooting"></a>Sorun giderme

HoloLens 2 ' de, aşağıdaki adımları izleyerek gösterilen hologramlar için en yüksek görsel kalitesinin görüntülenmesini sağlayın:

* **Ekran parlaklığını artırın.** Hologragram, ekran en parlak test düzeyinde olduğunda en iyi şekilde görünür.
* **Daha yakından gözlerinize göz katın.** Gözlerinizi en yakın konuma göre aşağı doğru kaydırın.
* **Kaydırma vizörü aşağı.** Bir tebede aşağı doğru hareket ettirmenize, bu da vizörü 'ın burun yakınına yaklaştırmasını deneyin.
* **Göz ayarlamayı Çalıştır.** Görüntü, ekranda görüntüleri iyileştirmek için ınterpupilılmi (ıPD) ve gözle göz çıkarması kullanır. Göz ayarlama 'yı çalıştırmazsanız görüntü kalitesi daha kötü hale getirilebilir. Göz ayarlama 'yı çalıştırmak için **Ayarlar**  >  **sistem**  >  **ayarı**  >  **çalışma göz ayarlama**' ya gidin.
* **Görüntü renk ayarlamayı çalıştırın**. [Windows holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonraki sürümlerinde, Hololens 2 ekran için **alternatif bir renk profili seçebilirsiniz** . Bu, özellikle daha düşük ekran parlaklığı düzeylerinde renklerin daha doğru görünmesine yardımcı olabilir. Ekran renk ayarlaması, **Ayarlar** uygulamasında **sistem > ayarlama** sayfasında bulunabilir.

    > [!NOTE]
    > Bu ayar, görüntüleme bellenimine yeni bir renk profili kaydederken bu, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

### <a name="how-to-use-display-color-calibration"></a>Ekran renk ayarı 'nı kullanma
1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında, **görüntü renk ayarlama Çalıştır** düğmesini seçin.
1. Ekran renk ayarlama deneyimi başlatılır ve bu işlem, vizörü ' inizin doğru konumda olduğundan emin olmanızı sağlar.
1. Yönerge iletişim kutularında ilerledikten sonra, ekran otomatik olarak %30 oranında gri olacak.
    > [!TIP]
    > Ortamınızdaki soluk sahneyi görmekte sorun yaşıyorsanız, cihazın sol tarafındaki parlaklık düğmelerini kullanarak HoloLens 2 ' nin parlaklık düzeyini el ile ayarlayabilirsiniz.
1. Her renk profilini hemen denemek ve gözlerinize en iyi şekilde bakmak için düğmeler 1-6 ' i seçin (Bu, genellikle sahnenin gri tonlamalı bir şekilde görünmesine yardımcı olan profil ve beklenen şekilde görünür.)

    ![Renk ayarlama sahnesini görüntüle](images/color-cal-ui.png)
    
6. Seçili profille memnun olduğunuzda **kaydet & çıkış** düğmesini seçin
1. Değişiklik yapmayı tercih ediyorsanız, **iptal & çıkış** düğmesini seçin ve değişiklikleriniz geri döndürülecek

> [!TIP]
> Görüntü renk ayarlama ayarını kullanırken göz önünde bulundurmanız gereken bazı yararlı ipuçları aşağıda verilmiştir:
> - İstediğiniz zaman ayarlar ' da ekran renk ayarlamayı yeniden çalıştırabilirsiniz
> - Cihazdaki herkes renk profillerini değiştirme ayarını daha önce kullanmışsa, en son değişikliğin tarih/saati ayarlar sayfasında yansıtılır
> - Ekran renk ayarı 'nı yeniden çalıştırdığınızda, daha önce kaydedilen renk profili vurgulanacaktır ve profil 0 görünmez (profil 0 ' ın özgün renk profilini gösterdiği gibi)
> - Ekran özgün renk profiline geri dönmek istiyorsanız, bu ayarı Ayarlar sayfasından yapabilirsiniz (bkz. [renk profilini sıfırlama](#how-to-reset-color-profile))

### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama

HoloLens 2 ' ye kaydedilmiş özel renk profili varsa, cihazın özgün renk profilini geri yükleyebilirsiniz:
1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında **varsayılan renk profilini Sıfırla** düğmesini seçin.
1. İletişim kutusu açıldığında, HoloLens 2 ' yi yeniden başlatmaya hazırsanız **Yeniden Başlat** ' ı seçin ve değişikliklerinizi uygulayın.

### <a name="top-display-color-calibration-known-issues"></a>En üstteki ekran renk ayarlaması bilinen sorunları

- Ayarlar sayfasında, bu ayar sayfasını yeniden yükleyene kadar, renk profilinin en son ne zaman değiştirildiğini söyleyen durum dizesi güncel olmayacaktır 
    - **Geçici çözüm**: başka bir ayarlar sayfası seçin ve ardından ayarlama sayfasını yeniden seçin.
- HoloLens 2, ekran renk ayarlamayı çalıştırırken uyku moduna geçtiğinde, daha sonra karışık gerçeklik evliğine devam eder ve ekran parlaklığı düzeyi soluk kalır.
- Beklenen şekilde çalışmadan önce cihazınızın sol tarafındaki parlaklık düğmelerine birkaç kez doğru bir şekilde basmanız gerekebilir.
- Yerelleştirme tüm pazarlar için tamamlanmadı

## <a name="faq"></a>SSS

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Ekranın alt köşelerinde zaman zaman yanıp sönebildiğiniz desenler nelerdir?

Zaman zaman, HoloLens 2 ' nin sol alt köşesinde ve sağ köşelerinden farklı desenler gösterilecektir. Örnekler aşağıda gösterilmiştir (animasyonlu GIF 'Ler). Bu model, en iyi deneyim için ekranı ayarlamak üzere HoloLens 2 cihazınızın normal işleminin bir parçasıdır.

![Biphao deseninin](./images/DAT-Biphase-Fiducial.gif) ![COĞRAFI model](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>HoloLens 2 görüntümin neden doğru fotoğrafımı alamıyorum?

HoloLens 2 ekranı insan gözle görüntülenmek üzere tasarlanmıştır. Cihazda, bir kullanıcının gözüyle uyum sağlayan etkin bir renk düzeltme sistemi vardır. İnsan gözle karşılaştırıldığında, kameralar ortamları farklı ve aşağıda, kameranın yakaladığı ve kullanıcının gördüğü her türlü tutarsızlığı etkileyebilecek bazı faktörlerdir.

* **Göz konumu.** HoloLens 2 ekranı, kullanıcının gözle bulunduğu konum için özel olarak tasarlanmıştır. HoloLens 2, kullanıcının göz konumuna uyum sağlamak için göz izleme teknolojisini kullanır. Birkaç milimetre tarafından yanlış konumlandırılmış bir kamera görüntü bozulmaya neden olabilir. Kamera ile doğru konumlandırma zor olur ve cihazın renk düzeltmesini gerçekleştirdiği tam konum ve gözle eşleşmesi gerekir.
* **Göz taşıma.** Görüntü, Kullanıcı gösteriminin renkleri ayarlamak için hareket halinde uyum sağlar. Görüntü üzerinde gösterilen özellikler, kullanıcının merkezine, kenarına veya ekran köşesine bakmış olmasına bağlı olarak farklılık gösterebilir. Tek bir görüntü yakalama, en iyi şekilde yalnızca görüntünün bir göz önünde bir yön ile eşleşen eksen için nasıl göründüğünü gösterebilir.
* **Binsel görüntüleme.** HoloLens 2 ekranı her iki gözle de görüntülenmek üzere tasarlanmıştır. Beyinde iki görüntü görmeye uyum sağlar ve bunları birlikte kullanır. Yalnızca bir görüntünün görüntüleri diğer görüntüden alınan bilgileri yoksayar.
* **Kamera etkilenme süresi.** Kameranın etkilenme süresi saniyenin 1/120'in tam katı olması gerekir. HoloLens görüntü çerçevesi oranı 120 Hz 'dir. HoloLens 2 ' nin görüntüleri çizme yöntemi nedeniyle, tek bir karenin yakalanması, insanların görsel deneyimiyle eşleşecek kadar de yeterli değildir. Aynı zamanda, cihaz her seferinde (mikro hareketlerle) hareket ettirildiğinde, sistem görüntü üzerindeki görüntüyü hologragram sabitlerine kadar yeniden projeler. HoloLens 'in taşınmasının dışında tutulması sırasında birden çok çerçeveyi yakalama, genellikle bir laboratuar Kurulumu gerektirir.
* **Kamera açıklık boyutu.** Doğru görüntüyü yakalamak için kameranın açıklık boyutu en az 3 mm olmalıdır. Küçük apertures ile cep telefonu kameraları, insan gözlükinden daha küçük bir alandan hafif bir şekilde tümleştirin. Cihaz, büyük apertures tarafından gözlenen desenler için renk düzeltmeleri uygular. Küçük apertures ile, uygunluk desenleri daha net ve sistem tarafından uygulanan renk düzeltmelere karşın görünür durumda kalır.
* **Kamera giriş Pupıl.** Doğru bir görüntüyü yakalamak için kameranın girişinde en az 3 mm çapı olmalıdır. Aksi halde, kamera göz önünde görünmeyen bazı yüksek frekanslı desenleri yakalar. Giriş Pupıl 'nin her ikisi de kameranın önünde olmalıdır ve yakalanan görüntüde Aberrations ve diğer çeşitliliğe ulaşmaktan kaçınmak için göz atması mesafesinin üzerinde konumlandırılmış.
* **Kamera konumu.** HoloLens 2 görüntüsünü görüntüleme gereksinimlerini karşılayan kameralar daha büyüktür ve renk düzeltilmiş görüntüsünü gözlemlemek için kameranın HoloLens 2 görüntüsüne yeterince yakın bir şekilde konumlandırılması zordur. Kamera yanlış bir yer alıyorsa, renk düzeltme, HoloLens 2 görüntüsü yakalamayı olumsuz etkileyebilir.
* **Görüntü düzeltme.** Tipik dijital kameralar ve akıllı telefon kameralar, snappier sonucu sağlamak üzere kontrast ve renk sağlayan bir ton çoğaltma eğrisi (TRC) uygular. HoloLens 2 görüntüsüne uygulandığında, bu ton eğrisi, tek başına olmayan özellikleri artırır.

Hepsi, özelleştirilmiş endüstriyel kameraların HoloLens 2 görüntülerinden temsili görüntüleri yakalaması için hala mümkündür. Ne yazık ki, Smartphone, tüketici ve profesyonel kameralar, kullanıcının HoloLens 2 ' de gördüğü şekilde eşleşen resimleri yakalamaz.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Görüntü kalitesini göstermek için göz ayarlama nedir?

HoloLens 2, Kullanıcı gözlerinizin konumunu temel alarak etkin renkte renkleri düzeltir. [Göz ayarlama](hololens-calibration.md) iki önemli giriş sağlar: (1) kullanıcının ınterpupilılmi (IPD) ve (2) her bir gözle arama yönü. Göz ayarlama olmadan sistem, göz önünde olmayan bir gözle varsayılan olarak kabul edin. Etkin renk düzeltme ve düzeltme olmadan fark, kullanıcının kendi zevklerine göre değişir. Örneğin, sistem varsayılanı ile aynı ıPD 'ye sahip kullanıcılar daha az renk düzeltme geliştirmesi görür. Daha dar veya daha geniş bir sistem sistemi olan kullanıcılar, ekran görüntüsünde daha fazla değişiklik görür.

[Windows holographic Version 20H2 sürümündeki](hololens-release-notes.md#windows-holographic-version-20h2) yeni bir özellik, göz önünde bulunduğu şekilde [otomatik olarak algılanacaktır](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>HoloLens (1. gen) ve HoloLens 2 arasındaki görüntüleme farkları nelerdir?

En üstteki istekler arasında, HoloLens 1 ' den sonra Microsoft 'un verdiği müşteriler, (1) görünüm alanını artırın ve (2) parlaklığı artırın. Teknoloji geliştirmeleri, Microsoft 'un, görünümün alanını iki katına çıkarmış ve en fazla üç kat daha parlakla hafif projektörler üreten dalga kılavuzlarını üretmesine izin verir. Donanım, görüntüleme görüntüsü kalitesi: (1), görünüm alanı, (2) parlaklığı ve (3) renk bütünlüğü için bir esneklik için temeli ayarlar. Devam eden teknoloji gelişmeleri, başka bir alandan ödün vermeden tüm alanlarda iyileştirmeler yapılmasına izin verir. Bu arada, mevcut teknoloji bu avantajları için kullanılabilen sınırları ayarlar.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>HoloLens 2 görüntü kalitesini geliştiren geliştirmeler ne olur?

Görüntü kalitesini geliştirecek birçok araştırma yaptığımız için aşağıdaki alanların yaklaşan güncelleştirmelere gelmesi beklenmektedir:

* **Otomatik göz konumu.** Bu özellik, göz ayarlama yordamlarını arka planda gerçekleştirecektir. Kullanıcıların, etkin renk düzeltmesinin çalışması için artık gözle değişiklik ayarlamasını çalıştırmaları gerekmez. Bunun yerine yalnızca çalışacaktır.
* **Renk ayarlama geliştirmeleri.** Bu güncelleştirme, koyu renklerin renk değerlerine odaklanır (örneğin, koyu gri). Şu anda renkleri karartma kırmızı bir ton seçin. Bu sorun, tüm ekran soluk olduğu için de gerçekleşir. tüm ekran kırmızı renkleri kullanır. Bu sorun, daha koyu renkler için kırmızı renk kanalında çok fazla etkinliğin bir sonucudur. Lazer Aydınlatma eğrilerini bu renk, renkler üzerinde niteliyoruz ve bir Kullanıcı ayar yordamı sunmak üzere çalışmaktadır. Sonuç, parlaklık spektrumu genelinde daha fazla renk doğruluğu olacaktır. Tam parlaklığa göre beyaz arka planların görünümünü değiştirmez. Uygulamalarda koyu modlu tasarım düzenlerini kullanmaya devam ediyoruz.
* **Okuma modu.** Uygulama geliştiricilerinin, daha yüksek Ansal çözüm elde etmek için Görünüm alanını zorunluluğunu getirir. Uygulama geliştiricileri, içeriğin ekran çizim çözünürlüğünde işlenmesi için İzdüşüm matrisini geçersiz kılabilir. Bu özellik, görünüm alanı ve angular çözünürlüğünde karşılık gelen artış %30 oranında azalmayla sonuçlanır. Bu özelliği [karma gerçeklik araç seti](https://github.com/Microsoft/MixedRealityToolkit-Unity)'ne tanıtmak için iş devam eden bir çalışmadır. Kullanılabilir olduğunda, okuma modu herhangi bir HoloLens 2 IŞLETIM sisteminde çalışır; bir işletim sistemi güncelleştirmesine bağımlı değildir.

İşletim sistemi güncelleştirmeleri otomatik olarak dağıtılır. Ayrıca, Insider Preview programı aracılığıyla yazılım geliştirme 'nin erken sürümlerini test edebilirsiniz.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Geliştiricilerin koyu modda tasarım ilkelerini uygulaması için hangi rehberlik vardır?

Kullanıcılar beyaz arka planların önlenmesiyle en iyi deneyimlere sahip olur. Koyu mod, uygulamalar tarafından siyah veya koyu renkli bir arka plan kullanmak için kullanılan bir tasarım ilkesidir. Sistem ayarları varsayılan olarak koyu modda ayarlanır ve **Ayarlar**  >  **sistem**  >  **rengine** giderek ayarlanabilir.

Geliştiricilerin koyu modda tasarım kılavuzunu izlemesi önerilir:

* [HoloLens ekranları için geliştirici tasarımı yönergeleri](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Önerilen yazı tipi boyutları](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Bir hologram beyaz bir arka plan gerektirdiğinde, hologram boyutunu görünümün tam alanından daha küçük tutun. Bu boyut, kullanıcıların hologram görüntüsünü ekran merkezine yerleştirmeye olanak tanır.

### <a name="how-do-you-clean-a-hololens-2-display"></a>HoloLens 2 görüntüsünü nasıl temizleyirim?

Bir mikro fiber bezi kullanarak, vizörü 'yi yavaşça temizleyin. Vizörü 'yi temizlemek için %70 ısopropyıl alkol kullanarak bir bezle, sonra da vizörü 'yi silebilirsiniz. [HoloLens 2 TEMIZLEME SSS](hololens2-maintenance.md)içindeki tam kılavuzu okuyun.
