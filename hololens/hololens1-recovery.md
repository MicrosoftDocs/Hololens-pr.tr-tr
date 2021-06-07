---
title: HoloLens 1'i yeniden başlatma, sıfırlama veya kurtarma
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens 1. Nesil'e görüntü gösterme.
keywords: nasıl yapıldığı, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, yazılım sıfırlaması, güç döngüsü, HoloLens, kapatma, wdrt, Windows cihaz kurtarma aracı
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
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379030"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens'i yeniden başlatma, sıfırlama veya kurtarma (1. Nesil)

HoloLens'iniz ile ilgili sorunlar yaşıyorsanız yeniden başlatmayı, sıfırlamayı veya hatta cihaz kurtarmayı kullanarak cihazı ters eğik çizgiyle sıfırlamayı sınabilirsiniz. Bu makale, önerilen kurtarma adımlarında sırayla size yol sağlar.

Bir HoloLens 2'nin kurtarılma sürecini arıyorsanız, bu işlem farklı olduğu için bkz. [HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)kurtarma.

> [!NOTE]
> Bu makale HoloLens cihazına ve yazılımına odaklanır. Hologramlar doğru görünmüyorsa hologram kalitesini geliştiren faktörler hakkında bilgi için **[HoloLens](hololens-environment-considerations.md)** ortamıyla ilgili dikkat edilmesi gerekenler'e bakın.

## <a name="restart"></a>Yeniden başlat

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana'yı kullanarak güvenli bir yeniden başlatma işlemi yapma

HoloLens'i yeniden başlatmanın en güvenli yolu Cortana'yı kullanmaktır. HoloLens ile ilgili bir sorun yaşamanız genellikle ilk denemedir.

> [!NOTE] 
> Cortana tüm cihazlarda kullanılamaz.
> - Cortana tüm HoloLens (1. Nesil) cihazlarda kullanılabilir. 
> - Cortana, Windows Holograpic Sürüm 2004 güncelleştirmeden önceki derlemelerde HoloLens 2 cihazlarında kullanılabilir.

1. HoloLens'inizi açma.
1. Kullanıcının oturum açtığından ve cihazın kilidini açmak için parola beklemey olduğundan emin olun.
2. "Hey Cortana, yeniden başlat" veya "Hey Cortana, yeniden başlat" de.
3. Cortana yanıt verir ve onaylamanızı istenir. Sorudan sonra bir ses çalması için bekleyin ve ardından "Evet" der. Cihaz yeniden başlatılır.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Güvenli yeniden başlatma yapmak için güç düğmesini kullanma

Cihazınızı yeniden başlatamaya devam ediyorsanız güç düğmesini kullanarak cihazı yeniden **başlatmayı** deneyin:

1. Güç düğmesine 5 **saniye** basılı tutun. 1 saniye sonra beş LED'in hepsi yavaş yavaş kapatılarak sağdan sola doğru tek tek devre dışı bırakılarak. 5 saniye sonra tüm LED'ler kapalı olur ve kapatma başarılı olur.
      
   > [!IMPORTANT]
   > Tüm LED'ler kapatıldığında düğmeye basmayı hemen durdurun.
1. Kapatma işleminin tamamlanması için 1 dakika bekleyin. Ekranlar kapatılana kadar kapatma işlemi devam ediyor olabilir.
2. Güç düğmesine 1 saniye basılı tutarak **cihazı** yeniden açın.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows Cihaz Portalı kullanarak güvenli bir yeniden başlatma Windows Cihaz Portalı

> [!NOTE]
> Bu işlem için HoloLens'in bir geliştirici cihazı olarak yapılandırılması gerekir. daha fazla bilgi için [Windows Cihaz Portalı.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)

