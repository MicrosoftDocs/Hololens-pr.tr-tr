---
title: HoloLens cihaz sorunlarını giderme
description: HoloLens cihaz sorunları ve sorun giderme teknikleri için en yaygın çözümlerin güncel kalmasını sağlar.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: sorunlar, hata, sorun giderme, çözüm, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924630"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="73e86-104">Cihaz sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="73e86-104">Device Troubleshooting</span></span>

<span data-ttu-id="73e86-105">Bu makalede, birkaç yaygın HoloLens sorununa nasıl çözüm yapılacağı açıklanır.</span><span class="sxs-lookup"><span data-stu-id="73e86-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="73e86-106">Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="73e86-107">Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="73e86-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="73e86-108">**Bilinen Sorunlar**</span><span class="sxs-lookup"><span data-stu-id="73e86-108">**Known Issues**</span></span>
- [<span data-ttu-id="73e86-109">Uzaktan Yardım Videosu 20 dakikadan sonra donuyor</span><span class="sxs-lookup"><span data-stu-id="73e86-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="73e86-110">Oturum açma için otomatik oturum açma sorulur</span><span class="sxs-lookup"><span data-stu-id="73e86-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="73e86-111">Microsoft Edge başlatılamadı</span><span class="sxs-lookup"><span data-stu-id="73e86-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="73e86-112">Klavye özel karakterlere geçmez</span><span class="sxs-lookup"><span data-stu-id="73e86-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="73e86-113">Kilitli dosyaların indirilmesi hata göstermiyor</span><span class="sxs-lookup"><span data-stu-id="73e86-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="73e86-114">Cihaz portalı dosya yükleme/indirme zaman aşımı</span><span class="sxs-lookup"><span data-stu-id="73e86-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="73e86-115">Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran</span><span class="sxs-lookup"><span data-stu-id="73e86-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="73e86-116">OneDrive resimleri otomatik olarak karşıya yüklememez</span><span class="sxs-lookup"><span data-stu-id="73e86-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="73e86-117">**Genel**</span><span class="sxs-lookup"><span data-stu-id="73e86-117">**General**</span></span>
- [<span data-ttu-id="73e86-118">HoloLens yanıt vermiyor veya başlamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="73e86-119">"Yetersiz disk alanı" hatası</span><span class="sxs-lookup"><span data-stu-id="73e86-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="73e86-120">Ayarlama başarısız</span><span class="sxs-lookup"><span data-stu-id="73e86-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="73e86-121">HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="73e86-122">Unity çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="73e86-123">Windows cihaz portalı düzgün çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="73e86-124">HoloLens öykünücüsü çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="73e86-125">**Giriş**</span><span class="sxs-lookup"><span data-stu-id="73e86-125">**Input**</span></span>
- [<span data-ttu-id="73e86-126">Sesli komutlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="73e86-127">El girişi çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="73e86-128">**Bağlantı**</span><span class="sxs-lookup"><span data-stu-id="73e86-128">**Connectivity**</span></span>
- [<span data-ttu-id="73e86-129">Wi-Fi ' a bağlanılamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="73e86-130">**Dış cihazlar**</span><span class="sxs-lookup"><span data-stu-id="73e86-130">**External Devices**</span></span> 
- [<span data-ttu-id="73e86-131">Bluetooth cihazları eşleştirme yok</span><span class="sxs-lookup"><span data-stu-id="73e86-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="73e86-132">USB-C mikrofonu çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="73e86-133">Ayarlarda kullanılabilir olarak listelenen cihazlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="73e86-134">Uzaktan Yardım Videosu 20 dakikadan sonra donuyor</span><span class="sxs-lookup"><span data-stu-id="73e86-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="73e86-135">Bu bilinen sorunun önem derecesine bağlı olarak, şu anda Windows holographic, sürüm 21H1 kullanılabilirliğini duraklattık.</span><span class="sxs-lookup"><span data-stu-id="73e86-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="73e86-136">Cihazlarınızı 21 H1 ' e güncelleştirmek istiyorsanız lütfen [sayfanın en üstündeki sürüm Notlarımızda bulunan yönergelere bakın.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="73e86-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="73e86-137">[Windows holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1)' in en son sürümünde, uzaktan yardım 'ın bazı kullanıcıları 20 dakikadan fazla çağrı sırasında video donduruyor demektir.</span><span class="sxs-lookup"><span data-stu-id="73e86-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="73e86-138">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="73e86-139">Geçici Çözümler</span><span class="sxs-lookup"><span data-stu-id="73e86-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="73e86-140">Çağrılar arasında yeniden Başlat</span><span class="sxs-lookup"><span data-stu-id="73e86-140">Restart in between calls</span></span>

<span data-ttu-id="73e86-141">Çağrılarınızın uzunluğu 20 dakikadan fazla olursa ve bu sorunu yaşıyorsanız cihazınızı yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="73e86-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="73e86-142">Cihazınızı uzaktan yardım çağrıları arasında yeniden başlatmak cihazınızı yenileyip iyi bir duruma geri yerleştirecek.</span><span class="sxs-lookup"><span data-stu-id="73e86-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="73e86-143">Windows holographic 'de bir cihazı hızlı bir şekilde yeniden başlatmak için [, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) Başlat menüsünü açın ve Kullanıcı simgesini seçin, sonra **Yeniden Başlat**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="73e86-144">Eski bir yapıya dön</span><span class="sxs-lookup"><span data-stu-id="73e86-144">Revert to an older build</span></span>

<span data-ttu-id="73e86-145">Bazı müşteriler daha önceki bir işletim sistemi sürümüne geri dönüldükten sonra bu sorunla karşılaşmamıştır.</span><span class="sxs-lookup"><span data-stu-id="73e86-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="73e86-146">Cihazlarınızın bu sorunla karşılaşdığını buldıysanız, şu adımları deneyin:</span><span class="sxs-lookup"><span data-stu-id="73e86-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="73e86-147">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="73e86-147">Workarounds:</span></span>

- <span data-ttu-id="73e86-148">İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="73e86-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="73e86-149">İş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması, çift oturum açma desteği sağlar).</span><span class="sxs-lookup"><span data-stu-id="73e86-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="73e86-150">OneDrive 'daki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="73e86-151">Fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="73e86-152">Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="73e86-153">Düğmeyi seçip **+** **karşıya yükle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="73e86-154">**Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun.</span><span class="sxs-lookup"><span data-stu-id="73e86-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="73e86-155">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="73e86-156">Windows holographic, sürüm 20H2 – Mayıs 2021 güncelleştirmesi için derlemeyi indirin</span><span class="sxs-lookup"><span data-stu-id="73e86-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="73e86-157">[Önceki bir işletim sistemi sürümüne geri dönme yönergelerini](hololens-update-hololens.md#go-back-to-a-previous-version) izleyin</span><span class="sxs-lookup"><span data-stu-id="73e86-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="73e86-158">[Cihazdaki işletim sistemi güncelleştirmelerini el ile duraklatın](hololens-updates.md#pause-updates-via-device) ya da birçok CIHAZ için [MDM aracılığıyla erteleme](hololens-updates.md#configure-an-update-deferral-policy)kullanın.</span><span class="sxs-lookup"><span data-stu-id="73e86-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="73e86-159">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="73e86-160">Oturum açma için otomatik oturum açma sorulur</span><span class="sxs-lookup"><span data-stu-id="73e86-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="73e86-161">Bir HoloLens 2 cihazı, **Ayarlar**  ->  **hesabı**  ->  **oturum açma seçenekleri** -> aracılığıyla otomatik olarak oturum açmak üzere yapılandırılabilir ve değer **gerekli** ayarı **hiçbir** şekilde ayarlanamaz.</span><span class="sxs-lookup"><span data-stu-id="73e86-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="73e86-162">Bir cihaz, özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştirilirken cihazda oturum açmak için bazı kullanıcılar gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="73e86-163">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-163">This is a **known issue**.</span></span>

<span data-ttu-id="73e86-164">Bunun gerçekleşebileceğini örnek:</span><span class="sxs-lookup"><span data-stu-id="73e86-164">Example of when this could occur:</span></span>

- <span data-ttu-id="73e86-165">Windows holographic, sürüm 2004 ' den (derleme 19041. xxxx) Windows holographic, sürüm 21H1 (derleme 20346. xxxx) ile cihaz güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="73e86-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="73e86-166">Bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örn. Windows holographic, sürüm 2004, Windows holographic, sürüm 20H2</span><span class="sxs-lookup"><span data-stu-id="73e86-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="73e86-167">Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="73e86-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="73e86-168">Bunun sırasında gerçekleşmemelidir:</span><span class="sxs-lookup"><span data-stu-id="73e86-168">This should not occur during:</span></span>

- <span data-ttu-id="73e86-169">Aylık bakım güncelleştirmesi alan cihazlar</span><span class="sxs-lookup"><span data-stu-id="73e86-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="73e86-170">Yöntemlerin etrafında çalışın:</span><span class="sxs-lookup"><span data-stu-id="73e86-170">Work around methods:</span></span>

- <span data-ttu-id="73e86-171">PIN, parola, Iris, Web kimlik doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="73e86-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="73e86-172">Cihaz PIN kodu hatırlanamaz ve diğer kimlik doğrulama yöntemleri kullanılabilir değilse, bir Kullanıcı [el ile yerleştirme modunu](hololens-recovery.md#manual-procedure)kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="73e86-173">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="73e86-174">Microsoft Edge başlatılamadı</span><span class="sxs-lookup"><span data-stu-id="73e86-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="73e86-175">Bu sorun başlangıçta Microsoft Edge 'in sevkiyat sürümü göz önünde bulundurularak oluşturulmuştur.</span><span class="sxs-lookup"><span data-stu-id="73e86-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="73e86-176">Bu sorun [Yeni Microsoft Edge](hololens-new-edge.md)'de çözülebilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="73e86-177">Aksi takdirde, lütfen geri bildirimde bulunun.</span><span class="sxs-lookup"><span data-stu-id="73e86-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="73e86-178">Birkaç müşteri, Microsoft Edge 'in başlatamayacağı bir sorun raporladı.</span><span class="sxs-lookup"><span data-stu-id="73e86-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="73e86-179">Bu müşteriler için, sorun yeniden başlatma ile devam etmez ve Windows veya uygulama güncelleştirmeleriyle çözümlenmez.</span><span class="sxs-lookup"><span data-stu-id="73e86-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="73e86-180">Bu sorunla karşılaşıyorsanız ve [Windows 'un güncel olduğunu](hololens-updates.md#manually-check-for-updates)onayladıysanız, lütfen aşağıdaki kategori ve alt kategori Ile [geri bildirim merkezi](hololens-feedback.md) uygulamasından bir hata bildirin: Windows Update indirme, yükleme ve yapılandırma > yükleme ve güncelleştirme.</span><span class="sxs-lookup"><span data-stu-id="73e86-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="73e86-181">Sorunun şu ana kadar köke neden olmadığı bilinen bir geçici çözüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="73e86-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="73e86-182">Geri Bildirim Hub 'ı aracılığıyla bir hata dosyalama araştırmasına yardımcı olacak!</span><span class="sxs-lookup"><span data-stu-id="73e86-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="73e86-183">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-183">This is a **known issue**.</span></span>

[<span data-ttu-id="73e86-184">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="73e86-185">Klavye özel karakterlere geçmez</span><span class="sxs-lookup"><span data-stu-id="73e86-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="73e86-186">Kullanıcı bir iş veya okul hesabı seçtiği ve parolasını girerken, OOBE sırasında, &123 düğmesine dokunarak klavye üzerindeki özel karakterlere geçiş yapmaya çalışırken, özel karakterlere değişmediğinden, OOBE sırasında bir sorun vardır.</span><span class="sxs-lookup"><span data-stu-id="73e86-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="73e86-187">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-187">This is a **known issue**.</span></span>

<span data-ttu-id="73e86-188">Work-arounds:</span><span class="sxs-lookup"><span data-stu-id="73e86-188">Work-arounds:</span></span>
-   <span data-ttu-id="73e86-189">Klavyeyi kapatın ve metin alanına dokunarak yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="73e86-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="73e86-190">Parolanızı yanlış girin.</span><span class="sxs-lookup"><span data-stu-id="73e86-190">Incorrectly enter your password.</span></span> <span data-ttu-id="73e86-191">Klavye bir dahaki sefer çalışırken beklendiği gibi çalışır.</span><span class="sxs-lookup"><span data-stu-id="73e86-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="73e86-192">Web kimlik doğrulaması, klavyeyi kapatın ve **başka bir cihazdan oturum aç**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="73e86-193">Yalnızca sayı girilirse, bir kullanıcı genişletilmiş bir menü açmak için belirli tuşları basılı tutabilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="73e86-194">USB klavye kullanma.</span><span class="sxs-lookup"><span data-stu-id="73e86-194">Using a USB keyboard.</span></span>

<span data-ttu-id="73e86-195">Bu, şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="73e86-195">This does not affect:</span></span>
- <span data-ttu-id="73e86-196">Kişisel hesap kullanmayı seçen kullanıcılar.</span><span class="sxs-lookup"><span data-stu-id="73e86-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="73e86-197">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="73e86-198">Kilitli dosyaların indirilmesi hatası yok</span><span class="sxs-lookup"><span data-stu-id="73e86-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="73e86-199">! Bu, Windows Insider Build, sürüm 20348,1403 ' de düzeltilen **bilinen bir sorundur** .</span><span class="sxs-lookup"><span data-stu-id="73e86-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="73e86-200">Önceki Windows holographic Derlemeleriyle, kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olur.</span><span class="sxs-lookup"><span data-stu-id="73e86-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="73e86-201">Windows holographic, sürüm 21H1 güncelleştirmesinde, kilitli bir dosyayı indirmeye çalışmak, hiçbir şey görünmediğine neden olmaz; dosya indirilmez ve hata vermez.</span><span class="sxs-lookup"><span data-stu-id="73e86-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="73e86-202">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="73e86-203">Cihaz portalı dosya yükleme/indirme zaman aşımı</span><span class="sxs-lookup"><span data-stu-id="73e86-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="73e86-204">! Bu, Windows Insider Build, sürüm 20348,1403 ' de düzeltilen **bilinen bir sorundur** .</span><span class="sxs-lookup"><span data-stu-id="73e86-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="73e86-205">Geçici çözümün bir parçası olarak SSL bağlantısını devre dışı bırakırsanız, yeniden etkinleştirmenizi kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="73e86-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="73e86-206">Bazı müşteriler, dosyaları karşıya yüklemeye veya indirmeye çalışırken, işlem askıda kalabilir ve sonra zaman aşımına uğrar veya hiç tamamlanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="73e86-207">Bu, '[dosya kilitli ' bilinen sorundan](#downloading-locked-files-doesnt-error) ayrıdır. Bu, Windows holographic, sürüm 2004, 20H2 ve 21 H1 Pazar sürümlerini etkiler.</span><span class="sxs-lookup"><span data-stu-id="73e86-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="73e86-208">Sorun, cihaz portalının belirli isteklerin işlenmesinde oluşan bir hataya yol açtı ve varsayılan değer olan https kullanılırken en tutarlı şekilde isabet ediyor.</span><span class="sxs-lookup"><span data-stu-id="73e86-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="73e86-209">Geçici çözüm</span><span class="sxs-lookup"><span data-stu-id="73e86-209">Workaround</span></span>

<span data-ttu-id="73e86-210">Wi-Fi ve UsbNcm 'ye eşit olarak uygulanan bu geçici çözüm, "SSL bağlantısı" altında "gerekli" seçeneğinin devre dışı bırakılması.</span><span class="sxs-lookup"><span data-stu-id="73e86-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="73e86-211">Bunu yapmak için cihaz portalı, **sistem**' e gidin ve **Tercihler** sayfasını seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="73e86-212">**Cihaz güvenliği** bölümünde, **SSL bağlantısı**' nı bulun ve **gerekli**' ı devre dışı bırakmak için işaretini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="73e86-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="73e86-213">Daha sonra Kullanıcı, https://(IP adresi) değil http://, dosya yükleme ve indirme gibi özellikler için de çalışır.</span><span class="sxs-lookup"><span data-stu-id="73e86-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="73e86-214">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="73e86-215">Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran</span><span class="sxs-lookup"><span data-stu-id="73e86-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="73e86-216">Bu, bir Insider Preview derlemesinde bulunan kullanıcıları etkiler, HoloLens 2 ' yi yeni bir Insider Preview derlemesi ile ve ardından Insider programından kaydını kaldırmış olan kullanıcıları etkiler.</span><span class="sxs-lookup"><span data-stu-id="73e86-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="73e86-217">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-217">This is a **known issue**.</span></span>

<span data-ttu-id="73e86-218">Bu, şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="73e86-218">This does not affect:</span></span>
- <span data-ttu-id="73e86-219">Windows Insider 'da kayıtlı olmayan kullanıcılar</span><span class="sxs-lookup"><span data-stu-id="73e86-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="73e86-220">Insiders</span><span class="sxs-lookup"><span data-stu-id="73e86-220">Insiders:</span></span>
    - <span data-ttu-id="73e86-221">Insider derlemeleri sürüm 18362. x olduğundan bir cihaz kaydedildiyse</span><span class="sxs-lookup"><span data-stu-id="73e86-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="73e86-222">Insider 'a imzalanmış bir 19041. x derlemesini düzder ve Insider programı 'nda kayıtlı kal</span><span class="sxs-lookup"><span data-stu-id="73e86-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="73e86-223">Geçici iş:</span><span class="sxs-lookup"><span data-stu-id="73e86-223">Work-around:</span></span> 
- <span data-ttu-id="73e86-224">Sorunu önleyin</span><span class="sxs-lookup"><span data-stu-id="73e86-224">Avoid the issue</span></span> 
    - <span data-ttu-id="73e86-225">Insider olmayan bir derlemeyi yakıp söndür.</span><span class="sxs-lookup"><span data-stu-id="73e86-225">Flash a non-insider build.</span></span> <span data-ttu-id="73e86-226">Normal aylık güncelleştirmelerden biri.</span><span class="sxs-lookup"><span data-stu-id="73e86-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="73e86-227">Insider Preview 'da kalın</span><span class="sxs-lookup"><span data-stu-id="73e86-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="73e86-228">Cihazı kırın</span><span class="sxs-lookup"><span data-stu-id="73e86-228">Reflash the device</span></span>

    1. <span data-ttu-id="73e86-229">Bağlama sırasında, Hololens 2 ' ye tamamen kapatarak el ile [yanıp sönme moduna](hololens-recovery.md) koyun.</span><span class="sxs-lookup"><span data-stu-id="73e86-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="73e86-230">Ardından, hacmi tutarken, güç düğmesine dokunun.</span><span class="sxs-lookup"><span data-stu-id="73e86-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="73e86-231">BILGISAYARA bağlanın ve Gelişmiş kurtarma Yardımcısı ' nı açın.</span><span class="sxs-lookup"><span data-stu-id="73e86-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="73e86-232">HoloLens 2 ' ye varsayılan yapıya Flash.</span><span class="sxs-lookup"><span data-stu-id="73e86-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="73e86-233">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="73e86-234">OneDrive resimleri otomatik olarak karşıya yüklememez</span><span class="sxs-lookup"><span data-stu-id="73e86-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="73e86-235">HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="73e86-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="73e86-236">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="73e86-236">This is a **known issue**.</span></span>

<span data-ttu-id="73e86-237">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="73e86-237">Workarounds:</span></span>

- <span data-ttu-id="73e86-238">İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="73e86-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="73e86-239">İş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması, çift oturum açma desteği sağlar).</span><span class="sxs-lookup"><span data-stu-id="73e86-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="73e86-240">OneDrive 'daki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="73e86-241">Fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="73e86-242">Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="73e86-243">Düğmeyi seçip **+** **karşıya yükle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="73e86-244">**Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun.</span><span class="sxs-lookup"><span data-stu-id="73e86-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="73e86-245">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="73e86-246">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="73e86-247">HoloLens yanıt vermiyor veya başlamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="73e86-248">HoloLens 'niz başlamazsa:</span><span class="sxs-lookup"><span data-stu-id="73e86-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="73e86-249">Güç düğmesinin yanındaki LED 'ler soluk veya yalnızca bir tane daha yanıp sönüyor değilse, [HoloLens 'nizi ücretlemeniz gerekebilir.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="73e86-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="73e86-250">Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey göremiyorsanız, [cihazın kalıcı olarak sıfırlanması](hololens-recovery.md#hard-reset-procedure)gerekir.</span><span class="sxs-lookup"><span data-stu-id="73e86-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="73e86-251">HoloLens 'niz dondurulmuş veya yanıt vermiyorsa:</span><span class="sxs-lookup"><span data-stu-id="73e86-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="73e86-252">Bir LED 'in beş bir kısmını devre dışı bırakır veya LED 'ler yanıt vermiyorsa 15 saniye boyunca güç düğmesine basarak HoloLens 'nizi kapatın.</span><span class="sxs-lookup"><span data-stu-id="73e86-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="73e86-253">HoloLens 'nizi başlatmak için, Power düğmesine yeniden basın.</span><span class="sxs-lookup"><span data-stu-id="73e86-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="73e86-254">Bu adımlar çalışmazsa, [HoloLens 2 cihazınızı](hololens-recovery.md) veya [HoloLens (1. gen) cihazınızı](hololens1-recovery.md) kurtarmayı deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="73e86-255">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="73e86-256">"Yetersiz disk alanı" hatası</span><span class="sxs-lookup"><span data-stu-id="73e86-256">"Low Disk Space" error</span></span>

<span data-ttu-id="73e86-257">Aşağıdakilerden birini veya birkaçını yaparak depolama alanını boşaltmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="73e86-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="73e86-258">Kullanılmayan bazı boşlukları silin.</span><span class="sxs-lookup"><span data-stu-id="73e86-258">Delete some unused spaces.</span></span> <span data-ttu-id="73e86-259">**Ayarlar**  >  **sistem**  >  **alanları**' na gidin, artık ihtiyacınız olmayan bir alan seçin ve ardından **Kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="73e86-260">Yerleştirdiğiniz hologramlar bölümünü kaldırın.</span><span class="sxs-lookup"><span data-stu-id="73e86-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="73e86-261">Fotoğraflar uygulamasındaki bazı resimleri ve videoları silin.</span><span class="sxs-lookup"><span data-stu-id="73e86-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="73e86-262">HoloLens 'ınızdan bazı uygulamaları kaldırın.</span><span class="sxs-lookup"><span data-stu-id="73e86-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="73e86-263">**Tüm uygulamalar** listesinde, kaldırmak istediğiniz uygulamayı ve ardından **Kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="73e86-264">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="73e86-265">Ayarlama başarısız</span><span class="sxs-lookup"><span data-stu-id="73e86-265">Calibration fails</span></span>

<span data-ttu-id="73e86-266">Ayarlama çoğu kişi için çalışmalıdır, ancak ayarlama işleminin başarısız olduğu durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="73e86-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="73e86-267">Ayarlama hatasının bazı olası nedenleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="73e86-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="73e86-268">Ayarlama hedeflerini takip etme</span><span class="sxs-lookup"><span data-stu-id="73e86-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="73e86-269">Kirli veya çizilmiş cihaz vizörü veya cihaz vizörü düzgün şekilde konumlandırılmadı</span><span class="sxs-lookup"><span data-stu-id="73e86-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="73e86-270">Kirli veya çizik gözlük</span><span class="sxs-lookup"><span data-stu-id="73e86-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="73e86-271">Belirli türlerde iletişim ve gözlük (renkli kişi mercekler, bazı haksız kişi mercekler, IR engelleme gözlüğü, yüksek kaliteli gözlük, güneş gözlüğü veya benzer)</span><span class="sxs-lookup"><span data-stu-id="73e86-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="73e86-272">Daha fazla bilgi ve bazı eyeflash uzantıları</span><span class="sxs-lookup"><span data-stu-id="73e86-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="73e86-273">Cihazın gözlerinizi görmesini engelliyorsa, saç veya kalın eyecam çerçeveler</span><span class="sxs-lookup"><span data-stu-id="73e86-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="73e86-274">Dar gözler, uzun Eyelashes, amblyopia, nystagmus, bazı LASIK veya diğer gözle bazı durumlar gibi belirli gözle, göz önünde ve göz yormalileri</span><span class="sxs-lookup"><span data-stu-id="73e86-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="73e86-275">Ayarlama başarısız olursa, deneyin:</span><span class="sxs-lookup"><span data-stu-id="73e86-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="73e86-276">Cihazınızı Temizleme vizörü</span><span class="sxs-lookup"><span data-stu-id="73e86-276">Cleaning your device visor</span></span>
- <span data-ttu-id="73e86-277">Gözlerinizi Temizleme</span><span class="sxs-lookup"><span data-stu-id="73e86-277">Cleaning your glasses</span></span>
- <span data-ttu-id="73e86-278">Cihazınızın vizörü ' i mümkün olduğunca yakın bir şekilde iletme</span><span class="sxs-lookup"><span data-stu-id="73e86-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="73e86-279">Nesneleri (örneğin, saç) vizörü içinde hareket ettirmenin</span><span class="sxs-lookup"><span data-stu-id="73e86-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="73e86-280">Odadaki bir ışığı açma veya doğrudan güneş dışına taşıma</span><span class="sxs-lookup"><span data-stu-id="73e86-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="73e86-281">Tüm yönergeleri izlediyseniz ve ayarlama hala başarısız olursa, Ayarlar ' da ayarlama isteğini devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="73e86-282">Ayrıca, [geri bildirim merkezinde](hololens-feedback.md)geri bildirimde bulunarak bize bilgi verin.</span><span class="sxs-lookup"><span data-stu-id="73e86-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="73e86-283">Ayrıca, [görüntü renk veya parlaklık sorun giderme](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) için ilgili bilgiler bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="73e86-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="73e86-284">Gözle ayar konumları sistem tarafından hesaplandığından, ıPD ayarı HoloLens 2 için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="73e86-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="73e86-285">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="73e86-286">HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="73e86-287">Cihazı daha [ **yanıp sönen moda** yerleştirebilir ve Gelişmiş kurtarma Yardımcısı 'nı kullanarak](hololens-recovery.md#clean-reflash-the-device) cihazı kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="73e86-288">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="73e86-289">Unity çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-289">Unity isn't working</span></span>

- <span data-ttu-id="73e86-290">HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.</span><span class="sxs-lookup"><span data-stu-id="73e86-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="73e86-291">Unity HoloLens Technical Preview ile ilgili bilinen sorunlar, [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="73e86-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="73e86-292">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="73e86-293">Windows cihaz portalı düzgün çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="73e86-294">Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="73e86-295">Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir.</span><span class="sxs-lookup"><span data-stu-id="73e86-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="73e86-296">Bunların kullanılması hiçbir etkiye sahip olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="73e86-296">Using them will have no effect.</span></span> <span data-ttu-id="73e86-297">Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="73e86-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="73e86-298">Ayarlar bölümünde Geliştirici modunu etkinleştirdikten sonra, cihaz Portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="73e86-299">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="73e86-300">Öykünücü</span><span class="sxs-lookup"><span data-stu-id="73e86-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="73e86-301">HoloLens öykünücüsü çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="73e86-302">HoloLens öykünücüsü hakkındaki bilgiler geliştirici belgelerimizde bulunur.</span><span class="sxs-lookup"><span data-stu-id="73e86-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="73e86-303">[HoloLens öykünücüsünün sorunlarını giderme](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="73e86-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="73e86-304">Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir.</span><span class="sxs-lookup"><span data-stu-id="73e86-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="73e86-305">Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.</span><span class="sxs-lookup"><span data-stu-id="73e86-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="73e86-306">Öykünücüsünde PC web kamerasını kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="73e86-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="73e86-307">Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="73e86-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="73e86-308">Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="73e86-309">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="73e86-310">HoloLens 2 öykünücüsünü yazmak için klavyeyi bulamıyorum veya kullanmıyorum</span><span class="sxs-lookup"><span data-stu-id="73e86-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="73e86-311">*Çok yakında*</span><span class="sxs-lookup"><span data-stu-id="73e86-311">*Coming soon*</span></span>

[<span data-ttu-id="73e86-312">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="73e86-313">Sesli komutlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-313">Voice commands aren't working</span></span>

<span data-ttu-id="73e86-314">Cortana, sesli komutlarınıza yanıt vermiyorsa Cortana 'Nın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="73e86-315">Tüm uygulamalar listesinde,   >    >  değişiklikler yapmak için Cortana menü **Not defteri**  >  **ayarları** ' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="73e86-316">Ne söyleyebilirim hakkında daha fazla bilgi edinmek için bkz. [HoloLens ile sesinizi kullanma](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="73e86-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="73e86-317">HoloLens 'te (1. Genel), yerleşik konuşma tanıma özelliği yapılandırılamaz.</span><span class="sxs-lookup"><span data-stu-id="73e86-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="73e86-318">Her zaman açıktır.</span><span class="sxs-lookup"><span data-stu-id="73e86-318">It is always turned on.</span></span> <span data-ttu-id="73e86-319">HoloLens 2 ' de, cihaz kurulumu sırasında hem konuşma tanıma hem de Cortana 'yı açıp kullanmayacağınızı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="73e86-320">HoloLens 2 sesinize yanıt vermiyorsa, konuşma tanımanın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="73e86-321">  >  **Ayarlar**  >  **Gizlilik**  >  **konuşmayı** Başlat ' a gidin ve **konuşma tanımayı** açın.</span><span class="sxs-lookup"><span data-stu-id="73e86-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="73e86-322">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="73e86-323">El girişi çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-323">Hand input isn't working</span></span>

<span data-ttu-id="73e86-324">HoloLens 'in ellerinizi görmesini sağlamak için bunları hareket çerçevesinde tutmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="73e86-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="73e86-325">Karma Gerçeklik ana sayfası, kollarınızın ne zaman izleneceğini bilmenizi sağlayan geri bildirim sağlar.</span><span class="sxs-lookup"><span data-stu-id="73e86-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="73e86-326">Geri bildirim, HoloLens 'in farklı sürümlerinde farklıdır:</span><span class="sxs-lookup"><span data-stu-id="73e86-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="73e86-327">HoloLens 'te (1. Genel), Gaze imleci bir noktadan halkaya dönüşür</span><span class="sxs-lookup"><span data-stu-id="73e86-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="73e86-328">HoloLens 2 ' de, elinizdeki bir kurşun kalem 'e yakın olduğunda parmak izi imleci görünür ve SLA 'lar daha fazla olduğunda bir el Ray görünür</span><span class="sxs-lookup"><span data-stu-id="73e86-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="73e86-329">Birçok modern uygulama, karma gerçeklik ana 'ya benzer giriş desenlerine uyar.</span><span class="sxs-lookup"><span data-stu-id="73e86-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="73e86-330">HoloLens 'te el girişi kullanma hakkında daha fazla bilgi edinin [(1. Genel)](hololens1-basic-usage.md#use-hololens-with-your-hands) ve [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="73e86-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="73e86-331">Birlikte çalışırken, bazı araç türlerinin el ile izleme ile çalışmadığına göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="73e86-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="73e86-332">Yaygın olarak kullanılan bir örnek, artışlarını devralarak kızılötesi ışınına eğilen ve derinlik kamerası tarafından alınmayan siyah bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="73e86-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="73e86-333">Çalışmanız lastik içeriyorsa, mavi veya gri gibi daha açık bir renk denemeyi öneririz.</span><span class="sxs-lookup"><span data-stu-id="73e86-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="73e86-334">Diğer bir örnek de büyük ölçekli bir örnektir ve bu, elinizin şeklinin gizlenmesi anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="73e86-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="73e86-335">En iyi sonuçlar için mümkün olduğunca form sığdırma olarak bulunan gloonları kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="73e86-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="73e86-336">Vizörü ' in parmak izleri veya kullanım alanları varsa, vizörü 'nizi temizlemek için HoloLens ile birlikte gelen mikro fiber Temizleme havsını kullanın.</span><span class="sxs-lookup"><span data-stu-id="73e86-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="73e86-337">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="73e86-338">Wi-Fi bağlanılamıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="73e86-339">HoloLens 'nizi bir Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="73e86-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="73e86-340">Wi-Fi açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="73e86-341">Denetlemek için başlangıç hareketini kullanın, ardından **Ayarlar**  >  **Ağ &amp; Internet**  >  **Wi-Fi**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="73e86-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="73e86-342">Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="73e86-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="73e86-343">Yönlendiriciye veya erişim noktasına yaklaşın.</span><span class="sxs-lookup"><span data-stu-id="73e86-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="73e86-344">Wi-Fi yönlendiricinizi yeniden başlatın ve [HoloLens 'i yeniden başlatın](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="73e86-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="73e86-345">Yeniden bağlanmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="73e86-345">Try connecting again.</span></span>
- <span data-ttu-id="73e86-346">Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="73e86-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="73e86-347">Bu bilgileri üretici web sitesinde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="73e86-348">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="73e86-349">Bluetooth cihazları eşleştirme yok</span><span class="sxs-lookup"><span data-stu-id="73e86-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="73e86-350">[Bluetooth cihazını eşleştirmenize](hololens-connect-devices.md)sorun yaşıyorsanız aşağıdakileri deneyin:</span><span class="sxs-lookup"><span data-stu-id="73e86-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="73e86-351">**Ayarlar**  >  **cihazlar**' a gidin ve Bluetooth 'un açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="73e86-352">Varsa, devre dışı bırakın ve tekrar açın.</span><span class="sxs-lookup"><span data-stu-id="73e86-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="73e86-353">Bluetooth cihazınızın tam olarak ücretlendirildiğini veya yeni pillere sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="73e86-354">Hala bağlanamıyorsanız, [HoloLens 'i yeniden başlatın](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="73e86-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="73e86-355">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="73e86-356">USB-C mikrofonu çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="73e86-357">Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="73e86-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="73e86-358">Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="73e86-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="73e86-359">Bu mikrofonlardan birini HoloLens 'e takarken ses kaybolmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="73e86-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="73e86-360">Neyse ki basit bir çözüm vardır.</span><span class="sxs-lookup"><span data-stu-id="73e86-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="73e86-361">**Ayarlar**  ->  **sistem**  ->  **sesi**' nde yerleşik hoparlörleri **(analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="73e86-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="73e86-362">Mikrofon kaldırılıp daha sonra yeniden bağlansa, HoloLens bu ayarı unutmalıdır.</span><span class="sxs-lookup"><span data-stu-id="73e86-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C mikrofonları sorunlarını giderme](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="73e86-364">Ayarlarda kullanılabilir olarak listelenen cihazlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="73e86-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="73e86-365">HoloLens (1. gen) Bluetooth ses profillerini desteklemez.</span><span class="sxs-lookup"><span data-stu-id="73e86-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="73e86-366">Hoparlörler ve kulaklıklar gibi Bluetooth ses cihazları, HoloLens ayarlarında kullanılabilir olarak görünebilir, ancak desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="73e86-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="73e86-367">HoloLens 2, stereo kayıttan yürütme için Bluetooth A2DP ses profilini destekler.</span><span class="sxs-lookup"><span data-stu-id="73e86-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="73e86-368">Bluetooth çevresel bir bilgisayardan mikrofon yakalamaya izin veren Bluetooth BT ücretsiz profili, HoloLens 2 ' de desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="73e86-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="73e86-369">Bluetooth cihazını kullanırken sorun yaşıyorsanız, desteklenen bir cihaz olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="73e86-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="73e86-370">Desteklenen cihazlar şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="73e86-370">Supported devices include the following:</span></span>

- <span data-ttu-id="73e86-371">İngilizce-dil QWERTY Bluetooth klavyeleri (bunları, Holographic Klavyesini kullandığınız her yerde kullanabilirsiniz).</span><span class="sxs-lookup"><span data-stu-id="73e86-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="73e86-372">Bluetooth fareler.</span><span class="sxs-lookup"><span data-stu-id="73e86-372">Bluetooth mice.</span></span>
- <span data-ttu-id="73e86-373">[HoloLens](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="73e86-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="73e86-374">Diğer Bluetooth HID ve GATT cihazlarını, HoloLens 'larınızla birlikte eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="73e86-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="73e86-375">Ancak, cihazları gerçekten kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="73e86-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="73e86-376">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="73e86-376">Back to list</span></span>](#list)
