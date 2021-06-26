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
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="99504-104">HoloLens 2'nizi ayarlama</span><span class="sxs-lookup"><span data-stu-id="99504-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="99504-105">HoloLens'i ilk kez açtıktan sonra cihazınızı kurma, bir kullanıcı hesabıyla oturum açma ve HoloLens'i göz göre ayarlama adımlarında size yol gösterir.</span><span class="sxs-lookup"><span data-stu-id="99504-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="99504-106">Bu bölüm HoloLens 2 ilk kurulum deneyiminde yol sunar.</span><span class="sxs-lookup"><span data-stu-id="99504-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="99504-107">Sonraki bölümde HoloLens ile çalışma ve hologramlarla etkileşim kurma hakkında bilgi edineceksiniz.</span><span class="sxs-lookup"><span data-stu-id="99504-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="99504-108">Bu makaleye atlamak için bkz. [HoloLens 2'de dolaşma.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="99504-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="99504-109">Başlamadan önce</span><span class="sxs-lookup"><span data-stu-id="99504-109">Before you start</span></span>

<span data-ttu-id="99504-110">Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:</span><span class="sxs-lookup"><span data-stu-id="99504-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="99504-111">**Bir ağ bağlantısı.**</span><span class="sxs-lookup"><span data-stu-id="99504-111">**A network connection**.</span></span> <span data-ttu-id="99504-112">HoloLens'inizi ayarlamak için bir ağa bağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="99504-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="99504-113">HoloLens 2 ile, Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir).</span><span class="sxs-lookup"><span data-stu-id="99504-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="99504-114">İlk kez bağlanacaksanız, bir web sitesine bağlanmayı veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız olur.</span><span class="sxs-lookup"><span data-stu-id="99504-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="99504-115">[HoloLens'in kullandığı web siteleri hakkında daha fazla bilgi edinebilirsiniz.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="99504-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="99504-116">**Bir Microsoft hesabı.**</span><span class="sxs-lookup"><span data-stu-id="99504-116">**A Microsoft account**.</span></span> <span data-ttu-id="99504-117">Ayrıca HoloLens'te bir Microsoft hesabı (veya cihazın sahibi kuruluşsa iş hesabınızla) oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="99504-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="99504-118">Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="99504-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="99504-119">**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.**</span><span class="sxs-lookup"><span data-stu-id="99504-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="99504-120">[Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="99504-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="99504-121">**HoloLens'inizi** en rahat şekilde sığdırmanıza yardımcı olmak için gelen isteğe bağlı konfor donatıları.</span><span class="sxs-lookup"><span data-stu-id="99504-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="99504-122">[Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="99504-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="99504-123">Windows'u Kurma</span><span class="sxs-lookup"><span data-stu-id="99504-123">Set up Windows</span></span>

<span data-ttu-id="99504-124">HoloLens 2'nizi ilk kez başlatacaksanız, ilk göreviniz Windows Holographic'i ayarlamaktır.</span><span class="sxs-lookup"><span data-stu-id="99504-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="99504-125">HoloLens'inizi başlatacaksanız müzik duyacak ve bir Windows logosuyla karşınıza gelecektir.</span><span class="sxs-lookup"><span data-stu-id="99504-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![İlk önyükleme sırasında ilk ekran](images/01-magic-moment.png)

<span data-ttu-id="99504-127">HoloLens 2 aşağıdaki adımlarda size yol sağlar:</span><span class="sxs-lookup"><span data-stu-id="99504-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="99504-128">Dilinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-128">Select your language.</span></span>

    ![Dil seçin](images/04-language.png)

1. <span data-ttu-id="99504-130">Bölgenizi seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-130">Select your region.</span></span>

    ![Bölge seçme](images/05-region.png)

1. <span data-ttu-id="99504-132">HoloLens'i göz önünde bulundurarak ayarlama.</span><span class="sxs-lookup"><span data-stu-id="99504-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="99504-133">Ayarlamayı atlarsanız, bir sonraki oturum aç adımında sorabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99504-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="99504-134">İlk olarak, mengenenizi ayarlaycaz.</span><span class="sxs-lookup"><span data-stu-id="99504-134">First, you'll adjust your visor.</span></span>
    
        ![Ayar seçimi ekranı](images/06-et-corners.png)

    2. <span data-ttu-id="99504-136">Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız.</span><span class="sxs-lookup"><span data-stu-id="99504-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="99504-137">Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil.</span><span class="sxs-lookup"><span data-stu-id="99504-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="99504-138">HoloLens, holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır.</span><span class="sxs-lookup"><span data-stu-id="99504-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Gözlerinizi göre ayarlayın](images/07-adjust-eyes.png)

        <span data-ttu-id="99504-140">Ayarlamadan sonra hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür.</span><span class="sxs-lookup"><span data-stu-id="99504-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="99504-141">Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir.</span><span class="sxs-lookup"><span data-stu-id="99504-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="99504-142">Daha fazla bilgi için [bkz. Ayar verileri ve güvenliği.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="99504-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Ayarlama tamamlandı](images/calibration-complete.png)

1. <span data-ttu-id="99504-144">İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).</span><span class="sxs-lookup"><span data-stu-id="99504-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="99504-145">HoloLens, ağdan alınan bilgilere göre saat diliminizi otomatik Wi-Fi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="99504-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="99504-146">Kurulum tamam olduktan sonra Ayarlar uygulamasını kullanarak saat dilimini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99504-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi'ye bağlanma](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="99504-148">Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Aynı anda Ses Düzeyi Kapalı ve Güç düğmelerine basabilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="99504-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="99504-149">Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="99504-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="99504-150">HoloLens Kurulumu sırasında iki dakikalık bir kimlik bilgisi zaman aşımı olduğunu da unutmayın.</span><span class="sxs-lookup"><span data-stu-id="99504-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="99504-151">Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.</span><span class="sxs-lookup"><span data-stu-id="99504-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="99504-152">HoloLens 2, bir Autopilot profili (varsa) araması yapacak ve uygulayacak.</span><span class="sxs-lookup"><span data-stu-id="99504-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="99504-153">Bu ekranda eylem gerekmez.</span><span class="sxs-lookup"><span data-stu-id="99504-153">No action is needed on this screen.</span></span>
 
    ![Autopilot profil araması](images/autopilot-profile-search.png) 

1. <span data-ttu-id="99504-155">**Lisanslama** ekranında Kabul Et'e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="99504-155">Click **Accept** on the licensing screen.</span></span>

    ![Windows lisans sözleşmesi](images/windows-license-agreement.png)

1. <span data-ttu-id="99504-157">Kullanıcı hesabınızla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="99504-157">Sign in to your user account.</span></span> <span data-ttu-id="99504-158">İş veya okul sahibi **ve sahibi** benim arasında **seçim var.**</span><span class="sxs-lookup"><span data-stu-id="99504-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="99504-159">İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="99504-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="99504-160">HoloLens, Azure AD Premium MDM kaydını yapılandırmışsa ve bu kaydı yapılandırmışsa HoloLens otomatik olarak MDM'ye kaydolacaktır.</span><span class="sxs-lookup"><span data-stu-id="99504-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="99504-161">Kuruluşta otomatik Azure AD Premium otomatik MDM kaydı kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="99504-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="99504-162">Bu durumda, [HoloLens'i cihaz yönetimine el ile kaydetmeniz gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="99504-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="99504-163">Kuruluş hesabı bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="99504-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="99504-164">Gizlilik bildirimini ve son kullanıcı lisans sözleşmenizi kabul edin.</span><span class="sxs-lookup"><span data-stu-id="99504-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="99504-165">Azure AD kimlik bilgilerinizi kullanarak oturum açma.</span><span class="sxs-lookup"><span data-stu-id="99504-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="99504-166">Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="99504-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="99504-167">Cihazı ayarlamaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="99504-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="99504-168">**Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı.</span><span class="sxs-lookup"><span data-stu-id="99504-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="99504-169">Kurulum tamamlandıktan sonra [HoloLens'i cihaz yönetimine el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="99504-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="99504-170">Aşağıdaki Microsoft hesabı girin.</span><span class="sxs-lookup"><span data-stu-id="99504-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="99504-171">Parolanızı girin.</span><span class="sxs-lookup"><span data-stu-id="99504-171">Enter your password.</span></span> <span data-ttu-id="99504-172">İki adımlı Microsoft hesabı [(2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa doğrulama işlemini tamamlar.</span><span class="sxs-lookup"><span data-stu-id="99504-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Kullanıcı ayarlama](images/13-device-owner.png)

