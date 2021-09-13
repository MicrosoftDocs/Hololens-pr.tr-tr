---
title: Dağıtım Kılavuzu - Dynamics 365 kılavuzları HoloLens 2 ile kurumsal bağlantılı HoloLens - Yapılandırma
description: Dynamics 365 Kılavuzları ile kurumsal HoloLens 2 cihazı dağıtmak için yapılandırmaları ayarlamayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033499"
---
# <a name="configure---corporate-connected-guide"></a>Yapılandırma - Kurumsal Bağlantılı Kılavuz

## <a name="azure-users-and-groups"></a>Azure Kullanıcıları ve Grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaları ve lisansları atamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamanın ve bir kılavuz hazır olup olmadığını kontrol etmek için bir&#39;hesabı gerektirebilirsiniz.

Özellikle lisans atamak için tek bir kullanıcı grubu kullanabiliriz.

Kullanabileceğiniz&#39;kullanıcı grubunda iki Azure AD hesabına erişiminiz yoksa; hızlı başlangıç kılavuzları şu şekildedir:

- [Kullanıcı oluşturma](/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Grup oluşturmak için oluşturulan kullanıcıları ekleme
- [Azure AD'yi Bir Kullanıcı Grubunun cihazlara katılmasına izin](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) verecek şekilde yapılandırma – Yeni kullanıcı grubunun cihazları Azure AD'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2'de Otomatik Kayıt

Sorunsuz ve sorunsuz bir deneyim elde etmek için, HoloLens 2 cihaz için Azure Active Directory Join (AADJ) ve Intune'a Otomatik Kayıt'ı ayarlamanın yoludur. Bu, kullanıcıların OOBE sırasında kuruluş oturum açma kimlik bilgilerini girişlerini ve Azure AD'ye otomatik olarak kaydolmalarını ve cihazı MDM'ye kaydetmelerini sağlar.

bu [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak, Bir deneme sürümü al'ı seçene kadar hizmetleri ve birkaç sayfayı Premium olabiliriz. Otomatik Kayıt P1 için Azure Active Directory Premium 1 ve 2'nin yeterli olduğunu fark olabilir. Intune'ı seçerek otomatik kayıt için kullanıcı kapsamını ve daha önce oluşturulmuş olan grubu seçerek.

Tüm ayrıntılar ve adımlar için [Intune için otomatik kaydı etkinleştirme kılavuzunu okuyun.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Kurumsal Wi-Fi Bağlantısı

Kurumsal Wi-Fi bağlantıları için genellikle 2. kimlik doğrulamasını kullanan müşteriler için sertifika HoloLens gerekir. MDM çözümünüzle tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya Ortak Anahtar Şifreleme Standardı (PKCS) sertifika altyapısı kullanarak bu sertifikaları dağıtmanız gerekir. Intune'Wi-Fi profilleri, sertifikaları ve ara sunucu ayarlarını dağıtmak, son kullanıcılar için sorunsuz bir deneyim oluşturur.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Sertifikaları ve Wi-Fi dağıtma

Sertifika ve profilleri Microsoft Endpoint Manager dağıtmak için şu adımları izleyin:

1. Kök ve Ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Bu profillerin her biri DD/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır.

    > [!CAUTION]
    > **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

2. Her SCEP veya PKCS sertifikası için bir profil oluşturun (bkz. SCEP sertifika profili oluşturma veya [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)sertifika profili oluşturma) Bu profillerden her biri DD/AA/YYYY biçiminde sona erme tarihi içeren bir açıklamaya sahip olmalıdır.

    > [!CAUTION]
    > **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

    > [!Note]
    > HoloLens 2, çoğu kişi için paylaşılan cihaz (örneğin, cihaz başına birden çok kullanıcı) olarak kabul edilir. Mümkün olduğunca, cihaz kimlik doğrulaması için Kullanıcı sertifikaları yerine Cihaz sertifikaları Wi-Fi önerilir.

3. Kurumsal ağ ağınız için bir profil oluşturun (Wi-Fi ve sonraki cihazlar için [Wi-Fi Windows 10 ayarlarına bakın).](/intune/wi-fi-settings-windows) Bu Wi-Fi içinde, kuruluş içindeki ara sunucu ayarlarını kullanmayı seçebilirsiniz.

    Seçenekleriniz şunlardır:
    - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
    - **El ile yapılandırma:** **Proxy sunucusu IP adresini ve Bağlantı** noktası numarasını **girin.**
    - **Otomatik olarak yapılandırma:** Proxy otomatik yapılandırma (PAC) betiğine işaret alan URL'yi girin. Örneğin, *http://proxy.contoso.com/proxy.pac* girin.

    PAC dosyaları hakkında daha fazla bilgi için bkz. [Proxy Otomatik Yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft olmayan bir site açar).
 
    > [!Note]
    > Mümkün olduğunca Wi-Fi kullanıcı grupları yerine Cihaz gruplarına atanmalarını öneririz.
     
    > [!Tip]
    > Ayrıca, çalışan bir Wi-Fi profilini kurumsal ağ Windows 10 bir pc'den dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'a aktarın ve 2 cihaz için Wi-Fi profil olarak HoloLens kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Cihaz](/mem/intune/configuration/device-profile-assign) profillerini cihaz grubuna HoloLens attayabilirsiniz.

2.  [](/mem/intune/configuration/device-profile-monitor) Intune'da cihaz profillerini izleme.

Profillerle ilgili sorunlar [Wi-Fi, Intune'da Wi-Fi cihaz yapılandırma profilleriyle ilgili sorunları giderme'ye bakın.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp Bağlıyken Dış İnternet Erişimi Sorunlarını Giderme
Hizmetler, ayarlanmış bir Ara Sunucudan devam etmeye çalışırken güvenlik duvarı üzerinden bağlanmayı deneyebilir. Bu sorunları gidermek için güvenlik duvarı kurallarınıza uç nokta özellikleri listesini ekleyebilirsiniz.

Güvenlik duvarı bağlantı noktaları engellenmişse, güvenlik duvarı bağlantı noktaları için [bazı yaygın HoloLens.](/hololens/hololens-offline)

Kılavuzlara özgü bağlantı noktalarını da etkinleştirabilirsiniz: bağlantı için [gereken İnternet'e erişilebilir URL'Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>Uygulama Dağıtımı

MDM aracılığıyla LOB uygulaması dağıtmak, kolayca ölçeklenebilir ve oluşturulan bir gruba kayıttan sonra cihazlarınıza otomatik olarak dağıtılabilir bir yöntemdir.

Hala Uygulamalarınızı geliştiriyorsanız veya henüz bir uygulamanız yoksa MRTK örnekleri hub'ını örnek bir uygulama kullanabilirsiniz. Bu örnek uygulama kullanıma hazırdır ve Unity veya Visual Studio. [MRTK Örnekleri Örnek uygulamasını indirin.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Kendi uygulamalarınızı kullanmayı tercih ediyorsanız veya Karma Gerçeklik için uygulama geliştirmeyle ilgileniyorsanız Karma Gerçeklik geliştirici belgelerimizi [gözden geçirebilirsiniz.](/windows/mixed-reality/design/design)

> [!NOTE]
> HoloLens cihazlar için Sistem Gereksinimleri, uygulama derlemenin mimarisini temel almaktadır. HoloLens 2 cihaz ARM mimarisini kullanır. Uygulamalarınızı Visual Studio cihaz için doğru mimariyi seçtiğinizden ve gerekli bağımlılıkları dahil edin.

> [!IMPORTANT]
> LOB uygulamalarını dağıtırken, sertifikayı Intune'a yüklemek ve uygulamayı kullanmayı amaçlanan gruba atamak da önemlidir, yoksa düzgün yüklenmez.

### <a name="upload-and-assign-the-app"></a>Upload Atama ve Atama

1. [MEM yönetim merkezine gidin.](https://endpoint.microsoft.com/#home)

2.   ->  **Uygulamalar'Tüm uygulamalar** ve + Ekle **düğmesini** seçin.

3. Diğer'in **altında İş hattı uygulamasını seçin.** **seç'e tıklayın.**

4. Uygulama paketi dosyasını seçin, bu sizin APPXBUNDLE dosyanızdır veya bu örnekte uygulama _MRTK Örnekleri \_ Hub'ı 2.4.2.0 \_ arm \_ Master.appxbundle'dır._

5. Eksik bağımlılıklar size bildirilecek. Bu _durumda, Microsoft.VCLibs.ARM.14.00.appx dosyasını karşıya yüklememiz gerekir._ Bir dosya seçin **altında bu dosyayı ara.**

6. Tamam'ı seçin.

7. Sonraki ekranda gerekli alanlar otomatik olarak doldurulur. **İleri**’yi seçin.

8. Bu uygulamanın grup için gerekli olması için Gerekli'nin altına daha önce oluşturduğunuz grubu ekleyin. Bu, uygulamanın gruptaki kayıtlı cihazlara otomatik olarak indirilir. **İleri**’yi seçin.

9. **Oluştur**’u seçin.

Daha fazla bilgi [edinin: Uygulamaları Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Kurulum Kılavuzları: Uygulama lisansları, veri tersi ve yazma

Dynamics 365 Kılavuzlarını kullanmak için bazı hazırlıklar yapmak gerekir. Hazırlamamız gereken üç alan vardır; kullanıcılar, veri tersi ve kılavuzların kendileri.

### <a name="users-and-application-licenses"></a>Kullanıcılar ve uygulama lisansları

Bir kişinin Kılavuzlar'ın kullanıla bir Azure AD hesabı kullanması gerekir. Bu hesabı daha önce bu kılavuzda ayarlayabilirsiniz.

Ayrıca oluşturduğunuz kullanıcıya Dynamics 365 Kılavuzları lisansı da atamanız gerekir. Bunu aşağıdaki [Microsoft 365 yönetim merkezi.](https://admin.microsoft.com/AdminPortal/Home) Ayrıca lisansı birincil Azure Hesabınıza da attayın.

Uygulama [lisanslarını uygulama](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) hakkında adım adım yönergeler için bu kısa kılavuzu resimlerle izleyin.

### <a name="set-up-the-dataverse"></a>Veri Ters'i ayarlama

Bir üretim [ortamı ayarlamak için iki](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) önkoşul karşılamanız gerekir. Sistem Yöneticisi [**rolüne**](/power-platform/admin/database-security) sahip  olmalı ve Power Apps lisansına [**(veya**](/power-platform/admin/signup-question-and-answer) Power Apps içeren Dynamics [**365 Kılavuzları**](/dynamics365/mixed-reality/guides/setup-step-one) lisansına) sahip Power Apps gerekir. Bu kılavuzu takip ettiyseniz Azure AD'i oluşturduktan sonra Sistem Yöneticisi için rol gereksinimlerini karşılarsunuz. Önceki adımda bir Kılavuz Lisansı da atatık.

Bir Microsoft [Dataverse ortamı oluşturmak için bu kılavuzda:](/dynamics365/mixed-reality/guides/setup-step-two)

1. başlangıç olarak yeni [Power Platform yönetim merkezi](https://admin.powerplatform.microsoft.com/environments) ortamını oluşturma.
2. Yeni **Ortam'ı oluştururken,** Tür **olarak&#39;'yi** **seçersiniz.**
3. Bu ortam için veritabanı **oluştur'a geçiş yapmak önemlidir.**  seçeneğini Evet olarak **belirleyin.**
4. Veritabanı  **ekle iletişim**  kutusunda  **Dynamics 365 uygulamalarını etkinleştir seçeneğini Evet**  olarak  **ayarlayın.**

Veri deposundaki öğelerin en büyük dosya boyutunu arttırmak isteyeceksiniz. En büyük dosya boyutunu artırmak kılavuzlarınızın daha sonra kullanacağınız daha büyük 3B modellerini veya video dosyalarını karşıya yüklemenizi sağlar. [Karşıya yükleme dosya boyutu üst sınırını değiştirmek için](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)kısa bir kılavuz izleyin.

Son olarak, [çözümü yükleyip yapılandırmanız](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)gerekir. [Power Platform Yönetim merkezinde](https://admin.powerplatform.microsoft.com/environments) **kaynaklar** \& gt; öğesini seçin.  **Dynamics 365 uygulamaları**, listeden **Dynamics 365 kılavuzlarını** seçin ve ardından **Install**' ı seçin.  

Uygulamaları kullanabilmeniz için önce [Kılavuzlar güvenlik rolü eklemeniz](/dynamics365/mixed-reality/guides/assign-role) gerekir.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Yazma yoluyla bilgisayarınızda bir test kılavuzu oluşturma

Kılavuzlar oluştururken her zaman bilgisayarınızda her zaman başlamanız gerekir. Adımları oluşturma, modeller seçme ve kılavuzun bağlantısının nasıl yapılacağı. bu, daha sonra HoloLens cihazınızda yazma modunda kılavuzunuz için içerik yerleştirilerek izlenir. Bu kılavuzun amaçları doğrultusunda, en az adım ve modellerle kısa bir test Kılavuzu yapmayı öneririz.

Kılavuzlar için yazma hakkında öğrenmeye başlamak isterseniz [yazma genel bakışı](/dynamics365/mixed-reality/guides/authoring-overview)ile buradan başlayın. Ya da hızlı bir izlemeye genel bakış almak için bu kısa videoyu izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>İsteğe bağlı: bilgi noktası modu

Bilgi noktası modu, bir BT Yöneticisi tarafından yalnızca tek bir uygulamayı veya uygulama seçimini göstermek üzere başlangıç menüsünün Kullanıcı arabirimini yapılandırabilmesine olanak tanıyan bir moddur. Bir bilgi noktası belirli kullanıcılara, gruplara veya cihaz düzeyine de uygulanabilir; Bazı durumlarda, bazı kullanıcıların, düzenli Başlat menüsüne erişmesine izin verirken bazı kullanıcıları da bilgi noktasından hariç tutun.

Bilgi noktası modu, hem kapsam hem de yapılandırmada ayarlanabilir birçok farklı değişkene ve ayrıca, bilgi noktası HoloLens dağıtım yöntemlerine sahiptir. Tüm bu değişkenler nedeniyle, bilgi noktası modu Bu kılavuz için _isteğe bağlı_ olarak kalmadı ve yeniden ziyaret edilmezler. kullanılabilir uygulamaları kullanıcılarla kısıtlamak ya da daha fazla bilgi edinmek ve daha fazla bilgi almak istiyorsanız, [HoloLens bir bilgi noktası olarak ayarlamayı](/hololens/hololens-kiosk)öğrenmekten çekinmeyin.

## <a name="optional-wdac"></a>İsteğe bağlı: WDAC

WDAC, BT yöneticisinin cihazlarını cihazlarda uygulamaların başlatılmasını engelleyecek şekilde yapılandırmasına olanak sağlar. Bu, kullanıcının cihazdaki uygulamaları gizleyen bir kullanıcı arabirimi ile sunulduğu, ancak yine de başlatılabileceği, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır. WDAC uygulandığında, uygulamalar tüm uygulamalar listesinde görünmeye devam eder, ancak bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılabilmesini engeller.

daha fazla bilgi için başvuru ' yı [kullanın ve Microsoft Intune ile HoloLens 2 cihazlarda uygulamalara izin vermek veya bunları engellemek için Windows PowerShell](/mem/intune/configuration/custom-profile-hololens).

[Windows Defender Uygulama denetimi-WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlı dağıtım-dağıtım](hololens2-corp-connected-deploy.md)