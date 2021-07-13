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
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636805"
---
# <a name="set-up-your-hololens-2"></a>2. HoloLens ayarlama

HoloLens cihazınızı ilk kez açtıktan sonra cihazınızı ayarlama, bir kullanıcı hesabıyla oturum açma ve cihazı HoloLens ayarlarsınız.  Bu bölümde, ilk 2 HoloLens deneyimin üzerinden geçebilirsiniz.

Bir sonraki bölümde, çalışma ve hologramlarla etkileşim HoloLens etmeyi öğrenirsiniz. Bu makaleye geçmek için bkz. [2. HoloLens alma.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir ağ bağlantısı.** Bunu ayarlamak için ağ HoloLens ağına bağlamanız gerekir. HoloLens 2 ile, Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir). İlk kez bağlanacaksanız, bir web sitesine bağlanmayı veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız olur. [tarafından kullanan web siteleri hakkında daha fazla HoloLens bilgi edinebilirsiniz.](hololens-offline.md)

**Bir Microsoft hesabı.** Ayrıca, bir HoloLens (veya Microsoft hesabı cihaza sahipse iş hesabınızla) oturum açmanız gerekir. Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)

**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.** [Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**En rahat uyumunu** elde etmek için HoloLens isteğe bağlı konfor donatıları. [Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Windows'u Kurma

İlk kez 2. HoloLens ilk kez holographic'i ayarlamak Windows görevidir.  Çalışmanızı başlatan HoloLens müzik duyar ve bir Windows logosunu göresiniz.

![İlk önyükleme sırasında ilk ekran](images/01-magic-moment.png)

Etrafında bir kuş uçuşu olduğunu göreceğiz.

![Kuş uçuşu](images/hummingbird-1.png)

El ile takip edin.

![Yakın bir şekilde uçmaya devam ediyor](images/hummingbird-2.png)

HoloLens 2, aşağıdaki adımlarda size yol vezneler:

1. Dilinizi seçin.

    ![Dil seçin](images/04-language.png)

1. Bölgenizi seçin.

    ![Bölge seçme](images/05-region.png)

1. Göz HoloLens ayarlama.  Ayarlamayı atlarsanız, bir sonraki oturum aç adımında sorabilirsiniz. 

    1. İlk olarak, mengenenizi ayarlaycaz.
    
        ![Ayar seçimi ekranı](images/06-et-corners.png)

    2. Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız. Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil. HoloLens holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır. 

        ![Gözlerinizi göre ayarlayın](images/07-adjust-eyes.png)

        Ayarlamadan sonra hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür. Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir. Daha fazla bilgi için [bkz. Ayar verileri ve güvenliği.](hololens-calibration.md#calibration-data-and-security)

        ![Ayarlama tamamlandı](images/calibration-complete.png)

1. Bağlan İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).

     HoloLens ağdan alınan bilgilere göre saat diliminizi otomatik olarak Wi-Fi ayarlar. Kurulum tamam olduktan sonra, Ayarlar uygulamasını kullanarak saat Ayarlar değiştirebilirsiniz.

    ![Wi-Fi'ye bağlanma](images/11-network.png)

    > [!NOTE] 
    > Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Aynı anda Ses Düzeyi Kapalı ve Güç düğmelerine basabilirsiniz.  Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)
    > 
    > Ayrıca Kurulum sırasında HoloLens kimlik bilgisi zaman aşımının iki dakika olduğunu unutmayın. Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.

1. HoloLens 2, varsa bir Autopilot profili araması yapacak ve uygulayacak. Bu ekranda eylem gerekmez.
 
    ![Autopilot profil araması](images/autopilot-profile-search.png) 

1. **Lisanslama** ekranında Kabul Et'e tıklayın.

    ![Windows lisans sözleşmesi](images/windows-license-agreement.png)

1. Kullanıcı hesabınızla oturum açın. İş veya okul sahibi **ve sahibi** benim arasında **seçim var.**

    ![Kullanıcı ayarlama](images/13-device-owner.png)
    - İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın. Kuruluş otomatik MDM Azure AD Premium yapılandırmışsa ve otomatik MDM kaydı HoloLens MDM'ye otomatik olarak kaydolacaktır. Kuruluşta otomatik MDM Azure AD Premium yoksa otomatik MDM kaydı kullanılamaz. Bu durumda, cihaz yönetimine [el ile HoloLens gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Kuruluş hesabı bilgilerini girin.
        1. Gizlilik bildirimini ve son kullanıcı lisans sözleşmenizi kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açma. Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.
        1. Cihazı ayarlamaya devam edin.

    - **Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı. Kurulum tamamlandıktan sonra, cihaz [yönetimine HoloLens el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Aşağıdaki Microsoft hesabı girin.
        2. Parolanızı girin. İki adımlı Microsoft hesabı [(2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa doğrulama işlemini tamamlar.

        
1. Sonraki 'yi seçerek Iris oturum açma **kurulumu.** Göz alıcıya benzer bir deneyimden geçerek devam edersiniz. Tarama **tamamlandığında** Bitti'yi seçin. Bu adımı atlamak için **Atla'yi** de seçin.
    
    ![Iris kurulumu ](images/setup-iris.png) ![ Iris kurulumu tamamlama](images/iris-setup-complete.png) 
     
  
1. Cihazda oturum açmak için bir PIN ayarlarsanız. Bu PIN cihaza özeldir. 

    ![Kurulum Windows Hello](images/setup-windows-hello.png)

    ![Kurulum Windows Hello PIN'i](images/windows-hello-pin.png)

    ![Windows Hello Kurulum başarılı](images/windows-hello-successful.png) 
    
1. 2. satırda konuşmayı etkinleştirip HoloLens seçin.

    ![Cortana](images/22-do-more-with-voice.png)

1. 2. konumda konumun etkinleştirip HoloLens seçin.
    
    ![Konum hizmetlerini etkinleştirme](images/setup-location-services.png)

1. Telemetri düzeyinizi seçin. Varsa, lütfen İsteğe bağlı telemetri'yi etkinleştirin. Bu bilgiler mühendislik ekibine HoloLens yardımcı olur.

     ![Telemetri düzeyi](images/24-telemetry.png)

1. HoloLens 2'de başlangıç hareketini kullanmayı öğrenin.

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 1](images/26-01-startmenu-learning.png)

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 2](images/26-02-startmenu-learning.png)

Tebrikler!  Kurulum tamamlandı ve HoloLens!

## <a name="next-steps"></a>Sonraki adımlar

1. karma gerçeklik ile hemen etkileşim kurmaya başlayın ve HoloLens Windows 10 gezinerek, bt etkileşimlerine yönelik uygulamalı öğreticiler için **İpuçları** uygulamasına göz atın. başlamak için başlangıç hareketini kullanın veya "başlat 'a git" deyin ve İpuçları ' yi seçin.

1. HoloLens 2 ' yi okumaya devam etmek için aşağıya tıklayın.

> [!div class="nextstepaction"]
> [HoloLens 2’de dolaşma](hololens2-basic-usage.md)
