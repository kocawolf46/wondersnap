# WonderSnap

* Tamamen tarayıcınızda çalışan, parlayan ışık parçacıklarından oluşan hareket kontrollü 3D modeller.**

Parmaklarınızı web kameranızın önüne çekin ve 250.000'e kadar GPU parçacığı var olur. Bir yumruk yap ve onlar
eyfel Kulesi'ni, atan bir kalbi veya bir V8 motorunu oluşturun. Elinizi açın ve model bir sonrakine dönüşür veya
her parçanın etiketli bir diyagramına patlar. Fare yok, denetleyici yok, düğümün ötesine kurulum yok.js.

![Parçacıklardan oluşan atan bir insan kalbini gösteren WonderSnap] (dokümanlar / önizleme.png)

## Hızlı başlangıç

İhtiyacın olan [Node.js ](https://nodejs.org /) 18 veya daha yenisi ve bir web kamerası (isteğe bağlı: her şey fare ile de çalışır ve
klavye).

"'bash
git clone  https://github.com/kocawolf46/wondersnap.git 
cd wondersnap
npm install
npm start
```

Sonra aç **http://localhost:5173 * * Chrome veya Edge'de * * Kamerayla başla ** veya * * Kamerasız devam Et'i tıklayın**
ekran düğmeleri ve klavye ile sürmek için.

> Tarayıcı yalnızca 'localhost` veya 'https'de kamera erişimine izin verir, bu nedenle uygulama kendi küçük özelliği ile birlikte gelir
> yerel sunucu. Farklı bir bağlantı noktası kullanmak için: 'npm start -- 8080'.

## Nasıl çalışır

/ Katman / Ne yapar |
|---|---|
/ ** El takibi * * / [MediaPipe El Yer İmi] (https://ai .Google.dev / edge / mediapipe / solutions / vision / hand_landmarker) web kamerasından tamamen cihaz üzerinde iki ele kadar (her biri 21 yer işareti) izler |
/ * * Jest tanıma * / / Özel sınıflandırıcılar, yer işaretlerini pozlara dönüştürür (yumruk, açık, nokta, tutam, barış), bir parmak çırpıda dedektör, elle döndürme / eğme ve iki elle yakınlaştırma, bir debouncer ve bir durum makinesinden beslenir |
/ * * Parçacık motoru * * / elle yazılmış bir WebGL2 oluşturucu. Parçacık fiziği gpu'da dönüşüm geri bildirimi ile çalışır: üç yok.js, oyun motoru yok, çerçeve yok |
/ ** Modeller * * / Patlayabilen, parlayabilen ve dışarı çekilebilen adlandırılmış parçalarla gerçek ölçümlerden oluşturulmuş ve nokta bulutlarına örneklenmiş 33 prosedür modeli |
/ * * Sunucu * * / sıfır bağımlılık Düğümü.js statik sunucusu ('sunucu.mjs`) |

Hiçbir yere hiçbir şey gönderilmez: video makinenizi asla terk etmez.

## Jestler

/ Jest / Ne yapar |
|---|---|
/Snap ** Snap ** / Parçacıkları çağır veya mevcut modeli çöz |
|Fist ** Yumruk * / / Harikayı, organı veya makineyi oluşturun |
/ hand ** Açık el ** / Harikalar bir sonrakine dönüşür. Organlar, motorlar ve araçlar * * patlar **: elinizi ne kadar açtığınız, parçaların ne kadar uzağa uçtuğunu belirler ve onu kapatmak onları tekrar bir araya getirir |
/ 🔄 ** Bükün / elinizi kaldırın * / / Oluşan modeli çevirin ve eğin |
/ ️ ️ ** Nokta ** / Seçmek için parmağınızı bir parçanın üzerinde tutun. Parlıyor ve bir kart ne yaptığını açıklıyor |
/ 🤏 ** Çimdik ** / Seçilen parçayı kendinize doğru çekin; geri koymak için tekrar çimdikleyin |
/ 🙌 ** İki el ** / Yakınlaştırmak için onları birbirinden ayırın veya birlikte hareket ettirin |
/ ✌ ️ ** Barış ** | Bir sonraki modele atla /

## Klavye ve fare

/ Anahtar / Eylem |
|---|---|
/ ' Boşluk' / Geçmeli |
/ `F ` | ` O ` / ' V ' / Yumruk / açık el / barış işareti |
/ '←"→'/ Önceki | sonraki model /
/ ` E`, '↑`↓', fare tekerleği | Patlama miktarı /
| `+` `-` `0`, ctrl + tekerlek / Yakınlaştır |
| ' C ' / Kamera açık / kapalı |
/ ' L ' / Parça etiketleri |
| ' R ' / Otomatik döndür |
/ 'G ' / El dönüşü açık / kapalı |
| 'X ` / Kesik kesit ( ` , 've'.'uçağı dürtün) |
| 'Q' | Sınav modu /
/ ' M ' / Sesli komutlar ve sesli okuma |
/ ' K ' / Videoya kaydet |
/ ' D ' / Demoyu çal |
/ ' İ ` | ` Esc ' / Açıkla / seçili parçanın seçimini kaldır |
| ' H ' / Yardım |

Bir parçayı seçmek için tıklayın, döndürmek için sürükleyin.

## Özellikler

- ** Kalp atışı ve akciğerleri solumak.** Kalp, dakikada 72 atımlık bir lub-dub ritminde kasılır, akciğerler her seferinde şişer.
  4.5 saniye ve ışık darbeleri kan veya hava gibi içlerinden geçer.
- ** Adlandırılmış parçalarla patlatılmış görünümler.** Her parçanın ne yaptığını söyleyen bir lider çizgisi etiketi vardır.
- ** Sınav modu.** "Bul: Hipokampus": sağ kısma gelin (veya tıklayın). Bir puanla beş soru.
- ** Ses kontrolü.** "Bana kalbi göster", "aç", "sağ atriyum nerede", "yakınlaştır", "sınav" ve daha fazlasını söyleyin.
  Parçalar konuşma sentezi (Krom veya Kenar) ile yüksek sesle okunur.
-Kesik kesik.* Bir kesme düzlemi elinizi takip eder ve parlayan bir kesit ortaya çıkarır.
- ** Kayıt.** Sahnenin bir WebM videosunu kaydedin.

## Modeller

/ Kategori / Modeller |
|---|---|
/ ** Harikalar (11) * * / Kaplumbağa Kulesi, Eyfel Kulesi, Özgürlük Anıtı, Burç Halife, Büyük Piramit, Kolezyum, Pisa Kulesi, Tac Mahal, Big Ben, Kurtarıcı İsa, Sidney Opera Binası |
/ * * Anatomi (10) * / / Beyin, atan Kalp, Böbrek, nefes alan Akciğerler, Göz, Kulak, Diş, Kafatası, iskelet, insan vücudu |cilt, organlar, sinirler, arterler, damarlar, iskelet) /
/ ** Biyoloji (2) * * / Fermuarını açan DNA çift sarmalı, Hayvan hücresi |
/ * * Motorlar (4) * / / Sıralı-4, Süper Şarjlı HEMİ V8, Turbofan jet, 9 silindirli radyal |
/ * * Araçlar (4) * / / Spor araba, Motosiklet, Uçak, Saturn V (kademe ayrımlı) |
/ * * Makineler (2) * / / Mekanik kol saati, EV pil takımı (280 hücre, baralar, soğutma, BMS) |

