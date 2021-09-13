---
title: dağıtım kılavuzu – Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-genel bakış
description: kurumsal bağlantılı bir ağ üzerinden Dynamics 365 kılavuzlarıyla HoloLens 2 cihazı kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlı, Dynamics 365 kılavuzlar, AAD, Azure AD, MDM, mobil cihaz yönetimi
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033426"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>dağıtım kılavuzu-Dynamics 365 kılavuzlarıyla kurumsal bağlı HoloLens 2-genel bakış

bu kılavuz, bt uzmanlarının Dynamics 365 kılavuzlarıyla (kılavuzlar) Microsoft HoloLens 2 cihaz planlaması ve dağıtmalarına yardımcı olur. Bu kılavuz, pilot ve üretim dağıtımları için harika ve [B: kuruluşunuzun ağ Kılavuzu Içinde dağıtma senaryosuna](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) benzer. kavram kanıtlarınızı test ettikten sonra, HoloLens kuruluşunuza tümleştirmeyle ileri doğru gitmek için bu kılavuzu kullanın.

Bu kılavuzda, cihazlarınızın mevcut cihaz yönetimine nasıl kaydedileceğini, gereken lisansları nasıl uygulayacağını ve son kullanıcılarınızın bir Dynamics 365 Kılavuzu çalıştıracağını ve cihaz kurulduktan sonra özel iş kolu uygulamaları kullanmasını nasıl doğrulayacağız. 

## <a name="prerequisites"></a>Önkoşullar

Aşağıdaki altyapı zaten yerinde olmalıdır:
- Wi-Fi
    - İç kaynaklara erişimi olan dahili kurumsal ağ ve internet veya bulut hizmetlerine sınırlı erişim
    - Cihaz tabanlı sertifika kimlik doğrulaması.
- Azure Active Directory (azure ad) MDM otomatik kaydıyla birleştir ([azure ad P1 aboneliği](/azure/active-directory/fundamentals/active-directory-whatis) gerekir)
- MDM (Intune) yönetiliyor
    - Bir veya daha fazla uygulama MDM aracılığıyla dağıtılır.
- Ağ 
    - Sertifikalar (SCEP veya PKCS)
    - Ara sunucu yapılandırması
- Kullanıcılar kendi şirket hesabıyla oturum açtığında (Azure AD)
    - Cihaz başına tek veya birden çok Kullanıcı desteklenir.
- Belirli kullanım örneklerine göre uygulanan cihaz kilitleme yapılandırmalarının farklı düzeyleri, tam açık tek uygulama bilgi noktası ile uygulanır.

## <a name="guides-licensing-and-requirements"></a>[Kılavuzlar lisanslama ve gereksinimler](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD hesabı
- Dynamics 365 kılavuzlar uygulamalar PC ve HoloLens
- Dynamics 365 kılavuzlar aboneliği
    - Microsoft Dataverse (dahil)
    - Power Apps (dahil)
- Power BI Desktop
- Ağ bağlantısı

[![Corp bağlı ağ diyagramı, 1. aşama. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp bağlı ağ diyagramı, Aşama 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Bu kılavuzda şunları yapmanız gerekir:
### <a name="prepare"></a>Hazırlama
> [!div class="checklist"]
>- [HoloLens 2 cihazları için altyapı temelleri hakkında bilgi edinin.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD hakkında daha fazla bilgi edinin ve yoksa bir tane ayarlayın.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.](hololens2-corp-connected-prepare.md#identity-management)
>- [MDM hakkında daha fazla bilgi edinin ve henüz bir hazırlayın yoksa Intune ile ayarlayın.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Sertifika tabanlı Wi-Fi hakkında bilgi edinin.](hololens2-corp-connected-prepare.md#certificates)
>- [Proxy hakkında bilgi edinin.](hololens2-corp-connected-prepare.md#proxy)
>- [Iş kolu uygulamalarını nasıl kullanabileceğinizi anlayın.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Kuruluşunuzun kılavuzlarını nasıl kullanabileceğiniz hakkında daha fazla bilgi edinin.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Yapılandırma
> [!div class="checklist"]
>- [Kullanıcı ve grup oluşturma.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Otomatik kayıt ayarlama.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Wi-Fi sertifikaları ve profilleri kurumsal Wi-Fi bağlantı için ayarlama.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload ve iş kolu (LOB) uygulama paketleri atayın.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 kılavuzlarını ayarlayın.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Bilgi noktası modunu yapılandırma (isteğe bağlı).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC yapılandırma (isteğe bağlı).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Dağıtma
> [!div class="checklist"]
>-  [Kaydı cihaz ve MDM aracılığıyla doğrulayın.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Wi-Fi sertifikalarını doğrulayın.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB uygulaması yüklemesini doğrulayın.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Yazma ve çalıştırma aracılığıyla kılavuzların doğrulanması.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Bakım
> [!div class="checklist"]
>- [güncelleştirme HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Kılavuzlarını güncelleştirme (Mağaza uygulamaları).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB uygulamalarını güncelleştirme.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Geliştirme planı.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Destek planı oluşturma.](hololens2-corp-connected-maintain.md#support-plan)
>- [Cihaz yönetimi seçenekleri.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlı dağıtım-hazırlama](hololens2-corp-connected-prepare.md)
