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
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380234"
---
# <a name="global-assigned-access--kiosk"></a>Genel atanan erişim – bilgi noktası

Bu özellik, HoloLens 2 cihazını, sistem düzeyinde geçerli olan birden çok uygulama bilgi noktası modu için yapılandırır, sistemde herhangi bir kimlikle hiçbir benzeşim yoktur ve cihazda oturum açan herkese uygulanır.

> [!NOTE]
> Bu özellik şu anda yalnızca Windows Insider Derlemeleriyle kullanılabilir. Bu özelliği, HoloLens sürümlerinde genel kullanıma açılmadan önce denemek istiyorsanız lütfen [Windows Insider](hololens-insider.md) derlemeleri hakkında daha fazla bilgi edinin.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Intune 'da genel atanan erişim nasıl kullanılır?

> [!NOTE]
> Lütfen "<!-" ile işaretlenmiş alanlara dikkat edin. Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.

1. Aşağıdaki gibi özel bir OMA URI cihaz yapılandırma profili oluşturun ve bunu HoloLens cihaz grubuna uygulayın:

    URI değeri:./Device/Vendor/MSFT/atandaccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Genel atanan Access OMA-URI 'SI Intune 'da](images/global-assigned-access-omauri.png)

2. Değer için aşağıdaki içeriği güncelleştirin ve yapıştırın:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Windows yapılandırma Tasarımcısı 'nda genel atanan erişim nasıl kullanılır?

1. XML dosyası olarak yukarıda bahsedilen XML blobu güncelleştirin ve kaydedin. 

2. [Tek bir uygulama veya birden çok uygulama bilgi noktası ayarlamak için sağlama paketini kullanma](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)bölümündeki adımları uygulayın, özellikle de "prov. paket, adım 2 – bilgi noktası yapılandırması XML dosyasını bir sağlama paketine ekleyin ve önceki adımda kaydedilen XML dosyasına başvurun.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Herkesin herkes için geçerli olduğu bir yapılandırma oluşturabilir miyim ve ayrı yapılandırma 1 Azure AD hesabı veya Azure AD grubu için geçerlidir mi? 

Evet, aşağıdaki örnek XML blobuna bakın. Genel atanan erişim profili, oturum açan kullanıcı için belirli bir tane bulunamadığında HoloLens 'te uygulanır, bu nedenle oturum açan kullanıcı için varsayılan bilgi noktası modu yapılandırması vardır.
Kullanılacak XML blobuna bir örnek aşağıda verilmiştir:

> [!NOTE]
> Lütfen ile işaretlenmiş vurgulanan alanlarla haberdar olun `<!-` . Bu alanlarda, tercihlerinize göre değişiklikler yapmanız gerekir.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Genel atanan erişim profilinden DeviceOwners hariç tutma

Bu özellik, HoloLens üzerinde "[cihaz sahibi](security-adminless-os.md)" olarak kabul edilen bir kullanıcının genel atanan erişimden dışlanması için izin verir. Bu özellikten yararlanabilmek için, birden çok uygulama bilgi noktası yapılandırması için XML blobu içinde, vurgulanan çizgilerin eklendiğinden emin olun:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Ek genel atanan erişim örnekleri

Bu, herhangi bir Kullanıcı oturum açtığında, ayarlar uygulaması, geri bildirim merkezi ve Microsoft Edge ile birden çok uygulama bilgi noktası olacağını belirten, genel olarak atanmış bir erişim bilgi noktası örneğidir.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Bu örnek, cihaz sahibini dışlayan, diğer Azure AD kullanıcıları oturum açtığında, ayarlar uygulaması, geri bildirim hub 'ı ve Microsoft Edge ile birden çok uygulama bilgi noktası olan genel olarak atanmış bir erişim bilgi noktası örneğidir. Bu bilgi noktası Ayrıca, bir ziyaretçi hesabı için bir ikincil bilgi noktası yapılandırması içerir ve bu, kilit ekranında herhangi bir kişi tarafından oturum açmış olabilir. Bir Kullanıcı ziyaretçi hesabına kaydolursa, yalnızca geri bildirim hub 'ı uygulamasına sahip bir çok uygulama bilgi noktası olur.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
