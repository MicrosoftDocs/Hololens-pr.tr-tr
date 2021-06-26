---
title: HoloLens 2 ekran sorunlarını giderme
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
ms.openlocfilehash: 96bacd79d559bc0adcd42665c4a8b4af856b58b0
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923627"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 ekran sorunlarını giderme

## <a name="overview"></a>Genel Bakış
HoloLens 2 ekranı, waveguides ve açık projektörlerin bir birleşimidir. Kullanıcılar, kulaklık taktığında (örneğin, vizörü içindeki mercekler) dalga kılavuzlarını gözden geçirin. Hafif projektörler, Brow 'ın üzerindeki kutunun içindedir. HoloLens 2, görüntüyü aydınlatmak için lazer ışığı kullanır.

## <a name="troubleshooting"></a>Sorun giderme

Aşağıda gösterilen en yüksek görsel kalite kalitesi kalitesini sağlamak için aşağıdaki adımları uygulayın:

* **Ekran parlaklığını artırın.** Hologragram, ekran en parlak test düzeyinde olduğunda en iyi şekilde görünür. HoloLens 'i takdığınızda, parlaklık düğmeleri, tüm vizörü 'ın Temple yakın tarafında yer alır.
* **Daha yakından gözlerinize göz katın.** Gözlerinizi en yakın konuma göre aşağı doğru kaydırın.
* **Kaydırma vizörü aşağı.** Bir tebede aşağı doğru hareket ettirmenize, bu da vizörü 'ın burun yakınına yaklaştırmasını deneyin.
* **[Göz ayarlamayı Çalıştır.](hololens-calibration.md#calibrating-your-hololens-2)** Görüntü, ekranda görüntüleri iyileştirmek için ınterpupilılmi (ıPD) ve gözle göz çıkarması kullanır. Göz ayarlama 'yı çalıştırmazsanız görüntü kalitesi daha kötü hale getirilebilir. Göz ayarlama 'yı çalıştırmak için **Ayarlar**  >  **sistem**  >  **ayarı**  >  **çalışma göz ayarlama**' ya gidin.
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

Hepsi, özelleştirilmiş endüstriyel kameraların HoloLens 2 görüntülerinden temsili görüntüleri yakalaması için hala mümkündür. Ne yazık ki akıllı telefon, tüketici ve profesyonel kameralar, kullanıcının HoloLens 2'de gördüğü görüntülerle eşleşmez.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Göz alıcısı görüntü kalitesini görüntülemek için ne yapar?

HoloLens 2 ekranı, görüntüleri kullanıcının gözüne göre etkin bir şekilde düzeltiyor. [Göz kılı](hololens-calibration.md) iki önemli giriş sağlar: (1) kullanıcının etkileşim uzaklığı (IPD) ve (2) her bir gözün bakarak yönü. Göz ayarı olmadan sistem varsayılan olarak göz hareketi olmayan nominal bir göz pozisyonuna sahiptir. Etkin renk düzeltmesi ile düzeltme arasındaki fark, kullanıcının kendi fiziksel durumuna bağlıdır. Örneğin, sistem varsayılanı ile aynı IPD'ye sahip kullanıcılar daha az renk düzeltmesi geliştirmesi görebilir. IpD değeri sistem varsayılan ayarından çok daha dar veya daha geniş olan kullanıcılar görüntü görüntüsünde daha fazla değişiklik görebilir.

[Windows Holographic sürüm 20H2'de](hololens-release-notes.md#windows-holographic-version-20h2) yeni bir özelliğin göz konumunu otomatik [olarak algılamaya başlayacağını unutmayın.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>HoloLens (1. nesil) ile HoloLens 2 arasındaki görüntü farkları nedir?

HoloLens 1'i yaşayan müşterilerin Microsoft'a verdiği en önemli istekler arasında, (1) görünüm alanını artırmak ve (2) parlaklığı artırmaktır. Teknolojideki gelişmeler, Microsoft'un görünüm alanını iki katına çıkaran dalga kılavuzlar üretmesine ve üç kat daha parlak bir ekrana sahip ışık projektörleri üretmesine izin verdi. Donanım, görüntü kalitesi için bir üç takasın taban çizgisini ayarlar: (1) görünüm alanı, (2) parlaklık ve (3) renk tekdüzması. Devam eden teknoloji ilerlemesi, başka bir alandan ödün vermeden tüm alanlarda iyileştirmelere olanak sağlar. Aradaki süre içinde, mevcut teknoloji bu takaslar için kullanılabilir sınırları ayarlar.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>HoloLens 2 görüntü kalitesini geliştirecek hangi geliştirmeler geliyor?

Görüntü kalitesini geliştirmek için birçok araştırmamız devam ederken, gelecek güncelleştirmelerde aşağıdaki alanların gelmesi beklenir:

* **Otomatik Göz Konumu.** Bu özellik, göz yordamlarının arka planda yer almalarını sağlar. Kullanıcıların artık etkin renk düzeltmesi için göz rengi düzeltmesi çalıştırması gerekmeyecek. Bunun yerine yalnızca çalışır.
* **Renk Düzeltmesi Geliştirmeleri.** Bu güncelleştirme daha koyu renklerin (örneğin koyu gri) renk değerlerine odaklanır. Şu anda, dimmer renkleri kırmızı bir ton alır. Bu sorun, tüm ekran soluk görüntüye sahip olduğunda da gerçekleşir; tüm ekran kırmızı renkler alır. Bu sorun, bu koyu renkler için kırmızı renk kanalında çok fazla etkinliğin sonucudur. Bu dimmer renklerine göre lazer eğrisi eğrilerini nitelendirtik ve kullanıcıya bir yordam sunmak için çalışıyoruz. Sonuç, renk spektrumu genelinde daha fazla renk doğruluğu elde etmektir. Beyaz arka planların tam parlaklığa sahip görünümünü değiştirmez. Uygulamalarda koyu mod tasarım desenlerinin kullanımını önerip kullanmaya devam edeceğiz.
* **Okuma Modu.** Uygulama geliştiricilerinin daha yüksek angular çözüm elde etmek için görüntüleme alanı arasında takas yapmak mümkündür. Uygulama geliştiricileri, içeriğin ekranın çizim çözünürlüğünde işlenecek şekilde projeksiyon matrisini geçersiz kabilirsiniz. Bu özellik, görünüm alanında %30 azalmaya ve buna karşılık gelen angular çözümleme artışına neden olur. Karma Gerçeklik Araç Seti'ne bu özelliği tanıtmak [için çalışmalar devam ediyor.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Kullanılabilir olduğunda, okuma modu herhangi bir HoloLens 2 işletim sistemi üzerinde çalışır; işletim sistemi güncelleştirmesine bağımlı değildir.

İşletim sistemi güncelleştirmeleri otomatik olarak teslim edilir. Ayrıca, insider önizleme programı aracılığıyla yazılım geliştirmenin erken yayınlarını da testabilirsiniz.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Geliştiricilerin koyu mod tasarım ilkelerini uygulayacakları kılavuzlar hangileridir?

Beyaz arka planlardan kaçınan kullanıcılar en iyi deneyime sahip olur. Koyu mod, uygulamalar tarafından siyah veya koyu renkli arka planlar kullanmak için kullanılan bir tasarım ilkesidir. Sistem ayarları varsayılan olarak koyu moddur ve Ayarlar Sistem **Rengi'ne gidip**  >    >  **ayarlanabilir.**

Geliştiricilerin koyu mod tasarım yönergelerini izlemesi önerilir:

* [HoloLens ekranları için geliştirici tasarım yönergeleri](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Önerilen yazı tipi boyutları](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Bir hologram için beyaz arka plan gerekli olduğunda, hologram boyutunu ekranın tam görünüm alanından küçük tutabilirsiniz. Bu boyut, kullanıcıların hologramı ekranın merkezine koymalarını sağlar.

### <a name="how-do-you-clean-a-hololens-2-display"></a>HoloLens 2 ekranı nasıl temizlenir?

Bir mikrofiber yalıtarak göz gözlerini tamamen temizleyin. Visor'ı temizlemek için %70 isopropylfaz kullanarak bir sigarayı hafife çekin ve sonra da güneş ışığını temizleyin. [HoloLens 2 temizleme hakkında SSS bölümünü okuyun.](hololens2-maintenance.md)
