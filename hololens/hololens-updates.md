---
title: HoloLens güncelleştirmelerini yönetme
description: yöneticilerinize HoloLens cihazlara yönelik güncelleştirmeleri yönetmek için mobil cihaz yönetimini nasıl kullanabileceğinizi öğrenin.
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
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190047"
---
# <a name="manage-hololens-updates"></a>HoloLens güncelleştirmelerini yönetme

HoloLens, Windows Update diğer Windows 10 cihazlarıyla aynı şekilde kullanır. Bir güncelleştirme kullanılabilir olduğunda, cihazınızın İnternet 'e bağlanması ve internet 'e bağlanması sırasında otomatik olarak indirilir ve yüklenir. Bu makalede, bir kuruluşta veya başka bir yönetilen ortamda güncelleştirmelerin nasıl yönetileceği açıklanır. ayrı HoloLens cihazlarda güncelleştirmelerin nasıl yönetileceği hakkında daha fazla bilgi için bkz. [güncelleştirme HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Güncelleştirmeleri otomatik olarak Yönet

### <a name="managing-updates-by-using-windows-update-for-business"></a>iş için Windows Update kullanarak güncelleştirmeleri yönetme

Windows Holographic for Business, güncelleştirmeleri yönetmek için [iş Windows Update](/windows/deployment/update/waas-manage-updates-wufb) kullanabilir. tüm HoloLens 2 cihazları Windows Holographic for Business kullanabilir. Windows Holographic for Business build 10.0.18362.1042 veya sonraki bir derlemeyi kullandıklarından emin olun. HoloLens (1. gen) cihazlara sahipseniz, güncelleştirmelerini yönetmek için [bunları Windows Holographic for Business yükseltmeniz](hololens1-upgrade-enterprise.md) gerekir.

Windows iş için güncelleştirme cihazları doğrudan Windows Update hizmetine bağlar HoloLens. iş için Windows Update kullanarak, hangi &mdash; cihazların hangi cihazlarda hangilerinin alınacağını, güncelleştirme işleminin birden çok yönünü kontrol edebilirsiniz. Örneğin, test için cihazların bir alt kümesine yapılan güncelleştirmeleri kullanıma alabilir ve daha sonra kalan cihazlara güncelleştirmeleri kullanıma alabilirsiniz. Ya da farklı güncelleştirme türleri için farklı güncelleştirme zamanlamaları tanımlayabilirsiniz.

> [!NOTE]  
> HoloLens cihazlarda, özellik güncelleştirmelerini (yılda iki kez yayınlanan) ve kalite güncelleştirmeleri (aylık veya gerekli olduğu gibi kritik güvenlik güncelleştirmeleri dahil) otomatik olarak yönetebilirsiniz. güncelleştirme türleri hakkında daha fazla bilgi için bkz. [iş için Windows Update yönetilen güncelleştirme türleri](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Microsoft Intune gibi bir mobil cihaz yönetimi (MDM) çözümünde ilkeleri kullanarak HoloLens için Windows Update iş ayarlarını yapılandırabilirsiniz.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Windows Update Microsoft Intune kullanarak iş için yönetme

ıntune 'u iş için Windows Update yapılandırmak üzere kullanma hakkında ayrıntılı bir tartışma için bkz. [ıntune 'da Windows 10 yazılım güncelleştirmelerini yönetme](/intune/protect/windows-update-for-business-configure). HoloLens desteklediği belirli ıntune işlevleri hakkında daha fazla bilgi için, bkz. [HoloLens tarafından desteklenen ıntune güncelleştirme yönetimi işlevleri](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> ıntune, güncelleştirmeleri yönetmek için iki ilke türü sağlar: *Windows 10 güncelleştirme halkası* ve *Windows 10 özellik güncelleştirmesi*. Windows 10 özelliği güncelleştirme ilkesi türü şu anda genel önizlemede ve HoloLens için desteklenmez.
>  
> HoloLens 2 güncelleştirmelerini yönetmek için Windows 10 güncelleştirme halkası ilkelerini kullanabilirsiniz.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>HoloLens 2 veya HoloLens için güncelleştirme ilkelerini yapılandırma (1. genel)

bu bölümde, HoloLens 2 veya HoloLens (1. gen) için güncelleştirmeleri yönetmek üzere kullanabileceğiniz ilkeler açıklanmaktadır. HoloLens 2 için kullanılabilen işlevler hakkında daha fazla bilgi için, bkz. [HoloLens 2 için update piyasaya çıkarma Plan ve yapılandırma](#plan-and-configure-update-rollouts-for-hololens-2).

[ilke CSP-güncelleştirme](/windows/client-management/mdm/policy-csp-update) , iş için Windows Update yapılandıran ilkeleri tanımlar.

> [!NOTE]  
> belirli HoloLens sürümleri tarafından desteklenen belirli ilke yapılandırma hizmeti sağlayıcılarının (csp) listesi için, bkz. [HoloLens cihazlar tarafından desteklenen ilke csp 'leri](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Güncelleştirmeler için otomatik denetimleri yapılandırma

Güncelleştirmeleri tarama, indirme ve yükleme gibi otomatik güncelleştirme davranışını yönetmek için **Update/allowupdate** ilkesini kullanabilirsiniz. Bu ilke için kullanılabilir ayarlar hakkında daha fazla bilgi için, bkz. [Update/Allowupdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> Microsoft Intune, bu ilkeyi değiştirmek için **otomatik güncelleştirme davranışını** kullanabilirsiniz. daha fazla bilgi için bkz. [ıntune 'da Windows 10 yazılım güncelleştirmelerini yönetme](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Güncelleştirme zamanlaması yapılandırma

Güncelleştirmelerin nasıl ve ne zaman uygulanacağını yapılandırmak için aşağıdaki ilkeleri kullanın:

- [Güncelleştirme/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Değerler: **0**–**7** (0 = her gün, 1 = Pazar, 7 = Cumartesi)
  - Varsayılan değer: **0** (her gün)
- [Güncelleştirme/Scheduledınstalltime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Değerler: 0 – 23 (0 = gece, 23 = 11 PM)
  - Varsayılan değer: 3

#### <a name="configure-active-hours"></a>Etkin saatleri yapılandırma
[Windows Holographic, sürüm 20h2 '](hololens-release-notes.md#windows-holographic-version-20h2) den başlayarak, bir bt yöneticisi HoloLens 2 cihazları için etkin saatler aralığını belirtebilir.

Etkin saatler, cihazın kullanımda olması beklendiğinde geçen süreyi belirler. Güncelleştirme, etkin saatlerin dışında gerçekleştikten sonra otomatik olarak yeniden başlatılır. Belirtilen Aralık, etkin saatler başlangıç zamanından itibaren sayılacak. MDM [ile etkin saatleri yapılandırma](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)bölümünde AÇıKLANDıĞı gibi MDM 'yi kullanabilirsiniz. MDM, Ilke CSP içindeki Update/ActiveHoursStart ve Update/ActiveHoursEnd ve Update/ActiveHoursMaxRange ayarlarını kullanarak etkin saatleri yapılandırır.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) -bu değer bitiş saatini ayarlar. Başlangıç zamanından itibaren 12 saat üst sınırı vardır.
    -   Desteklenen değerler 0-23, burada 0 ile 12, 1, vb. olur.
    -   Varsayılan değer 17 ' dir (5 PM).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) -bu değer başlangıç zamanından en fazla etkin saat sayısını ayarlar.
    -   Desteklenen değerler 8-18 ' dir.
    -   Varsayılan değer 18 ' dir (saat).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) -bu değer başlangıç saatini ayarlar. Bitiş zamanından itibaren 12 saat üst sınırı vardır.
    -   Desteklenen değerler 0-23, burada 0 ile 12, 1, vb. olur.
    -   Varsayılan değer 8 ' dir (8 har).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Windows 10 çalıştıran cihazlarda yalnızca sürüm 1607

Windows Update yerine Windows Server update Service (WSUS) güncelleştirmelerini almak üzere cihazları yapılandırmak için aşağıdaki güncelleştirme ilkelerini kullanabilirsiniz:

- [Güncelleştirme/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Güncelleştirme/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>HoloLens 2 için güncelleştirme piyasaya çıkarma planlayın ve yapılandırın

HoloLens 2 ' den daha fazla güncelleştirme otomasyonu özelliğini destekler HoloLens (1. gen). bu, Microsoft Intune Windows Update iş ilkelerini yönetmek için kullanıyorsanız özellikle doğrudur. Bu özellikler, kuruluşunuzda güncelleştirme piyasaya çıkarma planlamanızı ve uygulamanızı daha kolay hale getirir.

#### <a name="plan-the-update-strategy"></a>Güncelleştirme stratejisini planlayın

Windows Iş güncelleştirmeleri erteleme ilkelerini destekler. Microsoft bir güncelleştirmeyi yayınladıktan sonra, bu güncelleştirmeyi cihazlara yüklemeden önce ne kadar bekleneceğini tanımlamak için erteleme İlkesi kullanabilirsiniz. Cihazlarınızın alt kümelerini ( *güncelleştirme halkaları* olarak da bilinir) farklı erteleme ilkeleriyle ilişkilendirerek, kuruluşunuz için bir güncelleştirme dağıtımı stratejisini koordine edebilirsiniz.

Örneğin, 1.000 cihaz içeren bir kuruluş düşünün ve beş dalgadaki cihazları güncelleştirmek gerekir. Kuruluş, aşağıdaki tabloda gösterildiği gibi beş güncelleştirme halkaları oluşturabilir.

|Grup |Cihaz sayısı |Erteleme (gün) |
| ---| :---: | :---: |
|GRP 1 (BT personeli) |5 |0 |
|GRP 2 (erken benimseyeniler) |50 |60 |
|GRP 3 (ana 1) |250 |120 |
|GRP 4 (ana 2) |300 |150 |
|GRP 5 (ana 3) |395 |180 |

Kuruluşun tüm kuruluşa zaman içinde nasıl ilerlediğini aşağıda bulabilirsiniz.

![Güncelleştirmeleri dağıtmak için zaman çizelgesi.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Güncelleştirme erteleme ilkesini yapılandırma

Erteleme ilkesi, bir güncelleştirmenin kullanılabilir olduğu tarih ve güncelleştirmenin bir cihaza sunulacağı tarih arasındaki gün sayısını belirtir.

Özellik güncelleştirmeleri ve kalite güncelleştirmeleri için farklı erteleri yapılandırabilirsiniz. Aşağıdaki tabloda, her tür için kullanmak üzere belirli ilkeler ve her biri için en fazla erteleme listelemektedir.

|Kategori |İlke |Maksimum erteleme |
| --- | --- | --- |
|Özellik güncelleştirmeleri |DeferFeatureUpdatesPeriodInDays |365 gün |
|Kalite güncelleştirmeleri |DeferQualityUpdatesPeriodInDays |30 gün |

#### <a name="pause-updates-via-device"></a>Cihaz Aracılığıyla Güncelleştirmeleri Duraklatma

Bir kullanıcının MDM'ye erişimi yoksa, [Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki bir sürümde bir HoloLens 2 cihazında güncelleştirmeleri Windows tek tek 35 gün boyunca el ile duraklatabilir. Kullanıcılar Bu ayara ulaşmak için **Ayarlar > Update & Security >** Gelişmiş seçenekler'e giderek  Güncelleştirmeleri duraklatma'ya inin ve güncelleştirmeleri duraklatacakları tarihi seçin. Bir kullanıcı duraklatma sınırına ulaştıktan sonra cihazın yeniden duraklatılamadan önce yeni güncelleştirmeler alsa gerekir. 

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
- Windows Holographic for Business yalnızca bir Microsoft Bağlı Önbellek uç noktasına http [indirme modlarını ve indirmelerini destekler;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Eşler arası indirme modları ve grup atamaları şu anda HoloLens cihazlar için desteklenmiyor.
- HoloLens Sunucu Güncelleştirme Hizmetleri uç noktaları için dağıtım veya Windows iyileştirmeyi desteklemez.
- Sorun giderme işlemi için Bağlı Önbellek sunucusunda tanılama gerekir veya HoloLens'da HoloLens'de Ayarlar   >  **Update & Security**  >   **Troubleshooting** Windows Update aracılığıyla bir  >   **izleme toplanması gerekir.**

## <a name="manually-check-for-updates"></a>Güncelleştirmeleri el ile denetleme

Sistem HoloLens düzenli aralıklarla denetime alınsa da, el ile kontrol etmek istediğiniz durumlar olabilir.

Güncelleştirmeleri el ile kontrol etmek için güncelleştirmeleri **Ayarlar**  >  **Güncelleştirme & Güvenlik**  >  **Denetimi'ne gidin.** Uygulama Ayarlar cihazınızın güncel olduğunu gösteriyorsa, şu anda kullanılabilir durumda olan tüm güncelleştirmelere sahipsinizdir.

## <a name="manually-roll-back-an-update"></a>Bir güncelleştirmeyi el ile geri alma

Bazı durumlarda, HoloLens yazılımının önceki bir sürümüne dönmek HoloLens. Bunu yapma işlemi, 2. nesil veya HoloLens (1. nesil) HoloLens bağlıdır.

### <a name="revert-to-a-previous-version-hololens-2"></a>Önceki bir sürüme geri dönme (HoloLens 2)

Güncelleştirmelerinizi önceki sürüme sıfırlamak için Gelişmiş Kurtarma Yardımcı'yı [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) kullanarak HoloLens 2'nin önceki bir sürümüne geri HoloLens geri dönabilirsiniz.

> [!NOTE]
> Önceki bir sürüme geri dönmek kişisel dosyalarınızı ve ayarlarınızı siler.

HoloLens 2'nin önceki bir sürümüne dönmek için şu adımları izleyin:

1. Bilgisayarınıza takılı telefon veya Windows emin olun.
1. Bilgisayarınızda, Gelişmiş Kurtarma [Yardımcı'sı'Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)
1. 2 [sürümü için en HoloLens sürümü indirin.](https://aka.ms/hololens2download)
1. Bu indirmeler tamam olduktan sonra Dosya Gezgini İndirmeleri'ni açın, az önce indirdiğiniz sıkıştırılmış (.zip) klasörüne sağ tıklayın ve ardından Tüm Ayıkla'yı seçerek  >     >   dosyayı genişletin.
1. Bir USB-A-USB-C kablosu kullanarak HoloLens bilgisayarınıza bağlayın. Bağlantınızı bağlamak için başka kablolar HoloLens bile bu tür kablolar en iyi şekilde çalışır.
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
1. Yıldönümü [HoloLens kurtarma paketini indirin.](https://aka.ms/hololensrecovery)
1. İndirmeler tamam olduktan sonra Dosya Gezgini İndirmeler'i açın, az önce indirdiğiniz sıkıştırılmış (.zip) klasörüne sağ tıklayın ve ardından Tüm Ayıkla'yı seçerek   >     >   dosyayı genişletin.
1. HoloLens cihazınızla birlikte sağlanan mikro USB kablosunu kullanarak HoloLens bilgisayarınıza bağlayın. Cihazınızı bağlamak için başka kablolar kullanıyorsanız bile HoloLens bu en iyi şekilde çalışır.
1. WDRT, cihazlarınızı otomatik HoloLens algılar. Yeni **kutucuğu Microsoft HoloLens** seçin.
1. Sonraki ekranda El ile paket **seçimi'ne tıklayın** ve ardından daha önce genişlettiniz klasörü açın.
1. Yükleme (.ffu) dosyasını seçin.
1. Yazılım **yükle'yi** seçin ve yönergeleri izleyin.

**WDRT cihazınızı algılamazsa**

WDRT, cihazınızı algılamazsa HoloLens yeniden başlatmayı deneyin. Bu işe uymazsa Cihazım algılanmadı'yi  **seçin,** Microsoft HoloLens'yi seçin ve yönergeleri izleyin.

## <a name="related-articles"></a>İlgili makaleler:

- [HoloLens 2 sürüm notu](hololens-release-notes.md)
- [İş Windows Güncelleştirme nedir?](/windows/deployment/update/waas-manage-updates-wufb)
- [Cihaz güncelleştirmeleri için hizmet kanallarına Windows 10 atama](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Intune’da Windows 10 yazılım güncelleştirmelerini yönetme](/mem/intune/protect/windows-update-for-business-configure)
