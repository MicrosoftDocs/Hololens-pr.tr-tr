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
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380228"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="920fe-104">HoloLens 'i ağa bağlama</span><span class="sxs-lookup"><span data-stu-id="920fe-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="920fe-105">HoloLens 'te birçok şeyi yapmak için bir ağa bağlı olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="920fe-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="920fe-106">HoloLens, 802.11 AC özellikli, 2x2 Wi-Fi radyo ve bir ağa bağlamak bir Windows 10 Masaüstü veya mobil cihazı bir Wi-Fi ağına bağlamaya benzer.</span><span class="sxs-lookup"><span data-stu-id="920fe-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="920fe-107">Bu kılavuz şunları yapmanıza yardımcı olur:</span><span class="sxs-lookup"><span data-stu-id="920fe-107">This guide will help you:</span></span>

- <span data-ttu-id="920fe-108">Wi-Fi kullanarak bir ağa bağlanma veya yalnızca HoloLens 2 için USB-C üzerinden doğrudan veya Ethernet Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="920fe-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="920fe-109">Wi-Fi devre dışı bırakıp yeniden etkinleştirin</span><span class="sxs-lookup"><span data-stu-id="920fe-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="920fe-110">[HoloLens 'i çevrimdışı kullanma](hololens-offline.md)hakkında daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="920fe-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="920fe-111">İlk kez bağlanıyor</span><span class="sxs-lookup"><span data-stu-id="920fe-111">Connecting for the first time</span></span>

<span data-ttu-id="920fe-112">HoloLens 'i ilk kez kullandığınızda bir Wi-Fi ağa bağlanarak size kılavuzluk edilecek.</span><span class="sxs-lookup"><span data-stu-id="920fe-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="920fe-113">Kurulum sırasında Wi-Fi bağlanmada sorun yaşıyorsanız, ağınızın açık, parola korumalı bir ağ ya da bir açıklamalı Portal ağı olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="920fe-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="920fe-114">Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmediğini doğrulayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="920fe-115">Kurulumdan sonra, diğer Wi-Fi ağları türlerine bağlanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="920fe-116">HoloLens 2 cihazlarında, bir Kullanıcı, cihazı ayarlamaya yardımcı olmak üzere Wi-Fi doğrudan bağlanmak için [BIR USB-C-Ethernet bağdaştırıcısı da kullanabilir](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) .</span><span class="sxs-lookup"><span data-stu-id="920fe-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="920fe-117">Cihaz ayarlandıktan sonra, bir Kullanıcı bağdaştırıcıyı kullanmaya devam edebilir ya da cihazın bağdaştırıcı bağlantısını kesebilir ve ayarladıktan [sonra Wi-Fi 'a bağlanabilir](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="920fe-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="920fe-118">Kurulumdan sonra Wi-Fi bağlanma</span><span class="sxs-lookup"><span data-stu-id="920fe-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="920fe-119">**Başlangıç hareketini** önceden yapın ve **Ayarlar**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="920fe-120">Ayarlar uygulaması sizin için otomatik olarak yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="920fe-121">**Internet**  >  **Wi-Fi**& ağ ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="920fe-122">Wi-Fi’ın açık olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="920fe-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="920fe-123">Ağınızı görmüyorsanız listede aşağı kaydırın.</span><span class="sxs-lookup"><span data-stu-id="920fe-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="920fe-124">Bir ağ seçin ve ardından **Bağlan**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="920fe-125">Bir ağ parolası istenirse bu dosyayı yazın ve ardından **İleri**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi ayarları](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="920fe-127">Wi-Fi ağa bağlı olduğunu doğrulamak için, **Başlangıç** menüsündeki Wi-Fi durumunu kontrol edin:</span><span class="sxs-lookup"><span data-stu-id="920fe-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="920fe-128">**Başlat** menüsünü açın.</span><span class="sxs-lookup"><span data-stu-id="920fe-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="920fe-129">Wi-Fi durum için **Başlangıç** menüsünün sol üst kısmına bakın.</span><span class="sxs-lookup"><span data-stu-id="920fe-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="920fe-130">Wi-Fi durumu ve bağlı ağın SSID 'SI gösterilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="920fe-131">Wi-Fi yoksa [hücresel ve 5 g ağlarına da bağlanabilirsiniz](https://docs.microsoft.com/hololens/hololens-cellular).</span><span class="sxs-lookup"><span data-stu-id="920fe-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="920fe-132">Tasarım, kullanıcılar, HoloLens 2 ' nin Wi-Fi gezici davranışını ince ayarlayamez. **Wi-Fi listesini yenilemenin tek yolu Wi-Fi kapalı ve açık olarak geçiş yapmaz**.</span><span class="sxs-lookup"><span data-stu-id="920fe-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="920fe-133">Bu, bir cihazın Aralık dışına çıkdıktan sonra bir AP 'ye "takılı" kalabileceği gibi birçok sorunu önler.</span><span class="sxs-lookup"><span data-stu-id="920fe-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="920fe-134">Wi-Fi bağlantınızın sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="920fe-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="920fe-135">Wi-Fi ' a bağlanırken sorunlarla karşılaşırsanız, bkz. [Wi-Fi ile bağlanamıyorum](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="920fe-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="920fe-136">Cihazdaki bir kuruluşta veya kurumsal hesapta oturum açtığınızda, ilke BT yöneticiniz tarafından yapılandırılmışsa mobil cihaz yönetimi (MDM) ilkesi de uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="920fe-137">HoloLens 'i kurumsal Wi-Fi ağa bağlama</span><span class="sxs-lookup"><span data-stu-id="920fe-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="920fe-138">Kurumsal Wi-Fi profilleri, Wi-Fi bağlantılarının kimliğini doğrulamak için Genişletilebilir Kimlik Doğrulama Protokolü (EAP) kullanır.</span><span class="sxs-lookup"><span data-stu-id="920fe-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="920fe-139">HoloLens kurumsal Wi-Fi profili, [Windows yapılandırma Tasarımcısı](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)tarafından oluşturulan MDM veya sağlama paketi aracılığıyla yapılandırılabilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="920fe-140">Microsoft Intune yönetilen cihaz için yapılandırma yönergeleri için [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 'a bakın.</span><span class="sxs-lookup"><span data-stu-id="920fe-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="920fe-141">WCD 'de Wi-Fi sağlama paketi oluşturmak için, önceden yapılandırılmış bir Wi-Fi profili .xml dosyası gereklidir.</span><span class="sxs-lookup"><span data-stu-id="920fe-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="920fe-142">EAP-TLS kimlik doğrulaması ile WPA2-Enterprise için örnek bir Wi-Fi profili aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="920fe-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="920fe-143">Sunucu kök CA sertifikası ve istemci sertifikasının, EAP türüne bağlı olarak cihazda sağlanması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="920fe-144">Ek kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="920fe-144">Additional resources:</span></span>

- <span data-ttu-id="920fe-145">WLANv1Profile şeması: [[MS-GPWL]: Kablosuz LAN profili v1 şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="920fe-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="920fe-146">EAP-TLS şeması: [[MS-GPWL]: MICROSOFT EAP TLS şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="920fe-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="920fe-147">EAP sorunlarını giderme</span><span class="sxs-lookup"><span data-stu-id="920fe-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="920fe-148">Çoğu ağ sorunu, Wi-FI profilinde aşağıdaki 3 ayarlardan birinin yanlış olmasının sonucudur.</span><span class="sxs-lookup"><span data-stu-id="920fe-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="920fe-149">Çift denetim Wi-Fi profilinde doğru ayarlar var:</span><span class="sxs-lookup"><span data-stu-id="920fe-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="920fe-150">EAP türü doğru yapılandırılmış, ortak EAP türleri: EAP-TLS (13), EAP-TTLS (21) ve PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="920fe-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="920fe-151">Wi-Fi SSID adı doğru ve ONALTıLıK dizeyle eşleşiyor.</span><span class="sxs-lookup"><span data-stu-id="920fe-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="920fe-152">EAP-TLS için TrustedRootCA, Server&#39;s güvenilen kök CA sertifikasının SHA-1 karmasını içerir.</span><span class="sxs-lookup"><span data-stu-id="920fe-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="920fe-153">Windows bilgisayarında &quot;certutil.exe-döküm CERT \_ Dosya \_ adı &quot; komutu, BIR sertifika&#39;s SHA-1 karma dizesi gösterir.</span><span class="sxs-lookup"><span data-stu-id="920fe-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="920fe-154">EAP oturumunun nerede başarısız olduğunu öğrenmek için erişim noktası veya denetleyici ya da AAA sunucusu günlüklerinde ağ paketi yakalamayı toplayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="920fe-155">HoloLens tarafından sağlanan EAP kimliği beklenmiyorsa, kimliğin Wi-Fi profil veya istemci sertifikası aracılığıyla doğru şekilde sağlanmış olup olmadığını kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="920fe-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="920fe-156">Sunucu HoloLens istemci sertifikası 'nı reddederse, cihazda gerekli istemci sertifikasının sağlanıp sağlanmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="920fe-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="920fe-157">HoloLens sunucu sertifikasını reddederse, HoloLens üzerinde sunucu kök CA sertifikasının sağlanıp sağlanmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="920fe-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="920fe-158">Kurumsal profile Wi-Fi sağlama paketi aracılığıyla sağlandıysa, sağlama paketini bir Windows 10 BILGISAYARıNA uygulamayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="920fe-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="920fe-159">Windows 10 bilgisayarında de başarısız olursa, [Windows Client 802.1 x kimlik doğrulaması sorun giderme kılavuzunu](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)izleyin.</span><span class="sxs-lookup"><span data-stu-id="920fe-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="920fe-160">Telemetrinizi tam veya Isteğe bağlı olarak (derlemenize bağlı olarak) ayarlayın ve [Geri Bildirim Hub 'ı](https://docs.microsoft.com/hololens/hololens-feedback)aracılığıyla bize geri bildirim gönderin.</span><span class="sxs-lookup"><span data-stu-id="920fe-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="920fe-161">Ek kaynaklar:</span><span class="sxs-lookup"><span data-stu-id="920fe-161">Additional resources:</span></span>
- [<span data-ttu-id="920fe-162">Windows cihazından Wi-Fi ayarlarını dışarı aktarma</span><span class="sxs-lookup"><span data-stu-id="920fe-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="920fe-163">Ağ ara sunucusunu yapılandırma</span><span class="sxs-lookup"><span data-stu-id="920fe-163">Configure Network Proxy</span></span>

<span data-ttu-id="920fe-164">Bu bölümde, HoloLens OS ve Windows HTTP Stack kullanan Evrensel Windows Platformu (UWP) uygulamaları için ağ proxy 'si ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="920fe-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="920fe-165">Windows dışı HTTP yığını kullanan uygulamaların kendi proxy yapılandırması ve işlemesi olabilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="920fe-166">Proxy yapılandırması</span><span class="sxs-lookup"><span data-stu-id="920fe-166">Proxy Configurations</span></span> 

- <span data-ttu-id="920fe-167">Proxy otomatik yapılandırma (PAC) betiği: bir [pac dosyası](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft dışı bir site açar), FindProxyForURL (URL, ana bilgisayar) JavaScript işlevini içerir.</span><span class="sxs-lookup"><span data-stu-id="920fe-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="920fe-168">Statik proxy: sunucu: bağlantı noktası biçiminde.</span><span class="sxs-lookup"><span data-stu-id="920fe-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="920fe-169">Web proxy otomatik bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla proxy yapılandırma dosyasının URL 'sini sağlayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="920fe-170">Proxy sağlama yöntemleri</span><span class="sxs-lookup"><span data-stu-id="920fe-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="920fe-171">Proxy 'lerin sağlanması için üç yol vardır:</span><span class="sxs-lookup"><span data-stu-id="920fe-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="920fe-172">**Ayarlar Kullanıcı arabirimi:**</span><span class="sxs-lookup"><span data-stu-id="920fe-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="920fe-173">Kullanıcı başına proxy (20H2 veya önceki sürümler):</span><span class="sxs-lookup"><span data-stu-id="920fe-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="920fe-174">Başlat menüsünü açın ve Ayarlar ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="920fe-175">Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="920fe-176">, El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.</span><span class="sxs-lookup"><span data-stu-id="920fe-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="920fe-177">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="920fe-178">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-178">Enter the port number.</span></span>
        6. <span data-ttu-id="920fe-179">Kaydet’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-179">Click Save.</span></span>
      1. <span data-ttu-id="920fe-180">WiFi proxy (21H1 veya üzeri):</span><span class="sxs-lookup"><span data-stu-id="920fe-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="920fe-181">Başlat menüsünü açın ve Wi-Fi ağınızın Özellikler sayfasına gidin.</span><span class="sxs-lookup"><span data-stu-id="920fe-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="920fe-182">Aşağı kaydırarak ara sunucu</span><span class="sxs-lookup"><span data-stu-id="920fe-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="920fe-183">El Ile kuruluma geçiş yapın</span><span class="sxs-lookup"><span data-stu-id="920fe-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="920fe-184">Proxy sunucusunun IP adresini girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="920fe-185">Bağlantı noktası numarasını girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-185">Enter the port number.</span></span>
          1. <span data-ttu-id="920fe-186">Uygula ' ya tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="920fe-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="920fe-187">**MDM**</span></span> 
     1. <span data-ttu-id="920fe-188">Intune-Intune 'da proxy yapılandırmak için bu [adımları](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) kullanın.</span><span class="sxs-lookup"><span data-stu-id="920fe-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="920fe-189">Bölümün altına kaydırmanız gerekecektir.</span><span class="sxs-lookup"><span data-stu-id="920fe-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="920fe-190">Diğer üçüncü taraf MDM çözümleri- [WIFI CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)kullanın.</span><span class="sxs-lookup"><span data-stu-id="920fe-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="920fe-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="920fe-191">**PPKG**</span></span> 
    1. <span data-ttu-id="920fe-192">Windows yapılandırma Tasarımcısı 'Nı açın</span><span class="sxs-lookup"><span data-stu-id="920fe-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="920fe-193">Gelişmiş sağlama ' ya tıklayın, yeni projeniz için bir ad girin ve Ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="920fe-194">Windows holographic (HoloLens 2) öğesini seçin ve Ileri ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="920fe-195">PPKG 'nizi (isteğe bağlı) içeri aktarın ve son ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="920fe-196">Çalışma zamanı ayarları-> bağlantı profilleri ' ni > WLAN-> WLAN proxy 'Si.</span><span class="sxs-lookup"><span data-stu-id="920fe-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="920fe-197">Wi-Fi ağınızın SSID 'sini girin ve Ekle ' ye tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="920fe-198">Sol penceredeki Wi-Fi ağınızı seçin ve istediğiniz özelleştirmeleri girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="920fe-199">Etkin özelleştirmeler sol menüde kalın olarak görünür.</span><span class="sxs-lookup"><span data-stu-id="920fe-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="920fe-200">Kaydet ve çıkış ' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="920fe-201">[Sağlama](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) paketini HoloLens'e uygulama.</span><span class="sxs-lookup"><span data-stu-id="920fe-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="920fe-202">[CSP'ler,](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) hem Windows 10 hem de Microsoft olmayan MDM hizmet sağlayıcılarında Microsoft Intune yönetim görevlerinin ve ilkelerinin çoğunun arkasındadır.</span><span class="sxs-lookup"><span data-stu-id="920fe-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="920fe-203">Bir sağlama paketi [oluşturmak ve](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) [](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) HoloLens 2'ye uygulamak için Windows Yapılandırma Tasarımcısı'nın da kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="920fe-204">HoloLens 2'nize uygulanacak en olası CSP'ler:</span><span class="sxs-lookup"><span data-stu-id="920fe-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="920fe-205">[WiFi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)profil başına Wi-Fi ara sunucusu</span><span class="sxs-lookup"><span data-stu-id="920fe-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="920fe-206">HoloLens cihazlarında desteklenen diğer CSP'ler</span><span class="sxs-lookup"><span data-stu-id="920fe-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="920fe-207">VPN</span><span class="sxs-lookup"><span data-stu-id="920fe-207">VPN</span></span>
<span data-ttu-id="920fe-208">VPN bağlantısı, daha güvenli bir bağlantı ve şirket ağı ile İnternet erişimi sağlamanıza yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="920fe-209">HoloLens 2, yerleşik VPN istemcisini ve Evrensel Windows Platformu (UWP) VPN eklentisini destekler.</span><span class="sxs-lookup"><span data-stu-id="920fe-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="920fe-210">Desteklenen Yerleşik VPN protokolleri:</span><span class="sxs-lookup"><span data-stu-id="920fe-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="920fe-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="920fe-211">IKEv2</span></span>
- <span data-ttu-id="920fe-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="920fe-212">L2TP</span></span>
- <span data-ttu-id="920fe-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="920fe-213">PPTP</span></span>

<span data-ttu-id="920fe-214">Yerleşik VPN istemcisi için kimlik doğrulaması için sertifika kullanılıyorsa, gerekli istemci sertifikasının kullanıcı sertifika deposuna ekleniyor olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="920fe-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="920fe-215">3. taraf BIR VPN eklentisinin HoloLens 2'nin destekleyip desteklemediklerini bulmak için Store'a gidip VPN uygulamasını bulun ve HoloLens'in desteklenen bir cihaz olarak listelenmiş olup olduğunu ve Uygulamanın ARM veya ARM64 mimarisini desteklediği Sistem Gereksinimi sayfasından kontrol edin.</span><span class="sxs-lookup"><span data-stu-id="920fe-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="920fe-216">HoloLens yalnızca Evrensel Windows Platformu üçüncü taraf VPN için uygulama desteği sunar.</span><span class="sxs-lookup"><span data-stu-id="920fe-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="920fe-217">VPN, [Ayarlar/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla MDM tarafından yönetilebilir ve [Vpnv2-csp ilkesi aracılığıyla ayarlanır.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="920fe-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="920fe-218">Vpn'i [yapılandırma hakkında daha fazla bilgi için](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) bu kılavuzları [kullanın.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="920fe-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="920fe-219">Kullanıcı arabirimi üzerinden VPN</span><span class="sxs-lookup"><span data-stu-id="920fe-219">VPN via UI</span></span>

<span data-ttu-id="920fe-220">VPN varsayılan olarak etkin değildir, ancak  Ayarlar uygulaması açarak ve İnternet **-> VPN'e giderek & etkinleştirilebilir.**</span><span class="sxs-lookup"><span data-stu-id="920fe-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="920fe-221">Bir VPN sağlayıcısı seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="920fe-222">Bağlantı adı oluşturun.</span><span class="sxs-lookup"><span data-stu-id="920fe-222">Create a connection name.</span></span> 
1. <span data-ttu-id="920fe-223">Sunucu adı veya adresinizi girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="920fe-224">VPN türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-224">Select the VPN type.</span></span>
1. <span data-ttu-id="920fe-225">Oturum açma bilgileri türünü seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="920fe-226">İsteğe bağlı olarak kullanıcı adı ve parola ekleyin.</span><span class="sxs-lookup"><span data-stu-id="920fe-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="920fe-227">VPN ayarlarını uygulama.</span><span class="sxs-lookup"><span data-stu-id="920fe-227">Apply the VPN settings.</span></span> 

![HoloLens VPN ayarları](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="920fe-229">Sağlama Paketi aracılığıyla VPN kümesi</span><span class="sxs-lookup"><span data-stu-id="920fe-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="920fe-230">Windows Holographic sürüm 20H2'de VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi.</span><span class="sxs-lookup"><span data-stu-id="920fe-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="920fe-231">Bu akışı kullanmak için lütfen cihazları bu derlemeye yükseltmeyi göz önünde bulundurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="920fe-232">Windows Yapılandırma Tasarımcısı'ı başlatma.</span><span class="sxs-lookup"><span data-stu-id="920fe-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="920fe-233">**HoloLens cihazlarını sağlama'ya tıklayın,** ardından hedef cihazı ve Sonraki'yi **seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="920fe-234">Paket adını ve yolunu girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-234">Enter package name and path.</span></span>
1. <span data-ttu-id="920fe-235">Gelişmiş **düzenleyiciye geç'e tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="920fe-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="920fe-236">Çalışma **zamanı ayarları**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings'i açın.**</span><span class="sxs-lookup"><span data-stu-id="920fe-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="920fe-237">VPNProfileName yapılandırma</span><span class="sxs-lookup"><span data-stu-id="920fe-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="920fe-238">ProfileType: Yerel **veya Üçüncü** **Taraf'ı seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="920fe-239">Yerel profil için **NativeProtocolType'ı seçin,** ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="920fe-240">"Üçüncü Taraf" profili için sunucu URL'sini, VPN eklentisi Uygulama paketi aile adını (önceden tanımlanmış yalnızca 3) ve özel yapılandırmaları yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="920fe-241">Paketinizi dışarı aktarın.</span><span class="sxs-lookup"><span data-stu-id="920fe-241">Export your package.</span></span>
1. <span data-ttu-id="920fe-242">HoloLens'inizi bağlama ve .ppkg dosyasını cihaza kopyalama.</span><span class="sxs-lookup"><span data-stu-id="920fe-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="920fe-243">HoloLens'de, Başlat menüsü'yi açarak ve Ayarlar Hesap Erişimi iş veya okul Sağlama paketi ekleme veya kaldırma -> VPN paketinizi seçin'i seçerek VPN .ppkg'yi  ->    ->    ->   uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="920fe-244">Intune aracılığıyla VPN ayarlama</span><span class="sxs-lookup"><span data-stu-id="920fe-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="920fe-245">Çalışmaya devam etmek için Intune belgelerini takip edin.</span><span class="sxs-lookup"><span data-stu-id="920fe-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="920fe-246">Bu adımları takip edin ve HoloLens cihazlarının desteklemektedir yerleşik VPN protokollerini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="920fe-247">[Intune'da VPN sunucularına bağlanmak için VPN profilleri oluşturun.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="920fe-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="920fe-248">Windows 10 kullanarak VPN bağlantıları eklemek için Windows [Holographic cihaz ayarlarını kullanın.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="920fe-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="920fe-249">Bittiğinde lütfen profilini [atamayı unutmayın.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="920fe-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="920fe-250">3. taraf MDM çözümleri aracılığıyla VPN</span><span class="sxs-lookup"><span data-stu-id="920fe-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="920fe-251">3. taraf VPN bağlantısı örneği:</span><span class="sxs-lookup"><span data-stu-id="920fe-251">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="920fe-252">Yerel IKEv2 VPN örneği:</span><span class="sxs-lookup"><span data-stu-id="920fe-252">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="920fe-253">HoloLens'Wi-Fi devre dışı bırakma (1. nesil)</span><span class="sxs-lookup"><span data-stu-id="920fe-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="920fe-254">HoloLens'de Ayarlar uygulamasını kullanma</span><span class="sxs-lookup"><span data-stu-id="920fe-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="920fe-255">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="920fe-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="920fe-256">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="920fe-257">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="920fe-258">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="920fe-259">Kaydırıcıyı Wi-Fi kaydırıcısını seçerek Kapalı **konuma taşıyın.**</span><span class="sxs-lookup"><span data-stu-id="920fe-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="920fe-260">Bu, holoLens'de Wi-Fi rf bileşenlerini devre dışı Wi-Fi devre dışı bıraktır.</span><span class="sxs-lookup"><span data-stu-id="920fe-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="920fe-261">Sanal Wi-Fi devre dışı bırakılmıştır, HoloLens alanlarınızı otomatik olarak [yükemez.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="920fe-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="920fe-262">Kaydırıcı anahtarını Açık konuma **hareket ettirerek** Wi-Fi açma ve Wi-Fi geri yükleme işlevlerini Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="920fe-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="920fe-263">Seçilen radyo Wi-Fi ( Açık **veya Kapalı)** yeniden başlatmalarda kalıcı olur. </span><span class="sxs-lookup"><span data-stu-id="920fe-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="920fe-264">Sanal ağ üzerinde HoloLens'inizin IP Wi-Fi tanımlama</span><span class="sxs-lookup"><span data-stu-id="920fe-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="920fe-265">Ayarlar uygulamasını kullanarak</span><span class="sxs-lookup"><span data-stu-id="920fe-265">By using the Settings app</span></span>

1. <span data-ttu-id="920fe-266">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="920fe-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="920fe-267">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="920fe-268">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="920fe-269">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="920fe-270">Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Wi-Fi ayarlarında donanım özellikleri](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="920fe-272">IP adresi, **IPv4 adresinin yanında görünür.**</span><span class="sxs-lookup"><span data-stu-id="920fe-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="920fe-273">Ses komutlarını kullanarak</span><span class="sxs-lookup"><span data-stu-id="920fe-273">By using voice commands</span></span>

<span data-ttu-id="920fe-274">Cihaz derlemenize bağlı olarak, ip adresinizi görüntülemek için yerleşik sesli komutları veya Cortana'yı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="920fe-275">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sonrasındaki derlemelerde "IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="920fe-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="920fe-276">görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="920fe-276">and it will be displayed.</span></span> <span data-ttu-id="920fe-277">Önceki derlemeler veya HoloLens (1. nesil) için "Hey Cortana, IP adresim nedir?"</span><span class="sxs-lookup"><span data-stu-id="920fe-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="920fe-278">Cortana IP adresinizi görüntüler ve okur.</span><span class="sxs-lookup"><span data-stu-id="920fe-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="920fe-279">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="920fe-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="920fe-280">Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="920fe-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="920fe-281">Ağ **bölümüne** gidin.</span><span class="sxs-lookup"><span data-stu-id="920fe-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="920fe-282">Bu bölümde IP adresiniz ve diğer ağ bilgileri görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="920fe-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="920fe-283">Bu yöntemi kullanarak IP adresini kopyalayıp geliştirme bilgisayarınıza yapıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="920fe-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="920fe-284">IP Adresini statik adres olarak değiştirme</span><span class="sxs-lookup"><span data-stu-id="920fe-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="920fe-285">Ayarlar'ı kullanarak</span><span class="sxs-lookup"><span data-stu-id="920fe-285">By using Settings</span></span>
 
1. <span data-ttu-id="920fe-286">Başlat **menüsünü** açın.</span><span class="sxs-lookup"><span data-stu-id="920fe-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="920fe-287">Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="920fe-288">Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="920fe-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="920fe-289">Ağ **ve İnternet & seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="920fe-290">Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="920fe-291">IP **ayarlarını düzenle penceresinde** ilk alanı El ile olarak **değiştirin.**</span><span class="sxs-lookup"><span data-stu-id="920fe-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="920fe-292">Kalan alanlara istenen IP yapılandırmasını girin ve Kaydet'e **tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="920fe-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="920fe-293">Windows Cihaz Portalı</span><span class="sxs-lookup"><span data-stu-id="920fe-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="920fe-294">Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)</span><span class="sxs-lookup"><span data-stu-id="920fe-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="920fe-295">Ağ **bölümüne** gidin.</span><span class="sxs-lookup"><span data-stu-id="920fe-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="920fe-296">**IPv4 Yapılandırması düğmesini** seçin.</span><span class="sxs-lookup"><span data-stu-id="920fe-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="920fe-297">Aşağıdaki **IP adresini kullan'ı seçin** ve istediğiniz TCP/IP yapılandırmasını girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="920fe-298">Aşağıdaki **DNS sunucusu adreslerini kullan'ı seçin** ve gerekirse Tercih edilen ve Alternatif DNS sunucusu adreslerini girin.</span><span class="sxs-lookup"><span data-stu-id="920fe-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="920fe-299">**Kaydet**’e tıklayın.</span><span class="sxs-lookup"><span data-stu-id="920fe-299">Click **Save**.</span></span> 