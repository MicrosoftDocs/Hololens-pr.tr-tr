---
title: İşlerinizi çalıştırmak için sesinizi HoloLens
description: Bu Cortana komutları, dikte ve hologram etkileşimleri gibi karma gerçeklik HoloLens her türlü şeyi nasıl yapabilirsiniz?
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036279"
---
# <a name="use-your-voice-to-operate-hololens"></a>İşlerinizi çalıştırmak için sesinizi HoloLens

Sesinizi kullanarak hızlı bir fotoğraf HoloLens uygulama açma gibi neredeyse her şeyi yapabiliriz. Ses komutlarının çoğu HoloLens, diğerleri de Cortana.

Bu makale, sesinizi ve HoloLens ile holografik dünyanızı denetlemeyi Cortana.

> [!NOTE]
> Konuşma yalnızca bazı [dillerde de destekleni.](hololens2-language-support.md) Konuşma dili, klavye Windows değil görüntüleme dilini temel alan bir dildir.  
>  
> Saat ve Dil Windows'yi seçerek Ayarlar  >  **dilini**  >  **doğruabilirsiniz.**

## <a name="built-in-voice-commands"></a>Yerleşik sesli komutlar

Bu temel HoloLens daha hızlı bir şekilde iş yapabilirsiniz. Bunları kullanmak için cihazın ilk çalıştırması sırasında veya Gizlilik Konuşmasında **Konuşma'Ayarlar**  >    >  **etkinleştirmeniz gerekir.** Konuşmanın etkin olup olmadığını her zaman kontrol etmek için konuşmanın üst kısmından durumuna Başlat menüsü. En iyi konuşma tanıma sonuçları için HoloLens 2, Microsoft bulut tabanlı hizmetleri kullanır. Ancak, bu özelliği devre Ayarlar için Ayarlar kullanabilirsiniz. Bunu yapmak için, Ayarlar Konuşma **tanıma'Ayarlar'i kapatın.** Bu ayarı değiştirdikten sonra, HoloLens 2 yalnızca komutları ve dikteyi tanımak için ses verilerini yerel olarak işler ve Cortana kullanılamaz.

### <a name="general-speech-commands"></a>Genel konuşma komutları

Daha hızlı bir şekilde Windows Mixed Reality için bu komutları kullanın. Bazı komutlar, "seç" deerek getirdiğiniz bakış imlecini kullanır.

> [!NOTE]
> El rayları, HoloLens (1. Nesil) için desteklenmiyor.

| Bunu söyle | Bunu yapmak için |
| - | - |
| "Seç" | Bakış imlecini getirmek için "seç" diyelim. Ardından, imleci seçmek istediğiniz şeyin üzerine konumlandırmak için başını döndür ve tekrar "seç" de. |
| "Başla" |  Başlangıç menüsünü açma |
| "Kapat"  | Başlat menüsü |
| Hızlı eylemler menüsünü getirmek için "Başla"ya ve ardından "Karma gerçeklik giriş" diyelim.  | Çevreleyici bir uygulama bırakma |
| "Hide hand ray" / "Show hand ray" | El ışığını gizleme ve gösterme |
| "Ne diyoruz?"  | Kullanılabilir konuşma komutlarını görme |

HoloLens 2'nin 19041.x sürümünden itibaren şu komutları da kullanabilirsiniz:

| Bunu söyle | Bunu yapmak için |
| - | - |
| "Cihazı yeniden başlat" | Cihazı yeniden başlatmak istediğinizi onaylamak için bir iletişim açın. Yeniden başlatmak için "evet" diyoruz. |
| "Cihazı kapatma" | Cihazı kapatmak istediğinizden onaylamak için bir iletişim açın. Onaylamak için "evet" diyoruz. |
| "Brightness up/down" | Ekran parlaklığını %10 artır veya azalt. |
| "Birim yukarı/aşağı" | Birimi %10 artır veya azalt. |
| "IP adresim nedir" | Yerel ağ üzerinde cihazınızın geçerli IP adresini görüntüleyen bir iletişim açın. |
| "Fotoğraf çek" | Şu anda gördüklerinin karma gerçeklik fotoğrafını çekin. |
| "Video al" | Karma gerçeklik videosunu kaydetmeye başlama. | 
| "Kaydı durdur" | Devam eden bir karma gerçeklik video kaydını durdurur. |

### <a name="hologram-commands"></a>Hologram komutları

Bu komutları kullanmak için 3D nesne, hologram veya uygulama penceresine göz atabilirsiniz.

| Bunu söyle | Bunu yapmak için |
| - | - |
| "Daha büyük" | Daha büyük hale |
| "Daha küçük" | Daha küçük hale |
| "Benimle yüz yüze" | Yüz yüze gelecek şekilde döndür |
| "Bunu taşı" | Taşı (bakışlarınızı izleyin) |
| "Kapat" | Kapat |
| "Beni takip et" / "Takip etmeyi durdur" | Hareket ederken sizi takip ettirin |

