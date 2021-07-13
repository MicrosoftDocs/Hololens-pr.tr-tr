---
title: dağıtım kılavuzu – Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-dağıt
description: Dynamics 365 kılavuzlarıyla kurumsal bağlantılı ağ üzerinden HoloLens 2 cihaz dağıtımlarını ayarlamayı öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637073"
---
# <a name="deploy---corporate-connected-guide"></a>Dağıtım-kurumsal bağlantılı kılavuz

Her dağıtımın önemli bir kısmı, son kullanıcı için sorunsuz bir deneyim sağlamak üzere dağıtımınızı test etmeden önce doğru şekilde ayarlamış olmasını sağlamaktır.

MDM aracılığıyla Wi-Fi sertifikasını dağıtmakta olduğumuz için, başlangıçta, açık bir Wi-Fi ağa veya sertifikayı gerektirmeyen bir ağa HoloLens ve cihaz kaydetmeniz gerekir. HoloLens, OOBE ve kaydolduktan sonra cihaz, daha önce yapılandırılmış olan ağ sertifikasını ve LOB 'u alır ve cihaz tarafından her ikisinin de alındığını doğrulayabilecektir.

Daha sonra, bir test kılavuzunu yazıp çalıştıracağınızı doğrulayabileceksiniz.

## <a name="enrollment-validation"></a>Kayıt doğrulama

Artık her şey Azure AD ve MDM kaydı için düzgün şekilde yapılandırıldığından, Rest artık bir snap olmalıdır. Wi-Fi bağlantıya ve HoloLens cihazına ve daha önce yapılandırılmış Azure AD kullanıcı hesaplarından birine ihtiyacınız vardır.

