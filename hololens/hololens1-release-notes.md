---
title: HoloLens 1 (gen) sürüm notları
description: her yeni HoloLens sürümünde güncelleştirmeler hakkında bilgi edinin.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661842"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1 (gen) sürüm notları

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. genel) uzun süreli bakım
HoloLens (1. gen) uzun süreli bakım (lts) durumuna girdi. sonraki güncelleştirmeler sorun ve güvenlik düzeltmelerini odaklamaktadır. bu özellik eşlik Windows 10 Holographic, sürüm 1809 sürümü HoloLens (1. gen).

geliştiriciler için bu, HoloLens (1. gen) uygulamaların openxr apı 'sini desteklememeyeceği anlamına gelir.  Bu kulaklıklar, Unity 2019 LTS 'nin Mid-2022 üzerinden tam yaşam döngüsü için WinRT API arka ucu ile Unity 2019 LTS 'de desteklenmeye devam eder.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, sürüm 1809

> **uygulama hedefi:** HoloLens (1. genel)

| Özellik | Ayrıntılar |
|---|---|
| **Hızlı Eylemler menüsü** | Bir uygulamada olduğunuzda, Bloom hareketi artık uygulamayı bırakmaya gerek kalmadan yaygın olarak kullanılan sistem özelliklerine hızlı erişim sağlamak için hızlı eylemler menüsünü açar. <br> bilgi noktası modundaki hızlı eylemler menüsü hakkında daha fazla bilgi için bkz. bilgi [noktası modunda HoloLens ayarlama](hololens-kiosk.md) .<br><br> |
| **Başlat veya hızlı eylemler menüsünden video yakalamayı durdur** | video yakalamayı Başlat menüsü veya hızlı eylemler menüsünden başlatırsanız, kaydı aynı yerden durdurabilirsiniz. (Bunu unutmayın, her zaman sesli komutlarla bunu yapabilirsiniz.) |
| **Miracast etkin bir cihaza Project** | HoloLens içeriğinizi, Microsoft görüntü bağdaştırıcısı kullanıyorsanız yakındaki bir yüzey cihazına veya TV/izleyici 'ye Project.  **başlat**' ı **Bağlan** seçin ve ardından proje yapmak istediğiniz cihazı seçin. **Note:** Miracast projeksiyonu, geliştirici modunu etkinleştirmeden kullanmak için HoloLens dağıtabilirsiniz. |
| **Yeni bildirimler** | tıpkı bir PC 'de yaptığınız gibi HoloLens bildirimleri görüntüleyin ve bunlara yanıt verin. Yanıt verme veya kapatma (veya modern bir deneyimle karşılaşırsanız Bloom hareketini kullanın). |
| **HoloLens yer paylaşımları**<br>(dosya seçici, klavye, iletişim kutuları, vb.) | Artık, derinlikli uygulamalar kullanılırken klavye, iletişim kutusu, dosya seçici vb. gibi yer paylaşımlarını görürsünüz. |
| **Birim değişikliği için görsel geri bildirim kaplama Kullanıcı arabirimi** | HoloLens birim yukarı/aşağı düğmelerini kullandığınızda birim düzeyinin görsel bir görüntüsünü görürsünüz. |
| **Cihaz önyüklemesi için yeni kullanıcı arabirimi** | Sistemin yüklendiği görsel geri bildirim sağlamak için önyükleme işlemi sırasında bir yükleme göstergesi eklendi. yeni yükleme göstergesini görmek için cihazınızı yeniden başlatın — "merhaba" iletisi ve Windows önyükleme logosu arasındadır. |
| **Yakın paylaşım** | yakın Windows paylaşma deneyiminin eklenmesi, yakındaki bir Windows cihazınızla bir yakalama paylaşmanıza olanak sağlar. HoloLens bir fotoğraf veya video yakaladığınızda (veya Microsoft Edge gibi bir uygulamadan paylaşma düğmesini kullandığınızda), ile paylaşılacak yakındaki bir Windows cihazını seçin. |
| **Microsoft Edge paylaşma** | paylaşma düğmesi artık HoloLens Microsoft Edge windows üzerinde kullanılabilir. Microsoft Edge, **paylaşma**' yı seçin. web içeriğini paylaşmak için HoloLens paylaşma seçiciyi kullanın. |

#### <a name="for-international-customers"></a>Uluslararası müşteriler için

| Özellik | Ayrıntılar |
| --- | --- |
| Yerelleştirilmiş Çince ve Japonca derlemeler | yerelleştirilmiş Pinyin klavyesi, dikte etme ve ses komutları gibi basitleştirilmiş çince veya japonca için yerelleştirilmiş kullanıcı arabirimiyle HoloLens kullanın.<br>[HoloLens Çince ve Japonca sürümlerini yüklemeyi öğrenin.](hololens1-install-localized.md) |
| Konuşma birleştirme (TTS) | Konuşma birleştirme özelliği artık Çince, Japonca ve Ingilizce 'yi destekliyor. |

#### <a name="for-administrators"></a>Yöneticiler için

