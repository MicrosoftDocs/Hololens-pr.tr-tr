---
title: 2. HoloLens ayarlama
description: Microsoft (MSA) veya HoloLens (AAD) hesabıyla Wi-Fi ağ üzerinden Azure Active Directory 2'nizi ayarlamayı öğrenin.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189775"
---
# <a name="set-up-your-hololens-2"></a>2. HoloLens ayarlama

HoloLens'nizi ilk kez açtıktan sonra cihazınızı ayarlama, bir kullanıcı hesabıyla oturum açma ve HoloLens ayarlama adımlarını takip edersiniz.  Bu bölümde, ilk 2 HoloLens deneyimin üzerinden geçebilirsiniz.

Sonraki bölümde, yeni çalışma ve hologramlarla etkileşim HoloLens etmeyi öğrenirsiniz. Bu makaleye atlamak için bkz. [2. HoloLens.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir ağ bağlantısı.** Bunu ayarlamak için ağ HoloLens ağına bağlamanız gerekir. HoloLens 2 ile, Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir). İlk kez bağlanacaksanız, bir web sitesine gezinmeyi veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız vardır. [tarafından kullanan web siteleri hakkında daha fazla HoloLens bilgi edinebilirsiniz.](hololens-offline.md)

**Bir Microsoft hesabı.** Ayrıca, bir HoloLens (veya cihazın sahibi Microsoft hesabı iş hesabınızla) oturum açmanız gerekir. Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)

**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.** [Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**En rahat uyuma** sahip olmak için HoloLens isteğe bağlı konfor donatıları. [Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Windows'u Kurma

İlk olarak 2. HoloLens ilk kez holographic'i ayarlamak Windows görevidir.  Çalışmanıza baş HoloLens müzik dinleyecek ve bir Microsoft logosuyla karşınıza gelecektir.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Etrafında bir kuş uçuşu olduğunu göreceğiz.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Bu, sizin ellerinizi takip eder.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Microsoft logosu olan bir düğme gösterir. Düğmeye basın ve HoloLens 2'ye tıklayarak aşağıdaki adımları izleyin:

1. Dilinizi seçin.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Bölgenizi seçin.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Göz HoloLens ayarlama.  Ayarlamayı atlarsanız, bir sonraki oturum aç adımınız istenir. 

    1. İlk olarak, mengenenizi ayarlaycaz.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız. Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil. HoloLens holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Ayarlama sonrasında hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür. Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir. Daha fazla bilgi için [bkz. Ayar verileri ve güvenliği.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Bağlan İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).

     HoloLens ağdan alınan bilgilere göre saat diliminizi otomatik olarak Wi-Fi ayarlar. Kurulum tamam olduktan sonra, Ayarlar uygulamasını kullanarak saat Ayarlar değiştirebilirsiniz.

    ![Bağlan Wi-Fi'a bağlanın.](images/11-network.png)

    > [!NOTE] 
    > Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Aynı anda Ses Düzeyi Kapalı ve Güç düğmelerine basabilirsiniz.  Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)
    > 
    > Ayrıca, Kurulum HoloLens kimlik bilgisi zaman aşımının iki dakika olduğunu unutmayın. Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.

1. HoloLens 2, varsa bir Autopilot profili araması yapacak ve uygulayacak. Bu ekranda eylem gerekmez.
 
    ![Autopilot profil araması.](images/autopilot-profile-search.png) 

1. **Lisanslama** ekranında Kabul Et'e tıklayın.

    ![Windows lisans sözleşmesi.](images/windows-license-agreement.png)

1. Kullanıcı hesabınızla oturum açın. İş veya okul sahibi **ve sahibi** benim arasında **seçim seçimlerini siz seçersiniz.**

    ![Kullanıcı ayarlama.](images/13-device-owner.png)
    - İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın. Kuruluş otomatik MDM Azure AD Premium yapılandırmışsa ve otomatik MDM kaydı HoloLens MDM'ye otomatik olarak kaydolacaktır. Kuruluşta otomatik Azure AD Premium MDM kaydı kullanılamaz. Bu durumda, cihaz yönetimine [el ile HoloLens gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Kuruluş hesabı bilgilerini girin.
        1. Gizlilik bildirimini ve son kullanıcı lisans sözleşmelerini kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açma. Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.
        1. Cihazı ayarlamaya devam edin.

    - **Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı. Kurulum tamamlandıktan sonra, cihaz [yönetimine HoloLens el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Aşağıdaki Microsoft hesabı girin.
        2. Parolanızı girin. İki Microsoft hesabı doğrulama [(2FA) gerektiriyorsa](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)doğrulama işlemini tamamlar.

        
1. Sonraki 'yi seçerek Iris oturum açma **kurulumu.** Göz alıcıya benzer bir deneyimden geçerek devam edersiniz. Tarama **tamamlandığında** Bitti'yi seçin. Bu adımı atlamak için **Atla'yi** de seçin.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Cihazda oturum açmak için bir PIN ayarlarsanız. Bu PIN cihaza özeldir. 

    ![Kurulum Windows Hello.](images/setup-windows-hello.png)

    ![Pin'Windows Hello kurulumu.](images/windows-hello-pin.png)

    ![Windows Hello Kurulum başarılı.](images/windows-hello-successful.png) 

    
1. 2. satırda konuşmayı etkinleştirip HoloLens seçin.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. 2. konumda konumun etkinleştirip HoloLens seçin.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Telemetri düzeyinizi seçin. Varsa, lütfen İsteğe bağlı telemetri'yi etkinleştirin. Bu bilgiler mühendislik ekibine HoloLens yardımcı olur.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. HoloLens 2'de başlangıç HoloLens öğrenin.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Tebrikler!  Kurulum tamamlandı ve HoloLens!

## <a name="next-steps"></a>Sonraki adımlar

1. Karma Gerçeklik ile hemen etkileşime Windows 10 HoloLens uygulamanıza giderek İpuçları uygulamalı  etkileşimler için uygulamalı öğreticilere göz atabilirsiniz. Başlat'a gitmek için başlangıç hareketi kullanın veya "Başla'ya Git" de İpuçları.

1. 2.0'da çalışmaya devam etmek için HoloLens tıklayın.

> [!div class="nextstepaction"]
> [HoloLens 2’de dolaşma](hololens2-basic-usage.md)
