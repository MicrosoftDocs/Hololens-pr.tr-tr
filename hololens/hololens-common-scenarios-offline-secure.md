---
title: Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2
description: HoloLens cihazları için sağlama ile çevrimdışı güvenli dağıtım ve uygulama dağıtım senaryosu ayarlamayı öğrenin.
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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378961"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2

## <a name="overview"></a>Genel Bakış

Bu kılavuz, aşağıdaki kısıtlamalarla güvenli ortamlarda kullanmak üzere HoloLens 2'nin kilitlenmesini sağlayan örnek sağlama paketini uygulamaya yönelik kılavuz sağlar:

-   WiFi'yi devre dışı bırakma.
-   BlueTooth'ı devre dışı bırakma.
-   Mikrofonları devre dışı bırakma.
-   Sağlama paketleri eklemeyi veya kaldırmayı önler.
-   Hiçbir kullanıcı, yukarıdaki kısıtlı bileşenlerden herhangi birini etkinleştiremz.

[![Çevrimdışı Güvenli senaryosu ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Hazırlama

Windows 10 Pc Kurulumu
1. [En son HoloLens 2 işletim sistemi dosyasını doğrudan](https://aka.ms/hololens2download) bir bilgisayara indirin. 
   1. Bu yapılandırma için destek, Derleme 19041.1117 ve üzeri'ne dahildir.
1. Gelişmiş Kurtarma Yardımcı Aracı'nı (ARC) [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) bilgisayarınıza indirin/yükleyin
1. En son Windows Yapılandırma [Tasarımcısı (WCD) aracını](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) indirin/yükleyin Microsoft Store bilgisayarınıza yükleyin.
1. [PPKG'OfflineSecureHL2_Sample oluşturmak için proje dosyalarıyla](https://aka.ms/HoloLensDocs-SecureOfflineSample) birlikte OfflineSecureHL2_Sample klasörünü indirin.
1. Çevrimdışı İş [Hattı uygulamanızı PPKG dağıtımı için hazırlayın.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Yapılandırma

Güvenli Yapılandırma Sağlama Paketi Oluşturma

1. Bilgisayarınızda WCD aracını başlatma.
1. Dosya **-> Proje aç'ı seçin.**
  1. Daha önce kaydedilen OfflineSecureHL2_Sample klasörüne gidin ve şu seçeneği OfflineSecureHL2_Sample.icdproj.xml
1. Proje açılmalı ve artık Kullanılabilir Özelleştirmeler'in bir listesine sahipsiniz:

   > [!div class="mx-imgBorder"]
   > ![WCD'de açık yapılandırma paketinin ekran görüntüsü](images/offline-secure-sample-wcd.png)

   Bu sağlama paketinde ayarlanmış yapılandırmalar:
   
   |     Öğe                                                |     Ayar                       |     Açıklama                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Hesaplar / Kullanıcılar                                    |     Yerel Kullanıcı Adı & Parolası    |     Bu çevrimdışı cihazlar için tek bir kullanıcı adı ve parola ayar olmalı ve cihazın tüm kullanıcıları tarafından paylaşılır.          |
   |     İlk Deneyim / HoloLens / SkipCalibration       |     Doğru                          |     Yalnızca ilk cihaz kurulumu sırasında ayarlamayı atlar                                                                             |
   |     İlk Deneyim / HoloLens / SkipTraining          |     Doğru                          |     İlk cihaz kurulumu sırasında cihaz eğitimlerini atlar                                                                              |
   |     İlk Deneyim / HoloLens / WiFi                  |     Doğru                          |     İlk Wi-Fi sırasında yapılandırmayı atlar                                                                                 |
   |     İlkeler/Bağlantı/AllowBluetooth                |     Hayır                            |     Bluetooth'u devre dışı bırakma                                                                                                             |
   |     İlkeler/Deneyim/AllowCortana                    |     Hayır                            |     Cortana'yı devre dışı (mikrofonlar devre dışı bırakıldıklarında olası sorunları ortadan kaldırmak için)                                          |
   |     İlkeler/MixedReality/MicrophoneDisabled            |     Yes                           |     Mikrofonu Devre Dışı Bırakıyor                                                                                                            |
   |     İlkeler/Gizlilik/LetAppsAccessLocation              |     Reddetmeye zorlama                    |     Uygulamaların Konum verilerine erişmeye çalışmasını önler (Konum izleme devre dışı bırakılmıştır)    |
   |     İlkeler/Gizlilik/LetAppsAccessMicrophone            |     Reddetmeye zorlama                    |     Uygulamaların Mikrofonlara erişmeye çalışmasını önler (Mikrofonlar devre dışı bırakılmıştır)           |
   |     İlkeler/Güvenlik/AllowAddProvisioningPackage       |     Hayır                            |     Kilitlenmiş ilkeleri geçersiz kılmaya çalışan sağlama paketleri eklemesini önler.                         |
   |     İlkeler/Güvenlik/AllowRemoveProvisioningPackage    |     Hayır                            |     Kilitlenmiş bu sağlama paketini herkesin kaldırmasını önler.                                                           |
   |     İlkeler/Sistem/AllowLocation                       |     Hayır                            |     Cihazın konum verilerini izlemesini önler.                                                                        |
   |     İlkeler/WiFi/AllowWiFi                             |     Hayır                            |     Devre dışı Wi-Fi                                                                                                                 |

1. Çalışma Zamanı Ayarları altında Hesaplar **/ Kullanıcılar / KullanıcıAdı: Holo / Password öğesini seçin.**

   İsterseniz parolayı not edin ve sıfırlayın.

1. UniversalAppInstall / UserContextApp'e gidin ve bu cihazlara dağıtacakları [LOB](app-deploy-provisioning-package.md) uygulamasını yapılandırın.

   > [!div class="mx-imgBorder"]
   > ![WCD'de uygulamanın nereye ekli olduğunu ekran görüntüsü.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Tamamlandıktan sonra "Dışarı Aktar" düğmesini seçin ve sağlama paketiniz oluşturulana kadar tüm istemleri izleyin.

   > [!div class="mx-imgBorder"]
   > ![WCD'de bu paket için Dışarı Aktar düğmesinin ekran görüntüsü.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Dağıtma

1. HL2'i USB kablosu Windows 10 bilgisayarınıza bağlayın.
1. ARC aracını başlatma ve **HoloLens 2'yi seçme**

   ![HoloLens 2 temiz reflash ilk ekranı](images/ARC2.png)

1. Sonraki ekranda El ile paket **seçimi'ne tıklayın.**

   ![HoloLens 2 ARC bilgi ekranı](images/arc_device_info.png)

1. Daha önce indirilen .ffu dosyasına gidin ve Aç'ı **seçin.**
1. Uyarı sayfasında Devam'ı **seçin.**

   ![HoloLens 2 ARC uyarı ekranı](images/arc_warning.png)

1. ARC aracının HoloLens 2 işletim sistemi yükleme işlemini tamamlaması için bekleyin.
1. Cihaz yükleme ve yeniden yükleme işlemini tamamlandıktan sonra bilgisayarınızdan Dosya Gezgini'ye gidin ve daha önce kaydedilen PPKG dosyasını cihaz klasörüne kopyalayın.

   > [!div class="mx-imgBorder"]
   > ![Dosya Gezgini penceresindeki PC'de PPKG dosyası.](images/offline-secure-file-explorer.png)

1. HoloLens 2'de aşağıdaki düğme birleşik tuşuna basarak Sağlama  Paketini çalıştırın: Birim Kapalı ve Güç Düğmesi'ne **aynı** anda dokunun.
1. Sağlama Paketi'nin uygulanarak Onayla'nın seçili olması **istenir**
1. Sağlama paketi tamamlandıktan sonra Tamam'ı **seçin.**
1. Daha sonra cihazda paylaşılan yerel hesap ve parolayla oturum açmanız istendiğinde.

## <a name="maintain"></a>Bakım

Bu yapılandırmayla, yukarıdaki işlemi yeniden başlatmanız ve ARC aracıyla cihaza ters eğik çizgi uygulamanız ve işletim sistemi ve/veya uygulamalarda güncelleştirme yapmak için yeni bir PPKG uygulamanız önerilir.
