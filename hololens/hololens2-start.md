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
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="e939e-104">2. HoloLens ayarlama</span><span class="sxs-lookup"><span data-stu-id="e939e-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="e939e-105">HoloLens cihazınızı ilk kez açtıktan sonra cihazınızı ayarlama, bir kullanıcı hesabıyla oturum açma ve cihazı HoloLens ayarlarsınız.</span><span class="sxs-lookup"><span data-stu-id="e939e-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="e939e-106">Bu bölümde, ilk 2 HoloLens deneyimin üzerinden geçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="e939e-107">Bir sonraki bölümde, çalışma ve hologramlarla etkileşim HoloLens etmeyi öğrenirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="e939e-108">Bu makaleye geçmek için bkz. [2. HoloLens alma.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="e939e-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e939e-109">Başlamadan önce</span><span class="sxs-lookup"><span data-stu-id="e939e-109">Before you start</span></span>

<span data-ttu-id="e939e-110">Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:</span><span class="sxs-lookup"><span data-stu-id="e939e-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="e939e-111">**Bir ağ bağlantısı.**</span><span class="sxs-lookup"><span data-stu-id="e939e-111">**A network connection**.</span></span> <span data-ttu-id="e939e-112">Bunu ayarlamak için ağ HoloLens ağına bağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e939e-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="e939e-113">HoloLens 2 ile, Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir).</span><span class="sxs-lookup"><span data-stu-id="e939e-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="e939e-114">İlk kez bağlanacaksanız, bir web sitesine bağlanmayı veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız olur.</span><span class="sxs-lookup"><span data-stu-id="e939e-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="e939e-115">[tarafından kullanan web siteleri hakkında daha fazla HoloLens bilgi edinebilirsiniz.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="e939e-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="e939e-116">**Bir Microsoft hesabı.**</span><span class="sxs-lookup"><span data-stu-id="e939e-116">**A Microsoft account**.</span></span> <span data-ttu-id="e939e-117">Ayrıca, bir HoloLens (veya Microsoft hesabı cihaza sahipse iş hesabınızla) oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e939e-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="e939e-118">Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e939e-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="e939e-119">**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.**</span><span class="sxs-lookup"><span data-stu-id="e939e-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="e939e-120">[Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="e939e-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="e939e-121">**En rahat uyumunu** elde etmek için HoloLens isteğe bağlı konfor donatıları.</span><span class="sxs-lookup"><span data-stu-id="e939e-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="e939e-122">[Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="e939e-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="e939e-123">Windows'u Kurma</span><span class="sxs-lookup"><span data-stu-id="e939e-123">Set up Windows</span></span>

<span data-ttu-id="e939e-124">İlk kez 2. HoloLens ilk kez holographic'i ayarlamak Windows görevidir.</span><span class="sxs-lookup"><span data-stu-id="e939e-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="e939e-125">Çalışmanızı başlatan HoloLens müzik duyar ve bir Windows logosunu göresiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![İlk önyükleme sırasında ilk ekran](images/01-magic-moment.png)

<span data-ttu-id="e939e-127">Etrafında bir kuş uçuşu olduğunu göreceğiz.</span><span class="sxs-lookup"><span data-stu-id="e939e-127">You will see a hummingbird flying around.</span></span>

![Kuş uçuşu](images/hummingbird-1.png)

<span data-ttu-id="e939e-129">El ile takip edin.</span><span class="sxs-lookup"><span data-stu-id="e939e-129">Follow it with your hand.</span></span>

![Yakın bir şekilde uçmaya devam ediyor](images/hummingbird-2.png)

<span data-ttu-id="e939e-131">HoloLens 2, aşağıdaki adımlarda size yol vezneler:</span><span class="sxs-lookup"><span data-stu-id="e939e-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="e939e-132">Dilinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-132">Select your language.</span></span>

    ![Dil seçin](images/04-language.png)

1. <span data-ttu-id="e939e-134">Bölgenizi seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-134">Select your region.</span></span>

    ![Bölge seçme](images/05-region.png)

1. <span data-ttu-id="e939e-136">Göz HoloLens ayarlama.</span><span class="sxs-lookup"><span data-stu-id="e939e-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="e939e-137">Ayarlamayı atlarsanız, bir sonraki oturum aç adımında sorabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="e939e-138">İlk olarak, mengenenizi ayarlaycaz.</span><span class="sxs-lookup"><span data-stu-id="e939e-138">First, you'll adjust your visor.</span></span>
    
        ![Ayar seçimi ekranı](images/06-et-corners.png)

    2. <span data-ttu-id="e939e-140">Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız.</span><span class="sxs-lookup"><span data-stu-id="e939e-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="e939e-141">Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil.</span><span class="sxs-lookup"><span data-stu-id="e939e-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="e939e-142">HoloLens holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır.</span><span class="sxs-lookup"><span data-stu-id="e939e-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Gözlerinizi göre ayarlayın](images/07-adjust-eyes.png)

        <span data-ttu-id="e939e-144">Ayarlamadan sonra hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür.</span><span class="sxs-lookup"><span data-stu-id="e939e-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="e939e-145">Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir.</span><span class="sxs-lookup"><span data-stu-id="e939e-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="e939e-146">Daha fazla bilgi için [bkz. Ayar verileri ve güvenliği.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="e939e-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Ayarlama tamamlandı](images/calibration-complete.png)

1. <span data-ttu-id="e939e-148">Bağlan İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).</span><span class="sxs-lookup"><span data-stu-id="e939e-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="e939e-149">HoloLens ağdan alınan bilgilere göre saat diliminizi otomatik olarak Wi-Fi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="e939e-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="e939e-150">Kurulum tamam olduktan sonra, Ayarlar uygulamasını kullanarak saat Ayarlar değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi'ye bağlanma](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="e939e-152">Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Aynı anda Ses Düzeyi Kapalı ve Güç düğmelerine basabilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="e939e-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="e939e-153">Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="e939e-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="e939e-154">Ayrıca Kurulum sırasında HoloLens kimlik bilgisi zaman aşımının iki dakika olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e939e-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="e939e-155">Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.</span><span class="sxs-lookup"><span data-stu-id="e939e-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="e939e-156">HoloLens 2, varsa bir Autopilot profili araması yapacak ve uygulayacak.</span><span class="sxs-lookup"><span data-stu-id="e939e-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="e939e-157">Bu ekranda eylem gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e939e-157">No action is needed on this screen.</span></span>
 
    ![Autopilot profil araması](images/autopilot-profile-search.png) 

1. <span data-ttu-id="e939e-159">**Lisanslama** ekranında Kabul Et'e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e939e-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows lisans sözleşmesi](images/windows-license-agreement.png)

1. <span data-ttu-id="e939e-161">Kullanıcı hesabınızla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="e939e-161">Sign in to your user account.</span></span> <span data-ttu-id="e939e-162">İş veya okul sahibi **ve sahibi** benim arasında **seçim var.**</span><span class="sxs-lookup"><span data-stu-id="e939e-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![Kullanıcı ayarlama](images/13-device-owner.png)
    - <span data-ttu-id="e939e-164">İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="e939e-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="e939e-165">Kuruluş otomatik MDM Azure AD Premium yapılandırmışsa ve otomatik MDM kaydı HoloLens MDM'ye otomatik olarak kaydolacaktır.</span><span class="sxs-lookup"><span data-stu-id="e939e-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="e939e-166">Kuruluşta otomatik MDM Azure AD Premium yoksa otomatik MDM kaydı kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="e939e-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="e939e-167">Bu durumda, cihaz yönetimine [el ile HoloLens gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="e939e-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="e939e-168">Kuruluş hesabı bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="e939e-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="e939e-169">Gizlilik bildirimini ve son kullanıcı lisans sözleşmenizi kabul edin.</span><span class="sxs-lookup"><span data-stu-id="e939e-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="e939e-170">Azure AD kimlik bilgilerinizi kullanarak oturum açma.</span><span class="sxs-lookup"><span data-stu-id="e939e-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="e939e-171">Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="e939e-172">Cihazı ayarlamaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="e939e-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="e939e-173">**Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı.</span><span class="sxs-lookup"><span data-stu-id="e939e-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="e939e-174">Kurulum tamamlandıktan sonra, cihaz [yönetimine HoloLens el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="e939e-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="e939e-175">Aşağıdaki Microsoft hesabı girin.</span><span class="sxs-lookup"><span data-stu-id="e939e-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="e939e-176">Parolanızı girin.</span><span class="sxs-lookup"><span data-stu-id="e939e-176">Enter your password.</span></span> <span data-ttu-id="e939e-177">İki adımlı Microsoft hesabı [(2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa doğrulama işlemini tamamlar.</span><span class="sxs-lookup"><span data-stu-id="e939e-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="e939e-178">Sonraki 'yi seçerek Iris oturum açma **kurulumu.**</span><span class="sxs-lookup"><span data-stu-id="e939e-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="e939e-179">Göz alıcıya benzer bir deneyimden geçerek devam edersiniz.</span><span class="sxs-lookup"><span data-stu-id="e939e-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="e939e-180">Tarama **tamamlandığında** Bitti'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="e939e-181">Bu adımı atlamak için **Atla'yi** de seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="e939e-182">![Iris kurulumu ](images/setup-iris.png) ![ Iris kurulumu tamamlama](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="e939e-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="e939e-183">Cihazda oturum açmak için bir PIN ayarlarsanız.</span><span class="sxs-lookup"><span data-stu-id="e939e-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="e939e-184">Bu PIN cihaza özeldir.</span><span class="sxs-lookup"><span data-stu-id="e939e-184">This PIN is device specific.</span></span> 

    ![Kurulum Windows Hello](images/setup-windows-hello.png)

    ![Kurulum Windows Hello PIN'i](images/windows-hello-pin.png)

    ![Windows Hello Kurulum başarılı](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="e939e-188">2. satırda konuşmayı etkinleştirip HoloLens seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="e939e-190">2. konumda konumun etkinleştirip HoloLens seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Konum hizmetlerini etkinleştirme](images/setup-location-services.png)

1. <span data-ttu-id="e939e-192">Telemetri düzeyinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-192">Select your telemetry level.</span></span> <span data-ttu-id="e939e-193">Varsa, lütfen İsteğe bağlı telemetri'yi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="e939e-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="e939e-194">Bu bilgiler mühendislik ekibine HoloLens yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="e939e-194">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetri düzeyi](images/24-telemetry.png)

1. <span data-ttu-id="e939e-196">HoloLens 2'de başlangıç hareketini kullanmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="e939e-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 1](images/26-01-startmenu-learning.png)

     ![Başlangıç hareketini kullanmayı öğrenin, görüntü 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="e939e-199">Tebrikler!</span><span class="sxs-lookup"><span data-stu-id="e939e-199">Congratulations!</span></span>  <span data-ttu-id="e939e-200">Kurulum tamamlandı ve HoloLens!</span><span class="sxs-lookup"><span data-stu-id="e939e-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="e939e-201">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="e939e-201">Next steps</span></span>

1. <span data-ttu-id="e939e-202">karma gerçeklik ile hemen etkileşim kurmaya başlayın ve HoloLens Windows 10 gezinerek, bt etkileşimlerine yönelik uygulamalı öğreticiler için **İpuçları** uygulamasına göz atın.</span><span class="sxs-lookup"><span data-stu-id="e939e-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="e939e-203">başlamak için başlangıç hareketini kullanın veya "başlat 'a git" deyin ve İpuçları ' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="e939e-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="e939e-204">HoloLens 2 ' yi okumaya devam etmek için aşağıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e939e-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e939e-205">HoloLens 2’de dolaşma</span><span class="sxs-lookup"><span data-stu-id="e939e-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
