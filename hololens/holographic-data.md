---
title: HoloLens dosya bulma ve kaydetme
description: karma gerçeklik cihazındaki dosyaları açmak, görüntülemek ve yönetmek için HoloLens dosya gezgini 'ni nasıl kullanacağınızı öğrenin.
keywords: nasıl yapılır, dosya seçici, dosyalar, fotoğraflar, videolar, resimler, OneDrive, depolama, dosya gezgini, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ad210c9d31d8d7c226345618b6dfabf8457ee2398882935920d7b3217259a644
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664885"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens dosya bulun, açın ve kaydedin

fotoğraflar ve videolar dahil HoloLens oluşturduğunuz dosyalar doğrudan HoloLens cihazınıza kaydedilir. Windows 10 dosyaları yönettiğiniz şekilde görüntüleyin ve yönetin:

- Yerel klasörlere erişmek için dosya Gezgini uygulamasını kullanma.
- Bir uygulamanın depolama alanında.
- Özel bir klasörde (örneğin, video veya müzik kitaplığı).
- Uygulama ve dosya seçici (OneDrive gibi) içeren bir depolama hizmeti kullanma.
- MTP (medya aktarım protokolü) desteğini kullanarak bir USB kablosu kullanarak HoloLens bağlı masaüstü bilgisayar kullanma.

## <a name="view-files-on-hololens-using-file-explorer"></a>dosya gezgini 'ni kullanarak HoloLens dosyaları görüntüleme

> [HoloLens için Windows 10 nisan 2018 güncelleştirmesi (RS4)](/windows/mixed-reality/release-notes-april-2018)itibariyle tüm HoloLens 2 cihazlara ve HoloLens (1. gen) geçerlidir.

cihazınızdaki dosyaları görüntülemek ve yönetmek için, 3b nesneler, belgeler ve resimler dahil HoloLens dosya gezgini 'ni kullanın. Başlamak için    >  **tüm uygulamalar**   >  **Dosya Gezgini** ' ni Başlat ' a gidin.

> [!TIP]
> Dosya Gezgini 'nde listelenen dosya yoksa, sol üst bölmedeki **Bu cihazı** seçin.

Dosya Gezgini 'nde herhangi bir dosya görmüyorsanız, "son" filtre etkin olabilir (saat simgesi sol bölmede vurgulanır). Bu hatayı onarmak için sol bölmedeki (saat simgesinin altında) **Bu cihaz** belgesi simgesini seçin veya menüyü açın ve **Bu cihazı** seçin.

## <a name="find-and-view-your-photos-and-videos"></a>Fotoğraflarınızı ve videolarınızı bulun ve görüntüleyin

[Karma gerçeklik yakalama](holographic-photos-and-videos.md) , Hololens üzerinde karma gerçeklik fotoğraflarını ve videoları almanızı sağlar.  Bu fotoğraflar ve videolar cihazın kamera rulosu klasörüne kaydedilir.

HoloLens ile alınan fotoğraflara ve videolara erişebilirsiniz:

- doğrudan [Fotoğraflar uygulaması](holographic-photos-and-videos.md)aracılığıyla kamera rulonuza erişme.
- Fotoğraflarınızı ve videolarınızı OneDrive ile eşitleyerek, fotoğraf ve videoları bulut depolamaya yükleyin.
- [Windows cihaz portalının](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)karma gerçeklik yakalama sayfasını kullanma.

### <a name="photos-app"></a>Fotoğraflar uygulaması

Fotoğraflar uygulaması, **Başlangıç** menüsündeki varsayılan uygulamalardan biridir ve HoloLens ile yerleşik olarak sunulur. [İçeriği görüntülemek Için Fotoğraflar uygulamasını kullanma](holographic-photos-and-videos.md)hakkında daha fazla bilgi edinin.

