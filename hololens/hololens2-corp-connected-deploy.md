---
title: Dağıtım Kılavuzu – Dynamics 365 Kılavuzları ile kurumsal bağlantılı HoloLens 2 - Dağıtım
description: Dynamics 365 Kılavuzları ile kurumsal bir Bağlı ağ üzerinden HoloLens 2 cihazlarının dağıtımlarını ayarlamayı öğrenin.
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379017"
---
# <a name="deploy---corporate-connected-guide"></a>Dağıtma - Kurumsal Bağlantılı Kılavuz

Her dağıtımın önemli bir kısmı, son kullanıcı için sorunsuz bir deneyim sağlamak amacıyla dağıtımınızı kendiniz test etmeden önce düzgün bir şekilde ayarlanmış olmasını sağlamaktır.

Wi-Fi sertifikasını MDM aracılığıyla dağıtıyor olduğundan, başlangıçta HoloLens'i ayarlamamız ve açık bir Wi-Fi ağına veya sertifika gerektirmeyen bir ağa cihaz kaydetmemiz gerekir. HoloLens OOBE'yi ve Kaydol'u tamamlandıktan sonra cihaz daha önce yapılandırılan ağ sertifikasını ve LOB'u alacak ve her ikisinin de cihaz tarafından alınmakta olduğunu doğrulayabileceksiniz.

Daha sonra hem yazma hem de test kılavuzu çalıştırabilirsiniz.

## <a name="enrollment-validation"></a>Kayıt Doğrulama

Artık Azure AD ve MDM Kaydı için her şey düzgün yapılandırıldığından, geri kalanı hemen yapılandırıldı. Daha önce yapılandırılan Azure AD Wi-Fi ve HoloLens cihazı için bir sanal ağ bağlantısına ihtiyacınız vardır.

