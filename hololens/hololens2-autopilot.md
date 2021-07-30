---
title: HoloLens 2 için Windows Autopilot
description: HoloLens 2 cihazlarda Autopilot'ın nasıl ayar HoloLens ve sorunlarını gidermeyi öğrenin.
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
ms.openlocfilehash: ca50a4b0ec2e3687a350ca654aaa60c144c4c78a
ms.sourcegitcommit: 44d5fbee8aa0e2404137484edbeb4653437e79dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2021
ms.locfileid: "114991449"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

Windows Holographic sürüm 2004'den itibaren HoloLens 2, Microsoft Intune ile Windows [Autopilot](/mem/autopilot/self-deploying) Kendi Kendine Dağıtım Modunu destekler (3. taraf MDM'ler desteklanmaz). Yöneticiler, Microsoft Endpoint Manager'da ilk kullanım deneyimini (OOBE) yapılandırarak son kullanıcıların çok az etkileşimle veya hiç etkileşim olmadan cihazları iş kullanımına hazırlamasını sağlar. Bu, kurulum deneyimi sırasında çalışanlardan gelen stok yönetimi ek yükünü, cihaz hazırlığı ve destek çağrılarının maliyetini azaltır. Daha fazla bilgi için [Windows Autopilot belgelerine](/mem/autopilot/windows-autopilot) bakın.

