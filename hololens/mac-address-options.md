---
title: Enterprise MAC HoloLens kısıtlı Wi-Fi Ortamında Wi-Fi kaydı
description: HoloLens 2 cihazlardaki ağ için MAC adresi
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
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639446"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise MAC HoloLens kısıtlı Wi-Fi Ortamında Wi-Fi kaydı

Bu belgede, müşterinin ortamlarında, ağ iletişimin MAC adresleriyle Wi-Fi veya Kablosuz ağlara katılmak için sertifikaların gerekli olduğu yaygın bir senaryo açıklanmıştır.

## <a name="example-scenario"></a>Örnek Senaryo

Güvenli ortamlardaki birçok müşteri, Kablosuz veya kablolu ağlarında yalnızca onaylanan cihazların (MAC Adreslerine göre) başarıyla bağlanmasına izin verecek kısıtlamalara sahiptir. Bu, Bir Kablosuz Erişim Noktası'nın MAC Adresi filtrelemesi yoluyla veya bir DHCP sunucusu aracılığıyla zorlanan bir durum olabilir. Ayrıca, bazı Kablosuz ağlar PEAP ile korunarak Kablosuz ağ kimlik doğrulamadan önce cihaza bir sertifikanın uygulanması gerekir.

Bu senaryoda, iki temel gereksinimler gecikmelere neden olabilir veya cihazların ağa HoloLens el ile müdahale gerektirmektedir:

- Kablosuz PEAP sertifikası, cihazın kablosuz ağa başarıyla katılmadan önce cihaza uygulanması gerekir.
- HoloLens Wi-Fi mac adresi kayıtlı olması gerekir.

Yukarıdaki gereksinimlerle ilgili temel zorluklar:

1. MAC Adresi şu anda yalnızca cihaz Ayarlar veya başarılı bir kayıttan sonra Intune'dan belirleniyor.

2. MAC adresi olmadan cihaz kayıt işleminin başlaması için Wi-Fi Ağına katamaz.

3. Bu zorluklara el ile geçici çözümler için teknisyenin cihazla etkileşim kurması gerekir.

## <a name="solutions"></a>Çözümler

Ortamdaki altyapıya bağlı olarak bu durumu geliştirmenin birçok yolu vardır.

| Çözüm | Avantajlar | Gereksinimler |
| --- | --- | --- |
| Ethernet Adaptor ile Paket Sağlama | OOBE deneyimini iyiler ve daha hızlı bir teknisyen deneyimi sağlar. | HoloLens UYUMLU USB-C Hub + Ethernet uyarıcısı, teknisyenin YINE DE MAC yakalama ve OOBE son haline için cihazla etkileşim kurması gerekir |
| Ethernet üzerinden Intune Kaydı ile Autopilot | Bu tek adımlı bir bağlantıdır ve cihazın müşteri ortamına kaydıdır. MAC yakalama, cihazla etkileşim kurmak zorunda kalmadan tamamlanır | Müşteri AAD kiracısı ve uyumlu bir USB-C Ethernet HoloLens intune etkinleştirildi |
| MAC Adreslerinin otomatik raporlaması | Cihazlar Intune kiracısına kaydediken, bir betik MAC adresini teknisyene bildirebilirsiniz. | Intune PowerShell cmdlet'leri |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Ethernet Adaptor ile Paket Sağlama

> [!NOTE] 
> Kablolu ağ da MAC kısıtlamalarına tabi ise, USB-C Hub + Ethernet bağdaştırıcısının MAC adresinin de önceden onaylanması gerekir. Diğer cihazlardan ağa erişime izin verecek şekilde bu bağdaştırıcıyla dikkat edin.

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- HoloLens Ethernet bağdaştırıcısı ile uyumlu USB-C Hub — Ek sürücü veya uygulama yüklemesi gerektirmeyen tüm bağdaştırıcılar uygun olmalıdır.
- Şunları içeren Sağlama Paketi:
  - Kablosuz Ağ bilgilerini ve Sertifikayı İçeren
  - İsteğe bağlı olarak kuruluşun Azure AD'si için kayıt bilgilerini içerir
  - Gerekli diğer sağlama ayarlarını içeren

### <a name="process"></a>İşleme

