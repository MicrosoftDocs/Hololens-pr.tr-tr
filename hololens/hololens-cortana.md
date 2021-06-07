---
title: HoloLens 'i çalıştırmak için sesinizi kullanın
description: Cortana 'Nın, ses komutları, dikte ve hologram etkileşimleri dahil, HoloLens karma gerçeklik cihazlarınızda her türlü şeyi nasıl sağlayabileceğinize nasıl yardımcı olabileceğini öğrenin.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380241"
---
# <a name="use-your-voice-to-operate-hololens"></a>HoloLens 'i çalıştırmak için sesinizi kullanın

Sesinizi, hızlı bir fotoğraf alma veya uygulama açma gibi HoloLens üzerinde neredeyse her şey yapmak için kullanabilirsiniz. Birçok sesli komut HoloLens 'te yerleşiktir, diğerleri Cortana aracılığıyla kullanılabilir.

Bu makalede, HoloLens ve holographic dünyayı sesli ve Cortana ile nasıl denetleyeceğini öğretilir.

> [!NOTE]
> Konuşma yalnızca [bazı dillerde](hololens2-language-support.md)desteklenir. Konuşma dili, klavye dilini değil Windows görüntüleme diline dayalıdır.  
>  
> **Ayarlar**  >  **saat ve dil**  >  **dili**' ni seçerek Windows görüntüleme dilini doğrulayabilirsiniz.

## <a name="built-in-voice-commands"></a>Yerleşik sesli komutlar

Bu temel komutlarla HoloLens 'in etrafında daha hızlı yararlanın. Bunları kullanabilmeniz için, cihazın ilk çalıştırma sırasında veya **Ayarlar**  >  **Gizlilik**  >  **konuşma**' da konuşmayı etkinleştirmeniz gerekir. Başlangıç menüsünün en üstündeki duruma bakarak, konuşma özelliğinin etkinleştirilip etkinleştirilmeyeceğini her zaman denetleyebilirsiniz. En iyi konuşma tanıma sonuçları için, HoloLens 2 Microsoft bulut tabanlı Hizmetleri kullanır. Ancak, bu özelliği devre dışı bırakmak için ayarları kullanabilirsiniz. Bunu yapmak için ayarlar ' da **Çevrimiçi konuşma tanımayı** devre dışı bırakın. Bu ayarı değiştirdikten sonra, HoloLens 2, yalnızca komutları ve dikte etmeyi tanımak için ses verilerini yerel olarak işler ve Cortana kullanılamayacak.

### <a name="general-speech-commands"></a>Genel konuşma komutları

Daha hızlı bir şekilde yararlanmak için Windows Mixed Reality genelinde bu komutları kullanın. Bazı komutlar "Select" diyerek elde ettiğiniz Gaze imlecini kullanır.

> [!NOTE]
> HoloLens (1. gen) üzerinde el ışınları desteklenmez.

| Bunu söyleyin | Bunu yapmak için |
| - | - |
| Seçin | Gaze imlecini getirmek için "Seç" deyin. Ardından, imleci seçmek istediğiniz şey üzerine konumlandırmak için kafanızı açın ve "Seç" i yeniden söyleyin. |
| "Başlangıç 'a git" |  Başlangıç menüsünü açma |
| ~Eksik  | Başlat menüsünü kapat |
| Hızlı Eylemler menüsünü açmak için "Başlat 'a git" deyin ve "Karma Gerçeklik ana" deyin.  | Tam ekran uygulama bırakma |
| "El ışını gizle"/"el ışını göster" | Hand Ray 'ı gizleme ve gösterme |
| "Ne söyleyebilirim?"  | Bkz. kullanılabilir konuşma komutları |

HoloLens 2 sürümü 19041. x sürümünden başlayarak şu komutları da kullanabilirsiniz:

| Bunu söyleyin | Bunu yapmak için |
| - | - |
| "Cihazı yeniden Başlat" | Cihazı yeniden başlatmak istediğinizi onaylamak için bir iletişim kutusu açın. Yeniden başlatmak için "Evet" söyleyebilirsiniz. |
| "Cihaz kapatılıyor" | Cihazı kapatmak istediğinizi onaylamak için bir iletişim kutusu açın. Onaylamak için "Evet" diyebilirsiniz. |
| "Parlaklığı artırma/azaltma" | Ekran parlaklığını %10 oranında artırın veya azaltın. |
| "Birim yukarı/aşağı" | %10 oranında birimi artırın veya azaltın. |
| "IP adresim nedir?" | Cihazınızın yerel ağda geçerli IP adresini görüntüleyen bir iletişim kutusu alın. |
| "Resim al" | Şu anda gördüğünüzü karma gerçeklik fotoğrafını yakalayın. |
| "Video al" | Karma Gerçeklik videosunu kaydetmeye başlayın. | 
| "Kaydı Durdur" | Devam eden bir varsa geçerli karma gerçeklik video kaydını sonlandırır. |

### <a name="hologram-commands"></a>Hologram komutları

Bu komutları kullanmak için 3B nesne, hologram veya uygulama penceresinde Gaze.

