---
title: HoloLens'i MDM'ye kaydetme
description: Birden çok cihazın daha kolay yönetimi için HoloLens'i mobil cihaz yönetimine (MDM) kaydetmeyi öğrenin.
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379102"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="750c3-103">HoloLens'i MDM'ye kaydetme</span><span class="sxs-lookup"><span data-stu-id="750c3-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="750c3-104">birden çok Microsoft HoloLens cihazları aynı anda yönetmek için [Microsoft Intune.](https://docs.microsoft.com/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="750c3-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="750c3-105">Ayarları yönetecek, yükecek uygulamaları seçecek ve güvenlik yapılandırmalarını, kuruluş gereksinimlerine göre ayarlayabileceksiniz.</span><span class="sxs-lookup"><span data-stu-id="750c3-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="750c3-106">Bkz. [Windows Holographic](https://docs.microsoft.com/intune/windows-holographic-for-business)çalıştıran cihazları Microsoft Intune, Windows Holographic'te desteklenen yapılandırma hizmeti sağlayıcıları [(CSP'ler)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)ve [Windows Holographic for Business.](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)</span><span class="sxs-lookup"><span data-stu-id="750c3-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="750c3-107">VPN, Bitlocker ve bilgi noktası modu özellikleri de dahil olmak üzere mobil cihaz yönetimi (MDM), yalnızca [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="750c3-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="750c3-108">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="750c3-108">Requirements</span></span>

 <span data-ttu-id="750c3-109">HoloLens cihazlarını yönetmek için Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) ayarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="750c3-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="750c3-110">MDM sağlayıcınız microsoft Microsoft Intune Microsoft MDM API'lerini kullanan üçüncü taraf bir sağlayıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="750c3-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="750c3-111">Kaydetmenin farklı yolları</span><span class="sxs-lookup"><span data-stu-id="750c3-111">Different ways to enroll</span></span>

<span data-ttu-id="750c3-112">OOBE sırasında veya [oturum](hololens-identity.md) açma sonrası sırasında seçilen kimlik türüne bağlı olarak, farklı kayıt yöntemleri vardır.</span><span class="sxs-lookup"><span data-stu-id="750c3-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="750c3-113">Kimlik Azure AD ise OOBE veya Ayarlar Uygulama Erişimi **İş veya** Okul Bağlantısı  ->    ->  **düğmesi sırasında.**</span><span class="sxs-lookup"><span data-stu-id="750c3-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="750c3-114">Azure AD için, [otomatik MDM kaydı](hololens-enroll-mdm.md#auto-enrollment-in-mdm) yalnızca Azure AD kayıt URL'leri ile yapılandırılmışsa gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="750c3-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="750c3-115">Kimlik Azure AD ise ve cihaz, belirli bir yapılandırma profili atanmış intune MDM sunucusuna önceden kaydedilmişse, OOBE sırasında Azure AD-Join ve [otomatik MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) kaydı gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="750c3-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="750c3-116">Autopilot [akışı olarak da adlandırılan](hololens2-autopilot.md) Bu akış [19041.1103+derlemelerde kullanılabilir.](hololens-release-notes.md#windows-holographic-version-2004)</span><span class="sxs-lookup"><span data-stu-id="750c3-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="750c3-117">Kimlik MSA ise, Ayarlar Uygulama Erişimi **İş veya**  ->  **Okul Bağlantısı**  ->  **düğmesini** kullanın.</span><span class="sxs-lookup"><span data-stu-id="750c3-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="750c3-118">İş Hesabı Ekle (AWA) akışı olarak da adlandırılan.</span><span class="sxs-lookup"><span data-stu-id="750c3-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="750c3-119">Kimlik Yerel Kullanıcı ise, Ayarlar Uygulama Erişimi **İş veya** Okul  ->  **Kaydı'nın** yalnızca cihaz yönetimi  ->  **bağlantısında kullanın.**</span><span class="sxs-lookup"><span data-stu-id="750c3-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="750c3-120">Saf MDM kayıt akışı olarak da adlandırılan.</span><span class="sxs-lookup"><span data-stu-id="750c3-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="750c3-121">Cihaz MDM sunucunuza kaydedilenin ardından, Ayarlar uygulaması artık cihazın cihaz yönetimine kayded olduğunu yansıtacak.</span><span class="sxs-lookup"><span data-stu-id="750c3-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="750c3-122">MDM'de otomatik kayıt</span><span class="sxs-lookup"><span data-stu-id="750c3-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="750c3-123">Kurumda bir [Azure Premium](https://azure.microsoft.com/overview/)aboneliği varsa, Azure Active Directory (Azure AD) kullanıyorsa ve kimlik doğrulaması için Azure AD belirteci kabul eden bir MDM çözümü kullanıyorsa (şu anda yalnızca Microsoft Intune ve AirWatch'da de desteklemektedir), KULLANıCı Azure AD hesabıyla oturum atıktan sonra Azure AD'yi otomatik olarak MDM kaydına izin verecek şekilde yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="750c3-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="750c3-124">Azure AD kaydı yapılandırmayı öğrenin.</span><span class="sxs-lookup"><span data-stu-id="750c3-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="750c3-125">Otomatik kayıt etkinleştirildiğinde ek el ile kayıt gerekmez.</span><span class="sxs-lookup"><span data-stu-id="750c3-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="750c3-126">Kullanıcı bir Azure AD hesabıyla oturum açınca, ilk çalıştırma deneyimi tamamladıktan sonra cihaz MDM'ye kaydolacak.</span><span class="sxs-lookup"><span data-stu-id="750c3-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="750c3-127">Bir cihaz Azure AD'ye Katılmış olduğunda, cihaz sahibi olarak kabul [edilenleri etkileyebilir.](security-adminless-os.md#device-owner)</span><span class="sxs-lookup"><span data-stu-id="750c3-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="750c3-128">Intune'dan HoloLens'in kaydı</span><span class="sxs-lookup"><span data-stu-id="750c3-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="750c3-129">Kayıt yöntemine bağlı olarak, cihazınızın kaydı silinene kadar kullanılabilir olabilir.</span><span class="sxs-lookup"><span data-stu-id="750c3-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="750c3-130">Cihazınız bir Azure AD hesabına veya Autopilot'a kaydedildiyse, Intune'dan kayıttan silinamaz.</span><span class="sxs-lookup"><span data-stu-id="750c3-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="750c3-131">HoloLens'e Azure AD'den katılmayı veya Azure AD kiracılarından farklı bir kiracıya yeniden katılmayı isterseniz cihazı [sıfırlamanız/ters eğik](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) çizgiyle sıfırlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="750c3-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="750c3-132">Cihazınız iş hesabı ekli bir MSA hesabından veya yalnızca cihaz yönetimine kayıtlı bir Yerel hesaptan kayıtlı ise, cihazın kaydını sebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="750c3-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="750c3-133">Uygulamayı açın Başlat menüsü Ayarlar Uygulama Erişimi İş **veya** Okul YourAccount Bağlantısını  ->  **Kes**  ->    ->  **düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="750c3-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>