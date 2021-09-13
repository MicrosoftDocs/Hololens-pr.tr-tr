---
title: Ağ güvenliği
description: ağ güvenliği
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: Güvenlik, Hololens, ağ, ağ güvenliği
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036596"
---
# <a name="network-security"></a>Ağ güvenliği

## <a name="network-protocols"></a>Ağ protokolleri

Güncel olmayan NetBIOS (ağ temel giriş/çıkış sistemi), genellikle bir bilgisayar ve paylaşılan klasörlere ad çözümlemesi sağlamak için, geçmişte LAN senaryolarında yaygın olarak kullanılmaktadır. Ancak zaman içinde, NetBIOS çok sayıda saldırılara açıktır ve bunun ilgisi daha güvenli olan diğer protokollerin yerine düşdü. bu güvenlik açığı sorununu ortadan kaldırmak için, HoloLens 2, netbıos ile ilgili kodu işletim sisteminden çıkarmıştır.

TLS (Aktarım Katmanı Güvenliği) protokolleri sürekli gelişiyor. Bu alanın kapsamına girmeyen çeşitli güvenlik açıklarını izlemek için bilgi işlem sektörünün daha yeni ve daha etkin sürümlere göre derecelendirilmiş olması gerekir. Tüm sunucu dağıtımlarının yeni TLS protokolü sürümlerini benimsemesini sağlamak için gereken süre nedeniyle, farklı varsayılan protokol sürümlerindeki istemci ve sunucuların geçiş dönemi boyunca hala iletişim kurabilmesine izin veren bir geri dönüş mekanizması uygulanabilir.

## <a name="secure-connectivity"></a>Güvenli bağlantı 

Windows Defender güvenlik duvarı, cihaz bağlantısının güvenliğini sağlamak için kritik işlevler sunar. HoloLens 2 ile güvenlik duvarı her zaman etkindir ve bunu programlı olarak veya kullanıcı arabiriminden devre dışı bırakma yöntemi yoktur.

Mobil istemciler için uzaktan erişim ve bağlantı gizliliği, [UWP VPN eklentisi platformu](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)aracılığıyla garanti edilebilir. Üçüncü taraf VPN sağlayıcıları, uygulama kapsayıcısı korumalı alanı içinde çalışacak olan WinRT API 'Lerini kullanarak kendi eklentilerini oluşturabilir ve bu sayede sistem düzeyi sürücülerle ilgili sık karşılaşılan karmaşıklık ve sorunları ortadan kaldırır.
