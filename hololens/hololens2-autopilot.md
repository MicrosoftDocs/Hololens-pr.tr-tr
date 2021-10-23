---
title: HoloLens 2 için Windows Autopilot
description: HoloLens 2 cihazlarındaki Autopilot ayarlama, yapılandırma ve sorun giderme hakkında bilgi edinin.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilot
manager: sekerawa
ms.openlocfilehash: b343e4dc6e217319574efa068cd72c5f5a8675a8
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202922"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

## <a name="overview"></a>Genel Bakış

ölçekli dağıtım yapmak için Windows Autopilot kullanmaya başlamanızı öneririz. hem bt hem de son kullanıcılar için HoloLens ayarlamayı önemli ölçüde kolaylaştıran "düşük dokunma" olarak kabul edilir. 

yüksek düzeyde, bir bt yöneticisi tipik olarak iş için uygun yapılandırmalara sahiptir ve MDM portallarına HoloLens 2 cihaz kaydeder. HoloLens 2 cihaz, kullanıma hazır deneyimle (OOBE) ve Internet 'e bağlı olduğunda, kayıtlı HoloLens 2 cihazı için iş için hazır olan yapılandırmalara otomatik olarak indirilir ve bu cihazları kullanıcı müdahalesi olmadan iş için hazır hale getirmek üzere uygulanır.

daha fazla bilgi için bkz. [Autopilot to Overview Windows | Microsoft Docs](/mem/autopilot/windows-autopilot) makalesi.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>HoloLens 2 üzerinde desteklenen autopilot senaryosu

> [!NOTE]
> Microsoft Endpoint Manager HoloLens için Autopilot yapılandırması, genel **önizlemeden** **genel kullanıma** geçiş durumuna geçiyor. Tüm kiracılar, Autopilot 'yi MEM Yönetim merkezinde ayarlayabilecektir.

HoloLens 2 Windows Holographic sürüm 2004 ' den başlayarak, Microsoft Intune ile Windows Autopilot [kendi kendine dağıtım modunu](/mem/autopilot/self-deploying) destekler (üçüncü taraf mdms desteklenmez). Bu yapılandırma, envanter yönetimi ek yükünü, uygulamalı cihaz hazırlığının maliyetini ve kurulum deneyimi sırasında çalışanların destek çağrılarını azaltır. [Windows Autopilot](/mem/autopilot/windows-autopilot) belgelerinde daha fazla bilgi edinin.

