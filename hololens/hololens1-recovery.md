---
title: Yeniden başlatma, sıfırlama veya kurtarma HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows 1. Nesil'e bir görüntü HoloLens Için Cihaz Kurtarma Aracı'nı kullanma.
keywords: nasıl yapıldığı, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, yazılım sıfırlama, güç döngüsü, HoloLens, kapatma, wdrt, Windows cihaz kurtarma aracı
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d6eb706c50e97a81910180c70be1d9dbc52bc6603cbc77ad130c1dd3b6a9010e
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661814"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Yeniden başlatma, sıfırlama veya HoloLens (1. Nesil)

Cihaz kurtarma işlemiyle ilgili sorunlar HoloLens, yeniden başlatmayı veya sıfırlamayı veya hatta cihaz kurtarmayı kullanarak cihazı yeniden başlatmayı sınabilirsiniz. Bu makale, önerilen kurtarma adımlarında sırayla size yol sağlar.

2. bir HoloLens kurtarmak için bkz. Bu işlem [farklı HoloLens 2](hololens-recovery.md)kurtarma.

> [!NOTE]
> Bu makale, cihaz ve HoloLens yazılıma odaklanır. Hologramlar doğru görünmüyorsa, hologram **[kalitesini HoloLens](hololens-environment-considerations.md)** faktörler hakkında bilgi için bkz. ortamla ilgili dikkat edilmesi gerekenler.

## <a name="restart"></a>Yeniden başlat

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana kullanarak güvenli bir yeniden başlatma Cortana

HoloLens'ı yeniden başlatmanın en güvenli yolu, Cortana kullanarak yeniden başlatmanın en güvenli yoludur. Bu, genellikle HoloLens.

> [!NOTE] 
> Cortana tüm cihazlarda kullanılamaz.
> - Cortana tüm HoloLens (1. Nesil) cihazlarda kullanılabilir. 
> - Cortana, HoloLens Holograpic Sürüm 2004 güncelleştirme Windows derlemelerde 2 cihaz üzerinde kullanılabilir.

1. Kendi HoloLens.
1. Kullanıcının oturum açtığından ve cihazın kilidini açmak için parola beklemey olduğundan emin olun.
2. "Hey Cortana, yeniden başlat" veya "Hey Cortana, yeniden başlat" de.
3. Cortana yanıt verir ve onaylamanızı istenir. Sorudan sonra bir ses çalması için bekleyin ve ardından "Evet" der. Cihaz yeniden başlatılır.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Güvenli yeniden başlatma yapmak için güç düğmesini kullanma

Cihazınızı yeniden başlatamaya devam ediyorsanız güç düğmesini kullanarak cihazı yeniden **başlatmayı** deneyin:

1. Güç düğmesine 5 **saniye** basılı tutun. 1 saniye sonra, beş LED'in hepsi yanacak ve ardından sağdan sola doğru yavaş bir şekilde kapatacak. 5 saniye sonra tüm LED'ler kapalı olur ve kapatma başarılı olur.
      
   > [!IMPORTANT]
   > Tüm LED'ler kapatıldığında düğmeye basmayı hemen durdurun.
1. Kapatma işleminin tamamlanması için 1 dakika bekleyin. Ekranlar kapatılana kadar kapatma işlemi devam ediyor olabilir.
2. Güç düğmesine 1 saniye basılı tutarak **cihazı** yeniden açın.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows Cihaz Portalı kullanarak güvenli bir yeniden başlatma Windows Cihaz Portalı

> [!NOTE]
> Bu işlem için HoloLens bir geliştirici cihazı olarak yapılandırılması gerekir. daha fazla bilgi için [Windows Cihaz Portalı.](/windows/mixed-reality/using-the-windows-device-portal)

Önceki yordam işe başlatılmazsa, Windows Cihaz Portalı kullanarak cihazı [yeniden başlatmayı deneyin.](/windows/mixed-reality/using-the-windows-device-portal) Sağ üst köşede cihazı yeniden başlatma veya kapatma seçeneğini bulun.

### <a name="do-an-unsafe-forced-restart"></a>Güvenli olmayan bir zorlamalı yeniden başlatma yapma

Önceki yöntemler uygulamanızı yeniden başlatmadı HoloLens yeniden başlatmaya zorlar. Bu yöntem, pilin kaldırılmasına ve yeniden yüklenmesine eşdeğerdir. Cihazınızı bozuk durumda bırakarak tehlikeli olabilir. Böyle bir durumda, kendi HoloLens.  

> [!WARNING]
> Bu zararlı olabilecek bir yöntemdir ve yalnızca daha önce adedi yapılan yöntemler işemasa kullanılmalıdır.

1. Güç düğmesine en **az** 10 saniye basılı tutun.
   - Düğmeyi 10 saniyeden uzun süre tutabilir.
   - Herhangi bir LED etkinliğini yoksaymak güvenlidir.
1. Düğmeyi bırakın ve 2-3 saniye bekleyin.
1. Güç düğmesine 1 **saniye** basılı tutun.
1. Sorun devam ediyorsanız,  tüm pil göstergeleri belirene ve ekran hologramları görüntülemeyi durdurana kadar güç düğmesine 4 saniye basın. 1 dakika bekleyin ve ardından cihazı **açmak** için güç düğmesine tekrar basın.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Geri dön bir sürüme - HoloLens (1. Nesil)

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek HoloLens olabilir. Bunu yapmak için Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens önceki sürüme sıfırlayabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

