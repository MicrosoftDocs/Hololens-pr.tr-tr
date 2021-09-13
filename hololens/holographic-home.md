---
title: Başlat menüsü ve karma gerçeklik ana öğesini kullanın
description: başlat menüsünü kullanmayı, uygulamaları yönetme ve erişme hakkında bilgi edinin ve HoloLens cihazlarda karma gerçeklik giriş sayfasına gidin.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036540"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Başlat menüsü ve karma gerçeklik ana öğesini kullanın

Windows PC deneyiminin masaüstüyle başladığı gibi, Windows Holographic karma gerçeklik ana ile başlar.  Başlat menüsü kullanarak app windows, modern uygulama başlatma ve 3b içeriğini karma gerçeklik ana halinde açabilir ve yerleştirebilirsiniz ve fiziksel alanınızdaki yerleştirme anımsanacaktır.

## <a name="use-the-start-menu"></a>Başlat menüsü kullanın

HoloLens üzerindeki Başlat menüsü, uygulamaları açacak, önemli durum bilgilerini ve kamera gibi araçlara erişim araçlarını görürsünüz.

HoloLens nerede olursanız olun, **başlangıç hareketini** kullanarak Başlat menüsü her zaman açabilirsiniz.  HoloLens (1. genel) başlangıç hareketi [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures)olur. HoloLens 2 ' de, [başlangıç hareketi](hololens2-basic-usage.md#start-gesture) bilek 'da görünen başlangıç simgesine dokunmanız gerekir.  ayrıca, "başlat 'a git" dileyerek sesinizi kullanarak Başlat menüsü açabilirsiniz.

> [!TIP]
> Başlat menüsü açık olduğunda, kapatmak için başlangıç hareketini kullanın veya Başlat menüsü ve "kapat" deyin.

Başlat menüsü en üstünde Wi-Fi, pil, birim ve saat için durum göstergeleri görürsünüz. HoloLens 2 ' de, cihazın konuşma 'nın etkin olup olmadığını ve sesli komutları dinlediğini gösteren bir dinleme göstergesi de vardır. En altta, fotoğraf ve video kayıtları çekmenize imkan tanıyan **fotoğraf** ve **video** düğmeleri bulacaksınız.  ayrıca, Miracast kullanarak gördüğlerinizi başka bir cihaza proje ile oluşturmanıza olanak sağlayan bir **Bağlan** düğmesi de vardır.

### <a name="find-apps-on-start-menu"></a>Başlat menüsü uygulamalar bulma

Başlat menüsü bir **sabitlenmiş uygulamalar** listesi ve **tüm uygulamalar** listesi vardır.

- **Sabitlenmiş uygulamalar** listesi sabitlenmiş uygulamaları gösterir. Bir uygulama kutucuğunu **seçtiğinizde ve tuttuğunuzda** görüntülenen bağlam menüsünü kullanarak, **sabitlenmiş uygulamalar** listesinden uygulama ekleyebilir veya kaldırabilirsiniz.

- **Tüm uygulamalar** listesinde, cihazda yüklü olan tüm uygulamalar gösterilir.  Listeye ulaşmak için **Başlangıç** menüsünün sağ tarafındaki **tüm uygulamalar** düğmesini seçin.

her iki uygulama listesinde, listedeki tüm uygulamalar arasında gezinmek için Başlat menüsü sağ tarafındaki **sayfa yukarı** ve **sayfa aşağı** düğmelerini kullanın.  Her iki uygulama listesi de, bir cihaz oturumu sırasında en son kullanılan sayfaya otomatik olarak açılır.

> [!TIP]
> HoloLens 2 ' de, dizin parmağınızı kullanarak uygulama listelerini doğrudan kaydırabilirsiniz. Parmak ipucunuz ile listeye dokunmanız yeterlidir ve yukarı veya aşağı doğru sürükleyin.

### <a name="open-apps-from-start-menu"></a>Başlat menüsü uygulamaları açın

Başlat menüsü bir uygulamayı açmak için bir **uygulama kutucuğu** **seçmeniz** yeterlidir. Ayrıca, uygulamayı açmak için bir uygulamanın adını da söyleyebilirsiniz.

Başlat menüsü bir uygulamayı açtığınızda, uygulamanın nasıl tasarlandığına bağlı olarak aşağıdakilerden biri gerçekleşir:

- **Uygulama penceresi** yerleştirilir. Uygulama daha sonra pencereye yüklenir ve bunu dokunmatik ekran gibi kullanabilirsiniz.
- Modern bir uygulama için **3B uygulama başlatıcısı** yerleştirilir. Daha sonra, modern uygulamayı açmak için Başlatıcısı **seçmeniz** gerekir.
- Modern bir uygulama için bir **Başlatıcı** görevi gören bir uygulama penceresi yerleştirilir. Modern uygulama otomatik olarak çalışmaya devam edecektir.

Karma Gerçeklik evine yerleştirilmiş uygulama pencereleri ve uygulama başlatma programları, onları kaldırmaya karar verinceye kadar yerinde kalır.  bu uygulamalar, bu uygulama pencerelerini kullanmak veya Başlat menüsü bir kez daha açmak zorunda kalmadan, modern uygulamaları başlatmak için dünya çapında kullanışlı bir kısayol sunar. 

