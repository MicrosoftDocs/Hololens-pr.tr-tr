---
title: Yaygın Cihaz Kısıtlamaları
description: Karma gerçeklik cihazı için yaygın cihaz kısıtlamalarını ve ayarlarını HoloLens takip edin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924305"
---
# <a name="common-device-restrictions"></a>Yaygın Cihaz Kısıtlamaları

Bu kılavuz, BT uzmanlarının kuruluşta işletim sistemi için kullanılabilen daha yaygın Windows 10 Holographic yönetim seçeneklerini anlarını anlamanıza yardımcı olur. Bu ilkelerin MDM satıcınız tarafından nasıl etkinleştirildiğinden emin olmak için lütfen MDM sistem belgelerinize başvurun. Tüm MDM sistemleri bu kılavuzda açıklanan her ayarı desteklemez. Bazıları OMA-URI XML dosyaları aracılığıyla özel ilkeleri destekler. [Bkz Microsoft Intune özel ilkeler için destek.](/mem/intune/configuration/custom-settings-windows-10) Adlandırma kuralları MDM satıcıları arasında da değişiklik gösterebilir.

## <a name="prevent-changing-of-settings"></a>Ayarların değiştirilmesini engelleme

Çalışanların genellikle şirket cihazlarına kilitlemek istediğiniz bazı kişisel cihaz ayarlarını değiştirmesine izin verilir. Çalışanlar, ayarların kullanıcı arabirimi aracılığıyla HoloLens ayarlarını etkileşimli olarak ayarlayabilir. MDM kullanarak kullanıcıların değiştirmesine izin verilenleri sınırlandırabilirsiniz.
Aşağıda, sık kullanılan ve ayar kısıtlamalarını yapılandırmak için Windows 10 Holographic MDM ayarları listelebildi:

- [VPN'e izin ver:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Kullanıcının VPN ayarlarını değiştirmesini sağlar
- [El ile WiFi Yapılandırmasına İzin Ver:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Kullanıcıların MDM tarafından sağlanan Wi-Fi dışında bağlantı kurmalarına izin verir
- [El ile MDM Kaydı Geri Kaydına İzin Ver](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Kullanıcıların çalışma alanı hesabını silebilir olup olmadığı (örneğin, cihazın MDM sisteminden kaydı silin)

Windows 2 [cihazlar için Holographic sürüm 20H2 HoloLens](hololens-release-notes.md#windows-holographic-version-20h2) eklendi:

- [Sağlama Paketi Eklemeye İzin Ver:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Kullanıcıların yeni sağlama paketleri ek açıp ekleyeliklerini değiştirerek üzerine yeni değerler yazarak.
- [Sağlama Paketini Kaldırmaya İzin Ver:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Kullanıcılar sağlama paketlerini kaldırabilirse, önceden kilitlenmiş ayarları değiştirmelerine izin vererek iki durumlu düğmeyi değiştirin.

Windows [Holographic, sürüm 21H2'ye eklendi:](hololens-release-notes.md#windows-holographic-version-21h2)

- [RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) ilkesi, Microsoft Store uygulamasının yalnızca özel mağazayı yalnızca kendi özel mağazanızı gösterecek şekilde yapılandırılması için yapılandırıldığından, erişimi yalnızca kullanılabilir yaptık uygulamalarla sınırlandırabilirsiniz.

Desteklenen İlke CSP'leri için HoloLens seçenekleri [hakkında daha fazla ayrıntı bulabilirsiniz](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Donanım kısıtlamaları

Windows 10 Holographic cihazlar; kameralar, mikrofonlar, konuşmacılar, USB arabirimleri, Bluetooth arabirimleri ve Wi-Fi gibi popüler donanım özelliklerini içeren en son teknolojiden kullanılır. Bu özelliklerin kullanılabilirliğini kontrol etmek için donanım kısıtlamalarını kullanabilirsiniz.
Aşağıdaki liste, donanım kısıtlamalarını yapılandırmak için Windows 10 Holographic yaygın olarak kullanılan MDM ayarlarını listeler:

> [!NOTE]
> Bu donanım kısıtlamalarının bazıları, bağlantıları etkiler ve veri koruma konusunda yardımcı olur.

- [Wi-Fi'a izin ver:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Kullanıcıların cihazlarında WiFi radyoyu etkinleştirip kullanamayıp kullanamayyıp kullanamayabilirsiniz.
- [USB Bağlantısına İzin Ver:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB bağlantısının etkin olup olmadığı (USB ücretlendirmesini etkilemez.)
- [İzin Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Kullanıcıların cihazlarında Bluetooth ve kullanıp kullanamayıp kullanamayabilirsiniz.
- [Kamerayı Kısıtla:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Uygulamaların kameraya Windows olup olmadığını belirtir.
- [Mikrofonları Kısıtla:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Uygulamaların mikrofona Windows olup olmadığını belirtir.

Windows 2 [cihazlar için Holographic sürüm 20H2 HoloLens](hololens-release-notes.md#windows-holographic-version-20h2) eklendi:

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ekran kapatana kadar zaman ayarlayın ve ekranı kapatarak cihazı kilitler.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ekran kapatana kadar zaman ayarlayın ve ekranı kapatarak cihazı kilitler.
