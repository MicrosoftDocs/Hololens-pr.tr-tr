---
title: Bluetooth ve USB-C cihazlarına bağlanma
description: Kullanmaya başlayın HoloLens karma gerçeklik cihazlarından Bluetooth ve USB-C cihazlarına ve donatılarına bağlanmanızı sağlar.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2021
ms.locfileid: "111380243"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bluetooth ve USB-C cihazlarına bağlanma

## <a name="pair-bluetooth-devices"></a>Bluetooth cihazlarını eşleştirme

HoloLens 2, aşağıdaki Bluetooth cihaz sınıflarını destekler:

- [SİYAD:](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Fare
    - Klavye
- Ses çıkışı (A2DP) cihazları

HoloLens 2 aşağıdaki Bluetooth API'lerini destekler:
- GATT [Sunucusu](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) ve [İstemcisi](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> ASLıNDA WINDOWS ve GATT cihazlarını kullanmak için Microsoft Store yardımcı uygulamaları yüklemeniz gerekir.

HoloLens (1. nesil), aşağıdaki Bluetooth cihaz sınıflarını destekler:

- Fare
- Klavye
- [HoloLens (1. nesil) tıklama](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> HoloLens ayarlarında konuşmacılar, mikrofonlu telefonlar, akıllı telefonlar ve oyun paneli gibi diğer Bluetooth cihaz türleri listelenmiş olabilir. Ancak bu cihazlar HoloLens'te (1. nesil) desteklenmiyor. Daha fazla bilgi için [bkz. HoloLens Ayarları](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)cihazları kullanılabilir olarak listeler, ancak cihazlar çalışmıyor.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth klavyesini veya faresini eşleştirme

1. Klavyenizi veya farenizi açarak keşfedilebilir hale sürükleyin. Cihazın bulunabilir hale nasıl geleceklerini öğrenmek için cihazla ilgili bilgileri (veya belgelerini) inceleyin veya üreticinin web sitesini ziyaret edin.

1. Başlat 'a gidip Ayarlar'ı seçmek için bloom hareketini (HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) **kullanın.**

1. **Cihazlar'ı** seçin ve Bluetooth'un açık olduğundan emin olun.  

1. Cihaz adını gördüğünüzde **Eşleştir'i seçin** ve yönergeleri izleyin.

## <a name="disable-bluetooth"></a>Bluetooth'u devre dışı bırakma

Bu yordam, Bluetooth radyos un RF bileşenlerini devre dışı bırakarak tüm Bluetooth işlevlerini Microsoft HoloLens.

1. Başlat 'a gitmek için bloom hareketini (HoloLens (1. nesil)) veya başlangıç hareketini (HoloLens 2) kullanın ve ardından Ayarlar **Cihazları'ı**  >  **seçin.**

1. Bluetooth kaydırıcı anahtarını **Kapalı** **konuma** getirin.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: USB-C cihazlarını bağlama

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
> Müşteri geri bildirimlerine yanıt olarak USB-C aracılığıyla doğrudan HoloLens'e bağlı hücresel bağlantı için sınırlı destek sağladık. Daha [fazla bilgi için bkz. Hücresel ve 5G'ye](hololens-cellular.md) bağlanma.

### <a name="usb-c-external-microphone-support"></a>USB-C Dış Mikrofon Desteği

> [!IMPORTANT]
> BIR **USB mikrofona takan, bunu giriş cihazı olarak otomatik olarak ayarlamaz.** Kullanıcılar bir USB-C klavyesi kümesine takılıyken, mikrofonlu cihazın sesinin otomatik olarak mikrofona yeniden yönlendirilmesine neden olduğunu gözlemler ancak HoloLens işletim sistemi, iç mikrofon dizisini diğer giriş cihazlarından yüksek önceliklendirmektedir. **USB-C mikrofonunu kullanmak için aşağıdaki adımları izleyin.**

> [!NOTE]
> Dış mikrofonlar, Windows Holographic sürüm [21H1](hololens-release-notes.md#windows-holographic-version-21h1) ve daha önceki derlemelerde kullanılamaz. 

Kullanıcılar Ses ayarları panelini kullanarak USB-C bağlantılı dış **mikrofonları** seçebilirsiniz. USB-C mikrofonları arama, kayıt vb. için kullanılabilir.

Ayarlar uygulamasını **açın** ve Sistem **Sesi'ne**  >  **tıklayın.**

![Ses Ayarları](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Remote Assist ile dış **mikrofonları kullanmak için** kullanıcıların "Ses cihazlarını yönet" köprüsüne tıklaması gerekir.
>
> Ardından, dış mikrofonu Varsayılan veya İletişim Varsayılanı olarak ayarlamak **için açılır** **liste kullanın.** **Varsayılan'ın** seçerek dış mikrofon her yerde kullanılacaktır.
>
> İletişim **Varsayılanı'nın** seçimi, dış mikrofonun Remote Assist ve diğer iletişim uygulamaları için kullanılamayacak, ancak HoloLens mikrofon dizisi diğer görevler için de kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanı ayarlama](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği ne olacak?

Ne yazık ki, HoloLens 2'de Bluetooth mikrofonları şu anda desteklenmiyor.

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C mikrofon sorunlarını giderme

Bazı USB-C mikrofonlarının kendilerini hem mikrofon hem de konuşmacı olarak yanlış şekilde *raporlasalar.* Bu, HoloLens ile değil mikrofonla ilgili bir sorundur. Bu mikrofonlardan birini HoloLens'e takarak ses kaybolabilir. Neyse ki basit bir düzeltme var.  

Ayarlar   ->  **Sistem**  ->  **Sesi'nin** içinde yerleşik konuşmacıları (Analog Özellik Ses **Sürücüsü) Varsayılan** cihaz olarak açıkça **ayarlayın.** HoloLens, mikrofon daha sonra kaldırılarak yeniden bağlansa bile bu ayarı hatırlaması gerekir.

![USB-C mikrofon sorunlarını giderme](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>USB-C Hub'ları

Bazı kullanıcıların aynı anda birden çok cihaza bağlanması gerekir. [USB-C](#usb-c-external-microphone-support) mikrofonunu başka bir bağlı cihazla birlikte kullanmak isteyen kullanıcılar için, USB-C hub'ları müşterinin ihtiyaçlarına uygun olabilir. Microsoft bu cihazları test edilmemiştir ve herhangi bir marka önerilmez.

**USB-C hub'ı ve bağlı cihazlar için gereksinimler:**

- Bağlı cihazların bir sürücünün yüklü olması gerekli değildir.
- Bağlı tüm cihazların toplam güç çekimi 4,5 Watt'ın altında olması gerekir.

## <a name="connect-to-miracast"></a>Miracast'e bağlanma

Miracast'i kullanmak için şu adımları izleyin:

1. Aşağıdakilerden birini yapın:  

   - Başlat **menüsünü** açın ve Görüntü **simgesini** seçin.
   - Başlat menüsüne bakarken "Bağlan" **diyelim.**  

1. Görüntülenen cihaz listesinde kullanılabilir bir cihaz seçin.

1. Eşleştirmeyi tamamlar ve projeye başlar.
