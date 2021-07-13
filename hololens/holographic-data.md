---
title: Dosyalarda dosyaları bulma ve HoloLens
description: Karma gerçeklik Dosya Gezgini dosyaları HoloLens, görüntülemek ve yönetmek için HoloLens'i nasıl kullanabileceğinizi öğrenin.
keywords: nasıl kullanılır, dosya seçici, dosyalar, fotoğraflar, videolar, resimler, OneDrive, depolama, dosya gezgini, hololens
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636189"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="80555-104">Dosyalarda dosyaları bulma, açma ve HoloLens</span><span class="sxs-lookup"><span data-stu-id="80555-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="80555-105">Fotoğraflar ve videolar HoloLens dosyalar, doğrudan HoloLens cihazınıza kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="80555-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="80555-106">Bunları, aşağıdakiler üzerinde dosyaları yönetirken olduğu gibi görüntü Windows 10:</span><span class="sxs-lookup"><span data-stu-id="80555-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="80555-107">Yerel klasörlere Dosya Gezgini için Dosya Gezgini uygulamasını kullanma.</span><span class="sxs-lookup"><span data-stu-id="80555-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="80555-108">Bir uygulamanın depolama alanı içinde.</span><span class="sxs-lookup"><span data-stu-id="80555-108">Within an app's storage.</span></span>
- <span data-ttu-id="80555-109">Özel bir klasörde (video veya müzik kitaplığı gibi).</span><span class="sxs-lookup"><span data-stu-id="80555-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="80555-110">Uygulama ve dosya seçici içeren bir depolama hizmeti kullanma (örneğin, OneDrive).</span><span class="sxs-lookup"><span data-stu-id="80555-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="80555-111">MTP (Medya Aktarım Protokolü) HoloLens usb kablosu kullanarak bilgisayarınıza bağlı bir masaüstü bilgisayar kullanma.</span><span class="sxs-lookup"><span data-stu-id="80555-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="80555-112">Dosyaları HoloLens kullanarak Dosya Gezgini</span><span class="sxs-lookup"><span data-stu-id="80555-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="80555-113">HoloLens HoloLens Nisan [2018 Güncelleştirmesi (RS4) HoloLens (1. nesil) Windows 10 2.](/windows/mixed-reality/release-notes-april-2018)nesil tüm cihazlar ve HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="80555-114">3 Dosya Gezgini, HoloLens ve resimler dahil olmak üzere cihazınızın dosyalarını görüntülemek ve yönetmek için Dosya Gezgini'de dosyaları kullanın.</span><span class="sxs-lookup"><span data-stu-id="80555-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="80555-115">Başlamak **için Başlangıç**   >  **Tüm uygulamalar**   >  **Dosya Gezgini'a** gidin.</span><span class="sxs-lookup"><span data-stu-id="80555-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="80555-116">Listede dosya yoksa Dosya Gezgini sol üst **bölmede Bu** Cihaz'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="80555-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="80555-117">Dosyalarda hiç dosya görmüyorsanız Dosya Gezgini filtre etkin olabilir (sol bölmede saat simgesi vurgulanmış).</span><span class="sxs-lookup"><span data-stu-id="80555-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="80555-118">Bunu düzeltmek için sol **bölmede (saat** simgesinin altında) Bu Cihaz belge simgesini seçin veya menüyü açıp Bu **Cihaz'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="80555-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="80555-119">Fotoğraf ve videolarınızı bulma ve görüntüleme</span><span class="sxs-lookup"><span data-stu-id="80555-119">Find and view your photos and videos</span></span>

