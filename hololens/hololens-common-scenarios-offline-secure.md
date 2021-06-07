---
title: Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2
description: HoloLens cihazları için sağlama ile çevrimdışı güvenli dağıtım ve uygulama dağıtım senaryosu ayarlamayı öğrenin.
keywords: HoloLens, yönetim, çevrimdışı, çevrimdışı güvenli
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378961"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="bffb4-104">Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="bffb4-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="bffb4-105">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="bffb4-105">Overview</span></span>

<span data-ttu-id="bffb4-106">Bu kılavuz, aşağıdaki kısıtlamalarla güvenli ortamlarda kullanmak üzere HoloLens 2'nin kilitlenmesini sağlayan örnek sağlama paketini uygulamaya yönelik kılavuz sağlar:</span><span class="sxs-lookup"><span data-stu-id="bffb4-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="bffb4-107">WiFi'yi devre dışı bırakma.</span><span class="sxs-lookup"><span data-stu-id="bffb4-107">Disable WiFi.</span></span>
-   <span data-ttu-id="bffb4-108">BlueTooth'ı devre dışı bırakma.</span><span class="sxs-lookup"><span data-stu-id="bffb4-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="bffb4-109">Mikrofonları devre dışı bırakma.</span><span class="sxs-lookup"><span data-stu-id="bffb4-109">Disable Microphones.</span></span>
-   <span data-ttu-id="bffb4-110">Sağlama paketleri eklemeyi veya kaldırmayı önler.</span><span class="sxs-lookup"><span data-stu-id="bffb4-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="bffb4-111">Hiçbir kullanıcı, yukarıdaki kısıtlı bileşenlerden herhangi birini etkinleştiremz.</span><span class="sxs-lookup"><span data-stu-id="bffb4-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="bffb4-112">[![Çevrimdışı Güvenli senaryosu ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="bffb4-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="bffb4-113">Hazırlama</span><span class="sxs-lookup"><span data-stu-id="bffb4-113">Prepare</span></span>

<span data-ttu-id="bffb4-114">Windows 10 Pc Kurulumu</span><span class="sxs-lookup"><span data-stu-id="bffb4-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="bffb4-115">[En son HoloLens 2 işletim sistemi dosyasını doğrudan](https://aka.ms/hololens2download) bir bilgisayara indirin.</span><span class="sxs-lookup"><span data-stu-id="bffb4-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="bffb4-116">Bu yapılandırma için destek, Derleme 19041.1117 ve üzeri'ne dahildir.</span><span class="sxs-lookup"><span data-stu-id="bffb4-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="bffb4-117">Gelişmiş Kurtarma Yardımcı Aracı'nı (ARC) [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) bilgisayarınıza indirin/yükleyin</span><span class="sxs-lookup"><span data-stu-id="bffb4-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="bffb4-118">En son Windows Yapılandırma [Tasarımcısı (WCD) aracını](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) indirin/yükleyin Microsoft Store bilgisayarınıza yükleyin.</span><span class="sxs-lookup"><span data-stu-id="bffb4-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="bffb4-119">[PPKG'OfflineSecureHL2_Sample oluşturmak için proje dosyalarıyla](https://aka.ms/HoloLensDocs-SecureOfflineSample) birlikte OfflineSecureHL2_Sample klasörünü indirin.</span><span class="sxs-lookup"><span data-stu-id="bffb4-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="bffb4-120">Çevrimdışı İş [Hattı uygulamanızı PPKG dağıtımı için hazırlayın.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="bffb4-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="bffb4-121">Yapılandırma</span><span class="sxs-lookup"><span data-stu-id="bffb4-121">Configure</span></span>

<span data-ttu-id="bffb4-122">Güvenli Yapılandırma Sağlama Paketi Oluşturma</span><span class="sxs-lookup"><span data-stu-id="bffb4-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="bffb4-123">Bilgisayarınızda WCD aracını başlatma.</span><span class="sxs-lookup"><span data-stu-id="bffb4-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="bffb4-124">Dosya **-> Proje aç'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="bffb4-125">Daha önce kaydedilen OfflineSecureHL2_Sample klasörüne gidin ve şu seçeneği OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="bffb4-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="bffb4-126">Proje açılmalı ve artık Kullanılabilir Özelleştirmeler'in bir listesine sahipsiniz:</span><span class="sxs-lookup"><span data-stu-id="bffb4-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bffb4-127">![WCD'de açık yapılandırma paketinin ekran görüntüsü](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="bffb4-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="bffb4-128">Bu sağlama paketinde ayarlanmış yapılandırmalar:</span><span class="sxs-lookup"><span data-stu-id="bffb4-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="bffb4-129">Öğe</span><span class="sxs-lookup"><span data-stu-id="bffb4-129">Item</span></span>                                                |     <span data-ttu-id="bffb4-130">Ayar</span><span class="sxs-lookup"><span data-stu-id="bffb4-130">Setting</span></span>                       |     <span data-ttu-id="bffb4-131">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bffb4-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="bffb4-132">Hesaplar / Kullanıcılar</span><span class="sxs-lookup"><span data-stu-id="bffb4-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="bffb4-133">Yerel Kullanıcı Adı & Parolası</span><span class="sxs-lookup"><span data-stu-id="bffb4-133">Local User Name & Password</span></span>    |     <span data-ttu-id="bffb4-134">Bu çevrimdışı cihazlar için tek bir kullanıcı adı ve parola ayar olmalı ve cihazın tüm kullanıcıları tarafından paylaşılır.</span><span class="sxs-lookup"><span data-stu-id="bffb4-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="bffb4-135">İlk Deneyim / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="bffb4-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="bffb4-136">Doğru</span><span class="sxs-lookup"><span data-stu-id="bffb4-136">True</span></span>                          |     <span data-ttu-id="bffb4-137">Yalnızca ilk cihaz kurulumu sırasında ayarlamayı atlar</span><span class="sxs-lookup"><span data-stu-id="bffb4-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="bffb4-138">İlk Deneyim / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="bffb4-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="bffb4-139">Doğru</span><span class="sxs-lookup"><span data-stu-id="bffb4-139">True</span></span>                          |     <span data-ttu-id="bffb4-140">İlk cihaz kurulumu sırasında cihaz eğitimlerini atlar</span><span class="sxs-lookup"><span data-stu-id="bffb4-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="bffb4-141">İlk Deneyim / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="bffb4-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="bffb4-142">Doğru</span><span class="sxs-lookup"><span data-stu-id="bffb4-142">True</span></span>                          |     <span data-ttu-id="bffb4-143">İlk Wi-Fi sırasında yapılandırmayı atlar</span><span class="sxs-lookup"><span data-stu-id="bffb4-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="bffb4-144">İlkeler/Bağlantı/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="bffb4-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="bffb4-145">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-145">No</span></span>                            |     <span data-ttu-id="bffb4-146">Bluetooth'u devre dışı bırakma</span><span class="sxs-lookup"><span data-stu-id="bffb4-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="bffb4-147">İlkeler/Deneyim/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="bffb4-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="bffb4-148">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-148">No</span></span>                            |     <span data-ttu-id="bffb4-149">Cortana'yı devre dışı (mikrofonlar devre dışı bırakıldıklarında olası sorunları ortadan kaldırmak için)</span><span class="sxs-lookup"><span data-stu-id="bffb4-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="bffb4-150">İlkeler/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="bffb4-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="bffb4-151">Yes</span><span class="sxs-lookup"><span data-stu-id="bffb4-151">Yes</span></span>                           |     <span data-ttu-id="bffb4-152">Mikrofonu Devre Dışı Bırakıyor</span><span class="sxs-lookup"><span data-stu-id="bffb4-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="bffb4-153">İlkeler/Gizlilik/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="bffb4-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="bffb4-154">Reddetmeye zorlama</span><span class="sxs-lookup"><span data-stu-id="bffb4-154">Force deny</span></span>                    |     <span data-ttu-id="bffb4-155">Uygulamaların Konum verilerine erişmeye çalışmasını önler (Konum izleme devre dışı bırakılmıştır)</span><span class="sxs-lookup"><span data-stu-id="bffb4-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="bffb4-156">İlkeler/Gizlilik/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="bffb4-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="bffb4-157">Reddetmeye zorlama</span><span class="sxs-lookup"><span data-stu-id="bffb4-157">Force deny</span></span>                    |     <span data-ttu-id="bffb4-158">Uygulamaların Mikrofonlara erişmeye çalışmasını önler (Mikrofonlar devre dışı bırakılmıştır)</span><span class="sxs-lookup"><span data-stu-id="bffb4-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="bffb4-159">İlkeler/Güvenlik/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="bffb4-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="bffb4-160">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-160">No</span></span>                            |     <span data-ttu-id="bffb4-161">Kilitlenmiş ilkeleri geçersiz kılmaya çalışan sağlama paketleri eklemesini önler.</span><span class="sxs-lookup"><span data-stu-id="bffb4-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="bffb4-162">İlkeler/Güvenlik/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="bffb4-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="bffb4-163">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-163">No</span></span>                            |     <span data-ttu-id="bffb4-164">Kilitlenmiş bu sağlama paketini herkesin kaldırmasını önler.</span><span class="sxs-lookup"><span data-stu-id="bffb4-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="bffb4-165">İlkeler/Sistem/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="bffb4-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="bffb4-166">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-166">No</span></span>                            |     <span data-ttu-id="bffb4-167">Cihazın konum verilerini izlemesini önler.</span><span class="sxs-lookup"><span data-stu-id="bffb4-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="bffb4-168">İlkeler/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="bffb4-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="bffb4-169">Hayır</span><span class="sxs-lookup"><span data-stu-id="bffb4-169">No</span></span>                            |     <span data-ttu-id="bffb4-170">Devre dışı Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="bffb4-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="bffb4-171">Çalışma Zamanı Ayarları altında Hesaplar **/ Kullanıcılar / KullanıcıAdı: Holo / Password öğesini seçin.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="bffb4-172">İsterseniz parolayı not edin ve sıfırlayın.</span><span class="sxs-lookup"><span data-stu-id="bffb4-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="bffb4-173">UniversalAppInstall / UserContextApp'e gidin ve bu cihazlara dağıtacakları [LOB](app-deploy-provisioning-package.md) uygulamasını yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="bffb4-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bffb4-174">![WCD'de uygulamanın nereye ekli olduğunu ekran görüntüsü.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="bffb4-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="bffb4-175">Tamamlandıktan sonra "Dışarı Aktar" düğmesini seçin ve sağlama paketiniz oluşturulana kadar tüm istemleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="bffb4-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bffb4-176">![WCD'de bu paket için Dışarı Aktar düğmesinin ekran görüntüsü.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="bffb4-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="bffb4-177">Dağıtma</span><span class="sxs-lookup"><span data-stu-id="bffb4-177">Deploy</span></span>

1. <span data-ttu-id="bffb4-178">HL2'i USB kablosu Windows 10 bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="bffb4-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="bffb4-179">ARC aracını başlatma ve **HoloLens 2'yi seçme**</span><span class="sxs-lookup"><span data-stu-id="bffb4-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 temiz reflash ilk ekranı](images/ARC2.png)

1. <span data-ttu-id="bffb4-181">Sonraki ekranda El ile paket **seçimi'ne tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC bilgi ekranı](images/arc_device_info.png)

1. <span data-ttu-id="bffb4-183">Daha önce indirilen .ffu dosyasına gidin ve Aç'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="bffb4-184">Uyarı sayfasında Devam'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC uyarı ekranı](images/arc_warning.png)

1. <span data-ttu-id="bffb4-186">ARC aracının HoloLens 2 işletim sistemi yükleme işlemini tamamlaması için bekleyin.</span><span class="sxs-lookup"><span data-stu-id="bffb4-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="bffb4-187">Cihaz yükleme ve yeniden yükleme işlemini tamamlandıktan sonra bilgisayarınızdan Dosya Gezgini'ye gidin ve daha önce kaydedilen PPKG dosyasını cihaz klasörüne kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="bffb4-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bffb4-188">![Dosya Gezgini penceresindeki PC'de PPKG dosyası.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="bffb4-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="bffb4-189">HoloLens 2'de aşağıdaki düğme birleşik tuşuna basarak Sağlama  Paketini çalıştırın: Birim Kapalı ve Güç Düğmesi'ne **aynı** anda dokunun.</span><span class="sxs-lookup"><span data-stu-id="bffb4-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="bffb4-190">Sağlama Paketi'nin uygulanarak Onayla'nın seçili olması **istenir**</span><span class="sxs-lookup"><span data-stu-id="bffb4-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="bffb4-191">Sağlama paketi tamamlandıktan sonra Tamam'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="bffb4-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="bffb4-192">Daha sonra cihazda paylaşılan yerel hesap ve parolayla oturum açmanız istendiğinde.</span><span class="sxs-lookup"><span data-stu-id="bffb4-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="bffb4-193">Bakım</span><span class="sxs-lookup"><span data-stu-id="bffb4-193">Maintain</span></span>

<span data-ttu-id="bffb4-194">Bu yapılandırmayla, yukarıdaki işlemi yeniden başlatmanız ve ARC aracıyla cihaza ters eğik çizgi uygulamanız ve işletim sistemi ve/veya uygulamalarda güncelleştirme yapmak için yeni bir PPKG uygulamanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="bffb4-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
