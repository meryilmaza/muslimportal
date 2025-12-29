# 🚀 GitHub'a Yükleme ve Deploy Rehberi

Bu rehber, İslami Portal projesini GitHub'a yükleme ve GitHub Pages ile yayınlama adımlarını içerir.

---

## 📋 Ön Hazırlık

### Gereksinimler:
- ✅ GitHub hesabı (ücretsiz)
- ✅ Tüm HTML dosyaları (18 adet)
- ✅ README.md dosyası
- ⏳ Git kurulumu (komut satırı için - opsiyonel)

---

## 🎯 Yöntem 1: Web Arayüzü ile (En Kolay) ⭐

### Adım 1: Repository Oluştur

1. **GitHub.com'a git**
   - Tarayıcıda: https://github.com

2. **Giriş yap**
   - Kullanıcı adı ve şifre ile

3. **Yeni Repo Oluştur**
   - Sağ üstte **"+"** işaretine tıkla
   - **"New repository"** seç

4. **Repository Ayarları:**
   ```
   Repository name: islami-portal
   Description: Kapsamlı İslami Web Uygulaması
   ✅ Public (herkese açık)
   ✅ Add a README file (işaretleme)
   .gitignore: Seçme
   License: MIT (önerilen)
   ```

5. **Create repository** butonuna tıkla

---

### Adım 2: Dosyaları Yükle

1. **Yeni oluşturulan repo'da**
   - "uploading an existing file" linkine tıkla
   - VEYA "Add file" → "Upload files"

2. **Dosyaları Ekle:**
   
   Sürükle-bırak ile tüm dosyaları ekle:
   ```
   ✅ index.html
   ✅ kuran-with-fonts.html
   ✅ tesbih.html
   ✅ kible.html
   ✅ dualar.html
   ✅ esmaul-husna.html
   ✅ hadis.html
   ✅ fikih.html
   ✅ takvim.html
   ✅ ramazan.html
   ✅ kandiller.html
   ✅ cami-bulucu.html
   ✅ sosyal.html
   ✅ videolar.html
   ✅ ibadet-takip.html
   ✅ rozetler.html
   ✅ hatirlaticilar.html
   ✅ ayarlar.html
   ✅ README.md (varsa değiştir)
   ✅ GELECEK-OZELLIKLER.md
   ```

3. **Commit Mesajı:**
   ```
   İslami Portal - İlk yükleme
   
   18 sayfa eklendi:
   - Kuran okuma
   - Pratik araçlar (3)
   - Eğitim (3)
   - Özel günler (3)
   - Topluluk (3)
   - İbadet takibi (3)
   - Ayarlar (1)
   ```

4. **Commit changes** butonuna tıkla

✅ Dosyalar yüklendi!

---

### Adım 3: GitHub Pages Aktif Et

1. **Repository'de Settings'e git**
   - Repo ana sayfası → **Settings** (üstte)

2. **Pages bölümünü bul**
   - Sol menüden **Pages** seç

3. **Source Ayarla:**
   ```
   Source: Deploy from a branch
   Branch: main
   Folder: / (root)
   ```

4. **Save** butonuna tıkla

5. **Bekle** (2-3 dakika)
   - GitHub sayfanızı oluşturuyor

6. **Yenile** (F5)
   - "Your site is published at..." mesajı görünecek

7. **Link'i Kopyala:**
   ```
   https://your-username.github.io/islami-portal/
   ```

🎉 **Siten yayında!**

---

## 🖥️ Yöntem 2: Git Komut Satırı ile (İleri Seviye)

### Adım 1: Git Kurulumu

**Windows:**
```bash
# Git for Windows indir
https://git-scm.com/download/win
```

**Mac:**
```bash
# Homebrew ile
brew install git
```

**Linux:**
```bash
# Ubuntu/Debian
sudo apt-get install git

# Fedora
sudo dnf install git
```

---

### Adım 2: Git Yapılandırma