| Özellik |  Ayrıntılar  |
|---|----|
| [Kurulum sonrası sağlamayı etkinleştir](hololens-provisioning.md) | artık **Ayarlar** kullanarak dilediğiniz zaman bir çalışma zamanı sağlama paketi uygulayabilirsiniz. |
| Azure AD gruplarıyla erişim atandı | artık tek veya birden çok uygulama bilgi noktası yapılandırması ayarlamak için Windows atanan erişim yapılandırması için Azure AD gruplarını kullanabilirsiniz. |
| Oturum açma ekranından profil anahtarı 'nda oturum açma SABITLEME | PIN oturum açma, artık **diğer kullanıcılar** için kullanılabilir. |
| Parola kullanarak Web kimlik bilgisi sağlayıcısıyla oturum açın | Artık, parolanızla birlikte Web oturumu açmak için dünya çapında oturum açma seçeneğini belirleyebilirsiniz. Oturum açma ekranında, **oturum açma seçenekleri** ' ni seçin ve Web oturum açma 'yı başlatmak için dünya seçeneğini belirleyin. Gerekirse Kullanıcı adınızı girip parolanızı girin. <br>**Note:** Web oturum açma sırasında istendiğinde herhangi bir PIN/akıllı kart seçeneğini atlayabilirsiniz. |
| Cihazların seri numarasına göre izlenebilmesi için MDM aracılığıyla cihaz donanım bilgilerini okuyun | bt yöneticileri, MDM konsolundaki cihaz seri numarasına göre HoloLens görebilir ve izleyebilir. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |
| MDM aracılığıyla HoloLens cihaz adı ayarla (yeniden adlandır) | bt yöneticileri, MDM konsolundaki HoloLens cihazlarını görebilir ve yeniden adlandırabilir. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, Microsoft HoloLens için sürüm 1803

> **uygulama hedefi:** HoloLens (1. genel)

Windows 10, sürüm 1803, Windows 10 sürüm 1607 ' deki sürümü bu yana Windows Holographic for Business ilk özellik güncelleştirmesidir. Bu güncelleştirme aşağıdaki değişiklikleri tanıtır:

- daha önce, VPN 'nin cihazda kullanılabilir bir seçenek olup olmadığını denetleyerek, yalnızca ticari paketin yükseltme lisansının HoloLens cihazınıza uygulandığını doğrulayabilirsiniz. artık **Ayarlar**  >  **sistem** , yükseltme lisansı uygulandıktan sonra **Windows Holographic for Business** görüntüler. [Windows Holographic for Business özelliklerinin kilidini nasıl kilitleyeceğinizi öğrenin](hololens1-upgrade-enterprise.md).

- işletim sistemi yapı numarasını dosya gezgini uygulamasında ve [Windows cihaz kurtarma aracında (wdrt)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)cihaz özellikleri ' nde görüntüleyebilirsiniz.
- Windows Configuration Designer aracında yeni **sağlama HoloLens cihazları** sihirbazı ile HoloLens bir cihazın sağlanması artık daha kolay. Sihirbazda, kurulum deneyimini ve ağ bağlantılarını yapılandırabilir, Geliştirici modunu ayarlayabilir ve toplu Azure AD belirteçleri alabilirsiniz. [HoloLens için basit sağlama Sihirbazı 'nı kullanmayı öğrenin](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Bir sağlama paketinde yerel bir hesap oluşturduğunuzda, parola artık her 42 günde bir sona erer.

- [HoloLens tek uygulama veya birden çok uygulama bilgi noktası olarak yapılandırabilirsiniz](hololens-kiosk.md). birden çok uygulama bilgi noktası modu, yalnızca belirttiğiniz uygulamaları çalıştırmak için bir HoloLens ayarlamanıza olanak sağlar ve kullanıcıların değişiklik yapmalarını önler.

- medya aktarım protokolü (MTP), HoloLens cihazını USB ile bilgisayara bağlayabilmeniz ve HoloLens ile bilgisayar arasında dosya aktarabilmek için etkinleştirilmiştir. Dosya Gezgini uygulamasını, dosyaları HoloLens içinden taşımak ve silmek için de kullanabilirsiniz.

- daha önce, cihazda Azure Active Directory (Azure AD) hesabıyla oturum açtıktan sonra, şirket kaynaklarına erişim sağlamak için **Ayarlar** **iş erişimi eklemeniz** gerekiyordu. Artık bir Azure AD hesabıyla oturum açıp kayıt otomatik olarak gerçekleştirilir.

- Oturum açmadan önce, bağlanılacak farklı bir Wi-Fi ağı seçmek için parola alanının altında bulunan ağ simgesini seçebilirsiniz. Ayrıca, bir otel, konferans merkezi veya iş gibi bir konuk ağa da bağlanabilirsiniz.

- artık Azure AD hesaplarını kullanarak [birden çok kişiyle HoloLens kolayca paylaşabilirsiniz](hololens-multiple-users.md) .

- Kurulum veya oturum açma başarısız olduğunda, sorun giderme için tanılama günlüklerini almak üzere yeni **bilgi topla** seçeneğini belirleyin.

- Bireysel kullanıcılar, cihazlarını mobil cihaz yönetimine (MDM) kaydetmeden kurumsal e-postalarını eşitleyebilir. Cihazı bir Microsoft hesabıyla kullanabilir, posta uygulamasını indirip yükleyebilir ve doğrudan bir e-posta hesabı ekleyebilirsiniz.

- **Ayarlar**  >  **hesaplarında**  >  **iş veya okul**  >  **bilgilerine** erişim için MDM eşitleme durumunu kontrol edebilirsiniz. **Cihaz eşitleme durumu** bölümünde, bir eşitleme BAŞLATABILIR, MDM tarafından yönetilen alanlara bakın ve gelişmiş tanılama raporu oluşturabilir ve dışarı aktarabilirsiniz.
