---
title: Karma Gerçeklik fotoğraflarını ve videoları yakalayın, kaydedin ve paylaşabilirsiniz
description: HoloLens karma gerçeklik cihazlarını kullanarak, karma gerçeklik fotoğraflarını ve videoları nasıl yakaleyeceğinizi, kaydedeceğinizi ve görüntüleyebileceğinizi öğrenin. Miracast veya toplanan dosyalar aracılığıyla nasıl paylaşılacağını öğrenin.
keywords: Hololens, fotoğraf, video, yakalama, MRC, karma gerçeklik yakalama, fotoğraflar, kamera, Miracast, Stream, Livestream, demo, kayıt
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635968"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Karma Gerçeklik fotoğrafları ve videoları oluşturun

HoloLens kullanıcılara dijital dünyanın gerçek dünyasını karıştırma deneyimi sağlar.  Karma gerçeklik yakalama (MRC), bu deneyimi bir fotoğraf veya video olarak yakalamanıza ya da diğer kişilerle gerçek zamanlı olarak gördüklerinizi paylaşmanıza olanak sağlar.

Karma gerçeklik yakalama, diğer kişilerin gördüğünüz hologramlar görebilmesi için birinci kişi bir görünüm noktasını kullanır. Üçüncü kişi görünümü için [Spectator View](/windows/mixed-reality/spectator-view)kullanın. Spectator görünümü, tanıtımlar için özellikle faydalıdır.

Videoları arkadaşlar ve iş arkadaşlarınızla paylaşmak eğlencede olsa da, videolar diğer kişilerin bir uygulama kullanmasına ya da uygulama ve deneyimlerle ilgili sorunları iletmenize yardımcı olabilir.

> [!NOTE]
> karma gerçeklik yakalama deneyimlerini başlatamadıysanız ve HoloLens bir iş cihazından, sistem yöneticinizle görüşün. Kameraya erişim şirket ilkesiyle kısıtlanabilir.

## <a name="capture-a-mixed-reality-photo"></a>Karma Gerçeklik fotoğrafını yakalama

HoloLens bir karışık gerçeklik fotoğrafı almanın birkaç yolu vardır; donanım düğmeleri, ses veya Başlat menüsü kullanabilirsiniz.

### <a name="hardware-buttons-to-take-photos"></a>Fotoğraf çekmek için donanım düğmeleri

Geçerli görünümlerinizin hızlı bir fotoğrafını almak için, aynı anda ses ve ses düzeyi düğmelerine basın.  bu, bir ekran görüntüsü veya yazdırma ekranının HoloLens sürümü gibi bir bittir.

