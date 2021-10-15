---
title: HoloLens 2 sürüm notları
description: her yeni HoloLens 2 sürümündeki tüm güncelleştirmelerle güncel kalın.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/12/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 3f5e5f3e38c24805935fc69dfacd5eac93ddd017
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034289"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarınızla üretken bir deneyiminizin olduğundan emin olmak için özellik, hata ve güvenlik güncelleştirmelerini serbest bırakmaya devam ediyoruz. bu sayfada, her ay HoloLens yenilikleri görebilirsiniz. en son HoloLens 2 güncelleştirmesini almak için güncelleştirmeleri denetleyebilir ve [gelişmiş kurtarma yardımcısı aracılığıyla cihazınızı flash](hololens-recovery.md#clean-reflash-the-device) [ile el ile güncelleştirebilir](hololens-update-hololens.md#check-for-updates-and-manually-update) veya tam flash güncelleştirmesi (ffu) alabilirsiniz. [İndirme](https://aka.ms/hololens2download) güncel tutulur ve en son genel kullanıma sunulan derlemeyi sağlar.

> [!NOTE]
> son Windows 11 duyurusu, Windows bilgisayar sürümüne odaklanmıştı. son zamanlarda [2021 ekim ' de 2 ' ye HoloLens 2 ' ye büyük bir işletim sistemi güncelleştirmesi](#windows-holographic-version-21h2)başladık ve müşteri geri bildirimlerine göre daha yaklaşan yayınlar üzerinde çalışıyoruz.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, sürüm 21H2

- Derleme 20348,1432

Windows Holographic sürüm 21h2 artık kullanılabilir ve 2 kullanıcı ve bt uzmanlarına HoloLens harika yeni özellikler sunuyor. Bu, geliştirilmiş sorun giderme ve cihaz raporları, bilgi noktası modundaki bazı sabit hatalar ve sertifika Görüntüleyicisi, genişletilmiş yönetilebilirlik yüzeyi ve artırılmış güncelleştirme güvenilirliği hakkında bilgi sunar. bu özellik güncelleştirmesinin yeni bir flaggeme özelliği, hareketli Platform modumuza HoloLens geliyor. HoloLens 2 ' nin tüm yeni harika özelliklerine göz atın!

bu en son sürüm 21h1 sürümüne yönelik aylık bir güncelleştirmedir, ancak bu kez yeni özellikler ekledik, çünkü bu, önemli yapı numarası aynı kalacaktır ve Windows Update, sürüm 21h1 (derleme 20348) için aylık bir sürüm olduğunu gösterecektir. HoloLens 2 ayarları, bu yayına 21h2 olarak başvurduğumuz halde 21 h1 değerini de görüntüleyecektir. 21H2 aldığınızdan emin olmak için lütfen sürüm numarasının 20348,1432 veya daha yüksek olduğunu doğrulayın. en son kullanılabilir derleme 20348.1432 + ' de olduğunu onaylamak için Ayarlar > ekranında yapı numaranızı görebilirsiniz.

en son sürüme güncelleştirmek için Ayarlar uygulamasını açın, güncelleştirme & güvenlik ' e gidin ve güncelleştirmeler için denetle ' ye dokunun. HoloLens güncelleştirmelerinin nasıl yönetileceği hakkında daha fazla bilgi için, [HoloLens güncelleştirmelerini yönet](hololens-updates.md) ' e gidin.

| Özellik                 | Açıklama                | Kullanıcı veya senaryo |
|-------------------------|----------------------------|--------------|
| [Platform modu taşınıyor](#moving-platform-mode) | yapılandırıldığında, büyük deniz mavisi ' de düşük dinamik hareket yaşayan HoloLens 2 ' nin kullanımını sağlayan Platform modu beta 'yı tanıtır. | Tümü |
| [Sertifika Yöneticisi için PFX dosya desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleyin | Son Kullanıcı |
| [HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazdaki MDM tanılama günlüklerini görüntüle | Sorun giderme |
| [Çevrimdışı tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için audiogörsel geri bildirimi | Sorun giderme |
| [Düşük depolama günlüğü koleksiyonu geliştirmeleri](#low-storage-log-collection-improvements) | Düşük depolama durumları sırasında günlük toplama senaryolarında iyileştirmeler. | Sorun giderme |
| [raporlama HoloLens ayrıntıları için CSP değişiklikleri](#csp-changes-for-reporting-hololens-details) | Verileri sorgulamak için yeni CSP 'Ler | BT yöneticileri    |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Hesapta otomatik olarak oturum açmak için kullanılır | BT yöneticileri |
| [Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri](#improved-update-restart-detection-and-notifications) | Güncelleştirmeler için yeni etkinleştirilen ilkeler ve UX. | BT yöneticileri |
| [Uygulama güncelleştirmeleri için akıllı yeniden deneme](#smart-retry-for-app-updates) | BT yöneticilerinin uygulamaları güncelleştirmek için yeniden denemelere izin verir. | BT yöneticileri |
| [Yalnızca Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluştan gelen uygulamaları gösterecek şekilde yapılandırma | BT Yöneticisi |
| [WDAC ve LOB uygulamalarını kullanma](#use-wdac-and-lob-apps) | BT yöneticilerinin kendi uygulamalarını kullanmasına izin verir ve diğer uygulamaları engellemek için yine de WDAC kullanır. | BT yöneticileri |
| [Düzeltmeler ve geliştirmeler](#fixes-and-improvements) | HoloLens düzeltmeler ve geliştirmeler. | Tümü |

### <a name="it-admin-feature-checklist"></a>BT Yöneticisi özellik denetim listesi

✔️ otomatik olarak oturum açmak için tek bir Azure AD hesabı ayarlamak isterseniz, [Bu yenı CSP 'yi yapılandırın.](#auto-login-policy-controlled-by-csp) <br>
✔️ güncelleştirme başarısız olduktan sonra uygulamalarınızı otomatik olarak güncelleştirmeye çalışacak şekilde yapılandırmak istiyorsanız, [Bu yenı CSP 'yi akıllı yeniden deneme için ayarlayın.](#smart-retry-for-app-updates) <br>
✔️ işletim sistemi güncelleştirmeleri üzerinde daha fazla denetime sahip olmak istiyorsanız, bu [Yeni etkinleştirilmiş güncelleştirme ilkelerine](#improved-update-restart-detection-and-notifications) göz atın. <br>
✔️ kuruluşunuzun uygulamalarını Microsoft Store aracılığıyla şirket mağazasındaki kullanılabilir duruma getirmeniz gerekiyorsa, ancak yalnızca kuruluşunuzun uygulamalarına erişime izin vermek ve tam mağaza değil olmak istiyorsanız, [bu ilkeyi ayarlayın.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ boş depolama alanını, HoloLens cihazlarınızın ssıd veya bssıd 'sini öğrenmek isterseniz, bu [raporlama csp 'lerine](#csp-changes-for-reporting-hololens-details) göz atın. <br>
✔️ uygulamaların veya işlemlerin başlatılmasını engellemek için WDAC kullanmak istiyorsanız, ancak aynı zamanda kendi iş kolu uygulamalarınızı kullanmanız gerekiyorsa, artık [WDAC ILKENIZDE lob 'a izin](#use-wdac-and-lob-apps)verebilirsiniz.

### <a name="moving-platform-mode"></a>Platform modu taşınıyor

[Windows Holographic, sürüm 21h2 '](hololens-release-notes.md#windows-holographic-version-21h2) den başlayarak, HoloLens 2 ' de düşük dinamik hareket taşıma platformlarındaki izleme için beta desteği ekledik. derlemeyi yükledikten ve platformu taşıma modunu etkinleştirdikten sonra, büyük ve büyük deniz mavisi gibi daha önce erişilemeyen ortamlarda HoloLens 2 ' yi kullanabilirsiniz. Şu anda özelliği, yalnızca bu taşıma platformlarının etkinleştirilmesini hedeflenmiştir. Başka ortamlarda özelliği kullanmayı denediğinize hiçbir şey engel olmadıysa, bu özellik önce bu ortamlar için destek eklemeye odaklanılmıştır.

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

Yönetilen cihazlar için sorun giderme sırasında, beklenen bir ilke yapılandırmasının uygulandığını onaylayan önemli bir adımdır. daha önce bu yeni özellik için, bu yeni özelliğe, **Ayarlar** hesapları aracılığıyla toplanan mdm tanılama günlüklerini dışarı aktardıktan sonra, bu yeni özelliğe cihaz yakınından veya cihazın yakınında yapılması gerekiyordu  ->    >  . 

Artık MDM Tanılaması, Edge tarayıcısı kullanılarak cihazda görüntülenebilir. MDM Tanılama raporunu daha kolay bir şekilde görüntülemek için iş veya okul sayfasına gidin ve **Gelişmiş tanılama raporunu görüntüle**' yi seçin. Bu, raporu yeni bir kenar penceresinde oluşturur ve açar.

![Ayarlar uygulamasında gelişmiş tanılama raporunu görüntüleyin.](./images/view-advanced-diagnostic-report.jpg)

#### <a name="overview-to-try-out-the-advanced-diagnostic-report"></a>Gelişmiş tanılama raporunu denemek için genel bakış

1. Ayarlar uygulamasını açın.
1. Hesaplar sayfasına gidin ve yeni bağlantıya tıklayarak **Yönetim günlüklerinizi dışarı aktarın**.
1. Cihazınızın yapılandırmalarında Gelişmiş bilgileri görüntüleyin.

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı tanılama bildirimleri

Bu, [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)adlı mevcut bir özelliğe yönelik bir güncelleştirmedir. Daha önce, kullanıcıların tanılama toplamayı tetiklediği veya tamamladığı üzerinde hiçbir açık gösterge yoktu.
Artık [Holographic Windows 21H2](hololens-release-notes.md#windows-holographic-version-21h2)sürümüne eklenmiştir. Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim yöntemi vardır. Birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)

Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

Bu bilgiler daha sonra tanılama günlükleri [sayfasında görüntüleyebilirsiniz.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Tanılama bildirimlerini denemek için genel bakış

1. Cihazınızın kilidini açın ve cihazı yıprandırabilirsiniz.
1. Çevrimdışı **Tanılamayı** toplamak **için Güç** ve Birim kapalı [düğme birleşimine basın.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Bildirimlere bakın ve cihazınızın ne zaman başladığına ve günlük toplamayı bitirip ne zaman tamamladığına ilgili sesli ipuçlarına bakın.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü toplama geliştirmeleri

Tanılama günlükleri toplanmış durumdayken cihazın disk alanı düşük gibi görünen senaryolarda,StorageDiagnostics.zip **ek** bir rapor oluşturulur. Düşük depolama eşiği, depolama alanı algısı Windows [olarak belirlenir.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

Bu bilgiler daha sonra tanılama günlükleri [sayfasında görüntüleyebilirsiniz.](hololens-diagnostic-logs.md#offline-diagnostics)

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Düşük depolama geliştirmelerini denemek için genel bakış

1. Cihazınızın depolama alanını doldurun.
1. Çevrimdışı **Tanılamayı** toplamak **için Güç** ve Birim kapalı [düğme birleşimine basın.](hololens-diagnostic-logs.md#offline-diagnostics)
1. Dosyanın Belgeler klasöründe depolanan günlük koleksiyonunda yeni bir dosya olduğunu HoloLens.

### <a name="csp-changes-for-reporting-hololens-details"></a>Rapor ayrıntıları için CSP HoloLens değişiklikleri

Aşağıdaki CSP'ler, HoloLens cihazlarınıza ilişkin bilgileri bildirmenin yeni HoloLens güncelleştirilmiştir.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Ücretsiz Depolama

DevDetail CSP artık cihaz üzerinde boş depolama alanı HoloLens raporlar. Bu değer, uygulamanın Ayarlar sayfasında gösterilen değerle Depolama eşleşmesi gerekir. Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer aleladedir.

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

Bu ilkenin yapılandırıldığında, ilkede belirtilen kullanıcının en az bir kez oturum açması gerekir. İlk oturum açma sonrasında cihazın yeniden başlatılması, belirtilen kullanıcının otomatik olarak oturum açmasını sağlar. Yalnızca tek bir otomatik oturum açma kullanıcısı de destekler. Etkinleştirildikten sonra, otomatik olarak oturum açan kullanıcı el ile oturumu kapatamayacaktır. Farklı bir kullanıcı olarak oturum açmak için ilkenin önce devre dışı bırakılmıştır.

> [!NOTE]
>
> - Büyük işletim sistemi güncelleştirmeleri gibi bazı olaylar, belirtilen kullanıcının otomatik oturum açma davranışını sürdürmesi için cihazda yeniden oturum açmasını gerekli kilebilir.
> - Otomatik oturum açma yalnızca MSA ve AAD destekler.

#### <a name="overview-to-try-auto-logon-csp"></a>CSP'yi otomatik olarak oturum açmayı denemek için genel bakış

1. Özel bir ilke kullanarak yeni CSP'yi [istenen kullanıcıya yapılandırma:](/mem/intune/configuration/custom-settings-windows-10)`./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser`
1. CsP'yi sağlama paketi [veya](hololens-provisioning.md) [MDM aracılığıyla cihaza uygulama.](hololens-mdm-configure.md)
1. Belirtilen hesapta oturum açın.
1. Cihazı yeniden başlatın ve kullanıcının otomatik olarak oturum açtığını gözlemler.

### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

Etkin saatler ve yükleme zamanı ilkeleri arasında, kullanım sırasında HoloLens yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklemesini tamamlamak için yeniden başlatmalar oluşmazsa güncelleştirmelerin benimsenmesi de geciker. Şimdi, IT'nin son tarihleri ve gerekli yeniden başlatmaları zorlamasına ve güncelleştirme yükleme işleminin zamanında tamamlandığından emin olmasına olanak sağlayan ilkeler ekledik. Kullanıcılara, yeniden başlatma işlemi başlatmadan önce bildirebilirsiniz ve kullanıcılar, YENIDEN başlatmayı IT ilkesine uygun olarak geciktirebilirsiniz.

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

Artık HoloLens için etkinleştirilen yeni bir ilke, IT Yöneticilerinin, güncelleştirmenin uygulamaya uygulanmasına izin verme nedeniyle başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir saat tarihi ayarlamasına olanak sağlayan yeni bir ilkedir. Bunlar zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilirsiniz. Bu ilkeyi kullanma hakkında daha fazla bilgi edinmek için [applicationManagement/ScheduleForceRestartForUpdateFailures makalesini görüntüden edinebilirsiniz.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

Bu bilgiler daha sonra İş için [uygulama dağıtım mağazası sayfasında bulunabilir.](app-deploy-store-business.md)

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için Akıllı Yeniden Denemeyi denemek için genel bakış

1. Yeni akıllı yeniden deneme özelliğini yapılandırma.
1. Henüz uygulamanıza alınmış ve doğru şekilde yapılandırılmış bir cihazda, çevrimiçi bir ortamda oturum açın.
1. Cihazı kapatarak veya bağlantısını keserek uygulamayı indirenin.
1. İndirmeyi yeniden denemek için tetiklenen süre boyunca cihazınızın açık ve İnternet'e bağlı olduğundan emin olun.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Yalnızca özel mağaza uygulamalarını Microsoft Store

Bu ilke için RequirePrivateStoreOnly ilkesi HoloLens. Bu ilke, Microsoft Store uygulamasının yalnızca İş İçin Microsoft Store aracılığıyla özel mağazayı gösterecek şekilde [yapılandırılması için İş İçin Microsoft Store.](/microsoft-store/microsoft-store-for-business-overview) Erişimi yalnızca kullanılabilir yapmış olduğunuz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly hakkında daha fazla bilgi](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

Bu bilgiler daha sonra İş için [uygulama dağıtım mağazası sayfasında bulunabilir.](app-deploy-store-business.md)

#### <a name="overview-to-try-only-private-store-apps"></a>Yalnızca özel mağaza uygulamalarını denemek için genel bakış

1. MDM aracılığıyla cihazlarınız için [yeni ilkeyi yapılandırma.](hololens-mdm-configure.md)
1. İlkeye sahip bir cihazda oturum açın.
1. Uygulama Microsoft Store açın ve yalnızca kuruluş uygulamalarını gördüğünüze dikkat edin.

### <a name="use-wdac-and-lob-apps"></a>WDAC ve LOB uygulamalarını kullanma

Artık WDAC'i kullanarak uygulamaların veya işlemlerin başlatılmasını engelleyebilir ve kendi hazır olma uygulamalarınızı kullanmaya devam edersiniz. Artık WDAC ilkeniz içinde bu ilkelere izin vesersiniz. Bu ilkeyi kullanmak, WDAC ilkenizi oluştururken PowerShell'de fazladan bir kod satırı çalıştırmayı içerir. [Buradaki adımları gözden geçirme.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>WdAC kullanırken diğer uygulamaları engellemek için kendi uygulamalarınızı denemeye genel bakış

1. LOB uygulamanın AUMID'lerini ve engellemeyi amacınız olan uygulamaları toplayın.
1. [Yeni adımları takip eden yeni bir WDAC](/mem/intune/configuration/custom-profile-hololens) ilkesi oluşturun.
1. [MDM kullanarak ilkeyi cihazınıza](hololens-mdm-configure.md) dağıtın.
1. Cihazda oturum açın ve uygulamanızı başlatarak diğerlerini engelleyebilirsiniz.

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler

#### <a name="for-developers"></a>Geliştiriciler için

- kilitli dosyaları indirme isteminin Cihaz Portalı için [bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- dosya karşıya yükleme ve indirme Cihaz Portalı zaman için sorun [düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- 2D uygulamalar için gamepad işleme, Insider derlemelerde devre dışı bırakıldı. Bu kaldırılarak, uygulamalar artık doğrudan Gamepad API'lerini kullanabilir ve tüm denetim kümesine erişime sahip olur ve daha fazlasını yapmak için geliştirebilirsiniz. Geliştiricilerin Gamepad girişini kullanmak için Gamepad API'lerini kullanmaları gerekir. Gamepad Sınıfı için bir [örnek (Windows. Gaming.Input) - Windows UWP uygulamaları.](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)
- Atanmış Erişim [API'sini](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) etkinleştirdikten sonra uygulamalar, HoloLens oturum açmış olan kullanıcı için bilgi noktası modunda bir uygulamanın HoloLens.

#### <a name="for-enterprise"></a>Enterprise

- Cihazlardan uyumluluk özelliklerini raporlamayla ilgili HoloLens ele alan; Insider derlemeleri üzerinde doğru raporlamanın tetiklanması için yeniden başlatma gerekebilir.  
- Remote Assist'in yeni flash görüntülere yüklenmiş olan in-box sürümü güncelleştirildi.
- İlk kullanıcı oturum açma işlemi sonrasında, grup tabanlı bilgi noktası yapılandırmalarının AAD OOBE'nin sonlandırılma sorunu düzeltildi.
- Cihaz yeniden başlatma için güncelleştirme bildirimlerini ve iletişim kutusu istemlerini görüntülemeyle ilgili bir sorun düzeltildi.
- Cihaz yeniden başlatıldıktan sonra Xbox Denetleyicilerinin ve diğer Bluetooth LE çevre birimlerinin yeniden bağlanması gereken bir sorun düzeltildi.
- Uzaktan Yardım çağrısı sırasında giden videonun kısa bir donmasıyla ilgili video kodlayıcı sorunu düzeltildi. Wi-Fi "Parça ve Forge" güvenlik açıklarına yönelik sürücü ve üretici yazılımı Wi-Fi değişiklikleri.
- Wi-Fi "Parça ve Forge" güvenlik açıklarına yönelik sürücü ve üretici yazılımı Wi-Fi değişiklikleri.
- Hareketli Platform Modu (MPM) kullanımında "Aşağı" değeri, kısa bir süre içinde yer çekiminin ortalamaya indireceği tahmin edilmektedir. Bu değer, Platform Modu Hareket Ettirinken gerçek ağırlık değerinin yerini almaktadır.
- 3DoF modundayken veya izleme kaybı sırasında hologramlarda düzenli aralıklarla sallanıyor düzeltildi.
- Eski sürümlerden 21H1/21H2 yayın güncelleştirmelerini etkileyen bir sorunu gidermek.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, sürüm 20H2 - Ekim 2021 Güncelleştirmesi

- Derleme 19041.1168

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H2'nin en son Windows denemeniz gerekir.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, sürüm 21H1 - Eylül 2021 Güncelleştirmesi

- Derleme 20348.1018

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem zamanı beklenmedik bir şekilde sıçraması sorununu çözmeye ilişkin düzeltmeler.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, sürüm 20H2 - Eylül 2021 Güncelleştirmesi

- Derleme 19041.1165

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem zamanı beklenmedik bir şekilde sıçraması sorununu çözmeye ilişkin düzeltmeler.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, sürüm 21H1 - Ağustos 2021 Güncelleştirmesi

- Derleme 20348.1014

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Xbox denetleyicilerinin denetleyici desteğine sahip çevreleyici uygulamalarda çalışmasını engelleyen bir sorun düzeltildi.
- Cihaz güncelleştirme hataları için geliştirilmiş tanılama.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, sürüm 20H2 - Ağustos 2021 Güncelleştirmesi

- Derleme 19041.1161

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1 - Temmuz 2021 Güncelleştirmesi

- Derleme 20348.1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi Ayarlar > Ağ Wi-Fi & İnternet > Durum > Özellikler'den > sorunu **düzeltildi.**
- ESIM sertifikalarının işletim sistemi güncelleştirmeleri arasında kaldırılmasıyla ilgili bir sorun giderildi. Bu düzeltme, 21H1 sürümüne güncelleştirmeden önce eSIM sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- Önceden yüklenmiş uygulamaları işletim sistemi sıfırlamaları arasında etkileyen bir sorun düzeltildi.
- Artan CPU yüklemesi ile ücretlendirme sırasında çalışma zamanını artırmak için pil ücretlendirme performansı ayarlanmıştır. 2 HoloLens cihazı ücretlendirme sırasında, cihazın sıcak olarak çalıştırlı olduğu algılanırsa iç pil daha yavaş ücretlendirmek için ısıyı azaltır. Olumlu bir takas, bir cihazın termal sorun nedeniyle kapanma ihtimalinin düşük olması ve bunun etkisi cihazın daha uzun süre çalışma olasılığıdır. Cihaz cool çalışıyorsa, ücret oranı etkilenmez.

> [!IMPORTANT]
> [21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)derlememizde Remote Assist kullanıcılarını etkileyen bilinen bir sorun nedeniyle, Windows Holographic sürüm 21H1 güncelleştirmelerinin tekliflerini geçici olarak duraklatıldık. Ayrıca varsayılan Gelişmiş Kurtarma Yardımcı (ARC) derlemesini [Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi olarak değiştirdik.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update) ARC derlemesi artık 21H1 derlemeyi hedeflemeye devam edecek.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – Temmuz 2021 Güncelleştirmesi

- Derleme 19041.1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı kilitli dosyaları a açma sorunlarıyla karşılaştığında müşteriyi Dosya Gezgini için gelişmiş yöntemler vardır.
- Desteklenen tüm tarayıcılarda https kullanılırken dosya karşıya yükleme, indirme, yeniden adlandırma ve silme düzeltildi.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1 - Haziran 2021 Güncelleştirmesi

- Derleme 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive veya okul kameralarını karşıya yükleme

HoloLens 2 Ayarlar uygulamasına, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın Pictures > Camera Roll klasöründen iş veya okul için ilgili OneDrive klasörüne otomatik olarak yüklemelerini sağlayan yeni bir özellik ekledik. Bu özellik, [](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) OneDrive HoloLens 2'de OneDrive uygulamasındaki bir özellik açığına yöneliktir. Bu özellik, yalnızca müşterinin kişisel hesabına (iş veya okul hesabı değil) otomatik Kamera Microsoft hesabı yüklemesini destekler.

**Nasıl çalışır?**

- "Kamera **karşıya Ayarlar >" > System > Mixed Reality Camera'ı** ziyaret edin.
- Bu özellik Açık  konuma ayarlanır ve cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları, iş veya okul hesabı için > fotoğraf makinenizin Pictures > Camera Roll klasörüne yüklenmek için OneDrive kuyruğa eklenir.
    >[!NOTE]
    >Bu özellik etkinleştirilmeden önce yakalanan fotoğraflar ve videolar *karşıya* yükleme için kuyruğa yüklenmez ve yine de el ile karşıya yüklenmeleri gerekir.
- Ayarlar sayfasındaki durum iletisi karşıya yüklenmeyi bekleyen dosyaların sayısını görüntüler (veya bekleyen tüm dosyalar karşıya OneDrive "güncel" olarak görünür).
- Bant genişliği konusunda endişe ediyorsanız veya herhangi bir nedenle karşıya yüklemeyi "duraklatmak" için özelliği Kapalı konuma **geçebilirsiniz.** Özelliği geçici olarak devre dışı bırakmak, Kamera Roll klasörüne yeni dosya ekleyinceye kadar karşıya yükleme kuyruğunda artış devam eder, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmez.
- En yeni dosyalar ilk olarak karşıya yüklensin (son, ilk çıkar).
- Hesap OneDrive sorunları varsa (örneğin, parolanız değiştikten sonra) Yeni bir düzeltme düğmesi Ayarlar görüntülenir. 
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklemesi daha uzun sürer (özellikle karşıya yükleme bant genişliğiniz kısıtlanmışsa). Büyük bir dosya karşıya yükleme sırasında karşıya yüklemeyi "duraklatır" veya kapatırsanız, kısmi karşıya yükleme korunur. Karşıya yükleme "duraklatıldı" veya devre dışı bırakıldı. Birkaç saat içinde yeniden etkinleştirilirse, karşıya yükleme, bıraktığı yerden devam eder. Ancak, karşıya yükleme birkaç saat sonra yeniden etkinleştirilirse, büyük dosyanın karşıya yüklemesi en baştan yeniden başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayar, geçerli bant genişliği kullanımına göre yerleşik azaltmaya sahip değil. Başka bir senaryo için bant genişliğini en üst düzeye çıkarmanız gerekirse, ayarı el ile kapatın. Upload duraklatılır, ancak özellik Yeni eklenen dosyaları Kamera Roll'e izlemeye devam eder. Devam etmek için hazır olduğunda karşıya yüklemeyi yeniden etkinleştirin.
- Bu özellik cihaza her kullanıcı hesabı için etkinleştirilmelidir ve yalnızca o anda cihazda oturum açık olan kullanıcının dosyalarını etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasındaki karşıya yükleme sayısını izlerken fotoğraf veya video çekmiyorsanız, geçerli dosya karşıya yükleme tamamlanana kadar bekleyen dosya sayısı değişmeyebilirsiniz.
- Upload uykuda düşerse veya kapalı olursa, cihaz duraklatılır. Bekleyen karşıya yüklemelerin tamamlandığından emin olmak için, Ayarlar sayfası "OneDrive güncel" olana kadar cihazı etkin bir şekilde kullanın veya **Power & ayarlarını** yapın.

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri artık 2. HoloLens desteklemektedir:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx birlikte kullanarak uygulamanın Telemetri ve davranış üzerinde tam denetime Ayarlar gerekir.

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Renk ayarlama ile videonun önemli bozulmalarını düzeltir.
- Power menüsünde metnin kesilmesine neden olan bir sorunu gidermek.
- RequirePrivateStoreOnly ilkesi için destek sağlar.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, sürüm 20H2 – Haziran 2021 Güncelleştirmesi

- Derleme 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

Aşağıdaki telemetri ilkeleri artık 2. HoloLens desteklemektedir:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Hem System\AllowTelemetry hem de System\ConfigureTelemetryOptInSettingsUx birlikte kullanarak uygulamanın Telemetri ve davranış üzerinde tam denetime Ayarlar gerekir.

Holographic sürüm 21H1'Windows en son derlememizi denemeyi teşvik ederiz.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, sürüm 1903 - Haziran 2021 Güncelleştirmesi

- Derleme 18362.1116

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

>[!IMPORTANT]
> Bu derlemeye artık hizmet ve olmayacaktır.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, sürüm 21H1

- Derleme 20346.1002

Bu güncelleştirme, iki hedef kitleye yönelik özellikler içerir; Son Kullanıcı tarafından bir cihaz üzerinde herkes tarafından kullanılan özellikler ve IT Yöneticileri tarafından yapılandırılan yeni cihaz yönetimi seçenekleri. Aşağıdaki tabloda her hedef kitleyle ilgili özellikler gösterilmiştir. BIR IT Yöneticisiyseniz lütfen IT Yöneticisi - Güncelleştirme Denetim [Listesi'ne göz atın.](#it-admin---update-checklist)
>[!IMPORTANT]
>Bu derlemeye güncelleştirmek için HoloLens 2 cihazın Şubat 2021 güncelleştirmesini (derleme 19041.1136) veya daha yenisini çalıştıracak olması gerekir. Bu özellik güncelleştirmesini görmüyorsanız lütfen önce cihazınızı güncelleştirin ve yeniden deneyin.

>[!NOTE]
>Bugün Microsoft HoloLens 2, aşağıdaki sürümler için aylık bakım güncelleştirmelerini (hata ve güvenlik düzeltmeleri) destekler:
>
>- Windows Holographic, sürüm 20H2 (Derleme 19041.1128+)
>- Windows Holographic, sürüm 2004 (Derleme 19041.1103+)
>- Windows Holographic, sürüm 1903 (Derleme 18362+)
>
> Windows Holographic sürüm 21H1'in tanıtımıyla, Windows Holographic sürüm **1903** için aylık bakım güncelleştirmelerini sonlandırıyoruz. Bu sayede daha yeni sürümlere odaklanarak değerli geliştirmeler yapmaya devam edeceğiz.

| Özellik Adı                                              | Kısa açıklama                                                                      | Hedef Hedef Kitle |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Yeni Microsoft Edge](#introducing-the-new-microsoft-edge)  | Yeni, Chromium tabanlı Microsoft Edge artık 2. HoloLens kullanılabilir. | Son Kullanıcı |
[WebXR ve 360 Görüntüleyici](#webxr-and-360-viewer) | Tam ekran web deneyimlerini ve 360 video kayıttan yürütmeyi deneyin. | Son Kullanıcı |
[Yeni Ayarlar uygulaması](#new-settings-app) | Eski Ayarlar, güncelleştirilmiş bir sürümle yeni özellikler ve ayarlarla değiştir ediliyor. | Son Kullanıcı |
[Renk ayarlamayı görüntüleme](#display-color-calibration) | HoloLens 2 ekranınız için alternatif bir renk profili seçin. | Son Kullanıcı |
[Varsayılan uygulama seçici](#default-app-picker) | Her dosya veya bağlantı türü için hangi uygulamanın başlatılması gerektiğini seçin. | Son Kullanıcı |
[Uygulama başına birim denetimi](#per-app-volume-control) | Uygulama düzeyindeki birimi sistem biriminden bağımsız olarak denetleme. | Son Kullanıcı |
[Web uygulamalarını yükleme](#install-web-apps) | Yeni HoloLens tarayıcısıyla Microsoft Office 2. Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekin](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde cihazı yeniden başlatın ve HoloLens kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve /veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında bilgi noktası modları için otomatik oturum açma özelliğinin kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni uygulamalar ve Edge Ayarlar için AUMID'ler. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlat menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
[Sayfa Görünürlüğü için Yeni SettingsURIs Ayarlar Ayarları](#new-settings-uris-for-page-settings-visibility) | Ayarlar/PageVisibilityList ilkesi için 20'den fazla yeni SettingsURIs. | BT Yöneticisi |
[Geri Dönüş Tanılamasını Yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Ayarlar Uygulamasında Geri Dönüş Tanılama Davranışını Ayarlama. | BT Yöneticisi |
[Yakındaki cihazlarla paylaşım](#share-things-with-nearby-devices) | Dosya veya URL'leri bir HoloLens bilgisayara paylaşma. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | Işletim sistemi güncelleştirmeleri Ayarlar yeni sorun giderici. | BT Yöneticisi |
[Teslim İyileştirme Önizleme](#delivery-optimization-preview) | Birden çok farklı cihazdan yapılan indirmeler için bant HoloLens azaltabilirsiniz. | BT Yöneticisi |

İlgili sürüm notlarına göz at:

- [HoloLens Emulator arşivini ziyaret edin](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 kılavuzlar](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge tanıtımı

![eski Microsoft Edge logosunun yeni Microsoft Edge logoa animasyonu.](images/new-edge.gif)

yeni Microsoft Edge, müşteriler için daha iyi uyumluluk ve web geliştiricileri için web 'in daha az parçalanması oluşturmak üzere [Chromium açık kaynaklı projeyi benimsemektedir](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) .

> [!IMPORTANT]
> bu yeni Microsoft Edge, yeni sürümlerde [artık desteklenmeyen](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) eski Microsoft Edge otomatik olarak değiştirir.

![yeni Microsoft Edge ekran görüntüsü.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni Microsoft Edge başlatılıyor

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi.](images/new_edge_logo.png) (mavi ve yeşil girdap simgesiyle gösterilir) Başlat menüsü sabitlenmiştir ve bir web bağlantısını etkinleştirdiğinizde otomatik olarak başlatılır.

> [!NOTE]
> yeni Microsoft Edge HoloLens 2 ' de ilk kez başlattığınızda, ayarlarınız ve verileriniz eski Microsoft Edge içeri aktarılır. yeni Microsoft Edge başlattıktan sonra eski Microsoft Edge kullanmaya devam ederseniz, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge eşitlenmeyecektir.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni Microsoft Edge ilke ayarlarını yapılandırma

yeni Microsoft Edge, bt yöneticilerine HoloLens 2 ' de eski Microsoft Edge ile daha geniş bir tarayıcı ilkeleri kümesi sunar.

Yeni Microsoft Edge ilke ayarlarını yönetme hakkında daha fazla bilgi edinmek için bazı yararlı kaynaklar aşağıda verilmiştir:

- [Microsoft Intune ile Microsoft Edge ilkesi ayarlarını yapılandırma](/deployedge/configure-edge-with-intune)
- [Microsoft Edge ilke eşlemesine Microsoft Edge'in eski sürümü](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Microsoft Edge ilke eşleme için Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- tam [Microsoft Edge Enterprise belgeleri](/deployedge/)

> [!IMPORTANT]
> yeni Microsoft Edge tarafından desteklenen tarayıcı ilkelerinin hacmi nedeniyle, takımımız her yeni ilkenin HoloLens 2 ' de çalıştığından emin olamaz. ancak, daha önce HoloLens 2 ' de desteklenen her bir eski Microsoft Edge ilkesinin Microsoft Edge denk olarak sınanmış ve onayladık. HoloLens 2 ile kullandığınız her bir eski Microsoft Edge tarayıcı ilkesinin yeni Microsoft Edge eşdeğerini bulmak için [Microsoft Edge ilke eşlemesine Microsoft Edge'in eski sürümü](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) bakın.
>
> HoloLens 2 *ile çalışabildiğinizi* bildiğiniz en az iki yeni Microsoft Edge ilkesi vardır:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL 'Si

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 ' de yeni Microsoft Edge bekleneceğiniz

yeni Microsoft Edge yeni bir uwp bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan, bu, yalnızca HoloLens 2 gibi UWP cihazlarda çalışmasına izin vererek bazı özellikler hemen kullanılamayabilir. Önümüzdeki aylarda yeni senaryolar ve Özellikler destekliyoruz, bu nedenle bu alanı güncel bilgiler için denetleyin.

**Çalışması beklenen senaryolar ve Özellikler:**

- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri, beklendiği gibi işlenmeli ve davranmalıdır
- Çoğu tarayıcı işlevinin (Sık Kullanılanlar, geçmiş, vb.) beklenen şekilde çalışması gerekir
- Koyu mod
- Cihaza Web uygulamaları yükleme
- uzantılar yükleniyor (lütfen HoloLens 2 ' de düzgün çalışmayan uzantıları kullanıyorsanız bize bildirin)
- PDF 'YI görüntüleme ve işaretleme
- Tek bir tarayıcı penceresinden uzamsal ses
- Tarayıcının otomatik ve el ile güncelleştirilmesi
- PDF 'YI yazdırma menüsünden kaydetme ("PDF 'ye Kaydet" seçeneğini kullanarak)
- WebXR ve 360 Viewer uzantısı
- Ortamınıza yerleştirilmiş birden çok pencere arasında gezinerek, doğru pencereye içerik geri yükleme

**Çalışması beklenen senaryolar ve Özellikler:**

- Eşzamanlı ses akışları ile birden çok pencere arasındaki uzamsal ses
- "Görüntüleyin, söyleyin"
- Yazdırma

**Bilinen en iyi tarayıcı sorunları:**

- Yeni Microsoft Edge için holographic klavyesindeki Büyüteç önizlemesi devre dışı bırakıldı. Büyütme doğru şekilde çalışmaya başladıktan sonra bu özelliği gelecekteki bir güncelleştirmede yeniden etkinleştirmek isteriz.
- Başka bir tarayıcı penceresi açık ve etkin olduğunda ses yanlış tarayıcı penceresinden oynayabilir. Ses oynatılması beklenen diğer etkin pencereyi kapatarak Bu soruna geçici bir çözüm bulabilirsiniz.
- ["Beni takip etme" modunda](hololens2-basic-usage.md#follow-me-stop-following)bir tarayıcı penceresinden ses çalarken, "beni izle" modunu devre dışı bıraktığınızda ses çalmaya devam edecektir. "Beni Izle" modunu devre dışı bırakmadan veya **X** düğmesi ile pencereyi kapatarak bu sorunu geçici olarak çözebilirsiniz.
- active Microsoft Edge windows ile etkileşim kurmak, diğer 2b uygulama pencerelerinin beklenmedik şekilde etkin olmasına neden olabilir. Bu pencereleri yeniden etkileşimde bulunarak tekrar etkinleştirebilirsiniz.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Microsoft Edge ekibi, Edge ınsider community için üç önizleme kanalı sağlar: Beta, Dev ve canary. önizleme kanalının yüklenmesi, HoloLens 2 ' Microsoft Edge yayınlanan sürümünü kaldırmaz ve aynı anda birden fazla yükleyebilirsiniz.

Edge ınsider community hakkında daha fazla bilgi edinmek için [Microsoft Edge ınsider giriş sayfasını](https://www.microsoftedgeinsider.com) ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve kullanmaya başlamak için [Edge Insider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.

Microsoft Edge ınsider kanallarını HoloLens 2 ' ye yüklemek için kullanabileceğiniz birkaç yöntem vardır:

**Cihaza doğrudan yüklemek (Şu anda yalnızca yönetilmeyen cihazlar için kullanılabilir)**

  1. HoloLens 2 ' de [Edge ınsider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.
  1. yüklemek istediğiniz Edge ınsider kanalı için **HoloLens 2 için indir** düğmesini seçin.
  1. İndirilmiş. msix dosyasını Edge indirme kuyruğundan veya cihazınızın "Indirmeler" klasöründen (Dosya Gezgini 'ni kullanarak) başlatın.
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatılır.
  1. **Install** düğmesini seçin.
  1. başarılı bir yüklemeden sonra, Başlat menüsü **tüm uygulamalar** listesinde Microsoft Edge Beta, Dev veya canary ' ı ayrı bir giriş olarak bulacaksınız.

**Windows cihaz portalı ile bilgisayar aracılığıyla yükler (HoloLens 2 ' de [geliştirici modunun](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) etkinleştirilmesini gerektirir)**

  1. Bilgisayarınızda [Edge Insider indirme sayfasını](https://www.microsoftedgeinsider.com/download)ziyaret edin.
  1. yüklemek istediğiniz Edge ınsider kanalının "Windows 10 için indir" düğmesinin yanındaki **açılan ok düğmesini** seçin.
  1. açılan menüden **HoloLens 2** ' yi seçin.
  1. . Msix dosyasını BILGISAYARıNıZıN "Indirmeler" klasörüne (veya kolayca bulabileceğinizi bir klasöre) kaydedin.
  1. HoloLens 2 ' ye indirilen. msix dosyasını yüklemek için bilgisayarınızda [Windows cihaz portalı](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 'nı kullanın.
  1. başarılı bir yüklemeden sonra, Başlat menüsü **tüm uygulamalar** listesinde Microsoft Edge Beta, Dev veya canary ' ı ayrı bir giriş olarak bulacaksınız.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni Microsoft Edge engellemek için WDAC kullanma

bt yöneticileri için, yeni Microsoft Edge uygulamasını engelleyecek bir [WDAC ilkesini](windows-defender-application-control-wdac.md) güncelleştirmek isteyen bt yöneticileri için, aşağıdaki ilkeyi ilkenize eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni Microsoft Edge için uç noktaları yönetme

Bazı ortamların, dikkate alınması açısından hesaba yönelik ağ kısıtlamaları olabilir. Yeni kenara sorunsuz bir deneyim sağlamak için lütfen [Bu Microsoft uç noktalarını etkinleştirin.](/deployedge/microsoft-edge-security-endpoints)

HoloLens için şu anda kullanılabilir [uç noktalar](hololens-offline.md)hakkında daha fazla bilgi edinin.

### <a name="install-web-apps"></a>Web uygulamalarını yükler

 > [!Note]
>[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)itibariyle, Office web uygulaması artık önceden yüklenmeyecektir.

yeni kenarı, Microsoft Store uygulamalarla birlikte web uygulamaları yüklemek için kullanabilirsiniz. örneğin, SharePoint veya OneDrive barındırılan dosyaları görüntülemek ve düzenlemek için Microsoft Office web uygulamasını yükleyebilirsiniz. Office web uygulamasını yüklemek için, https://www.office.com adres çubuğuna **uygulama kullanılabilir** veya **Office** düğmesini seçin. Onaylamak için **yüklemeyi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca, HoloLens 2 etkin bir internet bağlantısına sahip olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyicisi

yeni Microsoft Edge, derinlikli web deneyimleri (webvr 'yi değiştirme) oluşturmaya yönelik yeni standart olan webxr için destek içerir. birçok modern web deneyimi, VR ile birlikte tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler HoloLens 2 tarafından da desteklenir. WebXR standardı, fiziksel ortamınızı kullanan genişletilmiş ve karma gerçeklik derinlikli web deneyimlerini de sunar. geliştiriciler webxr ile daha fazla zaman harcadığında, yeni genişleticilerin ve karma gerçeklik derinlikli deneyimlerin HoloLens 2 müşteri tarafından denemeye ulaştığını öneririz!

360 görüntüleyici uzantısı, webxr üzerinde oluşturulmuştur ve HoloLens 2 ' deki yeni Microsoft Edge birlikte otomatik olarak yüklenir. Bu web uzantısı size 360 derecelik videolarda araçlarındaki yeniliklere dalabilirsiniz olanağı sağlar. YouTube, 360 videoların en büyük seçimini sunarak, buradan başlamanız önerilir.

#### <a name="how-to-use-webxr"></a>WebXR kullanma

1. WebXR desteğiyle bir Web sitesine gidin.
1. Web sitesindeki **VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel temsili Web sitesi başına değişebilir, ancak şuna benzer olabilir:

    ![VR düğmesi örneği girin.](images/75px-enter-vr.png)

1. Belirli bir etki alanında WebXR deneyimini ilk kez başlatmayı deneyci, çevreleyici bir görünüm girmek için onay sorar ve İzin Ver'i **seçer.**
1. Deneyimi [HoloLens için 2 hareket](hololens2-basic-usage.md#the-hand-tracking-frame) kullanın.
1. Deneyimin Çıkış düğmesi **yoksa, girişe** dönmek [için Başlat](hololens2-basic-usage.md#start-gesture) hareketini kullanın.

**Önerilen WebXR örnekleri**

- 360 Görüntüleyici (sonraki bölüme bakın)
- [XR Yenileri](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 Görüntüleyici kullanma

1. YouTube'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde karma gerçeklik başlığı düğmesini seçin:

    ![360 Görüntüleyiciyi etkinleştirme düğmesi.](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyiciyi ilk kez başlatmayı deneyebilirsiniz; tarayıcı çevreleyici bir görünüm girmek için onay sorar. İzin **Ver'i seçin.**
1. [Kayıttan yürütme](hololens2-basic-usage.md#select-using-air-tap) denetimlerini açmak için havadan dokunma. El [işleyicileri](hololens2-basic-usage.md#select-using-air-tap) ve havadan dokunarak oynatma/duraklatma, ileri/geri atlama, açıklamalı alt yazıları açma/kapatma veya deneyimi durdurma (çevreleyici görünümden çıkar) için kullanın. Kayıttan yürütme denetimleri birkaç saniyelik bir süre sonra kaybolur.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>En önemli WebXR ve 360 Görüntüleyici bilinen sorunları

- WebXR deneyiminin karmaşıklığına bağlı olarak kare hızı düşerek veya düşerek düşebilirsiniz.
- WebXR'de ifadeli el bağlantılarında destek varsayılan olarak etkin değildir. Geliştiriciler `edge://flags` "WebXR El Girişi"ni etkinleştirerek desteği etkinleştirerek.
- YouTube dışında web sitelerinden 360 video beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici hakkında geri bildirim sağlama

Lütfen yeni çalışmadaki Geri Bildirim Gönder özelliği **aracılığıyla geri bildirimi ve** hataları ekibimizle Microsoft Edge.

### <a name="new-settings-app"></a>Yeni Ayarlar uygulaması

Bu sürümle birlikte, Ayarlar uygulamasının yeni bir sürümünü Ayarlar. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni uygulama Ayarlar eski Ayarlar farklı olduğundan, Ayarlar ortamınıza önceden yerleştiren tüm windows güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar giriş sayfası.](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**

- Ayarlar: Anahtar sözcükleri veya ayarın adını Ayarlar giriş sayfasından ayarları arama.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, ses ses cihazları aracılığıyla Bluetooth veya ses girişi için USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar, 2. HoloLens desteklemez.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Uygulama [başına birim denetimine bakın.](#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktanın otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık uçak modunu 2. HoloLens etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**

- Daha önce Ayarlar pencereleri kaldırılacak (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden Ayarlar. IT yöneticileri, HoloLens 2 cihaz adı şablonu [için Windows Autopilot'ı](hololens2-autopilot.md) veya MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme beklenmebilir).

#### <a name="display-color-calibration"></a>Renk ayarlamayı görüntüleme

Bu yeni ayarla, 2 ekran görüntüsü için alternatif bir renk HoloLens seçebilirsiniz. Bu, renklerin özellikle daha düşük ekran parlaklığı düzeylerinde daha doğru görünmesine yardımcı olabilir. Ekran rengi ayarı, sistem Ayarlar Sayfasındaki > bulunabilir.

> [!NOTE]
> Bu ayar görüntü üretici yazılımınıza yeni bir renk profili kaydedeci, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Görüntü rengi ayarlamayı kullanma

1. Ayarlar uygulamasını **başlatarak** **System > Olarak Ayarlama'ya gidin.**
1. Renk **ayarı görüntüle'nin** altında Renk **görüntüleme düzenini çalıştır düğmesini** seçin.
1. Ekran rengi ayarlama deneyimi başlatacak ve sizi, mengenenizin doğru konumda olduğundan emin olmak için teşvik eder.
1. Yönerge iletişim kutularına devam ettikten sonra, ekranınız otomatik olarak %30 parlaklığa soluk görüntülenir.
    > [!TIP]
    > Ortamınız soluk sahneyi görme konusunda sorun taşıyorsanız, cihazın sol tarafındaki parlaklığı düğmeleri kullanarak HoloLens 2'nin parlaklığını el ile ayarlayabilirsiniz.
1. Her renk profilini anında denemek için 1-6 düğmelerini seçin ve en iyi görüneni bulun (bu genellikle sahnenin gri tonlamalı desen ve ten rengi beklendiği gibi görünmesiyle sahnenin en nötr görünmesine yardımcı olan profil anlamına gelir).)

    ![Renk ayarı sahneyi görüntüleme.](images/color-cal-ui.png)

1. Seçilen profilden memnun değilken Kaydet ve Çıkış **& seçin**
1. Değişiklik yapmamayı tercih ederseniz, İptal et **& düğmesini** seçin; değişiklikleriniz geri döner

> [!TIP]
> Burada, görüntü rengi ayarıyla ilgili bazı yararlı ipuçlarına göz ayın:
>
> - Ekran renklerini istediğiniz zaman Ayarlar yeniden çalıştırarak
> - Cihaz üzerinde herhangi biri renk profillerini değiştirmek için daha önce bu ayarı kullandısa, en son değişikliğin tarih/saat ayarı Ayarlar yansıtılandır
> - Görüntü rengi ayarlamayı yeniden çalıştırarak daha önce kaydedilen renk profili vurgulanır ve Profil 0 görünmez (Profil 0, ekranın özgün renk profilini temsil ettiği için)
> - Ekranın özgün renk profiline geri dönmek için bu işlemi Ayarlar sayfasından (bkz. renk profilini [sıfırlama)](#how-to-reset-color-profile)

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama

HoloLens 2'ye kaydedilen özel renk profili sizi memnun HoloLens cihazın özgün renk profilini geri yükleyebilirsiniz:

1. Ayarlar uygulamasını **başlatarak** **System > Olarak Ayarlama'ya gidin.**
1. Renk **ayarı görüntüle altında** Varsayılan renk **profiline sıfırla düğmesini** seçin.
1. 2. sunucuya yeniden **başlatmaya ve** değişikliklerinizi uygulamanıza hazırsanız, iletişim HoloLens kutusu açıldığında Yeniden başlat'ı seçin.

#### <a name="top-display-color-calibration-known-issues"></a>Bilinen en çok görünen renk ayarı sorunları

- Bu Ayarlar, renk profilinin en son ne zaman değiştirdiğini size söyleyen durum dizesi, ilgili sayfayı yeniden yükleyene kadar güncel Ayarlar.
    - Geçici çözüm: Ayarlar sayfayı seçin ve Sonra Dalı sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirdiğinde veya birden fazla yüklü uygulamayla bir dosya türünü a açarsanız, hangi yüklü uygulamanın dosya veya bağlantı türünü işlemesi gerektiğini seçmenizi istediğiniz yeni bir pencere açılır. Bu pencerede, seçilen uygulamanın dosyayı işlemesi veya "Bir kez" ya da "Her zaman" bağlantı türünü de seçmeyi seçebilirsiniz.

"Her Zaman"ı seçerseniz ancak daha sonra belirli bir dosyayı veya bağlantı türünü hangi uygulamanın işleyeni değiştirmek istiyorsanız, Ayarlar > **Apps'te kaydedilmiş varsayılanlarınızı sıfırlayabilirsiniz.** Sayfanın en altına kaydırın ve  "Dosya türleri için varsayılan uygulamalar" ve/veya "Bağlantı türleri için varsayılan uygulamalar" altındaki Temizle düğmesini seçin. Masaüstü bilgisayarlardaki benzer ayarın aksine, tek tek dosya türü varsayılanlarını sıfırlayabilirsiniz.

#### <a name="per-app-volume-control"></a>Uygulama başına birim denetimi

Artık bu Windows kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duyan uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha iyi duymasını sağlar. Örneğin, başka bir uygulamada uzaktan yardım için başka bir kişiyi çağırırken bir uygulamanın hacmini kapatma ihtiyacı.

Tek bir uygulamanın hacmini ayarlamak için Ayarlar Sistem Sesi'ne gidin ve Gelişmiş ses seçenekleri'nin altında Uygulama hacmi  >    >  ve **cihaz tercihleri'ne tıklayın.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe doğru çekin

Bazı müşteriler, kullanmakta olduğu sözcüğün şeklini değiştirerek sanal klavyelerde "yazma" özelliğini daha hızlı bulabilir ve holografik klavye için bu özelliğin önizlemesini sunuyoruz. Holografik klavyenin düzlemi üzerinden parmak ucunu atarak, sözcüğün şeklini çekerek ve ardından klavyenin düzlemi üzerinden parmak ucunu çekerek tek tek çekerek tek tek çekin. Sözcüklerin arasındaki klavyeden parmaklarınızı kaldırarak boşluk çubuğuna basmanıza gerek kalmadan sözcükleri takip etmek için kaydırabilirsiniz. Klavyede parmak hareketini takip eden bir çekme izi görüyorsanız özelliğin çalıştığını bilirsiniz.

Lütfen unutmayın; bu özelliğin kullanımı ve ana bilgi sahibi olmak, parmak izinize karşı direnç hissetmeyebilirsiniz (cep telefonu görüntüsü aksine) holografik klavyenin yapısı nedeniyle karmaşık olabilir. 

### <a name="power-menu-from-start"></a>Başlat'tan Güç menüsü

Kullanıcının oturum kapatmasını, kapatmasını ve cihazı yeniden başlatmasını sağlayan yeni bir menü. Sistem güncelleştirmesini HoloLens Başlangıç ekranı gösteren bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. Başlangıç HoloLens Başlangıç ekranı kullanarak veya ["Başla"ya](hololens2-basic-usage.md#start-gesture) "Git" ifadesini kullanarak bu ifadeyi açın.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkatin:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Ellerinizi kullanarak kullanıcı profili resmini veya "Power" sesli komutunu seçin.

4. Cihazı kapatma, Yeniden Başlatma veya Kapatma seçeneklerinin yer alan bir menü görüntülenir:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Oturum kapatmak, yeniden başlatmak veya hizmetinizi kapatmak için menü seçeneklerini HoloLens. Cihaz tek bir Microsoft Hesabı [(MSA)](hololens-identity.md)veya yerel hesap için ayarlanmışsa, Oturum açma seçeneği kullanılamıyor olabilir.

6. Başka bir yere dokunarak veya Başlat hareketiyle Başlat menüsü menüyü kapatabilirsiniz.

#### <a name="update-indicator"></a>Göstergeyi güncelleştirme

Bir güncelleştirme kullanılabilir olduğunda, yeniden başlatmanın güncelleştirmeyi yükley hazır olduğunu belirtmek için üç nokta simgesi açılır Menü seçenekleri güncelleştirmenin varlığını yansıtacak şekilde de değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında listelenen birden çok kullanıcı

Daha önce Oturum Açma ekranında yalnızca en son oturum açık olan kullanıcının yanı sıra 'Diğer kullanıcı' giriş noktası da gösteri. Cihazda birden çok kullanıcı oturum amışsa bunun yeterli olmadığını ifade etmek için müşteri geri bildirimi aldık. Yine de kullanıcı adlarını yeniden yazmaları gerekmektedir.

Bu Windows, PIN girişi alanında sağ  tarafta bulunan Diğer kullanıcı'nın seçili olduğu bu derlemede Oturum açma ekranında daha önce cihazda oturum açmamış birden çok kullanıcı görüntülenir. Bu, kullanıcıların kendi kullanıcı profillerini seçmesini ve ardından kendi kullanıcı kimlik bilgilerini kullanarak Windows Hello sağlar. Cihaza hesap ekle düğmesi aracılığıyla bu Diğer kullanıcılar sayfasından yeni bir kullanıcı **da eklenebilir.**

Diğer kullanıcılar menüsünde, Diğer kullanıcılar düğmesi cihazda oturum açmış olan son kullanıcı görüntülenir. Bu kullanıcının Oturum açma ekranına dönmek için bu düğmeyi seçin.

![Oturum açma ekranı varsayılandır.](./images/multiusers1.jpg)

<br>

![Diğer kullanıcıların oturum açma ekranı.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C Dış Mikrofon Desteği

> [!IMPORTANT]
> BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.** Bir USB-C cihazına takan kullanıcılar, mikrofonlu cihazın sesinin otomatik olarak mikrofona yeniden yönlendirilmesine neden olduğunu gözlemler ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazının üzerinde önceliklendirmektedir. **USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**

Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz. USB-C mikrofonları arama, kayıt vb. için kullanılabilir.

Uygulama uygulamasını **Ayarlar** Sistem **Sesi'ne**  >  **seçin.**

![Ses Ayarlar.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.
>
> Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.** **Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.
>
> İletişim **Varsayılanı'nın** seçimi, dış mikrofonun Remote Assist ve diğer iletişim HoloLens kullanılamayacak, ancak bu mikrofon dizisi diğer görevler için hala kullanılabilir.

![Ses cihazlarını yönetme.](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlayın.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mikrofon desteği Bluetooth ne olacak?

Ne Bluetooth mikrofonlar hala 2. HoloLens desteklenmiyor.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofon sorunlarını giderme

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, mikrofonla ilgili değil mikrofonla ilgili HoloLens. Bu mikrofonlardan birini HoloLens ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Sistem   >  **Ayarlar'de** yerleşik konuşmacıları (Analog Özellik Ses  >   **Sürücüsü)** Varsayılan cihaz olarak **açıkça ayarlayın.** HoloLens mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlamanız gerekir.

![USB-C mikrofon sorunlarını giderme.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma

Bu yeni özellik, Ziyaretçi hesaplarında otomatik oturum açma özelliğinin Bilgi Noktası modları için kullanılmaktadır.

Oturum açma AAD, bir cihazı ziyaretçinin otomatik oturum açması için yapılandırmak üzere:

1. Şunları içeren bir sağlama paketi oluşturun:
    1. Ziyaretçi **hesaplarına izin vermek için Çalışma Zamanı ayarlarını/AssignedAccess'i** yapılandırıyor.
    1. İsteğe bağlı olarak, daha sonra yönetilsin diye cihazı MDM'ye (Çalışma zamanı **ayarları/Çalışma Alanı/Kayıtlar)** kaydediyor.
    1. Yerel hesap oluşturma
1. [Sağlama paketini uygulama.](hololens-provisioning.md)

Bir AAD yapılandırma için, kullanıcılar bu değişiklik olmadan bugün buna benzer bir şey elde ediyor olabilir. AAD bilgi noktası modu için yapılandırılan cihazlar, oturum açma ekranından tek bir düğmeye dokunarak Ziyaretçi hesabında oturum açmasını sağlar. Ziyaretçi hesabında oturum açıldıktan sonra, ziyaretçi başlat menüsünden açıkça oturum açıncaya veya cihaz yeniden başlatana kadar cihaz yeniden oturum açma isteminde olmayacaktır.

Ziyaretçi Otomatik oturum açma işlemi özel [OMA-URI ilkesi aracılığıyla](/mem/intune/configuration/custom-settings-windows-10) yönetilebilir:

- URI değeri: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| İlke  | Description   | Yapılandırmalar  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Ziyaretçinin Bilgi Noktası'da otomatik olarak oturum açmasını sağlar   | 1 (Evet), 0 (Hayır, varsayılan.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Bilgi Noktası modlarında yeni Ayarlar ve Edge uygulamalarını kullanma

Uygulamaları Bilgi [Noktası'ne](hololens-kiosk.md)eklerken, BIR IT Yöneticisi genellikle uygulamayı Bilgi Noktası'nın yerine Uygulama Kullanıcı Modeli Kimliği'ni (AUMID) kullanarak ekler. Hem Ayarlar hem de Microsoft Edge uygulaması yeni uygulamalar olarak kabul edilir ve bu uygulamalar için AUMID'leri kullanan eski uygulama Bilgi Noktası'lardan farklı olduğundan, yeni AUMID'yi kullanmak için güncelleştirilmelidir.

Bilgi Noktası'nın yeni uygulamaları içerecek şekilde değiştirilmesini sağlarken, yeni AUMID'ye eklemenizi ve eskisini bırakmanız önerilir. Bu, kullanıcılar işletim sistemi güncelleştirecek ve Bilgi Noktası'nın hedeflenen şekilde kullanmaya devam etmek için yeni ilkeler almaları gerekmayacak olduğunda kolay bir geçiş sağlar.

| Uygulama                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Eski Ayarlar Uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Yeni Ayarlar Uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri

Eski derlemelerde, bir cihazda hem genel atanan erişimin hem de AAD grup üyesinin atanmış erişiminin birleşimi olan bir bilgi noktası yapılandırması varsa, AAD grup üyeliğinin başarısız olduğu belirlenirse, kullanıcı["](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)başlat " menüsünde hiçbir şey gösterilmez.

Bu sürümden Windows bilgi noktası deneyimi, bilgi noktası modu sırasında hata olması durumunda genel bilgi noktası yapılandırmasına (varsa) AAD olur.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Sayfa Ayarlar Görünürlüğü için yeni Ayarlar URL'leri

[Holographic Windows sürüm 20H2'de,](hololens-release-notes.md#windows-holographic-version-20h2) [Ayarlar/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ilkesi eklenmiştir. Bu ilke, Ayarlar içinde görülen sayfaları kısıtlar. PageVisibilityList, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkedir.

Page [Ayarlar Visibility](settings-uri-list.md)sayfasını ziyaret ediyorsanız, bu CSP'yi kullanma yönergelerini ve önceki sürümlerde kullanılabilen URL'lerin listesini bulabilirsiniz.

IT Yöneticilerinin yönettikleri kullanılabilir Ayarlar URL'lerin listesini genişletiyoruz. Bu URI'lerden bazıları, yeni uygulamanın yeni Ayarlar içindir. Ayarlar/PageVisibilityList ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

> [!NOTE]
> **Kullanım dışı: ms-settings:network-proxy**
>
> Bu yeni derlemelerde bir ayarlar sayfası kullanım dışıdır. Eski Ağ **& İnternet**  >  **Ara** Sunucusu sayfası artık genel ayar olarak kullanılamaz. Yeni bağlantı başına ara sunucu ayarları, İnternet   >  **Wi-Fi**& Ağ Bağlantısı Özellikleri veya İnternet Ethernet Özellikleri altında  >   **&**  >    >  **bulunabilir.**

<br>

| Ayarlar sayfası                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Uygulamalar > Apps & özellikleri                               | `ms-settings:appsfeatures`                         |
| Uygulamalar > Gelişmiş & uygulamalar > özellikleri          | `ms-settings:appsfeatures-app`                     |
| Uygulamalar > Çevrimdışı haritalar                                  | `ms-settings:maps`                                 |
| Uygulamalar > Çevrimdışı haritalar > Haritaları indirme                  | `ms-settings:maps-downloadmaps`                    |
| Cihazlar > Fare                                      | `ms-settings:mouse`                                |
| Cihazlar > USB                                        | `ms-settings:usb`                                  |
| İnternet & Uçak > ağ bağlantısı                   | `ms-settings:network-airplanemode`                 |
| Gizlilik > Genel                                    | `ms-settings:privacy-general`                      |
| Gizlilik > Mürekkep & kişiselleştirme             | `ms-settings:privacy-speechtyping`                 |
| Gizlilik > Motion                                     | `ms-settings:privacy-motion`                       |
| Gizlilik > Ekran görüntüsü kenarlıkları                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Gizlilik > Ekran görüntüleri ve uygulamalar                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Sistem > Pil                                     | `ms-settings:batterysaver`                         |
| Sistem > Pil                                     | `ms-settings:batterysaver-settings`                |
| System > Sound                                       | `ms-settings:sound`                                |
| Sistem > Ses > Uygulama birimi ve cihaz tercihleri | `ms-settings:apps-volume`                          |
| System > Sound > Ses cihazlarını yönetme              | `ms-settings:sound-devices`                        |
| System > Depolama > Configure Depolama Sense         | `ms-settings:storagepolicies`                      |
| Saat & Dili > Tarih & saat                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Güncelleştirme & Güvenlik > Sıfırlama & kurtarma               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Güncelleştirilmiş URL'ler

Daha önce aşağıdaki iki URL, bir kullanıcıyı doğrudan belirtilen sayfalara götürmürken yalnızca ana güncelleştirmeler sayfasını engelledi. Aşağıdaki öğeler sayfalarına yönlendirecek şekilde güncelleştirilmiştir:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Geri Dönüş Tanılamasını uygulama aracılığıyla Ayarlar yapılandırma

Artık Ayarlar Uygulamasında, bir kullanıcı Geri Dönüş [Tanılaması'nın davranışını yapılandırabilirsiniz.](hololens-diagnostic-logs.md) Uygulamanın Ayarlar Gizlilik Sorunlarını **Giderme**  >  **sayfasına** gidin ve bu ayarı yapılandırabilirsiniz.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, kullanıcı bu davranışı geçersiz k aşağıdaki gibi davranamayacaktır.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla paylaşım

Hem bilgisayarlar hem de diğer Windows 10 2 cihazları da dahil olmak üzere neredeyse HoloLens cihazlarla paylaşım. Dosya veya URL'leri **bir Ayarlar** paylaşmak için Sistem Paylaşılan  >    >   Deneyimleri'HoloLens deneme yapabilirsiniz. Diğer ayrıntılar için, Windows 10'de [yakındaki cihazlarla şeyler paylaşma hakkında daha fazla bilgi Windows 10.](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

Bu özellik [Bağlantı/AllowConnectedDevices aracılığıyla yönetilebilir.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmeleri için yeni Ayarlar eklenmiştir. Güncelleştirme Ayarlar  >  **Sorun &amp; Giderme'ye gidin**  >  **Windows**  >  **Başlat'ı** **seçin.** Bu sayede, IŞLETIM sistemi güncelleştirmeleriyle sorunlarınızı yeniden üretirken, IT veya destekle ilgili sorun giderme konusunda daha iyi yardımcı olmak için izlemeleri toplamanıza olanak sağlar.

### <a name="delivery-optimization-preview"></a>Teslim İyileştirme Önizleme

Bu güncelleştirme HoloLens, birden Windows Holographic for Business cihazlardan yapılan indirmeler için bant genişliği tüketimini azaltmak üzere teslim iyileştirme ayarlarını HoloLens sağlar. Bu işlevin daha ayrıntılı bir açıklaması ve önerilen ağ yapılandırması burada mevcuttur: [güncelleştirmeleri Teslim İyileştirme için Windows 10 kullanılabilir.](/windows/deployment/update/waas-delivery-optimization)

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

### <a name="it-admin---update-checklist"></a>IT Yöneticisi - Güncelleştirme Denetim Listesi

Bu denetim listesi, geçerli cihaz yönetimi yapılandırmalarınızı veya kullanmaya başlamak istediğiniz yeni özellikleri etkileyebilecek bu özellik güncelleştirmesinde eklenen yeni öğeleri size yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi Noktası modundaki güncelleştirmeler

✔️ Bilgi [**Noktası modunda yeni uygulamalar için Yeni AUMID'ler oluşturun:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Daha önce Ayarlar uygulamasını veya Microsoft Edge Bilgi Noktası'Microsoft Edge kullanıyorsanız, bu uygulamaları farklı bir Uygulama Kimliği kullanan yeni uygulamalarla değiştiririz. Aşağıdaki Bilgi Noktası modundaki [yeni uygulamalar için Yeni AUMID'leri okumanız önemle](#use-the-new-settings-and-edge-apps-in-kiosk-modes) tavsiye edilecektir. Bu, bilgi noktası uygulamanıza sahip olmaya devam Ayarlar veya yeni uygulama uygulamanıza Microsoft Edge sağlar. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirmede daha sorunsuz bir geçişe olanak tanır.

✔️ [**Için ZiyaretçiNin Otomatik Oturum Açma Bilgileri:**](#visitor-auto-logon-for-kiosks)

Ziyaretçiler artık bir Bilgi Noktası'nde otomatik olarak oturum açabilirsiniz. Bu davranış varsayılan olarak açıktır, ancak yönetilebilir ve devre dışı bırakılabilir.

✔️ Bilgi [**Noktası modu hatası teslimi:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Oturum AAD kullanıcı grubu üyeliği AAD başarıyla belirlene değilse, başlat menüsü için genel bilgi noktası yapılandırması kullanılır (varsa) aksi takdirde kullanıcıya boş başlangıç menüsü açılır. Boş başlangıç menüsü doğrudan ayar oluşturabilecek bir yapılandırma değildir, ancak bilgi noktası kullanıyorsanız bu yeni işleme destek departmanınıza bildirmeniz gereken bir şey olabilir çünkü bu yapılandırmalar yapılandırmalar için geçerli olabilir veya atanan erişim yapılandırmalarında yeni ayarlamalar yapmak istiyor olabilir.

#### <a name="updates-to-page-settings-visibility"></a>Sayfa Ve Ayarlar Güncelleştirmeleri

✔️ [**Görünürlüğü Ayarlar Için Yeni Ayarlar URL'leri**](#new-settings-uris-for-page-settings-visibility)

Şu anda Sayfa Ayarlar [Görünürlüğü](settings-uri-list.md) kullanıyorsanız, izin verilen veya engellenen mevcut URI'ler üzerinde ayarlamalar yapmak iyi olabilir.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkeniz için güncelleştirmeler

✔️ WDAC aracılığıyla Microsoft Edge engelleme yaptıysanız WDAC ilkenizi güncelleştirmek istemeniz gerekir. Lütfen aşağıdakini gözden geçirin ve sağlanan örnek kodu kullanın.

#### <a name="enable-new-endpoints-for-edge"></a>Edge için yeni uç noktaları etkinleştirme

✔️ Ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa lütfen yeni uygulama için bu yeni uç Microsoft Edge etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

✔️ [Tanılamayı Yapılandır:](#configuring-fallback-diagnostics-via-settings-app)Geri Dönüş Tanılaması'nın tolere toplayıp toymayy ve kimlerin toplaymzı olduğunu yapılandırmış oluruz.

✔️ Cihazları[yakın cihazlarla paylaşma:](#share-things-with-nearby-devices)Yakındaki yeni paylaşım özelliğini devre dışı abilirsiniz.

✔️ için [ilke ayarlarını yapılandırma: Microsoft Edge](#configuring-policy-settings-for-the-new-microsoft-edge)için kullanılabilir olan yeni yapılandırmaları Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Yeni tanılama aracı

✔️ yeni[işletim sistemi tanılama izlemeleri:](#new-os-diagnostic-traces)Işletim Sistemi Güncelleştirmeleri ile ilgili günlükleri toplayın.

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- [Çevrimdışı tanılama,](hololens-diagnostic-logs.md#offline-diagnostics) seri numarası ve işletim sistemi sürümü için ek cihaz bilgileri de içerir.
- Çalışma zamanı sağlama paketleri aracılığıyla iş hattı uygulamalarının dağıtımıyla ilgili bir sorunu düzeltir.
- İş satırı uygulaması yükleme durumu raporlaması ile ilgili bir sorun düzeltildi.
- Cihaz sıfırlamalarında yeni uygulama paketlerinin kalıcılığıyla ilgili bir sorunu düzeltir.
- Japonca müşteriler için Edge'de yanlış sembollerin yaz yaz 2019'a neden olmasıyla ilgili bir sorun düzeltildi.
- Edge gibi önceden yüklenmiş uygulamalarla ilgili işletim sistemi güncelleştirmelerinin daha yüksek bir şekilde kullanılabilirlik sağlar.
- Güncelleştirmenin yüklemesini etkileyen bir güncelleştirme güvenilirliğini Microsoft Edge.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, sürüm 20H2 – Mayıs 2021 Güncelleştirmesi

- Derleme 19041.1146

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'de en son Windows denemeniz gerekir.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, sürüm 1903 - Mayıs 2021 Güncelleştirmesi

- Derleme 18362.1110

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. **Bu derleme artık aylık hizmet güncelleştirmelerini almayacak.** Holographic sürüm 21H1'Windows en son derlememizi denemeyi teşvik ederiz.

## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, sürüm 20H2 - Nisan 2021 Güncelleştirmesi

- Derleme 19041.1144

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İş satırı uygulaması yükleme durumu raporlaması ile ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, sürüm 1903 - Nisan 2021 Güncelleştirmesi

- Derleme 18362.1108

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Yerel bir hesap Ayarlar parola değiştirmeye çalışırken uygulamanın kilitlenmesi sorununa yol açıyor.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, sürüm 20H2 - Mart 2021 Güncelleştirmesi

- Derleme 19041.1140

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 ile fotoğraf yakalamak için AdvancedPhotoCapture veya LowLagPhotoCapture kullanan müşteriler artık fotoğraf kaydedildikten 3 saniye sonra kamera pozunu alabilir.
- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.
- Aşamalı Rollout'a kaydolan kullanıcıların cihazda oturum alamama sorunu düzeltildi.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, sürüm 1903 - Mart 2021 Güncelleştirmesi

- Derleme 18362.1102

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihaz Portalı Service'te bir bellek sızıntısı için düzeltme, hizmet tarafından bellek kullanımının artmasına neden oldu ve bu da diğer uygulamaların belleğin tamamında hataya neden oldu.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, sürüm 20H2 - Şubat 2021 Güncelleştirmesi

- Derleme 19041.1136

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- İlk cihaz kurulumu ve mağaza uygulaması güncelleştirmeleri ile ilgili bir sorunu düzeltir.
- Sonraki sürümler için yükseltme ve uçuş ile ilgili HoloLens gidermek.
- eSIM kök depolamadan kullanılmayan önceden yüklenmiş sertifikalar, HoloLens kaldırıldı.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, sürüm 1903 - Şubat 2021 Güncelleştirmesi

- Derleme 18362.1098

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, sürüm 20H2 - Ocak 2021 Güncelleştirmesi

- Derleme 19041.1134

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Cihazda çok sayıda kullanıcı olduğunda başlatma, sürdürme ve kullanıcı değiştirme sırasında performans geliştirildi.
- Araştırma Modu için arm32 [desteği eklendi.](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, sürüm 1903 - Ocak 2021 Güncelleştirmesi

- Derleme 18362.1091

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesi

- Derleme 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama Yükleyicisi aracılığıyla HoloLens 2'ye Uygulama Yükleyicisi

Uygulamaları 2 **cihaza daha sorunsuz Uygulama Yükleyicisi sağlamak** için yeni bir özellik (HoloLens) ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazları için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:

- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin cihazınıza usb üzerinden veya Edge üzerinden indirerek yüklemenin Dosya Gezgini appx paketine gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğunuz uygulamalar gibi, [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) uygulamaların da [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) İmza Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce imzalamak için kullanılan sertifikanın HoloLens cihazı tarafından güvenilir olması gerekir.

**Uygulama yükleme yönergeleri.**

1. Cihazınızın yönetilen olarak kabul edilen bir şey olduğundan emin olun
1. HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1. HoloLens 2 cihazında oturum HoloLens olun
1. Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads klasörüne kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1. HoloLens 2 cihazınızın Başlat Menüsünü açın, Tüm uygulamalar'ı seçin ve Dosya Gezgini açın.
1. İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1. yourapp.appxbundle dosyasını seçin.
1. Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Örnekleri GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamaları bulabilirsiniz.

Uygulama Yükleyicisi ile HoloLens [2'ye uygulama yükleme işleminin Uygulama Yükleyicisi.](app-deploy-app-installer.md)  

![Uygulama Yükleyicisi aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek el ile yalnızca konum güncelleştirilirken diğer ortaklar önceki bir poza göre ertelenmektedir.  Bu değişiklik, hareketlerde takip tutarlılığını artırmaya yardımcı olur; örneğin, kırpma, atma, kırpma ve kırpma.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El joint'ler inferred olduğunda, her [bir ortak](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi

- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesini ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz için sizi teşvik ederiz.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2

- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve 2 kullanıcı ve BT HoloLens yeni özellikler sunar. Otomatik Göz Konumlandırmadan Sertifika Yöneticisi'ne Ayarlar Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine. Bu yeni güncelleştirme, IT ekiplerinin cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip HoloLens ve kullanıcılara daha sorunsuz holografik deneyimler sunmaktadır.

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler eklmektedir. Ana derleme numarası aynı kalır ve Windows Güncelleştirmesi 2004 (derleme 19041) sürümüne bir aylık sürümü gösteriyor. En son 19041.1128+ derlemesinde olduğunu onaylamak için Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. Güncelleştirmeleri yönetme hakkında daha fazla bilgi HoloLens güncelleştirmeleri [yönetme'HoloLens ziyaret edin.](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows Holographic sürüm 20H2'daki yeniler  

| Özellik                                              | Açıklama                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Otomatik Göz Konumu Desteği](hololens-release-notes.md#auto-eye-position-support) | Kullanıcıların Göz İzleme ayarına girmeden göz konumlarını etkin bir şekilde hesaplama.   |
| [Sertifika Yöneticisi](hololens-release-notes.md#certificate-manager)   | Sertifika yükleme ve kaldırma için yeni basit yöntemlere izin verir Ayarlar sağlar.     |
| [USB'den sağlamayı otomatik başlatma](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB sürücülerinde paketlerin sağlanması, otomatik olarak OOBE'de sağlama sayfasına sorılır.                                                         |
| [OOBE'de sağlama paketlerini otomatik olarak onaylama](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Sağlama paketleri, sağlama sayfasından OOBE sırasında otomatik olarak uygulanır.                                                         |
| [Kullanıcı arabirimini kullanmadan otomatik sağlama](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Sağlama otomatik başlatma ve otomatik onaylamayı birlikte birleştirme. |
| [Autopilot'ı Wi-Fi kullanma](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Ethernet bağdaştırıcısına gerek kalmadan Wi-Fi otomatik pilot kullanın. |
| [Tenantlockdown CSP ve Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Kiracı kaydı ve ilke uygulandıktan sonra, cihaz yalnızca cihaz sıfırlanır veya yeniden yanıp söner. |
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli hale gelen birden çok uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens Koşullarıdır](hololens-release-notes.md#hololens-policies)                                    | Yeni ilkeler HoloLens.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların kaç gün boyunca çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz yönetimi ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [HoloLens 2 için Ayarlar sayfası görünürlüğü etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Uygulama içinde hangi sayfaların görül Ayarlar.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2'de Araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikayı geçmeyecek. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

Bu HoloLens 2'de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve geliştirilmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcı cihazı bağlı olduğu andan itibaren arka planda otomatik olarak çalışmaya başlar. Kullanıcının önceden göz izleme ayarı yoksa, Otomatik Göz Konumu 20 - 30 saniyelik bir işlem süresi sonra kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve bu nedenle kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, bir kullanıcı daha önce cihazda göz izleme ayarlama işleminin üzerinden geçilen birini ifade eder.

| Etkin Uygulama | Önceki Davranış | Windows Holographic sürüm 20H2 Güncelleştirmesi'nin davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Bakışın etkin olmayan uygulaması veya Holographic Shell |Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | İstem görüntülenmez. |
| Bakış özellikli uygulama | Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz bakışı akışına erişdiğinde görüntülenir. |

Kullanıcı, bakış etkin olmayan bir uygulamadan bakış verilerine erişen uygulamaya geçiş olursa, ayarlama istemi görüntülenir.

Diğer tüm sistem davranışları, geçerli kullanıcının etkin bir göz izleme cihazına sahip olmadığının benzeridir. Örneğin Tek Elli Başlangıç hareketi etkinleştirilmez. İlk kurulumda İlk İlk Deneyimi'ne hiçbir değişiklik olmayacaktır.

Göz bakışı verileri veya çok hassas hologram konumlandırması gerektiren deneyimler için kullanıcıların göz izleme cihazlarını çalıştırmalarını öneririz. Göz izleme ayarlama isteminden veya başlangıç menüsünden Ayarlar uygulamasını başlatarak ve ardından Sistem **> Lama**> Göz Ayarlaması'> Göz numarası çalıştır'ı seçerek erişilebilir.

Bu bilgiler daha sonra diğer ayarlama [bilgileriyle bulunabilir.](hololens-calibration.md#auto-eye-position-support)

### <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama aracı. Bu özellik, ticari ortamlarda büyük ölçekte sertifikalarınızı dağıtmanıza, sorun gidermenize ve doğrulamanıza olanak tanır.

Holographic Windows 20H2'de, HoloLens 2 Ayarlar ekliyoruz. Ayarlar > **Security & Sertifikalarını Güncelleştir > gidin.** Bu özellik, cihazınıza sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kullanımı kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için denetim, tanılama ve doğrulama araçlarını iyileştirdi.

- **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığından emin olmak veya sertifikanın uygun şekilde kaldırıldığından emin olmak.
- **Tanılama:** Sorunlar ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulama zaman kazandırır ve sorun gidermeye yardımcı olur.
- **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğunu doğrulamak, sertifikaları daha büyük ölçekte dağıtmadan önce özellikle ticari ortamlarda önemli ölçüde zaman tasarrufu sağlar.

Listede belirli bir sertifikayı hızla bulmak için ad, depolama veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar doğrudan bir sertifika da arayabilir. Tek tek sertifika özelliklerini görüntülemek için sertifikayı seçin ve Bilgi'ye **tıklayın.**

Sertifika yüklemesi şu anda .cer ve .crt dosyalarını desteklemektedir. Cihaz Sahipleri Sertifikaları Yerel Makineye ve Geçerli Kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca Geçerli Kullanıcı'ya yükleyebilir. Kullanıcılar yalnızca doğrudan Ayarlar kullanıcı arabiriminden Ayarlar kaldırabilir. Bir sertifika başka bir şekilde yüklendiyse, aynı mekanizma tarafından da kaldırılmalıdır.

#### <a name="steps-to-install-a-certificate"></a>Sertifika yükleme adımları

1. Bağlan 2 HoloLens bilgisayarınıza bağlayın.
1. Yüklemek istediğiniz sertifika dosyasını dosyanın 2. HoloLens.
1. Ayarlar **App > Update & Security > 'a gidin** ve Sertifika yükle'yi seçin.
1. Dosyayı **İçeri Aktar'a** tıklayın ve sertifikayı kaydeden konuma gidin.
1. Mağaza **Konumu'.**
1. Sertifika **Deposu'ları seçin.**
1. **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklenmiş olması gerekir.

#### <a name="steps-to-remove-a-certificate"></a>Sertifikayı kaldırma adımları

1. Ayarlar **App > Update and Security > Certificates 'a gidin.**
1. Arama kutusunda sertifikayı adıyla ara.
1. Sertifikayı seçin.
1. **Kaldır'a tıklayın**
1. Onay **istendiğinde** Evet'i seçin.

![Ayarlar uygulamasında sertifika görüntüleyici.](images/certificate-viewer-device.jpg)

![Sertifika kullanıcı arabirimini kullanarak sertifika yüklemenin nasıl olduğunu gösteren resim.](images/certificate-device-install.jpg)

Bu bilgiler daha sonra yeni [bir Sertifika Yöneticisi sayfasında bulunabilir.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>USB'den sağlamayı otomatik başlatma

- Otomatikleştirilmiş işlemler, OOBE sırasında Sağlama Paketleri ile USB Sürücüleri kullanılırken daha az kullanıcı etkileşimi sağlar.

Bu sürümden önce kullanıcıların bir düğme birleşimi kullanarak sağlama yapmak için OOBE sırasında sağlama ekranı el ile başlatmaları gerekmektedir. Artık kullanıcılar USB depolama sürücüsünde Sağlama Paketi kullanarak düğme birleşimini atlar.

1. OOBE'nin ilk etkileşime geçme anları sırasında USB sürücüyü sağlama paketiyle takın
1. Cihaz hazır olduğunda, sağlama sayfasıyla otomatik olarak istemi açar.

Not: Cihaz önyüklerken bir USB sürücü takılı bırakıldı ise OOBE mevcut USB depolama cihazını numaralandıracak ve eklerinin takılı olduğunu izler.

OOBE sırasında sağlama paketlerini uygulama hakkında daha fazla bilgi için, HoloLens [belgelerini ziyaret](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) edin.

[USB'den otomatik başlatma sağlama hakkında daha](hololens-provisioning.md#auto-launch-provisioning-from-usb) fazla bilgi için HoloLens edinebilirsiniz.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE'de sağlama paketlerini otomatik olarak onaylama

- Otomatik süreç daha az kullanıcı etkileşimine izin verirken, sağlama paketi sayfası görüntülendiğinde, listelenen tüm paketleri otomatik olarak uygular.

Sağlama ana ekranı geldiğinde, tüm sağlama paketlerinin uygulanması için OOBE 'nin otomatik olarak başlatılması için önce 10 saniye geçmesi gerekir. Kullanıcılar, bekledikleri paketleri doğruladıktan sonra bu 10 saniye içinde yine de [onaylama veya iptal](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) edebilir.

### <a name="automatic-provisioning-without-using-ui"></a>Kullanıcı arabirimi kullanmadan otomatik sağlama

- Sağlama için azaltılmış cihaz etkileşimleri için otomatik süreçler birleştirildi.

bir kullanıcı, USB cihazlarından sağlamanın otomatik olarak başlatılmasını ve sağlama paketlerinin otomatik onayını birleştirerek, cihazın kullanıcı arabirimini kullanmadan veya hatta cihazı takmadan HoloLens 2 cihaz otomatik olarak sağlayabilir. Birden çok cihaz için aynı USB sürücüsünü ve sağlama paketini kullanmaya devam edebilirsiniz. Bu, aynı alanda aynı anda birden çok cihazı dağıtmak için yararlıdır.

1. [Windows yapılandırma tasarımcısı](https://www.microsoft.com/store/productId/9NBLGGH4TX22)'nı kullanarak [bir sağlama paketi oluşturun](hololens-provisioning.md) .
1. Paketi bir USB depolama sürücüsüne kopyalayın.
1. [HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) ' ye [19041,1361 veya daha yeni bir derleme](https://aka.ms/hololens2previewdownload)yapın.
1. [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/store/productId/9P74Z35SFRS8) cihazınızın yanıp sönmesi TAMAMLANDıĞıNDA, USB-C kablonuzu sökün.
1. USB sürücünüzü cihaza takın.
1. HoloLens 2 cihazı OOBE 'de önyüklendiğinde, USB sürücüsünde sağlama paketini otomatik olarak algılayacak ve sağlama sayfasını başlatacaktır.
1. 10 saniye sonra cihaz, sağlama paketini otomatik olarak uygular.

Cihazınız artık yapılandırıldı ve [sağlama başarılı ekranı görüntülenir](hololens-provisioning.md#automatic-provisioning-without-using-ui).

### <a name="using-autopilot-with-wi-fi-connection"></a>Wi-Fi bağlantısı ile Autopilot kullanma

- Wi-Fi bağlı cihazlarda Autopilot çalışmasını etkinleştirerek, USB-C bağdaştırıcılarının Ethernet ile donanım ihtiyaçlarını azaltmaya gereksinimi ortadan kaldırılmıştır.

artık oobe sırasında, HoloLens 2 ' yi Wi-Fi ile bağlandıktan sonra, oobe cihaz için bir Autopilot profilini denetlecektir. bir tane bulunursa, AAD joın ve kayıt akışının geri kalanını tamamlaması için kullanılacaktır. Diğer bir deyişle, Ethernet ile USB-C veya Wi-Fi USB-C adaptörünün kullanılması artık bir gereksinim değildir, ancak OOBE 'nin başlangıcında sağlanmışsa çalışmaya devam ederler. [HoloLens 2 cihazları için Autopilot](hololens2-autopilot.md)hakkında daha fazla bilgi edinin.

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

- Cihaz sıfırlama veya refflash aracılığıyla bile, cihazı kiracıya kilitleyerek kuruluşun kiracısındaki cihazları tutar. , Sağlama yoluyla içinde hesap oluşturmayı engelleyerek daha fazla güvenlik ile.

HoloLens 2 cihaz artık [Windows Holographic sürümü 20h2](hololens-release-notes.md#windows-holographic-version-20h2)itibariyle tenantlockdown CSP 'yi destekliyor.

[Tenantlockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. tenantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer yeniden yanıp sönse, işletim sistemi güncelleştirmeleri, vb. için cihazda kalır.

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, ağ bağlantısından sonra OOBE, Autopilot profilinin başarıyla indirilip uygulanmasını bekler.

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, OOBE 'de aşağıdaki işlemlere izin verilmez:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma
- Çalışma zamanı sağlama aracılığıyla Azure AD JOIN işlemi gerçekleştiriliyor
- Cihaza kimin sahip olduğunu OOBE deneyiminde seçme

#### <a name="how-to-set-this-using-intune"></a>Bu Intune kullanılarak nasıl ayarlanır?

1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe düğümü için true değerini belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla kiracı kilidi ayarlanıyor.](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın.

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla geçerliyse, tenantlockdown etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>ıntune 'u kullanarak HoloLens 2 üzerinde tenantlockdown 'ın talep ırenetworkınoobe ayarı nasıl yapılır?

1. yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2 ' i kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe için false belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![Intune 'da OMA URI aracılığıyla talep ırenetworkınoobe ayarının false olarak ayarlanmasına yönelik ekran görüntüsü.](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın.

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandıktan sonra, tenantlockdown 'ın etkileri devre dışı bırakılır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Autopilot profili, maantlockdown true olarak ayarlandıktan sonra bir HoloLens için atanmazsa, OOBE sırasında ne olur?

OOBE, Autopilot profilinin indirilmek için süresiz olarak bekler ve aşağıdaki iletişim kutusu sunulacaktır. TenantLockdown 'in etkilerini kaldırmak için, önce Autopilot yalnızca bir cihaz özgün kiracısına kaydedilmelidir ve eski adımda açıklandığı gibi, TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önce bu, önkoşul olarak ayarlanmalıdır.

![Cihazda ilke uygulandığında cihaz içi görünümü.](images/hololens-autopilot-lockdown.png)

Bu bilgiler artık, [Tenantlockdown CSP ve Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)altında Autopilot 'in geri kalanının yanı sıra bulunabilir.

### <a name="global-assigned-access--kiosk-mode"></a>Genel atanan erişim – bilgi noktası modu

- Bilgi noktası için, sistem düzeyinde bilgi noktası modu uygulayan yeni bilgi noktası yöntemi etkinleştirilerek kimlik yönetimi azaltıldı.

bu yeni özellik, bir bt yöneticisinin sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için bir HoloLens 2 cihazı yapılandırmasına izin verir, sistemde hiçbir kimlikle benzeşim yoktur ve cihazda oturum açan herkese uygulanır. [HoloLens bilgi noktası modunda](hololens-kiosk.md)bu yeni özellik hakkında ayrıntılı bilgi edinin.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Birden çok uygulama bilgi noktası modunda bir uygulamayı otomatik olarak başlatma

- Otomatik uygulama başlatma ile odaklanmış deneyim, bilgi noktası modu deneyimleri için seçilen kullanıcı arabirimi ve uygulama seçimlerini daha da artırır.

Yalnızca birden çok uygulama bilgi noktası modu için geçerlidir ve atanan erişim yapılandırmasında aşağıda vurgulanan öznitelik kullanılarak otomatik başlatılacak şekilde yalnızca 1 uygulama belirlenebilir.

Uygulama, Kullanıcı oturum açtığında otomatik olarak başlatılır.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri

- Bilgi noktası modu hatalarında kullanılabilir uygulamaları ortadan kaldırarak daha güvenli bilgi noktası modu.

bilgi noktası modu ' nda hatalarla karşılaşmadan önce, başlangıç menüsündeki tüm uygulamaları göstermek için HoloLens kullanılır. artık Windows Holographic sürüm 20h2 ' de, aşağıdaki gibi başlangıç menüsünde hiçbir uygulama gösterilmez:

![Ne zaman bilgi noktası modunun başarısız olduğunu anlamak için görüntü görüntülenir.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Elerindeki

- cihazı yönetmek için HoloLens özel olarak cihaz yönetimi seçenekleri.

HoloLens 2 cihazları için yeni karma gerçeklik ilkeleri Windows Holographic version 20h2 ' de oluşturulmuştur. yeni denetlenebilir ayarlar şunlardır: parlaklık ayarlanıyor, birim ayarlama, karma gerçeklik halinde ses kaydı devre dışı bırakma, tanılama toplandığında ayarlama ve grup üyeliği önbelleği AAD.  

| yeni HoloLens ilkesi                                | Açıklama                                                                               | Notlar                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Mixedreality\parlatnessbuttondisabled              | Parlaklık düğmelerinin devre dışı olmasına izin verir ve bu sayede parlaklığı değiştirmez.       | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\VolumeButtonDisabled                  | Ses düğmelerinin devre dışı olmasına izin verir, böylece birim değişmez.               | 1 Evet, 0 Hayır (varsayılan)                                                |
| Mixedreality\mikro phonedisabled                    | HoloLens 2 ' de ses kaydı mümkün olmayacak şekilde mikrofonu devre dışı bırakır.                      | 1 Evet, 0 Hayır (varsayılan)                                                |
| MixedReality\FallbackDiagnostics                   | Tanılama günlüklerinin toplanabilmesi için davranışını denetler.                               | 0 devre dışı, 1 cihaz sahipleri için etkin, 2 tümü için etkin (varsayılan) |
| MixedReality\HeadTrackingMode                      | Daha sonraki kullanımlar için ayrılmıştır.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Azure AD gruplarını hedefleyen bilgi noktası için Azure AD grup üyeliği önbelleğinin kaç gün kullandığını denetler. | Aşağıya bakın.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Çevrimdışı bilgi noktası için Azure AD grubu üyeliğini önbelleğe alma

- 60 güne kadar bir AAD grup ile kullanılmak üzere çevrimdışı kiosks etkinleştirildi.

Bu ilke, kaç gün boyunca Azure AD grup üyeliği önbelleğinin oturum açmış kullanıcı için Azure AD gruplarını hedefleyen atanan erişim yapılandırmalarında kullanılmasına izin verileceğini denetler. Bu ilke değeri 0 ' dan büyük bir değere ayarlandıktan sonra, önbellek kullanılır.  

Ad: AADGroupMembershipCacheValidityInDays URI değeri:./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

En az-0 gün  
Maksimum 60 gün

Bu ilkeyi doğru kullanma adımları:

1. Azure AD gruplarını hedef alan bilgi noktası için bir cihaz yapılandırma profili oluşturun ve bu profili HoloLens cihaza attayın.
1. Bu ilke değerini istenen gün sayısına (> 0) ayaran ve bu değeri HoloLens cihaza atatan özel bir OMA URI tabanlı cihaz yapılandırması oluşturun.
    1. URI değeri OMA-URI metin kutusuna ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilebilir
    1. Değer izin verilen en az / en yüksek değer arasında olabilir.
1. Cihazları HoloLens ve her iki yapılandırmanın da cihaza uygulandığını doğrulayın.
1. İnternet kullanılabilir olduğunda Azure AD 1 kullanıcısı oturum açmasına izin ver. Kullanıcı oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur.
1. İlke değeri X gün sayısına izin HoloLens azure AD kullanıcı 1 artık çevrimdışı duruma HoloLens bilgi noktası modu için kullanabilir.
1. 4. ve 5. adımlar diğer Tüm Azure AD kullanıcılarının N. Önemli noktası, bilgi noktası yapılandırmasının hedeflene Azure AD grubuna üye olup olmadığını belirleyecek şekilde herhangi bir Azure AD kullanıcılarının internet kullanarak cihazda oturum açması gerektir.

> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilinceye kadar "bağlantısız" ortamlarda belirtilen hata davranışıyla karşılana kadar.

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri

- Kullanıcıların, sağlama paketleri eklemeyi veya kaldırmayı engelleme gibi belirli cihaz yönetimi ilkelerini yönetmesine izin verir.

2 cihaz için daha fazla yönetim seçeneğine izin HoloLens ilkeler.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni ilke, Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> [RemoteLock ile ilgili olarak,](/windows/client-management/mdm/remotelock-csp)HoloLens yalnızca ./Vendor/MSFT/RemoteLock/Lock yapılandırmasını destekler. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırmalar desteklenmiyor.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri

- Güç ilkeleri aracılığıyla uyku HoloLens kilitlerken daha fazla seçenek.

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumları denetlemesine olanak sağlar. Her ilke hakkında daha fazla bilgi için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows Configuration Designer'da (örneğin, 100) kullanmak için örnek değer                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows Configuration Designer'da kullanmak için örnek değer, örneğin,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery ve DisplayOffTimeoutPluggedIn için bu iki yeni ilke, Ortak Cihaz [Kısıtlamalarımıza ekleniyor.](hololens-common-device-restrictions.md)

> [!NOTE]
> 2. HoloLens tutarlı bir deneyim için, hem DisplayOffTimeoutOnBattery hem de StandbyTimeoutOnBattery değerlerinin aynı değer olarak ayarlanmış olduğundan emin olun. Aynı durum DisplayOffTimeoutPluggedIn ve StandbyTimeoutPluggedIn için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için Bkz. Boşta kalma [süreölçilerini](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) görüntüleme, uyku ve hazırda bekletme.

### <a name="newly-enabled-update-policies-for-hololens"></a>Yeni etkinleştirilen Güncelleştirme ilkeleri HoloLens

- Güncelleştirmelerin ne zaman yük devre dışı bırakıldığında veya güncelleştirmeleri sağlamak için Güncelleştirmeleri Duraklat düğmesinin devre dışı bırakılmasına yönelik diğer seçenekler.

Bu güncelleştirme ilkeleri artık 2 HoloLens etkinleştirilmiştir:

- [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Bu güncelleştirme ilkeleriyle ilgili tüm ayrıntılar ve bu ilkelerin HoloLens güncelleştirmeleri yönetme [makalesinde HoloLens okuyabilirsiniz.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Ayarlar 2 için sayfa görünürlüğü HoloLens etkinleştirildi

- Ayarlar Uygulamasında artan kullanıcı arabirimi denetimi, sınırlı sayıda sayfa göstermek için karıştırılabilir.

Artık, IT Yöneticilerinin System Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesini veya belirtilenler dışında tüm sayfalar için bunu yapmalarını sağlayan bir ilkeyi etkinleştirmiş olduk. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

2. sayfada hangi sayfa ayarlarını özelleştirebileceğinizi HoloLens için lütfen Ayarlar [sayfasını ziyaret edin.](settings-uri-list.md)

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu

Araştırma Modu'HoloLens 2, görüntü görme araştırmalarında önemli bir araç haline gelir. Önceki sürümlere kıyasla, HoloLens 2 için Araştırma Modu aşağıdaki avantajlara sahiptir:

- HoloLens (1. Nesil) Araştırma Modu'nun kullanımına açık algılayıcılara ek olarak artık bir ivmeölçer, jiroscope ve ölçer dahil olmak üzere IMU algılayıcı erişimi de sağlarsınız.
- HoloLens 2, Araştırma Modu ile birlikte kullanılan yeni özellikler sağlar. Özellikle, daha zengin bir deneme kümesi sunan, ifade edilebilir el izleme ve göz izleme API'lerine erişim.

Araştırmacılar artık araştırma cihazlarında Araştırma Modu'HoloLens dışarıdan bakan ham görüntü algılayıcılarının akışlarının tamamlarına erişmesini etkinleştirme seçeneğine sahip. HoloLens 2 için Araştırma Modu, ivmeölçer, jiroscope ve ölçer okumalarına da erişim sağlar. Kullanıcıların gizliliğini korumak için, araştırma modu aracılığıyla ham göz izleme kamera görüntüleri kullanılamaz, ancak mevcut API'ler aracılığıyla göz bakışı yönü kullanılabilir.

Diğer teknik ayrıntılar [için Araştırma Modu](/windows/mixed-reality/research-mode) belgelerine göz atabilirsiniz.

### <a name="recording-length-increased"></a>Kayıt uzunluğu artırıldı

Müşteri geri bildirimi nedeniyle karma gerçeklik yakalamalarının [kayıt uzunluğunu artırıldı.](holographic-photos-and-videos.md) Karma gerçeklik yakalamaları artık varsayılan olarak 5 dakikayla sınırlı olmayacak, bunun yerine kullanılabilir disk alanı temel alarak maksimum kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanını %80'e kadar olan kullanılabilir disk alanını temel alarak maksimum video kayıt süresini tahmin eder.

> [!NOTE]
> Aşağıdaki HoloLens biri gerçekleşirse varsayılan video kayıt uzunluğunu (5 dakika) kullanır:
>
> - Tahmini maksimum kayıt süresi, varsayılan 5 dakikadan küçüktür.
> - Kullanılabilir disk alanı toplam disk alanı %20'den azdır.

Holografik fotoğraflar ve videolar [belgemizde tüm gereksinimleri bulabilirsiniz.](holographic-photos-and-videos.md#maximum-recording-length)

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Windows Holographic sürüm 20H2 güncelleştirmesinde iyileştirmeler ve düzeltmeler:

- OOBE'de daha fazla ekran artık koyu moddadır.
- Daha fazla bilgi edinmek için çevrimiçi olarak en son Gizlilik Bildirimi'ne işaret edin.
- Kullanıcıların sağlama paketleri aracılığıyla VPN profilleri sağlamama sorunu giderildi.
- VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi.
- İlke, AllowUsbConnection için NCM için MDM aracılığıyla USB işlevlerinin numaralandırıcısını devre dışı bırakmak için güncelleştirildi.
- Cihaz tek uygulamalı bilgi noktası HoloLens medya aktarım protokolü (MTP) üzerinden Dosya Gezgini'de bir cihaz göstermesini engelleyen bir [sorun giderildi.](hololens-kiosk.md) MTP 'nin (ve genel olarak USB bağlantısının) [AllowUSBConnection ilkesi](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) kullanılarak devre dışı bırakılabilir olduğunu unutmayın.
- Uygulamanın simgelerini bilgi noktası Başlat menüsü doğru şekilde ölçeklendiren bir sorun düzeltildi.
- HTTP önbelleğinin Azure AD gruplarına hedeflenen bilgi noktası moduyla engellemesi nedeniyle bir sorun düzeltildi.
- Kullanıcıların Geliştirici modunu devre dışı bırakarak geliştirici modunu yeniden etkinleştirmediği sürece paket sağlama ile Geliştirici modunu etkinleştirdikten sonra Eşleştir düğmesini kullanamadığı bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, sürüm 1903 - Kasım 2020 Güncelleştirmesi

- Derleme 18362.1085

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 20H2'nin en son Windows sürümünü denemeniz gerekir.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, sürüm 2004 - Ekim 2020 Güncelleştirmesi

- Derleme 19041.1124

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çalışma zamanı sistem hatasına neden olan gereksiz bir denetim kaldırıldı.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, sürüm 1903 - Ekim 2020 Güncelleştirmesi

- Derleme 18362.1081

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, sürüm 2004 - Eylül 2020 Güncelleştirmesi

- Derleme 19041.1117

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Appxmanifest'Visual Studio SupportsMultipleInstances="true" olduğunda uygulamanın hata ayıklamasını engelleyen bir sorunu giderin.
- Bu sürüm, ağ ara sunucusu üzerinden başarısız İnternet algılamayı ele alan NCSI proxy algılama düzeltmesi içerir. NCSI, İnternet bağlantısı algılama için makine ara sunucusunu ve profil başına ara sunucu kullanabilir. Kullanıcı başına ara sunucu, gelecek sürümlerde NCSI tarafından desteklenecegizli olacak.
- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağı doğru eğiktir. Daha yeni HoloLens 2, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
- Belirli senaryolarda daha az izleme kaybıyla sonuçlanacak gelişmiş el izleme sağlamlığı.
- Bu sürüm, video yakalama sorunlarına katkıda bulunarak ses zaman damgası kalitesini geliştirmeye ilişkin bir düzeltme içerir.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, sürüm 1903 - Eylül 2020 Güncelleştirmesi

- Derleme 18362.1079

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağı doğru eğiktir. Daha yeni HoloLens 2, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
- Belirli senaryolarda daha az izleme kaybıyla sonuçlanacak gelişmiş el izleme sağlamlığı.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, sürüm 2004 - Ağustos 2020 Güncelleştirmesi

- Derleme 19041.1113

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Ayarlar uygulama artık Iris Kaydı veya Göz İzleme Ayarlama deneyimlerine kullanıcı takip etmemektedir.
- OOBE sırasında cihazı yeniden adlandıran ve diğer eylemleri (ağa bağlanma gibi) gerçekleştiren sağlama paketinin yeniden adlandırma nedeniyle cihaz yeniden başlatıldıktan sonra diğer eylemleri gerçekleştirememe hatası düzeltildi.
- Görsel kalitesini geliştirmek için ilk cihaz kurulumu akışlarının renk düzeni değiştirildi.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, sürüm 1903 - Ağustos 2020 Güncelleştirmesi

- Derleme 18362.1074

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Windows Holographic sürüm 2004 için en son derlemelerimizi denemeniz gerekir.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, sürüm 2004 - Temmuz 2020 Güncelleştirmesi

- Derleme 19041.1109

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Geliştiriciler artık güvenli bağlantı gerektiren bir uygulamanın etkinleştirilmesi veya devre Cihaz Portalı arasında seçim olabilir.
- Uygulamanın işletim sistemi güncelleştirmeleri sonrasında başlatılması için güvenilirlik artırıldı.
- Varsayılan gelen kutusu parlaklığı yüzde 100 olarak değiştirildi.
- HoloLens 2'de, Windows Cihaz Portalı için HTTPS iletmeyle ilgili bir HoloLens giderildi.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, sürüm 1903 - Temmuz 2020 Güncelleştirmesi

- Derleme 18362.1071

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamalarında izleme kaybı veya yeniden izleme elde edilirken hologramların kaybolmasına neden olan bir sorun düzeltildi.
- Belirli cihazlarda donanım hızlandırma ile HoloLens sırasında özel uygulama uygulamalarının kabukta kilitlenmesi HoloLens Emulator bir sorun düzeltildi.
- HoloLens 2'de Windows Cihaz Portalı https iletme ile ilgili bir sorun giderildi.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, sürüm 2004 - Haziran 2020 Güncelleştirmesi

- Derleme 19041.1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirli özellikler belirtilmezse yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses hatalarını **ortadan** kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, bir web tarayıcısı geçersiz sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı bu durumla devam etmek mümkün değildir. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş cihazından tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- HoloLens öykünücüsünü siyah olarak işlemek için piksel biçimlerini değiştirmeye neden olan HoloLens düzeltildi.
- Iris oturum açma sırasında kilitlenmeye neden olan bir hata düzeltildi.
- Zaten geçerli olan uygulamalar için yinelenen mağaza indirmeleri ile ilgili bir sorun düzeltildi.
- Çevreleyici uygulamaların arka arkaya uygulama açmasını engelleyen Microsoft Edge düzeltildi.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.
- Geliştirilmiş performans ve güvenilirlik.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, sürüm 1903 - Haziran 2020 Güncelleştirmesi

- Derleme 18362.1064

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri, belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, arka planda çalıştıracak ayar etkinleştirilse bile, bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Piksel biçimlerini siyah HoloLens olarak değiştiren uygulamalara neden olan bir sorun HoloLens Emulator.
- 1903 sürümü güncelleştirildikten sonra Photos uygulamasının ilk başlatmalarda başlatılmasıyla ilgili bir sorun düzeltildi.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, sürüm 2004

- Derleme - 19041.1103

HoloLens 2, Windows Holographic için Mayıs *2020* ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5G/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni özellikler içerir. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve   Güncelleştirmeleri **Denetleme düğmesini** ****   seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak yeni cihazları üretim için önceden yapılandırma ve sorunsuz bir şekilde ayarlama                 |
|       FIDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamasını etkinleştirmek için FIDO2 Güvenlik Anahtarları desteği            |
|       Geliştirilmiş sağlama                      |          Usb sürücüden uygulamanıza sorunsuz bir şekilde bir sağlama paketi HoloLens                              |
|       Uygulama yükleme durumu                 |          MDM aracılığıyla Ayarlar 2'ye HoloLens uygulamanın yükleme durumunu denetleme               |
|       Yapılandırma hizmeti sağlayıcıları (CSP'ler)   |          Yönetici denetimi özelliklerini geliştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği 5G/LTE desteği sağlar                                    |
|       Koyu uygulama modu                              |          Hem koyu hem de açık modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir ve görüntüleme deneyimini geliştirin        |
|       Sesli komutlar                             |          Uygulamasız ses denetimi için ek sistem HoloLens desteği                           |
|       El izleme geliştirmeleri                 |          El izleme geliştirmeleri düğmeleri ve 2D sayfalı etkileşimleri daha doğru hale sağlar                        |
|       Kalite geliştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik geliştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot desteği

Windows HoloLens 2 için Autopilot, cihaz satış kanalının Intune kiracınıza HoloLens önceden kaydolmasına olanak sağlar. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazır olur. Kendi kendine dağıtımdan yararlanmak için cihazın kurulumun ilk ekranı sırasında USB-C-Ethernet kullanarak bir ağa bağlanması gerekir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başladıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme.
1. Cihazı Microsoft Intune (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.
1. Cihaz hedefli ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlama.
1. Oturum açma ekranı kullanıcıya gösterilir.

[Windows autopilot for HoloLens 2 değerlendirme kılavuzundan daha fazla bilgi edinin.](hololens2-autopilot.md)

*Şimdi AutoPilot önizlemeye katılmak için Hesap Yöneticinize ulaşın. Autopilot'a hazır cihazlar yakında gönderime başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

Bazı kullanıcılar, HoloLens veya okul ortamındaki diğer kullanıcılarla bir cihaz paylaşır. Bu nedenle, kullanıcıların uzun kullanıcı adları ve parolalar yazmadan kolayca ulaşabiliyorları önemlidir. Fast Identity Online (FIDO), bir kullanıcı adı veya parola girmeden, kuruluşta (Azure AD kiracısı) HoloLens oturum açmasına olanak sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktöründe getirilebilir, standartlara dayalı bir parolasız kimlik doğrulama yöntemidir. FIDO, parolasız kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kaynaklarında kullanıcı adı veya parola olmadan oturum açmalarına olanak sağlar. Bunun yerine bir dış güvenlik anahtarı veya cihazda yerleşik olarak yer alan bir platform anahtarı kullanırlar.

Çalışmaya başlama için [bkz. Parolasız güvenlik anahtarı oturum açmasını etkinleştirme.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

Paketleri sağlama, HoloLens deneyimi yerine yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamayı sağlar. Daha önce, sağlama paketlerinin şirket içi belleğe HoloLens vardı. Artık bir USB sürücüde olabilir, böylece birden çok cihaz üzerinde daha kolay yeniden HoloLens cihazları paralel olarak silebilirsiniz. Paket sağlama artık cihaz yönetimine kaydolmak için bir alanı da desteklemektedir, bu nedenle sağlama sonrasında el ile kurulum yoktur.

Denemek için:

1. Windows Windows Configuration Designer'ın en son sürümünü Windows bilgisayarınıza indirin.
1. 2 **HoloLens**  >  **Sağlama'HoloLens Cihazlar'ı seçin.**
1. Yapılandırma profilinizi oluşturun. Ardından, oluşturulan tüm dosyaları bir USB-C depolama cihazına kopyalayın.
1. USB-C cihazını yeni yanıp sönen herhangi bir cihaza HoloLens. Ardından, sağlama **paketinizi**  +  **uygulamak** için güç düğmesine basın.

### <a name="line-of-business-application-install-status"></a>İş yeri uygulaması yükleme durumu

İş hattı uygulamaları için MDM uygulama dağıtımı ve yönetimi, iş HoloLens. Yöneticilerin ve kullanıcıların denetim ve tanılama için uygulama yükleme durumunu görüntülemesi gerekir. Bu sürümde, hesap bilgilerinize Ayarlar veya okula erişim için daha fazla ayrıntı  >    >    >    >  **ekledik.**

### <a name="additional-csps-and-policies"></a>Ek CSP'ler ve ilkeler

Yapılandırma [hizmeti sağlayıcısı (CSP),](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu sürümde, yöneticilerin dağıtılmış ve dağıtılmış cihazlarında denetim sayısını artırmak için daha fazla ilkeye HoloLens ekleeceğiz. HoloLens tarafından desteklenen CSP'ler listesi için bkz. [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

Bu sürümde yeni olan:

**İlke CSP'si** 

İlke yapılandırma hizmet sağlayıcısı, kuruluşa şirket dışı cihazlarda Windows sağlar. Bu sürümde, burada listelenen HoloLens yeni ilkeler ekledik. Daha fazla bilgi için [bkz. 2. HoloLens tarafından desteklenen İlke CSP'leri.](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessAccessAccesseInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

NetworkQoSPolicy yapılandırma hizmeti sağlayıcısı, ağ hizmet kalitesi (QoS) ilkeleri oluşturur. QoS ilkesi, bir dizi eşleşen koşulları temel alarak ağ trafiği üzerinde bir dizi eylem gerçekleştirir. Daha fazla bilgi için bkz. [NetworkQoSPolicy CSP.](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE bağlantısı olan cihazlar için genişletilmiş USB Ethernet desteği

5G/LTE telefonlar ve Wi-Fi etkin noktaları gibi belirli mobil geniş bant cihazlarının USB aracılığıyla HoloLens 2'ye bağlanarak etkin noktaları etkinleştirme desteği eklendi. Bu cihazlar artık ağ ayarlarında **başka bir** Ethernet bağlantısı olarak görüntülenir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmiyor.) Bu işlevsellik, Wi-Fi kullanılabilir değilse ve Wi-Fi yeterli performansa sahip değilse yüksek bant genişliğine sahip bağlantıları sağlar. Desteklenen USB cihazları hakkında daha fazla bilgi edinmek için [bkz. Bağlan ve USB-C Bluetooth için bkz.](hololens-connect-devices.md).  

### <a name="hand-tracking-improvements"></a>El izleme geliştirmeleri

Bu sürüm çeşitli el izleme geliştirmeleri içerir:

- **Duruş kararlılığını işaret ediyor:** Sistem artık dizin tarafından gizli olduğu zaman dizin parmaklarını bağlamaya karşı koyan bir sistemdir. Bu değişiklik düğmeleri itme, yazma, içerik kaydırma ve daha fazlasının doğruluğunu artırır! 
- **Yanlışlıkla havadan dokunma azaltıldı:** Havadan dokunma hareketi algılamasını iyileştirildi. Bazı yaygın senaryolarda ellerinizi yanlarına bırakmanız gibi yanlışlıkla yapılan etkinleştirme sayısı artık daha azdır.
- **Kullanıcı anahtarı güvenilirliği:** Artık bir cihazı paylaşırken el boyutunu güncelleştirme konusunda sistem daha hızlı ve daha güvenilirdir.
- **Azaltılmış el çalma:** Algılayıcıların görünümünde ikiden fazla el olduğu durumların işlenmesini iyileştirildi. Birden çok kişi birbirine yakın bir şekilde çalışıyorsa, artık takip edilen el kullanıcıdan sahnede başka birinin ele "atlayıp" atlama ihtimali çok daha düşüktür.
- **Sistem güvenilirliği:** Cihaz yüksek yük altındayken el izlemenin çalışmayı durdurmasına neden olan bir sorun düzeltildi.

### <a name="dark-mode"></a>Koyu mod

Birçok Windows artık hem koyu hem de açık modlarını destekliyor. HoloLens 2 kullanıcı, her ikisini de destekleyen uygulamalar için varsayılan modu seçebilir. Güncelleştirmeden sonra varsayılan uygulama modu "koyu" olur, ancak bu ayarı kolayca değiştirebilirsiniz: Sistem **Renkleri'ne Ayarlar**  >    >    >  **Varsayılan uygulama modunu seçin.**

Bu "in-box" uygulamaları koyu modu destekler:

- Ayarlar
- Microsoft Store
- Posta
- Takvim
- Dosya Gezgini
- Geri Bildirim Merkezi
- OneDrive
- Fotoğraflar
- 3B Görüntüleyici
- Filmler & TV

![Koyu mod pencereleri kutucuklı.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Sistem sesli komutları

Artık, cihazdaki herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için bkz. [HoloLens çalıştırmak için sesinizi kullanma](hololens-cortana.md). ayrıca [HoloLens 2 için desteklenen diller](hololens2-language-support.md)bölümüne bakın.  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

güncelleştirilmiş uygulama, cihazlarınız arasında daha fazla işlem yapmanıza yardımcı olmak için Microsoft 365 ile tümleşir (şu anda yalnızca US-English). HoloLens 2 ' de, Cortana birimi ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklememektedir. Bu seçenekler artık yeni sistem ses komutları tarafından desteklenmektedir. [blogumuza](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)yeni Cortana uygulaması hakkında daha fazla bilgi edinin.

### <a name="quality-improvements-and-fixes"></a>Kalite iyileştirmeleri ve düzeltmeleri

Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:  

- Etkin bir görüntüleme ayarlama sistemi sunuldu. Bu özellik hologragram kararlılığını ve hizalamasını geliştirir. Başlarınızı yan yana hareket ettirmek için artık yerinde kalabilirler.
- Wi-Fi akışının HoloLens düzenli aralıklarla kesintiye uğradığından hata düzeltildi. Bir uygulama düşük gecikmeli akış için ihtiyacı olduğunu gösteriyorsa, [Setsocketmediastreamingmode işlevini](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)çağırarak bu çözümü uygulayın.
- Araştırma modunda akış sırasında oluşan bir cihaz askıda kalması düzeltildi.
- Bir oturum sürdürülürken, bazı durumlarda oturum açma ekranında doğru kullanıcının görüntülenmediğini bir hata düzeltildi.
- kullanıcıların MDM günlüklerini **Ayarlar** aracılığıyla dışarı aktarmadık bir sorun düzeltildi.
- Hazır kurulum 'un doğruluk izlemenin bekleninden daha düşük olması nedeniyle oluşan bir sorun düzeltildi.
- Göz izleme alt sisteminin belirli koşullar altında başlatma veya ayarlama yapma işleminin başarısız olduğu bir sorun düzeltildi.
- Zaten kalibre edilmiş bir kullanıcı için göz ayarlamaya sorulacak bir sorun düzeltildi.
- Bir sürücünün göz ayarlama sırasında çöktüğünde bir sorun düzeltildi.
- Yinelenen güç düğmesi bastığı bir sorun düzeltildi, 60 saniyelik bir sistem zaman aşımı ve kabuk kilitlenmesine neden olabilir.
- Derinlik arabellekleri için iyileştirilmiş kararlılık.
- Geri bildirim merkezinde, kullanıcıların daha kolay geri bildirimde bulunmak için bir **paylaşma** düğmesi eklendi.
- Roboryardım 'ın doğru şekilde yüklendiği bir hata düzeltildi.

### <a name="known-issues"></a>Bilinen sorunlar

- Zh-CN sistem diliyle ilgili bir sorun, sesli komutların karma gerçeklik yakalama almasını veya cihaz IP adresini görüntülemesini engeller.
- bir sorun, cihazı "Hey Cortana" ses etkinleştirmesini kullanacak şekilde başlattıktan sonra Cortana uygulamasını başlatmanız gerekir. bir 18362 yapıdan güncelleştirdiyseniz, artık **başlangıç** aşamasında çalışmamış Cortana uygulamasının önceki sürümü için ikinci bir uygulama kutucuğu görebilirsiniz.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, sürüm 1903-Mayıs 2020 güncelleştirme

- Derleme 18362,1061

bu aylık kalite güncelleştirmesi, daha önce açıklandığı gibi, takım Windows Holographic sürüm 2004 ' de çalıştığı için herhangi bir önemli değişikliği içermez.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, sürüm 1903-Nisan 2020 güncelleştirme

- Derleme 18362,1059

**Desteklenen uygulamalar için koyu mod**

birçok Windows uygulama hem koyu hem de hafif modunu destekler. HoloLens 2 müşteri artık hem renk düzenlerini destekleyen uygulamalar için varsayılan modu seçebilirler. müşteri geri bildirimlerine bağlı olarak, varsayılan uygulama modunu "koyu" olarak ayarlarız, ancak bu ayarı dilediğiniz zaman kolayca değiştirebilirsiniz: **"varsayılan uygulama modunu seçin"** bulmak için **Ayarlar > sistem > rengine** gidin.

Bu "yerleşik" uygulamalar koyu modunu destekler:

- Ayarlar
- Microsoft Store
- Posta
- Takvim
- Dosya Gezgini
- Geribildirim Merkezi
- OneDrive
- Fotoğraflar
- 3B görüntüleyici
- TV & Filmler

**Güncelleştirmede Ayrıca geliştirmeler ve düzeltmeler:**

- Kabuk Yerpaylaşımları karma gerçeklik yakalamalarına dahil edilmiştir.
- Gerçek olmayan geliştiriciler artık cihaz portalındaki 3B görünüm sayfasını kullanarak uygulamalarını test edebilir ve hatalarını ayıklamanıza olanak sağlar.
- *Holographicdepthreprojectionbir yöntemi DepthReprojection* algoritması kullanıldığında karma gerçeklik yakalamadaki iyileştirilmiş hologram kararlılığı.
- 32-bit ARM uygulamalarında "WinRT ıstreamsocketlistener API sınıfı kaydedilemedi" hatası düzeltildi.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, sürüm 1903-Mart 2020 güncelleştirme

- Derleme 18362,1056

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- *Holographicdepthreprojection, oto planar* algoritması kullanıldığında karma gerçeklik yakalamadaki iyileştirilmiş hologram kararlılığı.
- Bir derinlik MF örneğine eklenen koordinat sisteminin ortak belgelerle tutarlı olmasını sağlar.
- Müşterilerin cihaz portalı üzerinden büyük miktarlarda metin yapıştırmasını sağlayarak geliştirilmiş geliştirici verimliliği.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, sürüm 1903-Şubat 2020 güncelleştirme

- Derleme 18362,1053

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamaları için HolographicSpace. Uservarlığına yönelik API geçici olarak devre dışı bırakıldı. Bu değişiklik, "arka planda çalıştır" ayarı etkinleştirilmiş olsa bile, bazı uygulamaların, vizörü çevrildikten sonra duraklamasını engelleyen bir sorunu önler.
- Kullanıcının bir kullanıcı arabirimi dontığı ve birkaç saniye sonra kabuğa geri dönmesi fark eden, izlenen bir rastgele kilitlenme çökme düzeltildi.
- Gelişmiş izleme, Dizin parmağınızla yer ayırdığınızda, o parmağınızla büyük bir kısmı beklenmedik şekilde eğilerek daha az olabilir.
- Baş izlemenin, uzamsal eşlemenin ve diğer çalışma zamanlarının güvenilirliği geliştirildi.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, sürüm 1903-Ocak 2020 güncelleştirme

- Derleme 18362,1043

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 öykünücüsü ile çalışırken özel uygulamalar için iyileştirilmiş kararlılık.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, sürüm 1903-Aralık 2019 güncelleştirme

- Derleme 18362,1042

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Son aşama üretilmesi (LSR) düzeltmeleri tanıtılmıştır. Daha kararlı ve daha doğru bir şekilde hesaba göre daha kararlı ve net bir şekilde görüntülenmesi için hologragram geliştirilmiş görsel işleme. Bu belirti, uygulamalar hologragram derinliğini doğru şekilde ayarlamazsanız bu güncelleştirmeden sonra daha belirgin olacaktır.
- Özel uygulamaların ve özel uygulamalar arasında gezinmesinin sabit kararlılığı.
- Karma Gerçeklik yakalamanın birkaç gün boyunca bekleme durumunda olduktan sonra video kaydedemediği bir sorun çözüldü.
- İyileştirilmiş hologram kararlılığı.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, sürüm 1903-Kasım 2019 güncelleştirme

- Derleme 18362,1039

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- En-CA ve en-AU için ilk kurulum sırasında sesli komut **seçme** işlevlerinin sabit işlevselliği.
- En son Unity ve karma gerçeklik araç seti (MRTK) sürümlerine daha fazla yerleştirilmiş olan nesnelerin geliştirilmiş görsel kalitesi.
- Başlat menüsü açılıp kapanana kadar başlangıçta durdurulmuş bir durumda takılarak holographic uygulamalarla ilgili sorunlar düzeltildi.
- HoloLens 2 ve öykünücü için openxr çalışma zamanı uyumluluk düzeltmeleri ve geliştirmeleri.