Surface cihazlarda olduğu gibi, müşterilerin iş ortağı merkezi aracılığıyla Autopilot hizmetine kayıtlı cihazları almak için Microsoft [Bulut Çözümü Sağlayıcısı](https://partner.microsoft.com/cloud-solution-provider) (satıcı veya dağıtıcı) ile çalışması önerilir.

Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattığında, Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin. HoloLens için Autopilot, Active Directory joın veya hibrit Azure AD joın 'i desteklemez.

1. cihazı Microsoft Endpoint Manager (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulayın.

1. Kullanıcıya oturum açma ekranını sunun.

## <a name="configuring-autopilot-for-hololens-2"></a>HoloLens 2 için Autopilot yapılandırma

Ortamınızı ayarlamak için aşağıdaki adımları izleyin:

1. [HoloLens 2 için Windows Autopilot için gereksinimleri gözden geçirin.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydını etkinleştir](#2-enable-automatic-mdm-enrollment)

1. (Yalnızca Intune için) [MDM kaydının Windows cihazlar için engellenmediğinden emin olun.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [cihazları Windows Autopilot 'ye kaydedin.](#4-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#5-create-a-device-group)

1. [Autopilot profili oluşturun ve cihaz grubuna atayın.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Kayıt durumu sayfası (ESP) yapılandırması oluşturun ve cihaz grubuna atayın.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [HoloLens cihazlarının profil durumunu doğrulayın.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. HoloLens 2 için Windows Autopilot gereksinimlerini gözden geçirin

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot requirements makalesinin aşağıdaki bölümlerini gözden geçirin:

- [Ağ gereksinimleri](/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying modu makalesinin "[gereksinimler](/windows/deployment/windows-autopilot/self-deploying#requirements)" bölümünü gözden geçirin.** ortamınızın bu gereksinimleri ve standart Windows Autopilot gereksinimlerini karşılaması vardır. Makalenin "adım adım" ve "doğrulama" bölümlerini gözden geçirmeniz gerekmez. Bu makalede daha sonra açıklanan yordamlar HoloLens özel ilgili adımları sağlar.

Cihazların zaten Azure AD üyesi olmadığından ve Intune 'A (veya başka bir MDM sistemine) kaydolmadığından emin olun. Autopilot kendi kendine dağıtım işlemi, bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlendiğinden emin olmak için hem Azure AD hem de Intune portallarındaki **cihazlar** sayfalarını denetleyin. şu anda HoloLens tüm hedeflenen cihazları Autopilot "özelliğine dönüştür" özelliği desteklenmiyor.

#### <a name="review-hololens-os-requirements"></a>HoloLens işletim sistemi gereksinimlerini gözden geçirin:

Cihazınızdaki derleme sürümünü doğrulamak veya en son işletim sistemine geri dönmek için, [Gelişmiş kurtarma Yardımcısı 'nı (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) ve [cihazımız, cihaz refflash yönergelerinizi](hololens-recovery.md)kullanın. en geç 2020 sürümüne Windows Holographic sürüm 1903 önceden yüklenmiş olarak sunulan cihazlar. Autopilot-Ready cihazların size sevk edilmesini sağlamak için satıcınıza başvurun.

 En düşük işletim sistemi sürümü | Desteklenen özellik | Açıklamalar
 ------ | ------ | ------  
 [Windows Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) (derleme 19041,1103) veya üzeri | 1. HoloLens 2 üzerinde Autopilot 'in kendine dağıtım senaryosu. | Autopilot profili indirmesi yalnızca Ethernet aracılığıyla desteklenir. açmadan **önce**, HoloLens "USB-C-ethernet" bağdaştırıcısı kullanılarak ethernet 'e bağlı olduğundan emin olun.  birçok HoloLens cihaza bir Autopilot toplaması planlıyorsanız, bağdaştırıcı altyapısını planlamanız önerilir. Genellikle HoloLens desteklenmeyen üçüncü taraf sürücülerin yüklenmesini gerektirdiğinden, USB hub 'Ları önermiyoruz.
 [Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041,1128) veya üzeri | 1. Autopilot profilini Wi-Fi üzerinden indirme. <br> 2. [kiracı KILITLEME CSP 'si ve Autopilot](#tenant-lockdown-csp-and-autopilot) Autopilot belirtilen kiracı ile cihazları kilitlemeye yönelik. | İsterseniz Ethernet bağdaştırıcılarını kullanmaya devam edebilirsiniz. Wi-Fi ile bağlanan cihazlar için, Kullanıcı yalnızca şunları içermelidir: <ul> <li> Hummingbird sahnesini gözden geçir. </li> <li> Dili ve yerel ayarı seçin. </li> <li> Göz ayarlamayı çalıştırın. </li> <li> İstenen WiFi ağına başarıyla bağlanın. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. otomatik MDM kaydını etkinleştirin:

Autopilot başarılı olabilmesi için Azure portal otomatik MDM kaydını etkinleştirmeniz gerekir. Bu, cihazın kullanıcı olmadan kaydolmasını sağlar.

Kurulumu daha fazla bilgi edinmek için [MDM otomatik kaydını etkinleştirme](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) veya [otomatik kayıt Hızlı Başlangıç Kılavuzu ' nu](/mem/intune/enrollment/quickstart-setup-auto-enrollment) etkinleştirmek üzere aşağıdaki kısa kılavuzu inceleyin.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Windows cihazlar için MDM kaydının engellenmediğinden emin olun.

Autopilot 'in başarılı olması için HoloLens cihazlarınızın kaydolmasını sağlayabilirsiniz. HoloLens Windows bir cihaz olarak kabul edildiğinden, dağıtımınızı engelleyebilen bir kayıt kısıtlaması olmaması gerekir. [Bu kısıtlamalar listesini gözden geçirin](/mem/intune/enrollment/enrollment-restrictions-set) ve cihazlarınızı kaydedeceksiniz emin olun.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Windows Autopilot cihazları kaydetme

cihazlarınız ilk kurulumdan önce Windows Autopilot kayıtlı olmalıdır.

HoloLens cihazları kaydetmek için üç temel yol vardır:

 - **Satıcı, bir sipariş yerleştirdiğinizde cihazları Iş Ortağı Merkezi 'ne kaydedebilir.**

   > [!NOTE]  
   > Bu, Autopilot hizmetine cihaz eklemek için önerilen yoldur. [Daha fazla bilgi edinin](/mem/autopilot/partner-registration).  

 - **[Destek isteğini](hololens2-autopilot-registration-support.md) doğrudan Microsoft 'a gönderebilirsiniz.**
 - **Donanım karmasını (donanım kimliği olarak da bilinir) alın ve aygıtı, mem yönetim merkezine el ile kaydedin**.

#### <a name="obtain-hardware-hash"></a>Donanım karmasını al

Donanım karmasını cihazdan alabilirsiniz. Cihaz, OOBE işlemi sırasında bir CSV dosyasında donanım karmasını kaydeder veya bir cihaz sahibi tanılama günlüğü toplama işlemini başlattığında (aşağıdaki yordamda açıklanmaktadır). Genellikle cihaz sahibi cihazda oturum açmak için ilk Kullanıcı olur.

> [!WARNING]
> 20H2 ' den önceki derlemelerde, OOBE 'den çıkıldıysanız ve telemetri gerekli olarak ayarlandıysa, bu yöntem aracılığıyla Autopilot için donanım karmasını toplayamazsınız. bu yöntem aracılığıyla donanım karmalarınızın toplanması için telemetri seçeneğinizi Ayarlar uygulaması aracılığıyla tam olarak ayarlayın ve **gizlilik**  >  **tanılaması**' nı seçin.

1. HoloLens 2 cihazını başlatın.

1. Cihazda, **Güç** ve **ses azaltma** düğmelerine aynı anda basın ve ardından onları serbest bırakın. Cihaz tanılama günlüklerini ve donanım karmasını toplar ve bunları bir dizi .zip dosya halinde depolar.

1. Tam ayrıntılar ve bu işlemi nasıl gerçekleştireceğiniz hakkında daha fazla bilgi için [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)hakkında bilgi edinin.

1. Cihazı bir bilgisayara bağlamak için USB-C kablosu kullanın.

1. Bilgisayarda dosya Gezgini ' ni açın. <b>bu bilgisayarı \\</b> < *HoloLens cihaz adı* > <b> \\ iç Depolama \\ belgeler</b>' i açın ve AutopilotDiagnostics.zip dosyasını bulun.  

   > [!NOTE]  
   > .zip dosyası hemen kullanılamıyor olabilir. Dosya henüz hazırsanız belgeler klasöründe bir HoloLensDiagnostics. temp dosyası görebilirsiniz. Dosya listesini güncelleştirmek için pencereyi yenileyin.

1. Dosyanın içeriğini AutopilotDiagnostics.zip.

1. Ayıklanan dosyalarda, "DeviceHash" dosya adı ön ekine sahip CSV dosyasını bulun. Bu dosyayı daha sonra erişebilirsiniz bilgisayarın bir sürücüsüne kopyalayın.  

   > [!IMPORTANT]  
   > CSV dosyasındaki veriler aşağıdaki üst bilgi ve satır biçimini kullanmıştır:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>MEM aracılığıyla cihaz kaydetme

1. Yönetim [Microsoft Endpoint Manager,](https://endpoint.microsoft.com)Cihazlar ve kayıt Windows Windows'ı seçin ve ardından Program'ın altında  >    >  Cihazlar   >   **İçeri Aktarma'Windows Autopilot Deployment seçin.**

1. **Autopilot Windows Ekle** altında DeviceHash CSV dosyasını seçin, Aç'ı **ve** ardından İçeri Aktar'ı **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Donanım karması içeri aktarın komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. İçeri aktarma işlemi tamam olduktan sonra  >  **Cihazlar'ı Windows**  >  **Windows Cihazları Eşitle'yi**  >    >  **seçin.** Kaç tane cihaz eşitlenmesine bağlı olarak, sürecin tamamlanması birkaç dakika sürebilir. Kayıtlı cihazı görmek için Yenile'yi **seçin.**  

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

1. Yönetim [merkezinde Microsoft Endpoint Manager](https://endpoint.microsoft.com)Autopilot dağıtım  >  **profilleri Windows**  >  **Windows'Windows**  >    >    >  Profil oluşturma'HoloLens.
   ![Profil oluştur açılan listesinde bir HoloLens vardır.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından Sonraki'yi **seçin.**  
   listesini içeren bir liste **HoloLens.** Bu seçenek yoksa geri bildirim seçenekleriyle [bize ulaşın.](hololens2-autopilot.md#feedback-and-support-for-autopilot)

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklama ekleyin.](./images/hololens-ap-profile-name.png)

1. İlk **deneyim (OOBE)** sayfasında, ayarların çoğu bu değerlendirme için OOBE'yi kolaylaştıracak şekilde önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (Bölge):** OOBE için dili seçin. 2 için desteklenen diller listesinden [bir dil HoloLens öneririz.](hololens2-language-support.md)
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
1. Dahil **etmek için grupları seçin listesinde** Autopilot cihazları için oluşturduğunuz cihaz grubunu HoloLens'ı **seçin.**  
  
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

1. Yönetim Microsoft Endpoint Manager'nde Cihazlar'ı **ve**  >  **Windows**  >  **Windows'yi**  >  **seçin.**

1. HoloLens cihazların listelenmiş olduğunu ve profil durumunun Atandı olduğunu **doğrulayın.**  

   > [!NOTE]  
   > Profilin cihaza atanmaları birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 Kullanıcı Deneyimi için Autopilot

Yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcınız kendi HoloLens cihazlarını sağlama konusunda aşağıdaki deneyimi deneyimler:  

1. Autopilot deneyimi için İnternet erişimi gerekir. İnternet erişimi sağlamak için aşağıdaki seçeneklerden birini kullanın:

    - Bağlan OOBE'Wi-Fi bir ağ üzerinden çalıştırın ve autopilot deneyimini otomatik olarak algılamasına izin verir. Autopilot deneyimi kendi kendine tamamlayana kadar OOBE ile yalnızca bu kez etkileşim kurmanız gerekir.

    - Bağlan İnternet bağlantısı için "USB-C'den Ethernet'e" bağdaştırıcıları kullanarak Ethernet ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

    - Bağlan İnternet bağlantısı için "USB-C-Wi-Fi" bağdaştırıcıları ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

        > [!IMPORTANT]  
       > Autopilot için OOBE'Wi-Fi ağlarını kullanmaya çalışan cihazların [Holographic sürüm 20H2'de Windows olması gerekir.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Ethernet bağdaştırıcıları kullanan cihazlar için, İlk-Kutu Deneyimi (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranında autopilot cihaz olarak sağ isteyip sağlama olmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı Autopilot cihazı olarak sağlamayı seçmiyorsanız, daha sonra Autopilot sağlama olarak değiştiremezsiniz. Bunun yerine, cihazı Autopilot cihaz olarak sağlama amacıyla bu yordamı baştan başlatmanız gerekir.

1. Cihazın OOBE'i otomatik olarak başlatması gerekir. OOBE ile etkileşim kurma.

    > [!IMPORTANT]
    > Otomatik pilot devam ederken, sistemi bekleme/kapatma moduna getirmek için lütfen OOBE ile etkileşime geçmeyin veya güç düğmesine basın. Bu, otomatik pilot akışının tamamlanmayacak şekilde tamamlanmasına neden olabilir.

   Ağ HoloLens 2'nin ağ bağlantısını algılamasına ve otomatik olarak OOBE'nin tamamlanmasına izin ver. Cihaz OOBE sırasında yeniden başlatabilirsiniz. OOBE ekranları aşağıdakine benzer.

   ![OOBE 1. adım. ](./images/autopilot-welcome.jpg)
    ![ OOBE 2. adım. ](./images/autopilot-step-complete.jpg)
    ![ OOBE 3. adım.](./images/autopilot-device-setup.jpg)

1. OOBE'nin sonunda kullanıcı adı ve parolanızı kullanarak cihazda oturum açın.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Kiracı kilitleme CSP'si ve Autopilot

HoloLens 2 cihaz, Holographic sürüm 20H2'den Windows TenantLockdown CSP'yi destekler. Bu CSP, cihaz sıfırlama veya ters eğik çizgi ile bile cihazları bu kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değerine ayarlandıktan sonra, bu değer başvuruya, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

HoloLens 2'de TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü true olarak ayarlandıktan sonra, OOBE ağ bağlantısı sonrasında Autopilot profilinin başarıyla indirilme ve uygulanması için süresiz olarak bekler.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE'de aşağıdaki işlemlere izin verilmiyor:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma
- Çalışma zamanı sağlama aracılığıyla Azure AD birleştirme işlemi gerçekleştirme
- OOBE deneyiminde cihazın sahibini seçme

#### <a name="how-to-set-this-using-intune"></a>Intune kullanılarak bu nasıl ayarlanır?

1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE düğümü için true belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla tennant kilitlemeyi ayarlama.](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

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

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>Autopilot sırasında neden kaydedilmesi 0x80180014 görüyorum?

Bu, cihazdaki Autopilot işlemi sırasında gösterilen bir hatadır. gösterilen bu sorun yalnızca HoloLens bir cihaz şunları yaparken geçerlidir:

1. En az bir kez Autopilot ile zaten geçmiş.
1. Artık Autopilot için sıfırlanmakta ve yeniden kullanılabilir.

Deneyim, Autopilot deneyimidir ve belirli bir hata ile başarısız olur.

![HoloLens Autopilot hatası hata kodu](images/autopilot-0x80180014-failure.jpg)

Bu hatayı çözmek için hangi adımların alınması gerekir?

1. Cihazı Intune 'dan kaldırmak için [Autopilot cihaz içeri aktarma ve kayıt sorunlarını giderme](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) adımlarını izleyin. (Intune yöneticinizin bu görevi gerçekleştirmesi gerekir)
1. 1. adım tamamlandıktan sonra, cihazı yeniden başlatın ve oturum açın.
1. **Ayarlar**  ->  **güncelleştirme & güvenlik**  ->  **sıfırlama & kurtarma** ' ya gidin ve **kullanmaya** başlayın ' ı seçin.
    1. 2 & 3. adımlarla ilgili sorunlar varsa, [sıfırlama/Refflash HoloLens](hololens-recovery.md)cihaz sıfırlama alternatifleri bölümüne bakın.

AutoPilot ardından başarıyla kaydolmalıdır.

### <a name="troubleshooting"></a>Sorun giderme

aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot sorunlarını gidermek için yararlı bir kaynak olabilir ancak bu makaleler Windows 10 masaüstü tabanlıdır ve tüm bilgiler HoloLens için uygulanabilir.

- [Windows Autopilot-bilinen sorunlar](/mem/autopilot/known-issues)
- [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot-Ilke çakışmaları](/mem/autopilot/policy-conflicts)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Autopilot profili Intune 'A atanmış olsa da neden Autopilot deneyimini görmüyorum?

varsayılan olarak, HoloLens 2, internet algılandıktan sonra Autopilot algılamasını 15 saniye bekler. 15 saniye içinde Autopilot profili algılanmazsa, bu, Autopilot doğru bir şekilde bulunamadığına ve EULA sayfasını görürsünüz.

Cihazınızı yeniden başlatın ve yeniden deneyin. Daha fazla bilgi için bkz. [bilinen sorunlar ve sınırlamalar](hololens2-autopilot.md#known-issues-and-limitations).

## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydı desteği için satıcı veya dağıtımcı ile iletişim kurun.
- Windows Autopilot hakkında genel destek sorguları veya profil atamaları, grup oluşturma veya MEM portalı denetimleri gibi sorunlar için [desteğe başvurun Microsoft Endpoint Manager](/mem/get-support)  
- cihazınız Autopilot hizmetine kayıtlıysa ve bu profil MEM portalında atanırsa, HoloLens [desteğe](/hololens/) başvurun (bkz. ' destek ' kartı). Bir destek bileti açın ve varsa, hazır olma deneyimi (OOBE) sırasında [çevrimdışı tanılama günlüklerini](hololens-diagnostic-logs.md#offline-diagnostics) yakalayarak ekran görüntüleri ve günlükleri dahil edin.
- Cihazdan bir sorun bildirmek için HoloLens geri bildirim Merkezi uygulamasını kullanın. geri bildirim Hub 'ında **Enterprise Management**  >  **cihaz** kategorisini seçin.
- HoloLens için Autopilot hakkında genel geri bildirim sağlamak için bu [anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) gönderebilirsiniz

## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Artık Autopilot için bir cihaz kullanmak veya cihazlarınızı farklı bir kiracıya kaydetmek isteyebilirsiniz. Bunu yapmak isterseniz, [Autopilot cihazlarını silmeyi okuyun.](/mem/autopilot/add-devices#delete-autopilot-devices)
