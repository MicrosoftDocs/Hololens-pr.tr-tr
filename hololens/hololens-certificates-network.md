---
title: HoloLens 2 için sertifikaları ve ağ profillerini hazırlama
description: 2 karma gerçeklik cihazı kullanarak ağ sertifikalarını yapılandırmayı, kullanmayı, dağıtmayı ve HoloLens gidermeyi öğrenin.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d9b752c820af8dbceb2b6b9f3c7a7be4df910805b5a5014bb3e3650551392ce8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664322"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>HoloLens 2 için sertifikaları ve ağ profillerini hazırlama

Sertifika tabanlı kimlik doğrulaması, HoloLens 2 kullanan müşteriler için yaygın bir gereksinimdir. Wi-Fi'a erişmek, VPN çözümlerine bağlanmak veya kuruluş içi kaynaklara erişmek için sertifikalar gerekli olabilir.

HoloLens 2 cihaz genellikle Azure Active Directory (Azure AD) ile birleştirilip Intune veya diğer MDM sağlayıcısı tarafından yönetiliyorsa, bu tür sertifikaları MDM çözümünüzle tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya Ortak Anahtar Şifreleme Standardı (PKCS) sertifika altyapısı kullanarak dağıtmanız gerekir. 

>[!NOTE]
> MDM sağlayıcınız yoksa, Windows Yapılandırma Tasarımcısı'nda veya [](hololens-provisioning.md#steps-for-creating-provisioning-packages) Sertifika Yöneticisi'nde bir sağlama paketi [](certificate-manager.md) aracılığıyla sertifika dağıtmaya devam etmek için [Ayarlar >](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) Update & Security > Certificate Manager 'a gidip sertifika **dağıtabilirsiniz.**

## <a name="certificate-requirements"></a>Sertifika gereksinimleri
Sertifikaları bir SCEP veya PKCS altyapısı aracılığıyla dağıtmak için kök sertifikalar gerekir. Kuruluşta yer alan diğer uygulama ve hizmetler, kök sertifikaların 2 cihaza HoloLens gerektirmektedir. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi bağlantı gereksinimleri
Bir cihazın kurumsal ağınız için gerekli yapılandırma Wi-Fi otomatik olarak sağlanacak şekilde izin vermek için bir Wi-Fi profili gerekir. Bu profilleri cihazlarınıza dağıtmak için Intune veya diğer MDM sağlayıcısını yapılandırabilirsiniz. Ağ güvenliğiniz için cihazların yerel etki alanına dahil olması gerekirse, Wi-Fi ağ altyapınızı değerlendirerek HoloLens 2 cihazlarıyla uyumlu olduğundan emin olun (HoloLens 2 cihaz yalnızca Azure AD'ye katılmış olabilir).

## <a name="deploy-certificate-infrastructure"></a>Sertifika altyapısını dağıtma
Henüz bir SCEP veya PKCS altyapısı yoksa, bir tane hazırlamamız gerekir. Kimlik doğrulaması için SCEP veya PKCS sertifikalarının kullanımını desteklemek için, Intune bir sertifika bağlayıcısı [kullanımını gerektirir.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> SCEP'yi bir Microsoft CA ile birlikte kullanırken, Ağ Cihazı Kayıt Hizmeti [(NDES) yapılandırmalı](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Daha fazla bilgi için, [bkz. Configure a certificate profile for your devices in Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Sertifikaları ve Wi-Fi/VPN profilini dağıtma
Sertifikaları ve profilleri dağıtmak için şu adımları izleyin:
1.  Kök ve Ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma.)](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Bu profillerin her biri DD/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**
1.  Her SCEP veya PKCS sertifikası için bir profil oluşturun (bkz. SCEP sertifika profili oluşturma veya [PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)sertifika profili oluşturma) Bu profillerden her biri DD/AA/YYYY biçiminde sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

    > [!NOTE]
    > HoloLens 2, birçoğu paylaşılan cihaz , cihaz başına birden çok kullanıcı olarak kabul edilir, mümkün olduğunca cihaz kimlik doğrulaması için Kullanıcı sertifikaları yerine Cihaz sertifikaları Wi-Fi önerilir

3.  Her kurumsal ağ için bir profil Wi-Fi (bkz. Windows 10 ve sonraki [cihazlar için Wi-Fi ayarları).](/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Mümkün olduğunca Wi-Fi [kullanıcı](/mem/intune/configuration/device-profile-assign) grupları yerine Cihaz gruplarına atanmalarını öneririz. 

    > [!TIP]
    > Ayrıca, kurumsal ağ Wi-Fi bir Windows 10 profili dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'a aktarın ve 2 Wi-Fi için HoloLens profili olarak kullanın. Bkz. [Cihazlar için Wi-Fi dışarı ve içeri Windows alma.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Her kurumsal VPN için bir profil oluşturun [(Intune kullanarak VPN Windows 10 eklemek Windows Holographic](/intune/vpn-settings-windows-10)cihaz ayarlarına bakın ve bu ayarları kullanın).

## <a name="troubleshooting-certificates"></a>Sertifika sorunlarını giderme

Bir sertifikanın doğru şekilde dağıtıldığından emin olmak için [](certificate-manager.md) lütfen sertifikanın mevcut olduğunu doğrulamak için cihazda Sertifika Yöneticisi'ni kullanın.  

>[!WARNING]
> Sertifika Yöneticisi'nde MDM tarafından dağıtılan sertifikaları görüntüleyebizle birlikte, bunları Sertifika Yöneticisi'nde kaldıramazsiniz. Bunları MDM aracılığıyla kaldırmanız gerekir.


