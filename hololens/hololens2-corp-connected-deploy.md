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
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="e4799-104">Dağıtma - Kurumsal Bağlantılı Kılavuz</span><span class="sxs-lookup"><span data-stu-id="e4799-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="e4799-105">Her dağıtımın önemli bir kısmı, son kullanıcı için sorunsuz bir deneyim sağlamak amacıyla dağıtımınızı kendiniz test etmeden önce düzgün bir şekilde ayarlanmış olmasını sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="e4799-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="e4799-106">Wi-Fi sertifikasını MDM aracılığıyla dağıtıyor olduğundan, başlangıçta HoloLens'i ayarlamamız ve açık bir Wi-Fi ağına veya sertifika gerektirmeyen bir ağa cihaz kaydetmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e4799-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="e4799-107">HoloLens OOBE'yi ve Kaydol'u tamamlandıktan sonra cihaz daha önce yapılandırılan ağ sertifikasını ve LOB'u alacak ve her ikisinin de cihaz tarafından alınmakta olduğunu doğrulayabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="e4799-108">Daha sonra hem yazma hem de test kılavuzu çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="e4799-109">Kayıt Doğrulama</span><span class="sxs-lookup"><span data-stu-id="e4799-109">Enrollment Validation</span></span>

<span data-ttu-id="e4799-110">Artık Azure AD ve MDM Kaydı için her şey düzgün yapılandırıldığından, geri kalanı hemen yapılandırıldı.</span><span class="sxs-lookup"><span data-stu-id="e4799-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="e4799-111">Daha önce yapılandırılan Azure AD Wi-Fi ve HoloLens cihazı için bir sanal ağ bağlantısına ihtiyacınız vardır.</span><span class="sxs-lookup"><span data-stu-id="e4799-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="e4799-112">Cihazınız şu anda fabrika ayarları durumda değilse, şimdi cihaza ters eğik çizgi [uygulamanın zamanı geldi.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="e4799-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="e4799-113">Cihazınız OOBE'ye başladıktan sonra etkileşime geçmeye ve istemleri takip edin.</span><span class="sxs-lookup"><span data-stu-id="e4799-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="e4799-114">Wi-Fi'Wi-Fi sertifikaların katılmasını gerektirmeyen açık bir ağ bağlantısına bağlanın.</span><span class="sxs-lookup"><span data-stu-id="e4799-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="e4799-115">Bu, cihazın ilk kurulumdan sonra kuruluşun Wi-Fi sertifikayı indirmesine olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="e4799-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="e4799-116">Bu **HoloLens'in sahibi kim? soruldiğinde kritik istem olur.**</span><span class="sxs-lookup"><span data-stu-id="e4799-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="e4799-117">İş **veya okul sahibim'i seçin** ve Azure AD hesabı kimlik bilgilerinizi girin.</span><span class="sxs-lookup"><span data-stu-id="e4799-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="e4799-118">Kayıt başarılı olduğunda bir PIN'i ayarlamanız istenir.</span><span class="sxs-lookup"><span data-stu-id="e4799-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="e4799-119">Bu PIN, bu kullanıcı için bu cihaz için benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="e4799-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="e4799-120">Iris taramaları, ses verileri ve telemetri ayarları da istenecek ve son olarak başlat menüsünü açıp OOBE'nin nasıl tamamlanabileceklerini öğrenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="e4799-121">Karma Gerçeklik Giriş'e girdiktan sonra, öğrendiği Başlat menüsü **Başlat hareketini kullanarak** giriş girişlerini açın.</span><span class="sxs-lookup"><span data-stu-id="e4799-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="e4799-122">Ayarlar uygulamasını **ve** ardından Sistem'i **seçin.**</span><span class="sxs-lookup"><span data-stu-id="e4799-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="e4799-123">Göreceğiniz ilk bilgi, HoloLens 2 cihazınız için HOLOLENS ve ardından altı karakter dizesi olacak Cihaz &quot; &quot; adınızdır.</span><span class="sxs-lookup"><span data-stu-id="e4799-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="e4799-124">Bu adı not alır.</span><span class="sxs-lookup"><span data-stu-id="e4799-124">Take note of this name.</span></span>

    ![HoloLens 2 Ayarlar ekranı](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="e4799-126">Cihazınızın Azure AD'ye başarıyla katıldığını doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="e4799-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="e4799-127">İki yol vardır:</span><span class="sxs-lookup"><span data-stu-id="e4799-127">There are two ways;</span></span>

    1.  <span data-ttu-id="e4799-128">Ayarlar uygulaması.</span><span class="sxs-lookup"><span data-stu-id="e4799-128">The Settings app.</span></span> <span data-ttu-id="e4799-129">**Ayarlar'dan** Hesaplar **İş veya okula**  ->  **erişim'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="e4799-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="e4799-130">Bu ekrandan, Azure AD'de adofAAD adına bağlandı'yı &quot;&#39;başarılı bir şekilde kaydolarak doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="e4799-131">tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı.</span><span class="sxs-lookup"><span data-stu-id="e4799-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="e4799-132">Bu, cihazınızın Azure AD'de&#39;olduğunu doğrular.</span><span class="sxs-lookup"><span data-stu-id="e4799-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="e4799-133">[Azure portal.](https://portal.azure.com/#home)</span><span class="sxs-lookup"><span data-stu-id="e4799-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="e4799-134">Cihazlar **Azure Active Directory**  ->    ->  **cihazlar'a gidin** ve cihaz adını arayın.</span><span class="sxs-lookup"><span data-stu-id="e4799-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="e4799-135">Birleştirme Türü altında 'Azure AD'ye Katılmış' olarak gösterir.</span><span class="sxs-lookup"><span data-stu-id="e4799-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="e4799-136">![Azure AD'de Birleştirme Türünü Doğrulama](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="e4799-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="e4799-137">Cihazınızın MDM'ye kayıtlı olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="e4799-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="e4799-138">İki yol vardır:</span><span class="sxs-lookup"><span data-stu-id="e4799-138">There are two ways;</span></span>

    1. <span data-ttu-id="e4799-139">**Ayarlar'da** Hesaplar İş **veya**  ->  **okula erişim'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="e4799-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="e4799-140">Bu ekrandan, Azure AD'de adofAAD adına bağlandı'yı &quot;&#39;başarılı bir şekilde kaydolarak doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="e4799-141">tarafından *yourusername@nameofAAD.onmicrosoft.com* bağlandı.</span><span class="sxs-lookup"><span data-stu-id="e4799-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="e4799-142">Bu Access iş veya okul hesabından Azure &quot; AD'nin adofAAD&#39;'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="e4799-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="e4799-143">Bağlı olan yourusername@nameofAAD.onmicrosoft.com &quot; ve Bilgi düğmesini **seçin.**</span><span class="sxs-lookup"><span data-stu-id="e4799-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="e4799-144">[Microsoft Endpoint Manager Yönetim Merkezi.](https://endpoint.microsoft.com/#home)</span><span class="sxs-lookup"><span data-stu-id="e4799-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="e4799-145">Oturum açma ve **Cihazlar'ı ve** ardından Tüm **cihazlar'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="e4799-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="e4799-146">Buradan HoloLens cihazınızın adını&#39;arayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="e4799-147">HoloLens'inizi Intune'da listelenmiş olarak görüyor olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e4799-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![Azure AD'de Intune tarafından yönetileni doğrulama](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="e4799-149">Wi-Fi doğrulama</span><span class="sxs-lookup"><span data-stu-id="e4799-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="e4799-150">Şu an için cihazın sertifikayı almış Wi-Fi gerekir.</span><span class="sxs-lookup"><span data-stu-id="e4799-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="e4799-151">En basit doğrulama, sertifikayı hangi Wi-Fi bağlantınıza&#39;denemedir.</span><span class="sxs-lookup"><span data-stu-id="e4799-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="e4799-152">Ayarlar uygulamasını **açın** ve Ağ İnterneti **&amp;**  ->  **Wi-Fi'a** gidin ve Wi-fi bağlantısını seçin.</span><span class="sxs-lookup"><span data-stu-id="e4799-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="e4799-153">Bağlandıktan sonra Microsoft Edge açın ve bir web sitesine gidebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="e4799-154">Cihazda sertifikayı aldığınızı onaylamak için Sertifika Yöneticisi'ni [kullanabilirsiniz.](https://docs.microsoft.com/hololens/certificate-manager)</span><span class="sxs-lookup"><span data-stu-id="e4799-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="e4799-155">LOB uygulaması yükleme doğrulama</span><span class="sxs-lookup"><span data-stu-id="e4799-155">Validate LOB app install</span></span>

<span data-ttu-id="e4799-156">Yönetilen bir uygulamanın yükleme ilerlemesini görmek için uygulamanın yüklü olup olduğunu görebilir veya Ayarlar'a bakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="e4799-157">Bir LOB uygulamasını grubumuz için gerekli bir yükleme olarak yapılandırarak, HoloLens'i atanan gruba bir kullanıcıyla kaydettikten sonra uygulama otomatik olarak HoloLens'e indirilir.</span><span class="sxs-lookup"><span data-stu-id="e4799-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="e4799-158">Dosyayı açın Başlat menüsü seçin **ve** Tüm uygulamalar.</span><span class="sxs-lookup"><span data-stu-id="e4799-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="e4799-159">Sahip olduğu uygulama sayısına bağlı olarak sayfa yukarı veya sayfa aşağı **düğmelerini** **kullanabilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="e4799-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="e4799-160">Uygulamanın cihaza yüklemesini doğrulamak için Ayarlar Hesapları İş veya okula erişim yoluyla bunu yapabilirsiniz; hesabı ve ardından Bilgi düğmesini seçin ve  ->    ->    MDM'den cihaza uygulanan farklı yapılandırmaları ve uygulamaları görmek için aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="e4799-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="e4799-161">Intune'dan yüklemeyi doğrulamak [için, MEM portalı](https://endpoint.microsoft.com/#home)  ->  **Uygulamalar** -> Tüm **uygulamalar**  -> *TheNameOfApp*  ->  **Cihazınız yükleme durumu sayfasına** gidin.</span><span class="sxs-lookup"><span data-stu-id="e4799-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="e4799-162">Daha fazla bilgi: [HoloLens için Intune Uygulama Dağıtımı](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="e4799-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="e4799-163">Dynamics 365 Kılavuzlarını Doğrulama</span><span class="sxs-lookup"><span data-stu-id="e4799-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="e4799-164">HoloLens'de Guides uygulaması için yazma ve çalıştırma modları vardır.</span><span class="sxs-lookup"><span data-stu-id="e4799-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="e4799-165">Çalıştırmadan önce bir kılavuz yazmayı bitirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e4799-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="e4799-166">Kılavuzu Yazma</span><span class="sxs-lookup"><span data-stu-id="e4799-166">Authoring the Guide</span></span>

<span data-ttu-id="e4799-167">Bu hızlı doğrulama için çok fazla şey yapmaya gerek yok.</span><span class="sxs-lookup"><span data-stu-id="e4799-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="e4799-168">Bilgisayarınızda hazırlığınız olan kılavuzu seçmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="e4799-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="e4799-169">Kılavuzu [sabitleniz gerekir.](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)Hızlı bir doğrulama için holografik yer bağlantısı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e4799-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="e4799-170">Daha sonra, adımlarınızı [ve modellerinizi yere sizin de yerniz.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)</span><span class="sxs-lookup"><span data-stu-id="e4799-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="e4799-171">**HoloLens'de** pc'de oturum açma ve yazma için Yazma rolüne ihtiyacınız olacak.</span><span class="sxs-lookup"><span data-stu-id="e4799-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="e4799-172">İşleç rolü salt okunur bir roldür ve bilgisayar uygulamasına erişimi yoktur.</span><span class="sxs-lookup"><span data-stu-id="e4799-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="e4799-173">Kılavuzu Çalıştırma</span><span class="sxs-lookup"><span data-stu-id="e4799-173">Operating the Guide</span></span>

<span data-ttu-id="e4799-174">Hologramlarınız tamam olduktan sonra kılavuzu çalıştırmayı test edin.</span><span class="sxs-lookup"><span data-stu-id="e4799-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="e4799-175">**İşleç modunu seçin**</span><span class="sxs-lookup"><span data-stu-id="e4799-175">Select **Operator mode**</span></span>
- <span data-ttu-id="e4799-176">Kılavuzun adımlarına tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e4799-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="e4799-177">Kılavuzun nasıl çalıştırıla ilgili daha ayrıntılı rehberlik için şu kaynaklara göz atabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="e4799-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="e4799-178">Dynamics 365 Kılavuzlarında kılavuzu çalıştırmaya genel bakış</span><span class="sxs-lookup"><span data-stu-id="e4799-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="e4799-179">Dynamics 365 Kılavuzlarında operatör olarak Adım kartına yönelin</span><span class="sxs-lookup"><span data-stu-id="e4799-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="e4799-180">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="e4799-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="e4799-181">Kurumsal bağlantılı dağıtım - Bakım</span><span class="sxs-lookup"><span data-stu-id="e4799-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
