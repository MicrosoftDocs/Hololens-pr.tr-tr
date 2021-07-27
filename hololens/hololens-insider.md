---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleri ile çalışmaya başlamayı ve bir sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamayı HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b7e5a7cbaa746f58fe0344dd8bf5b027e2e8cea7
ms.sourcegitcommit: dc5d6f3802c997749775be04de522af8cb6d0850
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2021
ms.locfileid: "114693708"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Önizleme derlemeleri' HoloLens! Hızlı bir şekilde çalışmaya [başlamanız ve bir sonraki](hololens-insider.md#start-receiving-insider-builds) büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Insider Sürüm Notları

Windows Insiders'a yeni özellikler Windows heyecanla başlayacağız. En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır. Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme ekley Windows devam edeceğiz. Bu güncelleştirmeleri gerçekliğinize göre karıştırmak için heyecan ve hazır olun.

| Özellik                 | Açıklama                | Kullanıcı veya Senaryo | Derleme tanıtıldı |
|-------------------------|----------------------------|--------------|------------------|
| [Rapor ayrıntıları için CSP HoloLens değişiklikleri](#csp-changes-for-reporting-hololens-details) | Veri sorgulamak için yeni CSP'ler | IT Yöneticileri    | 20348.1403                 |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Bir hesapta otomatik olarak oturum açmak için kullanılır | IT Yöneticileri | 20348.1405 |
| [Sertifika Yöneticisi için PFX dosyası desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleme | Son Kullanıcı | 20348.1405 |
| [Gelişmiş tanılama raporunu Ayarlar'da HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazda MDM tanılama günlüklerini görüntüleme | Sorun giderme | 20348.1405 |
| [Çevrimdışı Tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için görsel geri bildirim | Sorun giderme | 20348.1405 |
| [Yalnızca özel mağaza uygulamalarını yalnızca özel mağaza Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluş uygulamalarını gösterecek şekilde yapılandırma | BT Yöneticisi | 20348.1408 |
| [Düzeltmeler ve geliştirmeler](hololens-insider.md#fixes-and-improvements) | Düzeltmeler ve geliştirmeler HoloLens. | Tümü | 20348.1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Rapor ayrıntıları için CSP HoloLens değişiklikleri

- Windows Insider derlemesinde tanıtıldı, 20348.1403

Aşağıdaki CSP'ler, cihazlarından gelen bilgileri bildirmenin yeni HoloLens güncelleştirilmiştir.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP - Ücretsiz Depolama

DevDetail CSP artık cihaz üzerinde boş depolama alanı HoloLens raporlar. Bu değer, uygulamanın Ayarlar sayfasında gösterilen değerle yaklaşık Depolama eşleşmesi gerekir. Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer alenidir.

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

Bu yeni AutoLogonUser ilkesi, bir kullanıcının otomatik olarak oturum açıp oturum açmayacaklarını kontrol eder. Bazı müşteriler bir kimliğe bağlı ancak oturum açma deneyimi istemeden cihazları ayarlamak ister. Imagine cihazı alacak ve uzaktan yardım'ı hemen kullanmaya devam edebilirsiniz. Veya cihazları hızla dağıtarak son kullanıcılarının oturum açma HoloLens olanaklı olma avantajından da yararlanabilirsiniz.

İlke boş olmayan bir değere ayarlanırsa, otomatik oturum açma kullanıcısını e-posta adresi belirtir. Belirtilen kullanıcının otomatik oturum açmayı etkinleştirmek için cihazda en az bir kez oturum açması gerekir.

Yeni ilke Dizesi değerinin `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` OMA-URI'sı

- Aynı e-posta adresine sahip kullanıcı otomatik oturum açmayı etkinleştirmiş olur.

Bu ilkenin yapılandırıldığında, ilkede belirtilen kullanıcının en az bir kez oturum açması gerekir. İlk oturum açma sonrasında cihazın yeniden başlatılması, belirtilen kullanıcının otomatik olarak oturum açmasını sağlar. Yalnızca tek bir otomatik oturum açma kullanıcısı de destekler. Etkinleştirildikten sonra, otomatik olarak oturum açan kullanıcı el ile oturumu kapatamayacaktır. Farklı bir kullanıcı olarak oturum açması için ilkenin önce devre dışı bırakılmıştır.

> [!NOTE]
> - Büyük işletim sistemi güncelleştirmeleri gibi bazı olaylar, belirtilen kullanıcının otomatik oturum açma davranışını sürdürmesi için cihazda yeniden oturum açmasını gerekli kilebilir. 
> - Otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için de kullanılabilir.

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosyası desteği

Windows Insider derlemesi 20348.1405'te tanıtıldı. Artık .pfx sertifikalarını [kullanmak için](certificate-manager.md) Sertifika Yöneticisi'ne destek ekledik. Kullanıcılar Güvenlik Sertifikalarını  >  **Ayarlar'&'a** gidin ve Sertifika yükle'yi seçerek kullanıcı arabirimi  >  artık .pfx sertifika dosyasını destekliyor. 
Kullanıcılar özel anahtarla .pfx sertifikasını kullanıcı deposuna veya makine deposuna aktarabilirsiniz.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Gelişmiş tanılama raporunu Ayarlar'da HoloLens

Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır. Bu yeni özellikle daha önce, Ayarlar Hesapları Erişim iş veya okul aracılığıyla toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra cihazın MDM üzerinden veya cihazın yakınından yapılması ve Yönetim günlüklerinizi dışarı aktar'ı seçerek yakındaki bir pc'de  ->    >  görüntüleyebilirsiniz. 

Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz. MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.** Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.

![Gelişmiş tanılama raporunu uygulamanın Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı Tanılama bildirimleri

Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics) Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.
Artık Windows Insider derlemelerine eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır. Birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)
 
Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Yalnızca özel mağaza uygulamalarını Microsoft Store

RequirePrivateStoreOnly ilkesi, uygulama için HoloLens. Bu ilke, Microsoft Store uygulamasının yalnızca özel mağazayı kuruluş için yapılandırılan şekilde yapılandırılması için etkinleştirir. Erişimi yalnızca kullanılabilir yapmış olduğunuz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly hakkında daha fazla bilgi](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler:

- Kilitlenmiş [dosyaları indirme istemi Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Cihazlardan uyumluluk özelliklerini raporlamayla ilgili HoloLens ele; Insider derlemeleri üzerinde doğru raporlamanın tetiklanması için yeniden başlatma gerekebilir.  
- Remote Assist'in yeni flash görüntülere yüklenmiş olan in-box sürümü güncelleştirildi.


## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlama

> [!NOTE]
> Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.
> - "Cihazı yeniden başlat" sesli komutu iyi çalışıyor. 
> - Ayrıca, Ayarlar/Windows Insider Programı.
>
> Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.

Bir HoloLens 2 cihazında Update   >  **Ayarlar Security &'Windows Insider Programı** gidin ve  >   Kullanmaya başlayın.  Windows Insider olarak kaydetmek için kullanılan hesabı bağlama.

Windows artık Kanallar'a taşınıyor. Hızlı **halka** Geliştirme **Kanalı,** Yavaş  halka Beta Kanal olur **ve** **Yayın** Önizleme halkası Yayın Önizleme Kanalı **olur.** Eşleme şu şekildedir:

![Windows Insider Kanalları açıklaması](images/WindowsInsiderChannels.png)

Daha fazla bilgi için [bkz. Bloglarda Windows Insider Kanallarına](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows.
Ardından, **geliştirmenin etkin Windows'ı** seçin, **Geliştirme** Kanalı mı yoksa derlemeler mi **almak Beta Kanal** seçin ve program koşullarını gözden geçirin.
Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin. Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak Ayarlar > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.

### <a name="update-error-0x80070490-work-around"></a>Hata güncelleştirme 0x80070490 çalışma

Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli çalışmalara bakın. Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.

#### <a name="stage-one---release-preview"></a>1. aşama - Yayın Önizlemesi

1.  Ayarlar, Güncelleştirme &' Windows Insider Programı Yayın Önizleme **Kanalı'Windows Insider Programı seçin.**

2.  Ayarlar, Update & Security, Windows Update, **Güncelleştirmeleri kontrol edin.** Güncelleştirmeden sonra ikinci aşamaya devam et.

#### <a name="stage-two---dev-channel"></a>2. aşama - Geliştirme Kanalı

1. Ayarlar Güvenlik güncelleştirme &, Windows Insider Programı Dev **Channel'ı seçin.**

2. Ayarlar, Update & Security, Windows Update, **Güncelleştirmeleri kontrol edin.**

## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve flash yönler

Uçuş imzalı ffu ile test etmek için, uçuş imzalı ffu'nun yanıp sönmeden önce cihazınızın kilidinin açılması gerekir.

1. Pc'de:
    1. ffu'dan bilgisayarınıza [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) indirin.
    
    1. arc (Gelişmiş Kurtarma Yardımcı) yükleme Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. HoloLens - Flight Unlock: **Ayarlar**  >  **Update &**  >  **Security'Windows Insider Programı** açın ve cihazı yeniden başlatın.

1. Flash FFU - Artık ARC kullanarak uçuş imzalı FFU'nun flash'unu sönersiniz.

### <a name="provide-feedback-and-report-issues"></a>Geri bildirim sağlama ve sorunları bildirme

Geri bildirim [ve Geri Bildirim Merkezi sağlamak](hololens-feedback.md) için HoloLens uygulama uygulamanızı kullanın. Bu Geri Bildirim Merkezi, mühendislerimizin hızla hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgileri dahil edilir.  Bu sürümün Çince ve Japonca HoloLens aynı şekilde bildiriliyor olması gerekir.

> [!NOTE]
> Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).

## <a name="note-for-developers"></a>Geliştiriciler için not

Uygulamalarınızı derlemenin Insider derlemelerini kullanarak geliştirmeyi denemeniz HoloLens.  Çalışmaya başlamaya [HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz. Bu yönergeler, bir derlemenin Insider derlemeleriyle HoloLens.  Unity ve Visual Studio geliştirme için zaten HoloLens kullanabilirsiniz.

## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdurma

Windows Holographic'in Insider derlemelerini artık almak istemiyorsanız, HoloLens'niz bir üretim derlemesi çalıştırıyorsa iptal [](hololens-recovery.md) edebilirsiniz veya Cihazınızı Gelişmiş Kurtarma Yardımcı'sı kullanarak kurtararak cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarabilirsiniz.

> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır. Daha sonra, cihazlarını el ile kurtarmaları gerekir. Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Bir üretim HoloLens çalıştığını doğrulamak için:

1. System **Ayarlar > Hakkında'> gidin** ve derleme numarasını bulun.

1. [Üretim derleme numaraları için sürüm notlarına bakın.](hololens-release-notes.md)

Insider derlemelerini geri almak için:

1. Üretim HoloLens çalıştıran bir Ayarlar > Update **& Security > Windows Insider Programı**'a gidin ve Insider derlemelerini **durdur'a gidin.**

1. Cihazınızı geri almak için yönergeleri izleyin.
