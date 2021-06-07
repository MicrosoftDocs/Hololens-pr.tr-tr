---
title: Lisans gereksinimleri
description: Mobil cihaz yönetimi, HoloLens ve Uzaktan Yardım için ihtiyacınız olan tüm lisans gereksinimleri ve yönergeleriyle güncel tutun.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380233"
---
# <a name="license-requirements"></a>Lisans gereksinimleri

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Mobil cihaz yönetimi (MDM) lisans Kılavuzu

HoloLens cihazlarınızı yönetmeyi planlıyorsanız Azure AD 'ye ve MDM 'ye ihtiyacınız olacaktır. Active Director (AD), HoloLens cihazlarını yönetmek için kullanılamaz.
Intune dışında bir MDM kullanmayı planlıyorsanız [Azure Active Directory bir lisans](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) gerekir.
MDM 'niz olarak Intune kullanmayı planlıyorsanız, Intune lisanslarını içeren [paketler listesini](https://docs.microsoft.com/intune/fundamentals/licenses) okuyun. **Azure AD 'nin bu paketlerin çoğunluğuna dahil edildiğini lütfen unutmayın.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>Senaryonuz ve ürünleriniz için gereken lisansları belirler

### <a name="hololens-1st-gen-licenses-requirements"></a>HoloLens (1. Genel) lisans gereksinimleri

HoloLens (1. gen) cihazınızı Windows holographic for Business 'a yükseltmeniz gerekebilir. (Yükseltmeniz gerekip gerekmediğini öğrenmek için bkz. [HoloLens ticari özellikleri](holoLens-commercial-features.md#feature-comparison-between-editions) ).

 Bu durumda, şunları yapmanız gerekir:

- HoloLens Kurumsal Lisans XML dosyası alma
- XML dosyasını HoloLens 'e uygulayın. Bunu bir [sağlama paketi](hololens-provisioning.md) veya [Mobil Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade) aracılığıyla yapabilirsiniz

### <a name="remote-assist-license-requirements"></a>Uzaktan Yardım lisans gereksinimleri

Gerekli lisanslama ve cihaza sahip olduğunuzdan emin olun. Bu, [gereksinimler](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) belgelerini iade edebilirsiniz.

1. [Uzaktan Yardım lisansı](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Ya da bir [Uzaktan Yardım denemesi](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist) deneyin
1. [Ekipler Freemıum/takımlar](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) lisansı](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

**[Bu çapraz kiracı senaryosunu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** uygulamayı planlıyorsanız, bir bilgi engelleri lisansına ihtiyacınız olabilir. Bir bilgi engeli lisansının gerekip gerekmediğini öğrenmek için lütfen [Bu makaleye](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) bakın.

### <a name="guides-license-requirements"></a>Kılavuzlar lisans gereksinimleri

[Güncelleştirilmiş lisanslama ve cihaz gereksinimlerine](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)göz atın.

1. [Azure Active Directory (Azure AD) lisansı](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
