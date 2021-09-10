---
title: HoloLens (1. Nesil) sürüm notları
description: Her yeni sürümde güncelleştirmeler hakkında HoloLens öğrenin.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427551"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens (1. Nesil) sürüm notları

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. Nesil) Uzun Süreli Bakım
HoloLens (1. nesil) Uzun Süreli Bakım (LTS) durumuna girdi. Gelecekteki güncelleştirmeler sorun ve güvenlik düzeltmelerine odaklanırken Windows 10 Holographic sürüm 1809 sürümüyle (1. nesil) özellik HoloLens korur.

Geliştiriciler için bu, HoloLens (1. nesil) uygulamaların OpenXR API'sini desteklemeyecekleri anlamına gelir.  2022'nin ortalarında Unity 2019 LTS'nin tüm yaşam döngüsü boyunca WinRT API arka ucuyla birlikte Unity 2019 LTS'de bu mikrofonlu başlığın desteği devam eder.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, sürüm 1809

> **Uygulama:** HoloLens (1. nesil)

| Özellik | Ayrıntılar |
|---|---|
| **Hızlı eylemler menüsü** | Bir uygulamadayken Bloom hareketi artık uygulamadan ayrılmak zorunda kalmadan yaygın olarak kullanılan sistem özelliklerine hızlı erişim vermek için bir Hızlı eylemler menüsü açar. <br> Bilgi [noktası HoloLens hızlı eylemler menüsü hakkında](hololens-kiosk.md) bilgi için bkz. Bilgi noktası modunda HoloLens ayarlama.<br><br> |
| **Başlat veya hızlı eylemler menüsünden video yakalamayı durdurma** | Başlat menüsü veya hızlı eylemler menüsünden video yakalamayı başlattıysanız, kaydı aynı yerde durdurabilirsiniz. (Bunu sesli komutlarla da her zaman yapabilirsiniz.) |
| **Project etkin Miracast cihaza bağlantı** | Project microsoft HoloLens yakın bir Surface cihazına veya TV/İzleyici'ye bağlayın.  **Başlat'ta** **Bağlan'yi** ve ardından projesini yapmak istediğiniz cihazı seçin. **Not:** Geliştirici modunu etkinleştirmeden HoloLens projeksiyonu Miracast için uygulama dağıtabilirsiniz. |
| **Yeni bildirimler** | Tıpkı bir pc'de olduğu gibi HoloLens bildirim bildirimlerini görüntüleme ve yanıtlama. Yanıt vermeye veya bunları silene (veya çevreleyici bir deneyimdeysiniz) göz atarak bloom hareketini kullanın. |
| **HoloLens katmanları**<br>(dosya seçici, klavye, iletişim kutuları vb.) | Şimdi çevreleyici uygulamaları kullanırken klavye, iletişim kutuları, dosya seçici gibi katmanların olduğunu göreceğiz. |
| **Birim değişikliği için görsel geri bildirim katman kullanıcı arabirimi** | Birim yukarı/aşağı düğmelerini HoloLens düzeyin görsel bir görüntüsü görüntülenir. |
| **Cihaz önyüklemesi için yeni kullanıcı arabirimi** | Sistemin yükleniyor olduğuyla ilgili görsel geri bildirim sağlamak için önyükleme işlemi sırasında bir yükleme göstergesi eklendi. Yeni yükleme göstergesini görmek için cihazınızı yeniden başlatın; bu, "Hello" iletisiyle Windows logosu arasındadır. |
| **Yakındaki paylaşım** | Yakındaki Paylaşım Windows ek olarak, yakınlardaki bir cihazla yakalama Windows sağlar. HoloLens'da bir fotoğraf veya video yakalarken (veya Microsoft Edge gibi bir uygulamanın paylaş düğmesini kullanarak) yakınlardaki bir Windows cihazı seçin. |
| **Microsoft Edge'dan paylaşma** | Paylaş düğmesi artık Microsoft Edge windows üzerinde HoloLens. Bu Microsoft Edge Paylaş'ı **seçin.** Web içeriğini HoloLens için paylaşım seçiciyi kullanın. |

#### <a name="for-international-customers"></a>Uluslararası müşteriler için

