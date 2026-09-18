# MON-IN Marka Rehberi v1.0

> Son güncelleme: 2026-09-18
> Durum: Yürürlükte
> Kaynak: `index.html` — sitedeki değerler bu dokümanın doğrulandığı yerdir.

Bu dosya markanın tek doğruluk kaynağıdır. Renk, tipografi veya logo kuralı
değişecekse önce burası güncellenir, sonra koda taşınır — tersi değil.
`assets/design-tokens.json` ve `assets/design-tokens.css` buradaki değerlerin
makine tarafından okunabilir halidir.

## Hızlı Referans

| Element | Value |
|---------|-------|
| Primary Color | #141412 |
| Secondary Color | #F7F7F5 |
| Accent Color | #D71920 |
| Primary Font | Archivo |
| Body Font | Inter |
| Voice | Ölçülü, Yalın, Ciddi |

---

## 1. Renk Paleti

Palet açık ve sıcaktır. Saf beyaz ve saf siyah kullanılmaz — zemin kâğıda,
metin ise mürekkebe çalar. Bu, mimarlık yayıncılığından gelen bilinçli bir
tercihtir ve markanın en hızlı tanınan özelliğidir.

### Primary Colors

| Name | Hex | RGB | Kullanım |
|------|-----|-----|----------|
| Ink | #141412 | rgb(20, 20, 18) | Başlıklar, gövde metni, koyu zemin |
| Ink Soft | #3A3A36 | rgb(58, 58, 54) | İkincil metin, açıklama paragrafları |

### Secondary Colors

| Name | Hex | RGB | Kullanım |
|------|-----|-----|----------|
| Paper | #F7F7F5 | rgb(247, 247, 245) | Ana zemin |
| Paper Tint | #EFEFEC | rgb(239, 239, 236) | Komşu bölümleri ayırmak için |

### Accent Colors

| Name | Hex | RGB | Kullanım |
|------|-----|-----|----------|
| MON-IN Red | #D71920 | rgb(215, 25, 32) | × işareti, künye etiketi, tekil vurgu |

Kırmızı **asla geniş dolgu olarak kullanılmaz**. Bir düğme zemini, bir bölüm
arka planı veya bir kart dolgusu olamaz. Görevi tek bir yere bakmayı sağlamaktır;
iki yere birden bakmayı sağlamaya kalkarsa işlevini kaybeder.

### Nötrler

| Name | Hex | RGB | Kullanım |
|------|-----|-----|----------|
| Gray | #6D6D68 | rgb(109, 109, 104) | Kicker, metadata, tarih |
| Gray Light | #DBDBD6 | rgb(219, 219, 214) | Pasif işaretler, büyük hayalet rakamlar |
| Line | #E2E2DD | rgb(226, 226, 221) | Saç teli çizgiler, ayraçlar |

### Koyu Zemin — yalnızca hero

Sitenin açılış ekranı bilinçli olarak koyudur; tam boy fotoğrafın üstünde
tipografi ters okunur. **Bu tek istisnadır.** Başka hiçbir bölüm, hiçbir iç araç
ve hiçbir sunum koyu zemine geçmez.

| Name | Hex | RGB | Kullanım |
|------|-----|-----|----------|
| Night | #0E0E0C | rgb(14, 14, 12) | Hero fotoğraf zemini |
| Paper on Dark | #EDEDE8 | rgb(237, 237, 232) | Koyu zeminde başlık ve metin |
| Gray on Dark | #A9A9A1 | rgb(169, 169, 161) | Koyu zeminde kicker ve metadata |
| Red on Dark | #DE3F45 | rgb(222, 63, 69) | Koyu zeminde **küçük** kırmızı metin |

Koyu zeminde kırmızı metin yazarken `--red` değil `--red-dk` kullanılır. Marka
kırmızısı gece zeminde 3,73'te kalıyor; küçük punto için yetersiz. Büyük display
metinlerde (hero'daki ×, Intersection'daki ×) ve metin olmayan ögelerde
(gösterge çizgileri) marka kırmızısı olduğu gibi kullanılmaya devam eder.

