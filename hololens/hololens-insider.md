---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleriyle çalışmaya başlamayı ve HoloLens için bir sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamayı öğrenin.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924375"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="3637b-103">Microsoft HoloLens için Insider önizlemesi</span><span class="sxs-lookup"><span data-stu-id="3637b-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="3637b-104">HoloLens için en son Insider Preview derlemesine hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="3637b-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="3637b-105">HoloLens için [bir sonraki büyük](hololens-insider.md#start-receiving-insider-builds) işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamak ve çalışmaya başlamanız oldukça kolaydır.</span><span class="sxs-lookup"><span data-stu-id="3637b-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="3637b-106">Windows Insider Sürüm Notları</span><span class="sxs-lookup"><span data-stu-id="3637b-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="3637b-107">Windows Insider'lara yeni özelliklerle yeniden uçuş yapmaya başlamak için heyecanlanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="3637b-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="3637b-108">En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır.</span><span class="sxs-lookup"><span data-stu-id="3637b-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="3637b-109">Yeni derlemelerimize daha fazla özellik ve güncelleştirme eklerken bu sayfayı Windows Insider devam edeceğiz.</span><span class="sxs-lookup"><span data-stu-id="3637b-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="3637b-110">Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun.</span><span class="sxs-lookup"><span data-stu-id="3637b-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="3637b-111">HoloLens'de CSP değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="3637b-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="3637b-112">Windows Insider derlemesinde tanıtıldı, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="3637b-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="3637b-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="3637b-113">DevDetail CSP</span></span>

<span data-ttu-id="3637b-114">DevDetail CSP artık HoloLens cihazında boş depolama alanı da rapor ediyor.</span><span class="sxs-lookup"><span data-stu-id="3637b-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="3637b-115">Bu değer, Ayarlar Uygulamasının Depolama sayfasında gösterilen değerle yaklaşık olarak eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="3637b-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="3637b-116">Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer aleladedir.</span><span class="sxs-lookup"><span data-stu-id="3637b-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="3637b-117">./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)</span><span class="sxs-lookup"><span data-stu-id="3637b-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="3637b-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="3637b-118">DeviceStatus CSP</span></span>

<span data-ttu-id="3637b-119">DeviceStatus CSP artık HoloLens'in etkin olarak bağlı olduğu WiFi ağının SSID ve BSSID'lerini de rapor ediyor.</span><span class="sxs-lookup"><span data-stu-id="3637b-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="3637b-120">Aşağıda bu bilgileri içeren belirli düğümler yer almaktadır.</span><span class="sxs-lookup"><span data-stu-id="3637b-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="3637b-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/SSID</span><span class="sxs-lookup"><span data-stu-id="3637b-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="3637b-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/BSSID</span><span class="sxs-lookup"><span data-stu-id="3637b-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="3637b-123">NetworkIdentifiers sorgulamak için örnek syncml blobu (MDM satıcıları için)</span><span class="sxs-lookup"><span data-stu-id="3637b-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="3637b-124">Düzeltmeler ve geliştirmeler:</span><span class="sxs-lookup"><span data-stu-id="3637b-124">Fixes and improvements:</span></span>

