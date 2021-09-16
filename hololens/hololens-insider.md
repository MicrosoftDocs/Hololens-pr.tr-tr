---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleriyle çalışmaya başlamayı öğrenin ve yeni işletim sistemi güncelleştirmemiz için değerli geri HoloLens.
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
ms.openlocfilehash: e3b067987fb339bc070fcb64ed01c28dee21ec35
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833548"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview derlemeleri için hoş geldiniz! Hızlı bir şekilde çalışmaya [başlamanız ve bir](hololens-insider.md#start-receiving-insider-builds) sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider Sürüm Notları

Windows Insiders'a yeni özellikler Windows heyecanlanıyoruz. En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır. Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme ekley in bu sayfayı güncelleştirmeye devam edeceğiz. Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun.

Bu, geliştirilmiş sorun giderme ve cihaz raporları, bilgi noktası modundaki bazı düzeltilen hatalar ve sertifika görüntüleyici, genişletilmiş yönetilebilirlik yüzeyi ve artan güncelleştirme güvenilirliğiyle ilgili. Bu özellik güncelleştirmenin yeni bir önemli özelliği, HoloLens Platform Modumuzdur. HoloLens 2 için tüm yeni harika özelliklere göz at!

| Özellik                 | Açıklama                | Kullanıcı veya Senaryo | Derleme tanıtıldı |
|-------------------------|----------------------------|--------------|------------------|
| [Platform Modunu Taşıma](#moving-platform-mode) | Yapılandırıldığında, düşük dinamik hareketle karşılaşan büyük deniz HoloLens 2'nin kullanımını sağlayan Hareketli Platform Modu beta sürümü tanıtıldı. | Tümü | 20348.1411 |
| [Sertifika Yöneticisi için PFX dosyası desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleme | Son Kullanıcı | 20348.1405 |
| [Raporlarda gelişmiş tanılama Ayarlar görüntüleme HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazda MDM tanılama günlüklerini görüntüleme | Sorun giderme | 20348.1405 |
| [Çevrimdışı Tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için görsel geri bildirim | Sorun giderme | 20348.1405 |
| [Düşük depolama günlüğü toplama geliştirmeleri](#low-storage-log-collection-improvements) | Düşük depolama durumlarında günlük toplama senaryolarında iyileştirmeler. | Sorun giderme | 20348.1412 |
| [Rapor ayrıntıları için CSP HoloLens değişiklikleri](#csp-changes-for-reporting-hololens-details) | Veri sorgulamak için için yeni CSP'ler | IT Yöneticileri    | 20348.1403                 |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Bir hesapta otomatik olarak oturum açmak için kullanılır | IT Yöneticileri | 20348.1405 |
| [Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri](#improved-update-restart-detection-and-notifications) | Güncelleştirmeler için yeni etkin ilkeler ve UX. | IT Yöneticileri | 20348.1405 |
| [Uygulama güncelleştirmeleri için Akıllı Yeniden Deneme](#smart-retry-for-app-updates) | IT Yöneticilerinin uygulamaları güncelleştirmek için zamanlanmış yeniden denemeler denemelerini sağlar. | IT Yöneticileri | 20348.1405 |
| [Yalnızca özel mağaza uygulamalarını yalnızca özel mağaza Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluş uygulamalarını gösterecek şekilde yapılandırma | BT Yöneticisi | 20348.1408 |
| [WDAC ve LOB uygulamalarını kullanma](#use-wdac-and-lob-apps) | IT Yöneticilerinin kendi uygulamalarını kullanmalarına ve diğer uygulamaları engellemek için WDAC kullanmalarına izin verir. | IT Yöneticileri | 20348.1405 |
| [Düzeltmeler ve geliştirmeler](#fixes-and-improvements) | Düzeltmeler ve geliştirmeler HoloLens. | Tümü | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>IT Yöneticisi Insider Özellik Denetim Listesi

✔️ Otomatik olarak oturum açmak için tek bir Azure AD hesabı ayarlamak için bu yeni [CSP'yi yapılandırabilirsiniz.](#auto-login-policy-controlled-by-csp) <br>
✔️ güncelleştirme başarısız olduktan sonra uygulamalarınızı otomatik olarak güncelleştirmeyi denemek üzere yapılandırmak için akıllı yeniden deneme için bu [yeni CSP'yi ayarlayın.](#smart-retry-for-app-updates) <br>
✔️ işletim sistemi güncelleştirmeleri üzerinde daha fazla denetime sahip olmak için bu yeni etkinleştirilen Güncelleştirme [ilkelerine göz atabilirsiniz.](#improved-update-restart-detection-and-notifications) <br>
✔️ Kuruluş uygulamalarını Microsoft Store aracılığıyla şirket mağazasında kullanılabilir hale Microsoft Store ancak tam mağazaya değil yalnızca kuruluş uygulamalarına erişim izni vermek istemeniz gerekirse bu [ilkeyi ayarlayın.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ depolama alanı, SSID veya BSSID bilginiz varsa bu HoloLens CSP'leri [kontrol edin.](#csp-changes-for-reporting-hololens-details) <br>
✔️ uygulamaların veya işlemlerin başlatılmasını engellemek için WDAC kullanmak, ancak aynı zamanda kendi iş dalı uygulamalarınızı kullanmak zorundasanız, artık WDAC ilkenize LOB'a izin [veabilirsiniz.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platform Modunu Taşıma

**Insider derlemesi 20348.1411'den** sonra, HoloLens 2'de düşük dinamik hareket hareketli platformlarında izlemeye yönelik beta desteği ekledik. Derlemeyi yükleyerek Platform Modu'na taşımayı etkinleştirdikten sonra, HoloLens 2'nizi büyük gemiler ve büyük deniz gemileri gibi daha önce erişilemeyen ortamlarda kullanabilirsiniz. Şu anda bu özellik yalnızca bu hareketli platformların etkinleştirilmesini hedeflemektedir. Özelliği başka ortamlarda kullanmaya çalışmanıza engel olan bir şey yoktur ancak özellik önce bu ortamlar için destek eklemeye odaklanmaktadır.

Desteklenenler ve bu yeni özelliği etkinleştirme hakkında daha fazla bilgi edinmek [için, hareketli platform sayfasını ziyaret edin.](hololens2-moving-platform.md)

#### <a name="overview-to-try-out-moving-platform-mode"></a>Platform Modunu Taşımayı denemek için genel bakış

1. [Geliştirici modunu ve cihaz portalını etkinleştirin.](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. [Platform modunu Cihaz portalı aracılığıyla taşımayı etkinleştirin.](hololens2-moving-platform.md#enabling-moving-platform-mode)
1. Cihazınızı büyük hareketli platforma getirin ve kararlı hologramların ne kadar kararlı olduğunu gözlemler.

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosyası desteği

Windows Insider derlemesi 20348.1405'te tanıtıldı. Artık .pfx sertifikalarını [kullanmak için](certificate-manager.md) Sertifika Yöneticisi'ne destek ekledik. Kullanıcılar Güvenlik Sertifikalarını Ayarlar'& ve Sertifika yükle'yi seçerek kullanıcı arabirimi  >    >  artık .pfx sertifika dosyasını destekliyor. 
Kullanıcılar özel anahtarla .pfx sertifikasını kullanıcı deposuna veya makine deposuna aktarabilirsiniz.

#### <a name="overview-to-try-out-pfx-files-in-certificate-manager"></a>Sertifika Yöneticisi'nde PFX dosyalarını denemek için genel bakış

1. PFX dosyanızı hazırlayın.
1. Dosyayı USB-C kablosu aracılığıyla cihazınıza kopyalayın.
1. Uygulama Ayarlar açın, Sertifika [Yöneticisi'ne gidin](certificate-manager.md) ve sertifikayı uygulama.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Raporlarda gelişmiş tanılama Ayarlar görüntüleme HoloLens

Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır. Bu yeni özellikle daha önce, Ayarlar Hesapları Erişim iş veya okul üzerinden toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra bu bilgilerin **cihazdan** MDM aracılığıyla veya cihazın yakınından görüntülenmeleri gerekirdi ve Yönetim günlüklerinizi dışarı aktar'ı seçin ve yakındaki bir  ->    >  pc'de görüntüleyebilirsiniz. 

Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz. MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.** Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.

![Gelişmiş tanılama raporunu uygulamanın Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Gelişmiş tanılama raporunu denemek için genel bakış

1. Ayarlar uygulamasını açın.
1. Hesaplar sayfasına gidin ve yeni bağlantıya tıklayarak **Yönetim günlüklerinizi dışarı aktarın**.
1. Cihazınızın yapılandırmalarında Gelişmiş bilgileri görüntüleyin.

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı tanılama bildirimleri

Bu, [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)adlı mevcut bir özelliğe yönelik bir güncelleştirmedir. Daha önce, kullanıcıların tanılama toplamayı tetiklediği veya tamamladığı üzerinde hiçbir açık gösterge yoktu.
artık Windows ınsider derlemeleriyle birlikte çevrimdışı tanılama için iki tür audiogörsel geri bildirimi vardır. Koleksiyon başladığında ve tamamlandığında, her ikisi için de her ikisi için bir bildirim görüntülendi. Bunlar Kullanıcı oturum açtığında görüntülenir ve görseller vardır.

![Günlüklerin toplanması için bildirim.](./images/logcollection1.jpg)

![Günlük toplama tamamlandığında bildirim.](./images/logcollection2.jpg)

Kullanıcılar, bir görüntüleme erişimi olmayan için bir geri dönüş günlüğü toplama mekanizması olarak çevrimdışı tanılama kullandığından, oturum açma veya hala OOBE 'de yer alma, Günlükler toplandığında yürütülen bir ses destesi de olacaktır. Bu ses, bildirim bildirimine ek olarak çalınacaktır.

Bu yeni özellik, cihazınız güncelleştirildiğinde etkinleştirilecek ve etkinleştirilmesi veya yönetilmesi gerekmez. Bu yeni geri bildirimin görüntülenemediğini veya duyulmayacak herhangi bir olayda, çevrimdışı tanılama yine de oluşturulacaktır.

Daha yeni bir audiogörsel geri bildirimi eklenmesini umuyoruz ve daha hızlı bir şekilde Tanılama verileri toplanmanız ve sorunlarınızı giderebilmek daha kolay olacaktır.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Tanılama bildirimlerini denemek için genel bakış

1. Cihazınızın kilidini açın ve bunu aşın.
1. [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)toplamak için **Güç** ve **ses aşağı** düğmesi birleşimine basın.
1. Cihazınızın başlatıldığı ve günlüklerin toplanması tamamlandığında bildirim bildirimlerini görüntüleyin ve ses ipuçlarını dinleyin.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü koleksiyonu geliştirmeleri

Tanılama günlükleri toplandığında bir cihazın disk alanında yetersiz olduğu durumlarda, **StorageDiagnostics.zip** adlı ek bir rapor oluşturulur. düşük depolama eşiği Windows [depolama alanı algılaması](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)tarafından otomatik olarak belirlenir.

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Düşük depolama geliştirmelerini denemek için genel bakış

1. Cihazınızın depolama alanını doldurup dolduralım.
1. [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)toplamak için **Güç** ve **ses aşağı** düğmesi birleşimine basın.
1. HoloLens belgeler klasöründe depolanan Günlükler koleksiyonunda yeni bir dosya olduğunu gözlemleyin.

### <a name="csp-changes-for-reporting-hololens-details"></a>raporlama HoloLens ayrıntıları için CSP değişiklikleri

- Windows ınsider derlemesinde tanıtılan, 20348,1403

aşağıdaki csp 'ler HoloLens cihazlarınızdan bilgi bildirmenin yeni yollarla güncelleştirilmiştir.

#### <a name="devdetail-csp---free-storage"></a>devdetail CSP-ücretsiz Depolama

devdetail CSP artık HoloLens cihazda boş depolama alanı da bildiriyor. bu, Ayarlar uygulamanın Depolama sayfasında gösterilen değerle yaklaşık olarak eşleşmelidir. Bu bilgileri içeren belirli düğüm aşağıda verilmiştir.

- ./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP-SSID ve BSSıD

devicestatus CSP artık, HoloLens etkin bir şekilde bağlandığı Wi-Fi ağının ssıd ve bssıd 'sini de raporluyor. Bu bilgileri içeren belirli düğümler aşağıda verilmiştir.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/b SSID 'si

Networktanımlayıcılarına yönelik sorgu için örnek SyncML Blobu (MDM satıcıları için)

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

Bu yeni otomatik LogonUser ilkesi, bir kullanıcının otomatik olarak oturum açıp açmamayacağını denetler. Bazı müşteriler bir kimliğe bağlı olan ancak herhangi bir oturum açma deneyimini istemediğiniz cihazları ayarlamak ister. bir cihaz Imagine ve hemen uzaktan yardım 'ı kullanarak. ya da HoloLens cihazları hızla dağıtabilecek ve son kullanıcılarının oturum açma sürecini hızlandırmalarına olanak tanıtabilen bir avantajınız vardır.

İlke boş olmayan bir değere ayarlandığında, otomatik oturum açan kullanıcının e-posta adresini belirtir. Otomatik oturum açmayı etkinleştirmek için belirtilen kullanıcının cihazda en az bir kez oturum açması gerekir.

Yeni ilke dizesi değerinin OMA-URI 'SI `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`

- Aynı e-posta adresine sahip kullanıcı otomatik oturum açma özelliği etkin olacaktır.

Bu ilkenin yapılandırıldığı bir cihazda, ilkede belirtilen kullanıcının en az bir kez oturum açması gerekir. İlk oturum açma işleminden sonra cihazın sonraki yeniden başlatmaları belirtilen kullanıcı tarafından otomatik olarak oturum açar. Yalnızca tek bir otomatik oturum açma Kullanıcı desteklenir. Etkinleştirildikten sonra otomatik olarak oturum açan kullanıcı el ile oturum açamaz. Farklı bir kullanıcı olarak oturum açmak için, önce ilkenin devre dışı bırakılması gerekir.

> [!NOTE]
>
> - Ana işletim sistemi güncelleştirmeleri gibi bazı olaylar, otomatik oturum açma davranışını yeniden başlatmak için belirtilen kullanıcının cihazda yeniden oturum açmasını gerektirebilir.
> - Otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için desteklenir.

#### <a name="overview-to-try-auto-logon-csp"></a>Otomatik oturum açma CSP 'sini denemeye genel bakış

1. Yeni CSP 'yi [özel bir ilke kullanarak](/mem/intune/configuration/custom-settings-windows-10) istenen bir kullanıcıya yapılandırın: `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. CSP 'yi [sağlama paketi](hololens-provisioning.md) veya [MDM](hololens-mdm-configure.md)aracılığıyla cihaza uygulayın.
1. Belirtilen hesapta oturum açın.
1. Cihazı yeniden başlatın ve kullanıcının otomatik olarak oturum açtığını gözlemleyin.

### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

etkin saatler ve yüklemesi zaman ilkeleri arasında, kullanımda olduklarında HoloLens cihazların yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklenmesini tamamlaması durumunda yeniden başlatmalar gerçekleşmezseniz güncelleştirmelerin benimsenmesini de erteler. Artık, son tarihleri ve gerekli YENIDEN başlatmalar zorlayabilmesini ve bir güncelleştirme yüklemesinin zamanında tamamlandığından emin olmak için ilkeler ekledik. Kullanıcılardan önyükleme başlatılmadan önce bildirim alabilir ve BT ilkesine uygun olarak yeniden başlatma işleminin geciktirebilirler.

Aşağıdaki güncelleştirme ilkeleri eklendi:

- [Güncelleştirme/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Güncelleştirme/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Güncelleştirme/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Güncelleştirme/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Güncelleştirme/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Güncelleştirme/Configuredeadlinenooto reboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Güncelleştirme/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Güncelleştirme/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Güncelleştirme/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

#### <a name="overview-to-try-new-update-notifications"></a>Yeni güncelleştirme bildirimlerini denemek için genel bakış

1. Yeni güncelleştirme CSP 'Lerden birini [sağlama paketi](hololens-provisioning.md) veya [MDM](hololens-mdm-configure.md) aracılığıyla yapılandırın (yukarıdaki bağlantı listesine bakın ve bir tane seçin).
1. Zamanlanan sürede cihazı kullanın.
1. Kullanıcıya güncelleştirme hakkında bildirim gönderilmesini ve cihazı yeniden başlatma gereksinimini gözlemleyin \* .

\* Sonuçlarınız, kullanılan güncelleştirme ilkelerine göre farklılık gösterebilir.

### <a name="smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için akıllı yeniden deneme

HoloLens için etkin olan, bt yöneticilerinin güncelleştirme uygulanmasına izin verirken güncelleştirilmesi başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir zaman tarihi ayarlamasına izin veren yeni bir ilkedir. Bunlar, zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilir. Bu ilkenin nasıl kullanılacağı hakkında daha fazla bilgi edinmek için [ApplicationManagement/Scheduleforcerestartforupdatearızaları](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)' ne bakın.

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için akıllı yeniden denemeyi denemeye genel bakış

1. Yeni akıllı yeniden deneme özelliğini yapılandırın.
1. Uygulamanızı henüz almamış ve doğru şekilde yapılandırılmış bir cihazda çevrimiçi ortamda oturum açın.
1. Cihazı kapatma veya bağlantısını kesme yoluyla uygulamayı indiremiyor.
1. Cihazınızı açık bir şekilde kapatıp, yükleme işlemini yeniden denemek için tetiklediğiniz zamanda internet 'e bağlanın.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın

RequirePrivateStoreOnly ilkesi HoloLens için etkinleştirildi. bu ilke, Microsoft Store uygulamasının yalnızca kuruluşunuz için yapılandırılmış özel mağazayı gösterecek şekilde yapılandırılmasını sağlar. Erişimi yalnızca kullanılabilir hale getirdiğiniz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)hakkında daha fazla bilgi edinin.

#### <a name="overview-to-try-only-private-store-apps"></a>Yalnızca özel mağaza uygulamalarını denemeye genel bakış

1. [MDM](hololens-mdm-configure.md)aracılığıyla cihazlarınız için yeni ilkeyi yapılandırın.
1. İlkeye sahip bir cihazda oturum açın.
1. Microsoft Store uygulamasını açın ve kuruluşunuzun uygulamalarını görebilmenizi sağlayabilirsiniz.

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
