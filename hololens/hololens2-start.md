---
title: HoloLens 2'nizi ayarlama
description: HoloLens 2'nizi microsoft (MSA) veya Wi-Fi (AAD) hesabıyla Azure Active Directory ilk kez ayarlamayı öğrenin.
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380250"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="4971b-104">HoloLens 2'nizi ayarlama</span><span class="sxs-lookup"><span data-stu-id="4971b-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="4971b-105">HoloLens'i ilk kez açtıktan sonra cihazınızı kurma, bir kullanıcı hesabıyla oturum açma ve HoloLens'i göz göre ayarlama adımlarında size yol gösterir.</span><span class="sxs-lookup"><span data-stu-id="4971b-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="4971b-106">Bu bölüm HoloLens 2 ilk kurulum deneyiminde yol sunar.</span><span class="sxs-lookup"><span data-stu-id="4971b-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="4971b-107">Sonraki bölümde HoloLens ile çalışma ve hologramlarla etkileşim kurma hakkında bilgi edineceksiniz.</span><span class="sxs-lookup"><span data-stu-id="4971b-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="4971b-108">Bu makaleye atlamak için [holoLens 2 Kullanmaya başlayın makalesine bakın.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="4971b-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4971b-109">Başlamadan önce</span><span class="sxs-lookup"><span data-stu-id="4971b-109">Before you start</span></span>

<span data-ttu-id="4971b-110">Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:</span><span class="sxs-lookup"><span data-stu-id="4971b-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="4971b-111">**Bir ağ bağlantısı.**</span><span class="sxs-lookup"><span data-stu-id="4971b-111">**A network connection**.</span></span> <span data-ttu-id="4971b-112">HoloLens'inizi ayarlamak için bir ağa bağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4971b-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="4971b-113">HoloLens 2 ile Wi-Fi veya Ethernet kullanarak bağlanabilirsiniz (USB-C-Ethernet bağdaştırıcısı gerekir).</span><span class="sxs-lookup"><span data-stu-id="4971b-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="4971b-114">İlk kez bağlanacaksanız, bir web sitesine gezinmeyi veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="4971b-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="4971b-115">[HoloLens'in kullandığı web siteleri hakkında daha fazla bilgi edinebilirsiniz.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="4971b-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="4971b-116">**Bir Microsoft hesabı.**</span><span class="sxs-lookup"><span data-stu-id="4971b-116">**A Microsoft account**.</span></span> <span data-ttu-id="4971b-117">Ayrıca HoloLens'te bir Microsoft hesabı (veya cihazın sahibi kuruluşsa iş hesabınızla) oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4971b-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="4971b-118">Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4971b-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="4971b-119">**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.**</span><span class="sxs-lookup"><span data-stu-id="4971b-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="4971b-120">[Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="4971b-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="4971b-121">**HoloLens'inizi** en rahat şekilde sığdırmanıza yardımcı olmak için gelen isteğe bağlı konfor donatıları.</span><span class="sxs-lookup"><span data-stu-id="4971b-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="4971b-122">[Fit ve konfor hakkında daha fazla bilgi.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="4971b-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="4971b-123">Windows'u Kurma</span><span class="sxs-lookup"><span data-stu-id="4971b-123">Set up Windows</span></span>

<span data-ttu-id="4971b-124">HoloLens 2'nizi ilk kez başlatacaksanız, ilk göreviniz Windows Holographic'i ayarlamaktır.</span><span class="sxs-lookup"><span data-stu-id="4971b-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="4971b-125">HoloLens'inizi başlatacaksanız müzik duyacak ve bir Windows logosuyla karşınıza gelecektir.</span><span class="sxs-lookup"><span data-stu-id="4971b-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![İlk önyükleme sırasında ilk ekran](images/01-magic-moment.png)

<span data-ttu-id="4971b-127">HoloLens 2 aşağıdaki adımlarda size yol sağlar:</span><span class="sxs-lookup"><span data-stu-id="4971b-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="4971b-128">Dilinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="4971b-128">Select your language.</span></span>

    ![Dil seçin](images/04-language.png)

