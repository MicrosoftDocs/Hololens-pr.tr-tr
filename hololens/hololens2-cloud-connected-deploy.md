---
title: dağıtım kılavuzu – buluta bağlı HoloLens 2 dağıtım, uzaktan yardım dağıtımı ile ölçeklendirerek
description: bir buluta bağlı ağ üzerinden HoloLens cihazları için kayıt ve uzaktan yardım doğrulaması yapmayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635186"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="a7f03-104">Dağıtım-buluta bağlı Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="a7f03-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="a7f03-105">Her şeyi yapılandırdığınıza göre, cihazları dağıtmaya hazır olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="a7f03-106">Ancak, şimdi kurulumunu doğrulamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="a7f03-107">İlk olarak Azure AD JOIN ve MDM kayıt işleminin doğrulanması ve ardından bir uzaktan yardım çağrısının yerleştirilebileceğini doğrulamak gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="a7f03-108">Kayıt doğrulama</span><span class="sxs-lookup"><span data-stu-id="a7f03-108">Enrollment Validation</span></span>

<span data-ttu-id="a7f03-109">Artık her şey Azure AD ve MDM kaydı için düzgün şekilde yapılandırıldığından, Rest artık bir snap olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a7f03-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="a7f03-110">&#39;, Wi-Fi bir bağlantı ve HoloLens cihazının yanı sıra daha önce yapılandırılmış AAD kullanıcı hesaplarından biri gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="a7f03-111">Cihazınız şu anda bir fabrika ayarları durumunda oturur&#39;, [cihazı](/hololens/hololens-recovery#clean-reflash-the-device)yeniden oluşturmak için iyi bir zaman olabilir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="a7f03-112">Cihazınız OOBE 'de olduktan sonra, etkileşime başlamanız ve istemlerin takip etmeniz&#39;gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="a7f03-113">**bu HoloLens sahip Who** sorulduğunda kritik istem ne olur?</span><span class="sxs-lookup"><span data-stu-id="a7f03-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="a7f03-114">**Çalışmalarımı veya okulumu** seçin ve Azure AD hesabınızın kimlik bilgilerini girin.</span><span class="sxs-lookup"><span data-stu-id="a7f03-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="a7f03-115">Kayıt başarılı olduğunda, bir PIN ayarlamanız istenir&#39;.</span><span class="sxs-lookup"><span data-stu-id="a7f03-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="a7f03-116">Bu PIN, bu kullanıcı için bu cihaz için benzersizdir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="a7f03-117">Ayrıca, Iris taramaları, ses verileri ve telemetri ayarları için de istenir ve son olarak, Başlat menüsünü açmayı ve OOBE 'yi tamamlamayı öğrenebilirsiniz&#39;.</span><span class="sxs-lookup"><span data-stu-id="a7f03-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="a7f03-118">karma gerçeklik evine girdikten sonra, yeni öğrendiğiniz **başlangıç hareketini** kullanarak Başlat menüsü açın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="a7f03-119">**Ayarlar** uygulamayı seçip sistem ' i seçin **.**</span><span class="sxs-lookup"><span data-stu-id="a7f03-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="a7f03-120">&#39;, HoloLens 2 cihazınız, daha &quot; &quot; sonra altı karakterli bir dize olacak şekilde, 2 cihazınız için cihazınızın adı görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="a7f03-121">Bu adı bir yere göz atın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-121">Take note of this name.</span></span>

