---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider Derlemeleriyle çalışmaya başlama ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlama hakkında bilgi edinin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 09/14/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: bdfdcda8cc890691f6112e7798d402ca9e7f4c6d
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904319"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview yapılarına hoş geldiniz! [Başlamak ve HoloLens](hololens-insider.md#start-receiving-insider-builds) için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlamak kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider sürüm notları

ınsiders Windows yeni özellikleri yeniden başlatmak için heyecanlıyız. Yeni derlemeler, en son güncelleştirmeler için geliştirme ve Beta kanallarına uçucaktır. Windows ınsider derlemelerimize daha fazla özellik ve güncelleştirme eklediğimiz için bu sayfayı güncelleştirmeye devam edeceğiz. Heyecanlanmanıza ve bu güncelleştirmeleri gerçeğe sunmaya hazırlanın.

Bu, geliştirilmiş sorun giderme ve cihaz raporları, bilgi noktası modundaki bazı sabit hatalar ve sertifika Görüntüleyicisi, genişletilmiş yönetilebilirlik yüzeyi ve artırılmış güncelleştirme güvenilirliği hakkında bilgi sunar. bu özellik güncelleştirmesinin yeni bir flaggeme özelliği, hareketli Platform modumuza HoloLens geliyor. HoloLens 2 ' nin tüm yeni harika özelliklerine göz atın!

