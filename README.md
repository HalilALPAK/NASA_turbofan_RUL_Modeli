# 🚁 NASA Turbofan Motor RUL Tahmini - CNN+LSTM Hibrit Modeli

Bu proje, NASA CMaps dataset'ini kullanarak turbofan motorlarının **Remaining Useful Life (RUL)** tahminini yapan gelişmiş bir makine öğrenmesi uygulamasıdır. Proje, **Convolutional Neural Network (CNN)** ve **Long Short-Term Memory (LSTM)** hibrit mimarisini kullanarak zaman serisi verilerinden RUL tahmini yapmaktadır.

## 📋 Proje Özeti

### 🎯 Amaç

- Turbofan motorlarının kalan kullanım ömrünü (RUL) tahmin etmek
- CNN+LSTM hibrit yaklaşımı ile zaman serisi analizi yapmak
- Motor arızalarını önceden tespit ederek bakım planlaması yapmak

### 📊 Veri Seti

- **NASA CMaps FD001 Dataset**
- **Eğitim Verisi**: 20,631 satır (100 motor)
- **Test Verisi**: 13,096 satır (100 motor)
- **Özellik Sayısı**: 26 (17 sensör verisi seçildi)
- **Sekans Uzunluğu**: 30 zaman adımı

## 🧠 Model Mimarisi

### CNN+LSTM Hibrit Yaklaşımı

```
Input Layer (30, 17)
    ↓
Conv1D Layer (64 filters, kernel_size=3)
    ↓
LSTM Layer (50 units)
    ↓
Dense Layer (32 units)
    ↓
Output Layer (1 unit - RUL)
```

### 🔧 Teknik Detaylar

- **Framework**: TensorFlow/Keras
- **Optimizer**: Adam
- **Loss Function**: Mean Squared Error (MSE)
- **Activation**: ReLU, Tanh
- **Regularization**: Dropout, Early Stopping

## 📁 Dosya Yapısı

```
nasa/
├── CMaps/                    # NASA dataset dosyaları
│   ├── train_FD001.txt      # Eğitim verisi
│   ├── test_FD001.txt       # Test verisi
│   ├── RUL_FD001.txt        # Gerçek RUL değerleri
│   └── readme.txt           # Dataset açıklaması
├── nasa.ipynb               # Ana analiz ve model geliştirme
├── best.ipynb               # Kaydedilen model test dosyası
├── best_model.h5            # Eğitilmiş CNN+LSTM modeli
└── README.md                # Bu dosya
```

## 🚀 Kullanım

### 1. Gereksinimler

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn
```

### 2. Model Eğitimi

```python
# nasa.ipynb dosyasını çalıştırın
# Veri yükleme, preprocessing ve model eğitimi
```

### 3. Kaydedilen Model Testi

```python
# best.ipynb dosyasını çalıştırın
# Kaydedilen modeli yükleyip rastgele verilerle test edin
```

## 📈 Model Performansı

### 🏆 Ana Sonuçlar

- **Model Türü**: CNN+LSTM Hibrit
- **Parametre Sayısı**: ~50,000 parametre
- **Input Shape**: (30, 17) - 30 zaman adımı, 17 özellik
- **Output**: Tek değer (RUL tahmini)

### 📊 Test Senaryoları

1. **Erken Aşama Motor**: Düşük sensör değerleri
2. **Geç Aşama Motor**: Yüksek sensör değerleri
3. **Extremal Değerler**: Aşırı durumlar
4. **Rastgele Normal**: Standart test verileri

## 🔍 Özellikler

### ✅ Tamamlanan Çalışmalar

- [x] NASA CMaps veri analizi ve görselleştirme
- [x] Comprehensive Exploratory Data Analysis (EDA)
- [x] Zaman serisi veri preprocessing
- [x] CNN+LSTM hibrit model tasarımı
- [x] Model eğitimi ve optimizasyonu
- [x] Performans değerlendirmesi
- [x] Model kaydı (.h5 formatında)
- [x] Rastgele test veri generator
- [x] Çok senaryolu model testi
- [x] Sonuç görselleştirme

### 🎨 Görselleştirmeler

- RUL tahmin dağılımları
- Senaryo bazında karşılaştırma
- Model performans istatistikleri
- Zaman serisi grafikleri

## 🧪 Test Edilmiş Senaryolar

### 1. Pure Python Implementation

- Basit CNN+LSTM benzeri model (demo amaçlı)
- RMSE: 42.05
- Educational purposes için geliştirildi

### 2. TensorFlow CNN+LSTM Model

- Profesyonel CNN+LSTM implementasyonu
- best_model.h5 olarak kaydedildi
- Production-ready model

### 3. Rastgele Test Protokolü

- 10 farklı rastgele sample
- Erken/geç aşama simülasyonu
- Extremal değer testi

## 📝 Teknik Notlar

### 🔧 Veri Preprocessing

```python
# Özellik seçimi
selected_features = [
    'operational_setting_1', 'operational_setting_2', 'operational_setting_3',
    'sensor_measurement_2', 'sensor_measurement_3', 'sensor_measurement_4',
    # ... 17 özellik toplamda
]

# Sekans oluşturma
sequence_length = 30
X_shape = (n_samples, 30, 17)
```

### ⚙️ Model Parametreleri

```python
# CNN Layer
conv_filters = 64
kernel_size = 3

# LSTM Layer
lstm_units = 50

# Dense Layer
dense_units = 32
```

n

