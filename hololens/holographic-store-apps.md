---
title: Uygulamaları bulma, yükleme ve kaldırma
description: Microsoft Store, HoloLens birlikte çalışan uygulamalar ve oyunlar için kaynağınız olur.  Holographic uygulamalarını bulma, yükleme ve kaldırma hakkında daha fazla bilgi edinin.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: Hololens, mağaza, UWP, uygulama, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f7d4ddf41f02b083000c1e57f5140c38527826d7
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364406"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Microsoft Store uygulamaları bulun, yükleme ve kaldırma

Microsoft Store, HoloLens birlikte çalışan uygulamalar ve oyunlar için go kaynağıdır. HoloLens mağazaya gittiğinizde, burada gördüğünüz tüm uygulamalar üzerinde çalışır.

HoloLens uygulamalar, 2b görünüm veya holographic görünümünü kullanır. 2B görünümü kullanan uygulamalar Windows gibi görünür ve tüm bunların etrafında konumlandırılmış olabilir. Holographic View kullanan uygulamalar sizi çevreler ve gördüğünüz tek uygulama olur.

HoloLens, Microsoft Store birçok mevcut uygulamayı ve özellikle HoloLens için oluşturulan yeni uygulamaları destekler.  Bu makale, Microsoft Store holographic uygulamalarına odaklanır.

Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.

## <a name="find-apps"></a>Uygulama bulun

**başlangıç** menüsünden Microsoft Store açın. Ardından uygulamalar ve Oyunlar için tarama yapın. Arama penceresi açıldıktan sonra arama terimlerinizi söylediğinizde, "arama" ifadesini kullanarak arama yapmak için [sesli komutları](hololens-cortana.md) kullanabilirsiniz.

> [!NOTE]
> HoloLens cihazların sistem gereksinimleri, uygulama yapısı mimarisine dayalıdır. HoloLens için bir uygulama derlemesi (1. gen), ARM mimari paketini dahil etmek üzere mağazadaki daha yeni bir UWP ile güncellenmemişse, HoloLens 2 cihaz için kullanılamaz. benzer şekilde, bir HoloLens 2 uygulaması x86 mimari paketini içermiyorsa, HoloLens (1. gen) cihazlar için kullanılamaz. cihaz mimarilerini HoloLens:
>
> - x86 = HoloLens (1. genel)
> - ARM = HoloLens 2

> [!NOTE]
> 12 ocak 2021 tarihinde aşağıdaki uygulamalar HoloLens cihazlarda destek sonuna ulaşacaktır. Uygulamanın Web sürümünü kullanmak için cihazınızda aşağıdaki bağlantıyı kullanmanız önerilir.

| Uygulama        | Bağlantı                                          |
|------------|-----------------------------------------------|
| Excel mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> OneDrive uygulaması şu anda HoloLens Azure AD hesapları için desteklenmiyor. Microsoft OneDrive PWA uygulamasını indirmenizi öneririz. [Uygulamayı indirmek için bu adımları izleyin.]

## <a name="install-apps"></a>Uygulama yükleme

Uygulamaları indirmek için bir Microsoft hesabı oturum açmanız gerekir. Bazı uygulamalar ücretsizdir ve hemen indirilebilirler. Satın alma gerektiren uygulamalar için, Microsoft hesabı depoda oturum açmış ve geçerli bir ödeme yöntemine sahip olmanız gerekir.

> [!NOTE]
> Microsoft Store üzerinde kullandığınız hesabın, oturum açtığınız hesapla aynı olması gerekmez. HoloLens bir iş veya okul hesabı kullanıyorsanız, satın alma gerçekleştirmek için mağaza uygulamasındaki kişisel hesabınızla oturum açmanız gerekebilir.