fotoğrafları diğer cihazlara eşitlemek için Microsoft Store [OneDrive uygulamayı](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da yükleyebilirsiniz.

### <a name="onedrive-app"></a>OneDrive uygulaması

[OneDrive](https://onedrive.live.com/) , fotoğraf ve videolarınızı dilediğiniz cihazla ve herhangi bir kullanıcıyla erişmenizi, yönetmenizi ve paylaşmanızı sağlar. HoloLens yakalanan fotoğraflara ve videolara erişmek için, [OneDrive uygulamayı](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) HoloLens Microsoft Store indirin. indirildikten sonra OneDrive uygulamasını açın ve kamera karşıya   >  **yükleme** Ayarlar seçin ve **kamera karşıya yüklemeyi** açın.

### <a name="connect-to-a-pc"></a>bir bilgisayara Bağlan

HoloLens [Windows 10 nisan 2018 güncelleştirmesini](/windows/mixed-reality/release-notes-april-2018) veya sonrasını çalıştırıyorsa, MTP 'yi (medya aktarım protokolü) kullanarak cihazdaki fotoğraflara ve videolara taramak için bir USB kablosu kullanarak HoloLens Windows 10 bilgisayara bağlayabilirsiniz. Cihazınızda bir PIN veya parola ayarladıysanız, dosyalara gözatabilmeniz için cihazın kilidinin açık olduğundan emin olmanız gerekir.  

[Windows cihaz portalını](/windows/mixed-reality/using-the-windows-device-portal)etkinleştirdiyseniz, cihazınızda depolanan fotoğrafları ve videoları taramak, almak ve yönetmek için bu uygulamayı kullanabilirsiniz.

## <a name="access-files-within-an-app"></a>Bir uygulama içindeki dosyalara erişme

Bir uygulama aygıtınızdaki dosyaları kaydederse, bunlara erişmek için bu uygulamayı kullanabilirsiniz.

### <a name="requesting-files-from-another-app"></a>Başka bir uygulamadan dosya isteme

Bir uygulama, dosya [etiketlerini](/windows/mixed-reality/app-model#file-pickers)kullanarak bir dosyayı kaydetmek veya başka bir uygulamadan dosya açmak isteyebilir.

### <a name="known-folders"></a>Bilinen klasörler

HoloLens, uygulamaların erişim izni isteyebildiği bir dizi [bilinen klasörü](/windows/mixed-reality/app-model#known-folders) destekler.

## <a name="view-hololens-files-on-your-pc"></a>bilgisayarınızda HoloLens dosyaları görüntüleme

diğer mobil cihazlara benzer şekilde, MTP 'yi (medya aktarım protokolü) kullanarak masaüstü PC 'nize HoloLens bağlayın ve kolay aktarım için HoloLens kitaplıklarınıza erişmek üzere bilgisayarda dosya gezgini 'ni açın.

bilgisayarınızda dosya gezgini 'nde HoloLens dosyalarınızı görmek için:

1. HoloLens oturum açın ve HoloLens ile birlikte gelen USB kablosunu kullanarak bilgisayara takın.

1. **Dosya Gezgini ile dosyaları görüntülemek Için cihazı aç**' ı SEÇIN veya bilgisayarda dosya Gezgini 'ni açın ve cihaza gidin.

HoloLens hakkındaki bilgileri görmek için, bilgisayarınızda dosya gezgini ' nde cihaz adına sağ tıklayın ve ardından **özellikler**' i seçin.

> [!NOTE]
> HoloLens (1. gen), dış sabit sürücülere veya SD kartlara bağlanmayı desteklemez.

## <a name="sync-to-the-cloud"></a>Buluta Eşitle

HoloLens fotoğrafları ve diğer dosyaları buluta eşitlemek için HoloLens OneDrive kurun ve ayarlayın. OneDrive almak için HoloLens Microsoft Store arama yapın.

HoloLens uygulama dosyalarını ve verileri yedeklemediğinden önemli öğelerinizi OneDrive kaydetmek iyi bir fikirdir. Bu şekilde, cihazınızı sıfırlayabilir veya bir uygulamayı kaldırırsanız, bilgileriniz yedeklenir.
