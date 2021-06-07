---
title: Microsoft HoloLens için Insider önizlemesi
description: Insider derlemeleriyle çalışmaya başlamayı ve HoloLens için bir sonraki büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamayı öğrenin.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379080"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview derlemesine hoş geldiniz! HoloLens için bir [sonraki](hololens-insider.md#start-receiving-insider-builds) büyük işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamak ve çalışmaya başlamanız oldukça kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider Sürüm Notları

Windows Insider'lara yeni özelliklerle yeniden uçuş yapmaya başlamak için heyecanlanıyoruz. En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır. Yeni derlemelerimize daha fazla özellik ve güncelleştirme eklerken bu sayfayı Windows Insider devam edeceğiz. Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive iş veya okul KameraLarını Karşıya Yükleme

*20346.1402 derlemesinde tanıtıldı*

HoloLens 2 Ayarlar uygulamasına, müşterilerin cihazın Pictures > Camera Roll klasöründeki karma gerçeklik fotoğraflarını ve videolarını otomatik olarak ilgili OneDrive iş veya okul klasörüne yüklemesine olanak sağlayan yeni bir özellik ekledik. Bu özellik, HoloLens 2'de [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) uygulamasındaki bir özellik açığına yöneliktir ve müşterinin kişisel hesabına (iş veya okul hesabı değil) yalnızca otomatik KameraLı Microsoft hesabı yüklemesini destekler.

**Nasıl çalışır?**

- "Kamera **karşıya yükleme> etkinleştirmek > System > Mixed Reality Camera"** (Karma Gerçeklik Kamerası) için Ayarlar'ı ziyaret edin.
- Bu özellik Açık  konuma ayarlanır ve cihazınıza yakalanan karma gerçeklik fotoğrafları veya videoları otomatik olarak OneDrive iş veya okul hesabının Pictures > Camera Roll klasörüne yüklenmek için kuyruğa eklenir.
    >[!NOTE]
    >Bu özellik etkinleştirilmeden önce yakalanan fotoğraflar ve videolar *karşıya* yükleme için kuyruğa yüklenmez ve yine de el ile karşıya yüklenmeleri gerekir.
- Ayarlar sayfasındaki bir durum iletisi karşıya yüklenmeyi bekleyen dosyaların sayısını görüntüler (veya bekleyen tüm dosyalar karşıya yükleniyorken "OneDrive güncel" ifadesini okur).
- Bant genişliği konusunda endişe ediyorsanız veya herhangi bir nedenle karşıya yüklemeyi "duraklatmak" için özelliği Kapalı konuma **geçebilirsiniz.** Özelliği geçici olarak devre dışı bırakmak, Kamera Roll klasörüne yeni dosya ekleyinceye kadar karşıya yükleme kuyruğunda artış devam eder, ancak siz özelliği yeniden etkinleştirene kadar dosyalar karşıya yüklenmez.
- En yeni dosyalar ilk olarak karşıya yüklensin (son, ilk çıkar).
- OneDrive hesabınızla ilgili sorunlar varsa (örneğin, parolanız değiştikten sonra) Ayarlar sayfasında Şimdi düzelt düğmesi görüntülenir. 
- Dosya boyutu üst sınırı yoktur, ancak büyük dosyaların karşıya yüklemesi daha uzun sürer (özellikle karşıya yükleme bant genişliğiniz kısıtlanmışsa). Büyük bir dosya karşıya yüklerken karşıya yükleme işlemini "duraklatır" veya kapatırsanız, karşıya yükleme hemen iptal edilir. Özelliği yeniden etkinleştirdikten sonra karşıya yükleme yeniden başlatılır; Herhangi bir dosyayı kaybetmezsiniz, ancak kısmi karşıya yükleme atılır.

**Bilinen sorunlar ve uyarılar**

- Bu ayar, geçerli bant genişliği kullanımına göre yerleşik azaltmaya sahip değil. Başka bir senaryo için bant genişliğini en üst düzeye çıkarmanız gerekirse ayarı el ile kapatın. Karşıya yükleme duraklatılır, ancak özellik Yeni eklenen dosyaları Kamera Roll'e izlemeye devam eder. Devam etmek için hazır olduğunda karşıya yüklemeyi yeniden etkinleştirin.
- Bu özellik cihaza her kullanıcı hesabı için etkinleştirilmelidir ve yalnızca o anda cihazda oturum açık olan kullanıcı için dosyaları etkin bir şekilde karşıya yükleyebilir.
- Ayarlar sayfasındaki karşıya yükleme sayısını izlerken fotoğraf veya video sürüyorsanız, geçerli dosya karşıya yükleme tamamlanana kadar bekleyen dosya sayısı değişmeyebilirsiniz.
- Cihazınız uykuda düşerse veya kapalı olursa karşıya yükleme duraklatılır. Bekleyen karşıya yüklemelerin tamamlandığından emin olmak için Ayarlar sayfası "OneDrive güncel" olana kadar cihazı etkin bir şekilde kullanın veya Power & **ayarlarını** yapın.

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlama
> [!NOTE]
> Yakın zamanda güncelleştirme yaptıysanız lütfen durumu güncelleştirmek ve en son derlemeyi almak için cihazınızı yeniden başlatın.
> - "Cihazı yeniden başlat" sesli komutu iyi çalışıyor. 
> - Yeniden başlat düğmesini Ayarlar/Windows Insider Programı.
>
> Arka uçta karşılaşmış olduğunuz bir hata vardı ve bu sizi yeniden takip ediyor olacak.

