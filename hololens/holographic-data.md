---
title: HoloLens 'te dosyaları bulma ve kaydetme
description: Karma Gerçeklik cihazındaki dosyaları açmak, görüntülemek ve yönetmek için HoloLens 'te dosya Gezgini 'ni nasıl kullanacağınızı öğrenin.
keywords: Nasıl yapılır, dosya seçici, dosyalar, fotoğraflar, videolar, resimler, OneDrive, depolama, dosya Gezgini, Hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378974"
---
# <a name="find-open-and-save-files-on-hololens"></a>HoloLens 'te dosyaları bulun, açın ve kaydedin

HoloLens 'te fotoğraflar ve videolar dahil oluşturduğunuz dosyalar doğrudan HoloLens cihazınıza kaydedilir. Windows 10 ' da dosyaları yönettiğiniz şekilde görüntüleyin ve yönetin:

- Yerel klasörlere erişmek için dosya Gezgini uygulamasını kullanma.
- Bir uygulamanın depolama alanında.
- Özel bir klasörde (örneğin, video veya müzik kitaplığı).
- Uygulama ve dosya seçici (OneDrive gibi) içeren bir depolama hizmeti kullanma.
- MTP (Medya Aktarım Protokolü) desteğini kullanarak bir USB kablosu kullanarak HoloLens 'nizle bağlantılı masaüstü bılgısayar kullanma.

## <a name="view-files-on-hololens-using-file-explorer"></a>Dosya Gezgini 'ni kullanarak HoloLens 'te dosyaları görüntüleme

> [HoloLens Için Windows 10 nisan 2018 Güncelleştirmesi (RS4)](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)Itibariyle tüm HoloLens 2 cihazlara ve HoloLens (1. gen) için geçerlidir.

3D nesneler, belgeler ve resimler dahil olmak üzere cihazınızdaki dosyaları görüntülemek ve yönetmek için HoloLens üzerinde dosya Gezgini 'ni kullanın. Başlamak için    >  **tüm uygulamalar**   >  **Dosya Gezgini** ' ni Başlat ' a gidin.

> [!TIP]
> Dosya Gezgini 'nde listelenen dosya yoksa, sol üst bölmedeki **Bu cihazı** seçin.

Dosya Gezgini 'nde herhangi bir dosya görmüyorsanız, "son" filtre etkin olabilir (saat simgesi sol bölmede vurgulanır). Bu hatayı onarmak için sol bölmedeki (saat simgesinin altında) **Bu cihaz** belgesi simgesini seçin veya menüyü açın ve **Bu cihazı** seçin.

## <a name="find-and-view-your-photos-and-videos"></a>Fotoğraflarınızı ve videolarınızı bulun ve görüntüleyin

[Karma gerçeklik yakalama](holographic-photos-and-videos.md) , Hololens 'te karışık gerçeklik fotoğraflarını ve videoları almanızı sağlar.  Bu fotoğraflar ve videolar cihazın kamera rulosu klasörüne kaydedilir.

HoloLens ile çekilen fotoğraflara ve videolara erişebilirsiniz:

- doğrudan [Fotoğraflar uygulaması](holographic-photos-and-videos.md)aracılığıyla kamera rulonuza erişme.
- Fotoğraflarınızı ve videolarınızı OneDrive 'a eşitleyerek, fotoğraf ve videoları bulut depolamaya yükleme.
- [Windows cihaz portalının](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)karma gerçeklik yakalama sayfasını kullanma.

### <a name="photos-app"></a>Fotoğraflar uygulaması

Fotoğraflar uygulaması, **Başlangıç** menüsündeki varsayılan uygulamalardan biridir ve HoloLens ile yerleşik olarak sunulur. [İçeriği görüntülemek Için Fotoğraflar uygulamasını kullanma](holographic-photos-and-videos.md)hakkında daha fazla bilgi edinin.

Ayrıca, fotoğrafları diğer cihazlara eşitlemek için Microsoft Store [OneDrive uygulamasını](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) da yükleyebilirsiniz.

