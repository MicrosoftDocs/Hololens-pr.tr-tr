---
title: HoloLens 2'nizi ayarlama
description: HoloLens 2'nizi microsoft (MSA) veya Wi-Fi (AAD) hesabıyla Azure Active Directory ilk kez ayarlamayı öğrenin.
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
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923920"
---
# <a name="set-up-your-hololens-2"></a>HoloLens 2'nizi ayarlama

HoloLens'i ilk kez açtıktan sonra cihazınızı kurma, bir kullanıcı hesabıyla oturum açma ve HoloLens'i göz göre ayarlama adımlarında size yol gösterir.  Bu bölüm HoloLens 2 ilk kurulum deneyiminde yol sunar.

Sonraki bölümde HoloLens ile çalışma ve hologramlarla etkileşim kurma hakkında bilgi edineceksiniz. Bu makaleye atlamak için bkz. [HoloLens 2'de dolaşma.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir ağ bağlantısı.** HoloLens'inizi ayarlamak için bir ağa bağlamanız gerekir. HoloLens 2 ile, Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir). İlk kez bağlanacaksanız, bir web sitesine bağlanmayı veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız olur. [HoloLens'in kullandığı web siteleri hakkında daha fazla bilgi edinebilirsiniz.](hololens-offline.md)

**Bir Microsoft hesabı.** Ayrıca HoloLens'te bir Microsoft hesabı (veya cihazın sahibi kuruluşsa iş hesabınızla) oturum açmanız gerekir. Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)

**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.** [Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**HoloLens'inizi** en rahat şekilde sığdırmanıza yardımcı olmak için gelen isteğe bağlı konfor donatıları. [Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Windows'u Kurma

HoloLens 2'nizi ilk kez başlatacaksanız, ilk göreviniz Windows Holographic'i ayarlamaktır.  HoloLens'inizi başlatacaksanız müzik duyacak ve bir Windows logosuyla karşınıza gelecektir.

![İlk önyükleme sırasında ilk ekran](images/01-magic-moment.png)

HoloLens 2 aşağıdaki adımlarda size yol sağlar:

1. Dilinizi seçin.

    ![Dil seçin](images/04-language.png)

1. Bölgenizi seçin.

    ![Bölge seçme](images/05-region.png)

1. HoloLens'i göz önünde bulundurarak ayarlama.  Ayarlamayı atlarsanız, bir sonraki oturum aç adımında sorabilirsiniz. 

    1. İlk olarak, mengenenizi ayarlaycaz.
    
        ![Ayar seçimi ekranı](images/06-et-corners.png)

    2. Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız. Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil. HoloLens, holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır. 

        ![Gözlerinizi göre ayarlayın](images/07-adjust-eyes.png)

        Ayarlamadan sonra hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür. Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir. Daha fazla bilgi için [bkz. Ayar verileri ve güvenliği.](hololens-calibration.md#calibration-data-and-security)

        ![Ayarlama tamamlandı](images/calibration-complete.png)

1. İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).

     HoloLens, ağdan alınan bilgilere göre saat diliminizi otomatik Wi-Fi ayarlar. Kurulum tamam olduktan sonra Ayarlar uygulamasını kullanarak saat dilimini değiştirebilirsiniz.

    ![Wi-Fi'ye bağlanma](images/11-network.png)

    > [!NOTE] 
    > Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Aynı anda Ses Düzeyi Kapalı ve Güç düğmelerine basabilirsiniz.  Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)
    > 
    > HoloLens Kurulumu sırasında iki dakikalık bir kimlik bilgisi zaman aşımı olduğunu da unutmayın. Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.

1. HoloLens 2, bir Autopilot profili (varsa) araması yapacak ve uygulayacak. Bu ekranda eylem gerekmez.
 
    ![Autopilot profil araması](images/autopilot-profile-search.png) 

1. **Lisanslama** ekranında Kabul Et'e tıklayın.

    ![Windows lisans sözleşmesi](images/windows-license-agreement.png)

1. Kullanıcı hesabınızla oturum açın. İş veya okul sahibi **ve sahibi** benim arasında **seçim var.**

    - İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın. HoloLens, Azure AD Premium MDM kaydını yapılandırmışsa ve bu kaydı yapılandırmışsa HoloLens otomatik olarak MDM'ye kaydolacaktır. Kuruluşta otomatik Azure AD Premium otomatik MDM kaydı kullanılamaz. Bu durumda, [HoloLens'i cihaz yönetimine el ile kaydetmeniz gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Kuruluş hesabı bilgilerini girin.
        1. Gizlilik bildirimini ve son kullanıcı lisans sözleşmenizi kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açma. Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.
        1. Cihazı ayarlamaya devam edin.

    - **Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı. Kurulum tamamlandıktan sonra [HoloLens'i cihaz yönetimine el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Aşağıdaki Microsoft hesabı girin.
        2. Parolanızı girin. İki adımlı Microsoft hesabı [(2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa doğrulama işlemini tamamlar.

    ![Kullanıcı ayarlama](images/13-device-owner.png)

1. Sonraki 'yi seçerek Iris oturum açma **kurulumu.** Göz alıcıya benzer bir deneyimden geçerek devam edersiniz. Tarama **tamamlandığında** Bitti'yi seçin. Bu adımı atlamak için **Atla'yi** de seçin.
    
    ![Iris kurulumu ](images/setup-iris.png) ![ Iris kurulumu tamamlama](images/iris-setup-complete.png) 
     
  
1. Cihazda oturum açmak için bir PIN ayarlarsanız. Bu PIN cihaza özeldir. 

    ![Kurulum Windows Hello](images/setup-windows-hello.png)

    ![Kurulum Windows Hello PIN'i](images/windows-hello-pin.png)

    ![Windows Hello Kurulumu başarılı](images/windows-hello-successful.png) 
    
1. HoloLens 2'de konuşmayı etkinleştirip etkinleştirmeyeceklerini seçin.

    ![Cortana'yı etkinleştirme](images/22-do-more-with-voice.png)

1. HoloLens 2'de konumun etkinleştirip etkinleştirmeyeceklerini seçin.
    
    ![Konum hizmetlerini etkinleştirme](images/setup-location-services.png)

1. Telemetri düzeyinizi seçin. Varsa, lütfen İsteğe bağlı telemetri'yi etkinleştirin. Bu bilgiler HoloLens mühendislik ekibine gerçekten yardımcı olur.

     ![Telemetri düzeyi](images/24-telemetry.png)

1. HoloLens 2'de başlangıç hareketi kullanmayı öğrenin.

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 1](images/26-01-startmenu-learning.png)

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 2](images/26-02-startmenu-learning.png)

Tebrikler!  Kurulum tamamlandı ve HoloLens kullanmaya hazır oldu!

## <a name="next-steps"></a>Sonraki adımlar

1. Karma Gerçeklik ile hemen etkileşime Windows 10 HoloLens'inize giderek çalışmaya başlayabilirsiniz. El ile etkileşimler için uygulamalı öğreticiler için İpuçları uygulamasına göz atabilirsiniz.  Başlangıç hareketini kullanarak Başlat'a gidin veya "Başla"ya gidip İpuçları'ı seçin.

1. HoloLens 2 ile ilgili bilgi almaya devam etmek için aşağıya tıklayın.

> [!div class="nextstepaction"]
> [HoloLens 2’de dolaşma](hololens2-basic-usage.md)
