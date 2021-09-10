---
title: HoloLens 2 için Windows Autopilot
description: HoloLens 2 cihazlarda Autopilot'ın nasıl ayar HoloLens ve sorunlarını gidermeyi öğrenin.
author: qianw211
ms.author: v-qianwen
ms.date: 9/8/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Otopilot
manager: sekerawa
ms.openlocfilehash: c71716778ebd536d3aecd2a34c9929c8b2f76d98
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428058"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

## <a name="overview"></a>Genel Bakış

Büyük ölçekte dağıtım yapmak için Autopilot'Windows başlamayı öneririz. Hem IT hem de son kullanıcılar için ayarları önemli ölçüde basitleştirerek "HoloLens" olarak kabul edilir. 

Genel olarak, bir IT yöneticisi genellikle iş için hazır yapılandırmaları oluşturmalı ve MDM portallarında HoloLens 2 cihazı kaydedmektedir. İlk HoloLens (OOBE) ile önyüklenirken ve İnternet'e bağlandığında, kayıtlı HoloLens 2 cihazı için iş için hazır yapılandırmalar otomatik olarak indirilir ve cihaz herhangi bir kullanıcı müdahalesi olmadan iş için hazır hale gelir.

Daha fazla bilgi için [bkz. Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot) makale.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>HoloLens 2'de desteklenen otomatik pilot senaryosu

> [!NOTE]
> Microsoft Endpoint Manager'da HoloLens için Autopilot yapılandırması Genel Önizleme'den Genel **Kullanılabilirlik'e geçişte.**  Tüm kiracılar, MEM yönetim merkezinde Autopilot'u kurabilecek.

Windows Holographic sürüm 2004'den başlayarak, HoloLens 2, Windows [Autopilot](/mem/autopilot/self-deploying) Self Servis Dağıtım Modunu Microsoft Intune ile destekler (üçüncü taraf MDM'ler desteklanmaz). Bu yapılandırma, kurulum deneyimi sırasında stok yönetimi ek yükünü, uygulamalı cihaz hazırlama maliyetini ve çalışanlardan gelen destek çağrılarını azaltır. Daha fazla bilgi için [Windows Autopilot belgelerine](/mem/autopilot/windows-autopilot) bakın.

