---
title: HoloLens ayarlama (1. genel)
description: bir Microsoft (MSA) veya Azure Active Directory (AAD) hesabıyla Wi-Fi ağ üzerinden ilk kez HoloLens (1. genel) ayarlamayı öğrenin.
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033625"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens ayarlama (1. genel)

HoloLens ilk kez açtığınızda cihazınızı ayarlama, cihazınızı ayarlama ve oturum açma adımları gösterilecektir.  bu makalede, HoloLens (1. gen) ilk başlatma ve kurulum deneyiminde adım adım gösterilmektedir.

sonraki bölümde, HoloLens nasıl çalışacağınızı ve hologramlar ile nasıl etkileşime gireceğini öğreneceksiniz. bu makaleye ulaşmak için bkz. [HoloLens kullanmaya başlama (1. genel)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce, aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir Wi-Fi bağlantısı**. HoloLens ayarlamak için Wi-Fi bir ağa bağlamanız gerekir. İlk kez bağlandığınızda, bir Web sitesine gidilmesini veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız vardır. [HoloLens tarafından kullanılan web siteleri hakkında daha fazla bilgi edinin](hololens-offline.md).

**Microsoft hesabı veya iş hesabı**. Ayrıca, HoloLens oturum açmak için bir Microsoft hesabı (veya kuruluşunuzun cihazın sahibi olması halinde bir iş hesabı) kullanmanız gerekir. Bir Microsoft hesabı yoksa, [account.Microsoft.com](https://account.microsoft.com) adresine gidin ve birini ücretsiz olarak ayarlayın.

**Güvenilir ve Iyi bir şekilde bir arada olan tehlikeli bir alan**. [Sistem durumu ve güvenlik bilgileri](https://go.microsoft.com/fwlink/p/?LinkId=746661).

en rahat hale getirmenize yardımcı olmak için HoloLens ile birlikte gelen **isteğe bağlı rahatlar** . [Daha fazla uyum ve rahatlık](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - HoloLens ilk kez kullandığınızda, [Cortana](hololens-cortana.md) zaten açık ve size rehberlik etmeye hazırlanıyor (cihazınızı ayarlamadan sonra sorularınıza yanıt veremeyeceksiniz). Cortana ayarlarından dilediğiniz zaman Cortana kapatabilirsiniz.
> - HoloLens çince veya japonca sürümüne geçiş yapmak için, dil için derlemeyi bir bilgisayara indirmeniz ve sonra HoloLens yüklemeniz gerekir. daha fazla bilgi için bkz. [HoloLens yerelleştirilmiş sürümlerini (1. gen) yükler](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>HoloLens 'nizi başlatın ve Windows ayarlayın

HoloLens ilk kez başlattığınızda, ilk göreviniz cihazınızda Windows Holographic ayarlaması olur.

1. internet 'e Bağlan (HoloLens Wi-Fi ağ seçeneğini seçmenizi sağlar).

1. Kullanıcı hesabınızda oturum açın. **Çalışmalarım veya okulum** arasında seçim yapın ve **bunu sahipim**.
    - **Çalışmam veya okulumu** seçtiğinizde, BIR Azure AD hesabı kullanarak oturum açın. kuruluşunuz Azure AD Premium kullanıyorsa ve otomatik mdm kaydı yapılandırmışsa, HoloLens mdm 'ye otomatik olarak kaydeder. kuruluşunuz Azure AD Premium kullanmıyorsa otomatik MDM kaydı kullanılamaz, bu yüzden [HoloLens cihaz yönetimine el ile kaydetmeniz](hololens-enroll-mdm.md#different-ways-to-enroll)gerekir. Bir iş veya okul hesabı kullanarak cihazınızda oturum açmak için şu adımları izleyin:
        1. Kurumsal hesap bilgilerinizi girin.
        1. Gizlilik bildirimini kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açın. Bu, kuruluşunuzun oturum açma sayfasına yönlendirebilir.
        1. Cihazı ayarlamaya devam edin.
    - **Sahip olduğumu** seçtiğinizde, Microsoft hesabı kullanarak oturum açabilirsiniz. kurulum tamamlandıktan sonra, [cihaz yönetimi 'ne HoloLens el ile](hololens-enroll-mdm.md#different-ways-to-enroll)kaydedebilirsiniz.
        1. Microsoft hesabı bilgilerinizi girin.
        1. Parolanızı girin. Microsoft hesabı [iki adımlı doğrulama (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa, doğrulama işlemini doldurun.

1. Cihaz, zaman diliminizi Wi-Fi ağından aldığı bilgilere göre ayarlar.

## <a name="calibration"></a>Ayarları

Cortana, herkendi kendisini tanıtdıktan sonra, sonraki kurulum adımı ayarlanır. en iyi HoloLens deneyim için kurulum sırasında ayarlama işlemini tamamlamalısınız.

HoloLens (1. gen), holograclarınızın temiz ve etkileşimli bir şekilde etkileşimde bulunmak için, pupıls (ipd veya [ınterpupilılmi](https://en.wikipedia.org/wiki/Interpupillary_distance)) arasındaki mesafeyi kullanır. IPD doğru değilse, hologramlar kararsız veya hatalı bir mesafede görünebilir.

ayarlama sırasında, HoloLens parmağınızı, her göz için bir dizi altı hedefe hizalamanızı ister. HoloLens, gözleriniz için doğru ipd 'yi ayarlamak üzere bu işlemi kullanır. Yeni Kullanıcı için ayarlama işleminin güncelleştirilmesi veya ayarlanması gerekiyorsa, Yeni Kullanıcı ayar uygulamasını kurulum dışında çalıştırabilir.

![İkinci adımda ıPD Finger hizalama ekranı.](./images/ipd-finger-alignment-300px.jpg)

*İkinci adımda ıPD Finger hizalama ekranı*

Tebrikler! Kurulum tamamlanmıştır ve HoloLens kullanmaya başlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [HoloLens kullanmaya başlayın (1. genel)](hololens1-basic-usage.md)