HoloLens 2 cihazında Ayarlar  >  **Güncelleştirmesi & Security**  >  **Windows Insider Programı'e** gidin ve Kullanmaya başlayın. Hesap olarak kaydetmek için kullanılan hesabı Windows Insider.
Windows insider artık Kanallar'a taşınıyor. Hızlı **halka** Geliştirme **Kanalı,** Yavaş  halka Beta Kanal olur **ve** **Yayın** Önizleme halkası Yayın Önizleme Kanalı **olur.** Eşleme şu şekildedir: Windows Insider Kanallar açıklaması Daha fazla bilgi için ![ ](images/WindowsInsiderChannels.png) bkz. Windows [Bloglarında Windows Insider Kanallarına](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Tanıtma.
Ardından, **Windows'un** etkin geliştirmesi'yi seçin, **Geliştirme** Kanalı'nın mı yoksa derlemelerin **mi** Beta Kanal ve program koşullarını gözden geçirmeyi seçin.
Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin. Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.
### <a name="update-error-0x80070490-work-around"></a>Hata güncelleştirme 0x80070490 çalışma
Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli çalışmalara bakın. Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.
#### <a name="stage-one---release-preview"></a>1. Aşama - Yayın Önizlemesi
1.  Ayarlar, Güncelleştirme & Güvenlik, Windows Insider Programı Yayın Önizleme **Kanalı'Windows Insider Programı seçin.**
2.  Ayarlar, Güncelleştirme & Güvenlik, Windows Update, **Güncelleştirmeleri denetleme.** Güncelleştirmeden sonra ikinci aşamaya devam et.
#### <a name="stage-two---dev-channel"></a>Aşama iki - Geliştirme Kanalı
1. Ayarlar, Güncelleştirme & Güvenlik, Windows Insider Programı Dev **Channel'ı seçin.**
2. Ayarlar, Güncelleştirme & Güvenlik, Windows Update, **Güncelleştirmeleri denetleme.**
## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve flash yönler
Uçuş imzalı ffu ile test etmek için, uçuş imzalı ffu'nun yanıp sönmeden önce cihazınızın kilidinin açılması gerekir.
1. Pc'de:
    1. ffu'dan bilgisayarınıza [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) indirin.
    
    1. arc (Gelişmiş Kurtarma Yardımcı) yükleme Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. HoloLens - Flight Unlock'da: **Ayarlar**  >  **Güncelleştirmesi'& Güvenlik**  >  **Windows Insider Programı** açın ve cihazı yeniden başlatın.
1. Flash FFU - Artık ARC kullanarak uçuş imzalı FFU'nun flash'unu sönersiniz.
### <a name="provide-feedback-and-report-issues"></a>Geri bildirim sağlama ve sorunları bildirme
Geri bildirim [ve Geri Bildirim Merkezi için](hololens-feedback.md) lütfen HoloLens'inizin Geri Bildirim Merkezi uygulamasını kullanın. Bu Geri Bildirim Merkezi, mühendislerimizin hızla hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgileri dahil edilir.  HoloLens'in Çince ve Japonca sürümüyle ilgili sorunlar da aynı şekilde bildiriliyor.
> [!NOTE]
> Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).
## <a name="note-for-developers"></a>Geliştiriciler için not
HoloLens'in Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemek hoş geldiniz ve teşvik edilir.  Çalışmaya başlamaya [için HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz. Bu yönergeler HoloLens'in Insider derlemeleriyle de çalışır.  HoloLens geliştirmesi için zaten Visual Studio Unity ve Visual Studio derlemelerini kullanabilirsiniz.
## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdurma
Artık Windows Holographic'in Insider derlemelerini almak istemiyorsanız, HoloLens'iniz bir üretim derlemesi [](hololens-recovery.md) çalıştırılmasa da, cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarmak için Gelişmiş Kurtarma Yardımcı'sı kullanarak cihazınızı kurtarabilirsiniz.
> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır. Daha sonra, cihazlarını el ile kurtarmaları gerekir. Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
HoloLens'inizin bir üretim derlemesi çalıştırıyor olduğunu doğrulamak için:
1. **Ayarlar'a > System > Hakkında'ya** gidin ve derleme numarasını bulun.
1. [Üretim derleme numaraları için sürüm notlarına bakın.](hololens-release-notes.md)
Insider derlemelerini geri almak için:
1. Üretim derlemesi çalıştıran bir HoloLens'de Ayarlar **> Update & Security > Windows Insider Programı**'a gidin ve Insider derlemelerini **durdur'u seçin.**
1. Cihazınızı geri almak için yönergeleri izleyin.
