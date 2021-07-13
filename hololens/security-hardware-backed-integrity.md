---
title: Donanım tarafından desteklenen bütünlük ve çalışma zamanı kanıtlama
description: Donanım tarafından desteklenen bütünlük ve çalışma zamanı kanıtlama
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: güvenlik, hololens, donanım tarafından desteklenen bütünlük, çalışma zamanı kanıtlama, uefı, uefı güvenli önyükleme, güvenli önyükleme, TPM, tehdit koruması, Windows sürdürme güvenliği, kod bütünlüğü, kod koruma,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639344"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Donanımla desteklenen bütünlük ve çalışma zamanı kanıtlama

Donanım tarafından desteklenen bütünlük ve çalışma zamanı kanıtlama, işletim sisteminin başlangıcından önce, çalışma zamanı sırasında, cihaz donanımı kullandığında ve tüm çalışma zamanı süresince tutarlılık sağlamak için uzak kanıtlama Hizmetleri olan tehditlere karşı koruma sağlar.

## <a name="uefi-secure-boot"></a>UEFı güvenli önyükleme

HoloLens 2 Birleşik Genişletilebilir Bellenim Arabirimi (uefı) güvenli önyüklemeyi her zaman uygular ve uefı yalnızca Windows Holographic for Business önyükler.
güvenli önyükleme, tüm önyükleme zincirinin bütünlük için doğrulanmasını ve Windows her zaman uygulanan doğru güvenlik ilkeleriyle önyüklenmesini sağlar. [Güvenli önyükleme](/windows-hardware/design/device-experiences/oem-secure-boot)hakkında daha fazla bilgi edinin.

## <a name="tpm"></a>TPM

Güvenilir Platform Modülü (TPM), uç nokta cihazında özelleştirilmiş bir yongadır. HoloLens 2, donanım tarafından zorlanan anahtar yalıtımı sağlayan bir TPM 2,0 kullanır. [TPM temelleri](/windows/security/information-protection/tpm/tpm-fundamentals)hakkında daha fazla bilgi edinin.

## <a name="persistence-access-threat-protection"></a>Kalıcılık erişimi tehdit koruması

Çoğu cybersaldýrın amacı, cihaza kalıcı erişim sağlamak için kullanılır. siç için, bu kalıcılığı korumak, güvenliği aşılmış Windows cihazının bir botnet 'e katılmasına, cihaza veya diğer nefarli kullanıcılara erişmesini veya yinelenen veri hırsızlığını etkinleştirmesine olanak tanır. Hedeflenen saldırı dünyasında, kalıcı bir sanal saldırı için, bir cihazda veya (daha yaygın olarak) tüm ağ için kalıcılık gereklidir.  

Aslında, hedeflenen saldırılar "Gelişmiş kalıcı tehditler" olarak değerlendirilir ve bu nedenle, bir hedef cihaza veya ağa erişim sağlamak için stratejik gereksinimlerdir. bu nedenle, Windows Holographic for Business sürekliliği kesinlikle önemli bir şekilde ertelendirir ve bir ıronclad müşteri güvenlik taahhüdünü sağlamak için kalıcılık önleme teknolojisini kullanır.

### <a name="secure-boot"></a>Güvenli önyükleme

HoloLens 2, tüm çekirdek işletim sistemi durumunda Birleşik Genişletilebilir Bellenim Arabirimi (uefı) güvenli önyükleme uygular. uefı yalnızca Microsoft güvenilir platformlarını önyükler. bu, tüm önyükleme zincirinin bütünlük için doğrulanmasını ve Windows her zaman kendisine uygulanan doğru güvenlik ilkeleriyle önyüklenmesini sağlar. HoloLens 2, önyüklemesinin devre dışı bırakılmayacağı veya üçüncü taraf önyükleme yükleyicileriyle izin vermez.

> [!Tip]
> [Güvenli önyükleme](/windows-hardware/design/device-experiences/oem-secure-boot)hakkında daha fazla bilgi edinin.

### <a name="windows-anti-persistence-assurance"></a>Windows Kalıcılık önleme güvencesi

HoloLens 2 ' de kalıcı hale getirme, kullanıcıların bir sistem çalışma zamanı güvenliğinin herhangi bir zaman meydana gelmesinin (örneğin, uzak bir güvenlik açığından), bu tür bir olayın, cihazı kapatarak sistemden kaldırılmış olan tüm kötü amaçlı kod ile azaltılmasını sağlar. HoloLens 2, kalıcılığın korunmasını daha da güçlendirin, güçlü bütünlük koruması ekledi ve salt okunurdur.

Kullanıcı, tüm kesilebilir bölümleri temizler cihaz için basma-düğme sıfırlama (PBR) gerçekleştirmediği takdirde, işletim sistemi verilerinin veri biçiminde kalıcılığı yine de mümkündür. sabit bölümleri çok daha zor hale getirilirken, kullanıcının, kesilebilir bölümden olası tehdit kalıcılığını kaldırmak için HoloLens 2 ' ye uygun olması gerekir.

## <a name="code-integrity-protection"></a>Kod bütünlüğü koruması

Kod bütünlüğü (CI), modern bir işletim sisteminin önemli bir güvenlik özelliğidir. CI 'nın zorunlu kılınması, hem Kullanıcı hem de işletim sistemi için saydam hale getirdiğinden, ses güvenlik kararlarını sağlar. Tüm kod bütünlüğü, son ikili görüntü imzalamayı genişletmeli ve denetim akışı bütünlüğü ve dinamik kod kısıtlamaları gibi çalışma zamanı zorlamasını içermelidir. Idye yazılımı, uzaktan kod yürütme güvenlik açıkları ve çeşitli diğer saldırı sınıfları gibi, çok sayıda saldırı içeren bir kötü amaçlı yazılım da dahil olmak üzere, CI tarafından çok sayıda saldırının önlenmesi