### Erişilebilirlik

Ölçülen değerler (WCAG 2.1 kontrast oranları):

| Renk | Zemin | Oran | Normal metin | Büyük metin |
|------|-------|------|--------------|-------------|
| Ink #141412 | Paper | 17,20 | AAA | AAA |
| Ink Soft #3A3A36 | Paper | 10,65 | AAA | AAA |
| Gray #6D6D68 | Paper | 4,85 | AA | AA |
| Gray #6D6D68 | Paper Tint | 4,51 | AA | AA |
| Red #D71920 | Paper | 4,83 | AA | AA |
| Paper on Dark #EDEDE8 | Night | 16,45 | AAA | AAA |
| Gray on Dark #A9A9A1 | Night | 8,17 | AAA | AAA |
| Red on Dark #DE3F45 | Night | 4,51 | AA | AA |

**Metin renklerinin tamamı AA'yı geçiyor.** Palet ilk yazıldığında iki zayıf
nokta vardı ve ikisi de düzeltildi: Gray `#7C7C76` iken kâğıt zeminde 3,91'de
kalıyordu, `#6D6D68` oldu; marka kırmızısı koyu zeminde 3,73'te kalıyordu, küçük
metin için `--red-dk` eklendi. Her iki yeni değer de hem kâğıt hem ton zeminde
sınırı geçecek şekilde hesaplandı, gözle seçilerek değil.

Tek bilinçli sapma: hero fotoğrafları 5,4 saniyede bir kendiliğinden dönüyor ve
görünür bir durdurma düğmesi yok. Hareket azaltma tercihinde duruyor, ama tam
kadraj bir açılışa düğme koymanın tasarım bedeli kuralın kazancından ağır
görüldü. Bilerek bırakılmıştır.

---

## 2. Tipografi

### Font Stack

```css
--font-display: 'Archivo', system-ui, -apple-system, sans-serif;
--font-body: 'Inter', system-ui, -apple-system, sans-serif;
```

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Archivo:wght@400;500;600;700;800;900&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
```

Archivo yalnızca başlık ve display içindir, gövde metninde kullanılmaz.
Inter yalnızca gövde, navigasyon ve metadata içindir, büyük başlıklarda
kullanılmaz. Bu ayrım markanın en belirgin tipografik imzasıdır; bozulursa
sayfa anında jenerik görünür.

### Ağırlıklar

| Font | Ağırlık | Nerede |
|------|---------|--------|
| Archivo | 800 / 900 | Hero ve bölüm başlıkları |
| Archivo | 700 | Künye adı, logo kilidi, alt başlık |
| Archivo | 400 | Başlık içindeki ikincil kelime (ör. hero'daki "DESIGN") |
| Inter | 300 | Uzun açıklama paragrafları |
| Inter | 400 | Gövde metni, navigasyon |
| Inter | 500 / 600 | Etiket, sayaç, dil düğmesi |

### Ölçek

| Rol | Boyut | Satır yüksekliği | Harf aralığı |
|-----|-------|------------------|--------------|
| Hero display | clamp(2.6rem, 7.2vw, 6.4rem) | 0,92 | −0,045em |
| Bölüm başlığı | clamp(1.9rem, 4.4vw, 3.4rem) | 1,05–1,12 | −0,03em |
| Alt başlık | clamp(1.8rem, 3.6vw, 2.6rem) | 1,05 | −0,02em |
| Öne çıkan gövde | 1,06rem | 1,65 | 0 |
| Gövde | 0,96–0,98rem | 1,6–1,68 | 0 |
| Metadata | 0,76–0,84rem | 1,5 | 0 |
| Kicker | 0,62–0,80rem | 1,4 | +0,15em – +0,17em |

İki kural her şeyi taşır:

- **Başlıklar negatif harf aralığı alır.** Punto büyüdükçe aralık daralır.
- **Küçük büyük harfli etiketler pozitif aralık alır**, en az 0,15em. Aralıksız
  büyük harf kullanılmaz.

---

## 3. Logo

| Dosya | Kullanım |
|-------|----------|
| `assets/logo/mon-in.png` | Tek kaynak, siyah versiyon |

### Koyu zeminde

Ayrı bir beyaz dosya tutulmaz. Siyah logo CSS ile ters çevrilir:

```css
header.on-dark .brand img { filter: invert(1); }
```

Bu, tek bir dosyanın bakımını yapmayı sağlar. Yeni bir ortam için beyaz logo
gerekirse aynı dosyadan üretilir, ikinci bir kaynak dosya oluşturulmaz.

### Ölçü

| Bağlam | Yükseklik |
|--------|-----------|
| Site başlığı | 28px |
| Minimum dijital | 20px |
| Minimum baskı | 8mm |

### Boşluk

Logonun her yanında en az kendi yüksekliği kadar boşluk bırakılır.

### Kilit — iç araçlar

Stüdyoya ait iç araçlar sol üstte şu kilidi taşır:

```
MON-IN × PROJECT MANAGER
```

`×` bir `<span>` içinde ve kırmızıdır. 64px yüksekliğinde beyaz bir çubukta,
altında saç teli çizgiyle, Archivo 700, 15px, `letter-spacing: .12em`.
Bu kilit bu aileye ait her araçta aynı kalır.

### Yapılmayacaklar

- Döndürmek, eğmek, oranını bozmak
- Palet dışı renk vermek
- Gölge veya efekt eklemek
- Yeterli kontrast olmayan kalabalık fotoğrafın üstüne koymak

---

## 4. × İşareti

× markanın en değerli görsel varlığıdır. Dile bağlı değildir, her ölçekte
çalışır, favicon olur. Şu kurallarla korunur:

| Kural | Neden |
|-------|-------|
| Daima `--red` | Tek sahiplenilen kullanım budur |
| İnce ve geniş çizilir, blok değil | Kalın kırmızı × "kapat / sil" olarak okunur |
| İki terimin arasında durur | Bağlam çarpma/kesişim okumasını anında verir |
| Tek başına dev boyutta kullanılmaz | Bağlamsız kırmızı × "yanlış" demektir |

### Ana kilit

```
DESIGN      SPACE
            ×
