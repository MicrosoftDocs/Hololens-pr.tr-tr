---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider Derlemeleriyle çalışmaya başlama ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlama hakkında bilgi edinin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924351"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview yapılarına hoş geldiniz! [Başlamak ve HoloLens](hololens-insider.md#start-receiving-insider-builds) için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlamak kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider sürüm notları

Son Insider özelliklerimizin herkese açık bir şekilde gittiğinden heyecanlıyız! Bu bilgileri öğrenmek isterseniz, lütfen [sürüm notları sayfasına](hololens-release-notes.md) göz atın

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlayın

> [!NOTE]
> Son zamanlarda güncelleştirmediyseniz, durumu güncelleştirmek ve en son derlemeyi almak için lütfen cihazınızı yeniden başlatın.
>
> - "Cihazı yeniden Başlat" ses komutu iyi şekilde çalışmaktadır.
> - Ayarlar/Windows ınsider programı ' nda yeniden başlat düğmesini de seçebilirsiniz.
>
> Arka uçta karşılaştığınız bir hata yaşadık ve bu, izlemeye geri dönecek.

HoloLens 2 cihazında, **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' na gidin ve **kullanmaya** başlayın ' ı seçin. Windows bir ınsider olarak kaydetmek için kullandığınız hesabı bağlayın.

> [!NOTE]
> Cihazınızı Insider Derlemeleriyle kaydetmek için isteğe bağlı Telemetriyi etkinleştirmeniz gerekir. bunu yapmadıysanız, Ayarlar uygulamasını açın ve **gizlilik**  ->  **tanılama & geri bildirimi** ' ni seçin ve **isteğe bağlı tanılama verileri**' ni seçin.

Windows ınsider artık kanallara taşınıyor. **Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur. Bu, eşlemenin şöyle görünür:

![Windows Insider kanalları açıklaması.](images/WindowsInsiderChannels.png)

daha fazla bilgi için bkz. Windows bloglarda [Windows ınsider kanalları tanıtma](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .
sonra, **Windows için etkin geliştirme**' yı seçin, **Dev kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.
**> şimdi yeniden başlatmak Için Onayla** ' yı seçin. cihazınız yeniden başlatıldıktan sonra, **Ayarlar > güncelleştirme & güvenlik** ' e gidin > en son derlemeyi almak için güncelleştirmeleri denetleyin.

### <a name="update-error-0x80070490-work-around"></a>Güncelleştirme hatası 0x80070490 iş-etrafında

Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli işleri deneyin. Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.

#### <a name="stage-one---release-preview"></a>Aşama tek sürüm önizlemesi

1. Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **yayın önizleme kanalını** seçin.

2. Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**. Güncelleştirme sonrasında, ikinci aşamada devam edin.

#### <a name="stage-two---dev-channel"></a>İkinci geliştirme kanalı aşaması

1. Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **geliştirme kanalı**' nı seçin.

2. Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.

## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve Flash yönleri

Bir uçuş imzalı FFU ile test etmek için önce, uçuşdan ayrılmadan önce cihazınızın kilidini açmanız gerekir.

1. BILGISAYAR üzerinde:
    1. Hesabınızı ' den bilgisayarınıza indirin [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Microsoft Store: ile yay (Gelişmiş kurtarma Yardımcısı) yüklemesini yapın [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. HoloLens uçuşlamada kilit açma: **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' nı açın ve cihazı yeniden başlatın.

1. Flash FFU-şimdi yay kullanarak uçuştan imzalanmış FFU 'yi yakıp sönebilir.

### <a name="provide-feedback-and-report-issues"></a>Geri bildirim ve rapor sorunları sağlama

geri bildirim ve rapor sorunları sağlamak için lütfen HoloLens [geri bildirim merkezi uygulamasını](hololens-feedback.md) kullanın. Geri Bildirim Hub 'ı kullanmak, mühendislerimizin hata ayıklamasına ve sorunu çözmeye yardımcı olmak için gerekli tüm tanılama bilgilerinin eklenmesini sağlar.  HoloLens çince ve japonca sürümü ile ilgili sorunlar aynı şekilde bildirilmelidir.

> [!NOTE]
> Belge klasörünüze geri bildirim hub 'ı (sorulduğunda **Evet** ' i seçin) isteyip istemediğinizi soran istemi kabul ettiğinizden emin olun.

## <a name="note-for-developers"></a>Geliştiriciler için göz önünde

HoloLens Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemeye hoş geldiniz ve önerilir.  başlamak için [HoloLens geliştirici belgelerine](https://developer.microsoft.com/windows/mixed-reality/development) göz atın. Aynı yönergeler HoloLens Insider Derlemeleriyle birlikte çalışır.  HoloLens geliştirme için kullanmakta olduğunuz Unity ve Visual Studio derlemelerin aynısını kullanabilirsiniz.

## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdur

artık Windows Holographic ınsider derlemelerini almak istemiyorsanız, HoloLens bir üretim derlemesi çalıştırırken devre dışı bırakabilirsiniz veya cihazınızı Windows Holographic 'ın ınsider sürümüne kurtarmak için gelişmiş kurtarma yardımcısı 'nı kullanarak [cihazınızı kurtarabilirsiniz](hololens-recovery.md) .

> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydolmamış kullanıcıların mavi bir ekran deneymesinin bilinen bir sorunu vardır. Daha sonra cihazlarını el ile kurtarmanız gerekir. Etkilenmiş olmanız veya olmadıysanız ilgili tüm ayrıntılar için lütfen bu [bilinen sorunu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)izleyin.

HoloLens bir üretim derlemesi çalıştırdığından emin olmak için:

1. **Ayarlar > sistem >**' e gidin ve derleme numarasını bulun.

1. [Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).

Insider derlemelerini devre dışı bırakmak için:

1. üretim yapısını çalıştıran bir HoloLens, **Ayarlar > & güvenlik > Windows ınsider programı**' na gidin ve **ınsider derlemelerini durdur**' u seçin.

1. Cihazınızı devre dışı bırakmak için yönergeleri izleyin.
