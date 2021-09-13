---
title: Donanım tarafından arkalı bütünlük ve çalışma zamanı taadı
description: Donanım tarafından arkalı bütünlük ve çalışma zamanı taadı
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: güvenlik, hololens, Donanım ile destekli bütünlük, çalışma zamanı onay, UEFI, UEFI güvenli önyükleme, güvenli önyükleme, TPM, tehdit koruması, Windows Kalıcılık Koruması Güvencesi, kod bütünlüğü, kod koruması,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036549"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Donanım tabanlı bütünlük ve çalışma zamanıstation

Donanım tabanlı bütünlük ve çalışma zamanı taaması, bir işletim sisteminin başlatılmasından önce, çalışma zamanında, cihazın donanım kullandığında ve bütünlüğün başlangıçta ve çalışma zamanı süresince korunmasını sağlamak için uzak kimlik doğruları hizmetleri kullandığında ortaya çıkan tehditlere karşı koruma sağlar.

## <a name="uefi-secure-boot"></a>UEFI güvenli önyükleme

HoloLens 2, Birleşik Genişletilebilir Bellenim Arabirimi (UEFI) Güvenli Önyükleme'yi her zaman zorlar ve UEFI yalnızca Windows Holographic for Business.
Güvenli Önyükleme, önyükleme zincirinin tamamının bütünlük için doğrulandığından ve Windows her zaman doğru güvenlik ilkeleriyle önyüklemesini sağlar. Güvenli Önyükleme hakkında [daha fazla bilgi.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

Güvenilir Platform Modülü (TPM), uç nokta cihazında özelleştirilmiş bir yongadır. HoloLens 2, donanım tarafından zorlanan anahtar yalıtımı sağlayan bir TPM 2.0 kullanır. TPM temelleri hakkında [daha fazla bilgi.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Kalıcılık Erişimi Tehdit Koruması

Siber saldırıların çoğunun amacı bir cihaza kalıcı erişimi sürdürmektir. Siber suçlar için bu kalıcılığı korumak, güvenliği tehlikeye Windows bir cihazın botnet'e katılmasına, cihaza veya diğer kötü kullanıcılara erişim satışına veya yinelenen veri hırsızlığına olanak sağlar. Hedeflenen saldırılar dünyasında, bir cihazda veya (daha yaygın olarak) bir ağın tamamında başarılı bir siber saldırı için kalıcılık esastır.  

Aslında, hedef cihaza veya ağa erişimi korumak için stratejik ihtiyaçları nedeniyle hedeflenen saldırılar "gelişmiş kalıcı tehditler" olarak kabul edilir. Bu nedenle, Windows Holographic for Business savunmayı kesinlikle çok önemlidir ve kalıcılık önleme teknolojisini kullanarak bir müşteri güvenliğinin söz vermesini sağlar.

### <a name="secure-boot"></a>Güvenli önyükleme

HoloLens 2, tüm çekirdek işletim sistemi durumlarını Birleşik Genişletilebilir Bellenim Arabirimi (UEFI) Güvenli Önyüklemesi'ne zorlar. UEFI yalnızca, tüm önyükleme zincirinin bütünlük için doğrulandığından ve bu Windows her zaman ona uygulanan doğru güvenlik ilkeleriyle önyüklemesini sağlayan Microsoft güvenilen platformlarını önyükler. HoloLens 2, Güvenli Önyükleme'nin kapatılamayacak veya üçüncü taraf önyükleme yükleyicilerine izin vermez.

> [!Tip]
> Güvenli önyükleme hakkında daha [fazla bilgi.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Kalıcılığı Önleme Güvencesi

HoloLens 2 kalıcılığı önleme, kullanıcılarına, sistemin çalışma zamanı güvenliğinin tehlikeye atıldığı nadir durumlarda bile (örneğin uzaktan açıktan yararlanma) böyle bir olayın, cihazı kapatarak sistemden kaldırılan tüm kötü amaçlı kodlarla azaltılabileceği garantisini verir. Koruma kalıcılığını daha da güçlendirmek için HoloLens 2 güçlü bütünlük koruması ekledi ve salt okunur korumaları ekledi.

Kullanıcı, cihazın tüm table bölümlerini silen Push-button reset (PBR) işlemi gerçekleştiremedikçe, işletim sistemi verilerine veri olarak kalıcılık yine de mümkündür. Sabit bölümlere kalıcılık çok daha zor hale geldi, ancak kullanıcının değiştirilebilir parçalardan olası tehdit kalıcılıklarını kaldırmak için HoloLens 2'nin PBR'sı gerekir.

## <a name="code-integrity-protection"></a>Kod bütünlüğü koruması

Kod bütünlüğü (CI), modern bir işletim sisteminin önemli bir güvenlik özelliğidir. CI'nin zorlanmış olması, kodun kanıtlarının hem kullanıcı hem de işletim sistemi için saydam olduğunu garantilemektedir. Tam kod bütünlüğünün geçmiş ikili görüntü imzalamasını genişletmesi ve denetim akışı bütünlüğü ve dinamik kod kısıtlamaları gibi çalışma zamanı zorlamasını içermesi gerekir. CI; fidye yazılımı, uzaktan kod yürütme açıkları ve diğer çeşitli saldırı sınıfları gibi sosyal olarak tasarlanmış kötü amaçlı yazılımlar dahil olmak üzere birden çok saldırı sınıflarının önlenmesinde kritik öneme sahip.
