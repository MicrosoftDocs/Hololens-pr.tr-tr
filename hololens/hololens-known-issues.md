---
title: HoloLens için bilinen sorunlar (1. genel)
description: Unity ve Windows cihaz portalını kullanan HoloLens müşterileri ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemize ilişkin güncel tutun.
keywords: sorun giderme, bilinen sorun, yardım
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033084"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens için bilinen sorunlar (1. genel)

HoloLens cihazlar için bilinen sorunların güncel listesi aşağıda verilmiştir. Tek bir davranış görüyorsanız, önce burayı işaretleyin. bu liste, yeni sorunlar keşfedildiğinde veya raporlanacağı ya da sorunlar gelecekte HoloLens yazılım güncelleştirmelerinde giderildiği için güncelleştirilir.

>[!NOTE]
> - bunu engellemeyen bir sorun keşfettiğiniz takdirde, lütfen [geri bildirim merkezi](hololens-feedback.md)aracılığıyla HoloLens cihazınızda bildirin.
> - Karşılaştığınız sorun sizi engelliyorsa, geri bildirimde bulunmak için lütfen [bir destek isteği](https://aka.ms/hlsupport)gönderin.


- [tüm HoloLens oluşumlara yönelik bilinen sorunlar](#known-issues-for-all-hololens-generations)
- [HoloLens için bilinen sorunlar (1. genel)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>tüm HoloLens oluşumlara yönelik bilinen sorunlar

### <a name="unity"></a>Unity

- HoloLens geliştirme için önerilen en güncel Unity sürümü için [araçları yüklemeyi](/windows/mixed-reality/install-the-tools) inceleyin.
- unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında](https://forum.unity3d.com/threads/known-issues.394627/)belgelenmiştir.

### <a name="windows-device-portal"></a>Windows Cihaz portalı

- Karma Gerçeklik yakalamadaki canlı önizleme özelliği birkaç saniye gecikme gösterebilir.

- Sanal giriş sayfasında, sanal hareketler bölümünün altındaki hareket ve kaydırma denetimleri işlevsel değildir. Bunların kullanılması hiçbir etkiye sahip olmayacaktır. Sanal giriş sayfasındaki sanal klavye düzgün şekilde çalışmaktadır.

- Ayarlar geliştirici modunu etkinleştirdikten sonra, cihaz portalını açmak için anahtarın etkinleştirilmesi birkaç saniye sürebilir.

### <a name="onedrive-camera-upload"></a>kamera karşıya yükleme OneDrive

HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.

Geçici çözümler:

- İşletmeniz için uygun ise, tüketici Microsoft hesaplarında otomatik kamera yüklemesi desteklenir. iş veya okul hesabınıza ek olarak Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama, çift oturum açma desteği sağlar). OneDrive içindeki Microsoft hesabı profilinizde otomatik, arka planda kamera alma 'yı yükleyebilirsiniz.

- fotoğraflarınızı otomatik olarak yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanmıyorsanız, OneDrive uygulamasından iş veya okul hesabınıza fotoğraf el ile yükleyebilirsiniz. bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızda oturum açtığınızdan emin olun. Düğmesini seçin **+** ve **upload**' yi seçin. **Kamera rulosu > resimlere** giderek karşıya yüklemek istediğiniz fotoğrafları veya videoları bulun. Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından **Aç** düğmesini seçin.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens için bilinen sorunlar (1. genel)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Visual Studio üzerinden HoloLens bağlanamaz ve dağıtım yapılamıyor

> [!NOTE]
> son güncelleştirme: 8/8 @ 5:11pm-Visual Studio, bu soruna yönelik bir çözüm içeren VS 2019 sürüm 16,2 ' i yayımladı. Bu hatayı kullanmaktan kaçınmak için bu en yeni sürüme güncelleştirmenizi öneririz.

Visual Studio, bu soruna yönelik bir çözüm içeren VS 2019 sürüm 16,2 ' i yayımladı. Bu hatayı kullanmaktan kaçınmak için bu en yeni sürüme güncelleştirmenizi öneririz.

sorun kök-nedeni: HoloLens uygulamaları dağıtmak ve bunlara hata ayıklamak için Visual Studio 2017 ' nin Visual Studio 2015 veya sonraki sürümlerini kullanan kullanıcılar ve daha sonra Visual Studio 2017 ' ın en son sürümlerini ve Visual Studio 2019 ile aynı HoloLens etkilenir. Visual Studio yeni sürümleri, bir bileşenin yeni bir sürümünü dağıtmaktadır, ancak eski sürümdeki dosyalar cihazda bırakılır, bu da yeni sürümün başarısız olmasına neden olur.  Bu, şu hata iletisine neden olur: DEP0100: hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun. 80004005 hatası nedeniyle bir geliştirici lisansı alınamadı \<ip\> .

#### <a name="workaround"></a>Geçici çözüm

Ekibimiz şu anda bir çözüm üzerinde çalışıyor. Bu sırada, soruna geçici bir çözüm bulmak için aşağıdaki adımları kullanabilir ve dağıtımın ve hata ayıklamanın engellemesini kaldırabilirsiniz:  

1. Visual Studio'yu açın.

1. **dosya**  >  **yeni**  >  **Project** seçin.

1. **Visual C#**  >  **Windows masaüstü**  >  **konsol uygulaması (.NET Framework)** seçeneğini belirleyin.

1. projeye bir ad verin (örneğin, "holomersdeploymentdüzeltmesini") ve Framework 'ün en az .NET Framework 4,5 ' e ayarlandığından emin olun ve ardından **tamam**' ı seçin.

1. Çözüm Gezgini ' deki **Başvurular** düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin ( **Gözden** geçirme bölümüne ve sonra da **gözatatıon**' ı seçin):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 yüklü değilse, en son sürümü kullanın.

1. Çözüm Gezgini projede projeye sağ tıklayın ve   >  **var olan öğe** Ekle ' yi seçin.

1. C:\Program Files (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 konumuna gidin ve filtreyi **tüm dosyalar ( \* . \* )** olarak değiştirin.

1. SirepClient.dll ve SshClient.dll her ikisini de seçin ve **Ekle**' yi seçin.

1. Çözüm Gezgini her iki dosyayı da bulun ve seçin (dosyalar listesinin en altında olmaları gerekir) ve **her zaman kopyalamak** için **Özellikler** penceresinde **Çıkış Dizinine Kopyala** ' yı değiştirin.

1. Dosyanın üst kısmında, mevcut deyimler listesine aşağıdakileri ekleyin `using` :

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. İçinde `static void Main(...)` , aşağıdaki kodu ekleyin:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Yapı   >  **Yapı çözümünü** seçin.

1. Derlenmiş .exe dosyasını içeren klasöre bir komut Istemi penceresi ve CD açın (örneğin, C:\myprojeler\windows Holomersdeploymentfix\bin\debug).

1. Yürütülebilir dosyayı çalıştırın ve bir komut satırı bağımsız değişkeni olarak cihazın IP adresini sağlayın. (USB kullanarak bağlıysanız 127.0.0.1 kullanabilirsiniz, aksi takdirde cihazın Wi-Fi IP adresini kullanamazsınız.)  Örneğin, "Holomersdeploymentdüzeltmesini 127.0.0.1".

1. araç herhangi bir ileti olmadan çıktıktan sonra (bu yalnızca birkaç saniye sürer), artık Visual Studio 2017 veya daha yeni bir sürümü dağıtabilir ve hata ayıklaması yapabileceksiniz.  Aracın devam eden kullanımı gerekli değildir.

Kullanılabilir hale geldiğinde daha fazla güncelleştirme sağlayacağız.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens üzerinde Microsoft Store ve uygulamaları başlatan sorunlar

> [!NOTE]
> Son güncelleştirme: 4/2 @ 10-sorun çözüldü.

HoloLens üzerinde Microsoft Store ve uygulamaları başlatmaya çalışırken sorunlarla karşılaşabilirsiniz. Arka plan uygulama güncelleştirmeleri, bir veya daha fazla bağımlı uygulama çalışmaya devam ederken belirli bir sırada çerçeve paketlerinin daha yeni bir sürümünü dağıtırken sorunun oluştuğunu belirledik. bu durumda, bir otomatik uygulama güncelleştirmesi .NET Native framework 'ün yeni bir sürümünü (sürüm 10.0.25531 ile 10.0.27413) dağıttığı, çalışan uygulamaların, Framework 'ün önceki sürümünü kullanan tüm çalışan uygulamalar için düzgün şekilde güncelleştirileceğinden oluşur.  Çerçeve güncelleştirmesi için akış aşağıdaki gibidir:

1. Yeni çerçeve paketi mağazadan indirilir ve yüklenir.

1. Eski Framework kullanan tüm uygulamalar, daha yeni sürümü kullanmak için ' güncelleştirildi '.

2. adım tamamlanmadan önce kesintiye uğrarsa, daha yeni Framework 'ün kaydolmadığı tüm uygulamalar Başlangıç menüsünden başlayamaz.  HoloLens üzerinde herhangi bir uygulamanın bu sorundan etkilendiğine inandık.

Bazı kullanıcılar, askıda olan uygulamaları kapatan ve geri bildirim merkezi gibi diğer uygulamaları başlatan rapor verdi, 3B görüntüleyici veya fotoğraflar bu sorunu çözer. ancak, bu sürenin %100 ' i çalışmaz.

kök sunuyoruz, bu sorunun güncelleştirmenin kendisinin neden olmadığı, ancak işletim sisteminde .NET Native framework güncelleştirmesiyle yanlış işlenmekte olan bir hata oluştu. Bir onarım belirlediğimiz ve bu güncelleştirmeyi içeren bir güncelleştirme (OS sürüm 17763,380) yayımladığımızda duyurmaktan memnuniyet duyuyoruz.  

Cihazınızın güncelleştirmeyi alıp almaz:

1. Ayarlar uygulamasına gidin ve **güncelleştirme & güvenlik**' i açın.

1. **Güncelleştirmeleri denetle**' yi seçin.

1. 17763,380 güncelleştirmesi varsa, uygulama askıda kalma hatasına yönelik çözümü almak için lütfen bu yapıya güncelleştirin.

1. İşletim sisteminin bu sürümüne güncelleştirme yapıldığında uygulamalar beklendiği gibi çalışmalıdır.

ayrıca, her HoloLens işletim sistemi sürümünde yaptığımız gibi, [Microsoft indirme merkezi](https://aka.ms/hololensdownload/10.0.17763.380)'ne ffu görüntüsünü naklettik.

güncelleştirmeyi yapmak istemiyorsanız, 3/29 itibariyle Microsoft Store UWP uygulamasının yeni bir sürümünü yayımladık. Mağaza 'nın güncelleştirilmiş sürümüne sahip olduktan sonra:

1. Mağazayı açın ve yüklendiğini onaylayın.
1. Menüyü açmak için Bloom hareketini kullanın.
1. Daha önce bozulan uygulamaları açmayı deneyin.
1. Hala başlatılamaz, bozuk uygulamanın simgesine dokunup basılı tutun ve Kaldır ' ı seçin.
1. Bu uygulamaları mağazadan yeniden yükleyin.

cihazınız hala uygulama yükleyeerişemiyorsanız, aşağıdaki adımları izleyerek .NET Native Framework ve çalışma zamanının bir sürümünü indirme merkezi aracılığıyla dışarıdan yükleyebilirsiniz:

1. Lütfen [Bu zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi ' nden indirin. Unzippıng iki dosya oluşturur.  Microsoft. NET. Native. Runtime. 1.7. appx ve Microsoft. NET. Native. Framework. 1.7. appx.

1. Lütfen cihazınızın dev olarak kilidinin açık olduğundan emin olun.  daha önce yapmadıysanız yönergeler için [Windows cihaz portalını kullanma](/windows/mixed-reality/using-the-windows-device-portal) konusuna bakın.

1. daha sonra Windows cihaz portalına ulaşmak istiyorsunuz. Önerimiz bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak yapmanız gerekir http://127.0.0.1:10080 .

1. cihaz portalını Windows aldıktan sonra, indirdiğiniz iki dosyayı "dışarıdan yükleme" yapmanız gerekir. Bunu yapmak için, **uygulamalar** bölümüne ulaşana ve **uygulamalar**' ı seçene kadar sol taraftaki çubuğa gitmeniz gerekir.

1. Ardından aşağıdakine benzer bir ekran görürsünüz.  **Uygulamayı yüklemeyi** belirten bölüme gitmek ve bu iki appx dosyasının sıkıştırılanmasını nereden kaldırıtabileceğiniz konusunda gezinmek istiyorsunuz. Tek seferde yalnızca bir tane yapabilirsiniz, ilk olanı seçtikten sonra dağıt bölümünde "git" düğmesine tıklayın. İkinci APPX dosyası için bunu yapın.

   ![Windows Side-Loaded uygulamasını yüklemek için cihaz portalı.](images/20190322-DevicePortal.png)

1. Bu noktada, uygulamalarınızın yeniden çalışmaya başlaması ve mağazaya de başlayabilmeniz gerektiğini düşünüyoruz.

1. Bazı durumlarda, etkilenen uygulamaların başlatılması için önce 3B görüntüleyici uygulamasını başlatma ek adımını çalıştırmanız gerekir.

Bu sorunu çözmemiz için işlem boyunca yaptığımız ve başarılı karma gerçeklik deneyimleri oluşturmak için Topluluğumuzdan çalışmaya devam ediyoruz.

### <a name="device-update"></a>Cihaz Güncelleştirmesi

- 30 saniye yeni bir güncelleştirmeden sonra kabuk bir kez kaybolabilir. Oturumunuzu sürdürmeniz için lütfen **Bloom** hareketini gerçekleştirin.

### <a name="visual-studio"></a>Visual Studio

- HoloLens geliştirme için önerilen Visual Studio en güncel sürümü için bkz. [araçları kurma](/windows/mixed-reality/install-the-tools) .

- HoloLens Visual Studio bir uygulama dağıttığınızda, şu hatayı görebilirsiniz: **istenen işlem, kullanıcı eşlemeli bir bölümün açık olduğu bir dosya üzerinde gerçekleştirilemiyor. (HRESULT özel durumu: 0x800704C8)**. Bu durumda yeniden deneyin ve dağıtımınız genellikle başarılı olur.

### <a name="api"></a>API

- Uygulama, [odak noktasını](/windows/mixed-reality/focus-point-in-unity) kullanıcının arkasında veya normal olarak kameraya ayarlarsa, hologramlar karma gerçeklik yakalama fotoğraflarında veya videolarında görünmez. bu hata Windows düzeltilene kadar, uygulamalar odak noktasını etkin bir şekilde ayarladıklarında, [düzlemin](/windows/mixed-reality/focus-point-in-unity) normal şekilde ters kamera (örneğin, normal =-kamera. ileri) olarak ayarlandığından emin olunması gerekir.

### <a name="xbox-wireless-controller"></a>Xbox Kablosuz denetleyicisi

- Xbox Kablosuz denetleyicisi, HoloLens ile kullanılmadan önce güncelleştirilmeleri gerekir. Denetleyicinizi bir HoloLens eşleştirmeye [çalışmadan önce güncel olduğunuzdan emin](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) olun.

- Xbox kablosuz denetleyicisi bağlıyken HoloLens yeniden başlattıktan sonra, denetleyici HoloLens otomatik olarak yeniden bağlanmaz. Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatılıncaya kadar yavaş yanıp sönecektir. Denetleyicinizi hemen yeniden bağlamak için, ışık kapanmadan, rehber düğmesini basılı tutarak denetleyiciyi kapatın. Denetleyicinizi yeniden açtığınızda, HoloLens olarak yeniden bağlanır.

- Xbox kablosuz denetleyicisi bağlıyken HoloLens bekleme moduna girerse, denetleyicideki herhangi bir giriş HoloLens uyandırır. Bunu kullanarak işiniz bittiğinde denetleyicinizi devre dışı bırakabilirsiniz.

