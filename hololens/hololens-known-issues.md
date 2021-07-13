---
title: HoloLens için bilinen sorunlar (1. genel)
description: Unity ve Windows cihaz portalını kullanan HoloLens müşterileri ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemize ilişkin güncel tutun.
keywords: sorun giderme, bilinen sorun, yardım
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640313"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="b60e8-104">HoloLens için bilinen sorunlar (1. genel)</span><span class="sxs-lookup"><span data-stu-id="b60e8-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="b60e8-105">HoloLens cihazlar için bilinen sorunların güncel listesi aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="b60e8-106">Tek bir davranış görüyorsanız, önce burayı işaretleyin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="b60e8-107">bu liste, yeni sorunlar keşfedildiğinde veya raporlanacağı ya da sorunlar gelecekte HoloLens yazılım güncelleştirmelerinde giderildiği için güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="b60e8-108">bunu engellemeyen bir sorun keşfettiğiniz takdirde, lütfen [geri bildirim merkezi](hololens-feedback.md)aracılığıyla HoloLens cihazınızda bildirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="b60e8-109">Karşılaştığınız sorun sizi engelliyorsa, geri bildirimde bulunmak için lütfen [bir destek isteği](https://aka.ms/hlsupport)gönderin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="b60e8-110">tüm HoloLens oluşumlara yönelik bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="b60e8-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="b60e8-111">HoloLens için bilinen sorunlar (1. genel)</span><span class="sxs-lookup"><span data-stu-id="b60e8-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="b60e8-112">tüm HoloLens oluşumlara yönelik bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="b60e8-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="b60e8-113">Unity</span><span class="sxs-lookup"><span data-stu-id="b60e8-113">Unity</span></span>

- <span data-ttu-id="b60e8-114">HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="b60e8-115">unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="b60e8-116">Windows Cihaz portalı</span><span class="sxs-lookup"><span data-stu-id="b60e8-116">Windows Device Portal</span></span>

- <span data-ttu-id="b60e8-117">Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="b60e8-118">Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="b60e8-119">Bunların kullanılması hiçbir etkiye sahip olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="b60e8-119">Using them will have no effect.</span></span> <span data-ttu-id="b60e8-120">Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="b60e8-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="b60e8-121">Ayarlar geliştirici modunu etkinleştirdikten sonra, cihaz portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="b60e8-122">kamera karşıya yükleme OneDrive</span><span class="sxs-lookup"><span data-stu-id="b60e8-122">OneDrive camera upload</span></span>

<span data-ttu-id="b60e8-123">HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="b60e8-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="b60e8-124">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="b60e8-124">Workarounds:</span></span>

- <span data-ttu-id="b60e8-125">İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="b60e8-126">iş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama, çift oturum açma desteği sağlar).</span><span class="sxs-lookup"><span data-stu-id="b60e8-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="b60e8-127">OneDrive içindeki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="b60e8-128">fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza fotoğraf el ile yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="b60e8-129">bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="b60e8-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="b60e8-130">Düğmesini seçin **+** ve **upload**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="b60e8-131">**Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun.</span><span class="sxs-lookup"><span data-stu-id="b60e8-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="b60e8-132">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="b60e8-133">HoloLens için bilinen sorunlar (1. genel)</span><span class="sxs-lookup"><span data-stu-id="b60e8-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="b60e8-134">Visual Studio üzerinden HoloLens bağlanamaz ve dağıtım yapılamıyor</span><span class="sxs-lookup"><span data-stu-id="b60e8-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="b60e8-135">son güncelleştirme: 8/8 @ 5:11pm-Visual Studio, bu soruna yönelik bir çözüm içeren VS 2019 sürüm 16,2 ' i yayımladı.</span><span class="sxs-lookup"><span data-stu-id="b60e8-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="b60e8-136">Bu hatayı kullanmaktan kaçınmak için bu en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="b60e8-137">Visual Studio, bu soruna yönelik bir çözüm içeren VS 2019 sürüm 16,2 ' i yayımladı.</span><span class="sxs-lookup"><span data-stu-id="b60e8-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="b60e8-138">Bu hatayı kullanmaktan kaçınmak için bu en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="b60e8-139">sorun kök-nedeni: HoloLens uygulamaları dağıtmak ve bunlara hata ayıklamak için Visual Studio 2017 ' nin Visual Studio 2015 veya sonraki sürümlerini kullanan kullanıcılar ve daha sonra Visual Studio 2017 ' ın en son sürümlerini ve Visual Studio 2019 ile aynı HoloLens etkilenir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="b60e8-140">Visual Studio yeni sürümleri, bir bileşenin yeni bir sürümünü dağıtmaktadır, ancak eski sürümdeki dosyalar cihazda bırakılır, bu da yeni sürümün başarısız olmasına neden olur.</span><span class="sxs-lookup"><span data-stu-id="b60e8-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="b60e8-141">Bu, şu hata iletisine neden olur: DEP0100: hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="b60e8-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="b60e8-142">80004005 hatası nedeniyle bir geliştirici lisansı alınamadı \<ip\> .</span><span class="sxs-lookup"><span data-stu-id="b60e8-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="b60e8-143">Geçici çözüm</span><span class="sxs-lookup"><span data-stu-id="b60e8-143">Workaround</span></span>

