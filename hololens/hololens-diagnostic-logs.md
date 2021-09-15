---
title: Cihazlardan tanılama bilgilerini toplama HoloLens kullanma
description: Cihazlardan tanılama bilgilerini toplamayı, kullanmayı ve HoloLens öğrenin.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2cbf3005293f4fde91b22f3ff87edc6041e53336
ms.sourcegitcommit: 16897df83c309acecf04e2bcfea310891cb6681b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2021
ms.locfileid: "127817285"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Cihazlardan tanılama bilgilerini toplama HoloLens kullanma

HoloLens kullanıcılar ve yöneticiler aşağıdaki yöntemlerden tanılama bilgilerini toplamak için dört farklı yöntem arasından HoloLens:

- Geri Bildirim Merkezi uygulama
- DiagnosticLog CSP
- Ayarlar uygulama
- Çevrimdışı Tanılama

> [!IMPORTANT]  
> Cihaz tanılama günlükleri, kullanıcının tipik işlemler sırasında başladığı işlemler veya uygulamalar gibi kişisel bilgileri (PII) içerir. Birden çok kullanıcı bir HoloLens cihazı paylaştığında (örneğin, kullanıcılar farklı Microsoft Azure Active Directory (Azure AD) hesapları kullanarak aynı cihazda oturum açtığında), tanılama günlükleri birden çok kullanıcı için geçerli olan PII bilgilerini içerebilir. Daha fazla bilgi için [bkz. Microsoft Gizlilik bildirimi.](https://privacy.microsoft.com/privacystatement)

Aşağıdaki tabloda farklı koleksiyon yöntemleri karşılaştırıldı. Yöntem adları, tabloyu takip alan bölümlerde daha ayrıntılı bilgilere bağlantı sağlar.

|Yöntem |Önkoşullar |Veri konumları |Veri erişimi ve kullanımı |Veri saklama |
| --- | --- | --- | --- | --- |
|[Geri Bildirim Merkezi](#feedback-hub) |Ağ ve İnternet bağlantısı<br /><br />Geri Bildirim Merkezi uygulama<br /><br />Microsoft bulutuna dosya yükleme izni |Microsoft bulutu<br /><br />HoloLens cihazı (isteğe bağlı) |Kullanıcı yardım talep eder, kullanım koşullarını kabul eder ve verileri karşıya yükler<br /><br />Microsoft çalışanları, verileri kullanım koşullarıyla tutarlı olarak görünümündedir |Buluttaki veriler, Yeni Nesil Gizlilik (NGP) tarafından tanımlanan süre boyunca korunur. Ardından veriler otomatik olarak silinir.<br /><br />Cihaz verileri, Cihaz sahibi veya Yönetici izinleri olan bir kullanıcı **tarafından herhangi bir zamanda** **silinebilir.** |
|[Ayarlar Sorun giderici](#settings-troubleshooter) |Ayarlar uygulama |HoloLens cihazı<br /><br />Bağlı bilgisayar (isteğe bağlı) |Kullanıcı verileri depolar ve yalnızca kullanıcı verilere erişer (kullanıcı verileri özellikle başka bir kullanıcıyla paylaştığı sürece). |Veriler kullanıcı silene kadar cihazda korunur.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Ağ bağlantısı<br /><br />DiagnosticLog CSP'yi destekleyen MDM ortamı |Yönetici depolama konumlarını yapılandırıyor |Yönetilen ortamda, kullanıcı verilere yönetici erişimini örtülü olarak onaylar.<br /><br />Yönetici, erişim rollerini ve izinlerini yapılandırıyor. | Veriler bulut depolamada korunur ve Yönetici saklama ilkesi yapılandırıyor. |
|[Çevrimdışı tanılama](#offline-diagnostics) |Cihaz yapılandırması:<ul><li>Açık ve bilgisayara bağlı</li><li>Güç ve Ses düğmeleri çalışıyor</li></ul> |HoloLens cihazı<br /><br />Bağlı bilgisayar |Kullanıcı verileri depolar ve yalnızca kullanıcı verilere erişer (kullanıcı verileri özellikle başka bir kullanıcıyla paylaştığı sürece). |Veriler kullanıcı silene kadar cihazda korunur. |

* Son kullanıcı, günlükleri başka biriyle sorumlu bir şekilde paylaşmakla sorumludur. Bu dosyalar öncelikle müşteri hizmetleri ve destek ile iletişim kurmada yararlıdır.  

## <a name="feedback-hub"></a>Geri Bildirim Merkezi

Bir HoloLens, microsoft Geri Bildirim Merkezi masaüstü uygulamasını kullanarak Microsoft Desteği. Ayrıntılar ve tam yönergeler için bkz. [Bize geri bildirim gönderin.](hololens-feedback.md)  

> [!NOTE]  
> **Ticari veya kurumsal kullanıcılar:** Geri Bildirim Merkezi uygulamasını kullanarak MDM, sağlama veya diğer cihaz yönetimi yönleriyle ilgili bir sorun bildirecek olursanız, uygulama kategorisini Enterprise Yönetim Cihazı **kategorisi olarak**  >  **değiştirebilirsiniz.**

>[!IMPORTANT]
> Sorunları düzeltmek için mümkün olan en iyi verileri sağlamak için, cihaz telemetrinizi İsteğe Bağlı olarak ayarlamanızı **kesinlikle öneririz.** Bu değeri İlk İlk Deneyim (OOBE) sırasında veya uygulamanın  ilk Ayarlar ayarlayabilirsiniz. Bu seçeneği kullanarak bunu yapmak Ayarlar, Uygulama **Tanılama > Ayarlar > >'> Ayarlar > Gizlilik >'ı seçin.**

### <a name="prerequisites"></a>Önkoşullar

- Cihaz bir ağa bağlı.
- Geri Bildirim Merkezi uygulaması kullanıcının masaüstü bilgisayarına kullanılabilir ve kullanıcı microsoft bulutuna dosya yükleyebilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve saklama

Kullanıcı, Geri Bildirim Merkezi kullanım koşullarını kabul eder ve verilerin depolanmasına ve kullanımına (bu sözleşme tarafından tanımlandığı şekilde) açıkça onaylar.

Bu Geri Bildirim Merkezi, kullanıcının tanılama bilgilerini depolaması için iki yer sağlar:

- **Microsoft bulutu.** Geri Bildirim Merkezi uygulaması kullanılarak kullanıcının karşıya yükleylandığı veriler, Yeni Nesil Gizlilik (NGP) gereksinimleriyle tutarlı olan gün sayısı için depolanır. Microsoft çalışanları bu süre boyunca bilgilere erişmek için NGP uyumlu bir görüntüleyici kullanabilir.

   > [!NOTE]  
   > Bu gereksinimler tüm veri kategorilerine Geri Bildirim Merkezi geçerlidir.

- **HoloLens cihazı.** Bir raporu Geri Bildirim Merkezi kullanıcı, geri bildirim sağlarken oluşturulan tanılama ve eklerin yerel kopyasını **kaydet'i seçin.** Kullanıcı bu seçeneği seçerse, Geri Bildirim Merkezi tanılama bilgisinin bir kopyasını HoloLens depolar. Bu bilgiler, kullanıcı (veya bu hesabı kullanan herkes) tarafından erişime açık olmaya devam HoloLens. Bu bilgileri silmek için kullanıcının cihazda Cihaz sahibi **veya** **Yönetici izinleri** olması gerekir. Uygun izinlere sahip bir kullanıcı, oturum Geri Bildirim Merkezi, Tanılama **Ayarlar**  >  **görüntüle'yi seçin** ve bilgileri silebilir.

## <a name="settings-troubleshooter"></a>Ayarlar Sorun giderici

Bir HoloLens kullanıcı, sorunları **gidermek Ayarlar** tanılama bilgilerini toplamak için cihazda Ayarlar uygulamasını kullanabilir. Bunu yapmak için şu adımları uygulayın:

1. Ayarlar'yi açın ve & **Güvenlik Sorunlarını Giderme sayfasını**  >  **güncelleştir'i** seçin.
1. Uygun alanı seçin ve Başlat'ı **seçin.**
1. Sorunu yeniden üretin.
1. Sorunu yeniden üretdikten sonra yeniden Ayarlar durdur'a **seçin.**

Bir kullanıcı, geri dönüş tanılama davranışını uygulamanın Ayarlar **yapılandırabilirsiniz.** Bu ayarı **yapılandırmak > Gizlilik ->** Sorun Giderme sayfasına gidin.
> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, kullanıcı bu davranışı geçersiz k aşağıdaki gibi davranamayacaktır.

### <a name="os-update-troubleshooter"></a>Işletim Sistemi Güncelleştirme Sorun Gidericisi
[Holographic Windows sürüm 21H1 ve daha sonra](hololens-release-notes.md#windows-holographic-version-21h1) derlemelerde:
- Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmeleri için yeni Ayarlar eklenmiştir. **-Ayarlar -> Update & Security -> -> Windows Update'e gidin** ve Başlat'ı **seçin.** Bu sayede, IŞLETIM sistemi güncelleştirmeleriyle sorunlarınızı yeniden üretirken, IT veya destekle ilgili sorun giderme konusunda daha iyi yardımcı olmak için izlemeleri toplamanıza olanak sağlar.

### <a name="prerequisites"></a>Önkoşullar

- Ayarlar  uygulaması cihaza yüklenir ve kullanıcı tarafından kullanılabilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve saklama

Kullanıcı veri toplamayı başladığından, kullanıcı tanılama bilgilerini depolamaya örtülü olarak onaylar. Verilere yalnızca kullanıcı veya kullanıcının verileri paylaştığı herkes erişebilirsiniz.

Tanılama bilgileri cihazda depolanır. Cihaz kullanıcının bilgisayarına bağlı ise, bilgiler aşağıdaki dosyada da bilgisayarda yer almaktadır:

> Bu PC \\ \<*HoloLens device name*> \\ İç Depolama Belgeleri \\ İzleme \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Bu dosya yolunda ve adda, HoloLens ve dosyanın oluşturulma tarihini ve \<*HoloLens device name*> \<*ddmmyyhhmmss*> saati temsil eder.

Tanılama bilgileri, kullanıcı silene kadar bu konumlarda kalır.

### <a name="view-diagnostic-report"></a>Tanılama raporunu görüntüle

HoloLens 2 ' de MDM tanılamayı görüntülemek için, WiFi simgenizi seçin, sonra **Ayarlar**  ->  **hesaplara**  >  **erişim iş veya okul** ' ye gidin ve **yönetim günlüklerinizi dışa aktar**' ı seçin. HoloLens günlük dosyalarını hesabınıza gönderir ve konumlarını masaüstü bilgisayarınızda görüntüler.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

mobil cihaz yönetimi (MDM) ortamında, bt yöneticisi, kayıtlı HoloLens cihazlarda tanılama ayarlarını yapılandırmak için [diagnosticlog yapılandırma hizmeti sağlayıcısını (CSP)](/windows/client-management/mdm/diagnosticlog-csp) kullanabilir. BT Yöneticisi bu ayarları kayıtlı cihazlardan Günlükler toplayacak şekilde yapılandırabilir.

Daha fazla bilgi:
- [Windows cihazdan tanılama toplama](/mem/intune/remote-actions/collect-diagnostics)
- [ıntune genel önizleme-Windows 10 cihaz tanılaması](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Önkoşullar

- Cihaz bir ağa bağlı.
- Cihaz, DiagnosticLog CSP 'yi destekleyen bir MDM ortamına kaydedilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve bekletme

Cihaz yönetilen ortamın bir parçası olduğundan, Kullanıcı tanılama bilgilerine yönetici erişimini örtülü olarak onaylar.

BT Yöneticisi, aşağıdakileri yöneten ilkeler de dahil olmak üzere veri depolama, bekletme ve erişim ilkelerini yapılandırmak için DiagnosticLog CSP 'yi kullanır:

- Tanılama bilgilerini depolayan bulut altyapısı.
- Tanılama bilgileri için bekletme süresi.
- Tanılama bilgilerine erişimi denetleyen izinler.

## <a name="offline-diagnostics"></a>Çevrimdışı tanılama
cihazın geri bildirim merkezi veya Ayarlar sorun giderici aracılığıyla tanılama toplayamadığı durumlarda tanılamayı el ile toplayabilirsiniz. Bunun gerekli olduğu bir senaryo, cihazın Wi-Fi bağlanamadır veya yukarıda bahsedilen diğer yöntemlere erişemezsiniz. Tanılama, Microsoft destek mühendisinin sorunları yalıtmasına yardımcı olan kilitlenme dökümünü ve günlüklerini cihazdan toplar.

Bu, cihazın bir USB kablosu aracılığıyla bir BILGISAYARA bağlandıktan sonra Dosya Gezgini 'nde gösterdiği zaman çalışır.

> [!NOTE]
> Çevrimdışı tanılama oluşturma ve Yönetimi işletim sistemi sürümünüze bağlı olarak farklı şekilde denetlenir. Daha önce telemetri ayarı tarafından denetlenmişti, ancak artık MDM ilkesi aracılığıyla doğrudan denetleniyor. Ya ayar ya da MDM ilkesi aracılığıyla devre dışı bırakılmışsa, bu mekanizma kullanılarak tanılama günlükleri toplanamaz.

[Windows Holographic, sürüm 20h2 '](hololens-release-notes.md#windows-holographic-version-20h2)den önceki davranış:
 - Çevrimdışı tanılama yalnızca Kullanıcı OOBE veya [System\allowtelemetri](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) Ilkesi değeri Full olarak ayarlandığında etkinleştirilir (temel, Hololens varsayılan değeridir). 
- çevrimdışı tanılamayı devre dışı bırakmak için **Ayarlar uygulama > gizlilik** sayfasına gidin ve **tanılama verileri**' nde **temel** ' yı seçin. Çevrimdışı tanılama 'nın telemetri ayarına bağlı olduğu derlemeler üzerinde yalnızca herhangi bir günlüklerin toplanıp toplanmadığını etkiler. Hangi dosyaların toplandığını etkilemez.
- Cihaz kilitliyse Günlükler görünmez.

derlemeler [Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) ve sonraki sürümler:
- Geri dönüş tanılaması etkin olduğunda, karşılık gelen [Mixedreality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) ayarı ile belırlı bir MDM ilkesi tarafından kontrol edilir
- Cihaz kilitliyse Günlükler görünmez.

Daha fazla bilgi edinmek için bu videoyu izleyin.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Tanılamayı toplamak için aşağıdaki adımları izleyin:

1.  cihazı USB kablosuyla bilgisayarınıza Bağlan.

2.  bilgisayarınızda dosya gezgini ' nde, **' bu bilgisayar \<hololens-device> \ iç Depolama '** bölümüne gidin.

3.  **dahili Depolama** klasörü görünmüyorsa, cihaz bir kullanıcının oturum açmasını bekliyor. GÜÇ düğmesini 10 saniye boyunca tutarak oturum açın veya güç döngüsünü yapın.

4.  **Power + Volume aşağı** düğmelerini birlikte basılı tutarak hemen serbest bırakın.

5.  Cihazın ZIP arşivlerini hazırlaması için bir dakika bekleyin. (Cihaz ZIP arşivlerini oluştururken HololensDiagnostics. TEMP adlı geçici bir dosya görünür hale gelebilir. Bu dosyaya erişme veya dosyayı kaydetme. İşlem tamamlandığında, bu, ZIP arşivlerine göre değişir.)

6.  Dosya gezginini yenileyin ve **' \Documents '** klasörüne gidin.

7.  Tanılama ZIP dosyalarını kopyalayın ve Microsoft destek ekibi ile paylaşabilirsiniz.

    > [!NOTE]
    > Tanılama ZIP dosyalarından bazıları PII içerebilir.
