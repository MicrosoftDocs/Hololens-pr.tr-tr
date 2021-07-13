---
title: yeni Ayarlar uygulamasına giriş
description: yeni Ayarlar uygulaması hakkında bilgi edinin
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, ayarlar, uygulama seçicisi, birim
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640177"
---
# <a name="new-settings-app"></a>yeni Ayarlar uygulaması

[Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1)ile, Ayarlar uygulamasının yeni bir sürümünü kullanıma sunuyoruz. yeni Ayarlar uygulaması aşağıdaki alanlarda HoloLens 2 için yeni özellikleri ve genişletilmiş ayarları içerir: ses, güç & sleep, ağ & ınternet, uygulamalar, hesaplar, erişim kolaylığı ve daha fazlası.

> [!NOTE]
> yeni Ayarlar uygulaması eski Ayarlar uygulamasından farklı olduğu için, daha önce ortamınıza yerleştirdiğiniz tüm Ayarlar pencereleri güncelleştirme sonrasında kaldırılır.

![yeni Ayarlar uygulama giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- arama Ayarlar: anahtar sözcükler veya ayarın adı kullanılarak Ayarlar giriş sayfasından ayarları arayın.
- Sistem > [renk ayarlama](hololens2-display.md#how-to-use-display-color-calibration)
    - HoloLens 2 görüntü için alternatif bir renk profili seçin.
- Sistem > sesi:
  - giriş ve çıkış ses cihazları: bağımsız olarak giriş ve çıkış ses cihazlarınızı seçin (örneğin, Bluetooth kulaklık aracılığıyla ses dinleyin veya ses girişi için bir USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar HoloLens 2 tarafından desteklenmez.
  - Uygulama hacmi: her uygulamanın birimini bağımsız olarak ayarlayın. Bkz. [uygulama birimi denetimi başına](holographic-home.md#per-app-volume-control).
- System > güç & uyku: bir süre işlem yapılmadan sonra cihazın uyku moduna geçmesi gerektiğini seçin.
- Sistem > pili: pil tasarrufu modunu el ile etkinleştirin veya nokta pil tasarrufu modunun otomatik olarak etkinleştirileceği bir pil eşiği ayarlayın.
- USB > cihazlar: varsayılan olarak USB bağlantılarını devre dışı bırakabilirsiniz.
- Internet & ağı:
  - USB-C Ethernet bağdaştırıcıları artık ağ & Internet 'te görüntülenir.
  - USB-C Ethernet bağdaştırıcısı ayarları, IP adresi dahil artık kullanılabilir.
  - artık HoloLens 2 üzerinde uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için bkz. [Varsayılan uygulama Seçicisi](holographic-home.md#default-app-picker).
- Hesaplar diğer kullanıcılar >: cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilir, cihaz sahiplerini standart kullanıcılara indirgeyebilirler ve kullanıcıları kaldırabilir.
- Erişim kolaylığı: metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- daha önce yerleştirilmiş Ayarlar pencereleri kaldırılır (yukarıdaki nota bakın).
- cihazınızı artık Ayarlar uygulamayla yeniden adlandıramazsınız. bt yöneticileri, HoloLens 2 cihaz adı şablonu veya MDM [devdetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/dnscomputername düğümü [için Windows Autopilot](hololens2-autopilot.md) kullanarak cihazları yeniden adlandırabilirler.
- Ethernet sayfasında her zaman sanal bir Ethernet aygıtı ("UsbNcm") gösterilir.
- yeni Microsoft Edge pil kullanımı, bir UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak doğası nedeniyle doğru olmayabilir (kısa süre önce düzeltilmez).

