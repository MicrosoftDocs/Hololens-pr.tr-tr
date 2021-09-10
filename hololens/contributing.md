---
title: Katkıda bulunan yönergeler
description: GitHub-flavored markaşağı kullanarak docs.microsoft.com platformunda HoloLens belgelerine nasıl katkıda bulunabileceğinizi öğrenin.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428953"
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

Değişiklik, var olan bir makaleyi yeniden adlandırabilir veya silecektir, yeniden yönlendirme eklediğinizden emin olun. Bu şekilde, mevcut makaleye bağlantısı olan herkes doğru yerde sona kalır. Yeniden yönlendirmeler, deponun kökündeki .openpublishing.redirection.jsdosya tarafından yönetilir.

.openpublishing.redirection.jsbir yeniden yönlendirme eklemek için diziye bir giriş ekleyin `redirections` :

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

Görüntülerinizi, depodaki "Mixed-Reality-docs/Images" klasörüne yüklemeniz ve sonra makaleye uygun şekilde başvurmanız gerekir. Görüntüler otomatik olarak tam boyutta görünür, bu da büyük görüntülerin makalenin tüm genişliğini doldurmasıdır. Karşıya yüklemeden önce görüntülerinizi önceden boyutlandırmasını öneririz. Önerilen genişlik 600 ile 700 piksel arasındadır; Ancak, yoğun bir ekran görüntüsü veya ekran görüntüsünün bir kesri ise, bu boyut yukarı veya aşağı doğru olmalıdır.

