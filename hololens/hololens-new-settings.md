---
title: Yeni Ayarlar uygulamasına tanıtma
description: Yeni Ayarlar uygulaması hakkında bilgi edinebilirsiniz
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, ayarlar, uygulama seçici, birim
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380298"
---
# <a name="new-settings-app"></a>Yeni Ayarlar uygulaması

[Windows Holographic sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)ile, Ayarlar uygulamasının yeni bir sürümünü tanıtabilirsiniz. Yeni Ayarlar uygulaması şu alanlarda HoloLens 2 için yeni özellikler ve genişletilmiş ayarlar içerir: Ses, Power & uyku, Ağ & İnternet, Uygulamalar, Hesaplar, Erişim Kolaylığı ve daha fazlası.

> [!NOTE]
> Yeni Ayarlar uygulaması eski Ayarlar uygulamasından ayrı olduğundan, daha önce ortamınıza yerleştirilen tüm Ayarlar pencereleri güncelleştirmeden sonra kaldırılır.

![Yeni Ayarlar uygulaması giriş sayfası](images/new-settings-app.png)

**Yeni özellikler ve ayarlar**
- Ayarlar araması: Anahtar sözcükleri veya ayarın adını kullanarak Ayarlar giriş sayfasından ayarlar için arama yapın.
- Sistem > [Renk ayarlama](hololens2-display.md#how-to-use-display-color-calibration)
    - HoloLens 2 ekranınız için alternatif bir renk profili seçin.
- System > Sound:
  - Giriş ve çıkış ses cihazları: Giriş ve çıkış ses cihazlarınızı bağımsız olarak seçin (örneğin, Bluetooth mikrofonları aracılığıyla ses dinleme veya ses girişi için USB-C mikrofonu kullanma).
    > [!NOTE]
    > Bluetooth mikrofonları HoloLens 2 tarafından desteklenmiyor.
  - Uygulama hacmi: Her uygulamanın hacmini bağımsız olarak ayarlayın. Bkz. [uygulama başına birim denetimi.](holographic-home.md#per-app-volume-control)
- Sistem > Power & uykuda: Cihazın bir süre sonra ne zaman uykuda olması gerektiğini seçin.
- Sistem > Pil: Pil tasarrufu modunu el ile etkinleştirin veya belirli bir noktanın otomatik olarak pil tasarrufu bir pil eşiği ayarlayın.
- Cihazlar > USB kullanır: USB bağlantılarını varsayılan olarak devre dışı abilirsiniz.
- Ağ & İnternet:
  - USB-C Ethernet bağdaştırıcıları artık İnternet'te ağ & görünür.
  - USB-C Ethernet bağdaştırıcısı ayarları artık IP adresi de dahil olmak üzere kullanılabilir.
  - Artık HoloLens 2'de uçak modunu etkinleştirebilirsiniz.
- Uygulamalar: Dosya ve bağlantı türleri için kullanılan varsayılan uygulamaları sıfırlayabilirsiniz. Daha fazla bilgi için [bkz. Varsayılan uygulama seçici.](holographic-home.md#default-app-picker)
- Hesaplar > Diğer kullanıcılar: Cihaz sahipleri kullanıcı ekleyebilir, standart kullanıcıları cihaz sahiplerine yükseltebilirsiniz, cihaz sahiplerini standart kullanıcılara düşürebilirsiniz ve kullanıcıları kaldırabilir.
- Erişim Kolaylığı: Metin boyutunu ve bazı görsel etkileri değiştirme.

**Bilinen sorunlar**
- Daha önce yerleştirilen Ayarlar pencereleri kaldırılır (yukarıdaki nota bakın).
- Artık Ayarlar uygulamasıyla cihazınızı yeniden adlandıramazsiniz. IT [yöneticileri, HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) için Windows Autopilot şablonu veya MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName düğümünü kullanarak cihazları yeniden adlandırabilirsiniz.
- Ethernet sayfası her zaman bir sanal Ethernet cihazı ("UsbNcm") gösterir.
- Yeni uygulamanın pil Microsoft Edge, UWP bağdaştırıcı katmanı tarafından desteklenen bir Win32 masaüstü uygulaması olarak yapısı nedeniyle doğru olmayabilir (yakın zamanda düzeltme bek gerekmmektedir).

