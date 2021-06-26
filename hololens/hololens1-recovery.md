---
title: HoloLens 1 ' i yeniden başlatın, sıfırlayın veya kurtarın
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Windows cihaz kurtarma aracı 'nı kullanarak bir görüntüyü HoloLens 1 gen 'a yakıp söndür.
keywords: Nasıl yapılır, yeniden başlatma, sıfırlama, kurtarma, sabit sıfırlama, geçici sıfırlama, güç çevrimi, HoloLens, kapatma, WDRT, Windows cihaz kurtarma aracı
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
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923525"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>HoloLens 'i yeniden başlatma, sıfırlama veya kurtarma (1. Genel)

HoloLens ile ilgili sorunlar yaşıyorsanız, bir yeniden başlatma veya sıfırlama ya da cihazı cihaz kurtarma kullanarak yeniden faturalandırmayı denemek isteyebilirsiniz. Bu makale, önerilen kurtarma adımlarında sırasıyla size rehberlik eder.

HoloLens 2 ' yi kurtarmak istiyorsanız, bu işlem farklı olduğundan [HoloLens 2](hololens-recovery.md)' yi kurtarma bölümüne bakın.

> [!NOTE]
> Bu makale, HoloLens cihazına ve yazılımına odaklanır. Hologramlar doğru görünmüyorsa, hologram kalitesini artıran faktörler hakkında bilgi için bkz. **[HoloLens ortam konuları](hololens-environment-considerations.md)** .

## <a name="restart"></a>Yeniden başlat

### <a name="do-a-safe-restart-by-using-cortana"></a>Cortana 'Yı kullanarak güvenli bir yeniden başlatma

HoloLens 'i yeniden başlatmanın en güvenli yolu, genellikle HoloLens ile bir sorunla karşılaştığınızda deneyebileceğiniz ilk şey olan Cortana 'yı kullanmaktır.

> [!NOTE] 
> Cortana tüm cihazlarda kullanılabilir değildir.
> - Cortana, tüm HoloLens (1 gen) cihazlarda kullanılabilir. 
> - Cortana, Windows Holograpic, sürüm 2004 güncelleştirmesinden önceki derlemelerde bulunan HoloLens 2 cihazlarında kullanılabilir.

1. HoloLens 'nizi açın.
1. Bir kullanıcının oturum açtığından ve cihazın kilidini açmak için bir parola beklemediğinden emin olun.
2. "Hey Cortana, yeniden başlatma" veya "Hey Cortana, yeniden başlatma" deyin.
3. Cortana yanıt verir ve onaylamanız istenir. Sorudan sonra bir sesin çalmasını bekleyin ve sonra "Evet" deyin. Cihaz yeniden başlatılır.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Güvenli yeniden başlatma yapmak için güç düğmesini kullanın

Cihazınızı hala yeniden başlatmazsanız, **Güç** düğmesini kullanarak yeniden başlatmayı deneyin:

1. 5 saniye boyunca **Güç** düğmesine basın ve basılı tutun. 1 saniye sonra, beş LED 'in hepsi, bir tane, sağdan sola doğru bir şekilde çalışır. 5 saniye sonra, başarılı kapatmayı belirten tüm LED 'ler kapalı olur.
      
   > [!IMPORTANT]
   > Tüm LED 'ler devre dışı bırakıldıktan hemen sonra düğmeye basmayı durdurun.
1. Kapatılma işleminin tamamlanmasını 1 dakika bekleyin. Ekran kapatıldıktan sonra bile, kapatma devam ediyor olabilir.
2. 1 saniye boyunca **Güç** düğmesine basarak ve basılı tutarak cihazı tekrar açın.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Windows cihaz portalı 'nı kullanarak güvenli bir yeniden başlatma

> [!NOTE]
> Bu işlem için, HoloLens 'in bir geliştirici cihazı olarak yapılandırılması gerekir. [Windows cihaz portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)'nda daha fazla bilgi edinin.

