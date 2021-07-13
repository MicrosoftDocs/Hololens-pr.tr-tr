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
# <a name="connect-hololens-to-a-network"></a>bir ağa HoloLens Bağlan

HoloLens birçok şeyi yapmak için bir ağa bağlı olmanız gerekir. HoloLens bir 802.11 ac özellikli, 2x2 Wi-Fi radyo ve ağa bağlama bir Windows 10 masaüstü veya mobil cihazı bir Wi-Fi ağına bağlamaya benzer. Bu kılavuz şunları yapmanıza yardımcı olur:

- Wi-Fi kullanarak bir ağa Bağlan veya yalnızca HoloLens 2 için USB-C üzerinden doğrudan veya Ethernet Wi-Fi
- Wi-Fi devre dışı bırakıp yeniden etkinleştirin

[HoloLens çevrimdışı kullanma](hololens-offline.md)hakkında daha fazla bilgi edinin.

## <a name="connecting-for-the-first-time"></a>İlk kez bağlanıyor

HoloLens ilk kez kullandığınızda, bir Wi-Fi ağa bağlanarak gezinirsiniz. Kurulum sırasında Wi-Fi bağlanmada sorun yaşıyorsanız, ağınızın açık, parola korumalı bir ağ ya da bir açıklamalı Portal ağı olduğundan emin olun. Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmediğini doğrulayın. Kurulumdan sonra, diğer Wi-Fi ağları türlerine bağlanabilirsiniz.

