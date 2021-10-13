---
title: Cihazlardan tanılama bilgilerini toplama HoloLens kullanma
description: Cihazlardan tanılama bilgilerini toplamayı, kullanmayı ve HoloLens öğrenin.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 9/12/2021
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
ms.openlocfilehash: 4f62a70430d78087157b3adcdf76af53183db708
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924405"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Cihazlardan tanılama bilgilerini toplama HoloLens kullanma

HoloLens kullanıcılar ve yöneticiler, aşağıdaki yöntemlerden tanılama bilgilerini toplamak için dört farklı yöntem arasından HoloLens:

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
> **Ticari veya kurumsal kullanıcılar:** Geri Bildirim Merkezi uygulamasını MDM, sağlama veya diğer cihaz yönetimi yönleriyle ilgili bir sorunu rapor etmek için kullanırsanız, uygulama kategorisini Yönetim **Cihazı Enterprise**  >  **olarak değiştirebilirsiniz.**

>[!IMPORTANT]
> Sorunları düzeltmek için mümkün olan en iyi verileri sağlamak için, cihaz telemetrinizi İsteğe Bağlı olarak ayarlamanızı **kesinlikle öneririz.** Bu değeri İlk İlk Deneyim (OOBE) sırasında veya Ayarlar **ayarlayabilirsiniz.** Bu seçeneği kullanarak bunu yapmak Ayarlar, > Ayarlar > **Gizlilik > Uygulama Tanılaması'>'> seçin.**

### <a name="prerequisites"></a>Önkoşullar

- Cihaz bir ağa bağlı.
- Geri Bildirim Merkezi uygulaması kullanıcının masaüstü bilgisayarına kullanılabilir ve kullanıcı microsoft bulutuna dosya yükleyebilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve saklama

Kullanıcı, Geri Bildirim Merkezi kullanım koşullarını kabul eder ve verilerin depolanmasına ve kullanımına (bu sözleşme tarafından tanımlandığı şekilde) açıkça onaylar.

Bu Geri Bildirim Merkezi, kullanıcının tanılama bilgilerini depolaması için iki yer sağlar:

- **Microsoft bulutu.** Geri Bildirim Merkezi uygulaması kullanılarak kullanıcının karşıya yükleylandığı veriler, Yeni Nesil Gizlilik (NGP) gereksinimleriyle tutarlı olan gün sayısı için depolanır. Microsoft çalışanları bu süre boyunca bilgilere erişmek için NGP uyumlu bir görüntüleyici kullanabilir.

   > [!NOTE]  
   > Bu gereksinimler tüm veri kategorilerine Geri Bildirim Merkezi geçerlidir.

- **HoloLens cihazı.** Bir raporu Geri Bildirim Merkezi kullanıcı, geri bildirim sağlarken oluşturulan tanılama ve eklerin yerel kopyasını **kaydet'i seçin.** Kullanıcı bu seçeneği seçerse, Geri Bildirim Merkezi tanılama bilgisinin bir kopyasını HoloLens depolar. Bu bilgiler, kullanıcı (veya bu hesabı kullanan herkes) tarafından erişilebilen bir HoloLens. Bu bilgileri silmek için kullanıcının cihazda Cihaz sahibi **veya** **Yönetici izinleri** olması gerekir. Uygun izinlere sahip bir kullanıcı, oturum açma Geri Bildirim Merkezi, Tanılama **Ayarlar**  >  **görüntüle'yi seçin** ve bilgileri silebilir.

## <a name="settings-troubleshooter"></a>Ayarlar Sorun giderici

Bir HoloLens kullanıcı, sorunları **gidermek Ayarlar** tanılama bilgilerini toplamak için cihazda Ayarlar uygulamasını kullanabilir. Bunu yapmak için şu adımları uygulayın:

