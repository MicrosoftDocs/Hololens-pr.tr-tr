---
title: Ağ güvenliği
description: ağ güvenliği
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: güvenlik, hololens, ağ, ağ güvenliği
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640500"
---
# <a name="network-security"></a><span data-ttu-id="f066c-104">Ağ güvenliği</span><span class="sxs-lookup"><span data-stu-id="f066c-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="f066c-105">Ağ protokolleri</span><span class="sxs-lookup"><span data-stu-id="f066c-105">Network protocols</span></span>

<span data-ttu-id="f066c-106">Eski NetBIOS (Ağ Temel Giriş/Çıkış Sistemi), LAN senaryolarında yaygın olarak kullanılmıştır. Bu senaryolar genellikle bir bilgisayara ve paylaşılan klasörlere ad çözümlemesi sağlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f066c-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="f066c-107">Ancak zaman içinde NetBIOS'ın birden çok saldırıya açık olduğu kanıtlandı ve ilgi düzeyi diğer daha güvenli protokoller için azaldı.</span><span class="sxs-lookup"><span data-stu-id="f066c-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="f066c-108">Bu güvenlik açığı sorunu gidermek için HoloLens 2, NetBIOS ile ilgili kodu işletim sisteminden kaldırmış oldu.</span><span class="sxs-lookup"><span data-stu-id="f066c-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="f066c-109">TLS (Aktarım Katmanı Güvenliği) protokolleri sürekli gelişmektedir.</span><span class="sxs-lookup"><span data-stu-id="f066c-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="f066c-110">Bilgi işlem sektörü, bu alanda ortaya çıkan çeşitli güvenlik açıklarını takip etmek için daha yeni ve daha etkili sürümlere çıktı.</span><span class="sxs-lookup"><span data-stu-id="f066c-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="f066c-111">Tüm sunucu dağıtımlarının yeni TLS protokol sürümlerini benimsemesi için gereken süre nedeniyle, farklı varsayılan protokol sürümlerindeki istemci ve sunucuların geçiş dönemi boyunca iletişim kurmasına izin verir bir geri dönüş mekanizması uygulanabiliyor.</span><span class="sxs-lookup"><span data-stu-id="f066c-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="f066c-112">Güvenli bağlantı</span><span class="sxs-lookup"><span data-stu-id="f066c-112">Secure connectivity</span></span> 

<span data-ttu-id="f066c-113">Windows Defender Güvenlik Duvarı, cihaz bağlantısının güvenliğini sağlamak için kritik işlevler sunar.</span><span class="sxs-lookup"><span data-stu-id="f066c-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="f066c-114">Güvenlik HoloLens 2 ile güvenlik duvarı her zaman etkinleştirilir ve bunu program aracılığıyla veya kullanıcı arabirimi aracılığıyla devre dışı bırakmanın hiçbir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="f066c-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="f066c-115">Mobil istemciler için uzaktan erişim ve bağlantı gizliliği, [UWP VPN eklenti platformu aracılığıyla güvence olabilir.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="f066c-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="f066c-116">Üçüncü taraf VPN sağlayıcıları, AppContainer korumalı alanı içinde çalıştıracak WinRT API'lerini kullanarak kendi eklentilerini oluşturabilir ve bu da sistem düzeyinde sürücüler yazmayla ilgili karmaşıklığı ve sorunları ortadan kaldırmaktadır.</span><span class="sxs-lookup"><span data-stu-id="f066c-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
