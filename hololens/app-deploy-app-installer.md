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
ms.openlocfilehash: 0b0de9039ce4d0c1eeab968b0f7c2f5eee8cdc34739391b6022b409325955350
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665276"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme

> [!NOTE]
> bu özellik [Windows Holographic, sürüm 20h2 – aralık 2020 güncelleştirme](hololens-release-notes.md)' de kullanıma sunulmuştur. Cihazınızın bu özelliği kullanacak şekilde [güncelleştirildiğinden](hololens-update-hololens.md) emin olun.

HoloLens 2 cihazlarınıza **daha sorunsuz uygulamalar yüklemenize olanak tanımak için yeni bir yetenek (App ınstaller) ekledik** . Özelliği, **yönetilmeyen cihazlar için varsayılan olarak açık** olacaktır. Kurumların kesintiye uğramasını önlemek için, uygulama yükleyicisi Şu anda **Yönetilen cihazlarda kullanılamayacak** .  

**Aşağıdakilerden biri doğruysa** bir cihaz "yönetilen" olarak değerlendirilir:

- MDM [kaydı](hololens-enroll-mdm.md) yapılmış
- [Sağlama paketiyle](hololens-provisioning.md) yapılandırıldı
- Kullanıcı [kimliği](hololens-identity.md) Azure AD

Artık Geliştirici modunu etkinleştirmek veya cihaz portalını kullanmak gerekmeden uygulama yükleyebilirsiniz.  bilgisayarınıza appx paketini indirin (USB veya ile Microsoft Edge) ve dosya gezgini 'ndeki appx paketine giderek yüklemeyi yeniden başlatma istenir.  Alternatif olarak, [bir Web sayfasından bir yüklemeyi başlatabilirsiniz](/windows/msix/app-installer/installing-windows10-apps-web). MDM 'nin LOB uygulaması dağıtım özelliğini kullanarak Microsoft Store veya dışarıdan yüklemeden yüklediğiniz uygulamalar gibi uygulamalar, [imza aracı](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) ile dijital olarak imzalanmalıdır ve uygulama dağıtılmadan önce [imzalamak için kullanılan sertifikaya HoloLens cihaz tarafından güvenilmesi gerekir](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) .

## <a name="requirements"></a>Gereksinimler

### <a name="for-your-devices"></a>Cihazlarınız için:

bu özellik şu anda HoloLens 2 cihazları için Windows Holographic 20h2 derlemeleriyle sunulmaktadır. Bu yöntemi kullanan cihazların [güncelleştirildiğinden](hololens-update-hololens.md)emin olun.

### <a name="for-your-apps"></a>Uygulamalarınız için:

Uygulama yükleyicisi depodan bağımlılıklar kullanacağı için uygulamanızın çözüm yapılandırması **ana** veya **Sürüm** olmalıdır. [Uygulama paketleri oluşturma](/windows/msix/app-installer/create-appinstallerfile-vs)hakkında daha fazla bilgi için bkz..

Bu yöntem aracılığıyla yüklenen uygulamaların dijital olarak imzalanması gerekir. Uygulamayı imzalamak için bir sertifika kullanmanız gerekir. [MS GÜVENILEN CA listesinden](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)bir sertifika alabilirsiniz, bu durumda herhangi bir ek eylem gerçekleştirmeniz gerekmez. Ya da kendi sertifikanızı imzalayabilirsiniz, ancak sertifikanın cihaza itilmesi gerekecektir.

- [Imza aracını kullanarak](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) uygulamaları imzalama.

**Sertifika seçenekleri:**

- [MS güvenilen CA listesi](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Bir sertifika dağıtım yöntemi seçin.**

- [Sağlama paketleri](hololens-provisioning.md) , yerel cihazlara uygulanabilir.
- MDM, [cihaz yapılandırmalarına sahip sertifikalar uygulamak](/mem/intune/protect/certificates-configure)için kullanılabilir.
- Cihaz [Sertifika Yöneticisi](certificate-manager.md)' ni kullanın.

## <a name="installation-method"></a>Yükleme yöntemi

1. Cihazınızın yönetilen olarak değerlendirilmediğini denetleyin.
1. HoloLens 2 cihazınızın açık olup olmadığını ve oturum açtığınızdan emin olun.
1. bilgisayarınızda özel uygulamanıza gidin ve app. appxpaketi ' ni devicename\ınternal Depolama \downloadcopy dizinine kopyalayın.
    Dosyanızı kopyalamayı tamamladıktan sonra cihazınızın bağlantısını kesebilir ve yüklemeyi daha sonra tamamlayabiliriz.
1. HoloLens 2 cihazınızdan **başlat menüsünü** açın, **tüm uygulamalar** ' ı seçin ve **dosya gezgini** uygulamasını başlatın.
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
1. [Web sayfasından yüklemeyi etkinleştirmek için bu adımları](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)izleyin.

### <a name="end-user-experience"></a>Son Kullanıcı deneyimi:

1. Kullanıcı, yukarıda daha önce seçilmiş olan bir yöntemi kullanarak cihaza sertifikayı alır ve kurar.
1. Kullanıcı, yukarıdaki adımdan oluşturulan URL 'YI ziyaret ettiğinde.

Uygulama artık cihaza yüklenir. uygulamayı bulmak için **Başlat menüsü** açın ve uygulamanızı bulmak için **tüm uygulamalar** düğmesini seçin.

- Uygulama yükleyicisi yükleme yöntemiyle ilgili sorun giderme hakkında daha fazla yardım için [uygulama yükleyicisi sorunlarını giderme](/windows/msix/app-installer/troubleshoot-appinstaller-issues)makalesini ziyaret edin.

> [!NOTE]
> Güncelleştirme işlemi sırasında kullanıcı arabirimi desteklenmiyor. Bu nedenle, [Bu sayfadaki](/windows/msix/app-installer/update-settings) ShowPrompt seçeneği ve ilgili seçenekler desteklenmez.

## <a name="sample-apps"></a>Örnek Uygulamalar

Uygulama yükleyicisini kullanılabilir örnek uygulamalarımızdan biriyle deneyin. 
> [!div class="nextstepaction"]
> [Örnek uygulamalar](/windows/mixed-reality/develop/features-and-samples)
