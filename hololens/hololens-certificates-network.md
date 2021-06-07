---
title: HoloLens 2 için sertifikaları ve ağ profillerini hazırlama
description: HoloLens 2 karma gerçeklik cihazlarından ağ sertifikalarını yapılandırmayı, kullanmayı, dağıtmayı ve sorunlarını gidermeyi öğrenin.
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
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380158"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>HoloLens 2 için sertifikaları ve ağ profillerini hazırlama

Sertifika tabanlı kimlik doğrulaması, HoloLens 2 kullanan müşteriler için yaygın bir gereksinimdir. Wi-Fi'a erişmek, VPN çözümlerine bağlanmak veya kuruluş içi kaynaklara erişmek için sertifikalar gerekli olabilir.

HoloLens 2 cihazları genellikle Azure Active Directory (Azure AD) ile birleştirilip Intune veya diğer MDM sağlayıcısı tarafından yönetiliyor olduğundan, bu sertifikaları MDM çözümünüzle tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya Ortak Anahtar Şifreleme Standardı (PKCS) sertifika altyapısı kullanarak dağıtmanız gerekir. 

>[!NOTE]
> MDM sağlayıcınız yoksa, [Windows Yapılandırma](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) Tasarımcısı'nda veya [](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) Sertifika Yöneticisi'nde bir sağlama [](https://docs.microsoft.com/hololens/certificate-manager) paketi aracılığıyla Ayarlar > Update & Security > Sertifika Yöneticisi'ne gidip sertifikaları **dağıtabilirsiniz.**

## <a name="certificate-requirements"></a>Sertifika gereksinimleri
Sertifikaları bir SCEP veya PKCS altyapısı aracılığıyla dağıtmak için kök sertifikalar gerekir. HoloLens 2 cihazlarınıza kök sertifikaların da dağıtılmasını gerektiren diğer uygulamalar ve hizmetler vardır. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi bağlantı gereksinimleri
Bir cihazın kurumsal ağınız için gerekli yapılandırma Wi-Fi otomatik olarak sağlanacak şekilde izin vermek için bir Wi-Fi profili gerekir. Bu profilleri cihazlarınıza dağıtmak için Intune veya diğer MDM sağlayıcısını yapılandırabilirsiniz. Ağ güvenliğiniz için cihazların yerel etki alanına dahil olması gerekirse, HoloLens 2 cihazlarıyla uyumlu olduğundan emin olmak için Wi-Fi ağ altyapınızı da değerlendirmeniz gerekir (HoloLens 2 cihazları yalnızca Azure AD'ye katılmış).

## <a name="deploy-certificate-infrastructure"></a>Sertifika altyapısını dağıtma
SCEP veya PKCS altyapısı zaten yoksa, bir tane hazırlamamız gerekir. Kimlik doğrulaması için SCEP veya PKCS sertifikalarının kullanımını desteklemek için, Intune bir sertifika bağlayıcısı [kullanımını gerektirir.](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)

> [!NOTE]
> SCEP'yi bir Microsoft CA ile birlikte kullanırken, Ağ Cihazı Kayıt Hizmeti [(NDES) yapılandırmalı](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Daha fazla bilgi için, [bkz. Configure a certificate profile for your devices in Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Sertifikaları ve Wi-Fi/VPN profilini dağıtma
Sertifikaları ve profilleri dağıtmak için şu adımları izleyin:
1.  Kök ve Ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma.)](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Bu profillerin her biri DD/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**
1.  Her SCEP veya PKCS sertifikası için bir profil oluşturun (bkz. SCEP sertifika profili oluşturma veya [PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)sertifika profili oluşturma) Bu profillerden her biri DD/AA/YYYY biçiminde sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Sona erme tarihi olmayan sertifika profilleri dağıtılacaktır.**

    > [!NOTE]
    > HoloLens 2'nin paylaşılan bir cihaz, cihaz başına birden çok kullanıcı olduğu kabul edilir ve mümkün olduğunca cihaz kimlik doğrulaması için Kullanıcı sertifikaları yerine Cihaz sertifikaları Wi-Fi önerilir

3.  Her kurumsal ağ için bir profil Wi-Fi (bkz. Ağ ve Windows 10 cihazlar [için Wi-Fi ayarları).](https://docs.microsoft.com/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Mümkün olduğunca Wi-Fi [kullanıcı](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) grupları yerine Cihaz gruplarına atanmalarını öneririz. 

    > [!TIP]
    > Ayrıca, kurumsal ağ Wi-Fi bir Windows 10 profili dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. Ardından bu dosyayı Intune'a aktarın ve HoloLens 2 Wi-Fi profil olarak kullanın. Bkz. [Windows cihazları Wi-Fi dışarı ve içeri aktarma.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Her şirket VPN'i için bir profil [oluşturun (Intune kullanarak VPN Windows 10 ve Windows Holographic cihaz ayarlarına bakın).](https://docs.microsoft.com/intune/vpn-settings-windows-10)

## <a name="troubleshooting-certificates"></a>Sertifika sorunlarını giderme

Bir sertifikanın doğru şekilde dağıtıldığından emin olmak için [](certificate-manager.md) lütfen sertifikanın mevcut olduğunu doğrulamak için cihazda Sertifika Yöneticisi'ni kullanın.  

>[!WARNING]
> Sertifika Yöneticisi'nde MDM tarafından dağıtılan sertifikaları görüntüleyebizle birlikte, bunları Sertifika Yöneticisi'nde kaldıramazsiniz. Bunları MDM aracılığıyla kaldırmanız gerekir.


