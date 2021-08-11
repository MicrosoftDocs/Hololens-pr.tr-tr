---
title: HoloLens birden çok kişiyle paylaşma
description: HoloLens birden çok Azure Active Directory hesabı veya tek bir hesabı kullanan birden çok kullanıcı tarafından paylaşılacak şekilde yapılandırabilirsiniz.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663078"
---
# <a name="share-your-hololens-with-multiple-people"></a>HoloLens birden çok kişiyle paylaşma

birçok kişi ile bir HoloLens paylaşmak veya birçok kişinin bir dizi HoloLens cihazı paylaşması yaygındır.  Bu makalede, bir cihazı paylaşmak için kullanabileceğiniz farklı yollar açıklanmaktadır.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Her biri kendi hesabını kullanan birden fazla kişiyle paylaşma

**önkoşul**: HoloLens cihaz Windows 10, sürüm 1803 veya sonraki bir sürümü çalıştırmalıdır.  HoloLens (1. gen) [Windows Holographic for Business sürümüne de yükseltilmelidir](hololens-upgrade-enterprise.md).

kendi Azure Active Directory (Azure AD) hesaplarını kullandıklarında, birden çok kullanıcı kendi kullanıcı ayarlarını ve kullanıcı verilerini cihazda tutabilir.

birden çok kişinin HoloLens kendi hesaplarını kullanabilmesini sağlamak için, yapılandırmak için aşağıdaki adımları izleyin:

1. cihazın Windows 10, sürüm 1803 veya sonraki bir sürümü çalıştırdığından emin olun.
   > [!IMPORTANT]
   > HoloLens (1. gen) bir cihaz kullanıyorsanız, [cihazı Windows Holographic for Business sürümüne yükseltin](hololens1-upgrade-enterprise.md).
1. Cihazı ayarlarken, **iş veya okul** zamanı ' nı seçin ve bır Azure AD hesabı kullanarak oturum açın.
1. kurulumu tamamladıktan sonra hesap ayarlarının (**Ayarlar**  >  **hesapları**) **diğer kullanıcıları** içerdiğinden emin olun.

HoloLens kullanmak için, her kullanıcı şu adımları izler:

1. Başka bir Kullanıcı cihazı kullanıyorsa aşağıdakilerden birini yapın:
   - Bekleme moduna geçmek için güç düğmesine bir kez basın ve ardından kilit ekranına dönmek için güç düğmesine tekrar basın
   - HoloLens 2 kullanıcı, geçerli kullanıcının oturumunu kapatmak için Başlat menüsü kullanıcı kutucuğunu seçebilir.

1. Cihazda oturum açmak için Azure AD hesabı kimlik bilgilerinizi kullanın.  
    bu cihaz ilk kez kullanılıyorsa, HoloLens kendi gözlerinize [ayarlamanız](hololens-calibration.md) gerekir.

cihaz kullanıcılarının listesini görmek veya bir kullanıcıyı cihazdan kaldırmak için **Ayarlar**  >  **hesapları**  >  **diğer kullanıcılar**' a gidin.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Aynı hesabı kullanan birden fazla kişiyle paylaşma

tek bir kullanıcı hesabı kullanırken birden çok kullanıcı da HoloLens bir cihaz paylaşabilir.

**HoloLens 2**' de, yeni bir kullanıcı cihazı ilk kez baş üzerine yerleştirirken (aynı hesabı oturum açrken), cihaz yeni kullanıcıdan görüntüleme deneyimini hızlı bir şekilde ayarlama ve kişiselleştirmesini ister. Cihaz, gelecekte her kullanıcının görüntüleme deneyiminin kalitesini ve rahatlığını otomatik olarak en iyi hale getirebilmesi için ayarlama bilgilerini depolayabilirler. Kullanıcıların cihazı yeniden ayarlama gereksinimi yoktur.

**HoloLens (1. genel)** kullanıcının bir hesabı paylaşan kullanıcıların, Ayarlar uygulamada brate 'i yeniden yapması istenir.  [Ayarlama](hololens-calibration.md)hakkında daha fazla bilgi edinin.
