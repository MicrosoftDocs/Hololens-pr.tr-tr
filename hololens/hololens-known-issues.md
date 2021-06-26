---
title: HoloLens için bilinen sorunlar (1. Nesil)
description: Unity ve diğer platformları kullanan HoloLens müşterilerini ve geliştiricileri etkileyebilecek bilinen sorunlar ve geçici çözümler listemizi takip Windows Cihaz Portalı.
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923559"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens için bilinen sorunlar (1. Nesil)

HoloLens cihazları için bilinen sorunların güncel listesi burada vemektedir. Garip bir davranış görüyorsanız önce buraya göz sınız. Bu liste yeni sorunlar keşfedildi veya raporlandıkça ya da gelecek HoloLens yazılım güncelleştirmeleri ile ilgili sorunlar giderildikça güncelleştirilecek.

>[!NOTE]
> - Engellemeye neden olan bir sorun fark ediyorsanız lütfen bu sorunu [Geri Bildirim Merkezi.](hololens-feedback.md)
> - Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)


- [Tüm HoloLens nesilleri için bilinen sorunlar](#known-issues-for-all-hololens-generations)
- [HoloLens için bilinen sorunlar (1. Nesil)](#known-issues-for-hololens-1st-gen)

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

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens için bilinen sorunlar (1. Nesil)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Sanal ağ üzerinden HoloLens'e bağlanamıyor ve Visual Studio

> [!NOTE]
> Son Güncelleştirme: 8/05:11 - Visual Studio, bu soruna bir düzeltme içeren VS 2019 Sürüm 16.2'yi yayımladı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Sorunun kök nedeni: HoloLens'lerinde uygulamaları dağıtmak ve bunların hata ayıklamak için Visual Studio Visual Studio 2015 veya önceki sürümlerini kullanan ve daha sonra aynı HoloLens ile Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan kullanıcılar etkilenecektir. Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.  Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazda geliştirici modunun etkinleştirildiğinden emin olun. \<ip\>80004005 hatası nedeniyle üzerinde geliştirici lisansı alınemedi.

#### <a name="workaround"></a>Geçici çözüm

Ekibimiz şu anda bir düzeltme üzerinde çalışıyor. Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:  

1. Visual Studio'yu açın.

1. Dosya Yeni  >  **Proje'yi**  >  **seçin.**

1. **Visual C#**  >  **Windows Masaüstü Konsol Uygulaması**  >  **(.NET Framework) öğesini seçin.**

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

1. Araçtan herhangi bir ileti olmadan çıkıldıktan sonra (bu yalnızca birkaç saniye sürer), artık 2017 veya daha yeni bir sürümde Visual Studio ve hata ayıklaması alabilirsiniz.  Aracın devam eden kullanımı gerekli değildir.

Yeni güncelleştirmeler kullanılabilir hale geldi.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>HoloLens'Microsoft Store uygulamaları başlatma sorunları

> [!NOTE]
> Son Güncelleştirme: 10.00'da 4/2 - Sorun çözüldü.

HoloLens'de uygulama ve Microsoft Store başlatmaya çalışırken sorun yaşayabilirsiniz. Arka plan uygulama güncelleştirmeleri, bağımlı uygulamalardan biri veya daha fazlası çalışırken belirli dizilerde çerçeve paketlerinin daha yeni bir sürümünü dağıtıyorsa bu sorunun oluştuğuna karar verdik. Bu durumda, otomatik uygulama güncelleştirmesi .NET Native Framework'un yeni bir sürümünü (sürüm 10.0.25531-10.0.27413) teslim etti. Bu, çalışan uygulamaların çerçevenin önceki sürümünü tüketen tüm uygulamalar için doğru şekilde güncelleştirilenemalarına neden oldu.  Çerçeve güncelleştirme akışı aşağıdaki gibidir:

1. Yeni çerçeve paketi mağazadan indirilir ve yüklenir.

1. Tüm uygulamalar çerçeveyi kullanan tüm sürümler daha yeni sürümü kullanmak için 'güncelleştirilir'.

2. adım tamamlanmadan kesintiye uğrarsa, yeni çerçevenin kayıtlı olmadığı tüm uygulamalar başlat menüsünden başlatılamayacaktır.  HoloLens'in tüm uygulamalarının bu sorundan etkilenebilirsiniz.

Bazı kullanıcılar, askıda olan uygulamaları kapatmanın ve Geri Bildirim Merkezi, 3B Görüntüleyici veya Photos gibi diğer uygulamaların başlatılmasının sorunu çözeceklerini bildirdi. Ancak, bu sürenin %100'sinde işe yaramamektedir.

Kök neden olarak bu sorunun güncelleştirmenin kendisi değil, işletim sistemi hatası nedeniyle .NET Native framework güncelleştirmesi yanlış işlenmeye neden oldu. Bir düzeltme belirledik ve düzeltmeyi içeren bir güncelleştirme (işletim sistemi sürümü 17763.380) yayımlamıştık.  

Cihazınızın güncelleştirmeyi alıp alamayını görmek için:

1. Ayarlar uygulamasına gidin ve Update **& Security'& açın.**

1. Güncelleştirmeleri **Kontrol Edin'i seçin.**

1. 17763.380 güncelleştirmesi varsa, Uygulama Askıda Kalma hatasının düzeltmesini almak için lütfen bu derlemeye güncelleştirin.

1. Bu işletim sistemi sürümüne güncelleştiren Uygulamalar beklendiği gibi çalışmalı.

Ayrıca, her HoloLens işletim sistemi sürümüyle olduğu gibi, FFU görüntüsünü Microsoft İndirme [Merkezi'ne de paylaştık.](https://aka.ms/hololensdownload/10.0.17763.380)

Güncelleştirmeyi almak tercih ediyorsanız, 29/3/29'dan Microsoft Store UWP uygulamasının yeni bir sürümünü yayınlandı. Mağazanın güncelleştirilmiş sürümünü edindikten sonra:

1. Mağazayı açın ve yük olduğunu onaylayın.
1. Menüyü açmak için bloom hareketini kullanın.
1. Daha önce bozuk olan uygulamaları açmayı deneme.
1. Hala başlatılamaysa, bozuk uygulamanın simgesine dokunun ve basılı tutun ve kaldır'ı seçin.
1. Bu uygulamaları mağazadan yeniden yükleyin.

Cihazınız yine de uygulama yükleyenene kadar, aşağıdaki adımları kullanarak indirme merkezi üzerinden .NET Native Framework ve Çalışma Zamanı sürümünü kenardan indirebilirsiniz:

1. Lütfen bu [zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi'nden indirin. Sıkıştırmayı geri alama iki dosya üretir.  Microsoft .NET.Native.Runtime.1.7.appx ve Microsoft .NET.Native.Framework.1.7.appx.

1. Lütfen cihazınızın geliştirici kilidinin açık olduğunu doğrulayın.  Bunu daha önce yapmadıysanız yönergeler [için bkz. Windows Cihaz Portalı](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) kullanma.

1. Daha sonra yeni bir Windows Cihaz Portalı. Bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak http://127.0.0.1:10080 yapmaktır.

1. Uygulamayı yükledikten Windows Cihaz Portalı indirdiğiniz iki dosyayı "yan yükleme" gerekir. Bunu yapmak için Uygulamalar bölümüne gidip Uygulamalar'ı seçene **kadar** sol kenar çubuğuna **inebilirsiniz.**

1. Ardından aşağıdakine benzer bir ekran görürsünüz.  Uygulama Yükle bölümüne gitmek ve **bu** iki APPX dosyanın sıkıştırması açılmış olan yere göz atmak istiyorsanız. Aynı anda yalnızca bir tane abilirsiniz, bu nedenle ilki seçdikten sonra Dağıt bölümünün altındaki "Git" seçeneğine tıklayın. Ardından bunu ikinci APPX dosyası için yap.

   ![Windows Cihaz Portalı uygulamayı Side-Loaded gerekir](images/20190322-DevicePortal.png)

1. Bu noktada, uygulamalarınızı yeniden çalışmaya başlaması gerektiğine ve Mağaza'ya da varabilirsiniz.

1. Bazı durumlarda, etkilenen uygulamalar başlatılamadan önce 3B Görüntüleyici başlatmanın ek adımını çalıştırmak gerekir.

Bu sorunu çözecek süreci tamamlaya kadar sabırdan dolayı teşekkür ederiz ve başarılı Karma Gerçeklik deneyimleri oluşturmak için topluluğumuzla çalışmaya devam etmek için sabırsızlanıyoruz.

### <a name="device-update"></a>Cihaz Güncelleştirmesi

- Yeni güncelleştirmeden 30 saniye sonra kabuk bir kez gözden kaybolabilir. Oturum **sürdürmeniz için** lütfen bloom hareketi gerçekleştirin.

### <a name="visual-studio"></a>Visual Studio

- [HoloLens](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) geliştirmesi için önerilen en güncel Visual Studio için bkz. Araçları yükleme.

- Bir uygulamayı Visual Studio HoloLens'inize dağıtırken şu hatayı alabilirsiniz: İstenen işlem kullanıcıyla eşlenmiş bölümü açık olan **bir dosyada gerçekleştirilamaz. (HRESULT özel durumu: 0x800704C8)**. Bu durumda, yeniden deneyin ve dağıtımınız genel olarak başarılı olur.

### <a name="api"></a>API

- Uygulama kullanıcının odak noktasını [veya](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) camera.forward için normali ayarlarsa, hologramlar fotoğraf veya videolarda Karma Gerçeklik Yakalama görünmez. Bu hata Windows'da düzeltene kadar, [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) uygulamalar odak noktasını etkin bir şekilde ayarlasalar, düzlemin normalin kamera ileri doğru (örneğin, normal = -camera.forward) tersini ayarlaması gerekir.

### <a name="xbox-wireless-controller"></a>Xbox Kablosuz Denetleyicisi

- HoloLens ile kullanılamadan önce Xbox Kablosuz Denetleyici S'nin güncelleştirilmiş olması gerekir. Denetleyicinizi [HoloLens ile](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) eşleştirmeye çalışmadan önce güncel olduğundan emin olun.

- Xbox Kablosuz Denetleyicisi bağlıyken HoloLens'inizi yeniden başlatırsanız, denetleyici HoloLens'e otomatik olarak yeniden bağlanmaz. Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatana kadar yavaş yanıp sönecek. Denetleyicinizi hemen yeniden bağlanmak için, ışık kapatana kadar Kılavuz düğmesini basılı tutarak denetleyiciyi kapatın. Denetleyiciniz yeniden bağlandığında HoloLens'e yeniden bağlanır.

- Xbox Kablosuz Denetleyicisi bağlıyken HoloLens'iniz bekleme moduna girerse, denetleyicide herhangi bir giriş HoloLens'i uyandıracak. Kullanımınız bittiğinde denetleyicinizi kapatarak bunu önleyabilirsiniz.