Önceki yordam işe yaramazsa, [Windows cihaz portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)'nı kullanarak cihazı yeniden başlatmayı deneyin. Sağ üst köşede, cihazı yeniden başlatma veya kapatma seçeneğini bulun.

### <a name="do-an-unsafe-forced-restart"></a>Güvenli olmayan Zorlanmış yeniden başlatma

Önceki yöntemler HoloLens 'nizi yeniden başlatmadıysa, yeniden başlatmaya zorlayın. Bu yöntem, pili kaldırma ve yeniden yükleme ile eşdeğerdir. Cihazınızı bozulmuş bir durumda bırakabileceğinden tehlikeli olabilir. Bu durumda, HoloLens 'nizi Flash yapmanız gerekir.  

> [!WARNING]
> Bu, zararlı olabilecek bir yöntemdir ve yalnızca önceden alıntı yapılan Yöntemler çalışmazsa kullanılmalıdır.

1. En az 10 saniye için **Güç** düğmesine basın ve basılı tutun.
   - Bu, düğmeyi 10 saniyeden uzun süre tutmak kadar sürer.
   - Herhangi bir LED etkinliğini yoksaymak güvenlidir.
1. Düğmeyi bırakın ve 2-3 saniye bekleyin.
1. 1 saniye için **Güç** düğmesine basın ve basılı tutun.
1. Hala sorun yaşıyorsanız, tüm pil göstergeleri silinerek ve ekran hologramlar 'ı görüntülemeyi durdurana kadar, 4 saniye boyunca **Güç** düğmesine basın. 1 dakika bekleyin ve ardından cihazı açmak için **Güç** düğmesine yeniden basın.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Önceki bir sürüme geri dön-HoloLens (1. Genel)

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne geri dönmek isteyebilirsiniz. Bunu, Windows cihaz kurtarma aracı 'nı kullanarak, HoloLens 'nizi önceki sürüme sıfırlamak için yapabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

