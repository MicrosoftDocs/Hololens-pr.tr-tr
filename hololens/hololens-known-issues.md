---
title: HoloLens için bilinen sorunlar
description: Unity ve diğer platformları kullanan HoloLens müşterilerini ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemizi takip Windows Cihaz Portalı.
keywords: sorun giderme, bilinen sorun, yardım
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379071"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="d460c-104">HoloLens için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-104">Known issues for HoloLens</span></span>

<span data-ttu-id="d460c-105">HoloLens cihazları için bilinen sorunların güncel listesi burada vemektedir.</span><span class="sxs-lookup"><span data-stu-id="d460c-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="d460c-106">Garip bir davranış görüyorsanız önce buraya göz sınız.</span><span class="sxs-lookup"><span data-stu-id="d460c-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="d460c-107">Bu liste yeni sorunlar keşfedildi veya raporlandıkça ya da gelecek HoloLens yazılım güncelleştirmeleri ile ilgili sorunlar giderildikça güncelleştirilecek.</span><span class="sxs-lookup"><span data-stu-id="d460c-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="d460c-108">Engellemeye neden olan bir sorun fark ediyorsanız lütfen bu sorunu [Geri Bildirim Merkezi.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="d460c-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="d460c-109">Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="d460c-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="d460c-110">Tüm HoloLens nesilleri için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="d460c-111">HoloLens 2 cihazları için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="d460c-112">HoloLens için bilinen sorunlar (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="d460c-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="d460c-113">HoloLens öykünücüsü için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="d460c-114">Tüm HoloLens nesilleri için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="d460c-115">Unity</span><span class="sxs-lookup"><span data-stu-id="d460c-115">Unity</span></span>

- <span data-ttu-id="d460c-116">Bkz. [Unity'nin](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens geliştirmesi için önerilen en güncel sürümü için araçları yükleme.</span><span class="sxs-lookup"><span data-stu-id="d460c-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="d460c-117">Unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="d460c-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="d460c-118">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="d460c-118">Windows Device Portal</span></span>

- <span data-ttu-id="d460c-119">Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="d460c-120">Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir.</span><span class="sxs-lookup"><span data-stu-id="d460c-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="d460c-121">Bunları kullanmanın hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-121">Using them will have no effect.</span></span> <span data-ttu-id="d460c-122">Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="d460c-122">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="d460c-123">Ayarlar'da Geliştirici Modu etkinleştirildikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="d460c-124">OneDrive kamera karşıya yükleme</span><span class="sxs-lookup"><span data-stu-id="d460c-124">OneDrive camera upload</span></span>

<span data-ttu-id="d460c-125">HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="d460c-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="d460c-126">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="d460c-126">Workarounds:</span></span>

- <span data-ttu-id="d460c-127">İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="d460c-128">İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması çift oturum açmayı destekler).</span><span class="sxs-lookup"><span data-stu-id="d460c-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="d460c-129">OneDrive'Microsoft hesabı profilden otomatik, arka plan kameralı rolle karşıya yükleme özelliğini etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="d460c-130">Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="d460c-131">Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızla oturum asanıza.</span><span class="sxs-lookup"><span data-stu-id="d460c-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="d460c-132">Düğmesini seçin **+** ve Karşıya **Yükle'yi seçin.**</span><span class="sxs-lookup"><span data-stu-id="d460c-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="d460c-133">Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.**</span><span class="sxs-lookup"><span data-stu-id="d460c-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="d460c-134">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="d460c-135">HoloLens 2 cihazları için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-135">Known issues for HoloLens 2 devices</span></span>

### <a name="device-using-auto-login-asks-for-log-in"></a><span data-ttu-id="d460c-136">Otomatik oturum açma kullanan cihaz oturum açma bilgilerini sorar</span><span class="sxs-lookup"><span data-stu-id="d460c-136">Device using Auto-login asks for log-in</span></span>

<span data-ttu-id="d460c-137">Bir HoloLens 2 cihazı, Ayarlar Hesapları Oturum Açma Seçenekleri -> ve Gerekli altında değeri Asla olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.  </span><span class="sxs-lookup"><span data-stu-id="d460c-137">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="d460c-138">Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-138">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span>

