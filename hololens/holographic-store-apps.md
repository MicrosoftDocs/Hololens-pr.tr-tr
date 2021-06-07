---
title: Uygulamaları bulma, yükleme ve kaldırma
description: Microsoft Store, HoloLens ile çalışan uygulamalar ve Oyunlar için kaynağınız olur.  Holographic uygulamalarını bulma, yükleme ve kaldırma hakkında daha fazla bilgi edinin.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: Hololens, mağaza, UWP, uygulama, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111380171"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="a4b8e-105">Microsoft Store uygulamaları bulun, yükleme ve kaldırma</span><span class="sxs-lookup"><span data-stu-id="a4b8e-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="a4b8e-106">Microsoft Store, HoloLens ile çalışan uygulamalar ve Oyunlar için go kaynağıdır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="a4b8e-107">HoloLens 'teki mağazaya gittiğinizde, burada gördüğünüz tüm uygulamalar üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="a4b8e-108">HoloLens 'teki uygulamalar 2B görünüm veya holographic görünümünü kullanır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="a4b8e-109">2B görünümü kullanan uygulamalar Windows gibi görünür ve tüm bunların etrafında konumlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="a4b8e-110">Holographic View kullanan uygulamalar sizi çevreler ve gördüğünüz tek uygulama olur.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="a4b8e-111">HoloLens, Microsoft Store var olan birçok uygulamayı ve özel olarak HoloLens için oluşturulan yeni uygulamaları destekler.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="a4b8e-112">Bu makale, Microsoft Store holographic uygulamalarına odaklanır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="a4b8e-113">Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="a4b8e-114">Uygulama bulun</span><span class="sxs-lookup"><span data-stu-id="a4b8e-114">Find apps</span></span>

<span data-ttu-id="a4b8e-115">**Başlangıç** menüsünden Microsoft Store açın.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="a4b8e-116">Ardından uygulamalar ve Oyunlar için tarama yapın.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-116">Then browse for apps and games.</span></span> <span data-ttu-id="a4b8e-117">Arama penceresi açıldıktan sonra arama terimlerinizi söylediğinizde, "arama" ifadesini kullanarak arama yapmak için [sesli komutları](hololens-cortana.md) kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8e-118">HoloLens cihazları için sistem gereksinimleri, uygulama yapısının mimarisine dayalıdır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="a4b8e-119">HoloLens için bir uygulama derlemesi (1. gen), ARM mimari paketini dahil etmek üzere mağazadaki daha yeni bir UWP ile güncellenmemişse, HoloLens 2 cihazları için kullanılabilir olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="a4b8e-120">Benzer şekilde, bir HoloLens 2 uygulaması x86 mimari paketini içermiyorsa, HoloLens (1. gen) cihazlar için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="a4b8e-121">HoloLens cihaz mimarileri:</span><span class="sxs-lookup"><span data-stu-id="a4b8e-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="a4b8e-122">x86 = HoloLens (1. Genel)</span><span class="sxs-lookup"><span data-stu-id="a4b8e-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="a4b8e-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a4b8e-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8e-124">12 Ocak 2021 tarihinde aşağıdaki uygulamalar, HoloLens cihazlarda destek sonuna ulaşacaktır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="a4b8e-125">Uygulamanın Web sürümünü kullanmak için cihazınızda aşağıdaki bağlantıyı kullanmanız önerilir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="a4b8e-126">Uygulama</span><span class="sxs-lookup"><span data-stu-id="a4b8e-126">App</span></span>        | <span data-ttu-id="a4b8e-127">Bağlantı</span><span class="sxs-lookup"><span data-stu-id="a4b8e-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="a4b8e-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="a4b8e-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="a4b8e-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="a4b8e-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="a4b8e-130">PowerPoint mobil</span><span class="sxs-lookup"><span data-stu-id="a4b8e-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="a4b8e-131">Uygulama yükleme</span><span class="sxs-lookup"><span data-stu-id="a4b8e-131">Install apps</span></span>

<span data-ttu-id="a4b8e-132">Uygulamaları indirmek için bir Microsoft hesabı oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="a4b8e-133">Bazı uygulamalar ücretsizdir ve hemen indirilebilirler.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="a4b8e-134">Satın alma gerektiren uygulamalar için, Microsoft hesabı depoda oturum açmış ve geçerli bir ödeme yöntemine sahip olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8e-135">Microsoft Store üzerinde kullandığınız hesabın, oturum açtığınız hesapla aynı olması gerekmez.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="a4b8e-136">HoloLens 'te bir Iş veya okul hesabı kullanıyorsanız, satın alma gerçekleştirmek için mağaza uygulamasındaki kişisel hesabınızla oturum açmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="a4b8e-137">Bir ödeme yöntemi ayarlamak için [account.Microsoft.com](https://account.microsoft.com/) adresine gidin ve **ödeme & faturalandırma**  >  **ödeme seçenekleri**  >  **ödeme seçeneği Ekle**' yi seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="a4b8e-138">[ **Başlat** menüsünü](holographic-home.md)açmak için, Hololens (1. gen) üzerinde [Başlangıç hareketini](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) veya [Bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="a4b8e-139">Microsoft Store uygulamasını seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="a4b8e-140">Mağaza uygulaması açıldıktan sonra:</span><span class="sxs-lookup"><span data-stu-id="a4b8e-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="a4b8e-141">Uygulamaları aramak için arama çubuğunu kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="a4b8e-142">Seçilen kategorilerden birinden yalnızca HoloLens için oluşturulan temel uygulamaları veya uygulamaları seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="a4b8e-143">Mağaza uygulamasının sağ üst kısmında, **"..."** düğmesini seçin ve ardından, daha önce satın alınan uygulamaları görüntülemek için **Kitaplığımı** seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="a4b8e-144">Uygulamanın sayfasında Al **veya** **Al** ' ı seçin (satın alma gerekebilir).</span><span class="sxs-lookup"><span data-stu-id="a4b8e-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="a4b8e-145">Uygulamaları güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="a4b8e-145">Update Apps</span></span>

