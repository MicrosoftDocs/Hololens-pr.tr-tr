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
# <a name="connect-hololens-to-a-network"></a>HoloLens 'i ağa bağlama

HoloLens 'te birçok şeyi yapmak için bir ağa bağlı olmanız gerekir. HoloLens, 802.11 AC özellikli, 2x2 Wi-Fi radyo ve bir ağa bağlamak bir Windows 10 Masaüstü veya mobil cihazı bir Wi-Fi ağına bağlamaya benzer. Bu kılavuz şunları yapmanıza yardımcı olur:

- Wi-Fi kullanarak bir ağa bağlanma veya yalnızca HoloLens 2 için USB-C üzerinden doğrudan veya Ethernet Wi-Fi
- Wi-Fi devre dışı bırakıp yeniden etkinleştirin

[HoloLens 'i çevrimdışı kullanma](hololens-offline.md)hakkında daha fazla bilgi edinin.

## <a name="connecting-for-the-first-time"></a>İlk kez bağlanıyor

HoloLens 'i ilk kez kullandığınızda bir Wi-Fi ağa bağlanarak size kılavuzluk edilecek. Kurulum sırasında Wi-Fi bağlanmada sorun yaşıyorsanız, ağınızın açık, parola korumalı bir ağ ya da bir açıklamalı Portal ağı olduğundan emin olun. Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmediğini doğrulayın. Kurulumdan sonra, diğer Wi-Fi ağları türlerine bağlanabilirsiniz.

HoloLens 2 cihazlarında, bir Kullanıcı, cihazı ayarlamaya yardımcı olmak üzere Wi-Fi doğrudan bağlanmak için [BIR USB-C-Ethernet bağdaştırıcısı da kullanabilir](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) . Cihaz ayarlandıktan sonra, bir Kullanıcı bağdaştırıcıyı kullanmaya devam edebilir ya da cihazın bağdaştırıcı bağlantısını kesebilir ve ayarladıktan [sonra Wi-Fi 'a bağlanabilir](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Kurulumdan sonra Wi-Fi bağlanma

1. **Başlangıç hareketini** önceden yapın ve **Ayarlar**' ı seçin. Ayarlar uygulaması sizin için otomatik olarak yerleştirilir.
1. **Internet**  >  **Wi-Fi**& ağ ' ı seçin. Wi-Fi’ın açık olduğundan emin olun. Ağınızı görmüyorsanız listede aşağı kaydırın.
1. Bir ağ seçin ve ardından **Bağlan**' ı seçin.
1. Bir ağ parolası istenirse bu dosyayı yazın ve ardından **İleri**' yi seçin.

![HoloLens Wi-Fi ayarları](./images/hololens-2-wifi-settings.jpg)

Wi-Fi ağa bağlı olduğunu doğrulamak için, **Başlangıç** menüsündeki Wi-Fi durumunu kontrol edin:

1. **Başlat** menüsünü açın.
1. Wi-Fi durum için **Başlangıç** menüsünün sol üst kısmına bakın. Wi-Fi durumu ve bağlı ağın SSID 'SI gösterilir.

> [!TIP]
> Wi-Fi yoksa [hücresel ve 5 g ağlarına da bağlanabilirsiniz](hololens-cellular.md).

> [!IMPORTANT]
> Tasarım, kullanıcılar, HoloLens 2 ' nin Wi-Fi gezici davranışını ince ayarlayamez. **Wi-Fi listesini yenilemenin tek yolu Wi-Fi kapalı ve açık olarak geçiş yapmaz**. Bu, bir cihazın Aralık dışına çıkdıktan sonra bir AP 'ye "takılı" kalabileceği gibi birçok sorunu önler.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>HoloLens 'i kurumsal Wi-Fi ağa bağlama

Kurumsal Wi-Fi profilleri, Wi-Fi bağlantılarının kimliğini doğrulamak için Genişletilebilir Kimlik Doğrulama Protokolü (EAP) kullanır. HoloLens kurumsal Wi-Fi profili, [Windows yapılandırma Tasarımcısı](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)tarafından oluşturulan MDM veya sağlama paketi aracılığıyla yapılandırılabilir.

Microsoft Intune yönetilen cihaz için yapılandırma yönergeleri için [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) 'a bakın.

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

- WLANv1Profile şeması: [[MS-GPWL]: Kablosuz LAN profili v1 şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS şeması: [[MS-GPWL]: MICROSOFT EAP TLS şeması | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Wi-Fi 'nize bağlanmakta sorun yaşıyorsanız [sorun giderme](hololens2-enterprise-troubleshooting.md#) sayfamızı denetleyin.

## <a name="configure-network-proxy"></a>Ağ ara sunucusunu yapılandırma

Bu bölümde, HoloLens OS ve Windows HTTP Stack kullanan Evrensel Windows Platformu (UWP) uygulamaları için ağ proxy 'si ele alınmaktadır. Windows dışı HTTP yığını kullanan uygulamaların kendi proxy yapılandırması ve işlemesi olabilir. 

### <a name="proxy-configurations"></a>Proxy yapılandırması 

- Proxy otomatik yapılandırma (PAC) betiği: bir [pac dosyası](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (Microsoft dışı bir site açar), FindProxyForURL (URL, ana bilgisayar) JavaScript işlevini içerir. 
- Statik proxy: sunucu: bağlantı noktası biçiminde.  
- Web proxy otomatik bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla proxy yapılandırma dosyasının URL 'sini sağlayın. 

### <a name="proxy-provisioning-methods"></a>Proxy sağlama yöntemleri 
Proxy 'lerin sağlanması için üç yol vardır:

 

1.  **Ayarlar Kullanıcı arabirimi:** 
    1. Kullanıcı başına proxy (20H2 veya önceki sürümler):
        1. Başlat menüsünü açın ve Ayarlar ' ı seçin.
        2. Internet & Ağı ' nı ve ardından sol taraftaki menüden ara ' yı seçin.
        3. , El Ile ara sunucu kurulumuna gidin ve açık bir proxy sunucu kullan ' a geçiş yapın.
        4. Proxy sunucusunun IP adresini girin.
        5. Bağlantı noktası numarasını girin.
        6. Kaydet’e tıklayın.
      1. WiFi proxy (21H1 veya üzeri):
          1. Başlat menüsünü açın ve Wi-Fi ağınızın Özellikler sayfasına gidin.
          1. Aşağı kaydırarak ara sunucu
          1. El Ile kuruluma geçiş yapın
          1. Proxy sunucusunun IP adresini girin.
          1. Bağlantı noktası numarasını girin.
          1. Uygula ' ya tıklayın.
        
 2. **MDM** 
     1. Intune-Intune 'da proxy yapılandırmak için bu [adımları](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) kullanın. Bölümün altına kaydırmanız gerekecektir.
     1. Diğer üçüncü taraf MDM çözümleri- [WIFI CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)kullanın.

3. **PPKG** 
    1. Windows yapılandırma Tasarımcısı 'Nı açın
    1. Gelişmiş sağlama ' ya tıklayın, yeni projeniz için bir ad girin ve Ileri ' ye tıklayın.
    1. Windows holographic (HoloLens 2) öğesini seçin ve Ileri ' ye tıklayın.
    1. PPKG 'nizi (isteğe bağlı) içeri aktarın ve son ' a tıklayın.
    1. Çalışma zamanı ayarları-> bağlantı profilleri ' ni > WLAN-> WLAN proxy 'Si.
    1. Wi-Fi ağınızın SSID 'sini girin ve Ekle ' ye tıklayın.
    1. Sol penceredeki Wi-Fi ağınızı seçin ve istediğiniz özelleştirmeleri girin. Etkin özelleştirmeler sol menüde kalın olarak görünür.
    1. Kaydet ve çıkış ' a tıklayın.
    1. Sağlama paketini HoloLens 'e [uygulayın](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) .

[CSP 'ler](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) , hem Microsoft Intune hem de MICROSOFT dışı MDM hizmet sağlayıcılarındaki Windows 10 için yönetim görevlerinin ve ilkelerinin çoğundan daha gerisinde bulunur. Ayrıca, bir [sağlama paketi](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) oluşturmak ve bunu HoloLens 2 ' ye uygulamak Için [Windows yapılandırma Tasarımcısı](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) ' nı kullanabilirsiniz.
HoloLens 2 ' ye uygulanacak en olası CSP 'Ler şunlardır:

- [WIFI CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): profil başına Wi-Fi proxy 

[HoloLens cihazlarında desteklenen diğer CSP 'Ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN bağlantısı, şirketinizin ağına ve Internet 'e daha güvenli bir bağlantı ve erişim sağlamaya yardımcı olabilir. HoloLens 2 yerleşik VPN istemcisi ve Evrensel Windows Platformu (UWP) VPN eklentisini destekler. 

Desteklenen yerleşik VPN protokolleri:
- IKEv2
- L2TP
- PPTP

Sertifika, yerleşik VPN istemcisi için kimlik doğrulaması için kullanılıyorsa, gerekli istemci sertifikasının Kullanıcı sertifika deposuna eklenmesi gerekir. Bir 3. taraf VPN eklentisinin HoloLens 2 ' yi destekleyip desteklemediğini bulmak için, Mağaza ' ya giderek VPN uygulamasını bulun ve HoloLens 'in desteklenen bir cihaz olarak listelenip listelenmediğini denetleyin ve uygulama ARM veya ARM64 mimarisini destekler. HoloLens yalnızca 3. taraf VPN için Evrensel Windows Platformu uygulamalarını destekler.

 VPN, [Ayarlar/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla MDM tarafından yönetilebilir ve  [Vpnv2-CSP ilkesi](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)aracılığıyla ayarlanabilir.

[Bu KıLAVUZLARLA](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide) [VPN yapılandırma](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) hakkında daha fazla bilgi edinin.  

### <a name="vpn-via-ui"></a>Kullanıcı arabirimi üzerinden VPN

VPN varsayılan olarak etkin değildir, ancak  Ayarlar uygulaması açarak ve İnternet **-& VPN'e > etkinleştirilebilir.**
1. Bir VPN sağlayıcısı seçin.
1. Bağlantı adı oluşturun. 
1. Sunucu adı veya adresinizi girin.
1. VPN türünü seçin.
1. Oturum açma bilgileri türünü seçin. 
1. İsteğe bağlı olarak kullanıcı adı ve parola ekleyin.
1. VPN ayarlarını uygulama. 

![HoloLens VPN ayarları](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Sağlama Paketi aracılığıyla VPN kümesi

> [!TIP] 
> Windows Holographic sürüm 20H2'de VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi. Bu akışı kullanmak için lütfen cihazları bu derlemeye yükseltmeyi göz önünde bulundurabilirsiniz.

1. Windows Yapılandırma Tasarımcısı'ı başlatma.
1. **HoloLens cihazlarını sağlama'ya tıklayın,** ardından hedef cihazı ve Sonraki'yi **seçin.**
1. Paket adını ve yolunu girin.
1. Gelişmiş **düzenleyiciye geç'e tıklayın.**
1. Çalışma **zamanı ayarları**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings'i açın.**
1. VPNProfileName yapılandırma
1. Profil Türü: Yerel **veya Üçüncü** **Taraf'ı seçin.**
    1. Yerel profil için **NativeProtocolType'ı seçin,** ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırabilirsiniz.
    1. "Üçüncü Taraf" profili için sunucu URL'sini, VPN eklentisi Uygulama paketi aile adını (önceden tanımlanmış yalnızca 3) ve özel yapılandırmaları yapılandırabilirsiniz.
1. Paketinizi dışarı aktarın.
1. HoloLens'inizi bağlama ve .ppkg dosyasını cihaza kopyalama. 
1. HoloLens'de, Başlat menüsü'yi açarak ve Ayarlar Hesap Erişimi iş veya okul Sağlama paketi ekleme veya kaldırma -> VPN paketinizi seçin'i seçerek VPN .ppkg'yi  ->    ->    ->   uygulayabilirsiniz.


### <a name="setting-up-vpn-via-intune"></a>Intune aracılığıyla VPN ayarlama
Çalışmaya devam etmek için Intune belgelerini takip edin. Bu adımları takip edin ve HoloLens cihazlarının desteklemektedir yerleşik VPN protokollerini unutmayın. 

[Intune'da VPN sunucularına bağlanmak için VPN profilleri oluşturun.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)

Windows 10 kullanarak VPN bağlantıları eklemek için Windows [Holographic cihaz ayarlarını kullanın.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Bittiğinde lütfen profilini [atamayı unutmayın.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)

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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>HoloLens'Wi-Fi devre dışı bırakma (1. nesil)

### <a name="using-the-settings-app-on-hololens"></a>HoloLens'de Ayarlar uygulamasını kullanma

1. Başlat **menüsünü** açın.
1. Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **ve İnternet & seçin.**
1. Kaydırıcıyı Wi-Fi kaydırıcısını seçerek Kapalı **konuma taşıyın.** Bu, holoLens'de Wi-Fi rf bileşenlerini devre dışı Wi-Fi devre dışı bıraktır.

    > [!WARNING]
    > Sanal Wi-Fi devre dışı bırakılmıştır, HoloLens alanlarınızı otomatik olarak [yükemez.](hololens-spaces.md)

1. Kaydırıcı anahtarını Açık konuma **hareket ettirerek** Wi-Fi açma ve Wi-Fi geri yükleme işlevlerini Microsoft HoloLens. Seçilen radyo Wi-Fi ( Açık **veya Kapalı)** yeniden başlatmalarda kalıcı olur. 

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Sanal ağ üzerinde HoloLens'inizin IP Wi-Fi tanımlama

### <a name="by-using-the-settings-app"></a>Ayarlar uygulamasını kullanarak

1. Başlat **menüsünü** açın.
1. Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **ve İnternet & seçin.**
1. Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**

    ![Wi-Fi ayarlarında donanım özellikleri](./images/wifi-hololens-hwdetails.jpg)

   IP adresi, **IPv4 adresinin yanında görünür.**

### <a name="by-using-voice-commands"></a>Ses komutlarını kullanarak

Cihaz derlemenize bağlı olarak, ip adresinizi görüntülemek için yerleşik sesli komutları veya Cortana'yı kullanabilirsiniz. [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sonrasındaki derlemelerde "IP adresim nedir?" görüntülenir. Önceki derlemeler veya HoloLens (1. nesil) için "Hey Cortana, IP adresim nedir?" Cortana IP adresinizi görüntüler ve okur.

### <a name="by-using-windows-device-portal"></a>Windows Cihaz Portalı

1. Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Ağ **bölümüne** gidin.  
   Bu bölümde IP adresiniz ve diğer ağ bilgileri görüntülenir. Bu yöntemi kullanarak IP adresini kopyalayıp geliştirme bilgisayarınıza yapıştırabilirsiniz.

## <a name="change-ip-address-to-static-address"></a>IP Adresini statik adres olarak değiştirme
### <a name="by-using-settings"></a>Ayarlar'ı kullanarak
 
1. Başlat **menüsünü** açın.
1. Başlat **menüsünden** veya **Başlat** menüsünün **sağ tarafından** tüm Uygulamalar listesinden Ayarlar **uygulamasını** seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **ve İnternet & seçin.**
1. Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**
1. IP **ayarlarını düzenle penceresinde** ilk alanı El ile olarak **değiştirin.**
1. Kalan alanlara istenen IP yapılandırmasını girin ve Kaydet'e **tıklayın.**

### <a name="by-using-windows-device-portal"></a>Windows Cihaz Portalı

1. Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Ağ **bölümüne** gidin.
1. **IPv4 Yapılandırması düğmesini** seçin.
1. Aşağıdaki **IP adresini kullan'ı seçin** ve istediğiniz TCP/IP yapılandırmasını girin.
1. Aşağıdaki **DNS sunucusu adreslerini kullan'ı seçin** ve gerekirse Tercih edilen ve Alternatif DNS sunucusu adreslerini girin.
1. **Kaydet**’e tıklayın. 
