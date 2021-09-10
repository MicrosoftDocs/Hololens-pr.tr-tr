---
title: Ortak cihaz kısıtlamaları
description: HoloLens karma gerçeklik cihazının ortak cihaz kısıtlamaları ve ayarlarıyla güncel tutun.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427959"
---
# <a name="common-device-restrictions"></a>Ortak cihaz kısıtlamaları 

bu kılavuz, bt uzmanlarının kuruluştaki Windows 10 Holographic işletim sistemine yönelik daha yaygın olarak kullanılan yönetim seçeneklerini anlamalarına yardımcı olur. Bu ilkelerin MDM satıcınız tarafından nasıl etkinleştirildiğini anlamak için lütfen MDM sisteminizin belgelerine başvurun. Tüm MDM sistemleri bu kılavuzda açıklanan tüm ayarları desteklemez. Bazı özel ilkeleri OMA-URI XML dosyaları aracılığıyla destekler. bkz. [özel ilkeler için Microsoft Intune desteği](/mem/intune/configuration/custom-settings-windows-10). Adlandırma kuralları MDM satıcıları arasında da farklılık gösterebilir.

## <a name="prevent-changing-of-settings"></a>Ayarların değiştirilmesini engelle
Çalışanların genellikle kurumsal cihazlarda kilitlemek isteyebileceğiniz belirli kişisel cihaz ayarlarını değiştirmesine izin verilir. çalışanlar, ayarlar kullanıcı arabirimi aracılığıyla HoloLens belirli ayarlarını etkileşimli bir şekilde ayarlayabilir. MDM 'yi kullanarak kullanıcıların değiştirmesine izin verilen kullanıcıları sınırlayabilirsiniz. aşağıda, Windows 10 Holographic ayarları kısıtlamaları yapılandırmak üzere desteklediği yaygın olarak kullanılan MDM ayarları listelenmektedir:
-   [VPN 'ye Izin ver:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Kullanıcının VPN ayarlarını değiştirmesine izin verir
-   [El Ile WiFi yapılandırmasına Izin ver:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Kullanıcıların MDM tarafından sağlanan ağların dışında Wi-Fi bağlantıları yapmasına izin verir
-   [El Ile MDM kaydı kaldırmaya Izin ver](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Kullanıcıların çalışma alanı hesabını silmesine izin verilip verilmediği (yani, cihazın MDM sisteminden kaydını kaldırma)

HoloLens 2 cihazları için [Windows Holographic, sürüm 20h2 ' ye](hololens-release-notes.md#windows-holographic-version-20h2) eklendi:
- [Sağlama paketi eklemeye Izin ver:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Kullanıcıların yeni sağlama paketleri ekleyebiliyorsanız, yeni değerlerle üzerine yazarak geçiş yapın.
- [Sağlama paketinin kaldırılmasına Izin ver:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Kullanıcıların, sağlama paketlerini kaldırabilmesinin ardından daha önce kilitli ayarları değiştirmesine izin vermek için değiştirin.

HoloLens desteklenen [ilke csp 'lerine](/windows/client-management/mdm/policy-csps-supported-by-hololens2) ilke seçenekleri hakkında daha fazla ayrıntı bulun

## <a name="hardware-restrictions"></a>Donanım kısıtlamaları
Windows 10 Holographic cihazlar; kameralar, mikrofonlar, hoparlörler, USB arabirimleri, Bluetooth arabirimleri ve Wi-Fi gibi popüler donanım özelliklerini içeren son teknoloji teknolojisini kullanır. Bu özelliklerin kullanılabilirliğini denetlemek için donanım kısıtlamalarını kullanabilirsiniz.
aşağıda, donanım kısıtlamalarını yapılandırmak için Windows 10 Holographic desteklediği yaygın olarak kullanılan MDM ayarları listelenmektedir:

> [!NOTE]
> Bu donanım sınırlamalarından bazıları, veri korumasına yönelik bağlantıyı ve yardımı etkiler.

-   [Wi-Fi ' a Izin ver:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Kullanıcıların cihazlarında WiFi radyoyu etkinleştirip kullanıp kullanamayacağını belirtir.
-   [USB bağlantısına Izin ver:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB bağlantısının etkin olup olmadığı (USB şarjını etkilemez.)
-   [Bluetooth Izin ver:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) kullanıcıların cihazlarında Bluetooth radyoyu etkinleştirip kullanıp kullanamayacağını belirtir.
-   [Kamerayı kısıtla:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows uygulamaların kameraya erişip erişemeyeceğini belirtir.
-   [Mikrofonları kısıtla:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows uygulamaların mikrofona erişip erişemeyeceğini belirtir.

HoloLens 2 cihazları için [Windows Holographic, sürümü 20h2 ' ye](hololens-release-notes.md#windows-holographic-version-20h2) eklenmiştir. 
- [Displayofftimeoutonpili](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Görüntü kapanana kadar olan süreyi ayarlayın ve ekran devre dışı bırakarak cihazı kilitler. 
- [Displayofftimeoutpluggedın](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Görüntü kapanana kadar olan süreyi ayarlayın ve ekran devre dışı bırakarak cihazı kilitler. 
