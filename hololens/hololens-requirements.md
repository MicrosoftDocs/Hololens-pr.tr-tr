---
title: Ortak dağıtım senaryoları
description: altyapı, Azure Active Directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtma ve yönetme hakkında daha fazla bilgi edinin.
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
ms.openlocfilehash: 27fd7f81d2868134344c7563ebc0a93133a18c0a217d6eff820b5f322e9271a7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662915"
---
# <a name="common-deployment-scenarios"></a>Ortak dağıtım senaryoları

## <a name="overview"></a>Genel Bakış

Yeni bir cihazın nasıl dağıtılacağını öğrenmek, ilk kez deneme sırasında bir kilitlenme olabilir. burada, kuruluş içinde Microsoft HoloLens 2 cihazlarını dağıtmak ve yönetmek için farklı yollar paylaşıyoruz.

Çözümlerin ölçekli olarak dağıtılmasını istiyorsunuz. Buradan yararlanmak istiyoruz. D365 uzaktan yardım, kılavuzlar veya oluşturduğunuz Azure Karma Gerçeklik hizmeti özellikli bir uygulama kullanıp kullanmayacağınızı, hedef karma gerçeklik senaryonuz için değer elde etmek üzere, bu nedenle, cihaz dağıtma adımları hakkında konuşalım.

kuruluşunuz dahilinde HoloLens benimsemek için bir iş kararı oluşturucu, bt uzmanı veya bir yenilik ekibi olabilirsiniz. kavram kanıtı olarak ölçeklenen bir dağıtıma oluştururken dağıtım kılavuzlarımız, büyük veya küçük bir fark olmadan bt altyapınızda HoloLens anlamlı hale getirir. Aşağıdaki dağıtım senaryoları en yaygın olarak verilmiştir:

| Senaryo |Kullanım | Önemli noktalar |
|---------|---------|---------|
| [Senaryo A: buluta bağlı cihazlar](hololens2-cloud-connected-overview.md) | Dağıtıma ilk kez başladığınızda, temel süreci görmek için küçük bir başlangıç yapın ve buluta bağlı tek bir cihazı dağıtabilirsiniz. | Cihazlar, bulut hizmetleri ve genel İnternet 'e bağlanır. Bu, müşteri kullanım örnekleri, alan Hizmetleri ve kavram kanıtı için en uygundur.|
| [Senaryo B: kuruluşun ağı](hololens2-corp-connected-overview.md) | Ölçekli üretime dağıtırken kendi kuruluşunuzun ağıyla tümleştirmeniz gerekebilir. | Cihazlar, "Kurumsal" bir Wi-Fi ağına bağlanır. Bu, dahili kullanıcılar için en uygun veya şirket ortamında kullanım için uygundur.|
| [Senaryo C: çevrimdışı güvenli ortam](hololens-common-scenarios-offline-secure.md) | Görev açısından kritik bazı süreçler veya bazı kurumsal ilkeler, çevrimdışı ortamların kullanımını talep edebilir. | Cihazlar, yüksek oranda kısıtlayıcı bir ağa bağlanacak veya yalnızca çevrimdışı cihazlar olacaktır. Bu, büyük ölçüde güvenli ortamlar veya uzak alanlardaki internet bağlantısı kısıtlamaları için en uygun seçenektir. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Senaryo A: buluta bağlı cihazlara dağıtma

Bu senaryo, yönetilen mobil cihazların bir şirket içinde dağıtılmasıyla karşılaştırılabilir. HoloLens 2, öncelikli olarak kurumsal ağa harici ortamlarda kullanılmak üzere dağıtılır. Şirket kaynaklarına erişilmez veya VPN aracılığıyla sınırlı olabilir.

