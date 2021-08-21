---
title: HoloLens 2 için Windows Autopilot
description: HoloLens 2 cihazlarındaki Autopilot ayarlama, yapılandırma ve sorun giderme hakkında bilgi edinin.
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
keywords: Autopilot
manager: jarrettr
ms.openlocfilehash: b8bfa5359436151bcae9579c78674a93ae0db88d
ms.sourcegitcommit: dab46153e0948310a96b1a6f47d788b7130cfa14
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2021
ms.locfileid: "122620820"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

> [!NOTE]
> Microsoft Endpoint Manager HoloLens için Autopilot yapılandırması, genel **önizlemeden** **genel kullanıma** geçiş durumuna geçiyor. Tüm kiracılar, Autopilot 'yi MEM Yönetim merkezinde ayarlayabilecektir.

HoloLens 2 Windows Holographic sürüm 2004 ' den başlayarak, Microsoft Intune ile Windows Autopilot [kendi kendine dağıtım modunu](/mem/autopilot/self-deploying) destekler (üçüncü taraf mdms desteklenmez). yöneticiler, Microsoft Endpoint Manager içinde kullanıma hazır deneyimi (OOBE) yapılandırabilir ve son kullanıcıların cihazları iş için daha fazla etkileşime sahip olmayan şekilde hazırlamasına olanak sağlayabilir. Bu, envanter yönetimi ek yükünü, uygulamalı cihaz hazırlığının maliyetini ve kurulum deneyimi sırasında çalışanların destek çağrılarını azaltır. [Windows Autopilot](/mem/autopilot/windows-autopilot) belgelerinde daha fazla bilgi edinin.

