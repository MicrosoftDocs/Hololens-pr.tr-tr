---
title: Yaygın Cihaz Kısıtlamaları
description: HoloLens karma gerçeklik cihazı için yaygın cihaz kısıtlamaları ve ayarları hakkında güncel bilgi edinebilirsiniz.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378953"
---
# <a name="common-device-restrictions"></a>Yaygın Cihaz Kısıtlamaları 

Bu kılavuz, BT uzmanlarının kuruluşta işletim sistemi için kullanılabilen daha yaygın Windows 10 Holographic yönetim seçeneklerini anlarını anlamalarını sağlar. Bu ilkelerin MDM satıcınız tarafından nasıl etkinleştirildiğinden emin olmak için lütfen MDM sistem belgelerinize başvurun. Tüm MDM sistemleri bu kılavuzda açıklanan her ayarı desteklemez. Bazıları OMA-URI XML dosyaları aracılığıyla özel ilkeleri destekler. Bkz. [Microsoft Intune İlkeler için destek.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) Adlandırma kuralları MDM satıcıları arasında da değişiklik gösterebilir.

## <a name="prevent-changing-of-settings"></a>Ayarların değiştirilmesini engelleme
Çalışanların genellikle şirket cihazlarına kilitlemek istediğiniz bazı kişisel cihaz ayarlarını değiştirmesine izin verilir. Çalışanlar, ayarlar kullanıcı arabirimi aracılığıyla HoloLens'in belirli ayarlarını etkileşimli olarak ayarlayabilir. MDM kullanarak kullanıcıların değiştirmesine izin verilenleri sınırlandırabilirsiniz. Aşağıdaki listede, ayar kısıtlamalarını yapılandırmak için Windows 10 Holographic yaygın olarak kullanılan MDM ayarları listelebildi:
-   [VPN'e izin ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Kullanıcının VPN ayarlarını değiştirmesini sağlar
-   [El ile WiFi Yapılandırmasına İzin Ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Kullanıcıların MDM tarafından sağlanan Wi-Fi dışında bağlantı kurmalarına izin verir
-   [El ile MDM Kaydı Geri Kaydına İzin Ver](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Kullanıcıların çalışma alanı hesabını silebilir olup olmadığı (örneğin, cihazın MDM sisteminden kaydı silin)

Windows [Holographic, sürüm 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 cihazlara eklendi:
- [Sağlama Paketi Eklemeye İzin Ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Kullanıcıların yeni sağlama paketleri ek açıp ekleyeliklerini değiştirerek üzerine yeni değerler yazarak.
- [Sağlama Paketini Kaldırmaya İzin Ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Kullanıcılar sağlama paketlerini kaldırabilirse, önceden kilitlenmiş ayarları değiştirmelerine izin vererek iki durumlu düğmeyi değiştirin.

HoloLens tarafından desteklenen İlke CSP'leri içinde ilke seçenekleri hakkında [daha fazla ayrıntı bulabilirsiniz](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Donanım kısıtlamaları
Windows 10 Holographic cihazlar; kameralar, mikrofonlar, konuşmacılar, USB arabirimleri, Bluetooth arabirimleri ve Wi-Fi gibi popüler donanım özelliklerini içeren en son teknolojiden kullanılır. Bu özelliklerin kullanılabilirliğini kontrol etmek için donanım kısıtlamalarını kullanabilirsiniz.
Aşağıdaki liste, donanım kısıtlamalarını yapılandırmak için Windows 10 Holographic yaygın olarak kullanılan MDM ayarlarını listeler:

> [!NOTE]
> Bu donanım kısıtlamalarının bazıları, bağlantıları etkiler ve veri korumasına yardımcı olur.

-   [Wi-Fi'a izin ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Kullanıcıların cihazlarında WiFi radyoyu etkinleştirip kullanamayıp kullanayıp kullanamaylarından.
-   [USB Bağlantısına İzin Ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB bağlantısının etkin olup olmadığı (USB ücretlendirmesini etkilemez.)
-   [Bluetooth'a izin ver:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Kullanıcıların cihazlarında Bluetooth radyoyu etkinleştirip kullanamayıp kullanamayabiliyor.
-   [Kamerayı Kısıtla:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Windows uygulamalarının kameraya erişip erişe olmadığını belirtir.
-   [Mikrofonları Kısıtla:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Windows uygulamalarının mikrofona erişip erişe olmadığını belirtir.

Windows [Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 cihazlara eklendi. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ekran kapatana kadar zaman ayarlayın ve ekranı kapatarak cihazı kilitler. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ekran kapatana kadar zaman ayarlayın ve ekranı kapatarak cihazı kilitler. 
