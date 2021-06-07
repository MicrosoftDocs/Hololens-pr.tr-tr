---
title: HoloLens'i ticari bir ortamda ayarlama
description: Altyapı, Azure Active Directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtma ve yönetme hakkında daha fazla bilgi edinin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379061"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 kurumsal dağıtım ve yönetimi

Bu genel bakış, BT uzmanlarının kuruluş içinde 2 cihaz dağıtmaya ve yönetmeye Microsoft HoloLens dikkat edilmesi gerekenleri anlamalarını sağlar.

HoloLens 2, Windows 10 Holographic güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan sanal ağlarda çalışır. Windows 10 Holographic, şirketlere cihazları, verileri ve uygulamaları üzerinde denetim vermek için uz-2 4 cihaz yaşam döngüsü yönetimini destekler. HoloLens 2, kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak cihaz kaydı, yapılandırma ve uygulama yönetiminden bakım ve kullanımdan sonra standart yaşam döngüsü uygulamalarına kolayca dahil edilebilir.

## <a name="prepare"></a>Hazırlama

HoloLens 2'yi kurumsal kurumsal ortamınıza dağıtmaya hazır olurken, HoloLens 2'nin ölçek dağıtımlarını planlamaya başlarken gözden geçirilen ve anlaşılacak bazı noktalar vardır.

### <a name="infrastructure-essentials"></a>Altyapı TemelLeri

