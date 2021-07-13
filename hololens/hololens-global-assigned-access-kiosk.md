---
title: Genel atanan erişim
description: Intune ve Windows yapılandırma Tasarımcısı ile genel olarak atanmış erişim Kiisleri için OMA-URI ' y i kullanma kılavuzumuzu kullanmaya başlayın.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: Hololens, Hololens 2, atanan erişim, bilgi noktası
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640432"
---
# <a name="global-assigned-access--kiosk"></a>Genel atanan erişim – bilgi noktası

bu özellik, sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için HoloLens 2 cihazı yapılandırır, sistemde hiçbir kimlikle benzeşim yoktur ve cihazda oturum açan herkese uygulanır.

> [!NOTE]
> bu özellik şu anda yalnızca Windows ınsider derlemeleriyle kullanılabilir. bu özelliği HoloLens sürümlerde genel kullanıma açılmadan önce denemek istiyorsanız lütfen [Windows ınsider](hololens-insider.md) derlemeleri hakkında daha fazla bilgi edinin.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Intune 'da genel atanan erişim nasıl kullanılır?

> [!NOTE]
> Lütfen "<!-" ile işaretlenmiş alanlara dikkat edin. Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.

1. aşağıdaki gibi özel bir OMA urı cihaz yapılandırma profili oluşturun ve HoloLens cihaz grubuna uygulayın:

    URI değeri:./Device/Vendor/MSFT/atandaccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Genel atanan Access OMA-URI 'SI Intune 'da](images/global-assigned-access-omauri.png)

2. Değer için aşağıdaki içeriği güncelleştirin ve yapıştırın:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Windows yapılandırma tasarımcısında genel atanan erişim nasıl kullanılır?

1. XML dosyası olarak yukarıda bahsedilen XML blobu güncelleştirin ve kaydedin. 

2. [Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için sağlama paketini kullanma](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)bölümündeki adımları uygulayın, özellikle de "prov. paket, adım 2 – bilgi noktası yapılandırması XML dosyasını bir sağlama paketine ekleyin ve önceki adımda kaydedilen XML dosyasına başvurun.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Herkesin herkes için geçerli olduğu bir yapılandırma oluşturabilir miyim ve ayrı yapılandırma 1 Azure AD hesabı veya Azure AD grubu için geçerlidir mi? 

Evet, aşağıdaki örnek XML blobuna bakın. genel atanan erişim profili, oturum açmış kullanıcı için belirli bir tane bulunamadığında HoloLens uygulanır, bu nedenle oturum açan kullanıcı için varsayılan bilgi noktası modu yapılandırması olur.
Kullanılacak XML blobuna bir örnek aşağıda verilmiştir:

> [!NOTE]
> Lütfen ile işaretlenmiş vurgulanan alanlarla haberdar olun `<!-` . Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Genel atanan erişim profilinden DeviceOwners hariç tutma

bu özellik, HoloLens üzerinde "[cihaz sahibi](security-adminless-os.md)" olarak kabul edilen bir kullanıcının genel olarak atanmış erişimden dışlanması için izin verir. Bu özellikten yararlanabilmek için, birden çok uygulama bilgi noktası yapılandırması için XML blobu içinde, vurgulanan çizgilerin eklendiğinden emin olun:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Ek genel atanan erişim örnekleri

bu, herhangi bir kullanıcı oturum açtığında Ayarlar uygulaması, geri bildirim Hub 'ı ve Microsoft Edge birden çok uygulama bilgi noktası olacağını belirten, genel olarak atanmış bir erişim bilgi noktası örneğidir.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

bu örnek, cihaz sahibini dışlayan, diğer Azure AD kullanıcıları oturum açtığında Ayarlar uygulaması, geri bildirim Hub 'ı ve Microsoft Edge birden çok uygulama bilgi noktası olan genel olarak atanmış bir erişim bilgi noktası örneğidir. Bu bilgi noktası Ayrıca, bir ziyaretçi hesabı için bir ikincil bilgi noktası yapılandırması içerir ve bu, kilit ekranında herhangi bir kişi tarafından oturum açmış olabilir. Bir Kullanıcı ziyaretçi hesabına kaydolursa, yalnızca geri bildirim hub 'ı uygulamasına sahip bir çok uygulama bilgi noktası olur.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
