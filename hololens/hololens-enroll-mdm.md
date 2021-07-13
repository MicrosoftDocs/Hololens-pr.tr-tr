---
title: MDM'HoloLens kayıt
description: Birden çok cihazın daha HoloLens için mobil cihaz yönetimine (MDM) nasıl kayıt olduğunu öğrenin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640415"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="ba450-103">MDM'HoloLens kayıt</span><span class="sxs-lookup"><span data-stu-id="ba450-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="ba450-104">birden çok Microsoft HoloLens cihazları aynı anda yönetmek için [Microsoft Intune.](/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="ba450-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="ba450-105">Ayarları yönetecek, yükecek uygulamaları seçecek ve güvenlik yapılandırmalarını, kuruluş gereksinimlerine göre ayarlayabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="ba450-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="ba450-106">Bkz. [Microsoft Intune ile Windows Holographic](/intune/windows-holographic-for-business)çalıştıran cihazları yönetme, Windows Holographic'te desteklenen yapılandırma hizmeti sağlayıcıları [(CSP'ler)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)</span><span class="sxs-lookup"><span data-stu-id="ba450-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="ba450-107">VPN, Bitlocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM), yalnızca [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ba450-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="ba450-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="ba450-108">Requirements</span></span>

 <span data-ttu-id="ba450-109">Mobil cihazları yönetmek için, Cihaz Yönetimi mobil cihazları (MDM) HoloLens gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba450-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="ba450-110">MDM sağlayıcınız microsoft Microsoft Intune Microsoft MDM API'lerini kullanan üçüncü taraf bir sağlayıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="ba450-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="ba450-111">Kaydetmenin farklı yolları</span><span class="sxs-lookup"><span data-stu-id="ba450-111">Different ways to enroll</span></span>

<span data-ttu-id="ba450-112">OOBE sırasında veya [oturum](hololens-identity.md) açma sonrası sırasında seçilen kimlik türüne bağlı olarak, farklı kayıt yöntemleri vardır.</span><span class="sxs-lookup"><span data-stu-id="ba450-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="ba450-113">Kimlik Azure AD ise, OOBE sırasında veya uygulama **Ayarlar App** Access work  ->  **veya School**  ->  **Bağlan** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="ba450-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ba450-114">Azure AD için, [otomatik MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD kayıt URL'leri ile yapılandırılmışsa gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="ba450-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="ba450-115">Kimlik Azure AD ise ve cihaz, belirli bir yapılandırma profili atanmış intune MDM sunucusuna önceden kaydedilmişse, OOBE sırasında Azure AD-Join ve [otomatik MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) kaydı gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="ba450-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="ba450-116">Autopilot [akışı olarak da adlandırılan](hololens2-autopilot.md) Bu akış [19041.1103+derlemelerde kullanılabilir.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="ba450-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="ba450-117">Identity MSA ise, Uygulama **Erişimi Ayarlar veya Okul** Yönetimi düğmesini  ->    ->  **Bağlan** kullanın.</span><span class="sxs-lookup"><span data-stu-id="ba450-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ba450-118">İş Hesabı Ekle (AWA) akışı olarak da adlandırılan.</span><span class="sxs-lookup"><span data-stu-id="ba450-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="ba450-119">Kimlik Yerel Kullanıcı ise, Uygulama **Erişimi Ayarlar veya** Okul Kaydı'nın yalnızca cihaz yönetimi  ->    ->  **bağlantısında kaydını** kullanın.</span><span class="sxs-lookup"><span data-stu-id="ba450-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="ba450-120">Saf MDM kayıt akışı olarak da adlandırılan.</span><span class="sxs-lookup"><span data-stu-id="ba450-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="ba450-121">Cihaz MDM sunucunuza kaydedile Ayarlar uygulama artık cihazın cihaz yönetimine kayded olduğunu yansıtacak.</span><span class="sxs-lookup"><span data-stu-id="ba450-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="ba450-122">MDM'de otomatik kayıt</span><span class="sxs-lookup"><span data-stu-id="ba450-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="ba450-123">Kurumda bir [Azure Premium](https://azure.microsoft.com/overview/)aboneliği varsa, kimlik doğrulaması için bir Azure AD belirteci kabul eden bir MDM çözümü (şu anda yalnızca Microsoft Intune ve AirWatch'da desteklemektedir) Azure Active Directory (Azure AD) kullanıyorsa, IT yöneticiniz Azure AD'yi, kullanıcı Azure AD hesabıyla oturum atıktan sonra MDM kaydına otomatik olarak izin verecek şekilde yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ba450-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="ba450-124">Azure AD kaydı yapılandırmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="ba450-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="ba450-125">Otomatik kayıt etkinleştirildiğinde ek el ile kayıt gerekmez.</span><span class="sxs-lookup"><span data-stu-id="ba450-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="ba450-126">Kullanıcı bir Azure AD hesabıyla oturum açınca, ilk çalıştırma deneyimi tamamladıktan sonra cihaz MDM'ye kaydolacak.</span><span class="sxs-lookup"><span data-stu-id="ba450-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="ba450-127">Bir cihaz Azure AD'ye Katılmış olduğunda, cihaz sahibi olarak kabul [edilenleri etkileyebilir.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="ba450-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="ba450-128">Intune'HoloLens kaydı</span><span class="sxs-lookup"><span data-stu-id="ba450-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="ba450-129">Kayıt yöntemine bağlı olarak, cihazınızın kaydı silinene kadar kullanılabilir olabilir.</span><span class="sxs-lookup"><span data-stu-id="ba450-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="ba450-130">Cihazınız bir Azure AD hesabına veya Autopilot'a kaydedildiyse, Intune'dan kayıttan silinamaz.</span><span class="sxs-lookup"><span data-stu-id="ba450-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="ba450-131">Azure AD'den HoloLens veya Azure AD kiracılarından farklı bir kiracıya yeniden katılmayı isterseniz cihazı [sıfırlamanız/ters eğik](hololens-recovery.md#reset-the-device) çizgiyle sıfırlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba450-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="ba450-132">Cihazınız iş hesabı ekli bir MSA hesabından veya yalnızca cihaz yönetimine kayıtlı bir Yerel hesaptan kayıtlı ise, cihazın kaydını sebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="ba450-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="ba450-133">Uygulamayı açın Başlat menüsü App Access work **Ayarlar**  ->  **School**  ->  *YourAccount* Disconnect düğmesini  ->   seçin.</span><span class="sxs-lookup"><span data-stu-id="ba450-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>