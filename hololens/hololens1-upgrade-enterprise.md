---
title: Windows Holographic for Business özelliklerinin kilidini aç
description: Windows Holographic for Business yükselttiğinizde, HoloLens iş için tasarlanan ek özellikler sağlar.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427653"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Windows Holographic for Business özelliklerinin kilidini aç

> [!IMPORTANT]
> bu sayfa yalnızca 1. Gen HoloLens geçerlidir.

Microsoft HoloLens, Windows Holographic (HoloLens için tasarlanan bir Windows 10 sürümü) ve [ticari paketteki](hololens-commercial-features.md), iş için tasarlanan ek özellikler sağlayan *geliştirme sürümünde* kullanılabilir.

ticari paketi satın aldığınızda, Windows Holographic for Business Windows Holographic yükselten bir lisans alırsınız. Bu lisansı, kuruluşun [mobil cihaz yönetimi (MDM) sağlayıcısını](#edition-upgrade-by-using-mdm) veya bir [sağlama paketini](#edition-upgrade-by-using-a-provisioning-package)kullanarak cihaza uygulayabilirsiniz.

> [!TIP]
> Windows 10 sürüm 1803 ' de, **Ayarlar** sistem ' i seçerek HoloLens iş sürümüne yükseltildiğini kontrol edebilirsiniz  >  .

## <a name="edition-upgrade-by-using-mdm"></a>MDM kullanarak sürüm yükseltme

Enterprise lisansı, [Windowslisanslama yapılandırma hizmeti sağlayıcısı 'nı (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)destekleyen HERHANGI bir MDM sağlayıcısı tarafından uygulanabilir. Microsoft MDM API 'sinin en son sürümü, Windowslisanslama CSP 'YI destekleyecektir.

Microsoft Intune kullanarak HoloLens yükseltmeye yönelik adım adım yönergeler için, bkz. [Windows Holographic çalıştıran cihazları Windows Holographic for Business olarak yükseltme](/intune/holographic-upgrade).

 Diğer MDM sağlayıcılarıyla, ilkeyi ayarlamaya ve dağıtmaya yönelik belirli adımlar farklılık gösterebilir.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Sağlama paketi kullanarak sürüm yükseltme

sağlama paketleri, bir cihaza belirtilen yapılandırmayı uygulayan Windows configuration Designer aracı tarafından oluşturulan dosyalardır.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Windows Holographic sürümünü yükselten bir sağlama paketi oluşturma

1. [HoloLens için bir sağlama paketi oluşturun.](hololens-provisioning.md)
1. **Çalışma zamanı ayarları**  >  **sürümyükseltmesi**' ne gidin ve **sürümupgradewithlicense**' ı seçin.

    ![Sürüm, lisans ayarı seçili olarak yükseltilir.](images/icd1.png)

1. Ticari paketi satın aldığınızda sağlanmış olan XML lisans dosyasını bulun.

    > [!NOTE]
    > [Sağlama paketinde ek ayarlar](hololens-provisioning.md)yapılandırabilirsiniz.

1. **Dosya** menüsünde **Kaydet**’i seçin. 

1. Proje dosyalarının hassas bilgileri içerebileceğini belirten uyarıyı okuyun ve **Tamam**' ı tıklatın.

    > [!IMPORTANT]
    > Bir sağlama paketi oluşturduğunuzda, proje dosyaları ve sağlama paketi (. ppkg) dosyasına hassas bilgileri dahil edebilirsiniz. . Ppkg dosyasını şifreleme seçeneğiniz olsa da, proje dosyaları şifrelenmez. Proje dosyalarını güvenli bir konumda depolamanız ve artık gerekli olmadığında proje dosyalarını silmeniz gerekir.

1. **Dışarı aktar** menüsünde, **sağlama paketi**' ni seçin.

1. Bu sağlama paketinin önceliğini, farklı kaynaklardan bu cihaza uygulanan diğerlerinden daha yüksek **olacak şekilde ayarlayan** **BT Yöneticisi** olarak değiştirin ve ardından **İleri**' yi seçin.

1. **Paket sürümü** için bir değer ayarlayın.

    > [!TIP]
    > Mevcut paketlerde değişiklik yapabilir ve sürüm numarasını daha önce uygulanan paketleri güncelleştirecek şekilde değiştirebilirsiniz.

1. **Sağlama paketinin güvenlik ayrıntılarını seçin** sayfasında **İleri**' yi seçin.

1. Oluşturulduktan sonra sağlama paketinin gitmesini istediğiniz çıkış konumunu belirtmek için **İleri ' yi** seçin. varsayılan olarak, Windows icd, çıkış konumu olarak proje klasörünü kullanır.

    İsteğe bağlı olarak, varsayılan çıkış konumunu değiştirmek için **Araştır** ' ı seçebilirsiniz.

1. **İleri**’yi seçin.

1. Paketi oluşturmaya başlamak için **Oluştur** ' u seçin. Yapı sayfasında proje bilgileri görüntülenir ve ilerleme çubuğu derleme durumunu gösterir.

1. Oluşturma tamamlandığında **son**' u seçin.

### <a name="apply-the-provisioning-package-to-hololens"></a>Sağlama paketini HoloLens Uygula

1. USB kablosunu kullanarak cihazı bir BILGISAYARA bağlayın. Cihazı başlatın, ancak ilk Kurulum deneyiminin (mavi kutu ile ilk sayfa) durumunu aşan **bir sayfadan devam** etmez. bilgisayarda, HoloLens dosya gezgini 'nde bir cihaz olarak gösterilir.

    > [!NOTE]
    > HoloLens cihaz Windows 10, sürüm 1607 veya önceki bir sürümü çalıştırıyorsa, cihaz üzerinde aynı anda ve **güç** düğmelerine kısa bir süre **sonra ve** serbest bırakarak dosya gezgini 'ni açın.

1. Dosya Gezgini 'nde, sağlama paketini (. ppkg) cihaz depolamasına sürükleyin ve bırakın.

1. HoloLens hala **sığdırma** sayfasında, **sesi** ve **güç** düğmelerini aynı anda yeniden bas ve serbest bırak.

1. HoloLens pakete güveniyorsanız ve uygulamayı uygulamak isteyip istemediğinizi sorar. Pakete güvendiğinizden emin olun.

1. Paketin başarıyla uygulanıp uygulanmadığını görürsünüz. Başarılı bir şekilde uygulanmadığından paketinizi düzelleyebilir ve yeniden deneyebilirsiniz. Başarılı olursa, cihaz kurulumuna devam edin.
