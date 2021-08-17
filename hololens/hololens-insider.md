---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider Derlemeleriyle çalışmaya başlama ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlama hakkında bilgi edinin.
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
ms.date: 08/19/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3ccb9d0f7175a358262c39c76d364aee464c5469
ms.sourcegitcommit: e2a3e85882b7c594d73d08fbd7ae85856d22f8c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2021
ms.locfileid: "122213919"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview yapılarına hoş geldiniz! [Başlamak ve HoloLens](hololens-insider.md#start-receiving-insider-builds) için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlamak kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider sürüm notları

ınsiders Windows yeni özellikleri yeniden başlatmak için heyecanlıyız. Yeni derlemeler, en son güncelleştirmeler için geliştirme ve Beta kanallarına uçucaktır. Windows ınsider derlemelerimize daha fazla özellik ve güncelleştirme eklediğimiz için bu sayfayı güncelleştirmeye devam edeceğiz. Heyecanlanmanıza ve bu güncelleştirmeleri gerçeğe sunmaya hazırlanın.

| Özellik                 | Açıklama                | Kullanıcı veya senaryo | Tanıtılan derleme |
|-------------------------|----------------------------|--------------|------------------|
| [raporlama HoloLens ayrıntıları için CSP değişiklikleri](#csp-changes-for-reporting-hololens-details) | Verileri sorgulamak için yeni CSP 'Ler | BT yöneticileri    | 20348,1403                 |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Hesapta otomatik olarak oturum açmak için kullanılır | BT yöneticileri | 20348,1405 |
| [Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri](#improved-update-restart-detection-and-notifications) | Güncelleştirmeler için yeni etkinleştirilen ilkeler ve UX. | BT yöneticileri | 20348,1405 |
| [Sertifika Yöneticisi için PFX dosya desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleyin | Son Kullanıcı | 20348,1405 |
| [Uygulama güncelleştirmeleri için akıllı yeniden deneme](#smart-retry-for-app-updates) | BT yöneticilerinin uygulamaları güncelleştirmek için yeniden denemelere izin verir. | BT yöneticileri | 20348,1405 |
| [HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazdaki MDM tanılama günlüklerini görüntüle | Sorun giderme | 20348,1405 |
| [Çevrimdışı tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için audiogörsel geri bildirimi | Sorun giderme | 20348,1405 |
| [Yalnızca Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluştan gelen uygulamaları gösterecek şekilde yapılandırma | BT Yöneticisi | 20348,1408 |
| [Düşük depolama günlüğü koleksiyonu geliştirmeleri](#low-storage-log-collection-improvements) | Düşük depolama durumları sırasında günlük toplama senaryolarında iyileştirmeler. | BT Yöneticisi | 20348,1412 |
| [Platform modu taşınıyor](#moving-platform-mode) | yapılandırıldığında, büyük deniz mavisi ' de düşük dinamik hareket yaşayan HoloLens 2 ' nin kullanımını sağlayan Platform modu beta 'yı tanıtır. | Tümü | 20348,1411 |
| [Düzeltmeler ve geliştirmeler](#fixes-and-improvements) | HoloLens düzeltmeler ve geliştirmeler. | Tümü | 20348,1411 |

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

### <a name="improved-update-restart-detection-and-notifications"></a>Geliştirilmiş güncelleştirme yeniden başlatma algılaması ve bildirimleri

etkin saatler ve yüklemesi zaman ilkeleri arasında, kullanımda olduklarında HoloLens cihazların yeniden başlatılmasını önlemek mümkündür. Ancak, gerekli bir güncelleştirmenin yüklenmesini tamamlaması durumunda yeniden başlatmalar gerçekleşmezseniz güncelleştirmelerin benimsenmesini de erteler. Artık, son tarihleri ve gerekli YENIDEN başlatmalar zorlayabilmesini ve bir güncelleştirme yüklemesinin zamanında tamamlandığından emin olmak için ilkeler ekledik. Kullanıcılardan önyükleme başlatılmadan önce bildirim alabilir ve BT ilkesine uygun olarak yeniden başlatma işleminin geciktirebilirler.

Aşağıdaki güncelleştirme ilkeleri eklendi:

- [Güncelleştirme/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Güncelleştirme/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Güncelleştirme/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Güncelleştirme/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Güncelleştirme/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Güncelleştirme/Configuredeadlinenooto reboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosyası desteği

Windows Insider derlemesi 20348.1405'te tanıtıldı. Artık .pfx sertifikalarını [kullanmak için](certificate-manager.md) Sertifika Yöneticisi'ne destek ekledik. Kullanıcılar Güvenlik Sertifikalarını Ayarlar'&'ye gidin ve Sertifika yükle'yi seçerek kullanıcı arabirimi  >    >  artık .pfx sertifika dosyasını destekliyor. 
Kullanıcılar özel anahtarla .pfx sertifikasını kullanıcı deposuna veya makine deposuna aktarabilirsiniz.

### <a name="smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için Akıllı Yeniden Deneme

Artık HoloLens için etkinleştirilen yeni bir ilke, IT Yöneticilerinin, güncelleştirmenin uygulamaya uygulanmasına izin verme nedeniyle başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir saat tarihi ayarlamasına olanak sağlayan yeni bir ilkedir. Bunlar, zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilirsiniz. Bu ilkeyi kullanma hakkında daha fazla bilgi edinmek için [lütfen ApplicationManagement/ScheduleForceRestartForUpdateFailures 'i görüntüden edinebilirsiniz.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Gelişmiş tanılama raporunu Ayarlar'da HoloLens

Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır. Bu yeni özellikle daha önce, bu özelliğin, Ayarlar Hesapları Erişim iş veya okul aracılığıyla toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra MDM aracılığıyla veya cihaza yakın bir cihazdan yapılması ve Yönetim günlüklerinizi dışarı aktar'ı seçerek yakındaki bir pc'de  ->    >  görüntüleyebilirsiniz. 

Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz. MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.** Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.

![Gelişmiş tanılama raporunu Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı Tanılama bildirimleri

Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics) Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.
Artık Insider Windows eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır. birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)

Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Yalnızca özel mağaza uygulamalarını Microsoft Store

Uygulama için RequirePrivateStoreOnly ilkesi HoloLens. Bu ilke, Microsoft Store uygulamasının yalnızca özel mağazayı gösterecek şekilde yapılandırılması için yapılandırmayı etkinleştirir. Erişimi yalnızca kullanılabilir yapmış olduğunuz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly hakkında daha fazla bilgi](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü toplama geliştirmeleri

Tanılama günlükleri toplanmış durumdayken cihazın disk alanı düşük gibi görünen senaryolarda,StorageDiagnostics.zip **ek** bir rapor oluşturulur. Düşük depolama eşiği, depolama alanı algısı Windows [belirlenir.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Platform Modunu Taşıma

**Insider derlemesi 20348.1411'den** sonra, HoloLens 2'de düşük dinamik hareket hareketli platformlarında izlemeye yönelik beta desteği ekledik. Derlemeyi yükleyerek Ve Taşıma Platformu Modu'na etkinleştirdikten sonra, HoloLens 2'nizi büyük gemiler ve büyük deniz gemileri gibi daha önce erişilemeyen ortamlarda kullanabilirsiniz. Şu anda bu özellik yalnızca bu hareketli platformların etkinleştirilmesini hedeflemektedir. Özelliği başka ortamlarda kullanmaya çalışmanıza engel olan bir şey yoktur ancak özellik önce bu ortamlar için destek eklemeye odaklanmaktadır.

Desteklenenler ve bu yeni özelliği etkinleştirme hakkında daha fazla bilgi edinmek [için, hareketli platform sayfasını ziyaret edin.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler

- Kilitlenmiş [dosyaları indirme istemi Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Cihazlardan uyumluluk özelliklerini raporlamayla ilgili HoloLens ele; Insider derlemeleri üzerinde doğru raporlamanın tetiklanması için yeniden başlatma gerekebilir.  
- Atanmış Erişim [API'sini](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) etkinleştirdikten sonra uygulamalar artık HoloLens oturum açmış olan kullanıcı için bilgi noktası modunda bir uygulamanın çalıştırılıp HoloLens.
- Remote Assist'in yeni flash görüntülere yüklenmiş olan in-box sürümü güncelleştirildi.

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlama

> [!NOTE]
> Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.
>
> - "Cihazı yeniden başlat" sesli komutu iyi çalışıyor.
> - Ayrıca, Ayarlar/Windows Insider Programı.
>
> Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.

Bir HoloLens 2 cihazında Ayarlar  >  **Update & Security**  >  **Windows Insider Programı'ye gidin** ve Kullanmaya başlayın. Windows Insider olarak kaydetmek için kullanılan hesabı bağlama.

Windows artık Kanallar'a taşınıyor. Hızlı **halka** Geliştirme **Kanalı,** Yavaş  halka Beta Kanal olur **ve** **Yayın** Önizleme halkası Yayın Önizleme Kanalı **olur.** Eşleme şu şekildedir:

![Windows Insider Kanalları açıklaması](images/WindowsInsiderChannels.png)

Daha fazla bilgi için [bkz. Bloglarda Windows Insider Kanallarına](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows.
Ardından, **geliştirmenin etkin Windows'ı** seçin, **Geliştirme** Kanalı mı yoksa derlemeler mi **almak Beta Kanal** seçin ve program koşullarını gözden geçirin.
Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin. Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak Ayarlar > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.

### <a name="update-error-0x80070490-work-around"></a>Hata güncelleştirme 0x80070490 çalışma

Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli geliştirmeyi deneyin. Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.

#### <a name="stage-one---release-preview"></a>1. aşama - Yayın Önizlemesi

1. Ayarlar Update & Security Windows Insider Programı **Release Preview Channel (Yayın Önizleme Kanalı) öğesini seçin.**

2. Ayarlar, Update & Security, Windows Update, **Güncelleştirmeleri kontrol edin.** Güncelleştirmeden sonra ikinci aşamaya devam et.

#### <a name="stage-two---dev-channel"></a>2. aşama - Geliştirme Kanalı

1. Ayarlar Update & Security Windows Insider Programı **Dev Channel'ı seçin.**

2. Ayarlar, Update & Security, Windows Update, **Güncelleştirmeleri kontrol edin.**

## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve flash yönler

Uçuş imzalı ffu ile test etmek için, uçuş imzalı ffu'nun yanıp sönmeden önce cihazınızın kilidinin açılması gerekir.

1. Pc'de:
    1. ffu'dan bilgisayarınıza [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) indirin.

    1. arc (Gelişmiş Kurtarma Yardımcı) yükleme Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. HoloLens - Flight Unlock: Ayarlar   >  **Update & Security**  >  **Windows Insider Programı'i** açın ve cihazı yeniden başlatın.

1. Flash FFU - Artık ARC kullanarak uçuş imzalı FFU'nun flash'unu sönersiniz.

### <a name="provide-feedback-and-report-issues"></a>Geri bildirim sağlama ve sorunları bildirme

Geri bildirim [ve Geri Bildirim Merkezi sağlamak](hololens-feedback.md) için HoloLens uygulama uygulamanızı kullanın. Bu Geri Bildirim Merkezi, mühendislerimizin hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgilerine dahil edilir.  Bu sürümün Çince ve Japonca HoloLens aynı şekilde bildiriliyor olması gerekir.

> [!NOTE]
> Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).

## <a name="note-for-developers"></a>Geliştiriciler için not

Uygulamalarınızı derlemenin Insider derlemelerini kullanarak geliştirmeyi denemeniz HoloLens.  Çalışmaya başlamaya [HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz. Bu yönergeler, bir derlemenin Insider derlemeleriyle HoloLens.  Unity ve Visual Studio derlemelerini kullanarak HoloLens kullanabilirsiniz.

## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdurma

Windows Holographic'in Insider derlemelerini artık almak istemiyorsanız, HoloLens'niz bir üretim derlemesi çalıştırıyorsa [](hololens-recovery.md) geri almayı tercih edebilirsiniz veya Cihazınızı Gelişmiş Kurtarma Yardımcı'sı kullanarak kurtararak cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarabilirsiniz.

> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır. Daha sonra, cihazlarını el ile kurtarmaları gerekir. Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Bir üretim HoloLens çalıştığını doğrulamak için:

1. **Ayarlar > sistem >**' e gidin ve derleme numarasını bulun.

1. [Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).

Insider derlemelerini devre dışı bırakmak için:

1. üretim yapısını çalıştıran bir HoloLens, **Ayarlar > & güvenlik > Windows ınsider programı**' na gidin ve **ınsider derlemelerini durdur**' u seçin.

1. Cihazınızı devre dışı bırakmak için yönergeleri izleyin.
