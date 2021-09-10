---
title: HoloLens 2 için sertifikaları ve ağ profillerini hazırlayın
description: HoloLens 2 karma gerçeklik cihazlarındaki ağ için sertifikaları yapılandırma, kullanma, dağıtma ve sorun giderme hakkında bilgi edinin.
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
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428922"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>HoloLens 2 için sertifikaları ve ağ profillerini hazırlayın

sertifika tabanlı kimlik doğrulaması, HoloLens 2 kullanan müşteriler için ortak bir gereksinimdir. Wi-Fi ' e erişmek, VPN çözümlerine bağlanmak veya kuruluşunuzdaki iç kaynaklara erişmek için sertifikalara ihtiyaç duyabilirsiniz.

HoloLens 2 cihaz genellikle Azure Active Directory (Azure AD) ve ıntune veya diğer MDM sağlayıcısı tarafından yönetilen olduğundan, MDM çözümünüz ile tümleştirilmiş bir Basit Sertifika Kayıt Protokolü (SCEP) veya ortak anahtar şifreleme standardı (PKCS) sertifika altyapısını kullanarak bu tür sertifikaları dağıtmanız gerekir. 

>[!NOTE]
> MDM sağlayıcınız yoksa, [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) 'daki bir [sağlama paketiyle](hololens-provisioning.md#steps-for-creating-provisioning-packages) veya [sertifika yöneticisi](certificate-manager.md) aracılığıyla sertifikaları dağıtmaya devam edebilirsiniz **Ayarlar > & güvenlik > sertifika yöneticisi**' ne gidin.

## <a name="certificate-requirements"></a>Sertifika gereksinimleri
Kök sertifikalar, bir SCEP veya PKCS altyapısı aracılığıyla sertifika dağıtmak için gereklidir. kuruluşunuzdaki diğer uygulamalar ve hizmetler, HoloLens 2 cihazlarınıza da kök sertifikaların dağıtılmasını gerektirebilir. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi bağlantısı gereksinimleri
Bir cihazın kurumsal ağınız için gereken Wi-Fi yapılandırmasıyla otomatik olarak sağlanmasını sağlamak için bir Wi-Fi yapılandırma profiline ihtiyacınız olacaktır. Intune veya diğer MDM sağlayıcısını, bu profilleri cihazlarınıza dağıtmak üzere yapılandırabilirsiniz. ağ güvenliği cihazların yerel etki alanının bir parçası olmasını gerektiriyorsa, HoloLens 2 cihazlarıyla uyumlu olduğundan emin olmak için Wi-Fi ağ altyapınızı değerlendirmeniz gerekebilir (HoloLens 2 cihaz yalnızca Azure AD 'ye katılmış olmalıdır).

## <a name="deploy-certificate-infrastructure"></a>Sertifika altyapısını dağıt
Hiçbir SCEP veya PKCS altyapısı zaten mevcut değilse, bir tane hazırlamanız gerekir. Kimlik doğrulaması için SCEP veya PKCS sertifikalarının kullanımını desteklemek için Intune 'un bir [sertifika Bağlayıcısı](/mem/intune/protect/certificate-connectors)kullanması gerekir.

> [!NOTE]
> Bir Microsoft CA ile SCEP kullandığınızda, [ağ cihazı kayıt hizmeti 'ni (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes) da yapılandırmanız gerekir.

Daha fazla bilgi için, bkz [. Microsoft Intune cihazlarınız için sertifika profili yapılandırma.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Sertifikaları ve Wi-Fi/VPN profilini dağıtma
Sertifikaları ve profilleri dağıtmak için şu adımları izleyin:
1.  Kök ve ara sertifikaların her biri için bir profil oluşturun (bkz. [Güvenilen sertifika profilleri oluşturma](/intune/protect/certificates-configure#create-trusted-certificate-profiles).) Bu profillerin her biri GG/AA/YYYY biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Süre sonu tarihi olmayan sertifika profilleri dağıtılmaz.**
1.  Her SCEP veya PKCS sertifikaları için bir profil oluşturun (bkz. [SCEP sertifika profili oluşturma veya PKCS sertifika profili oluşturma](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) Bu profillerin her bırı, gg/aa/yyyy biçiminde bir sona erme tarihi içeren bir açıklamaya sahip olmalıdır. **Süre sonu tarihi olmayan sertifika profilleri dağıtılmaz.**

    > [!NOTE]
    > HoloLens 2 çok sayıda paylaşılan cihaz, cihaz başına birden çok kullanıcı olarak değerlendirildiğinden, mümkün olduğunda Wi-Fi kimlik doğrulaması için kullanıcı sertifikaları yerine cihaz sertifikalarını dağıtmanız önerilir

3.  her kurumsal Wi-Fi ağı için bir profil oluşturun (bkz. [Windows 10 ve üzeri cihazlar için Wi-Fi ayarları](/intune/wi-fi-settings-windows)). 
    > [!NOTE]
    > Wi-Fi profilinin mümkün olduğunda Kullanıcı grupları yerine cihaz gruplarına [atanması](/mem/intune/configuration/device-profile-assign) önerilir. 

    > [!TIP]
    > ayrıca, çalışan bir Wi-Fi profilini şirket ağınızdaki bir Windows 10 bilgisayardan dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm geçerli ayarlarla bir XML dosyası oluşturur. ardından, bu dosyayı ıntune 'a aktarın ve HoloLens 2 cihazlarınızın Wi-Fi profili olarak kullanın. bkz [. Windows cihazlar için Wi-Fi ayarlarını dışa ve içeri aktarma.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  her kurumsal VPN için bir profil oluşturun ( [ıntune kullanarak vpn bağlantıları eklemek için bkz. Windows 10 ve Windows Holographic cihaz ayarları](/intune/vpn-settings-windows-10)).

## <a name="troubleshooting-certificates"></a>Sertifika sorunlarını giderme

Bir sertifikanın doğru şekilde dağıtıldığını doğrulamanız gereken olayda Lütfen sertifikanızın mevcut olduğunu doğrulamak için cihazdaki [sertifika yöneticisini](certificate-manager.md) kullanın.  

>[!WARNING]
> MDM ile dağıtılan sertifikaları sertifika yöneticisi 'nde görüntüleyebilseniz de, bunları Sertifika Yöneticisi 'nde kaldıramazsınız. MDM aracılığıyla kaldırmanız gerekir.