| Bunu söyleyin | Bunu yapmak için |
| - | - |
| Karakterli | Daha büyük hale getirin |
| Artı | Daha küçük hale getirin |
| "Yüz bana" | Bunu sizin için etkinleştirin |
| "Bunu taşı" | Taşıyın (Gaze 'ı izleyin) |
| ~Eksik | Kapat |
| "Takip et"/"İzlemeyi Durdur" | Siz hareket ettiğiniz sırada takip edin |

### <a name="see-it-say-it"></a>Görüntüleyin, söyleyin

HoloLens 'teki pek çok düğme ve diğer öğe da sesinize yanıt verir — örneğin, uygulama çubuğunda **beni takip et** ve **Kapat** ' ı veya kenar düğmesini uç düğmesine **geri** götür. Bir düğmenin ses özellikli olup olmadığını öğrenmek için, biraz bekleyin **imlecinizi**, **dokunmatik imlecinizi** veya bir arada bir tek bir **ışını** geri çevirin. Düğme ses etkinse, bir ses ipucu görürsünüz.

### <a name="dictation-mode"></a>Dikte etme modu

Ne kadar yordunuz? Holographic klavyesi etkin olduğunda dikte moduna geçin. Başlamak için mikrofon düğmesini seçin veya "dikte başlatma" deyin. Dikte etmek için düğmeyi yeniden seçin veya "dikte etme Durdur" deyin. Az önce dikte ettiğiniz şeyi silmek için, "Delete The" deyin. 

> [!NOTE]
> Dikte modunu kullanmak için bir internet bağlantınızın olması gerekir.

HoloLens dikte açık noktalama kullanır, yani kullanmak istediğiniz noktalama işaretlerinin adını söylemeniz gerekir. Örneğin, "her ne kadar **soru işaretine** **kadar selam"** diyebilirsiniz.

Kullanabileceğiniz noktalama anahtar sözcükleri burada bulabilirsiniz:

- Nokta, virgül, soru işareti, ünlem işareti/ünlem işareti
- Yeni satır/yeni paragraf
- Noktalı virgül, iki nokta
- Tırnak (lar) aç, tırnak kapatma
- Diyez etiketi, gülen adam/gülen yüz, çili
- Dolar, yüzde

Bazen e-posta adresleri gibi şeyler için yazım denetimi yapmak faydalı olabilir. Örneğin, dikte etmek için example@outlook.com "Outlook nokta com ' da" e X a m P L e "deyin.

## <a name="do-more-with-cortana"></a>Cortana ile daha fazlasını yapın

Cortana, HoloLens 'te her türlü şeyi yapmanıza yardımcı olabilir, ancak kullandığınız Windows holographic sürümüne bağlı olarak yetenekler farklı olabilir. En son Cortana sürümünün güncelleştirilmiş özellikleri hakkında daha fazla bilgi edinebilirsiniz: [yakında çıkacak Windows 10 sürümünde Cortana: Gelişmiş güvenlik ve gizlilik sayesinde üretkenliğinizi odaklanın](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![Hey Cortana!](images/cortana-on-hololens.png)

Burada bazı şeyler söylemeyi denemeyi diyoruz (önce "Hey Cortana" dey).

**Cortana...**

- What can I say? (Ne söyleyebilirim?)
- Uygulama <*adını>.*
- Saat kaç?
- Bana en son NBA puanlarını göster.
- Bana bir fıkra anlat.

*18362.x veya* önceki bir sürümü kullanıyorsanız şu komutları da kullanabilirsiniz:

**Cortana...**

- Birimi artırma.
- Parlaklığı azaltın.
- Kapat'ı seçin.
- Yeniden başlatın.
- Uyu.
- Sessiz.
- Uygulama <*adını* buraya> (uygulamanın taşınmak istediğiniz noktaya bakabilirsiniz).
- Başlat'a gidin.
- Bir resim çek.
- Kaydı başlatma. (Video kaydetmeye başlar.)
- Kaydı durdurun. (Video kaydetmeyi durdurur.)
- Ne kadar pil kaldı?

Bilgisayarınızda veya telefonda Windows'dan kullandığınız bazı Cortana özellikleri (örneğin, anımsatıcılar ve bildirimler) Microsoft HoloLens'de desteklenmiyor ve Cortana deneyimi bir bölgeden diğerine farklılık gösterebilir.

### <a name="turn-cortana-off"></a>Cortana'yı kapatma

Cortana, HoloLens'i ilk kez konuşma etkinleştiriyorsanız kullanır. Cortana'nın ayarlarından onu kapatabilirsiniz. Yeni **Tüm uygulamalar** Cortana Ayarları'yı   >  **seçin.** Cortana'yı kapatmak size öneriler, fikirler, anımsatıcılar, uyarılar ve daha fazlasını sağlar.

Cortana "Hey Cortana" yanıt vermiyorsa Başlat'ta konuşmanın etkinleştirildiğinden emin olun, Cortana'nın ayarlarına gidin ve etkin olduğundan emin olun.