| Özellik                 | Açıklama                | Kullanıcı veya senaryo | Tanıtılan derleme |
|-------------------------|----------------------------|--------------|------------------|
| [Platform modu taşınıyor](#moving-platform-mode) | yapılandırıldığında, büyük deniz mavisi ' de düşük dinamik hareket yaşayan HoloLens 2 ' nin kullanımını sağlayan Platform modu beta 'yı tanıtır. | Tümü | 20348,1411 |
| [Sertifika Yöneticisi için PFX dosya desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleyin | Son Kullanıcı | 20348,1405 |
| [HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazdaki MDM tanılama günlüklerini görüntüle | Sorun giderme | 20348,1405 |
| [Çevrimdışı tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için audiogörsel geri bildirimi | Sorun giderme | 20348,1405 |
| [Düşük depolama günlüğü koleksiyonu geliştirmeleri](#low-storage-log-collection-improvements) | Düşük depolama durumları sırasında günlük toplama senaryolarında iyileştirmeler. | Sorun giderme | 20348,1412 |
| [raporlama HoloLens ayrıntıları için CSP değişiklikleri](#csp-changes-for-reporting-hololens-details) | Verileri sorgulamak için yeni CSP 'Ler | BT yöneticileri    | 20348,1403                 |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Hesapta otomatik olarak oturum açmak için kullanılır | BT yöneticileri | 20348,1405 |
| [Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri](#improved-update-restart-detection-and-notifications) | Güncelleştirmeler için yeni etkinleştirilen ilkeler ve UX. | BT yöneticileri | 20348,1405 |
| [Uygulama güncelleştirmeleri için akıllı yeniden deneme](#smart-retry-for-app-updates) | BT yöneticilerinin uygulamaları güncelleştirmek için yeniden denemelere izin verir. | BT yöneticileri | 20348,1405 |
| [Yalnızca Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluştan gelen uygulamaları gösterecek şekilde yapılandırma | BT Yöneticisi | 20348,1408 |
| [WDAC ve LOB uygulamalarını kullanma](#use-wdac-and-lob-apps) | BT yöneticilerinin kendi uygulamalarını kullanmasına izin verir ve diğer uygulamaları engellemek için yine de WDAC kullanır. | BT yöneticileri | 20348,1405 |
| [Düzeltmeler ve geliştirmeler](#fixes-and-improvements) | HoloLens düzeltmeler ve geliştirmeler. | Tümü | 20348,1411 |

### <a name="it-admin-insider-feature-checklist"></a>BT Yöneticisi Insider özelliği denetim listesi

✔️ otomatik olarak oturum açmak için tek bir Azure AD hesabı ayarlamak isterseniz, [Bu yenı CSP 'yi yapılandırın.](#auto-login-policy-controlled-by-csp) <br>
✔️ güncelleştirme başarısız olduktan sonra uygulamalarınızı otomatik olarak güncelleştirmeye çalışacak şekilde yapılandırmak istiyorsanız, [Bu yenı CSP 'yi akıllı yeniden deneme için ayarlayın.](#smart-retry-for-app-updates) <br>
✔️ işletim sistemi güncelleştirmeleri üzerinde daha fazla denetime sahip olmak istiyorsanız, bu [Yeni etkinleştirilmiş güncelleştirme ilkelerine](#improved-update-restart-detection-and-notifications)göz atın. <br>
✔️ kuruluşunuzun uygulamalarını, Microsoft Store aracılığıyla şirket mağazasının kullanımına sunmak, ancak yalnızca kuruluşunuzun uygulamalarına erişime izin vermek ve tam mağaza değil olmak istiyorsanız, [bu ilkeyi ayarlayın](#use-only-private-store-apps-for-microsoft-store). <br>
✔️ boş depolama alanını, HoloLens cihazlarınızın ssıd veya bssıd 'sini öğrenmek isterseniz, bu [raporlama csp 'lerine](#csp-changes-for-reporting-hololens-details)göz atın. <br>
✔️ uygulamaların veya işlemlerin başlatılmasını engellemek için WDAC kullanmak istiyorsanız, ancak aynı zamanda kendi iş kolu uygulamalarınızı kullanmanız gerekiyorsa, artık [WDAC ILKENIZDE lob 'a izin](#use-wdac-and-lob-apps)verebilirsiniz.

### <a name="moving-platform-mode"></a>Platform modu taşınıyor

**ınsider build 20348,1411** itibariyle, HoloLens 2 ' de düşük dinamik hareket taşınan platformları izlemek için beta desteği ekledik. derlemeyi yükledikten ve platformu taşıma modunu etkinleştirdikten sonra, büyük ve büyük deniz mavisi gibi daha önce erişilemeyen ortamlarda HoloLens 2 ' yi kullanabilirsiniz. Şu anda özelliği, yalnızca bu taşıma platformlarının etkinleştirilmesini hedeflenmiştir. Başka ortamlarda özelliği kullanmayı denediğinize hiçbir şey engel olmadıysa, bu özellik önce bu ortamlar için destek eklemeye odaklanılmıştır.

Nelerin desteklendiği ve bu yeni özelliğin nasıl etkinleştirileceği hakkında daha fazla bilgi edinmek için, [hareketli platform sayfasını ziyaret edin](hololens2-moving-platform.md).

#### <a name="overview-to-try-out-moving-platform-mode"></a>Taşıma platformu modunu denemeye genel bakış

1. [Geliştirici modunu ve cihaz portalını etkinleştirin](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. [Platform modunun cihaz portalı aracılığıyla taşınmasını etkinleştirin](hololens2-moving-platform.md#enabling-moving-platform-mode).
1. Cihazınızı büyük taşıma platformunuza götürün ve kararlı hologramlar olduğunu gözlemleyin.

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosya desteği

Windows ınsider build 20348,1405 ' de kullanıma sunulmuştur. Artık. pfx sertifikalarını kullanacak şekilde [sertifika yöneticisine](certificate-manager.md) destek ekledik. kullanıcılar **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **sertifikalarına** gezindiğinde ve **sertifikayı yükler** ' i seçtiğinizde, kullanıcı arabirimi artık. pfx sertifika dosyasını destekliyor.
Kullanıcılar, özel anahtarla, Kullanıcı deposuna veya makine deposuna. pfx sertifikasını içeri aktarabilir.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Sertifika Yöneticisi 'nde PFX dosyalarını denemeye genel bakış

1. PFX dosyanızı hazırlayın.
1. Bir USB-C kablosu aracılığıyla dosyayı cihazınıza kopyalayın.
1. Ayarlar uygulamasını açın ve [sertifika yöneticisi](certificate-manager.md) ' ne gidin ve sertifikayı uygulayın.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle

Yönetilen cihazlar için sorun giderme sırasında, beklenen bir ilke yapılandırmasının uygulandığını onaylayan önemli bir adımdır. daha önce bu yeni özellik için, bu bilgilerin görüntülenmesi, **Ayarlar** hesapları aracılığıyla toplanan mdm tanılama günlüklerini dışarı aktardıktan sonra iş veya okul aracılığıyla cihazın yakınında veya cihazın yakınında yapılması gerekiyordu  ->    >  ve **yönetim günlüklerinizi dışa aktarıp** yakındaki bir bilgisayarda görüntülenmiş olarak.

Artık MDM Tanılaması, Edge tarayıcısı kullanılarak cihazda görüntülenebilir. MDM Tanılama raporunu daha kolay bir şekilde görüntülemek için iş veya okul sayfasına gidin ve **Gelişmiş tanılama raporunu görüntüle**' yi seçin. Bu, raporu yeni bir kenar penceresinde oluşturur ve açar.

![Ayarlar uygulamasında gelişmiş tanılama raporunu görüntüleyin.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Gelişmiş tanılama raporunu denemek için genel bakış

1. Ayarlar uygulamasını açın.
1. Hesaplar sayfasına gidin ve yeni Yönetim günlüklerinizi dışarı **aktar bağlantısına tıklayın.**
1. Cihazınızın yapılandırmaları hakkında gelişmiş bilgileri görüntüleme.

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı Tanılama bildirimleri

Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics) Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.
Artık Windows Insider derlemelerine eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır. Birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)

Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Tanılama bildirimlerini denemek için genel bakış

1. Cihazınızın kilidini açın ve cihazı yıprandırabilirsiniz.
1. Çevrimdışı **Tanılamayı** toplamak **için Güç** ve Birim kapalı [düğme birleşimine basın.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Bildirimlere bakın ve cihazınızın ne zaman başladığına ve günlük toplamayı bitirip ne zaman tamamladığına ilgili sesli ipuçlarına bakın.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü toplama geliştirmeleri

Tanılama günlükleri toplanmışken cihazın disk alanı düşük gibi görünen senaryolarda,StorageDiagnostics.zip **ek** bir rapor oluşturulur. Düşük depolama eşiği, depolama alanı algısı Windows [belirlenir.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Düşük depolama geliştirmelerini denemek için genel bakış

1. Cihazınızın depolama alanını doldurun.
1. Çevrimdışı **Tanılamayı** toplamak **için Güç** ve Birim kapalı [düğme birleşimine basın.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Dosyanın Belgeler klasöründe depolanan günlük koleksiyonunda yeni bir dosya olduğunu HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Rapor ayrıntıları için CSP HoloLens değişiklikleri

- Windows Insider derlemesinde tanıtıldı, 20348.1403

Aşağıdaki CSP'ler, HoloLens cihazlarınıza ilişkin bilgileri bildirmenin yeni HoloLens güncelleştirilmiştir.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Ücretsiz Depolama

DevDetail CSP artık cihaz üzerinde boş depolama alanı HoloLens raporlar. Bu değer, uygulamanın Ayarlar sayfasında gösterilen değerle yaklaşık Depolama eşleşmesi gerekir. Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer aleladedir.

- ./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP - SSID ve BSSID

DeviceStatus CSP artık etkin olarak bağlı olduğu Wi-Fi SSID ve BSSID HoloLens raporlar. Aşağıda bu bilgileri içeren belirli düğümler yer almaktadır.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/BSSID

NetworkIdentifiers sorgulamak için örnek syncml blobu (MDM satıcıları için)

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>CSP tarafından denetlenen otomatik oturum açma ilkesi

Bu yeni AutoLogonUser ilkesi, bir kullanıcının otomatik olarak oturum açıp oturum açmayacaklarını kontrol eder. Bazı müşteriler, bir kimliğe bağlı ancak oturum açma deneyimi istemeden cihazları ayarlamak ister. Imagine cihazı alacak ve uzaktan yardım'ı hemen kullanmaya devam edebilirsiniz. Veya cihazları hızla dağıtarak son kullanıcılarının oturum açma HoloLens olanaklı olma avantajından da yararlanabilirsiniz.

İlke boş olmayan bir değere ayarlanırsa, otomatik oturum açma kullanıcısını e-posta adresi belirtir. Belirtilen kullanıcının otomatik oturum açmayı etkinleştirmek için cihazda en az bir kez oturum açması gerekir.

Yeni ilke Dizesi değerinin `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI'sı

- Aynı e-posta adresine sahip kullanıcı otomatik oturum açmayı etkinleştirmiş olur.

Bu ilkenin yapılandırıldığında, ilkede belirtilen kullanıcının en az bir kez oturum açması gerekir. İlk oturum açma sonrasında cihazın yeniden başlatılması, belirtilen kullanıcının otomatik olarak oturum açmasını sağlar. Yalnızca tek bir otomatik oturum açma kullanıcısı de destekler. Etkinleştirildikten sonra, otomatik olarak oturum açan kullanıcı el ile oturumu kapatamayacaktır. Farklı bir kullanıcı olarak oturum açılabilir. İlkenin önce devre dışı bırakılmıştır.

> [!NOTE]
>
> - Büyük işletim sistemi güncelleştirmeleri gibi bazı olaylar, belirtilen kullanıcının otomatik oturum açma davranışını sürdürmesi için cihazda yeniden oturum açmasını gerekli kilebilir.
> - Otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için de kullanılabilir.

#### <a name="overview-to-try-auto-logon-csp"></a>CSP'yi otomatik olarak oturum açmayı denemek için genel bakış

1. Özel bir ilke kullanarak yeni CSP'yi [istenen kullanıcıya yapılandırma:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. CsP'yi sağlama paketi [veya](hololens-provisioning.md) [MDM aracılığıyla cihaza uygulama.](hololens-mdm-configure.md)
1. Belirtilen hesapta oturum açın.
1. Cihazı yeniden başlatın ve kullanıcının otomatik olarak oturum açtığını gözlemler.

### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

Etkin saatler ve yükleme zamanı ilkeleri arasında, cihazlarda kullanım sırasında HoloLens yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklemesini tamamlamak için yeniden başlatmalar oluşmazsa güncelleştirmelerin benimsenmesi de geciker. Şimdi, IT'nin son tarihleri ve gerekli yeniden başlatmaları zorlamasına ve güncelleştirme yükleme işleminin zamanında tamamlandığından emin olmasına olanak sağlayan ilkeler ekledik. Kullanıcılara, yeniden başlatma işlemi başlatmadan önce bildirebilirsiniz ve kullanıcılar, YENIDEN başlatmayı IT ilkesine uygun olarak geciktirebilirsiniz.

Aşağıdaki güncelleştirme ilkeleri eklendi:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Yeni güncelleştirme bildirimlerini denemek için genel bakış

1. Sağlama paketi veya [MDM](hololens-mdm-configure.md) aracılığıyla yeni güncelleştirme CSP'lerinden birini yapılandırma (yukarıdaki bağlantı listesine bakın ve birini seçin). [](hololens-provisioning.md)
1. Zamanlanan saat boyunca cihazı kullanın.
1. Kullanıcıya güncelleştirme hakkında bilgi ve cihazı yeniden başlatma ihtiyacı olduğunu \* gözlemlemek.

\* Sonuçlarınız kullanılan Güncelleştirme ilkelerine göre değişebilir.

### <a name="smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için Akıllı Yeniden Deneme

Artık HoloLens için etkinleştirilen yeni bir ilke, IT Yöneticilerinin güncelleştirmenin uygulamaya uygulanmasına izin verme nedeniyle başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir saat tarihi ayarlamasına olanak sağlayan yeni bir ilkedir. Bunlar zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilirsiniz. Bu ilke görünümünü kullanma hakkında daha fazla bilgi edinmek için [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için Akıllı Yeniden Denemeyi denemek için genel bakış

1. Yeni akıllı yeniden deneme özelliğini yapılandırma.
1. Henüz uygulamanıza alınmış ve doğru şekilde yapılandırılmış bir cihazda, çevrimiçi bir ortamda oturum açın.
1. Cihazı kapatarak veya bağlantısını keserek uygulamayı indirenin.
1. İndirmeyi yeniden denemek için tetiklenen süre boyunca cihazınızın açık ve İnternet'e bağlı olduğundan emin olun.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Yalnızca özel mağaza uygulamalarını Microsoft Store

RequirePrivateStoreOnly ilkesi, HoloLens. Bu ilke, Microsoft Store uygulamasının yalnızca özel mağazayı gösterecek şekilde yapılandırılması için yapılandırmanıza olanak sağlar. Erişimi yalnızca kullanılabilir yapmış olduğunuz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly hakkında daha fazla bilgi edinebilirsiniz.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

#### <a name="overview-to-try-only-private-store-apps"></a>Yalnızca özel mağaza uygulamalarını denemek için genel bakış

1. MDM aracılığıyla cihazlarınız için [yeni ilkeyi yapılandırma.](hololens-mdm-configure.md)
1. İlkeye sahip bir cihazda oturum açın.
1. Uygulama Microsoft Store açın ve yalnızca kuruluş uygulamalarını gördüğünüze dikkat edin.

### <a name="use-wdac-and-lob-apps"></a>WDAC ve LOB uygulamalarını kullanma

Artık uygulama veya işlemlerin başlatılmasını engellemek için WDAC kullanabilir ve kendi işlem hattınızdan oluşan uygulamalarınızı kullanmaya devam edebilirsiniz. Artık bunlara WDAC ilkenizde izin verebilirsiniz. Bu ilkenin kullanılması, WDAC ilkenizi oluştururken PowerShell 'de ek bir kod satırı çalıştırmayı içerir. [Buradaki adımları gözden geçirin](/mem/intune/configuration/custom-profile-hololens).

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Diğer uygulamaları engellemek için WDAC kullanırken kendi uygulamalarınızı denemeye genel bakış

1. LOB uygulamanızın Aumkimliklerini ve engellemeyi planladığınız uygulamaları toplayın.
1. Yeni adımları izleyerek [Yeni BIR WDAC Ilkesi oluşturun](/mem/intune/configuration/custom-profile-hololens) .
1. [ILKEYI MDM kullanarak cihazınıza dağıtın](hololens-mdm-configure.md) .
1. Cihazda oturum açın ve uygulamanızı başlatıp diğerlerini engelleyebilmenizi sağlayabilirsiniz.

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler

- Bir [cihaz portalı için, kilitli dosyaları indirmede hiçbir istem olmadığı bilinen bir sorun](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)düzeltildi.
- [Karşıya dosya yükleme ve indirme zaman aşımları Ile cihaz portalı 'nın bilinen bir sorunu](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)düzeltildi.
- HoloLens cihazlarından raporlama uyumluluk özellikleri etrafında sorunları giderir; Insider Derlemeleriyle ilgili doğru raporlama tetiklenmesi için yeniden başlatma gerekebilir.  
- uygulamaların, HoloLens oturum açan kullanıcı için bilgi noktası modunda HoloLens çalışıp çalışmadığını belirleyebilmesi için [atanan erişim apı 'si](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) etkinleştirildi.
- Uzaktan Yardım 'ın yerleşik sürümü, yeni bir yanıp sönuca yüklenmiş olarak güncelleştirildi.
- 2B uygulamalar için oyun yüzeyi işleme, Insider Derlemeleriyle devre dışı bırakıldı. Bu uygulamayı kaldırarak, uygulamalar artık oyun yüzeyi API 'Lerini doğrudan kullanmaya ve tüm denetim kümesine erişime sahip olmak ve istedikleri her şeyi yapmak için ücretsizdir. Geliştiriciler oyun yüzeyi girişini tüketmek için oyun yüzeyi API 'Lerini kullanmalıdır. Bu, [oyun yüzeyi sınıfı (Windows için bir örnektir. Gaming. ınput)-UWP uygulamalarını Windows](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- İlk Kullanıcı oturum açma işleminden sonra yapılan bir sorun düzeltildi ve AAD grubu tabanlı bilgi noktası yapılandırmalarının kullanıldığı senaryolarda OOBE sonlandırılmıştı.
- Cihaz yeniden başlatması için güncelleştirme bildirimleri ve iletişim kutusu istemleri görüntülenirken bir sorun düzeltildi.

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlayın

> [!NOTE]
> Son zamanlarda güncelleştirmediyseniz, durumu güncelleştirmek ve en son derlemeyi almak için lütfen cihazınızı yeniden başlatın.
>
> - "Cihazı yeniden Başlat" ses komutu iyi şekilde çalışmaktadır.
> - Ayarlar/Windows ınsider programı ' nda yeniden başlat düğmesini de seçebilirsiniz.
>
> Arka uçta karşılaştığınız bir hata yaşadık ve bu, izlemeye geri dönecek.

HoloLens 2 cihazında, **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' na gidin ve **kullanmaya** başlayın ' ı seçin. Windows bir ınsider olarak kaydetmek için kullandığınız hesabı bağlayın.

> [!NOTE]
> Cihazınızı Insider Derlemeleriyle kaydetmek için isteğe bağlı Telemetriyi etkinleştirmeniz gerekir. bunu yapmadıysanız, Ayarlar uygulamasını açın ve **gizlilik**  ->  **tanılama & geri bildirimi** ' ni seçin ve **isteğe bağlı tanılama verileri**' ni seçin.

Windows ınsider artık kanallara taşınıyor. **Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur. Bu, eşlemenin şöyle görünür:

![Windows Insider kanalları açıklaması.](images/WindowsInsiderChannels.png)

daha fazla bilgi için bkz. Windows bloglarda [Windows ınsider kanalları tanıtma](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .
sonra, **Windows için etkin geliştirme**' yı seçin, **Dev kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.
**> şimdi yeniden başlatmak Için Onayla** ' yı seçin. cihazınız yeniden başlatıldıktan sonra, **Ayarlar > güncelleştirme & güvenlik** ' e gidin > en son derlemeyi almak için güncelleştirmeleri denetleyin.

### <a name="update-error-0x80070490-work-around"></a>Güncelleştirme hatası 0x80070490 iş-etrafında

Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli işleri deneyin. Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.

#### <a name="stage-one---release-preview"></a>Aşama tek sürüm önizlemesi

1. Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **yayın önizleme kanalını** seçin.

2. Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**. Güncelleştirme sonrasında, ikinci aşamada devam edin.

#### <a name="stage-two---dev-channel"></a>İkinci geliştirme kanalı aşaması

1. Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **geliştirme kanalı**' nı seçin.

2. Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.

## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve Flash yönleri

Bir uçuş imzalı FFU ile test etmek için önce, uçuşdan ayrılmadan önce cihazınızın kilidini açmanız gerekir.

1. BILGISAYAR üzerinde:
    1. Hesabınızı ' den bilgisayarınıza indirin [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Microsoft Store: ile yay (Gelişmiş kurtarma Yardımcısı) yüklemesini yapın [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. HoloLens uçuşlamada kilit açma: **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' nı açın ve cihazı yeniden başlatın.

1. Flash FFU-şimdi yay kullanarak uçuştan imzalanmış FFU 'yi yakıp sönebilir.

### <a name="provide-feedback-and-report-issues"></a>Geri bildirim ve rapor sorunları sağlama

geri bildirim ve rapor sorunları sağlamak için lütfen HoloLens [geri bildirim merkezi uygulamasını](hololens-feedback.md) kullanın. Geri Bildirim Hub 'ı kullanmak, mühendislerimizin hata ayıklamasına ve sorunu çözmeye yardımcı olmak için gerekli tüm tanılama bilgilerinin eklenmesini sağlar.  HoloLens çince ve japonca sürümü ile ilgili sorunlar aynı şekilde bildirilmelidir.

> [!NOTE]
> Belge klasörünüze geri bildirim hub 'ı (sorulduğunda **Evet** ' i seçin) isteyip istemediğinizi soran istemi kabul ettiğinizden emin olun.

## <a name="note-for-developers"></a>Geliştiriciler için göz önünde

HoloLens Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemeye hoş geldiniz ve önerilir.  başlamak için [HoloLens geliştirici belgelerine](https://developer.microsoft.com/windows/mixed-reality/development) göz atın. Aynı yönergeler HoloLens Insider Derlemeleriyle birlikte çalışır.  HoloLens geliştirme için kullanmakta olduğunuz Unity ve Visual Studio derlemelerin aynısını kullanabilirsiniz.

## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdur

artık Windows Holographic ınsider derlemelerini almak istemiyorsanız, HoloLens bir üretim derlemesi çalıştırırken devre dışı bırakabilirsiniz veya cihazınızı Windows Holographic 'ın ınsider sürümüne kurtarmak için gelişmiş kurtarma yardımcısı 'nı kullanarak [cihazınızı kurtarabilirsiniz](hololens-recovery.md) .

> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydolmamış kullanıcıların mavi bir ekran deneymesinin bilinen bir sorunu vardır. Daha sonra cihazlarını el ile kurtarmanız gerekir. Etkilenmiş olmanız veya olmadıysanız ilgili tüm ayrıntılar için lütfen bu [bilinen sorunu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)izleyin.

HoloLens bir üretim derlemesi çalıştırdığından emin olmak için:

1. **Ayarlar > sistem >**' e gidin ve derleme numarasını bulun.

1. [Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).

Insider derlemelerini devre dışı bırakmak için:

1. üretim yapısını çalıştıran bir HoloLens, **Ayarlar > & güvenlik > Windows ınsider programı**' na gidin ve **ınsider derlemelerini durdur**' u seçin.

1. Cihazınızı devre dışı bırakmak için yönergeleri izleyin.
