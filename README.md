# Ərkivan Restoran — Sayt Təlimatı

## 📁 Fayl Strukturu

```
erkivan-website/
├── index.html        ← Əsas sayt faylı
├── menu.pdf          ← Menyu PDF
└── images/           ← Bütün şəkillər bu qovluqda olmalıdır
    ├── photo_xxx.jpg
    └── ...
```

> ⚠️ `index.html`, `menu.pdf` və `images/` qovluğu həmişə **eyni yerdə** olmalıdır.

---

## 🌐 Saytı GitHub Pages-ə Yükləmək

1. GitHub-da yeni repo yarat (məs: `erkivan-website`)
2. `index.html`, `menu.pdf` və `images/` qovluğunu repoya yüklə
3. **Settings → Pages → Branch: main → Save**
4. Bir neçə dəqiqə sonra sayt bu ünvanda açılır:
   ```
   https://sənin_adın.github.io/erkivan-website/
   ```

---

## ✏️ Tez-tez Dəyişdirilən Yerlər

### 📞 Telefon nömrəsini dəyişmək
`index.html`-də axtarın: `+994 10 311 85 05`
Hər yerdə eyni nömrəni yeniləyin.

### 📸 Şəkilləri dəyişmək
| Yer | Sətir | İzah |
|-----|-------|------|
| Hero arxa fon | ~248 | Tam ekran şəkil |
| Haqqımızda | ~654 | Sol tərəfdəki şəkil |
| Rezervasiya | ~1034 | Formanın yanındakı şəkil |
| Qalereya | ~1949–1998 | 12 ədəd şəkil |
| Lightbox siyahısı | ~1370–1382 | Qalereya ilə eyni sırada olmalıdır |

### 🍽️ Menyuya yemək əlavə etmək
Müvafiq kateqoriyanı tapın, bu bloku kopyalayıb yeni yeməyi yazın:
```html
<div class="menu-item">
  <span class="menu-item-name">Yemək adı</span>
  <span class="menu-item-price">X.XX ₼</span>
</div>
```

### 🍽️ Menyudan yemək silmək
Həmin `<div class="menu-item">...</div>` blokunu tamamilə silin.

### 💰 Qiymət dəyişmək
`menu-item-price` içindəki rəqəmi dəyişin:
```html
<span class="menu-item-price">12.00 ₼</span>
```

### 🖼️ Qalereyaya şəkil əlavə etmək
**1-ci yer** — gallery-item siyahısına əlavə edin (son şəkilin ardından):
```html
<div class="gallery-item" onclick="openLb(12)">
  <img src="images/yeni_sekil.jpg" alt="Ərkivan" loading="lazy" />
</div>
```
**2-ci yer** — Lightbox siyahısına da əlavə edin (eyni sırada):
```js
'images/yeni_sekil.jpg',
```

---

## 📅 Rezervasiya Sistemi

İstifadəçi formu doldurandа **WhatsApp avtomatik açılır**, bütün məlumatlar (ad, tarix, nəfər, telefon) artıq yazılmış olur. Siz sadəcə **Göndər** basırsınız.

### WhatsApp nömrəsini dəyişmək
JS bölməsində bu sabitin dəyərini yeniləyin:
```js
const WHATSAPP_NUMBER = '994103118505';
```

### EmailJS əlavə etmək (istəyə görə)
[emailjs.com](https://emailjs.com) saytında qeydiyyatdan keçin, sonra bu 3 sabitin dəyərini yazın:
```js
const EMAILJS_PUBLIC_KEY  = 'buraya_yazin';
const EMAILJS_SERVICE_ID  = 'buraya_yazin';
const EMAILJS_TEMPLATE_ID = 'buraya_yazin';
```
Email şablonunda bu dəyişənləri istifadə edin:
`{{ad_soyad}}`, `{{telefon}}`, `{{tarix}}`, `{{saat}}`, `{{nefer}}`, `{{qeyd}}`

---

## 🌍 Çatdırılma Bölməsini Doldurmaq

Hazırda "Tezliklə" yazır. Hazır olanda JS-dəki `translations` obyektində bu açarları yeniləyin:
```js
// az:
delivery_desc: 'Yeni mətn...',
// en:
delivery_desc: 'New text...',
// ru:
delivery_desc: 'Новый текст...',
```

---

## 🎨 Rəngləri Dəyişmək

CSS-in əvvəlindəki `:root` blokunda dəyişin:
```css
:root {
  --gold:  #C9A84C;   ← qızılı rəng
  --dark:  #0F0C08;   ← arxa fon
  --cream: #F0E8D5;   ← mətn rəngi
}
```

---

## 📋 Əlaqə Məlumatları

| | |
|---|---|
| **Telefon** | +994 10 311 85 05 |
| **Email** | erkivan.restoran@gmail.com |
| **Instagram** | @erkivan.restoran |
| **Ünvan** | 1 Niyazi küçəsi, Sumqayıt 5000 |
| **WhatsApp** | +994 10 311 85 05 |