Surface cihazlarda olduğu gibi, müşterilerin iş ortağı merkezi aracılığıyla Autopilot hizmetine kayıtlı cihazları almak için Microsoft [Bulut Çözümü Sağlayıcısı](https://partner.microsoft.com/cloud-solution-provider) (satıcı veya dağıtıcı) ile çalışması önerilir. Cihaz kaydı için diğer yöntemler [cihaz ekleme](/mem/autopilot/add-devices) belgelerinde özetlenmiştir, ancak Microsoft 'un kanal iş ortaklarının en etkili uçtan uca yolunu sağlar.



Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattığında, Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin. HoloLens için Autopilot, Active Directory joın veya hibrit Azure AD joın ' i desteklemediğini unutmayın.

1. cihazı Microsoft Endpoint Manager (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulayın.

1. Cihazı sağlayın.

1. Kullanıcıya oturum açma ekranını sunun.

## <a name="configuring-autopilot-for-hololens-2"></a>HoloLens 2 için Autopilot yapılandırma

Ortamınızı ayarlamak için lütfen aşağıdaki adımları izleyin:

1. [HoloLens 2 için Windows Autopilot için gereksinimleri gözden geçirin.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydını etkinleştir](#2-enable-automatic-mdm-enrollment)

1. [cihazları Windows Autopilot 'ye kaydedin.](#3-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#4-create-a-device-group)

1. [Dağıtım profili oluşturun.](#5-create-a-deployment-profile)

1. [Kayıt durumu sayfası (ESP) yapılandırmasını doğrulayın.](#6-verify-the-esp-configuration)

1. [HoloLens cihazlarının profil durumunu doğrulayın.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. HoloLens 2 için Windows Autopilot gereksinimlerini gözden geçirin

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot requirements makalesinin aşağıdaki bölümlerini gözden geçirin:

- [Ağ gereksinimleri](/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying modu makalesinin "[gereksinimler](/windows/deployment/windows-autopilot/self-deploying#requirements)" bölümünü gözden geçirin.** ortamınızın bu gereksinimleri ve standart Windows Autopilot gereksinimlerini karşılaması de vardır. Makalenin "adım adım" ve "doğrulama" bölümlerini gözden geçirmeniz gerekmez. Bu makalede daha sonra açıklanan yordamlar HoloLens özel ilgili adımları sağlar.

Cihazların nasıl kaydedileceği ve profillerin nasıl yapılandırılacağı hakkında bilgi için, bkz [. 2. Windows Autopilot ve 4 ' te cihazları kaydettirin](#3-register-devices-in-windows-autopilot) [. Bu makalede bir dağıtım profili oluşturun](#5-create-a-deployment-profile) . Autopilot kendi kendine dağıtım modu profillerini yapılandırmak ve yönetmek için [Microsoft Endpoint Manager yönetim merkezine](https://endpoint.microsoft.com)erişiminiz olduğundan emin olun.

#### <a name="review-hololens-os-requirements"></a>HoloLens işletim sistemi gereksinimlerini gözden geçirin:

- cihazların [Windows Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) (derleme 19041,1103) veya sonraki bir sürümde olması gerekir. Cihazınızdaki derleme sürümünü doğrulamak veya en son işletim sistemine yeniden Flash 'u yeniden açmak için [Gelişmiş kurtarma Yardımcısı 'nı (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) ve [cihazımızı yeniden Flash yönergelerinizi](/hololens/hololens-recovery#clean-reflash-the-device)kullanın. en geç 2020 Windows Holographic sürüm 1903 önceden yüklenmiş olarak sunulan cihazların teslim edildiğini unutmayın. Autopilot-Ready cihazların size sevk edilmesini sağlamak için lütfen satıcınızla iletişime geçin.

- Windows Holographic, sürüm 2004 yalnızca Ethernet bağlantısı üzerinden Autopilot destekler. açmadan **önce**, HoloLens "USB-C-ethernet" bağdaştırıcısı kullanılarak ethernet 'e bağlı olduğundan emin olun. Cihaz önyüklemesi sonrasında Kullanıcı etkileşimi gerekmez. birçok HoloLens cihaza bir Autopilot toplaması planlıyorsanız, bağdaştırıcı altyapısını planlamanız önerilir. Genellikle HoloLens desteklenmeyen ek üçüncü taraf sürücülerin yüklenmesi gerektiği için, USB hub 'Ları önermiyoruz.

- [Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041,1128) veya daha sonraki bir sürümü Wi-Fi üzerinden Autopilot destekler, ancak yine de ethernet bağdaştırıcılarını kullanmaya devam edebilirsiniz. Wi-Fi ile bağlanan cihazlar için, Kullanıcı yalnızca şunları içermelidir:

     - Hummingbird sahneden geçin
     - Dili ve yerel ayarı seçin
     - Göz ayarlamayı Çalıştır
     - Ağ bağlantısı kurma

- Windows Holographic, 20H2 sürümü, bir cihazı kiracıya kilitleyen ve cihazın yanlışlıkla veya kasıtlı olarak sıfırlamaları veya wpes durumunda bu kiracıya bağlanmasını sağlamak için [Tenantlockdown CSP ve Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)'yi destekler.  

- Cihazların zaten Azure AD üyesi olmadığından ve Intune 'A (veya başka bir MDM sistemine) kaydolmadığından emin olun. Autopilot kendi kendine dağıtım işlemi, bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlendiğinden emin olmak için hem Azure AD hem de Intune portallarındaki **cihazlar** sayfalarını denetleyin. "tüm hedeflenen cihazları Autopilot 'e dönüştür" özelliğinin şu anda HoloLens desteklenmediğini unutmayın.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. otomatik MDM kaydını etkinleştirin:

Autopilot başarılı olabilmesi için Azure portal otomatik MDM kaydını etkinleştirmeniz gerekir. Bu, cihazın kullanıcı olmadan kaydolmasını sağlar.

[Azure portal](https://portal.azure.com/#home) **Azure Active Directory**  ->  **Mobility (MDM ve MAM)**  ->  **Microsoft Intune** seçin. Sonra **MDM Kullanıcı kapsamını** yapılandırın, **Tümü** seçeneğini belirlemeniz gerekir.

Daha fazla bilgi için bkz. [MDM otomatik kaydını etkinleştirme](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) veya [otomatik kayıt Hızlı Başlangıç Kılavuzu ' nu](/mem/intune/enrollment/quickstart-setup-auto-enrollment) etkinleştirmek için lütfen aşağıdaki kısa kılavuzu inceleyin.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Windows Autopilot 'de cihazları kaydetme

cihazlarınız ilk kurulumdan önce Windows Autopilot kayıtlı olmalıdır. Cihaz kaydı ile ilgili MEM belgeleri için lütfen bkz. [Autopilot 'e cihaz ekleme](/mem/autopilot/add-devices).  

HoloLens cihazları kaydetmek için üç temel yol vardır:

 - **Satıcı, bir sipariş yerleştirdiğinizde cihazları Iş Ortağı Merkezi 'ne kaydedebilir.**

   > [!NOTE]  
   > Bu, Autopilot hizmetine cihaz eklemek için önerilen yoldur. [Daha fazla bilgi edinin](/mem/autopilot/partner-registration).  

 - **[Destek isteğini](hololens2-autopilot-registration-support.md) doğrudan Microsoft 'a gönderebilirsiniz.**
 - **Donanım karmasını (donanım kimliği olarak da bilinir) alın ve aygıtı, mem yönetim merkezine el ile kaydedin**.

#### <a name="obtain-hardware-hash"></a>Donanım karmasını al
Donanım karmasını almanın iki yolu vardır.
1. [Destek isteğini](hololens2-autopilot-registration-support.md) doğrudan Microsoft 'a gönderebilirsiniz.
2. Bunu cihazdan alabilirsiniz. Cihaz, OOBE işlemi sırasında bir CSV dosyasında donanım karmasını kaydeder veya bir cihaz sahibi tanılama günlüğü toplama işlemini başlattığında (aşağıdaki yordamda açıklanmaktadır). Genellikle cihaz sahibi cihazda oturum açmak için ilk Kullanıcı olur.
     > [!WARNING]
     > 20H2 ' den önceki derlemelerde, OOBE 'den çıkıldıysanız ve telemetri gerekli olarak ayarlandıysa, bu yöntem aracılığıyla Autopilot için donanım karmasını toplayamazsınız. bu yöntem aracılığıyla donanım karmalarınızın toplanması için telemetri seçeneğinizi Ayarlar uygulaması aracılığıyla tam olarak ayarlayın ve gizlilik-> tanılama ' yı seçin.

    1. HoloLens 2 cihazını başlatın.

    1. Cihazda, **Güç** ve **ses azaltma** düğmelerine aynı anda basın ve ardından onları serbest bırakın. Cihaz tanılama günlüklerini ve donanım karmasını toplar ve bunları bir dizi .zip dosya halinde depolar.

   1. Bu, tam ayrıntılar ve bu işlemi önceden oluşturma hakkında bilgi edinmek için lütfen [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)hakkında bilgi edinin.

    1. Cihazı bir bilgisayara bağlamak için USB-C kablosu kullanın.

    1. Bilgisayarda dosya Gezgini ' ni açın. **bu PC \\ \<*HoloLens device name*> \\ iç Depolama \\ belgelerini** açın ve AutopilotDiagnostics.zip dosyasını bulun.  

       > [!NOTE]  
       > .zip dosyası hemen kullanılamıyor olabilir. Dosya henüz hazırsanız belgeler klasöründe bir HoloLensDiagnostics. temp dosyası görebilirsiniz. Dosya listesini güncelleştirmek için pencereyi yenileyin.
    
    1. AutopilotDiagnostics.zip dosyasının içeriğini ayıklayın.

    1. Ayıklanan dosyalarda, "DeviceHash" dosya adı ön ekine sahip CSV dosyasını bulun. Bu dosyayı, daha sonra erişebileceğiniz bilgisayardaki bir sürücüye kopyalayın.  

       > [!IMPORTANT]  
       > CSV dosyasındaki veriler aşağıdaki üstbilgiyi ve satır biçimini kullanmalıdır:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Cihazı bellek ile kaydetme

1. [Microsoft Endpoint Manager yönetim merkezi](https://endpoint.microsoft.com)'nde **cihazları**  >  **Windows**  >  **Windows kayıt**' ı seçin ve ardından   >  **Windows Autopilot Deployment Program** altında cihazlar **içeri aktar** ' ı seçin.

1. **Windows Autopilot cihazları ekle** altında devicehash CSV dosyasını seçin, **aç**' ı seçin ve ardından **içeri aktar**' ı seçin.  

   > [!div class="mx-imgBorder"]
   > ![Donanım karması içeri aktar için İçeri Aktar komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. İçeri aktarma işlemi tamam olduktan sonra Devices  >  **Windows Windows**  >    >  **'ı**  >  **seçin.** Kaç cihaz eşitlenmesine bağlı olarak işlem birkaç dakika sürebilir. Kayıtlı cihazı görmek için Yenile'yi **seçin.**  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Cihaz grubu oluşturma

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

### <a name="5-create-a-deployment-profile"></a>5. Dağıtım profili oluşturma

1. Yönetim [Microsoft Endpoint Manager Autopilot dağıtım](https://endpoint.microsoft.com)profilleri **Profil**  >  **Windows**  >  **Windows'Windows** için Cihazlar'ı  >    >    >  HoloLens.
   ![Profil oluştur açılan listesinde bir HoloLens vardır.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından Sonraki'yi **seçin.**  
   listesini içeren bir liste **HoloLens.** Bu seçenek yoksa Geri bildirim seçenekleriyle bize [ulaşın.](hololens2-autopilot.md#feedback-and-support-for-autopilot)

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklama ekleme](./images/hololens-ap-profile-name.png)

1. İlk **deneyim (OOBE)** sayfasında, ayarların çoğu bu değerlendirme için OOBE'yi kolaylaştıracak şekilde önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (Bölge):** OOBE için dili seçin. 2 için desteklenen diller [listesinden bir dil HoloLens öneririz.](hololens2-language-support.md)
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

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Cihaz profili HoloLens doğrulama

1. Yönetim Microsoft Endpoint Manager'nde Cihazlar'ı **ve**  >  **Windows**  >  **Windows'ı**  >  **seçin.**

1. Uygulama cihazlarının HoloLens ve profil durumlarının Atandı olduğunu **doğrulayın.**  

   > [!NOTE]  
   > Profilin cihaza atanmaları birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 Kullanıcı Deneyimi için Autopilot

Yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcınız aşağıdaki deneyimi izleyerek kendi HoloLens sağlar:  

1. Autopilot deneyimi için İnternet erişimi gerekir. İnternet erişimi sağlamak için lütfen aşağıdaki seçeneklerden birini kullanın:

    - Bağlan OOBE'Wi-Fi bir ağ üzerinden çalıştırın ve autopilot deneyimini otomatik olarak algılamasına izin verir. Autopilot deneyimi kendi kendine tamamlayana kadar OOBE ile yalnızca bu kez etkileşim kurmanız gerekir. İnternet algılayan autopilot'HoloLens algılamak için varsayılan olarak 2'nin 10 saniye beklemesi gerekir. 10 saniye içinde bir otomatik pilot profili algılanmazsa OOBE EULA'yı sunacak. Bu senaryoyla karşılaşırsanız, Autopilot'ın algılanabilir olması için cihazınızı yeniden başlatın. Ayrıca, OOBE'nin Autopilot için süresiz olarak yalnızca cihazda TenantLockdown ilkesi ayarlanmışsa bekleyebilir.

    - Bağlan İnternet bağlantısı için "USB-C'den Ethernet'e" bağdaştırıcıları kullanarak Ethernet ile cihazınızı bağlayın ve otomatik olarak 2 tam Autopilot deneyimi HoloLens izin verir.

    - Bağlan kablosuz İnternet bağlantısı için "USB-C'den Wifi'ye" bağdaştırıcıları kullanarak cihazınızı otomatik olarak 2 HoloLens Autopilot deneyimine izin verir.

        > [!IMPORTANT]  
       > Autopilot için OOBE'de Wi-Fi ağları kullanmaya çalışan cihazların [Holographic sürüm 20H2'de Windows olması gerekir.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > Ethernet bağdaştırıcıları kullanan cihazlar için, İlk-Kutu Deneyimi (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranında autopilot cihaz olarak sağ isteyip sağlama olmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı Autopilot cihazı olarak sağlamayı seçmiyorsanız, daha sonra Autopilot sağlama olarak değiştiremezsiniz. Bunun yerine, cihazı Autopilot cihazı olarak sağlama amacıyla bu yordamı baştan başlatmanız gerekir.

1. Cihazın OOBE'i otomatik olarak başlatması gerekir. OOBE ile etkileşim kurma.

    > [!IMPORTANT]
    > Otomatik pilot devam ederken, sistemi bekleme/kapatma moduna getirmek için lütfen OOBE ile etkileşime geçmeyin veya güç düğmesine basın. Bu, otomatik pilot akışının tamamlanmayacak şekilde tamamlanmasına neden olabilir.

   Ağ HoloLens 2'nin ağ bağlantısını algılamasına ve otomatik olarak OOBE'nin tamamlanmasına izin ver. Cihaz OOBE sırasında yeniden başlatabilirsiniz. OOBE ekranları aşağıdakine benzer.

   ![OOBE adım 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE adım 3](./images/autopilot-device-setup.jpg)

1. OOBE'nin sonunda kullanıcı adı ve parolanızı kullanarak cihazda oturum açın.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

HoloLens 2 cihaz, Holographic sürüm 20H2'den Windows TenantLockdown CSP'yi destekler. Bu CSP, cihaz sıfırlama veya ters eğik çizgi ile bile cihazları bu kiracıya kilitleyerek kuruluşun kiracısı üzerinde tutar.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2'nin yalnızca Autopilot kullanılarak MDM kaydına bağlı olması için olanak sağlar. TenantLockdown CSP'nin RequireNetworkInOOBE düğümü HoloLens 2'de true veya false (başlangıçta ayarlanmış) değerine ayarlandıktan sonra, bu değer yeniden yanıp sönmeye, işletim sistemi güncelleştirmelerine vb. rağmen cihazda kalır.

TenantLockdown CSP'lerinin RequireNetworkInOOBE düğümü HoloLens 2'de true olarak ayarlandıktan sonra, OOBE ağ bağlantısı sonrasında Autopilot profilinin başarıyla indirilme ve uygulanması için süresiz olarak bekler.

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

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır?

1. Yukarıda HoloLens yapılandırmasının daha önce atandığı cihaz grubundan 2. kümeyi kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe için false belirtin.
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