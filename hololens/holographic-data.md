---
title: HoloLens 'te dosyaları bulma ve kaydetme
description: Karma Gerçeklik cihazındaki dosyaları açmak, görüntülemek ve yönetmek için HoloLens 'te dosya Gezgini 'ni nasıl kullanacağınızı öğrenin.
keywords: Nasıl yapılır, dosya seçici, dosyalar, fotoğraflar, videolar, resimler, OneDrive, depolama, dosya Gezgini, Hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378974"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="6f6f1-104">HoloLens 'te dosyaları bulun, açın ve kaydedin</span><span class="sxs-lookup"><span data-stu-id="6f6f1-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="6f6f1-105">HoloLens 'te fotoğraflar ve videolar dahil oluşturduğunuz dosyalar doğrudan HoloLens cihazınıza kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="6f6f1-106">Windows 10 ' da dosyaları yönettiğiniz şekilde görüntüleyin ve yönetin:</span><span class="sxs-lookup"><span data-stu-id="6f6f1-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="6f6f1-107">Yerel klasörlere erişmek için dosya Gezgini uygulamasını kullanma.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="6f6f1-108">Bir uygulamanın depolama alanında.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-108">Within an app's storage.</span></span>
- <span data-ttu-id="6f6f1-109">Özel bir klasörde (örneğin, video veya müzik kitaplığı).</span><span class="sxs-lookup"><span data-stu-id="6f6f1-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="6f6f1-110">Uygulama ve dosya seçici (OneDrive gibi) içeren bir depolama hizmeti kullanma.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="6f6f1-111">MTP (Medya Aktarım Protokolü) desteğini kullanarak bir USB kablosu kullanarak HoloLens 'nizle bağlantılı masaüstü bılgısayar kullanma.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="6f6f1-112">Dosya Gezgini 'ni kullanarak HoloLens 'te dosyaları görüntüleme</span><span class="sxs-lookup"><span data-stu-id="6f6f1-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="6f6f1-113">[HoloLens Için Windows 10 nisan 2018 Güncelleştirmesi (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)Itibariyle tüm HoloLens 2 cihazlara ve HoloLens (1. gen) için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="6f6f1-114">3D nesneler, belgeler ve resimler dahil olmak üzere cihazınızdaki dosyaları görüntülemek ve yönetmek için HoloLens üzerinde dosya Gezgini 'ni kullanın.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="6f6f1-115">Başlamak için    >  **tüm uygulamalar**   >  **Dosya Gezgini** ' ni Başlat ' a gidin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="6f6f1-116">Dosya Gezgini 'nde listelenen dosya yoksa, sol üst bölmedeki **Bu cihazı** seçin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="6f6f1-117">Dosya Gezgini 'nde herhangi bir dosya görmüyorsanız, "son" filtre etkin olabilir (saat simgesi sol bölmede vurgulanır).</span><span class="sxs-lookup"><span data-stu-id="6f6f1-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="6f6f1-118">Bu hatayı onarmak için sol bölmedeki (saat simgesinin altında) **Bu cihaz** belgesi simgesini seçin veya menüyü açın ve **Bu cihazı** seçin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="6f6f1-119">Fotoğraflarınızı ve videolarınızı bulun ve görüntüleyin</span><span class="sxs-lookup"><span data-stu-id="6f6f1-119">Find and view your photos and videos</span></span>

<span data-ttu-id="6f6f1-120">[Karma gerçeklik yakalama](holographic-photos-and-videos.md) , Hololens 'te karışık gerçeklik fotoğraflarını ve videoları almanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="6f6f1-121">Bu fotoğraflar ve videolar cihazın kamera rulosu klasörüne kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="6f6f1-122">HoloLens ile çekilen fotoğraflara ve videolara erişebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="6f6f1-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="6f6f1-123">doğrudan [Fotoğraflar uygulaması](holographic-photos-and-videos.md)aracılığıyla kamera rulonuza erişme.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="6f6f1-124">Fotoğraflarınızı ve videolarınızı OneDrive 'a eşitleyerek, fotoğraf ve videoları bulut depolamaya yükleme.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="6f6f1-125">[Windows cihaz portalının](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)karma gerçeklik yakalama sayfasını kullanma.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="6f6f1-126">Fotoğraflar uygulaması</span><span class="sxs-lookup"><span data-stu-id="6f6f1-126">Photos app</span></span>

<span data-ttu-id="6f6f1-127">Fotoğraflar uygulaması, **Başlangıç** menüsündeki varsayılan uygulamalardan biridir ve HoloLens ile yerleşik olarak sunulur.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="6f6f1-128">[İçeriği görüntülemek Için Fotoğraflar uygulamasını kullanma](holographic-photos-and-videos.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="6f6f1-129">Ayrıca, fotoğrafları diğer cihazlara eşitlemek için Microsoft Store [OneDrive uygulamasını](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="6f6f1-130">OneDrive uygulaması</span><span class="sxs-lookup"><span data-stu-id="6f6f1-130">OneDrive app</span></span>

<span data-ttu-id="6f6f1-131">[OneDrive](https://onedrive.live.com/) , fotoğraf ve videolarınızı dilediğiniz cihazla ve herhangi bir kullanıcıyla erişmenizi, yönetmenizi ve paylaşmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="6f6f1-132">HoloLens 'te yakalanan fotoğraflara ve videolara erişmek için, HoloLens 'teki Microsoft Store [OneDrive uygulamasını](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) indirin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="6f6f1-133">İndirildikten sonra OneDrive uygulamasını açın ve **Ayarlar**  >  **Kamera karşıya yükle**' yi seçin ve **Kamera karşıya yüklemeyi** açın.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="6f6f1-134">BILGISAYARA Bağlan</span><span class="sxs-lookup"><span data-stu-id="6f6f1-134">Connect to a PC</span></span>

<span data-ttu-id="6f6f1-135">HoloLens 'niz [Windows 10 nisan 2018 güncelleştirmesini](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) veya sonrasını ÇALıŞTıRıYORSA, MTP 'yi (Medya Aktarım Protokolü) kullanarak cihazdaki fotoğraflara ve videolara taramak IÇIN bir USB kablosu kullanarak HoloLens 'Nizi bir WINDOWS 10 bilgisayarına bağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="6f6f1-136">Cihazınızda bir PIN veya parola ayarladıysanız, dosyalara gözatabilmeniz için cihazın kilidinin açık olduğundan emin olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="6f6f1-137">[Windows cihaz portalını](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)etkinleştirdiyseniz, cihazınızda depolanan fotoğrafları ve videoları taramak, almak ve yönetmek için bu uygulamayı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="6f6f1-138">Bir uygulama içindeki dosyalara erişme</span><span class="sxs-lookup"><span data-stu-id="6f6f1-138">Access files within an app</span></span>

<span data-ttu-id="6f6f1-139">Bir uygulama aygıtınızdaki dosyaları kaydederse, bunlara erişmek için bu uygulamayı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="6f6f1-140">Başka bir uygulamadan dosya isteme</span><span class="sxs-lookup"><span data-stu-id="6f6f1-140">Requesting files from another app</span></span>

<span data-ttu-id="6f6f1-141">Bir uygulama, dosya [etiketlerini](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)kullanarak bir dosyayı kaydetmek veya başka bir uygulamadan dosya açmak isteyebilir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="6f6f1-142">Bilinen klasörler</span><span class="sxs-lookup"><span data-stu-id="6f6f1-142">Known folders</span></span>

<span data-ttu-id="6f6f1-143">HoloLens, uygulamaların erişim için izin isteyebildiği bir dizi [bilinen klasörü](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) destekler.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="6f6f1-144">Bilgisayarınızda HoloLens dosyalarını görüntüleyin</span><span class="sxs-lookup"><span data-stu-id="6f6f1-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="6f6f1-145">Diğer mobil cihazlara benzer şekilde, MTP 'yi (Medya Aktarım Protokolü) kullanarak masaüstü PC 'nize bağlayın ve kolay Aktarım için HoloLens kitaplıklarınıza erişmek üzere bılgısayarda dosya Gezgini 'ni açın.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="6f6f1-146">Bilgisayarınızda dosya Gezgini 'nde HoloLens dosyalarınızı görmek için:</span><span class="sxs-lookup"><span data-stu-id="6f6f1-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="6f6f1-147">HoloLens 'te oturum açın, ardından HoloLens ile gelen USB kablosunu kullanarak BILGISAYARA takın.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="6f6f1-148">**Dosya Gezgini ile dosyaları görüntülemek Için cihazı aç**' ı SEÇIN veya bilgisayarda dosya Gezgini 'ni açın ve cihaza gidin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="6f6f1-149">HoloLens bilgileriniz hakkındaki bilgileri görmek için, bilgisayarınızda dosya Gezgini ' nde cihaz adına sağ tıklayın ve ardından **Özellikler**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="6f6f1-150">HoloLens (1. gen), dış sabit sürücülere veya SD kartlarına bağlanmayı desteklemez.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="6f6f1-151">Buluta Eşitle</span><span class="sxs-lookup"><span data-stu-id="6f6f1-151">Sync to the cloud</span></span>

<span data-ttu-id="6f6f1-152">HoloLens 'teki fotoğrafları ve diğer dosyaları buluta eşitlemek için, OneDrive 'ı yükleyin ve HoloLens 'te kurun.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="6f6f1-153">OneDrive 'ı almak için, HoloLens 'teki Microsoft Store arayın.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="6f6f1-154">HoloLens uygulama dosyalarını ve verileri yedeketmez, bu nedenle önemli öğelerinizi OneDrive 'a kaydetmeniz iyi bir fikirdir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="6f6f1-155">Bu şekilde, cihazınızı sıfırlayabilir veya bir uygulamayı kaldırırsanız, bilgileriniz yedeklenir.</span><span class="sxs-lookup"><span data-stu-id="6f6f1-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