### <a name="onedrive-app"></a>OneDrive uygulaması

[OneDrive](https://onedrive.live.com/) , fotoğraf ve videolarınızı dilediğiniz cihazla ve herhangi bir kullanıcıyla erişmenizi, yönetmenizi ve paylaşmanızı sağlar. HoloLens 'te yakalanan fotoğraflara ve videolara erişmek için, HoloLens 'teki Microsoft Store [OneDrive uygulamasını](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) indirin. İndirildikten sonra OneDrive uygulamasını açın ve **Ayarlar**  >  **Kamera karşıya yükle**' yi seçin ve **Kamera karşıya yüklemeyi** açın.

### <a name="connect-to-a-pc"></a>BILGISAYARA Bağlan

HoloLens 'niz [Windows 10 nisan 2018 güncelleştirmesini](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) veya sonrasını ÇALıŞTıRıYORSA, MTP 'yi (Medya Aktarım Protokolü) kullanarak cihazdaki fotoğraflara ve videolara taramak IÇIN bir USB kablosu kullanarak HoloLens 'Nizi bir WINDOWS 10 bilgisayarına bağlayabilirsiniz. Cihazınızda bir PIN veya parola ayarladıysanız, dosyalara gözatabilmeniz için cihazın kilidinin açık olduğundan emin olmanız gerekir.  

[Windows cihaz portalını](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)etkinleştirdiyseniz, cihazınızda depolanan fotoğrafları ve videoları taramak, almak ve yönetmek için bu uygulamayı kullanabilirsiniz.

## <a name="access-files-within-an-app"></a>Bir uygulama içindeki dosyalara erişme

Bir uygulama aygıtınızdaki dosyaları kaydederse, bunlara erişmek için bu uygulamayı kullanabilirsiniz.

### <a name="requesting-files-from-another-app"></a>Başka bir uygulamadan dosya isteme

Bir uygulama, dosya [etiketlerini](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)kullanarak bir dosyayı kaydetmek veya başka bir uygulamadan dosya açmak isteyebilir.

### <a name="known-folders"></a>Bilinen klasörler

HoloLens, uygulamaların erişim için izin isteyebildiği bir dizi [bilinen klasörü](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) destekler.

## <a name="view-hololens-files-on-your-pc"></a>Bilgisayarınızda HoloLens dosyalarını görüntüleyin

Diğer mobil cihazlara benzer şekilde, MTP 'yi (Medya Aktarım Protokolü) kullanarak masaüstü PC 'nize bağlayın ve kolay Aktarım için HoloLens kitaplıklarınıza erişmek üzere bılgısayarda dosya Gezgini 'ni açın.

Bilgisayarınızda dosya Gezgini 'nde HoloLens dosyalarınızı görmek için:

1. HoloLens 'te oturum açın, ardından HoloLens ile gelen USB kablosunu kullanarak BILGISAYARA takın.

1. **Dosya Gezgini ile dosyaları görüntülemek Için cihazı aç**' ı SEÇIN veya bilgisayarda dosya Gezgini 'ni açın ve cihaza gidin.

HoloLens bilgileriniz hakkındaki bilgileri görmek için, bilgisayarınızda dosya Gezgini ' nde cihaz adına sağ tıklayın ve ardından **Özellikler**' i seçin.

> [!NOTE]
> HoloLens (1. gen), dış sabit sürücülere veya SD kartlarına bağlanmayı desteklemez.

## <a name="sync-to-the-cloud"></a>Buluta Eşitle

HoloLens 'teki fotoğrafları ve diğer dosyaları buluta eşitlemek için, OneDrive 'ı yükleyin ve HoloLens 'te kurun. OneDrive 'ı almak için, HoloLens 'teki Microsoft Store arayın.

HoloLens uygulama dosyalarını ve verileri yedeketmez, bu nedenle önemli öğelerinizi OneDrive 'a kaydetmeniz iyi bir fikirdir. Bu şekilde, cihazınızı sıfırlayabilir veya bir uygulamayı kaldırırsanız, bilgileriniz yedeklenir.