1. <span data-ttu-id="99504-174">Sonraki 'yi seçerek Iris oturum açma **kurulumu.**</span><span class="sxs-lookup"><span data-stu-id="99504-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="99504-175">Göz alıcıya benzer bir deneyimden geçerek devam edersiniz.</span><span class="sxs-lookup"><span data-stu-id="99504-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="99504-176">Tarama **tamamlandığında** Bitti'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="99504-177">Bu adımı atlamak için **Atla'yi** de seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="99504-178">![Iris kurulumu ](images/setup-iris.png) ![ Iris kurulumu tamamlama](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="99504-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="99504-179">Cihazda oturum açmak için bir PIN ayarlarsanız.</span><span class="sxs-lookup"><span data-stu-id="99504-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="99504-180">Bu PIN cihaza özeldir.</span><span class="sxs-lookup"><span data-stu-id="99504-180">This PIN is device specific.</span></span> 

    ![Kurulum Windows Hello](images/setup-windows-hello.png)

    ![Kurulum Windows Hello PIN'i](images/windows-hello-pin.png)

    ![Windows Hello Kurulumu başarılı](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="99504-184">HoloLens 2'de konuşmayı etkinleştirip etkinleştirmeyeceklerini seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Cortana'yı etkinleştirme](images/22-do-more-with-voice.png)

1. <span data-ttu-id="99504-186">HoloLens 2'de konumun etkinleştirip etkinleştirmeyeceklerini seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Konum hizmetlerini etkinleştirme](images/setup-location-services.png)

1. <span data-ttu-id="99504-188">Telemetri düzeyinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-188">Select your telemetry level.</span></span> <span data-ttu-id="99504-189">Varsa, lütfen İsteğe bağlı telemetri'yi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="99504-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="99504-190">Bu bilgiler HoloLens mühendislik ekibine gerçekten yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="99504-190">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetri düzeyi](images/24-telemetry.png)

1. <span data-ttu-id="99504-192">HoloLens 2'de başlangıç hareketi kullanmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="99504-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 1](images/26-01-startmenu-learning.png)

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="99504-195">Tebrikler!</span><span class="sxs-lookup"><span data-stu-id="99504-195">Congratulations!</span></span>  <span data-ttu-id="99504-196">Kurulum tamamlandı ve HoloLens kullanmaya hazır oldu!</span><span class="sxs-lookup"><span data-stu-id="99504-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="99504-197">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="99504-197">Next steps</span></span>

1. <span data-ttu-id="99504-198">Karma Gerçeklik ile hemen etkileşime Windows 10 HoloLens'inize giderek çalışmaya başlayabilirsiniz. El ile etkileşimler için uygulamalı öğreticiler için İpuçları uygulamasına göz atabilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="99504-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="99504-199">Başlangıç hareketini kullanarak Başlat'a gidin veya "Başla"ya gidip İpuçları'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="99504-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="99504-200">HoloLens 2 ile ilgili bilgi almaya devam etmek için aşağıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="99504-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99504-201">HoloLens 2’de dolaşma</span><span class="sxs-lookup"><span data-stu-id="99504-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
