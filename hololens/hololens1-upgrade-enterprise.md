---
title: Windows Holographic for Business kilidini açma
description: Windows Holographic for Business HoloLens, iş için tasarlanmış ek özellikler sağlar.
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
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189197"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business kilidini açma

> [!IMPORTANT]
> Bu sayfa yalnızca 1. HoloLens için geçerlidir.

Microsoft HoloLens, Windows Holographic 'i (HoloLens için tasarlanmış bir Windows 10 sürümü) ve işletme için tasarlanmış ek özellikler sağlayan [Commercial Suite'te](hololens-commercial-features.md)çalışan *Geliştirme* Sürümü'ne sahiptir.

Commercial Suite'i satın aldığınız zaman Holographic'i sanal Windows yükselten bir Windows Holographic for Business. Bu lisansı, kuruluşun mobil cihaz yönetimi [(MDM)](#edition-upgrade-by-using-mdm) sağlayıcısını veya sağlama paketini kullanarak [cihaza uygulayabilirsiniz.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> Sürüm Windows 10 1803'te, HoloLens System 'i seçerek Ayarlar **sürümünün iş sürümüne yükseltil**  >  **Ayarlar.**

## <a name="edition-upgrade-by-using-mdm"></a>MDM kullanarak sürüm yükseltme

Kurumsal lisans, WindowsLicensing yapılandırma hizmet [sağlayıcısını (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)destekleyen herhangi bir MDM sağlayıcısı tarafından uygulanabilir. Microsoft MDM API'sini en son sürümü WindowsLicensing CSP'yi destekleyecektir.

Microsoft Intune kullanarak HoloLens yükseltmeye ilişkin adım adım yönergeler için bkz. [Windows Holographic](/intune/holographic-upgrade)çalıştıran cihazları Windows Holographic for Business.

 Diğer MDM sağlayıcılarda, ilkeyi ayarlamaya ve dağıtmaya yönelik belirli adımlar farklılık gösterebilir.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Sağlama paketi kullanarak sürüm yükseltmesi

Paket sağlama, Windows Yapılandırma Tasarımcısı aracı tarafından oluşturulan ve bir cihaza belirtilen yapılandırmayı uygulayan dosyalardır.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic sürümünü yükselten bir sağlama paketi oluşturma

1. [Uygulama için bir sağlama HoloLens.](hololens-provisioning.md)
1. Çalışma zamanı **ayarları**  >  **EditionUpgrade'a gidin** ve **EditionUpgradeWithLicense öğesini seçin.**

    ![Sürümü lisans ayarı seçili olarak yükseltin.](images/icd1.png)

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

### <a name="apply-the-provisioning-package-to-hololens"></a>Sağlama paketini HoloLens

1. USB kablosunu kullanarak cihazı bir bilgisayara bağlayın. Cihazı başlatın, ancak ilk kurulum deneyiminin **sığdırma** sayfasını (mavi kutuyla ilk sayfa) devam edin. Bilgisayarınızda, HoloLens cihaz olarak Dosya Gezgini.

    > [!NOTE]
    > HoloLens 1607 veya önceki bir sürümde Windows 10 çalışıyorsa, cihaz üzerinde Volume **Down** ve **Power** düğmelerine kısa bir süre basarak ve bırakarak Dosya Gezgini'i açın.

1. Bu Dosya Gezgini sağlama paketini (.ppkg) sürükleyip cihaz depolama alanına bırakın.

1. Bu HoloLens uygun **sayfadayken,** kısa bir süre için  Aşağı  Ses Düzeyi ve Güç düğmelerine tekrar basın ve bırakın.

1. HoloLens paketine güvenebilir ve uygulamak mı sorabilirsiniz. Pakete güvenen bir onaylayın.

1. Paketin başarıyla uygulanıp uygulanmadı olmadığını gösterir. Başarıyla uygulanmadı ise, paketinizi düzeltebilir ve yeniden sınabilirsiniz. Başarılı olursa, cihaz kurulumuna devam edin.
