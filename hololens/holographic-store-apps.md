---
title: Uygulamaları bulma, yükleme ve kaldırma
description: Microsoft Store, HoloLens ile çalışan uygulamalar ve Oyunlar için kaynağınız olur.  Holographic uygulamalarını bulma, yükleme ve kaldırma hakkında daha fazla bilgi edinin.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
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
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380171"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Microsoft Store uygulamaları bulun, yükleme ve kaldırma

Microsoft Store, HoloLens ile çalışan uygulamalar ve Oyunlar için go kaynağıdır. HoloLens 'teki mağazaya gittiğinizde, burada gördüğünüz tüm uygulamalar üzerinde çalışır.

HoloLens 'teki uygulamalar 2B görünüm veya holographic görünümünü kullanır. 2B görünümü kullanan uygulamalar Windows gibi görünür ve tüm bunların etrafında konumlandırılmış olabilir. Holographic View kullanan uygulamalar sizi çevreler ve gördüğünüz tek uygulama olur.

HoloLens, Microsoft Store var olan birçok uygulamayı ve özel olarak HoloLens için oluşturulan yeni uygulamaları destekler.  Bu makale, Microsoft Store holographic uygulamalarına odaklanır.

Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.

## <a name="find-apps"></a>Uygulama bulun

**Başlangıç** menüsünden Microsoft Store açın. Ardından uygulamalar ve Oyunlar için tarama yapın. Arama penceresi açıldıktan sonra arama terimlerinizi söylediğinizde, "arama" ifadesini kullanarak arama yapmak için [sesli komutları](hololens-cortana.md) kullanabilirsiniz.

> [!NOTE]
> HoloLens cihazları için sistem gereksinimleri, uygulama yapısının mimarisine dayalıdır. HoloLens için bir uygulama derlemesi (1. gen), ARM mimari paketini dahil etmek üzere mağazadaki daha yeni bir UWP ile güncellenmemişse, HoloLens 2 cihazları için kullanılabilir olmayacaktır. Benzer şekilde, bir HoloLens 2 uygulaması x86 mimari paketini içermiyorsa, HoloLens (1. gen) cihazlar için kullanılamaz. HoloLens cihaz mimarileri:
> - x86 = HoloLens (1. Genel)
> - ARM = HoloLens 2

> [!NOTE]
> 12 Ocak 2021 tarihinde aşağıdaki uygulamalar, HoloLens cihazlarda destek sonuna ulaşacaktır. Uygulamanın Web sürümünü kullanmak için cihazınızda aşağıdaki bağlantıyı kullanmanız önerilir.

| Uygulama        | Bağlantı                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint mobil | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a>Uygulama yükleme

Uygulamaları indirmek için bir Microsoft hesabı oturum açmanız gerekir. Bazı uygulamalar ücretsizdir ve hemen indirilebilirler. Satın alma gerektiren uygulamalar için, Microsoft hesabı depoda oturum açmış ve geçerli bir ödeme yöntemine sahip olmanız gerekir.

> [!NOTE]
> Microsoft Store üzerinde kullandığınız hesabın, oturum açtığınız hesapla aynı olması gerekmez. HoloLens 'te bir Iş veya okul hesabı kullanıyorsanız, satın alma gerçekleştirmek için mağaza uygulamasındaki kişisel hesabınızla oturum açmanız gerekebilir.