<span data-ttu-id="d460c-139">Bunun ne zaman oluştuğuna örnek:</span><span class="sxs-lookup"><span data-stu-id="d460c-139">Example of when this could occur:</span></span>

- <span data-ttu-id="d460c-140">Bir cihazı Windows Holographic sürüm 2004'den (Derleme 19041.xxxx) Windows Holographic, sürüm 21H1'e güncelleştirme (Derleme 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="d460c-140">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="d460c-141">Bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'ü Windows Holographic, sürüm 20H2</span><span class="sxs-lookup"><span data-stu-id="d460c-141">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="d460c-142">Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="d460c-142">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="d460c-143">Bu durum aşağıdakiler sırasında oluşmaz:</span><span class="sxs-lookup"><span data-stu-id="d460c-143">This should not occur during:</span></span>

- <span data-ttu-id="d460c-144">Aylık bakım güncelleştirmesi alan cihazlar</span><span class="sxs-lookup"><span data-stu-id="d460c-144">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="d460c-145">Yöntemlerle ilgili çalışma:</span><span class="sxs-lookup"><span data-stu-id="d460c-145">Work around methods:</span></span>

- <span data-ttu-id="d460c-146">PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="d460c-146">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="d460c-147">Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el [ile ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="d460c-147">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="d460c-148">Microsoft Edge başlatıla</span><span class="sxs-lookup"><span data-stu-id="d460c-148">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="d460c-149">Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş.</span><span class="sxs-lookup"><span data-stu-id="d460c-149">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="d460c-150">Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md)</span><span class="sxs-lookup"><span data-stu-id="d460c-150">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="d460c-151">Doğru değilse lütfen geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="d460c-151">If it is not, please file feedback.</span></span>

<span data-ttu-id="d460c-152">Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi.</span><span class="sxs-lookup"><span data-stu-id="d460c-152">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="d460c-153">Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve Windows veya uygulama güncelleştirmeleriyle çözülemez.</span><span class="sxs-lookup"><span data-stu-id="d460c-153">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="d460c-154">Bu sorunla karşılaşıyorsanız ve [Windows'un](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız lütfen [Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: >'i yükleme, yükleme ve yapılandırma adımları Windows Update.</span><span class="sxs-lookup"><span data-stu-id="d460c-154">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="d460c-155">Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="d460c-155">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="d460c-156">Geri Bildirim Merkezi aracılığıyla hata Geri Bildirim Merkezi araştırmamıza yardımcı olacak!</span><span class="sxs-lookup"><span data-stu-id="d460c-156">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="d460c-157">Klavye özel karakterlere geçmez</span><span class="sxs-lookup"><span data-stu-id="d460c-157">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="d460c-158">OOBE sırasında, kullanıcı bir iş veya okul hesabı seçtikten ve parolasını girdikten sonra &123 düğmesine dokunarak klavyedeki özel karakterlere geçmeye çalışırken özel karakterlere geçmemeye çalıştığı bir sorun vardır.</span><span class="sxs-lookup"><span data-stu-id="d460c-158">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span>

<span data-ttu-id="d460c-159">Çalışma:</span><span class="sxs-lookup"><span data-stu-id="d460c-159">Work-arounds:</span></span>
-   <span data-ttu-id="d460c-160">Metin alanına dokunarak klavyeyi kapatın ve yeniden açın.</span><span class="sxs-lookup"><span data-stu-id="d460c-160">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="d460c-161">Parolanızı yanlış girin.</span><span class="sxs-lookup"><span data-stu-id="d460c-161">Incorrectly enter your password.</span></span> <span data-ttu-id="d460c-162">Klavye bir sonraki sefer yeniden edilse beklendiği gibi çalışacaktır.</span><span class="sxs-lookup"><span data-stu-id="d460c-162">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="d460c-163">Web Kimlik Doğrulaması'nın klavyesini kapatın ve başka **bir cihazdan Oturum açın'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="d460c-163">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="d460c-164">Yalnızca sayı giriliyorsa, kullanıcı belirli tuşlara basarak ve basılı tutarak genişletilmiş bir menü açabilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-164">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="d460c-165">USB klavyesi kullanma.</span><span class="sxs-lookup"><span data-stu-id="d460c-165">Using a USB keyboard.</span></span>

<span data-ttu-id="d460c-166">Bu durum şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="d460c-166">This does not affect:</span></span>
- <span data-ttu-id="d460c-167">Kişisel hesap kullanmayı seçen kullanıcılar.</span><span class="sxs-lookup"><span data-stu-id="d460c-167">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a><span data-ttu-id="d460c-168">Insider önizleme derlemelerinin bir Insider derlemesi ile yeniden renkle gösterilen cihaz kaydından sonra mavi ekran gösterilir</span><span class="sxs-lookup"><span data-stu-id="d460c-168">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with an Insider build</span></span>

<span data-ttu-id="d460c-169">Bu, Bir Insider önizleme derlemesine sahip olan kullanıcıları etkileyen, HoloLens 2'lerini yeni bir insider önizleme derlemesi ile yeniden yazdıran ve insider programından kaydı s olan kullanıcıları etkileyen bir sorundur.</span><span class="sxs-lookup"><span data-stu-id="d460c-169">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span>

<span data-ttu-id="d460c-170">Bu durum şunları etkilemez:</span><span class="sxs-lookup"><span data-stu-id="d460c-170">This does not affect:</span></span>
- <span data-ttu-id="d460c-171">Windows Insider'a kayıtlı Windows Insider</span><span class="sxs-lookup"><span data-stu-id="d460c-171">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="d460c-172">Içerdekiler:</span><span class="sxs-lookup"><span data-stu-id="d460c-172">Insiders:</span></span>
    - <span data-ttu-id="d460c-173">Insider derlemeleri 18362.x sürümünden beri bir cihaz kayıtlı ise</span><span class="sxs-lookup"><span data-stu-id="d460c-173">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="d460c-174">Insider imzalı bir 19041.x derlemesi sönerse VE Insider programına kayıtlı kalır</span><span class="sxs-lookup"><span data-stu-id="d460c-174">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="d460c-175">Üzerinde çalışma:</span><span class="sxs-lookup"><span data-stu-id="d460c-175">Work-around:</span></span> 
- <span data-ttu-id="d460c-176">Sorundan kaçının</span><span class="sxs-lookup"><span data-stu-id="d460c-176">Avoid the issue</span></span> 
    - <span data-ttu-id="d460c-177">İçinde olmayan bir derlemeyi flash iletir.</span><span class="sxs-lookup"><span data-stu-id="d460c-177">Flash a non-insider build.</span></span> <span data-ttu-id="d460c-178">Normal aylık güncelleştirmelerden biri.</span><span class="sxs-lookup"><span data-stu-id="d460c-178">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="d460c-179">Insider Preview'da kalın</span><span class="sxs-lookup"><span data-stu-id="d460c-179">Stay on Insider Preview</span></span>
- <span data-ttu-id="d460c-180">Cihaza ters eğik çizgi</span><span class="sxs-lookup"><span data-stu-id="d460c-180">Reflash the device</span></span>

    1. <span data-ttu-id="d460c-181">[Bağlanmadan tamamen kapatarak HoloLens 2'nin](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) el ile yanıp sönme moduna alın.</span><span class="sxs-lookup"><span data-stu-id="d460c-181">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="d460c-182">Ardından Birim'i basılı tutarken Güç düğmesine dokunun.</span><span class="sxs-lookup"><span data-stu-id="d460c-182">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="d460c-183">Bilgisayara bağlanarak Gelişmiş Kurtarma Yardımcı'sı'nu açın.</span><span class="sxs-lookup"><span data-stu-id="d460c-183">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="d460c-184">HoloLens 2'nin varsayılan derlemesine flash iletir.</span><span class="sxs-lookup"><span data-stu-id="d460c-184">Flash the HoloLens 2 to the default build.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="d460c-185">HoloLens için bilinen sorunlar (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="d460c-185">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="d460c-186">Sanal ağ üzerinden HoloLens'e bağlanamıyor ve Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d460c-186">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="d460c-187">Son Güncelleştirme: 08.08. @ 17.11 - Visual Studio, bu sorunun düzeltmesini içeren VS 2019 Sürüm 16.2'yi yayımladı.</span><span class="sxs-lookup"><span data-stu-id="d460c-187">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="d460c-188">Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="d460c-188">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="d460c-189">Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı.</span><span class="sxs-lookup"><span data-stu-id="d460c-189">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="d460c-190">Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="d460c-190">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="d460c-191">Sorunun kök nedeni: HoloLens'lerinde uygulamaları dağıtmak ve hata ayıklamak için Visual Studio 2015 veya önceki Visual Studio 2017 sürümlerini kullanan ve daha sonra aynı HoloLens ile Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan kullanıcılar etkilenecektir.</span><span class="sxs-lookup"><span data-stu-id="d460c-191">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="d460c-192">Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.</span><span class="sxs-lookup"><span data-stu-id="d460c-192">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="d460c-193">Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="d460c-193">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="d460c-194">\<ip\>80004005 hatası nedeniyle üzerinde geliştirici lisansı alınemedi.</span><span class="sxs-lookup"><span data-stu-id="d460c-194">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="d460c-195">Geçici çözüm</span><span class="sxs-lookup"><span data-stu-id="d460c-195">Workaround</span></span>

<span data-ttu-id="d460c-196">Ekibimiz şu anda bir düzeltme üzerinde çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="d460c-196">Our team is currently working on a fix.</span></span> <span data-ttu-id="d460c-197">Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d460c-197">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="d460c-198">Visual Studio'yu açın.</span><span class="sxs-lookup"><span data-stu-id="d460c-198">Open Visual Studio.</span></span>

1. <span data-ttu-id="d460c-199">Dosya **Yeni**  >  **Proje'yi**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="d460c-199">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="d460c-200">**Visual C#**  >  **Windows Masaüstü Konsol Uygulaması**  >  **(.NET Framework) öğesini seçin.**</span><span class="sxs-lookup"><span data-stu-id="d460c-200">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="d460c-201">Projeye bir ad verin (örneğin, "Holomersdeploymentdüzeltmesini") ve Framework 'Ün en az .NET Framework 4,5 ' e ayarlandığından emin olun ve ardından **Tamam**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-201">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="d460c-202">Çözüm Gezgini ' deki **Başvurular** düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin ( **Gözden** geçirme bölümüne ve sonra da **gözatatıon**' ı seçin):</span><span class="sxs-lookup"><span data-stu-id="d460c-202">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="d460c-203">10.0.18362.0 yüklü değilse, en son sürümü kullanın.</span><span class="sxs-lookup"><span data-stu-id="d460c-203">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="d460c-204">Çözüm Gezgini projede projeye sağ tıklayın ve   >  **var olan öğe** Ekle ' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-204">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="d460c-205">C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 'e gidin ve filtreyi **tüm dosyalar ( \* . \* )** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="d460c-205">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="d460c-206">SirepClient.dll ve SshClient.dll her ikisini de seçin ve **Ekle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-206">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="d460c-207">Çözüm Gezgini her iki dosyayı da bulun ve seçin (dosyalar listesinin en altında olmaları gerekir) ve **her zaman kopyalamak** için **Özellikler** penceresinde **Çıkış Dizinine Kopyala** ' yı değiştirin.</span><span class="sxs-lookup"><span data-stu-id="d460c-207">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="d460c-208">Dosyanın üst kısmında, mevcut deyimler listesine aşağıdakileri ekleyin `using` :</span><span class="sxs-lookup"><span data-stu-id="d460c-208">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="d460c-209">İçinde `static void Main(...)` , aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="d460c-209">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="d460c-210">Yapı   >  **Yapı çözümünü** seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-210">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="d460c-211">Derlenmiş .exe dosyasını içeren klasöre bir komut Istemi penceresi ve CD açın (örneğin, C:\myprojeler\windows Holomersdeploymentfix\bin\debug).</span><span class="sxs-lookup"><span data-stu-id="d460c-211">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="d460c-212">Yürütülebilir dosyayı çalıştırın ve bir komut satırı bağımsız değişkeni olarak cihazın IP adresini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="d460c-212">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="d460c-213">(USB kullanarak bağlıysanız 127.0.0.1 kullanabilirsiniz, aksi takdirde cihazın Wi-Fi IP adresini kullanamazsınız.)  Örneğin, "Holomersdeploymentdüzeltmesini 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="d460c-213">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="d460c-214">Araç herhangi bir ileti olmadan çıkıldıktan sonra (Bu yalnızca birkaç saniye sürer), artık Visual Studio 2017 veya daha yeni bir sürümü dağıtabilir ve hata ayıklaması yapabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-214">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="d460c-215">Aracın devam eden kullanımı gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="d460c-215">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="d460c-216">Kullanılabilir hale geldiğinde daha fazla güncelleştirme sağlayacağız.</span><span class="sxs-lookup"><span data-stu-id="d460c-216">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="d460c-217">HoloLens 'te Microsoft Store ve uygulamaları başlatan sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-217">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="d460c-218">Son güncelleştirme: 4/2 @ 10-sorun çözüldü.</span><span class="sxs-lookup"><span data-stu-id="d460c-218">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="d460c-219">HoloLens üzerinde Microsoft Store ve uygulamaları başlatmaya çalışırken sorunlarla karşılaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-219">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="d460c-220">Arka plan uygulama güncelleştirmeleri, bir veya daha fazla bağımlı uygulama çalışmaya devam ederken belirli bir sırada çerçeve paketlerinin daha yeni bir sürümünü dağıtırken sorunun oluştuğunu belirledik.</span><span class="sxs-lookup"><span data-stu-id="d460c-220">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="d460c-221">Bu durumda, bir otomatik uygulama güncelleştirmesi .NET Native Framework 'ün yeni bir sürümünü (sürüm 10.0.25531 ile 10.0.27413) dağıttığı, çalışan uygulamaların, Framework 'ün önceki sürümünü kullanan tüm çalışan uygulamalar için düzgün şekilde güncelleştirileceğinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="d460c-221">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="d460c-222">Çerçeve güncelleştirmesi için akış aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="d460c-222">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="d460c-223">Yeni çerçeve paketi mağazadan indirilir ve yüklenir.</span><span class="sxs-lookup"><span data-stu-id="d460c-223">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="d460c-224">Eski Framework kullanan tüm uygulamalar, daha yeni sürümü kullanmak için ' güncelleştirildi '.</span><span class="sxs-lookup"><span data-stu-id="d460c-224">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="d460c-225">2. adım tamamlanmadan önce kesintiye uğrarsa, daha yeni Framework 'ün kaydolmadığı tüm uygulamalar Başlangıç menüsünden başlayamaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-225">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="d460c-226">HoloLens üzerinde herhangi bir uygulamanın bu sorundan etkilendiğine inandık.</span><span class="sxs-lookup"><span data-stu-id="d460c-226">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="d460c-227">Bazı kullanıcılar, askıda olan uygulamaları kapatan ve geri bildirim merkezi gibi diğer uygulamaları başlatan rapor verdi, 3B görüntüleyici veya fotoğraflar bu sorunu çözer. ancak, bu sürenin %100 ' i çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-227">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="d460c-228">Kök sunuyoruz, bu sorunun güncelleştirmenin kendisinin neden olmadığı, ancak işletim sisteminde .NET Native Framework güncelleştirmesiyle yanlış işlenmekte olan bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="d460c-228">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="d460c-229">Bir onarım belirlediğimiz ve bu güncelleştirmeyi içeren bir güncelleştirme (OS sürüm 17763,380) yayımladığımızda duyurmaktan memnuniyet duyuyoruz.</span><span class="sxs-lookup"><span data-stu-id="d460c-229">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="d460c-230">Cihazınızın güncelleştirmeyi alıp almaz:</span><span class="sxs-lookup"><span data-stu-id="d460c-230">To see if your device can take the update:</span></span>

1. <span data-ttu-id="d460c-231">Ayarlar uygulamasına gidin ve **güncelleştirme & güvenlik**' i açın.</span><span class="sxs-lookup"><span data-stu-id="d460c-231">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="d460c-232">**Güncelleştirmeleri denetle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-232">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="d460c-233">17763,380 güncelleştirmesi varsa, uygulama askıda kalma hatasına yönelik çözümü almak için lütfen bu yapıya güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="d460c-233">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="d460c-234">İşletim sisteminin bu sürümüne güncelleştirme yapıldığında uygulamalar beklendiği gibi çalışmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d460c-234">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="d460c-235">Ayrıca, her HoloLens işletim sistemi sürümünde yaptığımız gibi, [Microsoft Indirme merkezi](https://aka.ms/hololensdownload/10.0.17763.380)'ne FFU görüntüsünü naklettik.</span><span class="sxs-lookup"><span data-stu-id="d460c-235">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="d460c-236">Güncelleştirmeyi yapmak istemiyorsanız, 3/29 itibariyle Microsoft Store UWP uygulamasının yeni bir sürümünü yayımladık.</span><span class="sxs-lookup"><span data-stu-id="d460c-236">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="d460c-237">Mağaza 'nın güncelleştirilmiş sürümüne sahip olduktan sonra:</span><span class="sxs-lookup"><span data-stu-id="d460c-237">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="d460c-238">Mağazayı açın ve yüklendiğini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="d460c-238">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="d460c-239">Menüyü açmak için Bloom hareketini kullanın.</span><span class="sxs-lookup"><span data-stu-id="d460c-239">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="d460c-240">Daha önce bozulan uygulamaları açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="d460c-240">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="d460c-241">Hala başlatılamaz, bozuk uygulamanın simgesine dokunup basılı tutun ve Kaldır ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="d460c-241">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="d460c-242">Bu uygulamaları mağazadan yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="d460c-242">Reinstall these apps from the store.</span></span>

<span data-ttu-id="d460c-243">Cihazınız hala uygulama yükleyeerişemiyorsanız, aşağıdaki adımları izleyerek .NET Native Framework ve çalışma zamanının bir sürümünü indirme merkezi aracılığıyla dışarıdan yükleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d460c-243">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="d460c-244">Lütfen [Bu zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi ' nden indirin.</span><span class="sxs-lookup"><span data-stu-id="d460c-244">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="d460c-245">Unzippıng iki dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d460c-245">Unzipping will produce two files.</span></span>  <span data-ttu-id="d460c-246">Microsoft. NET. Native. Runtime. 1.7. appx ve Microsoft. NET. Native. Framework. 1.7. appx.</span><span class="sxs-lookup"><span data-stu-id="d460c-246">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="d460c-247">Lütfen cihazınızın dev olarak kilidinin açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="d460c-247">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="d460c-248">Daha önce yapmadıysanız yönergeler için bkz. [Windows cihaz portalını kullanma](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) .</span><span class="sxs-lookup"><span data-stu-id="d460c-248">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="d460c-249">Daha sonra Windows cihaz portalına ulaşmak istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="d460c-249">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="d460c-250">Önerimiz bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak yapmanız gerekir http://127.0.0.1:10080 .</span><span class="sxs-lookup"><span data-stu-id="d460c-250">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="d460c-251">Windows cihaz portalı 'nı yükledikten sonra, indirdiğiniz iki dosyayı "Dışarıdan yükleme" yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d460c-251">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="d460c-252">Bunu yapmak için, **uygulamalar** bölümüne ulaşana ve **uygulamalar**' ı seçene kadar sol taraftaki çubuğa gitmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d460c-252">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="d460c-253">Ardından aşağıdakine benzer bir ekran görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="d460c-253">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="d460c-254">**Uygulamayı yüklemeyi** belirten bölüme gitmek ve bu iki appx dosyasının sıkıştırılanmasını nereden kaldırıtabileceğiniz konusunda gezinmek istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="d460c-254">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="d460c-255">Tek seferde yalnızca bir tane yapabilirsiniz, ilk olanı seçtikten sonra dağıt bölümünde "git" düğmesine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="d460c-255">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="d460c-256">İkinci APPX dosyası için bunu yapın.</span><span class="sxs-lookup"><span data-stu-id="d460c-256">Then do this for the second APPX file.</span></span>

   ![Side-Loaded uygulamasını yüklemek için Windows cihaz portalı](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="d460c-258">Bu noktada, uygulamalarınızın yeniden çalışmaya başlaması ve mağazaya de başlayabilmeniz gerektiğini düşünüyoruz.</span><span class="sxs-lookup"><span data-stu-id="d460c-258">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="d460c-259">Bazı durumlarda, etkilenen uygulamaların başlatılması için önce 3B görüntüleyici uygulamasını başlatma ek adımını çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="d460c-259">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="d460c-260">Bu sorunu çözmemiz için işlem boyunca yaptığımız ve başarılı karma gerçeklik deneyimleri oluşturmak için Topluluğumuzdan çalışmaya devam ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="d460c-260">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="d460c-261">Cihaz Güncelleştirmesi</span><span class="sxs-lookup"><span data-stu-id="d460c-261">Device Update</span></span>

- <span data-ttu-id="d460c-262">30 saniye yeni bir güncelleştirmeden sonra kabuk bir kez kaybolabilir.</span><span class="sxs-lookup"><span data-stu-id="d460c-262">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="d460c-263">Oturumunuzu sürdürmeniz için lütfen **Bloom** hareketini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="d460c-263">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="d460c-264">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d460c-264">Visual Studio</span></span>

- <span data-ttu-id="d460c-265">Bkz. Visual Studio 'nun en güncel sürümü için, HoloLens geliştirme için önerilen [araçları kurma](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) .</span><span class="sxs-lookup"><span data-stu-id="d460c-265">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="d460c-266">Visual Studio 'dan HoloLens 'e bir uygulama dağıttığınızda şu hatayı görebilirsiniz: **istenen işlem Kullanıcı eşlemeli bir bölümün açık olduğu bir dosya üzerinde gerçekleştirilemiyor. (HRESULT özel durumu: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="d460c-266">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="d460c-267">Bu durumda yeniden deneyin ve dağıtımınız genellikle başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="d460c-267">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="d460c-268">API</span><span class="sxs-lookup"><span data-stu-id="d460c-268">API</span></span>

- <span data-ttu-id="d460c-269">Uygulama, [odak noktasını](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) kullanıcının arkasında veya normal olarak kameraya ayarlarsa, hologramlar karma gerçeklik yakalama fotoğraflarında veya videolarında görünmez.</span><span class="sxs-lookup"><span data-stu-id="d460c-269">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="d460c-270">Bu hata Windows 'da düzeltilene kadar, uygulamalar [odak noktasını](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) etkin bir şekilde ayarladıklarında, düzlemi normalin daha ters kamera iletme (örneğin, normal =-Camera. ileri) olarak ayarlandığından emin olunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d460c-270">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="d460c-271">Xbox Kablosuz denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="d460c-271">Xbox Wireless Controller</span></span>

- <span data-ttu-id="d460c-272">Xbox Kablosuz denetleyicisi, HoloLens ile kullanılmadan önce güncelleştirilmeleri gerekir.</span><span class="sxs-lookup"><span data-stu-id="d460c-272">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="d460c-273">Denetleyicinizi bir HoloLens ile eşleştirmeye [çalışmadan önce güncel olduğunuzdan emin](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) olun.</span><span class="sxs-lookup"><span data-stu-id="d460c-273">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="d460c-274">Xbox Kablosuz denetleyicisi bağlıyken HoloLens 'nizi yeniden başlattıktan sonra denetleyici, HoloLens 'e otomatik olarak yeniden bağlanmaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-274">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="d460c-275">Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatılıncaya kadar yavaş yanıp sönecektir.</span><span class="sxs-lookup"><span data-stu-id="d460c-275">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="d460c-276">Denetleyicinizi hemen yeniden bağlamak için, ışık kapanmadan, rehber düğmesini basılı tutarak denetleyiciyi kapatın.</span><span class="sxs-lookup"><span data-stu-id="d460c-276">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="d460c-277">Denetleyicinizi yeniden açtığınızda, HoloLens 'e yeniden bağlanır.</span><span class="sxs-lookup"><span data-stu-id="d460c-277">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="d460c-278">Xbox Kablosuz denetleyicisi bağlıyken HoloLens 'niz bekleme moduna girerse, denetleyicideki herhangi bir giriş HoloLens 'i uyandırır.</span><span class="sxs-lookup"><span data-stu-id="d460c-278">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="d460c-279">Bunu kullanarak işiniz bittiğinde denetleyicinizi devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-279">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="d460c-280">HoloLens öykünücüsü için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="d460c-280">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="d460c-281">Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir.</span><span class="sxs-lookup"><span data-stu-id="d460c-281">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="d460c-282">Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-282">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="d460c-283">Öykünücüsünde PC web kamerasını kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="d460c-283">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="d460c-284">Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="d460c-284">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="d460c-285">Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d460c-285">You can still capture Mixed Reality videos and images.</span></span>
