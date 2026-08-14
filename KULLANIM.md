# Web Sitesi Şablonu — Kullanım Kılavuzu

Bu klasör, herhangi bir işletme için **yeniden kullanabileceğin temiz bir şablondur.**
Yapı, tasarım, renkler ve animasyonlar hazır — sadece **yazıları** ve **fotoğrafları**
değiştirince yeni bir işletme sitesi çıkar.

## Klasör içeriği
| Dosya | Ne işe yarar |
|---|---|
| `index.html` | Ana sayfa (hero dalga arka planı, 3B hizmet kartları, yukarı akan galeri, hakkımızda, yorumlar, iletişim + gömülü harita) |
| `galeri.html` | Immersive 3B kavisli galeri (ana sayfadaki "İmmersive Galeriyi Aç" butonu buraya gider) |
| `KULLANIM.md` | Bu dosya |

> `index.html` ve `galeri.html` **aynı klasörde** durmalı ki galeri butonu çalışsın.

## Yeni bir işletme için nasıl kullanılır?

**İki yol var:**

### Yol 1 — Claude'a yaptır (önerilen, hızlı)
1. Yeni işletme için **yeni bir GitHub deposu** aç.
2. Bu klasördeki `index.html` + `galeri.html`'i o depoya at.
3. İşletmenin fotoğraflarını da depoya yükle.
4. Claude'da yeni bir pencere aç ve **aşağıdaki HAZIR KOMUT'u** yapıştır.

### Yol 2 — Kendin değiştir
`index.html`'i bir metin düzenleyiciyle aç, aşağıdaki **köşeli parantezli** yerleri doldur,
`FOTO` placeholder görsellerini kendi fotoğraflarınla değiştir. (Fotoğraf gömme işi teknik
olduğu için Yol 1 çok daha kolay.)

---

## 📋 Değiştirilecek yer tutucular
Şablonda şu işaretler geçer — hepsi yeni işletmeye göre doldurulacak:

| Yer tutucu | Ne yazılacak |
|---|---|
| `[İŞLETME ADI]` | İşletmenin adı |
| `[ALT BAŞLIK]` | Logo altı küçük yazı (ör. sektör/slogan) |
| `[TELEFON]` | Telefon numarası (görünen) |
| `90XXXXXXXXXX` | WhatsApp numarası (wa.me linkleri için, ülke koduyla) |
| `kullanici.adi` | Instagram kullanıcı adı |
| `[BÖLGE]` | Semt/bölge (ör. Kadıköy) |
| `[ADRES]`, `[ADRES / İL]`, `[İLÇE / İL]` | Açık adres satırları |
| `[HARITA-ADRESI]` | Haritada aranacak adres (Google Maps için) |
| `FOTO` (pastel kutular) | Gerçek fotoğraflar (galeri akışı, hizmet görselleri, hakkımızda) |
| **Logo** | İşletmenin logosu (varsa) |

Ayrıca gerekiyorsa: hizmet isimleri/açıklamaları, hero başlığı, yorumlar, çalışma saatleri
ve renk teması da değiştirilebilir.

### 🌟 Logo nasıl yerleştirilir?
İşletmenin logosu varsa (depoya yükle), **4 yere** konur — hepsinde **tam logo** (kırpma yok):
- **Hakkımızda** bölümündeki büyük görsel alanı → tam logo
- **Menü (üst bar)** ve **footer**'daki ikon → tam logo. Yanındaki `[İŞLETME ADI]` yazısı **kalır** (logo + isim birlikte). CSS'te `.brand-logo` sınıfı hazır; `.crown` ikonunun yerine `<img class="brand-logo" ...>` gelir.
- **Favicon** (tarayıcı sekmesi ikonu) → aynı logo (`<link rel="icon" ...>`).

---

## 🤖 HAZIR KOMUT (yeni Claude oturumuna yapıştır)

```
Elimde hazır bir web sitesi şablonu var (bu depodaki index.html + galeri.html).
Şablonun YAPISINI, TASARIMINI, RENK/animasyon sistemini AYNEN koru — hiçbir yapıyı bozma.
Sadece içeriği (yazılar) ve fotoğrafları yeni işletmeye göre değiştir.

İşletme bilgileri:
- İşletme adı:
- Sektör:
- Alt başlık/slogan:
- Telefon / WhatsApp:
- Instagram:
- Adres (semt / il):
- Çalışma saatleri:
- Hizmetler (isim + kısa açıklama):
- Renk tercihi (isteğe bağlı):

Fotoğrafları ve logoyu depoya yükleyeceğim. Şablondaki [KÖŞELİ PARANTEZ] yerlerini doldur,
"FOTO" placeholder görsellerini benim fotoğraflarımla değiştir (küçültüp dosyaya göm).
Logo varsa: tam halini (kırpmadan) Hakkımızda'ya, menü ikonuna, footer'a ve favicon'a
koy; menü/footer'da isim yazısı logonun yanında kalsın. Sonra commit'leyip push et.
```

Bilgileri ve fotoğrafları verdiğinde, Claude yer tutucuları doldurur, görselleri yerleştirir
ve siteyi hazır hale getirir.

---

## Notlar
- **Her işletme için ayrı GitHub deposu** aç (karışmasın, her müşteri kendi sitesi).
- Fotoğrafları Claude'un işlemesi için **depoya yükle** (sohbete yapıştırmak yetmez).
- Site bitince **yayına al** (GitHub Pages / Netlify) → müşteriye tek link ver.
- Renkleri değiştirmek çok kolay: `index.html` içindeki `:root` renk değişkenleri (ör.
  `--pink`, `--purple`, `--aqua`) değişince tüm sayfa o renklere döner.
