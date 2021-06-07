---
title: HoloLens 'i çalıştırmak için sesinizi kullanın
description: Cortana 'Nın, ses komutları, dikte ve hologram etkileşimleri dahil, HoloLens karma gerçeklik cihazlarınızda her türlü şeyi nasıl sağlayabileceğinize nasıl yardımcı olabileceğini öğrenin.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380241"
---
# <a name="use-your-voice-to-operate-hololens"></a><span data-ttu-id="23419-104">HoloLens 'i çalıştırmak için sesinizi kullanın</span><span class="sxs-lookup"><span data-stu-id="23419-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="23419-105">Sesinizi, hızlı bir fotoğraf alma veya uygulama açma gibi HoloLens üzerinde neredeyse her şey yapmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="23419-106">Birçok sesli komut HoloLens 'te yerleşiktir, diğerleri Cortana aracılığıyla kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="23419-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="23419-107">Bu makalede, HoloLens ve holographic dünyayı sesli ve Cortana ile nasıl denetleyeceğini öğretilir.</span><span class="sxs-lookup"><span data-stu-id="23419-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="23419-108">Konuşma yalnızca [bazı dillerde](hololens2-language-support.md)desteklenir.</span><span class="sxs-lookup"><span data-stu-id="23419-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="23419-109">Konuşma dili, klavye dilini değil Windows görüntüleme diline dayalıdır.</span><span class="sxs-lookup"><span data-stu-id="23419-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="23419-110">**Ayarlar**  >  **saat ve dil**  >  **dili**' ni seçerek Windows görüntüleme dilini doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <a name="built-in-voice-commands"></a><span data-ttu-id="23419-111">Yerleşik sesli komutlar</span><span class="sxs-lookup"><span data-stu-id="23419-111">Built-in voice commands</span></span>

<span data-ttu-id="23419-112">Bu temel komutlarla HoloLens 'in etrafında daha hızlı yararlanın.</span><span class="sxs-lookup"><span data-stu-id="23419-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="23419-113">Bunları kullanabilmeniz için, cihazın ilk çalıştırma sırasında veya **Ayarlar**  >  **Gizlilik**  >  **konuşma**' da konuşmayı etkinleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="23419-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="23419-114">Başlangıç menüsünün en üstündeki duruma bakarak, konuşma özelliğinin etkinleştirilip etkinleştirilmeyeceğini her zaman denetleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="23419-115">En iyi konuşma tanıma sonuçları için, HoloLens 2 Microsoft bulut tabanlı Hizmetleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="23419-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="23419-116">Ancak, bu özelliği devre dışı bırakmak için ayarları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="23419-117">Bunu yapmak için ayarlar ' da **Çevrimiçi konuşma tanımayı** devre dışı bırakın.</span><span class="sxs-lookup"><span data-stu-id="23419-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="23419-118">Bu ayarı değiştirdikten sonra, HoloLens 2, yalnızca komutları ve dikte etmeyi tanımak için ses verilerini yerel olarak işler ve Cortana kullanılamayacak.</span><span class="sxs-lookup"><span data-stu-id="23419-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <a name="general-speech-commands"></a><span data-ttu-id="23419-119">Genel konuşma komutları</span><span class="sxs-lookup"><span data-stu-id="23419-119">General speech commands</span></span>

