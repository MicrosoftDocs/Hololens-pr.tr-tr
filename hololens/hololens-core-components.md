---
title: ticari bir ortamda HoloLens 2 dağıtımı planlama
description: altyapı, azure active directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens dağıtmak ve yönetmek için temel gereksinimler hakkında bilgi edinin.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639089"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>ticari bir ortamda HoloLens 2 dağıtımı planlama

## <a name="overview"></a>Genel Bakış

> [!NOTE]
> bu genel bakış, bt uzmanlarının bir kuruluşta Microsoft HoloLens 2 cihaz dağıtma ve yönetme ile ilgili hususları anlamalarına yardımcı olmaya yöneliktir. cihaz son kullanıcıları için bkz. [HoloLens 2](hololens2-setup.md) ' yi kullanmaya başlamak için kullanıma hazırlanıyor.

HoloLens 2, kuruluşlar için güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan Windows 10 Holographic çalışır. Windows 10 Holographic, şirketlerinin cihazları, verileri ve uygulamaları üzerinde denetim sağlamak için uçtan uca cihaz yaşam döngüsü yönetimini destekler. HoloLens 2, standart yaşam döngüsü uygulamalarına, cihaz kaydı, yapılandırma ve uygulama yönetiminden kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak bakım ve kullanımdan kaldırma için kolayca eklenebilir.

aşağıdaki adımlar ve video, kuruluşunuzda HoloLens 2 benimseme sürecinde size rehberlik etmenize yardımcı olabilir.

| &nbsp; | &nbsp; |
|--|--|
| ![1. Adım](images/1green.png)| <br/> **[ortak dağıtım senaryoları](hololens-requirements.md)**: dağıtım senaryolarını anlayın ve HoloLens 2 cihaz dağıtmak için gereken çekirdek bileşenleri keşfedebilirsiniz. |
| ![2. Adım](images/2green.png)| <br/> **[hazırlama](#prepare)**: HoloLens 2 için gereken altyapı temelleri hakkında bilgi sahibi olun. |
| ![3. Adım](images/3green.png) | <br/> **[Yapılandırma](#configure)**: bulut tabanlı bir dağıtım için gerekli bileşenlerinizi nasıl yapılandıracağınızı öğrenin. |
| ![4. Adım](images/4green.png) | <br/> **[Dağıtım](#deploy)**: cihazlarınızı dağıtmayı ve uygulamalarınızı güvenli ve etkili bir şekilde dağıtmayı öğrenin. |
| ![5. Adım](images/5green.png) | <br/> **[bakım](#maintain)**: HoloLens 2 cihazlarınızın durumunu doğru bir şekilde korumak ve kurumsal ilkeyle uyumluluğu sağlamak için gerekenleri öğrenin. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Hazırlama

HoloLens 2 özelliklerini tam olarak desteklemek için gereken temel altyapı hizmetleri hakkında bilgi edinin.

| Bileşen | Açıklama |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2 için kimlik ve erişim yönetimi sağlar  |
| [Mobil Cihaz Yönetimi](hololens-mdm-configure.md)| kiracınıza bağlı HoloLens 2 cihazı yönetir  |
| [Wi-Fi ağı](hololens-commercial-infrastructure.md)| Wi-Fi kullanılabilir ve cihazlar Internet 'e bağlanabilir  |

## <a name="configure"></a>Yapılandırma

kuruluşunuzun Azure AD kiracısına ve MDM 'ye HoloLens 2 ' ye kaydolma ve yapılandırma için düşük dokunma çözümleri olarak ıntune ve Autopilot kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [Otomatik kayıt](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | İlk oturum açma işleminden sonra cihazlar Azure AD 'ye otomatik olarak kaydolduktan sonra MDM 'ye kaydolur  |
| [Uygulama lisansları](hololens2-cloud-connected-configure.md#application-licenses)| Kullanıcılara, Kullanıcı gruplarına veya cihaz gruplarına uygulanabilir  |
| [Azure kullanıcıları ve grupları](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2 için yapılandırmaların ve lisansların atanmasını sağlar  |

## <a name="deploy"></a>Dağıtma

HoloLens 2 cihazlarınızı dağıtın ve yapılandırmalarını doğrulayın. 

| Bileşen | Açıklama |
|-----------|------------|
| [Kayıt doğrulama](hololens2-corp-connected-deploy.md#enrollment-validation) | cihazın azure AD 'ye Ayarlar veya azure portalından katıldığını doğrulama |
| [Sertifika doğrulama](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ayarları denetleyin ve doğru şekilde dağıtıldığını doğrulayın |
| [Uygulama yüklemelerini doğrula](hololens2-corp-connected-deploy.md#validate-lob-app-install) | uygulamanın mevcut olduğunu ve HoloLens 2 ' de çalıştığını doğrulayın |

## <a name="maintain"></a>Bakım

HoloLens 2 ve uygulamalarının güncel kalmasını sağlamak için MDM sisteminizle birlikte iş için Windows Update veya Microsoft Store kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [güncelleştirme HoloLens 2](hololens-updates.md) | iş için Windows güncelleştirmeleri sayesinde güncelleştirmeleri gerektiği şekilde yapılandırın |
| [Uygulamaları güncelleştirme](app-deploy-overview.md) | MDM sisteminiz veya Microsoft Store ile yapılandırma
