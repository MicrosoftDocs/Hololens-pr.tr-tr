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
ms.openlocfilehash: 7dbe77c8c5999d5be1a61ca9deaa8071d152c87a
ms.sourcegitcommit: d0c7bf5b055fa1fa8ac5562eef904583a655da99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2021
ms.locfileid: "122782816"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

> [!NOTE]
> Microsoft Endpoint Manager HoloLens için Autopilot yapılandırması, genel **önizlemeden** **genel kullanıma** geçiş durumuna geçiyor. Tüm kiracılar, Autopilot 'yi MEM Yönetim merkezinde ayarlayabilecektir.

HoloLens 2 Windows Holographic sürüm 2004 ' den başlayarak, Microsoft Intune ile Windows Autopilot [kendi kendine dağıtım modunu](/mem/autopilot/self-deploying) destekler (üçüncü taraf mdms desteklenmez). yöneticiler, Microsoft Endpoint Manager içinde kullanıma hazır deneyim (OOBE) yapılandırabilir ve son kullanıcıların cihazları iş için daha fazla etkileşime sahip olmadan hazırlamasına olanak sağlayabilir. Bunu yapılandırarak, envanter yönetimi ek yükünü, uygulamalı cihaz hazırlığının maliyetini ve kurulum deneyimi sırasında çalışanların destek çağrılarını azaltır. [Windows Autopilot](/mem/autopilot/windows-autopilot) belgelerinde daha fazla bilgi edinin.

