---
title: Enterprise MAC HoloLens kısıtlı Wi-Fi Ortamında Wi-Fi kaydı
description: HoloLens 2 cihazlardaki ağ için MAC adresi
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
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639446"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="cca5a-103">Enterprise MAC HoloLens kısıtlı Wi-Fi Ortamında Wi-Fi kaydı</span><span class="sxs-lookup"><span data-stu-id="cca5a-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="cca5a-104">Bu belgede, müşterinin ortamlarında, ağ iletişimin MAC adresleriyle Wi-Fi veya Kablosuz ağlara katılmak için sertifikaların gerekli olduğu yaygın bir senaryo açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="cca5a-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="cca5a-105">Örnek Senaryo</span><span class="sxs-lookup"><span data-stu-id="cca5a-105">Example Scenario</span></span>

<span data-ttu-id="cca5a-106">Güvenli ortamlardaki birçok müşteri, Kablosuz veya kablolu ağlarında yalnızca onaylanan cihazların (MAC Adreslerine göre) başarıyla bağlanmasına izin verecek kısıtlamalara sahiptir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="cca5a-107">Bu, Bir Kablosuz Erişim Noktası'nın MAC Adresi filtrelemesi yoluyla veya bir DHCP sunucusu aracılığıyla zorlanan bir durum olabilir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="cca5a-108">Ayrıca, bazı Kablosuz ağlar PEAP ile korunarak Kablosuz ağ kimlik doğrulamadan önce cihaza bir sertifikanın uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="cca5a-109">Bu senaryoda, iki temel gereksinimler gecikmelere neden olabilir veya cihazların ağa HoloLens el ile müdahale gerektirmektedir:</span><span class="sxs-lookup"><span data-stu-id="cca5a-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="cca5a-110">Kablosuz PEAP sertifikası, cihazın kablosuz ağa başarıyla katılmadan önce cihaza uygulanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="cca5a-111">HoloLens Wi-Fi mac adresi kayıtlı olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="cca5a-112">Yukarıdaki gereksinimlerle ilgili temel zorluklar:</span><span class="sxs-lookup"><span data-stu-id="cca5a-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="cca5a-113">MAC Adresi şu anda yalnızca cihaz Ayarlar veya başarılı bir kayıttan sonra Intune'dan belirleniyor.</span><span class="sxs-lookup"><span data-stu-id="cca5a-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="cca5a-114">MAC adresi olmadan cihaz kayıt işleminin başlaması için Wi-Fi Ağına katamaz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="cca5a-115">Bu zorluklara el ile geçici çözümler için teknisyenin cihazla etkileşim kurması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="cca5a-116">Çözümler</span><span class="sxs-lookup"><span data-stu-id="cca5a-116">Solutions</span></span>

