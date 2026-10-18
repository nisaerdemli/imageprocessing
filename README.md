---

## 📌 Hafta 5: Canny Kenar Algoritması ve Adımların İncelenmesi

Bu ödev kapsamında Canny Kenar Bulma Algoritması Python, NumPy ve OpenCV kullanılarak sıfırdan 4 temel fonksiyon halinde kodlanmıştır.

### 1. Gürültü Bastırma (5x5 Gauss Filtresi)
* **Neden Gerekli?** Kenar tespiti pikseller arasındaki türev (ani yoğunluk değişimi) hesabına dayanır. Türev operatörleri görüntüdeki yüksek frekanslı parazit ve gürültülere karşı aşırı duyarlıdır. Önceden Gauss filtresi ile pürüzsüzleştirme yapılmazsa görüntüdeki rastgele gürültüler yanlışlıkla kenar olarak algılanır.

### 2. Sobel Filtresi ile Gradyan ve Yön Hesaplama
* **Neden Gerekli?** Kenarlar, piksel yoğunluğunun aniden değiştiği sınır hatlarıdır. Yatay ($I_x$) ve dikey ($I_y$) Sobel filtreleri konvolüsyon ile uygulanarak her pikselin gradyan büyüklüğü (kenarın şiddeti) ve gradyan yönü ($\theta$) matematiksel olarak hesaplanır.

### 3. Non-Maximum Suppression (NMS - Kenar İnceltme)
* **Neden Gerekli?** Gradyan hesaplaması sonrasında elde edilen kenar çizgileri kalın ve bulanıktır. NMS adımı, hesaplanan gradyan açısı doğrultusunda yerel maksimum (tepe noktası) olmayan pikselleri sıfırlayarak kenarları tek piksel genişliğine indirir ve keskinleştirir.

### 4. Hysteresis Thresholding (Çift Eşikleme ve Kenar Bağlama)
* **Neden Gerekli?** Tek bir sabit eşik kullanıldığında gerçek kenarlarda kopukluklar meydana gelebilir veya parazitler kenar sayılabilir. Çift eşikleme (alt ve üst eşik) uygulanarak kesin kenarlar doğrudan seçilir; zayıf kenarlar ise yalnızca güçlü bir kenarla bağlantılıysa kabul edilir. Böylece gerçek kenarların sürekliliği korunur.
