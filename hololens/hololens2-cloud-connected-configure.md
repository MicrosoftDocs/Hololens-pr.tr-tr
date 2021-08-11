---
title: dağıtım kılavuzu – buluta bağlı HoloLens 2 dağıtım, uzaktan yardım-yapılandırma ile uygun ölçekte
description: uzaktan yardım ile bir buluta bağlı ağ üzerinden HoloLens cihazları kaydetmek üzere yapılandırmaların nasıl ayarlanacağını öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, uzaktan yardım, AAD, Azure AD, MDM, mobil cihaz yönetimi
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
ms.openlocfilehash: 8e6999157c6f5a396812df26f748c771581b61d63709918abb2ae45063810ef8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660551"
---
# <a name="configure---cloud-connected-guide"></a>Yapılandırma-buluta bağlı Kılavuzu

Kılavuzun bu bölümünde, kiracınız için otomatik kaydı nasıl ayarlayacağınızı ve hem Intune hem de uzaktan yardım için lisansların nasıl uygulanacağını&#39;.

## <a name="azure-users-and-groups"></a>Azure kullanıcıları ve grupları

Bu uzantıya göre Azure ve Intune, yapılandırmaların ve lisansların atanmasını sağlamaya yardımcı olmak için kullanıcıları ve grupları kullanır. Bu dağıtım akışını doğrulamak ve bir kullanıcıdan başka bir kullanıcıya Uzaktan Yardım çağrısı yapabilmek için, iki kullanıcı hesabına ihtiyacınız vardır&#39;.

Lisans atama amacıyla tek bir Kullanıcı grubu yapabiliriz. Her iki kullanıcıyı aynı gruba birleştirebiliriz ve bu gruba Intune ve uzak yardım için bir lisans uygulayabiliriz.

&#39;t ' den daha önce kullanabileceğiniz bir kullanıcı grubunda iki Azure AD hesabına erişiminiz varsa; hızlı başlangıç kılavuzlarından bazıları şunlardır:

- [Kullanıcı oluşturma](/mem/intune/fundamentals/quickstart-create-user)
- [Grup oluşturma](/mem/intune/fundamentals/quickstart-create-group)
- [Gruba kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – grup oluşturmak için oluşturulan kullanıcılar ekleme
- [Azure AD 'yi bir Kullanıcı grubunun cihazlara katılmasına izin verecek şekilde yapılandırma](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -Yeni Kullanıcı grubunun CIHAZLARı Azure AD 'ye kaydetme izni olduğundan emin olun

## <a name="auto-enrollment-on-hololens-2"></a>HoloLens 2 ' de otomatik kayıt

sorunsuz ve sorunsuz bir deneyim sunmak için, HoloLens 2 cihazları için Azure Active Directory katılması (asıfatı) ve ıntune 'a otomatik kayıt ayarlamak için gidilecek yol. Bu, kullanıcıların, OOBE sırasında kuruluş oturum açma kimlik bilgilerini girmesini ve Azure AD 'ye otomatik olarak kaydolmasını ve cihazı MDM 'ye kaydetmelerini sağlar.

[Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak hizmetler ' i seçip Premium deneme sürümü ' nü seçene kadar birkaç sayfaya gidebilirsiniz. otomatik kayıt P1 'nın yeterli olduğunu Azure Active Directory Premium 1 ve 2 olduğunu fark edebilirsiniz. Intune 'U seçip otomatik kayıt için Kullanıcı kapsamını seçebilir ve daha önce oluşturulmuş olan grubu seçebilirsiniz.

Tam ayrıntılar ve adımlar için, [Intune için otomatik kaydı etkinleştirme](/mem/intune/enrollment/quickstart-setup-auto-enrollment)kılavuzunu okuyun.

## <a name="application-licenses"></a>Uygulama lisansları

Uygulama lisansı, kullanıcının satın alınan uygulamaları yüklemesine veya ücretsiz bir deneme sürümünden bir uygulamanın tam sürümüne yükseltmesine olanak tanır. Uygulama lisansları, kullanıcılar, Kullanıcı grupları ya da cihaz gruplarına uygulanabilir. Kuruluşunuzdaki kullanıcıların uzaktan yardım 'ı kullanabilmesi için uzaktan yardım lisanslarının&#39;gerekir. Bu kılavuzun amacı doğrultusunda, yukarıda oluşturduğunuz kullanıcı grubuna [Azure kullanıcıları ve grupları](hololens2-cloud-connected-configure.md#azure-users-and-groups)'Nda uzaktan yardım lisansları atayacağız.

Kullanıcının bir cihazdan uzaktan yardım araması yapıp yapmayacak veya Microsoft Teams bir uzak ortak çalışan olması durumunda, lisansların gereksinimleri farklı olabilir. varsayılan olarak, uzaktan yardım ve Teams onay kutuları her ikisi de işaretlenir. Bu kılavuzun amaçları doğrultusunda, varsayılan kutuları Denetlenmeye ayrıldık.

1. [Rol başına farklı lisanslama ve ürün gereksinimleri](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)hakkında daha fazla bilgi edinin. Birkaç farklı türde uzak yardım lisansı bulunur, bu nedenle gereksinimlerinize göre doğru olanları almanızı unutmayın.
2. [Lisansı edinmeniz](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)&#39;ll gerekir.
3. [Lisanslarınızı gruba uygulayın](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) .

## <a name="next-step"></a>Sonraki adım

> [!div class="nextstepaction"]
> [Buluta bağlı dağıtım-dağıt](hololens2-cloud-connected-deploy.md)