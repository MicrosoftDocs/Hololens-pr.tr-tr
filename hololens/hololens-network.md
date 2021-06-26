---
title: HoloLens 'i ağa bağlama
description: HoloLens ile internet 'i ayarlamayı ve bağlamayı ve cihaz IP adresini nasıl tanımlacağınızı öğrenin.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, WiFi, Kablosuz, internet, IP, IP adresi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923610"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="3276a-104">HoloLens 'i ağa bağlama</span><span class="sxs-lookup"><span data-stu-id="3276a-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="3276a-105">HoloLens 'te birçok şeyi yapmak için bir ağa bağlı olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="3276a-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="3276a-106">HoloLens, 802.11 AC özellikli, 2x2 Wi-Fi radyo ve bir ağa bağlamak bir Windows 10 Masaüstü veya mobil cihazı bir Wi-Fi ağına bağlamaya benzer.</span><span class="sxs-lookup"><span data-stu-id="3276a-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="3276a-107">Bu kılavuz şunları yapmanıza yardımcı olur:</span><span class="sxs-lookup"><span data-stu-id="3276a-107">This guide will help you:</span></span>

- <span data-ttu-id="3276a-108">Wi-Fi kullanarak bir ağa bağlanma veya yalnızca HoloLens 2 için USB-C üzerinden doğrudan veya Ethernet Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3276a-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="3276a-109">Wi-Fi devre dışı bırakıp yeniden etkinleştirin</span><span class="sxs-lookup"><span data-stu-id="3276a-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="3276a-110">[HoloLens 'i çevrimdışı kullanma](hololens-offline.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="3276a-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="3276a-111">İlk kez bağlanıyor</span><span class="sxs-lookup"><span data-stu-id="3276a-111">Connecting for the first time</span></span>

