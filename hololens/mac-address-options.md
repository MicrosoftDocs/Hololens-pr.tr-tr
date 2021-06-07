---
title: MAC adresi kısıtlanmış Wi-Fi ortamında, HoloLens cihazlarının kurumsal kaydı
description: HoloLens 2 cihazlarında ağ için MAC adresi
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380187"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="99e6c-103">MAC adresi kısıtlanmış Wi-Fi ortamında, HoloLens cihazlarının kurumsal kaydı</span><span class="sxs-lookup"><span data-stu-id="99e6c-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="99e6c-104">Bu belgede, Wi-Fi MAC adresleriyle kısıtlanmış müşteri ortamlarında belirlediğimiz ve kablosuz ağların katılması için sertifikaların gerekli olduğu ortak bir senaryo açıklanır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="99e6c-105">Örnek Senaryo</span><span class="sxs-lookup"><span data-stu-id="99e6c-105">Example Scenario</span></span>

<span data-ttu-id="99e6c-106">Güvenli ortamlarda birçok müşteri, kablosuz veya kablolu ağlarda yalnızca onaylanan cihazların (MAC adreslerine bağlı olarak) başarıyla bağlanmasına izin veren kısıtlamalara sahiptir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="99e6c-107">Bu, bir kablosuz erişim noktasında veya bir DHCP sunucusu üzerinden MAC adresi filtreleme aracılığıyla zorlanabilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="99e6c-108">Ayrıca, bazı kablosuz ağlar PEAP ile korunabilir, bu da kablosuz ağda kimlik doğrulamadan önce bir sertifikanın cihaza uygulanmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="99e6c-109">Bu senaryoda, iki temel gereksinim, HoloLens cihazlarını ağa eklerken gecikmeler verebilir veya el ile müdahale gerektirebilir:</span><span class="sxs-lookup"><span data-stu-id="99e6c-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="99e6c-110">Cihazın kablosuz ağa başarıyla katılmasını sağlamak için kablosuz PEAP sertifikasının cihaza uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="99e6c-111">HoloLens Wi-Fi bağdaştırıcısının MAC adresi kayıtlı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="99e6c-112">Yukarıdaki gereksinimlerle ilgili temel sorunlar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="99e6c-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="99e6c-113">MAC adresi şu anda yalnızca cihazdaki Ayarlar uygulamasından veya başarılı bir kayıttan sonra Intune 'dan tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="99e6c-114">MAC adresi olmadan, cihaz kayıt işlemine başlamak için Wi-Fi ağa katılamaz.</span><span class="sxs-lookup"><span data-stu-id="99e6c-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="99e6c-115">Bu güçlüklere yönelik el ile yapılan geçici çözümler, bir teknisyenin cihazla etkileşimini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="99e6c-116">Çözümler</span><span class="sxs-lookup"><span data-stu-id="99e6c-116">Solutions</span></span>

