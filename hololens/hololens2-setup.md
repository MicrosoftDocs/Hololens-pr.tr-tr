---
title: yeni bir HoloLens hazırla 2
description: durum ve güvenlik ipuçları ve donanım kılavuzlarıyla birlikte HoloLens 2 cihazınızı ilk kez ayarlamayı ve ayarlamayı öğrenin.
keywords: Hololens, ışıklar, sığdırma, rahatlık, parçalar
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 13f7000f608e6375efce201f1edd1627900ecdda2f86ddca8a174ac0b8e43ceb
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115658939"
---
# <a name="get-your-hololens-2-ready-to-use"></a>HoloLens 2 ' ye kullanıma hazırlanın

aşağıdaki yordamlar, ilk kez bir HoloLens 2 ayarlamanıza yardımcı olur.

## <a name="charge-your-hololens"></a>HoloLens ücretlendirme yapın

güç kaynağını, USB-C kablosunu (dahil) kullanarak ücretlendirme bağlantı noktasına Bağlan. Güç kaynağını bir güç prizine takın. aygıtla birlikte gelen güç kaynağı ve USB-c-c kablosu, HoloLens 2 ' inizi ücretlendirmenin en iyi yoludur. Cihazınızın şarj cihazına, 18W gücü (2a 'da 9V) sağlar. HoloLens 2 cihaz, izin verilen duvar karağını kullanarak, cihaz bekleme modundayken 65 dakikadan kısa bir süre içinde pili tam olarak ücretlendirmesini sağlayabilir.

Doldurma oranı ve hız, cihazın çalıştığı ortama göre farklılık gösterebilir.

- Cihaz şarj edildiğinde, pil göstergesi, geçerli ücret düzeyini belirtmek için ışıkları.  Son ışık, etkin şarjın olduğunu göstermek için soluklaşır ve artacaktır.
- HoloLens açık olduğunda, pil göstergesi pil düzeyini artışlarla görüntüler.
- Beş ışığının yalnızca biri açık olduğunda, pil düzeyi yüzde 20 ' nin altında olur.
- Pil düzeyi kritik düzeyde düşükse ve cihazı açmaya çalışırsanız, bir ışık kısa bir süre yanıp söndürmez ve sonra da çıkar.