>[!IMPORTANT]
>Birleştirmeden önce yalnızca çatallanmış depoya resim yükleyebilirsiniz. bu nedenle, bir makaleye görüntü eklemeyi planlıyorsanız, resimleri çatalınızın "resimler" klasörüne eklemek için [Visual Studio Code kullanmanız](#using-visual-studio-code) gerekir veya aşağıdakileri bir web tarayıcısında gerçekleştirdiğinizden emin olun:
>
>1. MicrosoftDocs/Mixed-Reality deposu ele geçirildi.
>2. Çatalınızdaki makale düzenlendi.
>3. Makalenize başvurduğunuz görüntüler çatalınızdaki "Karma Gerçeklik-docs/resimler" klasörüne yüklendi.
>4. Çatalınızı MicrosoftDocs/Mixed-Reality _ana_ dalında birleştirmek için bir **çekme isteği** oluşturuldu.
>
>Kendi kendine oluşturulan deponuzu ayarlamayı öğrenmek için [Yeni bir makale oluşturma](#creating-a-new-article)yönergelerini izleyin.

## <a name="previewing-your-work"></a>Çalışmanızı Önizleme

bir web tarayıcısı aracılığıyla GitHub düzenlenirken, çalıştırmadan önce işinizi önizlemek için sayfanın üst kısmındaki **önizleme** sekmesini seçebilirsiniz. 

>[!NOTE]
>review.docs.microsoft.com üzerinde yaptığınız değişikliklerin önizlemesi yalnızca Microsoft çalışanları tarafından kullanılabilir

Microsoft çalışanları: Katkılarınız varsayılan dal olan _ana öğe_ ile birleştirildiğinde, </HoloLens? Branch = Master> adresinden genel kullanıma geçmeden önce içeriği inceleyebilirsiniz. Sol sütundaki İçindekiler tablosunu kullanarak makalenizi bulun.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Tarayıcıda düzenleme ile masaüstü istemcisiyle düzenleme

Tarayıcıda düzenlemenin hızlı değişiklikler yapmanın en kolay yolu, ancak birkaç dezavantajın olması gerekir:

- Yazım denetimi yapmayın.
- Diğer makalelere akıllı bağlantı kurma (makalenin dosya adını el ile yazmanız gerekir).
- Görüntüleri karşıya yükleme ve başvuruları bir sorun olabilir.

bu sorunlarla ilgilenmezseniz, katkıda bulunmak için [Visual Studio Code](https://code.visualstudio.com/) gibi bir masaüstü istemcisi kullanın. [](#useful-extensions)

## <a name="using-visual-studio-code"></a>Visual Studio Code’u kullanma

[Yukarıda](#editing-in-the-browser-vs-editing-with-a-desktop-client)listelenen nedenlerle, bir Web tarayıcısı yerine belgeleri düzenlemek için bir masaüstü istemcisi kullanmayı tercih edebilirsiniz. [Visual Studio Code](https://code.visualstudio.com/)kullanmanızı öneririz.

### <a name="setup"></a>Kurulum

Visual Studio Code bu depoyla çalışacak şekilde yapılandırmak için aşağıdaki adımları izleyin:

1. Bir Web tarayıcısında:
    1. [Bilgisayarınız Için git](https://git-scm.com/downloads)'i yükler.
    2. [Visual Studio Code](https://code.visualstudio.com/)'i yükler.
    3. Henüz yapmadıysanız, [MicrosoftDocs/Mixed-Reality çatalını](#creating-a-new-article) yapın.
    4. Çatalınızda **kopyalama veya indirme** ve URL 'yi kopyalama ' yı seçin.
2. Visual Studio Code ' de çatalınızın yerel bir kopyasını oluşturun:
    1. **Görünüm** menüsünden **komut paleti**' ni seçin.
    2. "Git: Clone" yazın.
    3. Kopyaladığınız URL 'YI yapıştırın.
    4. Kopyanın bilgisayarınızda nereye kaydedileceğini seçin.
    5. Açılan pencerede **depoyu aç** ' ı seçin.

### <a name="editing-documentation"></a>Belge düzenleniyor

Visual Studio Code ile belgelerde değişiklik yapmak için aşağıdaki iş akışını kullanın:

>[!NOTE]
>makaleleri [düzenlemeyle](#editing-an-existing-article) ve [oluşturmaya](#creating-a-new-article) yönelik tüm yönergelerin yanı sıra [marku 'nin düzenlenmesine ilişkin temel bilgiler](#markdown-basics), Visual Studio Code de kullanılırken geçerlidir.

1. Kopyalanmış çatalınızın resmi depoından güncel olduğundan emin olun.

   1. Bir Web tarayıcısında, en son değişiklikleri MicrosoftDocs/Mixed-Reality, _Master_' ın varsayılan dalında Çatalınıza eşitlemek için bir çekme isteği oluşturun (okun doğru hedefe işaret ettiğinden emin olun).
      
      ![MicrosoftDocs/Mixed-Reality içindeki değişiklikleri Çatalınızla eşitleyin.](images/sync-repos.png)
      
   2. Visual Studio Code ' de, tekrar güncel çatalınızı yerel kopyaya eşitlemek için eşitle düğmesini seçin.
      
      ![Eşitle düğmesine tıklayın.](images/sync-clone.png)
      
2. Visual Studio Code kullanarak Klonladığınız depolarınızın makalelerini oluşturun veya düzenleyin.

   1. Bir veya daha fazla makaleyi düzenleyin (gerekiyorsa "görüntüler" klasörüne görüntü ekleyin).
   
   2. Değişiklikleri **Gezgin**'de **kaydedin** .
      
      ![Gezgin 'de "Tümünü Kaydet" i seçin](images/explorer-save.png)
      
   3. **Kaynak denetimindeki** **tüm değişiklikleri Yürüt** (sorulduğunda kayıt iletisi yaz).
   
      ![Kaynak denetimindeki "Tümünü Kaydet" i seçin](images/source-control-commit.png)
      
   4. Değişikliklerinizi yeniden kaynağa (GitHub çatalınız) eşitlemek için **Eşitle** düğmesini seçin.
      
      ![Eşitle düğmesine tıklayın.](images/sync-back.png)
      
3. Bir Web tarayıcısında, çatalınızdaki yeni değişiklikleri MicrosoftDocs/Mixed-Reality _ana_ öğesine geri eşitlemek için bir çekme isteği oluşturun (okun doğru hedefe işaret ettiğinden emin olun).

   ![Çatalınızdan, MicrosoftDocs/Mixed-Reality olarak çekme isteği oluşturun.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Kullanışlı uzantılar

belge düzenlenirken aşağıdaki Visual Studio Code uzantıları yararlı olur:

- [Visual Studio Code için docs markup uzantısı](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) -şu şekilde bir belge yazma seçenekleri menüsünü açmak için **Alt + M** kullanın:
   - Karşıya yüklediğiniz görüntüleri arayın ve referans yapın.
   - Gibi listeler, tablolar ve docs 'a özgü çağrı aşımları gibi biçimlendirmeler ekleyin `>[!NOTE]` .
   - İç bağlantılara ve yer işaretlerine yönelik arama yapın ve başvuruları yapın (sayfa içindeki belirli bölümlerin bağlantıları).
   - Biçimlendirme hataları vurgulanır (daha fazla bilgi için farenizi hatanın üzerine getirin).
- [Kod yazım denetleyicisi](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) -yanlış yazılan sözcüklerin altı çizili olacaktır; yanlış yazılmış bir sözcüğe sağ tıklayarak bunu değiştirin veya sözlüğe kaydedin.
