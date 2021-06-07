---
title: MAC adresi kısıtlanmış Wi-Fi ortamında, HoloLens cihazlarının kurumsal kaydı
description: HoloLens 2 cihazlarında ağ için MAC adresi
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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380187"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>MAC adresi kısıtlanmış Wi-Fi ortamında, HoloLens cihazlarının kurumsal kaydı

Bu belgede, Wi-Fi MAC adresleriyle kısıtlanmış müşteri ortamlarında belirlediğimiz ve kablosuz ağların katılması için sertifikaların gerekli olduğu ortak bir senaryo açıklanır.

## <a name="example-scenario"></a>Örnek Senaryo

Güvenli ortamlarda birçok müşteri, kablosuz veya kablolu ağlarda yalnızca onaylanan cihazların (MAC adreslerine bağlı olarak) başarıyla bağlanmasına izin veren kısıtlamalara sahiptir. Bu, bir kablosuz erişim noktasında veya bir DHCP sunucusu üzerinden MAC adresi filtreleme aracılığıyla zorlanabilir. Ayrıca, bazı kablosuz ağlar PEAP ile korunabilir, bu da kablosuz ağda kimlik doğrulamadan önce bir sertifikanın cihaza uygulanmasını gerektirir.

Bu senaryoda, iki temel gereksinim, HoloLens cihazlarını ağa eklerken gecikmeler verebilir veya el ile müdahale gerektirebilir:

- Cihazın kablosuz ağa başarıyla katılmasını sağlamak için kablosuz PEAP sertifikasının cihaza uygulanması gerekir.
- HoloLens Wi-Fi bağdaştırıcısının MAC adresi kayıtlı olmalıdır.

Yukarıdaki gereksinimlerle ilgili temel sorunlar şunlardır:

1. MAC adresi şu anda yalnızca cihazdaki Ayarlar uygulamasından veya başarılı bir kayıttan sonra Intune 'dan tanımlanabilir.

2. MAC adresi olmadan, cihaz kayıt işlemine başlamak için Wi-Fi ağa katılamaz.

3. Bu güçlüklere yönelik el ile yapılan geçici çözümler, bir teknisyenin cihazla etkileşimini gerektirir.

## <a name="solutions"></a>Çözümler

Ortamda kullanılabilir olan altyapıya bağlı olarak bu durumu geliştirmenin birçok yolu vardır.

| Çözüm | Avantajlar | Gereksinimler |
| --- | --- | --- |
| Ethernet bağdaştırıcısı ile paketi sağlama | , OOBE deneyimini geliştirir ve daha hızlı bir teknisyen deneyimi sağlar. | HoloLens uyumlu USB-C hub + Ethernet bağdaştırıcısı ve teknisyen, MAC yakalama ve OOBE sonlandırması için cihazla etkileşimde bulunmak zorunda kalır |
| Ethernet üzerinden Intune kaydıyla Autopilot | Bu, tek adımlı bir bağlantıdır ve cihazın müşteri ortamına kaydı olur. MAC yakalama, cihazla etkileşime gerek kalmadan tamamlanabilir | Intune, müşteri AAD kiracısı ve bir HoloLens uyumlu USB-C Ethernet bağdaştırıcısı için etkinleştirildi |
| MAC adreslerinin otomatik raporlaması | Cihazlar Intune kiracısına kaydedildiğinde, bir komut dosyası MAC adresini teknisyene rapor edebilir. | Intune PowerShell cmdlet 'leri |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Ethernet bağdaştırıcısı ile paketi sağlama

> [!NOTE] 
> Kablolu ağ aynı zamanda MAC kısıtlamalarına tabidir, USB-C hub + Ethernet bağdaştırıcısının MAC adresinin de önceden onaylanmış olması gerekir. Diğer cihazlardan ağa erişime izin verecek olduğundan, Bu bağdaştırıcıyla ilgilenmelidir.

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- Ethernet bağdaştırıcısı ile HoloLens uyumlu USB-C hub 'ı; ek sürücü veya uygulama yüklemesi gerektirmeyen herhangi bir bağdaştırıcı uygun olmalıdır.
- Şunu içeren sağlama paketi:
  - Kablosuz ağ bilgilerini ve sertifikayı içeren
  - Kuruluşun Azure AD için kayıt bilgilerini isteğe bağlı olarak içeren
  - Diğer gerekli sağlama ayarlarını içeren

### <a name="process"></a>İşleme