```bash
# İsim ayarla
git config --global user.name "Adınız Soyadınız"

# Email ayarla
git config --global user.email "email@example.com"

# Kontrol et
git config --list
```

---

### Adım 3: GitHub'da Repo Oluştur

1. GitHub.com → New repository
2. İsim: `islami-portal`
3. Public, Add README yok
4. Create repository

---

### Adım 4: Yerel Klasör Hazırla

```bash
# Proje klasörüne git
cd /path/to/your/project

# VEYA yeni klasör oluştur
mkdir islami-portal
cd islami-portal

# Tüm HTML dosyalarını bu klasöre kopyala
```

---

### Adım 5: Git ile Yükle

```bash
# Git başlat
git init

# Tüm dosyaları ekle
git add .

# Commit yap
git commit -m "İslami Portal - İlk commit

18 sayfa eklendi:
- Kuran okuma
- Pratik araçlar
- Eğitim içerikleri
- İbadet takibi
- Topluluk özellikleri"

# Ana branch'i main yap
git branch -M main

# Remote repo ekle (your-username'i değiştir!)
git remote add origin https://github.com/your-username/islami-portal.git

# Push et
git push -u origin main
```

**İlk push'ta GitHub şifreniz istenecek!**

---

### Adım 6: GitHub Pages Aktif Et

```bash
# Tarayıcıda repo'yu aç
https://github.com/your-username/islami-portal

# Settings → Pages
# Source: main, Folder: /
# Save
```

---

## 🔄 Güncelleme Nasıl Yapılır?

### Web Arayüzü ile:

1. GitHub'da dosyaya git
2. **Kalem** ikonuna tıkla (Edit)
3. Değişiklikleri yap
4. **Commit changes**

### Git ile:

```bash
# Değişiklikleri yap (dosyaları düzenle)

# Değişiklikleri ekle
git add .

# Commit yap
git commit -m "Özellik eklendi: XYZ"

# Push et
git push
```

⏰ **GitHub Pages otomatik güncellenecek (1-2 dakika)**

---

## 🔧 Sorun Giderme

### Problem: "Site yayınlanmıyor"

**Çözüm 1:** Bekle
- 5 dakika bekle
- Sayfayı yenile (F5)

**Çözüm 2:** Kontrol et
- Settings → Pages
- Source: main olmalı
- Folder: / olmalı

**Çözüm 3:** index.html kontrolü
- Dosya adı: `index.html` (küçük harf)
- Root dizinde olmalı

---

### Problem: "404 Not Found"

**Çözüm:**
- Link doğru mu? `https://username.github.io/repo-name/`
- index.html var mı?
- 5 dakika bekle

---

### Problem: "CSS/JS çalışmıyor"

**Çözüm:**
- Tüm path'ler relative olmalı
- ✅ `href="style.css"` 
- ❌ `href="/style.css"`
- ❌ `href="C:/style.css"`

---

### Problem: "API çalışmıyor"

**Çözüm:**
- HTTPS kullanılıyor mu?
- CORS sorunu olabilir
- Console'da hata kontrolü (F12)

---

## 📱 Custom Domain Bağlama (Opsiyonel)

Kendi domain'iniz varsa (örn: islamiportal.com):

1. **Domain sağlayıcınızda:**
   ```
   A Record: 185.199.108.153
   A Record: 185.199.109.153
   A Record: 185.199.110.153
   A Record: 185.199.111.153
   
   CNAME: www → your-username.github.io
   ```

2. **GitHub Settings → Pages:**
   ```
   Custom domain: islamiportal.com
   ✅ Enforce HTTPS
   ```

3. **Bekle:** DNS yayılması 24-48 saat

---

## 🎨 README.md Güncelleme

README'de değiştir:

```markdown
# Linkler
🔗 **Canlı Demo:** https://YOUR-USERNAME.github.io/islami-portal/

# Ekran Görüntüleri
(Ekran görüntüsü ekle)

# İstatistikler
- ⭐ GitHub Stars: [Sayı]
- 🍴 Forks: [Sayı]
- 👀 Views: [Sayı]
```

