---
title: Katkıda bulunan yönergeler
description: GitHub-flavored Markaşağı kullanarak docs.microsoft.com platformunda HoloLens docs 'a nasıl katkıda bulunabileceğinizi öğrenin.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378982"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="e40cf-103">HoloLens belgelerine katkıda bulunma</span><span class="sxs-lookup"><span data-stu-id="e40cf-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="e40cf-104">[HoloLens belgelerine](https://github.com/MicrosoftDocs/Hololens)hoş geldiniz!</span><span class="sxs-lookup"><span data-stu-id="e40cf-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="e40cf-105">Bu depoda oluşturduğunuz veya düzenlediğiniz makaleler **herkese açık olarak görünür.**</span><span class="sxs-lookup"><span data-stu-id="e40cf-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="e40cf-106">HoloLens docs, Markdıg özellikleriyle GitHub-flavored Markaşağı kullanan docs.microsoft.com platformunda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="e40cf-107">Bu depoda düzenlediğiniz içerik, ' yi gösteren stilize sayfalarla biçimlendirilir https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="e40cf-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="e40cf-108">Bu sayfada, katkıda bulunmak için temel adımlar ve kılavuzlar ve markın temel kavramları için bağlantılar ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="e40cf-109">Katkılarınız için teşekkürler!</span><span class="sxs-lookup"><span data-stu-id="e40cf-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="e40cf-110">Kullanılabilir depolar</span><span class="sxs-lookup"><span data-stu-id="e40cf-110">Available repos</span></span>

