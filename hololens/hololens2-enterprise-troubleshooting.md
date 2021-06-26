---
title: HoloLens 2 uygulaması ve yönetilen cihaz sorunlarını giderme
description: Enterprise ortamında HoloLens 2 cihazlarının sorunlarını giderme
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: sorun giderme
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961647"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="bc0e4-104">Uygulama ve yönetilen cihaz sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="bc0e4-105">Bu makalede HoloLens 2'nin uygulanması ve yönetimiyle ilgili çeşitli sorunların nasıl çözülecek veya soruların nasıl yanıtlandır soruları açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bc0e4-106">Herhangi bir sorun giderme yordamına başlamadan önce, mümkünse cihazınızın pil kapasitesinin yüzde **20-40'ını** ücrete tabi olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="bc0e4-107">Güç [düğmesinin altında](hololens2-setup.md#lights-that-indicate-the-battery-level) bulunan pil göstergesi ışığı, cihazda oturum açmadan pil kapasitesini doğrulamanın hızlı bir yolu olabilir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="bc0e4-108">EAP Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="bc0e4-109">Wi-Fi Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="bc0e4-110">Ağ Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="bc0e4-111">Daha önce kurulumu yapılan HoloLens cihazında oturum açma işlemi tamamlanmıyor</span><span class="sxs-lookup"><span data-stu-id="bc0e4-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="bc0e4-112">Windows Holographic 21H1'e güncelleştirdikten sonra oturum açılam</span><span class="sxs-lookup"><span data-stu-id="bc0e4-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="bc0e4-113">Autopilot Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="bc0e4-114">Yönetilen HoloLens Cihazları hakkında SSS</span><span class="sxs-lookup"><span data-stu-id="bc0e4-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="bc0e4-115">EAP Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="bc0e4-116">Profilde doğru Wi-Fi bir kez daha kontrol edin:</span><span class="sxs-lookup"><span data-stu-id="bc0e4-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="bc0e4-117">EAP türü doğru yapılandırıldı, yaygın EAP türleri: EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="bc0e4-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="bc0e4-118">Wi-Fi SSID adı doğru ve HEX dizesiyle eşler.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="bc0e4-119">EAP-TLS için TrustedRootCA, sunucunun güvenilen kök CA sertifikasının SHA-1 karması içerir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="bc0e4-120">Windows bilgisayar "certutil.exe -dump cert_file_name" komutu bir sertifikanın SHA-1 karma dizesini gösterir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="bc0e4-121">EAP oturumunun nerede başarısız olduğunu bulmak için Erişim Noktası, Denetleyici veya AAA sunucu günlüklerinde ağ paketi yakalamayı toplayın.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="bc0e4-122">HoloLens tarafından sağlanan EAP kimliği beklenlenmiyorsa, kimliğin bir profil veya istemci sertifikası aracılığıyla Wi-Fi sağ olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="bc0e4-123">Sunucu HoloLens istemci sertifikasını reddederse, gerekli istemci sertifikasının cihazda sağlandı olup olmadığını kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="bc0e4-124">HoloLens sunucu sertifikasını reddederse, sunucu kök CA sertifikasının HoloLens'de sağlandı olup olduğunu kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="bc0e4-125">Kurumsal profil bir sağlama paketi Wi-Fi sağlanıyorsa, sağlama paketini Windows 10 bilgisayarınızda uygulamayı göz önünde bulundurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="bc0e4-126">Bilgisayarınızda da başarısız Windows 10 Windows istemcisi 802.1X kimlik doğrulaması sorun giderme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="bc0e4-127">Bize geri bildirim göndererek Geri Bildirim Merkezi.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="bc0e4-128">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="bc0e4-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="bc0e4-129">Wi-Fi Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="bc0e4-130">HoloLens'inizi bir sanal ağ bağlantısı kuramıyorsanız deneyecek Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="bc0e4-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="bc0e4-131">Bu Wi-Fi emin olun.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="bc0e4-132">Kontrol etmek için Başlangıç hareketini kullanın ve ardından Wi-Fi ile > Ağ & İnternet >'ı seçin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="bc0e4-133">Bu Wi-Fi, kapatmayı ve sonra tekrar açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="bc0e4-134">Yönlendiriciye veya erişim noktasına yaklaşın.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="bc0e4-135">Sanal yönlendiricinizi Wi-Fi ve ardından HoloLens'i yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="bc0e4-136">Yeniden bağlanmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-136">Try connecting again.</span></span>
4. <span data-ttu-id="bc0e4-137">Bunlardan hiçbiri çalışmıyorsa, yönlendiricinizin en son üretici yazılımını kullanmaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="bc0e4-138">Bu bilgileri üretici web sitesinde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="bc0e4-139">Cihazda bir kuruluş veya kuruluş hesabında oturum asanız, ilkeNIN IT yöneticiniz tarafından yapılandırılması Cihaz Yönetimi Mobile Cihaz Yönetimi (MDM) ilkesi de uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="bc0e4-140">Ağ Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-140">Network Troubleshooting</span></span>
<span data-ttu-id="bc0e4-141">Ağ sorunları, HoloLens 2'yi başarıyla dağıtmanızı ve bunu kullanmayı engellerse, fiddler ve Wireshark gibi bilinen iki ağ tanılama aracının sorunları taramanıza, tanılamanıza ve tanımlamanıza nasıl yardımcı olduğunu öğrenin.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="bc0e4-142">Diğer ayrıntılar için [bu bloga](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) göz atabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="bc0e4-143">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="bc0e4-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="bc0e4-144">Daha önce kurulumu yapılan HoloLens cihazında oturum açma işlemi tamamlanmıyor</span><span class="sxs-lookup"><span data-stu-id="bc0e4-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="bc0e4-145">Cihazınız daha önce bir istemci için veya eski bir çalışan için başka biri için ayarlanmışsa ve cihazın kilidini açmak için parolanız yoksa, cihazı uzaktan silmek için Intune kullanabilirsiniz. [](https://docs.microsoft.com/intune/remote-actions/devices-wipe)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="bc0e4-146">Ardından cihaz kendisini yeniden yanıp söner.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="bc0e4-147">Cihazı silerken Kayıt durumunu ve kullanıcı hesabını **koruma işaretsiz bırakın.**</span><span class="sxs-lookup"><span data-stu-id="bc0e4-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="bc0e4-148">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="bc0e4-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="bc0e4-149">Windows Holographic 21H1'e güncelleştirdikten sonra oturum açılam</span><span class="sxs-lookup"><span data-stu-id="bc0e4-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="bc0e4-150">Belirtiler</span><span class="sxs-lookup"><span data-stu-id="bc0e4-150">Symptoms</span></span>
- <span data-ttu-id="bc0e4-151">Doğru PIN girdikten sonra oturum açma için PIN kullanma başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="bc0e4-152">Web sayfasında başarıyla oturum açma işlemi sonrasında web oturum açma yönteminin kullanımı başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="bc0e4-153">Cihaz , [-> Azure Active Directory](https://portal.azure.com/) -> Devices Azure portal "Azure AD'ye katılmış" olarak listelenmiyor.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="bc0e4-154">Nedeni</span><span class="sxs-lookup"><span data-stu-id="bc0e4-154">Cause</span></span>
<span data-ttu-id="bc0e4-155">Etkilene cihaz Azure AD kiracıdan silinmiş olabilir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="bc0e4-156">Örneğin, bunun nedeni:</span><span class="sxs-lookup"><span data-stu-id="bc0e4-156">For example, this may happen because:</span></span>

- <span data-ttu-id="bc0e4-157">Yönetici veya kullanıcı, cihazı cihazdan Azure portal PowerShell'i kullanarak sildi.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="bc0e4-158">Cihaz, işlem dışı olduğu için Azure AD kiracıdan kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="bc0e4-159">Verimli bir şekilde yönetilen bir ortam için, GENELLIKLE, IT yöneticilerinin eski, etkin olmayan cihazları [Azure AD kiracılarından kaldırmasını öneririz.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="bc0e4-160">Etkilene bir cihaz silindikten sonra Azure AD kiracısına yeniden iletişim kurma girişiminde bulunsa, Azure AD ile kimlik doğrulaması başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="bc0e4-161">PIN aracılığıyla önbelleğe alınan oturum açma işlemi kullanıcının oturum açmasına izin vermeye devam ettiği için bu etki genellikle cihaz kullanıcısı tarafından görünmez.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="bc0e4-162">Risk azaltma</span><span class="sxs-lookup"><span data-stu-id="bc0e4-162">Mitigation</span></span>
<span data-ttu-id="bc0e4-163">Şu anda silinmiş bir HoloLens cihazı Azure AD'ye geri eklemenin hiçbir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="bc0e4-164">Etkilenen cihazların cihazına ters eğik çizgiyle başvurulma yönergelerini izleyerek [temiz bir şekilde yeniden bayrakları gerekir.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="bc0e4-165">Autopilot Sorunlarını Giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="bc0e4-166">Aşağıdaki makaleler daha fazla bilgi edinmek ve Autopilot Sorunlarını gidermek için kullanışlı bir kaynak olabilir, ancak bu makalelerin Windows 10 Desktop'a dayandırılana kadar tüm bilgilerin HoloLens için geçerli olmadığını unutmayın:</span><span class="sxs-lookup"><span data-stu-id="bc0e4-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="bc0e4-167">Windows Autopilot - bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="bc0e4-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="bc0e4-168">Microsoft Intune'de Windows cihaz kaydı sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="bc0e4-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="bc0e4-169">Windows Autopilot - İlke Çakışmaları</span><span class="sxs-lookup"><span data-stu-id="bc0e4-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="bc0e4-170">Yönetilen HoloLens Cihazları hakkında SSS</span><span class="sxs-lookup"><span data-stu-id="bc0e4-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="bc0e4-171">HoloLens System Center Yapılandırma Yöneticisi yönetmek için System Center Yapılandırma Yöneticisi (SCCM) kullanabilir miyim?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="bc0e4-172">Hayır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-172">No.</span></span> <span data-ttu-id="bc0e4-173">HoloLens cihazlarını yönetmek için bir MDM sistemi kullanmak zorundasiniz.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="bc0e4-174">HoloLens kullanıcı Active Directory Domain Services (AD DS) kullanabilir miyim?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="bc0e4-175">Hayır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-175">No.</span></span> <span data-ttu-id="bc0e4-176">HoloLens cihazlarına Azure Active Directory hesaplarını yönetmek için Azure Active Directory (Azure AD) kullanasınız.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="bc0e4-177">HoloLens Otomatik Veri Yakalama Sistemleri (ADCS) otomatik kayıt özelliğine sahip mi?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="bc0e4-178">Hayır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="bc0e4-179">HoloLens, sanal Tümleşik Windows Kimlik Doğrulaması?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="bc0e4-180">Hayır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="bc0e4-181">HoloLens markayı destekliyor mu?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="bc0e4-182">Hayır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-182">No.</span></span> <span data-ttu-id="bc0e4-183">Ancak, aşağıdaki yaklaşımlardan birini kullanarak bu soruna yönelik bir çalışma yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="bc0e4-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="bc0e4-184">Özel bir uygulama oluşturun ve bilgi [noktası modunu etkinleştirin.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="bc0e4-185">Özel uygulama markaya sahip olabilir ve diğer uygulamaları (Remote Assist gibi) başlatabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="bc0e4-186">Azure AD'de tüm kullanıcı profili resimlerini şirket logonuzu olarak değiştirme.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="bc0e4-187">Ancak, tüm senaryolar için bu tercih edilmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="bc0e4-188">HoloLens 2 hangi günlük özelliklerini sunuyor?</span><span class="sxs-lookup"><span data-stu-id="bc0e4-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="bc0e4-189">Günlüğe kaydetme, geliştirme veya sorun giderme senaryolarında yakalanacak izlemeler veya cihazların Microsoft sunucularına göndermekte olduğu telemetri verileriyle sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="bc0e4-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="bc0e4-190">HoloLens cihazlarının güvenliğini sağlamayla ilgili sorular</span><span class="sxs-lookup"><span data-stu-id="bc0e4-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="bc0e4-191">[HoloLens 2 güvenlik bilgilerimize bakın.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="bc0e4-192">HoloLens 1. Nesil cihazlar için lütfen bu SSS [bölümünü gözden geçirin.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="bc0e4-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="bc0e4-193">Listeye dön</span><span class="sxs-lookup"><span data-stu-id="bc0e4-193">Back to list</span></span>](#list)
