---
title: HoloLens için özel uygulamaları yönetme (1. Genel)
description: Cihaz portalı ve Visual Studio kullanarak özel holographic uygulamalarını HoloLens cihazlarına yüklemeyi, kaldırmayı ve dışarıdan yüklemeyi öğrenin.
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379009"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>HoloLens için özel uygulamaları yönetme (1. Genel)

HoloLens, Microsoft Store mevcut birçok uygulamayı ve özellikle HoloLens için oluşturulmuş yeni uygulamaları destekler. Bu makale özel holographic uygulamalarına odaklanır.  

Mağaza uygulamaları hakkında daha fazla bilgi için bkz. [Store ile uygulamaları yönetme](holographic-store-apps.md).

> [!IMPORTANT]
> HoloLens (1. gen) için, aynı zamanda HoloLens geliştirici sürümü olarak da adlandırılan aşağıdaki bilgiler oluşturulmuştur. Bu tür dışarıdan yükleme uygulamaları cihaz portalı aracılığıyla ve uygulamaları Visual Studio aracılığıyla yüklerken normal daha sonra. Kurumsal dağıtımlar için, bu yöntemlerin her ikisinin de kullanıldığı geliştirici modunun etkinleştirilmesini önermeyiz. Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız lütfen [uygulama yönetimizi gözden geçirin: genel bakış](app-deploy-overview.md).
>
> HoloLens 2 cihazları için uygulama yüklemesinin geliştirici yöntemini arıyorsanız lütfen şu adresine başvurun:
> - [Cihaz Portalı: uygulama yükleme](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uygulamaları dağıtmak ve hatalarını ayıklamak için Visual Studio 'Yu kullanma](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Özel uygulamaları yükleme

Cihaz portalını kullanarak ya da uygulamaları Visual Studio 'dan dağıtarak, kendi uygulamalarınızı HoloLens 'te yükleyebilirsiniz.

### <a name="installing-an-application-package-with-the-device-portal"></a>Cihaz portalı ile uygulama paketi yükleme

1. [Cihaz portalından](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) hedef HoloLens 'e bir bağlantı kurun.

1. Sol gezinti bölmesinde **uygulamalar** sayfasına gidin.

1. Uygulama **paketi** altında, uygulamanızla ilişkili. appx dosyasına gidin.

   > [!IMPORTANT]
   > İlişkili tüm bağımlılık ve sertifika dosyalarına başvurduğunuzdan emin olun.

1. **Git**' i seçin.

   > [!div class="mx-imgBorder"]
   > ![Microsoft HoloLens 'te Windows cihaz portalında uygulama formu yüklemesi](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Microsoft Visual Studio 2015 ' den dağıtma

1. Uygulamanızın Visual Studio çözümünü (. sln dosyası) açın.

1. Projenin **özelliklerini** açın.

1. Aşağıdaki derleme yapılandırmasını seçin: **ana/x86/uzak makine**.

1. **Uzak makineyi** seçtiğinizde:
   - Adresin, HoloLens sitenizin Wi-Fi IP adresine işaret ettiğini doğrulayın.
   - Kimlik doğrulamasını **Evrensel (şifrelenmemiş protokol)** olarak ayarlayın.
   
1. Çözümünüzü oluşturun.

1. Uygulamayı geliştirme BILGISAYARıNıZDAN HoloLens 'e dağıtmak için **uzak makine**' yi seçin. HoloLens üzerinde zaten var olan bir derlemeniz varsa, bu yeni sürümü yüklemek için **Evet** ' i seçin.  

   ![Visual Studio 'da uygulamalar için uzak makine dağıtımı Microsoft HoloLens](images/vs2015-remotedeployment.jpg)  
   
1. Uygulama, HoloLens 'te yüklenir ve otomatik olarak başlatılır.

Bir uygulamayı yükledikten sonra, bu dosyayı **tüm uygulamalar** listesinde (  >  **tüm uygulamaları** Başlat) görürsünüz.