Önceki yordam işe başlatılmazsa, Windows Cihaz Portalı kullanarak [cihazı yeniden başlatmayı deneyin.](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Sağ üst köşede cihazı yeniden başlatma veya kapatma seçeneğini bulun.

### <a name="do-an-unsafe-forced-restart"></a>Güvenli olmayan bir zorlamalı yeniden başlatma yapma

Önceki yöntemler HoloLens'inizi yeniden başlatmamışsa yeniden başlatmaya zorlar. Bu yöntem, pilin kaldırılmasına ve yeniden yüklenmesine eşdeğerdir. Cihazınızı bozuk durumda bırakarak tehlikeli olabilir. Böyle bir durumda HoloLens'inizi flash iletirsiniz.  

> [!WARNING]
> Bu zararlı olabilecek bir yöntemdir ve yalnızca daha önce adedi yapılan yöntemler işemasa kullanılmalıdır.

1. Güç düğmesine en **az** 10 saniye basılı tutun.
   - Düğmeyi 10 saniyeden uzun süre tutabilir.
   - Herhangi bir LED etkinliğini yoksaymak güvenlidir.
1. Düğmeyi bırakın ve 2-3 saniye bekleyin.
1. Güç düğmesine 1 **saniye** basılı tutun.
1. Sorun devam ediyorsa,  tüm pil göstergeleri belirene ve ekran hologramları görüntülemeyi durdurana kadar güç düğmesine 4 saniye basın. 1 dakika bekleyin ve ardından cihazı **açmak** için güç düğmesine tekrar basın.

## <a name="reset-to-factory-settings"></a>Fabrika ayarlarına sıfırlama

> [!NOTE]
> Pilin sıfırlanabilir olması için en az yüzde 40 ücrete ihtiyacı vardır.

HoloLens'iniz hala sorun yaşıyorsa fabrika durumuna sıfırlamayı deneyin. Bu adım, windows Holographic yazılımının yüklü olduğu sürümü tutar ve diğer her şeyi fabrika ayarlarına döndürür.

>[!WARNING]
> Cihazınızı sıfırlarsanız TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir. Sıfırlama yalnızca Windows Holographic'in en son yüklü sürümünü yükleyecek. Tüm başlatma adımlarını (ayarlama, Wi-Fi'a bağlanma, bir kullanıcı hesabı oluşturma, uygulamaları indirme vb.) tekrarlamanız gerekir.

1. Ayarlar uygulamasını açın ve Kurtarmayı **Güncelleştir'i**  >  **seçin.**
1. Cihazı **sıfırla seçeneğini** belirleyin ve onay iletiyi okuyun.
1. Sıfırlamayı onaylayın. Cihaz yeniden başlatılır ve bir dizi dönen dişli ve ilerleme çubuğu görüntülenir.
1. Bu sürecin tamamlanması için yaklaşık 30 dakika bekleyin. Bu bittiğinde, cihaz "ilk önce" deneyimine yeniden başlatılır.

## <a name="reinstall-the-operating-system"></a>İşletim sistemini yeniden yükleme

Yeniden başlatma ve sıfırlama sonrasında cihaz sorun devam ediyorsa, HoloLens işletim sistemini ve üretici yazılımını yeniden yüklemek için bilgisayarınızda bir kurtarma aracı kullanabilirsiniz.  

HoloLens'in sıfırlama için ihtiyacı olan veriler bir .iso, .wim veya .vhd dosyasına benzer bir Tam Flash Güncelleştirme (FFU) içinde paketlenmiştir. [FFU görüntü dosyası biçimleri hakkında bilgi edinmek için.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows Cihaz Kurtarma Aracı'nı kullanarak HoloLens'inize (1. nesil) yeni bir işletim sistemi yükleyebilirsiniz. Bu aracı kullanmadan önce HoloLens'inizi yeniden başlatmanın veya sıfırlamanın sorunu düzeltup düzeltmesine bakın.

Kurtarma işlemi biraz zaman alır. Bu bittiğinde, Windows Holographic yazılımının en son sürümü yüklenir.

Aracı kullanmak için en az 4 GB boş Windows 10 veya sonraki bir bilgisayarda çalışmanız gerekir. Bu aracı bir sanal makinede çalıştıraabilirsiniz.

### <a name="recover-your-hololens"></a>HoloLens'inizi kurtarma

1. [Bilgisayarınıza Windows Cihaz Kurtarma Aracı'nı](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) indirin ve yükleyin.
1. HoloLens'iniz ile birlikte gelen Micro USB kablosunu kullanarak HoloLens'i (1. nesil) bilgisayarınıza bağlayın.
1. Windows Cihaz Kurtarma Aracı'nı açın ve yönergeleri izleyin.

HoloLens (1. nesil) otomatik olarak algılanmazsa Cihazım **algılanmadı seçeneğini seçin.** Ardından yönergeleri izleyerek cihazı kurtarma moduna alın.

### <a name="manual-flashing-mode"></a>El ile flashing modu

Cihazınız algılanmazsa, cihazı yanıp sönme moduna koymak için şu adımları izleyin:

1. Cihazı herhangi bir güç kaynağından çıkarın.
1. Cihaz açıksa, tamamen **kapatana** kadar güç düğmesini basılı tutun.
2. Birimi **yukarı doğru** tutun ve güç düğmesine kısa **bir süre** dokunun. Cihazın başlaması ve yalnızca ortadaki LED'i görüntülemesi gerekir.
3. Cihazı bilgisayarınıza takın.
4. Windows Cihaz Kurtarma Aracı'nı açın.
5. Cihazım **algılanmadı'yi ve ardından** **HoloLens'i seçin.** 
6. Cihazınızı kurtarmak için yönergeleri izleyin.
