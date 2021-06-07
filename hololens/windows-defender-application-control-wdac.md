---
title: Windows Defender uygulama denetimi-WDAC
description: Windows Defender uygulama denetiminin ne olduğu ve HoloLens karma gerçeklik cihazlarını yönetmek için nasıl kullanılacağı hakkında genel bakış.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379033"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="67267-103">Windows Defender uygulama denetimi-WDAC</span><span class="sxs-lookup"><span data-stu-id="67267-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="67267-104">WDAC, BT yöneticisinin cihazlarını cihazlarda uygulamaların başlatılmasını engelleyecek şekilde yapılandırmasına olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="67267-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="67267-105">Bu, kullanıcının cihazdaki uygulamaları gizleyen bir kullanıcı arabirimi ile sunulduğu, ancak yine de başlatılabileceği, bilgi noktası modu gibi cihaz kısıtlama yöntemlerinden farklıdır.</span><span class="sxs-lookup"><span data-stu-id="67267-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="67267-106">WDAC uygulandığında, uygulamalar tüm uygulamalar listesinde görünmeye devam eder, ancak bu uygulamaların ve işlemlerin cihaz kullanıcısı tarafından başlatılabilmesini engeller.</span><span class="sxs-lookup"><span data-stu-id="67267-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="67267-107">Bir cihaza birden fazla WDAC ilkesi atanmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="67267-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="67267-108">Bir sistemde birden çok WDAC ilkesi ayarlandıysa, en kısıtlayıcı olanlar geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="67267-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="67267-109">Son kullanıcılar, WDAC tarafından engellenen bir uygulamayı başlatmayı denediklerinde, HoloLens üzerinde bu uygulamayı başlatamayan hakkında bir bildirim almaz.</span><span class="sxs-lookup"><span data-stu-id="67267-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="67267-110">Aşağıda, kullanıcıların [Microsoft Intune Ile HoloLens 2 cihazlarda uygulamalara izin vermek veya bunları engellemek IÇIN WDac ve Windows PowerShell](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)'in nasıl kullanılacağını öğrenme kılavuzu verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="67267-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="67267-111">Kullanıcılar ilk örnek adımını kullanarak Windows 10 bilgisayarında yüklü olan uygulamaları ararken, sonuçları daraltmak için birkaç deneme yapması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="67267-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="67267-112">Paketin tam adını bilmiyorsanız, bulmak için ' Get-AppxPackage-Name, en iyi \* tahmin \* ' i birkaç kez çalıştırmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="67267-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="67267-113">Ardından, adı ' $package 1 = Get-AppxPackage-adı gerçek. PackageName ' olarak çalıştırırsınız</span><span class="sxs-lookup"><span data-stu-id="67267-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="67267-114">Örneğin, Microsoft Edge için aşağıdakiler çalıştırıldığında birden fazla sonuç döndürülür, ancak bu listeden, ihtiyacınız olan tam adın Microsoft. MicrosoftEdge olduğunu belirleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67267-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="67267-115">HoloLens 'teki uygulamalar için paket aile adları</span><span class="sxs-lookup"><span data-stu-id="67267-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="67267-116">Yukarıdaki kılavuzda, newPolicy.xml el ile düzenleyebilir ve yalnızca paket aile adlarıyla HoloLens 'te yüklü olan uygulamalar için kurallar ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="67267-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="67267-117">Bazen, ilke eklemek istediğiniz masaüstü bilgisayarınızda olmayan, kullanmak için kullanabileceğiniz uygulamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="67267-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="67267-118">HoloLens 2 cihazları için yaygın olarak kullanılan ve In-Box uygulamaların bir listesi aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="67267-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="67267-119">Uygulama Adı</span><span class="sxs-lookup"><span data-stu-id="67267-119">App Name</span></span>                   | <span data-ttu-id="67267-120">Paket ailesi adı</span><span class="sxs-lookup"><span data-stu-id="67267-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="67267-121">3B görüntüleyici</span><span class="sxs-lookup"><span data-stu-id="67267-121">3D Viewer</span></span>                  | <span data-ttu-id="67267-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="67267-123">Uygulama yükleyicisi</span><span class="sxs-lookup"><span data-stu-id="67267-123">App Installer</span></span>              | <span data-ttu-id="67267-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="67267-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="67267-125">Takvim</span><span class="sxs-lookup"><span data-stu-id="67267-125">Calendar</span></span>                   | <span data-ttu-id="67267-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="67267-127">Kamera</span><span class="sxs-lookup"><span data-stu-id="67267-127">Camera</span></span>                     | <span data-ttu-id="67267-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="67267-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="67267-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="67267-129">Cortana</span></span>                    | <span data-ttu-id="67267-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="67267-131">Dynamics 365 kılavuzlar</span><span class="sxs-lookup"><span data-stu-id="67267-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="67267-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="67267-133">Dynamics 365 uzaktan yardım</span><span class="sxs-lookup"><span data-stu-id="67267-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="67267-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="67267-135">Geribildirim Merkezi</span><span class="sxs-lookup"><span data-stu-id="67267-135">Feedback Hub</span></span>               | <span data-ttu-id="67267-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="67267-137">Dosya Gezgini</span><span class="sxs-lookup"><span data-stu-id="67267-137">File Explorer</span></span>              | <span data-ttu-id="67267-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="67267-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="67267-139">Posta</span><span class="sxs-lookup"><span data-stu-id="67267-139">Mail</span></span>                       | <span data-ttu-id="67267-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="67267-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="67267-141">Microsoft Store</span></span>            | <span data-ttu-id="67267-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="67267-143">TV & Filmler</span><span class="sxs-lookup"><span data-stu-id="67267-143">Movies & TV</span></span>                | <span data-ttu-id="67267-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="67267-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="67267-145">OneDrive</span></span>                   | <span data-ttu-id="67267-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="67267-147">Fotoğraflar</span><span class="sxs-lookup"><span data-stu-id="67267-147">Photos</span></span>                     | <span data-ttu-id="67267-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="67267-149">Ayarlar</span><span class="sxs-lookup"><span data-stu-id="67267-149">Settings</span></span>                   | <span data-ttu-id="67267-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="67267-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="67267-151">İpuçları</span><span class="sxs-lookup"><span data-stu-id="67267-151">Tips</span></span>                       | <span data-ttu-id="67267-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="67267-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="67267-153">1-uygulama yükleyicisi, uygulama yükleyici uygulamasını yalnızca Microsoft Store veya MDM çözümünüzden yüklenen uygulamalar değil, uygulamaları engeller.</span><span class="sxs-lookup"><span data-stu-id="67267-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="67267-154">Paket aile adını bulma</span><span class="sxs-lookup"><span data-stu-id="67267-154">How to find a Package Family Name</span></span>

