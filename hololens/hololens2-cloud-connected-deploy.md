---
title: dağıtım kılavuzu – buluta bağlı HoloLens 2 dağıtım, uzaktan yardım dağıtımı ile ölçeklendirerek
description: bir buluta bağlı ağ üzerinden HoloLens cihazları için kayıt ve uzaktan yardım doğrulaması yapmayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635186"
---
# <a name="deploy---cloud-connected-guide"></a>Dağıtım-buluta bağlı Kılavuzu

Her şeyi yapılandırdığınıza göre, cihazları dağıtmaya hazır olmanız gerekir. Ancak, şimdi kurulumunu doğrulamanız gerekir. İlk olarak Azure AD JOIN ve MDM kayıt işleminin doğrulanması ve ardından bir uzaktan yardım çağrısının yerleştirilebileceğini doğrulamak gerekir.

## <a name="enrollment-validation"></a>Kayıt doğrulama

Artık her şey Azure AD ve MDM kaydı için düzgün şekilde yapılandırıldığından, Rest artık bir snap olmalıdır. &#39;, Wi-Fi bir bağlantı ve HoloLens cihazının yanı sıra daha önce yapılandırılmış AAD kullanıcı hesaplarından biri gerekir.

Cihazınız şu anda bir fabrika ayarları durumunda oturur&#39;, [cihazı](/hololens/hololens-recovery#clean-reflash-the-device)yeniden oluşturmak için iyi bir zaman olabilir.

1. Cihazınız OOBE 'de olduktan sonra, etkileşime başlamanız ve istemlerin takip etmeniz&#39;gerekir. 
1. **bu HoloLens sahip Who** sorulduğunda kritik istem ne olur? **Çalışmalarımı veya okulumu** seçin ve Azure AD hesabınızın kimlik bilgilerini girin.
1. Kayıt başarılı olduğunda, bir PIN ayarlamanız istenir&#39;. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Ayrıca, Iris taramaları, ses verileri ve telemetri ayarları için de istenir ve son olarak, Başlat menüsünü açmayı ve OOBE 'yi tamamlamayı öğrenebilirsiniz&#39;.
1. karma gerçeklik evine girdikten sonra, yeni öğrendiğiniz **başlangıç hareketini** kullanarak Başlat menüsü açın.
1. **Ayarlar** uygulamayı seçip sistem ' i seçin **.** &#39;, HoloLens 2 cihazınız, daha &quot; &quot; sonra altı karakterli bir dize olacak şekilde, 2 cihazınız için cihazınızın adı görürsünüz.
1. Bu adı bir yere göz atın.

![HoloLens 2 Ayarlar-hakkında](./images/hololens2-settings-about.jpg)

7. cihazınızın Ayarlar uygulamasında Azure AD 'ye başarıyla kaydedildiğini doğrulayabilirsiniz. **Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yi seçin. Bu ekrandan, &quot; _Nameofaad_&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz. _YourUserName_ @ _nameofaad_. onmicrosoft.com ile bağlandı &quot; .


cihazın Azure AD 'ye katılmış olduğunu doğrulamak için, [Azure portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **cihazlarındaki** Azure Active Directory denetleyebilir  ->  ve cihaz adında arama yapabilirsiniz. &#39;, cihazın Azure Active Directory bir parçası olduğunu görebileceksiniz.


![Azure Active Directory-cihaz](./images/aad-enrollment.png)

daha sonra, [Microsoft Endpoint Manager yönetim merkezinde](https://endpoint.microsoft.com/#home)&#39;ll 'nin oturum açması gerekir. Oturum açın ve **cihazlar** ' ın ardından **tüm cihazlar**' ı seçin. buradan HoloLens cihazınızda&#39;adına arama yapabilirsiniz. HoloLens ıntune 'da listelenmiş olarak görebilmeniz gerekir.

![Intune-cihaz](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Uzaktan Yardım çağrı doğrulaması

Cihazınızın hem AAD hem de MDM 'nize kaydolduğunu&#39;ve bir test uzaktan yardım çağrısını yerleştirmek için bir süre&#39;. bu doğrulama için, HoloLens cihazının ve bir Windows 10 bilgisayarın yanı sıra bilgisayar için ikinci bir Azure AD kullanıcı hesabına sahip olmanız&#39;.

Bu doğrulama adımı, son doğrulama adımını daha önce tamamlamış olduğunu ve cihazınızın kaydolduğunu ve Azure AD kullanıcılarınızın cihazda olduğunu varsayacaktır.


1. bilgisayarınızda zaten yüklü Microsoft Teams yoksa, [Teams buradan indirebilirsiniz](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. ikinci Azure AD kullanıcı hesabını, HoloLens oturum açmış olandan daha önce Teams oturum açın. Bilgisayarınızda oturum açtıktan sonra, aramayı almaya hazırız.
3. HoloLens açın ve oturum açın.
4. Uzaktan Yardım uygulamasını başlatmak için **Başlat menüsünü** açın ve **Uzaktan Yardım**' ı seçin. uzaktan yardım yalnızca bir gelen kutusu uygulaması olarak paketlenmiştir, ancak HoloLens 2&#39;s başlat menüsüne sabitlenmiş. bir olayda, Başlat menüsü sabitlenmiş olduğunu görmedim&#39;, ardından aramak için **tüm uygulamalar** listesini açın.
5. Uzaktan Yardım başladıktan sonra, [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) aracılığıyla cihazın kullanıcısını tanımlamalıdır ve uygulamada oturum açmanız gerekir.
6. Uygulama içinden **Ara** ' yı SEÇIN ve bilgisayarda ikinci Kullanıcı için arama yapın. Çağrıyı başlatacak kullanıcıyı seçin.
7. Bilgisayarınızdan aramayı yanıtlayın.

Tebrikler, başarıyla bağlandınız ve Uzaktan Yardım çağrından&#39;. Şunu kullanarak belirli uzaktan yardım özelliklerini denediğinizden emin olun:

- [Mürekkep ek açıklamaları](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Karma Gerçeklik 'te dosya ve Görünüm paylaşma](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [başka bir HoloLens uygulamasında yardım alın](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım-koru](hololens2-cloud-connected-maintain.md)