<span data-ttu-id="80555-120">[Karma gerçeklik yakalama](holographic-photos-and-videos.md) özelliği, karma gerçeklik fotoğraf ve videolarını HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="80555-121">Bu fotoğraflar ve videolar cihazın Kamera Rulosu klasörüne kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="80555-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="80555-122">Fotoğraflara ve videolara şu şekilde HoloLens erişebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="80555-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="80555-123">Doğrudan Fotoğraflar uygulaması aracılığıyla Kamera [Roll'e erişin.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="80555-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="80555-124">fotoğraf ve videolarınızı bulut depolama alanına yüklemek için fotoğraf ve videolarınızı OneDrive.</span><span class="sxs-lookup"><span data-stu-id="80555-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="80555-125">Karma Gerçeklik Yakalama sayfasının [Windows Cihaz Portalı.](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)</span><span class="sxs-lookup"><span data-stu-id="80555-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="80555-126">Fotoğraflar uygulaması</span><span class="sxs-lookup"><span data-stu-id="80555-126">Photos app</span></span>

<span data-ttu-id="80555-127">Fotoğraflar uygulaması, Başlat menüsündeki varsayılan **uygulamalardan biridir** ve yeni uygulamalarla birlikte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="80555-128">İçeriği görüntülemek için [Fotoğraflar uygulamasını kullanma hakkında daha fazla bilgi edinebilirsiniz.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="80555-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="80555-129">Fotoğrafları diğer cihazlarla [OneDrive için](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store uygulamasından da yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80555-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="80555-130">OneDrive uygulama</span><span class="sxs-lookup"><span data-stu-id="80555-130">OneDrive app</span></span>

<span data-ttu-id="80555-131">[OneDrive](https://onedrive.live.com/) fotoğraflarınıza ve videolarınızı herhangi bir cihazla ve herhangi bir kullanıcıyla paylaşmanıza, yönetmenize ve paylaşmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="80555-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="80555-132">Bu uygulamada yakalanan fotoğraflara ve videolara erişmek HoloLens, [OneDrive uygulamanıza](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) Microsoft Store'den HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="80555-133">İndirildikten sonra, OneDrive'yi açın ve **Kamera**  >  **Ayarlar'ı seçin** ve Kamera karşıya **yükleme'yi açın.**</span><span class="sxs-lookup"><span data-stu-id="80555-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="80555-134">Bağlan bilgisayara yükleme</span><span class="sxs-lookup"><span data-stu-id="80555-134">Connect to a PC</span></span>

<span data-ttu-id="80555-135">HoloLens nisan [2018](/windows/mixed-reality/release-notes-april-2018) veya sonraki bir Windows 10 güncelleştirmesi çalıştıracaksa, MTP (medya aktarım protokolü) kullanarak cihazdaki fotoğraflara ve videolara göz atmak için USB kablosu kullanarak HoloLens'nizi bir Windows 10 bilgisayarına bağlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80555-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="80555-136">Cihazda bir PIN veya parola ayarlanmışsa dosyalara göz atmak için cihazın kilidinin açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="80555-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="80555-137">Windows Cihaz Portalı'ı etkinleştirdiyseniz, cihazınıza depolanmış fotoğraflara ve videolara göz atmak, almak ve yönetmek için kullanabilirsiniz. [](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="80555-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="80555-138">Uygulama içindeki dosyalara erişme</span><span class="sxs-lookup"><span data-stu-id="80555-138">Access files within an app</span></span>

<span data-ttu-id="80555-139">Bir uygulama, dosyaları cihazınıza kaydederse, bu uygulamayı kullanarak cihazınıza erişebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80555-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="80555-140">Başka bir uygulamadan dosya isteği</span><span class="sxs-lookup"><span data-stu-id="80555-140">Requesting files from another app</span></span>

<span data-ttu-id="80555-141">Bir uygulama, dosya seçicilerini kullanarak bir dosyayı kaydetmeyi veya başka bir uygulamanın [dosyasını açmayı talep ediyor olabilir.](/windows/mixed-reality/app-model#file-pickers)</span><span class="sxs-lookup"><span data-stu-id="80555-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="80555-142">Bilinen klasörler</span><span class="sxs-lookup"><span data-stu-id="80555-142">Known folders</span></span>

<span data-ttu-id="80555-143">HoloLens, uygulamaların erişim [izni talep](/windows/mixed-reality/app-model#known-folders) etmek için sahip olduğu bir dizi bilinen klasörü destekler.</span><span class="sxs-lookup"><span data-stu-id="80555-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="80555-144">Bilgisayarınız HoloLens dosyaları görüntüleme</span><span class="sxs-lookup"><span data-stu-id="80555-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="80555-145">Diğer mobil cihazlara benzer şekilde, HoloLens MTP (Medya Aktarım Protokolü) kullanarak masaüstü bilgisayarınıza bağlayın ve kolay aktarım için Dosya Gezgini kitaplıklarına erişmek için HoloLens'i açın.</span><span class="sxs-lookup"><span data-stu-id="80555-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="80555-146">Bilgisayarınızda HoloLens dosyalarınızı Dosya Gezgini görmek için:</span><span class="sxs-lookup"><span data-stu-id="80555-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="80555-147">Oturum HoloLens, ardından bilgisayarla birlikte gelen USB kablosunu kullanarak bilgisayara HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="80555-148">ile **dosyaları görüntülemek için Cihazı Aç'ı Dosya Gezgini** veya Dosya Gezgini açın ve cihaza gidin.</span><span class="sxs-lookup"><span data-stu-id="80555-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="80555-149">Bilgisayarınızla ilgili bilgileri görmek HoloLens, bilgisayarınızda bulunan Dosya Gezgini cihaz adına sağ tıklayın ve Ardından Özellikler'i **seçin.**</span><span class="sxs-lookup"><span data-stu-id="80555-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="80555-150">HoloLens (1. nesil) dış sabit sürücülere veya SD kartlara bağlanmayı desteklemez.</span><span class="sxs-lookup"><span data-stu-id="80555-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="80555-151">Buluta eşitleme</span><span class="sxs-lookup"><span data-stu-id="80555-151">Sync to the cloud</span></span>

<span data-ttu-id="80555-152">Fotoğrafları ve diğer dosyaları HoloLens buluta eşitlemek için, OneDrive'yi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="80555-153">Daha OneDrive için, bu sayfayı Microsoft Store arama HoloLens.</span><span class="sxs-lookup"><span data-stu-id="80555-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="80555-154">HoloLens uygulama dosyalarını ve verilerini yüklemez, bu nedenle önemli şeylerinizi veri kaynağınıza kaydetmek OneDrive.</span><span class="sxs-lookup"><span data-stu-id="80555-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="80555-155">Bu şekilde, cihazınızı sıfırlar veya bir uygulamayı kaldırırsanız, bilgileriniz de geri döner.</span><span class="sxs-lookup"><span data-stu-id="80555-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