<span data-ttu-id="67267-155">Bir uygulama bu listede yoksa, bir Kullanıcı, Packagerelativeıd 'sini ve PackageFamilyName Al ' ı öğrenmek için, uygulamayı engellenme olarak yükleyen bir HoloLens 2 ' ye bağlı olan cihaz portalını kullanabilir.</span><span class="sxs-lookup"><span data-stu-id="67267-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="67267-156">Uygulamayı HoloLens 2 cihazınıza yüklersiniz.</span><span class="sxs-lookup"><span data-stu-id="67267-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="67267-157">Ayarları aç-> güncelleştirmeler & geliştiriciler Için güvenlik-> ve **Geliştirici modunu** ve ardından **cihaz portalını** etkinleştirir.</span><span class="sxs-lookup"><span data-stu-id="67267-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="67267-158">Daha fazla ayrıntı yönergesi [cihaz portalının kurulumu ve kullanımı](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="67267-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="67267-159">Cihaz portalı bağlandıktan sonra, **Görünümler** ' e gidin ve ardından **uygulamalar**' a gidin.</span><span class="sxs-lookup"><span data-stu-id="67267-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="67267-160">Yüklü uygulamalar panelinde, açılan listeyi kullanarak yüklü uygulamayı seçin.</span><span class="sxs-lookup"><span data-stu-id="67267-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="67267-161">Packagerelativeıd öğesini bulun.</span><span class="sxs-lookup"><span data-stu-id="67267-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="67267-162">Uygulama karakterlerini! önüne kopyalayın, bu karakterler PackageFamilyName olacaktır.</span><span class="sxs-lookup"><span data-stu-id="67267-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


