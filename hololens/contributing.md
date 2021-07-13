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
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens katkıda bulunuyor

[HoloLens hoş geldiniz!](https://github.com/MicrosoftDocs/Hololens) Bu repoda oluştur veya düzenleyişle ilgili tüm **makaleler genel olarak görünür.** 

HoloLens belgeleri, Markdig özellikleriyle GitHub Markdown kullanan docs.microsoft.com platformda görüntülenir. Bu repoda düzenley istediğiniz içerik, /hololens'te yer alan stilleştirilmiş sayfalara biçimlendirilecek.

Bu sayfa, katkıda bulunmak için temel adımları ve yönergeleri ve Markdown temel bilgileri bağlantılarını kapsar. Katkılarınız için teşekkürler!

## <a name="available-repos"></a>Kullanılabilir repos

| Depo adı | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Karma Gerçeklik | [MicrosoftDocs/karma gerçeklik](/windows/mixed-reality) |
| VR Meraklıları Kılavuzu | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Başlamadan önce

Henüz bir hesabınız yoksa bir hesap oluşturmanız [GitHub gerekir.](https://github.com/join)

>[!NOTE]
>Microsoft çalışanıysanız, microsoft GitHub Microsoft Açık Kaynak portalında Microsoft diğer [adınıza bağlamanız gerekir.](https://repos.opensource.microsoft.com/) **"Microsoft" ve** **"MicrosoftDocs" kuruluşlarına** katılın.

Hesap GitHub ayarlarken şu güvenlik önlemlerini de öneririz:
- Hesap [hesabınız için güçlü bir GitHub oluşturun.](https://github.com/settings/admin)
- İki [faktörlü kimlik doğrulamasını etkinleştirin.](https://github.com/settings/two_factor_authentication/configure)
- Kurtarma [kodlarınızı güvenli](https://github.com/settings/auth/recovery-codes) bir yere kaydedin.
- Genel profil [ayarlarınızı güncelleştirin.](https://github.com/settings/profile)
   - Adınız olarak ayarlayın ve Genel e-postanızı *E-posta adresimi gösterme olarak ayarlayın.* 
   - Katkıda bulunmak istediğiniz belge sayfalarında küçük resim gösterildiği için profil resmini karşıya yüklemenizi öneririz.
- Komut satırı kullanmayı planlıyorsanız, git için [Git Kimlik Bilgileri Yöneticisi'Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Bu şekilde, her katkıda parolanızı girmenize gerek olmayacaktır.

Yayımlama sistemi, GitHub bu nedenle önemlidir. Diğer adınız kullanılarak her makalenin yazarı veya katkıda bulunanı olarak GitHub listelenirsiniz.

## <a name="editing-an-existing-article"></a>Mevcut bir makaleyi düzenleme

Web tarayıcısında mevcut bir makalede *güncelleştirmeler yapmak için* GitHub iş akışını kullanın:

1. "mixed-reality-docs" klasöründe düzenlemek istediğiniz makaleye gidin.

2. Sağ üst köşesindeki düzenle düğmesini (kalem simgesi) seçerek otomatik olarak "ana" daldan atılabilir bir dal oluşturulur.

   ![Bir makaleyi düzenleme.](images/editpage.png)
   
3. Makalenin içeriğini ["Markdown temel bilgileri" makalesine göre düzenleyin.](#markdown-basics)

4. Her makalenin en üstünde yer alan meta verileri güncelleştirin:

   * **title:** Makale görüntülendiğinde tarayıcı sekmesinde görüntülenen sayfa başlığı. Sayfa başlıkları SEO ve dizin oluşturma için kullanılır, bu nedenle gerekli olmadıkça başlığı değiştirme (belgeler genel hale gelmeden önce bu daha az kritik olsa da).
   * **açıklama:** Makalenin içeriğine ilişkin kısa bir açıklama yazarak SEO ve bulma desteği sağlar.
   * **yazar:** Sayfanın birincil sahibiyseniz sayfanın diğer adını buraya GitHub ekleyin.
   * **ms.author:** Sayfanın birincil sahibiyseniz, Microsoft diğer adını buraya ekleyin (yalnızca diğer adı @microsoft.com için ihtiyacınız yok).
   * **ms.date:** Sayfaya önemli içerik ekliyorsanız tarihi güncelleştirin, ancak açıklama, biçimlendirme, dil bilgisi veya yazım gibi düzeltmeler için güncelleştirin.
   * **keywords:** Keywords aid in SEO (search engine optimization). Makalenize özgü olan ancak listenizin son anahtar sözcüğünden sonra noktalama işareti eklemeden virgülle ve boşlukla ayrılmış anahtar sözcükler ekleyin. Tüm makaleler için geçerli olan genel anahtar sözcükler eklemenize gerek yok çünkü bunlar başka bir yerde yönetiliyor. 
   
5. Makale düzenlemelerinizi tamamlandıktan sonra sayfayı aşağı kaydırın ve Dosya değişikliği **öner'i seçin.**

6. Sonraki sayfada Çekme isteği **oluştur'a seçerek** otomatik olarak oluşturulan dalını 'ana dal' olarak birleştirin.

7. Düzenlemek istediğiniz sonraki makale için yukarıdaki adımları tekrarlayın.

## <a name="renaming-or-deleting-an-existing-article"></a>Mevcut bir makaleyi yeniden markalama veya silme

Değişikliğiniz mevcut bir makaleyi yeniden adlandıracak veya secekse, yeniden yönlendirme eklemeye emin olun. Bu şekilde, mevcut makaleye bağlantısı olan herkes yine de doğru yerde olur. Yeniden yönlendirmeler, .openpublishing.redirection.jsdosyasının kökünde yer alan dosyada yer alan dosya tarafından yönetilir.

Yeniden yönlendirmeyi .openpublishing.redirection.jsdizisine bir giriş `redirections` ekleyin:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`, kaldırmakta olduğunu eski makalenin göreli depo yoludur. Yolun ile başladığından ve ile `mixed-reality-docs` sona erdiğinden emin `.md` olun.

- `redirect_url`, eski makaleden yeni makaleye göreli genel URL'dir. Depo yolunu değil **genel URL'ye** başvurduğu için bu `mixed-reality-docs` URL'nin veya `.md` içermey olduğundan emin olun. kullanarak yeni makalenin içindeki bir bölüme `#section` bağlamaya izin verilir. Gerekirse burada başka bir sitenin mutlak yolunu da kullanabilirsiniz.

- `redirect_document_id` , belge kimliğini önceki dosyadan tutmak isteyip istemeyebilirsiniz. Varsayılan değer: `false`. Yeniden `true` yönlendirilen makaledeki `ms.documentid` öznitelik değerini korumak için kullanın. Belge kimliğini korursanız sayfa görüntülemeleri ve derecelendirmeler gibi veriler hedef makaleye aktarılır. Yeniden yönlendirme öncelikli olarak bir yeniden adlandırma ise ve aynı içeriğin yalnızca bir bölümü kapsayan farklı bir makale işaretçisi ise bunu yapma.

Yeniden yönlendirme eklersiniz, eski dosyayı da silebilirsiniz.

## <a name="creating-a-new-article"></a>Yeni makale oluşturma

Web tarayıcısında yeni *makaleler oluşturmak için* aşağıdaki iş akışını kullanarak GitHub kullanın:

1. MicrosoftDocs/mixed-reality 'master' dalını kullanarak bir mürekkep oluşturun (sağ **üstte yer** alan Fork düğmesini kullanarak).

   ![Ana dalda bir mürekkep.](images/forkbranch.png)
   
2. "mixed-reality-docs" klasöründe sağ üst **sırada Yeni dosya oluştur'a** tıklayın.

3. Makale için bir sayfa adı oluşturun (boşluk yerine kısa çizgi kullanın ve noktalama işareti veya kesme işareti kullanmayın) ve ".md" ifadesini ekleyin

   ![Yeni sayfanıza bir ad girin.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Yeni makaleyi "mixed-reality-docs" klasöründen oluştursanız emin olun. Yeni dosya adı satırına "/mixed-reality-docs/" ifadesini kontrol ederek bunu onaylayın.

4. Yeni sayfanın en üstüne aşağıdaki meta veri bloğu ekleyin:

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

5. Yukarıdaki bölümde yer alan yönergelere göre ilgili meta veri [alanlarını doldurun.](#editing-an-existing-article)

6. Markdown temellerini [kullanarak makale içeriği yazın.](#markdown-basics)

7. Makalenin `## See also` en altına diğer ilgili makalelerin bağlantılarını içeren bir bölüm ekleyin.

8. Tamamlandığında Yeni dosya **işle'yi seçin.**

9. Yeni **çekme isteği'yi** seçin ve mürekkep 'ana' dalını MicrosoftDocs/mixed-reality 'master' ile birleştirin (okun doğru yolu işaret eden olduğundan emin olun).

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturma](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown temelleri

Aşağıdaki kaynaklar, Markdown dilini kullanarak belgeleri düzenlemeyi öğrenmenizi sağlar:

- [Markdown temelleri](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Docs.microsoft.com için Markdown yazmak için ek kaynaklar](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Tablo ekleme

Stil tablolarının docs.microsoft.com nedeniyle satır içi CSS'i denesanız bile kenarlıklar veya özel stiller olmayacaktır. Kısa bir süre çalışacak gibi görünür, ancak sonunda platform stili tablodan çıkartır. Bu nedenle plan yapmayı ve tablolarınızı basit tutmaya devam edin. [Markdown tablolarını kolaylaştıran bir site şu şekildedir:](https://www.tablesgenerator.com/markdown_tables).

[Visual Studio Code için Docs Markdown](/teamblog/docs-extension) Uzantısı, belgeleri düzenlemek için Visual Studio Code [(aşağıya bakın)](#using-visual-studio-code) kullanıyorsanız tablo oluşturmayı da kolaylaştırır.

### <a name="adding-images"></a>Görüntü ekleme

Görüntülerinizi,po içinde "mixed-reality-docs/images" klasörüne yüklemeli ve ardından makalede uygun şekilde başvurabilirsiniz. Görüntüler otomatik olarak tam boyutlu olarak görüntülenir ve bu da büyük görüntülerin makalenin tüm genişliğini dolduracak olduğu anlamına gelir. Karşıya yüklemeden önce görüntülerinizi önceden boyutlandırmanızı öneririz. Önerilen genişlik 600 ile 700 piksel arasında olsa da, sırasıyla yoğun bir ekran görüntüsü veya ekran görüntüsü kesri olması için boyutu yukarı veya aşağı doğru boyutunuz olmalıdır.

>[!IMPORTANT]
>Birleştirmeden önce görüntüleri yalnızca bir mürekkepli repoya yükleyebilirsiniz. Bu nedenle, bir makaleye görüntü eklemeyi planlıyorsanız, önce [Visual Studio Code](#using-visual-studio-code) kullanarak görüntüleri bir web tarayıcısında kendi fork 'nizin "images" klasörüne eklemeniz veya aşağıdaki adımları gerçekleştirin:
>
>1. MicrosoftDocs/mixed-reality repo'su için bir mürekkep.
>2. Makaleyi, mürekkeple birlikte düzenledik.
>3. Makalenize başvurmakta olduğunuz görüntüleri, mürekkepte "mixed-reality-docs/images" klasörüne yükleyin.
>4. MicrosoftDocs/mixed-reality 'master' dalı ile mürekkeplerinizi birleştirmek için bir çekme isteği oluşturuldu. 
>
>Kendi forked repo'larınızı ayarlamayı öğrenmek için, yeni bir makale [oluşturmaya ilişkin yönergeleri izleyin.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Çalışmanızı önizleme

Web tarayıcısı GitHub web tarayıcısında düzenlerken, işlemeden önce çalışmanızı önizlemek için sayfanın üst kısmından Önizleme sekmesini seçin.  

>[!NOTE]
>Değişikliklerinizin önizlemesini review.docs.microsoft.com yalnızca Microsoft çalışanları tarafından kullanılabilir

Microsoft çalışanları: Katkılarınız 'ana' dala birleştirildiktan sonra içeriği /hololens?branch=master <'de genele>. Sol sütundaki içindekiler'i kullanarak makalenizi bulun.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Tarayıcıda düzenleme ve masaüstü istemcisiyle düzenleme karşılaştırması

Tarayıcıda düzenleme, hızlı değişiklikler yapmanın en kolay yolu olabilir ancak bazı dezavantajlar vardır:

- Yazım denetimine gerek yok.
- Diğer makalelere herhangi bir akıllı bağlantı elde etmeyebilirsiniz (makalenin dosya adını el ile yazmanız gerekir).
- Görüntüleri karşıya yüklemek ve başvuru yapmak zor olabilir.

Bu sorunları ele alamamayı tercih ediyorsanız, katkıda bulunmak için [Visual Studio Code](https://code.visualstudio.com/) uzantılarla birlikte kullanmak gibi [bir masaüstü](#useful-extensions) istemcisi kullanın.

## <a name="using-visual-studio-code"></a>Visual Studio Code’u kullanma

Yukarıda listelenen [nedenlerle,](#editing-in-the-browser-vs-editing-with-a-desktop-client)belgeleri düzenlemek için web tarayıcısı yerine masaüstü istemcisi kullanmayı tercih edersiniz. Visual Studio Code. [](https://code.visualstudio.com/)

### <a name="setup"></a>Kurulum

Bu repo ile çalışacak Visual Studio Code yapılandırmak için şu adımları izleyin:

1. Web tarayıcısında:
    1. Bilgisayarınız [için Git'i yükleyin.](https://git-scm.com/downloads)
    2. yükleme [Visual Studio Code.](https://code.visualstudio.com/)
    3. [Henüz bir sorun yoksa MicrosoftDocs/mixed-reality'den](#creating-a-new-article) bir fork edin.
    4. Mürekkepte Kopyala'ya tıklayın **veya url'yi** indirip kopyalayın.
2. Visual Studio Code'da kendi mürekkep kopyanızı Visual Studio Code:
    1. Görünüm menüsünde **Komut** **Paleti'ne tıklayın.**
    2. "Git: Clone" yazın.
    3. Kopyalanan URL'yi yapıştırın.
    4. Kopyanın bilgisayarınıza kaydedile yerini seçin.
    5. Açılan **pencerede Open repo** (Repo aç) öğesini seçin.

### <a name="editing-documentation"></a>Belgeleri düzenleme

Aşağıdaki iş akışını kullanarak belgelerde değişiklik Visual Studio Code:

>[!NOTE]
>Yukarıdan itibaren [makale düzenleme](#editing-an-existing-article) ve oluşturma ile ilgili tüm kılavuzlar ve [](#creating-a-new-article) [Markdown'ı](#markdown-basics)düzenlemenin temelleri, Visual Studio Code de geçerlidir.

1. Kopyalanan mürekkep resmi bir resm ile güncel olduğundan emin olun.

   1. Bir web tarayıcısında, MicrosoftDocs/mixed-reality 'master' belgesinde bulunan diğer katkıda bulunanlardan gelen son değişikliklerinizi kendi fork'nize eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ediyor olduğundan emin olun).
      
      ![MicrosoftDocs/mixed-reality değişikliklerini kendi fork'la eşitleme](images/sync-repos.png)
      
   2. Yeni Visual Studio Code yeni güncelleştirilmiş mürekkeplerinizi yerel kopyayla eşitlemek için eşitle düğmesini seçin.
      
      ![Eşitle düğmesine tıklayın resmi](images/sync-clone.png)
      
2. Visual Studio Code kullanarak kopyalanmış repoda makaleler oluşturun veya Visual Studio Code.

   1. Bir veya daha fazla makaleyi düzenleyin (gerekirse "images" klasörüne görüntü ekleyin).
   
   2. **Explorer'da** değişiklikleri **kaydedin.**
      
      ![Gezgin'de "Hepsini kaydet"i seçin](images/explorer-save.png)
      
   3. **Kaynak Denetiminde** tüm **değişiklikleri işle** (istendiğinde işleme iletisi yazın).
   
      ![Kaynak Denetiminde "Hepsini işle"yi seçin](images/source-control-commit.png)
      
   4. Değişikliklerinizi **çıkış** noktası olarak eşitlemek için eşitle düğmesini seçin (GitHub).
      
      ![Eşitle düğmesine tıklayın](images/sync-back.png)
      
3. Bir web tarayıcısında, yeni değişiklikleri microsoftDocs/mixed-reality 'master' ile eşitlemek için bir çekme isteği oluşturun (okun doğru yolu işaret ediyor olduğundan emin olun).

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturma](images/pr-to-master.png)

### <a name="useful-extensions"></a>Yararlı uzantılar

Aşağıdaki Visual Studio Code uzantıları, belgeleri düzenlerken yararlıdır:

- [Visual Studio Code için Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Uzantısı - **Alt+M** kullanarak aşağıdakiler gibi belge yazma seçenekleri menüsünü açın:
   - Karşıya yüklediğiniz görüntüleri arama ve referans olarak gönderme.
   - Listeler, tablolar ve gibi belgelere özgü çağrılar gibi biçimlendirmeler `>[!NOTE]` ekleyin.
   - İç bağlantılar ve yer işaretleri (bir sayfanın içindeki belirli bölümlere bağlantılar) arama ve başvuru.
   - Biçimlendirme hataları vurgulanmış (daha fazla bilgi edinmek için farenizi hatanın üzerine gelin).
- [Kod Yazım Denetleyicisi](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - yanlış yazılmış sözcüklerin altı çizili olur; yanlış yazılmış bir sözlüğe sağ tıklar ve sözlüğünü değiştirir veya sözlüğe kaydedebilirsiniz.