İşlem, cihazın yazılım düzeyine bağlı olarak değişebilir. Cihazda Mayıs [2004 güncelleştirmesi varsa](hololens-release-notes.md#windows-holographic-version-2004)aşağıdaki adımları izleyin.

1. Sağlama paketini USB çubuğu köküne yer ve Hub'a takın.
2. Bağlan Hub + Ethernet bağdaştırıcısına Ethernet kablosu.
3. Bağlan Usb-C Hub'HoloLens cihaz.
4. Cihazı HoloLens cihazı açın.
5. Sağlama **Paketini uygulamak için Birim Kapalı ve** Güç düğmesine basın.
6. Teknisyen artık OOBE'yi takip eder ve tamamlandığında cihazın MAC Adresini almak Ayarlar App'i açabilir.

Cihazın Mayıs [2004](hololens-release-notes.md#windows-holographic-version-2004)güncelleştirmesi öncesinde bir işletim sistemi derlemesi varsa aşağıdaki adımları izleyin.

1. Cihazı açın HoloLens bilgisayara takın.
2. Cihaz, pc'de bir dosya depolama cihazı olarak göster gerekir.
3. Sağlama Paketini Cihaza Kopyalama
4. Bağlan Hub'a Ethernet kablosu.
5. Bağlan Usb-C Hub'HoloLens cihaz.
6. İlkeyi HoloLens
7. Sağlama **Paketini uygulamak için Birim** Kapalı ve Güç düğmesine basın.
8. Teknisyen artık OOBE'yi takip eder ve tamamlandığında cihazın MAC Adresini almak Ayarlar App'i açabilir.

### <a name="benefits"></a>Avantajlar

Bu, doğru sağlama paketini uygulamak ve cihazın MAC adresini toplamak için cihazın "Tek dokunmasına" olanak sağlar. [Sağlama paketleri buradaki kılavuzdan sonra oluşturulabilir.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Intune Kaydı ile Autopilot

### <a name="requirements"></a>Gereksinimler

- Müşteri ağına erişimi olan kablolu ağ bağlantı noktası
- HoloLens Holographic 2004 Windows çalıştıran cihazlar
- HoloLens Uyumlu USB-C Ethernet bağdaştırıcısı
- Intune müşteri Kiracısı için ayarlanmış ve etkinleştirilmiştir
- Autopilot için kaydedilen ve Müşteri Kiracısına aktarılan cihaz
- Cihaz için tanımlanan Intune İlkeleri:
   - Kablosuz Ağ bilgilerini ve Sertifikayı İçeren
   - Gerekli diğer sağlama ayarlarını içeren

Bu, gelişmiş ağ gereksinimlerine sahip bir müşterinin cihazları el ile ve ölçeklenebilir bir yaklaşımla kaydetmesine olanak tanır

Aşağıdaki gibi ek önkullar gerekir:
1. [Autopilot önizlemesi için Kiracıyı etkinleştirin.](hololens2-autopilot.md)
1. Intune'HoloLens Sağlama Paketi'nin yerini alacak yeni ilkeler oluşturun.
1. Intune İlkeleri HoloLens oluşturma.
1. Cihazları doğru gruba attayabilirsiniz.

### <a name="process"></a>İşleme

1. Bağlan ethernet kablosunu bağdaştırıcıya takın ve bağdaştırıcıyı 2 cihazında USB-C bağlantı noktasına HoloLens takın.

2. İlkeyi HoloLens.

3. Cihazın Ethernet uyarıcısı aracılığıyla OOBE sırasında otomatik olarak İnternet'e bağlanması gerekir. Autopilot yapılandırmasını algılaması ve Azure AD ile Intune'a otomatik olarak kaydolması gerekir.

4. Cihaz gerekli sertifikaları ve Wi-Fi Intune aracılığıyla diğer yapılandırmaları uygulayacak.

5. Tamamlandığında, teknisyen Intune (Endpoint Manager) Portalı'> Cihazlar **-> DeviceName -> Donanım)** sayfasından Intune (Endpoint Manager) Portalını yükleyebilirsiniz.

6. Mac Wi-Fi adresi, Intune Portalı'nın içinde görünür.

   ![Intune aracılığıyla MAC Adresi](images/mac-address-intune.jpg)

7. Teknisyen bu MAC adresini izin verilen bir cihaz olarak ekler.

### <a name="benefits"></a>Avantajlar

Bu, teknisyenin cihazı takmasına veya cihaz ortamıyla el ile etkileşim kurmasına gerek kalmadan cihazın kutudan Azure AD'ye ve Intune'a kaydolmasına olanak sağlayan bir "Tura" dağıtım deneyimi HoloLens sağlar.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>MAC adreslerini Teknisyene bildirme

### <a name="requirements"></a>Gereksinimler

- Müşteri Kiracısına karşı "Intune Graph PowerShell" yetkilendirmesi
- Teknisyenler makinesine Intune Graph PowerShell yüklemesi.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Intune'daki "Yönetilen Cihazlar" öğelerine okuma erişimi. (Yardım Masası Operatörü veya üstü ya da özel bir rol)

Şu anda, Intune'da yeni bir cihazın kaydına bağlı olarak otomasyon komutunu tetiklemenin "basit" bir yolu yoktur. Bu nedenle, bu komut teknisyene portalda oturum açmak ve el ile almak zorunda kalmadan MAC adresini almak için basit bir yol sağlar.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Bu, son 30 gün içinde HoloLens cihazların adını ve MAC adresini geri verir.

![PowerShell aracılığıyla MAC Adresi](images/mac-address-powershell.jpg)

### <a name="process"></a>İşleme

Intune kaydı tamamlandıktan sonra teknisyen, MAC adresini almak için yukarıdaki betiği çalıştırır.
