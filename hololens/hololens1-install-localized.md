---
title: HoloLens'in yerelleştirilmiş sürümlerini yükleme
description: HoloLens'in yerelleştirilmiş sürümlerini (1. nesil) Çince ve Japonca sürümler de dahil olmak üzere yükleme hakkında bilgi.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379171"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="7895d-103">HoloLens'in yerelleştirilmiş sürümlerini yükleme (1. nesil)</span><span class="sxs-lookup"><span data-stu-id="7895d-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="7895d-104">HoloLens'in Çince veya Japonca sürümüne geçmek için Windows Cihaz Kurtarma Aracı'nı (WDRT) kullanarak dil derlemesini bir bilgisayara indirmeniz ve ardından HoloLens cihazınıza yüklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="7895d-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7895d-105">HoloLens'in Çince veya Japonca derlemelerini yüklemek için WDRT'nin kullanılması, kişisel dosyalar ve ayarlar gibi mevcut verileri HoloLens'inize siler.</span><span class="sxs-lookup"><span data-stu-id="7895d-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="7895d-106">Bilgisayarınızda Windows Cihaz Kurtarma Aracı'nı [(WDRT) indirip yükleyin.](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="7895d-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="7895d-107">Bilgisayarınıza istediğiniz dil için paketi indirin: Basitleştirilmiş [Çince veya](https://aka.ms/hololensdownload-ch) [Japonca.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="7895d-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="7895d-108">İndirme işlemi tamam olduğunda İndirmeler'i **Dosya Gezgini**  >  **seçin.**</span><span class="sxs-lookup"><span data-stu-id="7895d-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="7895d-109">Az önce indirdiğiniz sıkıştırılmış klasöre sağ tıklayın ve Sıkıştırmayı açmak **için Tüm**  >  **Ayıkla'yı** seçin.</span><span class="sxs-lookup"><span data-stu-id="7895d-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="7895d-110">HoloLens'inizi, birlikte gönderilen mikro USB kablosunu kullanarak bilgisayarınıza bağlayın.</span><span class="sxs-lookup"><span data-stu-id="7895d-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="7895d-111">(HoloLens'inizi bağlamak için başka kablolar kullanıyorsanız bile bu en iyi şekilde çalışır.)</span><span class="sxs-lookup"><span data-stu-id="7895d-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="7895d-112">Araç HoloLens'inizi otomatik olarak algıladikten sonra, Microsoft HoloLens seçin.</span><span class="sxs-lookup"><span data-stu-id="7895d-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="7895d-113">Sonraki ekranda El ile paket **seçimi'ne** tıklayın ve 4. adımda sıkıştırmasını açmak istediğiniz   klasörde bulunan yükleme dosyasını seçin.</span><span class="sxs-lookup"><span data-stu-id="7895d-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="7895d-114">(".ffu" uzantısına sahip bir dosya bulun.)</span><span class="sxs-lookup"><span data-stu-id="7895d-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="7895d-115">Yazılım **yükle'yi** seçin ve yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="7895d-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="7895d-116">Derleme yüklendikten sonra HoloLens kurulumu otomatik olarak başlatılır.</span><span class="sxs-lookup"><span data-stu-id="7895d-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="7895d-117">Cihazı açın ve kurulum yönergelerini izleyin.</span><span class="sxs-lookup"><span data-stu-id="7895d-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="7895d-118">Kurulumu tamamlasanız Ayarlar Güncelleştirmesi & Security Windows Insider Programı 'a gidin ve en son önizleme derlemelerini alacak şekilde  >    >  yapılandırıldığından emin olun.</span><span class="sxs-lookup"><span data-stu-id="7895d-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="7895d-119">İngilizce önizleme derlemeleri gibi, Windows Insider Programı ve Japonca HoloLens sürümlerini de en son önizleme derlemeleriyle güncel tutar.</span><span class="sxs-lookup"><span data-stu-id="7895d-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="7895d-120">Ayarlar uygulamasını kullanarak İngilizce, Japonca ve Çince arasındaki sistem dilini değiştiremezsiniz.</span><span class="sxs-lookup"><span data-stu-id="7895d-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="7895d-121">Cihaz sistemi dilini değiştirmenin desteklenen tek yolu yeni bir derlemenin yanıp sönmesidir.</span><span class="sxs-lookup"><span data-stu-id="7895d-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="7895d-122">Basitleştirilmiş Çince veya Japonca metin girmek için ekran üzerinde Pinyin klavyesini kullanabilirsiniz ancak Basitleştirilmiş Çince veya Japonca metinler girmek için Bluetooth donanım klavyesi kullanmak şu anda desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="7895d-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="7895d-123">Ancak, Çince veya Japonca HoloLens'te, İngilizce yazacak bir Bluetooth klavyesi kullanmaya devam edersiniz (bir donanım klavyesini İngilizce yazacak şekilde iki durumlu yapmak için ~ tuşuna basın).</span><span class="sxs-lookup"><span data-stu-id="7895d-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
