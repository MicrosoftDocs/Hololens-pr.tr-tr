---
title: Karma gerçeklik fotoğraflarını ve videolarını yakalama, kaydetme ve paylaşma
description: Karma gerçeklik cihazlarını kullanarak karma gerçeklik fotoğraf ve videolarını yakalama, kaydetme ve görüntülemeyi HoloLens öğrenin. Verilerle veya toplanan Miracast paylaşmayı öğrenin.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428532"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Karma gerçeklik fotoğrafları ve videoları oluşturma

HoloLens kullanıcılara gerçek dünyayı dijital dünyayla karıştırma deneyimi sunar.  Karma gerçeklik yakalama (MRC), bu deneyimi fotoğraf veya video olarak yakalama veya diğer kullanıcılarla gerçek zamanlı olarak paylaşma özelliği sunar.

Karma gerçeklik yakalama, diğer kişilerin sizin gördüğünüz hologramları görene kadar birinci kişi bakış açısı kullanır. Üçüncü kişi görünümü için izleyici [görünümünü kullanın.](/windows/mixed-reality/spectator-view) Spectator görünümü özellikle tanıtımlar için yararlıdır.

Arkadaşlarınızla iş arkadaşlarınız arasında video paylaşmak eğlencelidir ancak videolar diğer insanlara bir uygulamayı kullanmayı veya sorunları uygulamalarla ve deneyimlerle iletişim kurmayı öğretmeye de yardımcı olabilir.

> [!NOTE]
> Karma gerçeklik yakalama deneyimlerini başlatamıyorsanız ve HoloLens bir iş cihazı ise sistem yöneticinize danışın. Kameraya erişim şirket ilkesi aracılığıyla kısıtlanabilir.

## <a name="capture-a-mixed-reality-photo"></a>Karma gerçeklik fotoğrafı yakalama

Karma gerçeklik fotoğraflarını farklı şekillerde HoloLens; donanım düğmeleri, ses veya ses Başlat menüsü.

### <a name="hardware-buttons-to-take-photos"></a>Fotoğraf çekmek için donanım düğmeleri

Geçerli görünümle ilgili hızlı bir fotoğraf almak için aynı anda ses yukarı ve ses düzeyi aşağı düğmelerine basın.  Bu, ekran görüntüsünün HoloLens ekran görüntüsü sürümüne benzer.

