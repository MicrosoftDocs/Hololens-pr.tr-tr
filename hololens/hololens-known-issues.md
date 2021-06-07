---
title: HoloLens için bilinen sorunlar
description: Unity ve diğer platformları kullanan HoloLens müşterilerini ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemizi takip Windows Cihaz Portalı.
keywords: sorun giderme, bilinen sorun, yardım
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379071"
---
# <a name="known-issues-for-hololens"></a>HoloLens için bilinen sorunlar

HoloLens cihazları için bilinen sorunların güncel listesi burada vemektedir. Garip bir davranış görüyorsanız önce buraya göz sınız. Bu liste yeni sorunlar keşfedildi veya raporlandıkça ya da gelecek HoloLens yazılım güncelleştirmeleri ile ilgili sorunlar giderildikça güncelleştirilecek.

>[!NOTE]
> - Engellemeye neden olan bir sorun fark ediyorsanız lütfen bu sorunu [Geri Bildirim Merkezi.](hololens-feedback.md)
> - Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)

- [Tüm HoloLens nesilleri için bilinen sorunlar](#known-issues-for-all-hololens-generations)
- [HoloLens 2 cihazları için bilinen sorunlar](#known-issues-for-hololens-2-devices)
- [HoloLens için bilinen sorunlar (1. Nesil)](#known-issues-for-hololens-1st-gen)
- [HoloLens öykünücüsü için bilinen sorunlar](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Tüm HoloLens nesilleri için bilinen sorunlar

### <a name="unity"></a>Unity

- Bkz. [Unity'nin](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens geliştirmesi için önerilen en güncel sürümü için araçları yükleme.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar [HoloLens Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Cihaz Portalı

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Ayarlar'da Geliştirici Modu etkinleştirildikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

### <a name="onedrive-camera-upload"></a>OneDrive kamera karşıya yükleme

HoloLens için OneDrive uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulaması çift oturum açmayı destekler). OneDrive'Microsoft hesabı profilden otomatik, arka plan kameralı rolle karşıya yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile fotoğraf yükleyebilirsiniz. Bunu yapmak için OneDrive uygulamasında iş veya okul hesabınızla oturum asanıza. Düğmesini seçin **+** ve Karşıya **Yükle'yi seçin.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

## <a name="known-issues-for-hololens-2-devices"></a>HoloLens 2 cihazları için bilinen sorunlar

### <a name="device-using-auto-login-asks-for-log-in"></a>Otomatik oturum açma kullanan cihaz oturum açma bilgilerini sorar

Bir HoloLens 2 cihazı, Ayarlar Hesapları Oturum Açma Seçenekleri -> ve Gerekli altında değeri Asla olarak ayarlandı olarak otomatik olarak  ->    ->   oturum açacaktır.   Bazı kullanıcıların, bir cihazı özellik güncelleştirmesi gibi önemli ölçüde büyük bir güncelleştirmeyle güncelleştiren cihazda yeniden oturum açması gerekebilir.

Bunun ne zaman oluştuğuna örnek:

- Bir cihazı Windows Holographic sürüm 2004'den (Derleme 19041.xxxx) Windows Holographic, sürüm 21H1'e güncelleştirme (Derleme 20346.xxxx)
- Bir cihazı aynı ana derlemede büyük bir güncelleştirme alacak şekilde güncelleştirme, örneğin Windows Holographic, sürüm 2004'ü Windows Holographic, sürüm 20H2
- Bir cihazı fabrika görüntüsünden en son görüntüye güncelleştirme

Bu durum aşağıdakiler sırasında oluşmaz:

- Aylık bakım güncelleştirmesi alan cihazlar

Yöntemlerle ilgili çalışma:

- PIN, Parola, Iris, Web Kimlik Doğrulaması veya FIDO2 anahtarları gibi oturum açma yöntemleri.
- Cihaz PIN'i anımsanamazsa ve diğer kimlik doğrulama yöntemleri kullanılamıyorsa, kullanıcı el [ile ters eğik çizgi uygulama modunu kullanabilir.](hololens-recovery.md#manual-procedure)

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge başlatıla

> [!NOTE]
> Bu sorun başlangıçta Microsoft Edge sürümüyle oluşturulmuş. Bu sorun yeni [Microsoft Edge.](hololens-new-edge.md) Doğru değilse lütfen geri bildirim gönderin.

Birkaç müşteri, uygulamanın başlatılama Microsoft Edge bir sorun bildirdi. Bu müşteriler için sorun yeniden başlatma sırasında devam eder ve Windows veya uygulama güncelleştirmeleriyle çözülemez. Bu sorunla karşılaşıyorsanız ve [Windows'un](hololens-updates.md#manually-check-for-updates)güncel olduğunu onayladıysanız lütfen [Geri Bildirim Merkezi](hololens-feedback.md) uygulamasından şu kategoriye ve alt kategoriye sahip bir hata kaydedin: >'i yükleme, yükleme ve yapılandırma adımları Windows Update.

Şu ana kadar sorunun kök nedenini bulamamamız nedeniyle bilinen bir geçici çözüm yoktur. Geri Bildirim Merkezi aracılığıyla hata Geri Bildirim Merkezi araştırmamıza yardımcı olacak!

### <a name="keyboard-does-not-switch-to-special-characters"></a>Klavye özel karakterlere geçmez

OOBE sırasında, kullanıcı bir iş veya okul hesabı seçtikten ve parolasını girdikten sonra &123 düğmesine dokunarak klavyedeki özel karakterlere geçmeye çalışırken özel karakterlere geçmemeye çalıştığı bir sorun vardır.

Çalışma:
-   Metin alanına dokunarak klavyeyi kapatın ve yeniden açın.
-   Parolanızı yanlış girin. Klavye bir sonraki sefer yeniden edilse beklendiği gibi çalışacaktır.
- Web Kimlik Doğrulaması'nın klavyesini kapatın ve başka **bir cihazdan Oturum açın'ı seçin.**
-   Yalnızca sayı giriliyorsa, kullanıcı belirli tuşlara basarak ve basılı tutarak genişletilmiş bir menü açabilir.
-   USB klavyesi kullanma.

Bu durum şunları etkilemez:
- Kişisel hesap kullanmayı seçen kullanıcılar.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Insider önizleme derlemelerinin bir Insider derlemesi ile yeniden renkle gösterilen cihaz kaydından sonra mavi ekran gösterilir

Bu, Bir Insider önizleme derlemesine sahip olan kullanıcıları etkileyen, HoloLens 2'lerini yeni bir insider önizleme derlemesi ile yeniden yazdıran ve insider programından kaydı s olan kullanıcıları etkileyen bir sorundur.

Bu durum şunları etkilemez:
- Windows Insider'a kayıtlı Windows Insider 
- Içerdekiler:
    - Insider derlemeleri 18362.x sürümünden beri bir cihaz kayıtlı ise
    - Insider imzalı bir 19041.x derlemesi sönerse VE Insider programına kayıtlı kalır

Üzerinde çalışma: 
- Sorundan kaçının 
    - İçinde olmayan bir derlemeyi flash iletir. Normal aylık güncelleştirmelerden biri.
    - Insider Preview'da kalın
- Cihaza ters eğik çizgi

    1. [Bağlanmadan tamamen kapatarak HoloLens 2'nin](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) el ile yanıp sönme moduna alın. Ardından Birim'i basılı tutarken Güç düğmesine dokunun.
    
    1. Bilgisayara bağlanarak Gelişmiş Kurtarma Yardımcı'sı'nu açın.
    
    1. HoloLens 2'nin varsayılan derlemesine flash iletir.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens için bilinen sorunlar (1. Nesil)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Sanal ağ üzerinden HoloLens'e bağlanamıyor ve Visual Studio

> [!NOTE]
> Son Güncelleştirme: 08.08. @ 17.11 - Visual Studio, bu sorunun düzeltmesini içeren VS 2019 Sürüm 16.2'yi yayımladı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Sorunun kök nedeni: HoloLens'lerinde uygulamaları dağıtmak ve hata ayıklamak için Visual Studio 2015 veya önceki Visual Studio 2017 sürümlerini kullanan ve daha sonra aynı HoloLens ile Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan kullanıcılar etkilenecektir. Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.  Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun. \<ip\>80004005 hatası nedeniyle üzerinde geliştirici lisansı alınemedi.

#### <a name="workaround"></a>Geçici çözüm

Ekibimiz şu anda bir düzeltme üzerinde çalışıyor. Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:  

1. Visual Studio'yu açın.

1. Dosya **Yeni**  >  **Proje'yi**  >  **seçin.**

1. **Visual C#**  >  **Windows Masaüstü Konsol Uygulaması**  >  **(.NET Framework) öğesini seçin.**

1. Projeye bir ad verin (örneğin, "Holomersdeploymentdüzeltmesini") ve Framework 'Ün en az .NET Framework 4,5 ' e ayarlandığından emin olun ve ardından **Tamam**' ı seçin.

1. Çözüm Gezgini ' deki **Başvurular** düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin ( **Gözden** geçirme bölümüne ve sonra da **gözatatıon**' ı seçin):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 yüklü değilse, en son sürümü kullanın. 

1. Çözüm Gezgini projede projeye sağ tıklayın ve   >  **var olan öğe** Ekle ' yi seçin.

1. C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 'e gidin ve filtreyi **tüm dosyalar ( \* . \* )** olarak değiştirin.

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

1. Araç herhangi bir ileti olmadan çıkıldıktan sonra (Bu yalnızca birkaç saniye sürer), artık Visual Studio 2017 veya daha yeni bir sürümü dağıtabilir ve hata ayıklaması yapabileceksiniz.  Aracın devam eden kullanımı gerekli değildir.

Kullanılabilir hale geldiğinde daha fazla güncelleştirme sağlayacağız.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens 'te Microsoft Store ve uygulamaları başlatan sorunlar

> [!NOTE]
> Son güncelleştirme: 4/2 @ 10-sorun çözüldü.

HoloLens üzerinde Microsoft Store ve uygulamaları başlatmaya çalışırken sorunlarla karşılaşabilirsiniz. Arka plan uygulama güncelleştirmeleri, bir veya daha fazla bağımlı uygulama çalışmaya devam ederken belirli bir sırada çerçeve paketlerinin daha yeni bir sürümünü dağıtırken sorunun oluştuğunu belirledik. Bu durumda, bir otomatik uygulama güncelleştirmesi .NET Native Framework 'ün yeni bir sürümünü (sürüm 10.0.25531 ile 10.0.27413) dağıttığı, çalışan uygulamaların, Framework 'ün önceki sürümünü kullanan tüm çalışan uygulamalar için düzgün şekilde güncelleştirileceğinden oluşur.  Çerçeve güncelleştirmesi için akış aşağıdaki gibidir:

1. Yeni çerçeve paketi mağazadan indirilir ve yüklenir.

1. Eski Framework kullanan tüm uygulamalar, daha yeni sürümü kullanmak için ' güncelleştirildi '.

2. adım tamamlanmadan önce kesintiye uğrarsa, daha yeni Framework 'ün kaydolmadığı tüm uygulamalar Başlangıç menüsünden başlayamaz.  HoloLens üzerinde herhangi bir uygulamanın bu sorundan etkilendiğine inandık.

Bazı kullanıcılar, askıda olan uygulamaları kapatan ve geri bildirim merkezi gibi diğer uygulamaları başlatan rapor verdi, 3B görüntüleyici veya fotoğraflar bu sorunu çözer. ancak, bu sürenin %100 ' i çalışmaz.

Kök sunuyoruz, bu sorunun güncelleştirmenin kendisinin neden olmadığı, ancak işletim sisteminde .NET Native Framework güncelleştirmesiyle yanlış işlenmekte olan bir hata oluştu. Bir onarım belirlediğimiz ve bu güncelleştirmeyi içeren bir güncelleştirme (OS sürüm 17763,380) yayımladığımızda duyurmaktan memnuniyet duyuyoruz.  

Cihazınızın güncelleştirmeyi alıp almaz:

1. Ayarlar uygulamasına gidin ve **güncelleştirme & güvenlik**' i açın.

1. **Güncelleştirmeleri denetle**' yi seçin.

1. 17763,380 güncelleştirmesi varsa, uygulama askıda kalma hatasına yönelik çözümü almak için lütfen bu yapıya güncelleştirin.

1. İşletim sisteminin bu sürümüne güncelleştirme yapıldığında uygulamalar beklendiği gibi çalışmalıdır.

Ayrıca, her HoloLens işletim sistemi sürümünde yaptığımız gibi, [Microsoft Indirme merkezi](https://aka.ms/hololensdownload/10.0.17763.380)'ne FFU görüntüsünü naklettik.

Güncelleştirmeyi yapmak istemiyorsanız, 3/29 itibariyle Microsoft Store UWP uygulamasının yeni bir sürümünü yayımladık. Mağaza 'nın güncelleştirilmiş sürümüne sahip olduktan sonra:

1. Mağazayı açın ve yüklendiğini onaylayın.
1. Menüyü açmak için Bloom hareketini kullanın.
1. Daha önce bozulan uygulamaları açmayı deneyin.
1. Hala başlatılamaz, bozuk uygulamanın simgesine dokunup basılı tutun ve Kaldır ' ı seçin.
1. Bu uygulamaları mağazadan yeniden yükleyin.

Cihazınız hala uygulama yükleyeerişemiyorsanız, aşağıdaki adımları izleyerek .NET Native Framework ve çalışma zamanının bir sürümünü indirme merkezi aracılığıyla dışarıdan yükleyebilirsiniz:

1. Lütfen [Bu zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi ' nden indirin. Unzippıng iki dosya oluşturur.  Microsoft. NET. Native. Runtime. 1.7. appx ve Microsoft. NET. Native. Framework. 1.7. appx.

1. Lütfen cihazınızın dev olarak kilidinin açık olduğundan emin olun.  Daha önce yapmadıysanız yönergeler için bkz. [Windows cihaz portalını kullanma](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) .

1. Daha sonra Windows cihaz portalına ulaşmak istiyorsunuz. Önerimiz bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak yapmanız gerekir http://127.0.0.1:10080 .

1. Windows cihaz portalı 'nı yükledikten sonra, indirdiğiniz iki dosyayı "Dışarıdan yükleme" yapmanız gerekir. Bunu yapmak için, **uygulamalar** bölümüne ulaşana ve **uygulamalar**' ı seçene kadar sol taraftaki çubuğa gitmeniz gerekir.

1. Ardından aşağıdakine benzer bir ekran görürsünüz.  **Uygulamayı yüklemeyi** belirten bölüme gitmek ve bu iki appx dosyasının sıkıştırılanmasını nereden kaldırıtabileceğiniz konusunda gezinmek istiyorsunuz. Tek seferde yalnızca bir tane yapabilirsiniz, ilk olanı seçtikten sonra dağıt bölümünde "git" düğmesine tıklayın. İkinci APPX dosyası için bunu yapın.

   ![Side-Loaded uygulamasını yüklemek için Windows cihaz portalı](images/20190322-DevicePortal.png)
   
1. Bu noktada, uygulamalarınızın yeniden çalışmaya başlaması ve mağazaya de başlayabilmeniz gerektiğini düşünüyoruz.

1. Bazı durumlarda, etkilenen uygulamaların başlatılması için önce 3B görüntüleyici uygulamasını başlatma ek adımını çalıştırmanız gerekir. 

Bu sorunu çözmemiz için işlem boyunca yaptığımız ve başarılı karma gerçeklik deneyimleri oluşturmak için Topluluğumuzdan çalışmaya devam ediyoruz.

### <a name="device-update"></a>Cihaz Güncelleştirmesi

- 30 saniye yeni bir güncelleştirmeden sonra kabuk bir kez kaybolabilir. Oturumunuzu sürdürmeniz için lütfen **Bloom** hareketini gerçekleştirin.

### <a name="visual-studio"></a>Visual Studio

- Bkz. Visual Studio 'nun en güncel sürümü için, HoloLens geliştirme için önerilen [araçları kurma](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) .

- Visual Studio 'dan HoloLens 'e bir uygulama dağıttığınızda şu hatayı görebilirsiniz: **istenen işlem Kullanıcı eşlemeli bir bölümün açık olduğu bir dosya üzerinde gerçekleştirilemiyor. (HRESULT özel durumu: 0x800704C8)**. Bu durumda yeniden deneyin ve dağıtımınız genellikle başarılı olur.

### <a name="api"></a>API

- Uygulama, [odak noktasını](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) kullanıcının arkasında veya normal olarak kameraya ayarlarsa, hologramlar karma gerçeklik yakalama fotoğraflarında veya videolarında görünmez. Bu hata Windows 'da düzeltilene kadar, uygulamalar [odak noktasını](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) etkin bir şekilde ayarladıklarında, düzlemi normalin daha ters kamera iletme (örneğin, normal =-Camera. ileri) olarak ayarlandığından emin olunması gerekir.

### <a name="xbox-wireless-controller"></a>Xbox Kablosuz denetleyicisi

- Xbox Kablosuz denetleyicisi, HoloLens ile kullanılmadan önce güncelleştirilmeleri gerekir. Denetleyicinizi bir HoloLens ile eşleştirmeye [çalışmadan önce güncel olduğunuzdan emin](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) olun.

- Xbox Kablosuz denetleyicisi bağlıyken HoloLens 'nizi yeniden başlattıktan sonra denetleyici, HoloLens 'e otomatik olarak yeniden bağlanmaz. Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatılıncaya kadar yavaş yanıp sönecektir. Denetleyicinizi hemen yeniden bağlamak için, ışık kapanmadan, rehber düğmesini basılı tutarak denetleyiciyi kapatın. Denetleyicinizi yeniden açtığınızda, HoloLens 'e yeniden bağlanır.

- Xbox Kablosuz denetleyicisi bağlıyken HoloLens 'niz bekleme moduna girerse, denetleyicideki herhangi bir giriş HoloLens 'i uyandırır. Bunu kullanarak işiniz bittiğinde denetleyicinizi devre dışı bırakabilirsiniz.

## <a name="known-issues-for-hololens-emulator"></a>HoloLens öykünücüsü için bilinen sorunlar

- Microsoft Store tüm uygulamalar öykünücü ile uyumlu değildir. Örneğin, Genç ve parçaların öykünücü üzerinde oynatılamaz.
- Öykünücüsünde PC web kamerasını kullanamazsınız.
- Windows cihaz portalının canlı önizleme özelliği öykünücü ile çalışmaz. Hala karma gerçeklik Videoları ve görüntülerini yakalayabilirsiniz.
