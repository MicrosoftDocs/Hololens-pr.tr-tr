---
title: Ticari bir ortamda HoloLens 2 dağıtımını planlama
description: Altyapı, sanal ağ ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtma ve yönetme hakkında daha fazla bilgi Azure Active Directory bilgi edinebilirsiniz.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924613"
---
# <a name="common-deployment-scenarios"></a>Yaygın Dağıtım Senaryoları

## <a name="overview"></a>Genel Bakış

Bu sayfa, kuruluş içinde 2 cihaz dağıtma ve yönetmeye ilişkin üç yaygın senaryo için Microsoft HoloLens üst düzey mimariye genel bakış sağlar.

Genellikle, cihazlarınızı yönetme ve kuruluş kaynaklarına erişme, büyük ölçüde zaten var olan faktörler tarafından belirlenir. Mevcut altyapınıza bağlı olarak, aşağıdaki senaryolarda ortak cihaz yönetimi stilini (MDM) gözden geçirmenizi ve ardından hangi senaryonun ihtiyaçlarınıza uygun olduğunu belirlemek için ticari bir ortamda [HoloLens 2](hololens-core-components.md) dağıtımlarını planlama makalesini okumaya davet ediyoruz. Dağıtımınız sırasında kullanabileceğiniz üç ilgili kılavuz da vardır.


 1. [Buluta bağlı ortam dağıtım kılavuzu](hololens2-cloud-connected-overview.md)
     1. [Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu](hololens2-deployment-guide.md)
 1. [Kurumsal ağ dağıtım kılavuzu](hololens2-corp-connected-overview.md)
 1. [Çevrimdışı güvenli ortam dağıtım kılavuzu](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Senaryo A: Buluta bağlı cihazlara dağıtma

Bu senaryo, yönetilen mobil cihazları bir şirket içinde dağıtmakla karşılaştırılabilir. HoloLens 2, öncelikli olarak şirket ağının dışında olan ortamlarda kullanım için dağıtılır. Şirket kaynaklarına erişilemiyor veya VPN üzerinden sınırlı olabilir. 
 * Temel Ortak Yapılandırmalar
   * Wi-Fi ağlar genellikle İnternet ve Bulut hizmetleri için tamamen açıktır.
   * Azure AD'ye Mobil Cihaz Yönetimi (MDM) Otomatik Kaydı--MDM (Intune) Tarafından Yönetilen
   * Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
     * Desteklenen cihaz başına tek veya birden çok kullanıcı
   * Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.
   * MDM aracılığıyla bir veya daha fazla uygulama dağıtılır

* Yaygın Zorluklar
   * Senaryo gereksinimlerine göre HoloLens 2'ye uygulanacak MDM yapılandırmalarını belirleme.

[![Senaryo A diyagramı ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

İlgili Buluta bağlı kılavuzda HoloLens 2'nin cihaz yönetiminize nasıl kaydedeceği, gerektiğinde lisansları nasıl uygulayacakları ve cihaz kurulumu sırasında son kullanıcılarının Remote Assist'i hemen kullanabileceğini doğrulama adımları yer almaktadır. Kısa vadeli veya uzun vadeli dış kullanım için uzak bir siteye cihaz dağıtmak için Dış İstemciler kılavuzunu kullanın.

> [!div class="nextstepaction"]
> [Buluta bağlı ortam dağıtım kılavuzu](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Buluta bağlı ortam (Dış İstemciler) dağıtım kılavuzu](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Senaryo B: Kuruluş ağının içine dağıtma

Bu senaryo, çoğu bilgisayar için klasik dağıtımla Windows 10 aynıdır. HoloLens 2, şirket içi kaynaklara erişimi olan birincil olarak şirket ağına kullanım için dağıtılır. İnternet ve bulut hizmetleri sınırlı olabilir. 

 * Temel Ortak Yapılandırmalar
   * Wi-Fi, iç kaynaklara erişimi olan ve İnternet'e veya Bulut hizmetlerine sınırlı erişimi olan bir iç kurumsal ağdır.
   * MDM Otomatik Kaydı ile Azure AD'ye Katılma
   * MDM (Intune) Yönetilen
   * Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
     * Desteklenen cihaz başına tek veya birden çok kullanıcı
   * Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre farklı cihaz kilitleme yapılandırma düzeyleri uygulanır.
   * MDM aracılığıyla bir veya daha fazla uygulama dağıtılır

 * Yaygın Zorluklar
   * HoloLens 2, şirket içi AD'ye katılmayı veya SCCM'i desteklemez. MDM ile yalnızca Azure AD'ye katılma. Günümüzde birçok şirket, System Center Yapılandırma Yöneticisi (SCCM) tarafından yönetilen şirket içi AD'ye katılmış cihazlar olarak bu senaryoda Windows 10 bilgisayarlarını dağıtmaya devam ediyor ve bulut tabanlı MDM çözümleri aracılığıyla iç Windows 10 cihazlarını yönetmek için dağıtılmış/yapılandırılmış altyapıya sahip olabilir.
   * HoloLens 2 buluta özel bir cihaz olduğundan, Kullanıcı kimlik doğrulaması, işletim sistemi güncelleştirmeleri, MDM yönetimi ve diğer hizmetler için yoğun olarak İnternet'e ve buluta bağlı hizmetlere bağlıdır. Şirket ağına bağlanırken Büyük olasılıkla HoloLens 2'ye ve üzerinde çalıştıran uygulamalara erişimi etkinleştirmek için Ara Sunucu/Güvenlik Duvarı kurallarının ayarlanması gerekir.
   * Kurumsal Wi-Fi bağlantısı genellikle cihazın veya kullanıcının ağ kimlik doğrulaması için sertifikalar gerektirir. MDM aracılığıyla cihazlarına sertifika dağıtmak Windows 10 gerekli altyapının veya ayarların yapılandırılması zor olabilir.

[![Senaryo B1 diyagramı ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Senaryo B2 diyagramı ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

İlgili Kurumsal ağ kılavuzu, HoloLens 2'nin mevcut cihaz yönetiminize nasıl kaydedilir, gerektiğinde lisanslar nasıl uygulanacak ve son kullanıcılarının bir Dynamics 365 Kılavuzu çalıştırabileceklerini ve cihaz ayarlandıktan sonra özel iş hattı uygulamalarını kullanabileceğini nasıl doğrulayabilecekleri hakkında bilgi verir.

> [!div class="nextstepaction"]
> [Kurumsal ağ dağıtım kılavuzu](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Senaryo C: Güvenli çevrimdışı ortamda dağıtma

Bu, yüksek oranda güvenli veya gizli konumlar için tipik bir dağıtımdır. HoloLens 2, ağ veya internet erişimine sahip değilken öncelikli olarak çevrimdışı kullanım için dağıtılır. 
 * Temel Ortak Yapılandırmalar
   * Wi-Fi devre dışı bırakıldı. Gerekirse, LAN bağlantısı için USB üzerinden Ethernet etkinleştirilebilir.
   * Yönetilmiyor.
   * Cihaz oturum açma için yerel kullanıcı hesabı.
     * HoloLens 2 yalnızca bir yerel hesabı destekler.
   * Cihaz kilitleme yapılandırmalarının farklı düzeyleri, belirli kullanım örneklerine göre Sağlama Paketleri aracılığıyla uygulanır. Bu yapılandırmalar genellikle güvenli ortam gereksinimleri nedeniyle kısıtlanır.
   * Sağlama Paketi aracılığıyla bir veya daha fazla uygulama dağıtılır

 * Yaygın Zorluklar
   * Sağlama Paketleri aracılığıyla kullanılabilen sınırlı bir yapılandırma kümesi vardır
   * Bulut hizmetleri kullanılamaz, bu nedenle HoloLens 2 özelliklerini sınırlandırabilirsiniz.
   * Bu cihazların el ile yapılandırılması, yapılandırılması ve güncelleştirilmiş olması nedeniyle daha yüksek yönetim yükü.

[![Çevrimdışı Güvenli diyagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

İlgili Çevrimdışı güvenli kılavuz, güvenli ortamlarda kullanmak üzere Bir HoloLens 2'nin kilitlenmesini sağlayan örnek sağlama paketini uygulamaya dair yönerge sağlar.

> [!div class="nextstepaction"]
> [Çevrimdışı güvenli ortam dağıtım kılavuzu](hololens-common-scenarios-offline-secure.md)


