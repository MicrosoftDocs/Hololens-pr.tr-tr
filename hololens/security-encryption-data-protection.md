---
title: Şifreleme ve veri koruması
description: BitLocker ve Azure tümleştirmesi dahil olmak üzere HoloLens 2 cihazda şifreleme ve veri koruması hakkında bilgi edinin.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Güvenlik, Hololens, şifreleme, veri koruma, BitLocker cihazı, BitLocker, BitLocker, BitLocker şifrelemesi, Azure tümleştirmesi,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036604"
---
# <a name="encryption-and-data-protection"></a>Şifreleme ve veri koruması

Şifreleme ve veri koruma, cihaz kaybolduğunda veya çalındığında verileri korur ve yetkisiz uygulamaların hassas bilgilere erişmesini önler.

## <a name="bitlocker-device-encryption"></a>BitLocker cihaz şifrelemesi

BitLocker, yazılabilir medyanın salt okuma (RO) medyası ve gizlilik koruması 'nın bütünlük korumasına yönelik tam birim şifreleme özelliğidir.  Bu tarihten itibaren, çevrimdışı saldırı sırasında verilere yetkisiz erişime karşı etkili bir kalkan oldu. HoloLens 2, varsayılan olarak, cihaza herhangi bir yetkisiz fiziksel erişimden verileri korumak için Bitlocker cihaz şifrelemesini (BDE) sağlar. Gelecek ihtiyaçlarını karşılamak için her zaman gelişen Microsoft, bu teknolojiyi yatırım yapmaya ve geliştirmeye devam etmektedir.

BDE, cihazın durum ile ayrılmış düzeninde tüm birimlerde AES-XTS-256 şifrelemesini kullanan bir veri koruma özelliğidir. BDE, durum ile ayrılmış bir düzende cihaz düzeyinde şifreleme sağlar. BitLocker cihaz şifrelemesi, işletim sistemi ve sabit veri birimlerinde otomatik olarak etkinleştirilir ve cihazın her zaman korunması için BT yöneticileri tarafından bile devre dışı bırakılamaz.

Daha sonra BDE şifreleme anahtarları, ikili dosyaları ve cihazı önyüklemek için gereken verileri saydam bir şekilde çözmek için kullanılır. İşletim sistemi biriminin kilidi açık olduğundan ve bir sistem önyüklenirken, diğer birimler, otomatik kilit açma koruyucunun birime özgü bir sürümü kullanılarak erişilebilir hale gelir. Kullanıcı gizliliğini korumak için başka bir koruyucu yoktur ve sürücü yalnızca aynı cihazda açılabilir. Gerekli birimlerde salt okuma (RO) zorlaması, ilk önyüklemeden başlayarak hemen uygulanır ve uygulanır. HoloLens 2 yaşam döngüsünde Bitlocker kurtarma anahtarı gerekli değildir.

## <a name="azure-integration"></a>Azure tümleştirmesi 

HoloLens 2, müşterilerin cihazlarını Azure hizmetleriyle tümleştirmelerini sağlar. HoloLens 2 cihaz ile Azure arasındaki iletişimler arasında, güçlü kimlik doğrulaması, ileti gizliliği ve bütünlük sağlayan kendisi ile bulut hizmetleri arasında hareket eden verileri korumak için TLS (aktarım katmanı güvenliği) protokolü kullanılır. Tüm Azure hizmetleri TLS 1,2 ' i ve müşterilerin yalnızca TLS 1,2 kullandığı tüm hizmetleri tam olarak destekler ve yalnızca TLS 1,2 trafiğini kabul eder. Azure 'un yoldaki veriler için şifreleme standartları [Azure şifrelemesi 'ne genel bakış](/azure/security/fundamentals/encryption-overview)bölümünde ayrıntılı olarak açıklanmıştır. [Azure veri güvenliği ve şifreleme için en iyi uygulamalar](/azure/security/fundamentals/data-encryption-best-practices)hakkında daha fazla bilgi edinmek için Azure belgelerini ziyaret edin. 

OneDrive, HoloLens 2 ile bulut tümleştirmesine örnek olarak, ınternet 'e bağlıyken dosya ve belgelerinizin otomatik olarak buluta yüklenebildiği bir otomatik karşıya yükleme özelliğine sahiptir. Dosyaların otomatik eşitlemesini duraklatma, ilke aracılığıyla kapatılamaz ancak doğrudan UX aracılığıyla yapılandırılabilir. 