<span data-ttu-id="3276a-112">HoloLens 'i ilk kez kullandığınızda bir Wi-Fi ağa bağlanarak size kılavuzluk edilecek.</span><span class="sxs-lookup"><span data-stu-id="3276a-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="3276a-113">Kurulum sırasında Wi-Fi bağlanmada sorun yaşıyorsanız, ağınızın açık, parola korumalı bir ağ ya da bir açıklamalı Portal ağı olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="3276a-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="3276a-114">Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmediğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="3276a-115">Kurulumdan sonra, diğer Wi-Fi ağları türlerine bağlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="3276a-116">HoloLens 2 cihazlarında, bir Kullanıcı, cihazı ayarlamaya yardımcı olmak üzere Wi-Fi doğrudan bağlanmak için [BIR USB-C-Ethernet bağdaştırıcısı da kullanabilir](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) .</span><span class="sxs-lookup"><span data-stu-id="3276a-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="3276a-117">Cihaz ayarlandıktan sonra, bir Kullanıcı bağdaştırıcıyı kullanmaya devam edebilir ya da cihazın bağdaştırıcı bağlantısını kesebilir ve ayarladıktan [sonra Wi-Fi 'a bağlanabilir](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="3276a-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="3276a-118">Kurulumdan sonra Wi-Fi bağlanma</span><span class="sxs-lookup"><span data-stu-id="3276a-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="3276a-119">**Başlangıç hareketini** önceden yapın ve **Ayarlar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="3276a-120">Ayarlar uygulaması sizin için otomatik olarak yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3276a-121">**Internet**  >  **Wi-Fi**& ağ ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="3276a-122">Wi-Fi’ın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="3276a-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="3276a-123">Ağınızı görmüyorsanız listede aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="3276a-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="3276a-124">Bir ağ seçin ve ardından **Bağlan**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="3276a-125">Bir ağ parolası istenirse bu dosyayı yazın ve ardından **İleri**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi ayarları](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="3276a-127">Wi-Fi ağa bağlı olduğunu doğrulamak için, **Başlangıç** menüsündeki Wi-Fi durumunu kontrol edin:</span><span class="sxs-lookup"><span data-stu-id="3276a-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="3276a-128">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="3276a-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3276a-129">Wi-Fi durum için **Başlangıç** menüsünün sol üst kısmına bakın.</span><span class="sxs-lookup"><span data-stu-id="3276a-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="3276a-130">Wi-Fi durumu ve bağlı ağın SSID 'SI gösterilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="3276a-131">Wi-Fi yoksa [hücresel ve 5 g ağlarına da bağlanabilirsiniz](hololens-cellular.md).</span><span class="sxs-lookup"><span data-stu-id="3276a-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3276a-132">Tasarım, kullanıcılar, HoloLens 2 ' nin Wi-Fi gezici davranışını ince ayarlayamez. **Wi-Fi listesini yenilemenin tek yolu Wi-Fi kapalı ve açık olarak geçiş yapmaz**.</span><span class="sxs-lookup"><span data-stu-id="3276a-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="3276a-133">Bu, bir cihazın Aralık dışına çıkdıktan sonra bir AP 'ye "takılı" kalabileceği gibi birçok sorunu önler.</span><span class="sxs-lookup"><span data-stu-id="3276a-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="3276a-134">HoloLens 'i kurumsal Wi-Fi ağa bağlama</span><span class="sxs-lookup"><span data-stu-id="3276a-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="3276a-135">Kurumsal Wi-Fi profilleri, Wi-Fi bağlantılarının kimliğini doğrulamak için Genişletilebilir Kimlik Doğrulama Protokolü (EAP) kullanır.</span><span class="sxs-lookup"><span data-stu-id="3276a-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="3276a-136">HoloLens kurumsal Wi-Fi profili, [Windows yapılandırma Tasarımcısı](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)tarafından oluşturulan MDM veya sağlama paketi aracılığıyla yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="3276a-137">Microsoft Intune yönetilen cihaz için yapılandırma yönergeleri için [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 'a bakın.</span><span class="sxs-lookup"><span data-stu-id="3276a-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="3276a-138">WCD 'de Wi-Fi sağlama paketi oluşturmak için, önceden yapılandırılmış bir Wi-Fi profili .xml dosyası gereklidir.</span><span class="sxs-lookup"><span data-stu-id="3276a-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="3276a-139">EAP-TLS kimlik doğrulaması ile WPA2-Enterprise için örnek bir Wi-Fi profili aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="3276a-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="3276a-140">Sunucu kök CA sertifikası ve istemci sertifikasının, EAP türüne bağlı olarak cihazda sağlanması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="3276a-141">Ek kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="3276a-141">Additional resources:</span></span>

- <span data-ttu-id="3276a-142">WLANv1Profile şeması: [[MS-GPWL]: Kablosuz LAN profili v1 şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="3276a-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="3276a-143">EAP-TLS şeması: [[MS-GPWL]: MICROSOFT EAP TLS şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="3276a-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="3276a-144">Wi-Fi 'nize bağlanmakta sorun yaşıyorsanız [sorun giderme](hololens2-enterprise-troubleshooting.md#) sayfamızı denetleyin.</span><span class="sxs-lookup"><span data-stu-id="3276a-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="3276a-145">Ağ ara sunucusunu yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3276a-145">Configure Network Proxy</span></span>

<span data-ttu-id="3276a-146">Bu bölümde, HoloLens OS ve Windows HTTP Stack kullanan Evrensel Windows Platformu (UWP) uygulamaları için ağ proxy 'si ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="3276a-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="3276a-147">Windows dışı HTTP yığını kullanan uygulamaların kendi proxy yapılandırması ve işlemesi olabilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="3276a-148">Proxy yapılandırması</span><span class="sxs-lookup"><span data-stu-id="3276a-148">Proxy Configurations</span></span> 

- <span data-ttu-id="3276a-149">Proxy otomatik yapılandırma (PAC) betiği: bir [pac dosyası](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft dışı bir site açar), FindProxyForURL (URL, ana bilgisayar) JavaScript işlevini içerir.</span><span class="sxs-lookup"><span data-stu-id="3276a-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="3276a-150">Statik proxy: sunucu: bağlantı noktası biçiminde.</span><span class="sxs-lookup"><span data-stu-id="3276a-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="3276a-151">Web proxy otomatik bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla proxy yapılandırma dosyasının URL 'sini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="3276a-152">Proxy sağlama yöntemleri</span><span class="sxs-lookup"><span data-stu-id="3276a-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="3276a-153">Proxy 'lerin sağlanması için üç yol vardır:</span><span class="sxs-lookup"><span data-stu-id="3276a-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="3276a-154">**Ayarlar Kullanıcı arabirimi:**</span><span class="sxs-lookup"><span data-stu-id="3276a-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="3276a-155">Kullanıcı başına proxy (20H2 veya önceki sürümler):</span><span class="sxs-lookup"><span data-stu-id="3276a-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="3276a-156">Başlat menüsünü açın ve Ayarlar ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="3276a-157">Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="3276a-158">, El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.</span><span class="sxs-lookup"><span data-stu-id="3276a-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="3276a-159">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="3276a-160">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-160">Enter the port number.</span></span>
        6. <span data-ttu-id="3276a-161">Kaydet’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-161">Click Save.</span></span>
      1. <span data-ttu-id="3276a-162">WiFi proxy (21H1 veya üzeri):</span><span class="sxs-lookup"><span data-stu-id="3276a-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="3276a-163">Başlat menüsünü açın ve Wi-Fi ağınızın Özellikler sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="3276a-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="3276a-164">Aşağı kaydırarak ara sunucu</span><span class="sxs-lookup"><span data-stu-id="3276a-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="3276a-165">El Ile kuruluma geçiş yapın</span><span class="sxs-lookup"><span data-stu-id="3276a-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="3276a-166">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="3276a-167">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-167">Enter the port number.</span></span>
          1. <span data-ttu-id="3276a-168">Uygula ' ya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="3276a-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="3276a-169">**MDM**</span></span> 
     1. <span data-ttu-id="3276a-170">Intune-Intune 'da proxy yapılandırmak için bu [adımları](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) kullanın.</span><span class="sxs-lookup"><span data-stu-id="3276a-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="3276a-171">Bölümün altına kaydırmanız gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="3276a-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="3276a-172">Diğer üçüncü taraf MDM çözümleri- [WIFI CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)kullanın.</span><span class="sxs-lookup"><span data-stu-id="3276a-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="3276a-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="3276a-173">**PPKG**</span></span> 
    1. <span data-ttu-id="3276a-174">Windows yapılandırma Tasarımcısı 'Nı açın</span><span class="sxs-lookup"><span data-stu-id="3276a-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="3276a-175">Gelişmiş sağlama ' ya tıklayın, yeni projeniz için bir ad girin ve Ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="3276a-176">Windows holographic (HoloLens 2) öğesini seçin ve Ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="3276a-177">PPKG 'nizi (isteğe bağlı) içeri aktarın ve son ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="3276a-178">Çalışma zamanı ayarları-> bağlantı profilleri ' ni > WLAN-> WLAN proxy 'Si.</span><span class="sxs-lookup"><span data-stu-id="3276a-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="3276a-179">Wi-Fi ağınızın SSID 'sini girin ve Ekle ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="3276a-180">Sol penceredeki Wi-Fi ağınızı seçin ve istediğiniz özelleştirmeleri girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="3276a-181">Etkin özelleştirmeler sol menüde kalın olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="3276a-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="3276a-182">Kaydet ve çıkış ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="3276a-183">Sağlama paketini HoloLens 'e [uygulayın](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) .</span><span class="sxs-lookup"><span data-stu-id="3276a-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="3276a-184">[CSP 'ler](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) , hem Microsoft Intune hem de MICROSOFT dışı MDM hizmet sağlayıcılarındaki Windows 10 için yönetim görevlerinin ve ilkelerinin çoğundan daha gerisinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="3276a-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="3276a-185">Ayrıca, bir [sağlama paketi](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) oluşturmak ve bunu HoloLens 2 ' ye uygulamak Için [Windows yapılandırma Tasarımcısı](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) ' nı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="3276a-186">HoloLens 2 ' ye uygulanacak en olası CSP 'Ler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="3276a-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="3276a-187">[WIFI CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): profil başına Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="3276a-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="3276a-188">HoloLens cihazlarında desteklenen diğer CSP 'Ler</span><span class="sxs-lookup"><span data-stu-id="3276a-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="3276a-189">VPN</span><span class="sxs-lookup"><span data-stu-id="3276a-189">VPN</span></span>
<span data-ttu-id="3276a-190">VPN bağlantısı, şirketinizin ağına ve Internet 'e daha güvenli bir bağlantı ve erişim sağlamaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="3276a-191">HoloLens 2 yerleşik VPN istemcisi ve Evrensel Windows Platformu (UWP) VPN eklentisini destekler.</span><span class="sxs-lookup"><span data-stu-id="3276a-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="3276a-192">Desteklenen yerleşik VPN protokolleri:</span><span class="sxs-lookup"><span data-stu-id="3276a-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="3276a-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="3276a-193">IKEv2</span></span>
- <span data-ttu-id="3276a-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="3276a-194">L2TP</span></span>
- <span data-ttu-id="3276a-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="3276a-195">PPTP</span></span>

<span data-ttu-id="3276a-196">Sertifika, yerleşik VPN istemcisi için kimlik doğrulaması için kullanılıyorsa, gerekli istemci sertifikasının Kullanıcı sertifika deposuna eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="3276a-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="3276a-197">Bir 3. taraf VPN eklentisinin HoloLens 2 ' yi destekleyip desteklemediğini bulmak için, Mağaza ' ya giderek VPN uygulamasını bulun ve HoloLens 'in desteklenen bir cihaz olarak listelenip listelenmediğini denetleyin ve uygulama ARM veya ARM64 mimarisini destekler.</span><span class="sxs-lookup"><span data-stu-id="3276a-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="3276a-198">HoloLens yalnızca 3. taraf VPN için Evrensel Windows Platformu uygulamalarını destekler.</span><span class="sxs-lookup"><span data-stu-id="3276a-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="3276a-199">VPN, [Ayarlar/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla MDM tarafından yönetilebilir ve  [Vpnv2-CSP ilkesi](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)aracılığıyla ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="3276a-200">[Bu KıLAVUZLARLA](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) [VPN yapılandırma](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="3276a-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="3276a-201">Kullanıcı arabirimi üzerinden VPN</span><span class="sxs-lookup"><span data-stu-id="3276a-201">VPN via UI</span></span>

<span data-ttu-id="3276a-202">VPN varsayılan olarak etkin değildir, ancak  Ayarlar uygulaması açarak ve İnternet **-& VPN'e > etkinleştirilebilir.**</span><span class="sxs-lookup"><span data-stu-id="3276a-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="3276a-203">Bir VPN sağlayıcısı seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="3276a-204">Bağlantı adı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="3276a-204">Create a connection name.</span></span> 
1. <span data-ttu-id="3276a-205">Sunucu adı veya adresinizi girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="3276a-206">VPN türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-206">Select the VPN type.</span></span>
1. <span data-ttu-id="3276a-207">Oturum açma bilgileri türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="3276a-208">İsteğe bağlı olarak kullanıcı adı ve parola ekleyin.</span><span class="sxs-lookup"><span data-stu-id="3276a-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="3276a-209">VPN ayarlarını uygulama.</span><span class="sxs-lookup"><span data-stu-id="3276a-209">Apply the VPN settings.</span></span> 

![HoloLens VPN ayarları](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="3276a-211">Sağlama Paketi aracılığıyla VPN kümesi</span><span class="sxs-lookup"><span data-stu-id="3276a-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="3276a-212">Windows Holographic sürüm 20H2'de VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi.</span><span class="sxs-lookup"><span data-stu-id="3276a-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="3276a-213">Bu akışı kullanmak için lütfen cihazları bu derlemeye yükseltmeyi göz önünde bulundurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="3276a-214">Windows Yapılandırma Tasarımcısı'ı başlatma.</span><span class="sxs-lookup"><span data-stu-id="3276a-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="3276a-215">**HoloLens cihazlarını sağlama'ya tıklayın,** ardından hedef cihazı ve Sonraki'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="3276a-216">Paket adını ve yolunu girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-216">Enter package name and path.</span></span>
1. <span data-ttu-id="3276a-217">Gelişmiş **düzenleyiciye geç'e tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="3276a-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="3276a-218">Çalışma **zamanı ayarları**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings'i açın.**</span><span class="sxs-lookup"><span data-stu-id="3276a-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="3276a-219">VPNProfileName yapılandırma</span><span class="sxs-lookup"><span data-stu-id="3276a-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="3276a-220">Profil Türü: Yerel **veya Üçüncü** **Taraf'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="3276a-221">Yerel profil için **NativeProtocolType'ı seçin,** ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="3276a-222">"Üçüncü Taraf" profili için sunucu URL'sini, VPN eklentisi Uygulama paketi aile adını (önceden tanımlanmış yalnızca 3) ve özel yapılandırmaları yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="3276a-223">Paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="3276a-223">Export your package.</span></span>
1. <span data-ttu-id="3276a-224">HoloLens'inizi bağlama ve .ppkg dosyasını cihaza kopyalama.</span><span class="sxs-lookup"><span data-stu-id="3276a-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="3276a-225">HoloLens'de, Başlat menüsü'yi açarak ve Ayarlar Hesap Erişimi iş veya okul Sağlama paketi ekleme veya kaldırma -> VPN paketinizi seçin'i seçerek VPN .ppkg'yi  ->    ->    ->   uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="3276a-226">Intune aracılığıyla VPN ayarlama</span><span class="sxs-lookup"><span data-stu-id="3276a-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="3276a-227">Çalışmaya devam etmek için Intune belgelerini takip edin.</span><span class="sxs-lookup"><span data-stu-id="3276a-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="3276a-228">Bu adımları takip edin ve HoloLens cihazlarının desteklemektedir yerleşik VPN protokollerini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="3276a-229">[Intune'da VPN sunucularına bağlanmak için VPN profilleri oluşturun.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="3276a-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="3276a-230">Windows 10 kullanarak VPN bağlantıları eklemek için Windows [Holographic cihaz ayarlarını kullanın.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="3276a-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="3276a-231">Bittiğinde lütfen profilini [atamayı unutmayın.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="3276a-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="3276a-232">3. taraf MDM çözümleri aracılığıyla VPN</span><span class="sxs-lookup"><span data-stu-id="3276a-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="3276a-233">3. taraf VPN bağlantısı örneği:</span><span class="sxs-lookup"><span data-stu-id="3276a-233">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="3276a-234">Yerel IKEv2 VPN örneği:</span><span class="sxs-lookup"><span data-stu-id="3276a-234">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="3276a-235">HoloLens'Wi-Fi devre dışı bırakma (1. nesil)</span><span class="sxs-lookup"><span data-stu-id="3276a-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="3276a-236">HoloLens'de Ayarlar uygulamasını kullanma</span><span class="sxs-lookup"><span data-stu-id="3276a-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="3276a-237">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="3276a-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3276a-238">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3276a-239">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3276a-240">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3276a-241">Kaydırıcıyı Wi-Fi kaydırıcısını seçerek Kapalı **konuma taşıyın.**</span><span class="sxs-lookup"><span data-stu-id="3276a-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="3276a-242">Bu, holoLens'de Wi-Fi rf bileşenlerini devre dışı Wi-Fi devre dışı bıraktır.</span><span class="sxs-lookup"><span data-stu-id="3276a-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3276a-243">Sanal Wi-Fi devre dışı bırakılmıştır, HoloLens alanlarınızı otomatik olarak [yükemez.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="3276a-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="3276a-244">Kaydırıcı anahtarını Açık konuma **hareket ettirerek** Wi-Fi açma ve Wi-Fi geri yükleme işlevlerini Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3276a-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="3276a-245">Seçilen radyo Wi-Fi ( Açık **veya Kapalı)** yeniden başlatmalarda kalıcı olur. </span><span class="sxs-lookup"><span data-stu-id="3276a-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="3276a-246">Sanal ağ üzerinde HoloLens'inizin IP Wi-Fi tanımlama</span><span class="sxs-lookup"><span data-stu-id="3276a-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="3276a-247">Ayarlar uygulamasını kullanarak</span><span class="sxs-lookup"><span data-stu-id="3276a-247">By using the Settings app</span></span>

1. <span data-ttu-id="3276a-248">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="3276a-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3276a-249">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3276a-250">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3276a-251">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3276a-252">Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi ayarlarında donanım özellikleri](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="3276a-254">IP adresi, **IPv4 adresinin yanında görünür.**</span><span class="sxs-lookup"><span data-stu-id="3276a-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="3276a-255">Ses komutlarını kullanarak</span><span class="sxs-lookup"><span data-stu-id="3276a-255">By using voice commands</span></span>

<span data-ttu-id="3276a-256">Cihaz derlemenize bağlı olarak, ip adresinizi görüntülemek için yerleşik sesli komutları veya Cortana'yı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="3276a-257">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sonrasındaki derlemelerde "IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="3276a-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="3276a-258">görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="3276a-258">and it will be displayed.</span></span> <span data-ttu-id="3276a-259">Önceki derlemeler veya HoloLens (1. nesil) için "Hey Cortana, IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="3276a-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="3276a-260">Cortana IP adresinizi görüntüler ve okur.</span><span class="sxs-lookup"><span data-stu-id="3276a-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="3276a-261">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="3276a-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="3276a-262">Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="3276a-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="3276a-263">Ağ **bölümüne** gidin.</span><span class="sxs-lookup"><span data-stu-id="3276a-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="3276a-264">Bu bölümde IP adresiniz ve diğer ağ bilgileri görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="3276a-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="3276a-265">Bu yöntemi kullanarak IP adresini kopyalayıp geliştirme bilgisayarınıza yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3276a-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="3276a-266">IP Adresini statik adres olarak değiştirme</span><span class="sxs-lookup"><span data-stu-id="3276a-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="3276a-267">Ayarlar'ı kullanarak</span><span class="sxs-lookup"><span data-stu-id="3276a-267">By using Settings</span></span>
 
1. <span data-ttu-id="3276a-268">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="3276a-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="3276a-269">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="3276a-270">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="3276a-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="3276a-271">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="3276a-272">Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="3276a-273">IP **ayarlarını düzenle penceresinde** ilk alanı El ile olarak **değiştirin.**</span><span class="sxs-lookup"><span data-stu-id="3276a-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="3276a-274">Kalan alanlara istenen IP yapılandırmasını girin ve Kaydet'e **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="3276a-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="3276a-275">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="3276a-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="3276a-276">Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="3276a-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="3276a-277">Ağ **bölümüne** gidin.</span><span class="sxs-lookup"><span data-stu-id="3276a-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="3276a-278">**IPv4 Yapılandırması düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="3276a-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="3276a-279">Aşağıdaki **IP adresini kullan'ı seçin** ve istediğiniz TCP/IP yapılandırmasını girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="3276a-280">Aşağıdaki **DNS sunucusu adreslerini kullan'ı seçin** ve gerekirse Tercih edilen ve Alternatif DNS sunucusu adreslerini girin.</span><span class="sxs-lookup"><span data-stu-id="3276a-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="3276a-281">**Kaydet**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="3276a-281">Click **Save**.</span></span> 