1. Ayarlar uygulamasını açın ve Güncelleştirme ve & **Sorun Giderme**  >  **sayfasını** seçin.
1. Uygun alanı seçin ve Başlat'ı **seçin.**
1. Sorunu yeniden üretin.
1. Sorunu yeniden üretdikten sonra yeniden Ayarlar durdur'a **seçin.**

Bir kullanıcı, geri dönüş tanılama davranışını uygulamanın Ayarlar **yapılandırabilirsiniz.** Bu ayarı **yapılandırmak > Gizlilik ->** Sorun Giderme sayfasına gidin.
> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, kullanıcı bu davranışı geçersiz k aşağıdaki gibi davranamayacaktır.

### <a name="os-update-troubleshooter"></a>Işletim Sistemi Güncelleştirme Sorun Gidericisi

[Holographic Windows sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha sonra yapılan derlemelerde:
- Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmeleri için yeni Ayarlar eklenmiştir. **-Ayarlar Update > Security -& -> -> Windows Update'e** gidin ve Başlat'ı **seçin.** Bu sayede, sorunlarınızı işletim sistemi güncelleştirmeleriyle yeniden üretirken, IT veya destekle ilgili sorunları gidermeye daha iyi yardımcı olmak için izlemeleri toplayabilirsiniz.

### <a name="prerequisites"></a>Önkoşullar

- Ayarlar  uygulaması cihaza yüklenir ve kullanıcı tarafından kullanılabilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve saklama

Kullanıcı veri toplamayı başladığından, kullanıcı tanılama bilgilerini depolamaya örtülü olarak onaylar. Verilere yalnızca kullanıcı veya kullanıcının verileri paylaştığı herkes erişebilirsiniz.

Tanılama bilgileri cihazda depolanır. Cihaz kullanıcının bilgisayarına bağlı ise, bilgiler aşağıdaki dosyada da bilgisayarda yer almaktadır:

> Bu PC \\ \<*HoloLens device name*> \\ İç Depolama Belgeleri \\ İzleme \\ \<*ddmmyyhhmmss*> .etl

> [!NOTE]  
> Bu dosya yolunda ve adda, HoloLens cihazın adını ve \<*HoloLens device name*> \<*ddmmyyhhmmss*> dosyanın oluşturulma tarihini ve saati temsil eder.

Tanılama bilgileri, kullanıcı silene kadar bu konumlarda kalır.

### <a name="view-diagnostic-report"></a>Tanılama raporunu görüntüleme

HoloLens 2'de MDM Tanılama'yı görüntülemek için WiFi simgenizi seçin, sonra Ayarlar Hesapları İş veya okula erişim'e gidin ve Yönetim günlüklerinizi dışarı  ->    >   **aktar'ı seçin.** HoloLens günlük dosyalarını hesabınıza gönderir ve konumlarını masaüstü bilgisayarınızda görüntüler.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

Mobil Cihaz Yönetimi (MDM) ortamında, IT yöneticisi DiagnosticLog yapılandırma hizmet [sağlayıcısını (CSP)](/windows/client-management/mdm/diagnosticlog-csp) kullanarak kayıtlı HoloLens yapılandırabilirsiniz. IT yöneticisi, kayıtlı cihazlardan günlükleri toplamak için bu ayarları yapılandırabilirsiniz.

Daha fazla bilgi:
- [Bir Windows cihazdan tanılama toplama](/mem/intune/remote-actions/collect-diagnostics)
- [Intune Genel Önizleme - Windows 10 Cihaz tanılaması](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Önkoşullar

- Cihaz bir ağa bağlı.
- Cihaz, DiagnosticLog CSP'yi destekleyen bir MDM ortamına kayıtlıdır.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve saklama

Cihaz yönetilen ortamın bir parçası olduğundan, kullanıcı tanılama bilgilerine yönetici erişimini örtülü olarak onaylar.

IT yöneticisi, aşağıdaki ilkeleri de içeren veri depolama, saklama ve erişim ilkelerini yapılandırmak için DiagnosticLog CSP'yi kullanır:

- Tanılama bilgilerini depolar bulut altyapısı.
- Tanılama bilgileri için saklama süresi.
- Tanılama bilgilerine erişimi kontrol altına alan izinler.

## <a name="offline-diagnostics"></a>Çevrimdışı tanılama

Cihazın Geri Bildirim Merkezi veya Ayarlar Sorun Gidericisi aracılığıyla tanılamaları toplayamayabilecek durumlarda tanılamaları el ile toplayabilirsiniz. Bunun gerekli olduğu senaryolardan biri, cihazın Wi-Fi veya yukarıda bahsedilen diğer yöntemlere erişe erişiminizin bulunamaz olduğu durumdur. Tanılama, microsoft destek mühendisinin sorunları yalıtmanıza yardımcı olan kilitlenme dökümlerini ve günlüklerini cihazdan toplar.

Bu, cihaz USB kablosuyla Dosya Gezgini bilgisayara bağlanarak cihazda ortaya çıktıktan sonra çalışır.

> [!NOTE]
> Çevrimdışı Tanılama oluşturma ve yönetim, işletim sistemi sürümünüze bağlı olarak farklı şekilde denetlenmektedir. Daha önce telemetri ayarı tarafından denetlendi, ancak artık doğrudan MDM ilkesi aracılığıyla denetlendi. Ayar veya MDM ilkesi aracılığıyla devre dışı bırakılırsa, tanılama günlükleri bu mekanizma kullanılarak topılamaz.

[Windows Holographic sürüm 20H2'den önceki davranış:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Çevrimdışı tanılama yalnızca kullanıcı OOBE'den geçiyor veya [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ilke değeri Tam olarak ayarlanmış olduğunda etkinleştirilir (Temel, OOBE'de varsayılan HoloLens). 
- Çevrimdışı tanılamayı devre dışı bırakmak için App **Ayarlar Gizlilik > sayfasına** gidin ve Tanılama Verisinde **Temel'i** **seçin.** Çevrimdışı tanılamanın telemetri ayarına bağlı olduğu derlemelerde, yalnızca herhangi bir günlüğün toplanmış olup olmadığını etkiler. Hangi dosyaların toplanmış olduğunu etkilemez.
- Cihaz kilitliyse günlükler görünmez.

[Holographic, Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ve daha sonra derlemelerde:
- Geri Dönüş Tanılama etkinleştirildiğinde, [mixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) ayarına karşılık gelen belirli MDM ilkesi tarafından denetlenecek
- Cihaz kilitliyse günlükler görünmez.

Daha fazla bilgi edinmek için bu videoyu izleyin.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Tanılamaları toplamak için şu adımları izleyin:

1.  Bağlan USB kablosuyla bilgisayarınıza bağlayın.

2.  Bilgisayarınızda Dosya Gezgini 'Bu Bilgisayar \İç Ağ' **\<hololens-device> Depolama gidin.**

3.  İç **Depolama** klasörü göster yoksa, cihaz kullanıcının oturum açmasını bekler. POWER düğmesini 10 saniye boyunca basılı tutarak cihazda oturum açın veya güç döngüsü açın.

4.  **Power + Volume Down düğmelerine basın ve hemen** bırakın.

5.  Cihazın zip arşivlerini hazırlaması için bir dakika bekleyin. (Cihaz zip arşivlerini üretirken HololensDiagnostics.temp adlı geçici bir dosya görünür hale gelir. Bu dosyaya erişin veya dosyayı kaydetmeyin. İşlem tamam olduğunda zip arşivleri ile değiştirilir.)

6.  Dosya gezginini yenileyin ve **'\Documents' klasörüne** gidin.

7.  Tanılama ZIP dosyalarını kopyalayın ve Microsoft destek ekibiyle paylaşın.

> [!NOTE]
> Tanılama ZIP dosyalarının bazıları PII içerebilir.

### <a name="offline-diagnostics-notifications"></a>Çevrimdışı Tanılama bildirimleri

- [Windows Holographic, sürüm 21H2'de tanıtıldı.](hololens-release-notes.md#windows-holographic-version-21h2)

Bu, Çevrimdışı Tanılama adlı mevcut bir [özelliğin güncelleştirmesidir.](hololens-diagnostic-logs.md#offline-diagnostics) Daha önce, kullanıcılara tanılama toplamayı tetikle olduklarının veya tamamlandıktan sonra net bir gösterge yoktu.
Artık Insider Windows eklenmiştir, Çevrimdışı Tanılama için iki sesli ve görsel geri bildirim formu vardır. birincisi, koleksiyon başlatıldığında ve tamamlandığında her ikisi için de görüntülenen bildirimleri belirtir. Bunlar, kullanıcı oturum açtığında ve görselleri olduğunda görüntülenir.

![Günlükleri toplamak için yapılan konuşma.](./images/logcollection1.jpg)

![Günlük toplama işlemi tamamlandığında yapılan konuşma.](./images/logcollection2.jpg)

Kullanıcılar genellikle bir görüntüye erişimi olmayan, oturum açamaz veya hala OOBE'de olan bir geri dönüş günlüğü toplama mekanizması olarak Çevrimdışı Tanılamayı kullanır. Günlükler toplanarak sesli bir ipucu da gösterilir. Bu ses, bildirime ek olarak çalınacak.

Bu yeni özellik, cihazınız etkinleştirilmişse ve etkinleştirilmesi veya yönetilma ihtiyacı yoksa etkinleştirilir. Bu yeni geri bildirimin görüntülenemiyor veya duyulamaz olması durumunda Çevrimdışı Tanılama yine de oluşturulur.

Bu yeni görsel geri bildirim eklemesi ile tanılama verilerini toplamanın ve sorunlarınızı daha hızlı bir şekilde gidermenin daha kolay olduğunu umuyoruz.

### <a name="low-storage-log-collection-improvements"></a>Düşük depolama günlüğü toplama geliştirmeleri

- [Windows Holographic, sürüm 21H2'de tanıtıldı.](hololens-release-notes.md#windows-holographic-version-21h2)

Tanılama günlükleri toplanmışken cihazın disk alanı düşük gibi görünen senaryolarda,StorageDiagnostics.zipadlı **ek** bir rapor oluşturulur. Düşük depolama eşiği, depolama alanı algısı Windows [belirlenir.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

## <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Raporlarda gelişmiş tanılama Ayarlar görüntüleme HoloLens

- [Windows Holographic, sürüm 21H2'de tanıtıldı.](hololens-release-notes.md#windows-holographic-version-21h2)

Davranış sorunlarını giderirken yönetilen cihazlar için, beklenen bir ilke yapılandırmasının uygulandığını onaylamak önemli bir adımdır. Bu yeni özellikle daha önce, bu özelliğin, Ayarlar Hesapları Erişim veya okul aracılığıyla toplanan MDM tanılama günlükleri dışarı aktarıldıktan sonra MDM aracılığıyla veya cihaza yakın bir cihazdan yapılması ve Yönetim günlüklerinizi dışarı aktar'ı seçerek yakındaki bir pc'de  ->    >  görüntüleyebilirsiniz. 

Artık MDM Tanılamaları, Edge tarayıcısı kullanılarak cihazda görüntüleyebilirsiniz. MDM Tanılama raporunu daha kolay görüntülemek için İş veya okula erişim sayfasına gidin ve Gelişmiş tanılama raporunu **görüntüle'yi seçin.** Bu, raporu yeni bir Edge penceresinde oluşturulur ve açar.

![Gelişmiş tanılama raporunu uygulama Ayarlar görüntüleme.](./images/view-advanced-diagnostic-report.jpg)