HoloLens 2 cihazda, bir kullanıcı, cihazı ayarlarken yardım 'a doğrudan Wi-Fi bağlanmak için [bir USB-C-Ethernet bağdaştırıcısı da kullanabilir](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) . Cihaz ayarlandıktan sonra, bir Kullanıcı bağdaştırıcıyı kullanmaya devam edebilir ya da cihazın bağdaştırıcı bağlantısını kesebilir ve ayarladıktan [sonra Wi-Fi 'a bağlanabilir](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Kurulumdan sonra Wi-Fi bağlanma

1. **başlangıç hareketini** önceden oluşturup **Ayarlar** seçin. Ayarlar uygulama, sizin için otomatik olarak eklenir.
1. **Internet**  >  **Wi-Fi**& ağ ' ı seçin. Wi-Fi’ın açık olduğundan emin olun. Ağınızı görmüyorsanız listede aşağı kaydırın.
1. bir ağ seçin, sonra **Bağlan**' yi seçin.
1. Bir ağ parolası istenirse bu dosyayı yazın ve ardından **İleri**' yi seçin.

![HoloLens Wi-Fi ayarları](./images/hololens-2-wifi-settings.jpg)

Wi-Fi ağa bağlı olduğunu doğrulamak için, **Başlangıç** menüsündeki Wi-Fi durumunu kontrol edin:

1. **Başlat** menüsünü açın.
1. Wi-Fi durum için **Başlangıç** menüsünün sol üst kısmına bakın. Wi-Fi durumu ve bağlı ağın SSID 'SI gösterilir.

> [!TIP]
> Wi-Fi yoksa [hücresel ve 5 g ağlarına da bağlanabilirsiniz](hololens-cellular.md).

> [!IMPORTANT]
> tasarıma göre, kullanıcılar HoloLens 2 ' nin Wi-Fi dolaşım davranışını ince ayarlayamez. **Wi-Fi listesini yenilemenin tek yolu Wi-Fi kapalı ve açık olarak geçiş yapmaz**. Bu, bir cihazın Aralık dışına çıkdıktan sonra bir AP 'ye "takılı" kalabileceği gibi birçok sorunu önler.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Wi-Fi ağ Enterprise HoloLens Bağlan

Enterprise Wi-Fi profiller Wi-Fi bağlantılarının kimliğini doğrulamak için genişletilebilir kimlik doğrulama protokolü (EAP) kullanır. HoloLens Enterprise Wi-Fi profili, [Windows yapılandırma tasarımcısı](/windows/configuration/provisioning-packages/provisioning-packages)tarafından oluşturulan MDM veya sağlama paketi aracılığıyla yapılandırılabilir.

Microsoft Intune yönetilen cihaz için yapılandırma yönergeleri için [ıntune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 'a bakın.

WCD 'de Wi-Fi sağlama paketi oluşturmak için, önceden yapılandırılmış bir Wi-Fi profili .xml dosyası gereklidir. EAP-TLS kimlik doğrulaması ile WPA2-Enterprise için örnek bir Wi-Fi profili aşağıda verilmiştir:

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


Sunucu kök CA sertifikası ve istemci sertifikasının, EAP türüne bağlı olarak cihazda sağlanması gerekebilir.

Ek kaynaklar:

- WLANv1Profile şeması: [[MS-GPWL]: Kablosuz LAN profili v1 şeması | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS şeması: [[MS-GPWL]: MICROSOFT EAP TLS şeması | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Wi-Fi 'nize bağlanmakta sorun yaşıyorsanız [sorun giderme](hololens2-enterprise-troubleshooting.md#) sayfamızı denetleyin.

## <a name="configure-network-proxy"></a>Ağ ara sunucusunu yapılandırma

bu bölümde, Windows HTTP yığını kullanan HoloLens OS ve Evrensel Windows Platformu (UWP) uygulamaları için ağ proxy 'si ele alınmaktadır. Windows olmayan HTTP yığınının kullanıldığı uygulamalar kendi ara sunucu yapılandırmasına ve işlemeye sahip olabilir. 

### <a name="proxy-configurations"></a>Proxy yapılandırması 

- Proxy otomatik yapılandırma (PAC) betiği: bir [pac dosyası](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft dışı bir site açar), FindProxyForURL (URL, ana bilgisayar) JavaScript işlevini içerir. 
- Statik proxy: sunucu: bağlantı noktası biçiminde.  
- Web proxy otomatik bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla proxy yapılandırma dosyasının URL 'sini sağlayın. 

### <a name="proxy-provisioning-methods"></a>Proxy sağlama yöntemleri 
Proxy 'lerin sağlanması için üç yol vardır:

 

1.  **Ayarlar 'SıNı** 
    1. Kullanıcı başına proxy (20H2 veya önceki sürümler):
        1. Başlat menüsü açın ve Ayarlar ' i seçin.
        2. Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.
        3. , El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.
        4. Proxy sunucusunun IP adresini girin.
        5. Bağlantı noktası numarasını girin.
        6. Kaydet’e tıklayın.
      1. WiFi proxy (21H1 veya üzeri):
          1. Başlat menüsü açın ve Wi-Fi ağınızın özellikler sayfasına gidin.
          1. Aşağı kaydırarak ara sunucu
          1. El Ile kuruluma geçiş yapın
          1. Proxy sunucusunun IP adresini girin.
          1. Bağlantı noktası numarasını girin.
          1. Uygula ' ya tıklayın.
        
 2. **MDM** 
     1. Intune-Intune 'da proxy yapılandırmak için bu [adımları](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) kullanın. Bölümün altına kaydırmanız gerekecektir.
     1. Diğer üçüncü taraf MDM çözümleri- [WIFI CSP](/windows/client-management/mdm/wifi-csp)kullanın.

3. **PPKG** 
    1. Windows yapılandırma tasarımcısını aç
    1. gelişmiş sağlama ' ya tıklayın, yeni Project adını girin ve ileri ' ye tıklayın.
    1. Windows Holographic (HoloLens 2) öğesini seçin ve ileri ' ye tıklayın.
    1. PPKG 'nizi (isteğe bağlı) içeri aktarın ve son ' a tıklayın.
    1. çalışma zamanı Ayarlar-> bağlantı profilleri-> wlan-> wlan Proxy 'yi genişletin.
    1. Wi-Fi ağınızın SSID 'sini girin ve Ekle ' ye tıklayın.
    1. Sol penceredeki Wi-Fi ağınızı seçin ve istediğiniz özelleştirmeleri girin. Etkin özelleştirmeler sol menüde kalın olarak görünür.
    1. Kaydet ve çıkış ' a tıklayın.
    1. Sağlama paketini HoloLens [uygulayın](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) .

[csp 'ler](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) , hem Microsoft Intune hem de Microsoft dışı MDM hizmet sağlayıcılarının Windows 10 için yönetim görevlerinin ve ilkelerinin çoğundan daha gerisinde bulunur. ayrıca, bir [sağlama paketi](/windows/configuration/provisioning-packages/provisioning-packages) oluşturmak ve bunu HoloLens 2 ' ye uygulamak için [Windows yapılandırma tasarımcısı](/windows/configuration/provisioning-packages/provisioning-install-icd) ' nı kullanabilirsiniz.
HoloLens 2 ' ye uygulanacak en olası csp 'ler şunlardır:

- [WIFI CSP](/windows/client-management/mdm/wifi-csp): profil başına Wi-Fi proxy 

[HoloLens cihazlarda desteklenen diğer csp 'ler](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN bağlantısı, şirketinizin ağına ve Internet 'e daha güvenli bir bağlantı ve erişim sağlamaya yardımcı olabilir. HoloLens 2, yerleşik vpn istemcisi ve Evrensel Windows Platformu (UWP) vpn eklentisini destekler. 

Desteklenen yerleşik VPN protokolleri:
- IKEv2
- L2TP
- PPTP

Sertifika, yerleşik VPN istemcisi için kimlik doğrulaması için kullanılıyorsa, gerekli istemci sertifikasının Kullanıcı sertifika deposuna eklenmesi gerekir. 3. taraf vpn eklentisinin HoloLens 2 ' yi destekleyip desteklemediğini bulmak için, mağaza ' ya giderek vpn uygulamasını bulun ve HoloLens desteklenen bir cihaz olarak listelenip listelenmediğini ve sistem gereksinimi sayfasında, uygulamanın ARM veya ARM64 mimarisini destekleyip desteklemediğini denetleyin. HoloLens, 3. taraf VPN için yalnızca Evrensel Windows Platformu uygulamalarını destekler.

 VPN, MDM tarafından [Ayarlar/allowvpn](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla yönetilebilir ve [Vpnv2-csp ilkesi](/windows/client-management/mdm/vpnv2-csp)aracılığıyla ayarlanabilir.

[Bu KıLAVUZLARLA](/windows/security/identity-protection/vpn/vpn-guide) [VPN yapılandırma](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hakkında daha fazla bilgi edinin.  

### <a name="vpn-via-ui"></a>Kullanıcı arabirimi aracılığıyla VPN

vpn varsayılan olarak etkinleştirilmemiştir, ancak **Ayarlar** uygulaması açılarak ve **ağ & Internet-> VPN**'ye gidilerek el ile etkinleştirilebilir.
1. Bir VPN sağlayıcısı seçin.
1. Bir bağlantı adı oluşturun. 
1. Sunucu adınızı veya adresinizi girin.
1. VPN türünü seçin.
1. Oturum açma bilgilerinin türünü seçin. 
1. İsteğe bağlı olarak Kullanıcı adı ve parola ekleyin.
1. VPN ayarlarını uygulayın. 

![HoloLens VPN ayarları](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Sağlama paketi aracılığıyla VPN kümesi

> [!TIP] 
> Windows Holographic, sürüm 20h2 ' de VPN bağlantısı için bir ara sunucu yapılandırma sorunu düzeltildi. Bu akışı kullanmak istiyorsanız, lütfen cihazları bu yapıya yükseltmeyi göz önünde bulundurun.

1. Windows yapılandırma tasarımcısını başlatın.
1. **HoloLens cihazları sağla**' yı ve ardından hedef **cihaz ' ı seçin.**
1. Paket adı ve yolunu girin.
1. **Gelişmiş düzenleyiciye geç ' e** tıklayın.
1. **Çalışma zamanı ayarları**  ->  **connectivityprofiles**  ->  **VPN**  ->  **vpnsettings**' i açın.
1. VPNProfileName yapılandırma
1. ProfileType: **Native** veya **üçüncü taraf** seçeneğini belirleyin.
    1. Yerel profil için **Nativeprotocoltype**' ı seçin, ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırın.
    1. "Üçüncü taraf" profili için sunucu URL 'SI, VPN eklentisi uygulama paketi aile adı (yalnızca 3 önceden tanımlanmış) ve özel yapılandırma için yapılandırın.
1. Paketinizi dışarı aktarın.
1. HoloLens Bağlan ve. ppkg dosyasını cihaza kopyalayın. 
1. HoloLens, Başlat menüsü açıp **Ayarlar**  ->  **hesap**  ->  **erişimi iş veya okul**  ->  **sağlama paketi ekle veya kaldır** ' ı seçerek vpn. ppkg 'yi uygulayın-> VPN paketinizi seçin.


### <a name="setting-up-vpn-via-intune"></a>Intune aracılığıyla VPN ayarlama
Başlamak için Intune belgelerini izlemeniz yeterlidir. bu adımları izleyerek lütfen HoloLens cihazların desteklediği yerleşik VPN protokollerini aklınızda bulundurun. 

[Intune 'DA VPN sunucularına bağlanmak IÇIN VPN profilleri oluşturun](/mem/intune/configuration/vpn-settings-configure).

[ıntune kullanarak VPN bağlantıları eklemek için Windows 10 ve Windows cihaz ayarlarını](/mem/intune/configuration/vpn-settings-windows-10)kullanın.

İşiniz bittiğinde [, lütfen profili atamayı](/mem/intune/configuration/device-profile-assign)unutmayın.

### <a name="vpn-via-3rd-party-mdm-solutions"></a>3. taraf MDM çözümleri aracılığıyla VPN
3. taraf VPN bağlantısı örneği:
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

Yerel IKEv2 VPN örneği:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>HoloLens Wi-Fi devre dışı bırakma (1. genel)

### <a name="using-the-settings-app-on-hololens"></a>HoloLens Ayarlar uygulamasını kullanma

1. **Başlat** menüsünü açın.
1. **başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin. **Ayarlar** uygulama, sizin için otomatik olarak eklenir.
1. **Internet & ağı**' nı seçin.
1. **Kapalı** konuma taşımak için Wi-Fi kaydırıcı anahtarını seçin. Bu, Wi-Fi radyoın RF bileşenlerini kapatır ve HoloLens tüm Wi-Fi işlevlerini devre dışı bırakır.

    > [!WARNING]
    > Wi-Fi radyo devre dışı bırakıldığında, HoloLens otomatik olarak bu [alanları](hololens-spaces.md)yükleyemeyecektir.

1. Wi-Fi Radyoyu açmak ve Microsoft HoloLens Wi-Fi işlevselliğini geri yüklemek için kaydırıcı anahtarını **Açık** konuma taşıyın. Seçilen Wi-Fi radyo durumu (**Açık** veya **kapalı**), yeniden başlatmalar arasında kalır.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Wi-Fi ağda HoloLens IP adresini tanımlama

### <a name="by-using-the-settings-app"></a>Ayarlar uygulamasını kullanarak

1. **Başlat** menüsünü açın.
1. **başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin. **Ayarlar** uygulama, sizin için otomatik olarak eklenir.
1. **Internet & ağı**' nı seçin.
1. Kullanılabilir Wi-Fi ağları listesinin altına aşağı kaydırın ve **donanım özellikleri**' ni seçin.

    ![Wi-Fi ayarlarındaki donanım özellikleri](./images/wifi-hololens-hwdetails.jpg)

   IP adresi, **IPv4 adresi**' nin yanında görünür.

### <a name="by-using-voice-commands"></a>Sesli komutları kullanarak

cihazlarınıza bağlı olarak, ıp adresinizi göstermek için yerleşik sesli komutları veya Cortana kullanabilirsiniz. [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) konuşduktan sonra "IP adresim nedir?" ve görüntülenir. önceki derlemeler veya HoloLens (1. gen) için "Hey Cortana, ıp adresim nedir?" deyin Cortana, ıp adresinizi görüntüler ve okur.

### <a name="by-using-windows-device-portal"></a>Windows cihaz portalını kullanarak

1. Bilgisayarınızdaki bir Web tarayıcısında [cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal.md#networking)açın.
1. **Ağ** bölümüne gidin.  
   Bu bölüm, IP adresinizi ve diğer ağ bilgilerini görüntüler. Bu yöntemi kullanarak, IP adresini geliştirme bilgisayarınızda kopyalayabilir ve yapıştırabilirsiniz.

## <a name="change-ip-address-to-static-address"></a>IP adresini statik adres olarak değiştir
### <a name="by-using-settings"></a>Ayarlar kullanarak
 
1. **Başlat** menüsünü açın.
1. **başlat menüsünün sağ** tarafındaki **tüm uygulamalar** listesinden **Ayarlar** uygulamayı **başlat** ' ı seçin. **Ayarlar** uygulama, sizin için otomatik olarak eklenir.
1. **Internet & ağı**' nı seçin.
1. Kullanılabilir Wi-Fi ağları listesinin altına aşağı kaydırın ve **donanım özellikleri**' ni seçin.
1. **IP ayarlarını Düzenle** penceresinde, Ilk alanı **el ile** olarak değiştirin.
1. İstenen IP yapılandırmasını kalan alanlara girin ve **Kaydet**' e tıklayın.

### <a name="by-using-windows-device-portal"></a>Windows cihaz portalını kullanarak

1. Bilgisayarınızdaki bir Web tarayıcısında [cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal.md#networking)açın.
1. **Ağ** bölümüne gidin.
1. **IPv4 yapılandırma** düğmesini seçin.
1. **AŞAĞıDAKI IP adresini kullan** ' ı seçin ve istenen TCP/IP yapılandırmasını girin.
1. **AŞAĞıDAKI DNS sunucusu adreslerini kullan** ' ı seçin ve gerekirse tercih edilen ve alternatif DNS sunucusu adreslerini girin.
1. **Kaydet**’e tıklayın. 
