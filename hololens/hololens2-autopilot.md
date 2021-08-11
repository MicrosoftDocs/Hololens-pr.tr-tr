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
ms.openlocfilehash: 7438b147a31ff38233412a4213a568286fb2e3b8982bc4fd6af3f9dde842fd1a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662620"
---
# <a name="windows-autopilot-for-hololens-2"></a>HoloLens 2 için Windows Autopilot

> [!NOTE]
> Microsoft Endpoint Manager'da HoloLens için Autopilot yapılandırması Genel Önizleme'den Genel **Kullanılabilirlik'e geçişte.**  Tüm kiracılar, MEM yönetim merkezinde Autopilot'u kurabilecek.

Windows Holographic sürüm 2004'den itibaren HoloLens 2, Windows [Autopilot](/mem/autopilot/self-deploying) Self Servis Dağıtım Modunu Microsoft Intune ile destekler (3. taraf MDM'ler desteklanmaz). Yöneticiler, Microsoft Endpoint Manager'da ilk kullanım deneyimini (OOBE) yapılandırarak son kullanıcıların çok az etkileşimle veya hiç etkileşim olmadan cihazları iş kullanımına hazırlamasını sağlar. Bu, kurulum deneyimi sırasında çalışanlardan gelen stok yönetimi ek yükünü, cihaz hazırlığı ve destek çağrılarının maliyetini azaltır. Daha fazla bilgi için [Windows Autopilot belgelerine](/mem/autopilot/windows-autopilot) bakın.

