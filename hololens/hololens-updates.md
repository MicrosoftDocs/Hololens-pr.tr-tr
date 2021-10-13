---
title: Güncelleştirmeleri HoloLens yönetme
description: Yöneticilerinizin mobil cihaz yönetimi kullanarak cihazlarınıza yapılan güncelleştirmeleri nasıl HoloLens öğrenin.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/12/2021
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
ms.openlocfilehash: 854e867238de6c87732970fba75abdc8e1fb2c64
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924341"
---
# <a name="manage-hololens-updates"></a>Güncelleştirmeleri HoloLens yönetme

HoloLens, Windows Güncelleştirme'sini diğer Windows 10 kullanır. Bir güncelleştirme kullanılabilir olduğunda, cihazınız bir sonraki takıp İnternet'e bağlandığında otomatik olarak indirilir ve yüklenir. Bu makalede, bir kuruluş veya diğer yönetilen ortamda güncelleştirmelerin nasıl yönetil olduğu açıklanmıştır. Tek tek cihazlarda güncelleştirmeleri yönetme hakkında bilgi HoloLens bkz. [Güncelleştirme HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Güncelleştirmeleri otomatik olarak yönetme

### <a name="managing-updates-by-using-windows-update-for-business"></a>İş Için Güncelleştirme'Windows kullanarak güncelleştirmeleri yönetme

Windows Holographic for Business güncelleştirmeleri [yönetmek Windows için İş Güncelleştirmesi'ne](/windows/deployment/update/waas-manage-updates-wufb) tıklayın. Tüm HoloLens 2 cihaz, Windows Holographic for Business. 10.0.18362.1042 veya sonraki bir derlemeyi Windows Holographic for Business emin olun. HoloLens (1. nesil) cihazlarınız varsa, güncelleştirmelerini [yönetmek için Windows Holographic for Business](hololens1-upgrade-enterprise.md) cihazlara yükseltmeniz gerekir.

Windows İş için Güncelleştirme, HoloLens cihazları doğrudan Windows Update hizmetine bağlar. İş Windows Güncelleştirmesini kullanarak, güncelleştirme işleminin hangi cihazların hangi güncelleştirmeleri hangi zamanda alalı olduğunu birden &mdash; çok yönüyle kontrol edin. Örneğin, güncelleştirmeleri test etmek için cihazların bir alt kümesine ve ardından kalan cihazlara güncelleştirmeleri dışarı çıkarabilirsiniz. Veya farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

> [!NOTE]  
> Diğer HoloLens, özellik güncelleştirmelerini (yılda iki kez yayınlandı) ve kalite güncelleştirmelerini (kritik güvenlik güncelleştirmeleri de dahil olmak üzere aylık veya gerektiğinde yayınlandı) otomatik olarak yönetebilirsiniz. Güncelleştirme türleri hakkında daha fazla bilgi için [bkz. İş Için Güncelleştirme tarafından Windows güncelleştirme türleri.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

Windows mobil HoloLens (MDM) gibi bir Mobil Cihaz Yönetimi (MDM) çözümünde ilkeleri kullanarak Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>İş Windows Güncelleştirmesi'nin yönetimi için Microsoft Intune

İş için Güncelleştirme'yi yapılandırmak üzere Intune'Windows ayrıntılı bir tartışma için bkz. [Intune'da Windows 10 güncelleştirmelerini yönetme.](/intune/protect/windows-update-for-business-configure) Desteklemektedir belirli Intune işlevselliği hakkında daha fazla HoloLens için bkz. [Intune](#intune-update-management-functions-that-hololens-supports)güncelleştirme yönetimi işlevleri HoloLens destekler.

> [!IMPORTANT]  
> Intune, güncelleştirmeleri yönetmek için iki ilke türü sağlar: *Windows 10 halkası ve* *Windows 10 özelliği güncelleştirmesi.* Bu Windows 10 güncelleştirme ilkesi türü şu anda genel önizlemededir ve bu özellik güncelleştirme HoloLens.
>  
> Güncelleştirme halkası Windows 10 2 güncelleştirmesini yönetmek HoloLens kullanabilirsiniz.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 veya HoloLens (1. nesil) için güncelleştirme ilkelerini yapılandırma

Bu bölümde, 2. nesil veya HoloLens (1. nesil) için güncelleştirmeleri HoloLens kullanabileceğiniz ilkeler açıkmektedir. HoloLens 2 için kullanılabilen işlevler hakkında daha fazla bilgi için bkz. HoloLens 2 için güncelleştirme [HoloLens yapılandırma.](#plan-and-configure-update-rollouts-for-hololens-2)

[İlke CSP - Güncelleştirme,](/windows/client-management/mdm/policy-csp-update) İş için Güncelleştirme'Windows ilkeleri tanımlar.

> [!NOTE]  
> Belirli HoloLens sürümleri tarafından desteklenen belirli ilke yapılandırma hizmet sağlayıcılarının (CSP) listesi için bkz. HoloLens [tarafından desteklenen İlke CSP'leri.](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Güncelleştirmeler için otomatik denetimleri yapılandırma

Güncelleştirmeleri tarama, indirme ve yükleme gibi otomatik güncelleştirme davranışını yönetmek için **Update/AllowAutoUpdate** ilkesi kullanabilirsiniz. Bu ilkenin kullanılabilir ayarları hakkında daha fazla bilgi için bkz. [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Bu Microsoft Intune, bu ilkeyi **değiştirmek için Otomatik** Güncelleştirme Davranışı'nın kullanabilirsiniz. Daha fazla bilgi için [bkz. Intune'Windows 10 güncelleştirmelerini yönetme.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Güncelleştirme zamanlaması yapılandırma

Güncelleştirmelerin nasıl ve ne zaman uygulanıyor olduğunu yapılandırmak için aşağıdaki ilkeleri kullanın:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Değerler: **0**–**7** (0 = her gün, 1 = Pazar, 7 = Cumartesi)
  - Varsayılan değer: **0** (her gün)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Değerler: 0–23 (0 = gece yarısı, 23 = 11 PM)
  - Varsayılan değer: 03:00

#### <a name="configure-active-hours"></a>Etkin saatleri yapılandırma
[Holographic Windows sürüm 20H2'den başlayarak,](hololens-release-notes.md#windows-holographic-version-20h2) bir IT Yöneticisi 2 cihaz için HoloLens saat aralığını belirtebilirsiniz.

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

Cihazları güncelleştirmeleri Güncelleştirme'den değil Windows Server Update Service'den (WSUS) almak üzere yapılandırmak için Windows kullanabilirsiniz:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

#### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

- [Windows Holographic, sürüm 21H2'de tanıtıldı.](hololens-release-notes.md#windows-holographic-version-21h2)

Etkin saatler ve yükleme zamanı ilkeleri arasında, kullanım sırasında HoloLens yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklemesini tamamlamak için yeniden başlatmalar oluşmazsa güncelleştirmelerin benimsenmesi de geciker. Şimdi, IT'nin son tarihleri ve gerekli yeniden başlatmaları zorlamasına ve güncelleştirme yükleme işleminin zamanında tamamlandığından emin olmasına olanak sağlayan ilkeler ekledik. Yeniden başlatma işlemi başlatmadan önce kullanıcılara bildirebilirsiniz ve kullanıcılar, YENIDEN başlatmayı IT ilkesine uygun olarak geciktirebilirsiniz.

Aşağıdaki güncelleştirme ilkeleri eklenmiştir:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2 için güncelleştirme HoloLens yapılandırma

HoloLens 2, (1. nesil) HoloLens daha fazla güncelleştirme otomasyonu özelliği destekler. İş için Güncelleştirme ilkelerini yönetmek için Microsoft Intune bu Windows doğrudur. Bu özellikler, güncelleştirmeleri planlamanızı ve uygulamanızı kolaylaştırır.

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

Zaman içinde kuruluşun tamamı için de bu şekilde ilerleme kaydediyoruz.

![Güncelleştirmeleri dağıtmak için zaman çizelgesi.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Güncelleştirme erteleme ilkesi yapılandırma

Erteleme ilkesi, güncelleştirmenin kullanılabilir olduğu tarih ile cihazın güncelleştirmenin sunl olduğu tarih arasındaki gün sayısını belirtir.

Özellik güncelleştirmeleri ve kalite güncelleştirmeleri için farklı ertelemeler yapılandırabilirsiniz. Aşağıdaki tabloda, her tür için kullanmak üzere belirli ilkeler ve her biri için en fazla erteleme listelemektedir.

|Kategori |İlke |Maksimum erteleme |
| --- | --- | --- |
|Özellik güncelleştirmeleri |DeferFeatureUpdatesPeriodInDays |365 gün |
|Kalite güncelleştirmeleri |DeferQualityUpdatesPeriodInDays |30 gün |

#### <a name="pause-updates-via-device"></a>Cihaz Aracılığıyla Güncelleştirmeleri Duraklatma

Bir kullanıcının MDM'ye erişimi yoksa, [Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki bir sürümde bir HoloLens 2 cihazında güncelleştirmeleri Windows tek tek 35 gün boyunca el ile duraklatabilir. Kullanıcılar Bu ayara ulaşmak için Ayarlar > Update **& Security >** Gelişmiş seçenekler'e giderek  Güncelleştirmeleri duraklatma'ya kaydırın ve güncelleştirmeleri duraklatacakları tarihi seçin. Bir kullanıcı duraklatma sınırına ulaştıktan sonra cihazın yeniden duraklatılamadan önce yeni güncelleştirmeler alsa gerekir. 

[Holographic Windows sürüm 20H2'den](hololens-release-notes.md#windows-holographic-version-20h2)başlayarak, bu duraklatma güncelleştirmeleri işlevi HoloLens 2 cihaz için yönetilebilir. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (varsayılan) – Etkin
    - 1 – Devre dışı

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Intune güncelleştirme yönetimi işlevleri HoloLens destekler

Güncelleştirmeleri yönetmek için aşağıdaki Intune güncelleştirme yönetimi işlevlerini HoloLens.

- **Oluşturma** ve **Atama:** Bu işlevler, Windows 10 halkaları listesine bir güncelleştirme halkası ekler. Daha fazla bilgi için [bkz. Güncelleştirme halkaları oluşturma ve atama.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Duraklatma:** Bir özellik veya kalite güncelleştirmesi dağıtırken bir sorunla karşılaşırsanız güncelleştirmeyi 35 gün (belirtilen tarihten başlayarak) duraklatabilirsiniz. Bu duraklatma, siz sorunu çözene veya giderene kadar diğer cihazların güncelleştirmeyi yüklemesini önler. Bir özellik güncelleştirmesini duraklatmanız, cihazların güvenli kalmasını sağlamak için kalite güncelleştirmeleri yine de sunulur. Bir güncelleştirme türü duraklatılırsa, bu halkaya ilişkin Genel Bakış bölmesi, güncelleştirme türünün sürdürülmeden önce kaç gün kaldığı gösterir. Belirtilen süre bittikten sonra duraklatma otomatik olarak sona erer ve güncelleştirme işlemi devam eder.

  Güncelleştirme halkası duraklatılmışken aşağıdaki seçeneklerden birini seçebilirsiniz:

  - **Genişletme:** Bir güncelleştirme türü için duraklatma süresini 35 gün uzatın.
  - **Sürdürme:** Bu halka için güncelleştirmeleri etkin bir işlem olarak geri yükleyin. Gerekirse güncelleştirme halkası yeniden duraklatılır.

  > [!NOTE]  
  > Güncelleştirme **halkaları** için Kaldırma işlemi, 2 HoloLens için desteklenmiyor.

### <a name="delivery-optimization-preview"></a>Teslim İyileştirme Önizleme

[Windows Holographic sürüm 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) birden çok mobil cihazdan yapılan indirmeler için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarına HoloLens etkinleştirdi. Bu işlevin daha ayrıntılı bir açıklaması ve önerilen ağ yapılandırması burada mevcuttur: [güncelleştirmeleri Teslim İyileştirme için Windows 10 kullanılabilir.](/windows/deployment/update/waas-delivery-optimization)

Aşağıdaki ayarlar yönetim yüzeyinin bir parçası olarak etkinleştirilir [ve Intune'dan yalıtabilirsiniz:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Bu önizleme teklifiyle ilgili birkaç uyarı:

- HoloLens desteği bu önizlemede yalnızca işletim sistemi güncelleştirmeleri ile sınırlıdır.
- Windows Holographic for Business yalnızca bir Microsoft Bağlı Önbellek uç noktasına http indirme modlarını ve [indirmelerini destekler;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Eşler arası indirme modları ve grup atamaları şu anda HoloLens cihazlar için desteklenmiyor.
- HoloLens, Sunucu Güncelleştirme Hizmetleri uç noktaları için Windows veya teslim iyileştirmesini desteklemez.
- Sorun giderme işlemi, Bağlı Önbellek sunucusunda tanılama gerektirir veya HoloLens Update HoloLens & Security Troubleshooting Windows Update aracılığıyla **Ayarlar HoloLens** HoloLens üzerinde bir  >    >     >   **izleme toplamayı gerektirir.**

## <a name="manually-check-for-updates"></a>Güncelleştirmeleri el ile denetleme

Sistem HoloLens düzenli aralıklarla denetime alınsa da, el ile kontrol etmek istediğiniz durumlar olabilir.

Güncelleştirmeleri el ile kontrol etmek için güncelleştirmeleri **Ayarlar**  >  **Güncelleştirme & Güvenlik**  >  **Denetimi'ne gidin.** Uygulama Ayarlar cihazınızın güncel olduğunu gösteriyorsa, şu anda kullanılabilir durumda olan tüm güncelleştirmelere sahipsinizdir.

## <a name="manually-roll-back-an-update"></a>Bir güncelleştirmeyi el ile geri alma

Bazı durumlarda, yazılım yazılımının önceki bir sürümüne HoloLens. Bunu yapma işlemi, 2. nesil veya HoloLens (1. nesil) HoloLens bağlıdır.

### <a name="revert-to-a-previous-version-hololens-2"></a>Önceki bir sürüme geri dönme (HoloLens 2)

Gelişmiş Kurtarma Yardımcı'yı kullanarak güncelleştirmeleri geri almak ve HoloLens [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 2'nin önceki bir sürümüne geri dönmek için HoloLens önceki sürüme sıfırlayabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

HoloLens 2'nin önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows emin olun.
1. Bilgisayarınızda, Gelişmiş Kurtarma [Yardımcı'sı'Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)
1. en son [sürüm 2 HoloLens indirin.](https://aka.ms/hololens2download)
1. Bu indirmeler tamam olduktan sonra Dosya Gezgini İndirmeleri'ni açın, az önce indirdiğiniz sıkıştırılmış (.zip) klasörüne sağ tıklayın ve ardından Tüm Ayıkla'yı seçerek  >     >   dosyayı genişletin.
1. Bir USB-A- USB-C kablosu kullanarak HoloLens bilgisayarınıza bağlayın. Bağlantınızı bağlamak için başka kablolar HoloLens bile bu tür kablolar en iyi şekilde çalışır.
1. Gelişmiş Kurtarma Yardımcı, cihazınızı otomatik olarak HoloLens algılar. Yeni **kutucuğu Microsoft HoloLens** seçin.
1. Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve ardından daha önce genişlettiniz klasörü açın.
1. Yükleme (.ffu) dosyasını seçin.
1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Önceki bir sürüme geri dönme (HoloLens (1. nesil))

Güncelleştirmelerinizi önceki sürüme sıfırlamak için Windows Cihaz Kurtarma Aracı'nı [(WDRT)](https://support.microsoft.com/help/12379) kullanarak güncelleştirmeleri geri HoloLens (1. nesil) HoloLens dönebilirsiniz.

> [!NOTE]
> Önceki bir sürüme HoloLens, kişisel dosyalarınızı ve ayarlarınızı siler.

Önceki bir HoloLens (1. nesil) sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows emin olun.
1. Bilgisayarınızda, Windows [Kurtarma Aracı'nı (WDRT) indirin.](https://support.microsoft.com/help/12379)
1. yıldönümü [HoloLens kurtarma paketini indirin.](https://aka.ms/hololensrecovery)
1. İndirmeler tamam olduktan sonra Dosya Gezgini İndirmeler'i açın, az önce indirdiğiniz sıkıştırılmış (.zip) klasörüne sağ tıklayın ve ardından Tüm Ayıkla'yı seçerek   >     >   dosyayı genişletin.
1. HoloLens cihazınızı bilgisayarınıza bağlamak için HoloLens sağlanan mikro USB kablosunu kullanın. Cihazınızı bağlamak için başka kablolar kullanıyorsanız bile HoloLens bu en iyi şekilde çalışır.
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
