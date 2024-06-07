# MNIST Veritabanı ile Makine Öğrenimi Çalışması

Bu repo, el yazısı rakamların sınıflandırılması için yaygın olarak kullanılan MNIST veritabanını kullanarak makine öğrenimi modelleri üzerinde yapılan bir çalışmayı içermektedir.

## MNIST Veritabanı Hakkında

MNIST (Modifiye Ulusal Standartlar ve Teknoloji Enstitüsü) veritabanı, el yazısı rakamların 28x28 piksellik gri tonlamalı görüntülerinden oluşan geniş bir koleksiyondur. Veritabanı, makine öğrenimi ve görüntü işleme sistemlerini eğitmek için yaygın olarak kullanılmaktadır. MNIST, 60.000 eğitim görüntüsü ve 10.000 test görüntüsü içerir.

### Veritabanının Özellikleri
- **Eğitim Görüntüleri:** 60.000
- **Test Görüntüleri:** 10.000
- **Görüntü Boyutu:** 28x28 piksel, gri tonlamalı

## Çalışma Hakkında

Bu çalışmada, MNIST veritabanını kullanarak çeşitli makine öğrenimi modelleri eğitildi ve test edildi. Elde edilen sonuçlar, çeşitli metrikler (doğruluk, kayıp, kesinlik ve hatırlama) kullanılarak değerlendirildi.

### Kullanılan Modeller
- Destek Vektör Makineleri (SVM)
- Çok Katmanlı Algılayıcı (MLP)
- Evrişimsel Sinir Ağları (CNN)
- DropConnect ile Düzenlenmiş Sinir Ağları
- Rastgele Çarpıtma Altında Test Edilen Sinir Ağları

## Sonuçlar

Modellerin performansı, doğruluk ve hata oranları ile değerlendirildi. Elde edilen en iyi sonuçlar aşağıdaki gibidir:
- **Destek Vektör Makineleri:** %0.8 hata oranı
- **LIRA Sınıflandırıcısı:** %0.42 hata oranı
- **Elastik Distorsiyonlu Sinir Ağları:** %0.39 hata oranı
- **2011 Sinir Ağı Modeli:** %0.27 hata oranı
- **DropConnect Sinir Ağı:** %0.21 hata oranı
- **Tek Evrişimli Sinir Ağı:** %0.25 hata oranı
- **2018 Eşzamanlı Yığılmış Sinir Ağı Modeli:** %0.18 hata oranı

## Kullanım

Projeyi klonladıktan sonra, aşağıdaki adımları izleyerek çalıştırabilirsiniz:

1. Gerekli bağımlılıkları yükleyin:
    ```bash
    pip install -r requirements.txt
    ```

2. Eğitim ve test verilerini indirin:
    ```python
    from tensorflow.keras.datasets import mnist
    (x_train, y_train), (x_test, y_test) = mnist.load_data()
    ```

3. Modeli eğitin ve değerlendirin:
    ```python
    # Örnek eğitim ve değerlendirme kodu
    model = ...  # Modelinizi oluşturun
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
    model.fit(x_train, y_train, epochs=10, batch_size=32)
    loss, precision, recall, acc = model.evaluate(x_test, y_test, verbose=False)
    print("\nTest Accuracy: %.2f%%" % (100.0 * acc))
    print("\nTest Loss: %.2f" % loss)
    print("\nTest Precision: %.2f%%" % (100.0 * precision))
    print("\nTest Recall: %.2f%%" % (100.0 * recall))
    ```

## Katkıda Bulunma

Katkıda bulunmak isterseniz, lütfen bir pull request gönderin veya bir issue açın. Her türlü geri bildirime açığız!

---

## Kaynaklar

- [MNIST Veritabanı](http://yann.lecun.com/exdb/mnist/)
- [Destek Vektör Makineleri ile MNIST](https://www.researchgate.net/publication/13102767_Gradient-Based_Learning_Applied_to_Document_Recognition)
- [DropConnect ile Sinir Ağları](https://arxiv.org/abs/1306.0239)
- [2018 Sinir Ağı Modelleri](https://arxiv.org/abs/1808.01210)

