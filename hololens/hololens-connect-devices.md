---
title: Bluetooth ve USB-C cihazlarına Bağlan
description: HoloLens karma gerçeklik cihazlarınızdan Bluetooth ve USB-C cihazlarına ve donatılara bağlanma ile çalışmaya başlayın.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639106"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Bluetooth ve USB-C cihazlarına Bağlan

## <a name="pair-bluetooth-devices"></a>Bluetooth cihazları eşleştirin

HoloLens 2, aşağıdaki Bluetooth cihaz sınıflarını destekler:

- [HID](/windows-hardware/drivers/hid/):
    - Fare
    - Klavye
- Ses çıkışı (A2DP) cihazları

HoloLens 2 aşağıdaki Bluetooth apı 'lerini destekler:
- GATT [sunucusu](/windows/uwp/devices-sensors/gatt-server) ve [istemcisi](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> hıd ve gatt cihazlarını kullanmak için Microsoft Store ' den ilgili yardımcı uygulamaları yüklemek zorunda kalabilirsiniz.

HoloLens (1. gen), aşağıdaki Bluetooth cihaz sınıflarını destekler:

- Fare
- Klavye
- [HoloLens (1. genel) çi](hololens1-clicker.md)

> [!NOTE]
> hoparlörler, kulaklıklar, akıllı telefonlar ve oyun bölmeleri gibi diğer Bluetooth cihaz türleri HoloLens ayarlarında kullanılabilir olarak listelenebilir. ancak, bu cihazlar HoloLens desteklenmez (1. genel). daha fazla bilgi için bkz. [HoloLens Ayarlar cihazları kullanılabilir olarak listeler, ancak cihazlar çalışmıyor](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Bluetooth klavye veya fareyi eşleştirme

1. Klavyenizi veya farenizi açın ve bulunabilir hale getirin. Cihazı bulunabilir hale getirme hakkında bilgi edinmek için cihaz (veya belgeleri) hakkındaki bilgileri arayın veya üreticinin Web sitesini ziyaret edin.

1. **başlat**' a gitmek için bloom hareketini (HoloLens (1. gen)) veya başlangıç hareketini (HoloLens 2) kullanın ve **Ayarlar**' yı seçin.

1. **cihazlar**' ı seçin ve Bluetooth açık olduğundan emin olun.  

1. Cihaz adı ' nı gördüğünüzde, **Eşleştir**' i seçin ve ardından yönergeleri izleyin.

## <a name="disable-bluetooth"></a>Bluetooth devre dışı bırak

bu yordam Bluetooth radyoın RF bileşenlerini kapatır ve Microsoft HoloLens tüm Bluetooth işlevlerini devre dışı bırakır.

1. **başlat**' a gitmek için bloom hareketini (HoloLens (1. gen)) veya başlangıç hareketini (HoloLens 2) kullanın ve **Ayarlar**  >  **cihazlar**' ı seçin.

1. **Bluetooth** için kaydırıcı anahtarını **kapalı** konuma taşıyın.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Bağlan USB-C cihazları

HoloLens 2, aşağıdaki USB-C cihaz sınıflarını destekler:

- Yığın depolama cihazları (Thumb sürücüleri gibi)
- Ethernet bağdaştırıcıları (Ethernet Plus dolduruluyor dahil)
- USB-C-3,5 mm dijital ses bağdaştırıcıları
- USB-C Dijital Ses Kulaklıklar (kulaklık bağdaştırıcıları ve şarj etme dahil)
- USB-C dış mikrofonlar ([Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve üzeri)
- Kablolu fare
- Kablolu klavye
- Birleşik PD hub 'ları (USB A Plus PD doldurma)


> [!NOTE]
> müşteri geri bildirimlerine yanıt olarak, doğrudan USB-C aracılığıyla HoloLens hücresel bağlantı tethered için sınırlı destek sağlıyoruz. daha fazla bilgi için bkz. [hücresel ve 5 g 'ye Bağlan](hololens-cellular.md) .

### <a name="usb-c-external-microphone-support"></a>USB-C dış mikrofon desteği

> [!IMPORTANT]
> **BIR USB mikrofonun takmak, giriş cihazı olarak otomatik olarak ayarlanmayacak**. bir USB-C kulaklık kümesini takarken, kullanıcılar, kulaklık sesinin otomatik olarak kulaklıktan yeniden yönlendirildiğini gözlemleyecek ancak HoloLens OS, iç mikrofon dizisinin diğer herhangi bir giriş cihazını önceliklendirir. **Bir USB-C Mikrofonu kullanabilmek için aşağıdaki adımları izleyin.**

> [!NOTE]
> dış mikrofonlar [Windows Holographic, sürüm 21h1](hololens-release-notes.md#windows-holographic-version-21h1) ve üzeri sürümden önceki derlemelerde kullanılamaz. 

Kullanıcılar, **Ses** ayarları PANELINI kullanarak USB-C bağlantılı harici mikrofonlar seçebilir. USB-C mikrofonlar, arama, kaydetme, vb. için kullanılabilir.

**Ayarlar** uygulamasını açın ve **sistem**  >  **sesi**' ni seçin.

![ses Ayarlar](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Dış mikrofonları **Uzaktan Yardım** ile kullanmak için, kullanıcıların "ses cihazlarını yönetme" köprüsüne tıklamasına gerek vardır.
>
> Ardından açılan eklentiyi kullanarak dış mikrofonu **varsayılan** veya **iletişim varsayılanı** olarak ayarlayın. **Varsayılan** seçildiğinde dış mikrofonun her yerde kullanılacağı anlamına gelir.
>
> **iletişim varsayılanını** seçme, dış mikrofonun uzaktan yardım ve diğer iletişim uygulamalarında kullanılacağı anlamına gelir, ancak HoloLens mıc dizisi diğer görevler için hala kullanılabilir.

![Ses cihazlarını yönetme](images/usbc-mic-2.png)

<br>

![Mikrofon varsayılanını ayarla](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Bluetooth mikrofon desteği nedir?

ne yazık ki Bluetooth mikrofonlar halen HoloLens 2 ' de desteklenmemektedir.

### <a name="usb-c-hubs"></a>USB-C hub 'Ları

Bazı kullanıcıların aynı anda birden çok cihaza bağlanması gerekebilir. [USB-c mikrofonu](#usb-c-external-microphone-support) başka bir bağlı cihazla birlikte kullanmak isteyen kullanıcılar IÇIN, USB-c hub 'ları müşterinin ihtiyacı olabilir. Microsoft bu cihazları test etmemiş ve belirli markaların önermediğimiz için.

**USB-C hub ve bağlı cihazlar için gereksinimler:**

- Bağlı cihazların bir sürücünün yüklenmesini gerektirmemelidir.
- Tüm bağlı cihazların toplam güç çizimi 4,5 watt 'Tan daha düşük olmalıdır.

## <a name="connect-to-miracast"></a>Miracast Bağlan

Miracast kullanmak için şu adımları izleyin:

1. Aşağıdakilerden birini yapın:  

   - **Başlat** menüsünü açın ve **görüntü** simgesini seçin.
   - **başlangıç** menüsünde "Bağlan" deyin.  

1. Görüntülenen cihazların listesinde, kullanılabilir bir cihaz seçin.

1. Yansıtma başlamak için eşleştirmeyi doldurun.
