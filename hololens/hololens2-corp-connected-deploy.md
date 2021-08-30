---
title: Dağıtım Kılavuzu – Dynamics 365 kılavuzları HoloLens 2 kurumsal bağlantılı bağlantı - Dağıtma
description: Dynamics 365 Kılavuzları ile HoloLens bağlı ağ üzerinden 2 cihaz dağıtmayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189690"
---
# <a name="deploy---corporate-connected-guide"></a>Dağıtma - Kurumsal Bağlantılı Kılavuz

Her dağıtımın önemli bir kısmı, son kullanıcı için sorunsuz bir deneyim sağlamak amacıyla dağıtımınızı kendiniz test etmeden önce düzgün bir şekilde ayarlanmış olmasını sağlamaktır.

Wi-Fi sertifikasını MDM aracılığıyla dağıtıyor olduğundan, başlangıçta HoloLens'yi ayarlamamız ve açık Wi-Fi ağına veya sertifika gerektirmeyen bir ağa cihaz kaydetmemiz gerekir. Cihaz HoloLens OOBE ve Kayıtlı tamamlandıktan sonra, cihaz daha önce yapılandırılan ağ sertifikasını ve LOB'u alacak ve her ikisinin de cihaz tarafından alınmakta olduğunu doğrulayabileceksiniz.

Daha sonra hem yazma hem de test kılavuzu çalıştırabilirsiniz.

## <a name="enrollment-validation"></a>Kayıt Doğrulama

Artık Azure AD ve MDM Kaydı için her şey düzgün yapılandırıldığından, geri kalanı hemen yapılandırıldı. Önceden yapılandırılmış Azure AD kullanıcı Wi-Fi bir HoloLens bağlantısına ve HoloLens cihazına ihtiyacınız vardır.