<span data-ttu-id="cca5a-117">Ortamdaki altyapıya bağlı olarak bu durumu geliştirmenin birçok yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="cca5a-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="cca5a-118">Çözüm</span><span class="sxs-lookup"><span data-stu-id="cca5a-118">Solution</span></span> | <span data-ttu-id="cca5a-119">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="cca5a-119">Benefits</span></span> | <span data-ttu-id="cca5a-120">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cca5a-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="cca5a-121">Ethernet Adaptor ile Paket Sağlama</span><span class="sxs-lookup"><span data-stu-id="cca5a-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="cca5a-122">OOBE deneyimini iyiler ve daha hızlı bir teknisyen deneyimi sağlar.</span><span class="sxs-lookup"><span data-stu-id="cca5a-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="cca5a-123">HoloLens UYUMLU USB-C Hub + Ethernet uyarıcısı, teknisyenin YINE DE MAC yakalama ve OOBE son haline için cihazla etkileşim kurması gerekir</span><span class="sxs-lookup"><span data-stu-id="cca5a-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="cca5a-124">Ethernet üzerinden Intune Kaydı ile Autopilot</span><span class="sxs-lookup"><span data-stu-id="cca5a-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="cca5a-125">Bu tek adımlı bir bağlantıdır ve cihazın müşteri ortamına kaydıdır.</span><span class="sxs-lookup"><span data-stu-id="cca5a-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="cca5a-126">MAC yakalama, cihazla etkileşim kurmak zorunda kalmadan tamamlanır</span><span class="sxs-lookup"><span data-stu-id="cca5a-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="cca5a-127">Müşteri AAD kiracısı ve uyumlu bir USB-C Ethernet HoloLens intune etkinleştirildi</span><span class="sxs-lookup"><span data-stu-id="cca5a-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="cca5a-128">MAC Adreslerinin otomatik raporlaması</span><span class="sxs-lookup"><span data-stu-id="cca5a-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="cca5a-129">Cihazlar Intune kiracısına kaydediken, bir betik MAC adresini teknisyene bildirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="cca5a-130">Intune PowerShell cmdlet'leri</span><span class="sxs-lookup"><span data-stu-id="cca5a-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="cca5a-131">Ethernet Adaptor ile Paket Sağlama</span><span class="sxs-lookup"><span data-stu-id="cca5a-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="cca5a-132">Kablolu ağ da MAC kısıtlamalarına tabi ise, USB-C Hub + Ethernet bağdaştırıcısının MAC adresinin de önceden onaylanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="cca5a-133">Diğer cihazlardan ağa erişime izin verecek şekilde bu bağdaştırıcıyla dikkat edin.</span><span class="sxs-lookup"><span data-stu-id="cca5a-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="cca5a-134">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cca5a-134">Requirements</span></span>

- <span data-ttu-id="cca5a-135">Müşteri ağına erişimi olan kablolu ağ bağlantı noktası</span><span class="sxs-lookup"><span data-stu-id="cca5a-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="cca5a-136">HoloLens Ethernet bağdaştırıcısı ile uyumlu USB-C Hub — Ek sürücü veya uygulama yüklemesi gerektirmeyen tüm bağdaştırıcılar uygun olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cca5a-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="cca5a-137">Şunları içeren Sağlama Paketi:</span><span class="sxs-lookup"><span data-stu-id="cca5a-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="cca5a-138">Kablosuz Ağ bilgilerini ve Sertifikayı İçeren</span><span class="sxs-lookup"><span data-stu-id="cca5a-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="cca5a-139">İsteğe bağlı olarak kuruluşun Azure AD'si için kayıt bilgilerini içerir</span><span class="sxs-lookup"><span data-stu-id="cca5a-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="cca5a-140">Gerekli diğer sağlama ayarlarını içeren</span><span class="sxs-lookup"><span data-stu-id="cca5a-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="cca5a-141">İşleme</span><span class="sxs-lookup"><span data-stu-id="cca5a-141">Process</span></span>

