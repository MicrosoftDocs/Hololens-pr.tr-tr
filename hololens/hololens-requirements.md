---
title: Yaygın Dağıtım Senaryoları
description: Altyapı, Azure Active Directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens ve yönetme hakkında daha fazla bilgi edinebilirsiniz.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b8975d8eb362212eaf91966f4efa0bc22236327
ms.sourcegitcommit: 3f21b692be2f1b7f9c382f2b735b4c10339d4a78
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2021
ms.locfileid: "127934077"
---
# <a name="common-deployment-scenarios"></a>Yaygın Dağıtım Senaryoları

## <a name="overview"></a>Genel Bakış

Yeni bir cihazı nasıl dağıtacaklarını anlamak, ilk kez deneyebilirsiniz. Burada, kuruluş içinde 2 cihaza Microsoft HoloLens ve yönetmenin farklı yollarını paylaşıyoruz.

Çözümlerin büyük ölçekte dağıtılmasını istediğiniz. Sizi oraya almak istiyorum. Öncelikle hedef karma gerçeklik senaryona değer elde etmek için cihazları ve dolayısıyla hologramları dağıtma adımlarını konuşacağız. D365 Uzaktan Yardım, Kılavuzlar veya oluşturduğunuz Azure karma gerçeklik hizmeti etkinleştirilmiş bir uygulamayı kullanıyor olun, Ortak Dağıtım Senaryolarımız yolculuğunuza yol gösterir.

İşletme kararlarını veren, IT uzmanı veya kuruluş içinde çalışan ve benimsemeyi HoloLens bir yenilik ekibiysiniz. Kavram kanıtından ölçeklendirilen dağıtıma kadar her şey için dağıtım kılavuzlarımız, ne kadar büyük veya HoloLens fark etmez, IT altyapınız içindeki temel bilgileri anlar. En yaygın dağıtım senaryoları aşağıdakilerdir:

| Senaryo |Kullanım | Önemli noktalar |
|---------|---------|---------|
| [Senaryo A: Buluta bağlı cihazlar](hololens2-cloud-connected-overview.md) | Dağıtımınıza ilk kez baş olduğunuzda, yalnızca temel işlemi görmek için küçük bir başlangıç başlatabilirsiniz ve buluta bağlı tek bir cihaz dağıtabilirsiniz. | Cihazlar bulut hizmetleri ve genel İnternet'e bağlanır. Bu, müşteri kullanım örnekleri, alan hizmetleri ve kavram kanıtı için en uygundur.|
| [Senaryo B: Kuruluşun ağı](hololens2-corp-connected-overview.md) | Büyük ölçekte üretime dağıtım yapmak için kendi kuruluş ağıyla tümleştirebilirsiniz. | Cihazlar bir "Kurumsal" wi-fi ağına bağlanır. Bu, iç kullanıcılar için veya şirket ortamında kullanım için en uygundur.|
| [Senaryo C: Çevrimdışı güvenli ortam](hololens-common-scenarios-offline-secure.md) | Bazı görev açısından kritik süreçler veya bazı şirket ilkeleri çevrimdışı ortamların kullanımını talep ediyor olabilir. | Cihazlar yüksek oranda kısıtlayıcı bir ağa bağlanır veya tamamen çevrimdışı cihazlar olur. Bu, yüksek oranda güvenli ortamlar veya uzak alanlarda İnternet bağlantısı kısıtlamaları için uygundur. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Senaryo A: Buluta bağlı cihazlara dağıtma

Bu senaryo, yönetilen mobil cihazları bir şirket içinde dağıtmakla karşılaştırılabilir. HoloLens 2, birincil olarak şirket ağının dışında olan ortamlarda kullanım için dağıtılır. Şirket kaynaklarına erişilemiyor veya VPN üzerinden sınırlı olabilir.

