---
title: Şifreleme ve Veri Koruması
description: BitLocker ve Azure tümleştirmesi dahil olmak üzere HoloLens 2 cihazlarından şifreleme ve veri koruma hakkında bilgi edinin.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: güvenlik, hololens, Şifreleme, Veri Koruması, BitLocker Cihazı, BitLocker, bitlocker, bitlocker şifrelemesi, azure tümleştirmesi,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ebe1d072f36cdf4ad9b3543882e61fa2ed4a0300
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380182"
---
# <a name="encryption-and-data-protection"></a>Şifreleme ve veri koruması

Şifreleme ve Veri Koruması, cihaz kaybolur veya çalınırsa verileri korur ve yetkisiz uygulamaların hassas bilgilere erişmesini önler.

## <a name="bitlocker-device-encryption"></a>BitLocker cihaz şifrelemesi

BitLocker, Salt Okunur (RO) medyanın bütünlüğünü ve yazılabilir medyanın gizlilik korumasını sağlamak için kullanılan tam hacimli bir şifreleme özelliğidir.  İlk kurulduğundan beri, çevrimdışı saldırılar sırasında verilere yetkisiz erişime karşı etkili bir koruma olmuştur. HoloLens 2, verileri Cihaz Şifrelemesi yetkisiz fiziksel erişime karşı korumak için Bitlocker sanal ağlarını (BDE) varsayılan olarak etkinleştirir. Gelecekteki ihtiyaçları karşılamak için her zaman gelişen Microsoft, bu teknolojiye yatırım yapmaya ve geliştirmeye devam etmektedir.

BDE, cihazın durumla ayrılmış düzeninde yer alan tüm birimlerde AES-XTS-256 şifrelemesi kullanılan bir veri koruma özelliğidir. BDE, durumla ayrılmış bir düzende cihaz düzeyinde şifreleme sağlar. BitLocker Cihaz Şifrelemesi işletim sisteminde ve sabit veri birimlerinde otomatik olarak etkinleştirilir ve CIHAZıN her zaman korunması için, IT yöneticileri bile kapatamaz.

Ardından BDE şifreleme anahtarları, ikili dosyaların ve cihazın önyüklemesi için gereken verilerin saydam bir şekilde şifresini çözmek için kullanılır. İşletim sistemi biriminin kilidi açılır ve sistem önyüklerken, diğer birimlere otomatik kilit açma koruyucusunun bir bireye özgü bir sürümü kullanılarak erişilebilir hale gelir. Kullanıcı gizliliğini korumak için başka koruyucu yoktur ve sürücünün kilidi yalnızca aynı cihazdan açabilirsiniz. Gerekli birimlerde Salt Okunur (RO) zorlaması, ilk önyüklemeden başlayarak hemen uygulanır ve uygulanır. HoloLens 2 yaşam döngüsünde Bitlocker kurtarma anahtarı gerekmez.

## <a name="azure-integration"></a>Azure tümleştirmesi 

HoloLens 2, müşterilerin cihazlarını Azure hizmetleriyle tümleştirebilirsiniz. HoloLens 2 cihazları ile Azure arasındaki iletişimlerde, kendisiyle bulut hizmetleri arasında seyahat eden verileri korumak için TLS (Aktarım Katmanı Güvenliği) protokolü kullanılır. Bu protokol güçlü kimlik doğrulaması, ileti gizliliği ve bütünlük sağlar. Tüm Azure hizmetleri TLS 1.2'yi ve müşterilerin yalnızca TLS 1.2'yi kullanmakta olduğu tüm hizmetleri yalnızca TLS 1.2 trafiğini kabul eder. Azure'ın geçişte olan verilere ilişkin şifreleme standartları, Azure şifrelemeye genel [bakış içinde ayrıntılı olarak açık edilmiştir.](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview) Azure veri güvenliği ve şifrelemesi için en iyi [yöntemler hakkında daha fazla bilgi edinmek için Azure belgelerini ziyaret edin.](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices) 

HoloLens 2 ile bulut tümleştirmesi örneği olan OneDrive, dosya ve belgelerinizin İnternet'e bağlandıktan sonra buluta otomatik olarak yükleneceği otomatik karşıya yükleme özelliğine sahiptir. Dosyaların otomatik eşitlemesi duraklatma ilkesi aracılığıyla kapatılamaz, ancak UX aracılığıyla doğrudan yapılandırılabilir. 
