---
title: HoloLens BitLocker Şifrelemesi
description: Karma gerçeklik cihazlarınıza depolanmış dosyaları korumak için BitLocker cihaz HoloLens etkinleştirmeyi öğrenin.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635254"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="e8688-103">HoloLens (1. Nesil) BitLocker Şifrelemesi</span><span class="sxs-lookup"><span data-stu-id="e8688-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="e8688-104">HoloLens (1. nesil) ve HoloLens 2' nin her ikisi de BitLocker kullanarak cihaz şifrelemeyi destekler, ancak BitLocker her zaman HoloLens 2'de etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="e8688-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="e8688-105">Bu makale, BitLocker'ı HoloLens (1. nesil) etkinleştirmenizi ve yönetmenizi sağlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="e8688-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="e8688-106">Bu HoloLens (1. nesil) BitLocker cihaz şifrelemeyi el ile veya mobil cihaz yönetimi (MDM) kullanarak etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="e8688-107">Dosyalarda depolanan dosyaları ve [bilgileri korumak için BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) cihaz şifrelemeyi etkinleştirmek için bu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e8688-107">Follow these instructions to enable [BitLocker device encryption](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="e8688-108">Cihaz şifrelemesi, BitLocker yapılandırma hizmeti sağlayıcısında (CSP) [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) yöntemine eşdeğer olan AES-CBC 128 şifreleme yöntemini kullanarak verilerinizin korunmasına yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="e8688-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="e8688-109">Doğru şifreleme anahtarına (parola gibi) sahip personel bu anahtarın şifresini çözebilir veya bir veri kurtarma işlemi gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="e8688-110">MDM kullanarak cihaz şifrelemeyi etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="e8688-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="e8688-111">Cihaz şifrelemesi gerektiren bir Cihaz Yönetimi uygulamak için Mobile Cihaz Yönetimi (MDM) sağlayıcınızı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="e8688-112">İlke [CSP'sinde güvenlik/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) ayarı, kullanmak için ilkedir.</span><span class="sxs-lookup"><span data-stu-id="e8688-112">The policy to use is the [Security/RequireDeviceEncryption setting](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="e8688-113">Microsoft Intune kullanarak cihaz şifrelemeyi etkinleştirme yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="e8688-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="e8688-114">Diğer MDM araçları için yönergeler için MDM sağlayıcınızın belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="e8688-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="e8688-115">MDM sağlayıcınız cihaz şifrelemesi için özel URI gerektiriyorsa aşağıdaki yapılandırmayı kullanın:</span><span class="sxs-lookup"><span data-stu-id="e8688-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="e8688-116">**Ad:** istediğiniz bir ad</span><span class="sxs-lookup"><span data-stu-id="e8688-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="e8688-117">**Açıklama:** isteğe bağlı</span><span class="sxs-lookup"><span data-stu-id="e8688-117">**Description**: optional</span></span>
- <span data-ttu-id="e8688-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="e8688-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="e8688-119">**Veri türü:** tamsayı</span><span class="sxs-lookup"><span data-stu-id="e8688-119">**Data type**: integer</span></span>
- <span data-ttu-id="e8688-120">**Değer:**`1`</span><span class="sxs-lookup"><span data-stu-id="e8688-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="e8688-121">Sağlama paketi kullanarak cihaz şifrelemeyi etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="e8688-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="e8688-122">Paketleri sağlama, Windows Yapılandırma Tasarımcısı aracı tarafından oluşturulan ve cihaza belirtilen yapılandırmayı uygulayan dosyalardır.</span><span class="sxs-lookup"><span data-stu-id="e8688-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="e8688-123">Windows Holographic sürümünü yükselten ve şifrelemeyi sağlayan bir sağlama paketi oluşturma</span><span class="sxs-lookup"><span data-stu-id="e8688-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="e8688-124">Uygulama için bir sağlama HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e8688-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="e8688-125">Çalışma zamanı **ayarları**  >  **İlkeler**  >  **Güvenliği'ne** gidin ve **GerekliCimaCip Şifrele'yi seçin.**</span><span class="sxs-lookup"><span data-stu-id="e8688-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Cihaz şifreleme ayarının evet olarak yapılandırılması gerektir](images/device-encryption.png)

