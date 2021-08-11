---
title: HoloLens 2 Uyumluluk ve GDPR
description: GDPR belgeleri
keywords: HoloLens, GDPR, gizlilik, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3365e69c8408b75a5d4e1177df938f435dec05d9dc181c698d7991159645d15a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660157"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 Gizlilik Bildirimi

GDPR'nin temel öğeleriden biri de 'tasarıma göre veri koruması'dır. Bu kavram özellikle taşınabilirlik, sınırsız internet bağlantısı ve açık iletişim kanalları nedeniyle HoloLens 2 gibi mobil cihazlar için geçerlidir. Sonuç olarak, HoloLens 2'nin güvenliği, Microsoft'un gizlilik ve GDPR düzenlemelerine yaklaşımını da içeren gelişmiş, yenilikçi güvenlik ve gizlilik koruması sağlayacak şekilde yeniden [tasarlandı.](https://privacy.microsoft.com/) [](/hololens/security-architecture)

 >[!NOTE]
> Bu belge, HoloLens (1. nesil) için geçerli değildir.

## <a name="privacy-overview"></a>Gizlilik genel bakış

HoloLens 2, uygulamaları ve çözümleri çevreleyici bir karma gerçeklik ortamında Windows Holographic çalıştıran, kendi içinde Windows bir bilgisayardır. Güvenli bir çevrimdışı cihaz olarak kullanılabilir veya kuruluş içinde yönetilen [cihaz](/mem/intune/fundamentals/windows-holographic-for-business) olarak dağıtılabilir. HoloLens 2 ve Microsoft'un verilerinizi nasıl kullandığını ve korumalarını anlamak için aşağıdaki bağlantılara bakın:

1. [Microsoft Gizlilik Bildirimi - HoloLens](https://privacy.microsoft.com/privacystatement) – sol gezinti **menüsündeki Enterprise** ve geliştirici bölümünü genişletin ve Enterprise yazılım **ve gereçlerini seçin.** HoloLens **bölümüne** gidin.
2. [Windows 10 ve çevrimiçi hizmetler](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & Gizlilik Uyumluluğu Kılavuzu](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune’da gizlilik ve kişisel veriler](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Ağ Güvenliği
Aşağıdaki HoloLens 2 [Yaygın](/hololens/common-scenarios)Dağıtım Senaryosu'nun ardından, verileriniz [Azure'ın](/azure/compliance/) birinci sınıf uyumluluğu ve yasal/mevzuat standartları tümleştirmesi ile korunacaktır. Azure AD ve Dynamics 365 Remote Assist'i yeni başladıysanız, GDPR için Azure ve [Dynamics 365](/compliance/regulatory/gdpr-arc-azure-dynamics)sorumluluk hazırlığı denetim listesine bakın.

Ayrıca, Windows Defender Güvenlik Duvarı, cihaz bağlantısının güvenliğini sağlamak için kritik işlevler sunar. Güvenlik HoloLens 2 ile güvenlik duvarı her zaman etkinleştirilir ve bunu program aracılığıyla veya kullanıcı arabirimi aracılığıyla devre dışı bırakmanın hiçbir yolu yoktur. HoloLens [2, Intune](/mem/intune/protect/device-compliance-get-started)kullanılarak yönetilen bir cihaz olarak dağıtıldığında, Mobile Threat Defense çözümü olarak Microsoft Intune uç nokta tümleştirmesi [ile daha fazla](/mem/intune/protect/advanced-threat-protection) uyumluluk işlevi kullanılabilir.

HoloLens 2 güvenlik ve mimarisi hakkında [daha fazla bilgi.](/hololens/security-architecture)

## <a name="os-security"></a>Işletim Sistemi Güvenliği
Güncelleştirmeler otomatik olarak yapılır (varsayılan olarak), HoloLens 2'niz her zaman Windows Holographic'in ve yüklü uygulamaların son sürümüyle günceldir. Işletim sistemimizin güvenli bir şekilde nasıl tasarlanma hakkında daha fazla bilgi için aşağıdakilere bakın:

1. [Durum ayrımı ve yalıtım](/hololens/security-state-separation-isolation)
1. [Yönetici olmayan işletim sistemi](/hololens/security-adminless-os)
1. [Parola kullanımını sınırlama](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fiziksel Güvenlik
HoloLens 2, BitLocker şifrelemesi ile korunan flash [belleğe sahip.](/hololens/security-encryption-data-protection) Cihazınız ve yerel verileri, Gelişmiş Kurtarma Yardımcısı kullanılarak çevrimdışı olarak gönderilip veya yönetilen bir cihaz olarak dağıtılmışsa MDM üzerinden uzaktan silinebiliyor. [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab)

## <a name="data-protection"></a>Veri Koruma
Windows güncelleştirmeler otomatik olarak (varsayılan olarak) çalışır ve [Azure tümleştirmesi](/hololens/security-encryption-data-protection#Azure-integration) kendisiyle bulut arasında seyahat eden verileri korur.

[Dynamics 365 Remote Assist,](/hololens/hololens2-deployment-guide) HoloLens 2'yi dış istemcilere dağıtırken hassas şirket verilerinizin ve kaynaklarınızı ayrı ve güvenli bir şekilde sağlar.

Tanılama verilerini Microsoft ile paylaşmak MDM tarafından veya OOBE sırasında kullanıcı tarafından el ile yalıtılabilir. İki seçenek vardır: İsteğe bağlı tanılama verileri ve Gerekli tanılama verileri. Sorun giderme amacıyla özgün tanılama ayarınızı daha sonra değiştirmeniz gerekirse, yönetilen bir cihazsa **Ayarlar -> Gizlilik -> Tanılama** & Geri Bildirimi veya IT Yöneticisi (MDM) içinde kullanıcı tarafından değiştirilebilir. Tanılama, geri [bildirim ve gizlilik hakkında daha fazla bilgi için bkz. Windows 10.](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> Cihaz tanılama günlükleri, kullanıcının tipik işlemler sırasında başladığı işlemler veya uygulamalar gibi kişisel bilgileri (PII) içerir. Birden çok kullanıcı bir HoloLens cihazı paylaştığında (örneğin, kullanıcılar farklı Microsoft Azure Active Directory (Azure AD) hesapları kullanarak aynı cihazda oturum açtığında), tanılama günlükleri birden çok kullanıcı için geçerli olan PII bilgilerini içerebilir.

HoloLens [2'den tanılama verilerini toplamak](/hololens/hololens-diagnostic-logs) için çeşitli toplama yöntemleri ve veri saklama HoloLens vardır.  Microsoft'un tanılama verilerini nasıl toplayıp kullandığı hakkında daha fazla bilgi için bkz. [Microsoft Gizlilik](https://privacy.microsoft.com/privacystatement) Bildirimi - Tanılama - sol gezinti **menüsünde** Windows'yi genişletin ve Tanılama'yı **seçin.** Tanılama **bölümüne** gidin.