Surface cihazlarında olduğu gibi, müşterilerin Bulut Çözümü Sağlayıcısı aracılığıyla Autopilot [hizmetine](https://partner.microsoft.com/cloud-solution-provider) kayıtlı cihazları almak için Microsoft Bulut Çözümü Sağlayıcısı (kurumsal bayi veya dağıtımcı) ile İş Ortağı Merkezi.

Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başlatırsa Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme. HoloLens için Autopilot, Active Directory'ye katılmayı veya Hibrit Azure AD'ye katılmayı desteklemez.

1. Cihazı Microsoft Endpoint Manager (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulama.

1. Oturum açma ekranı kullanıcıya gösterilir.

## <a name="configuring-autopilot-for-hololens-2"></a>Autopilot'i HoloLens 2 için yapılandırma

Ortamınızı ayarlamak için aşağıdaki adımları izleyin:

1. [Windows 2 için Autopilot HoloLens gözden geçirme.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydı etkinleştirme](#2-enable-automatic-mdm-enrollment)

1. (Yalnızca Intune için) [Tüm cihazlarda MDM kaydı engellenmiş Windows olun.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Autopilot'ta Windows kaydetme.](#4-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#5-create-a-device-group)

1. [Otomatik pilot profili oluşturun ve bunu cihaz grubuna attayabilirsiniz.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Kayıt Durumu Sayfası (ESP) yapılandırmasını oluşturun ve bunu cihaz grubuna attayabilirsiniz.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Uygulama cihazlarının profil HoloLens doğrulayın.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Windows 2 için Autopilot HoloLens gözden geçirme

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot gereksinimleri makalesinde yer alan bölümleri gözden geçirebilirsiniz:

- [Ağ gereksinimleri](/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying gözden geçirebilirsiniz.[](/windows/deployment/windows-autopilot/self-deploying#requirements)** Ortamınız bu gereksinimleri ve Autopilot gereksinimlerini Windows karşılamalıdır. Makalenin "Adım adım" ve "Doğrulama" bölümlerini gözden geçirmeye gerek yok. Bu makalenin devamlarında yer alan yordamlar, bu yordamlara özgü HoloLens.

Cihazların zaten Azure AD'ye üye olduğundan ve Intune'a (veya başka bir MDM sistemine) kayıtlı değil olduğundan emin olun. Autopilot kendi kendine dağıtım işlemi bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlenmiş olduğundan emin  olmak için hem Azure AD hem de Intune Portalları'nın Cihazlar sayfalarını kontrol edin. Hedeflenen tüm cihazları Autopilot'a dönüştür" özelliği şu anda HoloLens için desteklenmiyor. 

#### <a name="review-hololens-os-requirements"></a>HoloLens işletim sistemi gereksinimlerini gözden geçirme:

Cihazınızın derleme sürümünü onaylamak veya en son işletim sistemiyle bağlantı kurmak için Gelişmiş Kurtarma Yardımcı [(ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) ve cihaz ters eğik çizgi [yönergelerimizi kullanın.](hololens-recovery.md) Eylül 2020'nin sonlarına kadar teslim edilen Windows Holographic sürüm 1903 önceden yüklenmiştir. Autopilot'a hazır cihazların size gönderiliyor olduğundan emin olmak için kurumsal bayinizle iletişime geçin.

 En düşük işletim sistemi sürümü | Desteklenen özellik | Açıklamalar 
 ------ | ------ | ------  
 [Windows Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) (derleme 19041.1103) veya sonrası | 1. HoloLens 2'de Autopilot'ın kendi kendine dağıtım senaryosu. | Autopilot profil indirmesi yalnızca Ethernet üzerinden de destek sağlar. Cihazı HoloLens önce "USB-C'den Ethernet'e" bağdaştırıcısı kullanarak **Ethernet'e bağlı olduğundan emin olun.**  Autopilot'ın birçok farklı cihaza HoloLens planlıyorsanız bağdaştırıcı altyapısını planlamanız önerilir. USB Hub'ları genellikle üçüncü taraf sürücülerin yüklü olması gerektirile birlikte önerilmez ve bu da HoloLens.
 [Windows Holographic, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041.1128) veya sonrası | 1. Otomatik pilot profilini Wi-Fi üzerinden indirme. <br> 2. Cihazları Autopilot [tarafından belirtilen kiracıyla kilitlemek](#tenant-lockdown-csp-and-autopilot) için kiracı kilitleme CSP'si ve Autopilot. | İsterseniz Yine de Ethernet bağdaştırıcıları kullanabilirsiniz. Wi-Fi üzerinden bağlanan cihazlar için kullanıcının yalnızca: <ul> <li> Kuş sahnelerini inceleme. </li> <li> Dili ve yerel dili seçin. </li> <li> Göz ayarlamayı çalıştırın. </li> <li> İstenen wifi ağına başarıyla bağlan. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Otomatik MDM Kaydı'nın etkinleştirin:

Autopilot'ın başarılı olması için otomatik MDM Kaydı'Azure portal. Bu, cihazın kullanıcı olmadan kaydolmalarını sağlar.

Ayarlama hakkında daha [fazla bilgi için MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) Otomatik Kayıt'ın etkinleştirilmesi hakkında aşağıdaki kısa kılavuzu veya Otomatik Kayıt Hızlı başlangıç kılavuzunu gözden geçirebilirsiniz. [](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Cihazlarda MDM kaydı engellenmiş Windows olun.

Autopilot'ın başarılı olması için cihazlarınızı kaydede HoloLens emin olun. Bu HoloLens bir Windows olarak kabul edilir, bu nedenle dağıtımınızı engelecek kayıt kısıtlamalarına gerek yoktur. [Bu kısıtlama listesini gözden geçirin](/mem/intune/enrollment/enrollment-restrictions-set) ve cihazlarınızı kaydedesiniz.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Autopilot'Windows kaydetme

cihazlarınızı ilk kurulumdan önce Windows Autopilot'a kayıtlı olması gerekir. 

Cihazları kaydetmek için başlıca üç HoloLens vardır:

 - **Kurumsal bayi, sipariş İş Ortağı Merkezi cihazları kayıt cihazına kaydedebilirsiniz.**

   > [!NOTE]  
   > Bu, Autopilot hizmetine cihaz eklemek için önerilen yoldur. [Daha fazla bilgi edinin](/mem/autopilot/partner-registration).  

 - **Destek [isteğini doğrudan Microsoft'a](hololens2-autopilot-registration-support.md) gönderebilirsiniz.**
 - **Donanım karması (donanım kimliği olarak da bilinir) alın ve cihazı MEM yönetim merkezine el ile kaydedin.**

#### <a name="obtain-hardware-hash"></a>Donanım karması alma

Donanım karması cihazdan alın. Cihaz, donanım karması OOBE işlemi sırasında veya daha sonra bir cihaz sahibi tanılama günlüğü toplama işlemini (aşağıdaki yordamda açıklanmıştır) başlatırken bir CSV dosyasına kaydedilir. Genellikle cihaz sahibi, cihazda oturum açması gereken ilk kullanıcıdır.

> [!WARNING]
> 20H2'den önceki derlemelerde, OOBE'den geçtiy ve telemetri Gerekli olarak ayarlanmışsa bu yöntem aracılığıyla Autopilot için donanım karması toplayabilirsiniz. Bu yöntem aracılığıyla donanım karmanızı toplamak için, Ayarlar App aracılığıyla telemetri seçeneğini Tam olarak ayarlayın ve Gizlilik -> Tanılama'yı seçin.

1. 2 HoloLens başlatma.

1. Cihazda, aynı anda **Güç ve** Ses Düzeyi **Aşağı** düğmelerine basın ve ardından bunları bırakın. Cihaz tanılama günlüklerini ve donanım karması toplar ve bunları bir dizi donanım .zip depolar.

1. Bu işlemi nasıl gerçekleştirecekleri hakkında ayrıntılı bilgi ve yönerge videosu için Çevrimdışı Tanılama [hakkında bilgi edinebilirsiniz.](hololens-diagnostic-logs.md#offline-diagnostics)

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

1. Yönetim [Microsoft Endpoint Manager altında,](https://endpoint.microsoft.com)Cihazlar ve  >  **Windows**  >  **Windows'ı** seçin ve ardından Program'ın altında Cihazlar İçeri Windows Autopilot Deployment  >   **seçin.**

1. **Autopilot Windows Ekle** altında DeviceHash CSV dosyasını seçin, Aç'ı **ve** ardından İçeri Aktar'ı **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Donanım karması içeri aktar için İçeri Aktar komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. İçeri aktarma işlemi tamam olduktan sonra Devices  >  **Windows Windows**  >    >  **'ı**  >  **seçin.** Kaç cihaz eşitlenmesine bağlı olarak işlem birkaç dakika sürebilir. Kayıtlı cihazı görmek için Yenile'yi **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Cihaz grubu oluşturma

1. Yönetim [Microsoft Endpoint Manager Gruplar Yeni](https://endpoint.microsoft.com) **grup'ı**  >  **seçin.**

1. Grup türü olarak **Güvenlik'i seçin** ve ardından bir grup adı ve açıklaması girin. 

1. Üyelik **türü olarak** Atanan veya Dinamik **Cihaz'ı seçin.** 

1. Aşağıdakilerden birini yapın:  

   - Önceki adımda **Üyelik türü olarak** **Atanan'ı** seçtiyebilirsiniz. Üyeler'i seçin ve ardından Autopilot cihazlarını gruba ekleyin. Henüz kayıtlı olmayan Autopilot cihazları, cihaz adı olarak cihaz seri numarası kullanılarak listelenir.
   - Bir önceki adımda **Üyelik** türü için **Dinamik** Cihazlar'ı seçtiyebilirsiniz,  Dinamik cihaz üyeleri'ni seçin ve ardından Gelişmiş kural'a aşağıdakine benzer bir kod girin:
     - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazın: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune'un grup etiketi alanı, Azure AD **cihazlarında OrderID** özniteliğiyle eşler. Belirli bir grup etiketine (Azure AD cihaz OrderID) sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazmanız gerekir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Belirli bir Satın Alma Siparişi Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak için şunları yazın: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Bu kurallar Autopilot cihazlarına özgü öznitelikleri hedefler.
1. **Kaydet'i** ve ardından Oluştur'a **tıklayın.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Otomatik pilot profili oluşturma ve bunu cihaz grubuna atama

1. Yönetim [Microsoft Endpoint Manager Autopilot dağıtım](https://endpoint.microsoft.com) **profilleri** Windows  >    >  **Windows'Windows** Profil oluşturma'HoloLens.  >    >    >  
   ![Profil oluştur açılan listesinde bir HoloLens vardır.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından Sonraki'yi **seçin.**  
   listesini içeren bir liste **HoloLens.** Bu seçenek yoksa Geri bildirim seçenekleriyle bize [ulaşın.](hololens2-autopilot.md#feedback-and-support-for-autopilot)

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklama ekleyin.](./images/hololens-ap-profile-name.png)

1. İlk **deneyim (OOBE)** sayfasında, ayarların çoğu bu değerlendirme için OOBE'yi kolaylaştıracak şekilde önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (Bölge):** OOBE için dili seçin. 2 için desteklenen diller listesinden [bir dil seçmenizi HoloLens.](hololens2-language-support.md)
   - **Klavyeyi otomatik olarak** yapılandırma: Klavyenin seçili dille eş olduğundan emin olmak için Evet'i **seçin.**
   - **Cihaz adı şablonu uygulama:** OOBE sırasında cihaz  adını otomatik olarak ayarlamak için Evet'i seçin ve Ardından Ad girin alanına şablon tümceciği ve yer tutucularını girin. Örneğin, dört basamaklı rastgele sayı için bir ön ek ve yer  `%RAND:4%` &mdash; tutucu girin.
     > [!NOTE]  
     > Cihaz adı şablonu kullanırsanız, OOBE işlemi cihaz adını uygulamanın ardından ve cihazı Azure AD'ye eklemeden önce cihazı bir kez yeniden başlatılır. Bu yeniden başlatma, yeni adın etkili olmasına olanak sağlar.  

   > [!div class="mx-imgBorder"]
   > ![OOBE ayarlarını yapılandırma.](./images/hololens-ap-profile-oobe.png)

1. Ayarları yapılandırdikten sonra, Sonraki'yi **seçin.**
1. Kapsam **etiketleri sayfasında,** isteğe bağlı olarak bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için [bkz. Dağıtılmış IT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma.](/mem/intune/fundamentals/scope-tags.md) Tamamlandığında, Sonraki'yi **seçin.**
1. Atamalar **sayfasında Atama** için Seçili **gruplar'ı** **seçin.**
1. **SEÇİLEN GRUPLAR** altında **+ Dahil etmek için grupları seçin'i seçin.**
1. Dahil **etmek için grupları seçin listesinde** Autopilot cihazları için oluşturduğunuz cihaz grubunu HoloLens ve ardından Sonraki'yi **seçin.**  
  
   Herhangi bir grubu dışlamak için Dışlamak istediğiniz Grupları **seç'i** seçin ve dışlamak istediğiniz grupları seçin.

   > [!div class="mx-imgBorder"]
   > ![Profile bir cihaz grubu atama.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Gözden Geçir **+ Oluştur sayfasında** ayarları gözden geçirerek Oluştur'a **seçerek** profili oluşturun.  

   > [!div class="mx-imgBorder"]
   > ![Gözden geçir ve oluştur.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Kayıt Durumu Sayfası (ESP) yapılandırması oluşturma ve bunu cihaz grubuna atama

Kayıt Durumu Sayfası (ESP), MDM ile yönetilen bir kullanıcı cihazda ilk kez oturum a açınca çalışan tam cihaz yapılandırma işleminin durumunu görüntüler. ESP yapılandırmanın aşağıdakine benzer olduğundan emin olun ve atamaların doğru olduğunu doğrulayın.  

> [!div class="mx-imgBorder"]
> ![ESP yapılandırması.](./images/hololens-ap-profile-settings.png)

ESP hakkında daha fazla bilgi için Kayıt [Durumu Sayfasını Ayarlama - Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Cihaz profili HoloLens doğrulama

1. Yönetim Microsoft Endpoint Manager'de Cihazlar'ı **seçin**  >  **Windows**  >  **Windows**  >  **cihazları' seçin.**

1. Uygulama cihazlarının HoloLens ve profil durumlarının Atandı olduğunu **doğrulayın.**  

   > [!NOTE]  
   > Profilin cihaza atanmaları birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 Kullanıcı Deneyimi için Autopilot

Yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcınız aşağıdaki deneyimi izleyerek kendi HoloLens sağlar:  

1. Autopilot deneyimi için İnternet erişimi gerekir. İnternet erişimi sağlamak için aşağıdaki seçeneklerden birini kullanın:

    - Bağlan OOBE'Wi-Fi bir ağ üzerinden çalıştırın ve autopilot deneyimini otomatik olarak algılamasına izin verir. Autopilot deneyimi kendi kendine tamamlayana kadar OOBE ile yalnızca bu kez etkileşim kurmanız gerekir. Varsayılan olarak HoloLens 2, İnternet'i algıladikten sonra Autopilot'ı algılamak için 10 saniye bekler. 10 saniye içinde bir otomatik pilot profili algılanmazsa OOBE EULA'yı sunacak. Bu senaryoyla karşılaşırsanız, Autopilot'ın algılanabilir olması için cihazınızı yeniden başlatın. Ayrıca OOBE'nin autopilot için süresiz olarak yalnızca cihazda TenantLockdown ilkesi ayarlanmışsa bekleyebilir.

    - Bağlan İnternet bağlantısı için "USB-C'den Ethernet'e" bağdaştırıcıları kullanarak Ethernet ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

    - Bağlan İnternet bağlantısı için "USB-C-Wi-Fi" bağdaştırıcıları ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

        > [!IMPORTANT]  
       > Autopilot için OOBE'Wi-Fi ağlarını kullanmaya çalışan cihazların [Holographic sürüm 20H2'de Windows olması gerekir.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Ethernet bağdaştırıcıları kullanan cihazlar için, İlk-Kutu Deneyimi (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranında autopilot cihaz olarak sağ isteyip sağlama olmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı Autopilot cihazı olarak sağlamayı seçmiyorsanız, daha sonra Autopilot sağlama olarak değiştiremezsiniz. Bunun yerine, cihazı Autopilot cihazı olarak sağlama amacıyla bu yordamı baştan başlatmanız gerekir.

1. Cihazın OOBE'i otomatik olarak başlatması gerekir. OOBE ile etkileşim kurma.

    > [!IMPORTANT]
    > Otomatik pilot devam ederken, sistemi bekleme/kapatma moduna getirmek için lütfen OOBE ile etkileşime geçmeyin veya güç düğmesine basın. Bu, otomatik pilot akışının tamamlanmayacak şekilde tamamlanmasına neden olabilir.

   2 HoloLens 2'nin ağ bağlantısını algılamasına ve otomatik olarak OOBE'nin tamamlanmasına izin ver. Cihaz OOBE sırasında yeniden başlatabilirsiniz. OOBE ekranları aşağıdakine benzer.

   ![OOBE 1. adım. ](./images/autopilot-welcome.jpg)
    ![ OOBE 2. adım. ](./images/autopilot-step-complete.jpg)
    ![ OOBE 3. adım.](./images/autopilot-device-setup.jpg)

1. OOBE'nin sonunda kullanıcı adı ve parolanızı kullanarak cihazda oturum açın.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Kiracı kilitleme CSP'si ve Autopilot

HoloLens 2 cihazları Holographic sürüm 20H2'den Windows TenantLockdown CSP'yi destekler. Bu CSP, cihaz sıfırlama veya ters eğik çizgi ile bile cihazları bu kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değerine ayarlandıktan sonra, bu değer ters eğik çizgiye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE ağ bağlantısı sonrasında Autopilot profilinin başarıyla indirilme ve uygulanması için süresiz olarak bekler.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE'de aşağıdaki işlemlere izin verilmiyor:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme 
- OOBE deneyiminde cihazın sahibini seçme 

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
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

## <a name="known-issues--limitations"></a>Bilinen sorunlar & sınırlamaları

- MEM içinde yapılandırılan cihaz bağlamı tabanlı uygulama yüklemesinin HoloLens için uygulanmamakta olduğu bir sorunu araştırıyoruz. [Cihaz bağlamı ve Kullanıcı bağlamı yüklemeleri hakkında daha fazla bilgi edinin.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Wi-Fi üzerinden Autopilot ayarlarken, Internet bağlantısı ilk kez oluşturulduğunda Autopilot profilinin indirilmediği bir örnek olabilir. Bu durumda, Son Kullanıcı Lisans Sözleşmesi (EULA) sunulur ve kullanıcının Autopilot olmayan kurulum deneyimiyle devam etme seçeneği vardır. Autopilot ile ayarlamayı yeniden denemek için cihazı uyku moduna alın ve ardından cihazı kapatıp yeniden başlatın ve tekrar deneyin.

### <a name="troubleshooting"></a>Sorun giderme

aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot sorunlarını gidermek için yararlı bir kaynak olabilir ancak bu makaleler Windows 10 masaüstü tabanlıdır ve tüm bilgiler HoloLens için uygulanabilir.

- [Windows Autopilot-bilinen sorunlar](/mem/autopilot/known-issues)
- [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot-Ilke çakışmaları](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydı desteği için satıcı veya dağıtımcı ile iletişim kurun.
- Windows Autopilot hakkında genel destek sorguları veya profil atamaları, grup oluşturma veya MEM portalı denetimleri gibi sorunlar için [desteğe başvurun Microsoft Endpoint Manager](/mem/get-support)  
- cihazınız Autopilot hizmetine kayıtlıysa ve bu profil MEM portalında atanırsa, HoloLens [desteğe](/hololens/) başvurun (bkz. ' destek ' kartı). Bir destek bileti açın ve varsa, hazır olma deneyimi (OOBE) sırasında [çevrimdışı tanılama günlüklerini](hololens-diagnostic-logs.md#offline-diagnostics) yakalayarak ekran görüntüleri ve günlükleri dahil edin.
- Cihazdan bir sorun bildirmek için HoloLens geri bildirim Merkezi uygulamasını kullanın. geri bildirim Hub 'ında **Enterprise Management**  >  **cihaz** kategorisini seçin.
- HoloLens için Autopilot hakkında genel geri bildirim sağlamak için bu [anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) gönderebilirsiniz

## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Artık Autopilot için bir cihaz kullanmak veya cihazlarınızı farklı bir kiracıya kaydetmek isteyebilirsiniz. Bunu yapmak isterseniz, [Autopilot cihazlarını silmeyi okuyun.](/mem/autopilot/add-devices#delete-autopilot-devices)