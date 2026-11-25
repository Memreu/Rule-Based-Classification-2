# Persona Bazlı Kural Tabanlı Sınıflandırma

Miuul bootcamp'inde yaptığım ikinci kural tabanlı sınıflandırma çalışması. Bu kez veri, uluslararası bir oyun şirketinin satış kayıtlarından oluşuyor ve amaç müşterileri ülke, cihaz, cinsiyet ve yaş grubuna göre "persona"lara ayırıp her personanın şirkete ortalama ne kadar kazandırdığını bulmak. Görevdeki örnek soru: Türkiye'den iOS kullanan 25 yaşında bir erkek kullanıcı ortalama ne kadar getirir?

## Veri

`persona.csv` dosyası bootcamp tarafından verildi. 5.000 satır ve 5 değişkenden oluşuyor: PRICE (harcama), SOURCE (android/ios), SEX, COUNTRY ve AGE. Her satır bir satış işlemi olduğu için tablo tekilleştirilmemiş; aynı özelliklere sahip bir kullanıcı birden fazla kez görünebiliyor. Fiyat aslında sürekli değil, yalnızca 6 farklı değer alıyor (9, 19, 29, 39, 49, 59) ve ortalaması 34.13. Satışların 2.065'i ABD'den, 2.974'ü Android cihazlardan geliyor.

## Nasıl ilerledim

- Önce ülke, cihaz ve fiyat kırılımlarında frekanslara ve ortalamalara baktım.
- COUNTRY, SOURCE, SEX, AGE kırılımında ortalama fiyatı hesaplayıp azalan sırada sıraladım.
- Yaşı 0_18, 19_23, 24_30, 31_40 ve 41_70 olmak üzere beş gruba ayırdım.
- Bu değişkenleri birleştirerek `TUR_ANDROID_FEMALE_31_40` gibi persona tanımları oluşturdum ve her persona için ortalama fiyatı aldım.
- Ortalamaları `qcut` ile dört çeyreğe bölüp D, C, B, A segmentlerini atadım.

## Sonuçlar

Veride 109 farklı persona oluştu. Segmentlerin ortalama getirileri D için 29.21, C için 33.51, B için 35.00 ve A için 38.69. Segmentler arasındaki fark çok büyük değil; bunun bir nedeni fiyatın zaten dar ve kesikli bir aralıkta olması.

Denediğim iki yeni kullanıcı örneğinde `TUR_ANDROID_FEMALE_31_40` A segmentine düştü (beklenen ortalama 41.83), `FRA_IOS_FEMALE_31_40` ise C segmentine (32.82).

Gezinomi çalışmasına göre burada dikkatimi çeken nokta, olası 120 kombinasyondan yalnızca 109'unun veride bulunması oldu. Yani bazı yeni kullanıcılar için hiç tahmin üretilemiyor; notebook bu durumda "veri bulunamadı" diyor. Bunun yanında persona ortalamaları, alt gruptaki ortalamaların tekrar ortalaması alınarak hesaplandığı için gözlem sayısıyla ağırlıklandırılmış değil.

## Çalıştırmak için

```bash
pip install -r requirements.txt
jupyter notebook Rule-Based-Classification.ipynb
```

İleride persona ortalamalarını doğrudan ham veriden ağırlıklı olarak hesaplamak ve veride olmayan kombinasyonlar için bir üst seviyeye (örneğin yalnızca ülke ve cihaz) geri dönen basit bir kural eklemek istiyorum.
