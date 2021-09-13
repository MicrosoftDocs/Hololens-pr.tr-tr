---
title: HoloLens için bağlantı uç noktalarını yönetme
description: Bağlantı uç noktalarını yönetme ve yapılandırma HoloLens bir Wi-Fi ağ üzerinden ağ bağlantısı ayarlamayı öğrenin.
keywords: hololens, çevrimdışı, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f2d9faafac2f84b727b1e10be83d4d1b53a707b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036524"
---
# <a name="manage-connection-endpoints-for-hololens"></a>HoloLens için bağlantı uç noktalarını yönetme

Bazı HoloLens bileşenleri, uygulamaları ve ilgili hizmetleri Microsoft ağ uç noktalarına veri aktarıyor. Bu makalede, bu bileşenlerin işlevsel olması için ağ yapılandırmanıza (ara sunucu veya güvenlik duvarı gibi) izin verilen farklı uç noktalar ve URL'ler listelemektedir.    

## <a name="near-offline-setup"></a>Çevrimdışına yakın kurulum

HoloLens, ağ ortamı kısıtlamaları olan müşteriler için sınırlı bir çevrimdışı deneyimler kümesi destekler. Ancak HoloLens cihaz ayarlaması için ağ bağlantısına ihtiyaç vardır ve aşağıdaki URL'lerin etkinleştirilmesi gerekir:

| Amaç | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pini | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pini | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Uç nokta yapılandırması

Yukarıdaki listeye ek olarak, HoloLens tam olarak yararlanmak için ağ yapılandırmanıza aşağıdaki uç noktaların etkinleştirilmesi gerekir.


| Amaç | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |
| Intune ve MDM Yapılandırmaları                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Sertifikalar                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana ve Ara                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Cihaz Kimlik Doğrulaması                               | login.live.com*                                                     |
| Cihaz meta verileri                                     | dmd.metaservices.microsoft.com                                      |
| Konum                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Tanılama Verileri                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Lisanslama                                           | licensing.mp.microsoft.com                                          |
| Microsoft Hesabı                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Microsoft forward link redirection service (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Ağ Bağlantı Durumu Göstergesi (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.tane                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Fotoğraflar Uygulaması                                          | evoke-windowsservices-tas.msedge.net                                |
| Ayarlar                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows Spot                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Başvurular

> [!NOTE]
> D365 Remote Assist dağıtıyorsanız, SharePoint Online için listelenen uç noktaları etkinleştirmeniz ve OneDrive İş URL'Office 365 IP adresi aralıklarında [etkinleştirmeniz gerekir.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- [Windows tanılama verilerini yapılandırma](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Windows 10 Enterprise sürüm 1903 için bağlantı uç noktalarını yönetme](/windows/privacy/manage-windows-1903-endpoints)
- [İşletim sistemi bileşenlerinden Windows 10 bileşenlerine bağlantıları Microsoft hizmetleri](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [MDM Sunucusu Windows 10 işletim sistemi bileşenlerinden Microsoft hizmetleri Microsoft Intune yönetme](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Intune ağ yapılandırması gereksinimleri ve bant genişliği](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Ağ uç noktaları Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Office 365 URL’leri ve IP adres aralıkları](/office365/enterprise/urls-and-ip-address-ranges)
- [Azure AD Connect Önkoşulları](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens sınırlamaları

Yapılandırmanız HoloLens sonra, bunu bir Wi-Fi bağlantısı olmadan kullanabilirsiniz, ancak çevrimdışı olarak HoloLens İnternet bağlantıları kullanan uygulamalara sahip olur.