- <span data-ttu-id="3637b-125">Kilitlenmiş [dosyaların indir Cihaz Portalı isteminin olmadığının bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="3637b-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="3637b-126">Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="3637b-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="3637b-127">Insider derlemelerini almaya başlama</span><span class="sxs-lookup"><span data-stu-id="3637b-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="3637b-128">Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="3637b-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="3637b-129">"Cihazı yeniden başlat" sesli komutu iyi çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="3637b-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="3637b-130">Yeniden başlat düğmesini Ayarlar/Windows Insider Programı.</span><span class="sxs-lookup"><span data-stu-id="3637b-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="3637b-131">Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.</span><span class="sxs-lookup"><span data-stu-id="3637b-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="3637b-132">HoloLens 2 cihazında Ayarlar  >  **Güncelleştirmesi & Security**  >  **Windows Insider Programı'e** gidin ve Kullanmaya başlayın.</span><span class="sxs-lookup"><span data-stu-id="3637b-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="3637b-133">Hesap olarak kaydetmek için kullanılan hesabı Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="3637b-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="3637b-134">Windows insider artık Kanallar'a taşınıyor.</span><span class="sxs-lookup"><span data-stu-id="3637b-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="3637b-135">Hızlı **halka** Geliştirme **Kanalı,** Yavaş  halka Beta Kanal olur **ve** **Yayın** Önizleme halkası Yayın Önizleme Kanalı **olur.**</span><span class="sxs-lookup"><span data-stu-id="3637b-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="3637b-136">Eşleme şu şekildedir: Windows Insider Kanallar açıklaması Daha fazla bilgi için ![ ](images/WindowsInsiderChannels.png) bkz. Windows [Bloglarında Windows Insider Kanallarına](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Tanıtma.</span><span class="sxs-lookup"><span data-stu-id="3637b-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="3637b-137">Ardından, **Windows'un** etkin geliştirmesi'yi seçin, **Geliştirme** Kanalı'nın mı yoksa derlemelerin **mi** Beta Kanal ve program koşullarını gözden geçirmeyi seçin.</span><span class="sxs-lookup"><span data-stu-id="3637b-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="3637b-138">Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin.</span><span class="sxs-lookup"><span data-stu-id="3637b-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="3637b-139">Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak için Ayarlar > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.</span><span class="sxs-lookup"><span data-stu-id="3637b-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="3637b-140">Hata güncelleştirme 0x80070490 çalışma</span><span class="sxs-lookup"><span data-stu-id="3637b-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="3637b-141">Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli çalışmalara bakın.</span><span class="sxs-lookup"><span data-stu-id="3637b-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="3637b-142">Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3637b-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="3637b-143">1. aşama - Yayın Önizlemesi</span><span class="sxs-lookup"><span data-stu-id="3637b-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="3637b-144">Ayarlar, Güncelleştirme & Güvenlik, Windows Insider Programı Yayın Önizleme **Kanalı'Windows Insider Programı seçin.**</span><span class="sxs-lookup"><span data-stu-id="3637b-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="3637b-145">Ayarlar, Güncelleştirme & Güvenlik, Windows Update, **Güncelleştirmeleri denetleme.**</span><span class="sxs-lookup"><span data-stu-id="3637b-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="3637b-146">Güncelleştirmeden sonra ikinci aşamaya devam et.</span><span class="sxs-lookup"><span data-stu-id="3637b-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="3637b-147">Aşama iki - Geliştirme Kanalı</span><span class="sxs-lookup"><span data-stu-id="3637b-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="3637b-148">Ayarlar, Güncelleştirme & Güvenlik, Windows Insider Programı Dev **Channel'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="3637b-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="3637b-149">Ayarlar, Güncelleştirme & Güvenlik, Windows Update, **Güncelleştirmeleri denetleme.**</span><span class="sxs-lookup"><span data-stu-id="3637b-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="3637b-150">FFU indirme ve flash yönler</span><span class="sxs-lookup"><span data-stu-id="3637b-150">FFU download and flash directions</span></span>
<span data-ttu-id="3637b-151">Uçuş imzalı ffu ile test etmek için, uçuş imzalı ffu'nun yanıp sönmeden önce cihazınızın kilidinin açılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3637b-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="3637b-152">Pc'de:</span><span class="sxs-lookup"><span data-stu-id="3637b-152">On PC:</span></span>
    1. <span data-ttu-id="3637b-153">ffu'dan bilgisayarınıza [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) indirin.</span><span class="sxs-lookup"><span data-stu-id="3637b-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="3637b-154">arc (Gelişmiş Kurtarma Yardımcı) yükleme Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="3637b-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="3637b-155">HoloLens - Flight Unlock'da: **Ayarlar**  >  **Güncelleştirmesi'& Güvenlik**  >  **Windows Insider Programı** açın ve cihazı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="3637b-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="3637b-156">Flash FFU - Artık ARC kullanarak uçuş imzalı FFU'nun flash'unu sönersiniz.</span><span class="sxs-lookup"><span data-stu-id="3637b-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="3637b-157">Geri bildirim sağlama ve sorunları bildirme</span><span class="sxs-lookup"><span data-stu-id="3637b-157">Provide feedback and report issues</span></span>
<span data-ttu-id="3637b-158">Geri bildirim [ve Geri Bildirim Merkezi için](hololens-feedback.md) lütfen HoloLens'inizin Geri Bildirim Merkezi uygulamasını kullanın.</span><span class="sxs-lookup"><span data-stu-id="3637b-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="3637b-159">Bu Geri Bildirim Merkezi, mühendislerimizin hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgilerine dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="3637b-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="3637b-160">HoloLens'in Çince ve Japonca sürümüyle ilgili sorunlar da aynı şekilde bildiriliyor.</span><span class="sxs-lookup"><span data-stu-id="3637b-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="3637b-161">Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).</span><span class="sxs-lookup"><span data-stu-id="3637b-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="3637b-162">Geliştiriciler için not</span><span class="sxs-lookup"><span data-stu-id="3637b-162">Note for developers</span></span>
<span data-ttu-id="3637b-163">HoloLens'in Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemek hoş geldiniz ve teşvik edilir.</span><span class="sxs-lookup"><span data-stu-id="3637b-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="3637b-164">Çalışmaya başlamaya [için HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3637b-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="3637b-165">Aynı yönergeler HoloLens'in Insider derlemeleriyle de çalışır.</span><span class="sxs-lookup"><span data-stu-id="3637b-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="3637b-166">HoloLens geliştirme için zaten Visual Studio Unity ve Visual Studio derlemelerini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3637b-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="3637b-167">Insider derlemelerini almayı durdurma</span><span class="sxs-lookup"><span data-stu-id="3637b-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="3637b-168">Artık Windows Holographic'in Insider derlemelerini almak istemiyorsanız, HoloLens'iniz bir üretim derlemesi [](hololens-recovery.md) çalıştırılmasa da, cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarmak için Gelişmiş Kurtarma Yardımcı'sı kullanarak cihazınızı kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3637b-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="3637b-169">Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır.</span><span class="sxs-lookup"><span data-stu-id="3637b-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="3637b-170">Daha sonra, cihazlarını el ile kurtarmaları gerekir.</span><span class="sxs-lookup"><span data-stu-id="3637b-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="3637b-171">Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="3637b-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="3637b-172">HoloLens'inizin bir üretim derlemesi çalıştırarak çalıştığını doğrulamak için:</span><span class="sxs-lookup"><span data-stu-id="3637b-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="3637b-173">**Ayarlar'a > System > Hakkında'ya** gidin ve derleme numarasını bulun.</span><span class="sxs-lookup"><span data-stu-id="3637b-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="3637b-174">[Üretim derleme numaraları için sürüm notlarına bakın.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="3637b-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="3637b-175">Insider derlemelerini geri almak için:</span><span class="sxs-lookup"><span data-stu-id="3637b-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="3637b-176">Üretim derlemesi çalıştıran bir HoloLens'de Ayarlar **> Update & Security > Windows Insider Programı**'a gidin ve Insider derlemelerini **durdur'u seçin.**</span><span class="sxs-lookup"><span data-stu-id="3637b-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="3637b-177">Cihazınızı geri almak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="3637b-177">Follow the instructions to opt out your device.</span></span>