Surface cihazlarında olduğu gibi, müşterilerin de microsoft Bulut Çözümü Sağlayıcısı (kurumsal bayi [veya](https://partner.microsoft.com/cloud-solution-provider) dağıtımcı) ile birlikte çalışması ve bu cihazlarla autopilot hizmetine kayıtlı cihazları İş Ortağı Merkezi. Cihaz kaydına ilişkin diğer yöntemler [](/mem/autopilot/add-devices) cihaz ekleme belgelerinde açıklanmıştır, ancak Microsoft'un kanal iş ortaklarından yararlanarak en etkili bitiş yolu garanti altına alınmaktadır.



Bir kullanıcı Autopilot kendi kendine dağıtım işlemini başlatırsa Autopilot aşağıdaki adımları tamamlar:

1. Cihazı Azure Active Directory (Azure AD) ile birleştirme. HoloLens için Autopilot'ın Active Directory'ye katılmayı veya Hibrit Azure AD'ye katılmayı desteklemez.

1. Cihazı Microsoft Endpoint Manager (veya başka bir MDM hizmetine) kaydetmek için Azure AD'i kullanın.

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

- Cihazlar [Holographic, Windows 2004 (derleme 19041.1103)](hololens-release-notes.md#windows-holographic-version-2004) veya sonraki bir sürümde olmalı. Cihazınızın derleme sürümünü onaylamak veya en son işletim sistemiyle yeniden flash kullanmak için Gelişmiş Kurtarma Yardımcı [(ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) ve cihazı yeniden [flash yönergelerini kullanın.](/hololens/hololens-recovery#clean-reflash-the-device) Eylül 2020'nin sonlarına kadar teslim edilen cihazlarda Holographic Windows 1903'ün önceden yüklü olduğunu unutmayın. Autopilot'a hazır cihazların size gönderiliyor olduğundan emin olmak için lütfen kurumsal bayinizle iletişime geçin.

- Windows Holographic sürüm 2004 yalnızca Ethernet bağlantısı üzerinden Autopilot'u destekler. Cihazı HoloLens önce "USB-C'den Ethernet'e" bağdaştırıcısı kullanarak **Ethernet'e bağlı olduğundan emin olun.** Cihaz önyüklemesi sırasında kullanıcı etkileşimi gerekmez. Autopilot'ın birçok farklı cihaza HoloLens, bağdaştırıcı altyapısını planlamanız önerilir. USB Hub'ları önerilmez çünkü bunlar genellikle ek üçüncü taraf sürücülerin yüklü olması gerektirir ve bu sürücüler HoloLens.

- [Windows Holographic sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (derleme 19041.1128) veya sonraki sürümler Wi-Fi üzerinden Autopilot'ı destekler, ancak yine de Ethernet bağdaştırıcıları kullanabilirsiniz. Wi-Fi üzerinden bağlanan cihazlar için kullanıcının yalnızca:

     - Kuş sahnelerini inceleme
     - Dili ve yerel dili seçin
     - Göz ayarlamayı çalıştırma
     - Ağ bağlantısı kurma

- Windows Holographic sürüm 20H2, bir cihazı bir kiracıya kilitleyen ve yanlışlıkla veya kasıtlı sıfırlama veya silme durumunda cihazın o kiracıya bağlı kalmasını sağlayan [Tenantlockdown CSP](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)ve Autopilot'ı destekler.  

- Cihazların zaten Azure AD'ye üye olduğundan ve Intune'a (veya başka bir MDM sistemine) kayıtlı değil olduğundan emin olun. Autopilot kendi kendine dağıtım işlemi bu adımları tamamlar. Cihazla ilgili tüm bilgilerin temizlenmiş olduğundan emin  olmak için hem Azure AD'de hem de Intune Portallarında Cihazlar sayfalarını kontrol edin. "Hedeflenen tüm cihazları Autopilot'a dönüştür" özelliğinin şu anda HoloLens olmadığını unutmayın.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Otomatik MDM Kaydı'nın etkinleştirin:

Autopilot'ın başarılı olması için otomatik MDM Kaydı'Azure portal. Bu, cihazın kullanıcı olmadan kaydolmalarını sağlar.

Veri [Azure portal](https://portal.azure.com/#home) Mobility **(MDM ve**  ->  **MAM) Azure Active Directory'yi**  ->  **Microsoft Intune.** Ardından **MDM kullanıcı kapsamını yapılandırarak** All (Tüm) seçeneğini seçmeniz **gerekir.**

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

    1. Cihazda, aynı anda **Güç ve** Ses Düzeyi **Aşağı** düğmelerine basın ve ardından bunları bırakın. Cihaz tanılama günlüklerini ve donanım karması toplar ve bunları bir dizi donanım .zip depolar.

   1. Bunun nasıl önceden biçimlendirilmiş olduğu hakkında ayrıntılı bilgi ve yönerge videosu için lütfen Çevrimdışı Tanılama [hakkında bilgi edinebilirsiniz.](hololens-diagnostic-logs.md#offline-diagnostics)

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
   > ![Donanım karmasını içeri aktarmak için Al komutunu kullanın.](./images/hololens-ap-hash-import.png)

1. içeri aktarma tamamlandıktan sonra **cihaz**  >  **Windows**  >  **Windows kayıt**  >  **cihazları**  >  **eşitleme**' yi seçin. Kaç cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakika sürebilir. Kayıtlı cihazı görmek için **Yenile**' yi seçin.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz listesini görüntülemek için Eşitle ve Yenile komutlarını kullanın.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. bir cihaz grubu oluşturun

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

### <a name="5-create-a-deployment-profile"></a>5. dağıtım profili oluşturma

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

### <a name="6-verify-the-esp-configuration"></a>6. ESP yapılandırmasını doğrulayın

Kayıt durumu sayfası (ESP), MDM ile yönetilen bir Kullanıcı bir cihazda ilk kez oturum açtığında çalışan tüm cihaz yapılandırma sürecinin durumunu görüntüler. ESP yapılandırmanızın aşağıdakine benzer olduğundan emin olun ve atamaların doğru olduğunu doğrulayın.  

> [!div class="mx-imgBorder"]
> ![ESP yapılandırması](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. HoloLens cihazların profil durumunu doğrulayın

1. Microsoft Endpoint Manager yönetim merkezi 'nde **cihazlar**  >    >  **Windows kayıt**  >  **cihazları** Windows ' nı seçin.

1. HoloLens cihazların listelendiğini ve profil durumunun **atandığını** doğrulayın.  

   > [!NOTE]  
   > Profilin cihaza atanması birkaç dakika sürebilir.  

   > [!div class="mx-imgBorder"]
   > ![Cihaz ve profil atamaları.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows HoloLens 2 kullanıcı deneyimi için Autopilot

yukarıdaki yönergeler tamamlandıktan sonra, HoloLens 2 kullanıcılarınız HoloLens cihazlarını sağlamak için aşağıdaki deneyimden geçer:  

1. Autopilot deneyimi Internet erişimi gerektirir. Internet erişimi sağlamak için lütfen aşağıdaki seçeneklerden birini kullanın:

    - Bağlan, bir Wi-Fi ağa OOBE 'de ve sonra otomatik olarak Autopilot deneyimini algılamasına izin verin. Bu, Autopilot deneyimi kendi kendine tamamlanana kadar OOBE ile etkileşimde bulunmak için tek zaman gerekir. lütfen varsayılan HoloLens 2 ' nin ınternet 'i algıladıktan sonra Autopilot algılamasını unutmayın. 10 saniye içinde Autopilot profili algılanmazsa, OOBE EULA sunacaktır. Bu senaryoya karşılaşıyorsanız, Autopilot algılamak için lütfen cihazınızı yeniden başlatın. Lütfen Ayrıca, cihazda yalnızca TenantLockdown ilkesi ayarlandıysa, OOBE 'nin Autopilot için süresiz olarak beklemeleri gerektiğini unutmayın.

    - kablolu internet bağlantısı için "USB-C-Ethernet" bağdaştırıcılarını kullanarak Ethernet ile cihazınızı Bağlan ve HoloLens 2 tam Autopilot deneyimini otomatik olarak sağlayın.

    - kablosuz internet bağlantısı için cihazınızı "USB-C-Wifi" bağdaştırıcılarıyla birlikte Bağlan ve HoloLens 2 tam Autopilot deneyimini otomatik olarak sağlayın.

        > [!IMPORTANT]  
       > Autopilot için OOBE 'de Wi-Fi ağlarını kullanmaya çalışan cihazların [, Windows Holographic, sürüm 20h2](hololens-release-notes.md#windows-holographic-version-20h2)üzerinde olması gerekir.
       >
       > Ethernet bağdaştırıcılarını kullanan cihazlarda, Ilk çalıştırma deneyimi (OOBE) başlamadan önce cihazı ağa bağlamanız gerekir. Cihaz, ilk OOBE ekranındaki bir Autopilot cihazı olarak sağlanıp sağlanmadığını belirler. Cihaz ağa bağlanamıyorsa veya cihazı bir Autopilot cihazı olarak sağlamayı tercih ediyorsanız, daha sonra Autopilot sağlamaya geçiş yapılamaz. Bunun yerine, cihazı bir Autopilot cihazı olarak sağlamak için bu yordamı yeniden başlatmanız gerekir.

1. Cihazın otomatik olarak OOBE başlatması gerekir. OOBE ile etkileşim kurma. Bunun yerine, geri ve rahat! HoloLens 2 ' nin ağ bağlantısını algılaması ve OOBE 'nin otomatik olarak tamamlanmasına izin verin. Cihaz, OOBE sırasında yeniden başlatılabilir. OOBE ekranları aşağıdakine benzemelidir.

   ![OOBE adım 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE adım 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE adım 3](./images/autopilot-device-setup.jpg)

1. OOBE 'nin sonunda, Kullanıcı adınızı ve parolanızı kullanarak cihazda oturum açabilirsiniz.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP ve Autopilot

HoloLens 2 cihaz, Windows Holographic, sürüm 20h2 itibariyle tenantlockdown CSP 'yi destekler. Bu CSP, cihaz sıfırlama veya refflash aracılığıyla bile, kuruluşun kiracısında cihazları bu kiracıya kilitleyerek korur.

[Tenantlockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP, HoloLens 2 ' nin yalnızca Autopilot kullanarak MDM kaydına bağlı olmasını sağlar. tenantlockdown CSP 'nin talep ırenetworkınoobe düğümü, HoloLens 2 ' de doğru veya yanlış (başlangıçta ayarlanmış) değere ayarlandığında, bu değer yeniden yanıp sönse, işletim sistemi güncelleştirmeleri, vb. için cihazda kalır.

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

1. önceki adımda oluşturulan grubun HoloLens 2 cihaz üyesini yapın ve eşitlemeyi tetikleyin.  

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. bu cihaz yapılandırması HoloLens 2 cihazında başarıyla geçerliyse, tenantlockdown etkileri etkin olur.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>ıntune 'u kullanarak HoloLens 2 üzerinde tenantlockdown 'ın talep ırenetworkınoobe ayarı nasıl yapılır?

1. yukarıda oluşturulan cihaz yapılandırmasının daha önce atandığı cihaz grubundan HoloLens 2 ' i kaldırın.

1. Özel bir OMA URI tabanlı cihaz yapılandırma profili oluşturun ve aşağıda gösterildiği gibi, talep ırenetworkınoobe için false belirtin.
OMA-URI değeri ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE olmalı

   > [!div class="mx-imgBorder"]
   > ![Intune'da OMA URI'sı aracılığıyla RequireNetworkInOOBE ayarının false olarak ayar ekran görüntüsü](images/hololens-tenant-lockdown-false.png)

1. Bir grup oluşturun ve cihaz yapılandırma profilini bu cihaz grubuna attayabilirsiniz. 

1. Önceki HoloLens oluşturulan grubun 2 cihaz üyesini seçin ve eşitlemeyi tetikler.

Intune portalında cihaz yapılandırmasının başarıyla uygulandığını doğrulayın. Bu cihaz yapılandırması HoloLens 2 cihazına başarıyla uygulandığında TenantLockdown'ın etkileri devre dışı kalır.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>TenantLockdown true olarak ayarlandıktan sonra Autopilot profili bir HoloLens OOBE sırasında ne olur? 
OOBE, Autopilot profilinin indirilene kadar süresiz olarak bekler ve aşağıdaki iletişim kutusu görüntülenir. TenantLockdown'ın etkilerini kaldırmak için, cihazın ilk olarak yalnızca Autopilot kullanılarak özgün kiracısına kayıtlı olması ve TenantLockdown CSP tarafından tanıtılan kısıtlamaların kaldırılması için önceki adımda açıklandığı gibi RequireNetworkInOOBE'nin kümeden kaldırılması gerekir.

![Cihazda ilkenin ne zaman zorlanan cihaz içinde görünümü.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Bilinen Sorunlar & sınırlamaları

- MEM'de yapılandırılan cihaz bağlamı tabanlı uygulama yüklemenin uygulama yüklemesi için geçerli HoloLens. [Cihaz bağlamı ve kullanıcı bağlamı yüklemeleri hakkında daha fazla bilgi edinebilirsiniz.](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Autopilot'ı Wi-Fi üzerinden ayarlarken, İnternet bağlantısı ilk kez kurulurken Autopilot profilinin indirilemedikleri bir örnek olabilir. Bu durumda Son Kullanıcı Lisans Sözleşmesi (EULA) sunulmuştur ve kullanıcının Autopilot olmayan kurulum deneyimine devam edebilirsiniz. Autopilot ile ayarlamayı yeniden denemek için cihazı uykuya bırakın ve cihazı açın veya yeniden başlatın ve yeniden deneyin.
- "Tüm hedeflenen cihazları Autopilot'a dönüştür" özelliği şu anda HoloLens cihazlarda desteklenmiyor.  

### <a name="troubleshooting"></a>Sorun giderme

Aşağıdaki makaleler daha fazla bilgi edinmek ve Autopilot Sorunlarını gidermek için yararlı bir kaynak olabilir, ancak bu makalelerin Windows 10 Desktop'a dayandırılana kadar tüm bilgilerin aşağıdakiler için geçerli HoloLens:

- [Windows Autopilot - bilinen sorunlar](/mem/autopilot/known-issues)
- [Windows cihaz kaydı sorunlarını Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - İlke Çakışmaları](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Autopilot için geri bildirim ve destek

Geri bildirim veya rapor sorunları sağlamak için aşağıdaki yöntemlerden birini kullanın:

- Cihaz kaydı desteği için lütfen satıcınıza veya dağıtımcınıza başvurun.
- Windows Autopilot ile ilgili genel destek sorguları veya profil atamaları, grup oluşturma veya MEM portalı denetimleri gibi sorunlar için lütfen Microsoft Endpoint Manager [başvurun](/mem/get-support)  
- Cihazınız Autopilot hizmetine kayıtlı ve profil MEM portalında atanmışsa, HoloLens [](/hololens/) (bkz. 'Destek' kartı). Lütfen bir destek bileti açın ve varsa, ilk deneyim [](hololens-diagnostic-logs.md#offline-diagnostics) (OOBE) sırasında çevrimdışı tanılama günlüklerini yakalayarak ekran görüntülerini ve günlükleri dahil edin.
- Cihazdan bir sorun rapor etmek için Geri Bildirim Merkezi uygulamanıza HoloLens. Bu Geri Bildirim Merkezi Yönetim Cihazı **Enterprise**  >  **seçin.**
- HoloLens için Autopilot hakkında genel geri bildirim sağlamak için bu anketi [gönderebilirsiniz](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Artık Autopilot için bir cihaz kullanmak veya cihazlarınızı farklı bir kiracıya kaydetmek zorunda kalmayabilirsiniz. Bunu yapmak için Autopilot cihazlarını silmek[için h ow okuyun.](/mem/autopilot/add-devices#delete-autopilot-devices)