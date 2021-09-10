---
title: Ticari HoloLens 2 dağıtımı planlama
description: Altyapı, Azure Active Directory ve mobil cihaz yönetimi gibi kurumsal HoloLens dağıtım ve yönetim için temel ihtiyaçlar hakkında bilgi edinin.
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
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428417"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Ticari HoloLens 2 dağıtımı planlama

## <a name="overview"></a>Genel Bakış

> [!NOTE]
> Bu genel bakış, BT uzmanlarının kuruluş içindeki 2 cihazı dağıtmaya ve yönetmeye Microsoft HoloLens dikkat edilmesi gerekenleri anlamalarında yardımcı olmak için tasarlanmıştır. Cihaz son kullanıcıları için [bkz. HoloLens 2'nizi kullanmaya](hololens2-setup.md) başlamaya hazır hale get your.

HoloLens 2, Windows 10 Holographic güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan bir uygulama üzerinde çalışır. Windows 10 Holographic, şirketlere cihazları, verileri ve uygulamaları üzerinde denetim vermek için 4-4 cihaz yaşam döngüsü yönetimini destekler. Cihaz HoloLens 2, kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak cihaz kaydı, yapılandırma ve uygulama yönetiminden bakım ve kullanımdan sonra standart yaşam döngüsü uygulamalarına kolayca dahil edilebilir.

Aşağıdaki adımlar ve video, 2. kuruluş benimseme sürecinde HoloLens yardımcı olabilir.

| &nbsp; | &nbsp; |
|--|--|
| ![Adım 1.](images/1green.png)| <br/> **[Yaygın Dağıtım Senaryoları:](hololens-requirements.md)** Dağıtım senaryolarını anlama ve 2 cihaza dağıtım için gereken HoloLens bileşenleri keşfedin. |
| ![Adım 2.](images/2green.png)| <br/> **[Hazırlama:](#prepare)** HoloLens 2 için gereken altyapı temelleri hakkında bilgi sahibi olma. |
| ![3. Adım](images/3green.png) | <br/> **[Yapılandırma:](#configure)** Bulut tabanlı dağıtım için temel bileşenlerinizi yapılandırmayı öğrenin. |
| ![4. Adım:](images/4green.png) | <br/> **[Dağıtma:](#deploy)** Cihazlarınızı dağıtmayı ve uygulamalarınızı güvenli ve verimli bir şekilde dağıtmayı keşfedin. |
| ![5. Adım.](images/5green.png) | <br/> **[Bakım:](#maintain)** HoloLens 2 cihazlarınızı düzgün bir şekilde korumak ve şirket ilkesiyle uyumluluğu sağlamak için gerekenleri bulun. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Hazırlama

2. ve 2. özelliklere sahip tüm altyapı HoloLens hakkında bilgi öğrenin.

| Bileşen | Açıklama |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2 için kimlik ve erişim yönetimi sağlar  |
| [Mobil Cihaz Yönetimi](hololens-mdm-configure.md)| Kiracınıza HoloLens 2 cihazı yönetir  |
| [Wi-Fi Ağı](hololens-commercial-infrastructure.md)| Wi-Fi kullanılabilir ve cihazlar İnternet'e bağlanabilir  |

## <a name="configure"></a>Yapılandırma

Intune ve Autopilot'u, 2. azure kiracısına ve MDM'nize kaydetmek ve yapılandırmak HoloLens çözümler olarak kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [Otomatik Kayıt](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | İlk oturum açma sonrasında cihazlar otomatik olarak Azure AD'ye kaydedilir ve MDM'ye kaydedilir  |
| [Uygulama Lisansları](hololens2-cloud-connected-configure.md#application-licenses)| Kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir  |
| [Azure Kullanıcıları ve Grupları](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2 için yapılandırmaları ve lisansları atamaya yardımcı olur  |

## <a name="deploy"></a>Dağıtma

2 HoloLens cihazlarınızı dağıtarak yapılandırmalarını doğrular. 

| Bileşen | Açıklama |
|-----------|------------|
| [Kayıt Doğrulama](hololens2-corp-connected-deploy.md#enrollment-validation) | Cihazda Azure AD'ye katılmış olduğunu Ayarlar Veya Azure Portal'dan doğrulama |
| [Sertifika Doğrulama](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ayarları denetleyin ve doğru dağıtıldıklarını doğrulayın |
| [Uygulama yüklemelerini doğrulama](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Uygulamanın mevcut olduğunu ve HoloLens 2'de çalıştığını onaylayın |

## <a name="maintain"></a>Bakım

Windows 2 ve uygulama filosunu güncel tutmak için MDM sisteminiz veya Microsoft Store İş için Güncelleştirme HoloLens kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [Güncelleştirme HoloLens 2](hololens-updates.md) | İş Için Güncelleştirmeler'i Windows güncelleştirmeleri yapılandırma |
| [Uygulamaları güncelleştirme](app-deploy-overview.md) | MDM sisteminiz veya Microsoft Store
