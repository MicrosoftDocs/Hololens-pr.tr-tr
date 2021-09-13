---
title: HoloLens 2. Uygulama Yükleyicisi aracılığıyla uygulamaları yan yükleme ve yükleme
description: Uygulama yükleyicisi ve kullanıcı arabirimi aracılığıyla uygulama yükleme ve yükleme ile uygulama yükleme ve sorunlarını giderme hakkında bilgi edinin.
keywords: uygulama yönetimi, uygulama, hololens, uygulama yükleyicisi
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033068"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Uygulama Yükleyicisi aracılığıyla HoloLens 2.Uygulama Yükleyicisi

> [!NOTE]
> Bu özellik Holographic sürüm [Windows 20H2 – Aralık 2020 Güncelleştirmesinde kullanılabilir yapıldı.](hololens-release-notes.md) Cihazınızın bu özelliği [kullanmak için](hololens-update-hololens.md) güncelleştirilmiş olduğundan emin olun.

Uygulamaları 2 **cihaza daha sorunsuz Uygulama Yükleyicisi için** yeni bir özellik (HoloLens) ekledik. Özellik, varsayılan **olarak, unmanaged cihazları için açık olur.** Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.  

Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:

- MDM [Kayıtlı](hololens-enroll-mdm.md)
- Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)
- Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir

Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.  Appx Paketi'Microsoft Edge VEYA USB üzerinden) cihazınıza indirin ve yüklemenin Dosya Gezgini appx paketine gidin.  Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web) MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğu gibi, uygulamaların [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) da İmza [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce imzalamak için kullanılan sertifikanın HoloLens cihazı tarafından güvenilir olması gerekir.

## <a name="requirements"></a>Gereksinimler

### <a name="for-your-devices"></a>Cihazlarınız için:

Bu özellik şu anda 2 Windows için Holographic 20H2 derlemeleri HoloLens kullanılabilir. Bu yöntemi kullanan tüm cihazların güncelleştirilmiş olduğundan emin [olun.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Uygulamalarınız için:

Uygulamanın depodan bağımlılıkları **kullanmayacak** olması **nedeniyle,** Uygulama Yükleyicisi Çözüm Yapılandırması Ana Sürüm veya Yayın olabilir. Uygulama paketleri oluşturma [hakkında daha fazla bilgi için bkz.](/windows/msix/app-installer/create-appinstallerfile-vs).

Bu yöntem aracılığıyla yüklenmiş olan uygulamaların dijital olarak imzaya sahip olması gerekir. Uygulamayı imzalamak için bir sertifika kullansanız gerekir. MS Güvenilen CA Listesinden bir [sertifika alır ve](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)bu durumda ek işlem yapmak zorunda olmaznız. Öte yandan kendi sertifikanızı da imzalarsanız bu sertifikanın cihaza da itilmiş olması gerekir.

- İmza Aracı'nı [kullanarak uygulamaları imzalama.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Sertifika seçenekleri:**

- [MS Güvenilen CA Listesi](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Bir sertifika dağıtım yöntemi seçin.**

- [Sağlama Paketleri](hololens-provisioning.md) yerel cihazlara uygulanabilir.
- MDM, cihaz [yapılandırmaları ile sertifikaları uygulamak için kullanılabilir.](/mem/intune/protect/certificates-configure)
- Cihazda Sertifika [Yöneticisi'ni kullanın.](certificate-manager.md)

## <a name="installation-method"></a>Yükleme yöntemi

1. Cihazınızın yönetilen olarak kabul olmadığını kontrol edin.
1. HoloLens 2 cihazınızın açık ve oturum açık olduğunu kontrol edin.
1. Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads klasörüne kopyalayın.
    Dosyanızı kopyalamayı bitirdikten sonra cihazınızın bağlantısını keserek yüklemeyi daha sonra tamamabilirsiniz.
1. HoloLens 2 cihazınızın Başlat **Menüsünü açın,** **Tüm uygulamalar'ı** seçin ve **Dosya Gezgini** açın.
1. İndirilenler klasörüne gidin. Uygulamanın sol panelinde Önce Bu cihaz'ı seçmeniz **ve** ardından İndirilenler'e gitmek zorundayabilirsiniz.
1. yourapp.appxbundle dosyasını seçin.
1. Uygulama Yükleyicisi başlatacak. Uygulamayı **yüklemek** için Yükle düğmesini seçin.

Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.

![Uygulama Yükleyicisi aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Yükleme sorunlarını giderme

Uygulamanız yüklenemediyse, sorun gidermek için aşağıdakilere göz açın:

- Uygulamanız bir Ana veya Yayın derlemesi.
- Cihazınız, bu özelliğin kullanılabilir olduğu bir derlemeye güncelleştirilir.
- [İnternet'e bağlandınız.](hololens-network.md)
- Uç [noktalarınız Microsoft Store](hololens-offline.md) yapılandırılmıştır.  

## <a name="web-installer"></a>Web Yükleyicisi

Kullanıcılar bir uygulamayı doğrudan bir web sunucusundan yükleyebilir. Bu akış, kolay Uygulama Yükleyicisi yükleme dağıtım yöntemiyle birlikte uygulamanın kullanımını kullanır.

### <a name="how-to-set-up-web-install"></a>Web yüklemesini ayarlama:

1. Uygulamanın yüklemek için doğru yapılandırıldığından emin olun.
1. Bir [web sayfasından yüklemeyi etkinleştirmek için bu adımları izleyin.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Son kullanıcı deneyimi:

1. Kullanıcı yukarıda daha önce seçilen bir yöntemi kullanarak sertifikayı alır ve cihaza yükleyebilir.
1. Kullanıcı yukarıdaki adımdan oluşturulan URL'yi ziyaret ediyor.

Uygulama artık cihaza yüklenir. Uygulamayı bulmak için Başlat menüsü **açın** ve Tüm uygulamalar **düğmesini** seçin.

- Uygulama yükleyicisi yükleme yönteminin sorunlarını giderme hakkında daha fazla yardım için uygulama [yükleyicisi sorunlarını giderme'ye bakın.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Güncelleştirme işlemi sırasında kullanıcı arabirimi desteklenmiyor. Bu nedenle bu sayfada GösterPrompt [seçeneği](/windows/msix/app-installer/update-settings) ve ilgili seçenekler desteklenmiyor.

## <a name="sample-apps"></a>Örnek Uygulamalar

Kullanılabilir örnek Uygulama Yükleyicisi uygulamalarımızın birini deneyin. 
> [!div class="nextstepaction"]
> [Örnek uygulamalar](/windows/mixed-reality/develop/features-and-samples)
