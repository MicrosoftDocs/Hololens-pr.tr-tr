---
title: Uygulamaları bulma, yükleme ve kaldırma
description: Bu Microsoft Store, uygulama ve oyunlarla çalışma kaynağınız HoloLens.  Holografik uygulamaları bulma, yükleme ve kaldırma hakkında daha fazla bilgi edinin.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036321"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Uygulamaları bulma, yükleme ve kaldırma Microsoft Store

Bu Microsoft Store, uygulama ve oyunlarla birlikte çalışmak için git kaynağınız HoloLens. Uygulama uygulamanıza mağazadan HoloLens gördüğünüz tüm uygulamalar bu uygulama üzerinde çalıştırabilirsiniz.

Sanal HoloLens 2D görünümü veya holografik görünüm kullanır. 2D görünüm kullanan uygulamalar pencerelere benzer ve etrafınız için konumlara yer ve olabilir. Holografik görünüm kullanan uygulamalar sizi çevreler ve gördüğünüz tek uygulama olur.

HoloLens, Microsoft Store'den birçok mevcut uygulamanın ve özel olarak HoloLens.  Bu makale, çalışma sayfalarından holografik uygulamalara Microsoft Store.

Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için Özel [holografik uygulamalar makalesini okuyun.](holographic-custom-apps.md)

## <a name="find-apps"></a>Uygulama bulun

Başlat Microsoft Store **menüyü** açın. Ardından uygulamalara ve oyunlara göz atabilirsiniz. Sesli komutları [kullanarak](hololens-cortana.md) arama yapmak için "Ara" ifadesini kullanabilirsiniz. Arama penceresi açıldığında "Dikteye başla" yazın ve istendiğinde arama terimlerinizi aramaya başlayabilirsiniz.

> [!NOTE]
> HoloLens cihazlar için Sistem Gereksinimleri, uygulama derlemenin mimarisini temel almaktadır. HoloLens (1. nesil) için uygulama derlemesi ARM mimari paketini içerecek şekilde mağazada daha yeni bir UWP'ye güncelleştirilmişse, HoloLens 2 cihaz için kullanılamaz. Benzer şekilde, HoloLens 2 uygulaması x86 mimari paketini içermezse, HoloLens (1. nesil) cihazlarda kullanılamaz. HoloLens cihaz mimarileri:
>
> - x86 = HoloLens (1. nesil)
> - ARM = HoloLens 2

> [!NOTE]
> 12 Ocak 2021'de aşağıdaki uygulamalar, HoloLens erişecek. Uygulamanın web sürümünü kullanmak için cihazınızın aşağıdaki bağlantısını kullanmanızı teşvik etmek için.

| Uygulama        | Bağlantı                                          |
|------------|-----------------------------------------------|
| Excel mobil      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobil | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> OneDrive uygulama şu anda azure ad hesapları için destek HoloLens. Microsoft OneDrive PWA indirmenizi öneririz. [Uygulamayı indirmek için bu adımları izleyin.]

## <a name="install-apps"></a>Uygulama yükleme

Uygulamaları indirmek için bir Microsoft hesabı. Bazı uygulamalar ücretsizdir ve hemen indirilebilir. Satın alma gerektiren uygulamalar için Mağaza'da oturum a Microsoft hesabı geçerli bir ödeme yöntemine sahipsiniz.

> [!NOTE]
> Bu hesapta Microsoft Store hesabın, oturum asanızla aynı olması gerek değildir. Uygulamanıza bir İş veya Okul hesabı HoloLens satın alma yapmak için Mağaza Uygulamasında kişisel hesabınızla oturum açmanız gerekir.

> [!TIP]
> Bir ödeme yöntemi ayarlamak için Ödeme'ye [account.microsoft.com](https://account.microsoft.com/) ödeme seçenekleri Ödeme **seçenekleri'&**  >  **Ödeme seçeneği**  >  **ekle'yi seçin.**

