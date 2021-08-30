---
title: HoloLens BitLocker Şifrelemesi
description: Karma gerçeklik cihazlarınıza depolanmış dosyaları korumak için BitLocker cihaz HoloLens etkinleştirmeyi öğrenin.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d5cf7385dd0a53c6b17f79e16364e84ab6ec867d
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189945"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. Nesil) BitLocker Şifrelemesi

HoloLens (1. nesil) ve HoloLens 2, BitLocker kullanarak cihaz şifrelemeyi destekler, ancak BitLocker her zaman HoloLens 2'de etkinleştirilir.

Bu makale, BitLocker'ı (1. nesil) HoloLens ve yönetmenize yardımcı olur.

Bu HoloLens (1. nesil) BitLocker cihaz şifrelemeyi el ile veya mobil cihaz yönetimi (MDM) kullanarak etkinleştirebilirsiniz. Dosyalarda depolanan dosyaları ve [bilgileri korumak için BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) cihaz şifrelemeyi etkinleştirmek için bu HoloLens. Cihaz şifrelemesi, BitLocker yapılandırma hizmeti sağlayıcısında (CSP) [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) yöntemine eşdeğer olan AES-CBC 128 şifreleme yöntemini kullanarak verilerinizin korunmasına yardımcı olur. Doğru şifreleme anahtarına (parola gibi) sahip personel şifresini çözebilir veya bir veri kurtarma işlemi gerçekleştirebilirsiniz.

## <a name="enable-device-encryption-using-mdm"></a>MDM kullanarak cihaz şifrelemeyi etkinleştirme

Cihaz şifrelemesi gerektiren bir Cihaz Yönetimi uygulamak için Mobile Cihaz Yönetimi (MDM) sağlayıcınızı kullanabilirsiniz. Bu ilke, İlke [CSP'sinde Güvenlik/GerekliYönetkenEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) ayarıdır.

[Microsoft Intune kullanarak cihaz şifrelemesini etkinleştirme yönergelerine bakın.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Diğer MDM araçları için yönergeler için MDM sağlayıcınızın belgelerine bakın. MDM sağlayıcınız cihaz şifrelemesi için özel URI gerektiriyorsa aşağıdaki yapılandırmayı kullanın:

- **Ad:** istediğiniz bir ad
- **Açıklama:** isteğe bağlı
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Veri türü:** tamsayı
- **Değer:**`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Sağlama paketi kullanarak cihaz şifrelemeyi etkinleştirme

Paket sağlama, Windows Yapılandırma Tasarımcısı aracı tarafından oluşturulan ve bir cihaza belirtilen yapılandırmayı uygulayan dosyalardır. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Windows Holographic sürümünü yükselten ve şifrelemeyi sağlayan bir sağlama paketi oluşturma

1. [Uygulama için bir sağlama HoloLens.](hololens-provisioning.md)
1. Çalışma zamanı **ayarları**  >  **İlkeler**  >  **Güvenliği'ne** gidin ve **GerekliCimaCip Şifrele'yi seçin.**

    ![Cihaz şifreleme ayarının evet olarak yapılandırılması gerektir.](images/device-encryption.png)

1. Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasını bulun.

1. Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasına göz atabilir ve dosyayı seçin.
    > [!NOTE]
    > Sağlama [paketinde ek ayarları yapılandırabilirsiniz.](hololens-provisioning.md)

1. **Dosya** menüsünde **Kaydet**’e tıklayın. 

1. Proje dosyalarının hassas bilgiler içerenin açık olduğu uyarıyı okuyun ve Tamam'a **tıklayın.**

    > [!IMPORTANT]
    > Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir. .ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.

1. Dışarı Aktar **menüsünde** Sağlama **paketi'ne tıklayın.**
1. **Sahip'i** **IT Yöneticisi** olarak değiştirerek bu sağlama paketinin önceliğe diğer kaynaklardan bu cihaza uygulanan paket sağlamadan daha yüksek bir öncelik ayarlayın ve ardından Sonraki'yi **seçin.**
1. Paket Sürümü için **bir değer ayarlayın.**

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilirsiniz ve sürüm numarasını, daha önce uygulanan paketleri güncelleştirmek için değiştirebilirsiniz.

1. Sağlama **paketi için güvenlik ayrıntılarını seçin'de, Sonraki**'ye **tıklayın.**
1. Hazır **olduktan** sonra sağlama paketinin gitmelerini istediğiniz çıkış konumunu belirtmek için, Sonraki'ye tıklayın. Varsayılan olarak, Windows ICD proje klasörünü çıkış konumu olarak kullanır.

    İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için Gözat'a tıkabilirsiniz.

1. **İleri**’ye tıklayın.
1. Paketi **derlemeye** başlamak için Derleme'ye tıklayın. Proje bilgileri derleme sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.
1. Derleme tamamlandığında Son'a **tıklayın.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Sağlama paketini HoloLens

1. Bağlan USB aracılığıyla bir bilgisayara bağlayın ve cihazı başlatın, ancak ilk  kurulum deneyiminin sığdırma sayfasını (mavi kutuyla ilk sayfa) geçe devam edin.
1. Ses Düzeyi Kapalı ve Güç **düğmelerine aynı anda** **kısa bir süre basın** ve bırakın.
1. HoloLens, pc'de bir Dosya Gezgini olarak gösterir.
1. Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.
1. Sığdırma sayfasındayken Ses **Düzeyi Kapalı ve** Güç **düğmelerine** tekrar kısa bir süre basın **ve bırakın.**
1. Cihaz, pakete güvenmiyorsanız ve bunu uygulamak mı isteyebilirsiniz? Pakete güvenen bir onaylayın.
1. Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir. Başarısız olursa, paketinizi düzeltebilir ve yeniden sınabilirsiniz. Başarılı olursa cihaz kurulumuna devam edin.

> [!NOTE]
> Cihaz Ağustos 2016'dan önce satın alındı ise cihazda Microsoft hesabı ile oturum açmanız, en son işletim sistemi güncelleştirmesini almanız ve sağlama paketini uygulamak için işletim sistemi sıfırlamanız gerekir.

## <a name="verify-device-encryption"></a>Cihaz şifrelemeyi doğrulama

Şifreleme, veri HoloLens. Cihaz şifreleme durumunu doğrulamak için:

- Bu HoloLens Sistem **Hakkında'Ayarlar**  >    >  **gidin.** Cihaz **şifrelenirse** **BitLocker** etkinleştirilir. 

    ![BitLocker'ın etkin olduğunu gösteren ekran hakkında.](images/about-encryption.png)
