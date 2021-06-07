---
title: Sertifika Yöneticisi
description: HoloLens 2 karma gerçeklik cihazlarındaki sertifikaları el ile yüklemeyi, yönetmeyi ve kaldırmayı öğrenin.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378989"
---
# <a name="certificate-manager"></a><span data-ttu-id="22ed0-103">Sertifika Yöneticisi</span><span class="sxs-lookup"><span data-stu-id="22ed0-103">Certificate Manager</span></span>

- <span data-ttu-id="22ed0-104">Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama araçları.</span><span class="sxs-lookup"><span data-stu-id="22ed0-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="22ed0-105">Bu özellik, ticari ortamlarda sertifikalarınızı bir ölçekte dağıtmanıza, gidermenize ve doğrulamanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="22ed0-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="22ed0-106">Windows holographic, sürüm 20H2 ' de, HoloLens 2 Ayarlar uygulamasına bir sertifika yöneticisi ekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="22ed0-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="22ed0-107">**Ayarlar > güncelleştirme & güvenlik > sertifikaları**' na gidin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="22ed0-108">Bu özellik, cihazınızdaki sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kolay bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="22ed0-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="22ed0-109">Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için daha fazla denetim, tanılama ve doğrulama araçları geliştirmiştir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="22ed0-110">**Denetim:** Bir sertifikanın doğru şekilde dağıtıldığını doğrulama veya uygun şekilde kaldırıldığını doğrulama özelliği.</span><span class="sxs-lookup"><span data-stu-id="22ed0-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="22ed0-111">**Tanılama:** Sorun ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulamak zaman kazandırır ve sorun gidermeye yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="22ed0-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="22ed0-112">**Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğu doğrulanıyor, özellikle de daha büyük ölçekte sertifika dağıtmadan önce ticari ortamlarda önemli bir zaman kazandırabilir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="22ed0-113">Listedeki belirli bir sertifikayı hızlı bir şekilde bulmak için ada, depoya veya sona erme tarihine göre sıralama seçenekleri vardır.</span><span class="sxs-lookup"><span data-stu-id="22ed0-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="22ed0-114">Kullanıcılar ayrıca bir sertifikayı doğrudan arayabilir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="22ed0-115">Ayrı sertifika özelliklerini görüntülemek için sertifikayı seçin ve **bilgi**'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="22ed0-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="22ed0-116">Sertifika yüklemesi şu anda. cer ve. CRT dosyalarını desteklemektedir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="22ed0-117">Cihaz sahipleri, sertifikaları yerel makineye ve geçerli kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca geçerli kullanıcıya yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="22ed0-118">Kullanıcılar yalnızca doğrudan ayarlar kullanıcı arabiriminden yüklenmiş sertifikaları kaldırabilir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="22ed0-119">Bir sertifika başka yollarla yüklendiyse aynı mekanizmaya de kaldırılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="22ed0-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="22ed0-120">Bir sertifika yüklemek için:</span><span class="sxs-lookup"><span data-stu-id="22ed0-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="22ed0-121">HoloLens 2 ' 'nizi bir BILGISAYARA bağlayın.</span><span class="sxs-lookup"><span data-stu-id="22ed0-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="22ed0-122">Yüklemek istediğiniz sertifika dosyasını HoloLens 2 ' de bir konuma yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="22ed0-123">**Ayarlar uygulaması > güncelleştirme & güvenlik > sertifikaları**' na gidin ve sertifika yüklemeyi seçin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="22ed0-124">**Dosyayı Içeri aktar** ' a tıklayın ve sertifikayı kaydettiğiniz konuma gidin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="22ed0-125">**Depo konumunu** seçin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="22ed0-126">**Sertifika deposunu** seçin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="22ed0-127">**Yükle**'ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="22ed0-127">Click **Install**.</span></span>

<span data-ttu-id="22ed0-128">Sertifikanın artık cihaza yüklü olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="22ed0-129">Bir sertifikayı kaldırmak için:</span><span class="sxs-lookup"><span data-stu-id="22ed0-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="22ed0-130">MDM ile dağıtılan sertifikaları sertifika yöneticisi 'nde görüntüleyebilseniz de, bunları Sertifika Yöneticisi 'nde kaldıramazsınız.</span><span class="sxs-lookup"><span data-stu-id="22ed0-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="22ed0-131">MDM aracılığıyla kaldırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="22ed0-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="22ed0-132">**Ayarlar uygulama > güncelleştirme ve güvenlik > sertifikaları '** na gidin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="22ed0-133">Arama kutusunda Sertifikayı ada göre arayın.</span><span class="sxs-lookup"><span data-stu-id="22ed0-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="22ed0-134">Sertifikayı seçin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-134">Select the certificate.</span></span>
1. <span data-ttu-id="22ed0-135">**Kaldır** 'a tıklayın</span><span class="sxs-lookup"><span data-stu-id="22ed0-135">Click **Remove**</span></span>
1. <span data-ttu-id="22ed0-136">Onay sorulduğunda **Evet** ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="22ed0-136">Select **Yes** when prompted for confirmation.</span></span>



![Sertifikalar altındaki Ayarlar uygulamasında sertifika Görüntüleyicisi](images/certificate-viewer-device.jpg)

![Ayarlar ' da bir sertifikayı yüklemek için sertifika kullanıcı arabirimini nasıl kullanacağınızı gösteren resim.](images/certificate-device-install.jpg)