> [!NOTE]
>Bir telefonda olduğu gibi, sistem kaynakları HoloLens otomatik olarak yönetilir.  Örneğin, yeni bir modern uygulama açtığınızda, çalışan diğer tüm uygulamalar hemen devre dışı olur. Sistem kaynaklarını boşaltmak için karma gerçeklik ana 'da uygulama pencerelerini ve launchers 'ı kaldırmaya gerek yoktur. 

## <a name="using-apps-on-hololens"></a>HoloLens uygulamalar kullanma

HoloLens uygulamalar uygulama pencere görünümü veya modern görünüm kullanabilir. Uygulama penceresi görünümünde, uygulamanın içeriğini bir pencere içinde gösterir. Derinlikli görünüm sayesinde bir uygulama, daha sonra içeriği sizin için fiziksel ortamda görüntüleyebilen karma Realty evden uzaklaştırabilir. Uygulamalar, her iki görünümü de kullanmayı seçebilir.

### <a name="use-app-windows"></a>Uygulama pencerelerini kullanma

HoloLens (1. gen) uygulama pencereleri, karma gerçeklik giriş bölümünde yer alır ve bunları dilediğiniz gibi [taşıyabilir, yeniden boyutlandırabilir ve döndürebilirsiniz](hololens1-basic-usage.md#move-resize-and-rotate-apps) . uygulama pencerelerini gaze ve hareket ile kullanmaya ek olarak, Bluetooth bağlantılı fare ve klavye ile de kullanabilirsiniz.

HoloLens 2 ' de, karma gerçeklik giriş sayfasında uygulama pencerelerini kullanmanın yanı sıra, tek bir uygulama penceresini tam ekran uygulaması içinde de kullanabilirsiniz. Ayrıca, **izleme** moduna geçmek üzere bir uygulama penceresi de yerleştirebilirsiniz. Modern bir uygulama içindeyken bir uygulama penceresi açtığınızda, bu işlem beni otomatik olarak **İzle** modunda açılır. Hem karma gerçeklik hem de tam ekran uygulama içinde kendi ellerinizi kullanarak uygulama pencerelerini doğrudan [taşıyabilir, yeniden boyutlandırabilir ve döndürebilirsiniz](hololens2-basic-usage.md#move-resize-and-rotate-holograms) .

> [!NOTE]
>
> - Tek seferde karma gerçeklik evinizde en fazla üç uygulama penceresi etkin olabilir. Daha fazlasını açabilirsiniz, ancak yalnızca üç etkin kalır.
> - Bir uygulama penceresi etkin olmadığında, etkin bir pencereyle karşılaştırıldığında koyulaştırılan içeriği gösterir.  Bazıları, herhangi bir içerik yerine yalnızca uygulama simgesini gösterir.  Etkin olmayan bir pencereyi etkinleştirmek için bunu **seçmeniz** yeterlidir.
> - her açık uygulama, Microsoft Edge hariç tek bir etkin pencere içerebilir ve bu en fazla üç tane olabilir.

### <a name="close-apps"></a>Uygulamaları kapat

Uygulama penceresi kullanan bir uygulamayı kapatmak için, başlık çubuğundaki **Kapat** düğmesi ile uygulama penceresini kapatmanız yeterlidir.  Ayrıca pencereye bakabilir ve "Kapat" deyin.

derinlikli görünüm kullanan bir uygulamadan çıkmak için başlangıç hareketini kullanarak **Başlat menüsü** açın ve ardından **karma gerçeklik giriş** düğmesini seçin.

modern bir uygulama bozuk durumdaysa ve yeniden başlatmanız gerekiyorsa, karma gerçeklik ana öğesinde başlatıcısı 'nı kapatarak ve sonra Başlat menüsü başlatarak uygulamanın tamamen kapandığından emin olabilirsiniz.

### <a name="default-app-picker"></a>Varsayılan uygulama seçici

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)ile, bir köprüyü etkinleştirdiğinizde veya birden fazla yüklü uygulama içeren bir dosya türünü açtığınızda, dosyayı veya bağlantı türünü hangi yüklü uygulamanın işleyeceği hakkında bilgi isteminde yeni bir pencere açılır. Bu pencerede, Seçilen uygulamanın "bir kez" veya "Always" dosya veya bağlantı türünü işlemesini de seçebilirsiniz.

![Uygulama Seçicisi penceresi.](images/default-app-picker.png)

"Always" seçeneğini belirlerseniz, daha sonra belirli bir dosyayı veya bağlantı türünü hangi uygulamanın işlediğini değiştirmek istiyorsanız, **Ayarlar > Apps**' te kaydedilmiş varsayılanları sıfırlayabilirsiniz. Sayfanın alt kısmına ilerleyin ve "dosya türleri için varsayılan uygulamalar" ve/veya "bağlantı türleri için varsayılan uygulamalar" altındaki **Temizle** düğmesini seçin. Masaüstü PC 'Lerde benzer ayarların aksine, tek tek dosya türü varsayılanlarını sıfırlayamazsınız.

### <a name="per-app-volume-control"></a>Uygulama birimi denetimi başına

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)ile, kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duydukları uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha fazla duymasını sağlar. Başka bir kişiyi başka bir kişiye uzak yardım için çağırırken bir uygulamanın hacminin kapatılmasının gereksinimi.

tek bir uygulamanın hacmini ayarlamak için **Ayarlar**  ->  **sistem**  ->  **sesi**' ne gidin ve gelişmiş ses seçenekleri altında **uygulama birimi ve cihaz tercihleri**' ni seçin.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>İlgili bilgiler

[Microsoft Store uygulamaları bulun, yükleme ve kaldırma](holographic-store-apps.md)