<span data-ttu-id="99e6c-117">Ortamda kullanılabilir olan altyapıya bağlı olarak bu durumu geliştirmenin birçok yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="99e6c-118">Çözüm</span><span class="sxs-lookup"><span data-stu-id="99e6c-118">Solution</span></span> | <span data-ttu-id="99e6c-119">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="99e6c-119">Benefits</span></span> | <span data-ttu-id="99e6c-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="99e6c-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="99e6c-121">Ethernet bağdaştırıcısı ile paketi sağlama</span><span class="sxs-lookup"><span data-stu-id="99e6c-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="99e6c-122">, OOBE deneyimini geliştirir ve daha hızlı bir teknisyen deneyimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="99e6c-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="99e6c-123">HoloLens uyumlu USB-C hub + Ethernet bağdaştırıcısı ve teknisyen, MAC yakalama ve OOBE sonlandırması için cihazla etkileşimde bulunmak zorunda kalır</span><span class="sxs-lookup"><span data-stu-id="99e6c-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="99e6c-124">Ethernet üzerinden Intune kaydıyla Autopilot</span><span class="sxs-lookup"><span data-stu-id="99e6c-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="99e6c-125">Bu, tek adımlı bir bağlantıdır ve cihazın müşteri ortamına kaydı olur.</span><span class="sxs-lookup"><span data-stu-id="99e6c-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="99e6c-126">MAC yakalama, cihazla etkileşime gerek kalmadan tamamlanabilir</span><span class="sxs-lookup"><span data-stu-id="99e6c-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="99e6c-127">Intune, müşteri AAD kiracısı ve bir HoloLens uyumlu USB-C Ethernet bağdaştırıcısı için etkinleştirildi</span><span class="sxs-lookup"><span data-stu-id="99e6c-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="99e6c-128">MAC adreslerinin otomatik raporlaması</span><span class="sxs-lookup"><span data-stu-id="99e6c-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="99e6c-129">Cihazlar Intune kiracısına kaydedildiğinde, bir komut dosyası MAC adresini teknisyene rapor edebilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="99e6c-130">Intune PowerShell cmdlet 'leri</span><span class="sxs-lookup"><span data-stu-id="99e6c-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="99e6c-131">Ethernet bağdaştırıcısı ile paketi sağlama</span><span class="sxs-lookup"><span data-stu-id="99e6c-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="99e6c-132">Kablolu ağ aynı zamanda MAC kısıtlamalarına tabidir, USB-C hub + Ethernet bağdaştırıcısının MAC adresinin de önceden onaylanmış olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="99e6c-133">Diğer cihazlardan ağa erişime izin verecek olduğundan, Bu bağdaştırıcıyla ilgilenmelidir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="99e6c-134">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="99e6c-134">Requirements</span></span>

- <span data-ttu-id="99e6c-135">Müşteri ağına erişimi olan kablolu ağ bağlantı noktası</span><span class="sxs-lookup"><span data-stu-id="99e6c-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="99e6c-136">Ethernet bağdaştırıcısı ile HoloLens uyumlu USB-C hub 'ı; ek sürücü veya uygulama yüklemesi gerektirmeyen herhangi bir bağdaştırıcı uygun olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="99e6c-137">Şunu içeren sağlama paketi:</span><span class="sxs-lookup"><span data-stu-id="99e6c-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="99e6c-138">Kablosuz ağ bilgilerini ve sertifikayı içeren</span><span class="sxs-lookup"><span data-stu-id="99e6c-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="99e6c-139">Kuruluşun Azure AD için kayıt bilgilerini isteğe bağlı olarak içeren</span><span class="sxs-lookup"><span data-stu-id="99e6c-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="99e6c-140">Diğer gerekli sağlama ayarlarını içeren</span><span class="sxs-lookup"><span data-stu-id="99e6c-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="99e6c-141">İşleme</span><span class="sxs-lookup"><span data-stu-id="99e6c-141">Process</span></span>