<span data-ttu-id="b60e8-144">Ekibimiz şu anda bir çözüm üzerinde çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="b60e8-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="b60e8-145">Bu sırada, soruna geçici bir çözüm bulmak için aşağıdaki adımları kullanabilir ve dağıtımın ve hata ayıklamanın engellemesini kaldırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b60e8-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="b60e8-146">Visual Studio'yu açın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="b60e8-147">**dosya**  >  **yeni**  >  **Project** seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="b60e8-148">**Visual C#**  >  **Windows masaüstü**  >  **konsol uygulaması (.NET Framework)** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="b60e8-149">projeye bir ad verin (örneğin, "holomersdeploymentdüzeltmesini") ve Framework 'ün en az .NET Framework 4,5 ' e ayarlandığından emin olun ve ardından **tamam**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="b60e8-150">Çözüm Gezgini ' deki **Başvurular** düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin ( **Gözden** geçirme bölümüne ve sonra da **gözatatıon**' ı seçin):</span><span class="sxs-lookup"><span data-stu-id="b60e8-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="b60e8-151">10.0.18362.0 yüklü değilse, en son sürümü kullanın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="b60e8-152">Çözüm Gezgini projede projeye sağ tıklayın ve   >  **var olan öğe** Ekle ' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="b60e8-153">C:\Program Files (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 konumuna gidin ve filtreyi **tüm dosyalar ( \* . \* )** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="b60e8-154">SirepClient.dll ve SshClient.dll her ikisini de seçin ve **Ekle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="b60e8-155">Çözüm Gezgini her iki dosyayı da bulun ve seçin (dosyalar listesinin en altında olmaları gerekir) ve **her zaman kopyalamak** için **Özellikler** penceresinde **Çıkış Dizinine Kopyala** ' yı değiştirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="b60e8-156">Dosyanın üst kısmında, mevcut deyimler listesine aşağıdakileri ekleyin `using` :</span><span class="sxs-lookup"><span data-stu-id="b60e8-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="b60e8-157">İçinde `static void Main(...)` , aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="b60e8-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="b60e8-158">Yapı   >  **Yapı çözümünü** seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="b60e8-159">Derlenmiş .exe dosyasını içeren klasöre bir komut Istemi penceresi ve CD açın (örneğin, C:\myprojeler\windows Holomersdeploymentfix\bin\debug).</span><span class="sxs-lookup"><span data-stu-id="b60e8-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="b60e8-160">Yürütülebilir dosyayı çalıştırın ve bir komut satırı bağımsız değişkeni olarak cihazın IP adresini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="b60e8-161">(USB kullanarak bağlıysanız 127.0.0.1 kullanabilirsiniz, aksi takdirde cihazın Wi-Fi IP adresini kullanamazsınız.)  Örneğin, "Holomersdeploymentdüzeltmesini 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="b60e8-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="b60e8-162">araç herhangi bir ileti olmadan çıktıktan sonra (bu yalnızca birkaç saniye sürer), artık Visual Studio 2017 veya daha yeni bir sürümü dağıtabilir ve hata ayıklaması yapabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="b60e8-163">Aracın devam eden kullanımı gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="b60e8-164">Kullanılabilir hale geldiğinde daha fazla güncelleştirme sağlayacağız.</span><span class="sxs-lookup"><span data-stu-id="b60e8-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="b60e8-165">HoloLens üzerinde Microsoft Store ve uygulamaları başlatan sorunlar</span><span class="sxs-lookup"><span data-stu-id="b60e8-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="b60e8-166">Son güncelleştirme: 4/2 @ 10-sorun çözüldü.</span><span class="sxs-lookup"><span data-stu-id="b60e8-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="b60e8-167">HoloLens üzerinde Microsoft Store ve uygulamaları başlatmaya çalışırken sorunlarla karşılaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="b60e8-168">Arka plan uygulama güncelleştirmeleri, bir veya daha fazla bağımlı uygulama çalışmaya devam ederken belirli bir sırada çerçeve paketlerinin daha yeni bir sürümünü dağıtırken sorunun oluştuğunu belirledik.</span><span class="sxs-lookup"><span data-stu-id="b60e8-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="b60e8-169">bu durumda, bir otomatik uygulama güncelleştirmesi .NET Native framework 'ün yeni bir sürümünü (sürüm 10.0.25531 ile 10.0.27413) dağıttığı, çalışan uygulamaların, Framework 'ün önceki sürümünü kullanan tüm çalışan uygulamalar için düzgün şekilde güncelleştirileceğinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="b60e8-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="b60e8-170">Çerçeve güncelleştirmesi için akış aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="b60e8-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="b60e8-171">Yeni çerçeve paketi mağazadan indirilir ve yüklenir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="b60e8-172">Eski Framework kullanan tüm uygulamalar, daha yeni sürümü kullanmak için ' güncelleştirildi '.</span><span class="sxs-lookup"><span data-stu-id="b60e8-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="b60e8-173">2. adım tamamlanmadan önce kesintiye uğrarsa, daha yeni Framework 'ün kaydolmadığı tüm uygulamalar Başlangıç menüsünden başlayamaz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="b60e8-174">HoloLens üzerinde herhangi bir uygulamanın bu sorundan etkilendiğine inandık.</span><span class="sxs-lookup"><span data-stu-id="b60e8-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="b60e8-175">Bazı kullanıcılar, askıda olan uygulamaları kapatan ve geri bildirim merkezi gibi diğer uygulamaları başlatan rapor verdi, 3B görüntüleyici veya fotoğraflar bu sorunu çözer. ancak, bu sürenin %100 ' i çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="b60e8-176">kök sunuyoruz, bu sorunun güncelleştirmenin kendisinin neden olmadığı, ancak işletim sisteminde .NET Native framework güncelleştirmesiyle yanlış işlenmekte olan bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="b60e8-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="b60e8-177">Bir onarım belirlediğimiz ve bu güncelleştirmeyi içeren bir güncelleştirme (OS sürüm 17763,380) yayımladığımızda duyurmaktan memnuniyet duyuyoruz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="b60e8-178">Cihazınızın güncelleştirmeyi alıp almaz:</span><span class="sxs-lookup"><span data-stu-id="b60e8-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="b60e8-179">Ayarlar uygulamasına gidin ve **güncelleştirme & güvenlik**' i açın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="b60e8-180">**Güncelleştirmeleri denetle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="b60e8-181">17763,380 güncelleştirmesi varsa, uygulama askıda kalma hatasına yönelik çözümü almak için lütfen bu yapıya güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="b60e8-182">İşletim sisteminin bu sürümüne güncelleştirme yapıldığında uygulamalar beklendiği gibi çalışmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b60e8-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="b60e8-183">ayrıca, her HoloLens işletim sistemi sürümünde yaptığımız gibi, [Microsoft indirme merkezi](https://aka.ms/hololensdownload/10.0.17763.380)'ne ffu görüntüsünü naklettik.</span><span class="sxs-lookup"><span data-stu-id="b60e8-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="b60e8-184">güncelleştirmeyi yapmak istemiyorsanız, 3/29 itibariyle Microsoft Store UWP uygulamasının yeni bir sürümünü yayımladık.</span><span class="sxs-lookup"><span data-stu-id="b60e8-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="b60e8-185">Mağaza 'nın güncelleştirilmiş sürümüne sahip olduktan sonra:</span><span class="sxs-lookup"><span data-stu-id="b60e8-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="b60e8-186">Mağazayı açın ve yüklendiğini onaylayın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="b60e8-187">Menüyü açmak için Bloom hareketini kullanın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="b60e8-188">Daha önce bozulan uygulamaları açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="b60e8-189">Hala başlatılamaz, bozuk uygulamanın simgesine dokunup basılı tutun ve Kaldır ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="b60e8-190">Bu uygulamaları mağazadan yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="b60e8-191">cihazınız hala uygulama yükleyeerişemiyorsanız, aşağıdaki adımları izleyerek .NET Native Framework ve çalışma zamanının bir sürümünü indirme merkezi aracılığıyla dışarıdan yükleyebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b60e8-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="b60e8-192">Lütfen [Bu zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi ' nden indirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="b60e8-193">Unzippıng iki dosya oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b60e8-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="b60e8-194">Microsoft. NET. Native. Runtime. 1.7. appx ve Microsoft. NET. Native. Framework. 1.7. appx.</span><span class="sxs-lookup"><span data-stu-id="b60e8-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="b60e8-195">Lütfen cihazınızın dev olarak kilidinin açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="b60e8-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="b60e8-196">daha önce yapmadıysanız yönergeler için [Windows cihaz portalını kullanma](/windows/mixed-reality/using-the-windows-device-portal) konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="b60e8-197">daha sonra Windows cihaz portalına ulaşmak istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="b60e8-198">Önerimiz bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak yapmanız gerekir http://127.0.0.1:10080 .</span><span class="sxs-lookup"><span data-stu-id="b60e8-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="b60e8-199">cihaz portalını Windows aldıktan sonra, indirdiğiniz iki dosyayı "dışarıdan yükleme" yapmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="b60e8-200">Bunu yapmak için, **uygulamalar** bölümüne ulaşana ve **uygulamalar**' ı seçene kadar sol taraftaki çubuğa gitmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="b60e8-201">Ardından aşağıdakine benzer bir ekran görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="b60e8-202">Uygulama Yükle bölümüne gitmek ve **bu** iki APPX dosyanın sıkıştırması açılmış olan yere göz atmak istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="b60e8-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="b60e8-203">Aynı anda yalnızca bir tane abilirsiniz, bu nedenle ilki seçdikten sonra Dağıt bölümünün altındaki "Git" seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="b60e8-204">Ardından bunu ikinci APPX dosyası için yap.</span><span class="sxs-lookup"><span data-stu-id="b60e8-204">Then do this for the second APPX file.</span></span>

   ![Windows Cihaz Portalı'i Side-Loaded yükleme](images/20190322-DevicePortal.png)

1. <span data-ttu-id="b60e8-206">Bu noktada, uygulamalarınızı yeniden çalışmaya başlaması gerektiğine ve Mağaza'ya da varabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="b60e8-207">Bazı durumlarda, etkilenen uygulamalar başlatılamadan önce 3B Görüntüleyici başlatmanın ek adımını çalıştırmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="b60e8-208">Bu sorunu çözecek süreci tamamlaya kadar sabırdan dolayı teşekkür ederiz ve başarılı Karma Gerçeklik deneyimleri oluşturmak için topluluğumuzla çalışmaya devam etmek için sabırsızlanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="b60e8-209">Cihaz Güncelleştirmesi</span><span class="sxs-lookup"><span data-stu-id="b60e8-209">Device Update</span></span>

- <span data-ttu-id="b60e8-210">Yeni güncelleştirmeden 30 saniye sonra kabuk bir kez gözden kaybolabilir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="b60e8-211">Oturum **sürdürmeniz için** lütfen bloom hareketi gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="b60e8-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="b60e8-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b60e8-212">Visual Studio</span></span>

- <span data-ttu-id="b60e8-213">Geliştirme [için önerilen](/windows/mixed-reality/install-the-tools) en güncel Visual Studio için araçları yükleme HoloLens bakın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="b60e8-214">Visual Studio'den HoloLens uygulama dağıtırken şu hatayı alabilirsiniz: İstenen işlem kullanıcıyla eşlenmiş bölümü açık olan **bir dosyada gerçekleştirilamaz. (HRESULT özel durumu: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="b60e8-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="b60e8-215">Bu durumda, yeniden deneyin ve dağıtımınız genel olarak başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="b60e8-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="b60e8-216">API</span><span class="sxs-lookup"><span data-stu-id="b60e8-216">API</span></span>

- <span data-ttu-id="b60e8-217">Uygulama kullanıcının odak noktasını [veya](/windows/mixed-reality/focus-point-in-unity) camera.forward için normali ayarlarsa, hologramlar fotoğraf veya videolarda Karma Gerçeklik Yakalama görünmez.</span><span class="sxs-lookup"><span data-stu-id="b60e8-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="b60e8-218">Bu hata Windows düzeltene kadar, uygulamalar odak noktasını [](/windows/mixed-reality/focus-point-in-unity) etkin bir şekilde ayarlasalar, düzlemin normalin kameranın tersini (örneğin, normal = -camera.forward) ayarlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="b60e8-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="b60e8-219">Xbox Kablosuz Denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="b60e8-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="b60e8-220">Xbox Kablosuz Denetleyici S, cihazla birlikte kullanılmadan önce HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b60e8-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="b60e8-221">Denetleyicinizi [bir güvenlik denetleyicisiyle](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) eşleştirmeye çalışmadan önce güncel HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b60e8-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="b60e8-222">Xbox Kablosuz HoloLens bağlıyken cihazınızı yeniden başlatırsanız denetleyici, konsola otomatik olarak HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b60e8-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="b60e8-223">Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatana kadar yavaş yanıp sönecek.</span><span class="sxs-lookup"><span data-stu-id="b60e8-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="b60e8-224">Denetleyicinizi hemen yeniden bağlanmak için, ışık kapatana kadar Kılavuz düğmesini basılı tutarak denetleyiciyi kapatın.</span><span class="sxs-lookup"><span data-stu-id="b60e8-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="b60e8-225">Denetleyiciniz yeniden bağlandığında, denetleyiciniz yeniden HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b60e8-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="b60e8-226">Konsolunuz HoloLens Xbox Kablosuz Denetleyicisi bağlıyken bekleme moduna girerse, denetleyicide herhangi bir giriş HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b60e8-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="b60e8-227">Kullanımınız bittiğinde denetleyicinizi kapatarak bunu önleyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b60e8-227">You can prevent this by powering off your controller when you are done using it.</span></span>

