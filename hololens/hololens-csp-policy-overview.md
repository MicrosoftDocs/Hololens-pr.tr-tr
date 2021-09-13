---
title: CSP'leri yapılandırma ve Cihaz Yönetimi genel bakış
description: Mobil uygulama ve sağlama paketlerini kullanarak CSP'leri, ilkeyi ve cihaz Cihaz Yönetimi yapılandırmayı öğrenin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032940"
---
# <a name="configure-csps-and-device-management-overview"></a>CSP'leri yapılandırma ve Cihaz Yönetimi genel bakış

IT Yöneticileri, 2. veya 2. HoloLens tanımlayabilir ve uygulama. Hangi yapılandırma ayarlarının dağıtım senaryosuna göre farklılık gösterir ve kurumsal cihazlar, EN geniş denetim yelpazesini IT'ye sunar. Bu Windows 10, Yapılandırma Hizmeti Sağlayıcıları (CSP) cihaz yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu ayarlar kayıt defteri anahtarları veya dosyalarıyla eşler. Bazı yapılandırma hizmeti sağlayıcıları WAP biçimini, bazıları SyncML'yi ve bazıları da ikisini de destekler.

Cihaz yönetimi CSP'Windows 10 Holographic hakkında daha fazla bilgi için, tüm cihazlarda desteklenen [CSP'HoloLens bakın.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)
AYRıCA, IT Yöneticileri cihazlarda İlke CSP'lerini yönetebilir, 2. için desteklenen İlke [CSP'HoloLens listesine bakın.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Yapılandırma yöntemleri

### <a name="configure-with-mdm"></a>MDM ile yapılandırma

CSP'ler ve İlkeler, MDM sistemine kayıtlı herhangi bir kişisel veya kurumsal cihazda kolayca yönetilebilir. Bir cihaz MDM çözümünüze kaydolarak cihaz yapılandırmalarını kullanarak bu cihazı veya cihaz kümelerini yönetebilirsiniz. [MDM aracılığıyla cihazlarınızı HoloLens hakkında daha fazla bilgi edinebilirsiniz.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Sağlama Paketleri ile yapılandırma

HoloLens 2, özel Sağlama Paketleri aracılığıyla 2 cihaz için HoloLens CSP yapılandırma kümesi ayarlamayı da destekler. Sağlama Paketleri genellikle MDM olmayan yönetilen cihazlar için kullanılır ve her cihaza el ile uygulanması gerekir. HoloLens için [özel Sağlama Paketleri oluşturma hakkında bilgi HoloLens.](hololens-provisioning.md)

## <a name="configurations"></a>Yapılandırmalar

### <a name="common-device-restrictions"></a>Yaygın cihaz kısıtlamaları

Bazı cihaz kısıtlamaları basit ve bir işlevselliği veya cihazla bağlantıyı devre dışı bırakmak kadar kolaydır. Bunlar hakkında bilgi edinmek için yaygın cihaz [kısıtlamaları hakkında daha fazla bilgi edinebilirsiniz.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Bilgi noktası modları

Hangi kimliklerin varsayılan olarak hangi uygulamalara erişimi olduğunu kontrol etmek için Bilgi Noktası modunu kullanın. Bilgi noktası, tek bir uygulama veya birden çok uygulama kullanıcı arabirimi deneyimi için kullanılabilir. Bilgi noktası yapılandırmaları, cihazı kullanan herkesin tek bir uygulamasından farklı gruplar için farklı uygulama seçimlerinden farklı seçimlere kadar değişir. Bilgi noktası modu, "izin verilen uygulamaların" diğer uygulamaları başlatmasına engel olmaz ve hiçbir zaman amaçlanmaz. Bilgi noktası modları [ve bunları kullanma hakkında daha fazla bilgi edinebilirsiniz.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Ayarlar Sayfa Görünürlüğü

Hangi Ayarlar varsayılan olarak ayarlara erişimi olduğunu kontrol etmek için bir uygulama ilkesi kullanın. Bu ilkeyi Ayarlar uygulama yalnızca seçili sayfaları gösterecek veya tüm seçili sayfaları gizleyecek şekilde ya da yalıtabilirsiniz. [Kullanılabilir sayfaları yapılandırma hakkında bilgi edinebilirsiniz.](settings-uri-list.md)

Bu özellik şu anda yalnızca [Insider Windows kullanılabilir.](hololens-insider.md) Bu özelliği kullanmayı niyetli cihazların 19041.1349+ derlemede olduğundan emin olun.

### <a name="wdac"></a>WDAC

WdAC yapılandırmasını, sistemin bilgi noktası modunda olup olmadığına bakılmaksızın hangi uygulamaların/işlemlerin başlatılacaklarına/izin verilmeyeceklerine göre kontrol etmek için kullanın.
[WDAC'ye genel bakış sayfamıza bakın.](windows-defender-application-control-wdac.md)
