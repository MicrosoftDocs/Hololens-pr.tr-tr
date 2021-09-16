---
title: HoloLens cihazlarından tanılama bilgilerini toplayın ve kullanın
description: HoloLens cihazlarından tanılama bilgilerini nasıl toplayacağınızı, kullanacağınızı ve koruyacağınızı öğrenin.
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
ms.openlocfilehash: e977d0d42831760749bb5c6c469d2482e2ca72e7
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833531"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>HoloLens cihazlarından tanılama bilgilerini toplayın ve kullanın

HoloLens kullanıcılar ve yöneticiler HoloLens tanılama bilgilerini toplamak için dört farklı yöntem arasından seçim yapabilir:

- Geri Bildirim Hub 'ı uygulaması
- DiagnosticLog CSP
- Ayarlar uygulaması
- Çevrimdışı tanılama

> [!IMPORTANT]  
> Cihaz tanılama günlükleri, tipik işlemler sırasında kullanıcının hangi işlemler veya uygulamalar tarafından başlatıldığı hakkında bilgi gibi kişisel olarak tanımlanabilen bilgileri (PII) içerir. birden çok kullanıcı bir HoloLens cihazını paylaşıyorsa (örneğin, kullanıcılar farklı Microsoft Azure Active Directory (Azure AD) hesapları kullanarak aynı cihazda oturum açtığında) tanılama günlükleri, birden fazla kullanıcı için geçerli olan pıı bilgilerini içerebilir. Daha fazla bilgi için bkz. [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement).

Aşağıdaki tabloda farklı koleksiyon yöntemleri karşılaştırılmaktadır. Yöntem adları, tabloyu izleyen bölümlerde daha ayrıntılı bilgilere bağlantı sağlar.