HoloLens 1 ' in önceki bir sürümüne geri dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarının olmadığından emin olun.
1. Bilgisayarınızda, [Windows cihaz kurtarma aracı 'nı (WDRT)](https://support.microsoft.com/help/12379)indirin.
1. [HoloLens yıldönümü güncelleştirme kurtarma paketini](https://aka.ms/hololensrecovery)indirin.
1. İndirmeler tamamlandığında, **Dosya Gezgini**  >  **İndirmeleri**' ni açın. İndirdiğiniz zip klasörüne sağ tıklayın ve sıkıştırmayı açmak için **Tümünü** Ayıkla ' yı seçin  >   .
1. HoloLens 'nizi, ile birlikte gelen mikro USB kablosunu kullanarak bilgisayarınıza bağlayın. (HoloLens 'nizi bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.)
1. WDRT, HoloLens 'nizi otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi** ' ni seçin ve 4. adımda sıkıştırunın bulunduğu klasörde bulunan yükleme dosyasını seçin. (. FFU uzantılı bir dosyayı arayın.)
1. **Yazılım yüklemesi**' ni seçin ve yönergeleri izleyin.

> [!NOTE]
> WDRT, HoloLens 'nizi algılamazsa bilgisayarınızı yeniden başlatmayı deneyin. Bu işe yaramazsa **cihazımın algılanmadığını** seçin, **Microsoft HoloLens**' i seçin ve ardından yönergeleri izleyin.

## <a name="reset-to-factory-settings"></a>Fabrika ayarlarına sıfırla

> [!NOTE]
> Pilin sıfırlanması için en az %40 oranında bir ücret gereklidir.

HoloLens 'niz hala bir sorun içeriyorsa, fabrika durumuna sıfırlamayı deneyin. Bu adım, üzerine yüklenmiş Windows holographic yazılımının sürümünü tutar ve fabrika ayarlarına diğer her şeyi döndürür.

>[!WARNING]
> Cihazınızı sıfırlarsanız, TPM sıfırlama bilgileri de dahil olmak üzere tüm kişisel verileriniz, uygulamalarınız ve ayarlarınız silinir. Sıfırlama yalnızca en son yüklenen Windows holographic sürümünü yükler. Tüm başlatma adımlarını (ayarlamak, Wi-Fi ' y e bağlanmanız, bir kullanıcı hesabı oluşturmak, uygulamaları indirmek vb.) yeniden yapmanız gerekir.

1. Ayarlar uygulamasını açın ve ardından kurtarmayı **Güncelleştir**' i seçin  >  .
1. **Cihazı Sıfırla** seçeneğini belirleyin ve onay iletisini okuyun.
1. Sıfırlamayı onaylayın. Cihaz yeniden başlatılır ve bir dizi dönen Gears ve ilerleme çubuğu görüntülenir.
1. Bu işlemin tamamlanabilmesi için yaklaşık 30 dakika bekleyin. İşlem tamamlandığında, cihaz "hazır olmayan" deneyimde yeniden başlatılır.

## <a name="reinstall-the-operating-system"></a>İşletim sistemini yeniden yükleme

Yeniden başlatma ve sıfırlama sonrasında cihaz sorun yaşamaya devam ediyorsa, HoloLens işletim sistemini ve üretici yazılımını yeniden yüklemek için bilgisayarınızda bir kurtarma aracı kullanabilirsiniz.  

HoloLens 'in sıfırlama için ihtiyaç duyacağı veriler, bir. iso,. wim veya. vhd dosyasına benzer bir tam Flash Güncelleştirmesi (FFU) ile paketlenmiştir. [FFU görüntü dosyası biçimleri hakkında bilgi edinin.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Windows cihaz kurtarma aracı 'nı kullanarak, HoloLens (1. gen) uygulamanıza yeni bir işletim sistemi yükleyebilirsiniz. Bu aracı kullanmadan önce, HoloLens 'in yeniden başlatılması veya sıfırlanması sorunu düzeltir bölümüne bakın.

Kurtarma işlemi biraz zaman alabilir. İşlem tamamlandığında, Windows holographic yazılımının en son sürümü yüklenir.

Aracı kullanmak için, en az 4 GB boş depolama alanı ile Windows 10 veya sonraki bir sürümünü çalıştıran bir bilgisayara ihtiyacınız vardır. Bu aracı bir sanal makinede çalıştıramazsınız.

### <a name="recover-your-hololens"></a>HoloLens 'nizi kurtarın

1. [Windows cihaz kurtarma aracı](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 'nı bilgisayarınıza indirip yükleyin.
1. HoloLens 'nizle birlikte gelen mikro USB kablosunu kullanarak HoloLens 'i (1. gen) bilgisayarınıza bağlayın.
1. Windows cihaz kurtarma aracı 'nı açın ve yönergeleri izleyin.

HoloLens (1. gen) otomatik olarak algılanmazsa **cihazımın algılanmadığını** seçin. Ardından, cihazı kurtarma moduna almak için yönergeleri izleyin.

### <a name="manual-flashing-mode"></a>Manuel yanıp sönen mod

Cihazınız algılanmadıysa, bu adımları yanıp sönen moda koymak için aşağıdaki adımları izleyin:

1. Cihazı herhangi bir güç kaynağından çıkarın.
1. Cihaz açık ise, tamamen kapanana kadar **Güç** düğmesini basılı tutun.
2. Birimi **yukarı doğru** tutun ve güç düğmesine kısa bir **süre** dokunun. Cihazın başlaması ve yalnızca ortadaki LED'i görüntülemesi gerekir.
3. Cihazı bilgisayarınıza takın.
4. Windows Cihaz Kurtarma Aracı'nı açın.
5. Cihazım **algılanmadı'yi ve ardından** **HoloLens'i seçin.** 
6. Cihazınızı kurtarmak için yönergeleri izleyin.