1. <span data-ttu-id="4971b-130">Bölgenizi seçin.</span><span class="sxs-lookup"><span data-stu-id="4971b-130">Select your region.</span></span>

    ![Bölge seçme](images/05-region.png)

1. <span data-ttu-id="4971b-132">HoloLens'i göz önünde bulundurarak ayarlama.</span><span class="sxs-lookup"><span data-stu-id="4971b-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="4971b-133">Ayarlamayı atlarsanız, bir sonraki oturum aç adımında sorabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4971b-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="4971b-134">Ayarlamak için bir hedef kümesine (gems olarak adlandırılır) bakacağız.</span><span class="sxs-lookup"><span data-stu-id="4971b-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="4971b-135">Ayarlama sırasında yanıp sönmeniz veya gözlerinizi kapatmanız, ancak oda veya fiziksel alanda diğer nesnelere göz atmamaya çalışmanız sorun değil.</span><span class="sxs-lookup"><span data-stu-id="4971b-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="4971b-136">HoloLens, holografik dünyanızı daha iyi hale getirmek için göz konumunuz hakkında bilgi edinmek için bu süreci kullanır.</span><span class="sxs-lookup"><span data-stu-id="4971b-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="4971b-137">Ayarlama sonrasında hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür.</span><span class="sxs-lookup"><span data-stu-id="4971b-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="4971b-138">Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir.</span><span class="sxs-lookup"><span data-stu-id="4971b-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="4971b-139">Daha fazla bilgi için [bkz. Veri ve güvenliği ayarlama.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="4971b-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Ayar seçimi ekranı](images/06-et-corners.png)

