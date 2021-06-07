---
title: Başlat menüsü ve karma gerçeklik girişlerini kullanma
description: Başlangıç menüsünü kullanmayı, uygulamaları yönetmeyi ve uygulamalara erişmeyi ve HoloLens cihazlarında karma gerçeklik girişlerine nasıl gidileni öğrenin.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 66271911a4692dea89b6338cc8c77a05dfcaae1d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380174"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Başlat menüsü ve karma gerçeklik girişlerini kullanma

Windows bilgisayarı deneyimi masaüstü ile başladığı gibi Windows Holographic de karma gerçeklik giriş ile başlar.  Bu Başlat menüsü kullanarak uygulama pencerelerini, tam ekran uygulama başlatıcılarını ve 3D içeriği karma gerçeklik girişine açıp yer açabilirsiniz ve bunların fiziksel alanınıza yerleştirilmesi hatırlanır.

## <a name="use-the-start-menu"></a>Başlat menüsü

HoloLens Başlat menüsü de uygulamalar açılır, önemli durum bilgileri ve kamera gibi erişim araçları açılır.

HoloLens'te nerede olursanız olun Başlangıç hareketini Başlat menüsü istediğiniz zaman bu **ifadeyi açtırarak açın.**  HoloLens'te (1. nesil) Başlangıç hareketi bloom [olur.](https://support.microsoft.com/help/12644/hololens-use-gestures) HoloLens 2'de [Başlangıç hareketi,](hololens2-basic-usage.md#start-gesture) bilek üzerinde görünen Başlat simgesine dokunmaktır.  Ayrıca sesinizi kullanarak Başlat menüsü "Başla"ya da gidebilirsiniz.

> [!TIP]
> Çalışma Başlat menüsü açık olduğunda Başlat hareketini kullanarak kapatın veya Başlat menüsü "Kapat" diyelim.

Wi-Fi Başlat menüsü, pil, hacim ve saat için durum göstergelerini en üstte yer alır. HoloLens 2'de cihazın konuşmanın etkin olup olmadığını ve sesli komutları dinlediğini gösteren bir dinleme göstergesi de vardır. En altta fotoğraf ve **video** **kayıtları** aya kaydetmeye olanak sağlayan Fotoğraf ve Video düğmelerini bulabilirsiniz.  Ayrıca Miracast **kullanarak** başka bir cihaza gördüğünüzleri proje olarak görmelerini sağlayan bir Bağlan düğmesi de vardır.

### <a name="find-apps-on-start-menu"></a>Uygulamalarınızı Başlat menüsü

Uygulamanın Başlat menüsü bir **Sabitlenmiş uygulamalar** listesi ve **bir** Tüm uygulamalar vardır.

- Sabitlenmiş **uygulamalar** listesi, sabitlenmiş uygulamaları gösterir. Bir uygulama kutucuğunu seçerek **ve** basılı tutarken görüntülenen bağlam menüsünü kullanarak Sabitlenmiş uygulamalar **listesinden** uygulama ekleyebilir ve kaldırabilirsiniz.

- Tüm uygulamalar  listesi, cihazda yüklü olan tüm uygulamaları gösterir.  Listeye **Tüm uygulamalar** menüsünün sağ tarafındaki Tüm uygulamalar  Düğmesi düğmesini seçin.

Her iki uygulama listesinde de,  **listenin** sağ tarafındaki Sayfa yukarı ve Sayfa aşağı düğmelerini Başlat menüsü uygulamalar arasında sayfa oluşturma.  Her iki uygulama listesi de bir cihaz oturumu sırasında son kullanılan sayfayı otomatik olarak açar.

> [!TIP]
> HoloLens 2'de dizin parmaklarınızı kullanarak uygulama listelerini doğrudan kaydırabilirsiniz. Parmak ucunuzla listeye dokunarak yukarı veya aşağı doğru sürüklemeniz gerekir.

### <a name="open-apps-from-start-menu"></a>Uygulamaları Başlat menüsü

Uygulama kutucuğunu kullanarak Başlat menüsü bir **uygulama** **kutucuğu seçmeniz gerekir.** Uygulamayı açmak için bir uygulamanın adını da söyleyebilirsiniz.

Uygulamayı uygulamanın tasarım Başlat menüsü bağlı olarak aşağıdakilerden biri olur:

- Bir **uygulama penceresi** yerleştirilir. Uygulama daha sonra pencereye yüklenir ve bunu dokunmatik ekran gibi kullanabilirsiniz.
- Çevreleyici **bir uygulama için 3D** uygulama başlatıcısı yerleştirilir. Ardından tam ekran **uygulamayı** açmak için başlatıcıyı seçmeniz gerekir.
- Çevreleyici bir uygulama için başlatıcı **olarak hareket** etmek için bir uygulama penceresi yerleştirilir. Çevreleyici uygulama otomatik olarak başlatılır.

Karma gerçeklik giriş girişlerine yerleştirilen uygulama pencereleri ve uygulama başlatıcıları, siz kaldırmaya karar verinceye kadar burada kalır.  Bu uygulamalar, dünya üzerinde bu uygulama pencerelerini kullanmak veya uygulama pencerelerini yeniden açmak zorunda kalmadan tam ekran uygulamaları başlatmak için kullanışlı bir kısayol Başlat menüsü. 

> [!NOTE]
>Telefonlarda olduğu gibi sistem kaynakları da HoloLens'de otomatik olarak yönetilir.  Örneğin, yeni bir çevreleyici uygulama açsanız, çalışan diğer tüm uygulamalar hemen devre dışı kalır. Sistem kaynaklarını serbest bırakarak karma gerçeklik giriş sayfalarındaki uygulama pencerelerini ve başlatıcıları kaldırmaya gerek yoktur. 

## <a name="using-apps-on-hololens"></a>HoloLens'de uygulamaları kullanma

HoloLens'in uygulamaları uygulama penceresi görünümünü veya çevreleyici görünümü kullanabilir. Uygulama penceresi görünümüyle uygulama yalnızca içeriğini bir pencerenin içinde gösterir. Çevreleyici görünümle, bir uygulama sizi karma gerçeklikten uzaklaştırır ve içeriğini etrafının her yanında fiziksel ortamda görüntüler. Uygulamalar her iki görünümleri de kullanmayı seçebilir.

### <a name="use-app-windows"></a>Uygulama pencerelerini kullanma

HoloLens (1. nesil) uygulama pencereleri, karma gerçeklik giriş girişlerine yerleştirilir ve kullanılır. Burada bunları istediğiniz gibi hareket [ettirebilir,](hololens1-basic-usage.md#move-resize-and-rotate-apps) yeniden boyutlandırabilir ve döndürebilirsiniz. Uygulama pencerelerini bakış ve hareket ile kullanmaya ek olarak, bunları Bluetooth bağlantılı fare ve klavye ile de kullanabilirsiniz.

HoloLens 2'de, karma gerçeklik ana bilgisayarlarında uygulama pencerelerini kullanmaya ek olarak, çevreleyici bir uygulamanın içinde aynı anda tek bir uygulama penceresi de kullanabilirsiniz. Ayrıca, bir uygulama penceresini Beni **takip** et moduna da koyabilirsiniz. Burada, siz yolu izleyebilirsiniz. Tam ekranlı bir uygulamanın içindeyken bir uygulama penceresi açsanız otomatik olarak Beni takip **et modunda** açılır. Hem karma [gerçeklikte hem de çevreleyici](hololens2-basic-usage.md#move-resize-and-rotate-holograms) bir uygulamanın içinde ellerinizi kullanarak uygulama pencerelerini doğrudan hareket ettirebilir, yeniden boyutlandırabilir ve döndürebilirsiniz.

> [!NOTE]
>
> - Karma gerçeklik evlerinde aynı anda en fazla üç uygulama pencereleri etkin olabilir. Daha fazla açabilir, ancak yalnızca üç tane etkin kalır.
> - Bir uygulama penceresi etkin değilken, etkin bir pencereye kıyasla koyu görünen içerik gösterilir.  Bazıları herhangi bir içerik yerine uygulama simgesini gösterir.  Etkin olmayan bir pencereyi etkinleştirmek için **bunu seçmeniz** gerekir.
> - Açık olan her uygulamanın tek bir etkin penceresi olabilir ancak Microsoft Edge kadar etkin olabilir.

### <a name="close-apps"></a>Uygulamaları kapatma

Uygulama penceresi kullanan bir uygulamayı kapatmak için başlık çubuğundaki Kapat **düğmesiyle** uygulama penceresini kapatmanız gerekir.  Ayrıca pencereye bakarak "Kapat" deebilirsiniz.

Tam ekran görünümü kullanan bir uygulamadan çıkmak için Başlangıç hareketini kullanarak Başlat menüsü açın **ve** Karma gerçeklik **giriş düğmesini** seçin.

Tam ekranlı bir uygulama bozuk durumda ise ve uygulamayı yeniden başlatmanız gerekirse, önce karma gerçeklik giriş giriş'inde başlatıcısını kapatarak ve uygulamanın sanal gerçeklikten başlatıcısını başlatarak tamamen Başlat menüsü.

### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Windows Holographic sürüm [21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile, bir köprüyü etkinleştirdiğinde veya birden fazla yüklü uygulamayla bir dosya türünü açicağsanız, dosyayı veya bağlantı türünü hangi yüklü uygulamanın işlemesi gerektiğini seçmenizi istemiyle yeni bir pencere açılır. Bu pencerede, seçilen uygulamanın dosyayı işlemesi veya "Bir kez" ya da "Her zaman" bağlantı türünü de seçmeyi seçebilirsiniz.

![Uygulama seçici penceresi](images/default-app-picker.png)

"Always" (Her Zaman) ifadesini seçerseniz ancak daha sonra hangi uygulamanın belirli bir dosyayı veya bağlantı türünü işleyeni değiştirmek istemeniz gerekirse, Ayarlar ve Uygulamalar'da kayıtlı **varsayılan > sıfırlayabilirsiniz.** Sayfanın en altına kaydırın ve  "Dosya türleri için varsayılan uygulamalar" ve/veya "Bağlantı türleri için varsayılan uygulamalar" altındaki Temizle düğmesini seçin. Masaüstü bilgisayarlardaki benzer ayarın aksine, tek tek dosya türü varsayılanlarını sıfırlayabilirsiniz.

### <a name="per-app-volume-control"></a>Uygulama başına birim denetimi

Windows [Holographic sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile, kullanıcılar her uygulamanın ses düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duyan uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha iyi duymasını sağlar. Örneğin, başka bir uygulamada uzaktan yardım için başka bir kişiyi çağırırken bir uygulamanın hacmini kapatmak gibi.

Tek bir uygulamanın hacmini ayarlamak için Ayarlar Sistem Sesi'ne gidin ve Gelişmiş ses seçenekleri altında Uygulama birimi  ->    ->  ve **cihaz tercihleri'ne tıklayın.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>İlgili bilgiler

[Uygulamaları bulma, yükleme ve kaldırma Microsoft Store](holographic-store-apps.md)