1. <span data-ttu-id="e8688-127">Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="e8688-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="e8688-128">Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasına göz atabilir ve dosyayı seçin.</span><span class="sxs-lookup"><span data-stu-id="e8688-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e8688-129">Sağlama [paketinde ek ayarları yapılandırabilirsiniz.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e8688-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="e8688-130">**Dosya** menüsünde **Kaydet**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e8688-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="e8688-131">Proje dosyalarının hassas bilgiler içerenin açık olduğu uyarıyı okuyun ve Tamam'a **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e8688-132">Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir.</span><span class="sxs-lookup"><span data-stu-id="e8688-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="e8688-133">.ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez.</span><span class="sxs-lookup"><span data-stu-id="e8688-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="e8688-134">Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="e8688-135">Dışarı Aktar **menüsünde** Sağlama **paketi'ne tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="e8688-136">**Sahip'i** **IT Yöneticisi** olarak değiştirerek bu sağlama paketinin önceliğe diğer kaynaklardan bu cihaza uygulanan paket sağlamadan daha yüksek bir öncelik ayarlayın ve ardından Sonraki'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="e8688-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="e8688-137">Paket Sürümü için **bir değer ayarlayın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8688-138">Mevcut paketlerde değişiklik yapabilirsiniz ve sürüm numarasını, daha önce uygulanan paketleri güncelleştirmek için değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="e8688-139">Sağlama **paketi için güvenlik ayrıntılarını seçin'de, Sonraki**'ye **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="e8688-140">Hazır **olduktan** sonra sağlama paketinin gitmelerini istediğiniz çıkış konumunu belirtmek için Sonraki'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e8688-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="e8688-141">Varsayılan olarak, Windows ICD proje klasörünü çıkış konumu olarak kullanır.</span><span class="sxs-lookup"><span data-stu-id="e8688-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="e8688-142">İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için Gözat'a tıkabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="e8688-143">**İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e8688-143">Click **Next**.</span></span>
1. <span data-ttu-id="e8688-144">Paketi **derlemeye** başlamak için Derleme'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="e8688-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="e8688-145">Proje bilgileri derleme sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e8688-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="e8688-146">Derleme tamamlandığında Son'a **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="e8688-147">Sağlama paketini HoloLens</span><span class="sxs-lookup"><span data-stu-id="e8688-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="e8688-148">Bağlan USB aracılığıyla bir bilgisayara bağlayın ve cihazı başlatın, ancak ilk  kurulum deneyiminin sığdırma sayfasını (mavi kutuyla ilk sayfa) devam edin.</span><span class="sxs-lookup"><span data-stu-id="e8688-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="e8688-149">Volume Down ve Power düğmelerine **aynı anda kısa** bir süre **basın** ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="e8688-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="e8688-150">HoloLens, bilgisayar üzerinde bir Dosya Gezgini olarak gösterir.</span><span class="sxs-lookup"><span data-stu-id="e8688-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="e8688-151">Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.</span><span class="sxs-lookup"><span data-stu-id="e8688-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="e8688-152">Sığdırma sayfasındayken Ses **Düzeyi Kapalı ve** Güç **düğmelerine** tekrar kısa bir süre basın **ve bırakın.**</span><span class="sxs-lookup"><span data-stu-id="e8688-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="e8688-153">Cihaz, pakete güvenebilir ve uygulamak mı isteyebilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="e8688-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="e8688-154">Pakete güvenen bir onaylayın.</span><span class="sxs-lookup"><span data-stu-id="e8688-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="e8688-155">Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="e8688-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="e8688-156">Başarısız olursa, paketinizi düzeltebilir ve yeniden sınabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e8688-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="e8688-157">Başarılı olursa cihaz kurulumuna devam edin.</span><span class="sxs-lookup"><span data-stu-id="e8688-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="e8688-158">Cihaz Ağustos 2016'dan önce satın alındı ise cihazda Microsoft hesabı ile oturum açmanız, en son işletim sistemi güncelleştirmesini almanız ve sağlama paketini uygulamak için işletim sistemi sıfırlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e8688-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="e8688-159">Cihaz şifrelemeyi doğrulama</span><span class="sxs-lookup"><span data-stu-id="e8688-159">Verify device encryption</span></span>

<span data-ttu-id="e8688-160">Şifreleme, veri HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e8688-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="e8688-161">Cihaz şifreleme durumunu doğrulamak için:</span><span class="sxs-lookup"><span data-stu-id="e8688-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="e8688-162">Bu HoloLens Sistem **Hakkında'Ayarlar**  >    >  **gidin.**</span><span class="sxs-lookup"><span data-stu-id="e8688-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="e8688-163">Cihaz **şifrelenirse** **BitLocker** etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="e8688-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![BitLocker'ın etkin olduğunu gösteren ekran hakkında](images/about-encryption.png)