> [!TIP]
> Bir ödeme yöntemi ayarlamak için [account.Microsoft.com](https://account.microsoft.com/) adresine gidin ve **ödeme & faturalandırma**  >  **ödeme seçenekleri**  >  **ödeme seçeneği Ekle**' yi seçin.

1. [ **Başlat** menüsünü](holographic-home.md)açmak için, Hololens (1. gen) üzerinde [Başlangıç hareketini](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) veya [Bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.

1. Microsoft Store uygulamasını seçin. Mağaza uygulaması açıldıktan sonra:
   1. Uygulamaları aramak için arama çubuğunu kullanın. 
   1. Seçilen kategorilerden birinden yalnızca HoloLens için oluşturulan temel uygulamaları veya uygulamaları seçin.
   1. Mağaza uygulamasının sağ üst kısmında, **"..."** düğmesini seçin ve ardından, daha önce satın alınan uygulamaları görüntülemek için **Kitaplığımı** seçin.

1. Uygulamanın sayfasında Al **veya** **Al** ' ı seçin (satın alma gerekebilir).

## <a name="update-apps"></a>Uygulamaları güncelleştirme

Microsoft Store yüklediğiniz bir uygulamayı güncelleştirmek için Microsoft Store uygulamasından uygulamayı güncelleştirebilirsiniz. Iş için Microsoft Store yüklü uygulamalar için, bu uygulamaları Microsoft Store Iş için de güncelleştirebilirsiniz. 

1. [ **Başlat** menüsünü](holographic-home.md)açmak için, Hololens (1. gen) üzerinde [Başlangıç hareketini](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) veya [Bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.

1. Mağaza uygulamasını seçin.

1. Mağaza uygulamasının sağ üst kısmına bakın. 

1. **"..."** Veya "daha fazla gör" düğmesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Uygulama ekran görüntüsü Microsoft Store.](images/store-update-1.png)

1. **İndirmeler ve Güncelleştirmeler '** i seçin.
    1. Cihazınızda daha önce güncelleştirmeler tanımlanmışsa, bekleyen güncelleştirmeleri temsil eden bir aşağı ok ve bir sayı olabilir.

1. **Güncelleştirme al**' ı seçin. Cihazınız artık güncelleştirmeleri arayacak ve bunları indirip yükleyecek şekilde ayarlayacaktır. 
 
   > [!div class="mx-imgBorder"]
   > ![Güncelleştirmelerin alınması için uygulama ekran görüntüsü Microsoft Store..](images/store-update-2.png.jpg)

> [!NOTE]
> Cihazınızdaki uygulamalar kuruluşunuz tarafından dağıtılmışsa, aynı ticari uygulama yönetimi yöntemleriyle de güncelleştirilemeyebilir. Bu durum geçerliyse, [ticari uygulama dağıtımına genel bakış](app-deploy-overview.md) aracılığıyla daha fazla bilgi edinin.
>
> Dışarıdan yüklenen veya dağıtılan bir özel uygulamayı güncelleştirmek isterseniz, uygulamanızın güncelleştirilmiş sürümüyle aynı yöntemi kullanmanız gerekir. Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.

## <a name="uninstall-apps"></a>Uygulamaları kaldırma

Uygulamaları kaldırmanın üç yolu vardır. Microsoft Store, Başlat menüsü veya ayarlardan uygulamaları kaldırabilirsiniz. 

> [!WARNING]
> Bir sistem uygulamasını veya Microsoft Store kaldıramıyorsunuz.

> [!IMPORTANT]
> HoloLens 2 ' de birden çok kullanıcı varsa, uygulamayı kaldırmak için uygulamayı yükleyen kullanıcı olarak oturum açmış olmanız gerekir. 

### <a name="uninstall-from-the-microsoft-store"></a>Microsoft Store kaldır

**Başlat** menüsünden Microsoft Store açın ve ardından kaldırmak istediğiniz uygulamaya gidin.  Mağaza sayfasında, yüklenen her uygulamanın bir **kaldırma** düğmesi vardır.

### <a name="uninstall-from-the-start-menu"></a>Başlat menüsünden kaldır

**Başlat** menüsünde veya **tüm uygulamalar** listesinde, uygulamaya gidin. Menü görünene kadar seçin ve basılı tutun, ardından **Kaldır**' ı seçin.

### <a name="uninstall-from-settings"></a>Ayarlardan kaldır
**Başlat** menüsünde **Ayarlar-> uygulamalar** ' ı seçin. Listeden uygulamayı bulun, seçin ve ardından **Kaldır**' a tıklayın.

Bir uygulamayı kaldıramıyorsanız lütfen geri bildirim hub 'ını kullanarak [geri bildirim gönderin](https://docs.microsoft.com/hololens/hololens-feedback) .
