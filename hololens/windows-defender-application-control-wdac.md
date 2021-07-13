---
title: Windows Defender Uygulama Denetimi - WDAC
description: Uygulama Denetimi Windows Defender nin ne olduğu ve karma gerçeklik cihazlarını yönetmek için HoloLens genel bakış.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639939"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="bfd37-103">Windows Defender Uygulama Denetimi - WDAC</span><span class="sxs-lookup"><span data-stu-id="bfd37-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="bfd37-104">WDAC, bir IT Yöneticisinin cihazlarda uygulama başlatmayı engellemek için cihazlarını yapılandırmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="bfd37-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="bfd37-105">Bu, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır; burada kullanıcıya cihazda uygulamaları gizleyen ancak hala başlatılana bir kullanıcı arabirimi sunulmaktadır.</span><span class="sxs-lookup"><span data-stu-id="bfd37-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="bfd37-106">WDAC uygulanırken, uygulamalar Hala Tüm Uygulamalar listesinde görünür durumdadır, ancak WDAC bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılamalarını durdurur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="bfd37-107">Bir cihaza birden fazla WDAC ilkesi atanabilir.</span><span class="sxs-lookup"><span data-stu-id="bfd37-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="bfd37-108">Bir sistemde birden çok WDAC ilkeleri ayarlanırsa, en kısıtlayıcı ilkeler etkili olur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="bfd37-109">Son kullanıcılar WDAC tarafından engellenen bir uygulamayı başlatmaya HoloLens uygulamanın başlatılamayacakları konusunda bir bildirim almaz.</span><span class="sxs-lookup"><span data-stu-id="bfd37-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="bfd37-110">Aşağıda, kullanıcıların wdac ve Windows PowerShell kullanarak 2 cihaz üzerinde uygulamalara izin verme veya uygulamaları engelleme hakkında bilgi HoloLens bir [kılavuz Microsoft Intune.](/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="bfd37-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="bfd37-111">Kullanıcılar, ilk örnek adımı kullanarak Windows 10 uygulamaları araysa da sonuçları daraltmak için birkaç deneme yapmaları gerekir.</span><span class="sxs-lookup"><span data-stu-id="bfd37-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="bfd37-112">Paketin tam adını bilmiyorsanız, paketi bulmak için birkaç kez 'Get-AppxPackage -name \* YourGueGuess \* ' çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="bfd37-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="bfd37-113">Ardından adı '$package 1 = Get-AppxPackage -name Actual.PackageName' çalıştırın</span><span class="sxs-lookup"><span data-stu-id="bfd37-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="bfd37-114">Örneğin, aşağıdakini Microsoft Edge birden fazla sonuç dönecektir, ancak bu listeden ihtiyacınız olan tam adın Microsoft.MicrosoftEdge olduğunu tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bfd37-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="bfd37-115">HoloLens'da uygulamalar için Paket HoloLens</span><span class="sxs-lookup"><span data-stu-id="bfd37-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="bfd37-116">Yukarıda bağlantılı kılavuzda, uygulama adlarını el newPolicy.xml ve yalnızca paket aile adlarıyla HoloLens uygulamalar için kurallar ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bfd37-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="bfd37-117">Bazen, masaüstü bilgisayarınızda ilkeye eklemek istediğiniz uygulamaları kullanmak için kullanabileceğiniz uygulamalar olabilir.</span><span class="sxs-lookup"><span data-stu-id="bfd37-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="bfd37-118">2 cihaz için yaygın olarak kullanılan ve In-Box uygulamaları HoloLens listesi ve ardından.</span><span class="sxs-lookup"><span data-stu-id="bfd37-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="bfd37-119">Uygulama Adı</span><span class="sxs-lookup"><span data-stu-id="bfd37-119">App Name</span></span>                   | <span data-ttu-id="bfd37-120">Paket Ailesi Adı</span><span class="sxs-lookup"><span data-stu-id="bfd37-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="bfd37-121">3B Görüntüleyici</span><span class="sxs-lookup"><span data-stu-id="bfd37-121">3D Viewer</span></span>                  | <span data-ttu-id="bfd37-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="bfd37-123">Uygulama Yükleyicisi</span><span class="sxs-lookup"><span data-stu-id="bfd37-123">App Installer</span></span>              | <span data-ttu-id="bfd37-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bfd37-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="bfd37-125">Takvim</span><span class="sxs-lookup"><span data-stu-id="bfd37-125">Calendar</span></span>                   | <span data-ttu-id="bfd37-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="bfd37-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="bfd37-127">Camera</span></span>                     | <span data-ttu-id="bfd37-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bfd37-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="bfd37-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="bfd37-129">Cortana</span></span>                    | <span data-ttu-id="bfd37-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="bfd37-131">Dynamics 365 Kılavuzları</span><span class="sxs-lookup"><span data-stu-id="bfd37-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="bfd37-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="bfd37-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bfd37-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="bfd37-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="bfd37-135">Geri Bildirim Merkezi</span><span class="sxs-lookup"><span data-stu-id="bfd37-135">Feedback Hub</span></span>               | <span data-ttu-id="bfd37-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="bfd37-137">Dosya Gezgini</span><span class="sxs-lookup"><span data-stu-id="bfd37-137">File Explorer</span></span>              | <span data-ttu-id="bfd37-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bfd37-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="bfd37-139">Posta</span><span class="sxs-lookup"><span data-stu-id="bfd37-139">Mail</span></span>                       | <span data-ttu-id="bfd37-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="bfd37-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bfd37-141">Microsoft Store</span></span>            | <span data-ttu-id="bfd37-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="bfd37-143">Filmler & TV</span><span class="sxs-lookup"><span data-stu-id="bfd37-143">Movies & TV</span></span>                | <span data-ttu-id="bfd37-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="bfd37-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bfd37-145">OneDrive</span></span>                   | <span data-ttu-id="bfd37-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="bfd37-147">Fotoğraflar</span><span class="sxs-lookup"><span data-stu-id="bfd37-147">Photos</span></span>                     | <span data-ttu-id="bfd37-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="bfd37-149">Ayarlar</span><span class="sxs-lookup"><span data-stu-id="bfd37-149">Settings</span></span>                   | <span data-ttu-id="bfd37-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="bfd37-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="bfd37-151">İpuçları</span><span class="sxs-lookup"><span data-stu-id="bfd37-151">Tips</span></span>                       | <span data-ttu-id="bfd37-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="bfd37-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="bfd37-153">1 - Uygulama Yükleyicisi yalnızca Uygulama Yükleyicisi uygulamasını engellemez; Microsoft Store veya MDM çözümünüz gibi diğer kaynaklardan yüklenmiş uygulamaları engellemez.</span><span class="sxs-lookup"><span data-stu-id="bfd37-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="bfd37-154">Paket Aile Adı bulma</span><span class="sxs-lookup"><span data-stu-id="bfd37-154">How to find a Package Family Name</span></span>

<span data-ttu-id="bfd37-155">Bir uygulama bu listede yoksa, bir kullanıcı PackageRelativeID'yi belirlemek ve buradan PackageFamilyName'i almak için, engellenmiş uygulamayı yüklemiş bir HoloLens 2'ye bağlı Cihaz Portalı kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="bfd37-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="bfd37-156">Uygulamayı 2. HoloLens yükleyin.</span><span class="sxs-lookup"><span data-stu-id="bfd37-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="bfd37-157">-Ayarlar -> Update & -> Geliştiriciler için'i açın ve Ardından Geliştirici **modunu ve** ardından **Cihaz portalı'ı etkinleştirin.**</span><span class="sxs-lookup"><span data-stu-id="bfd37-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="bfd37-158">Daha fazla ayrıntı yönergeleri için cihaz portalı [kurulumu ve kullanımı hakkında daha fazla bilgi için buraya bakın.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="bfd37-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="bfd37-159">Bağlandıktan Cihaz Portalı Görünümler'e ve **ardından Uygulamalar'a** **gidin.**</span><span class="sxs-lookup"><span data-stu-id="bfd37-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="bfd37-160">Yüklü Uygulamalar panelinde, yüklü uygulamayı seçmek için açılan liste kullanın.</span><span class="sxs-lookup"><span data-stu-id="bfd37-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="bfd37-161">PackageRelativeID'i bulun.</span><span class="sxs-lookup"><span data-stu-id="bfd37-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="bfd37-162">Uygulama karakterlerini !'den önce kopyalayın; bu karakterler PackageFamilyName'iniz olur.</span><span class="sxs-lookup"><span data-stu-id="bfd37-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


