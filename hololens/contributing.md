---
title: Katkıda bulunan yönergeler
description: HoloLens markdown kullanarak docs.microsoft.com platformda GitHub nasıl katkıda bulunabilirsiniz?
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635679"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="b0d21-103">HoloLens katkıda bulunuyor</span><span class="sxs-lookup"><span data-stu-id="b0d21-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="b0d21-104">[HoloLens hoş geldiniz!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="b0d21-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="b0d21-105">Bu repoda oluştur veya düzenleyişle ilgili tüm **makaleler genel olarak görünür.**</span><span class="sxs-lookup"><span data-stu-id="b0d21-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="b0d21-106">HoloLens belgeleri, Markdig özellikleriyle GitHub Markdown kullanan docs.microsoft.com platformda görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="b0d21-107">Bu repoda düzenley istediğiniz içerik, /hololens'te yer alan stilleştirilmiş sayfalara biçimlendirilecek.</span><span class="sxs-lookup"><span data-stu-id="b0d21-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="b0d21-108">Bu sayfa, katkıda bulunmak için temel adımları ve yönergeleri ve Markdown temel bilgileri bağlantılarını kapsar.</span><span class="sxs-lookup"><span data-stu-id="b0d21-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="b0d21-109">Katkılarınız için teşekkürler!</span><span class="sxs-lookup"><span data-stu-id="b0d21-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="b0d21-110">Kullanılabilir repos</span><span class="sxs-lookup"><span data-stu-id="b0d21-110">Available repos</span></span>

| <span data-ttu-id="b0d21-111">Depo adı</span><span class="sxs-lookup"><span data-stu-id="b0d21-111">Repository name</span></span> | <span data-ttu-id="b0d21-112">URL</span><span class="sxs-lookup"><span data-stu-id="b0d21-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="b0d21-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="b0d21-113">HoloLens</span></span> | [<span data-ttu-id="b0d21-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="b0d21-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="b0d21-115">Karma Gerçeklik</span><span class="sxs-lookup"><span data-stu-id="b0d21-115">Mixed Reality</span></span> | [<span data-ttu-id="b0d21-116">MicrosoftDocs/karma gerçeklik</span><span class="sxs-lookup"><span data-stu-id="b0d21-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="b0d21-117">VR Meraklıları Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="b0d21-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="b0d21-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span><span class="sxs-lookup"><span data-stu-id="b0d21-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="b0d21-119">Başlamadan önce</span><span class="sxs-lookup"><span data-stu-id="b0d21-119">Before you start</span></span>

<span data-ttu-id="b0d21-120">Henüz bir hesabınız yoksa bir hesap oluşturmanız [GitHub gerekir.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="b0d21-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="b0d21-121">Microsoft çalışanıysanız, microsoft GitHub Microsoft Açık Kaynak portalında Microsoft diğer [adınıza bağlamanız gerekir.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="b0d21-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="b0d21-122">**"Microsoft" ve** **"MicrosoftDocs" kuruluşlarına** katılın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="b0d21-123">Hesap GitHub ayarlarken şu güvenlik önlemlerini de öneririz:</span><span class="sxs-lookup"><span data-stu-id="b0d21-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="b0d21-124">Hesap [hesabınız için güçlü bir GitHub oluşturun.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="b0d21-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="b0d21-125">İki [faktörlü kimlik doğrulamasını etkinleştirin.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="b0d21-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="b0d21-126">Kurtarma [kodlarınızı güvenli](https://github.com/settings/auth/recovery-codes) bir yere kaydedin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="b0d21-127">Genel profil [ayarlarınızı güncelleştirin.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="b0d21-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="b0d21-128">Adınız olarak ayarlayın ve Genel e-postanızı *E-posta adresimi gösterme olarak ayarlayın.* </span><span class="sxs-lookup"><span data-stu-id="b0d21-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="b0d21-129">Katkıda bulunmak istediğiniz belge sayfalarında küçük resim gösterildiği için profil resmini karşıya yüklemenizi öneririz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="b0d21-130">Komut satırı kullanmayı planlıyorsanız, git için [Git Kimlik Bilgileri Yöneticisi'Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)</span><span class="sxs-lookup"><span data-stu-id="b0d21-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="b0d21-131">Bu şekilde, her katkıda parolanızı girmenize gerek olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="b0d21-132">Yayımlama sistemi, GitHub bu nedenle önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="b0d21-133">Diğer adınız kullanılarak her makalenin yazarı veya katkıda bulunanı olarak GitHub listelenirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="b0d21-134">Mevcut bir makaleyi düzenleme</span><span class="sxs-lookup"><span data-stu-id="b0d21-134">Editing an existing article</span></span>

<span data-ttu-id="b0d21-135">Web tarayıcısında mevcut bir makalede *güncelleştirmeler yapmak için* GitHub iş akışını kullanın:</span><span class="sxs-lookup"><span data-stu-id="b0d21-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="b0d21-136">"mixed-reality-docs" klasöründe düzenlemek istediğiniz makaleye gidin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="b0d21-137">Sağ üst köşesindeki düzenle düğmesini (kalem simgesi) seçerek otomatik olarak "ana" daldan atılabilir bir dal oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="b0d21-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Bir makaleyi düzenleme.](images/editpage.png)
   
3. <span data-ttu-id="b0d21-139">Makalenin içeriğini ["Markdown temel bilgileri" makalesine göre düzenleyin.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="b0d21-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="b0d21-140">Her makalenin en üstünde yer alan meta verileri güncelleştirin:</span><span class="sxs-lookup"><span data-stu-id="b0d21-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="b0d21-141">**title:** Makale görüntülendiğinde tarayıcı sekmesinde görüntülenen sayfa başlığı.</span><span class="sxs-lookup"><span data-stu-id="b0d21-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="b0d21-142">Sayfa başlıkları SEO ve dizin oluşturma için kullanılır, bu nedenle gerekli olmadıkça başlığı değiştirme (belgeler genel hale gelmeden önce bu daha az kritik olsa da).</span><span class="sxs-lookup"><span data-stu-id="b0d21-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="b0d21-143">**açıklama:** Makalenin içeriğine ilişkin kısa bir açıklama yazarak SEO ve bulma desteği sağlar.</span><span class="sxs-lookup"><span data-stu-id="b0d21-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="b0d21-144">**yazar:** Sayfanın birincil sahibiyseniz sayfanın diğer adını buraya GitHub ekleyin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="b0d21-145">**ms.author:** Sayfanın birincil sahibiyseniz, Microsoft diğer adını buraya ekleyin (yalnızca diğer adı @microsoft.com için ihtiyacınız yok).</span><span class="sxs-lookup"><span data-stu-id="b0d21-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="b0d21-146">**ms.date:** Sayfaya önemli içerik ekliyorsanız tarihi güncelleştirin, ancak açıklama, biçimlendirme, dil bilgisi veya yazım gibi düzeltmeler için güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="b0d21-147">**keywords:** Keywords aid in SEO (search engine optimization).</span><span class="sxs-lookup"><span data-stu-id="b0d21-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="b0d21-148">Makalenize özgü olan ancak listenizin son anahtar sözcüğünden sonra noktalama işareti eklemeden virgülle ve boşlukla ayrılmış anahtar sözcükler ekleyin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="b0d21-149">Tüm makaleler için geçerli olan genel anahtar sözcükler eklemenize gerek yok çünkü bunlar başka bir yerde yönetiliyor.</span><span class="sxs-lookup"><span data-stu-id="b0d21-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="b0d21-150">Makale düzenlemelerinizi tamamlandıktan sonra sayfayı aşağı kaydırın ve Dosya değişikliği **öner'i seçin.**</span><span class="sxs-lookup"><span data-stu-id="b0d21-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="b0d21-151">Sonraki sayfada Çekme isteği **oluştur'a seçerek** otomatik olarak oluşturulan dalını 'ana dal' olarak birleştirin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="b0d21-152">Düzenlemek istediğiniz sonraki makale için yukarıdaki adımları tekrarlayın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="b0d21-153">Mevcut bir makaleyi yeniden markalama veya silme</span><span class="sxs-lookup"><span data-stu-id="b0d21-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="b0d21-154">Değişikliğiniz mevcut bir makaleyi yeniden adlandıracak veya secekse, yeniden yönlendirme eklemeye emin olun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="b0d21-155">Bu şekilde, mevcut makaleye bağlantısı olan herkes yine de doğru yerde olur.</span><span class="sxs-lookup"><span data-stu-id="b0d21-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="b0d21-156">Yeniden yönlendirmeler, .openpublishing.redirection.jsdosyasının kökünde yer alan dosyada yer alan dosya tarafından yönetilir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="b0d21-157">Yeniden yönlendirmeyi .openpublishing.redirection.jsdizisine bir giriş `redirections` ekleyin:</span><span class="sxs-lookup"><span data-stu-id="b0d21-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="b0d21-158">`source_path`, kaldırmakta olduğunu eski makalenin göreli depo yoludur.</span><span class="sxs-lookup"><span data-stu-id="b0d21-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="b0d21-159">Yolun ile başladığından ve ile `mixed-reality-docs` sona erdiğinden emin `.md` olun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="b0d21-160">`redirect_url`, eski makaleden yeni makaleye göreli genel URL'dir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="b0d21-161">Depo yolunu değil **genel URL'ye** başvurduğu için bu `mixed-reality-docs` URL'nin veya `.md` içermey olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="b0d21-162">kullanarak yeni makalenin içindeki bir bölüme `#section` bağlamaya izin verilir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="b0d21-163">Gerekirse burada başka bir sitenin mutlak yolunu da kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="b0d21-164">`redirect_document_id` , belge kimliğini önceki dosyadan tutmak isteyip istemeyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="b0d21-165">Varsayılan değer: `false`.</span><span class="sxs-lookup"><span data-stu-id="b0d21-165">The default is `false`.</span></span> <span data-ttu-id="b0d21-166">Yeniden `true` yönlendirilen makaledeki `ms.documentid` öznitelik değerini korumak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="b0d21-167">Belge kimliğini korursanız sayfa görüntülemeleri ve derecelendirmeler gibi veriler hedef makaleye aktarılır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="b0d21-168">Yeniden yönlendirme öncelikli olarak bir yeniden adlandırma ise ve aynı içeriğin yalnızca bir bölümü kapsayan farklı bir makale işaretçisi ise bunu yapma.</span><span class="sxs-lookup"><span data-stu-id="b0d21-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="b0d21-169">Yeniden yönlendirme eklersiniz, eski dosyayı da silebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="b0d21-170">Yeni makale oluşturma</span><span class="sxs-lookup"><span data-stu-id="b0d21-170">Creating a new article</span></span>

<span data-ttu-id="b0d21-171">Web tarayıcısında yeni *makaleler oluşturmak için* aşağıdaki iş akışını kullanarak GitHub kullanın:</span><span class="sxs-lookup"><span data-stu-id="b0d21-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="b0d21-172">MicrosoftDocs/mixed-reality 'master' dalını kullanarak bir mürekkep oluşturun (sağ **üstte yer** alan Fork düğmesini kullanarak).</span><span class="sxs-lookup"><span data-stu-id="b0d21-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Ana dalda bir mürekkep.](images/forkbranch.png)
   
2. <span data-ttu-id="b0d21-174">"mixed-reality-docs" klasöründe sağ üst **sırada Yeni dosya oluştur'a** tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="b0d21-175">Makale için bir sayfa adı oluşturun (boşluk yerine kısa çizgi kullanın ve noktalama işareti veya kesme işareti kullanmayın) ve ".md" ifadesini ekleyin</span><span class="sxs-lookup"><span data-stu-id="b0d21-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Yeni sayfanıza bir ad girin.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="b0d21-177">Yeni makaleyi "mixed-reality-docs" klasöründen oluştursanız emin olun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="b0d21-178">Yeni dosya adı satırına "/mixed-reality-docs/" ifadesini kontrol ederek bunu onaylayın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="b0d21-179">Yeni sayfanın en üstüne aşağıdaki meta veri bloğu ekleyin:</span><span class="sxs-lookup"><span data-stu-id="b0d21-179">At the top of your new page, add the following metadata block:</span></span>

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

5. <span data-ttu-id="b0d21-180">Yukarıdaki bölümde yer alan yönergelere göre ilgili meta veri [alanlarını doldurun.](#editing-an-existing-article)</span><span class="sxs-lookup"><span data-stu-id="b0d21-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="b0d21-181">Markdown temellerini [kullanarak makale içeriği yazın.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="b0d21-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="b0d21-182">Makalenin `## See also` en altına diğer ilgili makalelerin bağlantılarını içeren bir bölüm ekleyin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="b0d21-183">Tamamlandığında Yeni dosya **işle'yi seçin.**</span><span class="sxs-lookup"><span data-stu-id="b0d21-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="b0d21-184">Yeni **çekme isteği'yi** seçin ve mürekkep 'ana' dalını MicrosoftDocs/mixed-reality 'master' ile birleştirin (okun doğru yolu işaret eden olduğundan emin olun).</span><span class="sxs-lookup"><span data-stu-id="b0d21-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturma](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="b0d21-186">Markdown temelleri</span><span class="sxs-lookup"><span data-stu-id="b0d21-186">Markdown basics</span></span>

<span data-ttu-id="b0d21-187">Aşağıdaki kaynaklar, Markdown dilini kullanarak belgeleri düzenlemeyi öğrenmenizi sağlar:</span><span class="sxs-lookup"><span data-stu-id="b0d21-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="b0d21-188">Markdown temelleri</span><span class="sxs-lookup"><span data-stu-id="b0d21-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="b0d21-189">Docs.microsoft.com için Markdown yazmak için ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b0d21-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="b0d21-190">Tablo ekleme</span><span class="sxs-lookup"><span data-stu-id="b0d21-190">Adding tables</span></span>

<span data-ttu-id="b0d21-191">Stil tablolarının docs.microsoft.com nedeniyle satır içi CSS'i denesanız bile kenarlıklar veya özel stiller olmayacaktır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="b0d21-192">Kısa bir süre çalışacak gibi görünür, ancak sonunda platform stili tablodan çıkartır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="b0d21-193">Bu nedenle plan yapmayı ve tablolarınızı basit tutmaya devam edin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="b0d21-194">[Markdown tablolarını kolaylaştıran bir site şu şekildedir:](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="b0d21-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="b0d21-195">[Visual Studio Code için Docs Markdown](/teamblog/docs-extension) Uzantısı, belgeleri düzenlemek için Visual Studio Code [(aşağıya bakın)](#using-visual-studio-code) kullanıyorsanız tablo oluşturmayı da kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="b0d21-196">Görüntü ekleme</span><span class="sxs-lookup"><span data-stu-id="b0d21-196">Adding images</span></span>

<span data-ttu-id="b0d21-197">Görüntülerinizi,po içinde "mixed-reality-docs/images" klasörüne yüklemeli ve ardından makalede uygun şekilde başvurabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="b0d21-198">Görüntüler otomatik olarak tam boyutlu olarak görüntülenir ve bu da büyük görüntülerin makalenin tüm genişliğini dolduracak olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="b0d21-199">Karşıya yüklemeden önce görüntülerinizi önceden boyutlandırmanızı öneririz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="b0d21-200">Önerilen genişlik 600 ile 700 piksel arasında olsa da, sırasıyla yoğun bir ekran görüntüsü veya ekran görüntüsü kesri olması için boyutu yukarı veya aşağı doğru boyutunuz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b0d21-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b0d21-201">Birleştirmeden önce görüntüleri yalnızca bir mürekkepli repoya yükleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="b0d21-202">Bu nedenle, bir makaleye görüntü eklemeyi planlıyorsanız, önce [Visual Studio Code](#using-visual-studio-code) kullanarak görüntüleri bir web tarayıcısında kendi fork 'nizin "images" klasörüne eklemeniz veya aşağıdaki adımları gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="b0d21-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="b0d21-203">MicrosoftDocs/mixed-reality repo'su için bir mürekkep.</span><span class="sxs-lookup"><span data-stu-id="b0d21-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="b0d21-204">Makaleyi, mürekkeple birlikte düzenledik.</span><span class="sxs-lookup"><span data-stu-id="b0d21-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="b0d21-205">Makalenize başvurmakta olduğunuz görüntüleri, mürekkepte "mixed-reality-docs/images" klasörüne yükleyin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="b0d21-206">MicrosoftDocs/mixed-reality 'master' dalı ile mürekkeplerinizi birleştirmek için bir çekme isteği oluşturuldu. </span><span class="sxs-lookup"><span data-stu-id="b0d21-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="b0d21-207">Kendi forked repo'larınızı ayarlamayı öğrenmek için, yeni bir makale [oluşturmaya ilişkin yönergeleri izleyin.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="b0d21-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="b0d21-208">Çalışmanızı önizleme</span><span class="sxs-lookup"><span data-stu-id="b0d21-208">Previewing your work</span></span>

<span data-ttu-id="b0d21-209">Web tarayıcısı GitHub web tarayıcısında düzenlerken, işlemeden önce çalışmanızı önizlemek için sayfanın üst kısmından Önizleme sekmesini seçin. </span><span class="sxs-lookup"><span data-stu-id="b0d21-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="b0d21-210">Değişikliklerinizin önizlemesini review.docs.microsoft.com yalnızca Microsoft çalışanları tarafından kullanılabilir</span><span class="sxs-lookup"><span data-stu-id="b0d21-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="b0d21-211">Microsoft çalışanları: Katkılarınız 'ana' dala birleştirildiktan sonra içeriği /hololens?branch=master <'de genele>.</span><span class="sxs-lookup"><span data-stu-id="b0d21-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="b0d21-212">Sol sütundaki içindekiler'i kullanarak makalenizi bulun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="b0d21-213">Tarayıcıda düzenleme ve masaüstü istemcisiyle düzenleme karşılaştırması</span><span class="sxs-lookup"><span data-stu-id="b0d21-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="b0d21-214">Tarayıcıda düzenleme, hızlı değişiklikler yapmanın en kolay yolu olabilir ancak bazı dezavantajlar vardır:</span><span class="sxs-lookup"><span data-stu-id="b0d21-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="b0d21-215">Yazım denetimine gerek yok.</span><span class="sxs-lookup"><span data-stu-id="b0d21-215">You don't get spell-check.</span></span>
- <span data-ttu-id="b0d21-216">Diğer makalelere herhangi bir akıllı bağlantı elde etmeyebilirsiniz (makalenin dosya adını el ile yazmanız gerekir).</span><span class="sxs-lookup"><span data-stu-id="b0d21-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="b0d21-217">Görüntüleri karşıya yüklemek ve başvuru yapmak zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="b0d21-218">Bu sorunları ele alamamayı tercih ediyorsanız, katkıda bulunmak için [Visual Studio Code](https://code.visualstudio.com/) uzantılarla birlikte kullanmak gibi [bir masaüstü](#useful-extensions) istemcisi kullanın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="b0d21-219">Visual Studio Code’u kullanma</span><span class="sxs-lookup"><span data-stu-id="b0d21-219">Using Visual Studio Code</span></span>

<span data-ttu-id="b0d21-220">Yukarıda listelenen [nedenlerle,](#editing-in-the-browser-vs-editing-with-a-desktop-client)belgeleri düzenlemek için web tarayıcısı yerine masaüstü istemcisi kullanmayı tercih edersiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="b0d21-221">Visual Studio Code. [](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="b0d21-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="b0d21-222">Kurulum</span><span class="sxs-lookup"><span data-stu-id="b0d21-222">Setup</span></span>

<span data-ttu-id="b0d21-223">Bu repo ile çalışacak Visual Studio Code yapılandırmak için şu adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="b0d21-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="b0d21-224">Web tarayıcısında:</span><span class="sxs-lookup"><span data-stu-id="b0d21-224">In a web browser:</span></span>
    1. <span data-ttu-id="b0d21-225">Bilgisayarınız [için Git'i yükleyin.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="b0d21-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="b0d21-226">yükleme [Visual Studio Code.](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="b0d21-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="b0d21-227">[Henüz bir sorun yoksa MicrosoftDocs/mixed-reality'den](#creating-a-new-article) bir fork edin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="b0d21-228">Mürekkepte Kopyala'ya tıklayın **veya url'yi** indirip kopyalayın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="b0d21-229">Visual Studio Code'da kendi mürekkep kopyanızı Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="b0d21-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="b0d21-230">Görünüm menüsünde **Komut** **Paleti'ne tıklayın.**</span><span class="sxs-lookup"><span data-stu-id="b0d21-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="b0d21-231">"Git: Clone" yazın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="b0d21-232">Kopyalanan URL'yi yapıştırın.</span><span class="sxs-lookup"><span data-stu-id="b0d21-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="b0d21-233">Kopyanın bilgisayarınıza kaydedile yerini seçin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="b0d21-234">Açılan **pencerede Open repo** (Repo aç) öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="b0d21-235">Belgeleri düzenleme</span><span class="sxs-lookup"><span data-stu-id="b0d21-235">Editing documentation</span></span>

<span data-ttu-id="b0d21-236">Aşağıdaki iş akışını kullanarak belgelerde değişiklik Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="b0d21-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="b0d21-237">Yukarıdan itibaren [makale düzenleme](#editing-an-existing-article) ve oluşturma ile ilgili tüm kılavuzlar ve [](#creating-a-new-article) [Markdown'ı](#markdown-basics)düzenlemenin temelleri, Visual Studio Code de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b0d21-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="b0d21-238">Kopyalanan mürekkep resmi bir resm ile güncel olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="b0d21-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="b0d21-239">Bir web tarayıcısında, MicrosoftDocs/mixed-reality 'master' belgesinde bulunan diğer katkıda bulunanlardan gelen son değişikliklerinizi kendi fork'nize eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ediyor olduğundan emin olun).</span><span class="sxs-lookup"><span data-stu-id="b0d21-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![MicrosoftDocs/mixed-reality değişikliklerini kendi fork'la eşitleme](images/sync-repos.png)
      
   2. <span data-ttu-id="b0d21-241">Yeni Visual Studio Code yeni güncelleştirilmiş mürekkeplerinizi yerel kopyayla eşitlemek için eşitle düğmesini seçin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Eşitle düğmesine tıklayın resmi](images/sync-clone.png)
      
2. <span data-ttu-id="b0d21-243">Visual Studio Code kullanarak kopyalanmış repoda makaleler oluşturun veya Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b0d21-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="b0d21-244">Bir veya daha fazla makaleyi düzenleyin (gerekirse "images" klasörüne görüntü ekleyin).</span><span class="sxs-lookup"><span data-stu-id="b0d21-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="b0d21-245">**Explorer'da** değişiklikleri **kaydedin.**</span><span class="sxs-lookup"><span data-stu-id="b0d21-245">**Save** changes in **Explorer**.</span></span>
      
      ![Gezgin'de "Hepsini kaydet"i seçin](images/explorer-save.png)
      
   3. <span data-ttu-id="b0d21-247">**Kaynak Denetiminde** tüm **değişiklikleri işle** (istendiğinde işleme iletisi yazın).</span><span class="sxs-lookup"><span data-stu-id="b0d21-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Kaynak Denetiminde "Hepsini işle"yi seçin](images/source-control-commit.png)
      
   4. <span data-ttu-id="b0d21-249">Değişikliklerinizi **çıkış** noktası olarak eşitlemek için eşitle düğmesini seçin (GitHub).</span><span class="sxs-lookup"><span data-stu-id="b0d21-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Eşitle düğmesine tıklayın](images/sync-back.png)
      
3. <span data-ttu-id="b0d21-251">Bir web tarayıcısında, yeni değişiklikleri microsoftDocs/mixed-reality 'master' ile eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ediyor olduğundan emin olun).</span><span class="sxs-lookup"><span data-stu-id="b0d21-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturma](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="b0d21-253">Yararlı uzantılar</span><span class="sxs-lookup"><span data-stu-id="b0d21-253">Useful extensions</span></span>

<span data-ttu-id="b0d21-254">Aşağıdaki Visual Studio Code uzantıları, belgeleri düzenlerken yararlıdır:</span><span class="sxs-lookup"><span data-stu-id="b0d21-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="b0d21-255">[Visual Studio Code için Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Uzantısı - **Alt+M** kullanarak aşağıdakiler gibi belge yazma seçenekleri menüsünü açın:</span><span class="sxs-lookup"><span data-stu-id="b0d21-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="b0d21-256">Karşıya yüklediğiniz görüntüleri arama ve referans olarak gönderme.</span><span class="sxs-lookup"><span data-stu-id="b0d21-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="b0d21-257">Listeler, tablolar ve gibi belgelere özgü çağrılar gibi biçimlendirmeler `>[!NOTE]` ekleyin.</span><span class="sxs-lookup"><span data-stu-id="b0d21-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="b0d21-258">İç bağlantılar ve yer işaretleri (bir sayfanın içindeki belirli bölümlere bağlantılar) arama ve başvuru.</span><span class="sxs-lookup"><span data-stu-id="b0d21-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="b0d21-259">Biçimlendirme hataları vurgulanmış (daha fazla bilgi edinmek için farenizi hatanın üzerine gelin).</span><span class="sxs-lookup"><span data-stu-id="b0d21-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="b0d21-260">[Kod Yazım Denetleyicisi](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - yanlış yazılmış sözcüklerin altı çizili olur; yanlış yazılmış bir sözlüğe sağ tıklar ve sözlüğünü değiştirir veya sözlüğe kaydedebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b0d21-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
