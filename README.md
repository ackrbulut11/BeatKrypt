# BeatKrypt 🫀🛡️

BeatKrypt, giyilebilir cihazlar (akıllı saatler) için geliştirilmiş, **Derin Öğrenme** tabanlı bir **Biyometrik Kimlik Doğrulama ve Çok Aşamalı Doğrulama (MFA)** güvenlik katmanıdır. 

Sistem, geleneksel statik şifreler yerine kullanıcının benzersiz EKG (Elektrokardiyogram) sinyal morfolojisini analiz eder. EKG'deki zamansal dalgalanmaları ve nabız değişkenliklerini tolere edebilmek adına, statik bir eşleştirme yerine **1D-CNN tabanlı Siyam Ağları (Siamese Network)** kullanarak iki farklı EKG sinyalinin aynı kalbe ait olma olasılığını (embedding mesafesini) ölçer.

---

## 🚀 Öne Çıkan Özellikler

*   **Tek Kanal (Lead I) Optimizasyonu:** Akıllı saat senaryolarını simüle etmek adına, 12 kanallı EKG verisinden sadece Sağ Kol - Sol Kol voltaj farkını içeren **Lead I** kanalı kullanılmıştır.
*   **Edge AI & Giyilebilir Uyumluluğu:** Model, düşük kaynaklı ve pilli cihazlarda sıfır gecikmeyle çalışabilmesi için **100Hz** örnekleme frekansına sahip verilerle eğitilmiş ve **ONNX** formatına dönüştürülecek şekilde tasarlanmıştır.
*   **Kriptografik Güvenlik (MFA):** Siyam ağının ürettiği doğrulama skoru, cihaz lokalindeki hassas verilerin şifrelenmesini (AES-256) tetikleyen bir MFA katmanı olarak çalışır.

---

## 📂 Proje Dizin Yapısı

```text
BeatKrypt/
│
├── .gitignore               # Geçici ve büyük veri dosyalarını Git dışında tutar
├── README.md                # Proje ana dökümantasyonu
├── requirements.txt         # Gerekli Python kütüphaneleri listesi
│
├── data/                    # PhysioNet veri seti ve filtreleme CSV'leri (Git tarafından yoksayılır)
│   
├── research/                # Ar-Ge ve Jupyter Notebook çalışmaları
│
├── src/                     # Üretim (Production) aşaması modüler kodları
│
└── models/                  # Eğitilmiş model çıktıları
