---
title: Windows Holographic for Business kilidini açma
description: Yeni sürüme Windows Holographic for Business, HoloLens iş için tasarlanmış ek özellikler sağlar.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379052"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business kilidini açma

> [!IMPORTANT]
> Bu sayfa yalnızca HoloLens 1. Nesil için geçerlidir.

Microsoft HoloLens, Windows Holographic (HoloLens için tasarlanmış bir Windows 10 sürümü) ve iş için tasarlanmış ek özellikler sağlayan [Commercial Suite'te](hololens-commercial-features.md)çalışan Development *Edition'da* kullanılabilir.

Commercial Suite'i satın aldığınız zaman, Windows Holographic'i sanal Windows Holographic for Business. Bu lisansı, kuruluşun mobil cihaz yönetimi [(MDM)](#edition-upgrade-by-using-mdm) sağlayıcısını veya sağlama paketini kullanarak [cihaza uygulayabilirsiniz.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> Sürüm Windows 10 1803'te Ayarlar Sistemi'ne bakarak HoloLens'in iş sürümüne yükseltildikten sonra bunu **kontrol**  >  **edebilirsiniz.**

## <a name="edition-upgrade-by-using-mdm"></a>MDM kullanarak sürüm yükseltme

Kurumsal lisans, WindowsLicensing yapılandırma hizmet [sağlayıcısını (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)destekleyen herhangi bir MDM sağlayıcısı tarafından uygulanabilir. Microsoft MDM API'sini en son sürümü WindowsLicensing CSP'yi destekleyecektir.

Microsoft Intune kullanarak HoloLens'i yükseltmeye ilişkin adım adım yönergeler için bkz. [Windows Holographic](https://docs.microsoft.com/intune/holographic-upgrade)çalıştıran cihazları Windows Holographic for Business.

 Diğer MDM sağlayıcılarda, ilkeyi ayarlamaya ve dağıtmaya yönelik belirli adımlar farklılık gösterebilir.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Sağlama paketi kullanarak sürüm yükseltmesi

Paket sağlama, Windows Yapılandırma Tasarımcısı aracı tarafından oluşturulan ve bir cihaza belirtilen yapılandırmayı uygulayan dosyalardır.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic sürümünü yükselten bir sağlama paketi oluşturma

1. [HoloLens için bir sağlama paketi oluşturun.](hololens-provisioning.md)
1. Çalışma zamanı **ayarları**  >  **EditionUpgrade'a gidin** ve **EditionUpgradeWithLicense öğesini seçin.**

    ![Sürümü lisans ayarı seçili olarak yükseltin](images/icd1.png)

1. Commercial Suite'i satın aldığınız zaman sağlanan XML lisans dosyasını bulun.

    > [!NOTE]
    > Sağlama [paketinde ek ayarları yapılandırabilirsiniz.](hololens-provisioning.md)

1. **Dosya** menüsünde **Kaydet**’i seçin. 

1. Proje dosyalarının hassas bilgiler içerene ilişkin uyarıyı okuyun ve Tamam'a **tıklayın.**

    > [!IMPORTANT]
    > Bir sağlama paketi derlemek için proje dosyalarına ve sağlama paketi (.ppkg) dosyasına hassas bilgiler dahildir. .ppkg dosyasını şifreleme seçeneğiniz olsa da proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamalı ve artık gerekli olmadığı zaman proje dosyalarını silebilirsiniz.

1. Dışarı Aktar **menüsünde** Sağlama **paketi'ne tıklayın.**

1. **Sahip'i** **IT Yöneticisi** olarak değiştirerek bu sağlama paketinin öncelisini bu cihaza farklı kaynaklardan uygulanan diğer kaynaklardan daha yüksek olacak şekilde ayarlar ve ardından Sonraki'yi **seçin.**

1. Paket Sürümü için **bir değer ayarlayın.**

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilirsiniz ve sürüm numarasını, daha önce uygulanan paketleri güncelleştirmek için değiştirebilirsiniz.

1. Sağlama **paketi için güvenlik ayrıntılarını seçin'de, Sonraki'yi** **seçin.**

1. Hazır **olduktan** sonra sağlama paketinin gitmelerini istediğiniz çıkış konumunu belirtmek için Sonraki'yi seçin. Varsayılan olarak, Windows ICD proje klasörünü çıkış konumu olarak kullanır.

    İsteğe bağlı olarak, varsayılan çıkış **konumunu** değiştirmek için Gözat'ı seçin.

1. **İleri**’yi seçin.

1. Paketi **derlemeye** başlamak için Derleme'yi seçin. Derleme sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

1. Derleme tamamlandığında Son'a **seçin.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Sağlama paketini HoloLens'e uygulama

1. USB kablosunu kullanarak cihazı bir bilgisayara bağlayın. Cihazı başlatın, ancak ilk kurulum deneyiminin **sığdırma** sayfasını (mavi kutuyla ilk sayfa) devam edin. HoloLens, bilgisayarınızda cihaz olarak Dosya Gezgini.

    > [!NOTE]
    > HoloLens cihazı Windows 10, sürüm 1607 veya önceki bir sürümde çalışıyorsa, cihazda Volume **Down** ve **Power** düğmelerine kısa bir süre basarak ve bırakarak Dosya Gezgini'i açın.

1. Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.

1. HoloLens hala uygun **sayfadayken,** kısa bir süre için Volume Down ve **Power** **düğmelerine tekrar** basın ve bırakın.

1. HoloLens, pakete güvenmiyorsanız ve bunu uygulamak mı? Pakete güvenen bir onaylayın.

1. Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir. Başarıyla uygulanmadı ise, paketinizi düzeltebilir ve yeniden sınabilirsiniz. Başarılı olursa, cihaz kurulumuna devam edin.
