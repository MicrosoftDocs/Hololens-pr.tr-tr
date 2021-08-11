---
title: Genel Atanan Erişim
description: Kullanmaya başlayın Genel Atanan Erişim Bilgi Noktası için OMA-URI'yi Intune ve Windows yapılandırma tasarımcısı ile kullanma kılavuzumuzla birlikte.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, atanan erişim, bilgi noktası
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d36192e7f65f7fe2ccc7ff8699484a19b3d5d3a7ccab0167d2dbdcaf64bb5880
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664024"
---
# <a name="global-assigned-access--kiosk"></a>Genel Atanan Erişim – Bilgi Noktası

Bu özellik HoloLens 2 cihazı birden çok uygulama bilgi noktası modu için yapılandırıyor. Bu mod sistem düzeyinde geçerlidir, sistem üzerinde herhangi bir kimliğe sahip değildir ve cihazda kimliğe sahip olan herkes için geçerlidir.

> [!NOTE]
> Bu özellik şu anda yalnızca Windows Insider derlemelerde kullanılabilir. Bu özelliği HoloLens sürümlerde genel kullanıma Windows istiyorsanız lütfen [Insider derlemeleri hakkında daha fazla bilgi](hololens-insider.md) edinebilirsiniz.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Intune'da Genel Atanan Erişimi nasıl kullanabilirim?

> [!NOTE]
> Lütfen "<!-" ile işaretlenmiş alanlara dikkat edin. Bu alanlar, tercihlerinize göre değişiklik yapmanızı gerektirir.

1. Aşağıdaki gibi özel bir OMA URI cihaz yapılandırma profili oluşturun ve bu profili HoloLens grubuna uygulama:

    URI değeri: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Intune'da Genel Atanan Erişim OMA-URI'sı](images/global-assigned-access-omauri.png)

2. Değer için aşağıdaki içeriği güncelleştirin ve yapıştırın:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Windows Configuration Designer'da Genel Atanan Erişim nasıl kullanılır?

1. Yukarıda belirtilen XML blobu XML dosyası olarak güncelleştirin ve kaydedin. 

2. Tek uygulamalı [veya çoklu uygulama](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)bilgi noktası ayarlamak için sağlama paketi kullanma bölümündeki adımları izleyin ve özellikle "Prov. package, step 2 – Bilgi noktası yapılandırma XML dosyasını bir sağlama paketine ekleyin" ve önceki adımda kaydedilen XML dosyasına bakın.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Genel yapılandırmanın herkes için geçerli olduğu ve ayrı yapılandırmanın 1 Azure AD hesabı veya Azure AD grubu için geçerli olduğu bir yapılandırma oluşturabilir miyim? 

Evet, aşağıdaki örnek XML blob'a bakın. Genel Atanan Erişim profili, HoloLens oturum açık kullanıcı için belirli bir profil bulunamadığı zaman genel erişim profiline uygulanır; bu nedenle oturum açık kullanıcı için varsayılan bilgi noktası modu yapılandırmasıdır.
Kullanılacak XML blobu örneği şu şekildedir:

> [!NOTE]
> lütfen ile işaretlenmiş vurgulanan alanlara dikkat `<!-` edin. Bu alanlar, tercihlerinize göre değişiklik yapmanızı gerektirir.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>DeviceOwners'ın Genel Atanan Erişim Profilinden Dışlama

Bu özellik, kullanıcı üzerinde "Cihaz sahibi"[olarak değerlendirilen](security-adminless-os.md)HoloLens Genel Atanmış Erişim'in dışında tutulabilir. Bu özelliğin avantajını kullanmak için, birden çok uygulamalı bilgi noktası yapılandırması için XML blobu içinde vurgulanan satırların eklendiklerinden emin olur:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Ek Genel Atanan Erişim Örnekleri

Bu, herhangi bir kullanıcı oturum açsa Ayarlar App, Geri Bildirim Merkezi ve Microsoft Edge ile çoklu uygulama bilgi noktasıyla oturum açabilen genel atanan erişim bilgi Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Bu örnek, cihaz sahibini dışlamak için bir Genel Atanmış Erişim bilgi noktasıdır. Başka bir Azure AD kullanıcısı oturum alasa da Ayarlar App, Geri Bildirim Merkezi ve Microsoft Edge. Bu bilgi noktası, ziyaretçi hesabı için kilit ekranında herkes tarafından oturum açılacak ikincil bir bilgi noktası yapılandırması da içerir. Bir kullanıcı Ziyaretçi hesabında oturum aleni bir çoklu uygulama bilgi noktasına sahip olur ve bu bilgi noktası yalnızca Geri Bildirim Merkezi olur.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