<span data-ttu-id="23419-120">Daha hızlı bir şekilde yararlanmak için Windows Mixed Reality genelinde bu komutları kullanın.</span><span class="sxs-lookup"><span data-stu-id="23419-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="23419-121">Bazı komutlar "Select" diyerek elde ettiğiniz Gaze imlecini kullanır.</span><span class="sxs-lookup"><span data-stu-id="23419-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="23419-122">HoloLens (1. gen) üzerinde el ışınları desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="23419-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="23419-123">Bunu söyleyin</span><span class="sxs-lookup"><span data-stu-id="23419-123">Say this</span></span> | <span data-ttu-id="23419-124">Bunu yapmak için</span><span class="sxs-lookup"><span data-stu-id="23419-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="23419-125">Seçin</span><span class="sxs-lookup"><span data-stu-id="23419-125">"Select"</span></span> | <span data-ttu-id="23419-126">Gaze imlecini getirmek için "Seç" deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="23419-127">Ardından, imleci seçmek istediğiniz şey üzerine konumlandırmak için kafanızı açın ve "Seç" i yeniden söyleyin.</span><span class="sxs-lookup"><span data-stu-id="23419-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
| <span data-ttu-id="23419-128">"Başlangıç 'a git"</span><span class="sxs-lookup"><span data-stu-id="23419-128">"Go to Start"</span></span> |  <span data-ttu-id="23419-129">Başlangıç menüsünü açma</span><span class="sxs-lookup"><span data-stu-id="23419-129">Open the Start menu</span></span> |
| <span data-ttu-id="23419-130">~Eksik</span><span class="sxs-lookup"><span data-stu-id="23419-130">"Close"</span></span>  | <span data-ttu-id="23419-131">Başlat menüsünü kapat</span><span class="sxs-lookup"><span data-stu-id="23419-131">Close the Start menu</span></span> |
| <span data-ttu-id="23419-132">Hızlı Eylemler menüsünü açmak için "Başlat 'a git" deyin ve "Karma Gerçeklik ana" deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-132">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span>  | <span data-ttu-id="23419-133">Tam ekran uygulama bırakma</span><span class="sxs-lookup"><span data-stu-id="23419-133">Leave an immersive app</span></span> |
| <span data-ttu-id="23419-134">"El ışını gizle"/"el ışını göster"</span><span class="sxs-lookup"><span data-stu-id="23419-134">"Hide hand ray" / "Show hand ray"</span></span> | <span data-ttu-id="23419-135">Hand Ray 'ı gizleme ve gösterme</span><span class="sxs-lookup"><span data-stu-id="23419-135">Hide and show hand ray</span></span> |
| <span data-ttu-id="23419-136">"Ne söyleyebilirim?"</span><span class="sxs-lookup"><span data-stu-id="23419-136">"What can I say?"</span></span>  | <span data-ttu-id="23419-137">Bkz. kullanılabilir konuşma komutları</span><span class="sxs-lookup"><span data-stu-id="23419-137">See available speech commands</span></span> |

<span data-ttu-id="23419-138">HoloLens 2 sürümü 19041. x sürümünden başlayarak şu komutları da kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="23419-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="23419-139">Bunu söyleyin</span><span class="sxs-lookup"><span data-stu-id="23419-139">Say this</span></span> | <span data-ttu-id="23419-140">Bunu yapmak için</span><span class="sxs-lookup"><span data-stu-id="23419-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="23419-141">"Cihazı yeniden Başlat"</span><span class="sxs-lookup"><span data-stu-id="23419-141">"Restart device"</span></span> | <span data-ttu-id="23419-142">Cihazı yeniden başlatmak istediğinizi onaylamak için bir iletişim kutusu açın.</span><span class="sxs-lookup"><span data-stu-id="23419-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="23419-143">Yeniden başlatmak için "Evet" söyleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="23419-144">"Cihaz kapatılıyor"</span><span class="sxs-lookup"><span data-stu-id="23419-144">"Shutdown device"</span></span> | <span data-ttu-id="23419-145">Cihazı kapatmak istediğinizi onaylamak için bir iletişim kutusu açın.</span><span class="sxs-lookup"><span data-stu-id="23419-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="23419-146">Onaylamak için "Evet" diyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="23419-147">"Parlaklığı artırma/azaltma"</span><span class="sxs-lookup"><span data-stu-id="23419-147">"Brightness up/down"</span></span> | <span data-ttu-id="23419-148">Ekran parlaklığını %10 oranında artırın veya azaltın.</span><span class="sxs-lookup"><span data-stu-id="23419-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="23419-149">"Birim yukarı/aşağı"</span><span class="sxs-lookup"><span data-stu-id="23419-149">"Volume up/down"</span></span> | <span data-ttu-id="23419-150">%10 oranında birimi artırın veya azaltın.</span><span class="sxs-lookup"><span data-stu-id="23419-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="23419-151">"IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="23419-151">"What's my IP address"</span></span> | <span data-ttu-id="23419-152">Cihazınızın yerel ağda geçerli IP adresini görüntüleyen bir iletişim kutusu alın.</span><span class="sxs-lookup"><span data-stu-id="23419-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="23419-153">"Resim al"</span><span class="sxs-lookup"><span data-stu-id="23419-153">"Take a picture"</span></span> | <span data-ttu-id="23419-154">Şu anda gördüğünüzü karma gerçeklik fotoğrafını yakalayın.</span><span class="sxs-lookup"><span data-stu-id="23419-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="23419-155">"Video al"</span><span class="sxs-lookup"><span data-stu-id="23419-155">"Take a video"</span></span> | <span data-ttu-id="23419-156">Karma Gerçeklik videosunu kaydetmeye başlayın.</span><span class="sxs-lookup"><span data-stu-id="23419-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="23419-157">"Kaydı Durdur"</span><span class="sxs-lookup"><span data-stu-id="23419-157">"Stop recording"</span></span> | <span data-ttu-id="23419-158">Devam eden bir varsa geçerli karma gerçeklik video kaydını sonlandırır.</span><span class="sxs-lookup"><span data-stu-id="23419-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <a name="hologram-commands"></a><span data-ttu-id="23419-159">Hologram komutları</span><span class="sxs-lookup"><span data-stu-id="23419-159">Hologram commands</span></span>