![HoloLens 2 Ayarlar-hakkında](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="a7f03-123">cihazınızın Ayarlar uygulamasında Azure AD 'ye başarıyla kaydedildiğini doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="a7f03-124">**Ayarlar** **hesap**  ->  **erişimi iş veya okul**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a7f03-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="a7f03-125">Bu ekrandan, &quot; _Nameofaad_&#39;s Azure AD 'ye bağlı olarak bakarak başarıyla kaydolduğunu doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="a7f03-126">_YourUserName_ @ _nameofaad_. onmicrosoft.com ile bağlandı &quot; .</span><span class="sxs-lookup"><span data-stu-id="a7f03-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="a7f03-127">cihazın Azure AD 'ye katılmış olduğunu doğrulamak için, [Azure portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **cihazlarındaki** Azure Active Directory denetleyebilir  ->  ve cihaz adında arama yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="a7f03-128">&#39;, cihazın Azure Active Directory bir parçası olduğunu görebileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-cihaz](./images/aad-enrollment.png)

<span data-ttu-id="a7f03-130">daha sonra, [Microsoft Endpoint Manager yönetim merkezinde](https://endpoint.microsoft.com/#home)&#39;ll 'nin oturum açması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="a7f03-131">Oturum açın ve **cihazlar** ' ın ardından **tüm cihazlar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a7f03-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="a7f03-132">buradan HoloLens cihazınızda&#39;adına arama yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a7f03-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="a7f03-133">HoloLens ıntune 'da listelenmiş olarak görebilmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-cihaz](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="a7f03-135">Uzaktan Yardım çağrı doğrulaması</span><span class="sxs-lookup"><span data-stu-id="a7f03-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="a7f03-136">Cihazınızın hem AAD hem de MDM 'nize kaydolduğunu&#39;ve bir test uzaktan yardım çağrısını yerleştirmek için bir süre&#39;.</span><span class="sxs-lookup"><span data-stu-id="a7f03-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="a7f03-137">bu doğrulama için, HoloLens cihazının ve bir Windows 10 bilgisayarın yanı sıra bilgisayar için ikinci bir Azure AD kullanıcı hesabına sahip olmanız&#39;.</span><span class="sxs-lookup"><span data-stu-id="a7f03-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="a7f03-138">Bu doğrulama adımı, son doğrulama adımını daha önce tamamlamış olduğunu ve cihazınızın kaydolduğunu ve Azure AD kullanıcılarınızın cihazda olduğunu varsayacaktır.</span><span class="sxs-lookup"><span data-stu-id="a7f03-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="a7f03-139">bilgisayarınızda zaten yüklü Microsoft Teams yoksa, [Teams buradan indirebilirsiniz](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span><span class="sxs-lookup"><span data-stu-id="a7f03-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="a7f03-140">ikinci Azure AD kullanıcı hesabını, HoloLens oturum açmış olandan daha önce Teams oturum açın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="a7f03-141">Bilgisayarınızda oturum açtıktan sonra, aramayı almaya hazırız.</span><span class="sxs-lookup"><span data-stu-id="a7f03-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="a7f03-142">HoloLens açın ve oturum açın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="a7f03-143">Uzaktan Yardım uygulamasını başlatmak için **Başlat menüsünü** açın ve **Uzaktan Yardım**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a7f03-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="a7f03-144">uzaktan yardım yalnızca bir gelen kutusu uygulaması olarak paketlenmiştir, ancak HoloLens 2&#39;s başlat menüsüne sabitlenmiş.</span><span class="sxs-lookup"><span data-stu-id="a7f03-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="a7f03-145">bir olayda, Başlat menüsü sabitlenmiş olduğunu görmedim&#39;, ardından aramak için **tüm uygulamalar** listesini açın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="a7f03-146">Uzaktan Yardım başladıktan sonra, [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) aracılığıyla cihazın kullanıcısını tanımlamalıdır ve uygulamada oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a7f03-146">Once Remote Assist starts it should identify the user of the device via [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="a7f03-147">Uygulama içinden **Ara** ' yı SEÇIN ve bilgisayarda ikinci Kullanıcı için arama yapın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="a7f03-148">Çağrıyı başlatacak kullanıcıyı seçin.</span><span class="sxs-lookup"><span data-stu-id="a7f03-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="a7f03-149">Bilgisayarınızdan aramayı yanıtlayın.</span><span class="sxs-lookup"><span data-stu-id="a7f03-149">From your PC, answer the call.</span></span>

<span data-ttu-id="a7f03-150">Tebrikler, başarıyla bağlandınız ve Uzaktan Yardım çağrından&#39;.</span><span class="sxs-lookup"><span data-stu-id="a7f03-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="a7f03-151">Şunu kullanarak belirli uzaktan yardım özelliklerini denediğinizden emin olun:</span><span class="sxs-lookup"><span data-stu-id="a7f03-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="a7f03-152">Mürekkep ek açıklamaları</span><span class="sxs-lookup"><span data-stu-id="a7f03-152">Inking annotations</span></span>](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="a7f03-153">Karma Gerçeklik 'te dosya ve Görünüm paylaşma</span><span class="sxs-lookup"><span data-stu-id="a7f03-153">Share a file and view in mixed reality</span></span>](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="a7f03-154">başka bir HoloLens uygulamasında yardım alın</span><span class="sxs-lookup"><span data-stu-id="a7f03-154">Get help in another HoloLens app</span></span>](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="a7f03-155">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="a7f03-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a7f03-156">Buluta bağlı dağıtım-koru</span><span class="sxs-lookup"><span data-stu-id="a7f03-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)