- [HoloLens 2 üzerinde düğme konumları](hololens2-hardware.md)
- [HoloLens üzerindeki düğme konumları (1. genel)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> **Birim yukarı** ve **ses azaltma** düğmelerinin üç saniye boyunca tutulması, fotoğraf almak yerine video kaydetmeye başlar. Kaydı durdurmak için hem **birim yukarı** hem de **Birim aşağı** düğmelerine aynı anda dokunun.

### <a name="voice-commands-to-take-photos"></a>Fotoğraf çekmek için sesli komutlar

HoloLens 2 ' de, sürüm 2004 (ve üzeri) ile: "bir resim al" deyin.

HoloLens (1. gen) veya HoloLens 2, sürüm 1903, "Hey Cortana, bir resim alın."

### <a name="start-menu-to-take-photos"></a>fotoğraf çekmek için Başlat menüsü

Başlangıç hareketini kullanarak **Başlat**' a gidin ve ardından **Kamera** simgesini seçin.

Havadan yakalamak istediğiniz yönü işaret edin ve ardından fotoğraf çekmek için [AIR ' e dokunun](hololens2-basic-usage.md#touch-holograms-near-you) . AIR 'e dokunmanıza ve ek fotoğraflar yakalamaya devam edebilirsiniz. Yakaladığınız tüm fotoğraflar cihazınıza kaydedilir.

Fotoğraf yakalamayı sonlandırmak için başlangıç hareketini yeniden kullanın.  

## <a name="capture-a-mixed-reality-video"></a>Karma Gerçeklik videosu yakalama

HoloLens, karışık gerçeklik videosunu kaydetmek için birkaç yol vardır. donanım düğmeleri, ses veya Başlat menüsü kullanabilirsiniz.

### <a name="hardware-buttons-to-record-videos"></a>Videoları kaydetmek için donanım düğmeleri

Bir videoyu kaydetme işleminin en hızlı yolu, üç saniyelik bir geri sayıma başlamadan önce **hacmi yukarı** ve **ses aşağı** düğmelerini aynı anda basılı tutmaktır. Kaydı durdurmak için her iki düğmeye aynı anda dokunun.

> [!NOTE]
> **Birim yukarı** ve **ses azaltma** düğmelerine aynı anda hızlı bir şekilde basmak, video kaydetmek yerine bir fotoğraf alacak.

### <a name="voice-to-record-videos"></a>Videoları kaydetmek için ses

HoloLens 2, sürüm 2004 (ve üzeri), "kaydı başlat" deyin. Kaydı durdurmak için "Kaydı Durdur" deyin.

HoloLens (1. gen) veya HoloLens 2, sürüm 1903, "Hey Cortana, kaydı başlat." kaydı durdurmak için "Hey Cortana, kaydı durdur" deyin.

### <a name="start-menu-to-record-videos"></a>videoları kaydetmek için Başlat menüsü

Başlangıç hareketini kullanarak **Başlat**' a gidin, ardından **video** simgesini seçin. Kafanızı yakalamak istediğiniz yöne getirin, sonra kayda başlamak için [AIR ' e dokunun](hololens2-basic-usage.md#touch-holograms-near-you) . Üç saniyelik bir geri sayım olacaktır ve kaydınız başlatılır.

Kaydı durdurmak için başlangıç hareketini kullanın ve vurgulanan **video** simgesini seçin. Video cihazınıza kaydedilir.

> [!NOTE]
> **yalnızca HoloLens için geçerlidir (1. genel)**  
> [Windows 10 Ekim 2018 Güncelleştirmesi](/windows/mixed-reality/release-notes-october-2018) , başlangıç hareketini ve Windows düğmesinin HoloLens (1. gen) üzerinde nasıl davranacağını değiştirir. güncelleştirmeden önce, başlangıç hareketi veya Windows düğmesi bir video kaydını durdurabilir. güncelleştirme sonrasında, başlangıç hareketi veya Windows düğmesi **başlangıç** menüsünü açar (veya bir modern uygulamanız varsa **hızlı eylemler menüsünü** ), buradan kaydı durdurmak için vurgulanan **video** simgesini seçebilirsiniz.

## <a name="share-what-you-see-in-real-time"></a>Gerçek zamanlı olarak gördüklerinizi paylaşma

arkadaşlarınızla ve iş arkadaşlarınızla gerçek zamanlı olarak HoloLens gördüklerinizi paylaşabilirsiniz. Kullanılabilecek birkaç yöntem vardır:

1. TV 'de izlemek için Miracast özellikli bir cihaza veya bağdaştırıcıya bağlanma.
1. bir PC 'de izlemek için [Windows cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal) kullanma
1. bir PC 'de izlemek için [Microsoft HoloLens yardımcı uygulamasını](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) kullanma.
1. Ön hat çalışanlarının uzak bir uzman 'a gördüklerine akışını sağlayan [Microsoft Dynamics 365 uzaktan yardım](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) uygulamasını dağıtma. Bu durumda, uzak uzman daha sonra ön satır çalışan verbbüne veya dünyasına açıklama ekleyebilir.

> [!NOTE]
> Windows cihaz portalı veya Microsoft HoloLens yardımcı uygulama aracılığıyla gördüklerinizi paylaşmak için HoloLens [geliştirici modunda](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)olması gerekir.

### <a name="stream-video-with-miracast"></a>Miracast ile video akışı

başlangıç hareketini kullanarak **başlat**' a gidin ve **Bağlan** simgesini seçin. görüntülenen seçicisinden, bağlanmak istediğiniz Miracast etkinleştirilmiş cihazı veya bağdaştırıcıyı seçin.

paylaşımı durdurmak için başlangıç hareketini kullanın ve vurgulanan **Bağlan** simgesini seçin. Akış yaptığınız için hiçbir şey cihazınıza kaydedilmez.

> [!NOTE]
> Miracast desteği, [Windows 10 Ekim 2018 Güncelleştirmesi](/windows/mixed-reality/release-notes-october-2018)başlayarak HoloLens (1. gen) üzerinde etkinleştirildi.

### <a name="real-time-video-with-windows-device-portal"></a>Windows cihaz portalı ile gerçek zamanlı video

Windows cihaz portalı aracılığıyla paylaşım için geliştirici modunun HoloLens etkinleştirilmiş olması gerektiğinden, geliştirici [modunu ayarlamak ve Windows cihaz portalında gezinmek](/windows/mixed-reality/using-the-windows-device-portal)için geliştirici belgelerimizin yönergelerini izleyin.

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens yardımcı uygulama

Microsoft HoloLens yardımcı uygulama aracılığıyla paylaşım, HoloLens üzerinde geliştirici modunun etkinleştirilmesini gerektirdiğinden geliştirici [modunu ayarlamak](/windows/mixed-reality/using-the-windows-device-portal)için geliştirici belgelerimizin yönergelerini izleyin. sonra, [Microsoft HoloLens yardımcı uygulamasını](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) indirin ve HoloLens bağlanmak için uygulama içindeki yönergeleri izleyin.

uygulama HoloLens ile kurulduktan sonra, uygulamanın ana menüsünde **canlı akış** seçeneğini belirleyin.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Karma Gerçeklik fotoğraflarınızı ve videolarınızı görüntüleyin

Karma Gerçeklik fotoğrafları ve videoları cihazın "kamera rulosu" a kaydedilir. dosya gezgini uygulamasıyla bu klasörün içeriklerine HoloLens gidebilirsiniz ( **resimlere > kamera rulosu**).

Karma Gerçeklik fotoğraflarınızı ve videolarınızı, HoloLens önceden yüklenmiş olan Fotoğraflar uygulamasında da görüntüleyebilirsiniz. Bir fotoğrafı dünyayı sabitlemek için Fotoğraflar uygulamasında seçip **karışık dünyada yerleştir**' i seçin. Yerleştirildikten sonra fotoğrafı dünyanın dört bir yanındaki taşıyabilirsiniz.

karma gerçeklik fotoğraflarınızı ve videolarınızı HoloLens bağlı bir bilgisayara görüntülemek ve/veya kaydetmek için, [Windows cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) veya bilgisayarınızın [dosya gezginini MTP aracılığıyla](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)kullanabilirsiniz.

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Resimlerinizi, videolarınızı ve dosyalarınızı almak için dosya Gezgini 'ni kullanın

diğer mobil cihazlara benzer şekilde, daha kolay aktarım için HoloLens kitaplıklara (fotoğraflar, videolar, belgeler) erişmek üzere dosya gezgini 'ni açmak üzere bilgisayarınıza HoloLens bağlayın. Bu yöntemin kullanımı kolaydır ve cihaz portalının veya Wi-Fi kullanımını gerektirmez.

1. Cihazın kilidini açın.
1. cihazı USB üzerinden bir bilgisayara Bağlan.
1. Dosya Gezgini, bilgisayarınızda açık olmalıdır.
1. şuraya gidin: bu bilgisayar \\ *yourholomersname*\ınternal Depolama \resim\camera rulosu
1. Bilgisayarınıza ihtiyacınız olan dosyaları kopyalayın.

İpuçları:
- hiçbir dosya görmüyorsanız, verilerinize erişim sağlamak için lütfen HoloLens oturum açarak emin olun.
- Belgeler klasöründeki [Tanılama dosyaları](hololens-diagnostic-logs.md#offline-diagnostics) gibi diğer klasörlerdeki diğer dosyaları da alabilirsiniz.
- bilgisayarınızdaki dosya gezgini 'nden cihaz özelliklerini seçerek Windows Holographic OS sürüm numarasını (bellenim sürümü), cihaz seri numarası ve pil yüzdesini görebilirsiniz.
- Kuruluşunuz [bağlantı/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 'ı devre dışı BıRAKMAK için MDM 'yi kullanmışsa, cihazınıza bağlanamazsınız.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Karma Gerçeklik fotoğraflarınızı ve videolarınızı paylaşma

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)' den önce, karma gerçeklik fotoğrafını veya videosunu yakaladıktan sonra bir önizleme görüntülenir. Paylaşma yardımcısını açmak için önizlemenin üzerindeki **paylaşma** simgesini seçin. Buradan, bu fotoğrafı veya videoyu paylaşmak istediğiniz bitiş noktasını seçebilirsiniz.

Windows Holographic, sürüm 21h1 ile, karma gerçeklik fotoğrafını veya videosunu yakaladıktan sonra önizleme görüntülenir. Paylaşma yardımcısını açmak için önizlemenin üzerindeki **paylaşma** simgesini seçin. buradan, bu fotoğrafı veya videoyu paylaşmak istediğiniz bitiş noktasını (posta, OneDrive vb.) seçebilirsiniz. -> System -HoloLens Paylaşılan Deneyimler'e gidip Ayarlar cihazlarınızı > **etkinleştirebilirsiniz.** Diğer ayrıntılar için, [Windows 10'da yakındaki cihazlarla Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

> [!TIP] 
> Karma gerçeklik fotoğraflarınızı ve videolarınızı otomatik olarak karşıya yük OneDrive karma gerçeklik fotoğraf ve videolarını da paylaşabilirsiniz. Henüz OneDrive uygulama HoloLens kişisel bir Microsoft hesabı ile **oturum [](https://account.microsoft.com)** açın. Uygulama simgesini **Ayarlar** Kamera karşıya **yükle'yi seçin.** Kamera karşıya yükleme'nizi açma. Karma gerçeklik fotoğraflarınız ve videolarınız artık uygulamayı OneDrive her HoloLens.

> [!NOTE]
> Kamera karşıya yüklemeyi yalnızca OneDrive kişisel bir kullanıcıyla OneDrive oturum Microsoft hesabı. Bu özelliği etkinleştirmek HoloLens bir iş veya okul hesabıyla bir Microsoft hesabı hesabı OneDrive bir kişisel hesap eklersiniz.

## <a name="limitations-of-mixed-reality-capture"></a>Karma gerçeklik yakalama sınırlamaları

- Karma gerçeklik yakalaması kullanırken, sanal HoloLens kare hızı yarıya inecek ve yarıya inecek.
- Fotoğraf/video kamerası başka bir uygulama tarafından zaten kullanıyorsa, canlı akış sırasında veya sistem kaynakları düşükse fotoğrafların ve videoların çözünürlüğü azaltabilirsiniz.

### <a name="maximum-recording-length"></a>Maksimum kayıt uzunluğu

HoloLens Holographic sürüm 20H2 Windows den önceki 2 cihazda, cihaza kaydedilen videolar en fazla beş dakika uzunluğundaydı.

Müşteri geri bildirimleri nedeniyle karma gerçeklik yakalamalarının kayıt [uzunluğunu artırıldı.](holographic-photos-and-videos.md) Karma gerçeklik yakalamaları artık varsayılan olarak 5 dakikayla sınırlı olmayacaktır, ancak bunun yerine kullanılabilir disk alanı temel alarak maksimum kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanını %80'e kadar olan kullanılabilir disk alanını temel alarak maksimum video kayıt süresini tahmin eder.

> [!NOTE]
> Aşağıdaki HoloLens biri gerçekleşirse varsayılan video kayıt uzunluğunu (5 dakika) kullanır:
> - Tahmini maksimum kayıt süresi, varsayılan 5 dakikadan küçüktür.
> - Kullanılabilir disk alanı toplam disk alanı %20'den azdır.

## <a name="default-file-format-and-resolution"></a>Varsayılan dosya biçimi ve çözümü

### <a name="default-photo-format-and-resolution"></a>Varsayılan fotoğraf biçimi ve çözünürlüğü

|  Cihaz  |  Biçimlendir  |  Uzantı  |  Çözüm  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. nesil) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Kaydedilen video biçimi ve çözünürlüğü

| Cihaz | Biçimlendir | Uzantı | Çözüm | Hız | Ses |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz Stereo |
| HoloLens (1. nesil) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz Stereo |