Surface cihazlarda olduğu gibi, müşterilerin iş ortağı merkezi aracılığıyla Autopilot hizmetine kayıtlı cihazları almak için Microsoft [Bulut Çözümü Sağlayıcısı](https://partner.microsoft.com/cloud-solution-provider) (satıcı veya dağıtıcı) ile çalışması önerilir. Cihaz kaydı için diğer yöntemler [cihaz ekleme](/mem/autopilot/add-devices) belgelerinde özetlenmiştir, ancak Microsoft 'un kanal iş ortakları, en etkili uçtan uca yolu sağlar.



Bir Kullanıcı Autopilot kendi kendine dağıtım işlemini başlattığında, Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirin. HoloLens için Autopilot, Active Directory joın veya hibrit Azure AD joın ' i desteklemediğini unutmayın.

1. cihazı Microsoft Endpoint Manager (veya başka bir MDM hizmeti) kaydetmek için Azure AD 'yi kullanın.

1. Cihaz hedefli ilkeleri, sertifikaları, ağ profillerini ve uygulamaları indirin ve uygulayın.

1. Cihazı sağlayın.

1. Kullanıcıya oturum açma ekranını sunun.

## <a name="configuring-autopilot-for-hololens-2"></a>HoloLens 2 için Autopilot yapılandırma

Ortamınızı ayarlamak için aşağıdaki adımları izleyin:

1. [HoloLens 2 için Windows Autopilot için gereksinimleri gözden geçirin.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Otomatik MDM kaydını etkinleştir](#2-enable-automatic-mdm-enrollment)

1. (Yalnızca Intune için) [lütfen Windows cihazlar için MDM kaydının engellenmediğinden emin olun.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [cihazları Windows Autopilot 'ye kaydedin.](#4-register-devices-in-windows-autopilot)

1. [Bir cihaz grubu oluşturun.](#5-create-a-device-group)

1. [Dağıtım profili oluşturun.](#6-create-a-deployment-profile)

1. [Kayıt durumu sayfası (ESP) yapılandırmasını doğrulayın.](#7-verify-the-esp-configuration)

1. [HoloLens cihazlarının profil durumunu doğrulayın.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. HoloLens 2 için Windows Autopilot gereksinimlerini gözden geçirin

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Windows Autopilot requirements makalesinin aşağıdaki bölümlerini gözden geçirin:

- [Ağ gereksinimleri](/mem/autopilot/networking-requirements)  
- [Lisanslama gereksinimleri](/mem/autopilot/licensing-requirements)  
- [Yapılandırma gereksinimleri](/mem/autopilot/configuration-requirements)

**Windows Autopilot Self-Deploying modu makalesinin "[gereksinimler](/windows/deployment/windows-autopilot/self-deploying#requirements)" bölümünü gözden geçirin.** ortamınızın bu gereksinimleri ve standart Windows Autopilot gereksinimlerini karşılaması de vardır. Makalenin "adım adım" ve "doğrulama" bölümlerini gözden geçirmeniz gerekmez. Bu makalede daha sonra açıklanan yordamlar HoloLens özel ilgili adımları sağlar.

Cihazların nasıl kaydedileceği ve profillerin nasıl yapılandırılacağı hakkında bilgi için bkz [. 4. Windows Autopilot ve 6 ' da cihazları kaydettirin](#4-register-devices-in-windows-autopilot) [. Bu makalede bir dağıtım profili oluşturun](#6-create-a-deployment-profile) . Autopilot kendi kendine dağıtım modu profillerini yapılandırmak ve yönetmek için [Microsoft Endpoint Manager yönetim merkezine](https://endpoint.microsoft.com)erişiminiz olduğundan emin olun.

#### <a name="review-hololens-os-requirements"></a>HoloLens işletim sistemi gereksinimlerini gözden geçirin:

- cihazların [Windows Holographic, sürüm 2004](hololens-release-notes.md#windows-holographic-version-2004) (derleme 19041,1103) veya sonraki bir sürümde olması gerekir. Cihazınızdaki derleme sürümünü doğrulamak veya en son işletim sistemine geri dönmek için, [Gelişmiş kurtarma Yardımcısı 'nı (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) ve [cihazımız, cihaz refflash yönergelerinizi](/hololens/hololens-recovery#clean-reflash-the-device)kullanın. en geç 2020 Windows Holographic sürüm 1903 önceden yüklenmiş olarak sunulan cihazların teslim edildiğini unutmayın. Autopilot-Ready cihazların size sevk edilmesini sağlamak için satıcınıza başvurun.

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

Kurulumu daha fazla bilgi edinmek için [MDM otomatik kaydını](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) veya [otomatik kayıt hızlı başlangıç kılavuzunu](/mem/intune/enrollment/quickstart-setup-auto-enrollment) etkinleştirmek üzere aşağıdaki kısa kılavuzu gözden geçirin.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Windows cihazlar için MDM kaydının engellenmediğinden emin olun.

Autopilot 'in başarılı olması için HoloLens cihazlarınızın kaydolmasını sağlayabilirsiniz. HoloLens Windows bir cihaz olarak değerlendirildiğinden, dağıtımınızı engelleyebilen bir kayıt kısıtlaması olmaması gerekir. [Bu kısıtlamalar listesini gözden geçirin](/mem/intune/enrollment/enrollment-restrictions-set) ve cihazlarınızı kaydedeceksiniz emin olun.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Windows Autopilot cihazları kaydetme

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

   1. Tam ayrıntılar ve bu, [çevrimdışı tanılama](hololens-diagnostic-logs.md#offline-diagnostics)hakkında bilgi edinin hakkında daha fazla bilgi için bkz..

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
   > ![Donanım karmasını içeri aktarmak için Al komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. içeri aktarma tamamlandıktan sonra **cihaz**  >  **Windows**  >  **Windows kayıt**  >  **cihazları**  >  **eşitleme**' yi seçin. Kaç cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakika sürebilir. Kayıtlı cihazı görmek için **Yenile**' yi seçin.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. bir cihaz grubu oluşturun

1. [Microsoft Endpoint Manager yönetim merkezi](https://endpoint.microsoft.com)'nde **gruplar**  >  **yeni grup**' u seçin.

1. **Grup türü** için **güvenlik**' i seçin ve ardından bir grup adı ve açıklama girin.

1. **Üyelik türü** için **atanan** ya da **dinamik cihaz**' ı seçin.

1. Aşağıdakilerden birini yapın:  

   - Önceki adımda **üyelik türü** için **atandı** ' ı seçtiyseniz **Üyeler**' i seçin ve ardından gruba Autopilot cihazları ekleyin. Henüz kayıtlı olmayan Autopilot cihazlar cihaz adı olarak cihaz seri numarası kullanılarak listelenir.
   - Önceki adımda **üyelik türü** Için **dinamik cihazlar** ' ı seçtiyseniz, **dinamik cihaz üyeleri**' ni seçin ve ardından aşağıdaki gibi **Gelişmiş kuralda** kodu girin:
     - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız şunu yazın: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 'un Grup etiketi alanı, Azure AD cihazlarındaki **OrderID** özniteliğiyle eşlenir. Belirli bir grup etiketine sahip tüm Autopilot cihazlarınızı (Azure AD cihaz OrderID) içeren bir grup oluşturmak istiyorsanız şunu yazmanız gerekir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Belirli bir satın alma siparişi KIMLIĞINE sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız şunu yazın: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Bu kurallar, Autopilot cihazlarına özgü öznitelikleri hedef olarak hedefler.
1. **Kaydet**' i seçin ve ardından **Oluştur**' u seçin.

### <a name="6-create-a-deployment-profile"></a>6. dağıtım profili oluşturma

1. [Microsoft Endpoint Manager yönetim merkezi](https://endpoint.microsoft.com)'nde Windows **cihazlar**' ı seçin  >    >  **Windows kayıt**  >  **Windows Autopilot dağıtım profilleri**  >  **profil oluştur**  >  **HoloLens**.
   ![profil oluştur açılır listesi bir HoloLens öğesi içerir.](./images/hololens-ap-enrollment-profiles.png)

1. Bir profil adı ve açıklama girin ve ardından **İleri**' yi seçin.  
   **HoloLens** içeren bir liste görmeniz gerekir. Bu seçenek yoksa, bizimle iletişim kurmak için [geri bildirim](hololens2-autopilot.md#feedback-and-support-for-autopilot) seçeneklerinden birini kullanın.

   > [!div class="mx-imgBorder"]
   > ![Profil adı ve açıklaması ekleyin](./images/hololens-ap-profile-name.png)

1. **Kullanıma hazır deneyim (OOBE)** sayfasında, ayarların çoğu bu DEĞERLENDIRME için OOBE 'yi kolaylaştırmak üzere önceden yapılandırılmıştır. İsteğe bağlı olarak, aşağıdaki ayarları yapılandırabilirsiniz:  

   - **Dil (bölge)**: OOBE dilini seçin. [HoloLens 2 için desteklenen diller](hololens2-language-support.md)listesinden bir dil seçmenizi öneririz.
   - **Klavyeyi otomatik olarak Yapılandır**: klavyenin seçili dille eşleştiğinden emin olmak için **Evet**' i seçin.
   - **Cihaz adı şablonu Uygula**: OOBE sırasında cihaz adını otomatik olarak ayarlamak için **Evet** ' i seçin ve ardından **bir ad girin** alanına şablon tümceciğini ve yer tutucuları girin. Örneğin, `%RAND:4%` &mdash; dört basamaklı rastgele bir sayı için bir ön ek ve yer tutucu girin.
     > [!NOTE]  
     > Bir cihaz adı şablonu kullanırsanız, OOBE işlemi cihaz adını uyguladıktan sonra ve cihazı Azure AD 'ye katmadan önce ek bir süre sonra yeniden başlatır. Bu yeniden başlatma, yeni adın geçerli olması için etkin bir ad sağlar.  

   > [!div class="mx-imgBorder"]
   > ![OOBE ayarlarını yapılandırma](./images/hololens-ap-profile-oobe.png)

1. Ayarları yapılandırdıktan sonra **İleri**' yi seçin.
1. **Kapsam etiketleri** sayfasında isteğe bağlı olarak, bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](/mem/intune/fundamentals/scope-tags.md). İşiniz bittiğinde **İleri**' yi seçin.
1. **Atamalar** sayfasında, **ata** için **Seçili gruplar** ' ı seçin.
1. **SEÇILI gruplar** altında **+ dahil edilecek grupları** Seç ' i seçin.
1. **dahil edilecek grupları seçin** listesinde, Autopilot HoloLens cihazları için oluşturduğunuz cihaz grubunu seçin ve ardından **ileri**' yi seçin.  
  
   Herhangi bir grubu dışlamak istiyorsanız, **hariç tutulacak grupları** seçin ' i seçin ve dışlamak istediğiniz grupları seçin.

   > [!div class="mx-imgBorder"]
   > ![Profile bir cihaz grubu atanıyor.](./images/hololens-ap-profile-assign-devicegroup.png)

1. **Gözden geçir + oluştur** sayfasında, ayarları gözden geçirin ve sonra profili oluşturmak için **Oluştur** ' u seçin.  

   > [!div class="mx-imgBorder"]
   > ![Gözden geçirme ve oluşturma](./images/hololens-ap-profile-summ.png)

### <a name="7-verify-the-esp-configuration"></a>7. ESP yapılandırmasını doğrulayın

Kayıt durumu sayfası (ESP), MDM ile yönetilen bir Kullanıcı bir cihazda ilk kez oturum açtığında çalışan tüm cihaz yapılandırma sürecinin durumunu görüntüler. ESP yapılandırmanızın aşağıdakine benzer olduğundan emin olun ve atamaların doğru olduğunu doğrulayın.  

> [!div class="mx-imgBorder"]
> ![ESP yapılandırması](./images/hololens-ap-profile-settings.png)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. HoloLens cihazların profil durumunu doğrulayın

1. Microsoft Endpoint Manager yönetim merkezi 'nde **cihazlar**  >    >  **Windows kayıt**  >  **cihazları** Windows ' nı seçin.

1. HoloLens cihazların listelendiğini ve profil durumunun **atandığını** doğrulayın.  

   > [!NOTE]  
   > Profilin cihaza atanması birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 kullanıcı deneyimi için Autopilot

yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcılarınız HoloLens cihazlarını sağlamak için aşağıdaki deneyimden geçer:  

1. Autopilot deneyimi Internet erişimi gerektirir. Internet erişimi sağlamak için aşağıdaki seçeneklerden birini kullanın:

    - Bağlan, bir Wi-Fi ağa OOBE 'de ve sonra otomatik olarak Autopilot deneyimini algılamasına izin verin. Bu, Autopilot deneyimi kendi kendine tamamlanana kadar OOBE ile etkileşimde bulunmak için tek zaman gerekir. lütfen varsayılan HoloLens 2 ' nin ınternet 'i algıladıktan sonra Autopilot algılamasını unutmayın. 10 saniye içinde Autopilot profili algılanmazsa, OOBE EULA sunacaktır. Bu senaryoya karşılaşıyorsanız, Autopilot algılamak için lütfen cihazınızı yeniden başlatın. Ayrıca, bir cihazda yalnızca TenantLockdown ilkesi ayarlandıysa, OOBE 'nin Autopilot için süresiz olarak beklemeleri gerektiğini unutmayın.

    - kablolu internet bağlantısı için "USB-C-Ethernet" bağdaştırıcılarını kullanarak Ethernet ile cihazınızı Bağlan ve HoloLens 2 tam Autopilot deneyimini otomatik olarak sağlayın.

    - kablosuz internet bağlantısı için cihazınızı "USB-C-Wi-Fi" bağdaştırıcılarına Bağlan ve HoloLens 2 tam Autopilot deneyimini otomatik olarak sağlayın.

        > [!IMPORTANT]  
       > Autopilot için OOBE 'de Wi-Fi ağlarını kullanmaya çalışan cihazların [, Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2)üzerinde olması gerekir.
       >
       > Ethernet bağdaştırıcılarını kullanan cihazlarda, Ilk çalıştırma deneyimi (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranındaki bir Autopilot cihazı olarak sağlanıp sağlanmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı bir Autopilot cihazı olarak sağlamayı tercih ediyorsanız, daha sonra Autopilot sağlamaya geçiş yapılamaz. Bunun yerine, cihazı bir Autopilot cihazı olarak sağlamak için bu yordamı yeniden başlatmanız gerekir.

1. Cihazın otomatik olarak OOBE başlatması gerekir. OOBE ile etkileşim kurma.

    > [!IMPORTANT]
    > Lütfen Autopilot devam ederken, sistemi bekleme/kapatma durumuna getirmek için OOBE ile etkileşime girmeyin veya güç düğmesine basın. Bu, Autopilot akışının tamamlanmamasına neden olabilir.

   HoloLens 2 ' nin ağ bağlantısını algılaması ve OOBE 'nin otomatik olarak tamamlanmasına izin verin. Cihaz, OOBE sırasında yeniden başlatılabilir. OOBE ekranları aşağıdakine benzemelidir.

   ![OOBE adım 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE adım 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE adım 3](./images/autopilot-device-setup.jpg)

1. OOBE 'nin sonunda, Kullanıcı adınızı ve parolanızı kullanarak cihazda oturum açabilirsiniz.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

HoloLens 2 cihaz, Windows Holographic, sürüm 20h2 itibariyle tenantlockdown CSP 'yi destekler. Bu CSP, cihaz sıfırlama veya refflash aracılığıyla bile, kuruluşun kiracısında cihazları bu kiracıya kilitleyerek korur.

[Tenantlockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. bir tenantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer, zaman damgası, işletim sistemi güncelleştirmeleri vb. olarak cihazda kalır.

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, ağ bağlantısından sonra OOBE, Autopilot profilinin başarıyla indirilip uygulanmasını bekler.

tenantlockdown csp 'ler ' talep ırenetworkınoobe düğümü HoloLens 2 ' de true olarak ayarlandığında, OOBE 'de aşağıdaki işlemlere izin verilmez:

- Çalışma zamanı sağlamayı kullanarak yerel kullanıcı oluşturma 
- Çalışma zamanı sağlama aracılığıyla Azure AD JOIN işlemi gerçekleştiriliyor 
- Cihaza kimin sahip olduğunu OOBE deneyiminde seçme 

#### <a name="how-to-set-this-using-intune"></a>Bu Intune kullanılarak nasıl ayarlanır? 
1. Özel bir OMA URI cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe düğümü için true değerini belirtin.
OMA-URI değeri olmalıdır./Vendor/MSFT/tenantlockdown/karşılandığından ırenetworkınoobe

   > [!div class="mx-imgBorder"]
   > ![OMA-URI aracılığıyla kiracı kilidi ayarlanıyor](images/hololens-tenant-lockdown.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna atayın.

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazında başarıyla uygulandığında TenantLockdown'ın etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Intune kullanarak TenantLockdown'ın RequireNetworkInOOBE HoloLens 2'nin kümesi nasıl geri alır?

1. Yukarıda HoloLens yapılandırmasının daha önce atandığı cihaz grubundan 2. kümeyi kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi RequireNetworkInOOBE için false belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Autopilot profili bir HoloLens OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilene kadar süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir.

![Cihazda ilkenin ne zaman zorlanan cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Bilinen Sorunlar & sınırlamaları

- MEM'de yapılandırılan cihaz bağlamı tabanlı uygulama yüklemenin uygulama yüklemesi için geçerli HoloLens. [Cihaz bağlamı ve kullanıcı bağlamı yüklemeleri hakkında daha fazla bilgi edinebilirsiniz.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Autopilot'ı Wi-Fi üzerinden ayarlarken, İnternet bağlantısı ilk kez kurulurken Autopilot profilinin indirilemedikleri bir örnek olabilir. Bu durumda Son Kullanıcı Lisans Sözleşmesi (EULA) sunulmuştur ve kullanıcının Autopilot olmayan kurulum deneyimine devam edebilirsiniz. Autopilot ile ayarlamayı yeniden denemek için cihazı uykuya bırakın ve cihazı açın veya yeniden başlatın ve yeniden deneyin.
- "Tüm hedeflenen cihazları Autopilot'a dönüştür" özelliği şu anda HoloLens için desteklenmiyor.  

### <a name="troubleshooting"></a>Sorun giderme

Aşağıdaki makaleler daha fazla bilgi edinmek ve Autopilot Sorunlarını gidermek için yararlı bir kaynak olabilir, ancak bu makalelerin Windows 10 Desktop'a dayalı olduğunu ve tüm bilgilerin aşağıdakiler için geçerli HoloLens:

- [Windows Autopilot - bilinen sorunlar](/mem/autopilot/known-issues)
- [Windows cihaz kaydı sorunlarını Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - İlke Çakışmaları](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydıyla ilgili destek için lütfen satıcınıza veya dağıtımcınıza başvurun.
- Windows Autopilot ile ilgili genel destek sorguları veya profil atamaları, grup oluşturma veya MEM portalı denetimleri gibi sorunlar için lütfen destek Microsoft Endpoint Manager [başvurun](/mem/get-support)  
- Cihazınız Autopilot hizmetine kayıtlı ve profil MEM portalında atanmışsa, HoloLens [](/hololens/) (bkz. 'Destek' kartı). Lütfen bir destek bileti açın ve varsa, ilk deneyim [](hololens-diagnostic-logs.md#offline-diagnostics) (OOBE) sırasında çevrimdışı tanılama günlüklerini yakalayarak ekran görüntülerini ve günlükleri dahil edin.
- Cihazdan bir sorun rapor etmek için Geri Bildirim Merkezi uygulamanıza HoloLens. Bu Geri Bildirim Merkezi Yönetim Cihazı **Enterprise**  >  **seçin.**
- Autopilot'ta HoloLens sağlamak için bu anketi [gönderebilirsiniz](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Artık Autopilot için bir cihaz kullanmak veya cihazlarınızı farklı bir kiracıya kaydetmek zorunda kalmayabilirsiniz. Bunu yapmak için Autopilot cihazlarını silmek[için how okuyun.](/mem/autopilot/add-devices#delete-autopilot-devices)