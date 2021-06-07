---
title: HoloLens 2 için özel uygulamaları yönetme
description: Cihaz portalı ve Visual Studio kullanarak, HoloLens 2 cihazlarında özel holographic uygulamalarını yüklemeyi, kaldırmayı ve dışarıdan yüklemeyi öğrenin.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: Hololens, Hololens 2, dışarıdan yükleme, dışarıdan yükleme, dışarıdan yükleme, mağaza, UWP, uygulama, yükleme
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379005"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="ba70b-104">HoloLens 2 için özel uygulamaları yönetme</span><span class="sxs-lookup"><span data-stu-id="ba70b-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="ba70b-105">HoloLens, Microsoft Store mevcut birçok uygulamayı ve özellikle HoloLens için oluşturulmuş yeni uygulamaları destekler.</span><span class="sxs-lookup"><span data-stu-id="ba70b-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="ba70b-106">Mağaza uygulamaları hakkında daha fazla bilgi için bkz. [Store ile uygulamaları yönetme](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ba70b-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba70b-107">Kurumsal dağıtımlar için, bu yöntemlerin her ikisinin de kullanacağı geliştirici modunun etkinleştirilmesini önermeyiz.</span><span class="sxs-lookup"><span data-stu-id="ba70b-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="ba70b-108">Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız lütfen [uygulama yönetimizi gözden geçirin: genel bakış](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba70b-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="ba70b-109">HoloLens 2 cihazları için uygulama yüklemesinin geliştirici yöntemlerinden birini arıyorsanız, bkz:</span><span class="sxs-lookup"><span data-stu-id="ba70b-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="ba70b-110">Cihaz Portalı: uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="ba70b-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="ba70b-111">Uygulamaları dağıtmak ve hatalarını ayıklamak için Visual Studio 'Yu kullanma</span><span class="sxs-lookup"><span data-stu-id="ba70b-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="ba70b-112">HoloLens 'te özel uygulamalar dağıtmak istiyorsanız [kılavuzumuza](holographic-custom-apps.md) bakın (1. Genel).</span><span class="sxs-lookup"><span data-stu-id="ba70b-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>