1. Başlat menüsünü [ **açmak için**](holographic-home.md)bir Başlangıç hareketi [veya](/hololens/hololens2-basic-usage#start-gesture) [çiçek](hololens1-basic-usage.md) açma hareketi HoloLens (1. nesil) gerçekleştirin.

1. Microsoft Store seçin. Mağaza uygulaması açıldıktan sonra:
   1. Uygulamaları aramak için arama çubuğunu kullanın.
   1. Seçki olarak seçki olarak seçki olarak HoloLens uygulamalar veya uygulamalar seçin.
   1. Mağaza uygulamasının sağ üst kısmında **"..." düğmesini** ve ardından Daha önce satın alınan uygulamaları **görüntülemek** için Kitaplığım'ı seçin.

1. **Uygulamanın** **sayfasında Al** veya Yükle'yi seçin (satın alma gerekebilir).

### <a name="install-microsoft-onedrive-pwa-app"></a>Microsoft OneDrive PWA Uygulamasını Yükleme

Önkullar: Kullanıcı, HoloLens 2 cihazına iş kiracısına katılmış.

1. Başlat menüsünü açın ve Edge tarayıcısını açın.

    ![Başlat menüsü](images/office-pwa-1.jpg)

1. Çalışma HoloLens gidin ve [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) İş hesabı kimlik bilgilerinizi girin

    ![İş oturum açma](images/office-pwa-2.jpg)

1. OneDrive web portalında başarıyla oturum açtıktan sonra indir düğmesinin 30 -60 PWA kadar bekleyin

    ![PWA yükle düğmesi](images/office-pwa-3.jpg)

1. İlk PWA düğmesini seçin ve uygulamayı yükleyin

    ![Yükleme istemi](images/office-pwa-4.jpg)

1. Edge tarayıcısını kapatın ve Başlat menüsü Tüm Uygulamalar düğmesini **seçin** ve OneDrive PWA App'i **Microsoft OneDrive**

    ![Tüm uygulamalar iki uygulama da gösteriliyor.](images/office-pwa-5.jpg)

> [!NOTE]
> "Microsoft OneDrive", "PWA" olarak eski UWP'OneDrive uygulamadır.

1. Daha sonra dosya dosyalarınızı OneDrive.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Ayrıca bkz. [İş için OneDrive karşıya yüklemeleri etkinleştirme](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Uygulamaları Güncelleştirme

Microsoft Store'den yüklemiş olduğu bir uygulamayı güncelleştirmek için Microsoft Store güncelleştirebilirsiniz. İş İçin Microsoft Store için İş İçin Microsoft Store uygulamalar için, bu uygulamaları İş İçin Microsoft Store.

1. Başlat menüsünü [ **açmak için**](holographic-home.md)bir Başlangıç hareketi [veya](/hololens/hololens2-basic-usage#start-gesture) [çiçek](hololens1-basic-usage.md) açma hareketi HoloLens (1. nesil) gerçekleştirin.

1. Mağaza uygulamasını seçin.

1. Mağaza uygulamasının sağ üst kısmından bakın.

1. **"..." veya "Daha** fazla gör" düğmesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store ekran görüntüsü.](images/store-update-1.png)

1. İndirmeler **ve güncelleştirmeler'i seçin.**
    1. Cihazınız daha önce güncelleştirmeleri belirlediyse, bekleyen güncelleştirmeleri temsil eden bir aşağı ok ve bir sayı olabilir.

1. Güncelleştirmeleri **al'ı seçin.** Cihazınız artık güncelleştirmeleri arayacak ve bunları indirecek ve yükecek şekilde ayarlayacak.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store alma uygulama ekran görüntüsü.](images/store-update-2.png.jpg)

> [!NOTE]
> Cihaz uygulamaları, cihazınız tarafından dağıtılmışsa, bunlar aynı ticari uygulama yönetimi yöntemleri aracılığıyla güncelleştirilebilir. Bu sizin durumunuz için geçerli ise, ticari uygulama dağıtımına genel [bakış bilgilerimiz aracılığıyla daha fazla bilgi edinebilirsiniz.](app-deploy-overview.md)
>
> Kenardan yüklenmiş veya dağıtılmış özel bir uygulamayı güncelleştirmek için, aynı yöntemi, uygulamanın güncelleştirilmiş sürümüyle birlikte kullanabilirsiniz. Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için özel [holografik uygulamalar makalesini okuyun.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Uygulamaları kaldırma

Uygulamaları kaldırmanın üç yolu vardır. Uygulamaları uygulama aracılığıyla Microsoft Store, Başlat menüsü veya Ayarlar.

> [!WARNING]
> Sistem uygulamasını veya uygulamanın kendisini Microsoft Store.

> [!IMPORTANT]
> 2. HoloLens kullanıcınız varsa, uygulamayı kaldırmak için uygulamayı yüken kullanıcı olarak oturum açmış olursanız.

### <a name="uninstall-from-the-microsoft-store"></a>Yüklemeden Microsoft Store

Başlat menüsünden Microsoft Store **açın** ve kaldırmak istediğiniz uygulamaya göz atabilirsiniz.  Mağaza sayfasında, yüklü her uygulamanın bir Kaldır **düğmesi** vardır.

### <a name="uninstall-from-the-start-menu"></a>Yüklemeden Başlat menüsü

Başlat **menüsünde** veya Tüm uygulamalar  uygulamaya göz atabilirsiniz. Menü görüntülenene kadar basılı tutun ve ardından Kaldır'ı **seçin.**

### <a name="uninstall-from-settings"></a>Ayarlar'den kaldırma

Başlat menüsünde **Uygulamalar'ı** **Ayarlar > seçin.** Listeden uygulamayı bulun, seçin ve ardından Kaldır'a **tıklayın.**

Bir uygulamayı kaldıramıyorsanız lütfen uygulamayı kullanarak [geri](/hololens/hololens-feedback) bildirim Geri Bildirim Merkezi.