Cihazınız şu anda fabrika ayarları durumda değilse, şimdi cihaza ters eğik çizgi [uygulamanın zamanı geldi.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Cihazınız OOBE'ye başladıktan sonra etkileşime geçmeye ve istemleri takip edin.

2. Wi-Fi'Wi-Fi sertifikaların katılmasını gerektirmeyen açık bir ağ bağlantısına bağlanın. Bu, cihazın ilk kurulumdan sonra kuruluşun Wi-Fi sertifikayı indirmesine olanak sağlar.

3. Bu **HoloLens'in sahibi kim? soruldiğinde kritik istem olur.** İş **veya okul sahibim'i seçin** ve Azure AD hesabı kimlik bilgilerinizi girin.

4. Kayıt başarılı olduğunda bir PIN'i ayarlamanız istenir. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Iris taramaları, ses verileri ve telemetri ayarları da istenecek ve son olarak başlat menüsünü açıp OOBE'nin nasıl tamamlanabileceklerini öğrenebilirsiniz.

5. Karma Gerçeklik Giriş'e girdiktan sonra, öğrendiği Başlat menüsü **Başlat hareketini kullanarak** giriş girişlerini açın.

6. Ayarlar uygulamasını **ve** ardından Sistem'i **seçin.** Göreceğiniz ilk bilgi, HoloLens 2 cihazınız için HOLOLENS ve ardından altı karakter dizesi olacak Cihaz &quot; &quot; adınızdır.

7. Bu adı not alır.

    ![HoloLens 2 Ayarlar ekranı](./images/hololens2-settings-about.jpg)

8. Cihazınızın Azure AD'ye başarıyla katıldığını doğrulayın. İki yol vardır:

    1.  Ayarlar uygulaması. **Ayarlar'dan** Hesaplar **İş veya okula**  ->  **erişim'i seçin.** Bu ekrandan, Azure AD'de adofAAD adına bağlandı'yı &quot;&#39;başarılı bir şekilde kaydolarak doğrulayabilirsiniz. tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı. Bu, cihazınızın Azure AD'de&#39;olduğunu doğrular.

    1. [Azure portal.](https://portal.azure.com/#home) Cihazlar **Azure Active Directory**  ->    ->  **cihazlar'a gidin** ve cihaz adını arayın. Birleştirme Türü altında 'Azure AD'ye Katılmış' olarak gösterir.
        ![Azure AD'de Birleştirme Türünü Doğrulama](./images/hololens2-devices-all-devices.png)

9. Cihazınızın MDM'ye kayıtlı olduğunu doğrulayın. İki yol vardır:

    1. **Ayarlar'da** Hesaplar İş **veya**  ->  **okula erişim'i seçin.** Bu ekrandan, Azure AD'de adofAAD adına bağlandı'yı &quot;&#39;başarılı bir şekilde kaydolarak doğrulayabilirsiniz. tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı. Bu Access iş veya okul hesabından Azure &quot; AD'nin adofAAD&#39;'ı seçin. Bağlı olan yourusername@nameofAAD.onmicrosoft.com &quot; ve Bilgi düğmesini **seçin.**

    1. [Microsoft Endpoint Manager Yönetim Merkezi.](https://endpoint.microsoft.com/#home) Oturum açma ve **Cihazlar'ı ve** ardından Tüm **cihazlar'ı seçin.** Buradan HoloLens cihazınızın adını&#39;arayabilirsiniz. HoloLens'inizi Intune'da listelenmiş olarak görüyor olması gerekir.

        ![Azure AD'de Intune tarafından yönetileni doğrulama](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi doğrulama

Şu an için cihazın sertifikayı almış Wi-Fi gerekir. En basit doğrulama, sertifikayı hangi Wi-Fi bağlantınıza&#39;denemedir. Ayarlar uygulamasını **açın** ve Ağ İnterneti **&amp;**  ->  **Wi-Fi'a** gidin ve Wi-fi bağlantısını seçin. Bağlandıktan sonra Microsoft Edge açın ve bir web sitesine gidebilirsiniz.

Cihazda sertifikayı aldığınızı onaylamak için Sertifika Yöneticisi'ni [kullanabilirsiniz.](https://docs.microsoft.com/hololens/certificate-manager)

## <a name="validate-lob-app-install"></a>LOB uygulaması yükleme doğrulama

Yönetilen bir uygulamanın yükleme ilerlemesini görmek için uygulamanın yüklü olup olduğunu görebilir veya Ayarlar'a bakabilirsiniz. Bir LOB uygulamasını grubumuz için gerekli bir yükleme olarak yapılandırarak, HoloLens'i atanan gruba bir kullanıcıyla kaydettikten sonra uygulama otomatik olarak HoloLens'e indirilir.

Dosyayı açın Başlat menüsü seçin **ve** Tüm uygulamalar. Sahip olduğu uygulama sayısına bağlı olarak sayfa yukarı veya sayfa aşağı **düğmelerini** **kullanabilirsiniz.**

Uygulamanın cihaza yüklemesini doğrulamak için Ayarlar Hesapları İş veya okula erişim yoluyla bunu yapabilirsiniz; hesabı ve ardından Bilgi düğmesini seçin ve  ->    ->    MDM'den cihaza uygulanan farklı yapılandırmaları ve uygulamaları görmek için aşağı kaydırın.

Intune'dan yüklemeyi doğrulamak [için, MEM portalı](https://endpoint.microsoft.com/#home)  ->  **Uygulamalar** -> Tüm **uygulamalar**  -> *TheNameOfApp*  ->  **Cihazınız yükleme durumu sayfasına** gidin.

Daha fazla bilgi: [HoloLens için Intune Uygulama Dağıtımı](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 Kılavuzlarını Doğrulama

HoloLens'de Guides uygulaması için yazma ve çalıştırma modları vardır. Çalıştırmadan önce bir kılavuz yazmayı bitirmeniz gerekir.

### <a name="authoring-the-guide"></a>Kılavuzu Yazma

Bu hızlı doğrulama için çok fazla şey yapmaya gerek yok. Bilgisayarınızda hazırlığınız olan kılavuzu seçmeniz gerekir. Kılavuzu [sabitleniz gerekir.](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)Hızlı bir doğrulama için holografik yer bağlantısı kullanabilirsiniz. Daha sonra, adımlarınızı [ve modellerinizi yere sizin de yerniz.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)

>[!NOTE]
> **HoloLens'de** pc'de oturum açma ve yazma için Yazma rolüne ihtiyacınız olacak. İşleç rolü salt okunur bir roldür ve bilgisayar uygulamasına erişimi yoktur.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Kılavuzu Çalıştırma

Hologramlarınız tamam olduktan sonra kılavuzu çalıştırmayı test edin. 
- **İşleç modunu seçin**
- Kılavuzun adımlarına tıklayın.

Kılavuzun nasıl çalıştırıla ilgili daha ayrıntılı rehberlik için şu kaynaklara göz atabilirsiniz:

[Dynamics 365 Kılavuzlarında kılavuzu çalıştırmaya genel bakış](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Dynamics 365 Kılavuzlarında operatör olarak Adım kartına yönelin](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Bakım](hololens2-corp-connected-maintain.md)
