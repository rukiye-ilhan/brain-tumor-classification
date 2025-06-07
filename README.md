# 🧠 Beyin Tümörü Sınıflandırma (Brain Tumor Classification)

Bu proje, beyin tümörlü ve tümörsüz MRI görüntülerini sınıflandırmak için derin öğrenme tabanlı bir model geliştirmeyi amaçlamaktadır. Görüntüler, CNN (Convolutional Neural Network) mimarisiyle analiz edilmiştir. Model, TensorFlow/Keras kütüphanesi kullanılarak sıfırdan oluşturulmuş ve başarıyla eğitilmiştir.

---

## 🎯 Proje Amacı

Bu çalışmanın temel amacı, MRI (Manyetik Rezonans Görüntüleme) görüntüleri üzerinde otomatik beyin tümörü tespiti yapabilen bir sınıflandırma sistemi geliştirmektir.

---

## 📁 Veri Kümesi

Veri kümesi iki sınıfa ayrılmıştır:

- `tumor_dataset/`: Beyin tümörü içeren MRI görüntüleri
- `no_tumor_dataset/`: Sağlıklı MRI görüntüleri

Tüm görseller `.jpg` formatındadır ve projede her biri 128x128 boyutuna yeniden boyutlandırılmıştır. Görüntüler RGB formatında olup, sadece `shape == (128, 128, 3)` olanlar modele dahil edilmiştir.

---

## 🧰 Kullanılan Kütüphaneler

- NumPy, Pandas
- TensorFlow, Keras
- Matplotlib, Seaborn
- PIL (Python Imaging Library)
- Scikit-learn

---

## 🧠 Model Mimarisi

Model, klasik bir CNN yapısını temel alır:

- 3 adet **Conv2D + MaxPooling2D** katmanı
- 1 adet **Flatten** katmanı
- 2 adet **Dense (Tam bağlantılı)** katman
- Son katmanda **sigmoid aktivasyon** (binary classification için)

**Model Özellikleri:**

- Kayıp fonksiyonu: `binary_crossentropy`  
- Optimizasyon algoritması: `adam`  
- Değerlendirme metriği: `accuracy`

---

## 🧪 Eğitim & Değerlendirme

- Görsellerin boyutu `(128, 128, 3)` olacak şekilde normalize edilmiştir (`data / 255.0`)
- Veri seti eğitim (%70) ve test (%30) olarak bölünmüştür.
- Eğitim süreci sonunda eğitim/test doğruluğu ve kaybı görselleştirilmiştir.
- Modelin başarımı şu metriklerle analiz edilmiştir:
  - **Doğruluk (Accuracy)**
  - **Karışıklık Matrisi (Confusion Matrix)**
  - **Sınıflandırma Raporu (Classification Report)**

---

## 📊 Sonuçlar

Model, MRI görüntüleri üzerinde beyin tümörü tespiti konusunda yüksek doğrulukla sınıflandırma yapabilmektedir. Eğitim/test performansı grafiklerle analiz edilmiş ve sınıflandırma başarı oranı oldukça yüksektir. Basit bir CNN mimarisiyle dahi etkili sonuçlar alınabileceği gösterilmiştir.

---

## 🚀 Nasıl Çalıştırılır?

### 1. Gerekli kütüphaneleri yükleyin:

```bash
pip install numpy pandas matplotlib seaborn pillow scikit-learn tensorflow
```

### 2. Notebook'u çalıştırın:

```bash
jupyter notebook brain_tumor_classification.ipynb
```
## 📌 Notlar

- Model sıfırdan oluşturulmuştur. Hazır mimariler (örneğin: VGG, ResNet) kullanılmamıştır.
- Görsellerin boyutu ve formatı kontrol edilerek temizlenmiştir.
- Rastgelelik etkisini azaltmak için sabit `random seed` kullanılmıştır.

👤 Geliştirici
Ad Soyad: [Rukiye İlhan]
İletişim: [ilhanxrukiye@gmail.com]


