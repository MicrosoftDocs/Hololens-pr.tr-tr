---
title: HoloLens BitLocker şifrelemesi
description: HoloLens karma gerçeklik cihazlarınızda depolanan dosyaları korumak için BitLocker cihaz şifrelemesini nasıl etkinleştirebileceğinizi öğrenin.
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
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378948"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. Genel) BitLocker şifrelemesi

HoloLens (1. gen) ve HoloLens 2 her ikisi de BitLocker kullanılarak cihaz şifrelemesini destekler, ancak, BitLocker her zaman HoloLens 2 ' de etkinleştirilir.

Bu makale, HoloLens 'te (1. Genel) BitLocker 'ı etkinleştirmenize ve yönetmenize yardımcı olur.

HoloLens 'te (1. Genel) BitLocker cihaz şifrelemesini el ile veya mobil cihaz yönetimi (MDM) kullanarak etkinleştirebilirsiniz. Bu yönergeleri izleyerek, HoloLens 'te depolanan dosya ve bilgileri korumak için [BitLocker cihaz şifrelemesini](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) etkinleştirin. Cihaz şifreleme, BitLocker yapılandırma hizmeti sağlayıcısı 'nda (CSP) [Encryptionmethodbydrivetype yöntemi 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ile eşdeğer olan AES-CBC 128 şifreleme yöntemini kullanarak verilerinizi korumanıza yardımcı olur. Doğru şifreleme anahtarına (parola gibi) sahip personel, şifresini çözebilir veya bir veri kurtarma işlemi gerçekleştirebilir.

## <a name="enable-device-encryption-using-mdm"></a>MDM kullanarak cihaz şifrelemesini etkinleştirme

Cihaz şifrelemesi gerektiren bir ilkeyi uygulamak için mobil cihaz yönetimi (MDM) sağlayıcınızı kullanabilirsiniz. Kullanılacak ilke, Ilke CSP 'deki [güvenlik/RequireDeviceEncryption ayarıdır](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) .

[Microsoft Intune kullanarak cihaz şifrelemesini etkinleştirme yönergelerine bakın.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Diğer MDM araçları için, yönergeler için MDM sağlayıcınızın belgelerine bakın. MDM sağlayıcınız cihaz şifreleme için özel URI gerektiriyorsa, aşağıdaki yapılandırmayı kullanın:

- **Ad**: seçtiğiniz bir ad
- **Açıklama**: isteğe bağlı
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Veri türü**: tamsayı
- **Değer**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Sağlama paketini kullanarak cihaz şifrelemesini etkinleştirme

Sağlama paketleri, belirli bir yapılandırmayı bir cihaza uygulayan Windows yapılandırma Tasarımcısı aracı tarafından oluşturulan dosyalardır. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Windows holographic sürümünü yükselten ve şifrelemeyi sağlayan bir sağlama paketi oluşturma

1. [HoloLens için bir sağlama paketi oluşturun.](hololens-provisioning.md)
1. **Çalışma zamanı ayarları**  >  **ilkeleri**  >  **güvenliği**' ne gidin ve **requiredeviceencryption**' ı seçin.

    ![Cihaz şifreleme ayarını Evet olarak yapılandırmak iste](images/device-encryption.png)

1. Ticari paketi satın aldığınızda sağlanmış olan XML lisans dosyasını bulun.

1. Ticari paketi satın aldığınızda sağlanmış olan XML Lisans dosyasına gidin ve seçin.
    > [!NOTE]
    > [Sağlama paketinde ek ayarlar](hololens-provisioning.md)yapılandırabilirsiniz.

1. **Dosya** menüsünde **Kaydet**’e tıklayın. 

1. Proje dosyalarının hassas bilgiler içerebileceğini belirten uyarıyı okuyun ve **Tamam**' ı tıklatın.

    > [!IMPORTANT]
    > Bir sağlama paketi oluşturduğunuzda, proje dosyaları ve sağlama paketi (. ppkg) dosyasına hassas bilgileri dahil edebilirsiniz. . Ppkg dosyasını şifreleme seçeneğiniz olsa da, proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamanız ve artık gerekli olmadığında proje dosyalarını silmeniz gerekir.

1. **Dışarı aktar** menüsünde, **sağlama paketi**' ne tıklayın.
1. Bu sağlama paketinin, diğer kaynaklardan bu cihaza uygulanan sağlama paketlerinden daha yüksek önceliği ayarlayabileceği **BT Yöneticisi** olarak **sahibini** değiştirin ve ardından **İleri**' yi seçin.
1. **Paket sürümü** için bir değer ayarlayın.

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilir ve sürüm numarasını daha önce uygulanan paketleri güncelleştirecek şekilde değiştirebilirsiniz.

1. **Sağlama paketinin güvenlik ayrıntılarını seçin** sayfasında **İleri**' ye tıklayın.
1. Oluşturulduktan sonra sağlama paketinin gitmesini istediğiniz çıkış konumunu belirtmek için **İleri** ' ye tıklayın. Varsayılan olarak, Windows ICD, çıkış konumu olarak proje klasörünü kullanır.

    İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için, Araştır ' ı tıklatabilirsiniz.

1. **İleri**’ye tıklayın.
1. Paketi oluşturmaya başlamak için **Oluştur** ' a tıklayın. Proje bilgileri yapı sayfasında görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.
1. Oluşturma tamamlandığında **son**' a tıklayın.

### <a name="apply-the-provisioning-package-to-hololens"></a>Hazırlama paketini HoloLens 'e Uygula

1. Cihazı USB ile BILGISAYARA bağlayın ve cihazı başlatın, ancak ilk Kurulum deneyiminin (mavi kutu ile ilk sayfa) durumunu aşan **bir sayfadan devam** etmez.
1. **Sesi** ve **Güç** düğmelerini aynı anda bir daha bas ve serbest bırakın.
1. HoloLens, BILGISAYAR üzerinde dosya Gezgini 'nde bir cihaz olarak görünür.
1. Dosya Gezgini 'nde, sağlama paketini (. ppkg) cihaz depolamasına sürükleyin ve bırakın.
1. **Sığdır** sayfasında, **birimi aşağı** ve **Güç** düğmelerine aynı anda tekrar basın ve serbest bırakın.
1. Cihaza güveniyorsanız ve uygulamayı uygulamak istiyorsanız bu cihaz sizi sorar. Pakete güvendiğinizden emin olun.
1. Paketin başarıyla uygulanıp uygulanmadığını görürsünüz. Başarısız olursa paketinizi düzelleyebilir ve yeniden deneyebilirsiniz. Başarılı olursa, cihaz kurulumuna devam edin.

> [!NOTE]
> Cihaz 2016 Ağustos 'Tan önce satın alındıysa, Microsoft hesabı cihazda oturum açmanız, en son işletim sistemi güncelleştirmesini almanız ve ardından sağlama paketini uygulamak için işletim sistemini sıfırlamanız gerekir.

## <a name="verify-device-encryption"></a>Cihaz şifrelemesini doğrulama

HoloLens üzerinde şifreleme sessiz. Cihaz şifreleme durumunu doğrulamak için:

- HoloLens 'te **Ayarlar**  >  **sistem**  >  **hakkında** bölümüne gidin. Cihaz şifrelenirse **BitLocker** **etkinleştirilir** . 

    ![BitLocker 'ın etkin olduğunu gösteren ekran hakkında](images/about-encryption.png)
