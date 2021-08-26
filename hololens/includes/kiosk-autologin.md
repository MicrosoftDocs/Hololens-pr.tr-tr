---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859413"
---
# <a name="non-aad-configuration"></a>[AAD olmayan yapılandırma](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>AAD olmayan yapılandırma

1. Şu şekilde bir sağlama paketi oluşturun:
    1. Ziyaretçi hesaplarına izin vermek için çalışma zamanı ayarlarını/Atananı yapılandırır.
    1. İsteğe bağlı olarak, cihazı daha sonra yönetilebilmesi için MDM 'de (çalışma zamanı ayarları/çalışma alanı/kayıtlar) kaydeder.
    1. Yerel hesap oluşturma
2. [Sağlama paketini uygulayın](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[AAD yapılandırması](#tab/aadlogon)

#### <a name="aad-configuration"></a>AAD yapılandırması

Bilgi noktası modu için yapılandırılmış AAD 'ye katılmış cihazlar, oturum açma ekranından tek bir düğmeye dokunarak bir ziyaretçi hesabında oturum açabilir. Ziyaretçi hesabında oturum açtıktan sonra, ziyaretçi başlangıç menüsünde açıkça oturum açana veya cihaz yeniden başlatılana kadar yeniden oturum açmayı istemez.

Ziyaretçi otomatik oturum açma, [özel OMA-URI ilkesi](/mem/intune/configuration/custom-settings-windows-10)aracılığıyla yönetilebilir:

- URI değeri:./Device/Vendor/MSFT/mixedreality/visitorampalogon

| İlke | Description | Yapılandırmalar |
| --------------------------- | ------------- | -------------------- |
| MixedReality/Visitooyutologon | Bir ziyaretçinin bir bilgi noktasında otomatik olarak oturum açmasına olanak tanır. | 1 (Evet), 0 (Hayır, varsayılan.) |