Kurumsal kurumsal dağıtım senaryosunda HoloLens 2 için, tüm özellikleri desteklemek için gereken bazı temel altyapı hizmetleri vardır. HoloLens 2, [modern](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) mobil Cihaz Yönetimi dağıtım ve yönetim için tasarlanmıştır. Azure AD Join + MDM, sürekli artan bir mobil iş gücünde bunu başarmanın birincil amacıdır. Aşağıdaki konular, HoloLens 2 için dağıtım planlamada dikkate alınacak her altyapı bileşenine kısa bir genel bakış sağlar.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD, kimlik ve erişim yönetimi sağlayan bulut tabanlı bir dizin hizmetidir. Karma kimlik çözümü oluşturmak için mevcut şirket içi dizinlerle tümleştirin. Microsoft Office 365 veya Intune kullanan kuruluşlar zaten üç sürümü olan Azure AD kullanıyor: Ücretsiz, Premium P1 ve Premium P2 (bkz. [Azure Active Directory sürümleri).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Tüm sürümler Azure AD cihaz kaydını destekler, ancak MDM otomatik kaydını etkinleştirmek için Premium P1 gereklidir. HoloLens 2, Azure Active Directory düzeydeki özelliklerin ve işlevlerin çoğunu etkinleştirmek için bir Join gerektirir.

> [!NOTE]
> HoloLens 2'de şirket içi Active Directory'ye Katılma desteklenmiyor.

### <a name="mobile-device-management"></a>Mobil Cihaz Yönetimi
HoloLens 2, kurumsal bir ortamdaki Mobile Cihaz Yönetimi (MDM) sistemleri tarafından yönetilecek şekilde tasarlanmıştır. Enterprise Mobility + Security'nin bir parçası olan Microsoft [Intune,](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)kuruluşta cihazları yöneten bulut tabanlı bir MDM sistemidir. Office 365'te olduğu gibi, Intune da kimlik yönetimi için Azure AD kullanır. Bu nedenle, çalışanlar, Office 365'te oturum atırken kullandığı cihazları Intune'a kaydetmek için aynı kimlik bilgilerini kullanır. Birden çok MDM sistemi, Windows 10 ve çoğu da kişisel ve kurumsal cihaz dağıtım senaryolarını destekler. MDM sistemleri HoloLens 2 için uygulama dağıtımlarını ve güncelleştirmelerini de yönetebilir. HoloLens 2'i destekleyen diğer MDM sağlayıcıları şunlardır: AirWatch, MobileIron ve diğerleri. Tüm MDM sistem satıcıları Windows 10 cihaz yönetimi yapılandırma hizmeti sağlayıcılarına (CSP) eşit erişime sahiptir ve bu da, IT kuruluşlarına yönetim gereksinimlerine en uygun sistemi (Microsoft Intune veya üçüncü taraf MDM ürünü) seçme özgürlüğü sağlar.

> [!NOTE]
> HoloLens 2'de System Center Yapılandırma Yöneticisi geleneksel şirket içi PC yönetim sistemleri desteklenmiyor.

### <a name="windows-update-for-business"></a>İş İçin Windows Update
Microsoft İş İçin Windows Update, GÜNCELLEŞTIRMEleri cihaz gruplarına dağıtma ve güncelleştirmeleri yüklemeye Windows Update bakım pencereleri tanımlama gibi ek Windows Update odaklı yönetim özellikleri sağlayacak şekilde tasarlanmıştır. [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2 güncelleştirmelerini yönetme hakkında ayrıntılı bilgi için HoloLens güncelleştirmeleri belgelerine bakın.

### <a name="certificates"></a>Sertifikalar
Ortamınız Corp Wi-Fi ağ kimlik doğrulaması veya diğer kaynaklara erişim gerektiriyorsa HoloLens 2, MDM aracılığıyla sertifikaların dağıtımını destekler. HoloLens 2'ye sertifika dağıtımlarını etkinleştirmek için bazı MDM altyapı yapılandırmaları gerekebilir. [HoloLens 2 için sertifikaları ve ağ profillerini hazırlama hakkında bilgi okuyun.](https://docs.microsoft.com/hololens/hololens-certificates-network) Intune kullanıyorsanız sertifika yapılandırma [ayrıntılarına göz](https://docs.microsoft.com/mem/intune/protect/certificates-configure) atabilirsiniz.

## <a name="configure"></a>Yapılandırma

MDM yöneticileri, bir MDM sistemine kayıtlı herhangi bir şirket cihazında ilke ayarlarını tanımlayabilir ve uygulama. Hangi yapılandırma ayarlarını kullanmalısınız, dağıtım senaryosuna göre farklılık gösterir. Bu Windows 10, Yapılandırma Hizmeti Sağlayıcıları (CSP) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu ayarlar kayıt defteri anahtarları veya dosyalarıyla eşler. HoloLens 2 için Windows 10 yönetimi CSP'leri hakkında daha fazla bilgi için, [HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)cihazlarında desteklenen CSP'lerin tam listesine bakın.

HoloLens 2, özel sağlama paketleri aracılığıyla sınırlı bir CSP yapılandırma kümesi ayarlamayı da destekler. Sağlama paketleri genellikle MDM tarafından yönetilmeyen cihazlar için kullanılır ve her cihaza el ile uygulanması gerekir. Özel sağlama paketleri oluşturma hakkında ayrıntılı bilgi için [HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) sağlama belgelerine bakın.

> [!NOTE]
> HoloLens [2, şirket Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)cihaz yapılandırmalarınızı yönetmek için kolay ve basit bir işlem sağlayan Windows 10 destekler.

### <a name="identity-management"></a>Kimlik Yönetimi

Çalışanlar, bir cihazı başlatmak için yalnızca bir hesap kullanabilir&#39;önce hangi hesabın etkinleştirildikten sonra kuruluş tarafından kontrol etkinleştirilmiş olması gerekir. Seçilen hesap, cihazı kimin kontrol altında olduğunu belirler ve yönetim özelliklerinizi etkiler. HoloLens 2, 3 hesap türü destekler: Yerel Kullanıcı hesabı, kişisel Microsoft Hesabı ve Azure Active Directory Hesapları. HoloLens 2 Azure Active Directory tüm özellikleri etkinleştirecek olan kurumsal kimlik yönetimi çözümünüz için bu çözümden faydalanmanızı kesinlikle öneririz. [HoloLens](https://docs.microsoft.com/hololens/hololens-identity) 2 kimlikleri hakkında daha fazla bilgi için HoloLens kimliği'ne göz atabilirsiniz.

### <a name="network-and-connectivity"></a>Ağ ve Bağlantı

HoloLens 2 buluta ilk kez sahip olduğu için tüm işlevlerin ve yeteneklerin kullanılabilir olması için çevrimiçi kaynaklara ağ erişimi gerekir. Kurumsal intranet ağınıza bağlantısı olan HoloLens 2 cihazları dağıtıyorsanız, HoloLens 2 bulut hizmetlerine erişime izin vermek için ara sunucu/güvenlik duvarı kurallarınızı güncelleştirmeniz gerekebilir. Daha fazla bilgi için [HoloLens 2 işletim sistemi](https://docs.microsoft.com/hololens/hololens-offline)için ortak uç noktalar listesine göz atabilirsiniz. Uygulamaların veya diğer bulut hizmetlerinin HoloLens 2'de başarıyla çalışması için ek uç noktalara erişim gerekebilir.

Ek uç nokta erişimi gerektiren bazı yaygın HoloLens 2 hizmetleri şunlardır:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 Kılavuzları](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (O365 Teams Altyapısı)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Sertifika Dağıtımı

Kurumsal ağlara veya kuruluş içindeki Wi-Fi için sertifikalar gerekli ise HoloLens 2, MDM aracılığıyla kullanıcı ve cihaz sertifikası dağıtımını destekler. Not: MDM çözümünüz, diğer cihazlara sertifika dağıtmak için ek Windows 10 gerektirmektedir.

### <a name="security-review"></a>Güvenlik İncelemesi

Çoğu kurumsal IT departmanı, kurumsal bir kurumsal ağa dağıtılan yeni cihazların değerlendirilmesi ve gözden geçirmesini gerektirir. HoloLens 2'nin güvenlik incelemesine ihtiyaç varsa, güvenlik onaylarını alma konusunda yardım almak için [daha fazla ayrıntı bulabilirsiniz.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Yaygın HoloLens 2 Cihaz Ayarları

HoloLens 2 cihazlarını kurumsal bir kuruluş ortamına dağıtırken, HoloLens 2 dağıtımınızı planlarken dikkate alınacak bir dizi ortak cihaz yapılandırması vardır. Bu liste, oldukça yaygın olduğu görülen yapılandırmaları ve ayarları vurgular ve kullanılabilir seçeneklerin tam listesini oluşturmaz:

| Cihaz Ayarı | Kısa açıklama.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Donanım kısıtlamaları](hololens-requirements.md#hardware-restrictions)               | Donanım kısıtlamaları, bağlantıları azaltır ve veri korumasına yardımcı olur.                        |
| [Wi-Fi profilleri](hololens-requirements.md#wi-fi-profiles)               | Kullanıcı Wi-Fi etkileşim olmadan profillerini yapılandırma.                              |
| [Sertifikalar](hololens-requirements.md#certificates-1)               | Web içeriği için hesap ve/Wi-Fi kimlik doğrulaması, VPN şifrelemesi ve SSL şifrelemesi sağlama. |
| [Proxy](hololens-requirements.md#proxy)              | İç trafiği yönetme.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Şirketin intraneti üzerinde uygulama ve kaynaklara erişimi denetleme.                               |
| [Bilgi Noktası Modu](hololens-requirements.md#kiosk-mode) | Kullanıcı arabirimi aracılığıyla kullanıcılara sunulan uygulamaları sınırlar. |

#### <a name="hardware-restrictions"></a>Donanım kısıtlamaları

HoloLens 2; kameralar, mikrofonlar, konuşmacılar, USB arabirimleri, Bluetooth arabirimleri ve Wi-Fi gibi popüler donanım özelliklerini içeren en son teknolojiden sahiptir. Bu özelliklerin kullanılabilirliğini kontrol etmek için donanım kısıtlamalarını kullanabilirsiniz.

Aşağıda, HoloLens 2'nin donanım kısıtlamalarını yapılandırmak için desteklediği en yaygın kullanılan MDM ayarları liste almaktadır. Bu donanım kısıtlamalarının bazıları bağlantı sağlar ve veri korumasına yardımcı olur.

- [**WiFi'ye izin ver:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Kullanıcıların cihazlarında Wi-Fi ve kullanıp kullanamayıp kullanamay
- [**USB Bağlantısına İzin Ver:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB bağlantısının etkin olup olmadığı (&#39;USB ücretlendirmesini etkilemez)
- [**Bluetooth'a izin ver:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Kullanıcıların cihazlarında Bluetooth radyoyu etkinleştirip kullanamayabiliyor mu?

Diğer yaygın cihaz kısıtlamaları [hakkında daha fazla bilgi edinebilirsiniz.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Wi-Fi profilleri

Çoğu kurumsal Wi-Fi, kullanıcı erişimini kısıtlamak ve güvenliğini sağlamak için sertifikalar ve diğer karmaşık bilgiler gerektirir. Bu gelişmiş Wi-Fi bilgileri tipik kullanıcılar için yapılandırmak zordur, ancak MDM sistemleri kullanıcı müdahalesi olmadan bu Wi-Fi profillerini tam olarak yapılandırabilirsiniz. MDM sistemi Wi-Fi birden çok profil oluşturabilirsiniz.

Yapılandırma ayarları hakkında daha Wi-Fi için Windows 10 Bkz. [Kurumsal Profil WiFi ayarları.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Sertifikalar

Sertifikalar, Web içeriğinin hesap kimlik doğrulaması, Wi-Fi kimlik doğrulaması, VPN şifrelemesi ve SSL şifrelemesi sağlayarak güvenliği artırmaya yardımcı olur. Yöneticiler, cihazlarda cihazları sağlama paketleri aracılığıyla el ile yönetebilse de, bu sertifikaları tüm yaşam döngüsünün tamamında (yenileme ve iptal etme yoluyla) yönetmek üzere MDM sisteminizi kullanmak için en iyi yöntem&#39;. MDM sisteminiz, cihaz kaydolduktan sonra bu sertifikaları&#39; sertifika depolarına otomatik olarak dağıtabilir (MDM sistemi Basit Sertifika Kayıt Protokolü (SCEP) veya ortak anahtar şifreleme standartlarını #12 (PKCS # 12)). MDM, kayıtlı istemci sertifikalarını sorgulayabilir ve silebilir ya da geçerli sertifikanın süre dolmadan önce yeni bir kayıt isteği tetikleyebilirsiniz.

[HoloLens 2 için sertifikaları ve ağ profillerini hazırlama](https://docs.microsoft.com/hololens/hololens-certificates-network) hakkında daha fazla bilgi edinin.

#### <a name="proxy"></a>Ara sunucu

Çoğu kurumsal intranet ağlarının iç trafiği yönetmek için bir proxy 'den faydalanır. HoloLens 2 ' de, Ethernet ve Wi-Fi bağlantıları için bir proxy sunucu yapılandırabilirsiniz. Bu ayarlar VPN bağlantıları için geçerlidir.

Windows 10 için ara sunucu ayarları hakkında daha fazla bilgi için bkz. [Networkproxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>VPN

Kuruluşlar, şirket&#39;s intranetinde bulunan uygulamalara ve kaynaklara erişimi denetlemek için genellikle bir VPN kullanır. HoloLens 2, Microsoft Store indirilebilir bir eklenti gerektiren SSL VPN bağlantılarını destekler ve seçtiğiniz VPN satıcısına özgüdür.

VPN profilleri hakkında daha fazla bilgi için bkz. [VPNV2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Bilgi noktası modu

Cihaz bilgi noktası modunda çalışacak şekilde yapılandırarak bir HoloLens 2 cihazını, bilgi noktası olarak da bilinen sabit amaçlı bir cihaz olarak çalışacak şekilde yapılandırabilirsiniz. Bilgi noktası modu, cihazdaki kullanılabilir uygulamaları (veya kullanıcıları) sınırlandırır. Bilgi noktası modu, HoloLens 2 cihazını iş uygulamalarına ayırmak veya bir uygulama tanıtımında HoloLens 2 cihazını kullanmak için kullanabileceğiniz kullanışlı bir özelliktir.

Bilgi noktası modunda HoloLens 2 ' yi yapılandırma hakkında daha fazla bilgi için bkz. [bilgi noktası olarak HoloLens kurulumu](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Dağıtma

### <a name="mdm-device-enrollment"></a>MDM cihaz kaydı

Kurumsal dağıtımlarda, cihazları yalnızca Azure AD JOIN ve otomatik MDM kaydı (Azure AD + MDM) ile kurumsal cihazlar olarak MDM 'ye [kaydetmeniz](https://docs.microsoft.com/hololens/hololens-enroll-mdm) önerilir. Bu, Azure AD Premium gerektirir ve Intune dahil olmak üzere çeşitli MDM sağlayıcılarının otomatik kaydını destekler.

Kendi kendine dağıtım [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)kayıt yöntemi hakkında daha fazla bilgi edinin.

### <a name="application-deployment"></a>Uygulama Dağıtımı

Mobil cihazlarda kullanıcı üretkenliği genellikle uygulamalar tarafından çalıştırılır.

Windows 10, Windows uygulamaları için Evrensel Windows Platformu (UWP) kullanarak birden çok cihazda sorunsuz şekilde çalışan uygulamalar geliştirmeyi mümkün kılar.

HoloLens 2 cihazlarına uygulama dağıtmanın birden çok yolu vardır. Uygulamalar MDM aracılığıyla doğrudan dağıtılabilir, Iş için Microsoft Store veya bir sağlama paketi aracılığıyla dışarıdan yüklenebilir. Daha fazla bilgi için [uygulama dağıtım](https://docs.microsoft.com/hololens/app-deploy-overview) belgelerine göz atın.

> [!NOTE]
> HoloLens 2 yalnızca UWP ARM64 uygulamalarının çalıştırılmasını destekler.

## <a name="maintain"></a>Bakım

Kurumsal BT ortamlarında, güvenlik ve maliyet denetimi gereksinimi, kullanıcılara en son teknolojileri sağlama gereksinimine karşı dengelenmesi gerekir. Cybersaldýrlar günlük bir oluşum olduğundan, Windows 10 cihazlarınızın durumunu düzgün bir şekilde korumak önemlidir. Yapılandırma ayarlarını kontrol etmek ve bunların, bunların, iç uygulamalara hangi cihazların erişebileceğini zorlayacağı bir şekilde tutulmasını sağlaması gerekir. HoloLens 2 cihazların kurumsal ilkeyle uyumlu olduğundan emin olmak için gereken mobil işlemler yönetimi özelliklerini sunar.

### <a name="os-servicing-options"></a>İşletim sistemi hizmet seçenekleri

**Kolaylaştırılmış güncelleştirme süreci**

Microsoft, Windows ürün mühendislerini ve yayın döngüsünü kolaylaştırmıştır. böylece pazar tarafından talep edilen yeni özellikler, deneyimler ve işlevler, hiç olmadığı kadar hızlı bir şekilde teslim edilebilir. Microsoft, yıl başına iki özellik güncelleştirmesi sunmayı planlamaktadır (12 aylık süre). **Özellik güncelleştirmeleri** güncel DALı veya CB, ilişkili bir sürüme sahip.

Microsoft ayrıca, güvenlik ve kararlılık için güncelleştirmeleri doğrudan HoloLens 2 cihazlarına teslim eder ve yükler. Windows Update aracılığıyla Microsoft denetimi altında yayınlanan bu **kalite güncelleştirmeleri** aylık olarak kullanılabilir. HoloLens 2 aynı standart güncelleştirme sürecinin bir parçası olarak özellik güncelleştirmelerini ve kalite güncelleştirmelerini kullanır.

Kurumsal müşteriler, bir MDM sistemi kullanarak HoloLens 'te güncelleştirme deneyimini ve sürecini yönetebilir. Çoğu durumda, güncelleştirme işlemini yönetmeye yönelik ilkeler her iki özellik ve kalite güncelleştirmeleri için de geçerlidir. [HoloLens güncelleştirmeleri IÇIN MDM 'yi yapılandırma konusunda](https://docs.microsoft.com/hololens/hololens-updates)daha fazla bilgi.

### <a name="managing-applications"></a>Uygulamaları yönetme

BT yöneticileri, HoloLens 2 ' de hangi uygulamaların yüklü olduğunu ve bunların güncel tutulması gerektiğini denetleyebilir.

HoloLens 2, yöneticilerin Microsoft Store uygulama listelerinin oluşturulmasını, izin vermemesine veya izin vermemesine olanak sağlayan [Windows Defender uygulama denetimi 'ni (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)destekler. Bu yetenek, yerleşik uygulamalara da genişletilir. Uygulamalara izin verme veya reddetme özelliği, kullanıcıların cihazlarını amaçlanan amaçlarla kullanmasını sağlamaya yardımcı olur. Ancak, çalışanların ihtiyacı olan veya istek ve güvenlik sorunları arasında bir denge bulmak için her zaman kolay bir yaklaşım değildir. İzin verme veya engelleme listelerinin oluşturulması ayrıca Microsoft Store değişen uygulamayla yatay olarak tutulmasını gerektirir.

Daha ayrıntılı bilgi için bkz. [uygulama denetımı CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Devre Dışı Bırakma

Cihaz kullanımdan kaldırma, cihaz yaşam döngüsünün son aşamasıdır. Bu&#39;, tüm şirket verilerinin, verilerin gizliliğini tehlikeye atabilecek bırakılmış cihazlarda kalmasını istemediğiniz için, daha yeni modeller ile değiştirilen cihazların güvenli bir şekilde&#39;kullanımdan kalktığı için önemlidir. Ayrıca, kaybolan veya çalınan cihazları silmesi gereken kullanıcıları yeterince desteklemek için bir yol gerekir.

HoloLens 2 cihazı silme 3 yöntemini destekler

**MDM fabrika silme:** HoloLens 2 ' i yönetici tarafından başlatılan MDM komutu aracılığıyla fabrika görüntüsüne geri döndürür. Cihazdaki tüm depolanmış verileri siler.

**Cihaz ayarları Içinden sıfırlandı:** Son kullanıcılar, cihaz üzerindeki ayarlar uygulamasında bulunan HoloLens 2 ' ye el ile sıfırlayabilirler. Cihazdaki tüm depolanmış verileri siler.

**Gelişmiş kurtarma Yardımcısı (ARC):** Bir kullanıcı veya yönetici, yay aracını çalıştıran bir BILGISAYARDAN USB kablosu aracılığıyla BILGISAYARA bağlı bir HoloLens 2 ' yi Flash kullanabilir. Cihazdaki tüm depolanmış verileri siler.

> [!div class="nextstepaction"]
> [Ortak dağıtım senaryoları](common-scenarios.md)
