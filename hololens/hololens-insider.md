---
title: Microsoft HoloLens için Insider Preview
description: Insider Derlemeleriyle çalışmaya başlama ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmemiz için değerli geri bildirim sağlama hakkında bilgi edinin.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977230"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Microsoft HoloLens için Insider Preview

HoloLens için en son Insider Preview yapılarına hoş geldiniz! Daha kolay [çalışmaya](hololens-insider.md#start-receiving-insider-builds) başlamak ve HoloLens için bir sonraki ana işletim sistemi güncelleştirmemiz için değerli geri bildirimler sağlamaktır.

## <a name="windows-insider-release-notes"></a>Windows Insider sürüm notları

Yeni özellikleri Windows Insider 'lar 'a yeniden başlatmak için heyecanlıyız. Yeni derlemeler, en son güncelleştirmeler için geliştirme ve Beta kanallarına uçucaktır. Windows Insider derlemelerimize daha fazla özellik ve güncelleştirme eklediğimiz için bu sayfayı güncelleştirmeye devam edeceğiz. Heyecanlanmanıza ve bu güncelleştirmeleri gerçeğe sunmaya hazırlanın.

| Özellik                 | Açıklama                | Hedef kullanıcılar | Tanıtılan derleme |
|-------------------------|----------------------------|--------------|------------------|
| HoloLens 'te CSP değişiklikleri | Verileri sorgulamak için yeni CSP 'Ler | BT yöneticileri    | 20348,1403                 |

### <a name="csp-changes-on-hololens"></a>HoloLens 'te CSP değişiklikleri

- Windows Insider Build, 20348,1403 ' de tanıtılan

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP artık HoloLens cihazında boş depolama alanı da bildiriyor. Bu, ayarlar uygulamasının depolama sayfasında gösterilen değerle yaklaşık olarak eşleşmelidir. Bu bilgileri içeren belirli düğüm aşağıda verilmiştir.

- ./DevDetail/Ext/Microsoft/FreeStorage (yalnızca GET işlemi)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP 'si

DeviceStatus CSP artık Ayrıca, HoloLens 'in etkin bir şekilde bağlandığı SSID ve WiFi ağının BSSıD 'sini de raporluyor. Bu bilgileri içeren belirli düğümler aşağıda verilmiştir.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*Wi-Fi bağdaştırıcısının MAC adresi*/b SSID 'si

Networktanımlayıcılarına yönelik sorgu için örnek SyncML Blobu (MDM satıcıları için)

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

- Bir [cihaz portalı için, kilitli dosyaları indirmede hiçbir istem olmadığı bilinen bir sorun düzeltildi.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- [Karşıya dosya yükleme ve indirme zaman aşımları Ile cihaz portalı 'nın bilinen bir sorunu düzeltildi.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Insider derlemelerini almaya başlayın
> [!NOTE]
> Son zamanlarda güncelleştirmediyseniz, durumu güncelleştirmek ve en son derlemeyi almak için lütfen cihazınızı yeniden başlatın.
> - "Cihazı yeniden Başlat" ses komutu iyi şekilde çalışmaktadır. 
> - Ayarlar/Windows Insider programı ' nda yeniden Başlat düğmesini de seçebilirsiniz.
>
> Arka uçta karşılaştığınız bir hata yaşadık ve bu, izlemeye geri dönecek.

HoloLens 2 cihazında **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows Insider programı** ' na gidin ve **kullanmaya** başlayın ' ı seçin. Windows Insider olarak kaydetmek için kullandığınız hesabı bağlayın.
Windows Insider artık kanallara taşınıyor. **Hızlı** halka **Geliştirici kanalı** olacaktır, **yavaş** halka **Beta kanalı** olur ve **Yayın Önizleme** halkası **Yayın Önizleme kanalı** olur. Bu, eşlemenin şöyle görünür: ![ Windows Insider Channels açıklaması ](images/WindowsInsiderChannels.png) daha fazla bilgi için bkz. Windows Web günlükleri üzerinde [Windows Insider kanalları tanıtımı](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) .
Ardından, **Windows 'un etkin geliştirmesini** seçin, **geliştirme kanalı** veya **Beta kanalı** derlemeleri almak isteyip istemediğinizi seçin ve program koşullarını gözden geçirin.
**> şimdi yeniden başlatmak Için Onayla** ' yı seçin. Cihazınız yeniden başlatıldıktan sonra **ayarlar > & güvenliği güncelleştirme** ' ye gidin > en son derlemeyi almak Için güncelleştirmeleri denetleyin.
### <a name="update-error-0x80070490-work-around"></a>Güncelleştirme hatası 0x80070490 iş-etrafında
Geliştirme veya beta kanalında güncelleştirme yaparken bir güncelleştirme hatası 0x80070490 ile karşılaşırsanız, aşağıdaki kısa süreli çalışmayı deneyin. Insider kanalınızın taşınmasını, güncelleştirmeyi nasıl çekmesini ve ardından Insider kanalını geri taşımayı içerir.
#### <a name="stage-one---release-preview"></a>Aşama tek sürüm önizlemesi
1.  Ayarlar, güncelleştirme & güvenliği, Windows Insider programı, **sürüm Önizleme kanalı**' nı seçin.
2.  Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**. Güncelleştirme sonrasında, ikinci aşamada devam edin.
#### <a name="stage-two---dev-channel"></a>İkinci geliştirme kanalı aşaması
1. Ayarlar, güncelleştirme & güvenliği, Windows Insider programı, **geliştirme kanalını** seçin.
2. Ayarlar, güncelleştirme & güvenlik Windows Update, **güncelleştirmeleri denetleyin**.
## <a name="ffu-download-and-flash-directions"></a>FFU indirme ve Flash yönleri
Bir uçuş imzalı FFU ile test etmek için önce, uçuşdan ayrılmadan önce cihazınızın kilidini açmanız gerekir.
1. BILGISAYAR üzerinde:
    1. Hesabınızı ' den bilgisayarınıza indirin [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Microsoft Store: ile yay (Gelişmiş kurtarma Yardımcısı) yüklemesini yapın [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. HoloLens üzerinde kilit açma: açık **Ayarlar**  >  **güncelleştirme & güvenlik**  >  **Windows Insider programı** ' nı açın, cihazı yeniden başlatın.
1. Flash FFU-şimdi yay kullanarak uçuştan imzalanmış FFU 'yi yakıp sönebilir.
### <a name="provide-feedback-and-report-issues"></a>Geri bildirim ve rapor sorunları sağlama
Geri bildirim ve rapor sorunları sağlamak için lütfen HoloLens 'teki [geri bildirim Merkezi uygulamasını](hololens-feedback.md) kullanın. Geri Bildirim Hub 'ı kullanmak, mühendislerimizin hata ayıklamasına ve sorunu çözmeye yardımcı olmak için gerekli tüm tanılama bilgilerinin eklenmesini sağlar.  HoloLens 'in Çince ve Japonca sürümündeki sorunlar aynı şekilde bildirilmelidir.
> [!NOTE]
> Belge klasörünüze geri bildirim hub 'ı (sorulduğunda **Evet** ' i seçin) isteyip istemediğinizi soran istemi kabul ettiğinizden emin olun.
## <a name="note-for-developers"></a>Geliştiriciler için göz önünde
Bu hoş geldiniz ve, HoloLens 'in Insider derlemelerini kullanarak uygulamalarınızı geliştirmeyi denemeye teşvik edersiniz.  Başlamak için [HoloLens geliştirici belgelerine](https://developer.microsoft.com/windows/mixed-reality/development) göz atın. Aynı yönergeler, HoloLens 'in Insider Derlemeleriyle birlikte çalışır.  HoloLens geliştirme için kullanmakta olduğunuz Unity ve Visual Studio Derlemeleriyle aynı şekilde yararlanabilirsiniz.
## <a name="stop-receiving-insider-builds"></a>Insider derlemelerini almayı durdur
Artık Windows holographic Insider derlemelerini almak istemiyorsanız, HoloLens 'in bir üretim derlemesi çalıştırması durumunda devre dışı bırakabilirsiniz veya cihazınızı, Gelişmiş kurtarma Yardımcısı 'nı kullanarak [kurtararak](hololens-recovery.md) cihazınızı Windows holographic 'ın Insider sürümüne kurtarabilirsiniz.
> [!CAUTION]
> Yeni bir önizleme derlemesini el ile yeniden yükledikten sonra Insider Preview derlemelerinden kaydolmamış kullanıcıların mavi bir ekran deneymesinin bilinen bir sorunu vardır. Daha sonra cihazlarını el ile kurtarmanız gerekir. Etkilenmiş olmanız veya olmadıysanız ilgili tüm ayrıntılar için lütfen bu [bilinen sorunu](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)izleyin.
HoloLens 'in bir üretim derlemesi çalıştırdığından emin olmak için:
1. **Ayarlar > sistem > hakkında**' ya gidin ve derleme numarasını bulun.
1. [Üretim derleme numaraları için sürüm notlarına bakın](hololens-release-notes.md).
Insider derlemelerini devre dışı bırakmak için:
1. Üretim yapısını çalıştıran bir HoloLens üzerinde, **ayarlar > güncelleştirme & güvenlik > Windows Insider programı**' na gidin ve **Insider derlemelerini durdur**' u seçin.
1. Cihazınızı devre dışı bırakmak için yönergeleri izleyin.