<span data-ttu-id="23419-160">Bu komutları kullanmak için 3B nesne, hologram veya uygulama penceresinde Gaze.</span><span class="sxs-lookup"><span data-stu-id="23419-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="23419-161">Bunu söyleyin</span><span class="sxs-lookup"><span data-stu-id="23419-161">Say this</span></span> | <span data-ttu-id="23419-162">Bunu yapmak için</span><span class="sxs-lookup"><span data-stu-id="23419-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="23419-163">Karakterli</span><span class="sxs-lookup"><span data-stu-id="23419-163">"Bigger"</span></span> | <span data-ttu-id="23419-164">Daha büyük hale getirin</span><span class="sxs-lookup"><span data-stu-id="23419-164">Make it bigger</span></span> |
| <span data-ttu-id="23419-165">Artı</span><span class="sxs-lookup"><span data-stu-id="23419-165">"Smaller"</span></span> | <span data-ttu-id="23419-166">Daha küçük hale getirin</span><span class="sxs-lookup"><span data-stu-id="23419-166">Make it smaller</span></span> |
| <span data-ttu-id="23419-167">"Yüz bana"</span><span class="sxs-lookup"><span data-stu-id="23419-167">"Face me"</span></span> | <span data-ttu-id="23419-168">Bunu sizin için etkinleştirin</span><span class="sxs-lookup"><span data-stu-id="23419-168">Turn it to face you</span></span> |
| <span data-ttu-id="23419-169">"Bunu taşı"</span><span class="sxs-lookup"><span data-stu-id="23419-169">"Move this"</span></span> | <span data-ttu-id="23419-170">Taşıyın (Gaze 'ı izleyin)</span><span class="sxs-lookup"><span data-stu-id="23419-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="23419-171">~Eksik</span><span class="sxs-lookup"><span data-stu-id="23419-171">"Close"</span></span> | <span data-ttu-id="23419-172">Kapat</span><span class="sxs-lookup"><span data-stu-id="23419-172">Close it</span></span> |
| <span data-ttu-id="23419-173">"Takip et"/"İzlemeyi Durdur"</span><span class="sxs-lookup"><span data-stu-id="23419-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="23419-174">Siz hareket ettiğiniz sırada takip edin</span><span class="sxs-lookup"><span data-stu-id="23419-174">Make it follow you as you move around</span></span> |

### <a name="see-it-say-it"></a><span data-ttu-id="23419-175">Görüntüleyin, söyleyin</span><span class="sxs-lookup"><span data-stu-id="23419-175">See it, say it</span></span>

<span data-ttu-id="23419-176">HoloLens 'teki pek çok düğme ve diğer öğe da sesinize yanıt verir — örneğin, uygulama çubuğunda **beni takip et** ve **Kapat** ' ı veya kenar düğmesini uç düğmesine **geri** götür.</span><span class="sxs-lookup"><span data-stu-id="23419-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="23419-177">Bir düğmenin ses özellikli olup olmadığını öğrenmek için, biraz bekleyin **imlecinizi**, **dokunmatik imlecinizi** veya bir arada bir tek bir **ışını** geri çevirin.</span><span class="sxs-lookup"><span data-stu-id="23419-177">To find out if a button is voice-enabled, rest your **gaze cursor**, **touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="23419-178">Düğme ses etkinse, bir ses ipucu görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="23419-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <a name="dictation-mode"></a><span data-ttu-id="23419-179">Dikte etme modu</span><span class="sxs-lookup"><span data-stu-id="23419-179">Dictation mode</span></span>

<span data-ttu-id="23419-180">Ne kadar yordunuz?</span><span class="sxs-lookup"><span data-stu-id="23419-180">Tired of typing?</span></span> <span data-ttu-id="23419-181">Holographic klavyesi etkin olduğunda dikte moduna geçin.</span><span class="sxs-lookup"><span data-stu-id="23419-181">Switch to dictation mode anytime that the holographic keyboard is active.</span></span> <span data-ttu-id="23419-182">Başlamak için mikrofon düğmesini seçin veya "dikte başlatma" deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="23419-183">Dikte etmek için düğmeyi yeniden seçin veya "dikte etme Durdur" deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="23419-184">Az önce dikte ettiğiniz şeyi silmek için, "Delete The" deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="23419-185">Dikte modunu kullanmak için bir internet bağlantınızın olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="23419-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="23419-186">HoloLens dikte açık noktalama kullanır, yani kullanmak istediğiniz noktalama işaretlerinin adını söylemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="23419-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="23419-187">Örneğin, "her ne kadar **soru işaretine** **kadar selam"** diyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="23419-188">Kullanabileceğiniz noktalama anahtar sözcükleri burada bulabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="23419-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="23419-189">Nokta, virgül, soru işareti, ünlem işareti/ünlem işareti</span><span class="sxs-lookup"><span data-stu-id="23419-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="23419-190">Yeni satır/yeni paragraf</span><span class="sxs-lookup"><span data-stu-id="23419-190">New line/new paragraph</span></span>
- <span data-ttu-id="23419-191">Noktalı virgül, iki nokta</span><span class="sxs-lookup"><span data-stu-id="23419-191">Semicolon, colon</span></span>
- <span data-ttu-id="23419-192">Tırnak (lar) aç, tırnak kapatma</span><span class="sxs-lookup"><span data-stu-id="23419-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="23419-193">Diyez etiketi, gülen adam/gülen yüz, çili</span><span class="sxs-lookup"><span data-stu-id="23419-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="23419-194">Dolar, yüzde</span><span class="sxs-lookup"><span data-stu-id="23419-194">Dollar, percent</span></span>

<span data-ttu-id="23419-195">Bazen e-posta adresleri gibi şeyler için yazım denetimi yapmak faydalı olabilir.</span><span class="sxs-lookup"><span data-stu-id="23419-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="23419-196">Örneğin, dikte etmek için example@outlook.com "Outlook nokta com ' da" e X a m P L e "deyin.</span><span class="sxs-lookup"><span data-stu-id="23419-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <a name="do-more-with-cortana"></a><span data-ttu-id="23419-197">Cortana ile daha fazlasını yapın</span><span class="sxs-lookup"><span data-stu-id="23419-197">Do more with Cortana</span></span>

<span data-ttu-id="23419-198">Cortana, HoloLens 'te her türlü şeyi yapmanıza yardımcı olabilir, ancak kullandığınız Windows holographic sürümüne bağlı olarak yetenekler farklı olabilir.</span><span class="sxs-lookup"><span data-stu-id="23419-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capabilities may be different.</span></span> <span data-ttu-id="23419-199">En son Cortana sürümünün güncelleştirilmiş özellikleri hakkında daha fazla bilgi edinebilirsiniz: [yakında çıkacak Windows 10 sürümünde Cortana: Gelişmiş güvenlik ve gizlilik sayesinde üretkenliğinizi odaklanın](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span><span class="sxs-lookup"><span data-stu-id="23419-199">You can learn more about the updated capabilities of the latest version of Cortana here: [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![Hey Cortana!](images/cortana-on-hololens.png)

<span data-ttu-id="23419-201">Burada bazı şeyler söylemeyi denemeyi diyoruz (önce "Hey Cortana" dey).</span><span class="sxs-lookup"><span data-stu-id="23419-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="23419-202">**Cortana...**</span><span class="sxs-lookup"><span data-stu-id="23419-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="23419-203">What can I say? (Ne söyleyebilirim?)</span><span class="sxs-lookup"><span data-stu-id="23419-203">What can I say?</span></span>
- <span data-ttu-id="23419-204">Uygulama <*adını>.*</span><span class="sxs-lookup"><span data-stu-id="23419-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="23419-205">Saat kaç?</span><span class="sxs-lookup"><span data-stu-id="23419-205">What time is it?</span></span>
- <span data-ttu-id="23419-206">Bana en son NBA puanlarını göster.</span><span class="sxs-lookup"><span data-stu-id="23419-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="23419-207">Bana bir fıkra anlat.</span><span class="sxs-lookup"><span data-stu-id="23419-207">Tell me a joke.</span></span>

<span data-ttu-id="23419-208">*18362.x veya* önceki bir sürümü kullanıyorsanız şu komutları da kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="23419-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="23419-209">**Cortana...**</span><span class="sxs-lookup"><span data-stu-id="23419-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="23419-210">Birimi artırma.</span><span class="sxs-lookup"><span data-stu-id="23419-210">Increase the volume.</span></span>
- <span data-ttu-id="23419-211">Parlaklığı azaltın.</span><span class="sxs-lookup"><span data-stu-id="23419-211">Decrease the brightness.</span></span>
- <span data-ttu-id="23419-212">Kapat'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="23419-212">Shut down.</span></span>
- <span data-ttu-id="23419-213">Yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="23419-213">Restart.</span></span>
- <span data-ttu-id="23419-214">Uyu.</span><span class="sxs-lookup"><span data-stu-id="23419-214">Go to sleep.</span></span>
- <span data-ttu-id="23419-215">Sessiz.</span><span class="sxs-lookup"><span data-stu-id="23419-215">Mute.</span></span>
- <span data-ttu-id="23419-216">Uygulama <*adını* buraya> (uygulamanın taşınmak istediğiniz noktaya bakabilirsiniz).</span><span class="sxs-lookup"><span data-stu-id="23419-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="23419-217">Başlat'a gidin.</span><span class="sxs-lookup"><span data-stu-id="23419-217">Go to Start.</span></span>
- <span data-ttu-id="23419-218">Bir resim çek.</span><span class="sxs-lookup"><span data-stu-id="23419-218">Take a picture.</span></span>
- <span data-ttu-id="23419-219">Kaydı başlatma.</span><span class="sxs-lookup"><span data-stu-id="23419-219">Start recording.</span></span> <span data-ttu-id="23419-220">(Video kaydetmeye başlar.)</span><span class="sxs-lookup"><span data-stu-id="23419-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="23419-221">Kaydı durdurun.</span><span class="sxs-lookup"><span data-stu-id="23419-221">Stop recording.</span></span> <span data-ttu-id="23419-222">(Video kaydetmeyi durdurur.)</span><span class="sxs-lookup"><span data-stu-id="23419-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="23419-223">Ne kadar pil kaldı?</span><span class="sxs-lookup"><span data-stu-id="23419-223">How much battery do I have left?</span></span>

<span data-ttu-id="23419-224">Bilgisayarınızda veya telefonda Windows'dan kullandığınız bazı Cortana özellikleri (örneğin, anımsatıcılar ve bildirimler) Microsoft HoloLens'de desteklenmiyor ve Cortana deneyimi bir bölgeden diğerine farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="23419-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <a name="turn-cortana-off"></a><span data-ttu-id="23419-225">Cortana'yı kapatma</span><span class="sxs-lookup"><span data-stu-id="23419-225">Turn Cortana off</span></span>

<span data-ttu-id="23419-226">Cortana, HoloLens'i ilk kez konuşma etkinleştiriyorsanız kullanır.</span><span class="sxs-lookup"><span data-stu-id="23419-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="23419-227">Cortana'nın ayarlarından onu kapatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="23419-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="23419-228">Yeni **Tüm uygulamalar** Cortana Ayarları'yı   >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="23419-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="23419-229">Cortana'yı kapatmak size öneriler, fikirler, anımsatıcılar, uyarılar ve daha fazlasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="23419-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="23419-230">Cortana "Hey Cortana" yanıt vermiyorsa Başlat'ta konuşmanın etkinleştirildiğinden emin olun, Cortana'nın ayarlarına gidin ve etkin olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="23419-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
