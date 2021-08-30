---
title: Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2
description: Mobil cihazlar için sağlama ile çevrimdışı güvenli dağıtım ve uygulama dağıtım senaryosu HoloLens öğrenin.
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189129"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Yaygın Senaryolar – Çevrimdışı Güvenli HoloLens 2

## <a name="overview"></a>Genel Bakış

Bu kılavuz, aşağıdaki kısıtlamalarla güvenli ortamlarda kullanmak üzere bir HoloLens 2'nin kilitlenmesini sağlayan örnek Sağlama Paketi uygulama konusunda rehberlik sağlar:

-   WiFi'yi devre dışı bırakma.
-   BlueTooth'ı devre dışı bırakma.
-   Mikrofonları devre dışı bırakma.
-   Sağlama paketleri eklemeyi veya kaldırmayı önler.
-   Hiçbir kullanıcı, yukarıdaki kısıtlı bileşenlerden herhangi birini etkinleştire değildir.

[![Çevrimdışı Güvenli senaryosu. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Hazırlama

Windows 10 BILGISAYAR Kurulumu
1. [En son HoloLens 2 işletim sistemi dosyasını](https://aka.ms/hololens2download) doğrudan bir bilgisayara indirin. 
   1. Bu yapılandırma için destek, Derleme 19041.1117 ve üzeri'ne dahildir.
1. Gelişmiş Kurtarma Yardımcı Aracı'nı (ARC) [Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) bilgisayarınıza indirin/yükleyin
1. En son Windows [Yapılandırma Tasarımcısı (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) aracını indirin/yükleyin Microsoft Store bilgisayarınıza yükleyin.
1. PPKG [OfflineSecureHL2_Sample proje dosyalarıyla birlikte](https://aka.ms/HoloLensDocs-SecureOfflineSample) OfflineSecureHL2_Sample klasörünü indirin.
1. Çevrimdışı İş [Hattı uygulamanızı PPKG dağıtımı için hazırlayın.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Yapılandırma

Güvenli Yapılandırma Sağlama Paketi Oluşturma

1. Bilgisayarınızda WCD aracını başlatma.
1. Dosya **-> Proje aç'ı seçin.**
  1. Daha önce kaydedilen OfflineSecureHL2_Sample klasörüne gidin ve şu seçeneği seçin: OfflineSecureHL2_Sample.icdproj.xml
1. Proje açılmalı ve artık Kullanılabilir Özelleştirmeler'in bir listesine sahipsiniz:

   > [!div class="mx-imgBorder"]
   > ![WCD'de açık yapılandırma paketinin ekran görüntüsü.](images/offline-secure-sample-wcd.png)

   Bu sağlama paketinde ayarlanmış yapılandırmalar:
   
   |     Öğe                                                |     Ayar                       |     Açıklama                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Hesaplar / Kullanıcılar                                    |     Yerel Kullanıcı Adı & Parolası    |     Bu çevrimdışı cihazlar için tek bir kullanıcı adı ve parola ayar olmalı ve cihazın tüm kullanıcıları tarafından paylaşılır.          |
   |     İlk Deneyim / HoloLens / SkipCalibration       |     Doğru                          |     Yalnızca ilk cihaz kurulumu sırasında ayarlamayı atlar                                                                             |
   |     İlk Deneyim / HoloLens / SkipTraining          |     Doğru                          |     İlk cihaz kurulumu sırasında cihaz eğitimlerini atlar                                                                              |
   |     İlk Deneyim / HoloLens / WiFi                  |     Doğru                          |     İlk Wi-Fi sırasında yapılandırmayı atlar                                                                                 |
   |     İlkeler/Bağlantı/AllowBluetooth                |     No                            |     Devre dışı Bluetooth                                                                                                             |
   |     İlkeler/Deneyim/AllowCortana                    |     No                            |     Devre Cortana devre dışı bırakılır (mikrofonlar devre dışı bırakılana kadar olası sorunları ortadan kaldırmak için)                                          |
   |     İlkeler/MixedReality/MikrofonDizli            |     Yes                           |     Mikrofonu Devre Dışı Bırakıyor                                                                                                            |
   |     İlkeler/Gizlilik/LetAppsAccessLocation              |     Reddetmeye zorlama                    |     Uygulamaların Konum verilerine erişmeye çalışmasını önler (Konum izleme devre dışı bırakılmıştır)    |
   |     İlkeler/Gizlilik/LetAppsAccessMicrophone            |     Reddetmeye zorlama                    |     Uygulamaların Mikrofonlara erişmeye çalışmasını önler (Mikrofonlar devre dışı bırakılmıştır)           |
   |     İlkeler/Güvenlik/AllowAddProvisioningPackage       |     No                            |     Kilitlenmiş ilkeleri geçersiz kılmaya çalışan sağlama paketleri eklemesini önler.                         |
   |     İlkeler/Güvenlik/AllowRemoveProvisioningPackage    |     No                            |     Herkesin bu kilitli sağlama paketini kaldırmasını önler.                                                           |
   |     İlkeler/Sistem/AllowLocation                       |     No                            |     Cihazın konum verilerini izlemesini önler.                                                                        |
   |     İlkeler/WiFi/AllowWiFi                             |     No                            |     Devre dışı Wi-Fi                                                                                                                 |

1. Çalışma zamanı Ayarlar Hesaplar **/ Kullanıcılar / KullanıcıAdı: Holo / Password seçeneğini seçin.**

   İsterseniz parolayı not edin ve sıfırlayın.

1. UniversalAppInstall / UserContextApp'e gidin ve bu cihazlara dağıtacakları [LOB](app-deploy-provisioning-package.md) uygulamasını yapılandırın.

   > [!div class="mx-imgBorder"]
   > ![WCD'de uygulamanın nereye ekli olduğunu ekran görüntüsü.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Tamamlandıktan sonra "Dışarı Aktar" düğmesini seçin ve sağlama paketiniz oluşturulana kadar tüm istemleri izleyin.

   > [!div class="mx-imgBorder"]
   > ![WCD'de bu paket için Dışarı Aktar düğmesinin ekran görüntüsü.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Dağıtma

1. Bağlan USB kablosu aracılığıyla HL2'Windows 10 bilgisayarınıza bağlayın.
1. ARC aracını başlatma ve HoloLens **2'yi seçme**

   ![HoloLens 2 temiz reflash başlangıç ekranı.](images/ARC2.png)

1. Sonraki ekranda El ile paket **seçimi'ne tıklayın.**

   ![HoloLens 2 ARC bilgi ekranı.](images/arc_device_info.png)

1. Daha önce indirilen .ffu dosyasına gidin ve Aç'ı **seçin.**
1. Uyarı sayfasında Devam'ı **seçin.**

   ![HoloLens 2 ARC uyarı ekranı.](images/arc_warning.png)

1. ARC aracının 2 işletim sistemi yüklemesi HoloLens bekleyin.
1. Cihaz yükleme ve yeniden yükleme işlemini tamamlandıktan sonra bilgisayarınızdan Dosya Gezgini'ye gidin ve daha önce kaydedilen PPKG dosyasını cihaz klasörüne kopyalayın.

   > [!div class="mx-imgBorder"]
   > ![Dosya Gezgini penceresindeki PC'de PPKG dosyası.](images/offline-secure-file-explorer.png)

1. 2. HoloLens şu düğme birleşik tuşuna basarak Sağlama Paketini çalıştırın: Birim Kapalı ve Güç Düğmesi'ne **aynı** anda dokunun. 
1. Sağlama Paketi'nin uygulanarak Onayla'nın seçili olması **istenir**
1. Sağlama paketi tamamlandıktan sonra Tamam'ı **seçin.**
1. Daha sonra paylaşılan yerel hesap ve parola ile cihazda oturum açmanız istendiğinde.

## <a name="maintain"></a>Bakım

Bu yapılandırmayla, yukarıdaki işlemi yeniden başlatmanız ve ARC aracıyla cihaza ters eğik çizgi uygulamanız ve işletim sistemi ve/veya uygulamalarda güncelleştirme yapmak için yeni bir PPKG uygulamanız önerilir.