<span data-ttu-id="cca5a-142">İşlem, cihazın yazılım düzeyine bağlı olarak değişebilir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="cca5a-143">Cihazda Mayıs [2004 güncelleştirmesi varsa](hololens-release-notes.md#windows-holographic-version-2004)aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="cca5a-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="cca5a-144">Sağlama paketini USB çubuğu köküne yer ve Hub'a takın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="cca5a-145">Bağlan Hub + Ethernet bağdaştırıcısına Ethernet kablosu.</span><span class="sxs-lookup"><span data-stu-id="cca5a-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="cca5a-146">Bağlan Usb-C Hub'HoloLens cihaz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="cca5a-147">Cihazı HoloLens cihazı açın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="cca5a-148">Sağlama **Paketini uygulamak için Birim Kapalı ve** Güç düğmesine basın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="cca5a-149">Teknisyen artık OOBE'yi takip eder ve tamamlandığında cihazın MAC Adresini almak Ayarlar App'i açabilir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="cca5a-150">Cihazın Mayıs [2004](hololens-release-notes.md#windows-holographic-version-2004)güncelleştirmesi öncesinde bir işletim sistemi derlemesi varsa aşağıdaki adımları izleyin.</span><span class="sxs-lookup"><span data-stu-id="cca5a-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="cca5a-151">Cihazı açın HoloLens bilgisayara takın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="cca5a-152">Cihaz, pc'de bir dosya depolama cihazı olarak göster gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="cca5a-153">Sağlama Paketini Cihaza Kopyalama</span><span class="sxs-lookup"><span data-stu-id="cca5a-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="cca5a-154">Bağlan Hub'a Ethernet kablosu.</span><span class="sxs-lookup"><span data-stu-id="cca5a-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="cca5a-155">Bağlan Usb-C Hub'HoloLens cihaz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="cca5a-156">İlkeyi HoloLens</span><span class="sxs-lookup"><span data-stu-id="cca5a-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="cca5a-157">Sağlama **Paketini uygulamak için Birim** Kapalı ve Güç düğmesine basın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="cca5a-158">Teknisyen artık OOBE'yi takip eder ve tamamlandığında cihazın MAC Adresini almak Ayarlar App'i açabilir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="cca5a-159">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="cca5a-159">Benefits</span></span>

<span data-ttu-id="cca5a-160">Bu, doğru sağlama paketini uygulamak ve cihazın MAC adresini toplamak için cihazın "Tek dokunmasına" olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="cca5a-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="cca5a-161">Sağlama paketleri buradaki kılavuzdan sonra oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="cca5a-162">Intune Kaydı ile Autopilot</span><span class="sxs-lookup"><span data-stu-id="cca5a-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="cca5a-163">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cca5a-163">Requirements</span></span>

- <span data-ttu-id="cca5a-164">Müşteri ağına erişimi olan kablolu ağ bağlantı noktası</span><span class="sxs-lookup"><span data-stu-id="cca5a-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="cca5a-165">HoloLens Holographic 2004 Windows çalıştıran cihazlar</span><span class="sxs-lookup"><span data-stu-id="cca5a-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="cca5a-166">HoloLens Uyumlu USB-C Ethernet bağdaştırıcısı</span><span class="sxs-lookup"><span data-stu-id="cca5a-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="cca5a-167">Intune müşteri Kiracısı için ayarlanmış ve etkinleştirilmiştir</span><span class="sxs-lookup"><span data-stu-id="cca5a-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="cca5a-168">Autopilot için kaydedilen ve Müşteri Kiracısına aktarılan cihaz</span><span class="sxs-lookup"><span data-stu-id="cca5a-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="cca5a-169">Cihaz için tanımlanan Intune İlkeleri:</span><span class="sxs-lookup"><span data-stu-id="cca5a-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="cca5a-170">Kablosuz Ağ bilgilerini ve Sertifikayı İçeren</span><span class="sxs-lookup"><span data-stu-id="cca5a-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="cca5a-171">Gerekli diğer sağlama ayarlarını içeren</span><span class="sxs-lookup"><span data-stu-id="cca5a-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="cca5a-172">Bu, gelişmiş ağ gereksinimlerine sahip bir müşterinin cihazları el ile ve ölçeklenebilir bir yaklaşımla kaydetmesine olanak tanır</span><span class="sxs-lookup"><span data-stu-id="cca5a-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="cca5a-173">Aşağıdaki gibi ek önkullar gerekir:</span><span class="sxs-lookup"><span data-stu-id="cca5a-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="cca5a-174">[Autopilot önizlemesi için Kiracıyı etkinleştirin.](hololens2-autopilot.md)</span><span class="sxs-lookup"><span data-stu-id="cca5a-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="cca5a-175">Intune'HoloLens Sağlama Paketi'nin yerini alacak yeni ilkeler oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cca5a-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="cca5a-176">Intune İlkeleri HoloLens oluşturma.</span><span class="sxs-lookup"><span data-stu-id="cca5a-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="cca5a-177">Cihazları doğru gruba attayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="cca5a-178">İşleme</span><span class="sxs-lookup"><span data-stu-id="cca5a-178">Process</span></span>

1. <span data-ttu-id="cca5a-179">Bağlan ethernet kablosunu bağdaştırıcıya takın ve bağdaştırıcıyı 2 cihazında USB-C bağlantı noktasına HoloLens takın.</span><span class="sxs-lookup"><span data-stu-id="cca5a-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="cca5a-180">İlkeyi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cca5a-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="cca5a-181">Cihazın Ethernet uyarıcısı aracılığıyla OOBE sırasında otomatik olarak İnternet'e bağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="cca5a-182">Autopilot yapılandırmasını algılaması ve Azure AD ile Intune'a otomatik olarak kaydolması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="cca5a-183">Cihaz gerekli sertifikaları ve Wi-Fi Intune aracılığıyla diğer yapılandırmaları uygulayacak.</span><span class="sxs-lookup"><span data-stu-id="cca5a-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="cca5a-184">Tamamlandığında, teknisyen Intune (Endpoint Manager) Portalı'> Cihazlar **-> DeviceName -> Donanım)** sayfasından Intune (Endpoint Manager) Portalını yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cca5a-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="cca5a-185">Mac Wi-Fi adresi, Intune Portalı'nın içinde görünür.</span><span class="sxs-lookup"><span data-stu-id="cca5a-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Intune aracılığıyla MAC Adresi](images/mac-address-intune.jpg)

7. <span data-ttu-id="cca5a-187">Teknisyen bu MAC adresini izin verilen bir cihaz olarak ekler.</span><span class="sxs-lookup"><span data-stu-id="cca5a-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="cca5a-188">Avantajlar</span><span class="sxs-lookup"><span data-stu-id="cca5a-188">Benefits</span></span>

<span data-ttu-id="cca5a-189">Bu, teknisyenin cihazı takmasına veya cihaz ortamıyla el ile etkileşim kurmasına gerek kalmadan cihazın kutudan Azure AD'ye ve Intune'a kaydolmasına olanak sağlayan bir "Tura" dağıtım deneyimi HoloLens sağlar.</span><span class="sxs-lookup"><span data-stu-id="cca5a-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="cca5a-190">MAC adreslerini Teknisyene bildirme</span><span class="sxs-lookup"><span data-stu-id="cca5a-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="cca5a-191">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cca5a-191">Requirements</span></span>

- <span data-ttu-id="cca5a-192">Müşteri Kiracısına karşı "Intune Graph PowerShell" yetkilendirmesi</span><span class="sxs-lookup"><span data-stu-id="cca5a-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="cca5a-193">Teknisyenler makinesine Intune Graph PowerShell yüklemesi.</span><span class="sxs-lookup"><span data-stu-id="cca5a-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="cca5a-194">Intune'daki "Yönetilen Cihazlar" öğelerine okuma erişimi.</span><span class="sxs-lookup"><span data-stu-id="cca5a-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="cca5a-195">(Yardım Masası Operatörü veya üstü ya da özel bir rol)</span><span class="sxs-lookup"><span data-stu-id="cca5a-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="cca5a-196">Şu anda, Intune'da yeni bir cihazın kaydına bağlı olarak otomasyon komutunu tetiklemenin "basit" bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="cca5a-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="cca5a-197">Bu nedenle, bu komut teknisyene portalda oturum açmak ve el ile almak zorunda kalmadan MAC adresini almak için basit bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="cca5a-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="cca5a-198">Bu, son 30 gün içinde HoloLens cihazların adını ve MAC adresini geri verir.</span><span class="sxs-lookup"><span data-stu-id="cca5a-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![PowerShell aracılığıyla MAC Adresi](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="cca5a-200">İşleme</span><span class="sxs-lookup"><span data-stu-id="cca5a-200">Process</span></span>

<span data-ttu-id="cca5a-201">Intune kaydı tamamlandıktan sonra teknisyen, MAC adresini almak için yukarıdaki betiği çalıştırır.</span><span class="sxs-lookup"><span data-stu-id="cca5a-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
