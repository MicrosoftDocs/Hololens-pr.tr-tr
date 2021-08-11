---
title: Bağlan VE USB-C Bluetooth'ye ve
description: Kullanmaya başlayın gerçeklik cihazlarından Bluetooth USB-C cihazlarına ve HoloLens cihazlarına bağlanmanızı sağlar.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1e478e366b8ad70243f6fffc47cd62e847af837637a992ebb60fc80bf6774186
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664297"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bağlan VE USB-C Bluetooth'ye ve

## <a name="pair-bluetooth-devices"></a>Cihaz Bluetooth eşleştirme

HoloLens 2, aşağıdaki Bluetooth destekler:

- [SİYAD:](/windows-hardware/drivers/hid/)
    - Fare
    - Klavye
- Ses çıkışı (A2DP) cihazları

HoloLens 2 aşağıdaki api'Bluetooth destekler:
- GATT [Sunucusu](/windows/uwp/devices-sensors/gatt-server) ve [İstemcisi](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> ASLıNDA WINDOWS ve GATT cihazlarını kullanmak için Microsoft Store yardımcı uygulamaları yüklemeniz gerekir.

HoloLens (1. nesil) aşağıdaki Bluetooth destekler:

- Fare
- Klavye
- [HoloLens (1. nesil) tıkıcı](hololens1-clicker.md)

> [!NOTE]
> Konuşmacılar, Bluetooth, akıllı telefonlar ve oyun pad'leri gibi diğer cihaz türleri, HoloLens kullanılabilir olarak listelenmiş olabilir. Ancak, bu cihazlar HoloLens (1. nesil) için destek değildir. Daha fazla bilgi HoloLens Ayarlar için bkz. cihazları kullanılabilir [olarak listeler, ancak cihazlar çalışmıyor.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Klavye veya Bluetooth eşleştirme

1. Klavyenizi veya farenizi açarak keşfedilebilir hale sürükleyin. Cihazın bulunabilir hale nasıl geleceklerini öğrenmek için cihazla ilgili bilgileri (veya belgelerini) inceleyin veya üreticinin web sitesini ziyaret edin.

1. Başlat 'a gitmek için bloom HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) kullanın ve ardından **Ayarlar.**

1. **Cihazlar'ı** seçin ve Bluetooth emin olun.  

1. Cihaz adını gördüğünüzde **Eşleştir'i seçin** ve yönergeleri izleyin.

## <a name="disable-bluetooth"></a>Devre dışı Bluetooth

Bu yordam, Bluetooth radyonun RF bileşenlerini devre dışı Bluetooth tüm Microsoft HoloLens.

1. Başlat 'a gitmek HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) kullanın ve ardından Cihazlar'ı **Ayarlar**  >  **seçin.**

1. Geçiş için kaydırıcı anahtarını **Bluetooth** **konuma** getirin.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Bağlan USB-C cihazları

HoloLens 2, aşağıdaki USB-C cihaz sınıflarını destekler:

- Yığın depolama cihazları (örneğin, parmak sürücüleri)
- Ethernet bağdaştırıcıları (ethernet artı ücretlendirme dahil)
- USB-C-3,5mm dijital ses bağdaştırıcıları
- USB-C dijital ses başlığı (mikrofonlu bağdaştırıcılar ve ücretlendirme dahil)
- USB-C Dış Mikrofonlar ([Windows Holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha yüksek)
- Kablolu fare
- Kablolu klavye
- PD hub'larını karma (USB A artı PD ücretlendirme)


> [!NOTE]
> Müşteri geri bildirimlerine yanıt olarak, USB-C aracılığıyla doğrudan cihaza bağlı hücresel bağlantı için HoloLens desteği etkinleştirildi. Daha [Bağlan için bkz. Hücresel ve 5G'ye](hololens-cellular.md) bağlantı.

### <a name="usb-c-external-microphone-support"></a>USB-C Dış Mikrofon Desteği

> [!IMPORTANT]
> BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.** Kullanıcılar bir USB-C kulaklık kümesine takılıyken, mikrofonlu cihazın sesinin otomatik olarak mikrofona yeniden yönlendirilmesine neden olduğunu gözlemler, ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazlarından yüksek önceliklendirmektedir. **USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**

> [!NOTE]
> [Holographic, sürüm 21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve Windows önce derlemelerde dış mikrofonlar kullanılamaz. 

Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz. USB-C mikrofonları arama, kayıt vb. için kullanılabilir.

Ayarlar **uygulamasını** açın ve Sistem **Sesi'ne**  >  **seçin.**

![Ses Ayarlar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.
>
> Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.** **Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.
>
> İletişim **Varsayılanı'nın** seçerek dış mikrofon Remote Assist ve diğer iletişim uygulamaları için kullanılacak ancak HoloLens mikrofon dizisi diğer görevler için de kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlama](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Mikrofon desteği Bluetooth ne olacak?

Ne yazık Bluetooth mikrofonlar henüz 2. HoloLens destek HoloLens.

### <a name="usb-c-hubs"></a>USB-C Hub'ları

Bazı kullanıcıların aynı anda birden çok cihaza bağlanması gerekir. [USB-C](#usb-c-external-microphone-support) mikrofonunu başka bir bağlı cihazla birlikte kullanmak isteyen kullanıcılar için, USB-C hub'ları müşterinin ihtiyaçlarına uygun olabilir. Microsoft bu cihazları test edilmemiştir ve herhangi bir marka önerilmez.

**USB-C hub'ı ve bağlı cihazlar için gereksinimler:**

- Bağlı cihazların bir sürücünün yüklü olması gerekli değildir.
- Bağlı tüm cihazların toplam güç çekimi 4,5 Watt'ın altında olması gerekir.

## <a name="connect-to-miracast"></a>Bağlan Miracast

Bu Miracast için şu adımları izleyin:

1. Aşağıdakilerden birini yapın:  

   - Başlat **menüsünü** açın ve Görüntü **simgesini** seçin.
   - Başlat Bağlan bakarken "Bağlan" **diyelim.**  

1. Görüntülenen cihaz listesinde kullanılabilir bir cihaz seçin.

1. Eşleştirmeyi tamamlar ve projeye başlar.
