---
title: Dağıtım Kılavuzu – bulut bağlantılı HoloLens 2 dağıtımı, uzaktan yardım dağıtımı ile ölçeklendirerek
description: Bir bulut bağlantılı ağı üzerinden HoloLens cihazları için kaydı ve uzaktan yardımı doğrulamayı öğrenin.
keywords: HoloLens, yönetim, bulut bağlantılı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379118"
---
# <a name="deploy---cloud-connected-guide"></a>Dağıtım-buluta bağlı Kılavuzu

Her şeyi yapılandırdığınıza göre, cihazları dağıtmaya hazır olmanız gerekir. Ancak, şimdi kurulumunu doğrulamanız gerekir. İlk olarak Azure AD JOIN ve MDM kayıt işleminin doğrulanması ve ardından bir uzaktan yardım çağrısının yerleştirilebileceğini doğrulamak gerekir.

## <a name="enrollment-validation"></a>Kayıt doğrulama

Artık her şey Azure AD ve MDM kaydı için düzgün şekilde yapılandırıldığından, Rest artık bir snap olmalıdır. &#39;, daha önce yapılandırılmış AAD Kullanıcı hesaplarından biri olan Wi-Fi bağlantısına ve HoloLens cihazına ihtiyacınız vardır.

Cihazınız şu anda bir fabrika ayarları durumunda oturur&#39;, [cihazı](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)yeniden oluşturmak için iyi bir zaman olabilir.

1. Cihazınız OOBE 'de olduktan sonra, etkileşime başlamanız ve istemlerin takip etmeniz&#39;gerekir. 
1. Kritik istem, **Bu HoloLens 'e sahip** olduğunuz sorulduğunda olur mu? **Çalışmalarımı veya okulumu** seçin ve Azure AD hesabınızın kimlik bilgilerini girin.
1. Kayıt başarılı olduğunda, bir PIN ayarlamanız istenir&#39;. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Ayrıca, Iris taramaları, ses verileri ve telemetri ayarları için de istenir ve son olarak, Başlat menüsünü açmayı ve OOBE 'yi tamamlamayı öğrenebilirsiniz&#39;.
1. Karma Gerçeklik evine girdikten sonra, yeni öğrendiğiniz **Başlangıç hareketini** kullanarak Başlat menüsünü açın.
1. **Ayarlar** uygulamasını seçin ve sistem ' i seçin **.** &#39;ll 'nin ilk bilgileri, HoloLens 2 cihazınızı izleyen, daha &quot; &quot; sonra altı karakterli bir dize olacak şekilde, cihazınızın adıdır.
1. Bu adı bir yere göz atın.

![HoloLens 2 ayarları-hakkında](./images/hololens2-settings-about.jpg)

7. Cihazınızın Azure AD 'ye ayarlar uygulaması içinde başarıyla kaydedildiğini doğrulayabilirsiniz. **Ayarlar** listesinden **Hesap**  ->  **erişimi iş veya okul**' yi seçin. Bu ekrandan, &quot; _Nameofaad_&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz. _YourUserName_ @ _nameofaad_. onmicrosoft.com ile bağlandı &quot; .


Cihazın Azure AD 'ye katılmış olduğunu doğrulamak için, [Azure Portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **cihazlarındaki** Azure Active Directory denetleyebilir  ->  ve cihaz adında arama yapabilirsiniz. &#39;, cihazın Azure Active Directory bir parçası olduğunu görebileceksiniz.


![Azure Active Directory-cihaz](./images/aad-enrollment.png)

Daha sonra, [Microsoft Endpoint Manager Yönetim merkezinde](https://endpoint.microsoft.com/#home)oturum açmanız&#39;. Oturum açın ve **cihazlar** ' ın ardından **tüm cihazlar**' ı seçin. Buradan, HoloLens cihazınızda&#39;s adını arayabilirsiniz. HoloLens 'nizi Intune 'da listelenmiş olarak görmeniz gerekir.

![Intune-cihaz](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Uzaktan Yardım çağrı doğrulaması

Cihazınızın hem AAD hem de MDM 'nize kaydolduğunu&#39;ve bir test uzaktan yardım çağrısını yerleştirmek için bir süre&#39;. Bu doğrulama için, bir BILGISAYAR için ikinci bir Azure AD Kullanıcı hesabının yanı sıra HoloLens cihazı ve bir Windows 10 PC 'ye sahip olmanız&#39;.

Bu doğrulama adımı, son doğrulama adımını daha önce tamamlamış olduğunu ve cihazınızın kaydolduğunu ve Azure AD kullanıcılarınızın cihazda olduğunu varsayacaktır.


1. Bilgisayarınızda Microsoft ekipleri zaten yüklü değilse, [takımları buradan indirebilirsiniz](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. İkinci bir Azure AD Kullanıcı hesabını, HoloLens 'larınızda oturum açmış olandan daha fazla kullanarak ekiplerde oturum açın. Bilgisayarınızda oturum açtıktan sonra, aramayı almaya hazırız.
3. HoloLens 'larınızın kilidini açın ve oturum açın.
4. Uzaktan Yardım uygulamasını başlatmak için **Başlat menüsünü** açın ve **Uzaktan Yardım**' ı seçin. Uzaktan Yardım yalnızca bir gelen kutusu uygulaması olarak paketlenmiş ancak HoloLens 2&#39;s Başlat menüsüne sabitlenmiş. Bir olayda, Başlat menüsüne sabitlenmiş olduğunu görmedim ve sonra aramak için **tüm uygulamalar** listesini açmanız&#39;.
5. Uzaktan Yardım başladıktan sonra, [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) aracılığıyla cihazın kullanıcısını tanımlamalıdır ve uygulamada oturum açmanız gerekir.
6. Uygulama içinden **Ara** ' yı SEÇIN ve bilgisayarda ikinci Kullanıcı için arama yapın. Çağrıyı başlatacak kullanıcıyı seçin.
7. Bilgisayarınızdan aramayı yanıtlayın.

Tebrikler, başarıyla bağlandınız ve Uzaktan Yardım çağrından&#39;. Şunu kullanarak belirli uzaktan yardım özelliklerini denediğinizden emin olun:

- [Mürekkep ek açıklamaları](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Karma Gerçeklik 'te dosya ve Görünüm paylaşma](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Başka bir HoloLens uygulamasında yardım alın](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım-koru](hololens2-cloud-connected-maintain.md)