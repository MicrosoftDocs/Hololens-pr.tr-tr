---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleriyle çalışmaya başlamayı öğrenin ve yeni işletim sistemi güncelleştirmemiz için değerli geri HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cabf35d44cdd144151e048d7a6e14e391629d00a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427080"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview derlemeleri için hoş geldiniz! Hızlı bir şekilde çalışmaya [başlamanız ve bir](hololens-insider.md#start-receiving-insider-builds) sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider Sürüm Notları

Windows Insiders'a yeni özellikler Windows heyecanlanıyoruz. En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır. Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme ekley Windows devam edeceğiz. Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun.

Bu, geliştirilmiş sorun giderme ve cihaz raporları, bilgi noktası modundaki bazı düzeltilen hatalar ve sertifika görüntüleyici, genişletilmiş yönetilebilirlik yüzeyi ve artan güncelleştirme güvenilirliğiyle ilgili. Bu özellik güncelleştirmenin yeni bir önemli özelliği, HoloLens Platform Modumuzdur. HoloLens 2 için tüm yeni harika özelliklere göz at!

| Özellik                 | Açıklama                | Kullanıcı veya Senaryo | Derleme tanıtıldı |
|-------------------------|----------------------------|--------------|------------------|
| [Platform Modunu Taşıma](#moving-platform-mode) | Yapılandırıldığında, düşük dinamik hareketle karşılaşan büyük deniz HoloLens 2'nin kullanımını sağlayan Hareketli Platform Modu beta sürümü tanıtıldı. | Tümü | 20348.1411 |
| [Sertifika Yöneticisi için PFX dosyası desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleme | Son Kullanıcı | 20348.1405 |
| [Gelişmiş tanılama raporunu Ayarlar'de HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazda MDM tanılama günlüklerini görüntüleme | Sorun giderme | 20348.1405 |
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
✔️ işletim sistemi güncelleştirmeleri üzerinde daha fazla denetime sahip olmak için bu yeni etkinleştirilen [Güncelleştirme ilkelerine göz atabilirsiniz.](#improved-update-restart-detection-and-notifications) <br>
✔️ Kuruluş uygulamalarını Microsoft Store aracılığıyla şirket mağazasında kullanılabilir hale Microsoft Store ancak tam mağazaya değil yalnızca kuruluş uygulamalarına erişim izni vermek istemeniz gerekirse bu [ilkeyi ayarlayın.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Depolama alanı, SSID veya BSSID cihazlarınızı bilmek HoloLens bu raporlama [CSP'lerini kontrol edin.](#csp-changes-for-reporting-hololens-details) <br>
✔️ uygulamaların veya işlemlerin başlatılmasını engellemek için WDAC kullanmak, ancak aynı zamanda kendi iş dalı uygulamalarınızı kullanmak zorundasanız, artık WDAC ilkenize LOB'a izin [veabilirsiniz.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Platform Modunu Taşıma

**Insider derlemesi 20348.1411'den** sonra, HoloLens 2'de düşük dinamik hareket hareketli platformlarında izlemeye yönelik beta desteği ekledik. Derlemeyi yükleyerek Ve Taşıma Platformu Modu'na etkinleştirdikten sonra, HoloLens 2'nizi büyük gemiler ve büyük deniz gemileri gibi daha önce erişilemeyen ortamlarda kullanabilirsiniz. Şu anda bu özellik yalnızca bu hareketli platformların etkinleştirilmesini hedeflemektedir. Özelliği başka ortamlarda kullanmaya çalışmanıza engel olan bir şey yoktur ancak özellik önce bu ortamlar için destek eklemeye odaklanmaktadır.

Desteklenenler ve bu yeni özelliği etkinleştirme hakkında daha fazla bilgi edinmek [için, hareketli platform sayfasını ziyaret edin.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosyası desteği

Windows Insider derlemesi 20348.1405'te tanıtıldı. Artık .pfx sertifikalarını [kullanmak için](certificate-manager.md) Sertifika Yöneticisi'ne destek ekledik. Kullanıcılar Güvenlik Sertifikalarını Ayarlar'&'a gidin ve Sertifika yükle'yi seçerek kullanıcı arabirimi  >    >  artık .pfx sertifika dosyasını destekliyor. 
Kullanıcılar özel anahtarla .pfx sertifikasını kullanıcı deposuna veya makine deposuna aktarabilirsiniz.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Gelişmiş tanılama raporunu Ayarlar'de HoloLens

Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır. Bu yeni özellikle daha önce, Ayarlar Hesapları Erişim iş veya okul üzerinden toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra bu bilgilerin **cihazdan** MDM aracılığıyla veya cihazın yakınından görüntülenmeleri gerekirdi ve Yönetim günlüklerinizi dışarı aktar'ı seçin ve yakındaki bir  ->    >  pc'de görüntüleyebilirsiniz. 

Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz. MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.** Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.

![Gelişmiş tanılama raporunu uygulamanın Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı Tanılama bildirimleri

Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics) Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.
Artık Insider Windows eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır. Birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)

Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü toplama geliştirmeleri

Tanılama günlükleri toplanmışken cihazın disk alanı düşük gibi görünen senaryolarda,StorageDiagnostics.zipadlı **ek** bir rapor oluşturulur. Düşük depolama eşiği, depolama alanı algısı Windows [olarak belirlenir.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

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

### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

Etkin saatler ve yükleme zamanı ilkeleri arasında, cihazların kullanım sırasında HoloLens yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklemesini tamamlamak için yeniden başlatmalar oluşmazsa güncelleştirmelerin benimsenmesi de geciker. Şimdi, IT'nin son tarihleri ve gerekli yeniden başlatmaları zorlamasına ve güncelleştirme yükleme işleminin zamanında tamamlandığından emin olmasına olanak sağlayan ilkeler ekledik. Kullanıcılara, yeniden başlatma işlemi başlatmadan önce bildirebilirsiniz ve kullanıcılar, YENIDEN başlatmayı IT ilkesine uygun olarak geciktirebilirsiniz.

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

### <a name="smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için Akıllı Yeniden Deneme

Artık HoloLens için etkinleştirilen yeni bir ilke, IT Yöneticilerinin, güncelleştirmenin uygulamaya uygulanmasına izin verme nedeniyle başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir saat tarihi ayarlamasını sağlayan yeni bir ilkedir. Bunlar zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilirsiniz. Bu ilke görünümünü kullanma hakkında daha fazla bilgi edinmek için [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures).

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Yalnızca özel mağaza uygulamalarını Microsoft Store

RequirePrivateStoreOnly ilkesi, HoloLens. Bu ilke, Microsoft Store uygulamasının yalnızca özel mağazayı gösterecek şekilde yapılandırılması için yapılandırmanıza olanak sağlar. Erişimi yalnızca kullanılabilir yapmış olduğunuz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly hakkında daha fazla bilgi](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>WDAC ve LOB uygulamalarını kullanma

Artık WDAC'i kullanarak uygulamaların veya işlemlerin başlatılmasını engelleyebilir ve kendi hazır olma uygulamalarınızı kullanmaya devam edersiniz. Artık WDAC ilkeniz içinde bu ilkelere izin vesersiniz. Bu ilkeyi kullanmak, WDAC ilkenizi oluştururken PowerShell'de fazladan bir kod satırı çalıştırmayı içerir. [Buradaki adımları gözden geçirme.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler

- Kilitlenmiş [dosyaları indirme istemi Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Cihazlardan uyumluluk özelliklerini raporlamayla ilgili HoloLens ele; Insider derlemeleri üzerinde doğru raporlamanın tetiklanması için yeniden başlatma gerekebilir.  
- Atanmış Erişim [API'sini](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) etkinleştirdikten sonra uygulamalar artık HoloLens oturum açmış olan kullanıcı için bilgi noktası modunda bir uygulamanın HoloLens.
- Remote Assist'in yeni flash görüntülere yüklenmiş olan in-box sürümü güncelleştirildi.
- 2D uygulamalar için gamepad işleme, Insider derlemelerde devre dışı bırakıldı. Uygulamalar artık bu api'leri kaldırarak doğrudan Gamepad API'lerini kullanabilir, tüm denetim kümesine erişime sahip olur ve ne yapmak isterse onu yapar. Geliştiricilerin Gamepad girişini kullanmak için Gamepad API'lerini kullanmaları gerekir. Gamepad Sınıfı [(Windows. Gaming.Input) - Windows UWP uygulamaları](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlama

> [!NOTE]
> Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.
>
> - "Cihazı yeniden başlat" sesli komutu iyi çalışıyor.
> - Ayrıca, Ayarlar/Windows Insider Programı.
>
> Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.

Bir HoloLens 2 cihazında Ayarlar   >  **Update & Security Windows Insider Programı'a** gidin ve  >   Kullanmaya başlayın.  Windows Insider olarak kaydetmek için kullanılan hesabı bağlama.

Windows artık Kanallar'a taşınıyor. Hızlı **halka** Geliştirme Kanalı, Yavaş  halka Beta Kanal olur **ve** **Yayın** Önizleme halkası Yayın Önizleme Kanalı **olur.** Eşleme şu şekildedir:

![Windows Insider Channels açıklaması.](images/WindowsInsiderChannels.png)

Daha fazla bilgi için [bkz. Bloglarda Windows Insider Kanallarına](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows.
Ardından, **geliştirmenin etkin Windows'ı** seçin, **Dev Channel'ı** mı yoksa derlemeleri mi **almak Beta Kanal** seçin ve program koşullarını gözden geçirin.
Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin. Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak Ayarlar > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.

### <a name="update-error-0x80070490-work-around"></a>Hata güncelleştirme 0x80070490 çalışma

Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli çalışmayı deneyin. Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.

#### <a name="stage-one---release-preview"></a>1. aşama - Yayın Önizlemesi

1. Ayarlar Update & Security Windows Insider Programı **Release Preview Channel (Yayın Önizleme Kanalı) öğesini seçin.**

2. Ayarlar, Update & Security, Windows Update, **Check for updates**. Güncelleştirmeden sonra ikinci aşamaya devam et.

#### <a name="stage-two---dev-channel"></a>Aşama iki - Geliştirme Kanalı

1. Ayarlar, Güncelleştirme &' Windows Insider Programı Dev **Channel'ı seçin.**

2. Ayarlar, Update & Security, Windows Update, **Check for updates**.

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
