---
title: Windows Holographic for Business kilidini açma
description: Yeni sürüme Windows Holographic for Business, HoloLens iş için tasarlanmış ek özellikler sağlar.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379052"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="78bff-103">Windows Holographic for Business kilidini açma</span><span class="sxs-lookup"><span data-stu-id="78bff-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78bff-104">Bu sayfa yalnızca HoloLens 1. Nesil için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="78bff-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="78bff-105">Microsoft HoloLens, Windows Holographic (HoloLens için tasarlanmış bir Windows 10 sürümü) ve iş için tasarlanmış ek özellikler sağlayan [Commercial Suite'te](hololens-commercial-features.md)çalışan Development *Edition'da* kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="78bff-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="78bff-106">Commercial Suite'i satın aldığınız zaman, Windows Holographic'i sanal Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="78bff-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="78bff-107">Bu lisansı, kuruluşun mobil cihaz yönetimi [(MDM)](#edition-upgrade-by-using-mdm) sağlayıcısını veya sağlama paketini kullanarak [cihaza uygulayabilirsiniz.](#edition-upgrade-by-using-a-provisioning-package)</span><span class="sxs-lookup"><span data-stu-id="78bff-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="78bff-108">Sürüm Windows 10 1803'te Ayarlar Sistemi'ne bakarak HoloLens'in iş sürümüne yükseltildikten sonra bunu **kontrol**  >  **edebilirsiniz.**</span><span class="sxs-lookup"><span data-stu-id="78bff-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="78bff-109">MDM kullanarak sürüm yükseltme</span><span class="sxs-lookup"><span data-stu-id="78bff-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="78bff-110">Kurumsal lisans, WindowsLicensing yapılandırma hizmet [sağlayıcısını (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)destekleyen herhangi bir MDM sağlayıcısı tarafından uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="78bff-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="78bff-111">Microsoft MDM API'sini en son sürümü WindowsLicensing CSP'yi destekleyecektir.</span><span class="sxs-lookup"><span data-stu-id="78bff-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="78bff-112">Microsoft Intune kullanarak HoloLens'i yükseltmeye ilişkin adım adım yönergeler için bkz. [Windows Holographic](https://docs.microsoft.com/intune/holographic-upgrade)çalıştıran cihazları Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="78bff-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="78bff-113">Diğer MDM sağlayıcılarda, ilkeyi ayarlamaya ve dağıtmaya yönelik belirli adımlar farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="78bff-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="78bff-114">Sağlama paketi kullanarak sürüm yükseltmesi</span><span class="sxs-lookup"><span data-stu-id="78bff-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="78bff-115">Paket sağlama, Windows Yapılandırma Tasarımcısı aracı tarafından oluşturulan ve bir cihaza belirtilen yapılandırmayı uygulayan dosyalardır.</span><span class="sxs-lookup"><span data-stu-id="78bff-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="78bff-116">Windows Holographic sürümünü yükselten bir sağlama paketi oluşturma</span><span class="sxs-lookup"><span data-stu-id="78bff-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="78bff-117">HoloLens için bir sağlama paketi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="78bff-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="78bff-118">Çalışma zamanı **ayarları**  >  **EditionUpgrade'a gidin** ve **EditionUpgradeWithLicense öğesini seçin.**</span><span class="sxs-lookup"><span data-stu-id="78bff-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Sürümü lisans ayarı seçili olarak yükseltin](images/icd1.png)

1. <span data-ttu-id="78bff-120">Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="78bff-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78bff-121">Sağlama [paketinde ek ayarları yapılandırabilirsiniz.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="78bff-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="78bff-122">**Dosya** menüsünde **Kaydet**’i seçin.</span><span class="sxs-lookup"><span data-stu-id="78bff-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="78bff-123">Proje dosyalarının hassas bilgiler içerene ilişkin uyarıyı okuyun ve Tamam'a **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="78bff-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="78bff-124">Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir.</span><span class="sxs-lookup"><span data-stu-id="78bff-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="78bff-125">.ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez.</span><span class="sxs-lookup"><span data-stu-id="78bff-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="78bff-126">Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78bff-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="78bff-127">Dışarı Aktar **menüsünde** Sağlama **paketi'ne tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="78bff-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="78bff-128">**Sahip'i** **IT Yöneticisi** olarak değiştirerek bu sağlama paketinin öncelisini bu cihaza farklı kaynaklardan uygulanan diğer kaynaklardan daha yüksek olacak şekilde ayarlar ve ardından Sonraki'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="78bff-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="78bff-129">Paket Sürümü için **bir değer ayarlayın.**</span><span class="sxs-lookup"><span data-stu-id="78bff-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="78bff-130">Mevcut paketlerde değişiklik yapabilirsiniz ve sürüm numarasını, daha önce uygulanan paketleri güncelleştirmek için değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78bff-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="78bff-131">Sağlama **paketi için güvenlik ayrıntılarını seçin'de, Sonraki'yi** **seçin.**</span><span class="sxs-lookup"><span data-stu-id="78bff-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="78bff-132">Hazır **olduktan** sonra sağlama paketinin gitmelerini istediğiniz çıkış konumunu belirtmek için Sonraki'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="78bff-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="78bff-133">Varsayılan olarak, Windows ICD proje klasörünü çıkış konumu olarak kullanır.</span><span class="sxs-lookup"><span data-stu-id="78bff-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="78bff-134">İsteğe bağlı olarak, varsayılan çıkış **konumunu** değiştirmek için Gözat'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="78bff-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="78bff-135">**İleri**’yi seçin.</span><span class="sxs-lookup"><span data-stu-id="78bff-135">Select **Next**.</span></span>

1. <span data-ttu-id="78bff-136">Paketi **derlemeye** başlamak için Derleme'yi seçin.</span><span class="sxs-lookup"><span data-stu-id="78bff-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="78bff-137">Derleme sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="78bff-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="78bff-138">Derleme tamamlandığında Son'a **seçin.**</span><span class="sxs-lookup"><span data-stu-id="78bff-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="78bff-139">Sağlama paketini HoloLens'e uygulama</span><span class="sxs-lookup"><span data-stu-id="78bff-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="78bff-140">USB kablosunu kullanarak cihazı bir bilgisayara bağlayın.</span><span class="sxs-lookup"><span data-stu-id="78bff-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="78bff-141">Cihazı başlatın, ancak ilk kurulum deneyiminin **sığdırma** sayfasını (mavi kutuyla ilk sayfa) devam edin.</span><span class="sxs-lookup"><span data-stu-id="78bff-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="78bff-142">HoloLens, bilgisayarınızda cihaz olarak Dosya Gezgini.</span><span class="sxs-lookup"><span data-stu-id="78bff-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78bff-143">HoloLens cihazı Windows 10, sürüm 1607 veya önceki bir sürümde çalışıyorsa, cihazda Volume **Down** ve **Power** düğmelerine kısa bir süre basarak ve bırakarak Dosya Gezgini'i açın.</span><span class="sxs-lookup"><span data-stu-id="78bff-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="78bff-144">Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.</span><span class="sxs-lookup"><span data-stu-id="78bff-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="78bff-145">HoloLens hala uygun **sayfadayken,** kısa bir süre için Volume Down ve **Power** **düğmelerine tekrar** basın ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="78bff-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="78bff-146">HoloLens, pakete güvenmiyorsanız ve bunu uygulamak mı?</span><span class="sxs-lookup"><span data-stu-id="78bff-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="78bff-147">Pakete güvenen bir onaylayın.</span><span class="sxs-lookup"><span data-stu-id="78bff-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="78bff-148">Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="78bff-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="78bff-149">Başarıyla uygulanmadı ise, paketinizi düzeltebilir ve yeniden sınabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78bff-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="78bff-150">Başarılı olursa, cihaz kurulumuna devam edin.</span><span class="sxs-lookup"><span data-stu-id="78bff-150">If successful, proceed with device setup.</span></span>
