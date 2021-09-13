---
title: HoloLens 2 ' 'nizi ayarlama
description: HoloLens 2 ' 'nizi Microsoft (MSA) veya Azure Active Directory (AAD) hesabıyla Wi-Fi ağ üzerinden ilk kez ayarlama hakkında bilgi edinin.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036341"
---
# <a name="set-up-your-hololens-2"></a>HoloLens 2 ' 'nizi ayarlama

HoloLens ilk kez açtığınızda, cihazınızı ayarlama, bir kullanıcı hesabı ile oturum açma ve HoloLens ayarlarınız için ayarlama adımları gösterilecektir.  bu bölümde, HoloLens 2 ilk kurulum deneyimi gösterilmektedir.

sonraki bölümde, HoloLens nasıl çalışacağınızı ve hologramlar ile nasıl etkileşime gireceğini öğreneceksiniz. bu makaleye yönelik daha fazla bilgi almak için bkz. [HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce, aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir ağ bağlantısı**. kurmak için HoloLens bir ağa bağlamanız gerekir. HoloLens 2 ile, Wi-Fi veya ethernet kullanarak bağlanabilirsiniz (USB-C-ethernet bağdaştırıcısı gerekir). İlk kez bağlandığınızda, bir Web sitesine gidilmesini veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız vardır. [HoloLens tarafından kullanılan web siteleri hakkında daha fazla bilgi edinin](hololens-offline.md).

**Bir Microsoft hesabı**. ayrıca, kuruluşunuz cihazın sahibi olan bir Microsoft hesabı (veya iş hesabınızla HoloLens oturum açmanız gerekir. Bir Microsoft hesabı yoksa, [account.Microsoft.com](https://account.microsoft.com) adresine gidin ve birini ücretsiz olarak ayarlayın.

**Güvenilir ve Iyi bir şekilde bir arada olan tehlikeli bir alan**. [Sistem durumu ve güvenlik bilgileri](https://go.microsoft.com/fwlink/p/?LinkId=746661).

en rahat hale getirmenize yardımcı olmak için HoloLens ile birlikte gelen **isteğe bağlı rahatlar** . [Daha fazla uyum ve rahatlık](hololens2-setup.md#adjust-fit).

## <a name="set-up-windows"></a>Windows'u Kurma

HoloLens 2 ' yi ilk kez başlattığınızda, ilk göreviniz Windows Holographic ayarlaması olur.  HoloLens başlattığınızda, müzik duyacaktır ve bir Microsoft logosu görürsünüz.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Etrafında bir Hummingbird görürsünüz.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Bu işlem, elinizin ardından gelir.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Microsoft logosu olan bir düğme görünür. düğmeye basın ve HoloLens 2 aşağıdaki adımlarda size yol gösterir:

1. Dilinizi seçin.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Bölgenizi seçin.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. HoloLens gözlerinize ayarlayın.  Ayarlamayı atlamayı seçerseniz, bir sonraki oturum açışınızda sorulur. 

    1. İlk olarak, vizörü 'nizi ayarlayacaksınız.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Ayarlamak için, bir dizi hedefe (Gems olarak adlandırılır) bakacaksınız. Ayarlama sırasında gözlerinizin yanıp sönmesini veya kapatılmasını, ancak odanın veya fiziksel alandaki diğer nesneler üzerinde ne zaman daha fazla bir sorun olduğunu deneyebilirsiniz. HoloLens, holographic dünyasını daha iyi işleyebilmesi için göz konumlarınızın hakkında bilgi edinmek üzere bu işlemi kullanır. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Ayarlandıktan sonra hologramlar, başlarınızın baş vardiyaları gibi doğru şekilde görünür. Ayarlama bilgileri cihazda yerel olarak depolanır ve herhangi bir hesap bilgileriyle ilişkili değildir. Daha fazla bilgi için bkz. [ayarlama verileri ve güvenliği](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. internet 'e Bağlan (Wi-Fi veya ethernet bağlantınızı seçin).

     HoloLens saat diliminizi Wi-Fi ağından elde edilen bilgilere göre otomatik olarak ayarlar. kurulum bittikten sonra, Ayarlar uygulamasını kullanarak saat dilimini değiştirebilirsiniz.

    ![Wi-Fi Bağlan.](images/11-network.png)

    > [!NOTE] 
    > Devam ederseniz Wi-Fi adımı ve sonrasında kurulum sırasında farklı bir ağa geçiş yapmanız gerekiyorsa, 2019 veya üzeri bir işletim sistemi sürümü çalıştırıyorsanız bu adıma geri dönmek için **Birim aşağı** ve **Güç** düğmelerine aynı anda basabilirsiniz. Önceki sürümler için [cihazı sıfırlamanız](hololens-recovery.md) veya Wi-Fi ağının otomatik olarak bağlanmasını engellemek için kullanılabilir olmayan bir konumda yeniden başlatmanız gerekebilir.
    > 
    > ayrıca, HoloLens kurulum sırasında iki dakikalık bir kimlik bilgisi zaman aşımı olduğunu unutmayın. Kullanıcı adı/parolanın iki dakika içinde girilmesi gerekir, aksi takdirde Kullanıcı adı alanı otomatik olarak temizlenir.

1. HoloLens 2, varsa, bir Autopilot profilini arar ve uygular. Bu ekranda bir işlem yapılması gerekmez.
 
    ![Autopilot profil araması.](images/autopilot-profile-search.png) 

1. Lisanslama ekranında **kabul et** ' e tıklayın.

    ![lisans sözleşmesini Windows.](images/windows-license-agreement.png)

1. Kullanıcı hesabınızda oturum açın. **Çalışmam veya okulum ile bu** arasında seçim yapmanız ve sahibi **olmam** gerekir.

    ![Kullanıcı ayarla.](images/13-device-owner.png)
    - **Çalışmam veya okulumu** seçtiğinizde, BIR Azure AD hesabıyla oturum açın. kuruluşunuz Azure AD Premium kullanıyorsa ve otomatik mdm kaydı yapılandırmışsa, HoloLens mdm 'ye otomatik olarak kaydeder. kuruluşunuz Azure AD Premium kullanmıyorsa otomatik MDM kaydı kullanılamaz. bu durumda, [HoloLens cihaz yönetimine el ile kaydetmeniz](hololens-enroll-mdm.md#different-ways-to-enroll)gerekir.

        1. Kurumsal hesap bilgilerinizi girin.
        1. Gizlilik bildirimini ve Son Kullanıcı Lisans sözleşmesini kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açın. Bu, kuruluşunuzun oturum açma sayfasına yönlendirebilir.
        1. Cihazı ayarlamaya devam edin.

    - Sahip **olduğumu** seçtiğinizde bir Microsoft hesabı oturum açın. kurulum tamamlandıktan sonra, [cihaz yönetimi 'ne HoloLens el ile](hololens-enroll-mdm.md#different-ways-to-enroll)kaydedebilirsiniz.

        1. Microsoft hesabı bilgilerinizi girin.
        2. Parolanızı girin. Microsoft hesabı [iki adımlı doğrulama (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa, doğrulama işlemini doldurun.

        
1. **İleri**' ye tıklayarak Iris oturum açma kurulumu. Göz ayarlamaya benzer bir deneyimle karşılaşırsınız. Tarama tamamlandığında **bitti** ' yi seçin. Bu adımı atlamak için **Atla** ' yı da seçebilirsiniz.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Cihazda oturum açmak için bir PIN ayarlayacaksınız. Bu PIN cihaza özeldir. 

    ![Kurulum Windows Hello.](images/setup-windows-hello.png)

    ![Windows Hello pın 'i ayarlayın.](images/windows-hello-pin.png)

    ![Windows Hello Kurulum başarılı oldu.](images/windows-hello-successful.png) 

    
1. HoloLens 2 ' de konuşmayı etkinleştirmek isteyip istemediğinizi seçin.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. HoloLens 2 ' de konumun etkinleştirilip etkinleştirilmeyeceğini seçin.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Telemetri düzeyinizi seçin. Mümkünse, lütfen Isteğe bağlı telemetrisini etkinleştirin. bu bilgiler, HoloLens mühendislik ekibine gerçekten yardımcı olur.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. HoloLens 2 ' de başlangıç hareketini nasıl kullanacağınızı öğrenin.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Tebrikler!  Kurulum tamamlanmıştır ve HoloLens kullanmaya hazırsınız!

## <a name="next-steps"></a>Sonraki adımlar

1. karma gerçeklik ile hemen etkileşim kurmaya başlayın ve HoloLens Windows 10 gezinerek, bt etkileşimlerine yönelik uygulamalı öğreticiler için **İpuçları** uygulamasına göz atın. başlamak için başlangıç hareketini kullanın veya "başlat 'a git" deyin ve İpuçları ' yi seçin.

1. HoloLens 2 ' yi okumaya devam etmek için aşağıya tıklayın.

> [!div class="nextstepaction"]
> [HoloLens 2’de dolaşma](hololens2-basic-usage.md)