<span data-ttu-id="99e6c-142">Işlem, cihazın yazılım düzeyine bağlı olarak farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="99e6c-143">Cihazda [mayıs 2004 Güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-2004)varsa aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="99e6c-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="99e6c-144">Sağlama paketini USB Stick köküne yerleştirin ve hub 'a takın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="99e6c-145">Ethernet kablosunu hub + Ethernet bağdaştırıcısına bağlayın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="99e6c-146">USB-C hub 'ını HoloLens cihazına bağlayın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="99e6c-147">HoloLens 'i açın ve cihaza yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="99e6c-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="99e6c-148">Sağlama paketini uygulamak için **ses azaltma ve güç düğmesine** basın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="99e6c-149">Teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="99e6c-150">Cihazda [mayıs 2004 güncelleştirmesinden](hololens-release-notes.md#windows-holographic-version-2004)önce bir işletim sistemi derlemesi varsa aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="99e6c-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="99e6c-151">HoloLens 'i açın ve cihazı bir BILGISAYARA takın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="99e6c-152">Cihazın bılgısayarda bir dosya depolama cihazı olarak gösterilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="99e6c-153">Sağlama paketini cihaza Kopyala</span><span class="sxs-lookup"><span data-stu-id="99e6c-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="99e6c-154">Ethernet kablosunu hub 'a bağlayın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="99e6c-155">USB-C hub 'ını HoloLens cihazına bağlayın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="99e6c-156">HoloLens 'e yerleştir</span><span class="sxs-lookup"><span data-stu-id="99e6c-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="99e6c-157">Sağlama paketini uygulamak için **ses azaltma ve güç** düğmesine basın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="99e6c-158">Teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="99e6c-159">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="99e6c-159">Benefits</span></span>

<span data-ttu-id="99e6c-160">Bu, cihazın "tek dokunmasına" olanak sağlayarak doğru sağlama paketini uygulayabilir ve cihazın MAC adresini toplar.</span><span class="sxs-lookup"><span data-stu-id="99e6c-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="99e6c-161">Aşağıdaki kılavuzdan sonra sağlama paketleri oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="99e6c-162">Intune kaydı ile Autopilot</span><span class="sxs-lookup"><span data-stu-id="99e6c-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="99e6c-163">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="99e6c-163">Requirements</span></span>

- <span data-ttu-id="99e6c-164">Müşteri ağına erişimi olan kablolu ağ bağlantı noktası</span><span class="sxs-lookup"><span data-stu-id="99e6c-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="99e6c-165">Windows holographic 2004 çalıştıran HoloLens cihazları</span><span class="sxs-lookup"><span data-stu-id="99e6c-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="99e6c-166">HoloLens uyumlu USB-C Ethernet bağdaştırıcısı</span><span class="sxs-lookup"><span data-stu-id="99e6c-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="99e6c-167">Intune, müşteri kiracısı için ayarlanır ve etkinleştirilir</span><span class="sxs-lookup"><span data-stu-id="99e6c-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="99e6c-168">Autopilot için kaydedilmiş ve müşteri kiracısına aktarılan cihaz</span><span class="sxs-lookup"><span data-stu-id="99e6c-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="99e6c-169">Cihaz için tanımlanan Intune Ilkeleri:</span><span class="sxs-lookup"><span data-stu-id="99e6c-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="99e6c-170">Kablosuz ağ bilgilerini ve sertifikayı içeren</span><span class="sxs-lookup"><span data-stu-id="99e6c-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="99e6c-171">Diğer gerekli sağlama ayarlarını içeren</span><span class="sxs-lookup"><span data-stu-id="99e6c-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="99e6c-172">Bu, Gelişmiş ağ gereksinimlerine sahip bir müşterinin cihazları uygulamalı, ölçeklenebilir bir yaklaşımda kaydetmesine olanak sağlar</span><span class="sxs-lookup"><span data-stu-id="99e6c-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="99e6c-173">Aşağıdaki gibi ek önkoşulların olması gerekir:</span><span class="sxs-lookup"><span data-stu-id="99e6c-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="99e6c-174">[Autopilot önizlemesi Için kiracıyı etkinleştirin](https://docs.microsoft.com/hololens/hololens2-autopilot).</span><span class="sxs-lookup"><span data-stu-id="99e6c-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="99e6c-175">Intune içindeki sağlama paketini değiştirmek için HoloLens ilkeleri oluşturun.</span><span class="sxs-lookup"><span data-stu-id="99e6c-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="99e6c-176">HoloLens Intune Ilkelerini oluşturun.</span><span class="sxs-lookup"><span data-stu-id="99e6c-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="99e6c-177">Cihazları doğru gruba atayın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="99e6c-178">İşleme</span><span class="sxs-lookup"><span data-stu-id="99e6c-178">Process</span></span>

1. <span data-ttu-id="99e6c-179">Ethernet kablosunu bağdaştırıcıya bağlayın ve HoloLens 2 cihazında bağdaştırıcıyı USB-C bağlantı noktasına takın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="99e6c-180">HoloLens 'i açın.</span><span class="sxs-lookup"><span data-stu-id="99e6c-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="99e6c-181">Cihazın, Ethernet bağdaştırıcısı aracılığıyla otomatik olarak OOBE sırasında internet 'e bağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="99e6c-182">Autopilot yapılandırmasını algılar ve Azure AD ve Intune ile otomatik olarak kayıt yaptırmalıdır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="99e6c-183">Cihaz gereken Wi-Fi sertifikaları ve diğer yapılandırmaları Intune aracılığıyla uygular.</span><span class="sxs-lookup"><span data-stu-id="99e6c-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="99e6c-184">Bu, tamamlandığında, teknisyen, Intune (Endpoint Manager) portalını yükleyebilir ve **ana > cihazlar-> aygıtadı > donanımında** cihaz özellikleri sayfasına gidebilir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="99e6c-185">Wi-Fi MAC adresi Intune portalında görünür olacaktır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Intune aracılığıyla MAC adresi](images/mac-address-intune.jpg)

7. <span data-ttu-id="99e6c-187">Teknisyen, bu MAC adresini izin verilen bir cihaz olarak ekler.</span><span class="sxs-lookup"><span data-stu-id="99e6c-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="99e6c-188">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="99e6c-188">Benefits</span></span>

<span data-ttu-id="99e6c-189">Bu, teknisyen için "kafa dışı" dağıtım deneyimine, cihazın Azure AD 'ye ve Intune 'a kaydolmasına gerek olmadan veya HoloLens ortamıyla el ile etkileşimde bulunmak zorunda kalmadan Azure AD ve Intune 'a kayıtlı olmasını sağlayacak şekilde izin verir.</span><span class="sxs-lookup"><span data-stu-id="99e6c-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="99e6c-190">MAC adreslerinin teknisyene raporlaması</span><span class="sxs-lookup"><span data-stu-id="99e6c-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="99e6c-191">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="99e6c-191">Requirements</span></span>

- <span data-ttu-id="99e6c-192">Müşteri kiracısında "Intune Graph PowerShell" yetkilendirmesi</span><span class="sxs-lookup"><span data-stu-id="99e6c-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="99e6c-193">Teknisyenler makinesinde Intune Graph PowerShell 'i yükleme.</span><span class="sxs-lookup"><span data-stu-id="99e6c-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="99e6c-194">Intune 'un "yönetilen cihazlar" öğelerine okuma erişimi.</span><span class="sxs-lookup"><span data-stu-id="99e6c-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="99e6c-195">(Yardım masası Işleci veya üzeri ya da özel bir rol)</span><span class="sxs-lookup"><span data-stu-id="99e6c-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="99e6c-196">Mevcut olduğunda, yeni bir cihazın Intune içindeki kaydına bağlı olarak bir Otomasyon komutu tetiklemenin "basit" bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="99e6c-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="99e6c-197">Bu nedenle, bu komut teknisyene Portal üzerinde oturum açıp el ile almak zorunda kalmadan MAC adresini almanın basit bir yolunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="99e6c-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="99e6c-198">Bu, son 30 güne kayıtlı olan herhangi bir HoloLens cihazlarının adını ve MAC adresini döndürür.</span><span class="sxs-lookup"><span data-stu-id="99e6c-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![PowerShell aracılığıyla MAC adresi](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="99e6c-200">İşleme</span><span class="sxs-lookup"><span data-stu-id="99e6c-200">Process</span></span>

<span data-ttu-id="99e6c-201">Intune kaydı tamamlandıktan sonra teknisyen, MAC adresini almak için yukarıdaki betiği çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="99e6c-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