- [HoloLens 2'de düğme konumları](hololens2-hardware.md)
- [HoloLens (1. nesil) üzerinde düğme konumları](hololens1-hardware.md#hololens-components)

> [!NOTE]
> Ses **düzeyinin üç** saniye **boyunca yüksek** ve ses düzeyi düşük tutularak fotoğraf çekiliyor yerine video kaydediliyor. Kaydı durdurmak için aynı anda hem **ses yukarı hem** de ses düzeyi **aşağı** düğmelerine dokunun.

### <a name="voice-commands-to-take-photos"></a>Fotoğraf çekmek için sesli komutlar

2 HoloLens 2004 (ve sonraki sürümler) için "Fotoğraf çek" diyelim.

HoloLens (1. nesil) veya HoloLens 2. sürüm 1903'te "Hey Cortana, fotoğraf çek" gibi bir ifadeyle devam edin.

### <a name="start-menu-to-take-photos"></a>Başlat menüsü fotoğraf çek

Başlat hareketini kullanarak **Başlat'a gidin** ve Kamera **simgesini** seçin.

Kafanızı yakalamak istediğiniz yöne, ardından havadan [dokunarak fotoğraf](hololens2-basic-usage.md#touch-holograms-near-you) çekin. Havadan dokunmaya ve ek fotoğraflar yakalamaya devam edersiniz. Yakalamanız gereken tüm fotoğraflar cihazınıza kaydedilir.

Fotoğraf yakalamayı sona ert için Başlangıç hareketini yeniden kullanın.  

## <a name="capture-a-mixed-reality-video"></a>Karma gerçeklik videosu yakalama

Karma gerçeklik videosunu HoloLens; donanım düğmeleri, ses veya ses Başlat menüsü.

### <a name="hardware-buttons-to-record-videos"></a>Videoları kaydetmek için donanım düğmeleri

Video kaydetmenin en hızlı yolu, üç  saniyelik  geri sayım başlayana kadar ses düzeyi yukarı ve ses düzeyi aşağı düğmelerine aynı anda basılı tutmaktır. Kaydı durdurmak için iki tuşa da aynı anda dokunun.

> [!NOTE]
> Ses düzeyi **yukarı ve ses** düzeyi aşağı **düğmelerine** aynı anda hızla basılarak video kaydı yerine fotoğraf çekebilirsiniz.

### <a name="voice-to-record-videos"></a>Videoları kaydetmek için seslendirme

2. HoloLens 2004 (ve sonrası) için "Kaydı başlat" de. Kaydı durdurmak için "Kaydı durdur" diyelim.

HoloLens (1. nesil) veya HoloLens 2. sürüm 1903'te "Hey Cortana, kaydı başlat" gibi bir ifadeyle devam edin. Kaydı durdurmak için "Hey Cortana, kaydı durdur" diyelim.

### <a name="start-menu-to-record-videos"></a>Başlat menüsü kaydetmek için

Başlat hareketini kullanarak **Başlat'a gidin** ve Video **simgesini** seçin. Kafanızı yakalamak istediğiniz yöne, ardından havadan [dokunarak kaydı](hololens2-basic-usage.md#touch-holograms-near-you) başlatabilirsiniz. Üç saniyelik geri sayım olacak ve kaydınız başlayacaktır.

Kaydı durdurmak için Başlat hareketini kullanın ve vurgulanan **Video simgesini** seçin. Video cihazınıza kaydedilir.

> [!NOTE]
> **Yalnızca HoloLens (1. nesil) için geçerlidir**  
> Bu [Windows 10 Ekim 2018 Güncelleştirmesi,](/windows/mixed-reality/release-notes-october-2018) Başlangıç hareketi ve Windows düğmesinin HoloLens (1. nesil) değiştirir. Güncelleştirmeden önce Başlat hareketi veya Windows düğmesi bir video kaydını durdurur. Ancak güncelleştirmeden sonra Başlat hareketi veya Windows düğmesi  Başlat menüsünü (veya çevreleyici bir uygulamadaysanız hızlı eylemler menüsünü) açar. Buradan vurgulanan **video** simgesini seçerek kaydı durdurabilirsiniz. 

## <a name="share-what-you-see-in-real-time"></a>Gördüğünüzleri gerçek zamanlı olarak paylaşma

İş arkadaşlarınızla ve iş arkadaşlarınızla HoloLens gerçek zamanlı olarak paylaşabilirsiniz. Kullanılabilir birkaç yöntem vardır:

1. Tv'Miracast izlemek için etkin bir cihaza veya bağdaştırıcıya bağlanma.
1. Bir [Windows Cihaz Portalı](/windows/mixed-reality/using-the-windows-device-portal) izlemek için Windows Cihaz Portalı kullanma
1. Bir [Microsoft HoloLens izlemek için yardımcı](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) uygulamayı kullanma.
1. Ön satır çalışanlarının uzak bir uzmana göre göre akış oluşturmalarını sağlayan [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) uygulamasını dağıtma. Bundan sonra uzak uzman ön satır çalışanına sözlü olarak veya kendi dünyasında not ek açıklamalarıyla yol da kullanabilir.

> [!NOTE]
> Yeni uygulama veya Windows Cihaz Portalı Microsoft HoloLens paylaştığınızda, HoloLens geliştirici modunda [olması gerekir.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Miracast ile video akışı Miracast

Başlat hareketini kullanarak **Başlat'a gidin** ve ardından Başlangıç **Bağlan** seçin. Görüntülenen seçiciden, bağlanmak Miracast cihaz veya bağdaştırıcıyı seçin.

Paylaşımı durdurmak için Başlat hareketini kullanın ve vurgulanan **simgeyi Bağlan** seçin. Akışta olduğundan cihazınıza hiçbir şey kaydedilamaz.

> [!NOTE]
> Miracast ile başlayan HoloLens (1. nesil) üzerinde [Windows 10 Ekim 2018 Güncelleştirmesi.](/windows/mixed-reality/release-notes-october-2018)

### <a name="real-time-video-with-windows-device-portal"></a>Windows Cihaz Portalı ile gerçek zamanlı video

Windows Cihaz Portalı aracılığıyla paylaşım, HoloLens geliştirici modunun etkinleştirilmesi gerektirdiği için, Geliştirici modunu ayarlamak için geliştirici belgelerimizde verilen [yönergeleri](/windows/mixed-reality/using-the-windows-device-portal)izleyin ve Windows Cihaz Portalı.

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens yardımcı uygulama

Microsoft HoloLens yardımcı uygulaması aracılığıyla paylaşım yapmak için geliştirici modunun HoloLens geliştirici belgelerimizde verilen yönergeleri izleyerek Geliştirici [modunu ayarlayın.](/windows/mixed-reality/using-the-windows-device-portal) Ardından, [Microsoft HoloLens yardımcı uygulamasını indirin](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ve uygulamanın içindeki yönergeleri izleyerek uygulamanıza HoloLens.

Uygulama uygulama uygulamanıza uygun HoloLens, **uygulamanın** ana menüsünden Canlı akış seçeneğini belirleyin.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Karma gerçeklik fotoğraflarınızı ve videolarınızı görüntüleme

Karma gerçeklik fotoğrafları ve videoları cihazın "KameraLı Zar At" cihazına kaydedilir. Dosya Gezgini uygulamasıyla bu klasörün içeriğine HoloLens göz atabilirsiniz (Resimler ve **Kamera >'a gidin).**

Karma gerçeklik fotoğraflarınızı ve videolarınızı, HoloLens'a önceden yüklenmiş olan Fotoğraflar uygulamasında da görüntü HoloLens. Dünyanıza bir fotoğraf sabitlemek için Fotoğraflar uygulamasında bunu seçin ve Karma dünyada **yer'i seçin.** Fotoğraf yerleştirildikten sonra dünyanız için hareket ettirin.

Karma gerçeklik fotoğraflarınızı ve videolarınızı HoloLens'a bağlı bir bilgisayara görüntülemek ve/veya kaydetmek için MTP [aracılığıyla Windows Cihaz Portalı](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) veya [bilgisayarınızın Dosya Gezgini kullanabilirsiniz.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Resimlerinizi Dosya Gezgini, videolarınızı ve dosyalarınızı almak için Dosya Gezgini'i kullanın

Diğer mobil cihazlara benzer şekilde, HoloLens bilgisayarınıza bağarak kolay aktarım Dosya Gezgini kitaplıklarına (fotoğraflar, videolar, belgeler) erişmek için HoloLens'nizi getirin. Bu yöntemin kullanımı kolaydır ve cihaz portalı veya Wi-Fi kullanımı gerektirmez.

1. Cihazın kilidini açın.
1. Bağlan USB aracılığıyla bir bilgisayara bağlayın.
1. Dosya Gezgini bilgisayarınızda açabilirsiniz.
1. Şu bilgisayara gidin: \\ *Yourhololensname*\Internal Depolama\Pictures\Camera Roll
1. Bilgisayarınıza ihtiyacınız olan dosyaları kopyalayın.

İpuçları:
- Herhangi bir dosya görmüyorsanız, verilerinize erişimi etkinleştirmek için HoloLens oturum HoloLens emin olun.
- Belgeler klasöründen tanılama dosyaları gibi diğer [klasörlerdeki diğer dosyaları](hololens-diagnostic-logs.md#offline-diagnostics) da edinebilirsiniz.
- Bilgisayarınızda Dosya Gezgini'den Cihaz özellikleri'Windows Holographic OS sürüm numarası (üretici yazılımı sürümü), cihaz seri numarası ve pil yüzdesini görüntüebilirsiniz.
- Cihazınız [Bağlantı/AllowUSBConnection'ı](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) devre dışı bırakmak için MDM kullandı ise cihazınıza bağlanamaz.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Karma gerçeklik fotoğraflarınızı ve videolarınızı paylaşma

[Holographic Windows sürüm 21H1'den](hololens-release-notes.md#windows-holographic-version-21h1)önce karma gerçeklik fotoğrafı veya videoyu yakalamadan önce önizleme görüntülenir. Paylaşım **yardımcıyı** getirmek için önizlemenin üzerindeki Paylaş simgesini seçin. Buradan, o fotoğrafı veya videoyu paylaşmak istediğiniz uç noktasını seçin.

Holographic Windows sürüm 21H1'de karma gerçeklik fotoğrafı veya video yakalandikten sonra önizleme görüntülenir. Paylaşım **yardımcıyı** getirmek için önizlemenin üzerindeki Paylaş simgesini seçin. Buradan, bu fotoğrafı veya videoyu paylaşmak istediğiniz uç nokta (Posta, OneDrive, vb.) seçin. -> System -HoloLens Paylaşılan Deneyimler'e gidip **Ayarlar cihazlarınızı > etkinleştirebilirsiniz.** Diğer ayrıntılar için, [Windows 10'da yakındaki cihazlarla Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

> [!TIP] 
> Karma gerçeklik fotoğraflarınızı ve videolarınızı otomatik olarak karşıya yük OneDrive karma gerçeklik fotoğraf ve videolarını da paylaşabilirsiniz. Henüz OneDrive uygulama HoloLens kişisel Microsoft hesabı oturum açın. **[](https://account.microsoft.com)** Uygulama simgesini **Ayarlar** Kamera karşıya **yükle'yi seçin.** Kamera karşıya yükleme'nizi açma. Karma gerçeklik fotoğraflarınız ve videolarınız artık uygulamayı OneDrive her HoloLens.

> [!NOTE]
> Kamera karşıya yükleme özelliği yalnızca OneDrive kişisel bir kullanıcı OneDrive oturum Microsoft hesabı. Bu özelliği etkinleştirmek HoloLens bir iş veya okul hesabıyla Microsoft hesabı bir OneDrive hesabı ekleme.

## <a name="limitations-of-mixed-reality-capture"></a>Karma gerçeklik yakalama sınırlamaları

- Karma gerçeklik yakalaması kullanırken, HoloLens kare hızı yarıya inecek.
- Fotoğraf/video kamerası başka bir uygulama tarafından zaten kullanıyorsa, canlı akış sırasında veya sistem kaynakları düşükse fotoğrafların ve videoların çözünürlüğü azaltabilirsiniz.

### <a name="maximum-recording-length"></a>Maksimum kayıt uzunluğu

HoloLens Holographic sürüm 20H2 Windows den önceki 2 cihazda, cihaza kaydedilen videolar en fazla beş dakika uzunluğundaydı.

Müşteri geri bildirimi nedeniyle karma gerçeklik yakalamalarının kayıt [uzunluğunu artırıldı.](holographic-photos-and-videos.md) Karma gerçeklik yakalamaları artık varsayılan olarak 5 dakikayla sınırlı olmayacaktır, ancak bunun yerine kullanılabilir disk alanı temel alarak maksimum kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanını %80'e kadar olan kullanılabilir disk alanını temel alarak maksimum video kayıt süresini tahmin eder.

> [!NOTE]
> Aşağıdaki HoloLens biri gerçekleşirse varsayılan video kayıt uzunluğunu (5 dakika) kullanır:
> - Tahmini maksimum kayıt süresi, varsayılan 5 dakikadan küçüktür.
> - Kullanılabilir disk alanı toplam disk alanı %20'den azdır.

## <a name="default-file-format-and-resolution"></a>Varsayılan dosya biçimi ve çözümü

### <a name="default-photo-format-and-resolution"></a>Varsayılan fotoğraf biçimi ve çözünürlüğü

|  Cihaz  |  Biçimlendir  |  Dahili numara  |  Çözüm  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (1. nesil) | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>Kaydedilen video biçimi ve çözünürlüğü

| Cihaz | Biçimlendir | Dahili numara | Çözüm | Hız | Ses |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz Stereo |
| HoloLens (1. nesil) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz Stereo |
