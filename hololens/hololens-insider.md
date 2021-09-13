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
ms.date: 09/10/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 84ec45a4bb05eb28106e4bfdc915a18ae6330767
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033275"
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
✔️ işletim sistemi güncelleştirmeleri üzerinde daha fazla denetime sahip olmak istiyorsanız, bu [Yeni etkinleştirilmiş güncelleştirme ilkelerine](#improved-update-restart-detection-and-notifications) göz atın. <br>
✔️ kuruluşunuzun uygulamalarını, Microsoft Store aracılığıyla şirket mağazasının kullanımına sunmak, ancak yalnızca kuruluşunuzun uygulamalarına erişime izin vermek ve tam mağaza değil olmak istiyorsanız, [bu ilkeyi ayarlayın.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ boş depolama alanını, HoloLens cihazlarınızın ssıd veya bssıd 'sini öğrenmek isterseniz, bu [raporlama csp 'lerine](#csp-changes-for-reporting-hololens-details) göz atın. <br>
✔️ uygulamaların veya işlemlerin başlatılmasını engellemek için WDAC kullanmak istiyorsanız, ancak aynı zamanda kendi iş kolu uygulamalarınızı kullanmanız gerekiyorsa, artık [WDAC ILKENIZDE lob 'a izin](#use-wdac-and-lob-apps)verebilirsiniz.

### <a name="moving-platform-mode"></a>Platform modu taşınıyor

**ınsider build 20348,1411** itibariyle, HoloLens 2 ' de düşük dinamik hareket taşınan platformları izlemek için beta desteği ekledik. derlemeyi yükledikten ve platformu taşıma modunu etkinleştirdikten sonra, büyük ve büyük deniz mavisi gibi daha önce erişilemeyen ortamlarda HoloLens 2 ' yi kullanabilirsiniz. Şu anda özelliği, yalnızca bu taşıma platformlarının etkinleştirilmesini hedeflenmiştir. Başka ortamlarda özelliği kullanmayı denediğinize hiçbir şey engel olmadıysa, bu özellik önce bu ortamlar için destek eklemeye odaklanılmıştır.

Nelerin desteklendiği ve bu yeni özelliğin nasıl etkinleştirileceği hakkında daha fazla bilgi edinmek için, [hareketli platform sayfasını ziyaret edin.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosya desteği

Windows ınsider build 20348,1405 ' de kullanıma sunulmuştur. Artık. pfx sertifikalarını kullanacak şekilde [sertifika yöneticisine](certificate-manager.md) destek ekledik. kullanıcılar **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **sertifikalarına** gezindiğinde ve **sertifikayı yükler** ' i seçtiğinizde, kullanıcı arabirimi artık. pfx sertifika dosyasını destekliyor.
Kullanıcılar, özel anahtarla, Kullanıcı deposuna veya makine deposuna. pfx sertifikasını içeri aktarabilir.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle

Yönetilen cihazlar için sorun giderme sırasında, beklenen bir ilke yapılandırmasının uygulandığını onaylayan önemli bir adımdır. daha önce bu yeni özellik için, bu bilgilerin görüntülenmesi, **Ayarlar** hesapları aracılığıyla toplanan mdm tanılama günlüklerini dışarı aktardıktan sonra iş veya okul aracılığıyla cihazın yakınında veya cihazın yakınında yapılması gerekiyordu  ->    >  ve **yönetim günlüklerinizi dışa aktarıp** yakındaki bir bilgisayarda görüntülenmiş olarak.

Artık MDM Tanılaması, Edge tarayıcısı kullanılarak cihazda görüntülenebilir. MDM Tanılama raporunu daha kolay bir şekilde görüntülemek için iş veya okul sayfasına gidin ve **Gelişmiş tanılama raporunu görüntüle**' yi seçin. Bu, raporu yeni bir kenar penceresinde oluşturur ve açar.

![Ayarlar uygulamasında gelişmiş tanılama raporunu görüntüleyin.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı tanılama bildirimleri

Bu, [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)adlı mevcut bir özelliğe yönelik bir güncelleştirmedir. Daha önce, kullanıcıların tanılama toplamayı tetiklediği veya tamamladığı üzerinde hiçbir açık gösterge yoktu.
artık Windows ınsider derlemeleriyle birlikte çevrimdışı tanılama için iki tür audiogörsel geri bildirimi vardır. Koleksiyon başladığında ve tamamlandığında, her ikisi için de her ikisi için bir bildirim görüntülendi. Bunlar Kullanıcı oturum açtığında görüntülenir ve görseller vardır.

![Günlüklerin toplanması için bildirim.](./images/logcollection1.jpg)

![Günlük toplama tamamlandığında bildirim.](./images/logcollection2.jpg)

Kullanıcılar, bir görüntüleme erişimi olmayan için bir geri dönüş günlüğü toplama mekanizması olarak çevrimdışı tanılama kullandığından, oturum açma veya hala OOBE 'de yer alma, Günlükler toplandığında yürütülen bir ses destesi de olacaktır. Bu ses, bildirim bildirimine ek olarak çalınacaktır.

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
- İlk kullanıcı oturum açma işlemi sonrasında AAD grup tabanlı bilgi noktası yapılandırmalarının kullanılıyor olduğu senaryolarda OOBE'nin sonlandırılma sorunu düzeltildi.
- Cihaz yeniden başlatma için güncelleştirme bildirimlerini ve iletişim kutusu istemlerini görüntülemeyle ilgili bir sorun düzeltildi.

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

1. Ayarlar, Güncelleştirme &' Windows Insider Programı Yayın Önizleme **Kanalı'Windows Insider Programı seçin.**

2. Ayarlar, Update & Security, Windows Update, **Check for updates**. Güncelleştirmeden sonra ikinci aşamaya devam et.

#### <a name="stage-two---dev-channel"></a>Aşama iki - Geliştirme Kanalı

1. Ayarlar, Güncelleştirme &' Windows Insider Programı Dev **Channel'ı seçin.**

2. Ayarlar, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve flash yönler

Uçuş imzalı ffu ile test etmek için, uçuş imzalı ffu'nun yanıp sönmeden önce cihazınızın kilidinin açılması gerekir.

1. Pc'de:
    1. ffu'dan bilgisayarınıza [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) indirin.

    1. Arc'ın (Gelişmiş Kurtarma Yardımcı) yüklemesi Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. HoloLens - Flight Unlock: **Ayarlar**  >  **Update &**  >  **Security'Windows Insider Programı** açın ve cihazı yeniden başlatın.

1. Flash FFU - Artık ARC kullanarak uçuş imzalı FFU'nun flash'unu sönersiniz.

### <a name="provide-feedback-and-report-issues"></a>Geri bildirim sağlama ve sorunları bildirme

Geri bildirim [ve Geri Bildirim Merkezi sağlamak](hololens-feedback.md) için HoloLens uygulama uygulamanızı kullanın. Bu Geri Bildirim Merkezi, mühendislerimizin hızla hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgileri dahil edilir.  Bu sürümün Çince ve Japonca HoloLens aynı şekilde bildiriliyor olması gerekir.

> [!NOTE]
> Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).

## <a name="note-for-developers"></a>Geliştiriciler için not

Uygulamalarınızı derlemenin Insider derlemelerini kullanarak geliştirmeyi denemeniz HoloLens.  Çalışmaya başlamaya [HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz. Bu yönergeler, bir derlemenin Insider derlemeleriyle HoloLens.  Unity ve Visual Studio derlemelerini kullanarak HoloLens kullanabilirsiniz.

## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdurma

Windows Holographic'in Insider derlemelerini artık almak istemiyorsanız, HoloLens'niz bir üretim derlemesi çalıştırıyorsa iptal [](hololens-recovery.md) edebilirsiniz veya Cihazınızı Gelişmiş Kurtarma Yardımcı'sı kullanarak kurtararak cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarabilirsiniz.

> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır. Daha sonra, cihazlarını el ile kurtarmaları gerekir. Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Bir üretim HoloLens çalıştığını doğrulamak için:

1. Ayarlar > **System > About 'a gidin** ve derleme numarasını bulun.

1. [Üretim derleme numaraları için sürüm notlarına bakın.](hololens-release-notes.md)

Insider derlemelerini geri almak için:

1. Üretim HoloLens çalıştıran bir Ayarlar > Update **& Security > Windows Insider Programı**'a gidin ve Insider derlemelerini **durdur'ı seçin.**

1. Cihazınızı geri almak için yönergeleri izleyin.