---

## 📊 GitHub Analytics

### Ziyaretçi İstatistikleri:

**Repository'de:**
- **Insights** → **Traffic**
  - Views (görüntüleme)
  - Unique visitors (benzersiz ziyaretçi)
  - Clones (klonlama)

### Star, Fork, Watch:

- **Stars:** Beğeni sayısı
- **Forks:** Kopyalama sayısı
- **Watch:** Takipçi sayısı

---

## 🔐 Repository Ayarları

### Public/Private:

**Public** (Önerilen):
- ✅ Herkes görebilir
- ✅ GitHub Pages ücretsiz
- ✅ Topluluk katkısı

**Private:**
- ❌ Sadece siz görebilirsiniz
- ❌ GitHub Pages ücretli (Pro)

---

### Lisans:

**MIT License** (Önerilen):
- ✅ Açık kaynak
- ✅ Serbest kullanım
- ✅ Değiştirme izni

---

## 🎯 SEO İpuçları

### README.md'de:

```markdown
## 🏷️ Keywords
İslami portal, namaz vakitleri, kuran okuma, 
dijital tesbih, hicri takvim, ramazan, 
kandil gecesi, dua koleksiyonu

## 🌍 Languages
Türkçe | Turkish | İslami İçerik
```

### Meta Tags (HTML):

Her sayfaya ekle:
```html
<meta name="description" content="Kapsamlı İslami portal">
<meta name="keywords" content="namaz, kuran, islam">
<meta name="author" content="Your Name">
```

---

## 📢 Paylaşım

### Sosyal Medya:

**Twitter:**
```
🕌 İslami Portal'ı yayınladım!

✅ 18 sayfa
✅ Kuran okuma
✅ Namaz vakitleri
✅ İbadet takibi

🔗 https://your-username.github.io/islami-portal/

#İslam #Namaz #Kuran #OpenSource
```

**LinkedIn/Facebook:**
```
Yeni projem: İslami Portal 🕌

Modern, kullanıcı dostu, kapsamlı bir İslami web uygulaması.

Özellikler:
• Kuran okuma (5 hat)
• Namaz vakitleri
• İbadet takip sistemi
• Eğitim içerikleri
• ve daha fazlası...

Tamamen ücretsiz ve açık kaynak!

Link: [GitHub Pages URL]
```

---

## 🤝 Katkıda Bulunma

### CONTRIBUTING.md oluştur:

```markdown
# Katkıda Bulunma Rehberi

1. Fork edin
2. Branch oluşturun (`git checkout -b feature/YeniOzellik`)
3. Commit edin (`git commit -m 'Yeni özellik eklendi'`)
4. Push edin (`git push origin feature/YeniOzellik`)
5. Pull Request açın

## Kod Standartları
- HTML5 semantik taglar
- CSS3 modern özellikler
- Vanilla JavaScript (framework yok)
- Responsive tasarım
- Yorumlu kod
```

---

## 📧 Destek

### Issues:
```
Sorun bildirmek için:
1. Issues sekmesi
2. New issue
3. Detaylı açıklama
4. Submit
```

### Discussions:
```
Tartışma için:
1. Discussions sekmesi
2. New discussion
3. Kategori seç
4. Başlat
```

---

## ✅ Checklist

Deploy öncesi kontrol:

- [ ] Tüm HTML dosyaları yüklendi
- [ ] README.md güncellendi
- [ ] LICENSE eklendi
- [ ] index.html root'ta
- [ ] Linkler çalışıyor
- [ ] Responsive test edildi
- [ ] GitHub Pages aktif
- [ ] Custom domain bağlandı (opsiyonel)
- [ ] Sosyal medyada paylaşıldı

---

## 🎉 Tebrikler!

Siteniz artık canlı! 🚀

**Link:** `https://your-username.github.io/islami-portal/`

**Paylaş, yıldız ver, katkıda bulun!** ⭐

---

**Hayırlı Kullanımlar! 🕌**

*Son Güncelleme: 30 Aralık 2024*
