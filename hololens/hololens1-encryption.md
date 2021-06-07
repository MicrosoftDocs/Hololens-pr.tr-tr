---
title: HoloLens BitLocker şifrelemesi
description: HoloLens karma gerçeklik cihazlarınızda depolanan dosyaları korumak için BitLocker cihaz şifrelemesini nasıl etkinleştirebileceğinizi öğrenin.
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
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378948"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="1a81c-103">HoloLens (1. Genel) BitLocker şifrelemesi</span><span class="sxs-lookup"><span data-stu-id="1a81c-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="1a81c-104">HoloLens (1. gen) ve HoloLens 2 her ikisi de BitLocker kullanılarak cihaz şifrelemesini destekler, ancak, BitLocker her zaman HoloLens 2 ' de etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="1a81c-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="1a81c-105">Bu makale, HoloLens 'te (1. Genel) BitLocker 'ı etkinleştirmenize ve yönetmenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="1a81c-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="1a81c-106">HoloLens 'te (1. Genel) BitLocker cihaz şifrelemesini el ile veya mobil cihaz yönetimi (MDM) kullanarak etkinleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="1a81c-107">Bu yönergeleri izleyerek, HoloLens 'te depolanan dosya ve bilgileri korumak için [BitLocker cihaz şifrelemesini](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="1a81c-108">Cihaz şifreleme, BitLocker yapılandırma hizmeti sağlayıcısı 'nda (CSP) [Encryptionmethodbydrivetype yöntemi 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ile eşdeğer olan AES-CBC 128 şifreleme yöntemini kullanarak verilerinizi korumanıza yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="1a81c-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="1a81c-109">Doğru şifreleme anahtarına (parola gibi) sahip personel, şifresini çözebilir veya bir veri kurtarma işlemi gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="1a81c-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="1a81c-110">MDM kullanarak cihaz şifrelemesini etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="1a81c-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="1a81c-111">Cihaz şifrelemesi gerektiren bir ilkeyi uygulamak için mobil cihaz yönetimi (MDM) sağlayıcınızı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="1a81c-112">Kullanılacak ilke, Ilke CSP 'deki [güvenlik/RequireDeviceEncryption ayarıdır](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) .</span><span class="sxs-lookup"><span data-stu-id="1a81c-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="1a81c-113">Microsoft Intune kullanarak cihaz şifrelemesini etkinleştirme yönergelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="1a81c-114">Diğer MDM araçları için, yönergeler için MDM sağlayıcınızın belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="1a81c-115">MDM sağlayıcınız cihaz şifreleme için özel URI gerektiriyorsa, aşağıdaki yapılandırmayı kullanın:</span><span class="sxs-lookup"><span data-stu-id="1a81c-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="1a81c-116">**Ad**: seçtiğiniz bir ad</span><span class="sxs-lookup"><span data-stu-id="1a81c-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="1a81c-117">**Açıklama**: isteğe bağlı</span><span class="sxs-lookup"><span data-stu-id="1a81c-117">**Description**: optional</span></span>
- <span data-ttu-id="1a81c-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="1a81c-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="1a81c-119">**Veri türü**: tamsayı</span><span class="sxs-lookup"><span data-stu-id="1a81c-119">**Data type**: integer</span></span>
- <span data-ttu-id="1a81c-120">**Değer**: `1`</span><span class="sxs-lookup"><span data-stu-id="1a81c-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="1a81c-121">Sağlama paketini kullanarak cihaz şifrelemesini etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="1a81c-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="1a81c-122">Sağlama paketleri, belirli bir yapılandırmayı bir cihaza uygulayan Windows yapılandırma Tasarımcısı aracı tarafından oluşturulan dosyalardır.</span><span class="sxs-lookup"><span data-stu-id="1a81c-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="1a81c-123">Windows holographic sürümünü yükselten ve şifrelemeyi sağlayan bir sağlama paketi oluşturma</span><span class="sxs-lookup"><span data-stu-id="1a81c-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="1a81c-124">HoloLens için bir sağlama paketi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="1a81c-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="1a81c-125">**Çalışma zamanı ayarları**  >  **ilkeleri**  >  **güvenliği**' ne gidin ve **requiredeviceencryption**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Cihaz şifreleme ayarını Evet olarak yapılandırmak iste](images/device-encryption.png)

1. <span data-ttu-id="1a81c-127">Ticari paketi satın aldığınızda sağlanmış olan XML lisans dosyasını bulun.</span><span class="sxs-lookup"><span data-stu-id="1a81c-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="1a81c-128">Ticari paketi satın aldığınızda sağlanmış olan XML Lisans dosyasına gidin ve seçin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="1a81c-129">[Sağlama paketinde ek ayarlar](hololens-provisioning.md)yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="1a81c-130">**Dosya** menüsünde **Kaydet**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="1a81c-131">Proje dosyalarının hassas bilgiler içerebileceğini belirten uyarıyı okuyun ve **Tamam**' ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a81c-132">Bir sağlama paketi oluşturduğunuzda, proje dosyaları ve sağlama paketi (. ppkg) dosyasına hassas bilgileri dahil edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="1a81c-133">. Ppkg dosyasını şifreleme seçeneğiniz olsa da, proje dosyaları şifrelenmez.</span><span class="sxs-lookup"><span data-stu-id="1a81c-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="1a81c-134">Proje dosyalarını güvenli bir konumda depolamanız ve artık gerekli olmadığında proje dosyalarını silmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="1a81c-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="1a81c-135">**Dışarı aktar** menüsünde, **sağlama paketi**' ne tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="1a81c-136">Bu sağlama paketinin, diğer kaynaklardan bu cihaza uygulanan sağlama paketlerinden daha yüksek önceliği ayarlayabileceği **BT Yöneticisi** olarak **sahibini** değiştirin ve ardından **İleri**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="1a81c-137">**Paket sürümü** için bir değer ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1a81c-138">Mevcut paketlerde değişiklik yapabilir ve sürüm numarasını daha önce uygulanan paketleri güncelleştirecek şekilde değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="1a81c-139">**Sağlama paketinin güvenlik ayrıntılarını seçin** sayfasında **İleri**' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="1a81c-140">Oluşturulduktan sonra sağlama paketinin gitmesini istediğiniz çıkış konumunu belirtmek için **İleri** ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="1a81c-141">Varsayılan olarak, Windows ICD, çıkış konumu olarak proje klasörünü kullanır.</span><span class="sxs-lookup"><span data-stu-id="1a81c-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="1a81c-142">İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için, Araştır ' ı tıklatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="1a81c-143">**İleri**’ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-143">Click **Next**.</span></span>
1. <span data-ttu-id="1a81c-144">Paketi oluşturmaya başlamak için **Oluştur** ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="1a81c-145">Proje bilgileri yapı sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="1a81c-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="1a81c-146">Oluşturma tamamlandığında **son**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="1a81c-147">Hazırlama paketini HoloLens 'e Uygula</span><span class="sxs-lookup"><span data-stu-id="1a81c-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="1a81c-148">Cihazı USB ile BILGISAYARA bağlayın ve cihazı başlatın, ancak ilk Kurulum deneyiminin (mavi kutu ile ilk sayfa) durumunu aşan **bir sayfadan devam** etmez.</span><span class="sxs-lookup"><span data-stu-id="1a81c-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="1a81c-149">**Sesi** ve **Güç** düğmelerini aynı anda bir daha bas ve serbest bırakın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="1a81c-150">HoloLens, BILGISAYAR üzerinde dosya Gezgini 'nde bir cihaz olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="1a81c-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="1a81c-151">Dosya Gezgini 'nde, sağlama paketini (. ppkg) cihaz depolamasına sürükleyin ve bırakın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="1a81c-152">**Sığdır** sayfasında, **birimi aşağı** ve **Güç** düğmelerine aynı anda tekrar basın ve serbest bırakın.</span><span class="sxs-lookup"><span data-stu-id="1a81c-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="1a81c-153">Cihaza güveniyorsanız ve uygulamayı uygulamak istiyorsanız bu cihaz sizi sorar.</span><span class="sxs-lookup"><span data-stu-id="1a81c-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="1a81c-154">Pakete güvendiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="1a81c-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="1a81c-155">Paketin başarıyla uygulanıp uygulanmadığını görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="1a81c-156">Başarısız olursa paketinizi düzelleyebilir ve yeniden deneyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="1a81c-157">Başarılı olursa, cihaz kurulumuna devam edin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="1a81c-158">Cihaz 2016 Ağustos 'Tan önce satın alındıysa, Microsoft hesabı cihazda oturum açmanız, en son işletim sistemi güncelleştirmesini almanız ve ardından sağlama paketini uygulamak için işletim sistemini sıfırlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="1a81c-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="1a81c-159">Cihaz şifrelemesini doğrulama</span><span class="sxs-lookup"><span data-stu-id="1a81c-159">Verify device encryption</span></span>

<span data-ttu-id="1a81c-160">HoloLens üzerinde şifreleme sessiz.</span><span class="sxs-lookup"><span data-stu-id="1a81c-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="1a81c-161">Cihaz şifreleme durumunu doğrulamak için:</span><span class="sxs-lookup"><span data-stu-id="1a81c-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="1a81c-162">HoloLens 'te **Ayarlar**  >  **sistem**  >  **hakkında** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="1a81c-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="1a81c-163">Cihaz şifrelenirse **BitLocker** **etkinleştirilir** .</span><span class="sxs-lookup"><span data-stu-id="1a81c-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![BitLocker 'ın etkin olduğunu gösteren ekran hakkında](images/about-encryption.png)