Daha fazla bilgi gerekirse [cihaz şarjındaki tüm ayrıntılar buradan okunabilir](hololens2-charging.md#charging-the-device) . 

## <a name="adjust-fit"></a>Sığdırmayı ayarla

HoloLens 2 ' ye kafaya yerleştirin. Gözeyede aşdığınızda, bunları açık bırakın.  Broş paneli, kendi başkananıza rahat bir şekilde oturmalıdır ve arka bantın ortasından geri doğru olması gerekir.

Gerekirse, ayarlama tekerleğini açıp daha sonra ek yükü strap 'yi gevyana ekleyerek başlık bandı ' ni genişletin.

![HoloLens 2 sığdırma ve ayarlama](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>Ek yükü strap 'yi iliştirme ve ayır

ek yükü strap gerekli değildir, ancak uzun süre kullanım sırasında 2. HoloLens daha rahat bir şekilde bulunabilir.

Ek yükün önünü ayırmak için, strap 'yi kaldırır ve Brow panelinde Retractable döngüsü aracılığıyla kaydırın. Yeniden iliştirmek için döngüyü çekin ve geriye doğru katman kaydırın.

Ek yükü strap 'nin geri ayrılması için her bağlantı sekmesinin altındaki düğmeye basın ve yavaşça çekin. Yeniden iliştirmek için bağlantı sekmelerini tıkladıkları sürece yuvalara geri gönderin.

![HoloLens 2 baş strap 'yi ekle veya kaldır](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>HoloLens 2 ' ye aç

HoloLens 2 ' yi açmak için, güç düğmesine basın.  Güç düğmesinin altındaki LED 'ler pil düzeyini görüntüler.

> [!NOTE]
> HoloLens 2 ' yi ilk kez açmak için, kutudan çıktıktan sonra, açmak için en az 4 saniyelik güç düğmesine basın ve basılı tutun. HoloLens 2 ' yi bir sonraki açışınızda, kısa bir güç düğmesine basduktan sonra başlatılır.

### <a name="power-button-actions-for-different-power-transitions"></a>Farklı güç geçişleri için güç düğmesi eylemleri

| Bunu yapmak için | Bu eylemi gerçekleştir | HoloLens 2 bunu yapacaktır |
| - | - | - |
| Açmak için | Tek düğmeye basma. | Beş ışık, sonra da pil düzeyini belirtecek şekilde değişir. Dört saniye sonra bir ses çalar. |
| Uykuya geçme | Tek düğmeye basma. | Beş ışık, her seferinde bir kez açık ve sonra kapanır. Işıklar kapatıldıktan sonra bir ses oynatılır ve ekran "güle" görüntülenir. |
| Uykudan uyanma için | Tek düğmeye basma. | Beş ışık, sonra da pil düzeyini belirtecek şekilde değişir. Bir ses hemen oynatılır. |
| Kapatmak için | 5 s için basın ve basılı tutun. |  Beş ışık, her seferinde bir kez açık ve sonra kapanır. Işıklar kapatıldıktan sonra bir ses oynatılır ve ekran "güle" görüntülenir. |
| yanıt vermiyorsa HoloLens yeniden başlamaya zorlamak için | 10 sn için basılı tutun. | Beş ışık, her seferinde bir kez açık ve sonra kapanır. Işıklar kapatıldıktan sonra. |

## <a name="hololens-behavior-reference"></a>HoloLens davranış başvurusu

HoloLens gösterge ışıklarının ne anlama geldiğinden emin değil misiniz? HoloLens şarj edilirken nasıl davranması gerektiğini öğrenmek mi istiyorsunuz?  İşte size bazı yardım!

### <a name="charging-behavior"></a>Ücretlendirme davranışı

| Cihazın durumu | Eylem | HoloLens 2 bunu yapacaktır |
| - | - | - |
| KAPALI | Eklenti USB kablosu | Cihaz düzeyini gösteren gösterge ışıkları ile açık cihaz geçişleri, cihaz şarjını başlatır.
| AÇIK | USB kablosunu kaldır | Cihazın dolumu durduruluyor
| AÇIK | Eklenti USB kablosu | Cihaz şarj başlıyor
| KULLANıLMADıĞıNDA | Eklenti USB kablosu | Cihaz şarj başlıyor
| KULLANıLMADıĞıNDA | USB kablosunu kaldır | Cihazın dolumu durduruluyor
| USB kablosu takılı olduğunda | Cihazı kapat | Pil düzeyini gösteren gösterge ışıkları ile açık olan cihaz geçişleri ve cihaz şarj başlatacak |

### <a name="lights-that-indicate-the-battery-level"></a>Pil düzeyini gösteren ışıklar

| Işık sayısı | Pil düzeyi |
| - | - |
| Dört katı ışık, bir açık ve dışarı geçiş | %100 ve %81 arasında (tam olarak ücretlendirilir) |
| Üç katı ışık, bir açık ve dışarı geçiş | %80 ile 61 arasında |
| İki katı ışık, bir açık soldurma ve dışarı | %60 ile 41 arasında |
| Tek bir katı ışık, bir açık ve dışarı geçiş | %40 ile %21 arasında |
| Bir açık ve dışarı geçişi | %20 ile %5 veya daha düşük (kritik pil) |

### <a name="sleep-behavior"></a>Uyku davranışı

| Cihazın Durumu | Eylem | HoloLens 2 bunu yapar |
| - | - | - |
| AÇIK | Tek Güç düğmesine basın | Cihaz UYKU'ya geçişler ve tüm gösterge ışıklarını kapatma |
| AÇIK | 3 dakika hareket yok | Cihaz UYKU'ya geçiş ve tüm gösterge ışıklarını kapatma |
| Uyku | Tek Güç düğmesi Tuşuna basın | Cihaz AÇıK'a geçişler ve gösterge ışıklarını aç |

### <a name="lights-to-indicate-problems"></a>Sorunları göstermek için lambalar

| Bunu yapmak için | Işıklar bunu yapar | Bunun anlamı |
| - | - | - |
| Güç düğmesine basabilirsiniz. | Bir ışık beş kez yanıp söner, sonra da kapalıdır. | Bu HoloLens kritik bir şekilde düşüktür. Ücretlerinizi HoloLens. |
| Güç düğmesine basabilirsiniz. | Beş ışığın hepsi beş kez yanıp söner, sonra da kapat. |  HoloLens doğru başlatamaz ve hata durumuna geldi. [Cihazınızı kurtarmak için işletim](hololens-recovery.md) sistemini yeniden yükleyin. |
| Güç düğmesine basabilirsiniz. | 1., 3. ve 5. lambalar sürekli olarak yanıp söner. |  HoloLens bir donanım hatası olabilir. De [destekle iletişime geçin.](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb) |

## <a name="safety-and-comfort"></a>Güvenlik ve konfor

### <a name="use-hololens-in-safe-surroundings"></a>Güvenli HoloLens için güvenlik bilgileri kullanma

Güvenlik HoloLens güvenli bir alanda kullanın. Bu, engellerden ve tehlikelerden kaynaksızdır. Net bir görünüm alanına ihtiyacınız olduğunda veya tüm dikkati çekerken (örneğin, bir araçla çalışırken veya diğer tehlikeli etkinlikler yaparken) bunu kullanmayın.

### <a name="stay-comfortable"></a>Rahat kalın

İlk birkaç oturumlarınızı kısa HoloLens ve ara verdiklerinizi unutmayın. Sorun yaşamazsanız, daha iyi hissedene kadar durdurun ve istirahat edin. Buna geçici olarak sıkıntı, hareket şikayeti, baş dönmesi, kafa karışıklığı, kasma, kasma, göz zorluğu veya kuru göz olabilir.

Ürün [güvenliği uyarıları ve yönergelerine bakın.](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)

> [!div class="nextstepaction"]
> [2. HoloLens ayarlama](hololens2-start.md)
