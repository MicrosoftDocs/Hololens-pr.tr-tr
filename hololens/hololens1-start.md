---
title: Kümeyi HoloLens (1. nesil)
description: Microsoft (MSA) veya HoloLens (AAD) hesabıyla Wi-Fi ağ üzerinden ilk kez Azure Active Directory (1. nesil) ayarlamayı öğrenin.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427762"
---
# <a name="set-up-your-hololens-1st-gen"></a>Kümenizi ayarlama HoloLens (1. nesil)

Cihazlarınızı ilk kez HoloLens cihazınızı ayarlama, cihazınızı ayarlama ve oturum açma adımlarında size yol gösterir.  Bu makalede, HoloLens (1. nesil) ilk başlatma ve kurulum deneyimi adım adım açıklanmıştır.

Sonraki bölümde, çalışma ve hologramlarla etkileşim HoloLens etmeyi öğrenirsiniz. Bu makaleye atlamak için [bkz. Kullanmaya başlayın (1. nesil) ile HoloLens.](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Başlamadan önce

Başlamadan önce aşağıdakilerin kullanılabilir olduğundan emin olun:

**Bir Wi-Fi bağlantısı.** Bunu ayarlamak için HoloLens bir Wi-Fi ağına bağlamanız gerekir. İlk kez bağlanacaksanız, bir web sitesine bağlanmayı veya bağlanmak için sertifikaları kullanmayı gerektirmeyen açık veya parola korumalı bir ağa ihtiyacınız olur. [tarafından kullanan web siteleri hakkında daha HoloLens.](hololens-offline.md)

**Bir Microsoft hesabı veya iş hesabı.** Ayrıca, Microsoft hesabı'de oturum Microsoft hesabı için bir iş hesabı (veya cihazınıza sahipse bir iş hesabı) HoloLens. Henüz bir Microsoft hesabı account.microsoft.com ücretsiz olarak ayarlayın. [](https://account.microsoft.com)

**Tarak tehlikeleri olmayan güvenli, iyi bir şekilde ışık alan.** [Sağlık ve güvenlik bilgileri.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**En rahat uyuma** sahip olmak için HoloLens isteğe bağlı konfor donatıları. [Fit ve konfor hakkında daha fazla bilgi.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - HoloLens Cortana'nizi ilk kez [](hololens-cortana.md) kullanıyorsanız, Cortana zaten açık ve size yol göstermeye hazırdır (ancak siz cihazınızı ayarlayana kadar sorularınıza yanıt vere bile olmayacaktır). Bu ayarları Cortana istediğiniz zaman Cortana kapatabilirsiniz.
> - HoloLens'nin Çince veya Japonca sürümüne geçmek için, dil için derlemeyi bir bilgisayara indirmeniz ve bilgisayarınıza yüklemeniz HoloLens. Daha fazla bilgi için [bkz. Yerelleştirilmiş HoloLens yükleme (1. nesil).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Hololens'inizi başlatma ve Windows

Hizmetinizi ilk kez HoloLens, ilk göreviniz cihazınıza Holographic'Windows ayarlamaktır.

1. Bağlan bağlantısı (ağ HoloLens seçmeniz için size Wi-Fi sağlar).

1. Kullanıcı hesabınızla oturum açın. İş veya **okulum buna sahip ve sahibim** **arasında seçim.**
    - İş veya **okul sahibim'i seçtiğiniz zaman,** bir Azure AD hesabı kullanarak oturum açın. Kuruluş otomatik MDM Azure AD Premium yapılandırmışsa, MDM'HoloLens otomatik olarak kaydedilir. Otomatik MDM kaydı Azure AD Premium, bu nedenle cihaz yönetimine el ile HoloLens [gerekir.](hololens-enroll-mdm.md#different-ways-to-enroll) Bir iş veya okul hesabı kullanarak cihazda ilk kez oturum açma için şu adımları izleyin:
        1. Kuruluş hesabı bilgilerini girin.
        1. Gizlilik bildirimini kabul edin.
        1. Azure AD kimlik bilgilerinizi kullanarak oturum açma. Bu, kuruluş oturum açma sayfasına yeniden yönlendirebilirsiniz.
        1. Cihazı ayarlamaya devam edin.
    - **Sahibim'i seçerek** oturum a Microsoft hesabı. Kurulum tamamlandıktan sonra, cihaz [yönetimine HoloLens el ile kaydedebilirsiniz.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Aşağıdaki Microsoft hesabı girin.
        1. Parolanızı girin. İki adımlı Microsoft hesabı [(2FA) gerektiriyorsa](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)doğrulama işlemini tamamlar.

1. Cihaz, ağdan edinilen bilgilere göre saat diliminizi Wi-Fi ayarlar.

## <a name="calibration"></a>Kalibrasyon

Bu Cortana kendini tanıttıktan sonra, sonraki kurulum adımı ayardır. En iyi HoloLens için kurulum sırasında ayarlama işlemini tamamlamanız gerekir.

HoloLens (1. nesil), hologramların net ve etkileşim kurması kolay hale etmek için göz bebekleri arasındaki mesafeyi (IPD veya aralık [uzaklığı)](https://en.wikipedia.org/wiki/Interpupillary_distance)kullanır. IPD doğruysa hologramlar kararsız veya yanlış bir uzaklıkta görünebilir.

Ayarlama sırasında HoloLens her göz için altı hedef dizisiyle hizalamanızı isteyen bir kullanıcı vardır. HoloLens için doğru IPD'yi ayarlamak için bu işlemi kullanır. Yeni bir kullanıcı için düzeltmenin güncelleştirilmiş veya ayarlanması gerekirse, yeni kullanıcı Ayarlama uygulamasını kurulumun dışında çalıştırabilirsiniz.

![İkinci adımda IPD parmak hizalama ekranı.](./images/ipd-finger-alignment-300px.jpg)

*İkinci adımda IPD parmak hizalama ekranı*

Tebrikler! Kurulum tamamlanmıştır ve HoloLens.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Kullanmaya başlayın ile HoloLens (1. nesil)](hololens1-basic-usage.md)
