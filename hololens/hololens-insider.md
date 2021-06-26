---
title: Microsoft HoloLens için Insider Preview
description: Insider Derlemeleriyle çalışmaya başlama ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmemiz için değerli geri bildirim sağlama hakkında bilgi edinin.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977230"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="4e82c-103">Microsoft HoloLens için Insider Preview</span><span class="sxs-lookup"><span data-stu-id="4e82c-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="4e82c-104">HoloLens için en son Insider Preview yapılarına hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="4e82c-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="4e82c-105">Daha kolay [çalışmaya](hololens-insider.md#start-receiving-insider-builds) başlamak ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamaktır.</span><span class="sxs-lookup"><span data-stu-id="4e82c-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="4e82c-106">Windows Insider sürüm notları</span><span class="sxs-lookup"><span data-stu-id="4e82c-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="4e82c-107">Yeni özellikleri Windows Insider 'lar 'a yeniden başlatmak için heyecanlıyız.</span><span class="sxs-lookup"><span data-stu-id="4e82c-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="4e82c-108">Yeni derlemeler, en son güncelleştirmeler için geliştirme ve Beta kanallarına uçucaktır.</span><span class="sxs-lookup"><span data-stu-id="4e82c-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="4e82c-109">Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme eklediğimiz için bu sayfayı güncelleştirmeye devam edeceğiz.</span><span class="sxs-lookup"><span data-stu-id="4e82c-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="4e82c-110">Heyecanlanmanıza ve bu güncelleştirmeleri gerçeğe sunmaya hazırlanın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="4e82c-111">Özellik</span><span class="sxs-lookup"><span data-stu-id="4e82c-111">Feature</span></span>                 | <span data-ttu-id="4e82c-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4e82c-112">Description</span></span>                | <span data-ttu-id="4e82c-113">Hedef kullanıcılar</span><span class="sxs-lookup"><span data-stu-id="4e82c-113">Target Users</span></span> | <span data-ttu-id="4e82c-114">Tanıtılan derleme</span><span class="sxs-lookup"><span data-stu-id="4e82c-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="4e82c-115">HoloLens 'te CSP değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="4e82c-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="4e82c-116">Verileri sorgulamak için yeni CSP 'Ler</span><span class="sxs-lookup"><span data-stu-id="4e82c-116">New CSPs for to query data</span></span> | <span data-ttu-id="4e82c-117">BT yöneticileri</span><span class="sxs-lookup"><span data-stu-id="4e82c-117">IT Admins</span></span>    | <span data-ttu-id="4e82c-118">20348,1403</span><span class="sxs-lookup"><span data-stu-id="4e82c-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="4e82c-119">HoloLens 'te CSP değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="4e82c-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="4e82c-120">Windows Insider Build, 20348,1403 ' de tanıtılan</span><span class="sxs-lookup"><span data-stu-id="4e82c-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="4e82c-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="4e82c-121">DevDetail CSP</span></span>

<span data-ttu-id="4e82c-122">DevDetail CSP artık HoloLens cihazında boş depolama alanı da bildiriyor.</span><span class="sxs-lookup"><span data-stu-id="4e82c-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="4e82c-123">Bu, ayarlar uygulamasının depolama sayfasında gösterilen değerle yaklaşık olarak eşleşmelidir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="4e82c-124">Bu bilgileri içeren belirli düğüm aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="4e82c-125">./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)</span><span class="sxs-lookup"><span data-stu-id="4e82c-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="4e82c-126">DeviceStatus CSP 'si</span><span class="sxs-lookup"><span data-stu-id="4e82c-126">DeviceStatus CSP</span></span>

<span data-ttu-id="4e82c-127">DeviceStatus CSP artık Ayrıca, HoloLens 'in etkin bir şekilde bağlandığı SSID ve WiFi ağının BSSıD 'sini de raporluyor.</span><span class="sxs-lookup"><span data-stu-id="4e82c-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="4e82c-128">Bu bilgileri içeren belirli düğümler aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="4e82c-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/SSID</span><span class="sxs-lookup"><span data-stu-id="4e82c-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="4e82c-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/b SSID 'si</span><span class="sxs-lookup"><span data-stu-id="4e82c-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="4e82c-131">Networktanımlayıcılarına yönelik sorgu için örnek SyncML Blobu (MDM satıcıları için)</span><span class="sxs-lookup"><span data-stu-id="4e82c-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="4e82c-132">Düzeltmeler ve geliştirmeler:</span><span class="sxs-lookup"><span data-stu-id="4e82c-132">Fixes and improvements:</span></span>

