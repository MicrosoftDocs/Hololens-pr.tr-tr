---
title: HoloLens 1 (genel) sürüm notları
description: Her yeni HoloLens sürümündeki güncelleştirmeler hakkında bilgi edinin.
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
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2021
ms.locfileid: "111378945"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1 (genel) sürüm notları

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. Genel) uzun süreli bakım
HoloLens (1. gen), uzun süreli bakım (LTS) durumuna girdi. Gelecekteki güncelleştirmeler, Windows 10 holographic, HoloLens için sürüm 1809 sürümü (1. Genel) ile özellik eşliği sağlarken, sorun ve güvenlik düzeltmelerini odaklayacaktır.

Geliştiriciler için bu, HoloLens (1. gen) uygulamalarının OpenXR API 'sini desteklemeceği anlamına gelir.  Bu kulaklıklar, Unity 2019 LTS 'nin Mid-2022 üzerinden tam yaşam döngüsü için WinRT API arka ucu ile Unity 2019 LTS 'de desteklenmeye devam eder.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 holographic, sürüm 1809

> **Uygulama hedefi:** HoloLens (1. Genel)

| Özellik | Ayrıntılar |
|---|---|
| **Hızlı Eylemler menüsü** | Bir uygulamada olduğunuzda, Bloom hareketi artık uygulamayı bırakmaya gerek kalmadan yaygın olarak kullanılan sistem özelliklerine hızlı erişim sağlamak için hızlı eylemler menüsünü açar. <br> Bilgi noktası modundaki Hızlı Eylemler menüsü hakkında daha fazla bilgi için bkz. bilgi [noktası modunda HoloLens ayarlama](hololens-kiosk.md) .<br><br> |
| **Başlat veya hızlı eylemler menüsünden video yakalamayı durdur** | Video yakalamayı Başlat menüsünde veya hızlı eylemler menüsünden başlatırsanız, kaydı aynı yerden durdurabilirsiniz. (Bunu unutmayın, her zaman sesli komutlarla bunu yapabilirsiniz.) |
| **Miracast özellikli bir cihaza proje** | HoloLens içeriğinizi, Microsoft görüntü bağdaştırıcısı kullanıyorsanız yakındaki bir yüzey cihazına veya TV/Izleyicisine göre proje.  **Başlat** sayfasında **Bağlan**' ı seçin ve ardından proje yapmak istediğiniz cihazı seçin. **Note:** Geliştirici modunu etkinleştirmeden Miracast projeksiyonunu kullanmak için HoloLens dağıtımı yapabilirsiniz. |
| **Yeni bildirimler** | Tıpkı bir PC 'de yaptığınız gibi, HoloLens 'teki bildirimleri görüntüleyin ve yanıtlayın. Yanıt verme veya kapatma (veya modern bir deneyimle karşılaşırsanız Bloom hareketini kullanın). |
| **HoloLens Yerpaylaşımları**<br>(dosya seçici, klavye, iletişim kutuları, vb.) | Artık, derinlikli uygulamalar kullanılırken klavye, iletişim kutusu, dosya seçici vb. gibi yer paylaşımlarını görürsünüz. |
| **Birim değişikliği için görsel geri bildirim kaplama Kullanıcı arabirimi** | HoloLens 'te birim yukarı/aşağı düğmelerini kullandığınızda birim düzeyinin görsel bir görüntüsünü görürsünüz. |
| **Cihaz önyüklemesi için yeni kullanıcı arabirimi** | Sistemin yüklendiği görsel geri bildirim sağlamak için önyükleme işlemi sırasında bir yükleme göstergesi eklendi. Yeni yükleme göstergesini görmek için cihazınızı yeniden başlatın — "Merhaba" iletisi ve Windows önyükleme logosu arasındadır. |
| **Yakın paylaşım** | Windows yakın paylaşım deneyiminin eklenmesi, yakındaki bir Windows cihazınızla bir yakalama paylaşmanıza olanak sağlar. HoloLens 'te bir fotoğraf veya video yakaladığınızda (veya Microsoft Edge gibi bir uygulamadan paylaşma düğmesini kullandığınızda), ile paylaşmak için yakındaki bir Windows cihazını seçin. |
| **Microsoft Edge 'ten paylaşma** | Paylaşma düğmesi artık HoloLens üzerinde Microsoft Edge Windows üzerinde kullanılabilir. Microsoft Edge 'de, **paylaşma**' yı seçin. Web içeriğini paylaşmak için HoloLens Share seçiciyi kullanın. |

#### <a name="for-international-customers"></a>Uluslararası müşteriler için