> [!TIP]
> Bir ödeme yöntemi ayarlamak için [account.Microsoft.com](https://account.microsoft.com/) adresine gidin ve **ödeme & faturalandırma**  >  **ödeme seçenekleri**  >  **ödeme seçeneği Ekle**' yi seçin.

1. [ **başlat** menüsünü](holographic-home.md)açmak için HoloLens (1. gen) bir [başlangıç hareketini](/hololens/hololens2-basic-usage#start-gesture) veya [bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.

1. Microsoft Store uygulamasını seçin. Mağaza uygulaması açıldıktan sonra:
   1. Uygulamaları aramak için arama çubuğunu kullanın.
   1. temel alınan kategorilerden birinden HoloLens için özel uygulamalar veya özel olarak yapılan uygulamalar seçin.
   1. Mağaza uygulamasının sağ üst kısmında, **"..."** düğmesini seçin ve ardından, daha önce satın alınan uygulamaları görüntülemek için **Kitaplığımı** seçin.

1. Uygulamanın sayfasında Al **veya** **Al** ' ı seçin (satın alma gerekebilir).

### <a name="install-microsoft-onedrive-pwa-app"></a>Microsoft OneDrive PWA uygulamasını yükler

ön koşullar: kullanıcı HoloLens 2 cihazını iş kiracılarına zaten katılmış.

1. Başlat menüsünü açın ve Edge tarayıcısını başlatın.

    ![Başlat menüsü](images/office-pwa-1.jpg)

1. HoloLens gidin [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) ve iş hesabı kimlik bilgilerinizi girin

    ![İş oturum açma](images/office-pwa-2.jpg)

1. OneDrive web portalınıza başarıyla oturum açtıktan sonra, PWA indirme düğmesinin görünmesi için 30 ila 60 saniye bekleyin

    ![PWA install düğmesi](images/office-pwa-3.jpg)

1. PWA indir düğmesini seçin ve uygulamayı yükleyin

    ![Yüklemeyi sor](images/office-pwa-4.jpg)

1. Edge tarayıcısını kapatıp Başlat menüsü, **tüm uygulamalar** düğmesini seçin ve etiketli OneDrive PWA uygulamayı başlatın **Microsoft OneDrive**

    ![Her iki uygulamayı da gösteren tüm uygulamalar.](images/office-pwa-5.jpg)

    > [!NOTE]
    > "Microsoft OneDrive", "OneDrive" nin eski UWP olduğu PWA uygulamasıdır.

1. daha sonra OneDrive dosyalarınızı görebileceksiniz.

    ![OneDrive PWA](images/office-pwa-6.jpg)

ayrıca bkz: [iş için OneDrive otomatik karşıya yüklemeyi etkinleştirme](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Uygulamaları güncelleştirme

### <a name="manual-updates"></a>El ile güncelleştirmeler

Microsoft Store yüklediğiniz bir uygulamayı güncelleştirmek için Microsoft Store uygulamasından uygulamayı güncelleştirebilirsiniz. İş İçin Microsoft Store için yüklü uygulamalar için bu uygulamaları İş İçin Microsoft Store güncelleştirebilirsiniz.

1. [ **başlat** menüsünü](holographic-home.md)açmak için HoloLens (1. gen) bir [başlangıç hareketini](/hololens/hololens2-basic-usage#start-gesture) veya [bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.

1. Mağaza uygulamasını seçin.

1. Mağaza uygulamasının sağ üst kısmına bakın.

1. **"..."** Veya "daha fazla gör" düğmesini seçin.

   > [!div class="mx-imgBorder"]
   > ![uygulama ekran görüntüsü Microsoft Store.](images/store-update-1.png)

1. **İndirmeler ve Güncelleştirmeler '** i seçin.
    1. Cihazınızda daha önce güncelleştirmeler tanımlanmışsa, bekleyen güncelleştirmeleri temsil eden bir aşağı ok ve bir sayı olabilir.

1. **Güncelleştirme al**' ı seçin. Cihazınız artık güncelleştirmeleri arayacak ve bunları indirip yükleyecek şekilde ayarlayacaktır.

   > [!div class="mx-imgBorder"]
   > ![güncelleştirmelerin alınması için uygulama ekran görüntüsü Microsoft Store..](images/store-update-2.png.jpg)

> [!NOTE]
> Cihazınızdaki uygulamalar kuruluşunuz tarafından dağıtılmışsa, aynı ticari uygulama yönetimi yöntemleriyle de güncelleştirilemeyebilir. Bu durum geçerliyse, [ticari uygulama dağıtımına genel bakış](app-deploy-overview.md) aracılığıyla daha fazla bilgi edinin.
>
> Dışarıdan yüklenen veya dağıtılan bir özel uygulamayı güncelleştirmek isterseniz, uygulamanızın güncelleştirilmiş sürümüyle aynı yöntemi kullanmanız gerekir. Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.

### <a name="automatic-app-updates"></a>Otomatik uygulama güncelleştirmeleri

otomatik güncelleştirmeler Microsoft Store veya İş İçin Microsoft Store uygulamalar için geçerlidir ve yalnızca doğrudan mağazadan yüklenmiş olmaları durumunda otomatik olarak güncelleştirilir. ıntune 'dan yüklüyse, uygulamanın kullanılabilir en son sürümü için İş İçin Microsoft Store ile eşitleyerek güncelleştirmeleri MDM 'den aşağı gönderebilir.

> [!NOTE]
> İş İçin Microsoft Store kaynaklı uygulamalar için, depoda oturum açmış ve cihazda kullanılan İş İçin Microsoft Store kataloğu ile ilişkili aynı kiracı ile kimlik doğrulamasından sahip olmalısınız.

#### <a name="how-automatic-updates-work"></a>Otomatik güncelleştirmeler nasıl çalışır?

Otomatik uygulama güncelleştirmeleri, ağ kullanılabilirliğine tabi olmak üzere her gün (yaklaşık 24 saatte bir) gerçekleşecek şekilde zamanlanır. Güncelleştirmeleri almak için cihazınızı etkin veya AC 'ya takılı tutun. Etkin günlük kullanım sırasında uygulama güncelleştirmeleri indirilse bile, bunlar yalnızca güncelleştirme yapılacak uygulama artık kullanımda olmadığında geçerli olur.

> [!TIP]
> Mümkünse, şirket ağına bağlıyken cihazınızı gece fazla ücretlendirin. Güncelleştirmeler indirilip aşırı gece yüklenebiliyorsanız, etkin cihaz kullanımını kesintiye uğratan daha az olabilir.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>BT yöneticileri otomatik güncelleştirmeleri nasıl denetleyebilir

BT yöneticileri, otomatik uygulama güncelleştirmelerini [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) ilkesi aracılığıyla denetleyebilir. Bu ilke, otomatik uygulama güncelleştirmelerini tamamen etkinleştirmesine veya devre dışı bırakmasına izin verir, ancak güncelleştirmelerin ne zaman gerçekleşeceğini denetlemez.

[21H2](hololens-release-notes.md#windows-holographic-version-21h1)itibariyle, BT yöneticileri kullanımda olan uygulamaların ne zaman çalıştığını denetlemek Için [Scheduleforcerestartforupdatearızaları](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) ilkesini de kullanabilir, ancak önceki denemelerde güncelleştirilemeyebilir, zorla yeniden başlatılmalıdır.

## <a name="uninstall-apps"></a>Uygulamaları kaldırma

Uygulamaları kaldırmanın üç yolu vardır. Microsoft Store, Başlat menüsü veya Ayarlar aracılığıyla uygulama kaldırabilirsiniz.

> [!WARNING]
> bir sistem uygulamasını veya Microsoft Store kaldıramıyorsunuz.

> [!IMPORTANT]
> HoloLens 2 ' de birden çok kullanıcı varsa, uygulamayı kaldırmak için uygulamayı yükleyen kullanıcı olarak oturum açmış olmanız gerekir.

### <a name="uninstall-from-the-microsoft-store"></a>Microsoft Store kaldır

**başlat** menüsünden Microsoft Store açın ve ardından kaldırmak istediğiniz uygulamaya gidin.  Mağaza sayfasında, yüklenen her uygulamanın bir **kaldırma** düğmesi vardır.

### <a name="uninstall-from-the-start-menu"></a>Başlat menüsü kaldır

**Başlat** menüsünde veya **tüm uygulamalar** listesinde, uygulamaya gidin. Menü görünene kadar seçin ve basılı tutun, ardından **Kaldır**' ı seçin.

### <a name="uninstall-from-settings"></a>Ayarlar 'den kaldır

**başlat** menüsünde **Ayarlar > uygulamalar** ' ı seçin. Listeden uygulamayı bulun, seçin ve ardından **Kaldır**' a tıklayın.

Bir uygulamayı kaldıramıyorsanız lütfen geri bildirim hub 'ını kullanarak [geri bildirim gönderin](/hololens/hololens-feedback) .
