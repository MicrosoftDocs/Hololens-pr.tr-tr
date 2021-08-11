---
title: HoloLens 2 özellik ve çözüm
description: İşletmelerin Microsoft HoloLens yönetmelerini kolaylaştıran ticari özellikler hakkında bilgi HoloLens öğrenin.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, ticari, özellikler, mdm, mobil cihaz yönetimi, bilgi noktası modu, uygulamalar, kimlik, Bitlocker, iris, Windows Hello, Azure destekli, Autopilot, karma gerçeklik, WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665354"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 özellik ve çözüm

## <a name="what-can-hololens-2-do-for-you"></a>2 HoloLens sizin için ne yapabiliriz?

Sınır olmadan işbirliği yapın ve HoloLens 2'de karma gerçeklik uygulamalarıyla çalışanların üretkenliğini artırmak için hassas HoloLens davranın. Görevleri hatasız olarak güvenli bir şekilde tamamlamaya sürekli odaklanmak için yerleşik sesli komutlar, göz izleme ve dünya yer bağlantısı ile sürekli olarak dikkat edin, daha uzun ve daha rahat bir şekilde hareket edin. Bağlan iş arkadaşlarınızla gerçek zamanlı olarak birlikte çalışır ve çalışma noktasındaki sorunları hızla çözmek için fiziksel ortamınıza yer paylaşımlı kapsamlı bir holografik tuvalde birlikte çalışırsınız. Microsoft'un güvenliği, güvenilirliği ve ölçeklenebilirliği ile desteklenen sağlam bir uygulama ekosistemi ile yatırım getirilerini hemen hayata kaldırın.  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 özellikleri

2. HoloLens neden bu kadar güçlü?

| Özellik | Açıklama |
|---------|-------------|
| Dünya yer bağlantısı | Sabitli hologramlar tam olarak yerinde kalır. HoloLens 2, çalışma alanınızı anlar. Bu nedenle dijital içerik, zaman içinde çalışmaya devam eder ve bu da sizin üzerinde çalışma yapılan nesnelere veya yüzeylere sabitler. |
| El izleme | Hologramları doğal bir şekilde dokunarak, kavrayarak ve hareket ettirin. HoloLens 2, etkileşimlerinize yeni bir memnuniyet sağlamak için size uyar. |
| Göz izleme | Yeni bir bağlam ve insan anlayışı düzeyinin keyfini çıkarın. HoloLens 2, tam olarak nerede olduğunu anlayacaktır, bu nedenle amacınızı anlayacaktır ve hologramları gerçek zamanlı olarak gözlere uyarlar. |
| Ses etkin | Yerleşik sesli komutlar, bir görevle HoloLens 2'de hızla gezinmenize ve çalışmanıza olanak sağlar. |
| Ergonomik | HoloLens 2, genişletilmiş kullanımı desteklemek için bir arama sığdırma sistemi içeren hafiftir (3,28kg). |
| Büyük FoV | Holografik tuvali yüksek çözünürlüklü, büyük görünüm alanı ekranları ile genişletin. |
| Untethered | İşlerinizi yapmak için kablo veya dış paketsiz serbestçe hareket etme. |
| Azure destekli | Azure karma gerçeklik hizmetleriyle kullanıcılar arasında devam eden bir konuma ve/veya nesneye sabitlene yüksek uygunlukta 3D içerik akışı.
| Karma gerçeklik yakalama | Deneyimi fotoğraf veya video olarak belgele, diğerleriyle gerçek zamanlı olarak paylaşabilirsiniz. |
| İş İçin Windows Hello | Iris tabanlı biyometrik kimlik doğrulaması, iş akışına hızlı ve güvenli bir şekilde erişim sağlar. |
| Windows Autopilot | HoloLens 2 için hizmetleri ayar ve önceden yapılandırarak dağıtılmış çalışma yerlerinin tamamda kullanıma hazır hale geldi. |
| Işletim Sistemi Güncelleştirmeleri | Aylık hizmet güncelleştirmeleri ile güvenliğinizi sağlamanın ve iki yıllık sürümlerde yeni üretkenlik ve yönetilebilirlik olanaklarının avantajından yararlanma. |
| Cihazları Kolayca Yönetme | Microsoft Intune, VMware Workspace One, MobileIron ve daha birçok Microsoft Intune kullanarak birden çok HoloLens 2 cihazı aynı anda yönetin. |
| Düzenlenen ortamlarda çalışma | HoloLens 2, ISO Sınıfı 5.0 ve UL Sınıf I, Bölüm 2 olarak belirlenmiş ortamlar da dahil olmak üzere yüksek düzenlemeye tabi ortamları destekleyen kapsamlı bir cihaz portföyüne sahiptir. |


