---
title: Dağıtım Kılavuzu - Dynamics 365 Kılavuzları ile kurumsal bağlantılı HoloLens 2 - Yapılandırma
description: Dynamics 365 Kılavuzları ile kurumsal bir Bağlı ağ üzerinden HoloLens 2 cihazları dağıtmak için yapılandırmaları ayarlamayı öğrenin.
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
ms.openlocfilehash: 939efc28a0c3255cc9a38af3cd8dd9aa8fc2ac98
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378956"
---
# <a name="configure---corporate-connected-guide"></a>Yapılandırma - Kurumsal Bağlantılı Kılavuz

## <a name="azure-users-and-groups"></a>Azure Kullanıcıları ve Grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaları ve lisansları atamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamanın ve bir kılavuz hazır olup olmadığını kontrol etmek için bir&#39;hesabı gerektirebilirsiniz.

Özellikle lisans atamak için tek bir kullanıcı grubu kullanabiliriz.

Henüz&#39;bir kullanıcı grubunda iki Azure AD hesabına erişiminiz yoksa; hızlı başlangıç kılavuzları şu şekildedir:

- [Kullanıcı oluşturma](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Grup oluşturmak için oluşturulan kullanıcıları ekleme
- [Azure AD'yi Bir Kullanıcı Grubunun cihazlara katılmasına izin](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) verecek şekilde yapılandırma – Yeni kullanıcı grubunun cihazları Azure AD'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2'de Otomatik Kayıt

Sorunsuz ve sorunsuz bir deneyim elde etmek için HoloLens 2 cihazları için Azure Active Directory Join (AADJ) ve Intune'a Otomatik Kayıt'ı ayarlama yoludur. Bu, kullanıcıların OOBE sırasında kuruluş oturum açma kimlik bilgilerini girişlerini ve Azure AD'ye otomatik olarak kaydolmalarını ve cihazı MDM'ye kaydetmelerini sağlar.

Microsoft [Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak, Premium deneme sürümü al'ı seçene kadar hizmetleri seçerek birkaç sayfada gezinebilirsiniz. Otomatik Kayıt P1 için Azure Active Directory Premium 1 ve 2'nin yeterli olduğunu fark olabilir. Intune'ı seçerek otomatik kayıt için kullanıcı kapsamını ve daha önce oluşturulmuş olan grubu seçerek.

Tüm ayrıntılar ve adımlar için [Intune için otomatik kaydı etkinleştirme kılavuzunu okuyun.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Kurumsal Wi-Fi Bağlantısı

Şirket Wi-Fi bağlantıları genellikle HoloLens 2 kullanan müşteriler için sertifika tabanlı kimlik doğrulaması gerektirir. MDM çözümünüzle tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya Ortak Anahtar Şifreleme Standardı (PKCS) sertifika altyapısı kullanarak bu sertifikaları dağıtmanız gerekir. Intune'Wi-Fi profilleri, sertifikaları ve ara sunucu ayarlarını dağıtmak, son kullanıcılar için sorunsuz bir deneyim oluşturur.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Sertifikaları ve Wi-Fi dağıtma

Sertifikaları ve profilleri Microsoft Endpoint Manager dağıtmak için şu adımları izleyin:

1. Kök ve Ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Bu profillerin her biri DD/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır. 

    > [!CAUTION]
    > **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

2.  Her SCEP veya PKCS sertifikası için bir profil oluşturun (bkz. SCEP sertifika profili oluşturma veya [PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)sertifika profili oluşturma) Bu profillerden her biri DD/AA/YYYY biçiminde sona erme tarihi içeren bir açıklamaya sahip olmalıdır. 

    > [!CAUTION]
    > **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

    > [!Note]
    > HoloLens 2'nin paylaşılan bir cihaz (cihaz başına birden çok kullanıcı) olduğu kabul edilir ve mümkün olduğunca Cihaz kimlik doğrulaması için Kullanıcı sertifikaları yerine Cihaz Wi-Fi dağıtmanız önerilir.

3.  Kurumsal ağ ağınız için bir profil oluşturun (Wi-Fi ve sonraki cihazlar için [Wi-Fi Windows 10 ayarlarına bakın).](https://docs.microsoft.com/intune/wi-fi-settings-windows) Uygulama Wi-Fi içinde, kuruluş içindeki ara sunucu ayarlarını kullanmayı seçebilirsiniz.
 
    Seçenekleriniz şunlardır:
    - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
    - **El ile yapılandırma:** **Proxy sunucusu IP adresini ve Bağlantı** noktası numarasını **girin.**
    - **Otomatik olarak yapılandırma:** Proxy otomatik yapılandırma (PAC) betiğine işaret alan URL'yi girin. Örneğin, *http://proxy.contoso.com/proxy.pac* girin.

    PAC dosyaları hakkında daha fazla bilgi için bkz. [Proxy Otomatik Yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft olmayan bir site açar).
 
    > [!Note]
    > Mümkün olduğunca Wi-Fi kullanıcı grupları yerine Cihaz gruplarına atanmalarını öneririz.
     
    > [!Tip]
    > Ayrıca, kurumsal ağ Wi-Fi bir Windows 10 profili dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. Ardından bu dosyayı Intune'a aktarın ve HoloLens 2 Wi-Fi profil olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Cihaz](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) profillerini HoloLens cihaz grubuna attayabilirsiniz.

2.  [](https://docs.microsoft.com/mem/intune/configuration/device-profile-monitor) Intune'da cihaz profillerini izleme.

Profillerle ilgili sorunlar [Wi-Fi, Intune'da Wi-Fi sorun giderme'ye bakın.](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Corp Bağlıyken Dış İnternet Erişimi Sorunlarını Giderme
Hizmetler, ayarlanmış bir Ara Sunucudan devam etmeye çalışırken güvenlik duvarı üzerinden bağlanmayı deneyebilir. Bu sorunları gidermek için güvenlik duvarı kurallarınıza uç nokta özellikleri listesini ekleyebilirsiniz.

Güvenlik duvarı bağlantı noktaları engellenmişse HoloLens için bazı [yaygın uç](https://docs.microsoft.com/hololens/hololens-offline) noktaları etkinleştirin.

Kılavuzlara özgü bağlantı noktalarını da etkinleştirabilirsiniz: İnternet'e erişim için gereken [URL'ler Microsoft Dynamics CRM Online.](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)

## <a name="app-deployment"></a>Uygulama Dağıtımı

MDM aracılığıyla LOB uygulaması dağıtmak, kolayca ölçeklenebilir ve oluşturulan bir gruba kayıttan sonra cihazlarınıza otomatik olarak dağıtılabilir bir yöntemdir.

Hala Uygulamalarınızı geliştiriyorsanız veya henüz bir uygulamanız yoksa MRTK örnekleri hub'ını örnek bir uygulama kullanabilirsiniz. Bu örnek uygulama kullanıma hazırdır ve Unity veya Visual Studio. [MRTK Örnekleri Örnek uygulamasını indirin.](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App)

Kendi uygulamalarınızı kullanmayı tercih ediyorsanız veya Karma Gerçeklik için uygulama geliştirmeyle ilgileniyorsanız Karma Gerçeklik geliştirici belgelerimizi [gözden geçirebilirsiniz.](https://docs.microsoft.com/windows/mixed-reality/design/design)

> [!NOTE]
> HoloLens cihazları için Sistem Gereksinimleri, uygulama derlemesi mimarisini temel almaktadır. HoloLens 2 cihazları ARM mimarisini kullanır. Uygulamalarınızı Visual Studio cihaz için doğru mimariyi seçtikten ve gerekli bağımlılıkları dahil edin.

> [!IMPORTANT]
> LOB uygulamalarını dağıtırken, sertifikayı Intune'a yüklemek ve uygulamayı kullanmayı amaçlanan gruba atamak da önemlidir, yoksa düzgün yüklenmez.

### <a name="upload-and-assign-the-app"></a>Uygulamayı Karşıya Yükleme ve Atama

1. [MEM yönetim merkezine gidin.](https://endpoint.microsoft.com/#home)

2. Uygulamalar **ve**  ->  **Tüm uygulamalar** ve **+ Ekle düğmesini** seçin.

3. Diğer altında İş **yeri uygulaması'nın altında öğesini seçin.** **Seç'e tıklayın.**

4. Uygulama paketi dosyasını seçin, bu sizin APPXBUNDLE dosyanızdır veya bu örnekte uygulama _MRTK Örnekleri \_ Hub'ı 2.4.2.0 \_ arm \_ Master.appxbundle'dır._

5. Eksik bağımlılıklar size bildirilecek. Bu durumda, _Microsoft.VCLibs.ARM.14.00.appx dosyasını karşıya yüklememiz gerekir._ Bir dosya seçin **altında bu dosyayı ara.**

6. Tamam'ı seçin.

7. Sonraki ekranda gerekli alanlar otomatik olarak doldurulur. **İleri**’yi seçin.

8. Bu uygulamanın grup için gerekli olması için Gerekli'nin altına daha önce oluşturduğunuz grubu ekleyin. Bu, uygulamanın gruptaki kayıtlı cihazlara otomatik olarak indirilir. **İleri**’yi seçin.

9. **Oluştur**’u seçin.

Daha fazla bilgi [edinin: Uygulamaları Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Kurulum Kılavuzları: Uygulama lisansları, veri tersi ve yazma

Dynamics 365 Kılavuzlarını kullanmak için bazı hazırlıklar yapmak gerekir. Hazırlamamız gereken üç alan vardır; kullanıcılar, veri tersi ve kılavuzların kendileri.

### <a name="users-and-application-licenses"></a>Kullanıcılar ve uygulama lisansları

Bir kişinin Kılavuzları kullanması için, daha önce bu kılavuzda ayarlayılan bir Azure AD hesabı kullanmaları gerekir.

Ayrıca oluşturduğunuz kullanıcıya Dynamics 365 Kılavuzları lisansı da atamanız gerekir. Bunu aşağıdaki [Microsoft 365 yönetim merkezi.](https://admin.microsoft.com/AdminPortal/Home) Ayrıca lisansı birincil Azure Hesabınıza da attayın.

Uygulama [lisanslarını uygulamayla](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ilgili adım adım yönergeler için bu kısa kılavuzu resimlerle izleyin.

### <a name="set-up-the-dataverse"></a>Veri Ters'i ayarlama

Bir üretim [ortamı ayarlamak için iki](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) önkolu karşılamanız gerekir. Sistem Yöneticisi [**rolüne**](https://docs.microsoft.com/power-platform/admin/database-security) sahip  olmalı ve Power Apps [**lisansına**](https://docs.microsoft.com/power-platform/admin/signup-question-and-answer) (veya Power Apps içeren Dynamics [**365 Kılavuzları**](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one) lisansına) sahip Power Apps gerekir. Bu kılavuzu takip ettiyseniz Azure AD'i oluşturduktan sonra Sistem Yöneticisi için rol gereksinimlerini karşılarsunuz. Ayrıca önceki adımda bir Kılavuz Lisansı da atatık.

Bir Microsoft [Dataverse ortamı oluşturmak için bu kılavuzda:](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two)

1. başlangıç olarak yeni [Power Platform yönetim merkezi](https://admin.powerplatform.microsoft.com/environments) ortamını oluşturma.
2. Yeni **Ortam'ı oluştururken,** Tür **olarak&#39;'ı** **seçersiniz.**
3. Bu ortam için veritabanı **oluştur'a geçiş yapmak önemlidir.**  seçeneğini Evet olarak **belirleyin.**
4. Veritabanı  **ekle iletişim**  kutusunda  **Dynamics 365 uygulamalarını etkinleştir seçeneğini Evet**  olarak  **ayarlayın.**

Veri deposundaki öğelerin en büyük dosya boyutunu arttırmak isteyeceksiniz. En büyük dosya boyutunu artırmak kılavuzlarınızın daha sonra kullanacağınız daha büyük 3B modellerini veya video dosyalarını karşıya yüklemenizi sağlar. [Karşıya yükleme dosya boyutu üst sınırını değiştirmek için](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)kısa bir kılavuz izleyin.

Son olarak, [çözümü yükleyip yapılandırmanız](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution)gerekir. [Power Platform Yönetim merkezinde](https://admin.powerplatform.microsoft.com/environments) **kaynaklar** \& gt; öğesini seçin.  **Dynamics 365 uygulamaları**, listeden **Dynamics 365 kılavuzlarını** seçin ve ardından **Install**' ı seçin.  

Uygulamaları kullanabilmeniz için önce [Kılavuzlar güvenlik rolü eklemeniz](https://docs.microsoft.com/dynamics365/mixed-reality/guides/assign-role) gerekir.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Yazma yoluyla bilgisayarınızda bir test kılavuzu oluşturma

Kılavuzlar oluştururken her zaman bilgisayarınızda her zaman başlamanız gerekir. Adımları oluşturma, modeller seçme ve kılavuzun bağlantısının nasıl yapılacağı. Bu, daha sonra, HoloLens cihazınızda yazma modunda kılavuzunuz için içerik yerleştirilerek izlenir. Bu kılavuzun amaçları doğrultusunda, en az adım ve modellerle kısa bir test Kılavuzu yapmayı öneririz.

Kılavuzlar için yazma hakkında öğrenmeye başlamak isterseniz [yazma genel bakışı](https://docs.microsoft.com/dynamics365/mixed-reality/guides/authoring-overview)ile buradan başlayın. Ya da hızlı bir izlemeye genel bakış almak için bu kısa videoyu izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>İsteğe bağlı: bilgi noktası modu

Bilgi noktası modu, bir BT Yöneticisi tarafından yalnızca tek bir uygulamayı veya uygulama seçimini göstermek üzere başlangıç menüsünün Kullanıcı arabirimini yapılandırabilmesine olanak tanıyan bir moddur. Bir bilgi noktası belirli kullanıcılara, gruplara veya cihaz düzeyine de uygulanabilir; Bazı durumlarda, bazı kullanıcıların, düzenli Başlat menüsüne erişmesine izin verirken bazı kullanıcıları da bilgi noktasından hariç tutun.

Bilgi noktası modu, hem kapsam hem de yapılandırma ve ayrıca, bilgi noktası HoloLens 'e dağıtma yöntemlerinden birçok farklı değişkene sahiptir. Tüm bu değişkenler nedeniyle, bilgi noktası modu Bu kılavuz için _isteğe bağlı_ olarak kalmadı ve yeniden ziyaret edilmezler. Kullanılabilir uygulamaları kullanıcılarla kısıtlamak ya da daha fazla bilgi edinmek ve daha fazla bilgi almak istiyorsanız, [HoloLens 'i bir bilgi noktası olarak ayarlamayı](https://docs.microsoft.com/hololens/hololens-kiosk)öğrenmekten çekinmeyin.

## <a name="optional-wdac"></a>İsteğe bağlı: WDAC

WDAC, BT yöneticisinin cihazlarını cihazlarda uygulamaların başlatılmasını engelleyecek şekilde yapılandırmasına olanak sağlar. Bu, kullanıcının cihazdaki uygulamaları gizleyen bir kullanıcı arabirimi ile sunulduğu, ancak yine de başlatılabileceği, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır. WDAC uygulandığında, uygulamalar tüm uygulamalar listesinde görünmeye devam eder, ancak bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılabilmesini engeller.

Daha fazla bilgi için başvuru, [Microsoft Intune Ile HoloLens 2 cihazlarındaki uygulamalara izin vermek veya bunları engellemek IÇIN WDac ve Windows PowerShell kullanın](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

[Windows Defender uygulama denetimi-WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlı dağıtım-dağıtım](hololens2-corp-connected-deploy.md)