---
title: Ticari bir ortamda HoloLens 2 dağıtımını planlama
description: Altyapı, Azure Active Directory ve mobil cihaz yönetimi dahil olmak üzere kurumsal ortamlarda HoloLens'i dağıtmak ve yönetmek için temel ihtiyaçları öğrenin.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961477"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Ticari bir ortamda HoloLens 2 dağıtımını planlama

## <a name="overview"></a>Genel Bakış
> [!NOTE]
> Bu genel bakış, BT uzmanlarının kuruluş içindeki 2 cihazı dağıtmaya ve yönetmeye Microsoft HoloLens dikkat edilmesi gerekenleri anlamalarında yardımcı olmak için tasarlanmıştır. Cihaz son kullanıcıları için [bkz. Çalışmaya başlamanın](hololens2-setup.md) temelleri.

HoloLens 2, Windows 10 Holographic güçlü, esnek, yerleşik mobil cihaz ve uygulama yönetimi teknolojileri sağlayan sanal ağlarda çalışır. Windows 10 Holographic, şirketlere cihazları, verileri ve uygulamaları üzerinde denetim vermek için uz-2 4 cihaz yaşam döngüsü yönetimini destekler. HoloLens 2, kapsamlı bir mobil cihaz yönetimi çözümü kullanılarak cihaz kaydı, yapılandırma ve uygulama yönetiminden bakım ve kullanımdan sonra standart yaşam döngüsü uygulamalarına kolayca dahil edilebilir.

Aşağıdaki adımlar, HoloLens 2'nin kuruluş içinde benimsenmesi sürecinde size yol yardımcı olabilir.

| | |
|--|--|
| ![1. Adım](images/1green.png)| <br/> **[Yaygın Dağıtım Senaryoları:](hololens-requirements.md)** Dağıtım senaryolarını anlama ve HoloLens 2 cihazlarını dağıtmak için gereken temel bileşenleri keşfetme. |
| ![2. Adım](images/2green.png)| <br/> **[Hazırlama:](#prepare)** HoloLens 2 için gereken altyapı temelleri hakkında bilgi sahibi olma. |
| ![3. Adım](images/3green.png) | <br/> **[Yapılandırma:](#configure)** Bulut tabanlı dağıtım için temel bileşenlerinizi yapılandırmayı öğrenin. |
| ![4. Adım](images/4green.png) | <br/> **[Dağıtma:](#deploy)** Cihazlarınızı dağıtmayı ve uygulamalarınızı güvenli ve verimli bir şekilde dağıtmayı keşfedin. |
| ![5. Adım](images/5green.png) | <br/> **[Bakım:](#maintain)** HoloLens 2 cihazlarınızı düzgün bir şekilde korumak ve şirket ilkesiyle uyumluluğu sağlamak için gerekenleri bulun. |

## <a name="prepare"></a>Hazırlama

Tüm HoloLens 2 özelliklerini desteklemek için gereken temel altyapı hizmetleri hakkında bilgi edinmek. 

| Bileşen | Açıklama |
|-----------|------------|
| [Azure AD](hololens-identity.md) | HoloLens 2 için kimlik ve erişim yönetimi sağlar  |
| [Mobil Cihaz Yönetimi](hololens-mdm-configure.md)| Kiracınıza bağlı HoloLens 2 cihazlarını yönetir  |
| [Wi-Fi Ağı](hololens-commercial-infrastructure.md)| Wi-Fi kullanılabilir ve cihazlar İnternet'e bağlanabilir  |

## <a name="configure"></a>Yapılandırma

HoloLens 2'nin kuruluşun Azure AD kiracısına ve MDM'sine kaydolması ve yapılandırılması için intune ve Autopilot'u düşük temaslı çözümler olarak kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [Otomatik Kayıt](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | İlk oturum açma sonrasında cihazlar otomatik olarak Azure AD'ye kaydedilir ve MDM'ye kaydedilir  |
| [Uygulama Lisansları](hololens2-cloud-connected-configure.md#application-licenses)| Kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir  |
| [Azure Kullanıcıları ve Grupları](hololens2-cloud-connected-configure.md#azure-users-and-groups) | HoloLens 2 için yapılandırma ve lisans atamaya yardımcı olur  |

## <a name="deploy"></a>Dağıtma

HoloLens 2 cihazlarınızı dağıtarak yapılandırmalarını doğrular. 

| Bileşen | Açıklama |
|-----------|------------|
| [Kayıt Doğrulama](hololens2-corp-connected-deploy.md#enrollment-validation) | Cihazda Ayarlar'dan veya Azure Portal'dan Azure AD'ye Katılmış olduğunu doğrulama |
| [Sertifika Doğrulama](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Ayarları denetleyin ve doğru dağıtıldıklarını doğrulayın |
| [Uygulama yüklemelerini doğrulama](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Uygulamanın mevcut olduğunu ve HoloLens 2'niz üzerinde çalıştığını onaylayın |

## <a name="maintain"></a>Bakım

HoloLens 2 İş İçin Windows Update ve uygulamalarınızı güncel tutmak için MDM sisteminiz veya Microsoft Store ile birlikte MDM sisteminizi kullanın.

| Bileşen | Açıklama |
|-----------|------------|
| [HoloLens 2'i güncelleştirme](hololens-updates.md) | İş için Windows Güncelleştirmeleri aracılığıyla güncelleştirmeleri gereken şekilde yapılandırma |
| [Uygulamaları güncelleştirme](app-deploy-overview.md) | MDM sisteminiz veya Microsoft Store