1. <span data-ttu-id="4971b-141">İnternet'e bağlanın (Wi-Fi ethernet bağlantınızı seçin).</span><span class="sxs-lookup"><span data-stu-id="4971b-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="4971b-142">HoloLens, ağdan alınan bilgilere göre saat diliminizi otomatik Wi-Fi ayarlar.</span><span class="sxs-lookup"><span data-stu-id="4971b-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="4971b-143">Kurulum tamam olduktan sonra Ayarlar uygulamasını kullanarak saat dilimini değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4971b-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Wi-Fi'ye bağlanma](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="4971b-145">Wi-Fi adımını geçmeniz ve daha sonra kurulum sırasında farklı bir ağa geçmeniz gerekirse, Ekim  2019 veya sonraki bir işletim sistemi sürümünü çalıştırıyorsanız bu adıma geri dönmek için Ses Düzeyi Kapalı ve Güç düğmelerine aynı anda basabilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="4971b-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="4971b-146">Önceki sürümlerde cihazı sıfırlamanız veya cihazın otomatik olarak bağlanmasını önlemek için Wi-Fi ağın kullanılabilir olmadığını bir konumda yeniden başlatmanız gerekir. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="4971b-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="4971b-147">HoloLens Kurulumu sırasında iki dakikalık bir kimlik bilgisi zaman aşımı olduğunu da unutmayın.</span><span class="sxs-lookup"><span data-stu-id="4971b-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="4971b-148">Kullanıcı adı/parola iki dakika içinde girilir, aksi takdirde kullanıcı adı alanı otomatik olarak temizlenir.</span><span class="sxs-lookup"><span data-stu-id="4971b-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="4971b-149">Kullanıcı hesabınızla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="4971b-149">Sign in to your user account.</span></span> <span data-ttu-id="4971b-150">İş veya okul sahibi **ve sahibi** benim arasında **seçim seçimlerini siz seçersiniz.**</span><span class="sxs-lookup"><span data-stu-id="4971b-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="4971b-151">İş veya **okul sahibim'i seçtiğiniz zaman** bir Azure AD hesabıyla oturum açın.</span><span class="sxs-lookup"><span data-stu-id="4971b-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="4971b-152">HoloLens, Azure AD Premium MDM kaydını yapılandırmışsa ve MDM kaydını otomatik olarak yapılandırmışsa, HoloLens otomatik olarak MDM'ye kaydolacaktır.</span><span class="sxs-lookup"><span data-stu-id="4971b-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="4971b-153">Kuruluşta otomatik Azure AD Premium MDM kaydı kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4971b-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="4971b-154">Bu durumda, [HoloLens'i cihaz yönetimine el ile kaydetmeniz gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="4971b-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="4971b-155">Kuruluş hesabı bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="4971b-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="4971b-156">Gizlilik bildirimini ve son kullanıcı lisans sözleşmenizi kabul edin.</span><span class="sxs-lookup"><span data-stu-id="4971b-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="4971b-157">Azure AD kimlik bilgilerinizi kullanarak oturum açma.</span><span class="sxs-lookup"><span data-stu-id="4971b-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="4971b-158">Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4971b-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="4971b-159">Cihazı ayarlamaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="4971b-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="4971b-160">**Sahibim'i seçerseniz,** bir kullanıcıyla oturum Microsoft hesabı.</span><span class="sxs-lookup"><span data-stu-id="4971b-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="4971b-161">Kurulum tamamlandıktan sonra [HoloLens'i cihaz yönetimine el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="4971b-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="4971b-162">Aşağıdaki Microsoft hesabı girin.</span><span class="sxs-lookup"><span data-stu-id="4971b-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="4971b-163">Parolanızı girin.</span><span class="sxs-lookup"><span data-stu-id="4971b-163">Enter your password.</span></span> <span data-ttu-id="4971b-164">İki adımlı Microsoft hesabı [(2FA) gerektiriyorsa](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)doğrulama işlemini tamamlar.</span><span class="sxs-lookup"><span data-stu-id="4971b-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Kullanıcı ayarlama](images/13-device-owner.png)

1. <span data-ttu-id="4971b-166">HoloLens 2'de konuşmayı etkinleştirmeyi ve tanılama telemetrisini gönderip göndermeyeceklerini seçin.</span><span class="sxs-lookup"><span data-stu-id="4971b-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Cortana'yı etkinleştirme](images/22-do-more-with-voice.png)

1. <span data-ttu-id="4971b-168">Telemetri düzeyinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="4971b-168">Select your telemetry level.</span></span> <span data-ttu-id="4971b-169">Varsa, lütfen Tam telemetri'yi etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="4971b-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="4971b-170">Bu bilgiler HoloLens mühendislik ekibine gerçekten yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="4971b-170">This information really helps the HoloLens engineering team.</span></span>

     ![Telemetri düzeyi](images/24-telemetry.png)

1. <span data-ttu-id="4971b-172">HoloLens 2'de başlangıç hareketi kullanmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="4971b-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="4971b-173">![Başlangıç hareketi kullanmayı öğrenin, görüntü 1 ](images/26-01-startmenu-learning.png) ![ Başlangıç hareketi kullanmayı öğrenin, görüntü 2](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="4971b-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="4971b-174">Tebrikler!</span><span class="sxs-lookup"><span data-stu-id="4971b-174">Congratulations!</span></span>  <span data-ttu-id="4971b-175">Kurulum tamamlandı ve HoloLens kullanmaya hazır oldu!</span><span class="sxs-lookup"><span data-stu-id="4971b-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="4971b-176">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="4971b-176">Next steps</span></span>

1. <span data-ttu-id="4971b-177">Karma Gerçeklik ile hemen etkileşime Windows 10 HoloLens'inize giderek çalışmaya başlayabilirsiniz. El ile etkileşimler için uygulamalı öğreticiler için İpuçları uygulamasına göz atabilirsiniz. </span><span class="sxs-lookup"><span data-stu-id="4971b-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="4971b-178">Başlangıç hareketini kullanarak Başlat'a gidin veya "Başla"ya gidip İpuçları'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4971b-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="4971b-179">HoloLens 2 ile ilgili bilgi almaya devam etmek için aşağıya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="4971b-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4971b-180">hololens 2 ile Kullanmaya başlayın</span><span class="sxs-lookup"><span data-stu-id="4971b-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
