---
title: HoloLens (1. Nesil) için bilinen sorunlar
description: Unity ve Windows Cihaz Portalı kullanan müşterileri ve geliştiricileri etkileyebilecek bilinen HoloLens sorunlar ve geçici çözümler listemizi takip Windows Cihaz Portalı.
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189299"
---
# <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (1. Nesil) için bilinen sorunlar

Bu cihazlar için bilinen sorunların güncel listesi HoloLens. İlk olarak garip bir davranış görüyorsanız buraya bakabilirsiniz. Bu liste yeni sorunlar keşfedildi veya raporlandıkça ya da gelecekte yazılım güncelleştirmeleri için sorun gideril HoloLens tutulacak.

>[!NOTE]
> - Engellemeye neden olan bir sorun fark ediyorsanız lütfen bunu HoloLens üzerinden [Geri Bildirim Merkezi.](hololens-feedback.md)
> - Karşılaştığınız sorun sizi engelliyorsa, geri bildirim göndermenin yanı sıra lütfen bir [destek isteği gönderin.](https://aka.ms/hlsupport)


- [Tüm yeni nesiller için HoloLens sorunlar](#known-issues-for-all-hololens-generations)
- [HoloLens (1. Nesil) için bilinen sorunlar](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Tüm yeni nesiller için HoloLens sorunlar

### <a name="unity"></a>Unity

- Daha [fazla geliştirme](/windows/mixed-reality/install-the-tools) için önerilen Unity'nin en güncel sürümü için araçları HoloLens bakın.
- Unity HoloLens Technical Preview ile ilgili bilinen sorunlar, unity [forumlarında HoloLens belgelenmiştir.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Cihaz Portalı

- Karma Gerçeklik yakalama özelliğinin Canlı Önizleme özelliği birkaç saniyelik gecikme süresine sahip olabilir.

- Sanal Giriş sayfasında, Sanal Hareketlerin altındaki Hareket ve Kaydırma denetimleri işlevsel değildir. Bunları kullanmanın hiçbir etkisi olmaz. Sanal giriş sayfasındaki sanal klavye düzgün çalışıyor.

- Geliştirici Modu'Ayarlar etkinleştirdikten sonra, anahtarın etkinleştirilmesi birkaç saniye Cihaz Portalı sürebilir.

### <a name="onedrive-camera-upload"></a>OneDrive karşıya kamera yükleme

OneDrive için HoloLens uygulaması, iş veya okul hesapları için otomatik kamera yüklemeyi desteklemez.

Geçici çözümler:

- İşletmeniz için uygunsa tüketici Microsoft hesaplarından otomatik kamera yüklemesi de desteklenebilir. İş veya okul hesabınıza Microsoft hesabı oturum açabilirsiniz (OneDrive uygulama çift oturum açmayı destekler). Microsoft hesabı profilinden OneDrive arka plan kameralı zar yükleme özelliğini etkinleştirebilirsiniz.

- Fotoğraflarınızı otomatik olarak karşıya yüklemek Microsoft hesabı bir tüketici hesabını güvenli bir şekilde kullanasanız, OneDrive uygulamasından iş veya okul hesabınıza el ile OneDrive yükleyebilirsiniz. Bunu yapmak için, OneDrive uygulamasında iş veya okul hesabınızla oturum OneDrive olun. düğmesini seçin **+** ve Upload. Karşıya yüklemek istediğiniz fotoğrafları veya videoları, Kamera Rulosu'na giderek **> bulun.** Karşıya yüklemek istediğiniz fotoğrafları veya videoları seçin ve ardından Aç **düğmesini** seçin.

## <a name="known-issues-for-hololens-1st-gen"></a>HoloLens (1. Nesil) için bilinen sorunlar

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Ağ üzerinden HoloLens bağlanamıyor ve Visual Studio

> [!NOTE]
> Son Güncelleştirme: 08.08. @ 17.11 - Visual Studio, bu sorunun düzeltmesini içeren VS 2019 Sürüm 16.2'yi yayımladı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Visual Studio sorunu düzeltmeyi içeren VS 2019 Sürüm 16.2'de yayınlandı. Bu hatayla karşılaşılmasından kaçınmak için en yeni sürüme güncelleştirmenizi öneririz.

Sorunun kök nedeni: HoloLens'larında uygulamaları dağıtmak ve hata ayıklamak için Visual Studio 2015 veya Visual Studio 2017'nin ilk sürümlerini kullanan ve daha sonra aynı Visual Studio 2017 veya Visual Studio 2019'un en son sürümlerini kullanan HoloLens etkilenecektir. Yeni sürümleri Visual Studio bileşenin yeni bir sürümünü dağıtıyor ancak eski sürümden dosyalar cihazda bırakarak yeni sürümün başarısız olmasına neden oluyor.  Bu, şu hata iletisine neden olur: DEP0100: Hedef cihazın geliştirici modunun etkinleştirildiğinden emin olun. Hata nedeniyle üzerinde geliştirici lisansı \<ip\> 80004005.

#### <a name="workaround"></a>Geçici çözüm

Ekibimiz şu anda bir düzeltme üzerinde çalışıyor. Bu arada, sorunu çözmek ve dağıtımın ve hata ayıklamanın engelini kaldırmaya yardımcı olmak için aşağıdaki adımları kullanabilirsiniz:  

1. Visual Studio'yu açın.

1. Dosya **Yeni**  >  **Dosya'Project.**  >  

1. Visual **C# Windows**  >  **Masaüstü Konsol** Uygulaması  >  **(.NET Framework) öğesini seçin.**

1. Projeye bir ad ("HoloLensDeploymentFix" gibi) ve Framework'in en az 4.5 .NET Framework olduğundan emin olun ve Tamam'ı **seçin.**

1. **Çözüm Gezgini'de** Başvurular düğümüne sağ tıklayın ve aşağıdaki başvuruları ekleyin (Gözat bölümüne gidin **ve Gözat'ı** **seçin):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > 10.0.18362.0 yüklü değilse, sahip olduğunuz en son sürümü kullanın.

1. Uygulama içinde projeye sağ tıklayın ve Çözüm Gezgini Öğe **Ekle'yi**  >  **seçin.**

1. C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 dizinine göz atarak filtreyi Tüm Dosyalar **( \* . ) \* olarak** değiştirebilirsiniz.

1. Hem SirepClient.dll hem de SshClient.dll ve Ekle'yi **seçin.**

1. Her iki dosyayı da Çözüm Gezgini (dosya listesinin en altında olmalıdır) bulun  ve seçin ve  Özellikler penceresindeKimlikler penceresinde Çıkış Dizinine Kopyala seçeneğini her zaman **olarak değiştirin.**

1. Dosyanın en üstüne, mevcut deyim listesine aşağıdakini `using` ekleyin:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. içinde `static void Main(...)` aşağıdaki kodu ekleyin:

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

Uygulama ve uygulamaları Microsoft Store'da başlatmaya çalışırken sorun HoloLens. Arka plan uygulama güncelleştirmeleri, bağımlı uygulamalardan biri veya daha fazlası çalışırken belirli dizilerde çerçeve paketlerinin daha yeni bir sürümünü dağıtıyorsa bu sorunun oluştuğuna karar verdik. Bu durumda, otomatik bir uygulama güncelleştirmesi .NET Native Framework'un yeni bir sürümünü (sürüm 10.0.25531'den 10.0.27413'e) teslim etti. Bu, çalışan uygulamaların çerçevenin önceki sürümünü tüketen tüm çalışan uygulamalar için doğru şekilde güncelleştirilenemalarına neden oldu.  Çerçeve güncelleştirme akışı aşağıdaki gibidir:

1. Yeni çerçeve paketi mağazadan indirilir ve yüklenir.

1. Tüm uygulamalar çerçeveyi kullanan tüm sürümler daha yeni sürümü kullanmak için 'güncelleştirilir'.

2. adım tamamlanmadan kesintiye uğrarsa, yeni çerçevenin kayıtlı olmadığı tüm uygulamalar başlat menüsünden başlatılamayacaktır.  HoloLens uygulamanın bu sorundan etkilendiğine inanıyoruz.

Bazı kullanıcılar, askıda olan uygulamaları kapatmanın ve Geri Bildirim Merkezi, 3B Görüntüleyici veya Fotoğraflar gibi diğer uygulamaların başlatılmasının sorunu çözeceklerini bildirdi. Ancak, bu sürenin %100'sinde çalışmıyor.

Kök neden olarak bu sorunun güncelleştirmenin kendisi değil, işletim sistemi hatası nedeniyle .NET Native framework güncelleştirmesi yanlış işlenmeye neden oldu. Bir düzeltme belirledik ve düzeltmeyi içeren bir güncelleştirme (işletim sistemi sürümü 17763.380) yayımlamıştık.  

Cihazınızın güncelleştirmeyi alıp alamayını görmek için:

1. Ayarlar uygulamasına gidin ve **Update & Security'& açın.**

1. Güncelleştirmeleri **Kontrol Edin'i seçin.**

1. 17763.380 güncelleştirmesi varsa, UygulamaNın Askıda Kalma hatasının düzeltmesini almak için lütfen bu derlemeye güncelleştirin.

1. Bu işletim sistemi sürümüne güncelleştiren Uygulamalar beklendiği gibi çalışmalı.

Ayrıca, her işletim sistemi HoloLens olduğu gibi, FFU görüntüsünü Microsoft İndirme Merkezi'ne [de paylaştık.](https://aka.ms/hololensdownload/10.0.17763.380)

Güncelleştirmeyi almak tercih ediyorsanız, 29/3/29'dan Microsoft Store UWP uygulamasının yeni bir sürümünü yayınlandı. Mağazanın güncelleştirilmiş sürümünü edindikten sonra:

1. Mağazayı açın ve yük olduğunu onaylayın.
1. Menüyü açmak için bloom hareketini kullanın.
1. Daha önce bozuk olan uygulamaları açmayı deneme.
1. Hala başlatılamaysa, bozuk uygulamanın simgesine dokunun ve basılı tutun ve kaldır'ı seçin.
1. Bu uygulamaları mağazadan yeniden yükleyin.

Cihazınız yine de uygulama yükleyemiyorsa, aşağıdaki adımları kullanarak indirme merkezi üzerinden .NET Native Framework ve Çalışma Zamanı'nın bir sürümünü kenardan indirebilirsiniz:

1. Lütfen bu [zip dosyasını](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Microsoft İndirme Merkezi'nden indirin. Sıkıştırmayı geri alama iki dosya üretir.  Microsoft .NET.Native.Runtime.1.7.appx ve Microsoft .NET.Native.Framework.1.7.appx.

1. Lütfen cihazınızın geliştirici kilidinin açık olduğunu doğrulayın.  Bunu daha önce yapmadıysanız yönergeler [için bkz. Windows Cihaz Portalı](/windows/mixed-reality/using-the-windows-device-portal) kullanma.

1. Daha sonra yeni bir Windows Cihaz Portalı. Bunu USB üzerinden yapmak ve bunu tarayıcınıza yazarak http://127.0.0.1:10080 yapmaktır.

1. Dosyayı yükledikten Windows Cihaz Portalı indirdiğiniz iki dosyayı "yan yükleme" gerekir. Bunu yapmak için Uygulamalar bölümüne gidip Uygulamalar'ı seçene **kadar** sol kenar çubuğuna **inebilirsiniz.**

1. Ardından aşağıdakine benzer bir ekran görürsünüz.  Uygulama Yükle bölümüne gidip bu **iki** APPX dosyası için sıkıştırmayı açmak istediğiniz yere gitmek istiyorsanız. Aynı anda yalnızca bir tane abilirsiniz, bu nedenle ilki seçdikten sonra Dağıt bölümünün altındaki "Git" seçeneğine tıklayın. Ardından bunu ikinci APPX dosyası için yap.

   ![Windows Cihaz Portalı Uygulamayı Side-Loaded.](images/20190322-DevicePortal.png)

1. Bu noktada, uygulamalarınızı yeniden çalışmaya başlaması gerektiğine ve Mağaza'ya da varabilirsiniz.

1. Bazı durumlarda, etkilenen uygulamalar başlatılamadan önce 3B Görüntüleyici başlatmanın ek adımını çalıştırmak gerekir.

Bu sorunu çözecek süreci tamamlaya kadar sabırdan dolayı teşekkür ederiz ve başarılı Karma Gerçeklik deneyimleri oluşturmak için topluluğumuzla çalışmaya devam etmek için sabırsızlanıyoruz.

### <a name="device-update"></a>Cihaz Güncelleştirmesi

- Yeni güncelleştirmeden 30 saniye sonra kabuk bir kez gözden kaybolabilir. Oturum **sürdürmeniz için** lütfen bloom hareketi gerçekleştirin.

### <a name="visual-studio"></a>Visual Studio

- Geliştirme [için önerilen](/windows/mixed-reality/install-the-tools) en güncel Visual Studio için araçları yükleme HoloLens bakın.

- Bir uygulamayı Visual Studio ortamınıza HoloLens şu hatayı alabilirsiniz: İstenen işlem kullanıcıyla eşlenmiş bölümü açık olan **bir dosyada gerçekleştirilamaz. (HRESULT özel durumu: 0x800704C8)**. Bu durumda, yeniden deneyin ve dağıtımınız genel olarak başarılı olur.

### <a name="api"></a>API

- Uygulama kullanıcının odak noktasını [veya](/windows/mixed-reality/focus-point-in-unity) camera.forward normal noktasını ayarlarsa, hologramlar fotoğraf veya videolarda Karma Gerçeklik Yakalama görünmez. Bu hata Windows düzeltene kadar, uygulamalar odak noktasını [](/windows/mixed-reality/focus-point-in-unity) etkin bir şekilde ayarlasalar, düzlemin normalin kamera ileri doğru (örneğin, normal = -camera.forward) tersini ayarlaması gerekir.

### <a name="xbox-wireless-controller"></a>Xbox Kablosuz Denetleyicisi

- Xbox Kablosuz Denetleyici S, cihazla birlikte kullanılmadan önce HoloLens. Denetleyicinizi [bir güvenlik denetleyicisiyle](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) eşleştirmeye çalışmadan önce güncel HoloLens.

- Xbox Kablosuz Denetleyicisi HoloLens cihazınızı yeniden başlatırsanız, denetleyici otomatik olarak HoloLens. Kılavuz düğmesi ışığı, denetleyici 3 dakika sonra kapatana kadar yavaş yanıp sönecek. Denetleyicinizi hemen yeniden bağlanmak için, ışık kapatana kadar Kılavuz düğmesini basılı tutarak denetleyiciyi kapatın. Denetleyiciniz yeniden bağlandığında, denetleyiciniz yeniden HoloLens.

- Konsolunuz HoloLens Xbox Kablosuz Denetleyicisi bağlıyken bekleme moduna girerse, denetleyicide herhangi bir giriş HoloLens. Kullanımınız bittiğinde denetleyicinizi kapatarak bunu önleyabilirsiniz.

