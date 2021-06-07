---
title: HoloLens ayarlama (1. Genel)
description: Microsoft (MSA) veya Azure Active Directory (AAD) hesabıyla Wi-Fi ağı üzerinden ilk kez HoloLens 'nizi (1. gen) ayarlamayı öğrenin.
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379023"
---
# <a name="set-up-your-hololens-1st-gen"></a>HoloLens 'nizi ayarlama (1. Genel)

HoloLens 'i ilk kez açtığınızda, cihazınızı ayarlama, cihazınızı ayarlama ve oturum açma adımları gösterilecektir.  Bu makalede, HoloLens (1. Genel) ilk başlatma ve kurulum deneyiminde izlenecek yol gösterilmektedir.

Sonraki bölümde, HoloLens ile çalışmayı ve hologramlar ile nasıl etkileşim kuracağınızı öğreneceksiniz. Bu makaleye devam etmek için bkz. [HoloLens ile çalışmaya başlama (1. Genel)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce, aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir Wi-Fi bağlantısı**. HoloLens 'nizi ayarlamak için bir Wi-Fi ağa bağlamanız gerekir. İlk kez bağlandığınızda, bir Web sitesine gidilmesini veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız vardır. [HoloLens 'in kullandığı Web siteleri hakkında daha fazla bilgi edinin](hololens-offline.md).

**Microsoft hesabı veya iş hesabı**. Ayrıca, HoloLens 'te oturum açmak için bir Microsoft hesabı (veya kuruluşunuzun cihazın sahibi olması halinde bir iş hesabı) kullanmanız gerekir. Bir Microsoft hesabı yoksa, [account.Microsoft.com](https://account.microsoft.com) adresine gidin ve birini ücretsiz olarak ayarlayın.

**Güvenilir ve Iyi bir şekilde bir arada olan tehlikeli bir alan**. [Sistem durumu ve güvenlik bilgileri](https://go.microsoft.com/fwlink/p/?LinkId=746661).

En rahat hale getirmenize yardımcı olmak için HoloLens 'nizle birlikte gelen **isteğe bağlı rahatlar** . [Daha fazla uyum ve rahatlık](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - HoloLens 'i ilk kez kullandığınızda [Cortana](hololens-cortana.md) zaten açık durumdadır ve size rehberlik etmeye hazırlanıyor (cihazınızı ayarlamadan sonra sorularınıza yanıt veremeyeceksiniz). Cortana 'nın ayarlarından herhangi bir zamanda Cortana 'yı kapatabilirsiniz.
> - HoloLens 'in Çince veya Japonca sürümüne geçiş yapmak için, dil için derlemeyi bir BILGISAYARA indirmeniz ve sonra HoloLens 'te yüklemeniz gerekir. Daha fazla bilgi için bkz. [HoloLens 'in yerelleştirilmiş sürümlerini (1. gen) yükler](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>HoloLens 'nizi başlatın ve Windows kurulumunu yapın

HoloLens 'i ilk kez başlattığınızda, ilk göreviniz cihazınızda Windows holographic 'ı kurmak olur.

1. İnternet 'e bağlanın (HoloLens, Wi-Fi ağı seçmek için sizi yönlendirir).

1. Kullanıcı hesabınızda oturum açın. **Çalışmalarım veya okulum** arasında seçim yapın ve **bunu sahipim**.
    - **Çalışmam veya okulumu** seçtiğinizde, BIR Azure AD hesabı kullanarak oturum açın. Kuruluşunuz Azure AD Premium kullanıyorsa ve otomatik MDM kaydı yapılandırmışsa, HoloLens MDM 'ye otomatik olarak kaydolur. Kuruluşunuz Azure AD Premium kullanmıyorsa otomatik MDM kaydı kullanılamaz, bu yüzden [HoloLens 'i cihaz yönetimine el ile kaydetmeniz](hololens-enroll-mdm.md#different-ways-to-enroll)gerekir. Bir iş veya okul hesabı kullanarak cihazınızda oturum açmak için şu adımları izleyin:
        1. Kurumsal hesap bilgilerinizi girin.
        1. Gizlilik bildirimini kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açın. Bu, kuruluşunuzun oturum açma sayfasına yönlendirebilir.
        1. Cihazı ayarlamaya devam edin.
    - **Sahip olduğumu** seçtiğinizde, Microsoft hesabı kullanarak oturum açabilirsiniz. Kurulum tamamlandıktan sonra, [HoloLens 'i cihaz yönetimine el ile](hololens-enroll-mdm.md#different-ways-to-enroll)kaydedebilirsiniz.
        1. Microsoft hesabı bilgilerinizi girin.
        1. Parolanızı girin. Microsoft hesabı [iki adımlı doğrulama (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)gerektiriyorsa, doğrulama işlemini doldurun.

1. Cihaz, zaman diliminizi Wi-Fi ağından aldığı bilgilere göre ayarlar.

## <a name="calibration"></a>Ayarları

Cortana, herkendi kendini tanıdıktan sonra, sonraki kurulum adımı kalibbdır. En iyi HoloLens deneyimi için kurulum sırasında ayarlama işlemini tamamlamalısınız.

HoloLens (1. gen), holograclarınızın temiz ve etkileşimli olarak kullanılabilmesini sağlamak için, pupıls (IPD veya [ınterpupilılmi](https://en.wikipedia.org/wiki/Interpupillary_distance)) arasındaki mesafeyi kullanır. IPD doğru değilse, hologramlar kararsız veya hatalı bir mesafede görünebilir.

Ayarlama sırasında, HoloLens, parmağınızı her göz için bir dizi altı hedefe hizalamanızı ister. HoloLens, gözleriniz için doğru IPD 'yi ayarlamak için bu işlemi kullanır. Yeni Kullanıcı için ayarlama işleminin güncelleştirilmesi veya ayarlanması gerekiyorsa, Yeni Kullanıcı ayar uygulamasını kurulum dışında çalıştırabilir.

![İkinci adımda ıPD Finger hizalama ekranı](./images/ipd-finger-alignment-300px.jpg)

*İkinci adımda ıPD Finger hizalama ekranı*

Tebrikler! Kurulum tamamlanmıştır ve HoloLens kullanmaya başlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [HoloLens ile çalışmaya başlama (1. Genel)](hololens1-basic-usage.md)
