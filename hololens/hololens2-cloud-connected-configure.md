---
title: Dağıtım Kılavuzu – Remote Assist ile büyük ölçekte buluta bağlı HoloLens 2 dağıtımı - Yapılandırma
description: Remote Assist ile Büyük ölçekte bir Bulut Bağlantılı ağ üzerinden HoloLens cihazlarını kaydetmek için yapılandırmaları ayarlamayı öğrenin.
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379022"
---
# <a name="configure---cloud-connected-guide"></a>Yapılandırma - Buluta bağlı Kılavuz

Kılavuzun bu bölümünde,&#39;için Otomatik Kaydı ayarlama ve hem Intune hem de Remote Assist için lisansları uygulama adımlarını aktarabilirsiniz.

## <a name="azure-users-and-groups"></a>Azure Kullanıcıları ve Grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaları ve lisansları atamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamanın ve bir kullanıcıdan diğerine Remote Assist çağrısı yapmak için iki kullanıcı&#39;gerekir.

Lisans atama amacıyla tek bir kullanıcı grubu kullanabiliriz. Her iki kullanıcıyı da aynı gruba katarak Intune ve Remote Assist için bir lisans uygulayabiliriz.

Kullanabileceğiniz&#39;kullanıcı grubunda iki Azure AD hesabına erişiminiz yoksa; hızlı başlangıç kılavuzları şu şekildedir:

- [Kullanıcı oluşturma](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Grup oluşturmak için oluşturulan kullanıcıları ekleme
- [Azure AD'yi Bir Kullanıcı Grubunun cihazlara katılmasına izin](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) verecek şekilde yapılandırma – Yeni kullanıcı grubunun cihazları Azure AD'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2'de Otomatik Kayıt

Sorunsuz ve sorunsuz bir deneyim elde etmek için HoloLens 2 cihazları için Azure Active Directory Join (AADJ) ve Intune'a Otomatik Kayıt'ı ayarlama yoludur. Bu, kullanıcıların OOBE sırasında kuruluş oturum açma kimlik bilgilerini girişine ve Azure AD'ye otomatik olarak kaydolmasına ve cihazı MDM'ye kaydetmesine olanak sağlar.

Microsoft [Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak, Premium deneme sürümü al'ı seçene kadar hizmetleri seçerek birkaç sayfada gezinebilirsiniz. Otomatik Kayıt P1 için Azure Active Directory Premium 1 ve 2'nin yeterli olduğunu fark olabilir. Intune'ı seçerek otomatik kayıt için kullanıcı kapsamını ve daha önce oluşturulmuş olan grubu seçerek.

Tüm ayrıntılar ve adımlar için [Intune için otomatik kaydı etkinleştirme kılavuzunu okuyun.](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Uygulama Lisansları

Uygulama lisansı, kullanıcıların şirket tarafından satın alınan Uygulamaları yüklemelerini veya ücretsiz deneme sürümünden uygulamanın tam sürümüne yükseltmelerini sağlar. Uygulama lisansları kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir. Uzaktan&#39;kullanmak için, kuruluşta kullanıcılar için Remote Assist lisansları gerekir. Bu kılavuzun amacı doğrultusunda, Yukarıda Azure Kullanıcıları ve Grupları'nda oluşturduğumuz kullanıcı grubuna Remote Assist [lisansları atayacak.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Lisans gereksinimleri, kullanıcının bir cihazdan Remote Assist çağrısı mı yoksa Microsoft Teams'den uzak ortak çalışan mı olacaklarına bağlı olarak farklı olabilir. Varsayılan olarak Remote Assist ve Teams onay kutularının her ikisi de işaretlenir. Bu kılavuzun amaçları doğrultusunda, varsayılan kutuları işaretli bırakmanızı öneririz.

1. Rol başına farklı Lisanslama [ve ürün gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Birkaç farklı Remote Assist lisansı türü vardır, bu nedenle, ihtiyaçlarınıza uygun lisanslara sahip olun.
2. &#39;lisansını [edinmeniz gerekir.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Lisanslarınızı gruba](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) uygulama.

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım - Dağıtma](hololens2-cloud-connected-deploy.md)