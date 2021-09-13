---
title: HoloLens 2 Görüntü Sorunlarını Giderme
description: 2 ekran HoloLens için beklentiler. En iyi görüntü kalitesi için ekranları yapılandırma kılavuzu.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: görüntüleme, ayarlama, konfor, görseller, kalite, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036444"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 Görüntü Sorunlarını Giderme

## <a name="overview"></a>Genel Bakış
İlk HoloLens 2 ekranı dalga kılavuzlarının ve ışık yansıtıcılarının bir birleşimidir. Kullanıcılar başlığı takmışken dalga kılavuzlarını (göz içindeki lensleri) bakar. Işık yansıtıcıları,gözün üzerindeki kasanın içindedir. HoloLens 2' de ekranda güneş ışığını kullanır.

## <a name="troubleshooting"></a>Sorun giderme

Ekranlarda sunulan en yüksek görsel hologram kalitesini sağlamak için aşağıdaki adımları uygulayın:

* **Ekranın parlaklığını artırma.** Hologramlar en parlak düzeyde olduğunda en iyi şekilde görünüyor. Düğmeyi HoloLens, parlaklığı düğmeleri, mabedin yakınındaki mengenenin sol tarafında bulunur.
* **Visor'ı gözlere yaklaştırın.** Gözlerinizi en yakın konuma getirin.
* **Mengeneyi aşağı kaydır.** Baş aşağı doğru hareket ettirin ve bu da mengenin buruna yakın bir yere inlmesiyle sonuçlandır.
* **[Göz ayarlamayı çalıştırın.](hololens-calibration.md#calibrating-your-hololens-2)** Ekranda, görüntüde görüntüleri iyileştirmek için aralıklar arası mesafe (IPD) ve göz bakışı kullanır. Göz ayarlaması çalıştırdıysanız görüntü kalitesi daha kötü hale getirebilir. Göz ayarlamayı çalıştırmak için Sistem **Ayarlar**  >  **Çalıştırma göz**  >    >  **ayarına gidin.**
* **Görüntü rengi ayarı çalıştırın.** [Holographic Windows sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonra, 2  ekran için alternatif bir renk profili HoloLens belirtebilirsiniz. Bu, renklerin özellikle daha düşük ekran parlaklığı düzeylerinde daha doğru görünmesine yardımcı olabilir. Ekran rengi düzeltmesi, Ayarlar **uygulamasında,** System > **Ayarlama sayfasında** bulunabilir.

    > [!NOTE]
    > Bu ayar görüntü üretici yazılımınıza yeni bir renk profili kaydedeci, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

### <a name="how-to-use-display-color-calibration"></a>Görüntü rengi ayarlamayı kullanma
1. Uygulama uygulamasını **Ayarlar** System > **Ayarlama'ya gidin.**
1. Renk **ayarı görüntüle'nin** altında Renk **görüntüleme düzenini çalıştır düğmesini** seçin.
1. Ekran rengi ayarlama deneyimi başlatacak ve sizi, mengenenizin doğru konumda olduğundan emin olmak için teşvik eder.
1. Yönerge iletişim kutularına devam ettikten sonra, ekranınız otomatik olarak %30 parlaklığa soluk görüntülenir.
    > [!TIP]
    > Ortamınız soluk sahneyi görme konusunda sorun taşıyorsanız, cihazın sol tarafındaki parlaklığı düğmeleri kullanarak HoloLens 2'nin parlaklığını el ile ayarlayabilirsiniz.
1. Her renk profilini anında denemek için 1-6 düğmelerini seçin ve en iyi görüneni bulun (bu genellikle sahnenin gri tonlamalı desen ve ten rengi beklendiği gibi görünmesiyle sahnenin en nötr görünmesine yardımcı olan profil anlamına gelir).)

    ![Renk ayarı sahneyi görüntüleme.](images/color-cal-ui.png)
    
6. Seçilen profilden memnun değilken Kaydet ve Çıkış **&** seçin
1. Değişiklik yapmamayı tercih ederseniz, İptal et **& düğmesini** seçin; değişiklikleriniz geri döner

> [!TIP]
> Burada, görüntü rengi ayarıyla ilgili bazı yararlı ipuçlarına göz ayın:
> - Ekran renklerini istediğiniz zaman Ayarlar yeniden çalıştırarak
> - Cihaz üzerinde herhangi biri renk profillerini değiştirmek için daha önce bu ayarı kullandısa, en son değişikliğin tarih/saat ayarı Ayarlar yansıtılandır
> - Görüntü rengi ayarlamayı yeniden çalıştırarak daha önce kaydedilen renk profili vurgulanır ve Profil 0 görünmez (Profil 0, ekranın özgün renk profilini temsil ettiği için)
> - Ekranın özgün renk profiline geri dönmek için bu işlemi Ayarlar sayfasından (bkz. renk profilini [sıfırlama)](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama

HoloLens 2'nize kaydedilen özel renk profili sizi üzerse, cihazın özgün renk profilini geri yükleyebilirsiniz:
1. Uygulama uygulamasını **Ayarlar** System > **Ayarlama'ya gidin.**
1. Renk **ayarı görüntüle altında** Varsayılan renk **profiline sıfırla düğmesini** seçin.
1. İletişim kutusu açıldığında, 2. **sunucuya** yeniden başlatmaya ve değişikliklerinizi HoloLens Yeniden Başlat'ı seçin.

### <a name="top-display-color-calibration-known-issues"></a>Bilinen en çok görünen renk ayarı sorunları

- Ayarlar sayfasında, renk profilinin en son ne zaman değiştirdiğini size söyleyen durum dizesi, ilgili sayfayı yeniden yükleyene kadar Ayarlar 
    - **Geçici** çözüm: Ayarlar sayfayı seçin ve Sonra Ayarlama sayfasını yeniden seçin.
- Ekran HoloLens 2'niz çalışırken uykuda olursa, daha sonra karma gerçeklik giriş ekranına devam eder ve ekran parlaklığı düzeyiniz soluk görüntülenir.
- Cihazınızın sol tarafındaki parlaklık düğmelerine beklendiği gibi çalışmadan önce birkaç kez yukarı/aşağı basabilirsiniz.
- Tüm pazarlar için yerelleştirme tamamlanmadı

## <a name="faq"></a>SSS

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Ekranın alt köşelerinde zaman zaman yanıp sönen desenler hangileridir?

Bazen, HoloLens 2'niz ekranın sol alt ve sağ köşelerinde farklı desenler gösterir. Örnekler aşağıda gösterilmiştir (animasyonlu GIF). Bu düzen, ekranı en iyi deneyim için ayarlamak HoloLens 2 cihazınızın normal çalışma şeklidir.

![İki aşamalı desen.](./images/DAT-Biphase-Fiducial.gif) ![COĞRAFI desen](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Neden HoloLens 2 ekranımı doğru HoloLens alamayım?

HoloLens 2 ekranı, insan gözü tarafından görüntülenmek üzere tasarlanmıştır. Cihazın, kullanıcının gözüne uyum sağlanmış etkin bir renk düzeltme sistemi vardır. İnsan gözüyle karşılaştırıldığında kameraların ortamları farklı ve aşağıda görmesi, kameranın yakalaması ile kullanıcının gördüğü şeyler arasındaki tutarsızlığı etkileyebilen bazı faktörlerdir.

* **Göz konumu.** HoloLens 2 ekranı, kullanıcının göz konumu için özel olarak tasarlanmıştır. Bu HoloLens 2, kullanıcının göz pozisyonuna uyum sağlamak için göz izleme teknolojisini kullanır. Birkaç milimetrenin yanlış konumlandırmış olduğu bir kamera, görüntüde bozulmaya neden olabilir. Kamerayla doğru konumlandırma zordur ve cihazın renk düzeltmesi gerçekleştirecek olduğu konum ve göz düzeltmesi ile tam olarak eşleşmesi gerekir.
* **Göz hareketi.** Ekran, renkleri ayarlamak için kullanıcının gözü hareketine uyum sağlar. Kullanıcının ekranın merkezine, kenarına veya köşesine bakarak ekranda gösterilenler farklılık gösterebilir. Tek bir görüntü yakalama en iyi şekilde yalnızca bir göz bakış yönüyle eşleşen eksen için ekranın nasıl göründüğünü gösterebilir.
* **Dürbün görüntüleme.** HoloLens 2 ekranı, her iki göz ile de görüntülenmek üzere tasarlanmıştır. Beyin iki görüntü görmeye uyum sağlar ve bunları bir arada birleştirmeye devam ediyor. Yalnızca bir ekranın görüntüleri diğer ekrandan gelen bilgileri yoksayar.
* **Kameraya maruz kalma süresi.** Kameranın maruz kalma süresi, saniyenin 1/120'sinde tam olarak katlarıdır. Ekran HoloLens hızı 120Hz'tir. HoloLens 2'nin görüntü çekme yolu nedeniyle, tek bir karenin yakalanması da bir insanın görsel deneyimiyle eşleşmek için yeterli değildir. Aynı zamanda, cihaz hiç hareket ederse (hatta mikromoveyalar) sistem hologramları kararlı hale getirecek şekilde görüntü üzerinde yeniden projelenir. Birden çok karenin yakalanması ve HoloLens bir laboratuvar kurulumu gerekir.
* **Kamera ölçüsü boyutu.** Doğru bir görüntüyü yakalamak için kameranın en az 3 mm boyutunda olması gerekir. Küçük cep telefonu kameraları, insan gözüne göre daha küçük bir alandan gelen ışığı tümleştirin. Cihaz, daha büyük büyük büyükler tarafından gözlemlenen desenler için renk düzeltmesi uygular. Küçük görüntülerle, tekdüzlük desenleri daha nettir ve sistem tarafından uygulanan renk düzeltmelerine rağmen görünür durumda kalır.
* **Kamera giriş gözbebeği.** Doğru bir görüntü yakalamak için kameranın giriş gözbebeği en az 3 mm uzunluğunda olmalıdır. Aksi takdirde kamera, göze görünmeyebilen bazı yüksek frekanslı desenleri yakalar. Giriş gözbebeğinin konumu, yakalanan görüntüye sapmalar ve diğer çeşitlemeler katmak için hem kameranın önünde hem de göz yardım uzaklığında yer alıyor olması gerekir.
* **Kamera konumu.** HoloLens 2 görüntüsünü görüntüleme gereksinimlerini karşıleyen kameralar daha büyüktür ve düzeltilen rengi gözlemlemek için kamerayı HoloLens 2 ekranına kadar konumlandırmak zordur. Kamera yanlış yerde ise renk düzeltmesi, 2 ekran görüntüsünde HoloLens etkileniyor olabilir.
* **Görüntü düzeltme.** Tipik dijital kameralar ve akıllı telefon kameraları, daha hızlı bir sonuç elde etmek için karşıtlığı ve rengi artıran bir ton yeniden üretme eğrisi (TRC) sunar. Bu ton eğrisi, HoloLens 2 ekranına uygulandığında, tekdüzlere karşı daha fazla genlik sağlar.

Tüm bunlar, özel endüstriyel kameraların 2 ekrandan temsili görüntüleri yakalaması HoloLens mümkündür. ne yazık ki, smartphone, tüketici ve profesyonel kameralar, kullanıcının HoloLens 2 ' de gördüğü şekilde eşleşen resimleri yakalamaz.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Görüntü kalitesini göstermek için göz ayarlama nedir?

HoloLens 2, kullanıcı gözlerinizin konumunu temel alarak etkin renkte renkleri düzeltir. [Göz ayarlama](hololens-calibration.md) iki önemli giriş sağlar: (1) kullanıcının ınterpupilılmi (IPD) ve (2) her bir gözle arama yönü. Göz ayarlama olmadan sistem, göz önünde olmayan bir gözle varsayılan olarak kabul edin. Etkin renk düzeltme ve düzeltme olmadan fark, kullanıcının kendi zevklerine göre değişir. Örneğin, sistem varsayılanı ile aynı ıPD 'ye sahip kullanıcılar daha az renk düzeltme geliştirmesi görür. Daha dar veya daha geniş bir sistem sistemi olan kullanıcılar, ekran görüntüsünde daha fazla değişiklik görür.

[Windows Holographic version 20h2 sürümündeki](hololens-release-notes.md#windows-holographic-version-20h2) yeni bir özellik, [gözle otomatik olarak algılanacaktır](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>HoloLens (1. gen) ve HoloLens 2 arasındaki görüntüleme farkları nelerdir?

önde gelen istekler arasında HoloLens 1 ' den sonra Microsoft 'un verdiği müşteriler, (1) görünüm alanını artırın ve (2) parlaklığı artırın. Teknoloji geliştirmeleri, Microsoft 'un, görünümün alanını iki katına çıkarmış ve en fazla üç kat daha parlakla hafif projektörler üreten dalga kılavuzlarını üretmesine izin verir. Donanım, görüntüleme görüntüsü kalitesi: (1), görünüm alanı, (2) parlaklığı ve (3) renk bütünlüğü için bir esneklik için temeli ayarlar. Devam eden teknoloji gelişmeleri, başka bir alandan ödün vermeden tüm alanlarda iyileştirmeler yapılmasına izin verir. Bu arada, mevcut teknoloji bu avantajları için kullanılabilen sınırları ayarlar.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>HoloLens 2 görüntü kalitesini iyileştirecek geliştirmeler ne olur?

Görüntü kalitesini geliştirecek birçok araştırma yaptığımız için aşağıdaki alanların yaklaşan güncelleştirmelere gelmesi beklenmektedir:

* **Otomatik göz konumu.** Bu özellik, göz ayarlama yordamlarını arka planda gerçekleştirecektir. Kullanıcıların, etkin renk düzeltmesinin çalışması için artık gözle değişiklik ayarlamasını çalıştırmaları gerekmez. Bunun yerine yalnızca çalışacaktır.
* **Renk ayarlama geliştirmeleri.** Bu güncelleştirme, koyu renklerin renk değerlerine odaklanır (örneğin, koyu gri). Şu anda renkleri karartma kırmızı bir ton seçin. Bu sorun, tüm ekran soluk olduğu için de gerçekleşir. tüm ekran kırmızı renkleri kullanır. Bu sorun, daha koyu renkler için kırmızı renk kanalında çok fazla etkinliğin bir sonucudur. Lazer Aydınlatma eğrilerini bu renk, renkler üzerinde niteliyoruz ve bir Kullanıcı ayar yordamı sunmak üzere çalışmaktadır. Sonuç, parlaklık spektrumu genelinde daha fazla renk doğruluğu olacaktır. Tam parlaklığa göre beyaz arka planların görünümünü değiştirmez. Uygulamalarda koyu modlu tasarım düzenlerini kullanmaya devam ediyoruz.
* **Okuma modu.** Uygulama geliştiricilerinin, daha yüksek Ansal çözüm elde etmek için Görünüm alanını zorunluluğunu getirir. Uygulama geliştiricileri, içeriğin ekran çizim çözünürlüğünde işlenmesi için İzdüşüm matrisini geçersiz kılabilir. Bu özellik, görünüm alanı ve angular çözünürlüğünde karşılık gelen artış %30 oranında azalmayla sonuçlanır. Bu özelliği [karma gerçeklik araç seti](https://github.com/Microsoft/MixedRealityToolkit-Unity)'ne tanıtmak için iş devam eden bir çalışmadır. kullanılabilir olduğunda okuma modu herhangi bir HoloLens 2 işletim sisteminde çalışır; bir işletim sistemi güncelleştirmesine bağlı değildir.

İşletim sistemi güncelleştirmeleri otomatik olarak dağıtılır. Ayrıca, Insider Preview programı aracılığıyla yazılım geliştirme 'nin erken sürümlerini test edebilirsiniz.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Geliştiricilerin koyu modda tasarım ilkelerini uygulaması için hangi rehberlik vardır?

Kullanıcılar beyaz arka planların önlenmesiyle en iyi deneyimlere sahip olur. Koyu mod, uygulamalar tarafından siyah veya koyu renkli bir arka plan kullanmak için kullanılan bir tasarım ilkesidir. sistem ayarları varsayılan olarak koyu modda ve **Ayarlar**  >  **sistem**  >  **rengine** giderek ayarlanabilir.

Geliştiricilerin koyu modda tasarım kılavuzunu izlemesi önerilir:

* [HoloLens ekranlar için geliştirici tasarımı yönergeleri](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Önerilen yazı tipi boyutları](/windows/mixed-reality/typography#recommended-font-size)

Bir hologram beyaz bir arka plan gerektirdiğinde, hologram boyutunu görünümün tam alanından daha küçük tutun. Bu boyut, kullanıcıların hologram görüntüsünü ekran merkezine yerleştirmeye olanak tanır.

### <a name="how-do-you-clean-a-hololens-2-display"></a>HoloLens 2 görüntüsünü nasıl temizleyirsiniz?

Bir mikro fiber bezi kullanarak, vizörü 'yi yavaşça temizleyin. Vizörü 'yi temizlemek için %70 ısopropyıl alkol kullanarak bir bezle, sonra da vizörü 'yi silebilirsiniz. [HoloLens 2 temizleme sss](hololens2-maintenance.md)bölümünde tam kılavuzu okuyun.
