---
title: HoloLens 2 gizlilik ve veri koruması
description: Gizlilik belgeleri
keywords: HoloLens, GDPR, gizlilik, pıı, veri koruma
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033292"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 gizlilik ve veri koruması

GDPR 'ın temel öğelerinden biri, ' tasarıma göre veri koruması ' ' dır. bu kavram, genellikle taşınabilirlik, sınırsız internet bağlantısı ve açık iletişim kanalları nedeniyle HoloLens 2 gibi mobil cihazlara uygulanır. HoloLens 2 ' nin [güvenliği](/hololens/security-architecture) , gelişmiş, yenilikçi güvenlik ve gizlilik koruması, hem Microsoft 'un [gizlilik ve GDPR düzenlemelerine](https://privacy.microsoft.com/)yönelik yaklaşımını dahil olmak üzere uçtan uca olacak şekilde yeniden tasarlanmıştır.

 >[!NOTE]
> bu belge HoloLens (1. gen) için uygulanmıyor.

## <a name="privacy-overview"></a>Gizliliğe Genel Bakış

HoloLens 2, bir modern karma gerçeklik ortamında uygulamalar ve çözümler çalıştıran Windows Holographic çalıştıran, kendi içinde bulunan bir Windows bilgisayardır. Bu, güvenli bir çevrimdışı cihaz olarak kullanılabilir veya kuruluşunuzda [yönetilen bir cihaz](/mem/intune/fundamentals/windows-holographic-for-business) olarak dağıtılabilir. HoloLens 2 ve Microsoft 'un verilerinizi nasıl kullandığını ve nasıl koruduğunu anlamak için aşağıdaki bağlantılara bakın:

1. [Microsoft gizlilik bildirimi-HoloLens](https://privacy.microsoft.com/privacystatement) – sol gezinti menüsündeki **Enterprise ve geliştirici** bölümünü genişletin ve **Enterprise ve geliştirici yazılımı ve gereçleri**' ni seçin. **HoloLens** bölümüne gidin.
2. [Windows 10 ve çevrimiçi hizmetler](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & gizlilik uyumluluğu kılavuzu](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune’da gizlilik ve kişisel veriler](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Ağ Güvenliği
HoloLens 2 [ortak dağıtım senaryolarından](/hololens/common-scenarios)sonra verileriniz, [Azure 'un birinci sınıf uyumluluğuyla](/azure/compliance/) ve yasal/yasal standartlar tümleştirmesiyle korunacaktır. Azure AD ve Dynamics 365 Uzaktan Yardım ' ı yeni kullanıyorsanız, [GDPR Için Azure ve dynamics 365 sorumluluk hazırlığı denetim listesine](/compliance/regulatory/gdpr-arc-azure-dynamics)başvurun.

ayrıca, Windows Defender güvenlik duvarı cihaz bağlantısının güvenliğini sağlamak için kritik işlevler sunar. HoloLens 2 ile güvenlik duvarı her zaman etkindir ve bunu programlı olarak veya kullanıcı arabiriminden devre dışı bırakma yöntemi yoktur. HoloLens 2, [ıntune](/mem/intune/protect/device-compliance-get-started)kullanılarak yönetilen bir cihaz olarak dağıtıldığında, mobil tehdit savunması çözümü olarak [Microsoft Intune olan uç nokta](/mem/intune/protect/advanced-threat-protection) tümleştirmesiyle birlikte daha fazla uyumluluk işlevselliği kullanılabilir.

HoloLens 2 [güvenliği ve mimarisi](/hololens/security-architecture)hakkında daha fazla bilgi edinin.

## <a name="os-security"></a>İşletim sistemi güvenliği
güncelleştirmeler otomatik olarak yapılır (varsayılan olarak) HoloLens 2 ' nin en son sürümü olan Windows Holographic ve yüklü tüm uygulamalar ile her zaman güncel olması önerilir. IŞLETIM sistemimizin güvenle nasıl tasarlandığına ilişkin daha fazla bilgi edinmek için aşağıdakilere bakın:

1. [Durum ayrımı ve yalıtımı](/hololens/security-state-separation-isolation)
1. [Yönetici-daha az işletim sistemi](/hololens/security-adminless-os)
1. [Parola kullanımını sınırlandırma](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fiziksel Güvenlik
HoloLens 2 ' nin [BitLocker şifrelemesi](/hololens/security-encryption-data-protection)tarafından korunan flash belleği vardır. Cihazınız ve yerel verileri, [Gelişmiş kurtarma Yardımcısı](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) kullanılarak çevrimdışı hale gelir veya yönetilen bir cihaz olarak dağıtılmışsa MDM aracılığıyla uzaktan temizlenir.

## <a name="data-protection"></a>Veri Koruma
Windows güncelleştirmeleri otomatik olarak çalıştırılır (varsayılan olarak) ve [Azure tümleştirmesi](/hololens/security-encryption-data-protection#Azure-integration) , verileri kendisi ile bulut arasında seyahat eden şekilde korur.

HoloLens 2 ' yi dış istemcilere dağıttığınızda, [Dynamics 365 uzaktan yardım](/hololens/hololens2-deployment-guide) , önemli şirket verileri ve kaynaklarınızın hem ayrı hem de güvenli olmasını sağlar.

Tanılama verilerinin Microsoft ile paylaşılması, MDM veya OOBE sırasında Kullanıcı tarafından el ile yapılandırılabilir. İki seçenek vardır: Isteğe bağlı Tanılama verileri ve gerekli Tanılama verileri. özgün tanılama ayarınız, sorun giderme amacıyla daha sonra değiştiriliyorsa, **Ayarlar > gizlilik-> tanılama & geri bildirimi** veya bt yöneticisi (MDM) tarafından yönetilen bir cihaz ise kullanıcı tarafından değiştirilebilir. [Windows 10 tanılama, geri bildirim ve gizlilik](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)hakkında daha fazla bilgi için bkz..

> [!Important]
> Cihaz tanılama günlükleri, tipik işlemler sırasında kullanıcının hangi işlemler veya uygulamalar tarafından başlatıldığı hakkında bilgi gibi kişisel olarak tanımlanabilen bilgileri (PII) içerir. birden çok kullanıcı bir HoloLens cihazını paylaşıyorsa (örneğin, kullanıcılar farklı Microsoft Azure Active Directory (Azure AD) hesapları kullanarak aynı cihazda oturum açtığında) tanılama günlükleri, birden fazla kullanıcı için geçerli olan pıı bilgilerini içerebilir.

HoloLens 2 ' den tanılama verilerini toplamak için [birkaç koleksiyon yöntemi ve veri saklama ilkesi](/hololens/hololens-diagnostic-logs) vardır.  microsoft 'un tanılama verilerini nasıl toplayıp kullandığı hakkında daha fazla bilgi için bkz. [microsoft gizlilik bildirimi-tanılama](https://privacy.microsoft.com/privacystatement) -sol gezinti menüsünde **Windows** ' i genişletin ve **tanılama**' yı seçin. **Tanılama** bölümüne gidin.