[![Senaryo: Diyagram.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Aşağıdakiler için bu dağıtım modelini düşünün:

* Kavram kanıtı, pilot ve saha hizmetlerini dağıtma
* Remote [Assist'i dağıtma](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Temel Ortak Yapılandırmalar

* Wi-Fi ağlar genellikle İnternet ve bulut hizmetleri için tamamen açıktır
* Mobil Cihaz (MDM) Cihaz Yönetimi (MDM) ile Azure AD'ye Katılma --MDM (Intune) Yönetilen
* Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
  * Desteklenen cihaz başına tek veya birden çok kullanıcı
* Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.
* MDM aracılığıyla bir veya daha fazla uygulama dağıtılır

### <a name="common-challenges"></a>Yaygın Zorluklar

* Senaryo gereksinimlerine göre HoloLens 2'ye uygulanacak MDM yapılandırmalarını belirleme

İlgili Bulut Bağlantılı kılavuzunda, HoloLens 2'nin cihaz yönetiminize nasıl kaydedeceği, gerektiğinde lisansları nasıl uygulayacakları ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulama adımları açıklanır.

> [!div class="nextstepaction"]
> [Bulut Bağlantılı dağıtım kılavuzu](hololens2-cloud-connected-overview.md)

Kısa vadeli veya uzun vadeli dış kullanım için uzak bir siteye cihaz dağıtmak için Dış İstemciler kılavuzunu kullanın.

> [!div class="nextstepaction"]
> [Bulut Bağlantılı (Dış İstemciler) dağıtım kılavuzu](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Senaryo B: Kuruluş ağının içine dağıtma

Bu senaryo, çoğu bilgisayar için klasik dağıtımla Windows 10 aynıdır. HoloLens 2, şirket içi kaynaklara erişimi olan birincil olarak şirket ağına kullanım için dağıtılır. İnternet ve bulut hizmetleri sınırlı olabilir. 

[![Senaryo B1 diyagramı.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Senaryo B2 diyagramı.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Aşağıdakiler için bu dağıtım modelini düşünün:

* İç kullanıcılar
* Kurumsal ortamda büyük ölçekte dağıtma (Pilot ve Üretim)

### <a name="basic-common-configurations"></a>Temel Ortak Yapılandırmalar

* Wi-Fi, iç kaynaklara erişimi olan ve İnternet'e veya Bulut hizmetlerine sınırlı erişimi olan bir iç kurumsal ağdır.
* MDM Otomatik Kaydı ile Azure AD'ye Katılma
* MDM (Intune) Yönetilen
* Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
  * Desteklenen cihaz başına tek veya birden çok kullanıcı
* Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.
* MDM aracılığıyla bir veya daha fazla uygulama dağıtılır

### <a name="common-challenges"></a>Yaygın Zorluklar

* HoloLens 2, şirket içi AD'ye katılmayı veya System Center Configuration Manager (SCCM) desteklemez. MDM ile yalnızca Azure AD'ye katılma. Günümüzde birçok şirket, şirket içi AD'ye katılmış cihazlar olarak bu senaryoda Windows 10 bilgisayarlarını dağıtmaya devam ediyor ve SCCM tarafından yönetilen ve bulut tabanlı MDM çözümleri aracılığıyla iç Windows 10 cihazlarını yönetmek için dağıtılmış/yapılandırılmış altyapıya sahip olamayabilirsiniz.
* 2 HoloLens bir bulut ilk cihazı olduğundan, kullanıcı kimlik doğrulaması, işletim sistemi güncelleştirmeleri, MDM yönetimi ve diğer hizmetler için yoğun olarak İnternet'e ve buluta bağlı hizmetlere bağlıdır. Şirket ağına bağlanırken, büyük olasılıkla HoloLens 2 ve üzerinde çalıştıran uygulamalar için erişimi etkinleştirmek için ara sunucu/güvenlik duvarı kurallarının ayarlanması gerekir.
* Kurumsal Wi-Fi bağlantısı genellikle cihazın veya kullanıcının ağ kimlik doğrulaması için sertifikalar gerektirir. MDM aracılığıyla cihazlarına sertifika dağıtmak Windows 10 gerekli altyapının veya ayarların yapılandırılması zor olabilir.

İlgili Kurumsal Bağlı kılavuzu, HoloLens 2'nin mevcut cihaz yönetiminize nasıl kaydedilir, gerektiğinde lisanslar nasıl uygulanacak ve son kullanıcılarının bir Dynamics 365 Kılavuzu çalıştırabileceklerini ve cihaz ayarlandıktan sonra özel iş hattı uygulamalarını kullanabileceğini nasıl doğrulayabilecekleri hakkında bilgi verir.

> [!div class="nextstepaction"]
> [Kurumsal Bağlantılı dağıtım kılavuzu](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Senaryo C: Güvenli çevrimdışı ortamda dağıtma

Bu, yüksek oranda güvenli veya gizli konumlar için tipik bir dağıtımdır. HoloLens 2, ağ veya internet erişimine sahip değilken öncelikli olarak çevrimdışı kullanım için dağıtılır.

[![Çevrimdışı Güvenli diyagram 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Aşağıdakiler için bu dağıtım modelini düşünün:

* Verilerin kendi içinde korunarak korunarak yüksek oranda güvenli olduğu ortamlar
* Genel olarak cihazların kullanılamayacakları "Deneyimler"
* Uzak alanda İnternet bağlantısı sorunu

### <a name="basic-common-configurations"></a>Temel Ortak Yapılandırmalar

* Wi-Fi devre dışı bırakıldı. Gerekirse LAN bağlantısı için USB üzerinden Ethernet etkinleştirilebilir
* Yönetilmiyor
* Cihaz oturum açma için yerel kullanıcı hesabı
  * HoloLens 2 yalnızca bir yerel hesabı destekler
* Cihaz kilitleme yapılandırmalarının farklı düzeyleri, belirli kullanım örneklerine göre Sağlama Paketleri aracılığıyla uygulanır. Bu yapılandırmalar genellikle güvenli ortam gereksinimleri nedeniyle kısıtlanır
* Sağlama Paketi aracılığıyla bir veya daha fazla uygulama dağıtılır

### <a name="common-challenges"></a>Yaygın Zorluklar

* Sağlama paketleri aracılığıyla kullanılabilen sınırlı bir yapılandırma kümesi vardır
* Bulut hizmetleri kullanılamaz, bu nedenle 2. HoloLens sınırlayıcıdır.
* Bu cihazların el ile yapılandırılması, yapılandırılması ve güncelleştirilmiş olması nedeniyle daha yüksek yönetim yükü.

karşılık gelen çevrimdışı güvenli kılavuz, güvenli ortamlarda kullanılmak üzere HoloLens 2 ' ye kilitlenecek örnek bir sağlama paketi uygulamaya yönelik yönerge sağlar.

> [!div class="nextstepaction"]
> [Çevrimdışı güvenli ortam dağıtım kılavuzu](hololens-common-scenarios-offline-secure.md)