HoloLens 1'in önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows emin olun.
1. Bilgisayarınızda, Windows [Kurtarma Aracı'nı (WDRT) indirin.](https://support.microsoft.com/help/12379)
1. Yıldönümü [HoloLens kurtarma paketini indirin.](https://aka.ms/hololensrecovery)
1. İndirmeler tamam olduğunda Dosya Gezgini **İndirmeleri'ni**  >  **açın.** İndirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak için **Tüm**  >  **Ayıkla'yı** seçin.
1. Bağlan, HoloLens mikro USB kablosunu kullanarak bilgisayarınıza bağlayın. (Bağlantınızı bağlamak için başka kablolar HoloLens bile bu en iyi şekilde çalışır.)
1. WDRT, kullanıcılarınızı otomatik olarak HoloLens. Yeni **kutucuğu Microsoft HoloLens** seçin.
1. Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve 4. adımda sıkıştırması açmak istediğiniz klasörde yer alan yükleme dosyasını seçin. (.ffu uzantısına sahip bir dosya bulun.)
1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

> [!NOTE]
> WDRT, uygulamanızı algılaya HoloLens bilgisayarınızı yeniden başlatmayı deneyin. Bu işe uymazsa Cihazım algılanmadı'yi  **seçin,** Microsoft HoloLens'ı seçin ve yönergeleri izleyin.

## <a name="reset-to-factory-settings"></a>Fabrika ayarlarına sıfırlama

> [!NOTE]
> Pilin sıfırlanabilir olması için en az yüzde 40 ücrete ihtiyacı vardır.

Çalışma HoloLens sorun devam ediyorsa fabrika durumuna sıfırlamayı deneyin. Bu adım, Windows Holographic yazılımının yüklü olduğu sürümü tutar ve diğer her şeyi fabrika ayarlarına döndürür.

>[!WARNING]
> Cihazınızı sıfırlarsanız TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir. Sıfırlama yalnızca Holographic'in en son yüklü Windows yüklenir. Tüm başlatma adımlarını (ayarlama, Wi-Fi'a bağlanma, bir kullanıcı hesabı oluşturma, uygulamaları indirme vb.) tekrarlamanız gerekir.

1. Uygulama uygulama Ayarlar ve ardından Kurtarmayı **Güncelleştir'i**  >  **seçin.**
1. Cihazı **sıfırla seçeneğini** belirleyin ve onay iletiyi okuyun.
1. Sıfırlamayı onaylayın. Cihaz yeniden başlatılır ve bir dizi dönen dişli ve ilerleme çubuğu görüntülenir.
1. Bu sürecin tamamlanması için yaklaşık 30 dakika bekleyin. Bu bittiğinde, cihaz "ilk önce" deneyimine yeniden başlatılır.

## <a name="reinstall-the-operating-system"></a>İşletim sistemini yeniden yükleme

Yeniden başlatma ve sıfırlama sonrasında cihaz sorun devam ediyorsa, bilgisayarınızda bir kurtarma aracı kullanarak işletim sistemini ve üretici yazılımını HoloLens yükleyebilirsiniz.  

Sıfırlama için HoloLens veriler bir .iso, .wim veya .vhd dosyasına benzer bir Tam Flash Güncelleştirme (FFU) içinde paketlenmiştir. [FFU görüntü dosyası biçimleri hakkında bilgi edinmek için.](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens (1. nesil) bilgisayarınıza yeni bir işletim sistemi yükleyebilirsiniz. Bu aracı kullanmadan önce, yeniden başlatma veya sıfırlama HoloLens düzeltin.

Kurtarma işlemi biraz zaman alır. Bu bittiğinde, Windows Holographic yazılımının en son sürümü yüklenir.

Aracı kullanmak için en az 4 GB boş Windows 10 veya sonraki bir bilgisayarda çalışmanız gerekir. Bu aracı bir sanal makinede çalıştıraabilirsiniz.

### <a name="recover-your-hololens"></a>HoloLens

1. Windows Cihaz [Kurtarma Aracı'nı indirip](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) bilgisayarınıza yükleyin.
1. Bağlan HoloLens mikro USB kablosunu kullanarak bilgisayarınıza (1. nesil) HoloLens.
1. Windows Kurtarma Aracı'nı açın ve yönergeleri izleyin.

Cihaz HoloLens (1. nesil) otomatik olarak algılanmazsa Cihazım **algılanmadı seçeneğini seçin.** Ardından yönergeleri izleyerek cihazı kurtarma moduna alın.

### <a name="manual-flashing-mode"></a>El ile yanıp sönme modu

Cihazınız algılanmazsa, cihazı yanıp sönen moda koymak için şu adımları izleyin:

1. Cihazı herhangi bir güç kaynağından çıkarın.
1. Cihaz açıksa, tamamen **kapatana** kadar güç düğmesini basılı tutun.
2. Birimi **yukarı doğru** tutun ve güç düğmesine kısa bir **süre** dokunun. Cihazın başlaması ve yalnızca ortadaki LED'i görüntülemesi gerekir.
3. Cihazı bilgisayarınıza takın.
4. Windows Kurtarma Aracı'nı açın.
5. Cihazım **algılanmadı'yi seçin ve** sonra **HoloLens.** 
6. Cihazınızı kurtarmak için yönergeleri izleyin.