| Özellik | Ayrıntılar |
| --- | --- |
| Yerelleştirilmiş Çince ve Japonca derlemeler | Yerelleştirilmiş Pinyin klavyesi, dikte etme ve ses komutları gibi Basitleştirilmiş Çince veya Japonca için, yerelleştirilmiş kullanıcı arabirimi ile HoloLens kullanın.<br>[HoloLens 'in Çince ve Japonca sürümlerini yüklemeyi öğrenin.](hololens1-install-localized.md) |
| Konuşma birleştirme (TTS) | Konuşma birleştirme özelliği artık Çince, Japonca ve Ingilizce 'yi destekliyor. |

#### <a name="for-administrators"></a>Yöneticiler için

| Özellik |  Ayrıntılar  |
|---|----|
| [Kurulum sonrası sağlamayı etkinleştir](hololens-provisioning.md) | Artık **ayarları** kullanarak istediğiniz zaman bir çalışma zamanı sağlama paketi uygulayabilirsiniz. |
| Azure AD gruplarıyla erişim atandı | Artık tek veya birden çok uygulama bilgi noktası yapılandırması ayarlamak için Windows atanan erişim yapılandırması için Azure AD gruplarını kullanabilirsiniz. |
| Oturum açma ekranından profil anahtarı 'nda oturum açma SABITLEME | PIN oturum açma, artık **diğer kullanıcılar** için kullanılabilir. |
| Parola kullanarak Web kimlik bilgisi sağlayıcısıyla oturum açın | Artık, parolanızla birlikte Web oturumu açmak için dünya çapında oturum açma seçeneğini belirleyebilirsiniz. Oturum açma ekranında, **oturum açma seçenekleri** ' ni seçin ve Web oturum açma 'yı başlatmak için dünya seçeneğini belirleyin. Gerekirse Kullanıcı adınızı girip parolanızı girin. <br>**Note:** Web oturum açma sırasında istendiğinde herhangi bir PIN/akıllı kart seçeneğini atlayabilirsiniz. |
| Cihazların seri numarasına göre izlenebilmesi için MDM aracılığıyla cihaz donanım bilgilerini okuyun | BT yöneticileri, MDM konsolundaki cihaz seri numarasına göre HoloLens 'i görebilir ve izleyebilir. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |
| MDM aracılığıyla HoloLens cihaz adını ayarlama (yeniden adlandır) | BT yöneticileri, MDM konsolunda HoloLens cihazlarını görebilir ve yeniden adlandırabilir. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Microsoft HoloLens için Windows 10, sürüm 1803

> **Uygulama hedefi:** HoloLens (1. Genel)

Windows 10, sürüm 1803, Windows 10, sürüm 1607 ' deki sürümünden itibaren Windows holographic for Business için ilk özellik güncelleştirmesidir. Bu güncelleştirme aşağıdaki değişiklikleri tanıtır:

- Daha önce, VPN 'nin cihazda kullanılabilir bir seçenek olup olmadığını denetleyerek, yalnızca ticari paketin yükseltme lisansının HoloLens cihazınıza uygulandığını doğrulayabilirsiniz. Şimdi,   >  yükseltme lisansı uygulandıktan sonra ayarlar **sistemi** **Windows holographic for Business** 'ı görüntüleyecek. [Windows holographic for Business özelliklerini nasıl kilitleyeceğinizi öğrenin](hololens1-upgrade-enterprise.md).

- İşletim sistemi yapı numarasını dosya Gezgini uygulamasında ve [Windows cihaz kurtarma aracında (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)cihaz özelliklerinde görüntüleyebilirsiniz.
- Windows yapılandırma Tasarımcısı aracında yeni **HoloLens cihazları sağlama** Sihirbazı Ile bir HoloLens cihazının sağlanması artık daha kolay. Sihirbazda, kurulum deneyimini ve ağ bağlantılarını yapılandırabilir, Geliştirici modunu ayarlayabilir ve toplu Azure AD belirteçleri alabilirsiniz. [HoloLens için basit sağlama Sihirbazı 'nı nasıl kullanacağınızı öğrenin](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Bir sağlama paketinde yerel bir hesap oluşturduğunuzda, parola artık her 42 günde bir sona erer.

- [HoloLens 'i tek uygulama veya birden çok uygulama bilgi noktası olarak yapılandırabilirsiniz](hololens-kiosk.md). Birden çok uygulama bilgi noktası modu, yalnızca belirttiğiniz uygulamaları çalıştırmak için bir HoloLens ayarlamanıza olanak sağlar ve kullanıcıların değişiklik yapmalarını önler.

- Medya Aktarım Protokolü (MTP), HoloLens cihazını USB ile bir BILGISAYARA bağlamak ve HoloLens ile BILGISAYAR arasında dosya aktarmak için etkinleştirilir. Ayrıca dosya Gezgini uygulamasını kullanarak, dosyaları HoloLens içinden taşıyabilir ve silebilirsiniz.

- Daha önce, cihazda Azure Active Directory (Azure AD) hesabıyla oturum açtıktan sonra, şirket kaynaklarına erişebilmek için **Ayarlar** ' da **iş erişimi eklemeniz** gerekiyordu. Artık bir Azure AD hesabıyla oturum açıp kayıt otomatik olarak gerçekleştirilir.

- Oturum açmadan önce, bağlanılacak farklı bir Wi-Fi ağı seçmek için parola alanının altında bulunan ağ simgesini seçebilirsiniz. Ayrıca, bir otel, konferans merkezi veya iş gibi bir konuk ağa da bağlanabilirsiniz.

- Artık Azure AD hesapları 'nı kullanarak [HoloLens 'i birden çok kişiyle kolayca paylaşabilirsiniz](hololens-multiple-users.md) .

- Kurulum veya oturum açma başarısız olduğunda, sorun giderme için tanılama günlüklerini almak üzere yeni **bilgi topla** seçeneğini belirleyin.

- Bireysel kullanıcılar, cihazlarını mobil cihaz yönetimine (MDM) kaydetmeden kurumsal e-postalarını eşitleyebilir. Cihazı bir Microsoft hesabıyla kullanabilir, posta uygulamasını indirip yükleyebilir ve doğrudan bir e-posta hesabı ekleyebilirsiniz.

- **Ayarlar**  >  **hesaplar**  >  **iş veya okul**  >  **bilgilerinde** erişim ' de bir cihazın MDM eşitleme durumunu kontrol edebilirsiniz. **Cihaz eşitleme durumu** bölümünde, bir eşitleme BAŞLATABILIR, MDM tarafından yönetilen alanlara bakın ve gelişmiş tanılama raporu oluşturabilir ve dışarı aktarabilirsiniz.
