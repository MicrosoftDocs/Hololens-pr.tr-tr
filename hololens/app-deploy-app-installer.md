---
title: HoloLens 2 uygulama yükleyicisi aracılığıyla uygulamaları dışarıdan yükleme ve yükleme
description: Uygulama Yükleyicisi ve dışarıdan yükleme ve uygulamaları kullanıcı arabirimi aracılığıyla yükleme hakkında bilgi edinin.
keywords: Uygulama yönetimi, uygulama, Hololens, uygulama yükleyicisi
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378999"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme

> [!NOTE]
> Bu özellik [Windows holographic, sürüm 20H2 – aralık 2020 güncelleştirmesi](hololens-release-notes.md)' nde kullanıma sunulmuştur. Cihazınızın bu özelliği kullanacak şekilde [güncelleştirildiğinden](hololens-update-hololens.md) emin olun.

HoloLens 2 cihazlarınızda **uygulamaları daha sorunsuz bir şekilde yüklemenize imkan tanımak için yeni bir yetenek (App Installer) ekledik** . Özelliği, **yönetilmeyen cihazlar için varsayılan olarak açık** olacaktır. Kurumların kesintiye uğramasını önlemek için, uygulama yükleyicisi Şu anda **Yönetilen cihazlarda kullanılamayacak** .  

**Aşağıdakilerden biri doğruysa** bir cihaz "yönetilen" olarak değerlendirilir:

- MDM [kaydı](hololens-enroll-mdm.md) yapılmış
- [Sağlama paketiyle](hololens-provisioning.md) yapılandırıldı
- Kullanıcı [kimliği](hololens-identity.md) Azure AD

Artık Geliştirici modunu etkinleştirmek veya cihaz portalını kullanmak gerekmeden uygulama yükleyebilirsiniz.  Cihazınıza appx paketini indirin (USB veya Microsoft Edge üzerinden) ve yüklemeyi başlatma isteminde bulunulacak dosya Gezgini 'ndeki appx grubuna gidin.  Alternatif olarak, [bir Web sayfasından bir yüklemeyi başlatabilirsiniz](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  MDM 'nin LOB uygulaması dağıtım özelliğini kullanarak Microsoft Store veya dışarıdan yüklemeden yüklediğiniz uygulamalar gibi uygulamalar, [Imza aracı](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) ile dijital olarak imzalanmalıdır ve uygulamanın dağıtılması [için, imzalama için kullanılan sertifikaya](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) , Hololens cihazı tarafından güvenilmesi gerekir.

## <a name="requirements"></a>Gereksinimler

### <a name="for-your-devices"></a>Cihazlarınız için:

Bu özellik şu anda HoloLens 2 cihazları için Windows holographic 20H2 Derlemeleriyle sunulmaktadır. Bu yöntemi kullanan cihazların [güncelleştirildiğinden](hololens-update-hololens.md)emin olun.

### <a name="for-your-apps"></a>Uygulamalarınız için:

Uygulama yükleyicisi depodan bağımlılıklar kullanacağı için uygulamanızın çözüm yapılandırması **ana** veya **Sürüm** olmalıdır. [Uygulama paketleri oluşturma](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)hakkında daha fazla bilgi için bkz..

Bu yöntem aracılığıyla yüklenen uygulamaların dijital olarak imzalanması gerekir. Uygulamayı imzalamak için bir sertifika kullanmanız gerekir. [MS GÜVENILEN CA listesinden](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)bir sertifika alabilirsiniz, bu durumda herhangi bir ek eylem gerçekleştirmeniz gerekmez. Ya da kendi sertifikanızı imzalayabilirsiniz, ancak sertifikanın cihaza itilmesi gerekecektir.

- [Imza aracını kullanarak](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) uygulamaları imzalama.

**Sertifika seçenekleri:**

