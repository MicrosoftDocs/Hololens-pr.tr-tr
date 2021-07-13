---
title: HoloLens 2. Uygulama Yükleyicisi aracılığıyla uygulamaları yan yükleme ve yükleme
description: Uygulama yükleyicisi ve kullanıcı arabirimi aracılığıyla uygulama yükleme ve yükleme ile uygulama yükleme ve sorunlarını giderme hakkında bilgi edinin.
keywords: uygulama yönetimi, uygulama, hololens, uygulama yükleyicisi
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635594"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="ad933-104">Uygulama Yükleyicisi aracılığıyla HoloLens 2'ye Uygulama Yükleyicisi</span><span class="sxs-lookup"><span data-stu-id="ad933-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="ad933-105">Bu özellik [Holographic 20H2 Windows Aralık 2020 Güncelleştirmesinde kullanılabilir oldu.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="ad933-106">Cihazınızın bu özelliği [kullanmak için](hololens-update-hololens.md) güncelleştirilmiş olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="ad933-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="ad933-107">Uygulamalarınızı **2 cihaza daha Uygulama Yükleyicisi yüklemenize** olanak sağlayan yeni bir özellik (HoloLens) ekledik.</span><span class="sxs-lookup"><span data-stu-id="ad933-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="ad933-108">Özellik, varsayılan **olarak, unmanaged cihazları için açık olur.**</span><span class="sxs-lookup"><span data-stu-id="ad933-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="ad933-109">Kuruluşlarda kesinti yaşanmasını önlemek için uygulama **yükleyicisi şu anda yönetilen cihazlarda** kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ad933-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="ad933-110">Aşağıdakilerden herhangi biri doğruysa **cihaz** "yönetilen" olarak kabul edilir:</span><span class="sxs-lookup"><span data-stu-id="ad933-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="ad933-111">MDM [Kayıtlı](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="ad933-112">Sağlama [paketiyle yapılandırılmış](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="ad933-113">Kullanıcı [Kimliği](hololens-identity.md) Azure AD'dir</span><span class="sxs-lookup"><span data-stu-id="ad933-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="ad933-114">Artık Geliştirici Modunu etkinleştirmeye veya uygulama modunu kullanmaya gerek kalmadan Uygulamaları Cihaz Portalı.</span><span class="sxs-lookup"><span data-stu-id="ad933-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="ad933-115">Appx Paketi'Microsoft Edge USB üzerinden veya Microsoft Edge üzerinden) indirin ve yükleme işlemini başlatması Dosya Gezgini appx paketine gidin.</span><span class="sxs-lookup"><span data-stu-id="ad933-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="ad933-116">Alternatif olarak, [bir web sayfasından yükleme başlatabilirsiniz.](/windows/msix/app-installer/installing-windows10-apps-web)</span><span class="sxs-lookup"><span data-stu-id="ad933-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="ad933-117">MDM'nin LOB Uygulaması dağıtım özelliğini kullanarak Microsoft Store veya sideload'tan yüklemiş olduğu gibi, uygulamaların [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) da İmza [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) Aracı ile dijital olarak imzalanacak ve uygulama dağıtılamadan önce imzalamak için kullanılan sertifikanın HoloLens cihazı tarafından güvenilir olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad933-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad933-118">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ad933-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="ad933-119">Cihazlarınız için:</span><span class="sxs-lookup"><span data-stu-id="ad933-119">For your devices:</span></span>

<span data-ttu-id="ad933-120">Bu özellik şu anda HoloLens 2 cihazlar için Holographic 20H2 Windows derlemelerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ad933-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="ad933-121">Bu yöntemi kullanan tüm cihazların güncelleştirilmiş olduğundan emin [olun.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="ad933-122">Uygulamalarınız için:</span><span class="sxs-lookup"><span data-stu-id="ad933-122">For your apps:</span></span>

<span data-ttu-id="ad933-123">Uygulamanın depodan bağımlılıkları **kullanmayacak** olması **nedeniyle,** Uygulama Yükleyicisi Çözüm Yapılandırması ana veya yayın olabilir.</span><span class="sxs-lookup"><span data-stu-id="ad933-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="ad933-124">Uygulama paketleri oluşturma [hakkında daha fazla bilgi için bkz.](/windows/msix/app-installer/create-appinstallerfile-vs).</span><span class="sxs-lookup"><span data-stu-id="ad933-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="ad933-125">Bu yöntem aracılığıyla yüklenmiş olan uygulamaların dijital olarak imzaya sahip olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad933-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="ad933-126">Uygulamayı imzalamak için bir sertifika kullansanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad933-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="ad933-127">MS Güvenilen CA Listesinden bir [sertifika alır ve](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)bu durumda ek işlem yapmak zorunda olmaznız.</span><span class="sxs-lookup"><span data-stu-id="ad933-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="ad933-128">Öte yandan kendi sertifikanızı da imzalarsanız bu sertifikanın cihaza da itilmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ad933-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="ad933-129">İmza Aracı'nı [kullanarak uygulamaları imzalama.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="ad933-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="ad933-130">**Sertifika seçenekleri:**</span><span class="sxs-lookup"><span data-stu-id="ad933-130">**Certificate options:**</span></span>

- [<span data-ttu-id="ad933-131">MS Güvenilen CA Listesi</span><span class="sxs-lookup"><span data-stu-id="ad933-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="ad933-132">**Bir sertifika dağıtım yöntemi seçin.**</span><span class="sxs-lookup"><span data-stu-id="ad933-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="ad933-133">[Sağlama Paketleri](hololens-provisioning.md) yerel cihazlara uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="ad933-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="ad933-134">MDM, cihaz [yapılandırmaları ile sertifikaları uygulamak için kullanılabilir.](/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="ad933-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="ad933-135">Cihazda Sertifika [Yöneticisi'ni kullanın.](certificate-manager.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="ad933-136">Yükleme yöntemi</span><span class="sxs-lookup"><span data-stu-id="ad933-136">Installation method</span></span>

1. <span data-ttu-id="ad933-137">Cihazınızın yönetilen olarak kabul olmadığını kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="ad933-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="ad933-138">HoloLens 2 cihazınızın açık olduğunu ve oturum açık olduğunu kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="ad933-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="ad933-139">Bilgisayarınızda özel uygulamanıza gidin ve yourapp.appxbundle'ı yourdevicename\Internal Depolama\Downloads dizinine kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="ad933-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="ad933-140">Dosyanızı kopyalamayı bitirdikten sonra cihazınızın bağlantısını keserek yüklemesini daha sonra tamamabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad933-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="ad933-141">2 HoloLens Başlat Menüsünü **açın,** **Başlat'ı Tüm uygulamalar** seçin ve **Dosya Gezgini** açın.</span><span class="sxs-lookup"><span data-stu-id="ad933-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="ad933-142">İndirilenler klasörüne gidin.</span><span class="sxs-lookup"><span data-stu-id="ad933-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="ad933-143">Uygulamanın sol panelinde Önce Bu cihaz'ı **seçmeniz** ve ardından İndirilenler'e gitmek zorundayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ad933-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="ad933-144">yourapp.appxbundle dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="ad933-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="ad933-145">Uygulama Yükleyicisi başlatacak.</span><span class="sxs-lookup"><span data-stu-id="ad933-145">The App Installer will launch.</span></span> <span data-ttu-id="ad933-146">Uygulamayı **yüklemek** için Yükle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="ad933-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="ad933-147">Yüklü uygulama, yükleme tamamlandıktan sonra otomatik olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="ad933-147">The installed app will automatically launch upon the completion of installing.</span></span>

![UYGULAMA YÜKLEYICISI aracılığıyla MRTK Örnekleri Uygulama Yükleyicisi](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="ad933-149">Yükleme sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="ad933-149">Troubleshooting Installs</span></span>

<span data-ttu-id="ad933-150">Uygulamanız yüklenemediyse, sorun gidermek için aşağıdakilere göz açın:</span><span class="sxs-lookup"><span data-stu-id="ad933-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="ad933-151">Uygulamanız bir Ana veya Yayın derlemesi.</span><span class="sxs-lookup"><span data-stu-id="ad933-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="ad933-152">Cihazınız, bu özelliğin kullanılabilir olduğu bir derlemeye güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="ad933-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="ad933-153">[İnternet'e bağlandınız.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="ad933-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="ad933-154">Uç [noktalarınız Microsoft Store](hololens-offline.md) yapılandırılmış.</span><span class="sxs-lookup"><span data-stu-id="ad933-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="ad933-155">Web Yükleyicisi</span><span class="sxs-lookup"><span data-stu-id="ad933-155">Web Installer</span></span>

<span data-ttu-id="ad933-156">Kullanıcılar bir uygulamayı doğrudan bir web sunucusundan yükleyebilir.</span><span class="sxs-lookup"><span data-stu-id="ad933-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="ad933-157">Bu akış, kolay Uygulama Yükleyicisi yükleme dağıtım yöntemiyle birlikte uygulamanın kullanımını kullanır.</span><span class="sxs-lookup"><span data-stu-id="ad933-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="ad933-158">Web yüklemesini ayarlama:</span><span class="sxs-lookup"><span data-stu-id="ad933-158">How to set up web install:</span></span>

1. <span data-ttu-id="ad933-159">Uygulamanın yüklemek için doğru yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="ad933-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="ad933-160">Bir [web sayfasından yüklemeyi etkinleştirmek için bu adımları izleyin.](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)</span><span class="sxs-lookup"><span data-stu-id="ad933-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="ad933-161">Son kullanıcı deneyimi:</span><span class="sxs-lookup"><span data-stu-id="ad933-161">End user experience:</span></span>

1. <span data-ttu-id="ad933-162">Kullanıcı yukarıda daha önce seçilen bir yöntemi kullanarak sertifikayı alır ve cihaza yüklür.</span><span class="sxs-lookup"><span data-stu-id="ad933-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="ad933-163">Kullanıcı yukarıdaki adımdan oluşturulan URL'yi ziyaret ediyor.</span><span class="sxs-lookup"><span data-stu-id="ad933-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="ad933-164">Uygulama artık cihaza yüklenir.</span><span class="sxs-lookup"><span data-stu-id="ad933-164">The app will now install to the device.</span></span> <span data-ttu-id="ad933-165">Uygulamayı bulmak için Başlat menüsü **açın** ve Tüm uygulamalar **düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="ad933-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="ad933-166">Uygulama yükleyicisi yükleme yönteminin sorunlarını giderme hakkında daha fazla yardım için uygulama [yükleyicisi sorunlarını giderme'ye bakın.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="ad933-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="ad933-167">Güncelleştirme işlemi sırasında kullanıcı arabirimi desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ad933-167">UI during the update process is not supported.</span></span> <span data-ttu-id="ad933-168">Bu nedenle bu sayfada GösterPrompt [seçeneği](/windows/msix/app-installer/update-settings) ve ilgili seçenekler desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ad933-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="ad933-169">Örnek Uygulamalar</span><span class="sxs-lookup"><span data-stu-id="ad933-169">Sample Apps</span></span>

<span data-ttu-id="ad933-170">Kullanılabilir örnek Uygulama Yükleyicisi uygulamalarımızın birini deneyin.</span><span class="sxs-lookup"><span data-stu-id="ad933-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="ad933-171">Örnek uygulamalar</span><span class="sxs-lookup"><span data-stu-id="ad933-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
