---
title: HoloLens 2 uygulama ve yönetilen cihaz sorunlarını giderme
description: Enterprise ortamında 2 cihazda HoloLens sorunlarını giderme
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636886"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="cf7b7-104">Uygulama ve yönetilen cihazlar sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="cf7b7-105">bu makalede, HoloLens 2 ' nin uygulanması ve yönetimiyle ilgili birçok sorunu nasıl giderebileceğinizi veya soruların nasıl yanıtlanabileceği açıklanır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="cf7b7-106">Herhangi bir sorun giderme yordamını başlatmaya başlamadan önce, cihazınızın, mümkünse pil kapasitesi için **yüzde 20 ila 40 oranında** ücretlendirildiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="cf7b7-107">Güç düğmesinin altında bulunan [Pil göstergesi ışıkları](hololens2-setup.md#lights-that-indicate-the-battery-level) , cihazda oturum açmadan pil kapasitesini doğrulamaya yönelik hızlı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="cf7b7-108">EAP sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="cf7b7-109">Wi-Fi sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="cf7b7-110">Ağ sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="cf7b7-111">daha önce bir kurulum HoloLens cihazda oturum açılamıyor</span><span class="sxs-lookup"><span data-stu-id="cf7b7-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="cf7b7-112">güncelleştirme sonrasında oturum açılamıyor Windows Holographic 21h1</span><span class="sxs-lookup"><span data-stu-id="cf7b7-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="cf7b7-113">Autopilot sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="cf7b7-114">yönetilen HoloLens cihazları sss</span><span class="sxs-lookup"><span data-stu-id="cf7b7-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="cf7b7-115">EAP sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="cf7b7-116">Çift denetim Wi-Fi profilinde doğru ayarlar var:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="cf7b7-117">EAP türü doğru yapılandırılmış, ortak EAP türleri: EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="cf7b7-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="cf7b7-118">Wi-Fi SSID adı doğru ve ONALTıLıK dizeyle eşleşiyor.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="cf7b7-119">EAP-TLS için TrustedRootCA sunucunun Güvenilen kök CA sertifikasının SHA-1 karmasını içerir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="cf7b7-120">Windows PC "certutil.exe-döküm cert_file_name" komutu, bir sertifikanın SHA-1 karma dizesini gösterir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="cf7b7-121">EAP oturumunun nerede başarısız olduğunu öğrenmek için erişim noktası veya denetleyici ya da AAA sunucusu günlüklerinde ağ paketi yakalamayı toplayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="cf7b7-122">HoloLens tarafından sağlanan EAP kimliği beklenmiyorsa, kimliğin Wi-Fi profil veya istemci sertifikası aracılığıyla doğru şekilde sağlanıp sağlanmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="cf7b7-123">sunucu HoloLens istemci sertifikasını reddederse, cihazda gerekli istemci sertifikasının sağlanıp sağlanmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="cf7b7-124">HoloLens sunucu sertifikasını reddederse, sunucu kök CA sertifikasının HoloLens sağlanıp sağlanmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="cf7b7-125">kurumsal profile Wi-Fi sağlama paketiyle sağlanmışsa, sağlama paketini bir Windows 10 bilgisayara uygulamayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="cf7b7-126">Windows 10 PC 'de de başarısız olursa, Windows client 802.1 x authentication sorun giderme kılavuzunu izleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="cf7b7-127">Geri Bildirim Hub 'ı aracılığıyla bize geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="cf7b7-128">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="cf7b7-129">Wi-Fi sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="cf7b7-130">HoloLens Wi-Fi ağa bağlanamadıysanız deneyebileceğiniz bazı şeyler aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="cf7b7-131">Wi-Fi açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="cf7b7-132">bunu denetlemek için başlangıç hareketini kullanın, Ayarlar > ağ & ınternet > Wi-Fi ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="cf7b7-133">Wi-Fi açık ise, kapatıp yeniden açmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="cf7b7-134">Yönlendiriciye veya erişim noktasına yaklaşın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="cf7b7-135">Wi-Fi yönlendiricinizi yeniden başlatın ve HoloLens yeniden başlatın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="cf7b7-136">Yeniden bağlanmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-136">Try connecting again.</span></span>
4. <span data-ttu-id="cf7b7-137">Bu öğelerin hiçbiri işe çalışmadıysanız, yönlendiricinizin en son bellenim sürümünü kullandığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="cf7b7-138">Bu bilgileri üretici web sitesinde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="cf7b7-139">Cihazdaki bir kuruluşta veya kurumsal hesapta oturum açtığınızda, ilke BT yöneticiniz tarafından yapılandırılmışsa mobil cihaz yönetimi (MDM) ilkesi de uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="cf7b7-140">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="cf7b7-141">Ağ sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-141">Network Troubleshooting</span></span>
<span data-ttu-id="cf7b7-142">ağ sorunları, kuruluşunuzda HoloLens 2 ' yi başarıyla dağıtmaya ve kullanmaya yönelik bir obstayor ise, fiddler ve/veya Wireshark 'yi, HTTP/HTTPS trafiğini yakalamak ve analiz etmek için yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="cf7b7-143">HTTP trafiğini yakalamak için Fiddler 'ı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cf7b7-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="cf7b7-144">Fiddler, Web hata ayıklama proxy 'si ve HTTP (S) sorunlarını gidermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="cf7b7-145">Bilgisayarın yaptığı tüm HTTP isteklerini yakalar ve onunla ilişkili her şeyi kaydeder.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="cf7b7-146">HTTPS uygulamalarınız için son kullanıcı kimlik doğrulama sorunlarını kapsaunın, hedef HoloLens 2 kullanım örnekleri için daha fazla üretkenlik ve verimlilik sağlayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="cf7b7-147">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="cf7b7-147">Prerequisites</span></span>
 
