---
title: dağıtım kılavuzu-Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-yapılandır
description: Dynamics 365 kılavuzlarıyla kurumsal bağlı bir ağ üzerinden HoloLens 2 cihaz dağıtmak üzere yapılandırmaların nasıl ayarlanacağını öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428771"
---
# <a name="configure---corporate-connected-guide"></a>Yapılandırma-kurumsal bağlantılı kılavuz

## <a name="azure-users-and-groups"></a>Azure kullanıcıları ve grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaların ve lisansların atanmasını sağlamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamak ve bir Kılavuzu yazıp çalıştıracağınızı kontrol etmek için bir kullanıcı hesabı gerekiyor&#39;.

Lisansları atamak için özel olarak tek bir Kullanıcı grubu yapabiliriz.

&#39;t ' den daha önce kullanabileceğiniz bir kullanıcı grubunda iki Azure AD hesabına erişiminiz varsa; hızlı başlangıç kılavuzlarından bazıları şunlardır:

- [Kullanıcı oluşturma](/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – grup oluşturmak için oluşturulan kullanıcılar ekleme
- [Azure AD 'yi bir Kullanıcı grubunun cihazlara katılmasına izin verecek şekilde yapılandırma](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -Yeni Kullanıcı grubunun CIHAZLARı Azure AD 'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 ' de otomatik kayıt

sorunsuz ve sorunsuz bir deneyim sunmak için, HoloLens 2 cihazları için Azure Active Directory katılması (asıfatı) ve ıntune 'a otomatik kayıt ayarlamak için gidilecek yol. Bu, kullanıcıların, OOBE sırasında kuruluş oturum açma kimlik bilgilerini girmesini ve Azure AD 'ye otomatik olarak kaydolmasını ve cihazı MDM 'ye kaydetmelerini sağlar.

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak hizmetler ' i seçip Premium deneme sürümü ' nü seçene kadar birkaç sayfaya gidebilirsiniz. otomatik kayıt P1 'nin yeterli olduğunu Azure Active Directory Premium 1 ve 2 ' nin olduğunu fark edebilirsiniz. Intune 'U seçip otomatik kayıt için Kullanıcı kapsamını seçebilir ve daha önce oluşturulmuş olan grubu seçebilirsiniz.

Tam ayrıntılar ve adımlar için, [Intune için otomatik kaydı etkinleştirme](/mem/intune/enrollment/quickstart-setup-auto-enrollment)kılavuzunu okuyun.

## <a name="corporate-wi-fi-connectivity"></a>Şirket Wi-Fi bağlantısı

şirket Wi-Fi bağlantıları, genellikle HoloLens 2 kullanan müşteriler için sertifika tabanlı kimlik doğrulaması gerektirir. MDM çözümünüz ile tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya ortak anahtar şifreleme standardı (PKCS) sertifika altyapısını kullanarak bu tür sertifikaları dağıtmanız gerekir. Wi-Fi profillerini dağıtmak için Intune kullanma, sertifikalar ve proxy ayarları, son kullanıcılar için sorunsuz bir deneyim oluşturur.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Sertifikaları ve Wi-Fi profillerini dağıtma

sertifikaları ve profilleri Microsoft Endpoint Manager aracılığıyla dağıtmak için şu adımları izleyin:

1. Kök ve ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma](/intune/protect/certificates-configure#create-trusted-certificate-profiles)). Bu profillerin her biri GG/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır.

    > [!CAUTION]
    > **Süre sonu tarihi olmayan sertifika profilleri dağıtılmaz**.

2. Her SCEP veya PKCS sertifikaları için bir profil oluşturun (bkz. [SCEP sertifika profili oluşturma veya PKCS sertifika profili oluşturma](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Bu profillerin her bırı, gg/aa/yyyy biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır.

    > [!CAUTION]
    > **Süre sonu tarihi olmayan sertifika profilleri dağıtılmaz.**

    > [!Note]
    > HoloLens 2 ' nin paylaşılan bir cihaz olması, yani cihaz başına birden çok kullanıcı olması halinde, mümkün olduğunda Wi-Fi kimlik doğrulaması için kullanıcı sertifikaları yerine cihaz sertifikalarının dağıtılması önerilir.

3. şirket Wi-Fi ağınız için bir profil oluşturun (bkz. [Windows 10 ve üzeri cihazlar için Wi-Fi ayarları](/intune/wi-fi-settings-windows)). Wi-Fi profilinizde, kuruluşunuzun içindeki proxy ayarlarını kullanmayı seçebilirsiniz.

    Seçenekleriniz şunlardır:
    - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
    - **El ile yapılandır**: **proxy sunucusu IP adresini** ve **bağlantı noktası numarasını** girin.
    - **Otomatik olarak Yapılandır**: proxy otomatik yapılandırma (PAC) betiğine işaret eden URL 'yi girin. Örneğin, girin *http://proxy.contoso.com/proxy.pac* .

    PAC dosyaları hakkında daha fazla bilgi için bkz. [proxy otomatik yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft dışı bir site açar).
 
    > [!Note]
    > Wi-Fi profilinin mümkün olduğunda Kullanıcı grupları yerine cihaz gruplarına atanması önerilir.
     
    > [!Tip]
    > ayrıca, çalışan bir Wi-Fi profilini şirket ağınızdaki bir Windows 10 bilgisayardan dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. ardından, bu dosyayı ıntune 'a aktarın ve HoloLens 2 cihazlarınızın Wi-Fi profili olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  cihaz profillerini HoloLens cihaz grubuna [atayın](/mem/intune/configuration/device-profile-assign) .

2.  Intune 'da cihaz profillerini [izleyin](/mem/intune/configuration/device-profile-monitor) .

Wi-Fi profillerle ilgili sorunlar varsa, referans [Intune 'da Wi-Fi cihaz yapılandırma profillerinde sorun giderin](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles).

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp bağlıyken dış Internet erişimi sorunlarını giderme
Hizmetler bir küme proxy 'Sine gitmediğinden, güvenlik duvarından bağlanmayı deneyebilir. Bu sorunları gidermek için güvenlik duvarı kurallarınız için uç nokta özelliklerinin bir listesini ekleyebilirsiniz.

Güvenlik Duvarı bağlantı noktalarında engellendiyse, HoloLens için bazı ortak [uç noktaları](/hololens/hololens-offline) etkinleştirin.

Ayrıca, kılavuzların belirli bağlantı noktalarını da etkinleştirebilirsiniz: [Microsoft Dynamics CRM Online bağlantı Için Internet 'e erişilebilir URL 'ler gereklidir](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami).

## <a name="app-deployment"></a>Uygulama Dağıtımı

MDM aracılığıyla LOB uygulaması dağıtmak, kolayca ölçeklendirilebilir ve oluşturulan bir grupta kayıt sırasında cihazlarınıza otomatik olarak dağıtılabilecek bir yöntemdir.

Uygulamalarınızı hala geliştirdiyseniz veya henüz bir tane yoksa, MRTK örnekleri hub 'ının örnek bir uygulamasını kullanabilirsiniz. Bu örnek uygulama kullanıma hazırdır ve Unity ya da Visual Studio kullanımını gerektirmez. [MRTK örnekleri örnek uygulamasını indirin](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Kendi uygulamanızı kullanmayı tercih ediyorsanız veya karma gerçeklik için uygulama geliştirmeye ilgileniyorsanız, [karma gerçeklik geliştirici belgelerimizi](/windows/mixed-reality/design/design)gözden geçirebilirsiniz.

> [!NOTE]
> HoloLens cihazların sistem gereksinimleri, uygulama yapısı mimarisine dayalıdır. HoloLens 2 cihaz ARM mimarisini kullanır. Visual Studio ' de uygulamalarınızı oluştururken, cihaz için doğru mimariyi seçtiğinizden ve gerekli tüm bağımlılıkları içerdiğinden emin olun.

> [!IMPORTANT]
> LOB uygulamalarını dağıttığınızda, sertifikayı Intune 'a yüklemek ve uygulamayı kullanmak üzere tasarlanan aynı gruba atamak önemlidir, aksi olarak da düzgün yüklenmez.

### <a name="upload-and-assign-the-app"></a>Upload ve uygulamayı atama

1. [Mem yönetim merkezine](https://endpoint.microsoft.com/#home)gidin.

2. **Uygulamalar**  ->  **tüm uygulamalar** ' ı seçin ve **+ Ekle** düğmesini seçin.

3. Diğer altında, **Iş kolu uygulaması**' nı seçin. **Seç**' e tıklayın.

4. Uygulama paketi dosyasını seçin, bu, APPXPAKET dosyanız veya bu örnekte uygulamanın _mrtk örnekleri Merkez \_ 2.4.2.0 \_ ARM \_ Master. AppxPackage_ olduğu durumdur.

5. Eksik bağımlılıklardan haberdar olursunuz. Bu durumda, _Microsoft. VCLibs. ARM. 14.00. appx_' i karşıya yüklememiz gerekir. **Bir dosya seçin** altında bulun.

6. Tamam'ı seçin.

7. Sonraki ekranda, gerekli alanlar otomatik olarak doldurulur. **İleri**’yi seçin.

8. Gerekli ' ın altında, bu uygulamayı grup için gerekli hale getirmek için önceden oluşturulmuş grubumuzu ekleyin. Bu, uygulamanın gruptaki kayıtlı cihazlara otomatik olarak indirilmesine neden olur. **İleri**’yi seçin.

9. **Oluştur**’u seçin.

Daha fazla bilgi: [Microsoft Intune gruplara uygulama atama](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Kurulum Kılavuzu: uygulama lisansları, veri deposu ve yazma

Dynamics 365 kılavuzlarını kullanabilmeniz için bazı hazırlıklar yapmanız gerekir. Hazırlanmanız gereken üç alan vardır; Kullanıcılar, veri deposu ve kılavuzlar kendi kendilerine ait.

### <a name="users-and-application-licenses"></a>Kullanıcılar ve uygulama lisansları

Birinin kılavuzlarını kullanabilmesi için, bu kılavuzda daha önce ayarlamış olduğumuz bir Azure AD hesabı kullanmaları gerekir.

Ayrıca, oluşturduğunuz kullanıcıya Dynamics 365 kılavuzlar lisansı atamanız gerekir. bunu [Microsoft 365 yönetim merkezi](https://admin.microsoft.com/AdminPortal/Home). Ayrıca, lisansı birincil Azure hesabınıza atayın.

Uygulama lisanslarını uygulamaya yönelik adım adım yönergeler için resimlerle birlikte [Bu kısa kılavuzu](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) izleyin.

### <a name="set-up-the-dataverse"></a>Veri deposu ayarlama

[Üretim ortamı ayarlamak](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) için iki önkoşulu karşılamanız gerekir. [**sistem yöneticisi**](/power-platform/admin/database-security) rolüne sahip olmanız gerekir **ve** bir [**Power Apps lisansınızın**](/power-platform/admin/signup-question-and-answer) olması gerekir (ya da bir Power Apps lisansı içeren [**Dynamics 365 kılavuz lisansına**](/dynamics365/mixed-reality/guides/setup-step-one) sahip olmanız gerekir). Bu kılavuzun ardından Azure AD 'yi oluşturduktan sonra, Sistem Yöneticisi için rol gereksinimlerini karşılamanız gerekir. Ayrıca, önceki adımda bir kılavuzlar lisansı atandık.

Bu kılavuzda, [bir Microsoft Dataverse ortamı oluşturmak](/dynamics365/mixed-reality/guides/setup-step-two)için:

1. [Power Platform Yönetim merkezini](https://admin.powerplatform.microsoft.com/environments) kullanarak başlayın ve yeni bir ortam oluşturun.
2. **Yeni ortam** oluştururken&#39;için **Üretim**' ı  seçin.
3. **Bu ortam için veritabanı oluştur ' a** geçiş yapmanız önemlidir mi?  seçeneğini  **Evet** yapın.
4. **Veritabanı Ekle** iletişim kutusunda, **Dynamics 365 uygulamalarını etkinleştir** seçeneğini Evet olarak ayarlayın **.**

Veri tersinizin en büyük dosya boyutunu artırmak istemeniz gerekir. Maksimum dosya boyutunu artırmak, kılavuzlarda daha sonra kullanmak üzere daha büyük 3 boyutlu modelleri veya video dosyalarını karşıya yüklemenizi sağlar. En büyük karşıya yükleme [dosyası boyutunu değiştirmek için kısa bir kılavuzu izleyin.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Son olarak, çözümünü yüklemeniz [ve yapılandırmamız gerekir.](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution) [İlkeler Power Platform yönetim merkezi](https://admin.powerplatform.microsoft.com/environments)Kaynaklar  \& gt; öğesini seçin.  **Dynamics 365 uygulamaları,** listeden **Dynamics 365 Kılavuzları'ı** ve ardından Yükle'yi **seçin.**  

Uygulamaları [kullanamadan önce bir](/dynamics365/mixed-reality/guides/assign-role) Kılavuz güvenlik rolü eklemeniz gerekir.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Yazma aracılığıyla bilgisayarınızda test kılavuzu oluşturma

Kılavuzlar oluştururken her zaman bilgisayarınızda başlarsınız. Adımları oluşturma, modelleri seçme ve kılavuzun yer bağlantısı oluşturma. Bunu takip eden kılavuzun içeriğini daha sonra HoloLens cihazınıza yazma moduna yerleştireceğiz. Bu kılavuzun amaçları doğrultusunda, minimum adımlara ve modellere sahip kısa bir test kılavuzu yapmanızı öneririz.

Kılavuzlar için yazma hakkında bilgi öğrenmeye başlamak için, yazmaya genel bakış ile [buradan başlayabilirsiniz.](/dynamics365/mixed-reality/guides/authoring-overview) Veya hızlı bir genel bakış elde etmek için bu kısa videoyu izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>İsteğe bağlı: Bilgi noktası modu

Bilgi noktası modu, BIR IT Yöneticisinin başlat menüsünün kullanıcı arabirimini yalnızca tek bir uygulamayı veya uygulama seçimini gösterecek şekilde yapılandırmasını sağlar. Bilgi noktası belirli kullanıcılara, gruplara veya cihaz düzeyinde de uygulanabilir; ve bazı durumlarda belirli kullanıcıları Bilgi Noktası'nın dışında bırakarak normal başlat menüsüne erişmelerini sekleyebilirsiniz.

Bilgi noktası modu hem kapsam hem de yapılandırmalar için ayarlanabiliyor ve Bilgi Noktası'nın bilgi noktası dağıtım yöntemleri gibi birçok farklı değişkene HoloLens. Tüm bu değişkenler nedeniyle Bilgi Noktası modu bu kılavuz için _isteğe_ bağlı olarak bırakılacaktır ve yeniden gözden geçirilmesi mümkün olmayacaktır. Kullanılabilir uygulamaları kullanıcılarla kısıtlamak veya daha fazla bilgi edinmek için bir işletmeye ihtiyacınız olduğuna inanıyorsanız, bilgi noktası olarak HoloLens bilgi noktası olarak [ayarlamayı öğrenmekten rahat olun.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>İsteğe bağlı: WDAC

WDAC, bir IT Yöneticisinin cihazlarda uygulama başlatmayı engellemek için cihazlarını yapılandırmasını sağlar. Bu, kullanıcıya cihaz uygulamalarını gizleten ancak hala başlatılana bir kullanıcı arabirimi sunulan Bilgi Noktası modu gibi cihaz kısıtlama yöntemlerden farklıdır. WDAC uygulanırken, uygulamalar Hala Tüm Uygulamalar listesinde görünür durumdadır, ancak WDAC bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılamalarını durdurur.

Daha fazla bilgi için, [wdac ve Windows PowerShell 2](/mem/intune/configuration/custom-profile-hololens)cihaz üzerinde uygulamalara izin vermek veya HoloLens engellemek için WDAC ve Microsoft Intune.

[Windows Defender Uygulama Denetimi - WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Dağıtma](hololens2-corp-connected-deploy.md)