<span data-ttu-id="a4b8e-146">Microsoft Store yüklediğiniz bir uygulamayı güncelleştirmek için Microsoft Store uygulamasından uygulamayı güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="a4b8e-147">Iş için Microsoft Store yüklü uygulamalar için, bu uygulamaları Microsoft Store Iş için de güncelleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="a4b8e-148">[ **Başlat** menüsünü](holographic-home.md)açmak için, Hololens (1. gen) üzerinde [Başlangıç hareketini](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) veya [Bloom](hololens1-basic-usage.md) hareketini gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="a4b8e-149">Mağaza uygulamasını seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-149">Select the Store app.</span></span>

1. <span data-ttu-id="a4b8e-150">Mağaza uygulamasının sağ üst kısmına bakın.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="a4b8e-151">**"..."** Veya "daha fazla gör" düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4b8e-152">![Uygulama ekran görüntüsü Microsoft Store.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="a4b8e-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="a4b8e-153">**İndirmeler ve Güncelleştirmeler '** i seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="a4b8e-154">Cihazınızda daha önce güncelleştirmeler tanımlanmışsa, bekleyen güncelleştirmeleri temsil eden bir aşağı ok ve bir sayı olabilir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="a4b8e-155">**Güncelleştirme al**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-155">Select **Get updates**.</span></span> <span data-ttu-id="a4b8e-156">Cihazınız artık güncelleştirmeleri arayacak ve bunları indirip yükleyecek şekilde ayarlayacaktır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4b8e-157">![Güncelleştirmelerin alınması için uygulama ekran görüntüsü Microsoft Store..](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="a4b8e-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="a4b8e-158">Cihazınızdaki uygulamalar kuruluşunuz tarafından dağıtılmışsa, aynı ticari uygulama yönetimi yöntemleriyle de güncelleştirilemeyebilir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="a4b8e-159">Bu durum geçerliyse, [ticari uygulama dağıtımına genel bakış](app-deploy-overview.md) aracılığıyla daha fazla bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="a4b8e-160">Dışarıdan yüklenen veya dağıtılan bir özel uygulamayı güncelleştirmek isterseniz, uygulamanızın güncelleştirilmiş sürümüyle aynı yöntemi kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="a4b8e-161">Özel uygulamaları yükleme ve çalıştırma hakkında daha fazla bilgi edinmek için [özel holographic uygulamalarını](holographic-custom-apps.md)okuyun.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="a4b8e-162">Uygulamaları kaldırma</span><span class="sxs-lookup"><span data-stu-id="a4b8e-162">Uninstall apps</span></span>

<span data-ttu-id="a4b8e-163">Uygulamaları kaldırmanın üç yolu vardır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="a4b8e-164">Microsoft Store, Başlat menüsü veya ayarlardan uygulamaları kaldırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="a4b8e-165">Bir sistem uygulamasını veya Microsoft Store kaldıramıyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4b8e-166">HoloLens 2 ' de birden çok kullanıcı varsa, uygulamayı kaldırmak için uygulamayı yükleyen kullanıcı olarak oturum açmış olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="a4b8e-167">Microsoft Store kaldır</span><span class="sxs-lookup"><span data-stu-id="a4b8e-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="a4b8e-168">**Başlat** menüsünden Microsoft Store açın ve ardından kaldırmak istediğiniz uygulamaya gidin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="a4b8e-169">Mağaza sayfasında, yüklenen her uygulamanın bir **kaldırma** düğmesi vardır.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="a4b8e-170">Başlat menüsünden kaldır</span><span class="sxs-lookup"><span data-stu-id="a4b8e-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="a4b8e-171">**Başlat** menüsünde veya **tüm uygulamalar** listesinde, uygulamaya gidin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="a4b8e-172">Menü görünene kadar seçin ve basılı tutun, ardından **Kaldır**' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="a4b8e-173">Ayarlardan kaldır</span><span class="sxs-lookup"><span data-stu-id="a4b8e-173">Uninstall from Settings</span></span>
<span data-ttu-id="a4b8e-174">**Başlat** menüsünde **Ayarlar-> uygulamalar** ' ı seçin.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="a4b8e-175">Listeden uygulamayı bulun, seçin ve ardından **Kaldır**' a tıklayın.</span><span class="sxs-lookup"><span data-stu-id="a4b8e-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="a4b8e-176">Bir uygulamayı kaldıramıyorsanız lütfen geri bildirim hub 'ını kullanarak [geri bildirim gönderin](https://docs.microsoft.com/hololens/hololens-feedback) .</span><span class="sxs-lookup"><span data-stu-id="a4b8e-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
