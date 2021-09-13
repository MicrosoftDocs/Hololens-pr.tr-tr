---
title: Dağıtım Kılavuzu – Remote Assist HoloLens büyük ölçekte buluta bağlı HoloLens 2 dağıtımı - Dağıtım
description: Buluta Bağlı ağ üzerinden cihazları HoloLens için kaydı ve Remote Assist'i doğrulamayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033535"
---
# <a name="deploy---cloud-connected-guide"></a>Dağıtma - Buluta bağlı Kılavuz

Artık her şeyi yapılandırmış olduğunuza göre cihazları dağıtmaya hazır oluruz. Ancak, artık kurulumlarınızı ilk kez doğrulamanız gerekir. İlk olarak Azure AD'ye Katılma ve MDM Kaydı işlemi doğrulanmış olmalı ve ardından Bir Remote Assist çağrısının yerleştirilenin doğrulanması gerekir.

## <a name="enrollment-validation"></a>Kayıt Doğrulama

Artık Azure AD ve MDM Kaydı için her şey düzgün yapılandırıldığından, geri kalanı hemen yapılandırıldı. Önceden&#39;bir Wi-Fi bağlantısına ve HoloLens cihazına ve önceden yapılandırılmış AAD kullanıcı hesaplarından biri gerekir.

Cihazınız şu&#39;fabrika ayarları durumuna göre değilse, şimdi cihazına başvuru yapmak [için iyi bir zaman olabilir.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Cihazınız OOBE'ye&#39;ve istemleri takip etmek için etkileşime geçmeniz gerekir. 
1. Kritik istem, bu dosyanın **sahibi Who sorul HoloLens?** İş **veya okul sahibim'i seçin** ve Azure AD hesabı kimlik bilgilerinizi girin.
1. Kayıt başarılı olduğunda&#39;PIN'i ayarlamanız istenir. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Ayrıca Iris taramaları, ses verileri ve telemetri ayarları da istenir ve son&#39;başlat menüsünü açıp OOBE'nin nasıl tamamlanabileceklerini öğrenebilirsiniz.
1. Karma Gerçeklik Giriş'e girdiktan sonra yeni öğrendiği Başlat menüsü **hareketini kullanarak giriş** girişlerini açın.
1. Uygulamanın **Ayarlar** sistem'i **seçin.** Göreceğiniz ilk bilgi&#39;, cihaz adınızdır. Bu, HoloLens 2 cihazınız için HOLOLENS ve ardından altı karakterlik &quot; &quot; bir dize olur.
1. Bu adı not alır.

![HoloLens 2 Ayarlar - Hakkında.](./images/hololens2-settings-about.jpg)

7. Cihazınızın Azure AD'ye başarıyla kaydolarak Ayarlar doğruabilirsiniz. Bu **Ayarlar** Hesaplar **İş veya okula**  ->  **erişim'i seçin.** Bu ekrandan, &quot; Azure AD'de _adofAAD'ye_ bağlandı ifadesini görerek&#39;kaydolarak doğruabilirsiniz. kullanıcı adınız @ _nameofAAD .onmicrosoft.com._ &quot;


Cihazın Azure AD'ye Katılmış olduğunu doğrulamak için Azure Active Directory cihazlardan [Azure portal](https://portal.azure.com/#home)Azure Active Directory Cihazlar ve cihaz  ->    ->    ->  adını arayabiliriz. Cihazın&#39;bir parçası olduğunu görebilir ve Azure Active Directory.


![Azure Active Directory - Cihaz.](./images/aad-enrollment.png)

Daha&#39;yönetim merkezinde oturum Microsoft Endpoint Manager [gerekir.](https://endpoint.microsoft.com/#home) Oturum açma ve **Cihazlar'ı ve** ardından Tüm **cihazlar'ı seçin.** Buradan cihazınızın adını HoloLens&#39;arayabilirsiniz. Intune'da listelenmiş HoloLens görüyor olması gerekir.

![Intune - Cihaz.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Remote Assist Çağrı Doğrulaması

Cihazınızın&#39;hem AAD hem de MDM'nize kayıtlı olduğunu doğruladıktan sonra,&#39;Bir test Remote Assist çağrısı yapmak için zaman vardır. Bu doğrulama için&#39;için HoloLens cihazına ve Windows 10 bilgisayar için ikinci bir Azure AD kullanıcı hesabına sahip olmak gerekir.

Bu doğrulama adımı, son doğrulama adımını daha önce tamamlamış olduğunu ve cihazınızın kayıtlı olduğunu ve Azure AD kullanıcınız cihazda olduğunu varsayacak.


1. Bilgisayarınızda henüz yüklü Microsoft Teams, buradan Teams [indirebilirsiniz.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Oturum Teams oturum asanızdan ikinci Azure AD kullanıcı hesabını kullanarak oturum HoloLens. Bilgisayarınızda oturum olduktan sonra çağrıyı almaya hazır olursınız.
3. Oturum HoloLens ve oturum açın.
4. Remote Assist uygulamasını başlatmak için Başlat Menüsünü **açın ve Remote** **Assist'i seçin.** Remote Assist yalnızca bir gelen kutusu uygulaması olarak paketlenmiş değil aynı zamanda HoloLens 2.&#39;menüsüne sabitlenmiş durumdadır. Bir olayda,&#39;için sabitlenmiş Başlat menüsü ve ardından **Tüm uygulamalar** listesini açın.
5. Remote Assist başladıktan sonra SSO aracılığıyla cihazın kullanıcılarını [tanımlaması ve](/azure/active-directory/manage-apps/what-is-single-sign-on) uygulamada oturum açması gerekir.
6. Uygulamanın içinde **Ara'yi seçin** ve pc'de ikinci kullanıcı için arama yapabilirsiniz. Çağrıyı başlatmak için kullanıcı seçin.
7. Çağrıyı bilgisayarınızdan yanıtla.

Tebrikler,&#39;ve uzaktan yardım çağrınıza bağlandınız. Aşağıdakiler gibi belirli uzaktan yardım özelliklerini deneyin:

- [Ek açıklamaların inking'i](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Bir dosyayı paylaşma ve karma gerçeklikte görüntüleme](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Başka bir uygulama için HoloLens al](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Bakım](hololens2-cloud-connected-maintain.md)