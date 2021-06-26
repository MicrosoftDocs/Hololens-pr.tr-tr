---
title: HoloLens 2 için Windows Autopilot
description: HoloLens 2 cihazlarından Autopilot'u ayarlamayı, yapılandırmayı ve sorunlarını gidermeyi öğrenin.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Otopilot
manager: jarrettr
ms.openlocfilehash: 10a577cf77a5c6faf0e7e07fa2fd5ad8603ec5ae
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923661"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

Windows Holographic sürüm 2004'den itibaren HoloLens 2, Microsoft Intune ile Windows Autopilot Kendi Kendine Dağıtım Modunu destekler (3. taraf MDM'ler desteklanmaz). [](https://docs.microsoft.com/mem/autopilot/self-deploying) Yöneticiler Microsoft Endpoint Manager'da ilk kullanım deneyimini (OOBE) yapılandırarak son kullanıcıların çok az etkileşimle veya hiç etkileşim olmadan cihazları iş için hazırlamasını sağlar. Bu, kurulum deneyimi sırasında çalışanlardan gelen stok yönetimi ek yükünü, cihaz hazırlığı ve destek çağrılarının maliyetini azaltır. Daha fazla bilgi için [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) edinin.

Surface cihazlarında olduğu gibi, müşterilerin Bulut Çözümü Sağlayıcısı aracılığıyla Autopilot [hizmetine](https://partner.microsoft.com/cloud-solution-provider) kayıtlı cihazları almak için Microsoft Bulut Çözümü Sağlayıcısı (kurumsal bayi veya dağıtımcı) ile İş Ortağı Merkezi. Cihaz kaydına ilişkin diğer yöntemler [](https://docs.microsoft.com/mem/autopilot/add-devices) cihaz ekleme belgelerinde açıklanmıştır, ancak Microsoft'un kanal iş ortaklarından yararlanarak en etkili bitiş yolu garanti altına alınmaktadır.

> [!NOTE]
> Microsoft Endpoint Manager'de HoloLens için Autopilot yapılandırması 20.11.2020'den Endpoint Manager **Genel Önizleme'ye geçişte.** Müşterilerin artık özel önizlemeye kaydolması gerekmemektedir ve tüm kiracılar MEM yönetim merkezinde Autopilot'u kurabilecektir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başlatırsa Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme. HoloLens için Autopilot'ın Active Directory'ye katılmayı veya Hibrit Azure AD'ye katılmayı desteklemez.

1. Cihazı Microsoft Endpoint Manager'a (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulama.

1. Cihazı sağlama.

1. Oturum açma ekranı kullanıcıya gösterilir.

## <a name="configuring-autopilot-for-hololens-2"></a>HoloLens 2 için Autopilot'u yapılandırma

Ortamınızı ayarlamak için lütfen aşağıdaki adımları izleyin:

1. [HoloLens 2 Windows Autopilot için gereksinimleri gözden geçirme.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydı etkinleştirme](#2-enable-automatic-mdm-enrollment)

1. [Cihazları Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#4-create-a-device-group)

1. [Dağıtım profili oluşturun.](#5-create-a-deployment-profile)

1. [Kayıt Durumu Sayfası (ESP) yapılandırmasını doğrulayın.](#6-verify-the-esp-configuration)

1. [HoloLens cihazlarının profil durumunu doğrulayın.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. HoloLens 2 Windows Autopilot için gereksinimleri gözden geçirme

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot gereksinimleri makalesinde yer alan Windows Autopilot gözden geçirebilirsiniz:

- [Ağ gereksinimleri](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying [modu](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)makalenin " Gereksinimler " bölümünü gözden geçirebilirsiniz.** Ortamınız hem bu gereksinimleri hem de standart Windows Autopilot karşılamalıdır. Makalenin "Adım adım" ve "Doğrulama" bölümlerini gözden geçirmeye gerek yok. Bu makalenin devamlarında yer alan yordamlar HoloLens'e özgü ilgili adımları sağlar.

Cihazları kaydetme ve profilleri yapılandırma hakkında bilgi için bkz. [2. Cihazları Windows Autopilot](#3-register-devices-in-windows-autopilot) [4'e kaydetme. Bu makalede bir dağıtım](#5-create-a-deployment-profile) profili oluşturun. Autopilot kendi kendine dağıtım modu profillerini yapılandırmak ve yönetmek için, Microsoft Yönetim Merkezi'ne erişiminiz [olduğundan Endpoint Manager olun.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>HoloLens işletim sistemi gereksinimlerini gözden geçirme:

- Cihazlar Windows [Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) (derleme 19041.1103) veya sonraki sürümlere sahip olması gerekir. Cihazınızın derleme sürümünü onaylamak veya en son işletim sistemiyle yeniden flash oluşturmak için Gelişmiş Kurtarma Yardımcı [(ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) ve cihazı yeniden [flash yönergelerini kullanın.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) Eylül 2020'nin sonlarına kadar teslim edilen cihazlarda Windows Holographic sürüm 1903'ün önceden yüklü olduğunu unutmayın. Autopilot'a hazır cihazların size gönderiliyor olduğundan emin olmak için lütfen kurumsal bayinizle iletişime geçin.

- Windows Holographic sürüm 2004 yalnızca Ethernet bağlantısı üzerinden Autopilot'ı destekler. HoloLens'in, "USB-C'den Ethernet'e" bağdaştırıcısını açmadan önce **Ethernet'e bağlı olduğundan emin olun.** Cihaz önyüklemesi sırasında kullanıcı etkileşimi gerekmez. Autopilot'ın birçok HoloLens cihazına devredecek bir planınız varsa bağdaştırıcı altyapısını planlamanız önerilir. HoloLens'de desteklen olmayan ek üçüncü taraf sürücülerin yüklü olması genellikle USB Hub'lar için önerilmez.

- [Windows Holographic sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041.1128) veya sonraki sürümler, Ethernet bağdaştırıcıları kullanmaya devam ediyor olsa da Wi-Fi üzerinden Autopilot'ı destekler. Wi-Fi üzerinden bağlanan cihazlar için kullanıcının yalnızca:

     - Kuş sahnelerini inceleme
     - Dili ve yerel dili seçin
     - Göz ayarlamayı çalıştırma
     - Ağ bağlantısı kurma

- Windows Holographic sürüm 20H2, bir cihazı kiracıya kilitleyen ve yanlışlıkla veya kasıtlı sıfırlama veya silme durumunda cihazın o kiracıya bağlı kalmasını sağlayan [Tenantlockdown CSP](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)ve Autopilot'ı destekler.  

- Cihazların zaten Azure AD'ye üye olduğundan ve Intune'a (veya başka bir MDM sistemine) kayıtlı değil olduğundan emin olun. Autopilot kendi kendine dağıtım işlemi bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlenmiş olduğundan emin  olmak için hem Azure AD'de hem de Intune Portallarında Cihazlar sayfalarını kontrol edin. HoloLens'de "Hedeflenen tüm cihazları Autopilot'a dönüştür" özelliğinin şu anda desteklene olmadığını unutmayın.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Otomatik MDM Kaydı'nın etkinleştirin:

Autopilot'ın başarılı olması için otomatik MDM Kaydı'Azure portal. Bu, cihazın kullanıcı olmadan kaydolmalarını sağlar.

Veri [Azure portal](https://portal.azure.com/#home) Mobility **(MDM ve**  ->  **MAM) Azure Active Directory'yi Microsoft Intune.**  ->   Ardından **MDM kullanıcı kapsamını yapılandırarak** All (Tüm) seçeneğini seçmeniz **gerekir.**

Ayarlama hakkında daha fazla [bilgi için lütfen MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) Otomatik Kaydı'nın etkinleştirilmesi ile ilgili aşağıdaki kısa kılavuzu veya Otomatik Kayıt Hızlı başlangıç kılavuzunu gözden geçirebilirsiniz. [](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

### <a name="3-register-devices-in-windows-autopilot"></a>3. Cihazları Windows Autopilot

İlk kurulumdan önce cihazlarınızı Windows Autopilot kayıtlı olması gerekir. Cihaz kaydıyla ilgili MEM belgeleri için [bkz. Autopilot'a cihaz ekleme.](https://docs.microsoft.com/mem/autopilot/add-devices)  

HoloLens cihazlarını kaydetmenin başlıca üç yolu vardır:

 - **Kurumsal bayi, sipariş İş Ortağı Merkezi cihazları kayıt cihazına kaydedebilirsiniz.**

   > [!NOTE]  
   > Bu, Autopilot hizmetine cihaz eklemek için önerilen yoldur. [Daha fazla bilgi edinin](https://docs.microsoft.com/mem/autopilot/partner-registration).  

 - **Destek [isteğini doğrudan Microsoft'a](hololens2-autopilot-registration-support.md) gönderebilirsiniz.**
 - **Donanım karması (donanım kimliği olarak da bilinir)** alın ve cihazı MEM yönetim merkezine el ile kaydedin.

#### <a name="obtain-hardware-hash"></a>Donanım karması alma
Donanım karması almanın iki yolu vardır.
1. Destek [isteğini doğrudan Microsoft'a](hololens2-autopilot-registration-support.md) gönderebilirsiniz.
2. Bunu cihazdan edinebilirsiniz. Cihaz, donanım karması OOBE işlemi sırasında veya daha sonra bir cihaz sahibi tanılama günlüğü toplama işlemini (aşağıdaki yordamda açıklanmıştır) başlatırken bir CSV dosyasına kaydedilir. Genellikle cihaz sahibi, cihazda oturum açması gereken ilk kullanıcıdır.
     > [!WARNING]
     > 20H2'den önceki derlemelerde, OOBE'den geçtiy ve telemetri Gerekli olarak ayarlanmışsa bu yöntem aracılığıyla Autopilot için donanım karması toplayabilirsiniz. Bu yöntem aracılığıyla donanım karmanızı toplamak için Ayarlar Uygulaması aracılığıyla telemetri seçeneğini Tam olarak ayarlayın ve Gizlilik -> Tanılama'yı seçin.

    1. HoloLens 2 cihazı başlatma.

    1. Cihazda, aynı anda **Güç ve** Ses Düzeyi **Aşağı** düğmelerine basın ve ardından bunları bırakın. Cihaz tanılama günlüklerini ve donanım karması toplar ve bunları bir dizi farklı .zip depolar.

   1. Tüm ayrıntılar ve bunun nasıl önceden biçimlendirilmiş olduğu hakkında bir yönerge videosu için çevrimdışı tanılama [hakkında bilgi alın.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Cihazı bir bilgisayara bağlamak için USB-C kablosu kullanın.

    1. Bilgisayarda, Dosya Gezgini. Bu **PC İç Depolama \\ \<*HoloLens device name*> \\ \\ Belgeleri'ne** açın ve AutopilotDiagnostics.zip bulun.  

       > [!NOTE]  
       > .zip dosyası hemen kullanılamıyor olabilir. Dosya henüz hazır değilse Belgeler klasöründe bir HoloLensDiagnostics.temp dosyası görebilir. Dosya listesini güncelleştirmek için pencereyi yenileyin.
    
    1. Dosyanın içeriğini AutopilotDiagnostics.zip.

    1. Ayıklanan dosyalarda, "DeviceHash" dosya adı ön ekine sahip CSV dosyasını bulun. Bu dosyayı daha sonra erişebilirsiniz bilgisayarın bir sürücüsüne kopyalayın.  

       > [!IMPORTANT]  
       > CSV dosyasındaki veriler aşağıdaki üst bilgi ve satır biçimini kullanmıştır:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>MEM aracılığıyla cihaz kaydetme

1. [Microsoft Endpoint Manager merkezinde Cihazlar](https://endpoint.microsoft.com)Windows Windows kaydı'ni seçin ve ardından  >    >  Program'ın altında Cihazlar   >   İçeri **Windows Autopilot Deployment seçin.**

1. Cihaz **ekle Windows Autopilot altında DeviceHash** CSV dosyasını seçin, Aç'ı **ve** ardından İçeri Aktar'ı **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Donanım karması içeri aktar için İçeri Aktar komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. İçeri aktarma işlemi tamam olduktan sonra Cihazlar Windows Windows **kaydı**  >    >  **Cihazlar Eşitleme'yi**  >    >  **seçin.** Kaç cihaz eşitlenmesine bağlı olarak işlem birkaç dakika sürebilir. Kayıtlı cihazı görmek için Yenile'yi **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Cihaz grubu oluşturma

1. [Microsoft Endpoint Manager merkezinde Gruplar Yeni](https://endpoint.microsoft.com) **grup'u**  >  **seçin.**

1. Grup türü olarak **Güvenlik'i seçin** ve ardından bir grup adı ve açıklaması girin. 

1. Üyelik **türü olarak** Atanan veya Dinamik **Cihaz'ı seçin.** 

1. Aşağıdakilerden birini yapın:  

   - Önceki adımda **Üyelik türü olarak** **Atanan'ı** seçtiyebilirsiniz. Üyeler'i seçin ve ardından Autopilot cihazlarını gruba ekleyin. Henüz kayıtlı olmayan Autopilot cihazları, cihaz adı olarak cihaz seri numarası kullanılarak listelenir.
   - Bir önceki adımda **Üyelik** türü olarak **Dinamik** Cihazlar'ı seçtiyebilirsiniz.  Dinamik cihaz üyeleri'ni seçin ve gelişmiş kural alanına aşağıdakine benzer bir kod girin:
     - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazın: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune'un grup etiketi alanı, Azure AD **cihazlarında OrderID** özniteliğiyle eşler. Belirli bir grup etiketine (Azure AD cihaz OrderID) sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazmanız gerekir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Belirli bir Satın Alma Siparişi Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazın: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Bu kurallar Autopilot cihazlarına özgü öznitelikleri hedefler.
1. **Kaydet'i** ve ardından Oluştur'a **tıklayın.**

### <a name="5-create-a-deployment-profile"></a>5. Dağıtım profili oluşturma

1. [Microsoft Endpoint Manager yönetim merkezinde Cihazlar](https://endpoint.microsoft.com) Windows Windows kaydı ve  >    >    >  **dağıtım profilleri Windows Autopilot**  >    >  **HoloLens'i seçin.**
   ![Profil oluştur açılan listesinde HoloLens öğesi yer almaktadır.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından Sonraki'yi **seçin.**  
   **HoloLens** içeren bir liste görüyor gerekir. Bu seçenek yoksa Geri bildirim seçenekleriyle bize [ulaşın.](hololens2-autopilot.md#feedback-and-support-for-autopilot)

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklama ekleme](./images/hololens-ap-profile-name.png)

1. İlk **deneyim (OOBE)** sayfasında, ayarların çoğu bu değerlendirme için OOBE'yi kolaylaştıracak şekilde önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (Bölge):** OOBE için dili seçin. HoloLens 2 için desteklenen [diller listesinden bir dil seçmenizi öneririz.](hololens2-language-support.md)
   - **Klavyeyi otomatik olarak** yapılandırma: Klavyenin seçili dille eş olduğundan emin olmak için Evet'i **seçin.**
   - **Cihaz adı şablonu uygulama:** OOBE sırasında cihaz  adını otomatik olarak ayarlamak için Evet'i seçin ve Ardından Ad girin alanına şablon tümceciği ve yer tutucularını girin. Örneğin, dört basamaklı rastgele sayı için bir ön ek ve yer  `%RAND:4%` &mdash; tutucu girin.
     > [!NOTE]  
     > Cihaz adı şablonu kullanıyorsanız, OOBE işlemi cihaz adını uygulamanın ardından ve cihazı Azure AD'ye eklemeden önce cihazı bir kez daha yeniden başlatıyor. Bu yeniden başlatma, yeni adın etkili olmasına olanak sağlar.  

   > [!div class="mx-imgBorder"]
   > ![OOBE ayarlarını yapılandırma](./images/hololens-ap-profile-oobe.png)

1. Ayarları yapılandırdikten sonra, Sonraki'yi **seçin.**
1. Kapsam **etiketleri sayfasında,** isteğe bağlı olarak bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için [bkz. Dağıtılmış IT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma.](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md) Tamamlandığında, Sonraki'yi **seçin.**
1. Atamalar **sayfasında Atama** için Seçili **gruplar'ı** **seçin.**
1. **SEÇİLEN GRUPLAR** altında **+ Dahil etmek için grupları seçin'i seçin.**
1. Dahil **etmek için grupları seçin listesinde** Autopilot HoloLens cihazları için oluşturduğunuz cihaz grubunu ve ardından Sonraki'yi **seçin.**  
  
   Herhangi bir grubu dışlamak için Dışlamak istediğiniz Grupları **seç'i** seçin ve dışlamak istediğiniz grupları seçin.

   > [!div class="mx-imgBorder"]
   > ![Profile bir cihaz grubu atama.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Gözden Geçir **+ Oluştur sayfasında** ayarları gözden geçirerek Oluştur'a **seçerek** profili oluşturun.  

   > [!div class="mx-imgBorder"]
   > ![Gözden geçirme ve oluşturma](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. ESP yapılandırmasını doğrulama

Kayıt Durumu Sayfası (ESP), MDM tarafından yönetilen bir kullanıcı bir cihazda ilk kez oturum a açınca çalışan tam cihaz yapılandırma işleminin durumunu görüntüler. ESP yapılandırmanın aşağıdakine benzer olduğundan emin olun ve atamaların doğru olduğunu doğrulayın.  

> [!div class="mx-imgBorder"]
> ![ESP yapılandırması](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. HoloLens cihazlarının profil durumunu doğrulama

1. Microsoft Endpoint Manager Yönetim Merkezi'nde Cihazlar  >  **Windows Windows** kayıt  >  **Cihazları'ı**  >  **seçin.**

1. HoloLens cihazlarının listelenmiş olduğunu ve profil durumunun Atandı olduğunu **doğrulayın.**  

   > [!NOTE]  
   > Profilin cihaza atanmaları birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>hololens 2 kullanıcı deneyimi için Windows Autopilot

Yukarıdaki yönergeler tamamlandıktan sonra HoloLens 2 kullanıcılarınız HoloLens cihazlarını sağlama konusunda aşağıdaki deneyimi deneyimle karşılar:  

1. Autopilot deneyimi için İnternet erişimi gerekir. İnternet erişimi sağlamak için lütfen aşağıdaki seçeneklerden birini kullanın:

    - Cihazınızı OOBE'Wi-Fi bir ağ üzerinden bağlama ve autopilot deneyimini otomatik olarak algılamasına izin verme. Autopilot deneyimi kendi kendine tamamlayana kadar OOBE ile yalnızca bu kez etkileşim kurmanız gerekir. Varsayılan olarak HoloLens 2'nin İnternet'i algılayan Autopilot'ı algılamak için 10 saniye bekleyeceğini lütfen unutmayın. 10 saniye içinde bir otomatik pilot profili algılanmazsa OOBE EULA'yı sunacak. Bu senaryoyla karşılaşırsanız, Autopilot'ın algılanabilir olması için cihazınızı yeniden başlatın. Ayrıca, OOBE'nin Autopilot için süresiz olarak yalnızca cihazda TenantLockdown ilkesi ayarlanmışsa bekleyebilir.

    - Kablolu internet bağlantısı için "USB-C'den Ethernet'e" bağdaştırıcıları kullanarak cihazınızı Ethernet'e bağlayın ve HoloLens 2'nin otomatik olarak Autopilot deneyimini tamamlamasına olanak sağlar.

    - Kablosuz İnternet bağlantısı için cihazınızı "USB-C'den Wifi'ye" bağdaştırıcılarla bağlayın ve HoloLens 2'nin otomatik olarak Autopilot deneyimini tamamlamasına izin verir.

        > [!IMPORTANT]  
       > Autopilot için OOBE'Wi-Fi ağlarını kullanmaya çalışan cihazların [Windows Holographic sürüm 20H2'de olması gerekir.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Ethernet bağdaştırıcıları kullanan cihazlar için, İlk İlk Deneyim (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranında autopilot cihaz olarak sağ isteyip sağlama olmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı Autopilot cihazı olarak sağlamayı seçmiyorsanız, daha sonra Autopilot sağlama olarak değiştiremezsiniz. Bunun yerine, cihazı Autopilot cihaz olarak sağlama amacıyla bu yordamı baştan başlatmanız gerekir.

1. Cihazın OOBE'i otomatik olarak başlatması gerekir. OOBE ile etkileşim kurma. Bunun yerine arkanıza yaslanın ve gevşeyin! HoloLens 2'nin ağ bağlantısını algılamasına ve otomatik olarak OOBE'nin tamamlanmasına izin vermesine izin ver. Cihaz OOBE sırasında yeniden başlatabilirsiniz. OOBE ekranları aşağıdakine benzer.

   ![OOBE adım 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE adım 3](./images/autopilot-device-setup.jpg)

1. OOBE'nin sonunda kullanıcı adı ve parolanızı kullanarak cihazda oturum açın.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

HoloLens 2 cihazları, Windows Holographic sürüm 20H2'den sonra TenantLockdown CSP'yi destekler. Bu CSP, cihaz sıfırlama veya ters eğik çizgi ile bile cihazları bu kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değere ayarlandıktan sonra bu değer yeniden yanıp sönmeye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra OOBE, Ağ bağlantısı sonrasında Autopilot profilinin başarıyla indirilme ve uygulanması için süresiz olarak bekler.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra OOBE'de aşağıdaki işlemlere izin verilmiyor:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme 
- OOBE deneyiminde cihazın sahibini seçme 

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesi yapma ve eşitlemeyi tetikleme.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak HoloLens 2'de TenantLockdown'ın RequireNetworkInOOBE'lerinin kümesi nasıl geri alır?

1. Yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2'i kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesi yapma ve eşitlemeyi tetikleme.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Autopilot profili HoloLens'te atanmamışsa OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilene kadar süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için, cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir.

![Cihazda ilkenin ne zaman zorlanan cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Bilinen Sorunlar & sınırlamaları

- MEM'de yapılandırılan cihaz bağlamı tabanlı uygulama yüklemenin HoloLens için geçerli olmayan bir sorunu araştırıyoruz. [Cihaz bağlamı ve kullanıcı bağlamı yüklemeleri hakkında daha fazla bilgi edinebilirsiniz.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Autopilot'ı Wi-Fi üzerinden ayarlarken, İnternet bağlantısı ilk kez kurulurken Autopilot profilinin indirilemedikleri bir örnek olabilir. Bu durumda Son Kullanıcı Lisans Sözleşmesi (EULA) sunulmuştur ve kullanıcının Autopilot olmayan kurulum deneyimine devam edebilirsiniz. Autopilot ile ayarlamayı yeniden denemek için cihazı uykuya bırakın ve cihazı açın veya yeniden başlatın ve yeniden deneyin.
- HoloLens'de "Hedeflenen tüm cihazları Autopilot'a dönüştür" özelliği şu anda desteklenmiyor.  


## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydı desteği için lütfen satıcınıza veya dağıtımcınıza başvurun.
- Profil atamaları, grup oluşturma Windows Autopilot MEM portalı denetimleri gibi sorunlar hakkında genel destek sorguları için lütfen Microsoft Endpoint Manager [başvurun](https://docs.microsoft.com/mem/get-support)  
- Cihazınız Autopilot hizmetine kayıtlı ve profil MEM portalında atanmışsa [HoloLens](https://docs.microsoft.com/hololens/) desteğine başvurun (bkz. 'Destek' kartı). Lütfen bir destek bileti açın ve varsa, ilk deneyim [](hololens-diagnostic-logs.md#offline-diagnostics) (OOBE) sırasında çevrimdışı tanılama günlüklerini yakalayarak ekran görüntülerini ve günlükleri dahil edin.
- Cihazdan bir sorun rapor etmek için HoloLens Geri Bildirim Merkezi uygulamayı kullanın. Bu Geri Bildirim Merkezi Kurumsal Yönetim **Cihazı**  >  **kategorisini** seçin.
- HoloLens için Autopilot hakkında genel geri bildirim sağlamak için bu anketi [gönderebilirsiniz](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
