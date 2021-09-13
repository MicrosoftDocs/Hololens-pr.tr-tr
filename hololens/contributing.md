---
title: Katkıda bulunan yönergeler
description: GitHub-flavored markaşağı kullanarak docs.microsoft.com platformunda HoloLens belgelerine nasıl katkıda bulunabileceğinizi öğrenin.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032971"
---
# <a name="contributing-to-the-hololens-documentation"></a>HoloLens belgelerine katkıda bulunma

[HoloLens belgelerine](https://github.com/MicrosoftDocs/Hololens)hoş geldiniz! Bu depoda oluşturduğunuz veya düzenlediğiniz makaleler **herkese açık olarak görünür.** 

HoloLens docs, markdıg özellikleriyle GitHub-flavored markaşağı kullanan docs.microsoft.com platformunda görüntülenir. Bu depoda düzenlediğiniz içerik,/holomers. ' de görüntülenen stilize sayfalarla biçimlendirilir.

Bu sayfada, katkıda bulunmak için temel adımlar ve kılavuzlar ve markın temel kavramları için bağlantılar ele alınmaktadır. Katkılarınız için teşekkürler!

## <a name="available-repos"></a>Kullanılabilir depolar

| Depo adı | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Karma Gerçeklik | [MicrosoftDocs/Mixed-Reality](/windows/mixed-reality) |
| VR Tutkunmları Kılavuzu | [MicrosoftDocs/Mixed-Reality/colanıast-Guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Başlamadan önce

henüz bir [hesabınız yoksa bir GitHub hesabı oluşturmanız](https://github.com/join)gerekir.

>[!NOTE]
>microsoft çalışanı kullanıyorsanız, GitHub hesabınızı [microsoft açık kaynak portalındaki](https://repos.opensource.microsoft.com/)microsoft diğer adınızla ilişkilendirin. **"Microsoft"** ve **"microsoftdocs"** kuruluşları ile birleştirin.

GitHub hesabınızı ayarlarken bu güvenlik önlemlerinizi de öneriyoruz:
- [GitHub hesabınız için güçlü bir parola](https://github.com/settings/admin)oluşturun.
- [İki öğeli kimlik doğrulamayı](https://github.com/settings/two_factor_authentication/configure)etkinleştirin.
- [Kurtarma kodlarınızı](https://github.com/settings/auth/recovery-codes) güvenli bir yerde saklayın.
- [Ortak profil ayarlarınızı](https://github.com/settings/profile)güncelleştirin.
   - Adınızı ayarlayın ve e-posta *adresimi göstermek* için *Genel e-postanızı* ayarlamayı düşünün.
   - Katkıda bulunan docs sayfalarında bir küçük resim gösterildiğinden bir profil resmini karşıya yüklemenizi öneririz.
- Komut satırını kullanmayı planlıyorsanız, [Windows Için git kimlik bilgileri Yöneticisi 'ni](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest)ayarlamayı düşünün. Bu şekilde, her katkı yaptığınızda parolanızı girmeniz gerekmez.

yayımlama sistemi GitHub bağlıdır, bu nedenle bu adımlar önemlidir. GitHub diğer adınızı kullanarak her bir makaleye yazar ya da katkıda bulunan olarak listelenecektir.

## <a name="editing-an-existing-article"></a>Mevcut bir makaleyi Düzenle

bir web tarayıcısında GitHub aracılığıyla *mevcut bir makaleye* güncelleştirme yapmak için aşağıdaki iş akışını kullanın:

1. "Mixed-Reality-docs" klasöründe düzenlemek istediğiniz makaleye gidin.

2. Sağ üst köşedeki Düzenle düğmesini (kurşun kalem simgesi) seçin.

   ![Bir makaleyi düzenleyin.](images/editpage.png)

   Bu, atılabilir dalını otomatik olarak varsayılan dal olan _ana öğe_ olacak şekilde çatallandıracaktır.

   > [!NOTE]
   > Bu makalede, Microsoft tarafından artık kullanılmayan bir terim olan _ana öğe_ başvuruları yer almaktadır. Terim yazılımlardan kaldırıldığında, bu makaleden kaldıracağız.
   
3. Makalenin içeriğini [Markaşağı temel bilgilere](#markdown-basics)göre düzenleyin.

4. Her bir makalenin üst kısmındaki meta verileri güncelleştir:

   * **title**: makale görüntülenirken tarayıcı sekmesinde görüntülenen sayfa başlığı. Sayfa başlıkları, SEO ve dizin oluşturma için kullanılır; bu nedenle, gerekli olmadığı takdirde başlığı değiştirmeyin (ancak belgeler genel çalışmadan önce daha az kritik olur).
   * **Açıklama**: makalenin içeriğine yönelik kısa bir açıklama yazın.
   * **yazar**: sayfanın birincil sahibiyseniz, burada GitHub diğer adınızı ekleyin.
   * **MS. Author**: sayfanın birincil sahibiyseniz, Microsoft diğer adınızı buraya ekleyin (gerekli değildir @microsoft.com , yalnızca diğer ad).
   * **MS. Date**: sayfaya önemli içerik ekliyorsanız, açıklama, biçimlendirme, dilbilgisi veya yazım gibi düzeltmeler için değil, tarihi güncelleştirin.
   * **anahtar sözcükler**: SEO 'e yardımcı anahtar kelimeleri (arama motoru iyileştirmesi). Makalenize özgü, ancak listenizdeki son anahtar sözcükten sonra noktalama olmadan, bir virgül ve boşlukla ayırarak anahtar sözcükler ekleyin. Diğer bir yerde yönetildiği için tüm makalelere uygulanan genel anahtar sözcükler eklemeniz gerekmez. 
   
5. Makale düzenlemelerinizi tamamladıktan sonra aşağı kaydırın ve **dosya değişikliği öner**' i seçin.

6. Bir sonraki sayfada, otomatik olarak oluşturulan dalınızı varsayılan dal olan _ana öğe_ ile birleştirmek için **çekme isteği oluştur** ' u seçin.

7. Düzenlemek istediğiniz Sonraki Makale için yukarıdaki adımları tekrarlayın.

## <a name="renaming-or-deleting-an-existing-article"></a>Mevcut bir makaleyi yeniden adlandırma veya silme

Değişiklik, var olan bir makaleyi yeniden adlandırabilir veya silecektir, yeniden yönlendirme eklediğinizden emin olun. Bu şekilde, mevcut makaleye bağlantısı olan herkes doğru yerde sona kalır. Yeniden yönlendirmeler, deponun kökündeki. openpublishing. Redirection. JSON dosyası tarafından yönetilir.

. Openpublishing. Redirection. JSON öğesine yeniden yönlendirme eklemek için diziye bir giriş ekleyin `redirections` :

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- , `source_path` Kaldırmakta olduğunuz eski makalenin göreli depo yoludur. Yolun ile başladığı `mixed-reality-docs` ve ile bitdiğinizden emin olun `.md` .

- , `redirect_url` Eski makalenin yeni makaleye yönelik göreli genel URL 'sidir. Bu **URL 'nin** `mixed-reality-docs` `.md` , depo yolu değil genel URL 'ye başvurduğundan veya içermediğinden emin olun. Kullanarak yeni makaledeki bir bölüme bağlama `#section` izin verilir. Ayrıca, gerekirse başka bir sitenin mutlak yolunu da kullanabilirsiniz.

- `redirect_document_id` Belge KIMLIĞINI önceki dosyadan korumak isteyip istemediğinizi belirtir. Varsayılan değer: `false`. `true` `ms.documentid` Yeniden yönlendirilen makaleden öznitelik değerini korumak istiyorsanız kullanın. Belge KIMLIĞINI korumazsanız, sayfa görünümleri ve ranlar gibi veriler hedef makaleye aktarılır. Yeniden yönlendirme birincil olarak bir yeniden adlandırma ise ve yalnızca aynı içeriğin bazılarını ele alan farklı bir makaleye işaretçi değilse bunu yapın.

Yeniden yönlendirme eklerseniz, eski dosyayı da silmeyi unutmayın.

## <a name="creating-a-new-article"></a>Yeni bir makale oluşturma

bir web tarayıcısında GitHub aracılığıyla belge deposunda *yeni makaleler oluşturmak* için aşağıdaki iş akışını kullanın:

1. En sağ üst köşedeki **çatal** düğmesini kullanarak microsoftdocs/Mixed-Reality varsayılan dalını, _ana öğe_ için bir çatal oluşturun.

   ![Şu anda "Master" olarak adlandırılan varsayılan dalı çatal.](images/forkbranch.png)

   > [!NOTE]
   > Bu makalede, Microsoft tarafından artık kullanılmayan bir terim olan _ana öğe_ başvuruları yer almaktadır. Terim yazılımlardan kaldırıldığında, bu makaleden kaldıracağız.
   
2. "Mixed-Reality-docs" klasöründe, sağ üst köşedeki **yeni dosya oluştur** ' u seçin.

3. Makale için bir sayfa adı oluşturun (boşluk yerine kısa çizgileri kullanın ve noktalama işaretleri veya kesme işareti kullanmayın) ve ". MD" ekleyin

   ![Yeni sayfanızı adlandırın.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Yeni makaleyi, "Mixed-Reality-docs" klasörü içinden oluşturduğunuzdan emin olun. Bunu, yeni dosya adı satırında "/Mixed-Reality-je/" olup olmadığını denetleyerek doğrulayabilirsiniz.

4. Yeni sayfanızın en üstünde aşağıdaki meta veri bloğunu ekleyin:

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

5. [Mevcut bir makaleyi düzenlemekte](#editing-an-existing-article)daha önce açıklandığı gibi ilgili meta veri alanlarını girin.

6. [Markın temel bilgilerini](#markdown-basics)kullanarak Makale içeriği yazın.

7. `## See also`Makalenin alt kısmına, diğer ilgili makalelerin bağlantılarıyla bir bölüm ekleyin.

8. İşiniz bittiğinde **yeni dosya Kaydet**' i seçin.

9. **Yeni çekme isteği ' ni** seçin ve çatalınızın _ana_ dalını microsoftdocs/Mixed-Reality _Master_ ile birleştirin (okun doğru hedefe işaret ettiğinden emin olun).

   ![Çatalınızdan, MicrosoftDocs/Mixed-Reality olarak çekme isteği oluşturun.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Markdown temelleri

Aşağıdaki kaynaklar markın dilini kullanarak belgeleri nasıl düzenleyeceğinizi öğrenmenize yardımcı olur:

- [Markdown temelleri](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Docs.microsoft.com için Markaşağı yazmak üzere ek kaynaklar](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Tablo ekleme

Docs.microsoft.com stilleri tablolarında, satır içi CSS ' yi deneseniz bile kenarlıklar veya özel stilleri olmaz. Kısa bir süre boyunca çalışır, ancak sonunda platform stili tablonun dışına çıkaracaktır. Bu nedenle, önceden planlayın ve tablolarınızı basit tutun. Şu şekilde Markaşağı tablolarının kolay olmasını sağlayan bir site: [tablo Oluşturucu]] ( https://www.tablesgenerator.com/markdown_tables) .

[Visual Studio Code için Docs markaşağı uzantısı](/teamblog/docs-extension) , belgeleri düzenlemek için [Visual Studio Code kullanıyorsanız (aşağıya bakın)](#using-visual-studio-code) tablo oluşturmayı da kolaylaştırır.

### <a name="adding-images"></a>Görüntü ekleme

Görüntülerinizi,po içinde "mixed-reality-docs/images" klasörüne yüklemeli ve ardından makalede uygun şekilde başvurabilirsiniz. Görüntüler otomatik olarak tam boyutlu olarak görüntülenir ve bu da büyük görüntülerin makalenin tüm genişliğini dolduracak olduğu anlamına gelir. Karşıya yüklemeden önce görüntülerinizi önceden boyutlandırmanızı öneririz. Önerilen genişlik 600 ile 700 piksel arasında olsa da, sırasıyla yoğun bir ekran görüntüsü veya ekran görüntüsü kesri ise boyutu yukarı veya aşağı doğru boyutunuz olmalıdır.

>[!IMPORTANT]
>Birleştirmeden önce görüntüleri yalnızca bir mürekkepli repoya yükleyebilirsiniz. Bu nedenle, bir makaleye görüntü eklemeyi planlıyorsanız, önce [Visual Studio Code](#using-visual-studio-code) kullanarak görüntüleri bir web tarayıcısında kendi fork 'nizin "images" klasörüne eklemeniz veya aşağıdaki adımları gerçekleştirin:
>
>1. MicrosoftDocs/mixed-reality repo'su için bir mürekkep.
>2. Makaleyi, mürekkeple birlikte düzenledik.
>3. Makalenize başvurmakta olduğunuz görüntüleri, mürekkepte "mixed-reality-docs/images" klasörüne yükleyin.
>4. MicrosoftDocs/mixed-reality ana dalı ile mürekkeplerinizi birleştirmek için bir _çekme isteği_ oluşturuldu. 
>
>Kendi forked repo'larınızı ayarlamayı öğrenmek için, yeni bir makale [oluşturmaya ilişkin yönergeleri izleyin.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Çalışmanızı önizleme

Web tarayıcısı GitHub web tarayıcısında düzenlerken, işlemeden önce çalışmanızı önizlemek için sayfanın üst kısmından Önizleme sekmesini seçin.  

>[!NOTE]
>Değişikliklerinizin önizlemesini review.docs.microsoft.com yalnızca Microsoft çalışanları tarafından kullanılabilir

Microsoft çalışanları: Katkılarınız varsayılan dal olan ana dala birleştirilmiştir ve içeriği /hololens?branch=master <'de genele>. Sol sütundaki içindekiler tablosundan makalenizi bulun.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Tarayıcıda düzenleme ve masaüstü istemcisiyle düzenleme karşılaştırması

Tarayıcıda düzenleme, hızlı değişiklikler yapmanın en kolay yolu olabilir ancak bazı dezavantajlar vardır:

- Yazım denetimine gerek yok.
- Diğer makalelere herhangi bir akıllı bağlantı elde etmeyebilirsiniz (makalenin dosya adını el ile yazmanız gerekir).
- Görüntüleri karşıya yüklemek ve başvuru yapmak zor olabilir.

Bu sorunları ele alamamayı tercih ediyorsanız, katkıda bulunan birkaç [Visual Studio Code](https://code.visualstudio.com/) gibi [bir masaüstü](#useful-extensions) istemcisi kullanın.

## <a name="using-visual-studio-code"></a>Visual Studio Code’u kullanma

Yukarıda listelenen [nedenlerle,](#editing-in-the-browser-vs-editing-with-a-desktop-client)belgeleri düzenlemek için web tarayıcısı yerine masaüstü istemcisi kullanmayı tercih edersiniz. Visual Studio Code. [](https://code.visualstudio.com/)

### <a name="setup"></a>Kurulum

Bu repo ile çalışacak Visual Studio Code yapılandırmak için şu adımları izleyin:

1. Web tarayıcısında:
    1. Bilgisayarınız [için Git'i yükleyin.](https://git-scm.com/downloads)
    2. yükleme [Visual Studio Code.](https://code.visualstudio.com/)
    3. [Henüz bir sorun yoksa MicrosoftDocs/mixed-reality'den](#creating-a-new-article) bir fork edin.
    4. Mürekkepte Kopyala'ya tıklayın **veya url'yi** indirip kopyalayın.
2. Visual Studio Code'de, mürekkeple ilgili yerel bir Visual Studio Code:
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

   1. Bir web tarayıcısında, MicrosoftDocs/mixed-reality'nin varsayılan dalı olan _ana_ dalda bulunan diğer katkıda bulunanlardan gelen son değişiklikleri, sizin fork'la eşitlemek için bir çekme isteği oluşturun (okun doğru hedefe işaret ediyor olduğundan emin olun).
      
      ![MicrosoftDocs/mixed-reality değişikliklerini kendi fork'la eşitler.](images/sync-repos.png)
      
   2. Yeni Visual Studio Code yeni güncelleştirilmiş mürekkeplerinizi yerel kopyayla eşitlemek için eşitle düğmesini seçin.
      
      ![Eşitle düğmesinin resmine tıklayın.](images/sync-clone.png)
      
2. Kopyalanan bir hesabı kullanarak kopyalanmış bir repoda makale Visual Studio Code.

   1. Bir veya daha fazla makaleyi düzenleyin (gerekirse "images" klasörüne görüntü ekleyin).
   
   2. **Explorer'da** değişiklikleri **kaydedin.**
      
      ![Gezgin'de "Hepsini kaydet"i seçin](images/explorer-save.png)
      
   3. **Kaynak Denetiminde** tüm **değişiklikleri işle** (istendiğinde işleme iletisi yazın).
   
      ![Kaynak Denetiminde "Hepsini işle"yi seçin](images/source-control-commit.png)
      
   4. Değişikliklerinizi **çıkış** noktasıyla eşitlemek için eşitle düğmesini seçin (GitHub).
      
      ![Eşitle düğmesine tıklayın.](images/sync-back.png)
      
3. Bir web tarayıcısında, yeni değişiklikleri microsoftdocs/mixed-reality _master_ ile eşitlemek için bir çekme isteği oluşturun (okun doğru hedefe işaret ediyor olduğundan emin olun).

   ![Mürekkepten MicrosoftDocs/mixed-reality'ye çekme isteği oluşturun.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Yararlı uzantılar

Aşağıdaki Visual Studio Code, belgeleri düzenlerken yararlıdır:

- [Visual Studio Code için Docs Markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) Uzantısı - **Alt+M** kullanarak aşağıdakiler gibi bir belge yazma seçenekleri menüsü açın:
   - Karşıya yüklediğiniz görüntüleri arama ve referans olarak gönderme.
   - Listeler, tablolar ve gibi belgelere özgü çağrılar gibi biçimlendirmeler `>[!NOTE]` ekleyin.
   - İç bağlantılar ve yer işaretleri (bir sayfanın içindeki belirli bölümlere bağlantılar) arama ve başvuru.
   - Biçimlendirme hataları vurgulanmış (daha fazla bilgi edinmek için farenizi hatanın üzerine gelin).
- [Kod Yazım Denetleyicisi](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - yanlış yazılmış sözcüklerin altı çizili olur; yanlış yazılmış bir sözlüğe sağ tıklar ve sözlüğünü değiştirir veya sözlüğe kaydedebilirsiniz.