- <span data-ttu-id="cf7b7-148">HoloLens 2 cihaz ve bilgisayarınızın aynı ağda olması gerekir</span><span class="sxs-lookup"><span data-stu-id="cf7b7-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="cf7b7-149">BILGISAYARıNıZıN IP adresini aklınızda</span><span class="sxs-lookup"><span data-stu-id="cf7b7-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="cf7b7-150">Fiddler 'i yükleyip yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cf7b7-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="cf7b7-151">Bilgisayarınızda, Fiddler 'ı [yükleyip](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) başlatın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="cf7b7-152">Bilgisayarınızda, uzak bilgisayarların bağlanmasına izin vermek için Fiddler 'ı yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="cf7b7-153">fiddler Ayarlar-> bağlantılarına git</span><span class="sxs-lookup"><span data-stu-id="cf7b7-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="cf7b7-154">Fiddler için dinleme bağlantı noktasını aklınızda (varsayılan 8866)</span><span class="sxs-lookup"><span data-stu-id="cf7b7-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="cf7b7-155">Uzak bilgisayarların bağlanmasına Izin ver ' i işaretleyin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="cf7b7-156">Kaydet’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-156">Click Save</span></span>
3. <span data-ttu-id="cf7b7-157">HoloLens 2 – ara sunucu olarak fiddler 'ı yapılandırın<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="cf7b7-158">Başlat menüsü açın ve Ayarlar seçin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="cf7b7-159">Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="cf7b7-160">Aşağı doğru ara sunucu kurulumuna gidin ve üzerinde bir proxy sunucusu kullan ' a geçiş yapın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="cf7b7-161">Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="cf7b7-162">Yukarıda belirtilen bağlantı noktası numarasını girin (varsayılan değer 8866 ' dir)</span><span class="sxs-lookup"><span data-stu-id="cf7b7-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="cf7b7-163">Kaydet’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-163">Click Save</span></span>

<span data-ttu-id="cf7b7-164"><sup>1</sup> derlemeler 20279.1006 + (Insiders ve yaklaşan sürüm) için, proxy 'yi yapılandırmak için aşağıdaki adımları kullanın:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="cf7b7-165">Başlat menüsü açın ve Wi-Fi ağınızın özellikler sayfasına gidin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="cf7b7-166">Aşağı kaydırarak ara sunucu</span><span class="sxs-lookup"><span data-stu-id="cf7b7-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="cf7b7-167">El Ile kuruluma geçiş yapın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="cf7b7-168">Fiddler 'ın yüklü olduğu BILGISAYARıN IP adresini girin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="cf7b7-169">Yukarıda belirtilen bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-169">Enter the port number noted above.</span></span> <span data-ttu-id="cf7b7-170">(varsayılan değer 8866 ' dir)</span><span class="sxs-lookup"><span data-stu-id="cf7b7-170">(default is 8866)</span></span>
1. <span data-ttu-id="cf7b7-171">Uygula ' ya tıklayın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="cf7b7-172">HoloLens 2 ' den HTTPS trafiğinin şifresini çözün</span><span class="sxs-lookup"><span data-stu-id="cf7b7-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="cf7b7-173">Bilgisayarınızda – Fiddler sertifikasını dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="cf7b7-174">fıddler Ayarlar-> HTTPS 'ye gidin ve gelişmiş Ayarlar genişletin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="cf7b7-175">Fiddler sertifikasını dışarı aktar ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="cf7b7-176">Masaüstünüze kaydedilecek</span><span class="sxs-lookup"><span data-stu-id="cf7b7-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="cf7b7-177">sertifikayı HoloLens 2 ' deki indirilenler klasörüne taşıyın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="cf7b7-178">HoloLens 2-fiddler sertifikasını içeri aktarın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="cf7b7-179">Ayarlar > güncelleştirme ve güvenlik-> sertifikalarına gidin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="cf7b7-180">Sertifika yüklensin ' e tıklayın, Indirmeler klasörüne gidin ve Fiddler sertifikasını seçin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="cf7b7-181">Depo konumunu yerel makineye Değiştir</span><span class="sxs-lookup"><span data-stu-id="cf7b7-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="cf7b7-182">Sertifika deposunu köke Dönüştür</span><span class="sxs-lookup"><span data-stu-id="cf7b7-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="cf7b7-183">Yüklemeyi seçin</span><span class="sxs-lookup"><span data-stu-id="cf7b7-183">Select Install</span></span>
    6. <span data-ttu-id="cf7b7-184">Sertifikanın sertifika listesinde görüntülendiğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="cf7b7-185">Aksi takdirde, yukarıdaki adımları tekrarlayın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="cf7b7-186">HTTP (S) oturumlarını İncele</span><span class="sxs-lookup"><span data-stu-id="cf7b7-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="cf7b7-187">bilgisayarınızda, fiddler 'ın HoloLens 2 ' nin canlı HTTP oturumlarını göstermesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="cf7b7-188">Fiddler 'daki Inspectors paneli, HTTP (S) istek/yanıtını farklı görünümlerde gösterebilir. Örneğin, "RAW" görünümü ham isteği veya yanıtı düz metin olarak gösterir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="cf7b7-189">Ağ trafiğini yakalamak için Wireshark 'ı yapılandırma</span><span class="sxs-lookup"><span data-stu-id="cf7b7-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="cf7b7-190">Wireshark bir ağ protokol çözümleyicisidir ve TCP/UDP trafiğini HoloLens 2 cihazınızdan denetlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="cf7b7-191">bu, ağınızı HoloLens 2 ' ye hangi trafiğin, ne kadarının, ne kadar sıklıkla olduğunu, belirli atlamaları arasında ne kadar gecikme olduğunu ve bu şekilde olduğunu belirlemeyi kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="cf7b7-192">Ön koşullar:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-192">Prerequisites:</span></span>
- <span data-ttu-id="cf7b7-193">BILGISAYAR Internet erişimine sahip olmalı ve Wi-Fi üzerinde Internet paylaşımını desteklemelidir</span><span class="sxs-lookup"><span data-stu-id="cf7b7-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="cf7b7-194">Wireshark 'yi yükleyip yapılandırın</span><span class="sxs-lookup"><span data-stu-id="cf7b7-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="cf7b7-195">Bilgisayarınızda [Wireshark](https://www.wireshark.org/#download) 'i yükledikten sonra</span><span class="sxs-lookup"><span data-stu-id="cf7b7-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="cf7b7-196">Bilgisayarınızda, Wi-Fi ' r e Internet bağlantınızı paylaşmak için mobil etkin noktayı etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="cf7b7-197">Bilgisayarınızı başlatın Wireshark ve mobil etkin nokta arabiriminden trafiği yakalayın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="cf7b7-198">HoloLens 2: Wi-Fi ağını bilgisayarın mobil etkin olmadan değiştirin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="cf7b7-199">HoloLens 2 ıp trafiği Wireshark ' de görünür.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="cf7b7-200">Wireshark günlüklerini çözümleme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="cf7b7-201">Wireshark filtreleri, ilgilendiğiniz paketlerin filtrelemesine yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="cf7b7-202">Özgün [bloga](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458)göz atın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="cf7b7-203">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="cf7b7-204">daha önce bir kurulum HoloLens cihazda oturum açılamıyor</span><span class="sxs-lookup"><span data-stu-id="cf7b7-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="cf7b7-205">Cihazınız daha önce bir istemcisi ya da bir önceki çalışan için daha önce ayarlandıysa ve cihazın kilidini açmak için bir parola yoksa, [cihazı uzaktan silmek](/intune/remote-actions/devices-wipe) için Intune 'u kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="cf7b7-206">Cihaz daha sonra kendisini yeniden yanıp sönmelidir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="cf7b7-207">Cihazı sildiğinizde, **kayıt durumunu ve Kullanıcı hesabını** işaretlenmemiş olarak bırakın ' ın işaretini kaldırın.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="cf7b7-208">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="cf7b7-209">güncelleştirme sonrasında oturum açılamıyor Windows Holographic 21h1</span><span class="sxs-lookup"><span data-stu-id="cf7b7-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="cf7b7-210">Belirtiler</span><span class="sxs-lookup"><span data-stu-id="cf7b7-210">Symptoms</span></span>
- <span data-ttu-id="cf7b7-211">Doğru PIN girildikten sonra, oturum açma için PIN kullanılması başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="cf7b7-212">Web sayfasında başarıyla oturum açıldıktan sonra Web oturum açma yönteminin kullanılması başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="cf7b7-213">cihaz, [Azure portal](https://portal.azure.com/) > Azure Active Directory-> cihazlarda "Azure AD 'ye katılmış" olarak listelenmez.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="cf7b7-214">Nedeni</span><span class="sxs-lookup"><span data-stu-id="cf7b7-214">Cause</span></span>
<span data-ttu-id="cf7b7-215">Etkilenen cihaz Azure AD kiracısından silinmiş olabilir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="cf7b7-216">Örneğin, bu durum oluşabilir:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-216">For example, this may happen because:</span></span>

- <span data-ttu-id="cf7b7-217">Yönetici veya Kullanıcı Azure portal cihazı veya PowerShell 'i kullanarak sildi.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="cf7b7-218">Cihaz, etkinlik dışı nedenlerle Azure AD kiracısından kaldırıldı.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="cf7b7-219">Etkin bir şekilde yönetilen bir ortamda, genellikle BT yöneticilerinin [Azure AD kiracısından eski, etkin olmayan cihazları kaldırmasını](/azure/active-directory/devices/manage-stale-devices)öneririz.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="cf7b7-220">Etkilenen bir cihaz silindikten sonra yeniden iletişim kurmayı denediğinde Azure AD ile kimlik doğrulaması başarısız olur.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="cf7b7-221">Bu efekt, PIN aracılığıyla önbelleğe alınan oturum açmanın kullanıcının oturum açmasına izin vermeyi sürdüreceği için genellikle cihazın kullanıcısı tarafından görünmez.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="cf7b7-222">Risk azaltma</span><span class="sxs-lookup"><span data-stu-id="cf7b7-222">Mitigation</span></span>
<span data-ttu-id="cf7b7-223">şu anda, silinen HoloLens cihazı Azure AD 'ye geri eklemenin bir yolu yoktur.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="cf7b7-224">Etkilenen cihazların, [cihazlarıyla](hololens-recovery.md#clean-reflash-the-device)ilgili yönergeleri izleyerek Temizleme sırasında Temizleme olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="cf7b7-225">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="cf7b7-226">Autopilot sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="cf7b7-227">aşağıdaki makaleler, daha fazla bilgi edinmek ve Autopilot sorunlarını gidermek için yararlı bir kaynak olabilir, ancak bu makalelerin Windows 10 masaüstüne bağlı olduğunu ve tüm bilgilerin HoloLens için uygulanabilir olabileceğini lütfen unutmayın:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="cf7b7-228">Windows Autopilot-bilinen sorunlar</span><span class="sxs-lookup"><span data-stu-id="cf7b7-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="cf7b7-229">Microsoft Intune Windows cihaz kaydı sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="cf7b7-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="cf7b7-230">Windows Autopilot-Ilke çakışmaları</span><span class="sxs-lookup"><span data-stu-id="cf7b7-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="cf7b7-231">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="cf7b7-232">yönetilen HoloLens cihazları sss</span><span class="sxs-lookup"><span data-stu-id="cf7b7-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="cf7b7-233">HoloLens cihazlarını yönetmek için System Center Configuration Manager (SCCM) kullanabilir miyim?</span><span class="sxs-lookup"><span data-stu-id="cf7b7-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="cf7b7-234">Hayır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-234">No.</span></span> <span data-ttu-id="cf7b7-235">HoloLens cihazlarını yönetmek için bir MDM sistemi kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="cf7b7-236">HoloLens kullanıcı hesaplarını yönetmek için Active Directory Domain Services (AD DS) kullanabilir miyim?</span><span class="sxs-lookup"><span data-stu-id="cf7b7-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="cf7b7-237">Hayır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-237">No.</span></span> <span data-ttu-id="cf7b7-238">HoloLens cihazların kullanıcı hesaplarını yönetmek için Azure Active Directory (Azure AD) kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="cf7b7-239">otomatik veri yakalama sistemleri (ADCS) otomatik kayıt özellikli HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="cf7b7-240">Hayır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="cf7b7-241">tümleşik Windows kimlik doğrulamasına HoloLens eklenebilir mi?</span><span class="sxs-lookup"><span data-stu-id="cf7b7-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="cf7b7-242">Hayır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="cf7b7-243">HoloLens markalamayı destekliyor mu?</span><span class="sxs-lookup"><span data-stu-id="cf7b7-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="cf7b7-244">Hayır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-244">No.</span></span> <span data-ttu-id="cf7b7-245">Ancak, aşağıdaki yaklaşımlardan birini kullanarak bu sorunu geçici olarak çözebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="cf7b7-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="cf7b7-246">Özel bir uygulama oluşturun ve [bilgi noktası modunu etkinleştirin](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="cf7b7-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="cf7b7-247">Özel uygulama marka içerebilir ve diğer uygulamaları başlatabilir (uzaktan yardım gibi).</span><span class="sxs-lookup"><span data-stu-id="cf7b7-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="cf7b7-248">Azure AD 'deki tüm Kullanıcı profili resimlerini şirket logonuz olacak şekilde değiştirin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="cf7b7-249">Ancak, bu, tüm senaryolar için istenmeyebilir.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="cf7b7-250">2 teklif HoloLens günlük oluşturma özellikleri nelerdir?</span><span class="sxs-lookup"><span data-stu-id="cf7b7-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="cf7b7-251">Günlüğe kaydetme, geliştirme veya sorun giderme senaryolarında yakalanamayan izlemelerle veya cihazların Microsoft sunucularına gönderdikleri telemetri ile sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="cf7b7-252">HoloLens cihazların güvenliğini sağlama hakkında sorular</span><span class="sxs-lookup"><span data-stu-id="cf7b7-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="cf7b7-253">[HoloLens 2 güvenlik bilgilerini](security-overview.md)inceleyin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="cf7b7-254">1. Gen cihaz HoloLens için lütfen [bu sss](hololens1-faq-security.yml)'yi gözden geçirin.</span><span class="sxs-lookup"><span data-stu-id="cf7b7-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="cf7b7-255">Listeye geri dön</span><span class="sxs-lookup"><span data-stu-id="cf7b7-255">Back to list</span></span>](#list)
