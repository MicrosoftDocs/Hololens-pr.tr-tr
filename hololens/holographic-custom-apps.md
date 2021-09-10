---
title: HoloLens için özel uygulamaları yönetme (1. nesil)
description: Sanal cihazları ve sanal cihazları kullanarak özel holografik uygulamaları HoloLens yüklemeyi, kaldırmayı ve Cihaz Portalı Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side-load, side-load, store, uwp, app, install
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428525"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>HoloLens için özel uygulamaları yönetme (1. nesil)

HoloLens, Microsoft Store'den birçok mevcut uygulamanın yanı sıra özel olarak yeni uygulamalar HoloLens. Bu makale özel holografik uygulamalara odaklanır.  

Mağaza uygulamaları hakkında daha fazla bilgi için [bkz. Mağaza ile uygulamaları yönetme.](holographic-store-apps.md)

> [!IMPORTANT]
> O sırada HoloLens Developer Edition olarak da adlandırılan HoloLens (1. nesil) için aşağıdaki bilgiler oluşturulmuştır. Bu nedenle, uygulamaları cihaz portalı üzerinden kenardan yüklemek ve uygulamaları Visual Studio sıradan bir yerdi. Kurumsal dağıtımlar için, bu yöntemlerin her ikisi de kullanan Geliştirici Modunu etkinleştirmenizi önerilmez. Güvenli bir uygulama dağıtım yöntemiyle ilgileniyorsanız Lütfen Uygulama Yönetimi: Genel [Bakış sayfamızı gözden geçirebilirsiniz.](app-deploy-overview.md)
>
> HoloLens 2 cihazları için uygulama yüklemenin herhangi bir geliştirici yöntemini arıyorsanız lütfen şu bağlantılara bakın:
>
> - [Cihaz Portalı: Uygulama Yükleme](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Uygulamaları Visual Studio ve hata ayıklamak için Visual Studio kullanma](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Özel uygulamaları yükleme

Cihaz Portalı kullanarak veya HoloLens'den dağıtarak kendi uygulamalarınızı Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Uygulama paketini uygulama paketiyle Cihaz Portalı

1. Ağdan hedef [Cihaz Portalı](/windows/mixed-reality/using-the-windows-device-portal) bağlantı HoloLens.

1. Sol gezinti bölmesinde Uygulamalar **sayfasına** gidin.

1. Uygulama **Paketi altında,** uygulamayla ilişkili .appx dosyasına göz atabilirsiniz.

   > [!IMPORTANT]
   > İlişkili tüm bağımlılıklara ve sertifika dosyalarına başvurarak emin olun.

1. **Git'i seçin.**

   > [!div class="mx-imgBorder"]
   > ![Uygulama formunu Windows Cihaz Portalı'Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Microsoft Visual Studio 2015'te dağıtma

1. Uygulamanın Visual Studio (.sln dosyası) açın.

1. Projenin Özellikler'ini **açın.**

1. Şu derleme yapılandırmasını seçin: **Ana/x86/Uzak Makine.**

1. Uzak **Makine'yi seçerek:**
   - Adresin, kendi ip Wi-Fi ip adresine HoloLens.
   - Kimlik doğrulamasını **Evrensel (Şifrelenmemiş Protokol) olarak ayarlayın.**
   
1. Çözümlerinizi oluşturma.

1. Uygulamayı geliştirme bilgisayarınızdan uygulamanıza dağıtmak HoloLens **Makine'yi seçin.** Yeni sürümde zaten bir derlemeniz varsa **HoloLens'ı** seçerek bu yeni sürümü yükleyin.  

   ![Uygulamalar için uzak makine dağıtımı Microsoft HoloLens uzaktan Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. Uygulama, uygulama uygulamanıza yüklenir ve HoloLens.

Bir uygulamayı yükledikten sonra uygulamayı Tüm uygulamalar listesinde bulabilirsiniz  (**Başlangıç**  >  **Tüm uygulamalar).**