### <a name="see-it-say-it"></a>Gör, söyle

Uygulama çubuğundaki beni HoloLens kapat veya Edge'de Geri düğmesi gibi  birçok düğme ve diğer  öğeler de sesinize yanıt verir.  Bir düğmenin ses etkin olup olduğunu bulmak için, bakış imlecinizi, **dokunma** imlecinizi veya bir **el imleci** üzerinde bir süre tutun. Düğme ses etkinse bir ses ipucuyla karşınız olur.

### <a name="dictation-mode"></a>Dikte modu

Yazmaktan sıkıldınız mı? Holografik klavyenin etkin olduğu her durumda dikte moduna geçiş yapabilirsiniz. Başlamak için mikrofon düğmesini seçin veya "Dikte etmeye başla" diyelim. Dikteyi durdurmak için düğmeyi yeniden seçin veya "Dikteyi durdur" diyelim. Az önce dikte ettiğiniz şeyi silmek için "Bunu sil" diyelim. 

> [!NOTE]
> Dikte modunu kullanmak için bir İnternet bağlantınız gerekir.

HoloLens, kullanmak istediğiniz noktalama işaretlerinin adını söylemeniz anlamına gelen açık noktalama işaretlerini kullanır. Örneğin, "Hey virgül **ne kadar** soru işaretine **sahipsiniz" deebilirsiniz.**

Kullanabileceğiniz noktalama işaretleri şu şekildedir:

- Nokta, virgül, soru işareti, ünlem işareti/ünlem işareti
- Yeni satır/yeni paragraf
- Noktalı virgül, iki nokta üst üste
- Açık tırnaklar, kapanış teklifleri
- Diyez etiketi, gülen/gülen yüz, kaş çatma, winky
- Dolar, yüzde

Bazen e-posta adresleri gibi şeyleri hecelemeniz faydalı olabilir. Örneğin, 'i dikte example@outlook.com etmek için "Outlook dot com'da E X A M P L E" deyebilirsiniz.

## <a name="do-more-with-cortana"></a>Cortana ile daha fazlasını Cortana

Cortana hizmetiniz üzerinde her türlü şeyi HoloLens yardımcı olabilir, ancak kullandığınız Holographic Windows sürümüne bağlı olarak özellikler farklı olabilir. Cortana'ın en son sürümünün güncelleştirilmiş özellikleri hakkında daha fazla bilgi edinmek Cortana edinebilir: Windows 10 sürümü: gelişmiş güvenlik ve gizlilik ile üretkenliğinize [odaklanan.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/) 

![Hey Cortana!](images/cortana-on-hololens.png)

işte deneyebileceğiniz bazı şeyler aşağıda verilmiştir (önce "Hey Cortana" söylediğini unutmayın).

**Hey, Cortana**...

- What can I say? (Ne söyleyebilirim?)
- <*app name*> başlatın.
- Saat kaç?
- En son NBA puanlarını göster.
- Bana bir fıkra anlat.

*18362. x veya önceki bir sürümü* kullanıyorsanız, bu komutları da kullanabilirsiniz:

**Hey, Cortana**...

- Birimi artırın.
- Parlaklığı azaltın.
- Kapat'ı seçin.
- Yeniden başlatın.
- Uyu.
- Mikrofon.
- <*app name*> buraya taşıyın (uygulamanın taşınmasını istediğiniz noktada).
- Başlat'a gidin.
- Bir resim alın.
- Kaydı başlatın. (Video kaydetmeye başlar.)
- Kaydı Durdur. (Video kaydetmeyi durduruyor.)
- Ne kadar pil kaldı?

bilgisayarınızda veya telefonunuzdaki Windows (örneğin, anımsatıcılar ve bildirimler) Cortana kullandığınız bazı özellikler Microsoft HoloLens desteklenmez ve Cortana deneyimi bir bölgeden diğerine farklılık gösterebilir.

### <a name="turn-cortana-off"></a>Cortana kapat

Cortana, konuşmayı etkinleştirdiğinizde HoloLens ilk kez kullanılır. Cortana ayarları ' nda devre dışı bırakabilirsiniz. **tüm uygulamalar** listesinde **Cortana**  >  **Ayarlar**' ni seçin. Cortana kapatmak için öneriler, fikirler, anımsatıcılar, uyarılar ve daha fazlasını kullanabilirsiniz.

Cortana "Hey Cortana" yanıt vermiyorsa, konuşma 'nın başlangıç sırasında etkin olup olmadığını denetleyin ve Cortana ayarları ' na gidin ve göründüğünden emin olun.
