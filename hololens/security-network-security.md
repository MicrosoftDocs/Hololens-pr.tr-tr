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
# <a name="network-security"></a>Ağ güvenliği

## <a name="network-protocols"></a>Ağ protokolleri

Eski NetBIOS (Ağ Temel Giriş/Çıkış Sistemi), LAN senaryolarında yaygın olarak kullanılmıştır. Bu senaryolar genellikle bir bilgisayara ve paylaşılan klasörlere ad çözümlemesi sağlamak için kullanılır. Ancak zaman içinde NetBIOS'ın birden çok saldırıya açık olduğu kanıtlandı ve ilgi düzeyi diğer daha güvenli protokoller için azaldı. Bu güvenlik açığı sorunu gidermek için HoloLens 2, NetBIOS ile ilgili kodu işletim sisteminden kaldırmış oldu.

TLS (Aktarım Katmanı Güvenliği) protokolleri sürekli gelişmektedir. Bilgi işlem sektörü, bu alanda ortaya çıkan çeşitli güvenlik açıklarını takip etmek için daha yeni ve daha etkili sürümlere çıktı. Tüm sunucu dağıtımlarının yeni TLS protokol sürümlerini benimsemesi için gereken süre nedeniyle, farklı varsayılan protokol sürümlerindeki istemci ve sunucuların geçiş dönemi boyunca iletişim kurmasına izin verir bir geri dönüş mekanizması uygulanabiliyor.

## <a name="secure-connectivity"></a>Güvenli bağlantı 

Windows Defender Güvenlik Duvarı, cihaz bağlantısının güvenliğini sağlamak için kritik işlevler sunar. Güvenlik HoloLens 2 ile güvenlik duvarı her zaman etkinleştirilir ve bunu program aracılığıyla veya kullanıcı arabirimi aracılığıyla devre dışı bırakmanın hiçbir yolu yoktur.

Mobil istemciler için uzaktan erişim ve bağlantı gizliliği, [UWP VPN eklenti platformu aracılığıyla güvence olabilir.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Üçüncü taraf VPN sağlayıcıları, AppContainer korumalı alanı içinde çalıştıracak WinRT API'lerini kullanarak kendi eklentilerini oluşturabilir ve bu da sistem düzeyinde sürücüler yazmayla ilgili karmaşıklığı ve sorunları ortadan kaldırmaktadır.
