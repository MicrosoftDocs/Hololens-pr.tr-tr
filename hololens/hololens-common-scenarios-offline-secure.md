---
title: 'ortak senaryolar: çevrimdışı güvenli HoloLens 2'
description: HoloLens cihazları için sağlama ile çevrimdışı bir güvenli dağıtım ve uygulama dağıtım senaryosu ayarlamayı öğrenin.
keywords: HoloLens, yönetim, çevrimdışı, çevrimdışı güvenli
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428816"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>ortak senaryolar: çevrimdışı güvenli HoloLens 2

## <a name="overview"></a>Genel Bakış

bu kılavuz, aşağıdaki kısıtlamalara sahip güvenli ortamlarda kullanılmak üzere HoloLens 2 ' ye kilitleyen örnek bir sağlama paketi uygulamaya yönelik rehberlik sağlar:

-   WiFi 'yi devre dışı bırakın.
-   BlueTooth 'U devre dışı bırakın.
-   Mikrofonları devre dışı bırakın.
-   Sağlama paketlerinin eklenmesini veya kaldırılmasını engeller.
-   Herhangi bir Kullanıcı, yukarıdaki kısıtlı bileşenlerden hiçbirini etkinleştiremez.

[![Çevrimdışı güvenli senaryo. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Hazırlama

Windows 10 BILGISAYAR kurulumu
1. [en son HoloLens 2 işletim sistemi dosyasını](https://aka.ms/hololens2download) doğrudan bir bilgisayara indirin. 
   1. Bu yapılandırma için destek, derleme 19041,1117 ve üzeri sürümlerde bulunur.
1. gelişmiş kurtarma yardımcısı (ARC) aracını [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) bilgisayarınıza indirin/yükleyin
1. en son [Windows yapılandırma tasarımcısı (wcd)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) aracını Microsoft Store bilgisayarınıza indirin/yükleyin.
1. OfflineSecureHL2_Sample klasörünü, PPKG oluşturmak için [Proje dosyalarıyla indirin](https://aka.ms/HoloLensDocs-SecureOfflineSample) .
1. Çevrimdışı [Iş kolu uygulamanızı PPKG dağıtımı için](app-deploy-provisioning-package.md)hazırlayın. 


## <a name="configure"></a>Yapılandırma

Güvenli yapılandırma sağlama paketi oluşturma

1. Bilgisayarınızda WCD aracını başlatın.
1. **Dosya-> aç proje**' yi seçin.
  1. Daha önce kaydedilen OfflineSecureHL2_Sample klasörünün konumuna gidin ve şunları seçin: OfflineSecureHL2_Sample.icdproj.xml
1. Projenin açık olması ve artık kullanılabilir özelleştirmeler listesine sahip olmanız gerekir:

   > [!div class="mx-imgBorder"]
   > ![WCD 'de açık olan yapılandırma paketinin ekran görüntüsü.](images/offline-secure-sample-wcd.png)

   Bu sağlama paketinde ayarlanan yapılandırma:
   
   |     Öğe                                                |     Ayar                       |     Açıklama                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Hesaplar/kullanıcılar                                    |     Yerel Kullanıcı adı & parolası    |     Bu çevrimdışı cihazlarda, tek bir Kullanıcı adı ve parolasının, cihazın tüm kullanıcıları tarafından ayarlanması ve paylaşılması gerekir.          |
   |     ilk deneyim/HoloLens/skipayarlaması       |     Doğru                          |     Yalnızca ilk cihaz kurulumu sırasında ayarlamayı atlar                                                                             |
   |     ilk deneyim/HoloLens/skipeğitim          |     Doğru                          |     İlk cihaz kurulumu sırasında cihaz eğitimini atlar                                                                              |
   |     ilk deneyim/HoloLens/WiFi                  |     Doğru                          |     İlk cihaz kurulumu sırasında Wi-Fi config 'i atlar                                                                                 |
   |     İlkeler/bağlantı/AllowBluetooth                |     No                            |     Bluetooth devre dışı bırakır                                                                                                             |
   |     İlkeler/deneyim/AllowCortana                    |     No                            |     Cortana devre dışı bırakır (mikrofonlar devre dışı bırakıldıktan sonra olası sorunları ortadan kaldırmak için)                                          |
   |     İlkeler/MixedReality/mikro Phonedisabled            |     Yes                           |     Mikrofonu devre dışı bırakır                                                                                                            |
   |     İlkeler/gizlilik/Litappsaccesslocation              |     Reddetme zorla                    |     Uygulamaların konum verilerine erişmeye çalışmasını engeller (konum izleme devre dışı olduğundan olası sorunları ortadan kaldırmak için)    |
   |     İlkeler/gizlilik/Litappsaccessmicrophone            |     Reddetme zorla                    |     Uygulamaların mikrofonlar 'e erişmesini engeller (mikrofonlar devre dışı bırakıldıklarından bu yana olası sorunları ortadan kaldırmak için)           |
   |     İlkeler/güvenlik/AllowAddProvisioningPackage       |     No                            |     Kullanıcıların, kilitli ilkeleri geçersiz kılmaya çalıştabilecek sağlama paketleri eklemesini önler.                         |
   |     İlkeler/güvenlik/AllowRemoveProvisioningPackage    |     No                            |     Başkalarının bu kilitli sağlama paketini kaldırmasını engeller.                                                           |
   |     İlkeler/sistem/AllowLocation                       |     No                            |     Cihazın konum verilerini izlemeye çalışmasını önler.                                                                        |
   |     İlkeler/WiFi/AllowWiFi                             |     No                            |     Wi-Fi devre dışı bırakır                                                                                                                 |

1. çalışma zamanı Ayarlar altında **hesaplar/kullanıcılar/kullanıcı adı: holo/parola**' yı seçin.

   Parolayı ve istenirse sıfırlamayı göz önünde edin.

1. Üniversalappınstall/UserContextApp dizinine gidin ve bu cihazlara dağıtabileceğiniz [lob uygulamasını yapılandırın](app-deploy-provisioning-package.md) .

   > [!div class="mx-imgBorder"]
   > ![Uygulamanızın WCD 'ye nereye ekleneceğini ekran görüntüsü.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Tamamlandıktan sonra, "dışarı aktar" düğmesini seçin ve sağlama paketiniz oluşturuluncaya kadar tüm istemleri izleyin.

   > [!div class="mx-imgBorder"]
   > ![WCD 'deki bu paketin dışa aktarma düğmesinin ekran görüntüsü.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Dağıtma

1. HL2 PC 'nizi USB kablosu aracılığıyla Windows 10 bilgisayarınıza Bağlan.
1. yay aracını başlatın ve **HoloLens 2** ' yi seçin

   ![HoloLens 2 temiz flash başlangıç ekranı.](images/ARC2.png)

1. Sonraki ekranda **el ile paket seçimi**' ni seçin.

   ![HoloLens 2 yay bilgisi ekranı.](images/arc_device_info.png)

1. Daha önce indirilen. FFU dosyasına gidin ve **Aç**' ı seçin.
1. Uyarı sayfasında **devam**' ı seçin.

   ![HoloLens 2 yay uyarı ekranı.](images/arc_warning.png)

1. yay aracının HoloLens 2 işletim sistemi yüklemesini tamamlamasını bekleyin.
1. Cihaz, yüklemeyi ve önyükleme işlemini tamamladıktan sonra, bilgisayarınızdan dosya Gezgini 'ne gidin ve daha önce kaydedilen PPKG dosyasını cihaz klasörüne kopyalayın.

   > [!div class="mx-imgBorder"]
   > ![Dosya Gezgini penceresinde BILGISAYARDAKI PPKG dosyası.](images/offline-secure-file-explorer.png)

1. HoloLens 2 ' de, sağlama paketini çalıştırmak için aşağıdaki düğmeye basın: **birim aşağı** ve **güç düğmesine** aynı anda dokunun.
1. Sağlama paketini uygulamanız istenir, **Onayla** ' yı seçin.
1. Sağlama paketi tamamlandıktan sonra Tamam ' **ı** seçin.
1. Bundan sonra, paylaşılan yerel hesap ve parolayla cihazda oturum açmanız istenir.

## <a name="maintain"></a>Bakım

Bu yapılandırmayla, yukarıdaki işlemi yeniden başlatmanız ve cihazı yay aracıyla yeniden başlatmanız ve işletim sistemi ve/veya uygulamalar üzerinde herhangi bir güncelleştirme yapmak için yeni bir PPKG uygulamanız önerilir.
