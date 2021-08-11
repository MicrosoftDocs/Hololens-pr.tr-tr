---
title: Görsel kalite ve rahatlık geliştirme
description: HoloLens cihazlarda görsellerinizin kalitesini artırmak için ınterg kızınızı (ıpd) ayarlamayı öğrenin.
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
keywords: ayarlama, rahatlık, görseller, kalite, ipd, HoloLens, Windows Mixed Reality, VR kulaklıklar
ms.openlocfilehash: 5ba00d873b8a42c3397315a62492b14ab04ded367ccdd05af8be4f68c56627e2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664804"
---
# <a name="improve-visual-quality-and-comfort"></a>Görsel kalite ve rahatlık geliştirme

HoloLens 2 ve HoloLens (1. gen), her ikisi de benzersiz gözlerinize kalibre edildiğinde daha iyi çalışır.

Her iki cihazın de en iyi hologram görüntüleme deneyimi için ayarlanması gerektiğinde, farklı ayarlama teknolojileri ve teknikleri kullanırlar.  [HoloLens 2 ayarlamaya](#calibrating-your-hololens-2) veya [HoloLens (1. gen) ayarlamaya](#calibrating-your-hololens-1st-gen)atlayın.

## <a name="calibrating-your-hololens-2"></a>HoloLens 2 ' 'nizi ayarlama

HoloLens 2, deneyiminizi geliştirmek ve sanal ortamla etkileşimde bulunmak için göz önünde bulunma teknolojisini kullanır. HoloLens 2 ' nin ayarlanması, gözlerinizin (ve cihazı kullanan başka birinin gözlerinizin) doğru bir şekilde izlenmesini sağlar. Ayrıca Kullanıcı rahatlığı, hologram hizalaması ve izleme konusunda da yardımcı olur. Ayarlandıktan sonra hologramlar, başlarınızın baş vardiyaları gibi doğru şekilde görünür.

HoloLens 2 kullanıcıdan cihazı aşağıdaki koşullarda kalibre etmesini ister:

- Kullanıcı cihazı ilk kez kullanıyor
- Kullanıcı daha önce ayarlama sürecini kabul etmedi
- Ayarlama işlemi, kullanıcının cihazı son kullandığı anda başarılı olmadı
- Kullanıcı kendi ayarlama profillerini sildi
- Cihaz kapalı duruma getirilir ve yukarıdaki durumlardan herhangi biri uygulanır 


![Gözlerinizi ayarlamak için ayarlama istemi.](./images/07-et-adjust-for-your-eyes.png)

Bu işlem sırasında, bir dizi hedefe (Gems) bakacaksınız. Ayarlama sırasında yanıp söndürmenize rağmen, odanın diğer nesneleri yerine Gems 'ye odaklanmaya çalışın.  gems 'ye odaklanma, holographic dünyasını işlemek için göz konumuyla ilgili bilgi HoloLens sağlar.

![Kalibrasyon, kullanıcıya hala kafa tutmasını ve noktalara ilişkin noktaları takip etmesini söylesin.](./images/07-et-hold-head-still.png)

![GED örneği ile ayarlama istemi.](./images/08-et-gems.png)

![Ayarlama istemi ayarlama.](./images/09-et-adjusting.png)

Ayarlama başarılı olduysa, başarılı bir ekran görürsünüz.  Aksi takdirde, [ayarlama başarısızlıklarını tanılama](hololens2-display.md#troubleshooting)hakkında daha fazla bilgi edinin.

![Ayarlama isteği başarılı.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Bir cihaz veya oturum paylaşılırken ayarlama

birden çok kullanıcı, her kişiye ait cihaz kurulumuna gerek duymadan HoloLens 2 cihazını paylaşabilir. yeni bir kullanıcı cihazı ilk kez baş üzerine yerleştiriyorsa, HoloLens 2 otomatik olarak kullanıcının görselleri kalibre etmesini ister. Daha önce kalibre edilmiş görselleri olan bir Kullanıcı cihazı baş üzerine yerleştiriyorsa, görüntü kalite ve rahat bir görüntüleme deneyimi için sorunsuz şekilde ayarlanır.  

### <a name="manually-starting-the-calibration-process"></a>Ayarlama işlemini el ile başlatma

1. [**Başlat menüsü**](hololens2-basic-usage.md#start-gesture)açmak için başlangıç hareketini kullanın.
1. Ayarlar uygulama **başlamak** için sabitlenmemişse **tüm uygulamalar**' ı seçin.
1. **Ayarlar**' yi seçin ve ardından **sistem**  >  **ayarlama**  >  **göz ayarlama**  >  **çalışma gözü ayarlaması**' nı seçin.

   ![gözle çalıştır ayarı seçeneğini gösteren Ayarlar uygulaması](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Otomatik göz konumu desteği

HoloLens 2 ' de, göz pozisyonları doğru hologram konumlandırmayı, rahat görüntüleme deneyimini ve geliştirilmiş görüntü kalitesini sağlar. Göz konumları, göz izleme hesaplamasının bir parçası olarak dahili olarak hesaplanır. Bununla birlikte, bu durum, deneyim göz önünde olmayan giriş gerektirmese de, her bir kullanıcının göz önünde geçiş ayarlaması için geçmesi gerekir.

**Otomatik göz konumu (AEP)** , bu senaryolara Kullanıcı için göz önünde bekleyen bir yol sağlar. Otomatik göz konumu, kullanıcının cihaza koyduğu andan itibaren otomatik olarak arka planda çalışmaya başlar. Kullanıcının önceki bir göz izleme ayarı yoksa, otomatik gözle, 20-30 saniyelik bir işlem zamanından sonra, ekran sistemine kullanıcının göz konumlarını sağlamaya başlayacaktır. Kullanıcı verileri cihazda kalıcı değildir ve Kullanıcı devre dışı bırakılırsa veya cihaz yeniden başlatıldığında veya uyku modundan çıktığında bu işlem yinelenir.

Kalibre edilmemiş bir Kullanıcı cihaza geçiş yaparken otomatik gözle konum özelliği olan birkaç sistem davranışı değişikliği vardır. Bu bağlamda, kalibre edilmemiş bir Kullanıcı, cihazda daha önce gelen göz izleme ayarlama işleminden geçmiş bir kişiye başvurur.

| Etkin uygulama | Önceki davranış | Windows Holographic, sürüm 20h2 güncelleştirme davranışı |
|:-------------------|:-----------------|:-----------------------------------|
| Gaze etkin olmayan uygulama veya holographic kabuğu |Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Hiçbir istem gösterilmez. |
| Etkin uygulama | Göz izleme ayarlama istemi iletişim kutusu görüntülenir. | Göz izleme ayarlama istemi yalnızca uygulama göz önünde akışa eriştiğinde görüntülenir. |

Kullanıcı, Gaze olmayan bir uygulamadan, Gaze verilerine erişen bir uygulamaya geçiş yaptığında ayarlama istemi görüntülenir. 

Geçerli kullanıcının etkin bir göz izleme ayarlaması olmadığında, diğer tüm sistem davranışları ile benzerdir. Örneğin, tek elli başlangıç hareketi etkinleştirilmez. İlk kurulum için hazır olmayan deneyimle ilgili hiçbir değişiklik olmayacaktır.

Verilerin veya kesin bir hologram konumlandırması gerektiren deneyimler için, kalibre izleme ayarlamayı çalıştırmak için kalibre edilmemiş kullanıcıları öneririz. göz izleme ayarlaması isteminden veya başlangıç menüsünden Ayarlar uygulamayı başlatarak ve ardından **sistem > ayarlama > göz ayarlama > çalıştır**' ı seçerek göz önünde erişilebilir.

#### <a name="deferred-calibration-prompt"></a>Ertelenmiş ayarlama Istemi

Otomatik gözle, göz Izleme ayarlaması istem iletişim kutusu, bir uygulama, verileri gözden kaçırana kadar ertelenir. Bu, etkin uygulama Gaze gerektirmiyorsa kullanıcıya istem olmamasını sağlar. Uygulama, verilerin Gaze olmasını gerektiriyorsa ve geçerli kullanıcı kalibre değilse, kullanıcıya bir ayarlama istemi sunulur. Bu davranış, deneyim için uygun bir zamanda göz izleme ayarlama isteğini göstermek üzere kullanılabilir. Bu yöntem aşağıdaki nedenlerle önerilir

1.  Göz Izleme ayarlaması Istem iletişim kutusu, kullanıcıya, göz izlemenin neden gerekli olduğuna ilişkin ayrıntıları sağlar.
2.  Kullanıcıya, gözlerinizin ayarlanması için bir yol sunar.

Kullanıcı, göz Izleme ayarlamasını başlatmayı seçerse, odak ayarlama tamamlandıktan sonra orijinal uygulamaya geri dönmelidir. 

### <a name="calibration-data-and-security"></a>Ayarlama verileri ve güvenliği

Ayarlama bilgileri cihazda yerel olarak depolanır ve herhangi bir hesap bilgileriyle ilişkili değildir. Cihazı ayarlama olmadan kimin kullanmışsa bir kayıt yoktur. Bu yeni kullanıcılardan, cihazı ilk kez kullandıklarında görselleri ayarlaması istenir ve daha önce ayarlamayı devre dışı bırakılmış olan kullanıcılar başarısız olur.

Cihaz, 50 ayar profilini yerel olarak saklayabilir. Bu sayıya ulaşıldığında cihaz, kullanılmamış en eski profili otomatik olarak siler.

ayar bilgileri her zaman cihazdan **Ayarlar**  >  **gizlilik**  >  **göz izleyicide** silinebilir.  

### <a name="disable-calibration"></a>Ayarlamayı devre dışı bırak

Ayrıca, aşağıdaki adımları izleyerek ayarlama isteğini devre dışı bırakabilirsiniz:

1. **Ayarlar**  >  **sistem**  >  **ayarlaması**' nı seçin.
1. **yeni bir kişi bu HoloLens kullandığında, otomatik olarak göz ayarlama özelliğini çalıştırmayı ister**.

   > [!IMPORTANT]
   > Bu ayar, hologram oluşturma kalitesini ve rahatlığını olumsuz etkileyebilir.  Bu ayarı devre dışı bırakırsanız, göz izlemeye (metin kaydırma gibi) bağlı olan özellikler artık modern uygulamalarda çalışmaz.

> [!NOTE]
> Ayarlar anahtarı, Windows Holographic, sürüm 20h2 itibarıyla [otomatik gözle, destek](hololens-release-notes.md#auto-eye-position-support)' i gözden geçirmek için kaldırılmıştır. Ayarlama istemi yalnızca kalibre edilmemiş bir Kullanıcı göz Izleme özellikli bir uygulama kullanıyorsa otomatik olarak görünür.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 göz önünde izleme teknolojisi

Cihaz, görüntü kalitesini artırmak için göz izleme teknolojisini kullanır ve tüm hologramlar 'ın 3B 'de görüntülenmesini doğru ve rahat bir şekilde konumlandırıldığından emin olmak için. Gözleri bir parça olarak kullandığından, cihaz her kullanıcı için kendisini ayarlayabilir ve kulaklık biraz daha az kullanımda kaydığı için görsellerini ayarlayabilir.  Tüm ayarlamalar el ile ayarlama gerekmeden anında gerçekleşir.
> [!NOTE]
> Göz pozisyonları sistem tarafından hesaplandığından, IPD 'nin ayarlanması HoloLens 2 için geçerli değildir.

HoloLens uygulamalar, gerçek zamanlı olarak aradığınızı izlemek için göz izlemeyi kullanır. Bu, geliştiricilerin tüm yeni bağlam, insan anlama ve holographic deneyimi kapsamındaki etkileşimleri sağlamak için kullanabileceği ana yetenektir. Geliştiricilerin bu özelliği kullanmak için herhangi bir şey yapması gerekmez.

## <a name="calibrating-your-hololens-1st-gen"></a>HoloLens ayarlama (1. genel)

HoloLens (1. gen), hologram görüntüsünü kendi [takdirine](https://en.wikipedia.org/wiki/Interpupillary_distance) (ipd) göre ayarlar. IPD doğru değilse, hologramlar kararsız şekilde veya yanlış bir mesafede görünebilir. Cihazı kendi kenetme uzaklığına (IPD) ayarlayarak görsellerinizin kalitesini artırabilirsiniz.

HoloLens (1. gen) cihazınızı ayarlarken, Cortana herkendisini tanıtdıktan sonra görsellerinizi ayarlamayı ister. Bu kurulum aşamasında ayarlama adımını doldurmanız önerilir. bununla birlikte, Cortana isteyip istemediğinizi bekleyip "atla" diyerek bunu atlayabilirsiniz.

ayarlama işlemi sırasında HoloLens, parmağınızı her göz için bir dizi altı hedefe hizalamanızı ister. HoloLens, bu işlemi, ipd 'yi gözleriniz için doğru şekilde ayarlamak üzere kullanır.

![İkinci adımda ıPD Finger hizalama ekranı](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ayarlama işlemini el ile başlatma

Ayarlamayı güncelleştirmeniz gerekiyorsa veya yeni bir kullanıcının onu ayarlaması gerekiyorsa, ayarlama uygulamasını dilediğiniz zaman el ile çalıştırabilirsiniz. Ayar uygulaması varsayılan olarak yüklenir. **başlat** menüsünü veya Ayarlar uygulamasını kullanarak bu uygulamaya erişebilirsiniz.

Ayar uygulamasını çalıştırmak için **Başlat** menüsünü kullanmak için şu adımları izleyin:

1. **Başlat** menüsünü açmak için [Bloom](hololens1-basic-usage.md) hareketini kullanın.
1. Tüm uygulamaları görüntülemek için öğesini seçin **+** .
1. **Ayarlama** seçeneğini belirleyin.

   ![Kabuktan ayarlama uygulamasına erişme](./images/calibration-shell.png)

   ![Başlatıldıktan sonra canlı küp olarak görünen ayarlama uygulaması](./images/calibration-livecube-200px.png)

Ayarlar uygulamasını kullanarak ayarlama uygulamasını çalıştırmak için aşağıdaki adımları izleyin:

1. **Başlat** menüsünü açmak için [Bloom](hololens1-basic-usage.md) hareketini kullanın.
1. **Ayarlar** **başlamak** için sabitlenmemişse, **+** tüm uygulamaları görüntülemek için seçin.
1. **Ayarlar**'ı seçin.
1. **Sistem**  >  **yardımcı programları**  >  **açma ayarlama** seçeneğini belirleyin.

   ![Ayarlar uygulamasından ayarlama uygulaması başlatılıyor](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Modern kulaklıklar

Bazı derinlikli kulaklıklar, ıPD ayarını özelleştirme olanağı sağlar. kulaklığınızın ıp 'sini değiştirmek için Ayarlar uygulamasını açın ve **karma gerçeklik**  >  **kulaklık görüntüsünü** seçin ve ardından kaydırıcı denetimini taşıyın. Değişiklikleri, kulaklığınızın gerçek zamanlı olarak görürsünüz. IPD 'nizi biliyorsanız, optometrik 'e bir ziyaretten belki de doğrudan girebilirsiniz.

ayrıca, **Ayarlar**  >  **karışık gerçeklik**  >  **kulaklık ekranı**' nı seçerek bu ayarı bilgisayarınızda ayarlayabilirsiniz.

Kulaklığınızın ıPD özelleştirmesini desteklememesi durumunda bu ayar devre dışı bırakılır.