## Hareket hassasiyeti

Durum panelindeki * * Hareket hassasiyeti * * kontrolü, orijinal hareketi koruyan ** Standart ** olarak varsayılandır
eşikler. ** Daha bağışlayıcı * * statik el pozu tanıma ve açıklığı hafifçe rahatlatır. Snap ve tutam algılama
değişmez ve seçim yalnızca geçerli sayfa oturumu için sürer.

## URL seçenekleri

/ Seçenek / Efekt |
|---|---|
| `?N = 250000 ' / Parçacık sayısı |
| `?model = 12' / Belirli bir modelde başla |
| `?otomatik başlatma = kamera '/'?otomatik başlatma = nocamera ' / Başlangıç ekranını atla /
| `?yollar = 0` / Parçacık yollarını kapat /
| `?dpr= 1` | Aygıt piksel oranını zorla (daha yavaş gpu'larda kullanışlıdır) /

## Testler

39 [Oyun Yazarı] ile uçtan uca ve birim testleri (https://playwright .dev /), gerçek uygulamayı sentetik ellerle sürmek
deterministik bir saat.

"'bash
npx oyun yazarı chromium'u bir kez yükleyin
npm testi
```

/ Spec / Kapaklar |
|---|---|
/ 'uygulama.spesifikasyon.js' / tam jest hikayesi, her model, patlama / sözleşme, klavye, tekerlek, sekmeler, demo, telefon düzeni, elle döndürme ve eğme /
/ 'özellikler.spesifikasyon.js' / Kalp atışı ve nefes alma, iki elle yakınlaştırma, noktadan noktaya seçme, sıkıştırarak çekme, bilgi yarışması, sesli komutlar, kesme, video kaydı |
/ 'kamera.spesifikasyon.js '/ Chromium'un sahte web kamerasında mediapipe'a gerçek 'getUserMedia' ve ayrıca kamera tarafından reddedilen geri dönüş |
/ 'gpu.spesifikasyon.js / / GPU fizik gölgelendiricisi, CPU ikizini her modda ~ 1e-7 ile eşleştirir |
/ 'mantık.spesifikasyon.js ' / Poz sınıflandırıcılar, snap dedektörü, debouncer, durum makinesi, kontrolör, sesli komut ayrıştırıcı |
/ 'modeller.spesifikasyon.js ' / Her model deterministik, sonlu ve hızlıdır, gerçek ölçümler ve doğru patlayan parçalar ile |

## Proje yapısı

```
indeks.html, stiller.css sayfası ve stilleri
sunucu.mjs sıfır bağımlılık statik sunucusu
modeller / MediaPipe el dönüm noktası modeli
src / uygulama.js oluşturma döngüsü, patlat, yakınlaştır, toplama, sınav, kesme, HUD, etiketler, demo
src / eller.js web kamerası + MediaPipe el Landmarker
src / özellikler.js sesli komutlar, sesli okuma, video kaydedici
src / gl / WebGL2 gölgelendiriciler ve oluşturucu (dönüşüm-geri bildirim fiziği)
src / mantık / hareketler, durum makinesi, kontrolör, CPU fiziği ikiz
src / lib / vektör matematiği, örnekleyiciler, prosedürel şekiller
src/modeller/harikalar anatomi biyoloji motorlar araçlar makineleri
testler / oyun yazarlarının özellikleri
```

## Sorun Giderme

- ** Kamera başlamıyor` * * uygulamayı 'http://localhost:5173 ', ' dizini çift tıklatarak değil.html' ve izin ver
  tarayıcı sorduğunda kameraya erişim.
- ** El takibi asla yüklenmez: * * önce `npm yüklemesini' çalıştırın; izleme çalışma zamanı 'mode_modules' öğesinden sunulur.
- ** Düşük kare hızı: * * deneyin `http://localhost:5173 /?n = 100000& dpr = 1'.
- ** Zaten kullanımda olan bağlantı noktası` ** 'npm başlat -- 8080' ve aç 'http://localhost:8080 '.

## Lisans

[MIT] (LİSANS) © 2026 Ali KOCA
