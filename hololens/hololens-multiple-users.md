---
title: HoloLens'inizi birden çok kişi ile paylaşma
description: HoloLens'i birden çok Azure Active Directory veya tek bir hesap kullanan birden çok kullanıcı tarafından paylaşılacak şekilde yapılandırabilirsiniz.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379068"
---
# <a name="share-your-hololens-with-multiple-people"></a>HoloLens'inizi birden çok kişi ile paylaşma

Bir HoloLens'i birçok kişi ile paylaşmak veya birçok kişinin bir Dizi HoloLens cihazı paylaşması yaygın bir durumdur.  Bu makalede, bir cihazı paylaşmanın farklı yolları açıklanmıştır.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Her biri kendi hesabını kullanarak birden çok kişi ile paylaşma

Önkoşul: HoloLens cihazı 1803 Windows 10 veya sonraki bir sürümü çalıştırmış olması gerekir.  HoloLens'in (1. nesil) sürümüne [de Windows Holographic for Business.](hololens-upgrade-enterprise.md)

Kullanıcılar kendi kullanıcı Azure Active Directory (Azure AD) hesaplarını kullanırsa, birden çok kullanıcı cihazda kendi kullanıcı ayarlarını ve kullanıcı verilerini saklayabilirsiniz.

HoloLens'iniz üzerinde birden çok kişinin kendi hesaplarını kullanabileceğini emin olmak için aşağıdaki adımları izleyin:

1. Cihazın 1803 veya Windows 10 çalıştırıla olduğundan emin olun.
   > [!IMPORTANT]
   > HoloLens (1. nesil) cihazı kullanıyorsanız, cihazı sanal [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Cihazı ayarsanız, cihazı iş veya okul **sahibim'i seçin ve** bir Azure AD hesabı kullanarak oturum açın.
1. Kurulumu tamamladikten sonra, hesap ayarlarının **(** Ayarlar Hesapları ) Diğer  >  **kullanıcılar'ın** olduğundan **emin olun.**

HoloLens'i kullanmak için her kullanıcı şu adımları izler:

1. Cihazı başka bir kullanıcı kullanıyorsa, aşağıdakilerden birini yapın:
   - Bekleme moduna dönmek için güç düğmesine bir kez basın ve ardından kilit ekranına dönmek için güç düğmesine tekrar basın
   - HoloLens 2 kullanıcıları, geçerli kullanıcının oturumlarını Başlat menüsü için kullanıcı kutucuğunu seçerek kullanıcı kutucuğunu seçerek kullanıcıdan yardım alan kullanıcılar olabilir.

1. Cihazda oturum açma için Azure AD hesabı kimlik bilgilerinizi kullanın.  
    Cihazı ilk kez kullandıysanız HoloLens'i [kendi gözünize](hololens-calibration.md) ayarlamanız gerekir.

Cihaz kullanıcılarının listesini görmek veya bir kullanıcıyı cihazdan kaldırmak için Ayarlar Hesapları **Diğer**  >  **kullanıcılar'a**  >  **gidin.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Hepsi aynı hesabı kullanarak birden çok kişi ile paylaşma

Ayrıca, tek bir kullanıcı hesabı kullanırken birden çok kullanıcı HoloLens cihazı paylaşabilir.

**HoloLens 2'de,** yeni bir kullanıcı cihazı ilk kez başına koyarken (aynı hesabın oturum açık tutularak) yeni kullanıcıdan görüntüleme deneyimini hızla ayarlamasını ve kişiselleştirmesini istenir. Cihaz, gelecekte her kullanıcının görüntüleme deneyiminin kalitesini ve rahatsını otomatik olarak iyileştirecek şekilde ayar bilgilerini depolar. Kullanıcıların cihazı yeniden ayarlaması gerek değildir.

**HoloLens'te (1. nesil)** hesap paylaşan kullanıcıların Ayarlar uygulamasında yeniden ölçeklendirme istemesi gerekir.  Ayarlama hakkında daha fazla [bilgi edinin.](hololens-calibration.md)