Cihazınız şu anda fabrika ayarları durumuna göre değilse, şimdi cihaza başvuru yapmak [için iyi bir zaman olabilir.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Cihazınız OOBE'ye başladıktan sonra etkileşime geçmeye ve istemleri takip edin.

2. Bağlan Wi-Fi'Wi-Fi katılmasını gerektirmeyen açık bir ağ bağlantısına bağlanın. Bu, cihazın ilk kurulumdan sonra kuruluşun Wi-Fi indirmesine olanak sağlar.

3. Kritik istem, bu dosyanın **sahibi Who sorul HoloLens?** İş **veya okul sahibim'i seçin** ve Azure AD hesabı kimlik bilgilerinizi girin.

4. Kayıt başarılı olduğunda bir PIN'i ayarlamanız istenir. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Iris taramaları, ses verileri ve telemetri ayarları da istenecek ve son olarak başlat menüsünü açıp OOBE'nin nasıl tamamlanabileceklerini öğrenebilirsiniz.

5. Karma Gerçeklik Giriş'e girdiktan sonra, öğrendiği Başlat menüsü **başlat hareketini kullanarak** giriş girişlerini açın.

6. Uygulamanın **Ayarlar** Sistem'i **seçin.** Göreceğiniz ilk bilgi Cihaz adınızdır. Bu bilgiler, HoloLens 2 cihazınız için HOLOLENS ve ardından altı karakter dizesi &quot; &quot; olacak.

7. Bu adı not alır.

    ![HoloLens 2 Ayarlar ekran.](./images/hololens2-settings-about.jpg)

8. Cihazınızın Azure AD'ye başarıyla katıldığını doğrulayın. İki yol vardır:

    1.  Uygulama Ayarlar. Bu **Ayarlar** Hesaplar **İş veya okula**  ->  **erişim'i seçin.** Bu ekrandan, Azure AD'nin adofAAD adına bağlandı ifadesini &quot; görerek&#39;şekilde kaydolabilirsiniz. tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı. Bu işlem, cihazınızın Azure AD'de&#39;olduğunu doğrular.

    1. [Azure portal.](https://portal.azure.com/#home) Cihazlar **Azure Active Directory**  ->    ->  **cihazlar'a gidin** ve cihaz adını arayın. Birleştirme Türü altında 'Azure AD'ye Katılmış' olarak gösterir.
        ![Azure AD'de Birleştirme Türünü doğrulayın.](./images/hololens2-devices-all-devices.png)

9. Cihazınızın MDM'ye kayıtlı olduğunu doğrulayın. İki yol vardır:

    1. Bu **Ayarlar** Hesaplar İş **veya okula**  ->  **erişim'i seçin.** Bu ekrandan, Azure AD'nin adofAAD adına bağlandı ifadesini &quot; görerek&#39;şekilde kaydolabilirsiniz. tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı. Bu Access iş veya okul hesabından Azure &quot; AD'nin adofAAD&#39;'yi seçin. Bağlanarak yourusername@nameofAAD.onmicrosoft.com &quot; bağlandıktan sonra **Bilgi düğmesini** seçin.

    1. [Microsoft Endpoint Manager Yönetim Merkezi'ni seçin.](https://endpoint.microsoft.com/#home) Oturum açma ve **Cihazlar'ı ve** ardından Tüm **cihazlar'ı seçin.** Buradan, cihazınızın adını HoloLens&#39;arayabilirsiniz. Intune'da listelenmiş HoloLens görüyor olması gerekir.

        ![Azure AD'de Intune tarafından yönetileni doğrulayın.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi doğrulama

Şu an için cihazın sertifikayı almış Wi-Fi gerekir. En basit doğrulama, sertifikayı hangi sertifikayı Wi-Fi bağlantınıza&#39;denemedir. Ayarlar **uygulamasını** açın ve Ağ **&amp;**  ->  **İnterneti Wi-Fi'a** gidin ve Wi-fi bağlantısını seçin. Bağlandıktan sonra Microsoft Edge açın ve bir web sitesine gidebilirsiniz.

Cihazda sertifikayı aldığınızı onaylamak için Sertifika Yöneticisi'ni [kullanabilirsiniz.](/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB uygulaması yükleme doğrulama

Yönetilen bir uygulamanın yükleme ilerlemesini görmek için uygulamanın yüklü olup Ayarlar. Lob uygulamasını grubumuz için gerekli bir yükleme olarak yapılandırarak, HoloLens'i atanan gruptaki bir kullanıcıya kaydettikten sonra uygulama otomatik olarak HoloLens.

Dosyayı açın ve **Başlat menüsü'yi Tüm uygulamalar.** Sahip olduğu uygulama sayısına bağlı olarak sayfa yukarı veya sayfa aşağı **düğmelerini** **kullanabilirsiniz.**

Uygulamanın cihaza yüklemesini doğrulamak için **Ayarlar** Hesapları İş veya okula erişim yoluyla bunu yapabiliriz; hesabı ve ardından Bilgi düğmesini seçin ve aşağı kaydırarak  ->    ->  MDM'den  cihaza uygulanan farklı yapılandırmaları ve uygulamaları görüntüebilirsiniz.

Intune'dan yüklemeyi doğrulamak [için, MEM portalı](https://endpoint.microsoft.com/#home)  ->  **Uygulamalar** -> Tüm **uygulamalar**  -> *TheNameOfApp Cihazınız* yükleme durumu  ->  **sayfasına** gidin.

Daha fazla bilgi: HoloLens için [Intune Uygulama Dağıtımı](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 Kılavuzlarını Doğrulama

Kılavuzlar uygulaması için HoloLens, yazma ve çalıştırma modları vardır. Çalıştırmadan önce bir kılavuz yazmayı bitirmeniz gerekir.

### <a name="authoring-the-guide"></a>Kılavuzu Yazma

Bu hızlı doğrulama için çok fazla şey yapmaya gerek yok. Bilgisayarınızda hazırlığınız olan kılavuzu seçmeniz gerekir. Kılavuzu [sabitleniz gerekir.](/dynamics365/mixed-reality/guides/hololens-app-anchor)Hızlı bir doğrulama için holografik sabit noktası kullanabilirsiniz. Daha sonra, adımlarınızı [ve modellerinizi yere sizin de yerniz.](/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> Pc'de **oturum açmanız** ve oturum açmanız için Yazma rolüne ve HoloLens. İşleç rolü salt okunur bir roldür ve bilgisayar uygulamasına erişimi yoktur.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Kılavuzu Çalıştırma

Hologramlarınız tamam olduktan sonra kılavuzu çalıştırmayı test edin. 
- **İşleç modunu seçin**
- Kılavuzun adımlarına tıklayın.

Kılavuzun nasıl çalıştırıla ilgili daha ayrıntılı rehberlik için şu kaynaklara göz atabilirsiniz:

[Dynamics 365 Kılavuzlarında kılavuzu çalıştırmaya genel bakış](/dynamics365/mixed-reality/guides/operator-overview)

[Dynamics 365 Kılavuzlarında operatör olarak Adım kartına yönelin](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Bakım](hololens2-corp-connected-maintain.md)