Işlem, cihazın yazılım düzeyine bağlı olarak farklılık gösterebilir. Cihazda [mayıs 2004 Güncelleştirmesi](hololens-release-notes.md#windows-holographic-version-2004)varsa aşağıdaki adımları izleyin.

1. Sağlama paketini USB Stick köküne yerleştirin ve hub 'a takın.
2. Ethernet kablosunu hub + Ethernet bağdaştırıcısına bağlayın.
3. USB-C hub 'ını HoloLens cihazına bağlayın.
4. HoloLens 'i açın ve cihaza yerleştirin.
5. Sağlama paketini uygulamak için **ses azaltma ve güç düğmesine** basın.
6. Teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.

Cihazda [mayıs 2004 güncelleştirmesinden](hololens-release-notes.md#windows-holographic-version-2004)önce bir işletim sistemi derlemesi varsa aşağıdaki adımları izleyin.

1. HoloLens 'i açın ve cihazı bir BILGISAYARA takın.
2. Cihazın bılgısayarda bir dosya depolama cihazı olarak gösterilmesi gerekir.
3. Sağlama paketini cihaza Kopyala
4. Ethernet kablosunu hub 'a bağlayın.
5. USB-C hub 'ını HoloLens cihazına bağlayın.
6. HoloLens 'e yerleştir
7. Sağlama paketini uygulamak için **ses azaltma ve güç** düğmesine basın.
8. Teknisyen artık OOBE 'yi izleyebilir ve tamamlandığında, cihazın MAC adresini almak için Ayarlar uygulamasını açın.

### <a name="benefits"></a>Avantajlar

Bu, cihazın "tek dokunmasına" olanak sağlayarak doğru sağlama paketini uygulayabilir ve cihazın MAC adresini toplar. [Aşağıdaki kılavuzdan sonra sağlama paketleri oluşturulabilir.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Intune kaydı ile Autopilot

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- Windows holographic 2004 çalıştıran HoloLens cihazları
- HoloLens uyumlu USB-C Ethernet bağdaştırıcısı
- Intune, müşteri kiracısı için ayarlanır ve etkinleştirilir
- Autopilot için kaydedilmiş ve müşteri kiracısına aktarılan cihaz
- Cihaz için tanımlanan Intune Ilkeleri:
   - Kablosuz ağ bilgilerini ve sertifikayı içeren
   - Diğer gerekli sağlama ayarlarını içeren

Bu, Gelişmiş ağ gereksinimlerine sahip bir müşterinin cihazları uygulamalı, ölçeklenebilir bir yaklaşımda kaydetmesine olanak sağlar

Aşağıdaki gibi ek önkoşulların olması gerekir:
1. [Autopilot önizlemesi Için kiracıyı etkinleştirin](https://docs.microsoft.com/hololens/hololens2-autopilot).
1. Intune içindeki sağlama paketini değiştirmek için HoloLens ilkeleri oluşturun.
1. HoloLens Intune Ilkelerini oluşturun.
1. Cihazları doğru gruba atayın.

### <a name="process"></a>İşleme

1. Ethernet kablosunu bağdaştırıcıya bağlayın ve HoloLens 2 cihazında bağdaştırıcıyı USB-C bağlantı noktasına takın.

2. HoloLens 'i açın.

3. Cihazın, Ethernet bağdaştırıcısı aracılığıyla otomatik olarak OOBE sırasında internet 'e bağlanması gerekir. Autopilot yapılandırmasını algılar ve Azure AD ve Intune ile otomatik olarak kayıt yaptırmalıdır.

4. Cihaz gereken Wi-Fi sertifikaları ve diğer yapılandırmaları Intune aracılığıyla uygular.

5. Bu, tamamlandığında, teknisyen, Intune (Endpoint Manager) portalını yükleyebilir ve **ana > cihazlar-> aygıtadı > donanımında** cihaz özellikleri sayfasına gidebilir.

6. Wi-Fi MAC adresi Intune portalında görünür olacaktır.

   ![Intune aracılığıyla MAC adresi](images/mac-address-intune.jpg)

7. Teknisyen, bu MAC adresini izin verilen bir cihaz olarak ekler.

### <a name="benefits"></a>Avantajlar

Bu, teknisyen için "kafa dışı" dağıtım deneyimine, cihazın Azure AD 'ye ve Intune 'a kaydolmasına gerek olmadan veya HoloLens ortamıyla el ile etkileşimde bulunmak zorunda kalmadan Azure AD ve Intune 'a kayıtlı olmasını sağlayacak şekilde izin verir.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>MAC adreslerinin teknisyene raporlaması

### <a name="requirements"></a>Gereksinimler

- Müşteri kiracısında "Intune Graph PowerShell" yetkilendirmesi
- Teknisyenler makinesinde Intune Graph PowerShell 'i yükleme.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune 'un "yönetilen cihazlar" öğelerine okuma erişimi. (Yardım masası Işleci veya üzeri ya da özel bir rol)

Mevcut olduğunda, yeni bir cihazın Intune içindeki kaydına bağlı olarak bir Otomasyon komutu tetiklemenin "basit" bir yolu yoktur. Bu nedenle, bu komut teknisyene Portal üzerinde oturum açıp el ile almak zorunda kalmadan MAC adresini almanın basit bir yolunu sağlar.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Bu, son 30 güne kayıtlı olan herhangi bir HoloLens cihazlarının adını ve MAC adresini döndürür.

![PowerShell aracılığıyla MAC adresi](images/mac-address-powershell.jpg)

### <a name="process"></a>İşleme

Intune kaydı tamamlandıktan sonra teknisyen, MAC adresini almak için yukarıdaki betiği çalıştırır.
