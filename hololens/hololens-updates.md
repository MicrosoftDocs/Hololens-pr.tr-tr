---
title: Güncelleştirmeleri HoloLens yönetme
description: Yöneticilerinizin mobil cihaz yönetimini kullanarak cihazlarınıza güncelleştirmeleri yönetmeyi HoloLens öğrenin.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 5ec26c64a971b8bfc9f8d1f9044e2e651a218816
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640007"
---
# <a name="manage-hololens-updates"></a>Güncelleştirmeleri HoloLens yönetme

HoloLens, Windows Güncelleştirme'sini diğer Windows 10 şekilde kullanır. Bir güncelleştirme kullanılabilir olduğunda, cihazınız bir sonraki takıp İnternet'e bağlandığında otomatik olarak indirilir ve yüklenir. Bu makalede, bir kuruluş veya diğer yönetilen ortamda güncelleştirmelerin nasıl yönetil olduğu açıklanmıştır. Tek tek cihazlara güncelleştirmeleri yönetme hakkında bilgi HoloLens bkz. [Güncelleştirme HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Güncelleştirmeleri otomatik olarak yönetme

### <a name="managing-updates-by-using-windows-update-for-business"></a>İş Için Windows Güncelleştirmesini kullanarak güncelleştirmeleri yönetme

Windows Holographic for Business güncelleştirmeleri [yönetmek Windows için İş Için Güncelleştirme'sini](/windows/deployment/update/waas-manage-updates-wufb) kullanabilirsiniz. Tüm HoloLens 2 cihaz, Windows Holographic for Business. 10.0.18362.1042 veya sonraki bir derlemeyi Windows Holographic for Business emin olun. HoloLens (1. nesil) cihazlarınız varsa, güncelleştirmelerini [yönetmek için Windows Holographic for Business](hololens1-upgrade-enterprise.md) cihazlara yükseltmeniz gerekir.

Windows İş için Güncelleştirme, HoloLens doğrudan Windows Update hizmetine bağlar. İş Windows Güncelleştirmesini kullanarak, güncelleştirme işleminin hangi cihazların hangi güncelleştirmeleri hangi zamanda alalı olduğunu birçok &mdash; yönüyle kontrol edin. Örneğin, güncelleştirmeleri test etmek için cihazların bir alt kümesine ve ardından kalan cihazlara güncelleştirmeleri dışarı çıkarabilirsiniz. Veya farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

> [!NOTE]  
> Diğer HoloLens, özellik güncelleştirmelerini (yılda iki kez yayınlandı) ve kalite güncelleştirmelerini (kritik güvenlik güncelleştirmeleri de dahil olmak üzere aylık veya gerektiğinde yayınlandı) otomatik olarak yönetebilirsiniz. Güncelleştirme türleri hakkında daha fazla bilgi için [bkz. İş Için Güncelleştirme Windows tarafından yönetilen güncelleştirme türleri.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

HoloLens Windows (MDM) gibi bir Mobil Cihaz Yönetimi (MDM) çözümünde ilkeleri kullanarak Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>İş Windows Güncelleştirmesi'nin yönetimi için Microsoft Intune

İş için Güncelleştirme'yi yapılandırmak üzere Intune'Windows ayrıntılı bir tartışma için bkz. [Intune'da Windows 10 güncelleştirmelerini yönetme.](/intune/protect/windows-update-for-business-configure) Desteklemektedir belirli Intune işlevselliği hakkında daha fazla HoloLens için bkz. [Intune](#intune-update-management-functions-that-hololens-supports)güncelleştirme yönetimi işlevleri HoloLens destekler.

> [!IMPORTANT]  
> Intune, güncelleştirmeleri yönetmek için iki ilke türü sağlar: *Windows 10 halkası* ve *Windows 10 özelliği güncelleştirmesi.* Bu Windows 10 güncelleştirme ilkesi türü şu anda genel önizlemededir ve bu özellik güncelleştirme HoloLens.
>  
> Güncelleştirme halkası Windows 10 2 güncelleştirmesini yönetmek HoloLens kullanabilirsiniz.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 veya HoloLens (1. nesil) için güncelleştirme ilkelerini yapılandırma

Bu bölümde, 2. nesil veya HoloLens (1. nesil) güncelleştirmeleri yönetmek için HoloLens ilkeleri açıkmektedir. HoloLens 2 için kullanılabilen işlevler hakkında daha fazla bilgi için bkz. HoloLens 2 için güncelleştirme [HoloLens yapılandırma.](#plan-and-configure-update-rollouts-for-hololens-2)

[İlke CSP - Güncelleştirme,](/windows/client-management/mdm/policy-csp-update) İş için Güncelleştirme'Windows yapılandıran ilkeleri tanımlar.

> [!NOTE]  
> Belirli HoloLens sürümleri tarafından desteklenen belirli ilke yapılandırma hizmeti sağlayıcılarının (CSP) listesi için bkz. HoloLens [tarafından desteklenen İlke CSP'leri.](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Güncelleştirmeler için otomatik denetimleri yapılandırma

Güncelleştirmeleri tarama, indirme ve yükleme gibi otomatik güncelleştirme davranışını yönetmek için **Update/AllowAutoUpdate** ilkesi kullanabilirsiniz. Bu ilkenin kullanılabilir ayarları hakkında daha fazla bilgi için bkz. [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Bu Microsoft Intune, bu ilkeyi **değiştirmek için Otomatik Güncelleştirme** Davranışı'nın kullanabilirsiniz. Daha fazla bilgi için [bkz. Intune'Windows 10 yazılım güncelleştirmelerini yönetme.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Güncelleştirme zamanlaması yapılandırma

Güncelleştirmelerin nasıl ve ne zaman uygulanıyor olduğunu yapılandırmak için aşağıdaki ilkeleri kullanın:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Değerler: **0**–**7** (0 = her gün, 1 = Pazar, 7 = Cumartesi)
  - Varsayılan değer: **0** (her gün)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Değerler: 0–23 (0 = gece yarısı, 23 = 11 PM)
  - Varsayılan değer: 03:00

#### <a name="configure-active-hours"></a>Etkin saatleri yapılandırma
[Holographic Windows sürüm 20H2'den](hololens-release-notes.md#windows-holographic-version-20h2) başlayarak, bir IT Yöneticisi 2 cihaz için HoloLens saat aralığını belirtebilirsiniz.

Etkin saatler, cihazın kullanımda olmasını beklediğiniz zamanı gösterir. Güncelleştirmeden sonra otomatik yeniden başlatmalar etkin saatlerin dışında gerçekleşir. Belirtilen aralık, etkin saat başlangıç zamanından itibaren sayılır. MDM ile etkin saatleri yapılandırma konusunda [açıklandığı gibi MDM'i kullanabilirsiniz.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM, etkin saatleri yapılandırmak için İlke CSP'sinde Update/ActiveHoursStart ve Update/ActiveHoursEnd ve Update/ActiveHoursMaxRange ayarlarını kullanır.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - Bu değer bitiş saati ayarlar. Başlangıç zamanından itibaren en fazla 12 saat sürer.
    -   Desteklenen değerler 0-23'tir; burada 0 12 am, 1 ise 1 am vb. olur.
    -   Varsayılan değer 17'dir (17:00).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - Bu değer başlangıç zamanından itibaren en fazla etkin saat sayısını ayarlar.
    -   Desteklenen değerler 8-18'tir.
    -   Varsayılan değer 18'tir (saat).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - Bu değer başlangıç saati ayarlar. Bitiş zamanından itibaren en fazla 12 saat sürer.
    -   Desteklenen değerler 0-23'tir; burada 0 12 am, 1 ise 1 am vb. olur.
    -   Varsayılan değer 8 'tir (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Yalnızca sürüm 1607 Windows 10 cihazlar için

Cihazları güncelleştirmeleri Güncelleştirme'den değil Windows Server Update Service'den (WSUS) almak üzere yapılandırmak için aşağıdaki Windows kullanabilirsiniz:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2 için güncelleştirme HoloLens yapılandırma

HoloLens 2, (1. nesil) HoloLens daha fazla güncelleştirme otomasyonu özelliği destekler. İş için Güncelleştirme ilkelerini yönetmek için Microsoft Intune kullanıyorsanız Windows bu durum doğrudur. Bu özellikler, güncelleştirmeleri planlamanızı ve uygulamanızı kolaylaştırır.

#### <a name="plan-the-update-strategy"></a>Güncelleştirme stratejisini planlama

Windows İş güncelleştirmeleri erteleme ilkelerini destekler. Microsoft bir güncelleştirmeyi yayımladikten sonra, bir erteleme ilkesi kullanarak bu güncelleştirmeyi cihazlara yüklemeden önce ne kadar bekleyeceğinizi tanımlayabilirsiniz. Cihaz alt kümelerinizi (güncelleştirme halkaları olarak da *bilinir)* farklı erteleme ilkeleriyle bağdarak, bir güncelleştirme alma stratejisini kuruluş için koordine edin.

Örneğin, 1.000 cihazı olan ve cihazları beş dalgada güncelleştirmesi gereken bir kuruluş düşünün. Kuruluş, aşağıdaki tabloda gösterildiği gibi beş güncelleştirme halkası oluşturabilir.

|Grup |Cihaz sayısı |Erteleme (gün) |
| ---| :---: | :---: |
|Grp 1 (IT personeli) |5 |0 |
|Grp 2 (erken benimseyenler) |50 |60 |
|Grp 3 (ana 1) |250 |120 |
|Grp 4 (ana 2) |300 |150 |
|Grp 5 (ana 3) |395 |180 |

Zaman içinde kuruluşun tamamı için nasıl bir ilerleme kaydediyoruz?

![Güncelleştirmeleri dağıtmak için zaman çizelgesi](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Güncelleştirme erteleme ilkesi yapılandırma

Erteleme ilkesi, güncelleştirmenin kullanılabilir olduğu tarih ile cihazın güncelleştirmenin sunl olduğu tarih arasındaki gün sayısını belirtir.

Özellik güncelleştirmeleri ve kalite güncelleştirmeleri için farklı ertelemeler yapılandırabilirsiniz. Aşağıdaki tabloda her bir tür için kullanılacak belirli ilkeler ve her biri için en fazla erteleme listelenmektedir.

|Kategori |İlke |Maksimum erteleme |
| --- | --- | --- |
|Özellik güncelleştirmeleri |DeferFeatureUpdatesPeriodInDays |365 gün |
|Kalite güncelleştirmeleri |DeferQualityUpdatesPeriodInDays |30 gün |

#### <a name="pause-updates-via-device"></a>Güncelleştirmeleri cihaz üzerinden Duraklat

bir kullanıcının MDM 'ye erişimi yoksa [, derleme Windows Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki sürümlerde HoloLens 2 cihazında 35 güne kadar güncelleştirmeleri tek tek duraklatabilir. kullanıcılar, **güncelleştirmeleri duraklatmak** için **Ayarlar > güncelleştirme & güvenlik > gelişmiş seçenekler** ' e giderek bu ayara ulaşabilir ve güncelleştirmeleri duraklatmaya devam edecek tarihi seçer. Kullanıcı duraklatma sınırına ulaştığında, yeniden duraklamadan önce cihazın yeni güncelleştirmeler alması gerekir. 

[Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2)' den başlayarak, bu güncelleştirme duraklatma işlevi, HoloLens 2 cihazları için yönetilebilir. 
- [Güncelleştirme/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (varsayılan) – etkin
    - 1 – devre dışı

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens desteklediği ıntune güncelleştirme yönetim işlevleri

HoloLens güncelleştirmelerini yönetmek için aşağıdaki Intune güncelleştirme yönetim işlevlerini kullanabilirsiniz.

- **oluştur** ve **ata**: bu işlevler, güncelleştirme halkaları listesine Windows 10 bir güncelleştirme halkası ekler. Daha fazla bilgi için bkz. [güncelleştirme halkaları oluşturma ve atama](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Duraklat**: bir özellik veya kalite güncelleştirmesi dağıtırken sorunla karşılaşırsanız, güncelleştirme 35 gün (belirtilen tarihten başlayarak) için güncelleştirmeyi duraklatabilirsiniz. Bu duraklatma, sorunu çözene veya azaltana kadar diğer cihazların güncelleştirmeyi yüklemesini önler. Bir özellik güncelleştirmesini duraklatmanız durumunda kalite güncelleştirmeleri hala cihazlara sunulmakta olduğundan emin olmak için cihazlara sunulur. Bir güncelleştirme türü duraklatıldığında, bu halkaya ilişkin genel bakış bölmesi, bu güncelleştirme türünün devam edebilmesi için kaç gün kaldığını gösterir. Belirtilen süre geçtikten sonra duraklatma otomatik olarak sona erer ve güncelleştirme işlemi devam eder.

  Güncelleştirme halkası duraklatıldığında, aşağıdaki seçeneklerden birini belirleyebilirsiniz:

  - **Uzat**: 35 gün için bir güncelleştirme türü için duraklatma süresini genişletin.
  - **Özgeçmişi**: bu halkadan etkin işleme yönelik güncelleştirmeleri geri yükleyin. Gerekirse, güncelleştirme halkasını yeniden duraklatabilirsiniz.

  > [!NOTE]  
  > güncelleştirme halkaları için **kaldırma** işlemi HoloLens 2 cihaz için desteklenmez.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

[Windows Holographic, sürüm 21h1,](hololens-release-notes.md#windows-holographic-version-21h1) birden çok HoloLens cihazdan indirmeleri için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarının erken bir önizlemesini etkinleştirdi. önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri için teslim iyileştirmesi](/windows/deployment/update/waas-delivery-optimization).

Aşağıdaki ayarlar yönetim yüzeyi kapsamında etkinleştirilmiştir ve [Intune 'dan yapılandırılabilir](/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [Dodelaycacheserverfallbackönalanı](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarılar:

- HoloLens desteği, bu önizlemede yalnızca işletim sistemi güncelleştirmeleri için sınırlıdır.
- Windows Holographic for Business yalnızca [Microsoft bağlı önbellek uç noktasından](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)HTTP indirme modlarını ve indirmeleri destekler; şu anda HoloLens cihazlarda eşler arası indirme modları ve grup atamaları desteklenmez.
- HoloLens, Windows Server Update Services uç noktaları için dağıtımı veya teslim iyileştirmeyi desteklemez.
- sorun giderme, bağlı önbellek sunucusunda tanılama gerektirir veya **Ayarlar**  >  **güncelleştirme & güvenlik**  >   **sorun giderme**  >   **Windows Update** aracılığıyla HoloLens HoloLens bir izleme topluyor.

## <a name="manually-check-for-updates"></a>Güncelleştirmeleri el ile denetle

HoloLens düzenli olarak sistem güncelleştirmelerini denetlemekle birlikte, el ile denetlemek istediğiniz durumlar olabilir.

güncelleştirmeleri el ile denetlemek için   >  güncelleştirmeler için Ayarlar **güncelleştirme & güvenlik**  >  **denetimi**' ne gidin. Ayarlar uygulama cihazınızın güncel olduğunu gösteriyorsa, şu anda kullanılabilir olan tüm güncelleştirmeler vardır.

## <a name="manually-roll-back-an-update"></a>Bir güncelleştirmeyi el ile geri alma

bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek isteyebilirsiniz. bunu yapma işlemi, HoloLens 2 veya HoloLens (1. gen) kullanıp kullanmayacağınızı bağlıdır.

### <a name="revert-to-a-previous-version-hololens-2"></a>önceki bir sürüme geri dön (HoloLens 2)

HoloLens önceki sürüme sıfırlamak için [gelişmiş kurtarma yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 'nı kullanarak güncelleştirmeleri geri alabilir ve önceki bir HoloLens 2 sürümüne döndürebilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

HoloLens 2 ' nin önceki bir sürümüne dönmek için şu adımları izleyin:

1. bilgisayarınıza takılı telefonlarınızın veya Windows cihazların olmadığından emin olun.
1. Bilgisayarınızda, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ' nı Microsoft Store indirin.
1. [en son HoloLens 2 sürümünü](https://aka.ms/hololens2download)indirin.
1. Bu indirmeler bittikten sonra, **Dosya Gezgini**  >  **İndirmeleri**' ni açın, indirdiğiniz sıkıştırılmış (.zip) klasöre sağ tıklayın ve ardından   >   dosyayı genişletmek için Tümünü Ayıkla Ayıkla ' yı seçin.
1. HoloLens cihazınızı bilgisayarınıza bağlamak için bir usb-a usb-C kablosu kullanın. HoloLens bağlamak için başka kablolar kullanıyor olsanız bile, bu tür bir kablo en iyi şekilde çalışmaktadır.
1. gelişmiş kurtarma yardımcısı HoloLens cihazınızı otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi**' ni seçin ve ardından daha önce genişletmiş olduğunuz klasörü açın.
1. Yükleme (. FFU) dosyasını seçin.
1. **Yazılımı yüklensin**' i seçin ve ardından yönergeleri izleyin.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>önceki bir sürüme geri dön (HoloLens (1. genel))

HoloLens önceki sürüme sıfırlamak için [Windows cihaz kurtarma aracı 'nı (wdrt)](https://support.microsoft.com/help/12379) kullanarak güncelleştirmeleri geri alabilir ve önceki bir HoloLens (1. gen) sürümüne dönebilirsiniz.

> [!NOTE]
> önceki bir HoloLens sürümüne geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

önceki bir HoloLens (1. gen) sürümüne geri dönmek için şu adımları izleyin:

1. bilgisayarınıza takılı telefonlarınızın veya Windows cihazların olmadığından emin olun.
1. bilgisayarınızda [Windows cihaz kurtarma aracı 'nı (wdrt)](https://support.microsoft.com/help/12379)indirin.
1. [HoloLens yıldönümü güncelleştirme kurtarma paketini](https://aka.ms/hololensrecovery)indirin.
1. İndirmeler bittikten sonra, **Dosya Gezgini**  >  **İndirmeleri**' ni açın, indirdiğiniz sıkıştırılmış (.zip) klasöre sağ tıklayın ve ardından   >  dosyayı genişletmek için tüm **ayıklamayı** Ayıkla ' yı seçin.
1. HoloLens cihazınızı bilgisayarınıza bağlamak için HoloLens cihazlarınızla birlikte sunulan mikro USB kablosunu kullanın. HoloLens cihazınızı bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.
1. wdrt HoloLens cihazınızı otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi**' ni seçin ve ardından daha önce genişletmiş olduğunuz klasörü açın.
1. Yükleme (. FFU) dosyasını seçin.
1. **Yazılımı yüklensin**' i seçin ve ardından yönergeleri izleyin.

**WDRT cihazınızı algılamazsa**

wdrt HoloLens cihazınızı algılamazsa, bilgisayarınızı yeniden başlatmayı deneyin. bu işe yaramazsa **cihazımın algılanmadığını** seçin, **Microsoft HoloLens**' yi seçin ve ardından yönergeleri izleyin.

## <a name="related-articles"></a>İlgili makaleler:

- [HoloLens 2 sürüm notları](hololens-release-notes.md)
- [iş için Windows Update nedir?](/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 güncelleştirmeleri için kanallara hizmet vermek üzere cihaz atama](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune’da Windows 10 yazılım güncelleştirmelerini yönetme](/mem/intune/protect/windows-update-for-business-configure)
