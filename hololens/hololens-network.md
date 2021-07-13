---
title: bir ağa HoloLens Bağlan
description: HoloLens ile internet 'i ayarlamayı ve bağlamayı öğrenin ve cihaz ıp adresini nasıl tanımlayacağınızı öğrenin.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, kablosuz, internet, ıp, ıp adresi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640228"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="fc996-104">bir ağa HoloLens Bağlan</span><span class="sxs-lookup"><span data-stu-id="fc996-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="fc996-105">HoloLens birçok şeyi yapmak için bir ağa bağlı olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="fc996-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="fc996-106">HoloLens bir 802.11 ac özellikli, 2x2 Wi-Fi radyo ve ağa bağlama bir Windows 10 masaüstü veya mobil cihazı bir Wi-Fi ağına bağlamaya benzer.</span><span class="sxs-lookup"><span data-stu-id="fc996-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="fc996-107">Bu kılavuz şunları yapmanıza yardımcı olur:</span><span class="sxs-lookup"><span data-stu-id="fc996-107">This guide will help you:</span></span>

- <span data-ttu-id="fc996-108">Wi-Fi kullanarak bir ağa Bağlan veya yalnızca HoloLens 2 için USB-C üzerinden doğrudan veya Ethernet Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="fc996-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="fc996-109">Wi-Fi devre dışı bırakıp yeniden etkinleştirin</span><span class="sxs-lookup"><span data-stu-id="fc996-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="fc996-110">[HoloLens çevrimdışı kullanma](hololens-offline.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="fc996-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="fc996-111">İlk kez bağlanıyor</span><span class="sxs-lookup"><span data-stu-id="fc996-111">Connecting for the first time</span></span>

<span data-ttu-id="fc996-112">HoloLens ilk kez kullandığınızda, bir Wi-Fi ağa bağlanarak gezinirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc996-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="fc996-113">Kurulum sırasında Wi-Fi bağlanmada sorun yaşıyorsanız, ağınızın açık, parola korumalı bir ağ ya da bir açıklamalı Portal ağı olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="fc996-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="fc996-114">Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmediğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="fc996-115">Kurulumdan sonra, diğer Wi-Fi ağları türlerine bağlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc996-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="fc996-116">HoloLens 2 cihazda, bir kullanıcı, cihazı ayarlarken yardım 'a doğrudan Wi-Fi bağlanmak için [bir USB-C-Ethernet bağdaştırıcısı da kullanabilir](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) .</span><span class="sxs-lookup"><span data-stu-id="fc996-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="fc996-117">Cihaz ayarlandıktan sonra, bir Kullanıcı bağdaştırıcıyı kullanmaya devam edebilir ya da cihazın bağdaştırıcı bağlantısını kesebilir ve ayarladıktan [sonra Wi-Fi 'a bağlanabilir](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="fc996-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="fc996-118">Kurulumdan sonra Wi-Fi bağlanma</span><span class="sxs-lookup"><span data-stu-id="fc996-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="fc996-119">**başlangıç hareketini** önceden oluşturup **Ayarlar** seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="fc996-120">Ayarlar uygulama, sizin için otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="fc996-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fc996-121">**Internet**  >  **Wi-Fi**& ağ ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="fc996-122">Wi-Fi’ın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="fc996-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="fc996-123">Ağınızı görmüyorsanız listede aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="fc996-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="fc996-124">bir ağ seçin, sonra **Bağlan**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="fc996-125">Bir ağ parolası istenirse bu dosyayı yazın ve ardından **İleri**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi ayarları](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="fc996-127">Wi-Fi ağa bağlı olduğunu doğrulamak için, **Başlangıç** menüsündeki Wi-Fi durumunu kontrol edin:</span><span class="sxs-lookup"><span data-stu-id="fc996-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="fc996-128">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fc996-129">Wi-Fi durum için **Başlangıç** menüsünün sol üst kısmına bakın.</span><span class="sxs-lookup"><span data-stu-id="fc996-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="fc996-130">Wi-Fi durumu ve bağlı ağın SSID 'SI gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="fc996-131">Wi-Fi yoksa [hücresel ve 5 g ağlarına da bağlanabilirsiniz](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="fc996-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc996-132">tasarıma göre, kullanıcılar HoloLens 2 ' nin Wi-Fi dolaşım davranışını ince ayarlayamez. **Wi-Fi listesini yenilemenin tek yolu Wi-Fi kapalı ve açık olarak geçiş yapmaz**.</span><span class="sxs-lookup"><span data-stu-id="fc996-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="fc996-133">Bu, bir cihazın Aralık dışına çıkdıktan sonra bir AP 'ye "takılı" kalabileceği gibi birçok sorunu önler.</span><span class="sxs-lookup"><span data-stu-id="fc996-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="fc996-134">Wi-Fi ağ Enterprise HoloLens Bağlan</span><span class="sxs-lookup"><span data-stu-id="fc996-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="fc996-135">Enterprise Wi-Fi profiller Wi-Fi bağlantılarının kimliğini doğrulamak için genişletilebilir kimlik doğrulama protokolü (EAP) kullanır.</span><span class="sxs-lookup"><span data-stu-id="fc996-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="fc996-136">HoloLens Enterprise Wi-Fi profili, [Windows yapılandırma tasarımcısı](/windows/configuration/provisioning-packages/provisioning-packages)tarafından oluşturulan MDM veya sağlama paketi aracılığıyla yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="fc996-137">Microsoft Intune yönetilen cihaz için yapılandırma yönergeleri için [ıntune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 'a bakın.</span><span class="sxs-lookup"><span data-stu-id="fc996-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="fc996-138">WCD 'de Wi-Fi sağlama paketi oluşturmak için, önceden yapılandırılmış bir Wi-Fi profili .xml dosyası gereklidir.</span><span class="sxs-lookup"><span data-stu-id="fc996-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="fc996-139">EAP-TLS kimlik doğrulaması ile WPA2-Enterprise için örnek bir Wi-Fi profili aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="fc996-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="fc996-140">Sunucu kök CA sertifikası ve istemci sertifikasının, EAP türüne bağlı olarak cihazda sağlanması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="fc996-141">Ek kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="fc996-141">Additional resources:</span></span>

- <span data-ttu-id="fc996-142">WLANv1Profile şeması: [[MS-GPWL]: Kablosuz LAN profili v1 şeması | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="fc996-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="fc996-143">EAP-TLS şeması: [[MS-GPWL]: MICROSOFT EAP TLS şeması | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="fc996-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="fc996-144">Wi-Fi 'nize bağlanmakta sorun yaşıyorsanız [sorun giderme](hololens2-enterprise-troubleshooting.md#) sayfamızı denetleyin.</span><span class="sxs-lookup"><span data-stu-id="fc996-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="fc996-145">Ağ ara sunucusunu yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fc996-145">Configure Network Proxy</span></span>

<span data-ttu-id="fc996-146">bu bölümde, Windows HTTP yığını kullanan HoloLens OS ve Evrensel Windows Platformu (UWP) uygulamaları için ağ proxy 'si ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="fc996-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="fc996-147">Windows olmayan HTTP yığınının kullanıldığı uygulamalar kendi ara sunucu yapılandırmasına ve işlemeye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="fc996-148">Proxy yapılandırması</span><span class="sxs-lookup"><span data-stu-id="fc996-148">Proxy Configurations</span></span> 

- <span data-ttu-id="fc996-149">Proxy otomatik yapılandırma (PAC) betiği: bir [pac dosyası](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft dışı bir site açar), FindProxyForURL (URL, ana bilgisayar) JavaScript işlevini içerir.</span><span class="sxs-lookup"><span data-stu-id="fc996-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="fc996-150">Statik proxy: sunucu: bağlantı noktası biçiminde.</span><span class="sxs-lookup"><span data-stu-id="fc996-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="fc996-151">Web proxy otomatik bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla proxy yapılandırma dosyasının URL 'sini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="fc996-152">Proxy sağlama yöntemleri</span><span class="sxs-lookup"><span data-stu-id="fc996-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="fc996-153">Proxy 'lerin sağlanması için üç yol vardır:</span><span class="sxs-lookup"><span data-stu-id="fc996-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="fc996-154">**Ayarlar 'SıNı**</span><span class="sxs-lookup"><span data-stu-id="fc996-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="fc996-155">Kullanıcı başına proxy (20H2 veya önceki sürümler):</span><span class="sxs-lookup"><span data-stu-id="fc996-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="fc996-156">Başlat menüsü açın ve Ayarlar ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="fc996-157">Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="fc996-158">, El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.</span><span class="sxs-lookup"><span data-stu-id="fc996-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="fc996-159">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="fc996-160">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-160">Enter the port number.</span></span>
        6. <span data-ttu-id="fc996-161">Kaydet’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-161">Click Save.</span></span>
      1. <span data-ttu-id="fc996-162">WiFi proxy (21H1 veya üzeri):</span><span class="sxs-lookup"><span data-stu-id="fc996-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="fc996-163">Başlat menüsü açın ve Wi-Fi ağınızın özellikler sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="fc996-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="fc996-164">Aşağı kaydırarak ara sunucu</span><span class="sxs-lookup"><span data-stu-id="fc996-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="fc996-165">El Ile kuruluma geçiş yapın</span><span class="sxs-lookup"><span data-stu-id="fc996-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="fc996-166">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="fc996-167">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-167">Enter the port number.</span></span>
          1. <span data-ttu-id="fc996-168">Uygula ' ya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="fc996-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="fc996-169">**MDM**</span></span> 
     1. <span data-ttu-id="fc996-170">Intune-Intune 'da proxy yapılandırmak için bu [adımları](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) kullanın.</span><span class="sxs-lookup"><span data-stu-id="fc996-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="fc996-171">Bölümün altına kaydırmanız gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="fc996-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="fc996-172">Diğer üçüncü taraf MDM çözümleri- [WIFI CSP](/windows/client-management/mdm/wifi-csp)kullanın.</span><span class="sxs-lookup"><span data-stu-id="fc996-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="fc996-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="fc996-173">**PPKG**</span></span> 
    1. <span data-ttu-id="fc996-174">Windows yapılandırma tasarımcısını aç</span><span class="sxs-lookup"><span data-stu-id="fc996-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="fc996-175">gelişmiş sağlama ' ya tıklayın, yeni Project adını girin ve ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="fc996-176">Windows Holographic (HoloLens 2) öğesini seçin ve ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="fc996-177">PPKG 'nizi (isteğe bağlı) içeri aktarın ve son ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="fc996-178">çalışma zamanı Ayarlar-> bağlantı profilleri-> wlan-> wlan Proxy 'yi genişletin.</span><span class="sxs-lookup"><span data-stu-id="fc996-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="fc996-179">Wi-Fi ağınızın SSID 'sini girin ve Ekle ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="fc996-180">Sol penceredeki Wi-Fi ağınızı seçin ve istediğiniz özelleştirmeleri girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="fc996-181">Etkin özelleştirmeler sol menüde kalın olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="fc996-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="fc996-182">Kaydet ve çıkış ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="fc996-183">Sağlama paketini HoloLens [uygulayın](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) .</span><span class="sxs-lookup"><span data-stu-id="fc996-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="fc996-184">[csp 'ler](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) , hem Microsoft Intune hem de Microsoft dışı MDM hizmet sağlayıcılarının Windows 10 için yönetim görevlerinin ve ilkelerinin çoğundan daha gerisinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="fc996-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="fc996-185">ayrıca, bir [sağlama paketi](/windows/configuration/provisioning-packages/provisioning-packages) oluşturmak ve bunu HoloLens 2 ' ye uygulamak için [Windows yapılandırma tasarımcısı](/windows/configuration/provisioning-packages/provisioning-install-icd) ' nı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc996-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="fc996-186">HoloLens 2 ' ye uygulanacak en olası csp 'ler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="fc996-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="fc996-187">[WIFI CSP](/windows/client-management/mdm/wifi-csp): profil başına Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="fc996-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="fc996-188">HoloLens cihazlarda desteklenen diğer csp 'ler</span><span class="sxs-lookup"><span data-stu-id="fc996-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="fc996-189">VPN</span><span class="sxs-lookup"><span data-stu-id="fc996-189">VPN</span></span>
<span data-ttu-id="fc996-190">VPN bağlantısı, şirketinizin ağına ve Internet 'e daha güvenli bir bağlantı ve erişim sağlamaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="fc996-191">HoloLens 2, yerleşik vpn istemcisi ve Evrensel Windows Platformu (UWP) vpn eklentisini destekler.</span><span class="sxs-lookup"><span data-stu-id="fc996-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="fc996-192">Desteklenen yerleşik VPN protokolleri:</span><span class="sxs-lookup"><span data-stu-id="fc996-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="fc996-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="fc996-193">IKEv2</span></span>
- <span data-ttu-id="fc996-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="fc996-194">L2TP</span></span>
- <span data-ttu-id="fc996-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="fc996-195">PPTP</span></span>

<span data-ttu-id="fc996-196">Sertifika, yerleşik VPN istemcisi için kimlik doğrulaması için kullanılıyorsa, gerekli istemci sertifikasının Kullanıcı sertifika deposuna eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="fc996-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="fc996-197">3. taraf vpn eklentisinin HoloLens 2 ' yi destekleyip desteklemediğini bulmak için, mağaza ' ya giderek vpn uygulamasını bulun ve HoloLens desteklenen bir cihaz olarak listelenip listelenmediğini ve sistem gereksinimi sayfasında, uygulamanın ARM veya ARM64 mimarisini destekleyip desteklemediğini denetleyin.</span><span class="sxs-lookup"><span data-stu-id="fc996-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="fc996-198">HoloLens, 3. taraf VPN için yalnızca Evrensel Windows Platformu uygulamalarını destekler.</span><span class="sxs-lookup"><span data-stu-id="fc996-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="fc996-199">VPN, MDM tarafından [Ayarlar/allowvpn](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla yönetilebilir ve [Vpnv2-csp ilkesi](/windows/client-management/mdm/vpnv2-csp)aracılığıyla ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="fc996-200">[Bu KıLAVUZLARLA](/windows/security/identity-protection/vpn/vpn-guide) [VPN yapılandırma](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="fc996-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="fc996-201">Kullanıcı arabirimi aracılığıyla VPN</span><span class="sxs-lookup"><span data-stu-id="fc996-201">VPN via UI</span></span>

<span data-ttu-id="fc996-202">vpn varsayılan olarak etkinleştirilmemiştir, ancak **Ayarlar** uygulaması açılarak ve **ağ & Internet-> VPN**'ye gidilerek el ile etkinleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="fc996-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="fc996-203">Bir VPN sağlayıcısı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="fc996-204">Bir bağlantı adı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="fc996-204">Create a connection name.</span></span> 
1. <span data-ttu-id="fc996-205">Sunucu adınızı veya adresinizi girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="fc996-206">VPN türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-206">Select the VPN type.</span></span>
1. <span data-ttu-id="fc996-207">Oturum açma bilgilerinin türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="fc996-208">İsteğe bağlı olarak Kullanıcı adı ve parola ekleyin.</span><span class="sxs-lookup"><span data-stu-id="fc996-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="fc996-209">VPN ayarlarını uygulayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-209">Apply the VPN settings.</span></span> 

![HoloLens VPN ayarları](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="fc996-211">Sağlama paketi aracılığıyla VPN kümesi</span><span class="sxs-lookup"><span data-stu-id="fc996-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="fc996-212">Windows Holographic, sürüm 20h2 ' de VPN bağlantısı için bir ara sunucu yapılandırma sorunu düzeltildi.</span><span class="sxs-lookup"><span data-stu-id="fc996-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="fc996-213">Bu akışı kullanmak istiyorsanız, lütfen cihazları bu yapıya yükseltmeyi göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="fc996-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="fc996-214">Windows yapılandırma tasarımcısını başlatın.</span><span class="sxs-lookup"><span data-stu-id="fc996-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="fc996-215">**HoloLens cihazları sağla**' yı ve ardından hedef **cihaz ' ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="fc996-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="fc996-216">Paket adı ve yolunu girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-216">Enter package name and path.</span></span>
1. <span data-ttu-id="fc996-217">**Gelişmiş düzenleyiciye geç ' e** tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="fc996-218">**Çalışma zamanı ayarları**  ->  **connectivityprofiles**  ->  **VPN**  ->  **vpnsettings**' i açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="fc996-219">VPNProfileName yapılandırma</span><span class="sxs-lookup"><span data-stu-id="fc996-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="fc996-220">ProfileType: **Native** veya **üçüncü taraf** seçeneğini belirleyin.</span><span class="sxs-lookup"><span data-stu-id="fc996-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="fc996-221">Yerel profil için **Nativeprotocoltype**' ı seçin, ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="fc996-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="fc996-222">"Üçüncü taraf" profili için sunucu URL 'SI, VPN eklentisi uygulama paketi aile adı (yalnızca 3 önceden tanımlanmış) ve özel yapılandırma için yapılandırın.</span><span class="sxs-lookup"><span data-stu-id="fc996-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="fc996-223">Paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="fc996-223">Export your package.</span></span>
1. <span data-ttu-id="fc996-224">HoloLens Bağlan ve. ppkg dosyasını cihaza kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="fc996-225">HoloLens, Başlat menüsü açıp **Ayarlar**  ->  **hesap**  ->  **erişimi iş veya okul**  ->  **sağlama paketi ekle veya kaldır** ' ı seçerek vpn. ppkg 'yi uygulayın-> VPN paketinizi seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="fc996-226">Intune aracılığıyla VPN ayarlama</span><span class="sxs-lookup"><span data-stu-id="fc996-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="fc996-227">Başlamak için Intune belgelerini izlemeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="fc996-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="fc996-228">bu adımları izleyerek lütfen HoloLens cihazların desteklediği yerleşik VPN protokollerini aklınızda bulundurun.</span><span class="sxs-lookup"><span data-stu-id="fc996-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="fc996-229">[Intune 'DA VPN sunucularına bağlanmak IÇIN VPN profilleri oluşturun](/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="fc996-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="fc996-230">[ıntune kullanarak VPN bağlantıları eklemek için Windows 10 ve Windows cihaz ayarlarını](/mem/intune/configuration/vpn-settings-windows-10)kullanın.</span><span class="sxs-lookup"><span data-stu-id="fc996-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="fc996-231">İşiniz bittiğinde [, lütfen profili atamayı](/mem/intune/configuration/device-profile-assign)unutmayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="fc996-232">3. taraf MDM çözümleri aracılığıyla VPN</span><span class="sxs-lookup"><span data-stu-id="fc996-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="fc996-233">3. taraf VPN bağlantısı örneği:</span><span class="sxs-lookup"><span data-stu-id="fc996-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="fc996-234">Yerel IKEv2 VPN örneği:</span><span class="sxs-lookup"><span data-stu-id="fc996-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="fc996-235">HoloLens Wi-Fi devre dışı bırakma (1. genel)</span><span class="sxs-lookup"><span data-stu-id="fc996-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="fc996-236">HoloLens Ayarlar uygulamasını kullanma</span><span class="sxs-lookup"><span data-stu-id="fc996-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="fc996-237">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fc996-238">**başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fc996-239">**Ayarlar** uygulama, sizin için otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="fc996-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fc996-240">**Internet & ağı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fc996-241">**Kapalı** konuma taşımak için Wi-Fi kaydırıcı anahtarını seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="fc996-242">Bu, Wi-Fi radyoın RF bileşenlerini kapatır ve HoloLens tüm Wi-Fi işlevlerini devre dışı bırakır.</span><span class="sxs-lookup"><span data-stu-id="fc996-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="fc996-243">Wi-Fi radyo devre dışı bırakıldığında, HoloLens otomatik olarak bu [alanları](hololens-spaces.md)yükleyemeyecektir.</span><span class="sxs-lookup"><span data-stu-id="fc996-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="fc996-244">Wi-Fi Radyoyu açmak ve Microsoft HoloLens Wi-Fi işlevselliğini geri yüklemek için kaydırıcı anahtarını **Açık** konuma taşıyın.</span><span class="sxs-lookup"><span data-stu-id="fc996-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="fc996-245">Seçilen Wi-Fi radyo durumu (**Açık** veya **kapalı**), yeniden başlatmalar arasında kalır.</span><span class="sxs-lookup"><span data-stu-id="fc996-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="fc996-246">Wi-Fi ağda HoloLens IP adresini tanımlama</span><span class="sxs-lookup"><span data-stu-id="fc996-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="fc996-247">Ayarlar uygulamasını kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc996-247">By using the Settings app</span></span>

1. <span data-ttu-id="fc996-248">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fc996-249">**başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fc996-250">**Ayarlar** uygulama, sizin için otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="fc996-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fc996-251">**Internet & ağı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fc996-252">Kullanılabilir Wi-Fi ağları listesinin altına aşağı kaydırın ve **donanım özellikleri**' ni seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi ayarlarındaki donanım özellikleri](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="fc996-254">IP adresi, **IPv4 adresi**' nin yanında görünür.</span><span class="sxs-lookup"><span data-stu-id="fc996-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="fc996-255">Sesli komutları kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc996-255">By using voice commands</span></span>

<span data-ttu-id="fc996-256">cihazlarınıza bağlı olarak, ıp adresinizi göstermek için yerleşik sesli komutları veya Cortana kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc996-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="fc996-257">[19041,1103](hololens-release-notes.md#windows-holographic-version-2004) konuşduktan sonra "IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="fc996-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="fc996-258">ve görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="fc996-258">and it will be displayed.</span></span> <span data-ttu-id="fc996-259">önceki derlemeler veya HoloLens (1. gen) için "Hey Cortana, ıp adresim nedir?" deyin</span><span class="sxs-lookup"><span data-stu-id="fc996-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="fc996-260">Cortana, ıp adresinizi görüntüler ve okur.</span><span class="sxs-lookup"><span data-stu-id="fc996-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="fc996-261">Windows cihaz portalını kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc996-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="fc996-262">Bilgisayarınızdaki bir Web tarayıcısında [cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal.md#networking)açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="fc996-263">**Ağ** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="fc996-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="fc996-264">Bu bölüm, IP adresinizi ve diğer ağ bilgilerini görüntüler.</span><span class="sxs-lookup"><span data-stu-id="fc996-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="fc996-265">Bu yöntemi kullanarak, IP adresini geliştirme bilgisayarınızda kopyalayabilir ve yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc996-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="fc996-266">IP adresini statik adres olarak değiştir</span><span class="sxs-lookup"><span data-stu-id="fc996-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="fc996-267">Ayarlar kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc996-267">By using Settings</span></span>
 
1. <span data-ttu-id="fc996-268">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="fc996-269">**başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="fc996-270">**Ayarlar** uygulama, sizin için otomatik olarak eklenir.</span><span class="sxs-lookup"><span data-stu-id="fc996-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="fc996-271">**Internet & ağı**' nı seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="fc996-272">Kullanılabilir Wi-Fi ağları listesinin altına aşağı kaydırın ve **donanım özellikleri**' ni seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="fc996-273">**IP ayarlarını Düzenle** penceresinde, Ilk alanı **el ile** olarak değiştirin.</span><span class="sxs-lookup"><span data-stu-id="fc996-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="fc996-274">İstenen IP yapılandırmasını kalan alanlara girin ve **Kaydet**' e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="fc996-275">Windows cihaz portalını kullanarak</span><span class="sxs-lookup"><span data-stu-id="fc996-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="fc996-276">Bilgisayarınızdaki bir Web tarayıcısında [cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal.md#networking)açın.</span><span class="sxs-lookup"><span data-stu-id="fc996-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="fc996-277">**Ağ** bölümüne gidin.</span><span class="sxs-lookup"><span data-stu-id="fc996-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="fc996-278">**IPv4 yapılandırma** düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="fc996-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="fc996-279">**AŞAĞıDAKI IP adresini kullan** ' ı seçin ve istenen TCP/IP yapılandırmasını girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="fc996-280">**AŞAĞıDAKI DNS sunucusu adreslerini kullan** ' ı seçin ve gerekirse tercih edilen ve alternatif DNS sunucusu adreslerini girin.</span><span class="sxs-lookup"><span data-stu-id="fc996-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="fc996-281">**Kaydet**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="fc996-281">Click **Save**.</span></span> 
