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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924375"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider önizlemesi

HoloLens için en son Insider Preview derlemesine hoş geldiniz! HoloLens için [bir sonraki büyük](hololens-insider.md#start-receiving-insider-builds) işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamak ve çalışmaya başlamanız oldukça kolaydır.

## <a name="windows-insider-release-notes"></a>Windows Insider Sürüm Notları

Windows Insider'lara yeni özelliklerle yeniden uçuş yapmaya başlamak için heyecanlanıyoruz. En son güncelleştirmeler için yeni derlemeler Geliştirme ve Beta Kanallarına sunulacaktır. Yeni derlemelerimize daha fazla özellik ve güncelleştirme eklerken bu sayfayı Windows Insider devam edeceğiz. Bu güncelleştirmeleri gerçekliğinize karıştırmak için heyecan ve hazır olun. 

### <a name="csp-changes-on-hololens"></a>HoloLens'de CSP değişiklikleri
 
- Windows Insider derlemesinde tanıtıldı, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP artık HoloLens cihazında boş depolama alanı da rapor ediyor. Bu değer, Ayarlar Uygulamasının Depolama sayfasında gösterilen değerle yaklaşık olarak eşleşmesi gerekir. Aşağıda, bu bilgileri içeren belirli bir düğüm ve ardından yer alan düğümler yer aleladedir.

- ./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP artık HoloLens'in etkin olarak bağlı olduğu WiFi ağının SSID ve BSSID'lerini de rapor ediyor. Aşağıda bu bilgileri içeren belirli düğümler yer almaktadır.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac adresi Wi-Fi bağdaştırıcısı*/BSSID

NetworkIdentifiers sorgulamak için örnek syncml blobu (MDM satıcıları için)

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Düzeltmeler ve geliştirmeler:

- Kilitlenmiş [dosyaların indir Cihaz Portalı isteminin olmadığının bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Dosya yükleme [ve indirme zaman Cihaz Portalı için bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

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
Tamamlamak **için > Şimdi Yeniden Başlat'ı** seçin. Cihazınız yeniden başlatıldıktan sonra, en son **derlemeyi almak için Ayarlar > Güncelleştirme & Güvenlik > Güncelleştirmeleri** denetleme'ye gidin.
### <a name="update-error-0x80070490-work-around"></a>Hata güncelleştirme 0x80070490 çalışma
Geliştirme veya Beta kanalında 0x80070490 bir güncelleştirme hatasıyla karşılaşırsanız aşağıdaki kısa vadeli çalışmalara bakın. Bunun için iç kanalınızı taşımanız, güncelleştirmeyi alıp Insider kanalınızı geri taşımanız gerekir.
#### <a name="stage-one---release-preview"></a>1. aşama - Yayın Önizlemesi
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
Geri bildirim [ve Geri Bildirim Merkezi için](hololens-feedback.md) lütfen HoloLens'inizin Geri Bildirim Merkezi uygulamasını kullanın. Bu Geri Bildirim Merkezi, mühendislerimizin hata ayıklaması ve sorunu çözmesine yardımcı olmak için tüm gerekli tanılama bilgilerine dahil edilir.  HoloLens'in Çince ve Japonca sürümüyle ilgili sorunlar da aynı şekilde bildiriliyor.
> [!NOTE]
> Belgeler klasörünüze erişmek isteyip Geri Bildirim Merkezi istemini kabul edin (istendiğinde **Evet'i** seçin).
## <a name="note-for-developers"></a>Geliştiriciler için not
HoloLens'in Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemek hoş geldiniz ve teşvik edilir.  Çalışmaya başlamaya [için HoloLens Geliştirici Belgeleri'ne](https://developer.microsoft.com/windows/mixed-reality/development) göz atabilirsiniz. Aynı yönergeler HoloLens'in Insider derlemeleriyle de çalışır.  HoloLens geliştirme için zaten Visual Studio Unity ve Visual Studio derlemelerini kullanabilirsiniz.
## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdurma
Artık Windows Holographic'in Insider derlemelerini almak istemiyorsanız, HoloLens'iniz bir üretim derlemesi [](hololens-recovery.md) çalıştırılmasa da, cihazınızı Windows Holographic'in Insider olmayan bir sürümüne kurtarmak için Gelişmiş Kurtarma Yardımcı'sı kullanarak cihazınızı kurtarabilirsiniz.
> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydını kaldıran kullanıcıların mavi ekranla karşına çıkar olduğu bilinen bir sorun vardır. Daha sonra, cihazlarını el ile kurtarmaları gerekir. Etkide olup olmadığınız hakkında tüm ayrıntılar için bu Bilinen Sorun hakkında daha fazla [bilgi edinebilirsiniz.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
HoloLens'inizin bir üretim derlemesi çalıştırarak çalıştığını doğrulamak için:
1. **Ayarlar'a > System > Hakkında'ya** gidin ve derleme numarasını bulun.
1. [Üretim derleme numaraları için sürüm notlarına bakın.](hololens-release-notes.md)
Insider derlemelerini geri almak için:
1. Üretim derlemesi çalıştıran bir HoloLens'de Ayarlar **> Update & Security > Windows Insider Programı**'a gidin ve Insider derlemelerini **durdur'u seçin.**
1. Cihazınızı geri almak için yönergeleri izleyin.