Cihazınız şu anda bir fabrika ayarları durumunda oturmazsa, [cihazı](/hololens/hololens-recovery#clean-reflash-the-device)yeniden oluşturmak için iyi bir zaman olurdu.

1. Cihazınız OOBE 'olduktan sonra, etkileşime başlamanız ve istemleri takip etmeniz gerekir.

2. Wi-Fi ' a katılması için sertifika gerektirmeyen açık bir Wi-Fi ağa Bağlan. Bu işlem, cihazın ilk kurulumdan sonra kuruluşun Wi-Fi kullanılacak sertifikayı indirmesini sağlar.

3. **bu HoloLens sahip Who** sorulduğunda kritik istem ne olur? **Çalışmalarımı veya okulumu** seçin ve Azure AD hesabınızın kimlik bilgilerini girin.

4. Kayıt başarılı olduğunda, bir PIN ayarlamanız istenir. Bu PIN, bu kullanıcı için bu cihaz için benzersizdir. Ayrıca, Iris taramaları, ses verileri ve telemetri ayarları istenir ve son olarak, Başlat menüsünü açmayı ve OOBE 'yi tamamlamayı öğreneceksiniz.

5. karma gerçeklik ana sayfasına girdikten sonra, yeni öğrendiğiniz **başlangıç hareketini** kullanarak Başlat menüsü açın.

6. **Ayarlar** uygulamayı seçip **sistem**' i seçin. HoloLens 2 cihazınız, daha &quot; &quot; sonra altı karakterli bir dize olmak üzere, sizin için göreceğiniz ilk bilgi parçasıdır.

7. Bu adı bir yere göz atın.

    ![HoloLens 2 Ayarlar ekran](./images/hololens2-settings-about.jpg)

8. Cihazınızın Azure AD 'ye başarıyla katıldığını doğrulayın. İki yol vardır;

    1.  Ayarlar uygulaması. **Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yi seçin. Bu ekrandan, &quot; nameofAAD&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz. İle bağlandı *yourusername@nameofAAD.onmicrosoft.com* . Bu, cihazınızın kuruluşunuza katıldığını doğrular&#39;s Azure AD.

    1. [Azure Portal](https://portal.azure.com/#home). **Azure Active Directory**  ->  **cihazlar**  ->  **tüm cihazlar**' a gidin ve cihaz adında arama yapın. Katılım türü altında, ' Azure AD 'ye katılmış ' olarak gösterilir.
        ![Azure AD 'de JOIN türünü doğrulama](./images/hololens2-devices-all-devices.png)

9. Cihazınızın MDM 'ye kayıtlı olduğunu doğrulayın. İki yol vardır;

    1. **Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yı seçin. Bu ekrandan, &quot; nameofAAD&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz. İle bağlandı *yourusername@nameofAAD.onmicrosoft.com* . Bu Access iş veya okul hesabından, &quot; nameofAAD&#39;s Azure AD ' a bağlı ' yı seçerek. İle bağlandı yourusername@nameofAAD.onmicrosoft.com &quot; ve **bilgi** düğmesini seçin.

    1. [Microsoft Endpoint Manager yönetim merkezi](https://endpoint.microsoft.com/#home). Oturum açın ve  **cihazlar**  ' ın ardından  **tüm cihazlar**' ı seçin. buradan HoloLens cihazınızda&#39;adına arama yapabilirsiniz. HoloLens ıntune 'da listelenmiş olarak görebilmeniz gerekir.

        ![Azure AD 'de Intune tarafından yönetilen doğrulama](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi sertifikası doğrulaması

Artık cihaz Wi-Fi sertifikasını almış olmalıdır. Yapabileceğiniz en basit doğrulama, sertifikayı&#39;aldığınız Wi-Fi bağlantıya bağlanmaya çalışır. **Ayarlar** uygulamasını açın ve **ağ &amp; ınternet**  ->  **Wi-fi** ' a gidin ve Wi-fi bağlantısını seçin. bağlandıktan sonra Microsoft Edge uygulamasını açın ve bir web sitesine gidebileceğiniz onaylayın.

Sertifikayı cihazda aldığınızı onaylamak için, [sertifika yöneticisini](/hololens/certificate-manager)kullanabilirsiniz.

## <a name="validate-lob-app-install"></a>LOB uygulaması yüklemesini doğrula

yönetilen bir uygulamanın yükleme ilerlemesini görmek için, uygulamanın yüklü olup olmadığını görürsünüz veya Ayarlar denetleyin. bir LOB uygulamasını grubumuza gerekli bir yükleme olarak yapılandırarak, HoloLens atanan gruptaki bir kullanıcıyla kaydettikten sonra, uygulama HoloLens otomatik olarak indirilir.

Başlat menüsü açın ve **tüm uygulamalar**' ı seçin. Sahip olduğunuz uygulama sayısına bağlı olarak, **sayfa yukarı** veya **sayfa aşağı** düğmelerini kullanmanız gerekebilir.

uygulamanın cihazda yüklenmesini doğrulamak için, **Ayarlar**  ->  **hesapları**  ->  **işe veya okula erişim** aracılığıyla yapabilirsiniz; hesabı sonra **bilgi** düğmesini seçip, ardından aşağı kaydırarak cihaz MDM 'den cihaza uygulanmış farklı yapılandırma ve uygulamaları görebilirsiniz.

Yüklemeyi Intune 'dan doğrulamak için, [mem portalı](https://endpoint.microsoft.com/#home)  ->  **uygulamalar** -   -> *uygulama*  ->  **cihaz yüklemesi durum** sayfasından > tüm uygulamalar ' a gidin.

Daha fazla bilgi [için bkz. HoloLens Için Intune uygulama dağıtımı](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Dynamics 365 kılavuzlarını doğrulama

HoloLens, yazma ve çalıştırma üzerinde kılavuzlar uygulamasının modları vardır. Kullanmadan önce bir kılavuz yazmayı gerçekleştirmeniz gerekir.

### <a name="authoring-the-guide"></a>Kılavuzu yazma

Bu hızlı doğrulama için çok gerekli değildir. Bilgisayarınızda hazırladığınız Kılavuzu seçmeniz yeterlidir. Hızlı bir doğrulama için [kılavuza bağlantı](/dynamics365/mixed-reality/guides/hololens-app-anchor)oluşturmanız gerekir. bir holographic bağlayıcısını kullanabilirsiniz. Daha sonra, [adımlarınızı ve modellerinizi yerleştirmeniz](/dynamics365/mixed-reality/guides/hololens-app-orientation)gerekir.

>[!NOTE]
> BILGISAYARDA oturum açmak ve HoloLens yazmak için **yazma** rolüne ihtiyacınız olacak. Işleç rolü salt okunurdur ve bılgısayar uygulamasına erişimi yoktur.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Kılavuzu çalıştırma

Hologramlar hazır olduktan sonra, kılavuzumuzu test edebilirsiniz. 
- **Operatör modunu** seçin
- Kılavuzunuz adımlarında tıklayın.

Kılavuzu nasıl çalıştıracaksınız hakkında daha ayrıntılı yönergeler için şu kaynaklara göz atın:

[Dynamics 365 kılavuzlarındaki bir Kılavuzu çalıştırma konusuna genel bakış](/dynamics365/mixed-reality/guides/operator-overview)

[Adım kartıyla Dynamics 365 kılavuzlarındaki bir operatör olarak yönlendirilirsiniz](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantı dağıtımı-koru](hololens2-corp-connected-maintain.md)
