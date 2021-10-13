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
ms.openlocfilehash: c45a9a05cc7911bc9866df5e4313bc27a205d333
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924485"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 sürüm notları

HoloLens cihazlarınızla üretken bir deneyiminizin olduğundan emin olmak için özellik, hata ve güvenlik güncelleştirmelerini serbest bırakmaya devam ediyoruz. bu sayfada, her ay HoloLens yenilikleri görebilirsiniz. en son HoloLens 2 güncelleştirmesini almak için güncelleştirmeleri denetleyebilir ve [gelişmiş kurtarma yardımcısı aracılığıyla cihazınızı flash](hololens-recovery.md#clean-reflash-the-device) [ile el ile güncelleştirebilir](hololens-update-hololens.md#check-for-updates-and-manually-update) veya tam flash güncelleştirmesi (ffu) alabilirsiniz. [İndirme](https://aka.ms/hololens2download) güncel tutulur ve en son genel kullanıma sunulan derlemeyi sağlar.

> [!NOTE]
> son Windows 11 duyurusu, Windows bilgisayar sürümüne odaklanmıştı. son zamanlarda [2021 ekim ' de 2 ' ye HoloLens 2 ' ye büyük bir işletim sistemi güncelleştirmesi](#windows-holographic-version-21h2)başladık ve müşteri geri bildirimlerine göre daha yaklaşan yayınlar üzerinde çalışıyoruz.

## <a name="windows-holographic-version-21h2"></a>Windows Holographic, sürüm 21H2

- Derleme 20348,1432

Windows Holographic sürüm 21h2 artık kullanılabilir ve 2 kullanıcı ve bt uzmanlarına HoloLens harika yeni özellikler sunuyor. Bu, geliştirilmiş sorun giderme ve cihaz raporları, bilgi noktası modundaki bazı sabit hatalar ve sertifika Görüntüleyicisi, genişletilmiş yönetilebilirlik yüzeyi ve artırılmış güncelleştirme güvenilirliği hakkında bilgi sunar. bu özellik güncelleştirmesinin yeni bir flaggeme özelliği, hareketli Platform modumuza HoloLens geliyor. HoloLens 2 ' nin tüm yeni harika özelliklerine göz atın!

Bu en son sürüm 21H1 sürümüne yönelik aylık bir güncelleştirmedir, ancak bu kez yeni özellikler de ekledik. ana yapı numarası aynı kalacaktır ve Windows Update sürüm 21h1 (derleme 20348) için aylık bir yayın olduğunu belirtecektir. en son kullanılabilir derleme 20348.1432 + ' de olduğunu onaylamak için Ayarlar > ekranında yapı numaranızı görebilirsiniz. en son sürüme güncelleştirmek için Ayarlar uygulamasını açın, güncelleştirme & güvenlik ' e gidin ve güncelleştirmeler için denetle ' ye dokunun. HoloLens güncelleştirmelerinin nasıl yönetileceği hakkında daha fazla bilgi için, [HoloLens güncelleştirmelerini yönet](hololens-updates.md) ' e gidin.

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
artık [Windows Holographic, sürüm 21h2](hololens-release-notes.md#windows-holographic-version-21h2)' ye eklenmiştir, çevrimdışı tanılamalar için iki tür audiogörsel geri bildirimi vardır. Koleksiyon başladığında ve tamamlandığında, her ikisi için de her ikisi için bir bildirim görüntülendi. Bunlar Kullanıcı oturum açtığında görüntülenir ve görseller vardır.

![Günlüklerin toplanması için bildirim.](./images/logcollection1.jpg)

![Günlük toplama tamamlandığında bildirim.](./images/logcollection2.jpg)

Kullanıcılar, bir görüntüleme erişimi olmayan için bir geri dönüş günlüğü toplama mekanizması olarak çevrimdışı tanılama kullandığından, oturum açma veya hala OOBE 'de yer alma, Günlükler toplandığında yürütülen bir ses destesi de olacaktır. Bu ses, bildirim bildirimine ek olarak çalınacaktır.

Bu yeni özellik, cihazınız güncelleştirildiğinde etkinleştirilecek ve etkinleştirilmesi veya yönetilmesi gerekmez. Bu yeni geri bildirimin görüntülenemediğini veya duyulmayacak herhangi bir olayda, çevrimdışı tanılama yine de oluşturulacaktır.

Daha yeni bir audiogörsel geri bildirimi eklenmesini umuyoruz ve daha hızlı bir şekilde Tanılama verileri toplanmanız ve sorunlarınızı giderebilmek daha kolay olacaktır.

Bu bilgiler daha sonra [tanılama günlükleri sayfasında](hololens-diagnostic-logs.md#offline-diagnostics)görüntülenebilir.

#### <a name="overview-to-try-out-the-diagnostics-notifications"></a>Tanılama bildirimlerini denemek için genel bakış

1. Cihazınızın kilidini açın ve bunu aşın.
1. [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)toplamak için **Güç** ve **ses aşağı** düğmesi birleşimine basın.
1. Cihazınızın başlatıldığı ve günlüklerin toplanması tamamlandığında bildirim bildirimlerini görüntüleyin ve ses ipuçlarını dinleyin.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü koleksiyonu geliştirmeleri

Tanılama günlükleri toplandığında bir cihazın disk alanında yetersiz olduğu durumlarda, **StorageDiagnostics.zip** adlı ek bir rapor oluşturulur. düşük depolama eşiği Windows [depolama alanı algılaması](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)tarafından otomatik olarak belirlenir.

Bu bilgiler daha sonra [tanılama günlükleri sayfasında](hololens-diagnostic-logs.md#offline-diagnostics)görüntülenebilir.

#### <a name="overview-to-try-out-the-low-storage-improvements"></a>Düşük depolama geliştirmelerini denemek için genel bakış

1. Cihazınızın depolama alanını doldurup dolduralım.
1. [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)toplamak için **Güç** ve **ses aşağı** düğmesi birleşimine basın.
1. HoloLens belgeler klasöründe depolanan Günlükler koleksiyonunda yeni bir dosya olduğunu gözlemleyin.

### <a name="csp-changes-for-reporting-hololens-details"></a>raporlama HoloLens ayrıntıları için CSP değişiklikleri

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
> - otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için desteklenir.

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

HoloLens için etkin olan, bt yöneticilerinin güncelleştirme uygulanmasına izin verirken güncelleştirilmesi başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir zaman tarihi ayarlamasına izin veren yeni bir ilkedir. Bunlar, zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilir. Bu ilkeyi kullanma hakkında daha fazla bilgi edinmek için lütfen [ApplicationManagement/Scheduleforcerestartforupdatebaşarısızlıklarını](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)görüntüleyin.

Bu bilgiler daha sonra [iş için uygulama dağıtım Deposu sayfasında](app-deploy-store-business.md)bulunabilir.

#### <a name="overview-to-try-smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için akıllı yeniden denemeyi denemeye genel bakış

1. Yeni akıllı yeniden deneme özelliğini yapılandırın.
1. Uygulamanızı henüz almamış ve doğru şekilde yapılandırılmış bir cihazda çevrimiçi ortamda oturum açın.
1. Cihazı kapatma veya bağlantısını kesme yoluyla uygulamayı indiremiyor.
1. Cihazınızı açık bir şekilde kapatıp, yükleme işlemini yeniden denemek için tetiklediğiniz zamanda internet 'e bağlanın.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın

RequirePrivateStoreOnly ilkesi HoloLens için etkinleştirildi. bu ilke, Microsoft Store uygulamasının yalnızca kuruluşunuz için yapılandırılmış özel mağazayı [İş İçin Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)aracılığıyla yapılandırmak üzere yapılandırılmasını sağlar. Erişimi yalnızca kullanılabilir hale getirdiğiniz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) hakkında daha fazla bilgi edinin

Bu bilgiler daha sonra [iş için uygulama dağıtım Deposu sayfasında](app-deploy-store-business.md)bulunabilir.

#### <a name="overview-to-try-only-private-store-apps"></a>Yalnızca özel mağaza uygulamalarını denemeye genel bakış

1. [MDM](hololens-mdm-configure.md)aracılığıyla cihazlarınız için yeni ilkeyi yapılandırın.
1. İlkeye sahip bir cihazda oturum açın.
1. Microsoft Store uygulamasını açın ve kuruluşunuzun uygulamalarını görebilmenizi sağlayabilirsiniz.

### <a name="use-wdac-and-lob-apps"></a>WDAC ve LOB uygulamalarını kullanma

Artık uygulama veya işlemlerin başlatılmasını engellemek için WDAC kullanabilir ve kendi işlem hattınızdan oluşan uygulamalarınızı kullanmaya devam edebilirsiniz. Artık bunlara WDAC ilkenizde izin verebilirsiniz. Bu ilkenin kullanılması, WDAC ilkenizi oluştururken PowerShell 'de ek bir kod satırı çalıştırmayı içerir. [Buradaki adımları gözden geçirin.](/mem/intune/configuration/custom-profile-hololens)

#### <a name="overview-to-try-your-own-apps-while-using-wdac-to-block-others"></a>Diğer uygulamaları engellemek için WDAC kullanırken kendi uygulamalarınızı denemeye genel bakış

1. LOB uygulamanızın Aumkimliklerini ve engellemeyi planladığınız uygulamaları toplayın.
1. Yeni adımları izleyerek [Yeni BIR WDAC Ilkesi oluşturun](/mem/intune/configuration/custom-profile-hololens) .
1. [ILKEYI MDM kullanarak cihazınıza dağıtın](hololens-mdm-configure.md) .
1. Cihazda oturum açın ve uygulamanızı başlatıp diğerlerini engelleyebilmenizi sağlayabilirsiniz.

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler

#### <a name="for-developers"></a>Geliştiriciler için

- Bir [cihaz portalı için, kilitli dosyaları indirmede hiçbir istem olmadığı bilinen bir sorun](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)düzeltildi.
- [Karşıya dosya yükleme ve indirme zaman aşımları Ile cihaz portalı 'nın bilinen bir sorunu](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)düzeltildi.
- 2B uygulamalar için oyun yüzeyi işleme, Insider Derlemeleriyle devre dışı bırakıldı. Bu uygulamayı kaldırarak, uygulamalar artık oyun yüzeyi API 'Lerini doğrudan kullanabilir ve tüm denetim kümesine erişebilir ve daha fazlasını yapmak için göz önünde bulundurularak geliştirilebilir. Geliştiriciler oyun yüzeyi girişini tüketmek için oyun yüzeyi API 'Lerini kullanmalıdır. Bu, [oyun yüzeyi sınıfı (Windows için bir örnektir. Gaming. ınput)-UWP uygulamalarını Windows](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true).
- uygulamaların, HoloLens oturum açan kullanıcı için bilgi noktası modunda HoloLens çalışıp çalışmadığını belirleyebilmesi için [atanan erişim apı 'si](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) etkinleştirildi.

#### <a name="for-enterprise"></a>Enterprise için

- HoloLens cihazlarından raporlama uyumluluk özellikleri etrafında sorunları giderir; Insider Derlemeleriyle ilgili doğru raporlama tetiklenmesi için yeniden başlatma gerekebilir.  
- Uzaktan Yardım 'ın yerleşik sürümü, yeni bir yanıp sönuca yüklenmiş olarak güncelleştirildi.
- ilk kullanıcı oturum açma işleminden sonra, AAD grup tabanlı bilgi noktası yapılandırmalarının kullanıldığı senaryolarda OOBE sonlandırılmakta olan bir sorun düzeltildi.
- Cihaz yeniden başlatması için güncelleştirme bildirimleri ve iletişim kutusu istemleri görüntülenirken bir sorun düzeltildi.
- cihaz yeniden başlatıldıktan sonra Xbox denetleyicileri ve diğer Bluetooth LE çevre birimlerinin bağlanması için yeniden eşleştirilmesi gereken bir sorun düzeltildi.
- Uzaktan Yardım çağrısı sırasında giden videonun kısa bir şekilde dondurmasına neden olabilecek bir sabit video Kodlayıcısı sorunu. "Parça ve Forge" Wi-Fi güvenlik açıklarını gidermek için sürücü ve bellenim değişiklikleri Wi-Fi.
- "Parça ve Forge" Wi-Fi güvenlik açıklarını gidermek için sürücü ve bellenim değişiklikleri Wi-Fi.
- Taşıma platformu modunun (MPı) kullanılması durumunda, "aşağı" kısa bir süre içinde zaman çekimi ortalaması alınarak tahmin edilir. Bu değer, platform modu taşınırken gerçek yerçekimi değiştirir.
- 3DoF modundayken veya izlemenin kaybolması sırasında hologramlar içinde düzenli olarak wobblek düzeltildi.
- Eski sürümlerden 21H1/21H2 sürümündeki güncelleştirmeleri etkileyen bir sorunu giderir.

## <a name="windows-holographic-version-20h2---october-2021-update"></a>Windows Holographic, sürüm 20H2-Ekim 2021 güncelleştirmesi

- Derleme 19041,1168

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, en son yapımızın Windows Holographic, sürüm 21h2 ' yi denemenizi öneririz.

## <a name="windows-holographic-version-21h1---september-2021-update"></a>Windows Holographic, sürüm 21H1-Eylül 2021 güncelleştirmesi

- Derleme 20348,1018

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem saatinin beklenmedik şekilde geçebileceği sorunu gidermeye yönelik düzeltmeler.

## <a name="windows-holographic-version-20h2---september-2021-update"></a>Windows Holographic, sürüm 20H2-Eylül 2021 güncelleştirmesi

- Derleme 19041,1165

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Sistem saatinin beklenmedik şekilde geçebileceği sorunu gidermeye yönelik düzeltmeler.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, sürüm 21H1-Ağustos 2021 güncelleştirmesi

- Derleme 20348,1014

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Xbox denetleyicilerinin, denetleyici desteğiyle Modern uygulamalarda çalışmasını engelleyen bir sorun düzeltildi.
- Cihaz güncelleştirme hatalarıyla ilgili tanılama geliştirildi.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, sürüm 20H2-Ağustos 2021 güncelleştirmesi

- Derleme 19041,1161

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows Holographic, sürüm 21h1 olan en son derlemeyi denemenizi öneririz.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, sürüm 21H1-Temmuz 2021 güncelleştirmesi

- Derleme 20348,1010

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Dosya Gezgini kilitli dosyaları açarken sorunlarla karşılaştığında, cihaz portalı, müşteriye bildirimde bulunmak için geliştirilmiş yöntemlere sahiptir.
- Dosya yükleme, indirme, yeniden adlandırma ve silme artık desteklenen tüm tarayıcılarda https kullanılırken düzeltildi.
- Wi-Fi özellikleri kullanıcı arabirimi **Ayarlar > ağ & Internet > durum > özelliklerinden** başlatıldığında Wi-Fi proxy 'nin kaydedilebileceği sorun düzeltildi.
- Esım sertifikalarının işletim sistemi güncelleştirmeleri üzerinde kaldırılmasına yönelik bir sorun oluştu. Bu çözüm, 21 H1 sürümüne güncelleştirme yaparken esım sertifikalarının ve ilgili bileşenlerin kaldırılmasını sağlar.
- İşletim sistemi sıfırlamaları üzerinde önceden yüklenmiş uygulamaları etkileyen bir sorun düzeltildi.
- Artan CPU yüklemesiyle ücretlendirmesi sırasında çalışma zamanını artırmak için pil şarj performansı ayarlandı. HoloLens 2 cihaz şarj edilirken, cihazın sık çalıştığı algılanırsa, iç pil, ısı azaltmayı daha yavaş ücretlendirir. Pozitif zorunluluğunu getirir, bir cihazın ısı sorunları nedeniyle kapanmasına daha az olma olasılığı vardır ve bu da cihazın daha uzun süre çalışmasına neden olur. Cihaz seyrek erişimli çalışıyorsa, ücretlendirme ücreti etkilenmez.

> [!IMPORTANT]
> [21 h1 deremizdeki, uzaktan yardım kullanıcılarını etkileyen bilinen bir sorun](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)nedeniyle, Windows Holographic, sürüm 21h1 güncelleştirmelerinin sunumunu zamana bağlı duraklattık. ayrıca, varsayılan gelişmiş kurtarma yardımcısı (ARC) derlemesini [Windows Holographic, sürüm 20h2 – haziran 2021 güncelleştirmesine](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)değiştirdik. Şimdi yay derlemesi, 21H1 derlemesini hedeflemeyi sürdürecek.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, sürüm 20H2 – 2021 Temmuz güncelleştirmesi

- Derleme 19041,1157

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Dosya Gezgini kilitli dosyaları açarken sorunlarla karşılaştığında, cihaz portalı, müşteriye bildirimde bulunmak için geliştirilmiş yöntemlere sahiptir.
- Dosya yükleme, indirme, yeniden adlandırma ve silme artık desteklenen tüm tarayıcılarda https kullanılırken düzeltildi.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, sürüm 21H1-Haziran 2021 güncelleştirmesi

- Derleme 20348,1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>iş veya okul kamerayı alma için karşıya yükleme OneDrive

HoloLens 2 Ayarlar uygulamasına yeni bir özellik ekledik. bu, müşterilerin karma gerçeklik fotoğraflarını ve videolarını cihazın resimleri > kamera rulosu klasöründen ilgili OneDrive iş veya okul klasörüne otomatik olarak yüklemesine olanak tanır. bu özellik, yalnızca bir müşterinin kişisel Microsoft hesabı (iş veya okul hesabına değil) otomatik kamera alma 'yı destekleyen HoloLens 2 üzerindeki [OneDrive uygulamasındaki bir özellik boşluğu](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) adresleridir.

**Nasıl çalışır?**

- "kamerayı karşıya yüklemeyi" etkinleştirmek için **karma gerçeklik kamerasından Ayarlar > sistemi >** ziyaret edin.
- bu özelliği **açık** konuma ayarlayarak, cihazınıza yakalanan tüm karma gerçeklik fotoğrafları veya videoları, OneDrive iş veya okul hesabınızın kamera rulosu klasörüne yüklenmek üzere otomatik olarak > kuyruğa alınır.
    >[!NOTE]
    >Bu özelliği etkinleştirmeden önce yakalanan fotoğraflar ve Videolar karşıya *yüklenmek üzere* sıraya alınır ve yine de el ile karşıya yüklenmelidir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yükleme bekleyen dosyaların sayısını görüntüler (veya tüm bekleyen dosyalar karşıya yüklendiğinde "OneDrive güncel olduğunu" okur).
- Bant genişliği hakkında endişeleriniz varsa veya herhangi bir nedenle "duraklatma" yapmak istiyorsanız, özelliği **kapalı** konuma geçirebilirsiniz. Özelliği geçici olarak devre dışı bırakmak, kamera rulosu klasörüne yeni dosyalar eklerken karşıya yükleme sırasının artmaya devam etmesini sağlar, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmeyecektir.
- En yeni dosyalar önce karşıya yüklenir (son, ilk çıkar).
- OneDrive hesabınızda sorunlar varsa (örneğin, parolanız değiştirildikten sonra) Ayarlar sayfasında **şimdi bir düzelme** düğmesi görünür.
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklenmesi daha uzun sürdüğüne (özellikle karşıya yükleme bant genişliğiniz kısıtlı ise) göz atalım. Büyük bir dosya karşıya yüklenirken "duraklatabilir" veya karşıya yüklemeyi kapatırsanız kısmi karşıya yükleme korunur. Karşıya yükleme işlemi birkaç saat içinde "duraklatıldı" veya devre dışı bırakıldığında, karşıya yükleme kaldığınız yerden devam eder. Ancak karşıya yükleme işlemi birkaç saat sonra yeniden etkinleştirildiyse, büyük dosyanın karşıya yüklemesi baştan başlatılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayarın geçerli bant genişliği kullanımına bağlı olarak yerleşik azaltma yoktur. Başka bir senaryo için bant genişliğini en iyi duruma getirmeniz gerekiyorsa, ayarı el ile kapatın. Upload duraklatılır, ancak özellik yeni eklenen dosyaları kamera rulonuza izlemeye devam edecektir. Devam etmek için hazırsanız karşıya yüklemeyi yeniden etkinleştirin.
- Bu özelliğin cihazdaki her kullanıcı hesabı için etkinleştirilmesi gerekir ve yalnızca cihazda oturum açmış olan kullanıcı için dosyaları etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasındaki karşıya yükleme sayısını gerçek zamanlı olarak izlerken fotoğraf veya video çekiyorsunuz, geçerli dosyanın karşıya yüklenmesi tamamlanana kadar bekleyen dosya sayısının değişebileceğini unutmayın.
- Upload, cihazınız uyku modunda kalırsa veya kapatılmışsa duraklatılır. bekleyen karşıya yüklemelerinizin tamamlanmasını sağlamak için, Ayarlar sayfası "OneDrive güncel değil" olarak okunana kadar aygıtı etkin bir şekilde kullanın veya **güç & uyku** ayarlarınızı yapın.

### <a name="added-support-for-some-telemetry-policies"></a>Bazı telemetri ilkeleri için destek eklendi

aşağıdaki telemetri ilkeleri artık HoloLens 2 ' de desteklenmektedir:

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

- Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. Holographic sürüm 21H1'Windows en son derlememizi denemeniz için sizi teşvik ederiz.

>[!IMPORTANT]
> Bu derleme artık hizmette olmayacaktır.

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
[Web uygulamalarını yükleme](#install-web-apps) | Microsoft Office gibi HoloLens 2. Microsoft Edge web Microsoft Edge yükleyin. | Son Kullanıcı |
[Türe doğru çekme](#swipe-to-type) | Holografik klavyede sözcükleri "kaydırmak" için parmak ucunu kullanın. | Son Kullanıcı |
[Başlat'tan Güç menüsü](#power-menu-from-start) | Başlat Menüsünde cihazı yeniden başlatın ve HoloLens kapatın. | Son Kullanıcı |
[Oturum açma ekranında listelenen birden çok kullanıcı](#multiple-users-listed-on-sign-in-screen) | Oturum açma ekranında birden çok kullanıcı hesabı görüntüler. | Son Kullanıcı |
[USB-C Dış Mikrofon Desteği](#usb-c-external-microphone-support) | Uygulamalar ve / veya Remote Assist için USB-C mikrofonlarını kullanın. | Son Kullanıcı |
[Bilgi Noktası için Ziyaretçi Otomatik Oturum Açma](#visitor-auto-logon-for-kiosks) | Ziyaretçi hesaplarında bilgi noktası modları için otomatik oturum açma özelliğinin kullanılmaktadır. | BT Yöneticisi |
[Bilgi Noktası modundaki yeni uygulamalar için yeni AUMID'ler](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Yeni uygulamalar ve Edge Ayarlar AUMID'leri. | BT Yöneticisi |
[Bilgi noktası modu hata teslimi iyileştirildi](#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu, boş başlat menüsünden önce Genel Atanan Erişim'i okur. | BT Yöneticisi |
[Sayfa Görünürlüğü için Yeni SettingsURIs Ayarlar Ayarları](#new-settings-uris-for-page-settings-visibility) | Ayarlar/PageVisibilityList ilkesi için 20'den fazla yeni SettingsURIs. | BT Yöneticisi |
[Geri Dönüş Tanılamasını Yapılandırma](#configuring-fallback-diagnostics-via-settings-app) | Ayarlar Uygulamasında Geri Dönüş Tanılama Davranışını Ayarlama. | BT Yöneticisi |
[Yakındaki cihazlarla paylaşım](#share-things-with-nearby-devices) | Dosya veya URL'leri bir HoloLens bilgisayara paylaşma. | Tümü |
[Yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces) | Işletim sistemi güncelleştirmeleri Ayarlar yeni sorun giderici. | BT Yöneticisi |
[Teslim İyileştirme Önizleme](#delivery-optimization-preview) | Birden çok mobil cihazdan yapılan indirmeler için bant HoloLens azaltabilirsiniz. | BT Yöneticisi |

İlgili sürüm notlarına göz at:

- [HoloLens Emulator arşivini ziyaret edin](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Kılavuzları](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Yeni Microsoft Edge

![Eski Microsoft Edge yeni logoya Microsoft Edge animasyonu.](images/new-edge.gif)

Yeni [Microsoft Edge, müşteriler için daha Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) uyumluluk ve web geliştiricileri için web'in daha az parçalanması için Chromium açık kaynak projesini benimsemektedir.

> [!IMPORTANT]
> Bu yeni Microsoft Edge, yeni sürümlerde artık Microsoft Edge eski [sürümlerin](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) yerini otomatik olarak almaktadır.

![Yeni Microsoft Edge ekran görüntüsü.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Yeni uygulamayı Microsoft Edge

Yeni Microsoft Edge ![yeni Microsoft Edge simgesi.](images/new_edge_logo.png) (mavi ve yeşil bir swirl simgesiyle gösterilir) Başlat menüsü sabitlenir ve bir web bağlantısını etkinleştirerek otomatik olarak başlatılır.

> [!NOTE]
> HoloLens 2'de yeni Microsoft Edge ilk kez başlatacak olurken, ayarlarınız ve verileriniz eski Microsoft Edge. Yeni Microsoft Edge başlattıktan sonra eski Microsoft Edge kullanmaya devam edersiniz, bu yeni veriler eski Microsoft Edge yeni Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Yeni uygulama için ilke ayarlarını Microsoft Edge

Yeni Microsoft Edge, ÖNCEKI 2. HoloLens'da, ESKI Microsoft Edge daha geniş bir tarayıcı ilkeleri kümesi Microsoft Edge.

Yeni ilke ayarlarını yönetme hakkında daha fazla bilgi için aşağıdaki yararlı kaynaklara Microsoft Edge:

- [İlke Microsoft Edge ayarlarını Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Microsoft Edge'in eski sürümü Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome'dan Microsoft Edge eşlemesi](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Tam [Microsoft Edge Enterprise belgeleri](/deployedge/)

> [!IMPORTANT]
> Yeni ilke tarafından desteklenen tarayıcı ilkelerinin hacmi Microsoft Edge, ekibimiz her yeni ilkenin 2. HoloLens garanti HoloLens. Ancak, daha önce HoloLens 2'de desteklenen her eski Microsoft Edge Microsoft Edge ilkenin eşdeğerini test ettik ve HoloLens doğruladık. Microsoft Edge'in eski sürümü 2 [ile Microsoft Edge](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) eski Microsoft Edge tarayıcı ilkesine eşdeğer yeni Microsoft Edge ilke eşlemesini bulmak için bkz. HoloLens eşlemesi.
>
> 2. Microsoft Edge en az iki *yeni* ilke HoloLens:
>
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2'de Microsoft Edge yeni HoloLens bekliyor

Yeni Microsoft Edge, yalnızca U HoloLens WP 2 gibi UWP cihazlarda çalışmasına izin veren yeni bir UWP bağdaştırıcı katmanına sahip yerel bir Win32 uygulaması olduğundan, bazı özellikler hemen kullanılabilir olmayacaktır. Önümüzdeki aylarda yeni senaryoları ve özellikleri destekley edeceğimiz için bu alanı güncel bilgiler için kontrol edin.

**Çalışması beklenen senaryolar ve özellikler:**

- İlk çalıştırma deneyimi, profilde oturum açma ve eşitleme
- Web siteleri beklendiği gibi işlemeli ve davranabilir
- Çoğu tarayıcı işlevi (Sık Kullanılanlar, Geçmiş vb.) beklendiği gibi çalışmalı
- Koyu mod
- Cihaza web uygulamaları yükleme
- Uzantıları yükleme (2. veya 2. gün içinde düzgün çalışmayan uzantılar kullanıyorsanız HoloLens bize haber ver)
- PDF'yi görüntüleme ve işaretleme
- Tek bir tarayıcı penceresinden uzamsal ses
- Tarayıcıyı otomatik ve el ile güncelleştirme
- Yazdır menüsünden PDF kaydetme ("PDF'ye Kaydet" seçeneğini kullanarak)
- WebXR ve 360 Görüntüleyici uzantısı
- Ortamınıza yerleştirilen birden çok pencereye göz atarak doğru pencereye içerik geri yükleme

**Çalışması beklenilen senaryolar ve özellikler:**

- Eşzamanlı ses akışlarıyla birden çok pencereden uzamsal ses
- "Gör, söyle"
- Yazdırma

**Bilinen en önemli tarayıcı sorunları:**

- Holografik klavyede büyüteç önizlemesi, yeni Microsoft Edge. Bu özelliği, büyütme doğru şekilde çalışmaya başladıktan sonra gelecekteki bir güncelleştirmede yeniden kullanılabilir hale gelecektir.
- Başka bir tarayıcı penceresi açık ve etkinse ses yanlış tarayıcı penceresinden oynatılmış olabilir. Ses çalması gereken diğer etkin pencereyi kapatarak bu soruna bir son ve sonra bakabilirsiniz.
- "Beni takip et" modundaki bir tarayıcı penceresinden ses çalacaksanız, "Beni takip [et"](hololens2-basic-usage.md#follow-me-stop-following)modunu devre dışı bıraksanız ses çalmaya devam eder. "Beni takip et" modunu devre dışı bırakmadan önce veya X düğmesiyle pencereyi kapatarak ses kayıttan yürütmeyi durdurarak bu sorunu **atlayabilirsiniz.**
- Etkin uygulama pencereleriyle Microsoft Edge, diğer 2D uygulama pencerelerinde beklenmedik şekilde etkin olmayan bir şekilde devre dışı bırakılamaları olabilir. Bu pencerelerle yeniden etkileşim kurarak bu pencereleri yeniden etkinleştirilebilir.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider kanalları

Yeni Microsoft Edge Edge Insider topluluğuna üç önizleme kanalı sağlar: Beta, Dev ve Canary. Önizleme kanalının yüklü olması, Microsoft Edge 2'nize HoloLens sürümünü kaldırmaz ve aynı anda birden fazla yükleyebilirsiniz.

Edge [Insider Microsoft Edge daha fazla bilgi](https://www.microsoftedgeinsider.com) edinmek için Microsoft Edge Insider giriş sayfasını ziyaret edin. Farklı Edge Insider kanalları hakkında daha fazla bilgi edinmek ve çalışmaya başlamak için [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)

Microsoft Edge Insider kanallarını HoloLens 2:

**Cihaza doğrudan yükleme (şu anda yalnızca yönetemeyen cihazlar tarafından kullanılabilir)**

  1. 2. HoloLens Edge Insider indirme [sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek istediğiniz Edge **Insider HoloLens 2** için İndir düğmesini seçin.
  1. edge indirme kuyruğundan veya cihazınızın "İndirilenler" klasöründen indirilen .msix dosyasını Dosya Gezgini.
  1. [Uygulama yükleyicisi](app-deploy-app-installer.md) başlatacak.
  1. Yükle **düğmesini** seçin.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

**Windows Cihaz Portalı ile PC üzerinden yükleme [](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) (2. HoloLens geliştirici modunun etkinleştirilmesi gerekir)**

  1. Bilgisayarınızda [Edge Insider indirme sayfasını ziyaret edin.](https://www.microsoftedgeinsider.com/download)
  1. Yüklemek **istediğiniz** Edge Insider kanalı için "Windows 10 indir" düğmesinin yanındaki aşağı ok düğmesini seçin.
  1. Açılan **HoloLens 2'yi** seçin.
  1. .msix dosyasını bilgisayarınızın "İndirilenler" klasörüne (veya kolayca bulabilirsiniz başka bir klasöre) kaydedin.
  1. İndirilen [.msix](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) dosyasını 2. Windows Cihaz Portalı yüklemek için bilgisayarınızda HoloLens kullanın.
  1. Yükleme başarılı olduktan sonra, Microsoft Edge Beta, Dev veya Canary'nin, Tüm uygulamalar listesi içinde ayrı **bir** giriş olarak Başlat menüsü.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Yeni depolamayı engellemek için WDAC Microsoft Edge

WDAC ilkelerini yeni [](windows-defender-application-control-wdac.md) uygulama Microsoft Edge güncelleştirmek Microsoft Edge, ilkenize aşağıdakini eklemeniz gerekir.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Yeni uygulamanın uç noktalarını Microsoft Edge

Bazı ortamların dikkate alınması gereken ağ kısıtlamaları olabilir. Yeni Edge ile sorunsuz bir deneyim sağlamak için lütfen [bu Microsoft uç noktalarını etkinleştirin.](/deployedge/microsoft-edge-security-endpoints)

için kullanılabilir olan uç noktalar hakkında [daha fazla bilgi HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Web uygulamalarını yükleme

 > [!Note]
>Holographic [Windows 21H1](hololens-release-notes.md#windows-holographic-version-21h1)sürümünden Office web uygulaması artık önceden yüklenmez.

Yeni Edge'i kullanarak web uygulamalarının yanı sıra yeni Microsoft Store yükleyebilirsiniz. Örneğin, Microsoft Office veya SharePoint barındırılan dosyaları görüntülemek ve düzenlemek için OneDrive. Office web uygulamasını yüklemek için adres çubuğundaki Kullanılabilir Uygulama https://www.office.com veya Office düğmesini seçin.   Onaylamak **için Yükle'yi** seçin.

> [!IMPORTANT]
> Office web uygulaması işlevselliği yalnızca 2. HoloLens etkin bir İnternet bağlantısı olduğunda kullanılabilir.

### <a name="webxr-and-360-viewer"></a>WebXR ve 360 Görüntüleyici

Yeni Microsoft Edge, tam ekran web deneyimleri oluşturmaya (WebVR yerine) yeni standart olan WebXR desteği içerir. Birçok çevreleyici web deneyimi VR ile tasarlanmıştır (görünüm alanınızı bir sanal ortamla değiştirir), ancak bu deneyimler 2. HoloLens de desteklemektedir. WebXR standardı, fiziksel ortamınızı kullanan artırılmış ve karma gerçeklik çevreleyici web deneyimleri de sağlar. Geliştiriciler WebXR ile daha fazla zaman harcayarak 2 müşterinin denemesi için yeni artırılmış ve karma gerçeklik HoloLens deneyimler gelmesini bekliyor!

360 Görüntüleyici uzantısı WebXR üzerinde oluşturulur ve 2. Microsoft Edge yeni HoloLens yüklenir. Bu web uzantısı, kendinizi 360 derecelik videolara daldırma olanağı sağlar. YouTube en fazla 360 video seçkisi sunduğundan, bu videoya orada başlamayı teşvik ediyoruz.

#### <a name="how-to-use-webxr"></a>WebXR'i kullanma

1. WebXR desteği olan bir web sitesine gidin.
1. Web **sitesinde VR girin** düğmesini seçin. Bu düğmenin konumu ve görsel gösterimi web sitesi başına farklılık gösterebilir ancak aşağıdakine benzer olabilir:

    ![VR düğmesi örneğini girin.](images/75px-enter-vr.png)

1. Belirli bir etki alanında WebXR deneyimini ilk kez başlatmayı deneyci, çevreleyici bir görünüm girmek için onay sorar ve İzin Ver'i **seçer.**
1. deneyimi işlemek için [HoloLens 2 hareketlerini](hololens2-basic-usage.md#the-hand-tracking-frame) kullanın.
1. Deneyimde **Çıkış** düğmesi yoksa, giriş geri döndürmek için [Başlangıç hareketini](hololens2-basic-usage.md#start-gesture) kullanın.

**Önerilen WebXR örnekleri**

- 360 Görüntüleyici (sonraki bölüme bakın)
- [XR Dinoı](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>360 görüntüleyicisini kullanma

1. YouTube 'da 360 derecelik bir videoya gidin.
1. Video çerçevesinde, karma gerçeklik kulaklık düğmesini seçin:

    ![360 görüntüleyicisini etkinleştirme düğmesi.](images/enter-360-viewer.jpg)

1. Belirli bir etki alanında 360 Görüntüleyici 'yi ilk kez başlattığınızda, tarayıcı bir tam ekran görünümü girmeye izin ister. **Izin ver**' i seçin.
1. Kayıttan yürütme denetimlerini görüntülemek için [AIR 'e dokunun](hololens2-basic-usage.md#select-using-air-tap) . [El ışınları ve AIR ' i dokunarak](hololens2-basic-usage.md#select-using-air-tap) Oynat/Duraklat, ileri/geri atla, açıklamalı alt yazıları aç/kapat veya deneyimi Durdur (tam ekran görünümünden çıkar). Kayıttan yürütme denetimleri birkaç saniyelik işlem yapılmadan sonra kaybolacaktır.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Popüler WebXR ve 360 Görüntüleyicisi bilinen sorunları

- WebXR deneyiminin karmaşıklığına bağlı olarak, kare hızı kesilebilir veya stutter.
- WebXR 'deki ifade eden her bir el ile yönelik destek, varsayılan olarak etkin değildir. Geliştiriciler, `edge://flags` "WebXR el girişi" ni etkinleştirerek aracılığıyla desteğini etkinleştirebilir.
- YouTube dışındaki Web sitelerinden 360 video, beklendiği gibi çalışmayabilir.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>WebXR ve 360 Viewer hakkında geri bildirim sağlama

Lütfen yeni Microsoft Edge **geri bildirim gönder** özelliği aracılığıyla ekibimize geri bildirim ve hata paylaşabilirsiniz.

### <a name="new-settings-app"></a>yeni Ayarlar uygulaması

bu sürümle birlikte Ayarlar uygulamasının yeni bir sürümünü sunuyoruz. yeni Ayarlar uygulaması aşağıdaki alanlarda HoloLens 2 için yeni özellikleri ve genişletilmiş ayarları içerir: ses, güç & sleep, ağ & ınternet, uygulamalar, hesaplar, erişim kolaylığı ve daha fazlası.

> [!NOTE]
> yeni Ayarlar uygulaması eski Ayarlar uygulamasından farklı olduğu için, daha önce ortamınıza yerleştirdiğiniz tüm Ayarlar pencereleri güncelleştirme sonrasında kaldırılır.

![yeni uygulama giriş sayfası Ayarlar.](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**

- arama Ayarlar: anahtar sözcükler veya ayarın adı kullanılarak Ayarlar giriş sayfasından ayarları arayın.
- Sistem > sesi:
  - giriş ve çıkış ses cihazları: bağımsız olarak giriş ve çıkış ses cihazlarınızı seçin (örneğin, Bluetooth kulaklık aracılığıyla ses dinleyin veya ses girişi için bir USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar HoloLens 2 tarafından desteklenmez.
  - Uygulama hacmi: her uygulamanın birimini bağımsız olarak ayarlayın. Bkz. [uygulama birimi denetimi başına](#per-app-volume-control).
- System > güç & uyku: bir süre işlem yapılmadan sonra cihazın uyku moduna geçmesi gerektiğini seçin.
- Sistem > pili: pil tasarrufu modunu el ile etkinleştirin veya nokta pil tasarrufu modunun otomatik olarak etkinleştirileceği bir pil eşiği ayarlayın.
- USB > cihazlar: varsayılan olarak USB bağlantılarını devre dışı bırakabilirsiniz.
- Internet & ağı:
  - USB-C Ethernet bağdaştırıcıları artık ağ & Internet 'te görüntülenir.
  - USB-C Ethernet bağdaştırıcısı ayarları, IP adresi dahil artık kullanılabilir.
  - artık HoloLens 2 üzerinde uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için bkz. [Varsayılan uygulama Seçicisi](#default-app-picker).
- Hesaplar diğer kullanıcılar >: cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilir, cihaz sahiplerini standart kullanıcılara indirgeyebilirler ve kullanıcıları kaldırabilir.
- Erişim kolaylığı: metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**

- daha önce yerleştirilmiş Ayarlar pencereleri kaldırılır (yukarıdaki nota bakın).
- cihazınızı artık Ayarlar uygulamayla yeniden adlandıramazsınız. bt yöneticileri, HoloLens 2 cihaz adı şablonu veya MDM [devdetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername düğümü [için Windows Autopilot](hololens2-autopilot.md) kullanarak cihazları yeniden adlandırabilirler.
- Ethernet sayfasında her zaman sanal bir Ethernet aygıtı ("UsbNcm") gösterilir.
- yeni Microsoft Edge pil kullanımı, bir UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak doğası nedeniyle doğru olmayabilir (kısa süre önce düzeltilmez).

#### <a name="display-color-calibration"></a>Ekran renk ayarı

bu yeni ayarla, HoloLens 2 görüntü için alternatif bir renk profili seçebilirsiniz. Bu, özellikle daha düşük ekran parlaklığı düzeylerinde renklerin daha doğru görünmesine yardımcı olabilir. ekran renk ayarlaması, Ayarlar uygulamasında, sistem > ayarlama sayfasında bulunabilir.

> [!NOTE]
> Bu ayar, görüntüleme bellenimine yeni bir renk profili kaydederken bu, cihaz başına bir ayardır (ve her kullanıcı hesabı için benzersiz değildir).

##### <a name="how-to-use-display-color-calibration"></a>Ekran renk ayarı 'nı kullanma

1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında, **görüntü renk ayarlama Çalıştır** düğmesini seçin.
1. Ekran renk ayarlama deneyimi başlatılır ve bu işlem, vizörü ' inizin doğru konumda olduğundan emin olmanızı sağlar.
1. Yönerge iletişim kutularında ilerledikten sonra, ekran otomatik olarak %30 oranında gri olacak.
    > [!TIP]
    > ortamınızdaki soluk sahneyi görmekte sorun yaşıyorsanız, cihazın sol tarafındaki parlaklık düğmelerini kullanarak HoloLens 2 ' nin parlaklık düzeyini el ile ayarlayabilirsiniz.
1. Her renk profilini hemen denemek ve gözlerinize en iyi şekilde bakmak için düğmeler 1-6 ' i seçin (Bu, genellikle sahnenin gri tonlamalı bir şekilde görünmesine yardımcı olan profil ve beklenen şekilde görünür.)

    ![Renk ayarlama sahneyi görüntüleyin.](images/color-cal-ui.png)

1. Seçili profille memnun olduğunuzda **kaydet & çıkış** düğmesini seçin
1. Değişiklik yapmayı tercih ediyorsanız, **iptal & çıkış** düğmesini seçin ve değişiklikleriniz geri döndürülecek

> [!TIP]
> Görüntü renk ayarlama ayarını kullanırken göz önünde bulundurmanız gereken bazı yararlı ipuçları aşağıda verilmiştir:
>
> - istediğiniz zaman Ayarlar ekran renk ayarlamayı yeniden çalıştırabilirsiniz
> - cihazdaki herkes renk profillerini değiştirme ayarını daha önce kullanmışsa, en son değişikliğin tarih/saati Ayarlar sayfasında yansıtılır
> - Ekran renk ayarı 'nı yeniden çalıştırdığınızda, daha önce kaydedilen renk profili vurgulanacaktır ve profil 0 görünmez (profil 0 ' ın özgün renk profilini gösterdiği gibi)
> - görüntüleme özgün renk profiline geri dönmek istiyorsanız, Ayarlar sayfasından bunu yapabilirsiniz (bkz. [renk profilini sıfırlama](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Renk profilini sıfırlama

HoloLens 2 ' ye kaydedilmiş özel renk profili yoksa, cihazın özgün renk profilini geri yükleyebilirsiniz:

1. **Ayarlar** uygulamasını başlatın ve **sistem > ayarlaması**' na gidin.
1. **Ekran renk ayarlaması** altında **varsayılan renk profilini Sıfırla** düğmesini seçin.
1. iletişim kutusu açıldığında, HoloLens 2 ' yi yeniden başlatmaya hazırsanız **yeniden başlat** ' ı seçin ve değişikliklerinizi uygulayın.

#### <a name="top-display-color-calibration-known-issues"></a>En üstteki ekran renk ayarlaması bilinen sorunları

- Ayarlar sayfasında, bu Ayarlar sayfasını yeniden yükleyene kadar, renk profilinin en son ne zaman değiştirildiğini söyleyen durum dizesi güncel olmayacaktır.
    - geçici çözüm: başka bir Ayarlar sayfası seçin ve ardından ayarlama sayfasını yeniden seçin.

#### <a name="default-app-picker"></a>Varsayılan uygulama seçici

Bir köprüyü etkinleştirir veya onu destekleyen birden fazla yüklü uygulama ile bir dosya türü açtığınızda, hangi yüklü uygulamanın dosyayı veya bağlantı türünü işlemesini seçmenizi isteyen yeni bir pencere açılır. Bu pencerede, Seçilen uygulamanın "bir kez" veya "Always" dosya veya bağlantı türünü işlemesini de seçebilirsiniz.

"Always" seçeneğini belirlerseniz, daha sonra belirli bir dosyayı veya bağlantı türünü hangi uygulamanın işlediğini değiştirmek istiyorsanız, **Ayarlar > Apps**' te kaydedilmiş varsayılanları sıfırlayabilirsiniz. Sayfanın alt kısmına ilerleyin ve "dosya türleri için varsayılan uygulamalar" ve/veya "bağlantı türleri için varsayılan uygulamalar" altındaki **Temizle** düğmesini seçin. Masaüstü PC 'Lerde benzer ayarların aksine, tek tek dosya türü varsayılanlarını sıfırlayamazsınız.

#### <a name="per-app-volume-control"></a>Uygulama birimi denetimi başına

artık bu Windows derlemede, kullanıcılar her bir uygulamanın birim düzeyini el ile ayarlayabilir. Bu, kullanıcıların ihtiyaç duydukları uygulamalara daha iyi odaklanmasını veya birden çok uygulama kullanırken daha fazla duymasını sağlar. Başka bir kişiyi başka bir kişiye uzak yardım için çağırırken bir uygulamanın hacminin kapatılmasının gereksinimi.

tek bir uygulamanın hacmini ayarlamak için **Ayarlar**  >  **sistem**  >  **sesi**' ne gidin ve gelişmiş ses seçenekleri altında **uygulama birimi ve cihaz tercihleri**' ni seçin.<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Türe göre kaydırın

Bazı müşteriler, yazmak istediğiniz sözcüğün şeklini çekerek sanal klavyelerde "tür" ı daha hızlı bulabilir ve bu özelliği holographic klavye için önizliyoruz. Parmaklarınızın ucunu holographic klavye düzlesiyle geçirerek bir kerede tek bir sözcük çekerek, sözcüğün şeklini çekerek ve sonra, parmağınızın ucunu klavyenin düzleminden çizerek bir kez dolaşaktarabilirsiniz. Sözcüklerinizi sözcükler arasındaki klavyeden kaldırarak, daha sonra da boşluk çubuğuna basmanız gerekmeden, izleme sözcüklerini çekerek bulabilirsiniz. Parmağınızın klavye üzerindeki hareketini takip eden bir çekme izi görürseniz özelliğin çalıştığını bilirsiniz.

Lütfen bu özelliğin, parmağınızla (cep telefonundan farklı olarak) bir holographic klavye için herhangi bir zaman duymayın. 

### <a name="power-menu-from-start"></a>Başlangıç menüsünde güç menüsü

Kullanıcının oturumu kapatmasını, kapatması ve cihazı yeniden başlatmasını sağlayan yeni bir menü. bir sistem güncelleştirmesi ne zaman kullanılabilir olduğunu gösteren HoloLens başlangıç ekranında bir gösterge.

#### <a name="how-to-use"></a>Nasıl kullanılır?

1. [başlangıç hareketini](hololens2-basic-usage.md#start-gesture) kullanarak HoloLens başlangıç ekranını açın veya "başlangıç ekranına git" diyorum.

2. Kullanıcı profili resminin yanındaki üç nokta simgesine (...) dikkat edin:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Kendi ellerinizi veya "Power" sesli komutunu kullanarak Kullanıcı profili resmini seçin.

4. Oturumu kapatma, cihazı yeniden başlatma veya kapatma seçeneklerinin bulunduğu bir menü görünür:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Oturumu kapatmak, HoloLens yeniden başlatmak veya kapatmak için menü seçeneklerini belirleyin. Cihaz [tek bir Microsoft hesabı (MSA) veya yerel hesap](hololens-identity.md)için ayarlandıysa, oturumu Kapat seçeneği kullanılamayabilir.

6. başka herhangi bir yere dokunarak veya başlangıç hareketiyle Başlat menüsü kapatarak menüyü kapatın.

#### <a name="update-indicator"></a>Göstergeyi Güncelleştir

Bir güncelleştirme kullanılabilir olduğunda, bir yeniden başlatmanın güncelleştirmeyi yükleyeceğini göstermek için üç nokta simgesi de açılır. Bu seçenek, güncelleştirmenin varlığını yansıtacak şekilde değişir.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Oturum açma ekranında birden çok Kullanıcı listelendi

Daha önce oturum açma ekranında yalnızca en son oturum açan kullanıcının yanı sıra ' diğer Kullanıcı ' giriş noktası gösteriliyordu. Cihazda birden çok kullanıcı oturum açmışsa, bu yeterli olmayan müşteri geri bildirimi aldık. Yine de bunların Kullanıcı adını yeniden yazması gerekiyordu.

bu Windows derlemesinde tanıtılan, pın girişi alanının sağında bulunan **başka bir kullanıcı** seçerken oturum açma ekranında, daha önce cihazda oturum açmış birden çok kullanıcı görüntülenir. bu, kullanıcıların kullanıcı profillerini seçmesini ve ardından Windows Hello kimlik bilgilerini kullanarak oturum açmasını sağlar. Bu diğer kullanıcılar sayfasından, **Hesap Ekle** düğmesi aracılığıyla cihaza yeni bir kullanıcı da eklenebilir.

Diğer kullanıcılar menüsünde, diğer kullanıcılar düğmesi cihazda oturum açan son kullanıcıyı görüntüler. Bu Kullanıcı için oturum açma ekranına geri dönmek için bu düğmeyi seçin.

![Varsayılan oturum açma ekranı.](./images/multiusers1.jpg)

<br>

![Diğer kullanıcılar için oturum açma ekranı.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C dış mikrofon desteği

> [!IMPORTANT]
> **BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**. bir USB-C kulaklık kümesini yüklerken, kullanıcıların kulaklık sesinin otomatik olarak yeniden yönlendirildiğini gözlemleyeceksiniz, ancak HoloLens OS iç microphone dizisinin diğer herhangi bir giriş cihazını önceliklendirilecektir. **Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**

Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir. USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.

**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.

![ses Ayarlar.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.
>
> Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın. **Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.
>
> **iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens mıc dizisi diğer görevler için hala kullanılabilir.

![Ses aygıtlarını yönetin.](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği nedir?

ne yazık ki Bluetooth mikrofonlar halen HoloLens 2 ' de desteklenmemektedir.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofonları sorunlarını giderme

Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın. Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur. bu mikrofonlardan birini HoloLens içine takarken, ses kaybolmuş olabilir. Neyse ki basit bir çözüm vardır.  

**Ayarlar**  >  **sistem**  >  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın. HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.

![USB-C mikrofonları sorunlarını giderme.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Kiosks için ziyaretçi otomatik oturum açma

Bu yeni özellik, ziyaretçi hesaplarında otomatik oturum açmanın bilgi noktası modları için kullanılmasını sağlar.

AAD olmayan bir yapılandırma için, bir cihazı ziyaretçi otomatik oturum açmaya yönelik olarak yapılandırmak için:

1. Şu şekilde bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için **çalışma zamanı ayarlarını/Atananı** yapılandırır.
    1. İsteğe bağlı olarak, cihazı daha sonra yönetilebilmesi için MDM 'de **(çalışma zamanı ayarları/çalışma alanı/kayıtlar)** kaydeder.
    1. Yerel hesap oluşturma
1. [Sağlama paketini uygulayın](hololens-provisioning.md).

AAD bir yapılandırma için, kullanıcılar bu değişiklik olmadan bugün buna benzer bir şey elde edebilir. bilgi noktası modu için yapılandırılmış AAD katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak bir ziyaretçi hesabında oturum açabilir. Ziyaretçi hesabında oturum açtıktan sonra, ziyaretçi başlangıç menüsünde açıkça oturum açana veya cihaz yeniden başlatılana kadar cihaz yeniden oturum açmayı istemez.

Ziyaretçi otomatik oturum açma, [özel OMA-URI](/mem/intune/configuration/custom-settings-windows-10) ilkesi aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon

| İlke  | Description   | Yapılandırmalar  |
|---|---|---|
| MixedReality/Visitooyutologon  | Bir ziyaretçinin bir bilgi noktasında otomatik olarak oturum açmasına izin verir   | 1 (Evet), 0 (Hayır, varsayılan.)  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>yeni Ayarlar ve uç uygulamalarını bilgi noktası modlarında kullanın

Bilgi [noktaları](hololens-kiosk.md), bir BT Yöneticisi tarafından, büyük bir yandan uygulama kullanıcı modeli kimliği (aumıd) kullanarak uygulamayı bilgi noktasında ekler. Ayarlar uygulaması ve Microsoft Edge uygulamasının her ikisi de yeni uygulamalar olarak değerlendirildiğinden ve bu uygulamalar için aumıds kullanan eski uygulamalardan farklı olduğundan, yeni aumıd kullanmak üzere güncelleştirilmeleri gerekecektir.

Yeni uygulamaları dahil etmek için bir bilgi noktası değiştirirken, yeni AUMıD 'de ekleme ve eskisini bırakma önerilir. Bu, kullanıcılar işletim sistemini güncelleştirinceye kadar kolay bir geçiş oluşturur ve bilgi noktası 'nı istendiği gibi kullanmaya devam etmek için yeni ilkeler almamayı gerektirmez.

| Uygulama                    | AUMıD                                                  |
|------------------------|--------------------------------------------------------|
| eski Ayarlar uygulaması       | HolographicSystemSettings_cw5n1h2txyewy! Uygulamanızda            |
| yeni Ayarlar uygulaması       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Uygulamanızda |
| eski Microsoft Edge uygulaması | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| yeni Microsoft Edge uygulaması | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Hataların işlenmesine yönelik bilgi noktası modu davranış değişiklikleri

daha eski derlemelerde, bir cihazın bir bilgi noktası yapılandırması varsa ve bu, hem küresel olarak atanan erişim hem de AAD grup üyesi tarafından atanan erişim ' in bir birleşimi olan AAD grup üyeliğini belirlemek başarısız olursa, kullanıcı "[başlangıç olarak gösterilmemektedir](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)

bu Windows sürümden itibaren, bilgi noktası deneyimi AAD grubu bilgi noktası modu sırasında oluşan hatalara karşı genel bilgi noktası yapılandırmasına (varsa) geri dönüş yapılır.

### <a name="new-settings-uris-for-page-settings-visibility"></a>sayfa Ayarlar görünürlüğü için yeni Ayarlar urı 'leri

[Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) ' de, Ayarlar uygulama içinde görülen sayfaları kısıtlamak için [Ayarlar/pagevisibilitylist ilkesini](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ekledik. pagevisibilitylist, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkedir.

[sayfa Ayarlar görünürlüğünü](settings-uri-list.md)ziyaret ederseniz, bu CSP 'yi ve önceki sürümlerde bulunan urı 'lerin listesini kullanmak için yönergeler bulabilirsiniz.

bt yöneticilerinin yönetebileceği kullanılabilir Ayarlar urı 'leri listesini genişlettik. bu urı 'lerden bazıları yeni Ayarlar uygulamasındaki yeni kullanılabilir alanlara yöneliktir. Ayarlar/pagevisibilitylist ilkesi kullanıyorsanız, aşağıdaki listeyi gözden geçirin ve izin verilen veya engellenen sayfalarınızı gereken şekilde ayarlayın.

> [!NOTE]
> **Kullanım dışı: MS-Settings: Network-proxy**
>
> Bu yeni derlemelerde bir ayarlar sayfası kullanımdan kaldırılmıştır. Eski **ağ & Internet**  >  **proxy** sayfası artık genel ayar olarak kullanılamıyor. Yeni bağlantı başına proxy ayarları, **İnternet & Internet**  >  **Wi-Fi**  >  **özellikleri** veya **ağ & Internet**  >  **Ethernet**  >  **özellikleri** altında bulunabilir.

<br>

| Ayarlar sayfası                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Uygulamalar > uygulamalar & Özellikler                               | `ms-settings:appsfeatures`                         |
| Uygulamalar > uygulamalar & özellikler > Gelişmiş Seçenekler          | `ms-settings:appsfeatures-app`                     |
| Çevrimdışı haritalar > uygulamalar                                  | `ms-settings:maps`                                 |
| Uygulamalar > çevrimdışı haritalar > Indirme haritaları                  | `ms-settings:maps-downloadmaps`                    |
| > fare cihazları                                      | `ms-settings:mouse`                                |
| USB > cihazlar                                        | `ms-settings:usb`                                  |
| Ağ & Internet > Uçak modu                   | `ms-settings:network-airplanemode`                 |
| Gizlilik > genel                                    | `ms-settings:privacy-general`                      |
| Gizlilik > mürekkep & yazma kişiselleştirmesi             | `ms-settings:privacy-speechtyping`                 |
| Gizlilik > hareketi                                     | `ms-settings:privacy-motion`                       |
| Gizlilik > ekran görüntüsü kenarlıkları                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Gizlilik > ekran görüntüleri ve uygulamalar                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| Sistem > pili                                     | `ms-settings:batterysaver`                         |
| Sistem > pili                                     | `ms-settings:batterysaver-settings`                |
| Sistem > sesi                                       | `ms-settings:sound`                                |
| System > Sound > uygulama hacmi ve cihaz tercihleri | `ms-settings:apps-volume`                          |
| System > Sound > ses cihazlarını yönetme              | `ms-settings:sound-devices`                        |
| sistem > Depolama > Depolama Sense yapılandırma         | `ms-settings:storagepolicies`                      |
| Saat & Dil > Tarih & saati                        | `ms-settings:dateandtime`                          |
| & Dil > klavye                           | `ms-settings:keyboard`                             |
| Zaman & Dil > dili                           | `ms-settings:language`                             |
| Zaman & Dil > dili                           | `ms-settings:regionlanguage-languageoptions`       |
| Güncelleştirme & güvenlik > sıfırlama & kurtarma               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Güncelleştirilmiş URI 'Ler

Daha önce aşağıdaki iki URI, belirtilen sayfalara doğrudan bir Kullanıcı almaz, ancak yalnızca ana güncelleştirmeler sayfasını engelledi. Aşağıdaki öğeler sayfalarına yönlendirecek şekilde güncelleştirildi:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Ayarlar uygulama aracılığıyla geri dönüş tanılamayı yapılandırma

artık Ayarlar uygulamada, bir kullanıcı [geri dönüş tanılamaları](hololens-diagnostic-logs.md)davranışını yapılandırabilir. Ayarlar uygulama,   >  bu ayarı yapılandırmak için gizlilik **sorunlarını giderme** sayfasına gidin.

> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, Kullanıcı bu davranışı geçersiz kılayamaz.  

### <a name="share-things-with-nearby-devices"></a>Yakındaki cihazlarla şeyleri paylaşma

hem bilgisayarlar hem de diğer HoloLens 2 cihazları dahil olmak üzere Windows 10 cihazları ile neredeyse her şeyi paylaşabilirsiniz.   >    >  dosya veya url 'leri bir bilgisayara HoloLens paylaşmak için Ayarlar sistem **paylaşılan deneyimleriyle** deneyebilirsiniz. Daha fazla ayrıntı için [Windows 10 ' de Yakındaki cihazlarla şeyler paylaşma](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)hakkında daha fazla bilgi edinin.

Bu özellik, [bağlantı/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)aracılığıyla yönetilebilir.

### <a name="new-os-diagnostic-traces"></a>Yeni işletim sistemi tanılama izlemeleri

Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmelerine yönelik yeni Ayarlar uygulamasının eklenmesiyle birlikte yeni bir sorun giderici eklenmiştir. **Ayarlar**  >  **güncelleştirme &amp; güvenliği**  >  **sorun giderme**  >  **Windows Update** gidin ve **başlat**' ı seçin. Bu, BT veya destek ile ilgili sorun giderme konusunda daha iyi yardımcı olması için işletim sistemi güncelleştirmeleriyle ilgili sorunları yeniden oluştururken izlemeleri toplamanıza olanak tanır.

### <a name="delivery-optimization-preview"></a>Teslim Iyileştirme önizlemesi

bu HoloLens güncelleştirme ile, Windows Holographic for Business birden çok HoloLens cihazdan indirilen bant genişliği tüketimini azaltmak için teslim iyileştirme ayarlarının kullanılmasına olanak sağlar. önerilen ağ yapılandırması ile birlikte bu işlevin daha kapsamlı bir açıklaması mevcuttur: [Windows 10 güncelleştirmeleri için teslim iyileştirmesi](/windows/deployment/update/waas-delivery-optimization).

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

### <a name="it-admin---update-checklist"></a>BT Yöneticisi-güncelleştirme denetim listesi

Bu denetim listesi, bu özellik güncelleştirmesinde eklenmekte olan yeni öğeleri, geçerli cihaz yönetimi yapılandırmalarından veya kullanmaya başlamak isteyebileceğiniz yeni özelliklerden haberdar etmenize yardımcı olur.

#### <a name="updates-to-kiosk-mode"></a>Bilgi noktası moduna güncelleştirmeler

[**bilgi noktası modunda yeni uygulamalar Için yeni AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)✔️:

daha önce bir bilgi noktasında Ayarlar uygulamasını veya Microsoft Edge uygulamasını kullanıyorsanız, bu uygulamaları farklı bir uygulama kimliği kullanan yeni uygulamalarla değiştirdik. [Yeni uygulamalar için yeni Aumıd 'Leri bilgi noktası modunda](#use-the-new-settings-and-edge-apps-in-kiosk-modes) okumanız önemle tavsiye ederiz. bu, Ayarlar uygulamanızın bilgi noktasında olmasına devam edebilir ya da yeni Microsoft Edge uygulamasını dahil etmeye devam eder. Bu değişiklikler şimdi yapılabilir ve tüm cihazlara dağıtılabilir ve güncelleştirme sırasında daha yumuşak bir geçişe izin verebilir.

[**kiosks Için ziyaretçi otomatik oturum açma**](#visitor-auto-logon-for-kiosks)✔️:

Ziyaretçiler artık bir bilgi noktasında otomatik olarak oturum açabilir. Bu davranış varsayılan olarak açık olmakla kalmaz, yönetilebilir ve devre dışı bırakılabilir.

✔️ [**Gelişmiş bilgi noktası modu hata teslim**](#kiosk-mode-behavior-changes-for-handling-of-failures)etme:

oturum açmış AAD kullanıcının AAD grup üyeliği başarıyla saptanmamışsa, bu durumda başlat menüsü (varsa) için genel bilgi noktası yapılandırması kullanılır, aksi takdirde kullanıcı boş başlat menüsüyle sunulur. Boş başlangıç menüsü, doğrudan ayarlayabileceğiniz bir yapılandırma olmadığından, bu yeni işleme, sizin yapılandırmanıza uygulanabilecek veya atanan erişim yapılandırmalarınıza yeni ayarlamalar yapmak isteyebileceğiniz için, bilgi noktaları kullanıyorsanız, destek bölümünüze bildirmek için bir şey olabilir.

#### <a name="updates-to-page-settings-visibility"></a>sayfa Ayarlar görünürlüğü için güncelleştirmeler

[**sayfa Ayarlar görünürlüğü için yeni Ayarlar urı** ✔️](#new-settings-uris-for-page-settings-visibility)

şu anda [sayfa Ayarlar görünürlüğü](settings-uri-list.md) kullanıyorsanız, var olan veya engellenen mevcut urı 'lerinizin ayarlamalarını yapmak isteyebilirsiniz.

#### <a name="updates-for-your-wdac-policy"></a>WDAC ilkenize yönelik güncelleştirmeler

✔️ daha önce Microsoft Edge wdac aracılığıyla bloke ediyorsanız, wdac ilkenizi güncellemek isteyeceksiniz. Lütfen aşağıdakileri gözden geçirin ve belirtilen örnek kodu kullanın.

#### <a name="enable-new-endpoints-for-edge"></a>Uç için yeni uç noktaları etkinleştir

✔️ ara sunucu veya güvenlik duvarı gibi ağ uç noktalarını yapılandırmayı içeren bir altyapınız varsa, lütfen yeni Microsoft Edge uygulaması için bu yeni uç noktaları etkinleştirin.

#### <a name="newly-configurable-items"></a>Yeni yapılandırılabilir öğeler

[geri dönüş tanılamayı yapılandırma](#configuring-fallback-diagnostics-via-settings-app)✔️: geri dönüş tanılamayı toplayıp toplayacağını yapılandırıp yönetemeyebilirsiniz.

[Yakındaki cihazlarla her şeyi paylaşmak](#share-things-with-nearby-devices)✔️: yeni yakın paylaşım özelliğini devre dışı bırakabilirsiniz.

[yeni Microsoft Edge ilke ayarlarını yapılandırma](#configuring-policy-settings-for-the-new-microsoft-edge)✔️: Microsoft Edge için kullanılabilen yeni konfigürasyonları inceleyin.

#### <a name="new-diagnostic-tool"></a>Yeni Tanılama Aracı

[yeni işletim sistemi tanılama izlemeleri](#new-os-diagnostic-traces)✔️: Işletim sistemi güncelleştirmeleriyle ilgili günlükleri toplayın.

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- [Çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics) , seri numarası ve işletim sistemi sürümü için ek cihaz bilgileri de içerir.
- Çalışma zamanı sağlama paketleri aracılığıyla iş kolu uygulamalarının dağıtımıyla ilgili bir sorunu düzeltir.
- İş kolu uygulama yüklemesi durum raporlama etrafında bir sorunu düzeltir.
- Cihaz sıfırlamaları genelinde yeni uygulama paketlerinin kalıcılığını aşmak için bir sorunu düzeltir.
- Japonca müşteriler için Edge 'de yanlış simgelere yol açabilecek bir sorunu düzeltir.
- , Uç gibi önceden yüklenmiş uygulamalar etrafında işletim sistemi güncelleştirmelerinin dayanıklılığını geliştirir.
- Microsoft Edge yüklemesini etkileyen bir güncelleştirme güvenilirliğini giderir.

## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, sürüm 20H2 – Mayıs 2021 güncelleştirmesi

- Derleme 19041,1146

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez, Windows Holographic, sürüm 21h1 olan en son derlemeyi denemenizi öneririz.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, sürüm 1903-Mayıs 2021 güncelleştirme

- Derleme 18362,1110

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermiyor. **Bu derleme artık aylık hizmet güncelleştirmelerini almamayacaktır**. Windows Holographic, sürüm 21h1 olan en son derlemenizi denemenizi öneririz.

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

Uygulamaları 2 **cihaza daha sorunsuz Uygulama Yükleyicisi için** yeni bir özellik (HoloLens) ekliyoruz. Özellik, varsayılan **olarak, unmanaged cihazlar için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:

- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'nin (USB üzerinden veya Edge üzerinden) cihazınıza indirerek yüklemenin Dosya Gezgini appx paketine gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web)  MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğu gibi, uygulamaların [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) da İmza [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce imzalamak için kullanılan sertifikanın HoloLens cihazı tarafından güvenilir olması gerekir.

**Uygulama yükleme yönergeleri.**

1. Cihazınızın yönetilen olarak kabul edilen bir şey olduğundan emin olun
1. HoloLens 2 cihazınızın açık ve bilgisayarınıza bağlı olduğundan emin olun
1. HoloLens 2 cihazında oturum HoloLens olun
1. Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads klasörüne kopyalayın.   Dosyanızı kopyalamayı tamamlayıp cihazınızın bağlantısını kesebilirsiniz
1. 2 HoloLens Başlat Menüsünü açın, Başlat'ı Tüm uygulamalar seçin ve Dosya Gezgini başlatabilirsiniz.
1. İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz ve ardından İndirilenler'e gitmek zorundayabilirsiniz.
1. yourapp.appxbundle dosyasını seçin.
1. Uygulama Yükleyicisi başlatacak. Uygulamayı yüklemek için Yükle düğmesini seçin.
Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

Bu akışı test etmek için [Windows Evrensel GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) örnek uygulamalar bulabilirsiniz.

Uygulama Yükleyicisi ile HoloLens [2'ye uygulama yükleme işleminin tam Uygulama Yükleyicisi.](app-deploy-app-installer.md)  

![Uygulama Yükleyicisi aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- El izleme artık daha önce el kayıpları olan birçok yeni durumda izlemeye devam ediyor.  Bu yeni durumlardan bazılarında, kullanıcının gerçek el ile yalnızca konum güncelleştirilirken diğer ortaklar önceki bir poza göre ertelenmektedir.  Bu değişiklik; tırslama, atma, kırpma ve kırpma gibi hareketlerde izleme tutarlılığının iyileştirilmesine yardımcı olur.  Ayrıca, el bir yüzeyin yakınında veya bir nesneyi tuttuğunda da yardımcı olur.  El birikleri vernilen zaman, [her bir ortak](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) doğruluk değeri "Yüksek" yerine "Yaklaşık" olarak ayarlanır.
- Azure AD hesapları için PIN sıfırlamanın "Bir sorun oluştu.
- Et, Ayarlar uygulamasından Iris, yeni kullanıcı veya bildirim bildirimi başlatan kullanıcılar önyükleme sonrası OOBE kilitlenmelerini çok daha az görüyor.
- Kullanıcıların OOBE'den gelen doğru saat dilimine sahip olması gerekir.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, sürüm 1903 – Aralık 2020 Güncelleştirmesi

- Derleme 18362.1088

Bu aylık kalite güncelleştirmesi önemli bir değişiklik içermemektedir. En son Windows Holographic, sürüm 20H2 – Aralık 2020 Güncelleştirmesini ve derlemeye eklenen yeni Uygulama Yükleyicisi özelliğini denemeniz gerekir.

## <a name="windows-holographic-version-20h2"></a>Windows Holographic, sürüm 20H2

- Derleme 19041.1128

Windows Holographic sürüm 20H2 artık kullanılabilir ve 2 kullanıcı ve BT HoloLens yeni özellikler sunar. Otomatik Göz Konumlandırmadan Sertifika Yöneticisi'ne Ayarlar Bilgi Noktası Modu işlevselliğine ve yeni Autopilot kurulum özelliklerine kadar. Bu yeni güncelleştirme, IT ekiplerinin cihazları yapılandırmak ve yönetmek için daha ayrıntılı denetime sahip HoloLens ve kullanıcılara daha sorunsuz holografik deneyimler sunar.

Bu en son sürüm, 2004 sürümüne aylık bir güncelleştirmedir, ancak bu kez yeni özellikler ekllmektedir. Ana derleme numarası aynı kalır ve Windows Update 2004 (derleme 19041) sürümüne aylık bir sürümü gösteriyor. Kullanılabilir en son derleme olan 19041.1128+ sürümünü onaylamak için Ayarlar > Hakkında ekranında Derleme Numaranıza bakabilirsiniz. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve Güncelleştirmeleri Kontrol Edin'e dokunun. Güncelleştirmeleri yönetme hakkında daha fazla bilgi için HoloLens güncelleştirmelerini [yönetme HoloLens ziyaret edin.](hololens-updates.md)

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
| [Genel Atanan Erişim](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Bilgi noktası sistem düzeyinde uygulanarak herkes için geçerli olacak şekilde çoklu uygulama bilgi noktası modu için yeni yapılandırma yöntemi.                  |
| [Çok uygulamalı bilgi noktası içinde bir uygulamayı otomatik başlatma](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Birden çok uygulamalı bilgi noktası modunda oturum a açılırken bir uygulamayı otomatik olarak başlatılacak şekilde ayarlar.                                                        |
| [Hataların işlenmesi için bilgi noktası modu davranış değişiklikleri](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Bilgi noktası modu hatası artık kısıtlayıcı geri dönüşe sahip.                                                                                                |
| [HoloLens Koşullarıdır](hololens-release-notes.md#hololens-policies)                                    | Yeni ilkeler HoloLens.     |
| [Çevrimdışı Bilgi Noktası için Azure AD Grubu üyeliğini önbelleğe alın](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Yeni ilke, kullanıcıların kaç gün boyunca çevrimdışı Bilgi Noktası modunu kullanmak için grup üyeliği önbelleğini kullanmalarını sağlar.                                        |
| [HoloLens 2 için yeni cihaz kısıtlama ilkeleri](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | HoloLens 2 için yeni etkinleştirilen cihaz yönetimi ilkeleri.                                                                                |
| [HoloLens 2 için yeni güç ilkeleri](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Güç zaman aşımı ayarları için yeni desteklenen ilkeler.  |
| [İlkeleri Güncelleştirme](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Güncelleştirmelerin denetimine izin veren yeni etkinleştirilen ilkeler.           |
| [Ayarlar 2 için sayfa görünürlüğü HoloLens etkinleştirildi](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Uygulama içinde hangi sayfaların görül Ayarlar.             |
| [Araştırma modu](hololens-release-notes.md#research-mode) | HoloLens 2'de Araştırma modunu kullanma. |
| [Kayıt uzunluğu artırıldı](hololens-release-notes.md#recording-length-increased) | MRC kayıtları artık 5 dakikayı geçmeyecek. |
| [Güncelleştirmedeki geliştirmeler ve düzeltmeler](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Güncelleştirmede ek düzeltmeler.   |

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

Bu HoloLens 2'de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve geliştirilmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcı cihazı bağlı olduğu andan itibaren arka planda otomatik olarak çalışmaya başlar. Kullanıcının daha önce göz izleme ayarı yoksa Otomatik Göz Konumu, 20 -30 saniyelik bir işlem süresi sonra kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve bu nedenle kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, bir kullanıcı daha önce cihazda göz izleme ayarlama işleminin üzerinden geçilen birini ifade eder.

| Etkin Uygulama | Önceki Davranış | Windows Holographic sürüm 20H2 Güncelleştirmesi'nin davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Bakışın etkin olmayan uygulaması veya Holographic Shell |Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | İstem görüntülenmez. |
| Bakış özellikli uygulama | Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz bakışı akışına erişdiğinde görüntülenir. |

Kullanıcı, bakış etkin olmayan bir uygulamadan bakış verilerine erişen uygulamaya geçiş olursa, ayarlama istemi görüntülenir.

Diğer tüm sistem davranışları, geçerli kullanıcının etkin bir göz izleme cihazına sahip olmadığının benzeridir. Örneğin Tek Elle Başlatma hareketi etkinleştirilmez. İlk kurulum için İlk İlk Deneyimi'ne hiçbir değişiklik olmayacaktır.

Göz bakışı verileri veya çok hassas hologram konumlandırması gerektiren deneyimler için kullanıcıların göz izleme cihazlarını çalıştırmalarını öneririz. Göz izleme ayarlama isteminden veya başlangıç menüsünden Ayarlar uygulamasını başlatarak ve ardından Sistem > Ayar > Göz Düzeltmesi'> **Çalıştır'ı seçerek** erişilebilir.

Bu bilgiler daha sonra diğer ayarlama [bilgileriyle bulunabilir.](hololens-calibration.md#auto-eye-position-support)

### <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama aracı. Bu özellik, ticari ortamlarda büyük ölçekte sertifikalarınızı dağıtmanıza, sorun gidermenize ve doğrulamanıza olanak tanır.

Holographic Windows 20H2'de, HoloLens 2 Ayarlar ekliyoruz. Ayarlar > **Security & Sertifikalarını Güncelleştir > gidin.** Bu özellik, cihazınıza sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kullanımı kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için denetim, tanılama ve doğrulama araçlarını iyileştirdi.

- **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığından veya uygun şekilde kaldırıldığından emin olmak için yeteneği.
- **Tanılama:** Sorunlar ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulama zaman kazandırır ve sorun gidermeye yardımcı olur.
- **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğunu doğrulamak, sertifikaları büyük ölçekte dağıtmadan önce özellikle ticari ortamlarda önemli zaman tasarrufu sağlar.

Listede belirli bir sertifikayı hızla bulmak için ad, depolama veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar doğrudan bir sertifika da arayabilir. Tek tek sertifika özelliklerini görüntülemek için sertifikayı seçin ve Bilgi'ye **tıklayın.**

Sertifika yüklemesi şu anda .cer ve .crt dosyalarını desteklemektedir. Cihaz Sahipleri Sertifikaları Yerel Makineye ve Geçerli Kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca Geçerli Kullanıcı'ya yükleyebilir. Kullanıcılar yalnızca doğrudan Ayarlar kullanıcı arabiriminden Ayarlar kaldırabilir. Bir sertifika başka bir şekilde yüklendiyse, aynı mekanizma tarafından da kaldırılmalıdır.

#### <a name="steps-to-install-a-certificate"></a>Sertifika yükleme adımları

1. Bağlan 2 HoloLens bilgisayarınıza bağlayın.
1. Yüklemek istediğiniz sertifika dosyasını HoloLens 2'de bir konuma yükleyin.
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

![Ayarlar uygulamasındaki sertifika görüntüleyici.](images/certificate-viewer-device.jpg)

![Sertifika kullanıcı arabirimini kullanarak sertifika yüklemenin nasıl olduğunu gösteren resim.](images/certificate-device-install.jpg)

Bu bilgiler daha sonra yeni [bir Sertifika Yöneticisi sayfasında bulunabilir.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>USB'den sağlamayı otomatik başlatma

- Otomatikleştirilmiş işlemler, OOBE sırasında Sağlama Paketleri ile USB Sürücüleri kullanılırken daha az kullanıcı etkileşimi sağlar.

Bu sürümden önce, kullanıcıların bir düğme birleşimi kullanarak sağlama yapmak için OOBE sırasında sağlama ekranı el ile başlatmaları gerekirdi. Artık kullanıcılar USB depolama sürücüsünde Sağlama Paketi kullanarak düğme birleşimini atlar.

1. OOBE'nin ilk etkileşime geçme anları sırasında USB sürücüyü sağlama paketiyle takın
1. Cihaz hazır olduğunda, sağlama sayfasıyla otomatik olarak istemi açar.

Not: Cihaz önyüklerken bir USB sürücü takılı bırakıldı ise OOBE mevcut USB depolama cihazını numaralandıracak ve eklerinin takılı olduğunu izler.

OOBE sırasında sağlama paketlerini uygulama hakkında daha fazla bilgi için, HoloLens [belgelerini ziyaret](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) edin.

[USB'den otomatik başlatma sağlama hakkında daha](hololens-provisioning.md#auto-launch-provisioning-from-usb) fazla bilgi için HoloLens edinebilirsiniz.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>OOBE'de sağlama paketlerini otomatik onaylama

- Daha az kullanıcı etkileşimi sağlayan otomatik işlem, Sağlama Paketi sayfası görüntülendiğinde listelenen tüm paketleri otomatik olarak uygulayacaktır.

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

1. Azure AD gruplarını hedefleyen bilgi noktası için bir cihaz yapılandırma profili oluşturun ve HoloLens cihazlara atayın.
1. bu ilke değerini istenen gün sayısına (> 0) ayarlayan ve HoloLens cihazlara atayan özel bir OMA urı tabanlı cihaz yapılandırması oluşturun.
    1. URI değeri, OMA-URI metin kutusunda./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays olarak girilmelidir
    1. Değer, izin verilen Min/Max arasında olabilir.
1. HoloLens cihazları kaydedin ve her iki yapılandırmanın cihaza uygulandığını doğrulayın.
1. Internet 'in kullanılabildiği Azure AD User 1 oturum açma ve Azure AD grup üyeliği başarıyla onaylandıktan sonra önbellek oluşturulur.
1. artık Azure AD kullanıcı 1, HoloLens çevrimdışına alabilir ve ilke değeri X gün sayısı için izin verdiği sürece bilgi noktası modu için kullanabilir.
1. 4 ve 5. adım, diğer tüm Azure AD kullanıcıları için yinelenebilir. burada anahtar noktası, herhangi bir Azure AD kullanıcısının Internet 'i kullanarak cihaza oturum açması gerekir. bu sayede, bilgi noktası yapılandırmasının hedeflediği Azure AD grubuna üye olduklarını belirleyebiliriz.

> [!NOTE]
> Bir Azure AD kullanıcısı için 4. adım gerçekleştirilene kadar "bağlantısı kesik" ortamlarda bahsedilen hata davranışı ile karşılaşırsınız.

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 için yeni cihaz kısıtlama ilkeleri

- Kullanıcıların, sağlama paketleri ekleme veya kaldırma gibi belirli cihaz yönetim ilkelerini yönetmesine olanak tanır.

HoloLens 2 cihazların daha fazla yönetim seçeneklerine izin veren yeni etkinleştirilen ilkeler.

- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage)
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage ve AllowRemoveProvisioningPackage için bu iki yeni ilke [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

> [!NOTE]
> [remotelock](/windows/client-management/mdm/remotelock-csp)ile ilgili olarak HoloLens yalnızca./vendor/msft/remotelock/lock yapılandırmasını destekler. Sıfırlama ve kurtarma gibi PIN ile ilgili yapılandırma desteklenmez.

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 için yeni güç ilkeleri

- HoloLens, güç ilkeleri aracılığıyla uyku moduna geçme veya kilitleme için daha fazla seçenek.

Bu yeni eklenen ilkeler, yöneticilerin boşta kalma zaman aşımı gibi güç durumlarını denetlemesine olanak tanır. Her ilke hakkında daha fazla bilgi edinmek için lütfen bu ilkenin bağlantısına tıklayın.

|     İlke belgeleri bağlantısı                |     Notlar                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [Displayofftimeoutonpili](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [Displayofftimeoutpluggedın](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [Enerji Gysaverbatteryıthresholdonpili](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                             |
|     [Enerji Gysaverbatteryıthresholdpluggedın](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, örn. 100                                                                          |
|     [Standbytimeoutonpili](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [Standbytimeoutpluggedın](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Windows yapılandırma tasarımcısında kullanılacak örnek değer, yani,`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Bu iki yeni ilke Displayofftimeoutonpili ve Displayofftimeoutpluggedın [ortak cihaz kısıtlamalarımıza](hololens-common-device-restrictions.md)ekleniyor.

> [!NOTE]
> HoloLens 2 ' de tutarlı deneyim için, lütfen hem displayofftimeoutonpili hem de standbytimeoutonpili değerlerinin aynı değer olarak ayarlandığından emin olun. Aynı, Displayofftimeoutpluggedın ve Standbytimeoutpluggedın için de geçerlidir. Modern bekleme hakkında daha fazla bilgi için [bkz. ekran, uyku ve hazırda bekleme boşta zamanlayıcılar](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) .

### <a name="newly-enabled-update-policies-for-hololens"></a>HoloLens için yeni etkinleştirilmiş güncelleştirme ilkeleri

- Güncelleştirmelerin yüklenmesi için daha fazla seçenek veya güncelleştirme için güncelleştirmeleri Duraklat düğmesini devre dışı bırakma.

bu güncelleştirme ilkeleri artık HoloLens 2 cihazlarda etkinleştirilmiştir:

- [Güncelleştirme/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
- [Güncelleştirme/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
- [Güncelleştirme/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
- [Güncelleştirme/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

bu güncelleştirme ilkelerine ilişkin tüm ayrıntılar ve bunların HoloLens cihazları için nasıl kullanılacağı, [HoloLens güncelleştirmelerini yönetme](hololens-updates.md)bölümünde buradan okunabilir.

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>HoloLens 2 için Ayarlar sayfa görünürlüğü etkinleştirildi

- Ayarlar uygulamasındaki artan uı denetimi, sınırlı sayıda sayfa seçimini göstermek için karışacaktır.

artık, bt yöneticilerinin sistem Ayarlar uygulamasındaki belirli sayfaların görünür veya erişilebilir olmasını engellemesine ya da belirtilenler hariç tüm sayfalarda yapılmasına izin veren bir ilkeyi etkinleştirdik. Bu özelliği tam olarak özelleştirmeyi öğrenmek için aşağıdaki bağlantıya tıklayın.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

HoloLens 2 ' de özelleştirebileceğiniz sayfa ayarlarını öğrenmek için lütfen [Ayarlar urı](settings-uri-list.md)'larımızı ziyaret edin.

![Ayarlar uygulamasında değiştirilen etkin saatlerin ekran görüntüsü.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Araştırma modu

araştırma modundayken, HoloLens 2, bilgisayar vision Research için bir pokatlanmış araç haline gelir. önceki sürümlere kıyasla, HoloLens 2 için araştırma modu aşağıdaki avantajları içerir:

- HoloLens (1. gen) araştırma modunda sunulan sensörlerden ek olarak, artık bir ivme ölçer, jroscope ve manyetik tometre dahil olmak üzere imu algılayıcı erişimi sağlıyoruz.
- HoloLens 2, araştırma moduyla birlikte kullanılabilecek yeni yetenekler sağlar. Özellikle, daha zengin bir denemeleri kümesini sunabilme ve göz önünde bulundurun.

araştırmacılar artık, bu dış kullanıma açık ham görüntü algılayıcı akışlarına erişmek için HoloLens cihazlarında araştırma modunu etkinleştirme seçeneğine sahiptir. HoloLens 2 için araştırma modu, ivometer, jroscope ve manyetik tometer okumaları için de erişim sağlar. Kullanıcıların gizliliğini korumak için, ham göz izleme kamera görüntüleri araştırma modu aracılığıyla kullanılamaz, ancak var olan API 'Ler aracılığıyla göz korunun yönü mevcuttur.

Daha fazla teknik ayrıntı için [araştırma modu belgelerine](/windows/mixed-reality/research-mode) göz atın.

### <a name="recording-length-increased"></a>Kayıt uzunluğu artırıldı

Müşteri geri bildirimi nedeniyle, [karma gerçeklik yakalamalarından](holographic-photos-and-videos.md)oluşan kayıt uzunluğunu artırdık. Karma Gerçeklik yakalamaları artık varsayılan olarak 5 dakikaya göre sınırlandırılamaz, bunun yerine kullanılabilir disk alanına göre en fazla kayıt uzunluğunu hesaplar. Cihaz, toplam disk alanının %80 ' suna kadar kullanılabilir disk alanına göre maksimum video kaydetme süresini tahmin edecektir.

> [!NOTE]
> aşağıdakilerden biri gerçekleşirse HoloLens varsayılan video kayıt uzunluğunu (5 dakika) kullanacaktır:
>
> - Tahmini en fazla kayıt süresi varsayılan 5 dakikadan daha küçüktür.
> - Kullanılabilir disk alanı, toplam disk alanının %20 ' inden daha az.

Tüm gereksinimleri [holographic fotoğraflarınız ve videolar](holographic-photos-and-videos.md#maximum-recording-length) belgelerimizde bulabilirsiniz.

### <a name="improvements-and-fixes-in-the-windows-holographic-version-20h2-update"></a>Windows Holographic, sürüm 20h2 güncelleştirmesiyle geliştirmeler ve düzeltmeler:

- OOBE 'deki daha fazla ekran artık koyu modda.
- Daha fazla bilgi edinin çevrimiçi gizlilik bildirimine en son çevrimiçi işaret etmelidir.
- Kullanıcıların, sağlama paketleri aracılığıyla VPN profilleri sağlayabildiği bir sorun oluştu.
- VPN bağlantısı için sabit proxy yapılandırması sorunu.
- AllowUsbConnection için NCM için MDM aracılığıyla USB işlevlerinin numaralandırılmasını devre dışı bırakma ilkesi güncelleştirildi.
- cihaz [tek uygulama bilgi noktası](hololens-kiosk.md)olarak ayarlandığında, bir HoloLens cihazının medya aktarım protokolü (MTP) üzerinden dosya gezgini 'nde gösterilmesini önleyen bir sorun ele alınmalıdır. MTP (genel olarak USB bağlantısının), [Allowusbconnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ilkesi kullanılarak hala devre dışı bırakılabileceğini unutmayın.
- Başlat menüsü simgelerin bilgi noktası modunda doğru şekilde ölçeklendirdiği bir sorun düzeltildi.
- Azure AD gruplarına hedeflenmiş bilgi noktası modu 'na engel olan HTTP önbelleklemesi nedeniyle bir sorun düzeltildi.
- Kullanıcıların, Geliştirici modunu devre dışı bırakmadığı ve yeniden etkinleştirmedikleri takdirde, sağlama paketleri ile Geliştirici modunu etkinleştirdikten sonra çift bir sorun düzeltildi.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, sürüm 1903-Kasım 2020 güncelleştirme

- Derleme 18362,1085

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermiyor; Holographic, sürüm 20h2 olan en son özellik yayın Windows derlemesini denemenizi öneririz.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, sürüm 2004-Ekim 2020 güncelleştirme

- Derleme 19041,1124

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çalışma zamanı sistem hatasına neden olan gereksiz bir denetim kaldırıldı.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, sürüm 1903-Ekim 2020 güncelleştirme

- Derleme 18362,1081

bu aylık kalite güncelleştirmesi herhangi bir önemli değişiklik içermez Windows Holographic, sürüm 2004 için en son derlemelerimizi denemenizi öneririz.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, sürüm 2004-Eylül 2020 güncelleştirme

- Derleme 19041,1117

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- appxmanifest 'de SupportsMultipleInstances = "true" olduğunda Visual Studio bir uygulamada hata ayıklamayı önleyen bir sorunu giderir.
- Bu sürüm, ağ proxy 'si üzerinden başarısız olan Internet algılamayı ele almak için NCSı proxy algılama düzeltmesini içerir. NCSı, Internet bağlantısı algılaması için makine ara sunucusunu ve profil başına proxy 'yi kullanabilir. Kullanıcı başına ara sunucu, gelecek sürümlerde NCSI tarafından desteklenecegizli olacak.
- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağıya doğru eğiktir. Daha yeni HoloLens 2 sürümleri, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
- Belirli senaryolarda daha az izleme kaybıyla sonuçlanacak gelişmiş el izleme sağlamlığı.
- Bu sürüm, video yakalama sorunlarına katkıda bulunarak ses zaman damgası kalitesini geliştirmeye ilişkin bir düzeltme içerir.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, sürüm 1903 - Eylül 2020 Güncelleştirmesi

- Derleme 18362.1079

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Çoğu Windows Mixed Reality, kullanıcının başı ileriye doğru nötr bir konumda olduğunda ileri yönlü vektörü yere paraleldir. Ancak, HoloLens 2'nin önceki sürümleri vektörü görüntüleme panelleri yerine dikey olacak şekilde hizalar ve bu da ideal yönlendirmeye göre birkaç derece aşağıya doğru eğiktir. Daha yeni HoloLens 2 sürümleri, form faktörleri arasında semantik tutarlılık sağlamak için bu sorunu düzeltti.
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

- Geliştiriciler artık güvenli bir bağlantı gerektiren bir uygulamanın etkinleştirilmesi Cihaz Portalı devre dışı bırakılması arasında seçim olabilir.
- Uygulamanın işletim sistemi güncelleştirmeleri sonrasında başlatılması için güvenilirlik artırıldı.
- Varsayılan gelen kutusu parlaklığı yüzde 100 olarak değiştirildi.
- HoloLens 2'de, Windows Cihaz Portalı için HTTPS iletmeyle ilgili bir HoloLens giderildi.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, sürüm 1903 - Temmuz 2020 Güncelleştirmesi

- Derleme 18362.1071

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamalarında izleme kaybı veya yeniden izleme elde edilirken hologramların kaybolmasına neden olan bir sorun düzeltildi.
- Belirli cihazlarda donanım hızlandırma ile HoloLens özel uygulamanın kabukta kilitlenmesi HoloLens Emulator bir sorun düzeltildi.
- HoloLens 2'de, Windows Cihaz Portalı için HTTPS iletmeyle ilgili bir HoloLens giderildi.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, sürüm 2004 - Haziran 2020 Güncelleştirmesi

- Derleme 19041.1106

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Özel MRC kaydedicileri artık belirtilmemişse belirli özellikler için yeni varsayılan değerlere sahiptir.
  - *MRC Video Etkisi üzerinde:*
    - PreferredHologramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0,9 (HoloLens) 1.0 (Çevreleyici başlığı))
  - *MRC Ses Etkisi üzerinde:*
    - LoopbackGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "App Audio Gain" Windows Cihaz Portalı)
    - MikrofonGain (Karma Gerçeklik Yakalama sayfasındaki geçerli "Mikrofon Ses Kazancı" Windows Cihaz Portalı)
- Karma gerçeklik yakalama senaryolarında ses kalitesini artırmaya yardımcı olan bir hata düzeltildi. Özellikle, bu düzeltme Başlat menüsü görüntülendiğinde kayıtta ses **hatalarını** ortadan kaldırmalı.
- Kaydedilen videolarda hologram kararlılığı geliştirildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- HolographicSpace.UserPresence API'si Genellikle Unity uygulamaları için devre dışı bırakılır. Bu davranış, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler. API artık Unity 2018.4.18 ve sonraki ve 2019.3.4 ve sonraki sürümleri için etkinleştirilmiştir.
- Bir web Cihaz Portalı üzerinden Wi-Fi, bir web tarayıcısı geçersiz sertifika nedeniyle erişimini engellenebilir. Tarayıcı, cihaz sertifikasına daha önce güvenilse bile "ERR_SSL_PROTOCOL_ERROR" gibi bir hata bildirebilirsiniz. Bu durumda, güvenlik uyarılarını yoksayma seçeneği Cihaz Portalı bu durumla devam etmek mümkün değildir. Bu güncelleştirme sorunu çözdü. Cihaz sertifikası daha önce bir bilgisayara indirildikten ve tarayıcı güvenlik uyarılarını kaldırmak için güvenilirse ve SSL hatası oluşursa, tarayıcı güvenlik uyarılarını ele almak için yeni sertifikanın indirildikten ve güvenilir olması gerekir.
- MSIX paketlerini kullanarak bir uygulama yükleyebilmeyi içeren bir çalışma zamanı sağlama paketi oluşturma özelliği etkinleştirildi.
- **Ayarlar**  >  **System**  >  **Hologramlar'da,** cihaz kapanıyorsa kullanıcıların karma gerçeklik giriş girişlerinden tüm hologramları otomatik olarak kaldırmasını sağlayan bir ayar eklendi.
- Piksel biçimini değiştiren uygulamaların HoloLens öykünücüde siyah işlemeye neden olan bir HoloLens düzeltildi.
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

HoloLens 2, Windows Holographic için Mayıs *2020* ana yazılım güncelleştirmesi, Windows Autopilot desteği, uygulama koyu modu, 5G/LTE etkin noktaları için USB Ethernet desteği ve çok daha fazlası gibi heyecan verici yeni özellikler içerir. En son sürüme güncelleştirmek için Ayarlar uygulamasını açın, & Güvenliği Güncelleştir'e gidin ve   Güncelleştirmeleri **Kontrol Edin düğmesini** ****   seçin. 

|             Özellik                              |          Açıklama                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Windows AutoPilot kullanarak yeni cihazları üretim için önceden yapılandırma ve sorunsuz bir şekilde ayarlama                 |
|       FIDO 2 desteği                             |          Paylaşılan cihazlar için hızlı ve güvenli kimlik doğrulamasını etkinleştirmek için FIDO2 Güvenlik Anahtarları desteği            |
|       Geliştirilmiş sağlama                      |          Usb sürücüden uygulamanıza sorunsuz bir şekilde bir sağlama paketi HoloLens                              |
|       Uygulama yükleme durumu                 |          MDM aracılığıyla Ayarlar uygulamalar için uygulamanın 2. HoloLens yükleme durumunu denetleme               |
|       Yapılandırma hizmeti sağlayıcıları (CSP'ler)   |          Yönetici denetimi özelliklerini geliştirmek için yeni yapılandırma hizmeti sağlayıcıları eklendi                 |
|       USB 5G/LTE desteği                       |          Genişletilmiş USB Ethernet özelliği 5G/LTE desteği sağlar                                    |
|       Koyu uygulama modu                              |          Hem koyu hem de açık modlarını destekleyen uygulamalar için koyu uygulama modu kullanılabilir ve görüntüleme deneyimini geliştirin        |
|       Sesli komutlar                             |          HoloLens eller denetlemek için ek sistem ses komutları desteği                           |
|       İzleme geliştirmeleri                 |          İzleme geliştirmeleri, düğmeleri ve 2B kurşun etkileşimini daha doğru hale getirir                        |
|       Kalite iyileştirmeleri ve düzeltmeleri                 |          Platform genelinde çeşitli sistem performansı ve güvenilirlik iyileştirmeleri                            |

### <a name="support-for-windows-autopilot"></a>Windows Autopilot için destek

Windows HoloLens 2 için Autopilot, cihaz satış kanalının ıntune kiracınıza HoloLens önceden kaydolmasına olanak tanır. Cihazlar geldiğinde, kiracınız altında paylaşılan cihazlar olarak kendi kendine dağıtım yapmaya hazırsınız demektir. Self-Deployment 'ın avantajlarından yararlanmak için, cihazın bir USB-C-Ethernet kullanarak kurulum 'daki ilk ekran sırasında ağa bağlanması gerekir.

Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattıktan sonra, işlem aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin.
1. cihazı Microsoft Intune (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.
1. Cihaza yönelik ilkeleri, sertifikaları ve ağ profillerini indirin.
1. Cihazı sağlayın.
1. Kullanıcıya oturum açma ekranını sunun.

[Windows Autopilot for HoloLens 2 değerlendirme kılavuzunda](hololens2-autopilot.md)daha fazla bilgi edinin.

*AutoPilot önizlemesini şimdi katmak için hesap yöneticinize başvurun. Autopilot için kullanıma sunulan cihazlar yakında gönderim yapmaya başlayacaktır.*

### <a name="fido2-security-key-support"></a>FIDO2 güvenlik anahtarı desteği

bazı kullanıcılar bir HoloLens cihazını iş veya okul ortamında başkalarıyla paylaşır. Bu nedenle, kullanıcıların uzun Kullanıcı adlarını ve parolalarını yazmadan kolayca kolayca olanak sağlamak önemlidir. hızlı kimlik çevrimiçi (fido), kuruluşunuzdaki herkesin (Azure AD kiracısı) kullanıcı adı veya parola girmeden HoloLens sorunsuzca oturum açmasını sağlar.

FIDO2 güvenlik anahtarları, herhangi bir form faktörüyle gelebilmesi için bir "unphishable" standartlara dayalı bir kimlik doğrulama yöntemidir. FıDO, passwordless kimlik doğrulaması için açık bir standarttır. Kullanıcıların ve kuruluşların kendi kaynaklarında Kullanıcı adı veya parola olmadan oturum açmasına olanak tanır. Bunun yerine, bir dış güvenlik anahtarı veya bir cihazda yerleşik bir platform anahtarı kullanırlar.

Başlamak için bkz. [passwordless güvenlik anahtarı oturum açma 'Yı etkinleştirme](/azure/active-directory/authentication/howto-authentication-passwordless-security-key).

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Sağlama paketi aracılığıyla geliştirilmiş MDM kaydı

sağlama paketleri, HoloLens kullanıma hazır deneyim yerine bir yapılandırma dosyası aracılığıyla HoloLens yapılandırmayı ayarlamanıza olanak sağlar. daha önce, sağlama paketlerinin HoloLens iç belleğe kopyalanması gerekiyordu. artık bir USB sürücüde olabilir, böylece birden çok HoloLens cihazda yeniden kullanmak daha kolay hale getiriyoruz ve cihazları paralel olarak sağlayabilirsiniz. Sağlama paketleri artık cihaz yönetimine kaydolmak için bir alanı destekledikten sonra, sağlamadan sonra el ile kurulum gerektirmez.

Denemek için:

1. Windows Configuration Designer 'ın en son sürümünü Windows mağazasından bilgisayarınıza indirin.
1. **HoloLens sağla**' yı seçin  >  **HoloLens 2 cihaz sağlayın**.
1. Yapılandırma profilinizi oluşturun. Ardından, bir USB-C depolama cihazına oluşturulan tüm dosyaları kopyalayın.
1. USB-C cihazını herhangi bir yeniden flaşla HoloLens bağlayın. Ardından,   +  sağlama paketinizi uygulamak için ses **tasarrufu** düğmelerine basın.

### <a name="line-of-business-application-install-status"></a>İş kolu uygulaması yüklemesi durumu

İş kolu uygulamaları için MDM uygulama dağıtımı ve yönetimi HoloLens için önemlidir. Yöneticiler ve kullanıcıların, denetim ve Tanılama için uygulama yüklemesi durumunu görüntülemesi gerekir. bu sürümde, **Ayarlar**  >  **hesaplarına**  >  **erişim iş veya okul**  >  **hesabına hesap**  >  **bilgilerinize** tıkladığımızda daha fazla ayrıntı ekledik.

### <a name="additional-csps-and-policies"></a>Ek CSP 'Ler ve ilkeler

Bir [yapılandırma hizmeti sağlayıcısı (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) bir cihazdaki yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. bu sürümde, denetim yöneticilerinin dağıtılan HoloLens cihazlara sahip olmasını sağlamak için daha fazla ilke desteği ekleyeceğiz. HoloLens tarafından desteklenen csp 'ler listesi için bkz. [networkqospolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

Bu sürümdeki yenilikler:

**İlke CSP 'si** 

ilke yapılandırma hizmeti sağlayıcısı, kuruluşun Windows cihazlarda ilkeleri yapılandırmasına olanak sağlar. bu sürümde, burada listelenen HoloLens için yeni ilkeler ekledik. daha fazla bilgi için bkz. [HoloLens 2 tarafından desteklenen ilke csp 'leri](/windows/client-management/mdm/policies-supported-by-hololens2).  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps
- LetAppsAccessGazeInput
- LetAppsAccessGazeInput_ForceAllowTheseApps
- LetAppsAccessGazeInput_ForceDenyTheseApps
- LetAppsAccessGazeInput_UserInControlOfTheseApps
- LetAppsAccessMicrophone_ForceAllowTheseApps
- LetAppsAccessMicrophone_ForceDenyTheseApps
- LetAppsAccessMicrophone_UserInControlOfTheseApps
- AllowWiFi

**NetworkQoSPolicy CSP**

NetworkQoSPolicy yapılandırma hizmeti sağlayıcısı, ağ hizmet kalitesi (QoS) ilkeleri oluşturur. QoS ilkesi, bir dizi eşleşen koşulu temel alarak ağ trafiği üzerinde bir dizi eylem gerçekleştirir. Daha fazla bilgi için bkz. [Networkqospolicy CSP](/windows/client-management/mdm/networkqospolicy-csp).

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>5G/LTE tethered cihazları için genişletilmiş USB Ethernet desteği

5 g/LTE telefonlar ve Wi-Fi etkin noktalar gibi belirli mobil geniş bant cihazlarının USB üzerinden HoloLens 2 ' ye tethered oldukları durumlarda etkinleştirilmesi için destek eklenmiştir. Bu cihazlar artık farklı bir Ethernet bağlantısı olarak **ağ ayarlarında** görüntülenmektedir. (Dış sürücü gerektiren mobil geniş bant cihazları desteklenmez.) Bu işlevsellik Wi-Fi kullanılabilir olmadığında yüksek bant genişliğine sahip bağlantılara izin verebilir ve Wi-Fi internet paylaşımı yeterince iyi değildir. desteklenen USB cihazları hakkında daha fazla bilgi edinmek için bkz. [Bağlan Bluetooth ve USB-C cihazları](hololens-connect-devices.md).  

### <a name="hand-tracking-improvements"></a>İzleme geliştirmeleri

Bu sürüm çeşitli izleme geliştirmeleri içerir:

- **İşaret pozu kararlılığı:** Sistem artık, Palm tarafından occlukal aldığında Dizin parmak yerini geri alır. Bu değişiklik, düğmeleri gönderdiğinizde, içerik yazarken ve daha fazlasını yaparken doğruluğu artırır! 
- **Azaltılmış, yanlışlıkla hava dokunmalar:** Hava dokunma hareketini algılamayı geliştirdik. Artık birkaç yaygın senaryoda (örneğin, ellerinizi yüzlerinizi bıraktığınızda) daha az yanlışlıkla etkinleştirme vardır.
- **Kullanıcı anahtarı güvenilirliği:** Bir cihaz paylaştığınızda el ile sistem boyutunu güncelleştirmek daha hızlı ve daha güvenilirdir.
- **Azaltılmış el çalma:** Sensörlerden ikiden fazla elinin bulunduğu durumların işlenmesini geliştirdik. Birden çok kişi birlikte çalışıyorsa, izlenen kişinin kullanıcıdan sahnedeki başka birinin adına "atlayacağı" bir şansınız daha düşüktür.
- **Sistem güvenilirliği:** Cihaz yüksek yük altında olduğunda bir yandan izlemenin çalışmayı durdurmasına neden olan bir sorun düzeltildi.

### <a name="dark-mode"></a>Koyu mod

birçok Windows uygulama artık koyu ve hafif modları desteklemektedir. HoloLens 2 kullanıcı, her ikisini de destekleyen uygulamalar için varsayılan modu seçebilirler. güncelleştirme sonrasında, varsayılan uygulama modu "koyu" olur, ancak bu ayarı kolayca değiştirebilirsiniz: **Ayarlar**  >  **sistem** renkleri ' ne gidin  >    >  **varsayılan uygulama modunu seçin**.

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

![Koyu modda Windows döşeli.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Sistem ses komutları

Artık, cihazdaki herhangi bir uygulamayla sesli komutları kullanabilirsiniz. Daha fazla bilgi için [bkz. Seslerinizi kullanarak HoloLens.](hololens-cortana.md) Ayrıca [bkz. HoloLens 2 için desteklenen diller.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana güncelleştirmeleri

Güncelleştirilmiş uygulama, cihazlarınızı Microsoft 365 (şu anda yalnızca US-English) yardımcı olmak için US-English tümleştirilmiştir. 2 HoloLens de, Cortana ayarlama veya yeniden başlatma gibi belirli cihaza özgü komutları artık desteklemez. Bu seçenekler artık yeni sistem ses komutları tarafından de desteklemektedir. Blog sayfamızda yeni Cortana hakkında daha fazla bilgi [edinebilirsiniz.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Kalite geliştirmeleri ve düzeltmeleri

Güncelleştirmede yapılan geliştirmeler ve düzeltmeler:  

- Etkin bir ekran ayarlama sistemi tanıtıldı. Bu özellik hologramların kararlılığını ve hizalamasını artırır. Artık kafanızı yan yana taşımış olurken bunlar yerinde kalır.
- Akış akışının Wi-Fi kesintiye HoloLens bir hata düzeltildi. Bir uygulama düşük gecikmeli akış gerektiğini gösteriyorsa, [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)işlevini çağırarak düzeltmeyi gerçekleştirin.
- Araştırma modunda akış sırasında bir cihazın askıda kalma süresi düzeltildi.
- Bazı durumlarda oturum devam edince oturum açma ekranında doğru kullanıcının görüntülenmey on the bug düzeltildi.
- Kullanıcıların MDM günlüklerini Ayarlar aracılığıyla dışarı **aktaramama sorunu düzeltildi.**
- İlk kurulumdan hemen sonra göz izleme doğruluğunun beklenenden daha düşük olduğu bir sorun düzeltildi.
- Göz izleme alt sisteminin belirli koşullar altında ayarlama işlemini başlatamadığı veya gerçekleştiramadığı bir sorun düzeltildi.
- Önceden ayarlanmış bir kullanıcı için göz düzeltmesi istendiğinde bir sorun düzeltildi.
- Bir sürücünün göz ayarı sırasında kilitlenmesi sorunu düzeltildi.
- Yinelenen güç düğmesi basmalarının 60 saniyelik sistem zaman aşımına ve kabuk kilitlenmeye neden olduğu bir sorun düzeltildi.
- Derinlik arabellekleri için geliştirilmiş kararlılık.
- Kullanıcıların geri **bildirimi** daha kolay paylaş Geri Bildirim Merkezi için paylaşıma bir Paylaş düğmesi eklendi.
- RoboRaid wan'ın düzgün yüklenmemiş olmasıyla ilgili bir hata düzeltildi.

### <a name="known-issues"></a>Bilinen sorunlar

- zh-CN sistem diliyle ilgili bir sorun ses komutlarının karma gerçeklik yakalamasını veya cihaz IP adresini görüntülemesini önlemektedir.
- Bir sorun, cihazı "Hey Cortana" ses etkinleştirmeyi kullanmak üzere başlattıktan sonra Cortana uygulamasını başlatmanız gerekir. Bir 18362 derlemesinde güncelleştirme yaptıysanız, Cortana uygulamasının önceki sürümü için Başlat'ta artık çalışmayan ikinci bir uygulama kutucuğu **da görüntüleniyor olabilir.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, sürüm 1903 - Mayıs 2020 Güncelleştirmesi

- Derleme 18362.1061

Bu aylık kalite güncelleştirmesi, ekip daha önce açıklandığı gibi Windows Holographic sürüm 2004 Mayıs Güncelleştirmesi üzerinde çalıştığı için önemli bir değişiklik içermemektedir.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, sürüm 1903 - Nisan 2020 Güncelleştirmesi

- Derleme 18362.1059

**Desteklenen uygulamalar için koyu mod**

Birçok Windows hem koyu hem de açık modu destekler. HoloLens 2 müşteri artık her iki renk düzenini de destekleyen uygulamalar için varsayılan modu seçebilir. Müşteri geri bildirimlerine dayanarak varsayılan uygulama modunu "koyu" olarak ayarlamış oluruz ancak bu ayarı istediğiniz zaman kolayca değiştirebilirsiniz: "Varsayılan uygulama modunu seçin" için **Ayarlar > System > Colors'a** **gidin.**

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

**Güncelleştirmede de iyileştirmeler ve düzeltmeler:**

- Kabuk katmanlarının karma gerçeklik yakalamalarına dahil olduğundan emin olmak.
- Unreal geliştiricileri artık uygulamalarını test etmek ve hata ayıklamak için Cihaz Portalı 3B Görünüm sayfasını kullanabilir.
- *HolographicDepthReprojectionMethod DepthReprojection* algoritması kullanılırken karma gerçeklik yakalamada geliştirilmiş hologram kararlılığı.
- 32 bit ARM uygulamaları üzerinde "WinRT IStreamSocketListener API Sınıfı kayıtlı değil" hatası düzeltildi.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, sürüm 1903 - Mart 2020 Güncelleştirmesi

- Derleme 18362.1056

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- *HolographicDepthReprojectionMethod AutoPlanar* algoritması kullanılırken karma gerçeklik yakalamada geliştirilmiş hologram kararlılığı.
- Derinlik MF örneğine bağlı koordinat sisteminin genel belgelerle tutarlı olduğundan emin olun.
- Müşterilerin cihaz portalı üzerinden büyük miktarlarda metin yapıştırmalarına olanak sağlayarak geliştirici üretkenliği geliştirildi.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, sürüm 1903 - Şubat 2020 Güncelleştirmesi

- Derleme 18362.1053

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Unity uygulamaları için HolographicSpace.UserPresence API'sini geçici olarak devre dışı bırakıldı. Bu değişiklik, "arka planda çalıştır" ayarı etkinleştirilse bile bazı uygulamaların, mengene çevrilmiş durumdayken duraklatılmasına neden olan bir sorunu önler.
- Kullanıcı birkaç saniye sonra kullanıcı arabiriminin donması ve tekrar kabukta kilitlenmesi nedeniyle oluşan rastgele BIR HUP kilitlenmesi düzeltildi.
- Dizin parmaklarınızı sıktınız ve bu şekilde el izleme iyileştirildi. Böylece, bu parmak büyük kısmı beklenmedik bir şekilde curl olma olasılığı daha düşük olur.
- Baş izleme, uzamsal eşleme ve diğer çalışma zamanlarının güvenilirliği geliştirildi.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, sürüm 1903 - Ocak 2020 Güncelleştirmesi

- Derleme 18362.1043

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- HoloLens 2 öykünücüsü ile çalışırken özel uygulamalar için geliştirilmiş kararlılık.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, sürüm 1903 - Aralık 2019 Güncelleştirmesi

- Derleme 18362.1042

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- Son aşama yeniden üretme (LSR) düzeltmeleri tanıtıldı. Hologramların görsel işlemesi, derinliğini daha doğru bir şekilde hesaparak daha kararlı ve daha yavaş görünecek şekilde iyileştirildi. Uygulamalar hologram derinliğini doğru ayarlamazsa bu belirti bu güncelleştirmeden sonra daha fark edilir.
- Özel uygulamaların kararlılığı ve özel uygulamalar arasında gezinme düzeltildi.
- Cihaz birkaç gün boyunca bekleme durumunda kaldıktan sonra karma gerçeklik yakalamanın video kaydedemezse bir sorun çözüldü.
- Geliştirilmiş hologram kararlılığı.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, sürüm 1903 - Kasım 2019 Güncelleştirmesi

- Derleme 18362.1039

Güncelleştirmedeki geliştirmeler ve düzeltmeler:

- en-CA **ve** en-AU için ilk kurulum sırasında Select voice komutlarının işlevselliği düzeltildi.
- En son Unity ve Karma Gerçeklik Araç Seti (MRTK) sürümlerinde uzak yerleştirilen nesnelerin görsel kalitesi geliştirildi.
- Holografik uygulamaların başlangıçta duraklatılmış durumda takılı kalan ve sonra kapatılana kadar Başlat menüsü sorunları düzeltildi.
- OpenXR çalışma zamanı uyumluluk düzeltmeleri ve HoloLens 2 ve öykünücü için geliştirmeler.
