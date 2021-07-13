---
title: HoloLens için özel uygulamaları yönetme (1. genel)
description: cihaz portalını ve Visual Studio kullanarak HoloLens cihazlarda özel holographic uygulamalarını yüklemeyi, kaldırmayı ve dışarıdan yüklemeyi öğrenin.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: Hololens, dışarıdan yükleme, dışarıdan yükleme, dışarıdan yükleme, mağaza, UWP, uygulama, yükleme
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635917"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>HoloLens için özel uygulamaları yönetme (1. genel)

HoloLens, Microsoft Store birçok mevcut uygulamayı ve özellikle HoloLens için oluşturulan yeni uygulamaları destekler. Bu makale özel holographic uygulamalarına odaklanır.  

Mağaza uygulamaları hakkında daha fazla bilgi için bkz. [Store ile uygulamaları yönetme](holographic-store-apps.md).

> [!IMPORTANT]
> HoloLens geliştirici sürümü olarak da adlandırılan HoloLens (1. gen) için aşağıdaki bilgiler oluşturulmuştur. bu tür dışarıdan yükleme uygulamaları cihaz portalı aracılığıyla ve uygulamaları Visual Studio aracılığıyla yüklerken daha fazla yer. Kurumsal dağıtımlar için, bu yöntemlerin her ikisinin de kullanıldığı geliştirici modunun etkinleştirilmesini önermeyiz. Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız lütfen [uygulama yönetimizi gözden geçirin: genel bakış](app-deploy-overview.md).
>
> HoloLens 2 cihazları için uygulama yüklemesinin geliştirici yöntemini arıyorsanız lütfen şu adresine başvurun:
>
> - [Cihaz Portalı: uygulama yükleme](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [uygulamaları dağıtmak ve hata ayıklamak için Visual Studio kullanma](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Özel uygulamaları yükleme

cihaz portalını kullanarak veya uygulamaları Visual Studio dağıtarak, kendi uygulamalarınızı HoloLens yükleyebilirsiniz.

### <a name="installing-an-application-package-with-the-device-portal"></a>Cihaz portalı ile uygulama paketi yükleme

1. [Cihaz portalından](/windows/mixed-reality/using-the-windows-device-portal) hedef HoloLens bir bağlantı kurun.

1. Sol gezinti bölmesinde **uygulamalar** sayfasına gidin.

1. Uygulama **paketi** altında, uygulamanızla ilişkili. appx dosyasına gidin.

   > [!IMPORTANT]
   > İlişkili tüm bağımlılık ve sertifika dosyalarına başvurduğunuzdan emin olun.

1. **Git**' i seçin.

   > [!div class="mx-imgBorder"]
   > ![uygulama formunu Windows cihaz portalında Microsoft HoloLens üzerine yükler](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Microsoft Visual Studio 2015 ' den dağıtma

1. uygulamanızın Visual Studio çözümünü (. sln dosyası) açın.

1. Projenin **özelliklerini** açın.

1. Aşağıdaki derleme yapılandırmasını seçin: **ana/x86/uzak makine**.

1. **Uzak makineyi** seçtiğinizde:
   - Adresin, HoloLens Wi-Fi IP adresine işaret ettiğini doğrulayın.
   - Kimlik doğrulamasını **Evrensel (şifrelenmemiş protokol)** olarak ayarlayın.
   
1. Çözümünüzü oluşturun.

1. uygulamayı geliştirme bilgisayarınızdan HoloLens dağıtmak için **uzak makine**' yi seçin. HoloLens zaten var olan bir derlemeniz varsa, bu yeni sürümü yüklemek için **evet** ' i seçin.  

   ![Visual Studio Microsoft HoloLens uygulamalar için uzak makine dağıtımı](images/vs2015-remotedeployment.jpg)  
   
1. Uygulama, HoloLens yükleyip otomatik olarak başlatılacak.

Bir uygulamayı yükledikten sonra, bu dosyayı **tüm uygulamalar** listesinde (  >  **tüm uygulamaları** Başlat) görürsünüz.
