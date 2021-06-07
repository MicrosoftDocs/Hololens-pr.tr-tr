---
title: Sertifika Yöneticisi
description: HoloLens 2 karma gerçeklik cihazlarındaki sertifikaları el ile yüklemeyi, yönetmeyi ve kaldırmayı öğrenin.
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378989"
---
# <a name="certificate-manager"></a>Sertifika Yöneticisi

- Yeni Sertifika Yöneticisi aracılığıyla cihaz güvenliği ve uyumluluğu için geliştirilmiş denetim, tanılama ve doğrulama araçları. Bu özellik, ticari ortamlarda sertifikalarınızı bir ölçekte dağıtmanıza, gidermenize ve doğrulamanıza olanak sağlar.

Windows holographic, sürüm 20H2 ' de, HoloLens 2 Ayarlar uygulamasına bir sertifika yöneticisi ekliyoruz. **Ayarlar > güncelleştirme & güvenlik > sertifikaları**' na gidin. Bu özellik, cihazınızdaki sertifikaları görüntülemek, yüklemek ve kaldırmak için basit ve kolay bir yol sağlar. Yeni Sertifika Yöneticisi ile yöneticiler ve kullanıcılar artık cihazların güvenli ve uyumlu kalmasını sağlamak için daha fazla denetim, tanılama ve doğrulama araçları geliştirmiştir. 

-   **Denetim:** Bir sertifikanın doğru şekilde dağıtıldığını doğrulama veya uygun şekilde kaldırıldığını doğrulama özelliği. 
-   **Tanılama:** Sorun ortaya çıktığında, cihazda uygun sertifikaların mevcut olduğunu doğrulamak zaman kazandırır ve sorun gidermeye yardımcı olur. 
-   **Doğrulama:** Bir sertifikanın hedeflenen amaca hizmet ettiği ve işlevsel olduğu doğrulanıyor, özellikle de daha büyük ölçekte sertifika dağıtmadan önce ticari ortamlarda önemli bir zaman kazandırabilir.

Listedeki belirli bir sertifikayı hızlı bir şekilde bulmak için ada, depoya veya sona erme tarihine göre sıralama seçenekleri vardır. Kullanıcılar ayrıca bir sertifikayı doğrudan arayabilir. Ayrı sertifika özelliklerini görüntülemek için sertifikayı seçin ve **bilgi**'ye tıklayın. 

Sertifika yüklemesi şu anda. cer ve. CRT dosyalarını desteklemektedir. Cihaz sahipleri, sertifikaları yerel makineye ve geçerli kullanıcıya yükleyebilir;  diğer tüm kullanıcılar yalnızca geçerli kullanıcıya yüklenebilir. Kullanıcılar yalnızca doğrudan ayarlar kullanıcı arabiriminden yüklenmiş sertifikaları kaldırabilir. Bir sertifika başka yollarla yüklendiyse aynı mekanizmaya de kaldırılmalıdır.

## <a name="to-install-a-certificate"></a>Bir sertifika yüklemek için: 

1.  HoloLens 2 ' 'nizi bir BILGISAYARA bağlayın.
1.  Yüklemek istediğiniz sertifika dosyasını HoloLens 2 ' de bir konuma yerleştirin.
1.  **Ayarlar uygulaması > güncelleştirme & güvenlik > sertifikaları**' na gidin ve sertifika yüklemeyi seçin.
1.  **Dosyayı Içeri aktar** ' a tıklayın ve sertifikayı kaydettiğiniz konuma gidin.
1.  **Depo konumunu** seçin.
1.  **Sertifika deposunu** seçin.
1.  **Yükle**'ye tıklayın.

Sertifikanın artık cihaza yüklü olması gerekir.

## <a name="to-remove-a-certificate"></a>Bir sertifikayı kaldırmak için: 
>[!WARNING]
> MDM ile dağıtılan sertifikaları sertifika yöneticisi 'nde görüntüleyebilseniz de, bunları Sertifika Yöneticisi 'nde kaldıramazsınız. MDM aracılığıyla kaldırmanız gerekir.
1. **Ayarlar uygulama > güncelleştirme ve güvenlik > sertifikaları '** na gidin.
1. Arama kutusunda Sertifikayı ada göre arayın.
1. Sertifikayı seçin.
1. **Kaldır** 'a tıklayın
1. Onay sorulduğunda **Evet** ' i seçin.



![Sertifikalar altındaki Ayarlar uygulamasında sertifika Görüntüleyicisi](images/certificate-viewer-device.jpg)

![Ayarlar ' da bir sertifikayı yüklemek için sertifika kullanıcı arabirimini nasıl kullanacağınızı gösteren resim.](images/certificate-device-install.jpg)
