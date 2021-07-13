---
title: Dağıtım Kılavuzu – Remote Assist HoloLens büyük ölçekte buluta bağlı ve 2 dağıtım - Yapılandırma
description: Remote Assist ile bulut bağlantılı bir ağ üzerinden HoloLens cihazları büyük ölçekte kaydetmek için yapılandırmaları ayarlamayı öğrenin.
keywords: HoloLens, yönetim, buluta bağlı, Remote Assist, AAD, Azure AD, MDM, Mobil Cihaz Yönetimi
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635152"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="dad33-104">Yapılandırma - Buluta bağlı Kılavuz</span><span class="sxs-lookup"><span data-stu-id="dad33-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="dad33-105">Kılavuzun bu bölümünde,&#39;için Otomatik Kaydı ayarlama ve hem Intune hem de Remote Assist için lisansları uygulama adımlarını aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dad33-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="dad33-106">Azure Kullanıcıları ve Grupları</span><span class="sxs-lookup"><span data-stu-id="dad33-106">Azure Users and Groups</span></span>

<span data-ttu-id="dad33-107">Bu uzantıya göre Azure ve Intune, yapılandırmaları ve lisansları atamaya yardımcı olmak için kullanıcıları ve grupları kullanır.</span><span class="sxs-lookup"><span data-stu-id="dad33-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="dad33-108">Bu dağıtım akışını doğrulamanın ve bir kullanıcıdan diğerine Remote Assist çağrısı yapmak için iki kullanıcı&#39;gerekir.</span><span class="sxs-lookup"><span data-stu-id="dad33-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="dad33-109">Lisans atama amacıyla tek bir kullanıcı grubu kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="dad33-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="dad33-110">Her iki kullanıcıyı da aynı gruba katarak Intune ve Remote Assist için bir lisans uygulayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="dad33-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="dad33-111">Henüz&#39;bir kullanıcı grubunda iki Azure AD hesabına erişiminiz yoksa; hızlı başlangıç kılavuzları şu şekildedir:</span><span class="sxs-lookup"><span data-stu-id="dad33-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="dad33-112">Kullanıcı oluşturma</span><span class="sxs-lookup"><span data-stu-id="dad33-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="dad33-113">Grup oluşturma</span><span class="sxs-lookup"><span data-stu-id="dad33-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="dad33-114">[Gruba kullanıcı ekleme](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Grup oluşturmak için oluşturulan kullanıcıları ekleme</span><span class="sxs-lookup"><span data-stu-id="dad33-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="dad33-115">[Azure AD'yi Bir Kullanıcı Grubunun cihazlara katılmasına izin](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) verecek şekilde yapılandırma – Yeni kullanıcı grubunun cihazları Azure AD'ye kaydetme izni olduğundan emin olun</span><span class="sxs-lookup"><span data-stu-id="dad33-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="dad33-116">HoloLens 2'de Otomatik Kayıt</span><span class="sxs-lookup"><span data-stu-id="dad33-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="dad33-117">Sorunsuz ve sorunsuz bir deneyim elde etmek için, Azure Active Directory 2 cihaz için Intune'a Azure Active Directory Join (AADJ) ve HoloLens Otomatik Kayıt'ı ayarlama yoludur.</span><span class="sxs-lookup"><span data-stu-id="dad33-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="dad33-118">Bu, kullanıcıların OOBE sırasında kuruluş oturum açma kimlik bilgilerini girişine ve Azure AD'ye otomatik olarak kaydolmasına ve cihazı MDM'ye kaydetmesine olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="dad33-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="dad33-119">bu [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)kullanarak Hizmetler'i seçerek deneme sürümü için Bir Premium seçene kadar Premium gezinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dad33-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="dad33-120">Otomatik Kayıt P1 için Azure Active Directory Premium 1 ve 2'nin yeterli olduğunu fark olabilir.</span><span class="sxs-lookup"><span data-stu-id="dad33-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="dad33-121">Intune'ı seçerek otomatik kayıt için kullanıcı kapsamını ve daha önce oluşturulmuş olan grubu seçerek.</span><span class="sxs-lookup"><span data-stu-id="dad33-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="dad33-122">Tüm ayrıntılar ve adımlar için [Intune için otomatik kaydı etkinleştirme kılavuzunu okuyun.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)</span><span class="sxs-lookup"><span data-stu-id="dad33-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="dad33-123">Uygulama Lisansları</span><span class="sxs-lookup"><span data-stu-id="dad33-123">Application Licenses</span></span>

<span data-ttu-id="dad33-124">Uygulama lisansı, kullanıcıların şirket tarafından satın alınan Uygulamaları yüklemelerini veya ücretsiz deneme sürümünden uygulamanın tam sürümüne yükseltmelerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="dad33-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="dad33-125">Uygulama lisansları kullanıcılara, kullanıcı gruplarına veya cihaz gruplarına uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="dad33-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="dad33-126">Uzaktan&#39;kullanmak için, kuruluşta kullanıcılar için Remote Assist lisansları gerekir.</span><span class="sxs-lookup"><span data-stu-id="dad33-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="dad33-127">Bu kılavuzun amacı doğrultusunda, yukarıda Azure Kullanıcıları ve Grupları'nda oluşturduğumuz kullanıcı grubuna Remote Assist [lisansları atayacak.](hololens2-cloud-connected-configure.md#azure-users-and-groups)</span><span class="sxs-lookup"><span data-stu-id="dad33-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="dad33-128">Lisans gereksinimleri, kullanıcının bir cihazdan Remote Assist çağrısı mı yaptığına veya cihazın uzaktan ortak Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dad33-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="dad33-129">Varsayılan olarak Remote Assist ve Teams onay kutularının her ikisi de işaretlenir.</span><span class="sxs-lookup"><span data-stu-id="dad33-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="dad33-130">Bu kılavuzun amaçları doğrultusunda, varsayılan kutuları işaretli bırakmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="dad33-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="dad33-131">Rol başına farklı Lisanslama [ve ürün gereksinimleri hakkında daha fazla bilgi edinebilirsiniz.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)</span><span class="sxs-lookup"><span data-stu-id="dad33-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="dad33-132">Birkaç farklı Türde Remote Assist lisansı olduğundan, ihtiyaçlarınıza uygun lisansları edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dad33-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="dad33-133">&#39;lisansını [edinmeniz gerekir.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="dad33-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="dad33-134">[Lisanslarınızı gruba](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) uygulama.</span><span class="sxs-lookup"><span data-stu-id="dad33-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="dad33-135">Sonraki adım</span><span class="sxs-lookup"><span data-stu-id="dad33-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dad33-136">Buluta bağlı dağıtım - Dağıtma</span><span class="sxs-lookup"><span data-stu-id="dad33-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)