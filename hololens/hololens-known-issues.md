---
title: HoloLens için bilinen sorunlar (1. Nesil)
description: Unity ve diğer platformları kullanan HoloLens müşterilerini ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemizi takip Windows Cihaz Portalı.
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923559"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="1d510-104">HoloLens için bilinen sorunlar (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="1d510-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="1d510-105">HoloLens cihazları için bilinen sorunların güncel listesi burada vemektedir.</span><span class="sxs-lookup"><span data-stu-id="1d510-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="1d510-106">Garip bir davranış görüyorsanız önce buraya göz sınız.</span><span class="sxs-lookup"><span data-stu-id="1d510-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="1d510-107">Bu liste yeni sorunlar keşfedildi veya raporlandıkça ya da gelecek HoloLens yazılım güncelleştirmeleri ile ilgili sorunlar giderildikça güncelleştirilecek.</span><span class="sxs-lookup"><span data-stu-id="1d510-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="1d510-108">Engellemeye neden olan bir sorun fark ediyorsanız lütfen bu sorunu [Geri Bildirim Merkezi.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="1d510-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="1d510-109">Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="1d510-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="1d510-110">Tüm HoloLens nesilleri için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="1d510-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="1d510-111">HoloLens için bilinen sorunlar (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="1d510-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="1d510-112">Tüm HoloLens nesilleri için bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="1d510-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="1d510-113">Unity</span><span class="sxs-lookup"><span data-stu-id="1d510-113">Unity</span></span>

- <span data-ttu-id="1d510-114">Bkz. [Unity'nin](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens geliştirmesi için önerilen en güncel sürümü için araçları yükleme.</span><span class="sxs-lookup"><span data-stu-id="1d510-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="1d510-115">Unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="1d510-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="1d510-116">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="1d510-116">Windows Device Portal</span></span>

- <span data-ttu-id="1d510-117">Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="1d510-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="1d510-118">Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir.</span><span class="sxs-lookup"><span data-stu-id="1d510-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="1d510-119">Bunları kullanmanın hiçbir etkisi olmaz.</span><span class="sxs-lookup"><span data-stu-id="1d510-119">Using them will have no effect.</span></span> <span data-ttu-id="1d510-120">Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="1d510-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="1d510-121">Ayarlar'da Geliştirici Modu etkinleştirildikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.</span><span class="sxs-lookup"><span data-stu-id="1d510-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="1d510-122">OneDrive kamera karşıya yükleme</span><span class="sxs-lookup"><span data-stu-id="1d510-122">OneDrive camera upload</span></span>

<span data-ttu-id="1d510-123">HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.</span><span class="sxs-lookup"><span data-stu-id="1d510-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="1d510-124">Geçici çözümler:</span><span class="sxs-lookup"><span data-stu-id="1d510-124">Workarounds:</span></span>

- <span data-ttu-id="1d510-125">İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir.</span><span class="sxs-lookup"><span data-stu-id="1d510-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="1d510-126">İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması çift oturum açmayı destekler).</span><span class="sxs-lookup"><span data-stu-id="1d510-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="1d510-127">OneDrive'Microsoft hesabı profilden otomatik, arka plan kameralı rolle karşıya yükleme özelliğini etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="1d510-128">Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="1d510-129">Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızla oturum asanıza.</span><span class="sxs-lookup"><span data-stu-id="1d510-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="1d510-130">Düğmesini seçin **+** ve Karşıya **Yükle'yi seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="1d510-131">Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.**</span><span class="sxs-lookup"><span data-stu-id="1d510-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="1d510-132">Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="1d510-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="1d510-133">HoloLens için bilinen sorunlar (1. Nesil)</span><span class="sxs-lookup"><span data-stu-id="1d510-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="1d510-134">Sanal ağ üzerinden HoloLens'e bağlanamıyor ve Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1d510-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="1d510-135">Son Güncelleştirme: 8/05:11 - Visual Studio, bu soruna bir düzeltme içeren VS 2019 Sürüm 16.2'yi yayımladı.</span><span class="sxs-lookup"><span data-stu-id="1d510-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="1d510-136">Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="1d510-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="1d510-137">Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı.</span><span class="sxs-lookup"><span data-stu-id="1d510-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="1d510-138">Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="1d510-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="1d510-139">Sorunun kök nedeni: HoloLens'lerinde uygulamaları dağıtmak ve bunların hata ayıklamak için Visual Studio Visual Studio 2015 veya önceki sürümlerini kullanan ve daha sonra aynı HoloLens ile Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan kullanıcılar etkilenecektir.</span><span class="sxs-lookup"><span data-stu-id="1d510-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="1d510-140">Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.</span><span class="sxs-lookup"><span data-stu-id="1d510-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="1d510-141">Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="1d510-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="1d510-142">\<ip\>80004005 hatası nedeniyle üzerinde geliştirici lisansı alınemedi.</span><span class="sxs-lookup"><span data-stu-id="1d510-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="1d510-143">Geçici çözüm</span><span class="sxs-lookup"><span data-stu-id="1d510-143">Workaround</span></span>

<span data-ttu-id="1d510-144">Ekibimiz şu anda bir düzeltme üzerinde çalışıyor.</span><span class="sxs-lookup"><span data-stu-id="1d510-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="1d510-145">Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1d510-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="1d510-146">Visual Studio'yu açın.</span><span class="sxs-lookup"><span data-stu-id="1d510-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="1d510-147">Dosya Yeni  >  **Proje'yi**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="1d510-148">**Visual C#**  >  **Windows Masaüstü Konsol Uygulaması**  >  **(.NET Framework) öğesini seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="1d510-149">Projeye bir ad ("HoloLensDeploymentFix" gibi) ve Framework'in en az 4.5 .NET Framework olduğundan emin olun ve Tamam'ı **seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="1d510-150">Çözüm Gezgini'de  Başvurular düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin **(Gözat** bölümüne gidin ve Gözat'ı **seçin):**</span><span class="sxs-lookup"><span data-stu-id="1d510-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="1d510-151">10.0.18362.0 yüklü değilse, sahip olduğunuz en son sürümü kullanın.</span><span class="sxs-lookup"><span data-stu-id="1d510-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="1d510-152">Uygulama içinde projeye sağ tıklayın ve Çözüm Gezgini **Ekle'yi**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="1d510-153">C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 dizinine göz atarak filtreyi Tüm Dosyalar **( \* . ) \* olarak** değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="1d510-154">Hem SirepClient.dll hem de SshClient.dll ve Ekle'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="1d510-155">Her iki dosyayı da Çözüm Gezgini (dosya listesinin en altında olması gerekir)  bulun ve seçin  ve Özellikler penceresindeKi Çıkış Dizinine Kopyala seçeneğini Her zaman kopyala **olarak değiştirin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="1d510-156">Dosyanın en üstüne, mevcut deyim listesine aşağıdakini `using` ekleyin:</span><span class="sxs-lookup"><span data-stu-id="1d510-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="1d510-157">içinde, `static void Main(...)` aşağıdaki kodu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="1d510-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="1d510-158">Derleme   >  **Çözümü'lerini seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="1d510-159">Bir Komut İstemi Penceresi açın ve derlenmiş .exe dosyasını içeren klasöre cd yazın (örneğin, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="1d510-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="1d510-160">Yürütülebilir dosyayı çalıştırın ve cihazın IP adresini komut satırı bağımsız değişkeni olarak girin.</span><span class="sxs-lookup"><span data-stu-id="1d510-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="1d510-161">(USB kullanarak bağlandıysanız 127.0.0.1 kullanabilirsiniz, aksi takdirde cihazın ip Wi-Fi kullanabilirsiniz.)  Örneğin, "HoloLensDeploymentFix 127.0.0.1".</span><span class="sxs-lookup"><span data-stu-id="1d510-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="1d510-162">Araçtan herhangi bir ileti olmadan çıkıldıktan sonra (bu yalnızca birkaç saniye sürer), artık 2017 veya daha yeni bir sürümde Visual Studio ve hata ayıklaması alabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="1d510-163">Aracın devam eden kullanımı gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="1d510-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="1d510-164">Yeni güncelleştirmeler kullanılabilir hale geldi.</span><span class="sxs-lookup"><span data-stu-id="1d510-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="1d510-165">HoloLens'Microsoft Store uygulamaları başlatma sorunları</span><span class="sxs-lookup"><span data-stu-id="1d510-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="1d510-166">Son Güncelleştirme: 10.00'da 4/2 - Sorun çözüldü.</span><span class="sxs-lookup"><span data-stu-id="1d510-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="1d510-167">HoloLens'de uygulama ve Microsoft Store başlatmaya çalışırken sorun yaşayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="1d510-168">Arka plan uygulama güncelleştirmeleri, bağımlı uygulamalardan biri veya daha fazlası çalışırken belirli dizilerde çerçeve paketlerinin daha yeni bir sürümünü dağıtıyorsa bu sorunun oluştuğuna karar verdik.</span><span class="sxs-lookup"><span data-stu-id="1d510-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="1d510-169">Bu durumda, otomatik uygulama güncelleştirmesi .NET Native Framework'un yeni bir sürümünü (sürüm 10.0.25531-10.0.27413) teslim etti. Bu, çalışan uygulamaların çerçevenin önceki sürümünü tüketen tüm uygulamalar için doğru şekilde güncelleştirilenemalarına neden oldu.</span><span class="sxs-lookup"><span data-stu-id="1d510-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="1d510-170">Çerçeve güncelleştirme akışı aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="1d510-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="1d510-171">Yeni çerçeve paketi mağazadan indirilir ve yüklenir.</span><span class="sxs-lookup"><span data-stu-id="1d510-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="1d510-172">Tüm uygulamalar çerçeveyi kullanan tüm sürümler daha yeni sürümü kullanmak için 'güncelleştirilir'.</span><span class="sxs-lookup"><span data-stu-id="1d510-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="1d510-173">2. adım tamamlanmadan kesintiye uğrarsa, yeni çerçevenin kayıtlı olmadığı tüm uygulamalar başlat menüsünden başlatılamayacaktır.</span><span class="sxs-lookup"><span data-stu-id="1d510-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="1d510-174">HoloLens'in tüm uygulamalarının bu sorundan etkilenebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="1d510-175">Bazı kullanıcılar, askıda olan uygulamaları kapatmanın ve Geri Bildirim Merkezi, 3B Görüntüleyici veya Photos gibi diğer uygulamaların başlatılmasının sorunu çözeceklerini bildirdi. Ancak, bu sürenin %100'sinde işe yaramamektedir.</span><span class="sxs-lookup"><span data-stu-id="1d510-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="1d510-176">Kök neden olarak bu sorunun güncelleştirmenin kendisi değil, işletim sistemi hatası nedeniyle .NET Native framework güncelleştirmesi yanlış işlenmeye neden oldu.</span><span class="sxs-lookup"><span data-stu-id="1d510-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="1d510-177">Bir düzeltme belirledik ve düzeltmeyi içeren bir güncelleştirme (işletim sistemi sürümü 17763.380) yayımlamıştık.</span><span class="sxs-lookup"><span data-stu-id="1d510-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="1d510-178">Cihazınızın güncelleştirmeyi alıp alamayını görmek için:</span><span class="sxs-lookup"><span data-stu-id="1d510-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="1d510-179">Ayarlar uygulamasına gidin ve Update **& Security'& açın.**</span><span class="sxs-lookup"><span data-stu-id="1d510-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="1d510-180">Güncelleştirmeleri **Kontrol Edin'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="1d510-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="1d510-181">17763.380 güncelleştirmesi varsa, Uygulama Askıda Kalma hatasının düzeltmesini almak için lütfen bu derlemeye güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="1d510-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="1d510-182">Bu işletim sistemi sürümüne güncelleştiren Uygulamalar beklendiği gibi çalışmalı.</span><span class="sxs-lookup"><span data-stu-id="1d510-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="1d510-183">Ayrıca, her HoloLens işletim sistemi sürümüyle olduğu gibi, FFU görüntüsünü Microsoft İndirme [Merkezi'ne de paylaştık.](https://aka.ms/hololensdownload/10.0.17763.380)</span><span class="sxs-lookup"><span data-stu-id="1d510-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="1d510-184">Güncelleştirmeyi almak tercih ediyorsanız, 29/3/29'dan Microsoft Store UWP uygulamasının yeni bir sürümünü yayınlandı.</span><span class="sxs-lookup"><span data-stu-id="1d510-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="1d510-185">Mağazanın güncelleştirilmiş sürümünü edindikten sonra:</span><span class="sxs-lookup"><span data-stu-id="1d510-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="1d510-186">Mağazayı açın ve yük olduğunu onaylayın.</span><span class="sxs-lookup"><span data-stu-id="1d510-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="1d510-187">Menüyü açmak için bloom hareketini kullanın.</span><span class="sxs-lookup"><span data-stu-id="1d510-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="1d510-188">Daha önce bozuk olan uygulamaları açmayı deneme.</span><span class="sxs-lookup"><span data-stu-id="1d510-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="1d510-189">Hala başlatılamaysa, bozuk uygulamanın simgesine dokunun ve basılı tutun ve kaldır'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="1d510-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="1d510-190">Bu uygulamaları mağazadan yeniden yükleyin.</span><span class="sxs-lookup"><span data-stu-id="1d510-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="1d510-191">Cihazınız yine de uygulama yükleyenene kadar, aşağıdaki adımları kullanarak indirme merkezi üzerinden .NET Native Framework ve Çalışma Zamanı sürümünü kenardan indirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="1d510-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="1d510-192">Lütfen bu [zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi'nden indirin.</span><span class="sxs-lookup"><span data-stu-id="1d510-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="1d510-193">Sıkıştırmayı geri alama iki dosya üretir.</span><span class="sxs-lookup"><span data-stu-id="1d510-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="1d510-194">Microsoft .NET.Native.Runtime.1.7.appx ve Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="1d510-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="1d510-195">Lütfen cihazınızın geliştirici kilidinin açık olduğunu doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="1d510-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="1d510-196">Bunu daha önce yapmadıysanız yönergeler [için bkz. Windows Cihaz Portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) kullanma.</span><span class="sxs-lookup"><span data-stu-id="1d510-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="1d510-197">Daha sonra yeni bir Windows Cihaz Portalı.</span><span class="sxs-lookup"><span data-stu-id="1d510-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="1d510-198">Bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak http://127.0.0.1:10080 yapmaktır.</span><span class="sxs-lookup"><span data-stu-id="1d510-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="1d510-199">Uygulamayı yükledikten Windows Cihaz Portalı indirdiğiniz iki dosyayı "yan yükleme" gerekir.</span><span class="sxs-lookup"><span data-stu-id="1d510-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="1d510-200">Bunu yapmak için Uygulamalar bölümüne gidip Uygulamalar'ı seçene **kadar** sol kenar çubuğuna **inebilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="1d510-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="1d510-201">Ardından aşağıdakine benzer bir ekran görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="1d510-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="1d510-202">Uygulama Yükle bölümüne gitmek ve **bu** iki APPX dosyanın sıkıştırması açılmış olan yere göz atmak istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="1d510-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="1d510-203">Aynı anda yalnızca bir tane abilirsiniz, bu nedenle ilki seçdikten sonra Dağıt bölümünün altındaki "Git" seçeneğine tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1d510-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="1d510-204">Ardından bunu ikinci APPX dosyası için yap.</span><span class="sxs-lookup"><span data-stu-id="1d510-204">Then do this for the second APPX file.</span></span>

   ![Windows Cihaz Portalı uygulamayı Side-Loaded gerekir](images/20190322-DevicePortal.png)

1. <span data-ttu-id="1d510-206">Bu noktada, uygulamalarınızı yeniden çalışmaya başlaması gerektiğine ve Mağaza'ya da varabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="1d510-207">Bazı durumlarda, etkilenen uygulamalar başlatılamadan önce 3B Görüntüleyici başlatmanın ek adımını çalıştırmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="1d510-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="1d510-208">Bu sorunu çözecek süreci tamamlaya kadar sabırdan dolayı teşekkür ederiz ve başarılı Karma Gerçeklik deneyimleri oluşturmak için topluluğumuzla çalışmaya devam etmek için sabırsızlanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="1d510-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="1d510-209">Cihaz Güncelleştirmesi</span><span class="sxs-lookup"><span data-stu-id="1d510-209">Device Update</span></span>

- <span data-ttu-id="1d510-210">Yeni güncelleştirmeden 30 saniye sonra kabuk bir kez gözden kaybolabilir.</span><span class="sxs-lookup"><span data-stu-id="1d510-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="1d510-211">Oturum **sürdürmeniz için** lütfen bloom hareketi gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="1d510-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="1d510-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1d510-212">Visual Studio</span></span>

- <span data-ttu-id="1d510-213">[HoloLens](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) geliştirmesi için önerilen en güncel Visual Studio için bkz. Araçları yükleme.</span><span class="sxs-lookup"><span data-stu-id="1d510-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="1d510-214">Bir uygulamayı Visual Studio HoloLens'inize dağıtırken şu hatayı alabilirsiniz: İstenen işlem kullanıcıyla eşlenmiş bölümü açık olan **bir dosyada gerçekleştirilamaz. (HRESULT özel durumu: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="1d510-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="1d510-215">Bu durumda, yeniden deneyin ve dağıtımınız genel olarak başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="1d510-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="1d510-216">API</span><span class="sxs-lookup"><span data-stu-id="1d510-216">API</span></span>

- <span data-ttu-id="1d510-217">Uygulama kullanıcının odak noktasını [veya](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) camera.forward için normali ayarlarsa, hologramlar fotoğraf veya videolarda Karma Gerçeklik Yakalama görünmez.</span><span class="sxs-lookup"><span data-stu-id="1d510-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="1d510-218">Bu hata Windows'da düzeltene kadar, [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) uygulamalar odak noktasını etkin bir şekilde ayarlasalar, düzlemin normalin kamera ileri doğru (örneğin, normal = -camera.forward) tersini ayarlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1d510-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="1d510-219">Xbox Kablosuz Denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="1d510-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="1d510-220">HoloLens ile kullanılamadan önce Xbox Kablosuz Denetleyici S'nin güncelleştirilmiş olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="1d510-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="1d510-221">Denetleyicinizi [HoloLens ile](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) eşleştirmeye çalışmadan önce güncel olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="1d510-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="1d510-222">Xbox Kablosuz Denetleyicisi bağlıyken HoloLens'inizi yeniden başlatırsanız, denetleyici HoloLens'e otomatik olarak yeniden bağlanmaz.</span><span class="sxs-lookup"><span data-stu-id="1d510-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="1d510-223">Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatana kadar yavaş yanıp sönecek.</span><span class="sxs-lookup"><span data-stu-id="1d510-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="1d510-224">Denetleyicinizi hemen yeniden bağlanmak için, ışık kapatana kadar Kılavuz düğmesini basılı tutarak denetleyiciyi kapatın.</span><span class="sxs-lookup"><span data-stu-id="1d510-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="1d510-225">Denetleyiciniz yeniden bağlandığında HoloLens'e yeniden bağlanır.</span><span class="sxs-lookup"><span data-stu-id="1d510-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="1d510-226">Xbox Kablosuz Denetleyicisi bağlıyken HoloLens'iniz bekleme moduna girerse, denetleyicide herhangi bir giriş HoloLens'i uyandıracak.</span><span class="sxs-lookup"><span data-stu-id="1d510-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="1d510-227">Kullanımınız bittiğinde denetleyicinizi kapatarak bunu önleyabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1d510-227">You can prevent this by powering off your controller when you are done using it.</span></span>

