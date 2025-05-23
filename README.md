# 📊 Banka Müşteri Yanıt Tahmini Projesi

## 📌 Giriş

Bu proje, bir bankanın gerçekleştirdiği telefonla pazarlama kampanyalarında müşterilerin vadeli mevduat hesabı açıp açmayacaklarını tahmin etmeyi amaçlamaktadır. Tahmin modeli sayesinde:

- Pazarlama kaynaklarının verimli kullanımı
- Doğru müşteri segmentlerine ulaşım
- Müşteri deneyiminin iyileştirilmesi
- Kampanya maliyetlerinin azaltılması

hedeflenmiştir.

---

## 🧾 Kullanılan Veri Seti

- **Kaynak:** [UCI Machine Learning Repository - Bank Marketing Dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
- **Gözlem Sayısı:** 20.000
- **Özellik Sayısı:** 21
- **Dönem:** Mayıs 2008 - Kasım 2010

Veri seti; demografik bilgiler, ekonomik değişkenler ve kampanya geçmişi gibi verilerden oluşmaktadır.

---

## 🛠 Kullanılan Yöntemler ve Modeller

### 🔍 Veri Ön İşleme

- Eksik veri kontrolü
- Kategorik değişkenlerin dönüştürülmesi
- Öznitelik ölçekleme

### 🧠 Uygulanan Modeller

- Random Forest
- XGBoost

Her modelde:

- Hiperparametre optimizasyonu (RandomizedSearchCV)
- Ağırlıklandırma (class_weight, scale_pos_weight)
- Eşik değeri ayarlamaları

### 📈 Değerlendirme Metrikleri

- Accuracy, Precision, Recall, F1-Score
- ROC AUC
- Karmaşıklık Matrisi
- Özellik Önemi Grafikleri

---

## 📊 Metrikler ve Sonuçlar

Proje kapsamında farklı modeller denenmiş ve aşağıdaki metrikler elde edilmiştir:

| Model                   | F1-Score (Evet) | F1-Score (Hayır) | ROC-AUC  |
|------------------------|-----------------|------------------|----------|
| Random Forest           | 0.95            | 0.50             | 0.945009 |
| XGBoost                 | 0.93            | 0.63             | 0.942918 |
| En İyi Random Forest    | 0.95            | 0.63             | 0.944916 |
| Ağırlıklandırılmış RF   | 0.94            | 0.63             | 0.945009 |
| Final RF (Eşik 0.6)     | 0.94            | 0.64             | 0.944916 |

- **En başarılı model:** Final Random Forest (Eşik 0.6) modeli, `0.94` F1-score (Evet), `0.64` F1-score (Hayır) ve `0.9449` ROC-AUC değeri ile öne çıkmaktadır.
- **En önemli 5 özellik:** `duration`, `campaign`, `pdays`, `emp.var.rate`, `month`

---

## ✅ Sonuç ve Gelecek Çalışmalar

Bu proje, sınıflandırma algoritmaları ile müşteri davranışlarının tahmin edilebileceğini göstermektedir. Gelecekte bu projeye;

- Streamlit ile kullanıcı arayüzü (UI) eklenmesi
- Gerçek zamanlı veri akışı ile modelin güncellenmesi
- Daha büyük ve güncel veri setleri ile yeniden eğitilmesi

gibi geliştirmeler yapılabilir.

---

## 🔗 Linkler

- 📘 [Kaggle Notebook - Tahmin Modeli](https://www.kaggle.com/code/busradeveci/bank-customer-response-prediction)
- 📂 [Veri Seti Kaynağı](https://archive.ics.uci.edu/ml/datasets/bank+marketing)

---
