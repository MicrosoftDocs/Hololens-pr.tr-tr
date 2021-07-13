---
title: Dağıtım Kılavuzu – Remote Assist HoloLens büyük ölçekte buluta bağlı ve 2 dağıtım - Yapılandırma
description: Remote Assist ile bulut bağlantılı bir ağ üzerinden HoloLens cihazları büyük ölçekte kaydetmek için yapılandırmaları ayarlamayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635152"
---
# <a name="configure---cloud-connected-guide"></a>Yapılandırma - Buluta bağlı Kılavuz

Kılavuzun bu bölümünde,&#39;için Otomatik Kaydı ayarlama ve hem Intune hem de Remote Assist için lisansları uygulama adımlarını aktarabilirsiniz.

## <a name="azure-users-and-groups"></a>Azure Kullanıcıları ve Grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaları ve lisansları atamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamanın ve bir kullanıcıdan diğerine Remote Assist çağrısı yapmak için iki kullanıcı&#39;gerekir.

Lisans atama amacıyla tek bir kullanıcı grubu kullanabiliriz. Her iki kullanıcıyı da aynı gruba katarak Intune ve Remote Assist için bir lisans uygulayabiliriz.

Henüz&#39;bir kullanıcı grubunda iki Azure AD hesabına erişiminiz yoksa; hızlı başlangıç kılavuzları şu şekildedir:

- [Kullanıcı oluşturma](/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Grup oluşturmak için oluşturulan kullanıcıları ekleme
- [Azure AD'yi Bir Kullanıcı Grubunun cihazlara katılmasına izin](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) verecek şekilde yapılandırma – Yeni kullanıcı grubunun cihazları Azure AD'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2'de Otomatik Kayıt

Sorunsuz ve sorunsuz bir deneyim elde etmek için, Azure Active Directory 2 cihaz için Intune'a Azure Active Directory Join (AADJ) ve HoloLens Otomatik Kayıt'ı ayarlama yoludur. Bu, kullanıcıların OOBE sırasında kuruluş oturum açma kimlik bilgilerini girişine ve Azure AD'ye otomatik olarak kaydolmasına ve cihazı MDM'ye kaydetmesine olanak sağlar.

bu [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak Hizmetler'i seçerek deneme sürümü için Bir Premium seçene kadar Premium gezinebilirsiniz. Otomatik Kayıt P1 için Azure Active Directory Premium 1 ve 2'nin yeterli olduğunu fark olabilir. Intune'ı seçerek otomatik kayıt için kullanıcı kapsamını ve daha önce oluşturulmuş olan grubu seçerek.

Tüm ayrıntılar ve adımlar için [Intune için otomatik kaydı etkinleştirme kılavuzunu okuyun.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Uygulama Lisansları

Uygulama lisansı, kullanıcıların şirket tarafından satın alınan Uygulamaları yüklemelerini veya ücretsiz deneme sürümünden uygulamanın tam sürümüne yükseltmelerini sağlar. Uygulama lisansları kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir. Uzaktan&#39;kullanmak için, kuruluşta kullanıcılar için Remote Assist lisansları gerekir. Bu kılavuzun amacı doğrultusunda, yukarıda Azure Kullanıcıları ve Grupları'nda oluşturduğumuz kullanıcı grubuna Remote Assist [lisansları atayacak.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Lisans gereksinimleri, kullanıcının bir cihazdan Remote Assist çağrısı mı yaptığına veya cihazın uzaktan ortak Microsoft Teams. Varsayılan olarak Remote Assist ve Teams onay kutularının her ikisi de işaretlenir. Bu kılavuzun amaçları doğrultusunda, varsayılan kutuları işaretli bırakmanızı öneririz.

1. Rol başına farklı Lisanslama [ve ürün gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Birkaç farklı Türde Remote Assist lisansı olduğundan, ihtiyaçlarınıza uygun lisansları edinebilirsiniz.
2. &#39;lisansını [edinmeniz gerekir.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Lisanslarınızı gruba](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) uygulama.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Dağıtma](hololens2-cloud-connected-deploy.md)