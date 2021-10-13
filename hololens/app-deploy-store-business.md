---
title: İş İçin Microsoft Store
description: karma gerçeklik uygulamalarınızı işletmenize yayımlamak için İş İçin Microsoft Store ile nasıl çalışacağınızı öğrenin.
keywords: İş İçin Microsoft Store, msfb, uygulama dağıtımı, mağaza
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924323"
---
# <a name="microsoft-store-for-business"></a>İş İçin Microsoft Store

[İş İçin Microsoft Store](/microsoft-store/microsoft-store-for-business-overview) , birincil olarak iş veya kuruluşların bt karar mekanizmalarına ve yöneticilerine, toplu ve ücretli uygulamaları, birim içindeki cihazlara Windows 10 için seçin. 

Microsoft Store uygulamalarını ve özel iş kolu uygulamalarını tek bir envanterde yönetebilir ve gerektiğinde lisansları atayabilir ve yeniden kullanabilirsiniz. kuruluşunuz için en iyi dağıtım yöntemini de seçebilirsiniz: doğrudan kişilere ve takımlara uygulama atama, Microsoft Store ' deki özel sayfalara uygulama yayımlama veya daha fazla seçenek için yönetim çözümlerine bağlanma.

İş İçin Microsoft Store son kullanıcı tarafından kullanıldığında Microsoft Store uygulamasını başlatacaktır. Kullanıcı başlatıldıktan sonra, kuruluş adlarıyla ilgili sekmeyi seçebilecektir, daha sonra kendilerine veya bu cihaz için kullanılabilir uygulamalar sunulur.

> [!Note]
> İş İçin Microsoft Store uygulamaları cihazlara otomatik olarak indirmez (gönderim). ancak, İş İçin Microsoft Store uygulamalar, uygulamaları hedeflemek ve cihazlara eşitlemek için cihaz yönetimi (MDM) sunucusuyla ilişkilendirilebilir.

İş İçin Microsoft Store kullanma hakkında daha fazla bilgi edinmek için aşağıdaki sayfaları ziyaret edin:

* [Uygulamaları yüklemek için kullanılan izin düzeyleri](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Iş için deponuza uygulama ekleme](/mem/intune/apps/store-apps-windows)
* [Çalışan gruplarına uygulama atama](/mem/intune/apps/windows-store-for-business)

İş İçin Microsoft Store ilişkilendirmek için [İş İçin Microsoft Store ıntune ile ilişkilendirme](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)makalesini ziyaret edin.

> [!Tip]
> gelişmiş kurtarma yardımcısı (ARC) ve Windows yapılandırma tasarımcısı (wcd) gibi uygulamalar kullanırken [çevrimdışı uygulamalar dağıtma](/microsoft-store/distribute-offline-apps) hakkında daha fazla bilgi edinin.

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Microsoft Store için yalnızca özel Mağaza uygulamaları kullanın

- [Windows Holographic, sürüm 21h2 '](hololens-release-notes.md#windows-holographic-version-21h2)de kullanıma sunulmuştur.

RequirePrivateStoreOnly ilkesi HoloLens için etkinleştirildi. bu ilke, Microsoft Store uygulamasının yalnızca kuruluşunuz için yapılandırılmış özel mağazayı gösterecek şekilde yapılandırılmasını sağlar. Erişimi yalnızca kullanılabilir hale getirdiğiniz uygulamalarla sınırlama.

[ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) hakkında daha fazla bilgi edinin

## <a name="smart-retry-for-app-updates"></a>Uygulama güncelleştirmeleri için akıllı yeniden deneme

- [Windows Holographic, sürüm 21h2 '](hololens-release-notes.md#windows-holographic-version-21h2)de kullanıma sunulmuştur.

HoloLens için etkin olan, bt yöneticilerinin güncelleştirme uygulanmasına izin verirken güncelleştirilmesi başarısız olan uygulamaları yeniden başlatmak için yinelenen veya bir zaman tarihi ayarlamasına izin veren yeni bir ilkedir. Bunlar, zamanlanan saat veya oturum açma gibi birkaç farklı tetikleyiciye göre ayarlanabilir. Bu ilkeyi kullanma hakkında daha fazla bilgi edinmek için lütfen [ApplicationManagement/Scheduleforcerestartforupdatebaşarısızlıklarını](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)görüntüleyin.