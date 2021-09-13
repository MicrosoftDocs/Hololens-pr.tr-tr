---
title: Enterprise MAC adresi kısıtlanmış Wi-Fi ortamında HoloLens cihazların kaydı
description: HoloLens 2 cihazlarındaki ağ için MAC adresi
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036588"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise MAC adresi kısıtlanmış Wi-Fi ortamında HoloLens cihazların kaydı

Bu belgede, Wi-Fi MAC adresleriyle kısıtlanmış müşteri ortamlarında belirlediğimiz ve kablosuz ağların katılması için sertifikaların gerekli olduğu ortak bir senaryo açıklanır.

## <a name="example-scenario"></a>Örnek Senaryo

Güvenli ortamlarda birçok müşteri, kablosuz veya kablolu ağlarda yalnızca onaylanan cihazların (MAC adreslerine bağlı olarak) başarıyla bağlanmasına izin veren kısıtlamalara sahiptir. Bu, bir kablosuz erişim noktasında veya bir DHCP sunucusu üzerinden MAC adresi filtreleme aracılığıyla zorlanabilir. Ayrıca, bazı kablosuz ağlar PEAP ile korunabilir, bu da kablosuz ağda kimlik doğrulamadan önce bir sertifikanın cihaza uygulanmasını gerektirir.

bu senaryoda, iki temel gereksinim, HoloLens cihazları ağa birleştirilirken gecikme veya el ile müdahale gerektirebilir:

- Cihazın kablosuz ağa başarıyla katılmasını sağlamak için kablosuz PEAP sertifikasının cihaza uygulanması gerekir.
- HoloLens Wi-Fi bağdaştırıcısının MAC adresi kayıtlı olmalıdır.

Yukarıdaki gereksinimlerle ilgili temel sorunlar şunlardır:

1. MAC adresi şu anda yalnızca cihazdaki Ayarlar uygulamadan veya başarılı bir kayıttan sonra ıntune 'dan tanımlanabilir.

2. MAC adresi olmadan, cihaz kayıt işlemine başlamak için Wi-Fi ağa katılamaz.

3. Bu güçlüklere yönelik el ile yapılan geçici çözümler, bir teknisyenin cihazla etkileşimini gerektirir.

## <a name="solutions"></a>Çözümler

Ortamda kullanılabilir olan altyapıya bağlı olarak bu durumu geliştirmenin birçok yolu vardır.

| Çözüm | Avantajlar | Gereksinimler |
| --- | --- | --- |
| Ethernet bağdaştırıcısı ile paketi sağlama | , OOBE deneyimini geliştirir ve daha hızlı bir teknisyen deneyimi sağlar. | uyumlu USB-C Hub + Ethernet bağdaştırıcısı HoloLens ve teknisyen, MAC yakalama ve OOBE sonlandırması için cihazla etkileşime geçmek zorunda kalır |
| Ethernet üzerinden Intune kaydıyla Autopilot | Bu, tek adımlı bir bağlantıdır ve cihazın müşteri ortamına kaydı olur. MAC yakalama, cihazla etkileşime gerek kalmadan tamamlanabilir | ıntune, müşteri AAD kiracısı ve HoloLens uyumlu bir USB-C Ethernet bağdaştırıcısı için etkinleştirildi |
| MAC adreslerinin otomatik raporlaması | Cihazlar Intune kiracısına kaydedildiğinde, bir komut dosyası MAC adresini teknisyene rapor edebilir. | Intune PowerShell cmdlet 'leri |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Ethernet bağdaştırıcısı ile paketi sağlama

> [!NOTE] 
> Kablolu ağ aynı zamanda MAC kısıtlamalarına tabidir, USB-C hub + Ethernet bağdaştırıcısının MAC adresinin de önceden onaylanmış olması gerekir. Diğer cihazlardan ağa erişime izin verecek olduğundan, Bu bağdaştırıcıyla ilgilenmelidir.

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- HoloLens Ethernet bağdaştırıcısı ile uyumlu USB-C hub 'ı; ek sürücü veya uygulama yüklemesi gerektirmeyen herhangi bir bağdaştırıcı uygun olmalıdır.
- Şunu içeren sağlama paketi:
  - Kablosuz ağ bilgilerini ve sertifikayı içeren
  - Kuruluşun Azure AD için kayıt bilgilerini isteğe bağlı olarak içeren
  - Diğer gerekli sağlama ayarlarını içeren

### <a name="process"></a>İşleme

Işlem, cihazın yazılım düzeyine bağlı olarak farklılık gösterebilir. Cihazda [mayıs 2004 Güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-2004)varsa aşağıdaki adımları izleyin.

1. Sağlama paketini USB Stick köküne yerleştirin ve hub 'a takın.
2. Bağlan Hub + Ethernet bağdaştırıcısına Ethernet kablosu.
3. Bağlan HoloLens cihaza USB-C Hub 'ı.
4. HoloLens açın ve cihaza yerleştirin.
5. Sağlama paketini uygulamak için **ses azaltma ve güç düğmesine** basın.
6. teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.

