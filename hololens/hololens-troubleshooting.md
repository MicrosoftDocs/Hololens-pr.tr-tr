---
title: HoloLens Cihaz Sorunlarını Giderme
description: Cihaz sorunlarını ve sorun giderme tekniklerini takip etmek için HoloLens en yaygın çözümleri takip edin.
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
keywords: sorunlar, hata, sorun giderme, düzeltme, yardım, destek, HoloLens, öykünücü
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635458"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="144a4-104">Cihaz Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="144a4-104">Device Troubleshooting</span></span>

<span data-ttu-id="144a4-105">Bu makalede çeşitli yaygın sorun giderme sorunlarının HoloLens açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="144a4-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="144a4-106">Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="144a4-107">Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="144a4-108">**Bilinen Sorunlar**</span><span class="sxs-lookup"><span data-stu-id="144a4-108">**Known Issues**</span></span>
- [<span data-ttu-id="144a4-109">Remote Assist videosu 20 dakika sonra donuyor</span><span class="sxs-lookup"><span data-stu-id="144a4-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="144a4-110">Otomatik oturum açma, oturum açma bilgilerini sorar</span><span class="sxs-lookup"><span data-stu-id="144a4-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="144a4-111">Microsoft Edge başlatıla</span><span class="sxs-lookup"><span data-stu-id="144a4-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="144a4-112">Klavye özel karakterlere geçiş değil</span><span class="sxs-lookup"><span data-stu-id="144a4-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="144a4-113">Kilitli dosyaları indirerek hata göster yok</span><span class="sxs-lookup"><span data-stu-id="144a4-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="144a4-114">Cihaz Portalı karşıya yükleme/indirme zamanları dışında</span><span class="sxs-lookup"><span data-stu-id="144a4-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="144a4-115">Insider derlemesi ile yanıp sönen bir cihazda Insider önizleme kaydından sonra mavi ekran</span><span class="sxs-lookup"><span data-stu-id="144a4-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="144a4-116">OneDrive resimleri otomatik olarak karşıya yüklemez</span><span class="sxs-lookup"><span data-stu-id="144a4-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="144a4-117">**Genel**</span><span class="sxs-lookup"><span data-stu-id="144a4-117">**General**</span></span>
- [<span data-ttu-id="144a4-118">HoloLens yanıt vermiyor veya başlatılmayıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="144a4-119">"Düşük Disk Alanı" hatası</span><span class="sxs-lookup"><span data-stu-id="144a4-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="144a4-120">HataYazma</span><span class="sxs-lookup"><span data-stu-id="144a4-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="144a4-121">Oturum açam daha önce HoloLens başka biri için ayar olduğundan oturum aça bilmiyorum</span><span class="sxs-lookup"><span data-stu-id="144a4-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="144a4-122">Unity çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="144a4-123">Windows Cihaz Portalı düzgün çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="144a4-124">HoloLens Emulator çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="144a4-125">**Giriş**</span><span class="sxs-lookup"><span data-stu-id="144a4-125">**Input**</span></span>
- [<span data-ttu-id="144a4-126">Ses komutları çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="144a4-127">El girişi çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="144a4-128">**Bağlantı**</span><span class="sxs-lookup"><span data-stu-id="144a4-128">**Connectivity**</span></span>
- [<span data-ttu-id="144a4-129">Wi-Fi bağlantısı kuramıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="144a4-130">**Dış Cihazlar**</span><span class="sxs-lookup"><span data-stu-id="144a4-130">**External Devices**</span></span> 
- [<span data-ttu-id="144a4-131">Bluetooth cihazları eşleyemli değil</span><span class="sxs-lookup"><span data-stu-id="144a4-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="144a4-132">USB-C Mikrofon çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="144a4-133">Cihazlarda kullanılabilir Ayarlar cihazlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="144a4-134">Remote Assist videosu 20 dakika sonra donuyor</span><span class="sxs-lookup"><span data-stu-id="144a4-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-135">Remote Assist'in bu sorun için bir düzeltmesi olan daha yeni bir sürümü vardır.</span><span class="sxs-lookup"><span data-stu-id="144a4-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="144a4-136">Bu [sorunu önlemek için lütfen Remote Assist'i](holographic-store-apps.md#update-apps) en son sürüme güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="144a4-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-137">Bu Bilinen Sorunun önem derecesi nedeniyle Holographic sürüm 21H1'Windows geçici olarak duraklatıldı.</span><span class="sxs-lookup"><span data-stu-id="144a4-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="144a4-138">21H1 derlemesi artık yeniden kullanılabilir, bu nedenle cihazlar bir kez daha en son 21H1 derlemeye güncelleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="144a4-139">[Windows Holographic sürüm 21H1'in](hololens-release-notes.md#windows-holographic-version-21h1)en son sürümünde, Remote Assist'in bazı kullanıcıları 20 dakikadan fazla arama sırasında video donma durumuyla karşılandı.</span><span class="sxs-lookup"><span data-stu-id="144a4-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="144a4-140">Bu bilinen bir **sorundur.**</span><span class="sxs-lookup"><span data-stu-id="144a4-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="144a4-141">Geçici Çözümler</span><span class="sxs-lookup"><span data-stu-id="144a4-141">Workarounds</span></span>

<span data-ttu-id="144a4-142">Remote Assist'i daha yeni bir derlemeye güncelleştiremiyorsanız aşağıdaki adımları deneyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="144a4-143">Çağrılar arasında içinde yeniden başlatma</span><span class="sxs-lookup"><span data-stu-id="144a4-143">Restart in between calls</span></span>

<span data-ttu-id="144a4-144">Çağrılarınız 20 dakikadan uzun sürüyorsa ve bu sorunla karşılaşıyorsanız cihazınızı yeniden başlatmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="144a4-145">Cihazınızı Remote Assist çağrıları arasında yeniden başlatmak cihazınızı yeniler ve iyi bir durum haline geri döner.</span><span class="sxs-lookup"><span data-stu-id="144a4-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="144a4-146">Holographic'te bir cihazı Windows başlatmak için [sürüm 21H1'de](hololens-release-notes.md#windows-holographic-version-21h1) başlat menüsünü açın ve kullanıcı simgesini ve ardından Yeniden Başlat'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="144a4-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="144a4-147">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="144a4-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="144a4-148">Otomatik oturum açma, oturum açma bilgilerini sorar</span><span class="sxs-lookup"><span data-stu-id="144a4-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="144a4-149">Bir HoloLens 2 cihazı, Ayarlar Hesapları Oturum Açma Seçenekleri **->** ve Gerekli altında değeri Hiçbir zaman olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.  </span><span class="sxs-lookup"><span data-stu-id="144a4-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="144a4-150">Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="144a4-151">Bu bilinen bir **sorundur.**</span><span class="sxs-lookup"><span data-stu-id="144a4-151">This is a **known issue**.</span></span>

<span data-ttu-id="144a4-152">Bunun ne zaman oluştuğuna örnek:</span><span class="sxs-lookup"><span data-stu-id="144a4-152">Example of when this could occur:</span></span>

- <span data-ttu-id="144a4-153">Bir cihazı Windows Holographic sürüm 2004 'den (Derleme 19041.xxxx) Windows Holographic, sürüm 21H1'e güncelleştirme (Derleme 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="144a4-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="144a4-154">Bir cihazı aynı büyük derlemede büyük bir güncelleştirmeyi alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'Windows Holographic, sürüm 20H2</span><span class="sxs-lookup"><span data-stu-id="144a4-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="144a4-155">Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="144a4-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="144a4-156">Bu durum aşağıdakiler sırasında oluşmaz:</span><span class="sxs-lookup"><span data-stu-id="144a4-156">This should not occur during:</span></span>

- <span data-ttu-id="144a4-157">Aylık bakım güncelleştirmesi alan cihazlar</span><span class="sxs-lookup"><span data-stu-id="144a4-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="144a4-158">Yöntemlerle ilgili çalışma:</span><span class="sxs-lookup"><span data-stu-id="144a4-158">Work around methods:</span></span>

- <span data-ttu-id="144a4-159">PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="144a4-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="144a4-160">Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el [ile ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="144a4-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="144a4-161">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="144a4-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="144a4-162">Microsoft Edge başlatıla</span><span class="sxs-lookup"><span data-stu-id="144a4-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-163">Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş.</span><span class="sxs-lookup"><span data-stu-id="144a4-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="144a4-164">Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md)</span><span class="sxs-lookup"><span data-stu-id="144a4-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="144a4-165">Doğru değilse lütfen geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="144a4-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="144a4-166">Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi.</span><span class="sxs-lookup"><span data-stu-id="144a4-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="144a4-167">Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve uygulama güncelleştirmeleriyle Windows çözülemez.</span><span class="sxs-lookup"><span data-stu-id="144a4-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="144a4-168">Bu sorunla karşılaşıyorsanız ve [Windows'nin](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız, [lütfen Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: > Güncelleştirme'yi yükleme Windows, yükleme ve yapılandırma.</span><span class="sxs-lookup"><span data-stu-id="144a4-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="144a4-169">Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="144a4-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="144a4-170">Geri Bildirim Merkezi aracılığıyla hata Geri Bildirim Merkezi araştırmamıza yardımcı olacak!</span><span class="sxs-lookup"><span data-stu-id="144a4-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="144a4-171">Bu bilinen bir **sorundur.**</span><span class="sxs-lookup"><span data-stu-id="144a4-171">This is a **known issue**.</span></span>

[<span data-ttu-id="144a4-172">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="144a4-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="144a4-173">Klavye özel karakterlere geçiş değil</span><span class="sxs-lookup"><span data-stu-id="144a4-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="144a4-174">OOBE sırasında, kullanıcı bir iş veya okul hesabı seçtikten ve parolasını girdikten sonra &123 düğmesine dokunarak klavyedeki özel karakterlere geçmeye çalışırken özel karakterlere geçmemeye çalıştığı bir sorun vardır.</span><span class="sxs-lookup"><span data-stu-id="144a4-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="144a4-175">Bu bilinen bir **sorundur.**</span><span class="sxs-lookup"><span data-stu-id="144a4-175">This is a **known issue**.</span></span>

<span data-ttu-id="144a4-176">Çalışma:</span><span class="sxs-lookup"><span data-stu-id="144a4-176">Work-arounds:</span></span>
-   <span data-ttu-id="144a4-177">Metin alanına dokunarak klavyeyi kapatın ve yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="144a4-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="144a4-178">Parolanızı yanlış girin.</span><span class="sxs-lookup"><span data-stu-id="144a4-178">Incorrectly enter your password.</span></span> <span data-ttu-id="144a4-179">Klavye bir sonraki sefer yeniden edilse beklendiği gibi çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="144a4-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="144a4-180">Web Kimlik Doğrulaması'nın klavyesini kapatın ve başka **bir cihazdan Oturum açın'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="144a4-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="144a4-181">Yalnızca sayı giriliyorsa, kullanıcı belirli tuşlara basarak ve basılı tutarak genişletilmiş menüyü açabilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="144a4-182">USB klavyesi kullanma.</span><span class="sxs-lookup"><span data-stu-id="144a4-182">Using a USB keyboard.</span></span>

<span data-ttu-id="144a4-183">Bu durum şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="144a4-183">This does not affect:</span></span>
- <span data-ttu-id="144a4-184">Kişisel hesap kullanmayı seçen kullanıcılar.</span><span class="sxs-lookup"><span data-stu-id="144a4-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="144a4-185">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="144a4-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="144a4-186">Kilitli dosyaları indirme hatası yok</span><span class="sxs-lookup"><span data-stu-id="144a4-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="144a4-187">Bu, Insider **derlemesi** 20348.1403 Windows düzelten bilinen bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="144a4-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="144a4-188">Windows Holographic'in önceki derlemesinde kilitli bir dosyayı indirmeye çalışırken sonuç bir HTTP hata sayfası olurdu.</span><span class="sxs-lookup"><span data-stu-id="144a4-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="144a4-189">Windows Holographic sürüm 21H1 güncelleştirmesinde kilitli bir dosyayı indirmeye çalışıldı. Bunun sonucunda görünür bir şey olmuyor, dosya indir olmuyor ve hata yok.</span><span class="sxs-lookup"><span data-stu-id="144a4-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="144a4-190">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="144a4-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="144a4-191">Cihaz Portalı karşıya yükleme/indirme zamanları dışında</span><span class="sxs-lookup"><span data-stu-id="144a4-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="144a4-192">Bu, Insider **derlemesi** 20348.1403 Windows düzelten bilinen bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="144a4-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="144a4-193">Ssl Bağlantısını daha önce geçici çözümün bir parçası olarak devre dışı bırakdıysanız, yeniden etkinleştirmenizi kesinlikle öneririz.</span><span class="sxs-lookup"><span data-stu-id="144a4-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="144a4-194">Bazı müşteriler dosyaları karşıya yükleme veya indirme girişiminde bulunurken işlem askıda gibi görünebilir ve sonra zaman uzar veya hiçbir zaman tamamlanmadı.</span><span class="sxs-lookup"><span data-stu-id="144a4-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="144a4-195">Bu, bilinen 'dosya[kilitli'](#downloading-locked-files-doesnt-error) sorunundan ayrıdır. Bu durum Holographic Windows 2004, 20H2 ve 21H1 sürümleri pazar içinde derlemeleri etkiler.</span><span class="sxs-lookup"><span data-stu-id="144a4-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="144a4-196">Sorunun kök nedeni, Cihaz Portalı isteklerin işlenmesinde oluşan bir hatadır ve varsayılan https kullanılırken en tutarlı şekilde karşına çıkan sorundur.</span><span class="sxs-lookup"><span data-stu-id="144a4-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="144a4-197">Geçici çözüm</span><span class="sxs-lookup"><span data-stu-id="144a4-197">Workaround</span></span>

<span data-ttu-id="144a4-198">Wi-Fi ve UsbNcm için de aynı şekilde geçerli olan bu geçici çözüm, "SSL Bağlantısı" altında "gerekli" seçeneğini devre dışı bırakmaktır.</span><span class="sxs-lookup"><span data-stu-id="144a4-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="144a4-199">Bunu yapmak için Cihaz Portalı, **Sistem'e gidin** ve **Tercihler sayfasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="144a4-200">Cihaz Güvenliği bölümünde SSL **Bağlantısı'nın** **yerini bulun ve Gerekli'yi** devre dışı bırakmak için işaretini **kaldırın.**</span><span class="sxs-lookup"><span data-stu-id="144a4-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="144a4-201">Daha sonra Kullanıcı, https://(IP adresi) değil http://, dosya yükleme ve indirme gibi özellikler için de çalışır.</span><span class="sxs-lookup"><span data-stu-id="144a4-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="144a4-202">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="144a4-203">Insider derlemesi ile bir cihaz için Insider Preview 'dan kaydolduktan sonra mavi ekran</span><span class="sxs-lookup"><span data-stu-id="144a4-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="144a4-204">bu, bir ınsider preview derlemesinde bulunan kullanıcıları etkiler, yeni bir ınsider preview derlemesi ile HoloLens 2 ' yi geri ve ardından ınsider programından kaydolduğunu etkileyen bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="144a4-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="144a4-205">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="144a4-205">This is a **known issue**.</span></span>

<span data-ttu-id="144a4-206">Bu, şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="144a4-206">This does not affect:</span></span>
- <span data-ttu-id="144a4-207">Windows ınsider 'da kayıtlı olmayan kullanıcılar</span><span class="sxs-lookup"><span data-stu-id="144a4-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="144a4-208">Insiders</span><span class="sxs-lookup"><span data-stu-id="144a4-208">Insiders:</span></span>
    - <span data-ttu-id="144a4-209">Insider derlemeleri sürüm 18362. x olduğundan bir cihaz kaydedildiyse</span><span class="sxs-lookup"><span data-stu-id="144a4-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="144a4-210">Insider 'a imzalanmış bir 19041. x derlemesini düzder ve Insider programı 'nda kayıtlı kal</span><span class="sxs-lookup"><span data-stu-id="144a4-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="144a4-211">Geçici iş:</span><span class="sxs-lookup"><span data-stu-id="144a4-211">Work-around:</span></span> 
- <span data-ttu-id="144a4-212">Sorunu önleyin</span><span class="sxs-lookup"><span data-stu-id="144a4-212">Avoid the issue</span></span> 
    - <span data-ttu-id="144a4-213">Insider olmayan bir derlemeyi yakıp söndür.</span><span class="sxs-lookup"><span data-stu-id="144a4-213">Flash a non-insider build.</span></span> <span data-ttu-id="144a4-214">Normal aylık güncelleştirmelerden biri.</span><span class="sxs-lookup"><span data-stu-id="144a4-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="144a4-215">Insider Preview 'da kalın</span><span class="sxs-lookup"><span data-stu-id="144a4-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="144a4-216">Cihazı kırın</span><span class="sxs-lookup"><span data-stu-id="144a4-216">Reflash the device</span></span>

    1. <span data-ttu-id="144a4-217">[HoloLens 2 ' ye](hololens-recovery.md) , bağlantı kurulamadı, tamamen güçleyerek manuel moduna koyun.</span><span class="sxs-lookup"><span data-stu-id="144a4-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="144a4-218">Ardından, hacmi tutarken, güç düğmesine dokunun.</span><span class="sxs-lookup"><span data-stu-id="144a4-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="144a4-219">bilgisayara Bağlan ve gelişmiş kurtarma yardımcısı ' nı açın.</span><span class="sxs-lookup"><span data-stu-id="144a4-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="144a4-220">HoloLens 2 ' i varsayılan yapıya yakıp söndür.</span><span class="sxs-lookup"><span data-stu-id="144a4-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="144a4-221">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="144a4-222">OneDrive otomatik olarak resim karşıya yüklememez</span><span class="sxs-lookup"><span data-stu-id="144a4-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="144a4-223">HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="144a4-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="144a4-224">Bu bilinen bir **sorundur**.</span><span class="sxs-lookup"><span data-stu-id="144a4-224">This is a **known issue**.</span></span>

<span data-ttu-id="144a4-225">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="144a4-225">Workarounds:</span></span>

- <span data-ttu-id="144a4-226">İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="144a4-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="144a4-227">iş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama, çift oturum açma desteği sağlar).</span><span class="sxs-lookup"><span data-stu-id="144a4-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="144a4-228">OneDrive içindeki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="144a4-229">fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza fotoğraf el ile yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="144a4-230">bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="144a4-231">Düğmesini seçin **+** ve **upload**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="144a4-232">**Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun.</span><span class="sxs-lookup"><span data-stu-id="144a4-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="144a4-233">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="144a4-234">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="144a4-235">HoloLens yanıt vermiyor veya başlamıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="144a4-236">HoloLens başlamazsa:</span><span class="sxs-lookup"><span data-stu-id="144a4-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="144a4-237">Güç düğmesinin yanındaki LED 'ler soluk veya yalnızca bir tane kısa süreliğine yanıp sönse, [HoloLens ücretlendirmeniz gerekebilir.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="144a4-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="144a4-238">Güç düğmesine bastığınızda LED ışığı ışık, ancak ekranda hiçbir şey göremiyorsanız, [cihazın kalıcı olarak sıfırlanması](hololens-recovery.md#hard-reset-procedure)gerekir.</span><span class="sxs-lookup"><span data-stu-id="144a4-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="144a4-239">HoloLens dondurulmuş hale gelirse veya yanıt vermiyorsa:</span><span class="sxs-lookup"><span data-stu-id="144a4-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="144a4-240">bir led 'in beş bir kısmını devre dışı bırakır veya led 'ler yanıt vermiyorsa 15 saniye boyunca güç düğmesine basarak HoloLens kapatın.</span><span class="sxs-lookup"><span data-stu-id="144a4-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="144a4-241">HoloLens başlatmak için, güç düğmesine yeniden basın.</span><span class="sxs-lookup"><span data-stu-id="144a4-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="144a4-242">bu adımlar işe yoksa, [HoloLens 2 cihazınızı](hololens-recovery.md) veya [HoloLens (1. gen) cihazınızı](hololens1-recovery.md) kurtarmayı deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="144a4-243">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="144a4-244">"Yetersiz disk alanı" hatası</span><span class="sxs-lookup"><span data-stu-id="144a4-244">"Low Disk Space" error</span></span>

<span data-ttu-id="144a4-245">Aşağıdakilerden birini veya birkaçını yaparak depolama alanını boşaltmanız gerekir:</span><span class="sxs-lookup"><span data-stu-id="144a4-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="144a4-246">Kullanılmayan bazı boşlukları silin.</span><span class="sxs-lookup"><span data-stu-id="144a4-246">Delete some unused spaces.</span></span> <span data-ttu-id="144a4-247">**Ayarlar**  >  **sistem**  >  **alanları**' na gidin, artık ihtiyacınız olmayan bir alan seçin ve ardından **kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="144a4-248">Yerleştirdiğiniz hologramlar bölümünü kaldırın.</span><span class="sxs-lookup"><span data-stu-id="144a4-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="144a4-249">Fotoğraflar uygulamasındaki bazı resimleri ve videoları silin.</span><span class="sxs-lookup"><span data-stu-id="144a4-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="144a4-250">HoloLens bazı uygulamaları kaldırın.</span><span class="sxs-lookup"><span data-stu-id="144a4-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="144a4-251">**Tüm uygulamalar** listesinde, kaldırmak istediğiniz uygulamayı ve ardından **Kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="144a4-252">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="144a4-253">Ayarlama başarısız</span><span class="sxs-lookup"><span data-stu-id="144a4-253">Calibration fails</span></span>

<span data-ttu-id="144a4-254">Ayarlama çoğu kişi için çalışmalıdır, ancak ayarlama işleminin başarısız olduğu durumlar vardır.</span><span class="sxs-lookup"><span data-stu-id="144a4-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="144a4-255">Ayarlama hatasının bazı olası nedenleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="144a4-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="144a4-256">Ayarlama hedeflerini takip etme</span><span class="sxs-lookup"><span data-stu-id="144a4-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="144a4-257">Kirli veya çizilmiş cihaz vizörü veya cihaz vizörü düzgün şekilde konumlandırılmadı</span><span class="sxs-lookup"><span data-stu-id="144a4-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="144a4-258">Kirli veya çizik gözlük</span><span class="sxs-lookup"><span data-stu-id="144a4-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="144a4-259">Belirli türlerde iletişim ve gözlük (renkli kişi mercekler, bazı haksız kişi mercekler, IR engelleme gözlüğü, yüksek kaliteli gözlük, güneş gözlüğü veya benzer)</span><span class="sxs-lookup"><span data-stu-id="144a4-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="144a4-260">Daha fazla bilgi ve bazı eyeflash uzantıları</span><span class="sxs-lookup"><span data-stu-id="144a4-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="144a4-261">Cihazın gözlerinizi görmesini engelliyorsa, saç veya kalın eyecam çerçeveler</span><span class="sxs-lookup"><span data-stu-id="144a4-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="144a4-262">Dar gözler, uzun Eyelashes, amblyopia, nystagmus, bazı LASIK veya diğer gözle bazı durumlar gibi belirli gözle, göz önünde ve göz yormalileri</span><span class="sxs-lookup"><span data-stu-id="144a4-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="144a4-263">Ayarlama başarısız olursa, deneyin:</span><span class="sxs-lookup"><span data-stu-id="144a4-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="144a4-264">Cihazınızı Temizleme vizörü</span><span class="sxs-lookup"><span data-stu-id="144a4-264">Cleaning your device visor</span></span>
- <span data-ttu-id="144a4-265">Gözlerinizi Temizleme</span><span class="sxs-lookup"><span data-stu-id="144a4-265">Cleaning your glasses</span></span>
- <span data-ttu-id="144a4-266">Cihazınızın vizörü ' i mümkün olduğunca yakın bir şekilde iletme</span><span class="sxs-lookup"><span data-stu-id="144a4-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="144a4-267">Nesneleri (örneğin, saç) vizörü içinde hareket ettirmenin</span><span class="sxs-lookup"><span data-stu-id="144a4-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="144a4-268">Odadaki bir ışığı açma veya doğrudan güneş dışına taşıma</span><span class="sxs-lookup"><span data-stu-id="144a4-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="144a4-269">tüm yönergeleri izlediyseniz ve ayarlama hala başarısız olursa, Ayarlar ayarlama isteğini devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="144a4-270">Ayrıca, [geri bildirim merkezinde](hololens-feedback.md)geri bildirimde bulunarak bize bilgi verin.</span><span class="sxs-lookup"><span data-stu-id="144a4-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="144a4-271">Ayrıca, [görüntü renk veya parlaklık sorun giderme](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right) için ilgili bilgiler bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="144a4-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="144a4-272">göz konumları sistem tarafından hesaplandığından ıpd 'nin ayarlanması HoloLens 2 için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="144a4-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="144a4-273">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="144a4-274">HoloLens daha önce başka bir kişi için ayarlandığından oturum açılamıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="144a4-275">Cihazı daha [ **yanıp sönen moda** yerleştirebilir ve Gelişmiş kurtarma Yardımcısı 'nı kullanarak](hololens-recovery.md#clean-reflash-the-device) cihazı kurtarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="144a4-276">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="144a4-277">Unity çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-277">Unity isn't working</span></span>

- <span data-ttu-id="144a4-278">HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="144a4-279">unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="144a4-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="144a4-280">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="144a4-281">Windows Cihaz portalı düzgün çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="144a4-282">Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="144a4-283">Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir.</span><span class="sxs-lookup"><span data-stu-id="144a4-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="144a4-284">Bunların kullanılması hiçbir etkiye sahip olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="144a4-284">Using them will have no effect.</span></span> <span data-ttu-id="144a4-285">Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="144a4-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="144a4-286">Ayarlar geliştirici modunu etkinleştirdikten sonra, cihaz portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="144a4-287">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="144a4-288">HoloLens Emulator çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="144a4-289">HoloLens öykünücüsü hakkındaki bilgiler geliştirici belgelerimizde bulunur.</span><span class="sxs-lookup"><span data-stu-id="144a4-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="144a4-290">[HoloLens öykünücüsünün sorunlarını giderme](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="144a4-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="144a4-291">Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir.</span><span class="sxs-lookup"><span data-stu-id="144a4-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="144a4-292">Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.</span><span class="sxs-lookup"><span data-stu-id="144a4-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="144a4-293">Emulator PC web kamerasını kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="144a4-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="144a4-294">Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="144a4-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="144a4-295">Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="144a4-296">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="144a4-297">Sesli komutlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-297">Voice commands aren't working</span></span>

<span data-ttu-id="144a4-298">Cortana sesli komutlarınıza yanıt vermiyorsa Cortana açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="144a4-299">tüm uygulamalar listesinde,   >    >  değişiklikler yapmak için Cortana menü **not defteri**  >  **Ayarlar** ' ni seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="144a4-300">Ne söyleyebilirim hakkında daha fazla bilgi edinmek için bkz. [HoloLens sesinizi kullanma](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="144a4-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="144a4-301">HoloLens (1. gen) üzerinde, yerleşik konuşma tanıma yapılandırılabilir değildir.</span><span class="sxs-lookup"><span data-stu-id="144a4-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="144a4-302">Her zaman açıktır.</span><span class="sxs-lookup"><span data-stu-id="144a4-302">It is always turned on.</span></span> <span data-ttu-id="144a4-303">HoloLens 2 ' de, cihaz kurulumu sırasında hem konuşma tanımayı hem de Cortana açıp kullanmayacağınızı seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="144a4-304">HoloLens 2 sesinize yanıt vermiyorsa, konuşma tanımanın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="144a4-305">  >  **Ayarlar**  >  **gizlilik**  >  **konuşmayı** başlat ' a gidin ve **konuşma tanımayı** açın.</span><span class="sxs-lookup"><span data-stu-id="144a4-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="144a4-306">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="144a4-307">El girişi çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-307">Hand input isn't working</span></span>

<span data-ttu-id="144a4-308">HoloLens kendi ellerinizi görememesini sağlamak için, bunları hareket çerçevesinde tutmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="144a4-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="144a4-309">Karma Gerçeklik ana sayfası, kollarınızın ne zaman izleneceğini bilmenizi sağlayan geri bildirim sağlar.</span><span class="sxs-lookup"><span data-stu-id="144a4-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="144a4-310">HoloLens farklı sürümlerinde geri bildirim farklıdır:</span><span class="sxs-lookup"><span data-stu-id="144a4-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="144a4-311">HoloLens (1. genel) ' de, gaze imleci bir noktadan halka arasında değişir</span><span class="sxs-lookup"><span data-stu-id="144a4-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="144a4-312">HoloLens 2 ' de, elinizdeki bir kurşun kalem 'e yakın olduğunda parmak izi imleci görünür ve sla 'lar daha fazla olduğunda bir el ray görünür</span><span class="sxs-lookup"><span data-stu-id="144a4-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="144a4-313">Birçok modern uygulama, karma gerçeklik ana 'ya benzer giriş desenlerine uyar.</span><span class="sxs-lookup"><span data-stu-id="144a4-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="144a4-314">[HoloLens (1. gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) ve [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)' de el girişi kullanma hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="144a4-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="144a4-315">Birlikte çalışırken, bazı araç türlerinin el ile izleme ile çalışmadığına göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="144a4-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="144a4-316">Yaygın olarak kullanılan bir örnek, artışlarını devralarak kızılötesi ışınına eğilen ve derinlik kamerası tarafından alınmayan siyah bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="144a4-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="144a4-317">Çalışmanız lastik içeriyorsa, mavi veya gri gibi daha açık bir renk denemeyi öneririz.</span><span class="sxs-lookup"><span data-stu-id="144a4-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="144a4-318">Diğer bir örnek de büyük ölçekli bir örnektir ve bu, elinizin şeklinin gizlenmesi anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="144a4-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="144a4-319">En iyi sonuçlar için mümkün olduğunca form sığdırma olarak bulunan gloonları kullanmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="144a4-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="144a4-320">vizörü ' in parmak izleri veya kullanım alanları varsa, HoloLens ile birlikte gelen mikro fiber temizleme havsını kullanarak, vizörü 'yi temizleyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="144a4-321">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="144a4-322">Wi-Fi bağlanılamıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="144a4-323">HoloLens Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="144a4-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="144a4-324">Wi-Fi açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="144a4-325">bunu denetlemek için başlangıç hareketini kullanın, ardından **Ayarlar**  >  **Network &amp; ınternet**  >  **Wi-Fi** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="144a4-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="144a4-326">Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="144a4-327">Yönlendiriciye veya erişim noktasına yaklaşın.</span><span class="sxs-lookup"><span data-stu-id="144a4-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="144a4-328">Wi-Fi yönlendiricinizi yeniden başlatın ve [HoloLens yeniden başlatın](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="144a4-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="144a4-329">Yeniden bağlanmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-329">Try connecting again.</span></span>
- <span data-ttu-id="144a4-330">Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="144a4-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="144a4-331">Bu bilgileri üretici web sitesinde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="144a4-332">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="144a4-333">Bluetooth cihazlar eşleştirmiyor</span><span class="sxs-lookup"><span data-stu-id="144a4-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="144a4-334">[Bluetooth bir cihazla eşleştirme](hololens-connect-devices.md)sorunları yaşıyorsanız, aşağıdakileri deneyin:</span><span class="sxs-lookup"><span data-stu-id="144a4-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="144a4-335">**Ayarlar**  >  **cihazlar**' a gidin ve Bluetooth açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="144a4-336">Varsa, devre dışı bırakın ve tekrar açın.</span><span class="sxs-lookup"><span data-stu-id="144a4-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="144a4-337">Bluetooth cihazınızın tam olarak ücretlendirildiğini veya yeni pillere sahip olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="144a4-338">Hala bağlanamıyorsanız [HoloLens yeniden başlatın](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="144a4-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="144a4-339">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="144a4-340">USB-C mikrofonu çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="144a4-341">Bazı USB-C mikrofonların kendilerini bir mikrofon *ve* konuşmacı olarak doğru bir şekilde rapor ettiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="144a4-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="144a4-342">Bu, HoloLens ile değil, mikrofonla ilgili bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="144a4-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="144a4-343">bu mikrofonlardan birini HoloLens içine takarken, ses kaybolmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="144a4-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="144a4-344">Neyse ki basit bir çözüm vardır.</span><span class="sxs-lookup"><span data-stu-id="144a4-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="144a4-345">**Ayarlar**  ->  **sistem**  ->  **sesi**' nde, yerleşik hoparlörleri **(Analog özellik ses sürücüsü)** **varsayılan cihaz** olarak açıkça ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="144a4-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="144a4-346">HoloLens, mikrofon kaldırılıp daha sonra yeniden bağlansa bile bu ayarı unutmalıdır.</span><span class="sxs-lookup"><span data-stu-id="144a4-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C mikrofonları sorunlarını giderme](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="144a4-348">Ayarlar kullanılabilir olarak listelenen cihazlar çalışmıyor</span><span class="sxs-lookup"><span data-stu-id="144a4-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="144a4-349">HoloLens (1. gen) Bluetooth ses profillerini desteklemez.</span><span class="sxs-lookup"><span data-stu-id="144a4-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="144a4-350">hoparlörler ve kulaklıklar gibi Bluetooth ses cihazları HoloLens ayarlarında kullanılabilir olarak görünebilir, ancak desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="144a4-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="144a4-351">HoloLens 2, stereo kayıttan yürütme için Bluetooth A2DP ses profilini destekler.</span><span class="sxs-lookup"><span data-stu-id="144a4-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="144a4-352">Bluetooth, Bluetooth çevresel bilgisayardan mikrofon yakalamaya izin veren ücretsiz profil HoloLens 2 ' de desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="144a4-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="144a4-353">Bluetooth bir cihaz kullanırken sorun yaşıyorsanız, desteklenen bir cihaz olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="144a4-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="144a4-354">Desteklenen cihazlar şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="144a4-354">Supported devices include the following:</span></span>

- <span data-ttu-id="144a4-355">ingilizce-dil QWERTY Bluetooth klavyeler (bunları holographic klavyesini kullandığınız her yerde kullanabilirsiniz).</span><span class="sxs-lookup"><span data-stu-id="144a4-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="144a4-356">Bluetooth fareler.</span><span class="sxs-lookup"><span data-stu-id="144a4-356">Bluetooth mice.</span></span>
- <span data-ttu-id="144a4-357">[HoloLens click](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="144a4-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="144a4-358">diğer Bluetooth hıd ve gatt cihazlarını HoloLens ile birlikte eşleştirin.</span><span class="sxs-lookup"><span data-stu-id="144a4-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="144a4-359">ancak, cihazları gerçekten kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="144a4-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="144a4-360">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="144a4-360">Back to list</span></span>](#list)
