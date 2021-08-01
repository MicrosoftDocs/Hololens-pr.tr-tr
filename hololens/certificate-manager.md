---
title: Sertifika Yöneticisi
description: 2 karma gerçeklik cihazına el ile sertifika yükleme, HoloLens kaldırmayı öğrenin.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: 78e5f26014e55c13fee9c2b75a80810fd2e77877
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2021
ms.locfileid: "115009332"
---
# <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama aracı. Bu özellik, ticari ortamlarda büyük ölçekte sertifikalarınızı dağıtmanıza, sorun gidermenize ve doğrulamanıza olanak tanır.

Holographic Windows sürüm 20H2'de, HoloLens 2 Ayarlar ekliyoruz. Ayarlar > **Security & Sertifikaları'> gidin.** Bu özellik, cihazınıza sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kullanımı kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için denetim, tanılama ve doğrulama araçlarını iyileştirdi. 

-   **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığından emin olmak veya sertifikanın uygun şekilde kaldırıldığından emin olmak. 
-   **Tanılama:** Sorunlar ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulama zaman kazandırır ve sorun gidermeye yardımcı olur. 
-   **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğunu doğrulamak, sertifikaları daha büyük ölçekte dağıtmadan önce özellikle ticari ortamlarda önemli ölçüde zaman tasarrufu sağlar.

Listede belirli bir sertifikayı hızla bulmak için ad, depolama veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar sertifikayı doğrudan da arayabilir. Tek tek sertifika özelliklerini görüntülemek için sertifikayı seçin ve Bilgi'ye **tıklayın.** 

Sertifika yüklemesi şu anda .cer ve .crt dosyalarını desteklemektedir. Cihaz Sahipleri Sertifikaları Yerel Makineye ve Geçerli Kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca Geçerli Kullanıcı'ya yükleyebilir.

## <a name="to-install-a-certificate"></a>Sertifika yüklemek için: 

1.  Bağlan 2 HoloLens bilgisayara bağlayın.
1.  Yüklemek istediğiniz sertifika dosyasını dosyanın 2. HoloLens.
1.  Ayarlar **App > Update & Security > 'a** gidin ve Sertifika yükle'yi seçin.
1.  Dosyayı **İçeri Aktar'a** tıklayın ve sertifikayı kaydeden konuma gidin.
1.  Mağaza **Konumu'.**
1.  Sertifika **Deposu'ları seçin.**
1.  **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklenmiş olması gerekir.

![Sertifikalar altındaki Ayarlar görüntüleyici.](images/certificate-viewer-device.jpg)

![Sertifika kullanıcı arabirimini kullanarak sertifikayı Ayarlar.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Bir sertifikayı kaldırmak için:

> [!WARNING]
> Sertifika Yöneticisi'ni kullanarak, kullanıcılar yalnızca doğrudan Ayarlar kaldırabilir. Bir sertifika başka bir şekilde yüklendiyse, aynı mekanizma tarafından da kaldırılması gerekir ve Sertifika Yöneticisi'ne kaldırılamaz. Sertifika Yöneticisi'nde MDM tarafından dağıtılan sertifikaları görüntüleyebizle birlikte, bunları Sertifika Yöneticisi'nde kaldıramazsiniz. Bunları MDM aracılığıyla kaldırmanız gerekir.

1. Ayarlar **App > Update and Security > Certificates 'a gidin.**
1. Arama kutusunda sertifikayı adıyla ara.
1. Sertifikayı seçin.
1. **Kaldır'a tıklayın**
1. Onay **istendiğinde** Evet'i seçin.