| <span data-ttu-id="e40cf-111">Depo adı</span><span class="sxs-lookup"><span data-stu-id="e40cf-111">Repository name</span></span> | <span data-ttu-id="e40cf-112">URL</span><span class="sxs-lookup"><span data-stu-id="e40cf-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="e40cf-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="e40cf-113">HoloLens</span></span> | [<span data-ttu-id="e40cf-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="e40cf-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="e40cf-115">Karma Gerçeklik</span><span class="sxs-lookup"><span data-stu-id="e40cf-115">Mixed Reality</span></span> | [<span data-ttu-id="e40cf-116">MicrosoftDocs/Mixed-Reality</span><span class="sxs-lookup"><span data-stu-id="e40cf-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="e40cf-117">VR Tutkunmları Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="e40cf-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="e40cf-118">MicrosoftDocs/Mixed-Reality/colanıast-Guide</span><span class="sxs-lookup"><span data-stu-id="e40cf-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="e40cf-119">Başlamadan önce</span><span class="sxs-lookup"><span data-stu-id="e40cf-119">Before you start</span></span>

<span data-ttu-id="e40cf-120">Henüz bir tane yoksa [bir GitHub hesabı oluşturmanız](https://github.com/join)gerekir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="e40cf-121">Microsoft çalışanı kullanıyorsanız, GitHub hesabınızı [Microsoft açık kaynak portalındaki](https://repos.opensource.microsoft.com/)Microsoft diğer adınızla ilişkilendirin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="e40cf-122">**"Microsoft"** ve **"microsoftdocs"** kuruluşları ile birleştirin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="e40cf-123">GitHub hesabınızı ayarlarken bu güvenlik önlemlerinizi de öneriyoruz:</span><span class="sxs-lookup"><span data-stu-id="e40cf-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="e40cf-124">[Github hesabınız için güçlü bir parola](https://github.com/settings/admin)oluşturun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="e40cf-125">[İki öğeli kimlik doğrulamayı](https://github.com/settings/two_factor_authentication/configure)etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="e40cf-126">[Kurtarma kodlarınızı](https://github.com/settings/auth/recovery-codes) güvenli bir yerde saklayın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="e40cf-127">[Ortak profil ayarlarınızı](https://github.com/settings/profile)güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="e40cf-128">Adınızı ayarlayın ve e-posta *adresimi göstermek* için *Genel e-postanızı* ayarlamayı düşünün.</span><span class="sxs-lookup"><span data-stu-id="e40cf-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="e40cf-129">Katkıda bulunan docs sayfalarında bir küçük resim gösterildiğinden bir profil resmini karşıya yüklemenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="e40cf-130">Komut satırını kullanmayı planlıyorsanız, [Windows Için git kimlik bilgileri Yöneticisi 'ni](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)ayarlamayı göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="e40cf-131">Bu şekilde, her katkı yaptığınızda parolanızı girmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e40cf-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="e40cf-132">Yayımlama sistemi GitHub 'a bağlıdır, bu nedenle bu adımlar önemlidir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="e40cf-133">GitHub diğer adınızı kullanarak her bir makaleye yazar ya da katkıda bulunan olarak listelenecektir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="e40cf-134">Mevcut bir makaleyi Düzenle</span><span class="sxs-lookup"><span data-stu-id="e40cf-134">Editing an existing article</span></span>

<span data-ttu-id="e40cf-135">Bir Web tarayıcısında GitHub aracılığıyla *mevcut bir makaleye* güncelleştirme yapmak için aşağıdaki iş akışını kullanın:</span><span class="sxs-lookup"><span data-stu-id="e40cf-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e40cf-136">"Mixed-Reality-docs" klasöründe düzenlemek istediğiniz makaleye gidin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="e40cf-137">Sağ üst köşedeki Düzenle düğmesini (kurşun kalem simgesi) seçin. Bu, bir atılabilir dalını ' Ana ' dalından otomatik olarak çatallandıracaktır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bir makaleyi düzenleyin.](images/editpage.png)
   
3. <span data-ttu-id="e40cf-139">Makalenin içeriğini ["Markaşağı temel bilgiler"](#markdown-basics)e göre düzenleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="e40cf-140">Her bir makalenin üst kısmındaki meta verileri güncelleştir:</span><span class="sxs-lookup"><span data-stu-id="e40cf-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="e40cf-141">**title**: makale görüntülenirken tarayıcı sekmesinde görüntülenen sayfa başlığı.</span><span class="sxs-lookup"><span data-stu-id="e40cf-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="e40cf-142">Sayfa başlıkları, SEO ve dizin oluşturma için kullanılır; bu nedenle, gerekli olmadığı takdirde başlığı değiştirmeyin (ancak belgeler genel çalışmadan önce daha az kritik olur).</span><span class="sxs-lookup"><span data-stu-id="e40cf-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="e40cf-143">**Açıklama**: makalenin içeriğine yönelik kısa bir açıklama yazın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="e40cf-144">**Yazar**: sayfanın birincil sahibiyseniz, GitHub diğer adınızı buraya ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="e40cf-145">**MS. Author**: sayfanın birincil sahibiyseniz, Microsoft diğer adınızı buraya ekleyin (gerekli değildir @microsoft.com , yalnızca diğer ad).</span><span class="sxs-lookup"><span data-stu-id="e40cf-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="e40cf-146">**MS. Date**: sayfaya önemli içerik ekliyorsanız, açıklama, biçimlendirme, dilbilgisi veya yazım gibi düzeltmeler için değil, tarihi güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="e40cf-147">**anahtar sözcükler**: SEO 'e yardımcı anahtar kelimeleri (arama motoru iyileştirmesi).</span><span class="sxs-lookup"><span data-stu-id="e40cf-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="e40cf-148">Makalenize özgü, ancak listenizdeki son anahtar sözcükten sonra noktalama olmadan, bir virgül ve boşlukla ayırarak anahtar sözcükler ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="e40cf-149">Diğer bir yerde yönetildiği için tüm makalelere uygulanan genel anahtar sözcükler eklemeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="e40cf-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="e40cf-150">Makale düzenlemelerinizi tamamladıktan sonra aşağı kaydırın ve **dosya değişikliği öner**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="e40cf-151">Bir sonraki sayfada, otomatik olarak oluşturulan dalınızı ' Ana ' ile birleştirmek için **çekme Isteği oluştur** ' u seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="e40cf-152">Düzenlemek istediğiniz Sonraki Makale için yukarıdaki adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="e40cf-153">Mevcut bir makaleyi yeniden adlandırma veya silme</span><span class="sxs-lookup"><span data-stu-id="e40cf-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="e40cf-154">Değişiklik, var olan bir makaleyi yeniden adlandırabilir veya silecektir, yeniden yönlendirme eklediğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="e40cf-155">Bu şekilde, mevcut makaleye bağlantısı olan herkes doğru yerde sona kalır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="e40cf-156">Yeniden yönlendirmeler, deponun kökündeki .openpublishing.redirection.jsdosya tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="e40cf-157">.openpublishing.redirection.jsbir yeniden yönlendirme eklemek için diziye bir giriş ekleyin `redirections` :</span><span class="sxs-lookup"><span data-stu-id="e40cf-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="e40cf-158">, `source_path` Kaldırmakta olduğunuz eski makalenin göreli depo yoludur.</span><span class="sxs-lookup"><span data-stu-id="e40cf-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="e40cf-159">Yolun ile başladığı `mixed-reality-docs` ve ile bitdiğinizden emin olun `.md` .</span><span class="sxs-lookup"><span data-stu-id="e40cf-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="e40cf-160">, `redirect_url` Eski makalenin yeni makaleye yönelik göreli genel URL 'sidir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="e40cf-161">Bu **URL 'nin** `mixed-reality-docs` `.md` , depo yolu değil genel URL 'ye başvurduğundan veya içermediğinden emin olun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="e40cf-162">Kullanarak yeni makaledeki bir bölüme bağlama `#section` izin verilir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="e40cf-163">Ayrıca, gerekirse başka bir sitenin mutlak yolunu da kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="e40cf-164">`redirect_document_id` Belge KIMLIĞINI önceki dosyadan korumak isteyip istemediğinizi belirtir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="e40cf-165">Varsayılan değer: `false`.</span><span class="sxs-lookup"><span data-stu-id="e40cf-165">The default is `false`.</span></span> <span data-ttu-id="e40cf-166">`true` `ms.documentid` Yeniden yönlendirilen makaleden öznitelik değerini korumak istiyorsanız kullanın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="e40cf-167">Belge KIMLIĞINI korumazsanız, sayfa görünümleri ve ranlar gibi veriler hedef makaleye aktarılır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="e40cf-168">Yeniden yönlendirme birincil olarak bir yeniden adlandırma ise ve yalnızca aynı içeriğin bazılarını ele alan farklı bir makaleye işaretçi değilse bunu yapın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="e40cf-169">Yeniden yönlendirme eklerseniz, eski dosyayı da silmeyi unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="e40cf-170">Yeni bir makale oluşturma</span><span class="sxs-lookup"><span data-stu-id="e40cf-170">Creating a new article</span></span>

<span data-ttu-id="e40cf-171">Bir Web tarayıcısında GitHub aracılığıyla belge deposunda *yeni makaleler oluşturmak* için aşağıdaki iş akışını kullanın:</span><span class="sxs-lookup"><span data-stu-id="e40cf-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="e40cf-172">MicrosoftDocs/Mixed-Reality ' Ana ' dalından bir çatal oluşturun (sağ üst köşedeki **çatal** düğmesini kullanarak).</span><span class="sxs-lookup"><span data-stu-id="e40cf-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Ana dalı çatalla.](images/forkbranch.png)
   
2. <span data-ttu-id="e40cf-174">"Mixed-Reality-docs" klasöründe, sağ üst köşedeki **yeni dosya oluştur** ' u seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="e40cf-175">Makale için bir sayfa adı oluşturun (boşluk yerine kısa çizgileri kullanın ve noktalama işaretleri veya kesme işareti kullanmayın) ve ". MD" ekleyin</span><span class="sxs-lookup"><span data-stu-id="e40cf-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Yeni sayfanızı adlandırın.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="e40cf-177">Yeni makaleyi, "Mixed-Reality-docs" klasörü içinden oluşturduğunuzdan emin olun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="e40cf-178">Bunu, yeni dosya adı satırında "/Mixed-Reality-je/" olup olmadığını denetleyerek doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="e40cf-179">Yeni sayfanızın en üstünde aşağıdaki meta veri bloğunu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="e40cf-179">At the top of your new page, add the following metadata block:</span></span>

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. <span data-ttu-id="e40cf-180">[Yukarıdaki bölümde](#editing-an-existing-article)yer alan yönergelere göre ilgili meta veri alanlarını girin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="e40cf-181">[Markın temel bilgilerini](#markdown-basics)kullanarak Makale içeriği yazın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="e40cf-182">`## See also`Makalenin alt kısmına, diğer ilgili makalelerin bağlantılarıyla bir bölüm ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="e40cf-183">İşiniz bittiğinde **yeni dosya Kaydet**' i seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="e40cf-184">**Yeni çekme isteği ' ni** seçin ve çatalınızın ' Ana ' dalını microsoftdocs/Mixed-Reality ' Master ' olarak birleştirin (okun doğru şekilde göründüğünden emin olun).</span><span class="sxs-lookup"><span data-stu-id="e40cf-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Çatalınızdan, MicrosoftDocs/Mixed-Reality olarak çekme isteği oluşturun](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="e40cf-186">Markdown temelleri</span><span class="sxs-lookup"><span data-stu-id="e40cf-186">Markdown basics</span></span>

<span data-ttu-id="e40cf-187">Aşağıdaki kaynaklar markın dilini kullanarak belgeleri nasıl düzenleyeceğinizi öğrenmenize yardımcı olur:</span><span class="sxs-lookup"><span data-stu-id="e40cf-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="e40cf-188">Markdown temelleri</span><span class="sxs-lookup"><span data-stu-id="e40cf-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="e40cf-189">Docs.microsoft.com için Markaşağı yazmak üzere ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="e40cf-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="e40cf-190">Tablo ekleme</span><span class="sxs-lookup"><span data-stu-id="e40cf-190">Adding tables</span></span>

<span data-ttu-id="e40cf-191">Docs.microsoft.com stilleri tablolarında, satır içi CSS ' yi deneseniz bile kenarlıklar veya özel stilleri olmaz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="e40cf-192">Kısa bir süre boyunca çalışır, ancak sonunda platform stili tablonun dışına çıkaracaktır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="e40cf-193">Bu nedenle, önceden planlayın ve tablolarınızı basit tutun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="e40cf-194">[Markın tablolarının kolay hale gelmesini sağlayan bir site aşağıda verilmiştir](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="e40cf-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="e40cf-195">[Visual Studio Code Için docs Markaşağı uzantısı](https://docs.microsoft.com/teamblog/docs-extension) , belgeleri düzenlemek için [Visual Studio Code kullanıyorsanız (aşağıya bakın)](#using-visual-studio-code) tablo oluşturmayı da kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="e40cf-196">Görüntü ekleme</span><span class="sxs-lookup"><span data-stu-id="e40cf-196">Adding images</span></span>

<span data-ttu-id="e40cf-197">Görüntülerinizi, depodaki "Mixed-Reality-docs/Images" klasörüne yüklemeniz ve sonra makaleye uygun şekilde başvurmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="e40cf-198">Görüntüler otomatik olarak tam boyutta görünür, bu da büyük görüntülerin makalenin tüm genişliğini doldurmasıdır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="e40cf-199">Karşıya yüklemeden önce görüntülerinizi önceden boyutlandırmasını öneririz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="e40cf-200">Önerilen genişlik 600 ile 700 piksel arasındadır; Ancak, yoğun bir ekran görüntüsü veya ekran görüntüsünün bir kesri ise, bu boyut yukarı veya aşağı doğru olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e40cf-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e40cf-201">Birleştirmeden önce görüntüleri yalnızca bir mürekkepli repoya yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="e40cf-202">Bu nedenle, bir makaleye görüntü eklemeyi planlıyorsanız, önce [Visual Studio Code'yi](#using-visual-studio-code) kullanarak görüntüleri bir web tarayıcısında kendi fork 'nizin "images" klasörüne eklemeniz veya aşağıdaki adımları tamamlayasınız:</span><span class="sxs-lookup"><span data-stu-id="e40cf-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="e40cf-203">MicrosoftDocs/mixed-reality repo'su için bir mürekkep.</span><span class="sxs-lookup"><span data-stu-id="e40cf-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="e40cf-204">Makaleyi, mürekkeple birlikte düzenledik.</span><span class="sxs-lookup"><span data-stu-id="e40cf-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="e40cf-205">Makalenize başvurmakta olduğunuz görüntüleri, mürekkepte "mixed-reality-docs/images" klasörüne yükleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="e40cf-206">MicrosoftDocs/mixed-reality 'master' dalı ile mürekkeplerinizi birleştirmek için bir çekme isteği oluşturuldu. </span><span class="sxs-lookup"><span data-stu-id="e40cf-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="e40cf-207">Kendi forked repo'larınızı ayarlamayı öğrenmek için yeni bir makale [oluşturmaya ilişkin yönergeleri izleyin.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="e40cf-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="e40cf-208">Çalışmanızı önizleme</span><span class="sxs-lookup"><span data-stu-id="e40cf-208">Previewing your work</span></span>

<span data-ttu-id="e40cf-209">GitHub'da web tarayıcısı aracılığıyla düzenlerken,  işlemeden önce çalışmanızı önizlemek için sayfanın üst kısmından Önizleme sekmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="e40cf-210">Değişikliklerinizin önizlemesini review.docs.microsoft.com yalnızca Microsoft çalışanları tarafından kullanılabilir</span><span class="sxs-lookup"><span data-stu-id="e40cf-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="e40cf-211">Microsoft çalışanları: Katkılarınız 'ana' dala birleştirildi mi, içeriği'de genele gitmeden önce gözden https://review.docs.microsoft.com/hololens?branch=master geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="e40cf-212">Sol sütundaki içindekiler'i kullanarak makalenizi bulun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="e40cf-213">Tarayıcıda düzenleme ve masaüstü istemcisiyle düzenleme karşılaştırması</span><span class="sxs-lookup"><span data-stu-id="e40cf-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="e40cf-214">Tarayıcıda düzenleme, hızlı değişiklikler yapmanın en kolay yolu olabilir ancak bazı dezavantajlar vardır:</span><span class="sxs-lookup"><span data-stu-id="e40cf-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="e40cf-215">Yazım denetimine gerek yok.</span><span class="sxs-lookup"><span data-stu-id="e40cf-215">You don't get spell-check.</span></span>
- <span data-ttu-id="e40cf-216">Diğer makalelere herhangi bir akıllı bağlantı elde etmeyebilirsiniz (makalenin dosya adını el ile yazmanız gerekir).</span><span class="sxs-lookup"><span data-stu-id="e40cf-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="e40cf-217">Görüntüleri karşıya yüklemek ve başvuru yapmak zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="e40cf-218">Bu sorunları ele alamamayı tercih ediyorsanız, katkıda bulunmak için [Visual Studio Code](https://code.visualstudio.com/) uzantılarla birlikte kullanmak gibi [bir masaüstü](#useful-extensions) istemcisi kullanın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="e40cf-219">Visual Studio Code’u kullanma</span><span class="sxs-lookup"><span data-stu-id="e40cf-219">Using Visual Studio Code</span></span>

<span data-ttu-id="e40cf-220">Yukarıda listelenen [nedenlerle,](#editing-in-the-browser-vs-editing-with-a-desktop-client)belgeleri düzenlemek için web tarayıcısı yerine masaüstü istemcisi kullanmayı tercih edersiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="e40cf-221">Visual Studio Code. [](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="e40cf-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="e40cf-222">Kurulum</span><span class="sxs-lookup"><span data-stu-id="e40cf-222">Setup</span></span>

<span data-ttu-id="e40cf-223">Bu repo ile çalışacak Visual Studio Code yapılandırmak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="e40cf-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="e40cf-224">Web tarayıcısında:</span><span class="sxs-lookup"><span data-stu-id="e40cf-224">In a web browser:</span></span>
    1. <span data-ttu-id="e40cf-225">Bilgisayarınız [için Git'i yükleyin.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="e40cf-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="e40cf-226">yükleme [Visual Studio Code.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="e40cf-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="e40cf-227">[Henüz bir sorun yoksa MicrosoftDocs/mixed-reality'den](#creating-a-new-article) bir fork edin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="e40cf-228">Mürekkepte Kopyala'ya tıklayın **veya url'yi** indirip kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="e40cf-229">Visual Studio Code'da kendi mürekkep kopyanızı yerel Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="e40cf-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="e40cf-230">Görünüm menüsünde **Komut** **Paleti'ne tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="e40cf-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="e40cf-231">"Git: Clone" yazın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="e40cf-232">Kopyalanan URL'yi yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="e40cf-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="e40cf-233">Kopyanın bilgisayarınıza kaydedile yerini seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="e40cf-234">Açılan **pencerede Open repo** (Repo aç) öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="e40cf-235">Belgeleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="e40cf-235">Editing documentation</span></span>

<span data-ttu-id="e40cf-236">Aşağıdaki iş akışını kullanarak belgelerde değişiklik Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="e40cf-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="e40cf-237">Yukarıdan itibaren makale [düzenleme](#editing-an-existing-article) ve [oluşturma](#creating-a-new-article) ile ilgili tüm kılavuzlar ve [Markdown'ı](#markdown-basics)düzenlemenin temelleri, Visual Studio Code de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="e40cf-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="e40cf-238">Kopyalanan mürekkep resmi bir resm ile güncel olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="e40cf-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="e40cf-239">Bir web tarayıcısında, MicrosoftDocs/mixed-reality 'master' belgesinde bulunan diğer katkıda bulunanlardan gelen son değişikliklerinizi kendi fork'nize eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ettiglerinden emin olun).</span><span class="sxs-lookup"><span data-stu-id="e40cf-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/mixed-reality değişikliklerini kendi fork'la eşitleme](images/sync-repos.png)
      
   2. <span data-ttu-id="e40cf-241">Yeni Visual Studio Code yeni güncelleştirilmiş mürekkeplerinizi yerel kopyayla eşitlemek için eşitle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Eşitle düğmesine tıklayın resmi](images/sync-clone.png)
      
2. <span data-ttu-id="e40cf-243">Kopyalanan bir hesabı kullanarak kopyalanmış bir şekilde makale Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e40cf-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="e40cf-244">Bir veya daha fazla makaleyi düzenleyin (gerekirse "images" klasörüne görüntü ekleyin).</span><span class="sxs-lookup"><span data-stu-id="e40cf-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="e40cf-245">**Explorer'da** değişiklikleri **kaydedin.**</span><span class="sxs-lookup"><span data-stu-id="e40cf-245">**Save** changes in **Explorer**.</span></span>
      
      ![Gezgin'de "Hepsini kaydet"i seçin](images/explorer-save.png)
      
   3. <span data-ttu-id="e40cf-247">**Kaynak Denetiminde** tüm **değişiklikleri işle** (istendiğinde işleme iletisi yazın).</span><span class="sxs-lookup"><span data-stu-id="e40cf-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Kaynak Denetiminde "Hepsini işle"yi seçin](images/source-control-commit.png)
      
   4. <span data-ttu-id="e40cf-249">Değişikliklerinizi **çıkış** noktasıyla (GitHub'daki çatalı) eşitlemek için eşitle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Eşitle düğmesine tıklayın](images/sync-back.png)
      
3. <span data-ttu-id="e40cf-251">Bir web tarayıcısında, yeni değişiklikleri microsoftDocs/mixed-reality 'master' ile eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ediyor olduğundan emin olun).</span><span class="sxs-lookup"><span data-stu-id="e40cf-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturma](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="e40cf-253">Yararlı uzantılar</span><span class="sxs-lookup"><span data-stu-id="e40cf-253">Useful extensions</span></span>

<span data-ttu-id="e40cf-254">Aşağıdaki Visual Studio Code uzantıları, belgeleri düzenlerken yararlıdır:</span><span class="sxs-lookup"><span data-stu-id="e40cf-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="e40cf-255">[Visual Studio Code için Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Uzantısı - **Alt+M** kullanarak aşağıdakiler gibi bir belge yazma seçenekleri menüsü açın:</span><span class="sxs-lookup"><span data-stu-id="e40cf-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="e40cf-256">Karşıya yüklediğiniz görüntüleri arama ve referans olarak gönderme.</span><span class="sxs-lookup"><span data-stu-id="e40cf-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="e40cf-257">Listeler, tablolar ve gibi belgelere özgü çağrılar gibi biçimlendirmeler `>[!NOTE]` ekleyin.</span><span class="sxs-lookup"><span data-stu-id="e40cf-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="e40cf-258">İç bağlantılar ve yer işaretleri (bir sayfanın içindeki belirli bölümlere bağlantılar) arama ve başvuru.</span><span class="sxs-lookup"><span data-stu-id="e40cf-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="e40cf-259">Biçimlendirme hataları vurgulanmış (daha fazla bilgi edinmek için farenizi hatanın üzerine gelin).</span><span class="sxs-lookup"><span data-stu-id="e40cf-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="e40cf-260">[Kod Yazım Denetleyicisi](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - yanlış yazılmış sözcüklerin altı çizili olur; yanlış yazılmış bir sözlüğe sağ tıklar ve sözlüğünü değiştirir veya sözlüğe kaydedebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e40cf-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