## <a name="managing-hololens-2-in-your-organization"></a>HoloLens 2'nin yönetimi
HoloLens 2, kuruluşların cihazları yönetmelerini ve kullanmalarını kolaylaştıran HoloLens içerir. Bazı özellikler cihaza dahil edilirken, diğerleri HoloLens için Mobil Cihaz Yönetimi [(MDM)](hololens-mdm-configure.md) [](hololens-provisioning.md) veya Windows Yapılandırma Tasarımcısı kullanılarak [Paket Sağlama aracılığıyla etkinleştirilebilir.](app-deploy-provisioning-package.md#setup)

| Yapmak istiyorum... | Çözüm | Description |  
|---------| ------------|------------|
Son kullanıcılarımı oturum açma adımlarını yönetme | [**Kimlik**](hololens-identity.md) | HoloLens 2, Azure Active Directory (AAD), Microsoft Hesabı (MSA) ve yerel hesaplar gibi çeşitli kullanıcı kimliklerini destekler.  |
| Kullanıcı verilerini şifreleme | [**Veri güvenliği**](security-encryption-data-protection.md) | BitLocker veri şifrelemesi, diğer HoloLens cihazla aynı güvenlik koruması düzeyini sağlamak için Windows etkinleştirilir. | 
Kuruluşumda Hololens cihazlarını yönetme | [**Mobil Cihaz Yönetimi**](hololens-mdm-configure.md) | Ayarları yönetin, merkezi bir konumdan 2 farklı cihaza sahip birden fazla cihaza, HoloLens gereksinimlerine uyarlanmış güvenlik yapılandırmalarını yüklemek ve ayarlamak için uygulamaları seçin. | 
|Yeni kullanıcılar ve cihazlar için kurulum süresini en aza indirme | [**Otopilot**](hololens2-autopilot.md) | Microsoft Endpoint Manager'da ilk kullanım deneyimini (OOBE) yapılandırma ve son kullanıcıların çok az etkileşimle veya hiç etkileşim olmadan cihazları iş kullanımına hazırlamasını sağlar. |  
| Cihazlarım için işletim sistemi güncelleştirmelerini denetleme | [**İş İçin Windows Update**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | Windows İş için Güncelleştirme cihazlara denetimli işletim sistemi güncelleştirmeleri ve uzun süreli bakım kanalı için destek sağlar. |  
| Belirli ve LOB uygulamalarının indirilmelerine izin ver |[**Uygulama Yönetimi**](app-deploy-overview.md) | 2 kullanıcıdan daha fazla kullanıcıdan seçilen gruplarda uygulamaları HoloLens ve denetlemeyi seçin. | 
| Başlat men menüsünde belirli uygulamaları gösterme veya gizleme |[**Bilgi noktası modu**](hololens-kiosk.md) | Uygulama HoloLens veya ayrılmış iş uygulamaları için sabit amaçlı bir cihaz olarak işleve sahip olacak şekilde HoloLens 2'yi yapılandırma. 
| Uygulamaları kilitleyerek ortamımı güvenli hale sağlama | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender Uygulama Denetimi (WDAC), uygulama ve işlemlerin cihaz kullanıcısı tarafından başlatılanlarını engeller.
| Uygulamalar ve işlemler için kurallarla cihaz güvenliğini yönetme | [**İlkeler (CSP'ler)**](hololens-csp-policy-overview.md) | IT Yöneticileri, HoloLens 2'de desteklenen İlke CSP'lerinin mevcut listesini kullanarak ilke ayarlarını tanımlayabilir ve HoloLens olabilir. |  
| Cihazın İnternet'e nasıl bağlanıyor olduğunu yönetme | [**Ağ ve Bağlantı**](hololens-certificates-network.md) | Wi-Fi, VPN'ler veya iç kaynaklara erişmek için sertifika tabanlı kimlik doğrulaması kullanın. | 
| Cihazı birden çok kullanıcıyla paylaşma | [**Otomatik Özelleştirilmiş Görüntü**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 ekran Otomatik Göz Konumu (AEP) ile otomatik olarak ayarlanır ve cihaz kullanıcılar arasında paylaşılırken el ile ayarlama [işlemi çalıştırma ihtiyacı ortadan kaldırılır.](hololens-multiple-users.md) |

Yukarıdaki çözümler [için LisansLama](hololens-licenses-requirements.md) Gereksinimleri hakkında bilgi edinebilirsiniz.

## <a name="next-steps"></a>Sonraki Adımlar
> [!div class="nextstepaction"]
> [2 HoloLens keşfetme](hololens2-options.md)

> [!div class="nextstepaction"]
>[Planlama HoloLens 2 dağıtımı](hololens-requirements.md) 
