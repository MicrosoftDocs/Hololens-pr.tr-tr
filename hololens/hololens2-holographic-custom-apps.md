---
title: HoloLens 2 için özel uygulamaları yönetme
description: HoloLens 2 cihaza özel holografik uygulamaları yükleme, kaldırma ve yan yükleme hakkında bilgi Cihaz Portalı ve Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, sideload, side load, side-load, store, uwp, app, install
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
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636410"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="1c336-104">HoloLens 2 için özel uygulamaları yönetme</span><span class="sxs-lookup"><span data-stu-id="1c336-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="1c336-105">HoloLens, Microsoft Store'dan birçok mevcut uygulamanın yanı sıra özel olarak yeni uygulamalar HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1c336-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="1c336-106">Mağaza uygulamaları hakkında daha fazla bilgi için [bkz. Mağaza ile uygulamaları yönetme.](holographic-store-apps.md)</span><span class="sxs-lookup"><span data-stu-id="1c336-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c336-107">Kurumsal dağıtımlar için, bu yöntemlerin her ikisi de kullanan Geliştirici Modunu etkinleştirmenizi önerilmez.</span><span class="sxs-lookup"><span data-stu-id="1c336-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="1c336-108">Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız Lütfen Uygulama Yönetimi: Genel Bakış [sayfamızı gözden geçirebilirsiniz.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1c336-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="1c336-109">2 cihaz için herhangi bir geliştirici uygulama yükleme yöntemi HoloLens, bkz:</span><span class="sxs-lookup"><span data-stu-id="1c336-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="1c336-110">Cihaz Portalı: Uygulama Yükleme</span><span class="sxs-lookup"><span data-stu-id="1c336-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="1c336-111">Uygulamaları Visual Studio ve hata ayıklamak için Visual Studio kullanma</span><span class="sxs-lookup"><span data-stu-id="1c336-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="1c336-112">HoloLens [](holographic-custom-apps.md) (1. nesil) üzerinde özel uygulamalar dağıtmak HoloLens kılavuzumuza bakın.</span><span class="sxs-lookup"><span data-stu-id="1c336-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
