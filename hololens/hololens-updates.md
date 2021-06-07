---
title: HoloLens güncelleştirmelerini yönetme
description: Yöneticilerinizin HoloLens cihaz güncelleştirmelerini yönetmek için mobil cihaz yönetimini nasıl kullanabileceğini öğrenin.
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
ms.openlocfilehash: 6c9d1551b2a3348a6ff9962180c2d5552eb100f1
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380217"
---
# <a name="manage-hololens-updates"></a>HoloLens güncelleştirmelerini yönetme

HoloLens, Windows Update cihazlarla aynı şekilde Windows 10 kullanır. Bir güncelleştirme kullanılabilir olduğunda, cihazınız bir sonraki takıp İnternet'e bağlandığında otomatik olarak indirilir ve yüklenir. Bu makalede, bir kuruluş veya diğer yönetilen ortamda güncelleştirmelerin nasıl yönetil olduğu açıklanmıştır. Tek tek HoloLens cihazlarına güncelleştirmeleri yönetme hakkında bilgi için bkz. [HoloLens'i güncelleştirme.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Güncelleştirmeleri otomatik olarak yönetme

### <a name="managing-updates-by-using-windows-update-for-business"></a>Güncelleştirmeleri İş İçin Windows Update

Windows Holographic for Business, [güncelleştirmeleri İş İçin Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) için İş İçin Windows Update kullanabilir. Tüm HoloLens 2 cihazları Windows Holographic for Business. 10.0.18362.1042 veya sonraki bir derlemeyi Windows Holographic for Business emin olun. HoloLens (1. nesil) cihazlarınız varsa, güncelleştirmelerini yönetmek [için bunları Windows Holographic for Business](hololens1-upgrade-enterprise.md) cihazlara yükseltmeniz gerekir.

İş İçin Windows Update HoloLens cihazlarını doğrudan Windows Update bağlar. Bu İş İçin Windows Update kullanarak, güncelleştirme işleminin hangi cihazların hangi güncelleştirmeleri hangi zamanda alalı olduğunu birçok &mdash; yönüyle kontrol edin. Örneğin, güncelleştirmeleri test etmek için cihazların bir alt kümesine ve ardından kalan cihazlara güncelleştirmeleri dışarı çıkarabilirsiniz. Veya farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

> [!NOTE]  
> HoloLens cihazlarında özellik güncelleştirmelerini (yılda iki kez yayınlandı) ve kalite güncelleştirmelerini (kritik güvenlik güncelleştirmeleri de dahil olmak üzere aylık veya gerekli şekilde yayınlandı) otomatik olarak yönetebilirsiniz. Güncelleştirme türleri hakkında daha fazla bilgi için bkz. İş İçin Windows Update tarafından [yönetilen güncelleştirme türleri.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

Mobil İş İçin Windows Update (MDM) çözümünde ilkeler kullanarak HoloLens için Cihaz Yönetimi ayarlarını Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>İş İçin Windows Update kullanarak Microsoft Intune

Intune'İş İçin Windows Update yapılandırma hakkında ayrıntılı bir tartışma için bkz. [Intune'da Windows 10 güncelleştirmelerini yönetme.](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure) HoloLens'in desteklediği belirli Intune işlevleri hakkında daha fazla bilgi için bkz. [HoloLens'in desteklediği Intune güncelleştirme yönetimi işlevleri.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Intune, güncelleştirmeleri yönetmek için iki ilke türü sağlar: *Windows 10 halkası* ve *Windows 10 özelliği güncelleştirmesi.* Bu Windows 10 güncelleştirme ilkesi türü şu anda genel önizlemededir ve HoloLens için desteklenmmektedir.
>  
> HoloLens 2 Windows 10 yönetmek için güncelleştirme halkası ilkelerini kullanabilirsiniz.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 veya HoloLens için güncelleştirme ilkelerini yapılandırma (1. nesil)

Bu bölümde HoloLens 2 veya HoloLens (1. nesil) güncelleştirmelerini yönetmek için kullanabileceğiniz ilkeler açıkmektedir. HoloLens 2'nin işlevselliği hakkında daha fazla bilgi için bkz. [HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2)için güncelleştirme çıkışlarını planlama ve yapılandırma.

[İlke CSP - Güncelleştirme,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) ilkeyi yapılandıran İş İçin Windows Update.