|Yöntem |Önkoşullar |Veri konumları |Veri erişimi ve kullanımı |Veri saklama |
| --- | --- | --- | --- | --- |
|[Geribildirim Merkezi](#feedback-hub) |Ağ ve internet bağlantısı<br /><br />Geri Bildirim Hub 'ı uygulaması<br /><br />Microsoft bulutuna dosya yükleme izni |Microsoft bulut<br /><br />HoloLens cihaz (isteğe bağlı) |Kullanıcı Yardım ister, kullanım koşullarını kabul eder ve verileri karşıya yükler<br /><br />Microsoft çalışanları, verileri kullanım koşulları ile tutarlı olarak görüntüler |Buluttaki veriler, bir sonraki nesil Gizlilik (NGP) tarafından tanımlanan süre için tutulur. Ardından veriler otomatik olarak silinir.<br /><br />Cihazdaki veriler, **cihaz sahibi** veya **yönetici** izinlerine sahip olan bir kullanıcı tarafından dilediğiniz zaman silinebilir. |
|[Ayarlar İdir](#settings-troubleshooter) |Ayarlar uygulaması |HoloLens cihaz<br /><br />Bağlı bilgisayar (isteğe bağlı) |Kullanıcı verileri depolar ve yalnızca Kullanıcı verilere erişir (Kullanıcı, verileri başka bir kullanıcıyla paylaştığı takdirde). |Veriler, Kullanıcı tarafından silinene kadar cihazda tutulur. * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Ağ bağlantısı<br /><br />DiagnosticLog CSP 'yi destekleyen MDM ortamı |Yönetici, depolama konumlarını yapılandırır |Yönetilen ortamda, Kullanıcı verilere yönetici erişimini örtülü olarak onaylar.<br /><br />Yönetici, erişim rollerini ve izinleri yapılandırır. | Veriler Bulut depolamada tutulur ve yöneticiler bekletme ilkesini yapılandırır. |
|[Çevrimdışı tanılama](#offline-diagnostics) |Cihaz yapılandırması:<ul><li>Açık ve bilgisayara bağlı</li><li>Güç ve ses düğmeleri çalışıyor</li></ul> |HoloLens cihaz<br /><br />Bağlı bilgisayar |Kullanıcı verileri depolar ve yalnızca Kullanıcı verilere erişir (Kullanıcı, verileri başka bir kullanıcıyla paylaştığı takdirde). |Veriler, Kullanıcı tarafından silinene kadar cihazda tutulur. |

* Son Kullanıcı, başka biriyle sorumlu olan günlüklerin paylaşılmasından sorumludur. Bu dosyalar, birincil olarak müşteri hizmetleri ve destek ile iletişim kurulurken yararlı olur.  

## <a name="feedback-hub"></a>Geribildirim Merkezi

HoloLens kullanıcı, Microsoft Desteği tanılama bilgilerini göndermek için Microsoft geri bildirim merkezi masaüstü uygulamasını kullanabilir. Ayrıntılar ve tüm yönergeler için bkz. [bize geri bildirim verme](hololens-feedback.md).  

> [!NOTE]  
> **Ticari veya kurumsal kullanıcılar:** MDM, sağlama veya diğer cihaz yönetimi ile ilgili bir sorunu raporlamak için geri bildirim merkezi uygulamasını kullanıyorsanız, uygulama kategorisini **Enterprise yönetim**  >  **cihazı kategorisi** olarak değiştirin.

>[!IMPORTANT]
> Sorunları çözmek için mümkün olan en iyi verileri sağlamak üzere cihaz telemetrinizi **Isteğe bağlı** olarak ayarlamanızı kesinlikle öneririz. bu değeri, hazır olmayan deneyim (OOBE) sırasında veya **Ayarlar** uygulamasını kullanarak ayarlayabilirsiniz. bunu Ayarlar kullanarak yapmak için, > başlat ' ı seçin **Ayarlar > gizlilik > uygulama tanılama >**.

### <a name="prerequisites"></a>Önkoşullar

- Cihaz bir ağa bağlı.
- Geri Bildirim Hub 'ı uygulaması kullanıcının masaüstü bilgisayarında kullanılabilir ve Kullanıcı Microsoft bulutuna dosya yükleyebilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve bekletme

Kabul etmiş, geri bildirim hub 'ının kullanım koşullarına göre, Kullanıcı (Bu anlaşma tarafından tanımlanan) verilerin depolanmasını ve kullanımını açıkça kabul eder.

Geri Bildirim Hub 'ı, kullanıcının tanılama bilgilerini depolaması için iki konum sağlar:

- **Microsoft bulutu**. Geri Bildirim Merkezi uygulaması kullanılarak Kullanıcı tarafından karşıya yüklenen veriler, yeni nesil Gizlilik (NGP) gereksinimleriyle tutarlı olan gün sayısı için depolanır. Microsoft çalışanları, bu süre boyunca bilgilere erişmek için NGP uyumlu bir Görüntüleyici kullanabilir.

   > [!NOTE]  
   > Bu gereksinimler tüm geri bildirim hub kategorilerindeki veriler için geçerlidir.

- **HoloLens cihaz**. Geri Bildirim Hub 'ına bir rapor dosyalarken Kullanıcı, **geri bildirim verirken oluşturulan bir tanılama ve eklerin yerel kopyasını kaydet** seçeneğini belirleyebilir. kullanıcı bu seçeneği seçerse, geri bildirim merkezi HoloLens cihazında tanılama bilgilerinin bir kopyasını depolar. Bu bilgiler Kullanıcı (veya HoloLens oturum açmak için bu hesabı kullanan herkes) tarafından erişilebilir durumda kalır. Bu bilgileri silmek için bir kullanıcının cihazda **cihaz sahibi** veya **yönetici** izinleri olması gerekir. uygun izinlere sahip bir kullanıcı geri bildirim Hub 'ında oturum açabilir, **Ayarlar**  >  **tanılama günlüklerini görüntüle**' yi seçip bilgileri silebilir.

## <a name="settings-troubleshooter"></a>Ayarlar İdir

HoloLens kullanıcı, sorunları gidermek ve tanılama bilgilerini toplamak için cihazdaki **Ayarlar** uygulamayı kullanabilir. Bunu yapmak için şu adımları uygulayın:

1. Ayarlar uygulamasını açın ve **& güvenlik**  >  **sorunlarını gider** sayfasında güncelleştir ' i seçin.
1. Uygun alanı seçin ve **Başlat**' ı seçin.
1. Sorunu yeniden üretin.
1. sorunu yeniden oluşturduktan sonra Ayarlar ' a dönüp **durdur**' u seçin.

ayrıca, bir kullanıcı **Ayarlar** uygulamasından geri dönüş tanılamaları davranışını yapılandırabilir. Bu ayarı yapılandırmak için **Gizlilik-> sorun giderme** sayfasına gidin.
> [!NOTE]
> Cihaz için yapılandırılmış MDM ilkesi varsa, Kullanıcı bu davranışı geçersiz kılayamaz.

### <a name="os-update-troubleshooter"></a>İşletim sistemi güncelleştirmesi sorun giderici

derlemeler [Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve sonraki sürümler:
- Ayarlar uygulamasındaki önceki sorun gidericilere ek olarak, işletim sistemi güncelleştirmelerine yönelik yeni Ayarlar uygulamasının eklenmesiyle birlikte yeni bir sorun giderici eklenmiştir. **Ayarlar-> güncelleştirme & güvenlik > sorun giderme-> Windows Update** ' a gidin ve **başlat**' ı seçin. Bu, BT veya destek ile ilgili sorun giderme konusunda daha iyi yardımcı olması için işletim sistemi güncelleştirmeleriyle ilgili sorunları yeniden oluştururken izlemeleri toplamanıza olanak tanır.

### <a name="prerequisites"></a>Önkoşullar

- **Ayarlar** uygulama cihaza yüklenir ve kullanıcı tarafından kullanılabilir.

### <a name="data-locations-access-and-retention"></a>Veri konumları, erişim ve bekletme

Kullanıcı veri toplamayı başlattığı için Kullanıcı, tanılama bilgilerinin depolamasına örtük olarak izin verir. Yalnızca Kullanıcı veya kullanıcının verileri paylaştığı kişi veriye erişebilir.

Tanılama bilgileri cihazda depolanır. Cihaz kullanıcının bilgisayarına bağlıysa, bilgiler aşağıdaki dosyadaki bilgisayarda da bulunur:

> bu PC \\ \<*HoloLens device name*> \\ iç Depolama \\ belgeler \\ Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> bu dosya yolu ve adı ' nda, \<*HoloLens device name*> HoloLens cihazının adını temsil eder ve \<*ddmmyyhhmmss*> dosyanın oluşturulduğu tarih ve saati temsil eder.

Tanılama bilgileri, Kullanıcı tarafından silinene kadar bu konumlarda kalır.

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

Cihaz yönetilen ortamın bir parçası olduğundan, kullanıcı tanılama bilgilerine yönetim erişimini örtülü olarak onaylar.

IT yöneticisi, aşağıdaki ilkeleri de içeren veri depolama, saklama ve erişim ilkelerini yapılandırmak için DiagnosticLog CSP'yi kullanır:

- Tanılama bilgilerini depo alan bulut altyapısı.
- Tanılama bilgileri için saklama süresi.
- Tanılama bilgilerine erişimi kontrol altına alan izinler.

## <a name="offline-diagnostics"></a>Çevrimdışı tanılama

Cihazın Geri Bildirim Merkezi veya Ayarlar Sorun Gidericisi aracılığıyla tanılama toplayamayabilecek durumlarda tanılamaları el ile toplayabilirsiniz. Bunun gerekli olduğu senaryolardan biri, cihazın Wi-Fi veya yukarıda belirtilen diğer yöntemlere erişe erişiminizin bulunamaz olduğu durumdur. Tanılama, microsoft destek mühendisinin sorunları yalıtmanıza yardımcı olan kilitlenme dökümlerini ve günlüklerini cihazdan toplar.

Bu, cihaz USB kablosuyla Dosya Gezgini bilgisayara bağlanarak cihazda ortaya çıktıktan sonra çalışır.

> [!NOTE]
> Çevrimdışı Tanılama oluşturma ve yönetim, işletim sistemi sürümünüze bağlı olarak farklı şekilde denetlenmektedir. Daha önce telemetri ayarı tarafından denetlendi, ancak artık doğrudan MDM ilkesi aracılığıyla denetlendi. Ayar veya MDM ilkesi aracılığıyla devre dışı bırakılırsa, tanılama günlükleri bu mekanizma kullanılarak topılamaz.

[Holographic sürüm 20H2 Windows den önceki davranış:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Çevrimdışı tanılama yalnızca kullanıcı OOBE'den geçiyor veya [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) ilke değeri Tam olarak ayarlanmış olduğunda etkinleştirilir (Temel, OOBE'de varsayılan HoloLens). 
- Çevrimdışı tanılamayı devre dışı bırakmak için App **Ayarlar Gizlilik > sayfasına** gidin ve Tanılama Verisinde **Temel'i** **seçin.** Çevrimdışı tanılamanın telemetri ayarına bağlı olduğu derlemelerde, yalnızca herhangi bir günlüğün toplanmış olup olmadığını etkiler. Hangi dosyaların toplanmış olduğunu etkilemez.
- Cihaz kilitliyse günlükler görünmez.

[Holographic, Windows 20H2](hololens-release-notes.md#windows-holographic-version-20h2) ve daha sonra derlemelerde:
- Geri Dönüş Tanılama etkinleştirildiğinde, [mixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics) ayarına karşılık gelen MDM ilkesi tarafından denetlenecek
- Cihaz kilitliyse günlükler görünmez.

Daha fazla bilgi edinmek için bu videoyu izleyin.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Tanılamaları toplamak için şu adımları izleyin:

1.  Bağlan USB kablosuyla bilgisayarınıza bağlayın.

2.  Bilgisayarınızda Dosya Gezgini 'Bu Bilgisayar **\<hololens-device> \İç** Ağ' Depolama.

3.  İç **Depolama** klasörü göster yoksa, cihaz kullanıcının oturum açmasını bekler. POWER düğmesini 10 saniye boyunca basılı tutarak cihazda oturum açın veya güç döngüsü açın.

4.  **Power + Volume Down düğmelerine basın ve hemen** bırakın.

5.  Cihazın zip arşivlerini hazırlaması için bir dakika bekleyin. (Cihaz zip arşivlerini üretirken HololensDiagnostics.temp adlı geçici bir dosya görünür hale gelir. Bu dosyaya erişme veya dosyayı kaydetme. İşlem tamam olduğunda zip arşivleri ile değiştirilir.)

6.  Dosya gezginini yenileyin ve **'\Documents' klasörüne** gidin.

7.  Tanılama ZIP dosyalarını kopyalayın ve Microsoft destek ekibiyle paylaşın.

    > [!NOTE]
    > Tanılama ZIP dosyalarının bazıları PII içerebilir.