- [MS güvenilen CA listesi](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Bir sertifika dağıtım yöntemi seçin.**

- [Sağlama paketleri](hololens-provisioning.md) , yerel cihazlara uygulanabilir.
- MDM, [cihaz yapılandırmalarına sahip sertifikalar uygulamak](https://docs.microsoft.com/mem/intune/protect/certificates-configure)için kullanılabilir.
- Cihaz [Sertifika Yöneticisi](certificate-manager.md)' ni kullanın.

## <a name="installation-method"></a>Yükleme yöntemi

1. Cihazınızın yönetilen olarak değerlendirilmediğini denetleyin.
1. HoloLens 2 cihazınızın açık olup olmadığını ve oturum açtığınızdan emin olun.
1. Bilgisayarınızda özel uygulamanıza gidin ve App. appxpaketi ' ni Devicename\ınternal Storage\downloadcopy dizinine kopyalayın.
    Dosyanızı kopyalamayı tamamladıktan sonra cihazınızın bağlantısını kesebilir ve yüklemeyi daha sonra tamamlayabiliriz.
1. HoloLens 2 cihazınızdan **Başlat menüsünü** açın, **tüm uygulamalar** ' ı seçin ve **Dosya Gezgini** uygulamasını başlatın.
1. Indirmeler klasörüne gidin. Uygulamanın sol panelinde **Bu cihazı** önce seçin, sonra İndirmeler ' a gidin.
1. Yourapp. appxpaket dosyasını seçin.
1. Uygulama yükleyicisi başlatılır. Uygulamanızı yüklemek için **Install** (Çalıştır) düğmesini seçin.

Yüklenen uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

![Uygulama yükleyicisi aracılığıyla MRTK örnekleri yükleme](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Yükleme sorunlarını giderme

Uygulamanız yüklenemedi, sorun gidermek için aşağıdakileri denetleyin:

- Uygulamanız bir ana veya yayın yapımı.
- Cihazınız, bu özelliğin kullanılabildiği bir yapıya güncelleştirildi.
- [İnternet 'e bağlısınız](hololens-network.md).
- [Microsoft Store uç noktalarınız](hololens-offline.md) doğru şekilde yapılandırılmıştır.  

## <a name="web-installer"></a>Web Yükleyicisi

Kullanıcılar, bir uygulamayı doğrudan bir Web sunucusundan yükleyebilir. Bu akış, kolay bir indirme ve yükleme dağıtım yöntemiyle birleştirilmiş uygulama yükleyicisini kullanır.

### <a name="how-to-set-up-web-install"></a>Web yüklemesini ayarlama:

1. Uygulamanızın yüklenmek üzere doğru yapılandırıldığından emin olun.
1. [Web sayfasından yüklemeyi etkinleştirmek için bu adımları](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)izleyin.

### <a name="end-user-experience"></a>Son Kullanıcı deneyimi:

1. Kullanıcı, yukarıda daha önce seçilmiş olan bir yöntemi kullanarak cihaza sertifikayı alır ve kurar.
1. Kullanıcı, yukarıdaki adımdan oluşturulan URL 'YI ziyaret ettiğinde.

Uygulama artık cihaza yüklenir. Uygulamayı bulmak için **Başlat menüsünü** açın ve uygulamanızı bulmak için **tüm uygulamalar** düğmesini seçin.

- Uygulama yükleyicisi yükleme yöntemiyle ilgili sorun giderme hakkında daha fazla yardım için [uygulama yükleyicisi sorunlarını giderme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)makalesini ziyaret edin.

> [!NOTE]
> Güncelleştirme işlemi sırasında kullanıcı arabirimi desteklenmiyor. Bu nedenle, [Bu sayfadaki](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ShowPrompt seçeneği ve ilgili seçenekler desteklenmez.

## <a name="sample-apps"></a>Örnek Uygulamalar

Uygulama yükleyicisini bazı örnek uygulamalarla denemek için bazı mevcut örneklerimizden göz atın:

- [MRTK örnekleri Merkezi](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Leri](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Test için kullanılabilen UWP örnek uygulamaları](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