Cihazda [mayıs 2004 güncelleştirmesinden](hololens-release-notes.md#windows-holographic-version-2004)önce bir işletim sistemi derlemesi varsa aşağıdaki adımları izleyin.

1. HoloLens açın ve cihazı bir bilgisayara takın.
2. Cihazın bılgısayarda bir dosya depolama cihazı olarak gösterilmesi gerekir.
3. Sağlama paketini cihaza Kopyala
4. Bağlan Hub 'a Ethernet kablosu.
5. Bağlan HoloLens cihaza USB-C Hub 'ı.
6. HoloLens koy
7. Sağlama paketini uygulamak için **ses azaltma ve güç** düğmesine basın.
8. teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.

### <a name="benefits"></a>Avantajlar

Bu, cihazın "tek dokunmasına" olanak sağlayarak doğru sağlama paketini uygulayabilir ve cihazın MAC adresini toplar. [Aşağıdaki kılavuzdan sonra sağlama paketleri oluşturulabilir.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Intune kaydı ile Autopilot

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- Windows Holographic 2004 çalıştıran HoloLens cihazları
- HoloLens Uyumlu USB-C Ethernet bağdaştırıcısı
- Intune, müşteri kiracısı için ayarlanır ve etkinleştirilir
- Autopilot için kaydedilmiş ve müşteri kiracısına aktarılan cihaz
- Cihaz için tanımlanan Intune Ilkeleri:
   - Kablosuz ağ bilgilerini ve sertifikayı içeren
   - Diğer gerekli sağlama ayarlarını içeren

Bu, Gelişmiş ağ gereksinimlerine sahip bir müşterinin cihazları uygulamalı, ölçeklenebilir bir yaklaşımda kaydetmesine olanak sağlar

Aşağıdaki gibi ek önkoşulların olması gerekir:
1. [Autopilot önizlemesi Için kiracıyı etkinleştirin](hololens2-autopilot.md).
1. ıntune içindeki sağlama paketinin yerini alacak HoloLens ilkeleri oluşturun.
1. HoloLens ıntune ilkelerini oluşturun.
1. Cihazları doğru gruba atayın.

### <a name="process"></a>İşleme

1. ethernet kablosunu bağdaştırıcıya Bağlan ve bağdaştırıcıyı HoloLens 2 cihazında USB-C bağlantı noktasına takın.

2. HoloLens açın.

3. Cihazın, Ethernet bağdaştırıcısı aracılığıyla otomatik olarak OOBE sırasında internet 'e bağlanması gerekir. Autopilot yapılandırmasını algılar ve Azure AD ve Intune ile otomatik olarak kayıt yaptırmalıdır.

4. Cihaz gereken Wi-Fi sertifikaları ve diğer yapılandırmaları Intune aracılığıyla uygular.

5. bu, tamamlandığında, ıntune (Endpoint Manager) portalını yükleyebilir ve **giriş > cihazları-> aygıa > donanımlarındaki** cihaz özellikleri sayfasına gidebilir.

6. Wi-Fi MAC adresi Intune portalında görünür olacaktır.

   ![Intune aracılığıyla MAC adresi.](images/mac-address-intune.jpg)

7. Teknisyen, bu MAC adresini izin verilen bir cihaz olarak ekler.

### <a name="benefits"></a>Avantajlar

bu, teknisyen için "kafa dışı" dağıtım deneyimine, cihazın Azure AD 'ye ve ıntune 'a kaydolmasına veya HoloLens ortamıyla el ile etkileşime girmesine gerek kalmadan Azure AD ve ıntune 'a kayıtlı olmasını sağlayacak şekilde izin verir.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>MAC adreslerinin teknisyene raporlaması

### <a name="requirements"></a>Gereksinimler

- müşteri kiracısında "ıntune Graph PowerShell" yetkilendirmesi
- ıntune Graph PowerShell 'i teknisyen makinesine yükleme.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune 'un "yönetilen cihazlar" öğelerine okuma erişimi. (Yardım masası Işleci veya üzeri ya da özel bir rol)

Mevcut olduğunda, yeni bir cihazın Intune içindeki kaydına bağlı olarak bir Otomasyon komutu tetiklemenin "basit" bir yolu yoktur. Bu nedenle, bu komut teknisyene Portal üzerinde oturum açıp el ile almak zorunda kalmadan MAC adresini almanın basit bir yolunu sağlar.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

bu, son 30 güne kayıtlı olan tüm HoloLens cihazlarının adını ve MAC adresini döndürür.

![PowerShell aracılığıyla MAC adresi.](images/mac-address-powershell.jpg)

### <a name="process"></a>İşleme

Intune kaydı tamamlandıktan sonra teknisyen, MAC adresini almak için yukarıdaki betiği çalıştırır.