| Özellik | Ayrıntılar |
| --- | --- |
| Yerelleştirilmiş Çince ve Japonca derlemeler | Yerelleştirilmiş Pinyin HoloLens, dikte ve ses komutları da dahil olmak üzere Basitleştirilmiş Çince veya Japonca için yerelleştirilmiş kullanıcı arabirimiyle birlikte kullanın.<br>[HoloLens'nin Çince ve Japonca sürümlerini HoloLens.](hololens1-install-localized.md) |
| Konuşma Sentezi (TTS) | Konuşma sentezi özelliği artık Çince, Japonca ve İngilizce desteğine sahiptir. |

#### <a name="for-administrators"></a>Yöneticiler için

| Özellik |  Ayrıntılar  |
|---|----|
| [Kurulum sonrası sağlamayı etkinleştirme](hololens-provisioning.md) | Artık bir çalışma zamanı sağlama paketini kullanarak herhangi bir zamanda **Ayarlar.** |
| Azure AD gruplarıyla atanan erişim | Artık tek veya çok uygulamalı bilgi noktası yapılandırması Windows erişimin yapılandırması için Azure AD gruplarını kullanabilirsiniz. |
| Oturum açma ekranından PIN oturum açma profili anahtarı | PIN oturum açma artık Diğer Kullanıcı **için kullanılabilir.** |
| Parola kullanarak Web Kimlik Bilgisi Sağlayıcı oturum açma | Artık Dünya'da oturum açma seçeneğini seçerek parolanız ile web'de oturum açma başlatabilirsiniz. Oturum açma ekranında Oturum Açma **seçenekleri'ne tıklayın ve Dünya** seçeneğini seçerek web'de oturum açmayı başlatabilirsiniz. Gerekirse kullanıcı adını ve ardından parolanızı girin. <br>**Not:** Web'de oturum açma sırasında istendiğinde herhangi bir PIN/Akıllı Kart seçeneklerini atlaabilirsiniz. |
| Cihazların seri numarasıyla izlen için MDM aracılığıyla cihaz donanım bilgilerini okuma | IT yöneticileri, MDM konsolunda HoloLens seri numarasına göre değişiklikleri görebilir ve izleyebilir. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |
| MDM HoloLens cihaz adını ayarlama (yeniden adlandırma) | IT yöneticileri, MDM konsolunda HoloLens cihazları görebilir ve yeniden adlandırabilirsiniz. Özellik kullanılabilirliği ve yönergeleri için MDM belgelerinize bakın. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 sürüm 1803 Microsoft HoloLens

> **Uygulama:** HoloLens (1. nesil)

Windows 10 1803 sürümü, Windows Holographic for Business 1607 sürümünden bu yana Windows 10 güncelleştirmedir. Bu güncelleştirme aşağıdaki değişiklikleri içerir:

- Daha önce, yalnızca VPN'in cihazda kullanılabilir bir seçenek olup HoloLens bakarak Commercial Suite yükseltme lisansının HoloLens cihazınıza uygulandığını doğrulayabilirsiniz. Şimdi **Ayarlar**  >  **lisansı** **uygulandıktan Windows Holographic for Business** Sistem tarafından görüntülenir. [Yeni özelliklerin kilidini Windows Holographic for Business öğrenin.](hololens1-upgrade-enterprise.md)

- İşletim sistemi derleme numarasını, Dosya Gezgini uygulamasındaki cihaz özelliklerinde ve [Windows Kurtarma Aracı(WDRT) içinde görüntüebilirsiniz.](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Windows Configuration Designer aracında yeni HoloLens  cihazları sağlama sihirbazı ile HoloLens cihaz sağlama artık daha kolay. Sihirbazda kurulum deneyimini ve ağ bağlantılarını yapılandırabilirsiniz, geliştirici modunu ayarlar ve toplu Azure AD belirteçleri elde edersiniz. [HoloLens için basit sağlama sihirbazını kullanmayı HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Sağlama paketinde yerel bir hesap sanız, parolanın süresi 42 günde bir dolmaz.

- Uygulamaları tek [HoloLens veya çoklu uygulama bilgi noktası olarak yapılandırabilirsiniz.](hololens-kiosk.md) Çoklu uygulama bilgi noktası modu, yalnızca belirttiğiniz HoloLens çalıştırmak için bir uygulama noktası ayarlamaya olanak sağlar ve kullanıcıların değişiklik yapmalarını önler.

- Medya Aktarım Protokolü (MTP) etkindir, böylece HoloLens USB ile bir bilgisayara bağ ve HoloLens bilgisayar arasında dosya aktarabilirsiniz. Ayrıca, dosyaları Dosya Gezgini ve silmek için HoloLens.

- Daha önce, bir Azure Active Directory (Azure AD) hesabıyla cihazda oturum Ayarlar şirket  kaynaklarına erişmek  için Ayarlar erişimi eklemeniz gerekirdi. Şimdi bir Azure AD hesabıyla oturum açın ve kayıt otomatik olarak gerçekleşir.

- Oturum açmadan önce, bağlanmak için farklı bir ağ seçmek için parola Wi-Fi ağ simgesini seçebilirsiniz. Ayrıca otel, konferans merkezi veya işletme gibi bir konuk ağına da bağlanabilirsiniz.

- Artık Azure AD [hesaplarını kullanarak HoloLens kişi ile](hololens-multiple-users.md) kolayca paylaşımda bulundurabilirsiniz.

- Kurulum veya oturum açma başarısız olduğunda, sorun gidermeye yönelik tanılama **günlüklerini almak** için yeni Bilgi topla seçeneğini belirleyin.

- Bireysel kullanıcılar, cihazlarını mobil cihaz yönetimine (MDM) kaydetmeden şirket e-postalarını eşitler. Cihazı bir Microsoft Hesabı ile kullanabilir, Posta uygulamasını indirip yükleyebilir ve doğrudan bir e-posta hesabı indirebilirsiniz.

- Hesapların İş veya Okul Bilgilerine Erişmesi için MDM **Ayarlar** durumunu  >    >  **kontrol**  >  **edebilirsiniz.** Cihaz eşitleme **durumu bölümünde bir** eşitleme başlatabilirsiniz, MDM tarafından yönetilen alanları görebilir ve gelişmiş bir tanılama raporu oluşturabilir ve dışarı aktarabilirsiniz.
