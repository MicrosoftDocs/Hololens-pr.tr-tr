---
title: Görsel kalitesini ve rahatı geliştirme
description: Farklı cihazlardaki görsellerin kalitesini artırmak için aralıklar arası mesafenizi (IPD) ayarlamayı HoloLens öğrenin.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: ayarlama, konfor, görseller, kalite, ipd, HoloLens, Windows Mixed Reality, VR başlığı
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036297"
---
# <a name="improve-visual-quality-and-comfort"></a>Görsel kalitesini ve rahatı geliştirme

HoloLens 2 ve HoloLens (1. nesil) her ikisi de benzersiz gözlere göre ayarlandıklarına göre daha iyi çalışır.

Her iki cihaz da en iyi hologram görüntüleme deneyimi için ayarlamalar yapmak zorundayken farklı ayarlama teknolojileri ve teknikleri kullanır.  [2 HoloLens veya HoloLens](#calibrating-your-hololens-2) [(1. nesil) ayarına atlayın.](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>HoloLens 2'nizi ayarlama

HoloLens 2, sanal ortamı görme ve etkileşim kurma deneyiminizi geliştirmek için göz izleme teknolojisini kullanır. 2 HoloLens 2'nin ayarlanmamış olması, cihazın sizin (ve cihazı kullanan herkesin) doğru şekilde izlemenizi sağlar. Ayrıca kullanıcı rahatı, hologram hizalaması ve el izleme ile de yardımcı olur. Ayarlamadan sonra hologramlar, kafanıza gelen güneşliği değiştirse bile doğru şekilde görünür.

HoloLens 2, bir kullanıcıdan cihazı aşağıdaki koşullarda ayarlaması istenir:

- Kullanıcı cihazı ilk kez kullanıyor
- Kullanıcı daha önce ayarlama işlemini iptal etti
- Kullanıcı cihazı son kez kullandığında ayarlama işlemi başarılı olmadı
- Kullanıcı, profillerini sildi
- Cihaz çıkarılarak tekrar üzerine alınır ve yukarıdaki koşullardan herhangi biri geçerli olur 


![Gözlere ayarlama için ayarlama istemi.](./images/07-et-adjust-for-your-eyes.png)

Bu işlem sırasında bir dizi hedefi (gem) göz atacağız. Ayarlama sırasında yanıp sönüyorsanız ama odadaki diğer nesneler yerine gem'lere odaklanmaya çalışıyorsanız sorun değil.  Gem'lere odaklanmak, HoloLens dünyanızı işlemek için göz konumunuz hakkında bilgi öğrenmenizi sağlar.

![Kullanıcıya kafalarını takip etmelerini ve noktaları gözleriyle izlemelerini söyleyen ayar istemi.](./images/07-et-hold-head-still.png)

![Gem örneğiyle birlikte ayar istemi.](./images/08-et-gems.png)

![Ayarlama istemi.](./images/09-et-adjusting.png)

Ayarlama başarılı olursa bir başarı ekranı görürsünüz.  Aksi durumunda, hata tanılama [hakkında daha fazla bilgi okuyun.](hololens2-display.md#troubleshooting)

![Ayar istemi başarılı.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Cihaz veya oturum paylaşımı sırasında ayar

Birden çok kullanıcı, her HoloLens cihaz kurulumuna gerek kalmadan bir HoloLens 2 cihazı paylaşabilir. Yeni bir kullanıcı cihazı ilk kez başına koyarsa, HoloLens 2 otomatik olarak kullanıcıdan görselleri ayarlaması istenir. Daha önce ayarlanmış görselleri olan bir kullanıcı cihazı başına koyarsa, görüntü kaliteye ve rahat bir görüntüleme deneyimine sorunsuz bir şekilde ayarlanır.  

### <a name="manually-starting-the-calibration-process"></a>Ayarlama işlemini el ile başlatma

1. başlangıç hareketini kullanarak [**Başlat menüsü.**](hololens2-basic-usage.md#start-gesture)
1. Uygulama Ayarlar sabitlenmiş değilse Tüm Uygulamalar'ı **seçin.**
1. Sistem **Ayarlar'yi** seçin ve ardından **Sistem**  >  **Ayarlama Göz Ayarlama** Çalıştırma  >  **göz**  >  **ayarı'ı seçin.**

   ![Göz Ayarlar seçeneğini gösteren bir uygulamadır.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Otomatik Göz Konumu Desteği

2 HoloLens de göz pozisyonları doğru hologram konumlandırma, rahat görüntüleme deneyimi ve gelişmiş görüntü kalitesi sağlar. Göz pozisyonları, göz izleme hesaplaması kapsamında dahili olarak hesaplanır. Ancak bu, deneyim göz bakışı girişi gerekmese bile her kullanıcının göz izleme ayarlaması izlemesini gerektirir.

**Otomatik Göz Konumu (AEP),** bu senaryoları kullanıcı için göz konumlarını hesaplamanın etkileşimsiz bir yolu ile sağlar. Otomatik Göz Konumu, kullanıcının cihaza koyan andan itibaren arka planda otomatik olarak çalışmaya başlar. Kullanıcının daha önce göz izleme ayarı yoksa Otomatik Göz Konumu, 20 -30 saniyelik bir işleme süresi sonra kullanıcının göz konumlarını görüntüleme sistemine sağlamaya başlar. Kullanıcı verileri cihazda kalıcı olmaz ve kullanıcı çıkar ve cihazı yeniden başlatırsa ya da cihaz yeniden başlatılırsa ya da uykudan çıkarsa bu işlem yinelenir.

Otomatik Göz Konumu özelliğinde, kullanıcı cihaza bağlıyken birkaç sistem davranışı değişikliği vardır. Bu bağlamda, bir kullanıcı, daha önce cihazda göz izleme ayarlama işleminin üzerinden geçilen bir kullanıcıya başvurur.

| Etkin Uygulama | Önceki Davranış | Windows Holographic sürüm 20H2 Güncelleştirmesi'nin davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Bakışın etkin olmayan uygulaması veya Holographic Shell |Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | İstem görüntülenmez. |
| Bakış özellikli uygulama | Göz izleme düzeltme istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz bakışı akışına erişdiğinde görüntülenir. |

Kullanıcı, bakış etkin olmayan bir uygulamadan bakış verilerine erişen uygulamaya geçiş olursa, ayarlama istemi görüntülenir. 

Diğer tüm sistem davranışları, geçerli kullanıcının etkin bir göz izleme cihazına sahip olmadığının benzeridir. Örneğin Tek Elle Başlatma hareketi etkinleştirilmez. İlk kurulumda İlk İlk Deneyimi'ne hiçbir değişiklik olmayacaktır.

Göz bakışı verileri veya hassas hologram konumlandırması gerektiren deneyimler için kullanıcıların göz izleme cihazı çalıştırmalarını öneririz. Bu, göz izleme isteminden veya başlangıç menüsünden Ayarlar uygulamasını başlatarak ve ardından Sistem > > Göz Ayarlaması'> Göz numarası çalıştır'ı seçerek **erişilebilir.**

#### <a name="deferred-calibration-prompt"></a>Ertelenmiş Düzeltme İstemi

Otomatik Göz Konumu ile, Bir uygulama Göz Bakışı verileri isteğinde bulunana kadar Göz İzleme Ayarlama istemi iletişim kutusu ertelenebilir. Bu, etkin uygulamanın bakış gerektirmesi gerektirdiğinde kullanıcıya sorulmaymalarını sağlar. Uygulamanın verilere bakarak bakarak ayarlaması gerekli değilse kullanıcıya bir ayarlama istemiyle başvurur. Bu davranış, deneyim için uygun bir zamanda göz izleme istemini görüntülemek için kullanılabilir. Bu yöntem aşağıdaki nedenlerden dolayı önerilir

1.  Göz İzleme Ayarlama İstemi iletişim kutusu, kullanıcıya göz izlemenin neden gerekli olduğuyla ilgili ayrıntılar sağlar.
2.  Kullanıcıya, gözü ayarlanmış şekilde reddetmek için bir yol sunar.

Kullanıcı Göz İzleme Ayarlaması'nın başlatılmasını seçerse, ayarlama tamamlandıktan sonra odak özgün uygulamaya geri dönmeli. 

### <a name="calibration-data-and-security"></a>Veri ve güvenliği ayarlama

Ayar bilgileri cihazda yerel olarak depolanır ve hiçbir hesap bilgisiyle ilişkili değildir. Cihazı kimin izinsiz kullandığına bir kayıt yoktur. Bu, yeni kullanıcılardan cihazı ilk kez kullanan görselleri ayarlamaları istenecek ve daha önce düzeltmeyi geri alan kullanıcılar veya ayarlama başarısız olmuşsa.

Cihaz en fazla 50 ayar profilini yerel olarak depolar. Bu numaraya ulaşıldıktan sonra cihaz kullanılmayan en eski profili otomatik olarak siler.

Ayar bilgileri, Gizlilik Göz izleyicisi'nin **Ayarlar**  >    >  **cihazdan silinebilir.**  

### <a name="disable-calibration"></a>Devre dışı bırakma

Ayrıca aşağıdaki adımları kullanarak da onay istemini devre dışı abilirsiniz:

1. Sistem   >  **Ayarlar'ı**  >  **seçin.**
1. Bu ayarı **kullanan yeni bir kişi HoloLens, otomatik olarak göz ayarı çalıştırmayı sorun.**

   > [!IMPORTANT]
   > Bu ayar hologram işleme kalitesini ve rahatını olumsuz etkileyebilir.  Bu ayarı kapatarak göz izleme özelliğine (metin kaydırma gibi) bağlı olan özellikler artık çevreleyici uygulamalarda çalışmaz.

> [!NOTE]
> Ayarlar anahtarı, Otomatik Göz Konumu Desteği Windows Holographic sürüm 20H2'den [itibaren kaldırılmıştır.](hololens-release-notes.md#auto-eye-position-support) İstem otomatik olarak yalnızca bir kullanıcı Göz İzleme özellikli bir uygulama kullanıyorsa görünür.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 göz izleme teknolojisi

Cihaz, görüntüleme kalitesini artırmak ve tüm hologramların doğru ve 3D görüntüye uygun şekilde konumlarını sağlamak için göz izleme teknolojisini kullanır. Göz işaretleri yer işaretleri olarak kullandığı için cihaz, her kullanıcı için kendisini ayarlayabilir ve kullanım boyunca başlığın biraz kayması nedeniyle görsellerini ayarlayabilir.  Tüm ayarlamalar, el ile ayarlamaya gerek kalmadan hemen uzabilir.
> [!NOTE]
> Göz pozisyonları sistem tarafından hesaplandıklarından, IPD ayarı Hololens 2 için geçerli değildir.

HoloLens uygulamalar, gerçek zamanlı olarak nerede arayabilirsiniz? için göz izleme kullanır. Bu, geliştiricilerin Holographic deneyiminde yepyeni bir bağlam düzeyi, insan anlayışı ve etkileşimler sağlamak için kullanabileceği ana özelliktir. Geliştiricilerin bu özelliği kullanmak için herhangi bir şey yapmaları gerek yok.

## <a name="calibrating-your-hololens-1st-gen"></a>HoloLens ayarlama (1. nesil)

HoloLens (1. nesil) hologramı, etkileşim mesafenize (IPD) [göre](https://en.wikipedia.org/wiki/Interpupillary_distance) ayarlar. IPD doğru değilse hologramlar kararsız veya yanlış bir uzaklıkta görünebilir. Cihazı etkileşim mesafenize (IPD) ayarerek görsellerin kalitesini geliştirebilirsiniz.

HoloLens (1. nesil) cihazınızı ayarlarken, yeni bir görüntü ortaya çıktıktan sonra Cortana ayarlamanızı istenir. Bu kurulum aşamasında ayarlama adımını tamamlamanız önerilir. bununla birlikte, Cortana isteyip istemediğinizi bekleyip "atla" diyerek bunu atlayabilirsiniz.

ayarlama işlemi sırasında HoloLens, parmağınızı her göz için bir dizi altı hedefe hizalamanızı ister. HoloLens, bu işlemi, ipd 'yi gözleriniz için doğru şekilde ayarlamak üzere kullanır.

![İkinci adımda ıPD Finger hizalama ekranı.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ayarlama işlemini el ile başlatma

Ayarlamayı güncelleştirmeniz gerekiyorsa veya yeni bir kullanıcının onu ayarlaması gerekiyorsa, ayarlama uygulamasını dilediğiniz zaman el ile çalıştırabilirsiniz. Ayar uygulaması varsayılan olarak yüklenir. **başlat** menüsünü veya Ayarlar uygulamasını kullanarak bu uygulamaya erişebilirsiniz.

Ayar uygulamasını çalıştırmak için **Başlat** menüsünü kullanmak için şu adımları izleyin:

1. **Başlat** menüsünü açmak için [Bloom](hololens1-basic-usage.md) hareketini kullanın.
1. Tüm uygulamaları görüntülemek için öğesini seçin **+** .
1. **Ayarlama** seçeneğini belirleyin.

   ![Kabuktan ayarlama uygulamasına erişme.](./images/calibration-shell.png)

   ![Başlatıldıktan sonra canlı küp olarak görünen ayarlama uygulaması.](./images/calibration-livecube-200px.png)

Ayarlar uygulamasını kullanarak ayarlama uygulamasını çalıştırmak için aşağıdaki adımları izleyin:

1. **Başlat** menüsünü açmak için [Bloom](hololens1-basic-usage.md) hareketini kullanın.
1. **Ayarlar** **başlamak** için sabitlenmemişse, **+** tüm uygulamaları görüntülemek için seçin.
1. **Ayarlar**'ı seçin.
1. **Sistem**  >  **yardımcı programları**  >  **açma ayarlama** seçeneğini belirleyin.

   ![Ayarlar uygulamasından ayarlama uygulaması başlatılıyor.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Modern kulaklıklar

Bazı derinlikli kulaklıklar, ıPD ayarını özelleştirme olanağı sağlar. kulaklığınızın ıp 'sini değiştirmek için Ayarlar uygulamasını açın ve **karma gerçeklik**  >  **kulaklık görüntüsünü** seçin ve ardından kaydırıcı denetimini taşıyın. Değişiklikleri, kulaklığınızın gerçek zamanlı olarak görürsünüz. IPD 'nizi biliyorsanız, optometrik 'e bir ziyaretten belki de doğrudan girebilirsiniz.

ayrıca, **Ayarlar**  >  **karışık gerçeklik**  >  **kulaklık ekranı**' nı seçerek bu ayarı bilgisayarınızda ayarlayabilirsiniz.

Kulaklığınızın ıPD özelleştirmesini desteklememesi durumunda bu ayar devre dışı bırakılır.
