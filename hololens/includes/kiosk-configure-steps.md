---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859433"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[tek uygulama bilgi noktası şablonu Microsoft Intune](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>tek uygulama bilgi noktası şablonu Microsoft Intune

1. Yapılandırma profili oluşturma <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Bilgi noktası şablonu seçin <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Tek bir uygulama veya birden çok uygulama bilgi noktası olup olmadığını ve ayrıca bilgi noktası modu için kullanıcı hedefleme türünü seçin <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Bilgi noktası modunda çalıştırılacak uygulamayı seçin <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Diğer seçenekleri olduğu gibi bırakın <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Bu yapılandırma profilinin atanması gereken grupları/cihazları veya kullanıcıları seçin <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Yapılandırma profilini kaydetmek için gözden geçirin ve oluşturun
8. Cihaza yapılandırma uygulamak için cihazdan veya Intune 'dan başlayarak MDM eşitlemesini gerçekleştirin. [cihazları ıntune 'dan](/mem/intune/remote-actions/device-sync#sync-a-device) veya cihazda **Ayarlar-> hesaplar aracılığıyla eşitleme-> iş veya okul >** bağlı hesap **-> bilgi-> eşitleme**
9. Bilgi noktası deneyimi için hedef kullanıcı olarak oturum açın.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[birden çok uygulama bilgi noktası şablonu Microsoft Intune](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>birden çok uygulama bilgi noktası şablonu Microsoft Intune

1. Yapılandırma profili oluşturma <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Bilgi noktası şablonu seçin <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Tek bir uygulama veya birden çok uygulama bilgi noktası olup olmadığını ve ayrıca bilgi noktası modu için kullanıcı hedefleme türünü seçin <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Bilgi noktası modunda çalıştırılacak uygulamaları seçin <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Diğer seçenekleri olduğu gibi bırakın <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Bu yapılandırma profilinin atanması gereken grupları/cihazları veya kullanıcıları seçin <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Yapılandırma profilini kaydetmek için gözden geçirin ve oluşturun
8. Cihaza yapılandırma uygulamak için cihazdan veya Intune 'dan başlayarak MDM eşitlemesini gerçekleştirin. [cihazları ıntune 'dan](/mem/intune/remote-actions/device-sync#sync-a-device) veya cihazda **Ayarlar-> hesaplar aracılığıyla eşitleme-> iş veya okul >** bağlı hesap **-> bilgi-> eşitleme**
9. Bilgi noktası deneyimi için hedef kullanıcı olarak oturum açın.

# <a name="microsoft-intune-custom-template"></a>[özel şablon Microsoft Intune](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>özel şablon Microsoft Intune

1. İstediğiniz bilgi noktası deneyiminiz için XML yapılandırması oluşturun. Başlamak için buradaki [örneklere](../hololens-kiosk-reference.md#kiosk-xml-code-samples) bakın.

1. Özel yapılandırma profili oluşturma <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Özel yapılandırma profilinin adını belirtin ve OMA-URI ayarları eklemek için "yapılandırma ayarları" bölümünde "Ekle" ye tıklayın. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. OMA-URI ayarlarının adını belirtin.

    1. OMA-URI metin kutusunda **./Device/Vendor/MSFT/atandaccess/Configuration** yazın
    1. Veri türünü **dize** olarak seçin.
    1. Değer metin kutusu ' nda, atanan erişim yapılandırması XML 'sini kopyalayın (Bu senaryoya bağlı olarak, senaryolarınızı temel alan örnekler için başvuru bağlantılarına bakın ve kopyalama-yapıştırmayı yapmadan önce gerekirse güncelleştirin).
    1. Ayarı ve yapılandırmayı kaydetmek için Kaydet düğmesini seçin.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Bu yapılandırma profilinin atanması gereken grupları/cihazları veya kullanıcıları seçin. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Yapılandırma profilini kaydetmek için gözden geçirin ve oluşturun.
1. Cihaza yapılandırma uygulamak için cihazdan veya Intune 'dan başlayarak MDM eşitlemesini gerçekleştirin. [cihazları ıntune 'dan](/mem/intune/remote-actions/device-sync#sync-a-device) veya cihazda **Ayarlar-> hesaplar aracılığıyla eşitleme-> iş veya okul >** bağlı hesap **-> bilgi-> eşitleme**
1. Bilgi noktası deneyimi için hedef kullanıcı olarak oturum açın.

# <a name="runtime-provisioning---multi-app"></a>[Çalışma zamanı sağlama-çoklu uygulama](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Çalışma zamanı sağlama-çoklu uygulama

1. İstediğiniz bilgi noktası deneyiminiz için XML yapılandırması oluşturun. Başlamak için buradaki [örneklere](../hololens-kiosk-reference.md#kiosk-xml-code-samples) bakın.

1. [Windows yapılandırma tasarımcısını](https://www.microsoft.com/store/apps/9nblggh4tx22)açın.

1. başlangıç sayfasında **HoloLens cihazları sağla** ' yı seçin. <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. **HoloLens 2 cihazlarını sağla '** yı seçin ve ardından ileri ' yi seçin. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Projenizi adlandırın. İsteğe bağlı olarak bir açıklama yazın. Devam etmek için **son** ' u seçin.

6. Ekranın sol alt kısmında **Gelişmiş düzenleyiciye geç** ' i seçin. Evet ' i seçerek gelişmiş düzenleyiciye geçiş yapmayı onaylayın **.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Sol tarafta, çalışma zamanı ayarları, atanan ' i genişletin ve **Multiappassignedaccess**' ı seçin. <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Web kaynağı olarak karşıya yüklenecek bir dosya seçmek için **Gözat…** düğmesini açın. Ve yapılandırılmış bilgi noktası XML dosyanızı seçin.

9. **Dışarı aktar** ' ı ve **sağlama paketi**' ni seçin.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Sahip türünü **BT Yöneticisi** olarak değiştirin. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Üç kez **İleri**'yi seçin. Ardından **Oluştur**' u seçin.

12. Sağlama paketiniz oluşturulduktan sonra çıkış konumu klasörünü açın. . Ppkg dosyası, sağlama paketiniz. İsteğe bağlı adım: projenizi kaydedin.

13. Artık sağlama paketinizi uygulayabilirsiniz. [kurulum sırasında HoloLens bir sağlama paketi uygulayabilir](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) veya [kurulum sonrasında HoloLens bir sağlama paketi uygulayabilirsiniz](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Bilgi noktası deneyimi için hedef kullanıcı olarak oturum açın.

# <a name="runtime-provisioning---single-app"></a>[Çalışma zamanı sağlama-tek uygulama](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Çalışma zamanı sağlama-tek uygulama

1. [Windows yapılandırma tasarımcısını](https://www.microsoft.com/store/apps/9nblggh4tx22)açın.

1. başlangıç sayfasında **HoloLens cihazları sağla** ' yı seçin. <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. **HoloLens 2 cihazlarını sağla '** yı seçin ve ardından ileri ' yi seçin. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Projenizi adlandırın. İsteğe bağlı olarak bir açıklama yazın. Devam etmek için **son** ' u seçin.

5. Ekranın sol alt kısmında **Gelişmiş düzenleyiciye geç** ' i seçin. Evet ' i seçerek gelişmiş düzenleyiciye geçiş yapmayı onaylayın **.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Sol tarafta, çalışma zamanı ayarları, atanan ' i genişletin ve **atanan Daccesssettings**' i seçin. <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Metin kutusunda bilgi bilgilerinizi tanımlayın. Örneğin, aşağıdaki, ayarlar uygulaması olan LocalAccount adlı yerel bir hesap için tek bir uygulama bilgi noktası oluşturur.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. **Dışarı aktar** ' ı ve **sağlama paketi**' ni seçin. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Sahip türünü **BT Yöneticisi** olarak değiştirin. <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Üç kez **İleri**'yi seçin. Ardından **Oluştur**' u seçin.

11. Sağlama paketiniz oluşturulduktan sonra çıkış konumu klasörünü açın. . Ppkg dosyası, sağlama paketiniz. İsteğe bağlı adım: projenizi kaydedin.

12. Artık sağlama paketinizi uygulayabilirsiniz. [kurulum sırasında HoloLens bir sağlama paketi uygulayabilir](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) veya [kurulum sonrasında HoloLens bir sağlama paketi uygulayabilirsiniz](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).