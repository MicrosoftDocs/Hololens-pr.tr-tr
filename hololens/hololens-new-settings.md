---
title: Yeni Ayarlar tanıtımı
description: Yeni uygulama hakkında Ayarlar öğrenin
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, ayarlar, uygulama seçici, birim
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189673"
---
# <a name="new-settings-app"></a>Yeni Ayarlar uygulaması

[Holographic Windows sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile, Ayarlar uygulamasının yeni bir sürümünü Ayarlar tanıtabilirsiniz. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni uygulama Ayarlar eski Ayarlar farklı olduğundan, Ayarlar ortamınıza yerleştiren tüm windows güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar giriş sayfası.](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarlar: Anahtar sözcükleri veya ayarın adını Ayarlar giriş sayfasından ayarlar için arama yapın.
- Sistem > [Renk ayarlama](hololens2-display.md#how-to-use-display-color-calibration)
    - HoloLens 2 ekranınız için alternatif bir renk profili seçin.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, ses seslerini ses Bluetooth veya ses girişi için USB-C mikrofonu kullanın).
    > [!NOTE]
    > Bluetooth mikrofonlar, 2. HoloLens desteklemez.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Uygulama [başına birim denetimine bakın.](holographic-home.md#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktada otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık uçak modunu 2. HoloLens etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](holographic-home.md#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Daha önce Ayarlar pencereler kaldırılır (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden Ayarlar. IT yöneticileri, HoloLens 2 cihaz adı şablonu için [Windows Autopilot'ı](hololens2-autopilot.md) veya MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme beklİlmz).

