---
title: Dağıtım Kılavuzu – Dynamics 365 kılavuzları HoloLens 2 kurumsal bağlantılı bağlantı - Genel Bakış
description: Bir kurumsal Bağlı ağ HoloLens Dynamics 365 Kılavuzları ile 2 cihaz kaydetmeyi öğrenin.
keywords: HoloLens, yönetim, kurumsal bağlantılı, Dynamics 365 Kılavuzları, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427432"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Dağıtım Kılavuzu - Dynamics 365 kılavuzları HoloLens 2 Kurumsal Bağlantılı Dağıtım Kılavuzu - Genel Bakış

Bu kılavuz, BT uzmanlarının Dynamics 365 Kılavuzları (Kılavuzlar) ile Microsoft HoloLens 2 cihazları planlamalarına ve kuruluşlarına dağıtmalarına yardımcı olur. Bu kılavuz hem pilotlar hem de üretim dağıtımları için harikadır ve [Senaryo B: Kuruluş](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) ağ kılavuzu içinde dağıtma ile benzerdir. Kavram kanıtınızı test ettikten sonra, bu kılavuzu kullanarak uygulamalarınızı HoloLens tümleştirmeye devam edin.

Bu kılavuzda, cihazlarınızı mevcut cihaz yönetiminize kaydetmeyi, gerektiğinde lisansları uygulamayı ve son kullanıcılarının bir Dynamics 365 Kılavuzu çalıştırabileceklerini ve cihaz ayarlandıktan sonra özel iş hattı uygulamalarını kullanabileceğini doğrulamayı kapsıyoruz. 

## <a name="prerequisites"></a>Önkoşullar

Aşağıdaki altyapı zaten yerinde olmalı:
- Wi-Fi
    - İç kaynaklara erişimi olan ve İnternet'e veya Bulut hizmetlerine sınırlı erişime sahip iç kurumsal ağ
    - Cihaz tabanlı sertifika kimlik doğrulaması.
- Azure Active Directory (Azure AD) MDM Otomatik Kaydı ile Katılma[(Azure AD P1 aboneliği](/azure/active-directory/fundamentals/active-directory-whatis) gerekir)
- MDM (Intune) Yönetilen
    - MDM aracılığıyla bir veya daha fazla uygulama dağıtılır.
- Ağ 
    - Sertifikalar (SCEP veya PKCS)
    - Ara sunucu yapılandırması
- Kullanıcılar kendi kurumsal hesaplarıyla (Azure AD) oturum açma
    - Cihaz başına tek veya birden çok kullanıcı desteği vardır.
- Tamamen Açık'tan Tek Uygulama Bilgi Noktası'ya kadar belirli kullanım örneklerine göre uygulanan çeşitli cihaz kilitleme yapılandırmaları düzeyleri.

## <a name="guides-licensing-and-requirements"></a>[Kılavuzlar Lisanslama ve Gereksinimler](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD hesabı
- Dynamics 365 Kılavuzları uygulamaları PC ve HoloLens
- Dynamics 365 Kılavuzları aboneliği
    - Microsoft Dataverse (dahil)
    - Power Apps (dahil)
- Power BI Desktop
- Ağ Bağlantısı

[![Corp bağlı ağ diyagramı, 1. aşama. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Corp bağlı ağ diyagramı, 2. aşama. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Bu kılavuzda şunların için:
### <a name="prepare"></a>Hazırlama
> [!div class="checklist"]
>- [2 cihaz için altyapı temelleri HoloLens öğrenin.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Azure AD hakkında daha fazla bilgi edinin ve yoksa bir tane ayarlayın.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Kimlik yönetimi ve Azure AD hesaplarını en iyi şekilde ayarlama hakkında bilgi edinin.](hololens2-corp-connected-prepare.md#identity-management)
>- [MDM hakkında daha fazla bilgi edinmek ve henüz hazır bir MDM'leri yoksa Intune ile ayarlamak.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Sertifika tabanlı Wi-Fi'ı tanıma.](hololens2-corp-connected-prepare.md#certificates)
>- [Ara Sunucu hakkında bilgi sahibi olmak.](hololens2-corp-connected-prepare.md#proxy)
>- [İş Dalı Uygulamalarını nasıl kullanabileceğini anlama.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Kılavuzları kuruluş için nasıl kullanabileceğiniz hakkında daha fazla bilgi edinmek için.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Yapılandırma
> [!div class="checklist"]
>- [Kullanıcı ve grup oluşturma.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Otomatik Kaydı ayarlama.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Kurumsal Bağlantı için Wi-Fi sertifikaları ve profillerini Wi-Fi ayarlama.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload İş Hattı (LOB) Uygulama paketlerini seçin ve attayabilirsiniz.](hololens2-corp-connected-configure.md#app-deployment)
>- [Dynamics 365 Kılavuzlarını ayarlama.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Bilgi Noktası Modunu yapılandırma (isteğe bağlı).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [WDAC yapılandırma (isteğe bağlı).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Dağıtma
> [!div class="checklist"]
>-  [Cihaz ve MDM aracılığıyla kaydı doğrulama.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Sertifika Wi-Fi doğrulama.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [LOB uygulaması yüklemesi doğrulama.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Yazma ve çalıştırma yoluyla Kılavuzları Doğrulama.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Bakım
> [!div class="checklist"]
>- [Güncelleştirme HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Kılavuzları (mağaza uygulamaları) güncelleştirme.](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [LOB uygulamalarını güncelleştirme.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Geliştirme planı.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Destek planı yapma.](hololens2-corp-connected-maintain.md#support-plan)
>- [Cihaz yönetimi seçenekleri.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Sonraki adım 
> [!div class="nextstepaction"]
> [Kurumsal bağlantılı dağıtım - Hazırlama](hololens2-corp-connected-prepare.md)
