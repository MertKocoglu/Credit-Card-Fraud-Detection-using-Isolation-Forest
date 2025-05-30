

---

# 🕵️‍♀️ Credit Card Fraud Detection Using Unsupervised Learning

Bu proje, **gözetimsiz makine öğrenimi teknikleri** kullanarak kredi kartı işlemlerindeki dolandırıcılıkları tespit etmeyi amaçlamaktadır. Özellikle **Isolation Forest** ve **Local Outlier Factor (LOF)** algoritmaları kullanılarak normal ve anormal işlemler ayrıştırılmıştır.

## 📁 Veri Kümesi

Kullanılan veri seti: [`creditcard.csv`](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

* 284,807 işlem kaydı
* 30 özellik (V1–V28 PCA dönüşümlü), işlem zamanı, işlem miktarı ve hedef değişken: `Class`
* `Class` değişkeni:

  * `0` → Normal işlem
  * `1` → Dolandırıcılık işlemi

## 🔍 Proje Özeti

### 1. **Veri Keşfi & Görselleştirme**

* Sınıf dağılımı incelendi (Veri çok dengesiz: yalnızca %0.17'si dolandırıcılık).
* Saatlik işlem yoğunluğu görselleştirildi.
* Tüm öznitelikler için dolandırıcılık ve normal dağılımlar karşılaştırıldı.

### 2. **Öznitelik İşleme**

* `Time` ve `Amount` öznitelikleri PCA kullanılarak `V29` ve `V30` adında iki yeni bileşene dönüştürüldü.
* İstatistiksel anlamlı öznitelikler için Z-test uygulandı.
* Anlamlı olan öznitelikler seçilerek modelleme için kullanıldı.

### 3. **Modelleme**

#### Isolation Forest

* **Normal işlem tespiti doğruluğu:** 95.78%
* **Dolandırıcılık tespiti doğruluğu:** 86.38%

#### Local Outlier Factor (LOF)

* **Normal işlem tespiti doğruluğu:** 98.75%
* **Dolandırıcılık tespiti doğruluğu:** 23.58%

## 🛠 Kullanılan Kütüphaneler

* `pandas`, `numpy`, `matplotlib`, `seaborn`
* `sklearn`: PCA, IsolationForest, LocalOutlierFactor

## 📈 Sonuç

* **Isolation Forest**, dolandırıcılık tespiti konusunda **LOF'a göre daha başarılı** sonuçlar verdi.
* Verinin dengesiz yapısı nedeniyle gözetimsiz öğrenme yöntemleri, sınırlı ama değerli sonuçlar sundu.

## 🚀 Nasıl Çalıştırılır?

1. Bu repoyu klonlayın:

   ```bash
   git clone https://github.com/kullaniciadi/credit-card-fraud-unsupervised.git
   cd credit-card-fraud-unsupervised
   ```

2. Gerekli kütüphaneleri yükleyin:

   ```bash
   pip install -r requirements.txt
   ```

3. Notebook'u çalıştırın:

   ```bash
   jupyter notebook
   ```

## 📌 Notlar

* Projede **gözetimsiz öğrenme** teknikleri tercih edilmiştir, çünkü veride `Class=1` örnekleri çok azdır.
* Z-Test ile anlamlı özniteliklerin seçilmesi, model başarısını artırmada önemli rol oynamıştır.

## 🧠 Geliştirici Notları

Bu proje, sahte işlemlerin tespiti için klasik gözetimsiz öğrenme algoritmalarının potansiyelini araştırmak amacıyla hazırlanmıştır. Daha gelişmiş modeller (örneğin autoencoder veya deep SVDD) ile geliştirilebilir.

---
