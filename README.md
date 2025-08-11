# 🎯 Kural Tabanlı Sınıflandırma ile Potansiyel Müşteri Getirisi Hesaplama

📌 Bu proje, uluslararası bir oyun şirketinin müşteri verileri kullanılarak **level-based (seviye tabanlı)** yeni müşteri tanımları (**persona**) oluşturmayı, bu müşteri gruplarını segmentlere ayırmayı ve her segment için potansiyel getiri tahmini yapmayı amaçlamaktadır.  
Çalışmada, veri seti üzerinde **kural tabanlı segmentasyon** teknikleri uygulanmış, **fiyat analizleri** yapılmış ve sonuçlar **grafikler** ile görselleştirilmiştir.

💻 **Jupyter Notebook** formatında geliştirilmiş olup, veri analizi ve sınıflandırma adımlarını **adım adım** içermektedir.

---

## 📚 İçindekiler

- [📌 Proje Hakkında](#-proje-hakkında)  
- [🛠 Kullanılan Teknolojiler](#-kullanılan-teknolojiler)  
- [⚙️ Kurulum](#%EF%B8%8F-kurulum)  
- [🚀 Kullanım](#-kullanım)  
- [📊 Veri Seti](#-veri-seti)  
- [📈 Sonuçlar](#-sonuçlar)  
- [🔄 Çalışma Akışı](#-çalışma-akışı)   

---

## 📌 Proje Hakkında

Bu proje kapsamında:  

✅ Müşteri verilerinden **persona** tanımları oluşturulmuştur.  
✅ Her persona **segmentlere** ayrılmıştır.  
✅ Segment bazlı **ortalama gelir tahmini** yapılmıştır.  
✅ Sonuçlar **tablolar** ve **grafikler** ile sunulmuştur.

> 🔍 **Amaç:** Örneğin, Türkiye’den IOS kullanıcısı olan 25 yaşındaki bir erkek müşterinin şirkete ortalama ne kadar kazandıracağını tahmin etmek.

---

## 🛠 Kullanılan Teknolojiler

| Teknoloji | Açıklama |
|-----------|----------|
| **Python 3.x** | Ana programlama dili |
| **Jupyter Notebook** | Çalışma ortamı |
| **Pandas** | Veri analizi |
| **NumPy** | Sayısal hesaplamalar |
| **Matplotlib / Seaborn** | Veri görselleştirme |

---

## ⚙️ Kurulum

1️⃣ **Python** ve **Jupyter Notebook** bilgisayarınızda kurulu değilse yükleyin.  
2️⃣ Projeyi klonlayın veya indirin:  

```bash
git clone https://github.com/Memreu/Rule-Based-Classification-2.git
cd Rule-Based-Classification-2
```

3️⃣ Gerekli kütüphaneleri yükleyin:  

```bash
pip install pandas numpy matplotlib seaborn
```

---

## 🚀 Kullanım

💡 **Notebook dosyası** içerisinde adım adım kod blokları ve açıklamalar mevcuttur.  

1. `Rule-Based-Classification.ipynb` dosyasını Jupyter Notebook ile açın.  
2. Kod hücrelerini **sırasıyla çalıştırın**.  
3. Kendi verinizi kullanmak isterseniz veri yükleme adımındaki **dosya yolunu** değiştirin.  

---

## 📊 Veri Seti

📂 **Persona.csv** veri seti, uluslararası bir oyun şirketinin sattığı ürünlerin fiyatlarını ve bu ürünleri satın alan kullanıcıların bazı demografik bilgilerini içermektedir.  
Veri seti her satış işleminde oluşan kayıtlardan meydana gelir, bu nedenle **tekilleştirilmemiştir**.  

**Değişkenler:**  
- **PRICE:** Müşterinin harcama tutarı  
- **SOURCE:** Müşterinin bağlandığı cihaz türü  
- **SEX:** Müşterinin cinsiyeti  
- **COUNTRY:** Müşterinin ülkesi  
- **AGE:** Müşterinin yaşı  

---

## 📈 Sonuçlar

📌 Proje sonucunda:  

1. Veriler, **kural tabanlı sınıflandırma** ile segmentlere ayrıldı.  
2. Her segment için ortalama gelir tahminleri yapıldı.  
3. Sonuçlar **grafik** ve **tablo** formatında görselleştirildi.  

---

## 🔄 Çalışma Akışı

\`\`\`mermaid
flowchart TD
    A[Veri Seti Yükleme] --> B[Veri Ön İşleme]
    B --> C[Persona Oluşturma]
    C --> D[Segmentlere Ayırma]
    D --> E[Gelir Tahmini]
    E --> F[Sonuçların Görselleştirilmesi]
\`\`\`