[![Senaryo bir diyagram](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Şu dağıtım modelini göz önünde bulundurun:

* Kavram kanıtı, pilotlar ve alan hizmetlerini dağıtma
* [Uzaktan Yardım](hololens2-options-remote-assist.md) dağıtma

### <a name="basic-common-configurations"></a>Temel ortak yapılandırma

* Wi-Fi ağlar genellikle internet ve bulut hizmetlerine tamamen açıktır
* Mobil cihaz yönetimi (MDM) otomatik kayıt--MDM (Intune) ile Azure AD 'ye ekleme
* Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
  * Cihaz başına desteklenen tek veya birden çok Kullanıcı
* Cihaz kilitleme yapılandırmalarının farklı düzeyleri, tam açık olan tek uygulama bilgi noktası arasında belirli kullanım durumlarına göre uygulanır.
* Bir veya daha fazla uygulama MDM aracılığıyla dağıtıldı

### <a name="common-challenges"></a>Yaygın sorunlar

* senaryo gereksinimlerine bağlı olarak HoloLens 2 ' ye hangi MDM yapılandırmalarının uygulanacağını belirleme

karşılık gelen bulut bağlantılı kılavuzu, cihaz yönetimine HoloLens 2 kaydetme, lisansları gerektiğinde uygulama ve son kullanıcılarınızın cihaz kurulumu sırasında uzaktan yardım 'ı hemen kullanabildiğini doğrulama konularını ele almaktadır.

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım kılavuzu](hololens2-cloud-connected-overview.md)

Kısa vadeli veya uzun vadeli dış kullanım için uzak bir siteye cihaz dağıtmak üzere dış Istemciler kılavuzunu kullanın.

> [!div class="nextstepaction"]
> [Buluta bağlı (dış Istemciler) dağıtım kılavuzu](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Senaryo B: kuruluşunuzun ağı içinde dağıtma

bu senaryo, çoğu Windows 10 pc için klasik bir dağıtımla aynıdır. HoloLens 2, birincil kurumsal kaynaklara erişimi olan kurumsal ağda kullanılmak üzere dağıtılır. Internet ve bulut hizmetleri sınırlı olabilir. 

[![Senaryo B1 diyagramı](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Senaryo B2 diyagramı](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Şu dağıtım modelini göz önünde bulundurun:

* İç kullanıcılar
* Şirket ortamında ölçeğe (pilot ve üretim) dağıtım

### <a name="basic-common-configurations"></a>Temel ortak yapılandırma

* Wi-Fi ağ, iç kaynaklara erişimi olan bir dahili kurumsal ağ ve internet veya bulut hizmetlerine sınırlı erişim sağlar.
* MDM otomatik kayıt ile Azure AD 'ye ekleme
* MDM (Intune) yönetiliyor
* Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
  * Cihaz başına desteklenen tek veya birden çok Kullanıcı
* Cihaz kilitleme yapılandırmalarının farklı düzeyleri, tam açık olan tek uygulama bilgi noktası arasında belirli kullanım durumlarına göre uygulanır.
* Bir veya daha fazla uygulama MDM aracılığıyla dağıtıldı

### <a name="common-challenges"></a>Yaygın sorunlar

* HoloLens 2, şirket içi AD joın veya System Center Configuration Manager (SCCM) üzerinde desteklenmez. MDM ile yalnızca Azure AD katılımı. günümüzde pek çok şirket şirket içi AD 'ye katılmış cihazlarda Windows 10 bilgisayarları dağıtmakta, SCCM tarafından yönetilen ve bulut tabanlı MDM çözümleri aracılığıyla iç Windows 10 cihazlarını yönetmek için dağıtılan/yapılandırılmış altyapıyı içermeyebilir.
* HoloLens 2 bir bulut ilk cihaz olduğundan, kullanıcı kimlik doğrulaması, işletim sistemi güncelleştirmeleri, MDM yönetimi vb. için internet ve bulut bağlantılı hizmetleri yoğun bir şekilde kullanır. bir kurumsal ağa bağlanırken, proxy/güvenlik duvarı kurallarının büyük olasılıkla HoloLens 2 ve üzerinde çalışan uygulamalar için erişimi etkinleştirmek üzere ayarlanması gerekir.
* Şirket Wi-Fi bağlantısı, genellikle cihazın veya kullanıcının kimliğini doğrulamak için sertifika gerektirir. MDM aracılığıyla Windows 10 cihazlara sertifika dağıtmaya yönelik gerekli altyapı veya ayarların yapılandırılması zor olabilir.

buna karşılık gelen kurumsal bağlantı kılavuzu, mevcut cihaz yönetimine HoloLens 2 kaydetme, lisansları gerektiği gibi uygulama ve son kullanıcılarınızın bir Dynamics 365 kılavuzu çalıştırabildiğini ve cihaz kurulduktan sonra özel iş kolu uygulamalarını kullanmasını söyler.

> [!div class="nextstepaction"]
> [Kurumsal bağlı dağıtım kılavuzu](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Senaryo C: güvenli çevrimdışı ortamda dağıtma

Bu, yüksek oranda güvenli veya gizli konumlar için tipik bir dağıtımdır. HoloLens 2, ağ veya internet erişimi olmadan birincil olarak çevrimdışı kullanım için dağıtılır.

[![Çevrimdışı güvenli diyagram 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Kullanılması gereken durumlar

Şu dağıtım modelini göz önünde bulundurun:

* Verilerin şirket içinde korunması gereken yüksek oranda güvenli ortamlar
* Ortak cihazların kullanıldığı "deneyimler"
* Uzak alanda Internet bağlantısı sorunu

### <a name="basic-common-configurations"></a>Temel ortak yapılandırma

* Wi-Fi bağlantısı devre dışı bırakıldı. Gerekirse, USB üzerinden Ethernet LAN bağlantısı için etkinleştirilebilir
* Yönetilmiyor
* Cihaz oturum açma için yerel kullanıcı hesabı
  * HoloLens 2 yalnızca bir yerel hesabı destekler
* Cihaz kilitleme yapılandırmalarının farklı düzeyleri, belirli kullanım örneklerine göre sağlama paketleri aracılığıyla uygulanır. Bu yapılandırma genellikle güvenli ortam gereksinimleri nedeniyle kısıtlanır
* Bir veya daha fazla uygulama sağlama paketi aracılığıyla dağıtıldı

### <a name="common-challenges"></a>Yaygın sorunlar

* Sağlama paketleri aracılığıyla kullanılabilen sınırlı bir yapılandırma kümesi vardır
* bulut hizmetleri kullanılamaz, bu nedenle HoloLens 2 yeteneklerini sınırlandırdık.
* Bu cihazların el ile ayarlanması, yapılandırılması ve güncellenmesi gerektiğinden daha yüksek yönetim yükü.

karşılık gelen çevrimdışı güvenli kılavuz, güvenli ortamlarda kullanılmak üzere HoloLens 2 ' ye kilitlenecek örnek bir sağlama paketi uygulamaya yönelik yönerge sağlar.

> [!div class="nextstepaction"]
> [Çevrimdışı güvenli ortam dağıtım kılavuzu](hololens-common-scenarios-offline-secure.md)