TECHNICAL   SPACE
```

Sol kolon açık ağırlıkta niteleyici (DESIGN / TECHNICAL), sağ kolon kalın
ağırlıkta ortak kelime (SPACE / SPACE). Kırmızı × ikisinin arasında, sağ
kolonda durur — böylece iki SPACE kelimesi üst üste hizalanır ve × tam
ortalarına gelir.

İki tarafın da SPACE ile bitmesi tesadüf değil: simetri, iki alanın aynı işin
iki yüzü olduğunu kelime düzeyinde gösterir. Ayrıca Türkçeye çevrilebilir —
**tasarım mekânı** ve **teknik mekân** ikisi de yerleşik terimlerdir.

**Bilinen risk:** Türkiye'de çarpı, okul çağından gelen kodlamayla "yanlış"
anlamı taşır; arayüzlerde de kapatma düğmesidir. Yukarıdaki kurallar bu riski
yönetmek içindir, süs değildir. Navigasyon menüsünde bağlantı etiketi olarak
kullanmak bu yüzden sakıncalıdır.

---

## 5. Ses ve Ton

### Kişilik

| Özellik | Anlamı |
|---------|--------|
| **Ölçülü** | Az kelime. Sıfat yerine somut isim. Ünlem yok. |
| **Yalın** | Tek bir kelime seçilir ve arkasında durulur. |
| **Ciddi** | Espri, kelime oyunu ve moda terim yok. |

Görsel dil zaten sakin ve boşluklu; metin de aynı yerde durmalıdır. Coşkulu
veya karmaşık bir metin, tasarımla çelişir ve ikisini birden zayıflatır.

### Ses Tablosu

| Özellik | Böyleyiz | Böyle değiliz |
|---------|----------|---------------|
| Ölçülü | "100.000 m². 2019." | "Nefes kesen bir ölçekte!" |
| Yalın | "Havalimanı terminali tasarladık." | "Mekânsal deneyim ekosistemleri kurguluyoruz." |
| Ciddi | "Tunceli Şehir Müzesi" | "Müzecilikte oyunun kurallarını değiştirdik" |
| Dürüst | "Tasarladığımız müze EMYA finalisti oldu." | "EMYA ödüllü MON-IN" |

### Yasaklı kalıplar

| Kaçınılacak | Neden |
|-------------|-------|
| "Let's build what's next" | Yüzlerce teknoloji şirketinin kullandığı hazır cümle |
| Üç eşanlamlı yan yana ("spaces, environments and ecosystems") | Somutlaşamayınca genişlemenin işareti; bir tane seçin |
| "Not only X — but Y" | Bir çerçeveyi reddetmek onu pekiştirir |
| "vision", "seamless", "revolutionary", "best-in-class" | İçi boş dolgu |
| "MON-IN won…" (doğrulanmamış ödül) | Ödül müzeye verildi, ofise değil |

### Bağlama göre ton

| Bağlam | Ton | Örnek |
|--------|-----|-------|
| Proje künyesi | Yalnızca olgu | "Interior design project. 2.000 m². 2016." |
| Bölüm başlığı | Kısa, iddialı | "ONE SPACE. MULTIPLE DISCIPLINES." |
| Hakkımızda | Birinci çoğul, sakin | "We design the spaces technology lives in." |
| İletişim | Davet, satış değil | Uzun form yok, tek bir adres yeter |

---

## 6. Fotoğraf ve Görsel Dil

- Gerçek projeler. **Stok fotoğraf kullanılmaz** — ne kadar iyi olursa olsun,
  başkasının görseli stüdyonun işini zayıflatır.
- **Render kullanılır, ama künyesinde belirtilir.** Görselleştirme MON-IN için
  gizlenecek bir eksiklik değil, satılan bir üründür: kurucunun unvanı "Digital
  Artist", yetkinlik listesinde `VISUALIZATION` var ve katalog 360° VR turlarını
  ayrı bir hizmet olarak anlatıyor. Kural şudur: render göstermek serbesttir,
  yapılmış işmiş gibi göstermek değildir. Künyenin sonuna `Visualization.` eklenir.
- Mimari çerçeveleme: yapı tam olarak kadrajda, insan kalabalığı yok.
- Doğal ışık tercih edilir; gece çekimlerinde sıcak yapay ışık kabul edilir.
- Renk düzeltmesi nötr kalır. Filtre, vinyet ve ağır kontrast uygulanmaz.
- Her fotoğrafın künyesi vardır: etiket + proje adı. Künyesiz fotoğraf
  yayınlanmaz; künyesi bilinmiyorsa arşiv olarak işaretlenir.

### Hero rotasyonu

Açılış fotoğrafları `index.html` içindeki proje listesinden `hero:true`
işaretiyle seçilir. Kare başına 5,4 saniye, yatay kaydırma 9,5 saniye.
Rotasyona altıdan fazla kare konmaz — daha fazlası hem yükü artırır hem
döngüyü fark edilir kılar.

---

## 7. İsim

**MON-IN** iki parçadan oluşur:

- `MON` — Fransızca "benim"
- `IN` — hem **In**terior hem **In**telligence

Yani mekân ve teknoloji ikiliği markanın adında, kuruluşundan beri vardır.
Yeni bir konumlandırma anlatılırken bu gerçek kullanılır; kurgulanmış bir
kelime oyunu üretilmez. "Baştan beri buyduk, şimdi adını koyuyoruz" demek,
"yeni bir yöne gidiyoruz" demekten güçlüdür.

Yazım kuralı: her yerde tireli — `MON-IN`. Asla `MONIN` yazılmaz; küresel
dağıtımı olan Fransız şurup markası Monin ile karışır.

---

## Changelog

| Sürüm | Tarih | Değişiklik |
|-------|-------|------------|
| 1.0 | 2026-09-18 | İlk rehber. Değerler `index.html`'den doğrulandı, kontrast oranları ölçüldü. |
