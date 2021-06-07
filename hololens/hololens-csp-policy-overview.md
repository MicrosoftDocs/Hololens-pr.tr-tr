---
title: CSP 'Leri ve cihaz yönetimine genel bakış
description: Mobil cihaz yönetimi ve sağlama paketleri kullanarak CSP 'Leri, ilkeyi ve cihaz yönetimini yapılandırmayı öğrenin.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379103"
---
# <a name="configure-csps-and-device-management-overview"></a>CSP 'Leri ve cihaz yönetimine genel bakış

BT yöneticileri, HoloLens 2 ' de ilke ayarlarını tanımlayabilir ve uygulayabilir. Kullandığınız yapılandırma ayarları dağıtım senaryosuna göre farklılık gösterir ve şirket cihazları bu en geniş denetim aralığını sunar. Windows 10 ' da yapılandırma hizmeti sağlayıcıları (CSP), cihazdaki yapılandırma ayarlarını okumak, ayarlamak, değiştirmek veya silmek için bir arabirimdir. Bu ayarlar kayıt defteri anahtarları veya dosyalarıyla eşlenir. Bazı yapılandırma hizmeti sağlayıcıları WAP biçimini, bazı destek SyncML ' i ve her ikisini de destekler.

Windows 10 holographic cihaz yönetimi CSP 'Leri hakkında daha fazla bilgi için, [HoloLens cihazlarında desteklenen CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)'lerin tam listesine bakın.
BT yöneticileri cihazlarda Ilke CSP 'sini de yönetebilir, [HoloLens 2 tarafından desteklenen Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)'lerin tam listesine bakın.

## <a name="configuration-methods"></a>Yapılandırma yöntemleri

### <a name="configure-with-mdm"></a>MDM ile yapılandırma

CSP 'Ler ve Ilkeler, bir MDM sistemine kayıtlı tüm kişisel veya şirket cihazlarından kolayca yönetilebilir. Bir cihaz MDM çözümünüze kaydedildikten sonra bu cihazı veya cihaz yapılandırması kullanarak cihaz kümesini yönetebileceksiniz. [HoloLens CIHAZLARıNıZı MDM aracılığıyla yönetme](hololens-mdm-configure.md)hakkında daha fazla bilgi edinin.

### <a name="configure-with-provisioning-packages"></a>Sağlama paketleriyle yapılandırma

HoloLens 2 Ayrıca, özel sağlama paketleri aracılığıyla HoloLens 2 cihazları için sınırlı sayıda CSP yapılandırması ayarlamayı destekler. Sağlama paketleri genellikle MDM olmayan yönetilen cihazlar için yararlanılabilir ve her cihaza el ile uygulanması gerekir. [HoloLens için özel sağlama paketleri](https://docs.microsoft.com/hololens/hololens-provisioning)oluşturma hakkında bilgi edinin.

## <a name="configurations"></a>Yapılandırmalar

### <a name="common-device-restrictions"></a>Ortak cihaz kısıtlamaları

Bazı cihaz kısıtlamaları basittir ve bir işlevi veya cihazla bağlantıyı devre dışı bırakır. Bu konuda daha fazla bilgi edinmek için [ortak cihaz kısıtlamaları](hololens-common-device-restrictions.md) hakkında daha fazla bilgi edinin

### <a name="kiosk-modes"></a>Bilgi noktası modları

Hangi kimliklerin varsayılan olarak hangilerinin erişebileceğini denetlemek için bilgi noktası modunu kullanın. Kiosks, tek bir uygulama veya birden çok uygulama kullanıcı arabirimi deneyimi için kullanılabilir. Bilgi noktası yapılandırmalarının, cihazı kullanan herkes için tek bir uygulamadan farklı gruplar için farklı uygulama seçimleriyle aralığı vardır. Bilgi noktası modu, "izin verilen uygulamaların" diğer uygulamaları başlatmasını engellemez ve hiçbir zaman amaçlanmamıştır. Bilgi [noktası modlarını ve bunların nasıl kullanılacağını okuyarak](hololens-kiosk.md)daha fazla bilgi edinin.

### <a name="settings-page-visibility"></a>Ayarlar sayfası görünürlüğü

Ayarlara hangi kimliklerin varsayılan olarak erişebileceğini denetlemek için ayarlar uygulama ilkesi ' ni kullanın. Bu ilkeyi kullanarak, ayarlar uygulaması yalnızca seçim sayfalarını gösterecek şekilde veya seçili tüm sayfaları gizleyecek şekilde yapılandırılabilir. [Kullanılabilir sayfaları yapılandırma hakkında bilgi edinin](settings-uri-list.md).

Bu özellik şu anda yalnızca [Windows Insider Derlemeleriyle](hololens-insider.md)kullanılabilir. İçin bu özelliği kullanmayı düşündüğünüz cihazların Build 19041.1349 + konumunda olduğundan emin olun.

### <a name="wdac"></a>Ung

Sistemin bilgi noktası modunda olup olmadığı ne olursa olsun, hangi uygulamaların/işlemlerin çalıştırılmasına izin verildiğini/izin verileceğini denetlemek için WDAC yapılandırmasını kullanın.
[WDAC için genel bakış bölümüne bakın.](windows-defender-application-control-wdac.md)