- <span data-ttu-id="4e82c-133">Bir [cihaz portalı için, kilitli dosyaları indirmede hiçbir istem olmadığı bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="4e82c-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="4e82c-134">[Karşıya dosya yükleme ve indirme zaman aşımları Ile cihaz portalı 'nın bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="4e82c-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="4e82c-135">Insider derlemelerini almaya başlayın</span><span class="sxs-lookup"><span data-stu-id="4e82c-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="4e82c-136">Son zamanlarda güncelleştirmediyseniz, durumu güncelleştirmek ve en son derlemeyi almak için lütfen cihazınızı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="4e82c-137">"Cihazı yeniden Başlat" ses komutu iyi şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4e82c-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="4e82c-138">Ayarlar/Windows Insider programı ' nda yeniden Başlat düğmesini de seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4e82c-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="4e82c-139">Arka uçta karşılaştığınız bir hata yaşadık ve bu, izlemeye geri dönecek.</span><span class="sxs-lookup"><span data-stu-id="4e82c-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="4e82c-140">HoloLens 2 cihazında **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows Insider programı** ' na gidin ve **kullanmaya** başlayın ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="4e82c-141">Windows Insider olarak kaydetmek için kullandığınız hesabı bağlayın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="4e82c-142">Windows Insider artık kanallara taşınıyor.</span><span class="sxs-lookup"><span data-stu-id="4e82c-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="4e82c-143">**Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur.</span><span class="sxs-lookup"><span data-stu-id="4e82c-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="4e82c-144">Bu, eşlemenin şöyle görünür: ![ Windows Insider Channels açıklaması ](images/WindowsInsiderChannels.png) daha fazla bilgi için bkz. Windows Web günlükleri üzerinde [Windows Insider kanalları tanıtımı](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .</span><span class="sxs-lookup"><span data-stu-id="4e82c-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="4e82c-145">Ardından, **Windows 'un etkin geliştirmesini** seçin, **geliştirme kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="4e82c-146">**> şimdi yeniden başlatmak Için Onayla** ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="4e82c-147">Cihazınız yeniden başlatıldıktan sonra **ayarlar > & güvenliği güncelleştirme** ' ye gidin > en son derlemeyi almak Için güncelleştirmeleri denetleyin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="4e82c-148">Güncelleştirme hatası 0x80070490 iş-etrafında</span><span class="sxs-lookup"><span data-stu-id="4e82c-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="4e82c-149">Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli çalışmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="4e82c-150">Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="4e82c-151">Aşama tek sürüm önizlemesi</span><span class="sxs-lookup"><span data-stu-id="4e82c-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="4e82c-152">Ayarlar, güncelleştirme & güvenliği, Windows Insider programı, **sürüm Önizleme kanalı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="4e82c-153">Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.</span><span class="sxs-lookup"><span data-stu-id="4e82c-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="4e82c-154">Güncelleştirme sonrasında, ikinci aşamada devam edin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="4e82c-155">İkinci geliştirme kanalı aşaması</span><span class="sxs-lookup"><span data-stu-id="4e82c-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="4e82c-156">Ayarlar, güncelleştirme & güvenliği, Windows Insider programı, **geliştirme kanalını** seçin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="4e82c-157">Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.</span><span class="sxs-lookup"><span data-stu-id="4e82c-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="4e82c-158">FFU indirme ve Flash yönleri</span><span class="sxs-lookup"><span data-stu-id="4e82c-158">FFU download and flash directions</span></span>
<span data-ttu-id="4e82c-159">Bir uçuş imzalı FFU ile test etmek için önce, uçuşdan ayrılmadan önce cihazınızın kilidini açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="4e82c-160">BILGISAYAR üzerinde:</span><span class="sxs-lookup"><span data-stu-id="4e82c-160">On PC:</span></span>
    1. <span data-ttu-id="4e82c-161">Hesabınızı ' den bilgisayarınıza indirin [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="4e82c-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="4e82c-162">Microsoft Store: ile yay (Gelişmiş kurtarma Yardımcısı) yüklemesini yapın [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="4e82c-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="4e82c-163">HoloLens üzerinde kilit açma: açık **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows Insider programı** ' nı açın, cihazı yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="4e82c-164">Flash FFU-şimdi yay kullanarak uçuştan imzalanmış FFU 'yi yakıp sönebilir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="4e82c-165">Geri bildirim ve rapor sorunları sağlama</span><span class="sxs-lookup"><span data-stu-id="4e82c-165">Provide feedback and report issues</span></span>
<span data-ttu-id="4e82c-166">Geri bildirim ve rapor sorunları sağlamak için lütfen HoloLens 'teki [geri bildirim Merkezi uygulamasını](hololens-feedback.md) kullanın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="4e82c-167">Geri Bildirim Hub 'ı kullanmak, mühendislerimizin hata ayıklamasına ve sorunu çözmeye yardımcı olmak için gerekli tüm tanılama bilgilerinin eklenmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="4e82c-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="4e82c-168">HoloLens 'in Çince ve Japonca sürümündeki sorunlar aynı şekilde bildirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="4e82c-169">Belge klasörünüze geri bildirim hub 'ı (sorulduğunda **Evet** ' i seçin) isteyip istemediğinizi soran istemi kabul ettiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="4e82c-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="4e82c-170">Geliştiriciler için göz önünde</span><span class="sxs-lookup"><span data-stu-id="4e82c-170">Note for developers</span></span>
<span data-ttu-id="4e82c-171">Bu hoş geldiniz ve, HoloLens 'in Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemeye teşvik edersiniz.</span><span class="sxs-lookup"><span data-stu-id="4e82c-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="4e82c-172">Başlamak için [HoloLens geliştirici belgelerine](https://developer.microsoft.com/windows/mixed-reality/development) göz atın.</span><span class="sxs-lookup"><span data-stu-id="4e82c-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="4e82c-173">Aynı yönergeler, HoloLens 'in Insider Derlemeleriyle birlikte çalışır.</span><span class="sxs-lookup"><span data-stu-id="4e82c-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="4e82c-174">HoloLens geliştirme için kullanmakta olduğunuz Unity ve Visual Studio Derlemeleriyle aynı şekilde yararlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4e82c-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="4e82c-175">Insider derlemelerini almayı durdur</span><span class="sxs-lookup"><span data-stu-id="4e82c-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="4e82c-176">Artık Windows holographic Insider derlemelerini almak istemiyorsanız, HoloLens 'in bir üretim derlemesi çalıştırması durumunda devre dışı bırakabilirsiniz veya cihazınızı, Gelişmiş kurtarma Yardımcısı 'nı kullanarak [kurtararak](hololens-recovery.md) cihazınızı Windows holographic 'ın Insider sürümüne kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4e82c-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="4e82c-177">Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydolmamış kullanıcıların mavi bir ekran deneymesinin bilinen bir sorunu vardır.</span><span class="sxs-lookup"><span data-stu-id="4e82c-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="4e82c-178">Daha sonra cihazlarını el ile kurtarmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="4e82c-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="4e82c-179">Etkilenmiş olmanız veya olmadıysanız ilgili tüm ayrıntılar için lütfen bu [bilinen sorunu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)izleyin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="4e82c-180">HoloLens 'in bir üretim derlemesi çalıştırdığından emin olmak için:</span><span class="sxs-lookup"><span data-stu-id="4e82c-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="4e82c-181">**Ayarlar > sistem > hakkında**' ya gidin ve derleme numarasını bulun.</span><span class="sxs-lookup"><span data-stu-id="4e82c-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="4e82c-182">[Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="4e82c-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="4e82c-183">Insider derlemelerini devre dışı bırakmak için:</span><span class="sxs-lookup"><span data-stu-id="4e82c-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="4e82c-184">Üretim yapısını çalıştıran bir HoloLens üzerinde, **ayarlar > güncelleştirme & güvenlik > Windows Insider programı**' na gidin ve **Insider derlemelerini durdur**' u seçin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="4e82c-185">Cihazınızı devre dışı bırakmak için yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="4e82c-185">Follow the instructions to opt out your device.</span></span>
