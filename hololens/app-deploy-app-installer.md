---
title: HoloLens 2 uygulama yükleyicisi aracılığıyla uygulamaları dışarıdan yükleme ve yükleme
description: Uygulama Yükleyicisi ve dışarıdan yükleme ve uygulamaları kullanıcı arabirimi aracılığıyla yükleme hakkında bilgi edinin.
keywords: Uygulama yönetimi, uygulama, Hololens, uygulama yükleyicisi
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378999"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="5a58b-104">Uygulama yükleyicisi aracılığıyla HoloLens 2 ' ye uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="5a58b-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="5a58b-105">Bu özellik [Windows holographic, sürüm 20H2 – aralık 2020 güncelleştirmesi](hololens-release-notes.md)' nde kullanıma sunulmuştur.</span><span class="sxs-lookup"><span data-stu-id="5a58b-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="5a58b-106">Cihazınızın bu özelliği kullanacak şekilde [güncelleştirildiğinden](hololens-update-hololens.md) emin olun.</span><span class="sxs-lookup"><span data-stu-id="5a58b-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="5a58b-107">HoloLens 2 cihazlarınızda **uygulamaları daha sorunsuz bir şekilde yüklemenize imkan tanımak için yeni bir yetenek (App Installer) ekledik** .</span><span class="sxs-lookup"><span data-stu-id="5a58b-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="5a58b-108">Özelliği, **yönetilmeyen cihazlar için varsayılan olarak açık** olacaktır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="5a58b-109">Kurumların kesintiye uğramasını önlemek için, uygulama yükleyicisi Şu anda **Yönetilen cihazlarda kullanılamayacak** .</span><span class="sxs-lookup"><span data-stu-id="5a58b-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="5a58b-110">**Aşağıdakilerden biri doğruysa** bir cihaz "yönetilen" olarak değerlendirilir:</span><span class="sxs-lookup"><span data-stu-id="5a58b-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="5a58b-111">MDM [kaydı](hololens-enroll-mdm.md) yapılmış</span><span class="sxs-lookup"><span data-stu-id="5a58b-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="5a58b-112">[Sağlama paketiyle](hololens-provisioning.md) yapılandırıldı</span><span class="sxs-lookup"><span data-stu-id="5a58b-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="5a58b-113">Kullanıcı [kimliği](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="5a58b-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="5a58b-114">Artık Geliştirici modunu etkinleştirmek veya cihaz portalını kullanmak gerekmeden uygulama yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="5a58b-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="5a58b-115">Cihazınıza appx paketini indirin (USB veya Microsoft Edge üzerinden) ve yüklemeyi başlatma isteminde bulunulacak dosya Gezgini 'ndeki appx grubuna gidin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="5a58b-116">Alternatif olarak, [bir Web sayfasından bir yüklemeyi başlatabilirsiniz](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="5a58b-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="5a58b-117">MDM 'nin LOB uygulaması dağıtım özelliğini kullanarak Microsoft Store veya dışarıdan yüklemeden yüklediğiniz uygulamalar gibi uygulamalar, [Imza aracı](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) ile dijital olarak imzalanmalıdır ve uygulamanın dağıtılması [için, imzalama için kullanılan sertifikaya](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) , Hololens cihazı tarafından güvenilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a58b-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="5a58b-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="5a58b-119">Cihazlarınız için:</span><span class="sxs-lookup"><span data-stu-id="5a58b-119">For your devices:</span></span>

<span data-ttu-id="5a58b-120">Bu özellik şu anda HoloLens 2 cihazları için Windows holographic 20H2 Derlemeleriyle sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="5a58b-121">Bu yöntemi kullanan cihazların [güncelleştirildiğinden](hololens-update-hololens.md)emin olun.</span><span class="sxs-lookup"><span data-stu-id="5a58b-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="5a58b-122">Uygulamalarınız için:</span><span class="sxs-lookup"><span data-stu-id="5a58b-122">For your apps:</span></span>

<span data-ttu-id="5a58b-123">Uygulama yükleyicisi depodan bağımlılıklar kullanacağı için uygulamanızın çözüm yapılandırması **ana** veya **Sürüm** olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="5a58b-124">[Uygulama paketleri oluşturma](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)hakkında daha fazla bilgi için bkz..</span><span class="sxs-lookup"><span data-stu-id="5a58b-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="5a58b-125">Bu yöntem aracılığıyla yüklenen uygulamaların dijital olarak imzalanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="5a58b-126">Uygulamayı imzalamak için bir sertifika kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="5a58b-127">[MS GÜVENILEN CA listesinden](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)bir sertifika alabilirsiniz, bu durumda herhangi bir ek eylem gerçekleştirmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="5a58b-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="5a58b-128">Ya da kendi sertifikanızı imzalayabilirsiniz, ancak sertifikanın cihaza itilmesi gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="5a58b-129">[Imza aracını kullanarak](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) uygulamaları imzalama.</span><span class="sxs-lookup"><span data-stu-id="5a58b-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="5a58b-130">**Sertifika seçenekleri:**</span><span class="sxs-lookup"><span data-stu-id="5a58b-130">**Certificate options:**</span></span>

- [<span data-ttu-id="5a58b-131">MS güvenilen CA listesi</span><span class="sxs-lookup"><span data-stu-id="5a58b-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="5a58b-132">**Bir sertifika dağıtım yöntemi seçin.**</span><span class="sxs-lookup"><span data-stu-id="5a58b-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="5a58b-133">[Sağlama paketleri](hololens-provisioning.md) , yerel cihazlara uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="5a58b-134">MDM, [cihaz yapılandırmalarına sahip sertifikalar uygulamak](https://docs.microsoft.com/mem/intune/protect/certificates-configure)için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="5a58b-135">Cihaz [Sertifika Yöneticisi](certificate-manager.md)' ni kullanın.</span><span class="sxs-lookup"><span data-stu-id="5a58b-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="5a58b-136">Yükleme yöntemi</span><span class="sxs-lookup"><span data-stu-id="5a58b-136">Installation method</span></span>

1. <span data-ttu-id="5a58b-137">Cihazınızın yönetilen olarak değerlendirilmediğini denetleyin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="5a58b-138">HoloLens 2 cihazınızın açık olup olmadığını ve oturum açtığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="5a58b-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="5a58b-139">Bilgisayarınızda özel uygulamanıza gidin ve App. appxpaketi ' ni Devicename\ınternal Storage\downloadcopy dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="5a58b-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="5a58b-140">Dosyanızı kopyalamayı tamamladıktan sonra cihazınızın bağlantısını kesebilir ve yüklemeyi daha sonra tamamlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="5a58b-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="5a58b-141">HoloLens 2 cihazınızdan **Başlat menüsünü** açın, **tüm uygulamalar** ' ı seçin ve **Dosya Gezgini** uygulamasını başlatın.</span><span class="sxs-lookup"><span data-stu-id="5a58b-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="5a58b-142">Indirmeler klasörüne gidin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="5a58b-143">Uygulamanın sol panelinde **Bu cihazı** önce seçin, sonra İndirmeler ' a gidin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="5a58b-144">Yourapp. appxpaket dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="5a58b-145">Uygulama yükleyicisi başlatılır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-145">The App Installer will launch.</span></span> <span data-ttu-id="5a58b-146">Uygulamanızı yüklemek için **Install** (Çalıştır) düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="5a58b-147">Yüklenen uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Uygulama yükleyicisi aracılığıyla MRTK örnekleri yükleme](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="5a58b-149">Yükleme sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="5a58b-149">Troubleshooting Installs</span></span>

<span data-ttu-id="5a58b-150">Uygulamanız yüklenemedi, sorun gidermek için aşağıdakileri denetleyin:</span><span class="sxs-lookup"><span data-stu-id="5a58b-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="5a58b-151">Uygulamanız bir ana veya yayın yapımı.</span><span class="sxs-lookup"><span data-stu-id="5a58b-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="5a58b-152">Cihazınız, bu özelliğin kullanılabildiği bir yapıya güncelleştirildi.</span><span class="sxs-lookup"><span data-stu-id="5a58b-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="5a58b-153">[İnternet 'e bağlısınız](hololens-network.md).</span><span class="sxs-lookup"><span data-stu-id="5a58b-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="5a58b-154">[Microsoft Store uç noktalarınız](hololens-offline.md) doğru şekilde yapılandırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="5a58b-155">Web Yükleyicisi</span><span class="sxs-lookup"><span data-stu-id="5a58b-155">Web Installer</span></span>

<span data-ttu-id="5a58b-156">Kullanıcılar, bir uygulamayı doğrudan bir Web sunucusundan yükleyebilir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="5a58b-157">Bu akış, kolay bir indirme ve yükleme dağıtım yöntemiyle birleştirilmiş uygulama yükleyicisini kullanır.</span><span class="sxs-lookup"><span data-stu-id="5a58b-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="5a58b-158">Web yüklemesini ayarlama:</span><span class="sxs-lookup"><span data-stu-id="5a58b-158">How to set up web install:</span></span>

1. <span data-ttu-id="5a58b-159">Uygulamanızın yüklenmek üzere doğru yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="5a58b-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="5a58b-160">[Web sayfasından yüklemeyi etkinleştirmek için bu adımları](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)izleyin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="5a58b-161">Son Kullanıcı deneyimi:</span><span class="sxs-lookup"><span data-stu-id="5a58b-161">End user experience:</span></span>

1. <span data-ttu-id="5a58b-162">Kullanıcı, yukarıda daha önce seçilmiş olan bir yöntemi kullanarak cihaza sertifikayı alır ve kurar.</span><span class="sxs-lookup"><span data-stu-id="5a58b-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="5a58b-163">Kullanıcı, yukarıdaki adımdan oluşturulan URL 'YI ziyaret ettiğinde.</span><span class="sxs-lookup"><span data-stu-id="5a58b-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="5a58b-164">Uygulama artık cihaza yüklenir.</span><span class="sxs-lookup"><span data-stu-id="5a58b-164">The app will now install to the device.</span></span> <span data-ttu-id="5a58b-165">Uygulamayı bulmak için **Başlat menüsünü** açın ve uygulamanızı bulmak için **tüm uygulamalar** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="5a58b-166">Uygulama yükleyicisi yükleme yöntemiyle ilgili sorun giderme hakkında daha fazla yardım için [uygulama yükleyicisi sorunlarını giderme](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)makalesini ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="5a58b-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="5a58b-167">Güncelleştirme işlemi sırasında kullanıcı arabirimi desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="5a58b-167">UI during the update process is not supported.</span></span> <span data-ttu-id="5a58b-168">Bu nedenle, [Bu sayfadaki](https://docs.microsoft.com/windows/msix/app-installer/update-settings) ShowPrompt seçeneği ve ilgili seçenekler desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="5a58b-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="5a58b-169">Örnek Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="5a58b-169">Sample Apps</span></span>

<span data-ttu-id="5a58b-170">Uygulama yükleyicisini bazı örnek uygulamalarla denemek için bazı mevcut örneklerimizden göz atın:</span><span class="sxs-lookup"><span data-stu-id="5a58b-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="5a58b-171">MRTK örnekleri Merkezi</span><span class="sxs-lookup"><span data-stu-id="5a58b-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="5a58b-172">Leri</span><span class="sxs-lookup"><span data-stu-id="5a58b-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="5a58b-173">Test için kullanılabilen UWP örnek uygulamaları</span><span class="sxs-lookup"><span data-stu-id="5a58b-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