> [!NOTE]  
> HoloLens'in belirli sürümleri tarafından desteklenen belirli ilke yapılandırma hizmeti sağlayıcılarının (CSP) listesi için bkz. HoloLens cihazları tarafından desteklenen [İlke CSP'leri.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Güncelleştirmeler için otomatik denetimleri yapılandırma

Güncelleştirmeleri tarama, indirme ve yükleme gibi otomatik güncelleştirme davranışını yönetmek için **Update/AllowAutoUpdate** ilkesi kullanabilirsiniz. Bu ilkenin kullanılabilir ayarları hakkında daha fazla bilgi için bkz. [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Bu Microsoft Intune, bu ilkeyi **değiştirmek için Otomatik Güncelleştirme** Davranışı'nın kullanabilirsiniz. Daha fazla bilgi için [bkz. Intune'Windows 10 güncelleştirmelerini yönetme.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Güncelleştirme zamanlaması yapılandırma

Güncelleştirmelerin nasıl ve ne zaman uygulanıyor olduğunu yapılandırmak için aşağıdaki ilkeleri kullanın:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Değerler: **0**–**7** (0 = her gün, 1 = Pazar, 7 = Cumartesi)
  - Varsayılan değer: **0** (her gün)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Değerler: 0–23 (0 = gece yarısı, 23 = 11 PM)
  - Varsayılan değer: 15:00

#### <a name="configure-active-hours"></a>Etkin saatleri yapılandırma
Windows [Holographic sürüm 20H2'den](hololens-release-notes.md#windows-holographic-version-20h2) başlayarak, bir IT Yöneticisi HoloLens 2 cihazları için etkin saat aralığını belirtebilirsiniz.

Etkin saatler, cihazın kullanımda olmasını beklediğiniz zamanı gösterir. Güncelleştirmeden sonra otomatik yeniden başlatmalar etkin saatlerin dışında gerçekleşir. Belirtilen aralık, etkin saat başlangıç zamanından itibaren sayılır. MDM ile etkin saatleri yapılandırma konusunda [açıklandığı gibi MDM'i kullanabilirsiniz.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM, etkin saatleri yapılandırmak için İlke CSP'sinde Update/ActiveHoursStart ve Update/ActiveHoursEnd ve Update/ActiveHoursMaxRange ayarlarını kullanır.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) - Bu değer bitiş saati ayarlar. Başlangıç zamanından itibaren en fazla 12 saat olur.
    -   Desteklenen değerler 0-23'tir; burada 0 12 am, 1 ise 1 am vb. olur.
    -   Varsayılan değer 17'dir (17:00).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - Bu değer başlangıç zamanından itibaren en fazla etkin saat sayısını ayarlar.
    -   Desteklenen değerler 8-18'tir.
    -   Varsayılan değer 18 'tir (saat).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - Bu değer başlangıç saati ayarlar. Bitiş zamanından itibaren en fazla 12 saat olur.
    -   Desteklenen değerler 0-23'tir; burada 0 12 am, 1 ise 1 am vb. olur.
    -   Varsayılan değer 8 'tir (8 AM).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Yalnızca sürüm 1607 Windows 10 cihazlar için

Aşağıdaki güncelleştirme ilkelerini kullanarak cihazları windows update service (WSUS) yerine Windows Server Update Service'den (WSUS) güncelleştirmeleri Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2 için güncelleştirmeleri planlama ve yapılandırma

HoloLens 2, HoloLens'in (1. nesil) desteklediğinden daha fazla güncelleştirme otomasyonu özelliği destekler. Bu durum özellikle Microsoft Intune İş İçin Windows Update doğrudur. Bu özellikler, güncelleştirmeleri planlamanızı ve uygulamanızı kolaylaştırır.

#### <a name="plan-the-update-strategy"></a>Güncelleştirme stratejisini planlama

İş için Windows Güncelleştirmeleri erteleme ilkelerini destekler. Microsoft bir güncelleştirmeyi yayımladikten sonra, bir erteleme ilkesi kullanarak bu güncelleştirmeyi cihazlara yüklemeden önce ne kadar beklemeniz gerektir olduğunu tanımlayabilirsiniz. Cihaz alt kümelerinizi (güncelleştirme halkaları olarak da *bilinir)* farklı erteleme ilkeleriyle bağdarak, bir güncelleştirme alma stratejisini kuruluş için koordine edin.

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

Bir kullanıcının MDM 'ye erişimi yoksa [, Windows holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki sürümlerini oluşturan bir HoloLens 2 cihazında güncelleştirmeleri tek başına 35 güne kadar duraklatabilirsiniz. **Ayarlar-> güncelleştirme & güvenlik-> gelişmiş seçenekler** ' e giderek bu ayara ulaşabilir ve güncelleştirmeleri **duraklatmak** için aşağı kaydırın ve güncelleştirmeleri duraklatmaya kadar olan tarihi seçin. Bir Kullanıcı duraklatma sınırına ulaştığında, yeniden duraklatılamadığından cihazın yeni güncelleştirmeler alması gerekir. 

[Windows holographic, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2)ile başlayarak, bu güncelleştirme duraklatma Işlevi, Hololens 2 cihazları için yönetilebilir. 
- [Güncelleştirme/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (varsayılan) – etkin
    - 1 – devre dışı

#### <a name="intune-update-management-functions-that-hololens-supports"></a>HoloLens 'in desteklediği Intune güncelleştirme yönetimi işlevleri

HoloLens güncelleştirmelerini yönetmek için aşağıdaki Intune güncelleştirme yönetim işlevlerini kullanabilirsiniz.

- **Oluştur** ve **ata**: Bu işlevler, güncelleştirme halkaları listesine bir Windows 10 güncelleştirme halkası ekler. Daha fazla bilgi için bkz. [güncelleştirme halkaları oluşturma ve atama](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Duraklat**: bir özellik veya kalite güncelleştirmesi dağıtırken sorunla karşılaşırsanız, güncelleştirme 35 gün (belirtilen tarihten başlayarak) için güncelleştirmeyi duraklatabilirsiniz. Bu duraklatma, sorunu çözene veya azaltana kadar diğer cihazların güncelleştirmeyi yüklemesini önler. Bir özellik güncelleştirmesini duraklatmanız durumunda kalite güncelleştirmeleri hala cihazlara sunulmakta olduğundan emin olmak için cihazlara sunulur. Bir güncelleştirme türü duraklatıldığında, bu halkaya ilişkin genel bakış bölmesi, bu güncelleştirme türünün devam edebilmesi için kaç gün kaldığını gösterir. Belirtilen süre geçtikten sonra duraklatma otomatik olarak sona erer ve güncelleştirme işlemi devam eder.

  Güncelleştirme halkası duraklatıldığında, aşağıdaki seçeneklerden birini belirleyebilirsiniz:

  - **Uzat**: 35 gün için bir güncelleştirme türü için duraklatma süresini genişletin.
  - **Özgeçmişi**: bu halkadan etkin işleme yönelik güncelleştirmeleri geri yükleyin. Gerekirse, güncelleştirme halkasını yeniden duraklatabilirsiniz.

  > [!NOTE]  
  > HoloLens 2 cihazlarında güncelleştirme halkaları için **kaldırma** işlemi desteklenmez.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

[Windows holographic, sürüm 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) birden çok HoloLens cihazlarından indirilen bant genişliği tüketimini azaltmak için teslim iyileştirme ayarlarının erken bir önizlemesini etkinleştirdi. Önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri Için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Aşağıdaki ayarlar yönetim yüzeyi kapsamında etkinleştirilmiştir ve [Intune 'dan yapılandırılabilir](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [Dodelaycacheserverfallbackönalanı](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarılar:

- HoloLens desteği yalnızca işletim sistemi güncelleştirmelerine yönelik bu önizlemede sınırlıdır.
- Windows holographic for Business yalnızca bir [Microsoft bağlı önbellek uç NOKTASıNDAN](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)http indirme modlarını ve İndirmeleri destekler; Şu anda HoloLens cihazlarda eşler arası indirme modları ve Grup atamaları desteklenmez.
- HoloLens, Windows Server Update Services uç noktaları için dağıtımı veya teslim iyileştirmeyi desteklemez.
- Sorun giderme, bağlı önbellek sunucusunda tanılamayı veya **Ayarlar**  >  **güncelleştirme & güvenlik**  >   **sorun giderme**  >   **Windows Update** ile HoloLens üzerinde bir izleme toplamayı gerektirir.

## <a name="manually-check-for-updates"></a>Güncelleştirmeleri el ile denetle

HoloLens düzenli olarak sistem güncelleştirmelerini denetetse de, el ile denetlemek istediğiniz durumlar olabilir.

Güncelleştirmeleri el ile denetlemek için **Ayarlar**  >  **güncelleştirme &**  >  **güncelleştirmeler için güvenlik denetimi**' ne gidin. Ayarlar uygulaması cihazınızın güncel olduğunu gösteriyorsa, şu anda kullanılabilir olan tüm güncelleştirmeler vardır.

## <a name="manually-roll-back-an-update"></a>Bir güncelleştirmeyi el ile geri alma

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek isteyebilirsiniz. Bunu yapma süreci, HoloLens 2 veya HoloLens (1. gen) kullanıp kullanmayacağınızı bağlıdır.

### <a name="revert-to-a-previous-version-hololens-2"></a>Önceki bir sürüme geri dön (HoloLens 2)

HoloLens 'nizi önceki sürüme sıfırlamak için [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 'nı kullanarak güncelleştirmeleri geri alabilir ve önceki bir HoloLens 2 sürümüne dönebilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

HoloLens 2 ' nin önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarınızın olmadığından emin olun.
1. Bilgisayarınızda, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) ' nı Microsoft Store indirin.
1. [En son HoloLens 2 sürümünü](https://aka.ms/hololens2download)indirin.
1. Bu indirmeler bittikten sonra, **Dosya Gezgini**  >  **İndirmeleri**' ni açın, indirdiğiniz sıkıştırılmış (.zip) klasöre sağ tıklayın ve ardından   >   dosyayı genişletmek için Tümünü Ayıkla Ayıkla ' yı seçin.
1. HoloLens cihazınızı bilgisayarınıza bağlamak için bir USB-A USB-C kablosu kullanın. HoloLens 'nizi bağlamak için başka kablolar kullanıyor olsanız bile, bu tür bir kablo en iyi şekilde çalışmaktadır.
1. Gelişmiş kurtarma Yardımcısı, HoloLens cihazınızı otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi**' ni seçin ve ardından daha önce genişletmiş olduğunuz klasörü açın.
1. Yükleme (. FFU) dosyasını seçin.
1. **Yazılımı yüklensin**' i seçin ve ardından yönergeleri izleyin.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Önceki bir sürüme geri dön (HoloLens (1. Genel))

HoloLens 'nizi önceki sürüme sıfırlamak için [Windows cihaz kurtarma aracı 'nı (WDRT)](https://support.microsoft.com/help/12379) kullanarak güncelleştirmeleri geri alabilir ve önceki bir HoloLens (1. gen) sürümüne dönebilirsiniz.

> [!NOTE]
> Önceki bir HoloLens sürümüne geri dönmek kişisel dosyalarınızı ve ayarlarını siler.

HoloLens 'in önceki bir sürümüne (1. gen) dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefonlarınızın veya Windows cihazlarının olmadığından emin olun.
1. Bilgisayarınızda, [Windows cihaz kurtarma aracı 'nı (WDRT)](https://support.microsoft.com/help/12379)indirin.
1. [HoloLens yıldönümü güncelleştirme kurtarma paketini](https://aka.ms/hololensrecovery)indirin.
1. İndirmeler bittikten sonra, **Dosya Gezgini**  >  **İndirmeleri**' ni açın, indirdiğiniz sıkıştırılmış (.zip) klasöre sağ tıklayın ve ardından   >  dosyayı genişletmek için tüm **ayıklamayı** Ayıkla ' yı seçin.
1. HoloLens cihazınızı bilgisayarınıza bağlamak için HoloLens cihazlarınızla birlikte sunulan mikro USB kablosunu kullanın. HoloLens Cihazınızı bağlamak için başka kablolar kullanıyor olsanız bile, bu en iyi şekilde geçerlidir.
1. WDRT, HoloLens cihazınızı otomatik olarak algılar. **Microsoft HoloLens** kutucuğunu seçin.
1. Sonraki ekranda, **el ile paket seçimi**' ni seçin ve ardından daha önce genişletmiş olduğunuz klasörü açın.
1. Yükleme (. FFU) dosyasını seçin.
1. **Yazılımı yüklensin**' i seçin ve ardından yönergeleri izleyin.

**WDRT cihazınızı algılamazsa**

WDRT, HoloLens cihazınızı algılamazsa, bilgisayarınızı yeniden başlatmayı deneyin. Bu işe yaramazsa **cihazımın algılanmadığını** seçin, **Microsoft HoloLens**' i seçin ve ardından yönergeleri izleyin.

## <a name="related-articles"></a>İlgili makaleler:

- [HoloLens 2 sürüm notları](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Iş için Windows Update nedir?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Windows 10 güncelleştirmeleri için kanallara bakım yapmak üzere cihaz atama](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune’da Windows 10 yazılım güncelleştirmelerini yönetme](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
