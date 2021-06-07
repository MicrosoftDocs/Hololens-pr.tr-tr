---
title: HoloLens'inizi birden çok kişi ile paylaşma
description: HoloLens'i birden çok Azure Active Directory veya tek bir hesap kullanan birden çok kullanıcı tarafından paylaşılacak şekilde yapılandırabilirsiniz.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379068"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="06359-103">HoloLens'inizi birden çok kişi ile paylaşma</span><span class="sxs-lookup"><span data-stu-id="06359-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="06359-104">Bir HoloLens'i birçok kişi ile paylaşmak veya birçok kişinin bir Dizi HoloLens cihazı paylaşması yaygın bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="06359-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="06359-105">Bu makalede, bir cihazı paylaşmanın farklı yolları açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="06359-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="06359-106">Her biri kendi hesabını kullanarak birden çok kişi ile paylaşma</span><span class="sxs-lookup"><span data-stu-id="06359-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="06359-107">Önkoşul: HoloLens cihazı 1803 Windows 10 veya sonraki bir sürümü çalıştırmış olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="06359-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="06359-108">HoloLens'in (1. nesil) sürümüne [de Windows Holographic for Business.](hololens-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="06359-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="06359-109">Kullanıcılar kendi kullanıcı Azure Active Directory (Azure AD) hesaplarını kullanırsa, birden çok kullanıcı cihazda kendi kullanıcı ayarlarını ve kullanıcı verilerini saklayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="06359-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="06359-110">HoloLens'iniz üzerinde birden çok kişinin kendi hesaplarını kullanabileceğini emin olmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="06359-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="06359-111">Cihazın 1803 veya Windows 10 çalıştırıla olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="06359-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="06359-112">HoloLens (1. nesil) cihazı kullanıyorsanız, cihazı sanal [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="06359-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="06359-113">Cihazı ayarsanız, cihazı iş veya okul **sahibim'i seçin ve** bir Azure AD hesabı kullanarak oturum açın.</span><span class="sxs-lookup"><span data-stu-id="06359-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="06359-114">Kurulumu tamamladikten sonra, hesap ayarlarının **(** Ayarlar Hesapları ) Diğer  >  **kullanıcılar'ın** olduğundan **emin olun.**</span><span class="sxs-lookup"><span data-stu-id="06359-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="06359-115">HoloLens'i kullanmak için her kullanıcı şu adımları izler:</span><span class="sxs-lookup"><span data-stu-id="06359-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="06359-116">Cihazı başka bir kullanıcı kullanıyorsa, aşağıdakilerden birini yapın:</span><span class="sxs-lookup"><span data-stu-id="06359-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="06359-117">Bekleme moduna dönmek için güç düğmesine bir kez basın ve ardından kilit ekranına dönmek için güç düğmesine tekrar basın</span><span class="sxs-lookup"><span data-stu-id="06359-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="06359-118">HoloLens 2 kullanıcıları, geçerli kullanıcının oturumlarını Başlat menüsü için kullanıcı kutucuğunu seçerek kullanıcı kutucuğunu seçerek kullanıcıdan yardım alan kullanıcılar olabilir.</span><span class="sxs-lookup"><span data-stu-id="06359-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="06359-119">Cihazda oturum açma için Azure AD hesabı kimlik bilgilerinizi kullanın.</span><span class="sxs-lookup"><span data-stu-id="06359-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="06359-120">Cihazı ilk kez kullandıysanız HoloLens'i [kendi gözünize](hololens-calibration.md) ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="06359-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="06359-121">Cihaz kullanıcılarının listesini görmek veya bir kullanıcıyı cihazdan kaldırmak için Ayarlar Hesapları **Diğer**  >  **kullanıcılar'a**  >  **gidin.**</span><span class="sxs-lookup"><span data-stu-id="06359-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="06359-122">Hepsi aynı hesabı kullanarak birden çok kişi ile paylaşma</span><span class="sxs-lookup"><span data-stu-id="06359-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="06359-123">Ayrıca, tek bir kullanıcı hesabı kullanırken birden çok kullanıcı HoloLens cihazı paylaşabilir.</span><span class="sxs-lookup"><span data-stu-id="06359-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="06359-124">**HoloLens 2'de,** yeni bir kullanıcı cihazı ilk kez başına koyarken (aynı hesabın oturum açık tutularak) yeni kullanıcıdan görüntüleme deneyimini hızla ayarlamasını ve kişiselleştirmesini istenir.</span><span class="sxs-lookup"><span data-stu-id="06359-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="06359-125">Cihaz, gelecekte her kullanıcının görüntüleme deneyiminin kalitesini ve rahatsını otomatik olarak iyileştirecek şekilde ayar bilgilerini depolar.</span><span class="sxs-lookup"><span data-stu-id="06359-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="06359-126">Kullanıcıların cihazı yeniden ayarlaması gerek değildir.</span><span class="sxs-lookup"><span data-stu-id="06359-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="06359-127">**HoloLens'te (1. nesil)** hesap paylaşan kullanıcıların Ayarlar uygulamasında yeniden ölçeklendirme istemesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="06359-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="06359-128">Ayarlama hakkında daha fazla [bilgi edinin.](hololens-calibration.md)</span><span class="sxs-lookup"><span data-stu-id="06359-128">Read more about [calibration](hololens-calibration.md).</span></span>
