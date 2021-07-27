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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 12c5586f931487d871d4b6e98992ca0047b2adbf
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659208"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview yapılarına hoş geldiniz! [Başlamak ve HoloLens](hololens-insider.md#start-receiving-insider-builds) için bir sonraki ana işletim sistemi güncelleştirmesine yönelik değerli geri bildirimler sağlamak kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider sürüm notları

ınsiders Windows yeni özellikleri yeniden başlatmak için heyecanlıyız. Yeni derlemeler, en son güncelleştirmeler için geliştirme ve Beta kanallarına uçucaktır. Windows ınsider derlemelerimize daha fazla özellik ve güncelleştirme eklediğimiz için bu sayfayı güncelleştirmeye devam edeceğiz. Heyecanlanmanıza ve bu güncelleştirmeleri gerçeğe sunmaya hazırlanın.

| Özellik                 | Açıklama                | Kullanıcı veya senaryo | Tanıtılan derleme |
|-------------------------|----------------------------|--------------|------------------|
| [raporlama HoloLens ayrıntıları için CSP değişiklikleri](#csp-changes-for-reporting-hololens-details) | Verileri sorgulamak için yeni CSP 'Ler | BT yöneticileri    | 20348,1403                 |
| [CSP tarafından denetlenen otomatik oturum açma ilkesi](#auto-login-policy-controlled-by-csp) | Hesapta otomatik olarak oturum açmak için kullanılır | BT yöneticileri | 20348,1405 |
| [Sertifika Yöneticisi için PFX dosya desteği](#pfx-file-support-for-certificate-manager) | Ayarlar kullanıcı arabirimi aracılığıyla PFX sertifikaları ekleyin | Son Kullanıcı | 20348,1405 |
| [HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle](#view-advanced-diagnostic-report-in-settings-on-hololens) | Cihazdaki MDM tanılama günlüklerini görüntüle | Sorun giderme | 20348,1405 |
| [Çevrimdışı tanılama bildirimleri](#offline-diagnostics-notifications) | Günlük toplama için audiogörsel geri bildirimi | Sorun giderme | 20348,1405 |
| [Yalnızca Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın](#use-only-private-store-apps-for-microsoft-store) | Mağaza uygulamasını yalnızca kuruluştan gelen uygulamaları gösterecek şekilde yapılandırma | BT Yöneticisi | 20348,1408 |

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
> - Ana işletim sistemi güncelleştirmeleri gibi bazı olaylar, otomatik oturum açma davranışını yeniden başlatmak için belirtilen kullanıcının cihazda yeniden oturum açmasını gerektirebilir. 
> - Otomatik oturum açma yalnızca MSA ve AAD kullanıcıları için desteklenir.

### <a name="pfx-file-support-for-certificate-manager"></a>Sertifika Yöneticisi için PFX dosya desteği

Windows ınsider build 20348,1405 ' de kullanıma sunulmuştur. Artık. pfx sertifikalarını kullanacak şekilde [sertifika yöneticisine](certificate-manager.md) destek ekledik. kullanıcılar **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **sertifikalarına** gezindiğinde ve **sertifikayı yükler** ' i seçtiğinizde, kullanıcı arabirimi artık. pfx sertifika dosyasını destekliyor.
Kullanıcılar, özel anahtarla, Kullanıcı deposuna veya makine deposuna. pfx sertifikasını içeri aktarabilir.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>HoloLens üzerinde Ayarlar gelişmiş tanılama raporunu görüntüle

Yönetilen cihazlar için sorun giderme sırasında, beklenen bir ilke yapılandırmasının uygulandığını onaylayan önemli bir adımdır. daha önce bu yeni özellik için, bu yeni özelliğe, **Ayarlar** hesapları aracılığıyla toplanan mdm tanılama günlüklerini dışarı aktardıktan sonra, bu yeni özelliğe cihaz yakınından veya cihazın yakınında yapılması gerekiyordu  ->    >  . 

Artık MDM Tanılaması, Edge tarayıcısı kullanılarak cihazda görüntülenebilir. MDM Tanılama raporunu daha kolay bir şekilde görüntülemek için iş veya okul sayfasına gidin ve **Gelişmiş tanılama raporunu görüntüle**' yi seçin. Bu, raporu yeni bir kenar penceresinde oluşturur ve açar.

![Ayarlar uygulamasında gelişmiş tanılama raporunu görüntüleyin.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı tanılama bildirimleri

Bu, [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)adlı mevcut bir özelliğe yönelik bir güncelleştirmedir. Daha önce, kullanıcıların tanılama toplamayı tetiklediği veya tamamladığı üzerinde hiçbir açık gösterge yoktu.
artık Windows ınsider derlemeleriyle birlikte çevrimdışı tanılama için iki tür audiogörsel geri bildirimi vardır. Koleksiyon başladığında ve tamamlandığında, her ikisi için de her ikisi için bir bildirim görüntülendi. Bunlar Kullanıcı oturum açtığında görüntülenir ve görseller vardır.

![Günlüklerin toplanması için bildirim.](./images/logcollection1.jpg)

![Günlük toplama tamamlandığında bildirim.](./images/logcollection2.jpg)
 
Kullanıcılar, bir görüntüleme erişimi olmayan için bir geri dönüş günlüğü toplama mekanizması olarak çevrimdışı tanılama kullandığından, oturum açma veya hala OOBE 'de yer alma, Günlükler toplandığında yürütülen bir ses destesi de olacaktır. Bu ses, bildirim bildirimine ek olarak çalınacaktır.

Bu yeni özellik, cihazınız güncelleştirildiğinde etkinleştirilecek ve etkinleştirilmesi veya yönetilmesi gerekmez. Bu yeni geri bildirimin görüntülenemediğini veya duyulmayacak herhangi bir olayda, çevrimdışı tanılama yine de oluşturulacaktır.

Daha yeni bir audiogörsel geri bildirimi eklenmesini umuyoruz ve daha hızlı bir şekilde Tanılama verileri toplanmanız ve sorunlarınızı giderebilmek daha kolay olacaktır.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın

RequirePrivateStoreOnly ilkesi HoloLens için etkinleştirildi. bu ilke, Microsoft Store uygulamasının yalnızca kuruluşunuz için yapılandırılmış özel mağazayı gösterecek şekilde yapılandırılmasını sağlar. Erişimi yalnızca kullanılabilir hale getirdiğiniz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) hakkında daha fazla bilgi edinin

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler:

- Bir [cihaz portalı için, kilitli dosyaları indirmede hiçbir istem olmadığı bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [Karşıya dosya yükleme ve indirme zaman aşımları Ile cihaz portalı 'nın bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- HoloLens cihazlarından raporlama uyumluluk özellikleri etrafında sorunları giderir; Insider Derlemeleriyle ilgili doğru raporlama tetiklenmesi için yeniden başlatma gerekebilir.  
- Uzaktan Yardım 'ın yerleşik sürümü, yeni bir yanıp sönuca yüklenmiş olarak güncelleştirildi.


## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlayın

> [!NOTE]
> Son zamanlarda güncelleştirmediyseniz, durumu güncelleştirmek ve en son derlemeyi almak için lütfen cihazınızı yeniden başlatın.
> - "Cihazı yeniden Başlat" ses komutu iyi şekilde çalışmaktadır. 
> - Ayarlar/Windows ınsider programı ' nda yeniden başlat düğmesini de seçebilirsiniz.
>
> Arka uçta karşılaştığınız bir hata yaşadık ve bu, izlemeye geri dönecek.

HoloLens 2 cihazında, **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows ınsider programı** ' na gidin ve **kullanmaya** başlayın ' ı seçin. Windows bir ınsider olarak kaydetmek için kullandığınız hesabı bağlayın.

Windows ınsider artık kanallara taşınıyor. **Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur. Bu, eşlemenin şöyle görünür:

![Windows Insider kanalları açıklaması](images/WindowsInsiderChannels.png)

daha fazla bilgi için bkz. Windows bloglarda [Windows ınsider kanalları tanıtma](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .
sonra, **Windows için etkin geliştirme**' yı seçin, **Dev kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.
**> şimdi yeniden başlatmak Için Onayla** ' yı seçin. cihazınız yeniden başlatıldıktan sonra, **Ayarlar > güncelleştirme & güvenlik** ' e gidin > en son derlemeyi almak için güncelleştirmeleri denetleyin.

### <a name="update-error-0x80070490-work-around"></a>Güncelleştirme hatası 0x80070490 iş-etrafında

Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli çalışmayı deneyin. Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.

#### <a name="stage-one---release-preview"></a>Aşama tek sürüm önizlemesi

1.  Ayarlar, & güvenlik Windows ınsider programını güncelleştirin, **yayın önizleme kanalını** seçin.

2.  Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**. Güncelleştirme sonrasında, ikinci aşamada devam edin.

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