Surface cihazlarında olduğu gibi, müşterilerin de microsoft Bulut Çözümü Sağlayıcısı (kurumsal bayi [veya](https://partner.microsoft.com/cloud-solution-provider) dağıtımcı) ile birlikte çalışması ve bu cihazlarla autopilot hizmetine kayıtlı cihazları İş Ortağı Merkezi. Cihaz kaydına ilişkin diğer yöntemler [](/mem/autopilot/add-devices) cihaz ekleme belgelerinde açıklanmıştır, ancak Microsoft'un kanal iş ortaklarından yararlanarak en etkili bitiş yolu garanti altına alınmaktadır.

> [!NOTE]
> 20.11.2020 tarihinde HoloLens için Autopilot yapılandırması Microsoft Endpoint Manager Genel Önizleme'ye **geçişte.** Müşterilerin artık özel önizlemeye kaydolması gerekmemektedir ve tüm kiracılar MEM yönetim merkezinde Autopilot'u kurabilecektir.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başlatırsa Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme. HoloLens için Autopilot'ın Active Directory'ye katılmayı veya Hibrit Azure AD'ye katılmayı desteklemez.

1. Azure AD'ye kullanarak cihazı bir Microsoft Endpoint Manager (veya başka bir MDM hizmetine) kaydetme.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulama.

1. Cihazı sağlama.

1. Oturum açma ekranı kullanıcıya gösterilir.

## <a name="configuring-autopilot-for-hololens-2"></a>Autopilot'i HoloLens 2 için yapılandırma

Ortamınızı ayarlamak için lütfen aşağıdaki adımları izleyin:

1. [Windows 2 için Autopilot HoloLens gözden geçirme.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydı etkinleştirme](#2-enable-automatic-mdm-enrollment)

1. [Autopilot'ta Windows kaydetme.](#3-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#4-create-a-device-group)

1. [Dağıtım profili oluşturun.](#5-create-a-deployment-profile)

1. [Kayıt Durumu Sayfası (ESP) yapılandırmasını doğrulayın.](#6-verify-the-esp-configuration)

1. [Uygulama cihazlarının profil HoloLens doğrulayın.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Windows 2 için Autopilot HoloLens gözden geçirme

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot gereksinimleri makalesinde yer alan aşağıdaki bölümleri gözden geçirebilirsiniz:

- [Ağ gereksinimleri](/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying gözden geçirebilirsiniz.[](/windows/deployment/windows-autopilot/self-deploying#requirements)** Ortamınız hem bu gereksinimleri hem de Autopilot gereksinimlerini Windows karşılamalıdır. Makalenin "Adım adım" ve "Doğrulama" bölümlerini gözden geçirmeye gerek yok. Bu makalenin devamlarında yer alan yordamlar, belirli bir HoloLens.

Cihazları kaydetme ve profilleri yapılandırma hakkında bilgi için bkz. [2. Windows Autopilot ve](#3-register-devices-in-windows-autopilot) [4'e cihaz kaydetme. Bu makalede bir dağıtım](#5-create-a-deployment-profile) profili oluşturun. Autopilot kendi kendine dağıtım modu profillerini yapılandırmak ve yönetmek için, yönetim merkezinden Microsoft Endpoint Manager [emin olun.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Sistem HoloLens gereksinimlerini gözden geçirme:

- Cihazlar [Holographic, Windows 2004 (derleme 19041.1103)](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki bir sürümde olmalı. Cihazınızın derleme sürümünü onaylamak veya en son işletim sistemiyle yeniden flash oluşturmak için Gelişmiş Kurtarma Yardımcı [(ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) ve cihazı yeniden [flash yönergelerini kullanın.](/hololens/hololens-recovery#clean-reflash-the-device) Eylül 2020'nin sonlarına kadar teslim edilen cihazlarda Holographic Windows 1903'ün önceden yüklü olduğunu unutmayın. Autopilot'a hazır cihazların size gönderiliyor olduğundan emin olmak için lütfen kurumsal bayinizle iletişime geçin.

- Windows Holographic sürüm 2004 yalnızca Ethernet bağlantısı üzerinden Autopilot'u destekler. Cihazı HoloLens önce "USB-C'den Ethernet'e" bağdaştırıcısı kullanarak **Ethernet'e bağlı olduğundan emin olun.** Cihaz önyüklemesi sırasında kullanıcı etkileşimi gerekmez. Autopilot'ın birçok farklı cihaza HoloLens, bağdaştırıcı altyapısını planlamanız önerilir. Usb Hub'ları önerilmez çünkü bunlar genellikle ek üçüncü taraf sürücülerin yüklü HoloLens.

- [Windows Holographic sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041.1128) veya sonraki sürümler Wi-Fi üzerinden Autopilot'ı destekler, ancak yine de Ethernet bağdaştırıcıları kullanabilirsiniz. Wi-Fi üzerinden bağlanan cihazlar için kullanıcının yalnızca:

     - Kuş sahnelerini inceleme
     - Dili ve yerel dili seçin
     - Göz ayarlamayı çalıştırma
     - Ağ bağlantısı kurma

- Windows Holographic sürüm 20H2, bir cihazı bir kiracıya kilitleyen ve yanlışlıkla veya kasıtlı sıfırlama veya silme durumunda cihazın o kiracıya bağlı kalmasını sağlayan [Tenantlockdown CSP](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)ve Autopilot'ı destekler.  

- Cihazların zaten Azure AD'ye üye olduğundan ve Intune'a (veya başka bir MDM sistemine) kayıtlı değil olduğundan emin olun. Autopilot kendi kendine dağıtım işlemi bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlenmiş olduğundan emin  olmak için hem Azure AD'de hem de Intune Portallarında Cihazlar sayfalarını kontrol edin. "Tüm hedeflenen cihazları Autopilot'a dönüştür" özelliğinin şu anda HoloLens olmadığını unutmayın.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Otomatik MDM Kaydı'nın etkinleştirin:

Autopilot'ın başarılı olması için otomatik MDM Kaydı'Azure portal. Bu, cihazın kullanıcı olmadan kaydolmalarını sağlar.

Veri [Azure portal](https://portal.azure.com/#home) Mobility **(MDM ve**  ->  **MAM) Azure Active Directory'yi Microsoft Intune.**  ->   Ardından **MDM kullanıcı kapsamını yapılandırarak** All (Tüm) seçeneğini seçmeniz **gerekir.**

Ayarlama hakkında daha fazla [bilgi için lütfen MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) Otomatik Kaydı'nın etkinleştirilmesi ile ilgili aşağıdaki kısa kılavuzu veya Otomatik Kayıt Hızlı başlangıç kılavuzunu gözden geçirebilirsiniz. [](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

### <a name="3-register-devices-in-windows-autopilot"></a>3. Autopilot'Windows kaydetme

cihazlarınızı ilk kurulumdan önce Windows Autopilot'a kayıtlı olması gerekir. Cihaz kaydıyla ilgili MEM belgeleri için [bkz. Autopilot'a cihaz ekleme.](/mem/autopilot/add-devices)  

Cihazları kaydetmek için başlıca üç HoloLens vardır:

 - **Kurumsal bayi, sipariş İş Ortağı Merkezi cihazları kayıt cihazına kaydedebilirsiniz.**

   > [!NOTE]  
   > Bu, Autopilot hizmetine cihaz eklemek için önerilen yoldur. [Daha fazla bilgi edinin](/mem/autopilot/partner-registration).  

 - **Destek [isteğini doğrudan Microsoft'a](hololens2-autopilot-registration-support.md) gönderebilirsiniz.**
 - **Donanım karması (donanım kimliği olarak da bilinir)** alın ve cihazı MEM yönetim merkezine el ile kaydedin.

#### <a name="obtain-hardware-hash"></a>Donanım karması alma
Donanım karması almanın iki yolu vardır.
1. Destek [isteğini doğrudan Microsoft'a](hololens2-autopilot-registration-support.md) gönderebilirsiniz.
2. Bunu cihazdan edinebilirsiniz. Cihaz, donanım karması OOBE işlemi sırasında veya daha sonra bir cihaz sahibi tanılama günlüğü toplama işlemini (aşağıdaki yordamda açıklanmıştır) başlatırken bir CSV dosyasına kaydedilir. Genellikle cihaz sahibi, cihazda oturum açması gereken ilk kullanıcıdır.
     > [!WARNING]
     > 20H2'den önceki derlemelerde, OOBE'den geçtiy ve telemetri Gerekli olarak ayarlanmışsa bu yöntem aracılığıyla Autopilot için donanım karması toplayabilirsiniz. Bu yöntem aracılığıyla donanım karmanızı toplamak için, Ayarlar App aracılığıyla telemetri seçeneğini Tam olarak ayarlayın ve Gizlilik -> Tanılama'yı seçin.

    1. 2 HoloLens başlatma.

    1. Cihazda, aynı anda **Güç ve** Ses Düzeyi **Aşağı** düğmelerine basın ve ardından bunları bırakın. Cihaz tanılama günlüklerini ve donanım karması toplar ve bunları bir dizi farklı .zip depolar.

   1. Tüm ayrıntılar ve bunun nasıl önceden biçimlendirilmiş olduğu hakkında bir yönerge videosu için çevrimdışı tanılama [hakkında bilgi alın.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Cihazı bir bilgisayara bağlamak için USB-C kablosu kullanın.

    1. Bilgisayarda, Dosya Gezgini. Bu **PC İç Depolama \\ \<*HoloLens device name*> \\ \\ Belgeler'i** açın ve AutopilotDiagnostics.zip bulun.  

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

1. Yönetim [Microsoft Endpoint Manager altında,](https://endpoint.microsoft.com)Cihazlar ve kayıt Windows Windows ve ardından Program'ın altında Cihazlar İçeri  >    >     >   **Aktarma'Windows Autopilot Deployment seçin.**

1. **Autopilot Windows Ekle altında DeviceHash** CSV dosyasını seçin, Aç'ı **ve** ardından İçeri Aktar'ı **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Donanım karması içeri aktar için İçeri Aktar komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. İçeri aktarma işlemi tamam olduktan sonra Cihazlar'ı  >  **Windows**  >  **Windows Cihazları**  >  **Eşitleme'yi**  >  **seçin.** Kaç cihaz eşitlenmesine bağlı olarak işlem birkaç dakika sürebilir. Kayıtlı cihazı görmek için Yenile'yi **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Cihaz grubu oluşturma

1. Yönetim [Microsoft Endpoint Manager Gruplar Yeni](https://endpoint.microsoft.com) **grup'ı**  >  **seçin.**

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

1. Yönetim [Microsoft Endpoint Manager Autopilot dağıtım](https://endpoint.microsoft.com) **profilleri** Windows  >    >  **Windows'Windows** Için Cihazlar'ı seçin  >    >  **HoloLens.**  >  
   ![Profil oluştur açılan listesinde bir HoloLens vardır.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından Sonraki'yi **seçin.**  
   listesini içeren bir liste **HoloLens.** Bu seçenek yoksa Geri bildirim seçenekleriyle bize [ulaşın.](hololens2-autopilot.md#feedback-and-support-for-autopilot)

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklama ekleme](./images/hololens-ap-profile-name.png)

1. İlk **deneyim (OOBE)** sayfasında, ayarların çoğu bu değerlendirme için OOBE'yi kolaylaştıracak şekilde önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (Bölge):** OOBE için dili seçin. 2 için desteklenen diller listesinden [bir dil HoloLens öneririz.](hololens2-language-support.md)
   - **Klavyeyi otomatik olarak** yapılandırma: Klavyenin seçili dille eş olduğundan emin olmak için Evet'i **seçin.**
   - **Cihaz adı şablonu uygulama:** OOBE sırasında cihaz  adını otomatik olarak ayarlamak için Evet'i seçin ve Ardından Ad girin alanına şablon tümceciği ve yer tutucularını girin. Örneğin, dört basamaklı rastgele sayı için bir ön ek ve yer  `%RAND:4%` &mdash; tutucu girin.
     > [!NOTE]  
     > Cihaz adı şablonu kullanıyorsanız, OOBE işlemi cihaz adını uygulamanın ardından ve cihazı Azure AD'ye eklemeden önce cihazı bir kez daha yeniden başlatıyor. Bu yeniden başlatma, yeni adın etkili olmasına olanak sağlar.  

   > [!div class="mx-imgBorder"]
   > ![OOBE ayarlarını yapılandırma](./images/hololens-ap-profile-oobe.png)

1. Ayarları yapılandırdikten sonra, Sonraki'yi **seçin.**
1. Kapsam **etiketleri sayfasında,** isteğe bağlı olarak bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için [bkz. Dağıtılmış IT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma.](/mem/intune/fundamentals/scope-tags.md) Tamamlandığında, Sonraki'yi **seçin.**
1. Atamalar **sayfasında Atama** için Seçili **gruplar'ı** **seçin.**
1. **SEÇİLEN GRUPLAR** altında **+ Dahil etmek için grupları seçin'i seçin.**
1. Dahil **etmek için grupları seçin listesinde** Autopilot cihazları için oluşturduğunuz cihaz grubunu HoloLens'ı **seçin.**  
  
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

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Uygulama cihazlarının profil HoloLens doğrulama

1. Yönetim Microsoft Endpoint Manager'nde Cihazlar'ı **ve**  >  **Windows**  >  **Windows'yi**  >  **seçin.**

1. HoloLens cihazların listelenmiş olduğunu ve profil durumunun Atandı olduğunu **doğrulayın.**  

   > [!NOTE]  
   > Profilin cihaza atanmaları birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 Kullanıcı Deneyimi için Autopilot

Yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcınız kendi HoloLens cihazlarını sağlama konusunda aşağıdaki deneyimi HoloLens geçecektir:  

1. Autopilot deneyimi için İnternet erişimi gerekir. İnternet erişimi sağlamak için lütfen aşağıdaki seçeneklerden birini kullanın:

    - Bağlan OOBE'Wi-Fi bir ağ üzerinden çalıştırın ve autopilot deneyimini otomatik olarak algılamasına izin verir. Autopilot deneyimi kendi kendine tamamlayana kadar OOBE ile yalnızca bu kez etkileşim kurmanız gerekir. İnternet algılayan autopilot'HoloLens algılamak için varsayılan olarak 2'nin 10 saniye beklemesi gerekir. 10 saniye içinde bir otomatik pilot profili algılanmazsa OOBE EULA'yı sunacak. Bu senaryoyla karşılaşırsanız, Autopilot'ın algılanabilir olması için cihazınızı yeniden başlatın. Ayrıca, OOBE'nin Autopilot için süresiz olarak yalnızca cihazda TenantLockdown ilkesi ayarlanmışsa bekleyebilir.

    - Bağlan İnternet bağlantısı için "USB-C'den Ethernet'e" bağdaştırıcıları kullanarak Ethernet ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimini HoloLens izin verir.

    - Bağlan İnternet bağlantısı için "USB-C'den Wifi'ye" bağdaştırıcıları kullanarak cihazınızı çalıştırın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

        > [!IMPORTANT]  
       > Autopilot için OOBE'Wi-Fi ağlarını kullanmaya çalışan cihazların [Holographic sürüm 20H2'de Windows olması gerekir.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Ethernet bağdaştırıcıları kullanan cihazlar için, İlk İlk Deneyim (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranında autopilot cihaz olarak sağ isteyip sağlama olmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı Autopilot cihazı olarak sağlamayı seçmiyorsanız, daha sonra Autopilot sağlama olarak değiştiremezsiniz. Bunun yerine, cihazı Autopilot cihaz olarak sağlama amacıyla bu yordamı baştan başlatmanız gerekir.

1. Cihazın OOBE'i otomatik olarak başlatması gerekir. OOBE ile etkileşim kurma. Bunun yerine arkanıza yaslanın ve gevşeyin! 2 HoloLens 2'nin ağ bağlantısını algılamasına ve otomatik olarak OOBE'nin tamamlanmasına izin ver. Cihaz OOBE sırasında yeniden başlatabilirsiniz. OOBE ekranları aşağıdakine benzer.

   ![OOBE adım 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE adım 3](./images/autopilot-device-setup.jpg)

1. OOBE'nin sonunda kullanıcı adı ve parolanızı kullanarak cihazda oturum açın.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

HoloLens 2 cihaz, Holographic sürüm 20H2'den Windows TenantLockdown CSP'yi destekler. Bu CSP, cihaz sıfırlama veya ters eğik çizgi ile bile cihazları bu kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değerine ayarlandıktan sonra, bu değer yeniden yanıp sönmeye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

HoloLens 2'de TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü true olarak ayarlandıktan sonra OOBE, Autopilot profilinin ağ bağlantısı sonrasında başarıyla indirilme ve uygulanması için süresiz olarak bekler.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE'de aşağıdaki işlemlere izin verilmiyor:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme 
- OOBE deneyiminde cihazın sahibini seçme 

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır?

1. Yukarıda HoloLens 2 olan cihaz 2'nin daha önce atanmış olduğu cihaz yapılandırmasını kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![Intune 'da OMA URI aracılığıyla talep ırenetworkınoobe ayarının false olarak ayarlanmasına yönelik ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın. 

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandıktan sonra, tenantlockdown 'ın etkileri devre dışı bırakılır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Autopilot profili, maantlockdown true olarak ayarlandıktan sonra bir HoloLens için atanmazsa, OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilmek için süresiz olarak bekler ve aşağıdaki iletişim kutusu sunulacaktır. TenantLockdown 'in etkilerini kaldırmak için, önce Autopilot yalnızca bir cihaz özgün kiracısına kaydedilmelidir ve eski adımda açıklandığı gibi, TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önce bu, önkoşul olarak ayarlanmalıdır.

![Cihazda ilke uygulandığında cihaz içi görünümü.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Bilinen sorunlar & sınırlamaları

- MEM içinde yapılandırılan cihaz bağlamı tabanlı uygulama yüklemesinin HoloLens için uygulanmamakta olduğu bir sorunu araştırıyoruz. [Cihaz bağlamı ve Kullanıcı bağlamı yüklemeleri hakkında daha fazla bilgi edinin.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Wi-Fi üzerinden Autopilot ayarlarken, Internet bağlantısı ilk kez oluşturulduğunda Autopilot profilinin indirilmediği bir örnek olabilir. Bu durumda, Son Kullanıcı Lisans Sözleşmesi (EULA) sunulur ve kullanıcının Autopilot olmayan kurulum deneyimiyle devam etme seçeneği vardır. Autopilot ile ayarlamayı yeniden denemek için cihazı uyku moduna alın ve ardından cihazı kapatıp yeniden başlatın ve tekrar deneyin.
- "hedeflenen tüm cihazları Autopilot 'e dönüştür" özelliği şu anda HoloLens desteklenmez.  

### <a name="troubleshooting"></a>Sorun giderme

aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot sorunlarını gidermek için yararlı bir kaynak olabilir, ancak bu makalelerin Windows 10 masaüstüne bağlı olduğunu ve tüm bilgilerin HoloLens için uygulanabilir olabileceğini lütfen unutmayın:

- [Windows Autopilot-bilinen sorunlar](/mem/autopilot/known-issues)
- [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot-Ilke çakışmaları](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydı desteği için lütfen satıcı veya dağıtıcı ile iletişime geçin.
- Windows Autopilot hakkında genel destek sorguları veya profil atamaları, grup oluşturma veya MEM portalı denetimleri gibi sorunlar için [lütfen Microsoft Endpoint Manager desteğe başvurun](/mem/get-support)  
- cihazınız Autopilot hizmetine kayıtlıysa ve bu profil MEM portalında atanırsa, HoloLens [desteğe](/hololens/) başvurun (bkz. ' destek ' kartı). Lütfen bir destek bileti açın ve varsa, [çevrimdışı tanılama günlüklerini](hololens-diagnostic-logs.md#offline-diagnostics) kullanıma hazır deneyım (OOBE) sırasında yakalayıp ekran görüntüleri ve Günlükler ekleyin.
- Cihazdan bir sorun bildirmek için HoloLens geri bildirim Merkezi uygulamasını kullanın. geri bildirim Hub 'ında **Enterprise Management**  >  **cihaz** kategorisini seçin.
- HoloLens için Autopilot hakkında genel geri bildirim sağlamak için bu [anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) gönderebilirsiniz

## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Artık Autopilot için bir cihaz kullanmak veya cihazlarınızı farklı bir kiracıya kaydetmek isteyebilirsiniz. Bunu yapmak istiyorsanız,[Autopilot cihazlarını silmek için h ow](/mem/autopilot/add-devices#delete-autopilot-devices) makalesini okuyun.