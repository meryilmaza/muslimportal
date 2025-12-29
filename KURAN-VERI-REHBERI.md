# Kuran-ı Kerim Veri İndirme Rehberi

## Gerekli Veriler

Kuran okuma sayfanız için aşağıdaki verilere ihtiyacınız var:

### 1. Kuran Metni (Osmanlı Hatlı)
- API: https://api.alquran.cloud/v1/quran/quran-uthmani
- Bu API Osmanlı stili (Uthmani) yazım şeklini içerir

### 2. Elmalılı Hamdi Yazır Meali
- API: https://api.alquran.cloud/v1/quran/tr.yazir
- Türkçe meal

### 3. Sayfa Bilgileri
- API: https://api.alquran.cloud/v1/page/{sayfa_no}
- Mushaf sayfa düzeni için

## İndirme Adımları

### Yöntem 1: Tarayıcıdan İndirme

1. Tarayıcınızda şu URL'leri açın:
   - https://api.alquran.cloud/v1/quran/quran-uthmani
   - https://api.alquran.cloud/v1/quran/tr.yazir

2. Sayfada görünen JSON verisini kopyalayın

3. `quran-uthmani.json` ve `quran-meal.json` olarak kaydedin

### Yöntem 2: Terminal/CMD ile İndirme

```bash
# Kuran metni (Osmanlı hatlı)
curl -o quran-uthmani.json "https://api.alquran.cloud/v1/quran/quran-uthmani"

# Elmalılı Hamdi Yazır meali
curl -o quran-meal.json "https://api.alquran.cloud/v1/quran/tr.yazir"
```

### Yöntem 3: Python ile İndirme

```python
import requests
import json

# Kuran metni
response1 = requests.get('https://api.alquran.cloud/v1/quran/quran-uthmani')
with open('quran-uthmani.json', 'w', encoding='utf-8') as f:
    json.dump(response1.json(), f, ensure_ascii=False, indent=2)

# Meal
response2 = requests.get('https://api.alquran.cloud/v1/quran/tr.yazir')
with open('quran-meal.json', 'w', encoding='utf-8') as f:
    json.dump(response2.json(), f, ensure_ascii=False, indent=2)

print("İndirme tamamlandı!")
```

## Dosya Yapısı

İndirilen dosyaları şu şekilde organize edin:

```
kuran-okuma/
├── index.html (kuran-okuma.html)
├── data/
│   ├── quran-uthmani.json
│   ├── quran-meal.json
│   └── page-info.json
└── README.md
```

## Veri Entegrasyonu

HTML dosyanıza JSON verilerini şu şekilde ekleyin:

```javascript
// Verileri yükle
fetch('data/quran-uthmani.json')
    .then(response => response.json())
    .then(data => {
        // Arapça metin
        const arabicData = data.data.surahs;
        
        fetch('data/quran-meal.json')
            .then(response => response.json())
            .then(mealData => {
                // Türkçe meal
                const translationData = mealData.data.surahs;
                
                // Verileri birleştir ve göster
                loadQuranData(arabicData, translationData);
            });
    });
```

## Alternatif Kaynaklar

Eğer yukarıdaki API çalışmazsa:

1. **Quran.com API**
   - https://api.quran.com/api/v4/quran/verses/uthmani
   
2. **Tanzil.net**
   - https://tanzil.net/docs/download
   
3. **IslamicFinder**
   - https://www.islamicfinder.org/api/

## Not

- Verileri indirdikten sonra `kuran-okuma.html` dosyasındaki `quranData` objesi içindeki örnek verileri silin
- Gerçek JSON verilerini JavaScript ile yükleyin
- Tüm 114 sure ve 604 sayfayı destekler

## İletişim

Herhangi bir sorun olursa:
- API dokümantasyonu: https://alquran.cloud/api
- Sure bilgileri için: https://api.alquran.cloud/v1/surah
