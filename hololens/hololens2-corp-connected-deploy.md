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
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="163df-104">Dağıtım-kurumsal bağlantılı kılavuz</span><span class="sxs-lookup"><span data-stu-id="163df-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="163df-105">Her dağıtımın önemli bir kısmı, son kullanıcı için sorunsuz bir deneyim sağlamak üzere dağıtımınızı test etmeden önce doğru şekilde ayarlamış olmasını sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="163df-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="163df-106">MDM aracılığıyla Wi-Fi sertifikasını dağıtmakta olduğumuz için, başlangıçta, açık bir Wi-Fi ağa veya sertifikayı gerektirmeyen bir ağa HoloLens ve cihaz kaydetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="163df-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="163df-107">HoloLens, OOBE ve kaydolduktan sonra cihaz, daha önce yapılandırılmış olan ağ sertifikasını ve LOB 'u alır ve cihaz tarafından her ikisinin de alındığını doğrulayabilecektir.</span><span class="sxs-lookup"><span data-stu-id="163df-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="163df-108">Daha sonra, bir test kılavuzunu yazıp çalıştıracağınızı doğrulayabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="163df-109">Kayıt doğrulama</span><span class="sxs-lookup"><span data-stu-id="163df-109">Enrollment Validation</span></span>

<span data-ttu-id="163df-110">Artık her şey Azure AD ve MDM kaydı için düzgün şekilde yapılandırıldığından, Rest artık bir snap olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="163df-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="163df-111">Wi-Fi bağlantıya ve HoloLens cihazına ve daha önce yapılandırılmış Azure AD kullanıcı hesaplarından birine ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="163df-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="163df-112">Cihazınız şu anda bir fabrika ayarları durumunda oturmazsa, [cihazı](/hololens/hololens-recovery#clean-reflash-the-device)yeniden oluşturmak için iyi bir zaman olurdu.</span><span class="sxs-lookup"><span data-stu-id="163df-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="163df-113">Cihazınız OOBE 'olduktan sonra, etkileşime başlamanız ve istemleri takip etmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="163df-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="163df-114">Wi-Fi ' a katılması için sertifika gerektirmeyen açık bir Wi-Fi ağa Bağlan.</span><span class="sxs-lookup"><span data-stu-id="163df-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="163df-115">Bu işlem, cihazın ilk kurulumdan sonra kuruluşun Wi-Fi kullanılacak sertifikayı indirmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="163df-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="163df-116">**bu HoloLens sahip Who** sorulduğunda kritik istem ne olur?</span><span class="sxs-lookup"><span data-stu-id="163df-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="163df-117">**Çalışmalarımı veya okulumu** seçin ve Azure AD hesabınızın kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="163df-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="163df-118">Kayıt başarılı olduğunda, bir PIN ayarlamanız istenir.</span><span class="sxs-lookup"><span data-stu-id="163df-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="163df-119">Bu PIN, bu kullanıcı için bu cihaz için benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="163df-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="163df-120">Ayrıca, Iris taramaları, ses verileri ve telemetri ayarları istenir ve son olarak, Başlat menüsünü açmayı ve OOBE 'yi tamamlamayı öğreneceksiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="163df-121">karma gerçeklik ana sayfasına girdikten sonra, yeni öğrendiğiniz **başlangıç hareketini** kullanarak Başlat menüsü açın.</span><span class="sxs-lookup"><span data-stu-id="163df-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="163df-122">**Ayarlar** uygulamayı seçip **sistem**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="163df-123">HoloLens 2 cihazınız, daha &quot; &quot; sonra altı karakterli bir dize olmak üzere, sizin için göreceğiniz ilk bilgi parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="163df-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="163df-124">Bu adı bir yere göz atın.</span><span class="sxs-lookup"><span data-stu-id="163df-124">Take note of this name.</span></span>

    ![HoloLens 2 Ayarlar ekran](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="163df-126">Cihazınızın Azure AD 'ye başarıyla katıldığını doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="163df-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="163df-127">İki yol vardır;</span><span class="sxs-lookup"><span data-stu-id="163df-127">There are two ways;</span></span>

    1.  <span data-ttu-id="163df-128">Ayarlar uygulaması.</span><span class="sxs-lookup"><span data-stu-id="163df-128">The Settings app.</span></span> <span data-ttu-id="163df-129">**Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="163df-130">Bu ekrandan, &quot; nameofAAD&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="163df-131">İle bağlandı *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="163df-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="163df-132">Bu, cihazınızın kuruluşunuza katıldığını doğrular&#39;s Azure AD.</span><span class="sxs-lookup"><span data-stu-id="163df-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="163df-133">[Azure Portal](https://portal.azure.com/#home).</span><span class="sxs-lookup"><span data-stu-id="163df-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="163df-134">**Azure Active Directory**  ->  **cihazlar**  ->  **tüm cihazlar**' a gidin ve cihaz adında arama yapın.</span><span class="sxs-lookup"><span data-stu-id="163df-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="163df-135">Katılım türü altında, ' Azure AD 'ye katılmış ' olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="163df-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="163df-136">![Azure AD 'de JOIN türünü doğrulama](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="163df-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="163df-137">Cihazınızın MDM 'ye kayıtlı olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="163df-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="163df-138">İki yol vardır;</span><span class="sxs-lookup"><span data-stu-id="163df-138">There are two ways;</span></span>

    1. <span data-ttu-id="163df-139">**Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="163df-140">Bu ekrandan, &quot; nameofAAD&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="163df-141">İle bağlandı *yourusername@nameofAAD.onmicrosoft.com* .</span><span class="sxs-lookup"><span data-stu-id="163df-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="163df-142">Bu Access iş veya okul hesabından, &quot; nameofAAD&#39;s Azure AD ' a bağlı ' yı seçerek.</span><span class="sxs-lookup"><span data-stu-id="163df-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="163df-143">İle bağlandı yourusername@nameofAAD.onmicrosoft.com &quot; ve **bilgi** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="163df-144">[Microsoft Endpoint Manager yönetim merkezi](https://endpoint.microsoft.com/#home).</span><span class="sxs-lookup"><span data-stu-id="163df-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="163df-145">Oturum açın ve  **cihazlar**  ' ın ardından  **tüm cihazlar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="163df-146">buradan HoloLens cihazınızda&#39;adına arama yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="163df-147">HoloLens ıntune 'da listelenmiş olarak görebilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="163df-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Azure AD 'de Intune tarafından yönetilen doğrulama](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="163df-149">Wi-Fi sertifikası doğrulaması</span><span class="sxs-lookup"><span data-stu-id="163df-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="163df-150">Artık cihaz Wi-Fi sertifikasını almış olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="163df-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="163df-151">Yapabileceğiniz en basit doğrulama, sertifikayı&#39;aldığınız Wi-Fi bağlantıya bağlanmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="163df-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="163df-152">**Ayarlar** uygulamasını açın ve **ağ &amp; ınternet**  ->  **Wi-fi** ' a gidin ve Wi-fi bağlantısını seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="163df-153">bağlandıktan sonra Microsoft Edge uygulamasını açın ve bir web sitesine gidebileceğiniz onaylayın.</span><span class="sxs-lookup"><span data-stu-id="163df-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="163df-154">Sertifikayı cihazda aldığınızı onaylamak için, [sertifika yöneticisini](/hololens/certificate-manager)kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="163df-155">LOB uygulaması yüklemesini doğrula</span><span class="sxs-lookup"><span data-stu-id="163df-155">Validate LOB app install</span></span>

<span data-ttu-id="163df-156">yönetilen bir uygulamanın yükleme ilerlemesini görmek için, uygulamanın yüklü olup olmadığını görürsünüz veya Ayarlar denetleyin.</span><span class="sxs-lookup"><span data-stu-id="163df-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="163df-157">bir LOB uygulamasını grubumuza gerekli bir yükleme olarak yapılandırarak, HoloLens atanan gruptaki bir kullanıcıyla kaydettikten sonra, uygulama HoloLens otomatik olarak indirilir.</span><span class="sxs-lookup"><span data-stu-id="163df-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="163df-158">Başlat menüsü açın ve **tüm uygulamalar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="163df-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="163df-159">Sahip olduğunuz uygulama sayısına bağlı olarak, **sayfa yukarı** veya **sayfa aşağı** düğmelerini kullanmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="163df-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="163df-160">uygulamanın cihazda yüklenmesini doğrulamak için, **Ayarlar**  ->  **hesapları**  ->  **işe veya okula erişim** aracılığıyla yapabilirsiniz; hesabı sonra **bilgi** düğmesini seçip, ardından aşağı kaydırarak cihaz MDM 'den cihaza uygulanmış farklı yapılandırma ve uygulamaları görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="163df-161">Yüklemeyi Intune 'dan doğrulamak için, [mem portalı](https://endpoint.microsoft.com/#home)  ->  **uygulamalar** -   -> *uygulama*  ->  **cihaz yüklemesi durum** sayfasından > tüm uygulamalar ' a gidin.</span><span class="sxs-lookup"><span data-stu-id="163df-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="163df-162">Daha fazla bilgi [için bkz. HoloLens Için Intune uygulama dağıtımı](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="163df-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="163df-163">Dynamics 365 kılavuzlarını doğrulama</span><span class="sxs-lookup"><span data-stu-id="163df-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="163df-164">HoloLens, yazma ve çalıştırma üzerinde kılavuzlar uygulamasının modları vardır.</span><span class="sxs-lookup"><span data-stu-id="163df-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="163df-165">Kullanmadan önce bir kılavuz yazmayı gerçekleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="163df-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="163df-166">Kılavuzu yazma</span><span class="sxs-lookup"><span data-stu-id="163df-166">Authoring the Guide</span></span>

<span data-ttu-id="163df-167">Bu hızlı doğrulama için çok gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="163df-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="163df-168">Bilgisayarınızda hazırladığınız Kılavuzu seçmeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="163df-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="163df-169">Hızlı bir doğrulama için [kılavuza bağlantı](/dynamics365/mixed-reality/guides/hololens-app-anchor)oluşturmanız gerekir. bir holographic bağlayıcısını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="163df-170">Daha sonra, [adımlarınızı ve modellerinizi yerleştirmeniz](/dynamics365/mixed-reality/guides/hololens-app-orientation)gerekir.</span><span class="sxs-lookup"><span data-stu-id="163df-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="163df-171">BILGISAYARDA oturum açmak ve HoloLens yazmak için **yazma** rolüne ihtiyacınız olacak.</span><span class="sxs-lookup"><span data-stu-id="163df-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="163df-172">Işleç rolü salt okunurdur ve bılgısayar uygulamasına erişimi yoktur.</span><span class="sxs-lookup"><span data-stu-id="163df-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="163df-173">Kılavuzu çalıştırma</span><span class="sxs-lookup"><span data-stu-id="163df-173">Operating the Guide</span></span>

<span data-ttu-id="163df-174">Hologramlar hazır olduktan sonra, kılavuzumuzu test edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="163df-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="163df-175">**Operatör modunu** seçin</span><span class="sxs-lookup"><span data-stu-id="163df-175">Select **Operator mode**</span></span>
- <span data-ttu-id="163df-176">Kılavuzunuz adımlarında tıklayın.</span><span class="sxs-lookup"><span data-stu-id="163df-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="163df-177">Kılavuzu nasıl çalıştıracaksınız hakkında daha ayrıntılı yönergeler için şu kaynaklara göz atın:</span><span class="sxs-lookup"><span data-stu-id="163df-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="163df-178">Dynamics 365 kılavuzlarındaki bir Kılavuzu çalıştırma konusuna genel bakış</span><span class="sxs-lookup"><span data-stu-id="163df-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="163df-179">Adım kartıyla Dynamics 365 kılavuzlarındaki bir operatör olarak yönlendirilirsiniz</span><span class="sxs-lookup"><span data-stu-id="163df-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="163df-180">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="163df-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="163df-181">Kurumsal bağlantı dağıtımı-koru</span><span class="sxs-lookup"><span data-stu-id="163df-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
