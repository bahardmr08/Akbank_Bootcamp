# Akbank_Bootcamp

## Balık Türlerini Sınıflandırma-Yapay Sinir Ağları Projesi

### Proje Amacı
Bu Projede amaç, balık verisindeki balıkları görüntü tabanlı olarak doğru bir şekilde sınıflandırabilen bir model gerçekleştirme.

### Kullanılan Kütüphaneler
• **TensorFlow/Keras**  
• **Pandas**  
• **NumPy**  
• **Matplotlib**

## Proje Adımları
### Veri Ön İşleme
  • Görüntü dosyaları GT klasörleri hariç olacak şekilde filtrelendi.  
  
  • Veri seti, etiketler(label) ve dosya yolu(path) kullanılarak bir pandas DataFrame'e dönüştürüldü.    
  
  • Balık türlerine ait görüntülerin bulunduğu dizindeki dosyalar okunarak, etiketler ve görüntü dosya yolları listelendi.  
  
  • Görüntü dosyaları boyutlandırıldı (128x128 piksel) ve normalizasyon işlemi gerçekleştirildi (0-1 arası değerler).  
  
  • Veri, eğitim, doğrulama ve test setlerine ayrıldı (%70 eğitim, %15 doğrulama, %15 test).  
  

### Veri Artırma:
Eğitim verileri için ImageDataGenerator kullanılarak veri artırma işlemi uygulandı. Bu işlem, veri setini genişletmek amacıyla görüntüler üzerinde çeşitli dönüşümler (döndürme, kaydırma, ölçekleme, vb.) yapatı.

### **Modelin Oluşturulması ve Eğitimi:**

Yapay sinir ağı modeli Sequential yapısıyla oluşturuldu ve aşağıdaki katmanlar eklendi:
Giriş katmanı (Flatten): Görüntüyü düzleştiren katman.
İki gizli katman (Dense), ReLU aktivasyon fonksiyonu ile. Aşırı öğrenmeyi önlemek için Dropout katmanları kullanıldı.
Çıkış katmanı (Dense), softmax aktivasyon fonksiyonu ile, sınıfların olasılıklarını hesaplayan katman kullanıldı.
Model, Adam optimizasyon algoritması ve categorical_crossentropy kayıp fonksiyonu(loss) kullanılarak derlendi.
Model, 20 epochs eğitim verileriyle eğitildi ve her Epochs sonunda validation verisi kullanılarak modelin performansı kontrol edildi.

### **Eğitim Sonuçlarının Görselleştirilmesi:**
Eğitim ve doğrulama için kayıp(loss) ve doğruluk(accuracy) grafikleri çizildi.

### **Model Performansının Değerlendirilmesi:**
Test verisiyle tahmin yapıldı ve karışıklık matrisi (confusion matrix) ile sınıflandırma performansı görselleştirildi.
Sınıflandırma raporu, her sınıf için doğruluk, hassasiyet, ve F1 skoru gibi metrikler gösterildi.

### **Hiperparametre Ayarlaması:**
Keras Tuner kullanılarak hiperparametre araması yapıldı. Bu süreçte, gizli katman sayısı, katmanlardaki nöron sayısı, dropout oranları ve optimizer gibi parametreler denendi.
Özetle, bu adımlarla balık türlerini sınıflandırmak için bir sinir ağı modeli(ANN) oluşturuldu, eğitildi ve performansı değerlendirildi. Hiperparametre ayarlamaları ile modelin doğruluğu artırılmaya çalışıldı.

https://www.kaggle.com/code/bahardemir08/fish-siniflandirmesi
