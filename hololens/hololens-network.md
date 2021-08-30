---
title: Bağlan HoloLens ağa bağlantı
description: HoloLens ile İnternet'i ayarlamayı ve İnternet'e bağlamayı ve cihaz IP adresini tanımlamayı öğrenin.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, kablosuz, internet, ip, ip adresi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189112"
---
# <a name="connect-hololens-to-a-network"></a>Bağlan HoloLens ağa bağlantı

Ağ üzerinde çoğu HoloLens yapmak için bir ağa bağlı olmak gerekir. HoloLens 802.11ac özellikli, 2x2 Wi-Fi radyo içerir ve bir ağa bağlamak, Windows 10 Desktop veya Mobil cihazı bir Wi-Fi ağına bağlamaya benzer. Bu kılavuz size yardımcı olacaktır:

- Bağlan Wi-Fi kullanarak ağa veya yalnızca HoloLens 2 için, USB-C üzerinden Wi-Fi Veya Ethernet'e bağlanın
- Wi-Fi'yi devre dışı bırakma ve yeniden etkinleştirme

Çevrimdışı uygulama kullanma [hakkında daha HoloLens okuyun.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>İlk kez bağlanma

Ağ bağlantınızı ilk kez HoloLens, bir ağ ile bağlantı Wi-Fi yönlendirebilirsiniz. Kurulum sırasında ağ Wi-Fi sorunlarınız varsa, ağın açık, parola korumalı bir ağ veya bir portal ağı olduğundan emin olun. Ayrıca, ağın bağlanmak için bir sertifika kullanmanızı gerektirmeyen bir sertifika olduğunu onaylayın. Kurulumdan sonra, diğer ağ türlerine Wi-Fi bağlanabilirsiniz.

Bir HoloLens 2 cihazda, bir kullanıcı cihazı ayarlamaya yardımcı olmak üzere doğrudan Wi-Fi bağlanmak için [USB-C'den Ethernet'e](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) bağdaştırıcısı da kullanabilir. Cihaz ayar verdikten sonra bir kullanıcı bağdaştırıcıyı kullanmaya devam eder veya cihazı bağdaştırıcıdan kesdikten sonra [wi-fi bağlantısı kurarak bağlantısı kesebilirsiniz.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>Kurulumdan sonra Wi-Fi bağlantı kurma

1. Başlangıç hareketini **önceden biçimlendirilmiş** olarak **Ayarlar.** Ayarlar uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **bağlantısı & İnternet**  >  **Wi-Fi'ı seçin.** Wi-Fi’ın açık olduğundan emin olun. Anızı görmüyorsanız listeyi aşağı kaydırın.
1. Bir ağ seçin ve sonra da ağ **Bağlan.**
1. Bir ağ parolası girmeniz istenirse parolayı yazın ve ardından Sonraki'yi **seçin.**

![HoloLens Wi-Fi ayarları.](./images/hololens-2-wifi-settings.jpg)

Wi-Fi ağına bağlı olduğunuzdan emin olmak Wi-Fi menüsünden durumu **kontrol** edin:

1. Başlat **menüsünü** açın.
1. Durum bilgi için Başlat **menüsünün** sol üst Wi-Fi bakın. Bağlı ağın Wi-Fi SSID'leri ve ağ bağlantılarının durumu gösterilir.

> [!TIP]
> Bu Wi-Fi yoksa Hücresel ve [5G ağlarına da bağlanabilirsiniz.](hololens-cellular.md)

> [!IMPORTANT]
> Tasarım olarak, kullanıcılar HoloLens 2'nin Wi-Fi dolaşım davranışında ince ayarlamalar Wi-Fi listesini yenilemenin tek yolu Wi-Fi Kapalı ve Açık **olarak ayarlamaktır.** Bu, bir cihazın aralık dışından bir AP'ye "takılı kalarak" kalamaması gibi birçok sorunu önler.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Bağlan HoloLens ağ Enterprise Wi-Fi için

Enterprise Wi-Fi profiller, bağlantılarda kimlik doğrulaması yapmak için Genişletilebilir Kimlik Doğrulama Protokolü'Wi-Fi kullanır. HoloLens Enterprise Wi-Fi profili, MDM aracılığıyla ya da Windows Yapılandırma Tasarımcısı [tarafından oluşturulan sağlama paketi aracılığıyla yalıtabilirsiniz.](/windows/configuration/provisioning-packages/provisioning-packages)

Yönetilen Microsoft Intune için yapılandırma yönergeleri [için Intune'a](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) bakın.

WCD'de Wi-Fi paketi oluşturmak için önceden yapılandırılmış bir Wi-Fi profili .xml dosyası gerekir. EAP-TLS kimlik Wi-Fi için WPA2-Enterprise profili örneği:

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


EAP türüne bağlı olarak cihazda sunucu kök CA sertifikasının ve istemci sertifikasının sağlanması gerekir.

Ek kaynaklar:

- WLANv1Profile Şeması: [[MS-GPWL]: Kablosuz LAN Profili v1 Şema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS Şeması: [[MS-GPWL]: Microsoft EAP TLS Şeması | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

[Wi-Fi'ınıza](hololens2-enterprise-troubleshooting.md#) bağlanırken sorun giderme sayfamızı kontrol edin.

## <a name="configure-network-proxy"></a>Ağ Ara Sunucusunu Yapılandırma

Bu bölüm, http yığınını kullanan HoloLens işletim sistemi ve Evrensel Windows Platformu (UWP) uygulamaları için Windows ara sunucusunu kapsar. HTTP yığınında Windows uygulamalar kendi ara sunucu yapılandırmasına ve işlemeye sahip olabilir. 

### <a name="proxy-configurations"></a>Proxy Yapılandırmaları 

- Proxy Otomatik Yapılandırma (PAC) betiği: [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) dosyası (Microsoft olmayan bir site açar) FindProxyForURL(url, host) JavaScript işlevi içerir. 
- Statik Ara Sunucu: Sunucu:Bağlantı Noktası şeklinde.  
- Web Proxy Otomatik Bulma Protokolü (WPAD): DHCP veya DNS aracılığıyla ara sunucu yapılandırma dosyasının URL'sini belirtin. 

### <a name="proxy-provisioning-methods"></a>Ara Sunucu Sağlama Yöntemleri 
İki tane sağlamanın üç yolu vardır:

 

1.  **Ayarlar UI:** 
    1. Kullanıcı başına ara sunucu (20H2 veya önceki):
        1. Dosyayı açın Başlat menüsü'ı Ayarlar.
        2. Ağ ve &'yi ve ardından sol menüde Ara Sunucu'ya tıklayın.
        3. Ekranı aşağı kaydırarak El ile ara sunucu kurulumu'nı seçin ve Ara sunucu kullan'ı Açık olarak kaydırın.
        4. Proxy sunucusunun IP adresini girin.
        5. Bağlantı noktası numarasını girin.
        6. Kaydet’e tıklayın.
      1. WiFi ara sunucusu (21H1 veya daha yüksek):
          1. Ağ Başlat menüsü açın ve Wi-Fi Ağının Özellikler sayfasına gidin.
          1. Ekranı aşağı kaydırarak Ara Sunucu'ya kaydırın
          1. El ile Kurulum olarak değiştirme
          1. Proxy sunucusunun IP adresini girin.
          1. Bağlantı noktası numarasını girin.
          1. Uygula'ya tıklayın.
        
 2. **MDM** 
     1. Intune - [Intune'da](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) ara sunucu yapılandırmak için bu adımları kullanın. Bölümün en altına kaydırmalısiniz.
     1. Diğer 3. taraf MDM çözümleri - [WiFi CSP kullanın.](/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. Açık Windows Yapılandırma Tasarımcısı
    1. Gelişmiş Sağlama'ya tıklayın, yeni kullanıcı adınıza Project İleri'ye tıklayın.
    1. Holographic Windows (HoloLens 2) öğesini seçin ve Ardından'ya tıklayın.
    1. PPKG'nizi içeri aktarın (isteğe bağlı) ve Son'a tıklayın.
    1. Çalışma Zamanı Ayarlar -> Bağlantı Profilleri -> WLAN -> WLAN Ara Sunucusu'> genişletin.
    1. Ağ ağ Wi-Fi SSID'yi girin ve Ekle'ye tıklayın.
    1. Sol pencerede Wi-Fi ağına tıklayın ve istediğiniz özelleştirmeleri girin. Etkinleştirildiğinde özelleştirmeler sol menüde kalın olarak gösterilir.
    1. Kaydet ve Çık'a tıklayın.
    1. [Sağlama](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) paketini HoloLens.

[CSP'ler,](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) hem Microsoft Intune hem de Microsoft olmayan MDM hizmet sağlayıcılarında Windows 10 için yönetim görevlerinin ve ilkelerinin birçoğundadır. Bir sağlama paketi [Windows ve](/windows/configuration/provisioning-packages/provisioning-install-icd) bunu HoloLens [](/windows/configuration/provisioning-packages/provisioning-packages) 2'ye uygulamak için de HoloLens kullanabilirsiniz.
En olası CSP'ler, 2. HoloLens uygulanır:

- [WiFi CSP:](/windows/client-management/mdm/wifi-csp)profil başına Wi-Fi ara sunucusu 

[HoloLens cihazlarda desteklenen diğer CSP'ler](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
VPN bağlantısı, daha güvenli bir bağlantı ve şirket ağı ile İnternet erişimi sağlamanıza yardımcı olabilir. HoloLens 2, yerleşik VPN istemcisini ve Evrensel Windows Platformu (UWP) VPN eklentisini destekler. 

Desteklenen Yerleşik VPN protokolleri:
- IKEv2
- L2TP
- PPTP

Yerleşik VPN istemcisi için kimlik doğrulaması için sertifika kullanılıyorsa, gerekli istemci sertifikasının kullanıcı sertifika deposuna eklenmiş olması gerekir. 3. taraf BIR VPN eklentisinin HoloLens 2'nin destekleyip desteklemediklerini bulmak için, VPN uygulamasını bulmak için Mağaza'ya gidin, HoloLens'nin desteklenen bir cihaz olarak listelenmiş olup olduğunu ve uygulamanın ARM veya ARM64 mimarisini desteklediği Sistem Gereksinimi sayfasından kontrol edin. HoloLens, yalnızca 3. Windows VPN için Universal Windows Platform uygulamalarını destekler.

 VPN, MDM tarafından [Ayarlar/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)aracılığıyla yönetilebilir ve [Vpnv2-csp ilkesi aracılığıyla ayarlanır.](/windows/client-management/mdm/vpnv2-csp)

Vpn'i [yapılandırma hakkında daha fazla bilgi için](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) bu kılavuzları [kullanın.](/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>Kullanıcı arabirimi üzerinden VPN

VPN varsayılan olarak etkin değildir, ancak Ayarlar uygulaması açarak **ve İnternet** **-& VPN'e > etkinleştirilebilir.**
1. Bir VPN sağlayıcısı seçin.
1. Bağlantı adı oluşturun. 
1. Sunucu adı veya adresinizi girin.
1. VPN türünü seçin.
1. Oturum açma bilgileri türünü seçin. 
1. İsteğe bağlı olarak kullanıcı adı ve parola ekleyin.
1. VPN ayarlarını uygulama. 

![HoloLens VPN ayarları.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Sağlama Paketi aracılığıyla VPN kümesi

> [!TIP] 
> Holographic Windows sürüm 20H2'de VPN bağlantısı için ara sunucu yapılandırma sorunu düzeltildi. Bu akışı kullanmak için lütfen cihazları bu derlemeye yükseltmeyi göz önünde bulundurabilirsiniz.

1. Yapılandırma Windows'i başlatma.
1. Cihazları **HoloLens'a tıklayın,** ardından hedef cihazı ve Sonraki'yi **seçin.**
1. Paket adını ve yolunu girin.
1. Gelişmiş **düzenleyiciye geç'e tıklayın.**
1. Çalışma **zamanı ayarları**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings'i açın.**
1. VPNProfileName yapılandırma
1. Profil Türü: Yerel **veya Üçüncü** **Taraf'ı seçin.**
    1. Yerel profil için **NativeProtocolType'ı seçin,** ardından sunucu, yönlendirme ilkesi, kimlik doğrulama türü ve diğer ayarları yapılandırabilirsiniz.
    1. "Üçüncü Taraf" profili için sunucu URL'sini, VPN eklentisi Uygulama paketi aile adını (önceden tanımlanmış yalnızca 3) ve özel yapılandırmaları yapılandırabilirsiniz.
1. Paketinizi dışarı aktarın.
1. Bağlan HoloLens ve .ppkg dosyasını cihaza kopyalayın. 
1. Bu HoloLens, Başlat menüsü'yi açarak ve Ayarlar Hesap Erişimi iş veya okul Sağlama paketi ekle veya kaldır -> VPN paketinizi seçin'i seçerek VPN .ppkg'yi  ->    ->    ->   uygulayabilirsiniz.


### <a name="setting-up-vpn-via-intune"></a>Intune aracılığıyla VPN ayarlama
Çalışmaya devam etmek için Intune belgelerini takip edin. Bu adımları takip edin ve bu cihazları destekleyen yerleşik VPN HoloLens unutmayın. 

[Intune'da VPN sunucularına bağlanmak için VPN profilleri oluşturun.](/mem/intune/configuration/vpn-settings-configure)

[Windows 10 kullanarak WINDOWS eklemek için Holographic cihaz](/mem/intune/configuration/vpn-settings-windows-10)ayarlarını kullanın ve kullanın.

Bittiğinde lütfen profilini [atamayı unutmayın.](/mem/intune/configuration/device-profile-assign)

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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Wi-Fi 'de HoloLens devre dışı bırakma (1. nesil)

### <a name="using-the-settings-app-on-hololens"></a>Ayarlar'da HoloLens

1. Başlat **menüsünü** açın.
1. **Başlat Ayarlar** **menüsünden** veya Sağdan Tüm **Uygulamalar** listesinden uygulamanın **seçerek** uygulamayı seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **ve İnternet & seçin.**
1. Kaydırıcıyı Wi-Fi kaydırıcısını seçerek Kapalı **konuma taşıyın.** Bu, Wi-Fi radyonun RF bileşenlerini devre dışı Wi-Fi tüm HoloLens.

    > [!WARNING]
    > Yeni Wi-Fi devre dışı HoloLens, alanlarınızı otomatik olarak [yükleyemez.](hololens-spaces.md)

1. Kaydırıcı anahtarını Açık konuma **hareket ettirerek** Wi-Fi açma ve Wi-Fi geri yükleme Microsoft HoloLens. Seçilen radyo Wi-Fi (**Açık veya Kapalı)** **yeniden** başlatmalarda kalıcı olur.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Ağ ağ üzerinde HoloLens IP Wi-Fi tanımlama

### <a name="by-using-the-settings-app"></a>Ayarlar kullanarak

1. Başlat **menüsünü** açın.
1. **Başlat Ayarlar** **menüsünden** veya Sağdan Tüm **Uygulamalar** listesinden uygulamanın **seçerek** uygulamayı seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
1. Ağ **ve İnternet & seçin.**
1. Kullanılabilir ağların listesinin altına inin ve Wi-Fi **özellikler'i seçin.**

    ![Donanım özellikleri Wi-Fi.](./images/wifi-hololens-hwdetails.jpg)

   IP adresi, **IPv4 adresinin yanında görünür.**

### <a name="by-using-voice-commands"></a>Ses komutlarını kullanarak

Cihaz derlemenize bağlı olarak, IP adresinizi görüntülemek için yerleşik ses komutlarını Cortana komutlarını kullanabilirsiniz. [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) sonrasındaki derlemelerde "IP adresim nedir?" görüntülenir. Önceki derlemeler veya HoloLens (1. nesil) için "Merhaba Cortana, IP adresim nedir?" ve Cortana IP adresinizi görüntüler ve okur.

### <a name="by-using-windows-device-portal"></a>Windows Cihaz Portalı

1. Bilgisayarınızda bir web tarayıcısında, cihaz [portalını açın.](/windows/mixed-reality/using-the-windows-device-portal.md#networking)
1. Ağ **bölümüne** gidin.  
   Bu bölümde IP adresiniz ve diğer ağ bilgileri görüntülenir. Bu yöntemi kullanarak IP adresini kopyalayıp geliştirme bilgisayarınıza yapıştırabilirsiniz.

## <a name="change-ip-address-to-static-address"></a>IP Adresini statik adres olarak değiştirme
### <a name="by-using-settings"></a>Ayarlar
 
1. Başlat **menüsünü** açın.
1. **Başlat Ayarlar** **menüsünden** veya Sağdan Tüm **Uygulamalar** listesinden uygulamanın **seçerek** uygulamayı seçin. Ayarlar  uygulaması otomatik olarak önüne yerleştirilir.
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
