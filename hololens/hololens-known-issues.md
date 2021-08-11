---
title: HoloLens (1. Nesil) için bilinen sorunlar
description: Unity ve Windows Cihaz Portalı kullanan müşterileri ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici HoloLens listemizi takip Windows Cihaz Portalı.
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
ms.openlocfilehash: d2a8ae420a0c1d646625fe81b166e2daae07e44652b70f2e4a1b19ccba240cfb
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663959"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (1. Nesil) için bilinen sorunlar

Bu cihazlar için bilinen sorunların güncel listesi HoloLens. İlk olarak garip bir davranış görüyorsanız buraya bakabilirsiniz. Bu liste, yeni sorunlar keşfedildi veya raporlandıkça ya da gelecekte yazılım güncelleştirmeleri için sorun gideril HoloLens tutulacak.

>[!NOTE]
> - Engellemeye neden olan bir sorun fark ediyorsanız lütfen bunu HoloLens üzerinden [Geri Bildirim Merkezi.](hololens-feedback.md)
> - Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)


- [Tüm yeni nesiller için HoloLens sorunlar](#known-issues-for-all-hololens-generations)
- [HoloLens (1. Nesil) için bilinen sorunlar](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Tüm yeni nesiller için HoloLens sorunlar

### <a name="unity"></a>Unity

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar HoloLens [Unity forumlarında belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Cihaz Portalı

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Geliştirici Modu'Ayarlar etkinleştirildikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

### <a name="onedrive-camera-upload"></a>OneDrive karşıya kamera yükleme

OneDrive uygulaması HoloLens iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama çift oturum açmayı destekler). Otomatik Microsoft hesabı profilinden OneDrive arka plan kameralı zar yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek için bir tüketici Microsoft hesabı güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile OneDrive yükleyebilirsiniz. Bunu yapmak için, OneDrive uygulamasında iş veya okul hesabınızla oturum OneDrive olun. düğmesini seçin **+** ve Upload. Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (1. Nesil) için bilinen sorunlar

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Ağ üzerinden HoloLens bağlanamıyor Visual Studio

> [!NOTE]
> Son Güncelleştirme: 08.08. @ 17:11 - Visual Studio, bu soruna bir düzeltme içeren VS 2019 Sürüm 16.2'yi yayımladı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Sorunun kök nedeni: HoloLens'larında uygulamaları dağıtmak ve hata ayıklamak için Visual Studio 2015 veya Visual Studio 2017'nin ilk sürümlerini kullanan ve ardından aynı Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan HoloLens etkilenecektir. Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.  Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazın geliştirici modunun etkinleştirildiğinden emin olun. Hata nedeniyle üzerinde geliştirici lisansı \<ip\> 80004005.

#### <a name="workaround"></a>Geçici çözüm

Ekibimiz şu anda bir düzeltme üzerinde çalışıyor. Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:  

1. Visual Studio'yu açın.

1. Dosya Yeni  >  **Dosya'Project.**  >  

1. Visual **C# Windows**  >  **Masaüstü Konsol** Uygulaması  >  **(.NET Framework) öğesini seçin.**

1. Projeye bir ad ("HoloLensDeploymentFix" gibi) ve Framework'in en az 4.5 .NET Framework olduğundan emin olun ve Tamam'ı **seçin.**

1. Çözüm Gezgini'de  Başvurular düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin **(Gözat** bölümüne gidin ve Gözat'ı **seçin):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 yüklü değilse, sahip olduğunuz en son sürümü kullanın.

1. Uygulama içinde projeye sağ tıklayın ve Çözüm Gezgini **Ekle'yi**  >  **seçin.**

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 dizinine göz atarak filtreyi Tüm Dosyalar **( \* . ) \* olarak** değiştirebilirsiniz.

1. Hem SirepClient.dll hem de SshClient.dll ve Ekle'yi **seçin.**

1. Her iki dosyayı da Çözüm Gezgini (dosya listesinin en altında olması gerekir)  bulun ve seçin  ve Özellikler penceresindeKi Çıkış Dizinine Kopyala seçeneğini Her zaman kopyala **olarak değiştirin.**

1. Dosyanın en üstüne, mevcut deyim listesine aşağıdakini `using` ekleyin:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. içinde, `static void Main(...)` aşağıdaki kodu ekleyin:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Derleme   >  **Çözümü'lerini seçin.**

1. Bir Komut İstemi Penceresi açın ve derlenmiş .exe dosyasını içeren klasöre cd yazın (örneğin, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Yürütülebilir dosyayı çalıştırın ve cihazın IP adresini komut satırı bağımsız değişkeni olarak girin. (USB kullanarak bağlandıysanız 127.0.0.1 kullanabilirsiniz, aksi takdirde cihazın ip Wi-Fi kullanabilirsiniz.)  Örneğin, "HoloLensDeploymentFix 127.0.0.1".

1. Araçtan herhangi bir ileti olmadan çıkıldıktan sonra (yalnızca birkaç saniye sürer), artık 2017 veya daha yeni bir sürümde Visual Studio ve hata ayıklaması alabilirsiniz.  Aracın devam eden kullanımı gerekli değildir.

Yeni güncelleştirmeler kullanılabilir hale geldi.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Microsoft Store ve uygulamaları HoloLens

> [!NOTE]
> Son Güncelleştirme: 10.00'da 4/2 - Sorun çözüldü.

Uygulama ve uygulamaları Microsoft Store'da başlatmaya çalışırken sorun HoloLens. Arka plan uygulama güncelleştirmeleri, bağımlı uygulamalardan biri veya daha fazlası çalışırken belirli dizilerde çerçeve paketlerinin daha yeni bir sürümünü dağıtıyorsa bu sorunun oluştuğuna karar verdik. Bu durumda, otomatik uygulama güncelleştirmesi .NET Native Framework'un yeni bir sürümünü (sürüm 10.0.25531'den 10.0.27413'e) teslim etti. Bu, çalışan uygulamaların çerçevenin önceki sürümünü tüketen tüm uygulamalar için doğru şekilde güncelleştirilenemalarına neden oldu.  Çerçeve güncelleştirme akışı aşağıdaki gibidir:

1. Yeni çerçeve paketi mağazadan indirilir ve yüklenir.

1. Tüm uygulamalar çerçevenin kullanımı daha yeni sürümü kullanmak için 'güncelleştirilir'.

2. adım tamamlanmadan kesintiye uğrarsa, yeni çerçevenin kayıtlı olmadığı tüm uygulamalar başlat menüsünden başlatılamayacaktır.  HoloLens uygulamanın bu sorundan etkilendiğine inanıyoruz.

Bazı kullanıcılar, askıda olan uygulamaları kapatmanın ve Geri Bildirim Merkezi, 3B Görüntüleyici veya Photos gibi diğer uygulamaların başlatılmasının sorunu çözeceklerini bildirdi. Ancak, bu sürenin %100'sinde işe yaramamektedir.

Kök neden olarak bu sorunun güncelleştirmenin kendisi değil, işletim sistemi hatası nedeniyle .NET Native framework güncelleştirmesi yanlış işlenmeye neden oldu. Bir düzeltme belirledik ve düzeltmeyi içeren bir güncelleştirme (işletim sistemi sürümü 17763.380) yayımlamıştık.  

Cihazınızın güncelleştirmeyi alıp alamayını görmek için:

1. Ayarlar'a gidin ve **Update & Security'& açın.**

1. Güncelleştirmeleri **Kontrol Edin'i seçin.**

1. 17763.380 güncelleştirmesi varsa, Uygulama Askıda Kalma hatasının düzeltmesini almak için lütfen bu derlemeye güncelleştirin.

1. Bu işletim sistemi sürümüne güncelleştiren Uygulamalar beklendiği gibi çalışmalı.

Ayrıca, her işletim sistemi HoloLens olduğu gibi, FFU görüntüsünü Microsoft İndirme [Merkezi'ne paylaştık.](https://aka.ms/hololensdownload/10.0.17763.380)

Güncelleştirmeyi almak tercih ediyorsanız, 29.03.29'dan Microsoft Store UWP uygulamasının yeni bir sürümünü yayınlandık. Mağazanın güncelleştirilmiş sürümünü edindikten sonra:

1. Mağazayı açın ve yük olduğunu onaylayın.
1. Menüyü açmak için bloom hareketini kullanın.
1. Daha önce bozuk olan uygulamaları açmayı deneme.
1. Hala başlatılamaysa, bozuk uygulamanın simgesine dokunun ve basılı tutun ve kaldır'ı seçin.
1. Bu uygulamaları mağazadan yeniden yükleyin.

Cihazınız yine de uygulama yükleyenene kadar, aşağıdaki adımları kullanarak .NET Native Framework ve Runtime sürümünü indirme merkezi üzerinden kenardan indirebilirsiniz:

1. Lütfen bu [zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi'nden indirin. Sıkıştırmayı geri alama iki dosya üretir.  Microsoft .NET.Native.Runtime.1.7.appx ve Microsoft .NET.Native.Framework.1.7.appx.

1. Lütfen cihazınızın geliştirici kilidinin açık olduğunu doğrulayın.  Bunu daha önce yapmadıysanız yönergeler için [bkz. Windows Cihaz Portalı](/windows/mixed-reality/using-the-windows-device-portal) kullanma.

1. Daha sonra yeni bir Windows Cihaz Portalı. Bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak http://127.0.0.1:10080 yapmaktır.

1. Dosyayı yükledikten Windows Cihaz Portalı indirdiğiniz iki dosyayı "yan yükleme" gerekir. Bunu yapmak için Uygulamalar bölümüne gidip Uygulamalar'ı seçene **kadar** sol kenar çubuğuna **inebilirsiniz.**

1. Ardından aşağıdakine benzer bir ekran görürsünüz.  **Uygulamayı yüklemeyi** belirten bölüme gitmek ve bu iki appx dosyasının sıkıştırılanmasını nereden kaldırıtabileceğiniz konusunda gezinmek istiyorsunuz. Tek seferde yalnızca bir tane yapabilirsiniz, ilk olanı seçtikten sonra dağıt bölümünde "git" düğmesine tıklayın. İkinci APPX dosyası için bunu yapın.

   ![Windows Side-Loaded uygulamasını yüklemek için cihaz portalı](images/20190322-DevicePortal.png)

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

