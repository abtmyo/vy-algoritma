# Ödev 1: Düzgün Çokgenler Sınıfı (Regular Polygon Class)

## 🎯 Amaç

Bu ödevin amacı, derste öğrendiğimiz **Sınıflar (Classes)**, **Nesneler (Objects)**, **Constructor (init)** ve **Metodlar** konularını pekiştirmektir.

Sizden geometrik bir şekil olan "Düzgün Çokgen"i temsil eden bir Python sınıfı yazmanızı istiyoruz. Bu sınıfı kullanarak kare, beşgen, altıgen gibi şekillerin alanlarını ve açılarını otomatik hesaplayan bir program oluşturacaksınız.

🔗 **Ders Notları:** [Sınıflar ve Objeler Dersine Gitmek İçin Tıklayın](https://gusanmaz.github.io/alg21nov/siniflar.html)

-----

## 📘 Ön Bilgi: Matematiksel Formüller

Bu ödevi yapmak için matematik dehası olmanıza gerek yok\! 🤓 Aşağıdaki formülleri Python koduna çevirmeniz yeterli olacaktır.

Bir düzgün çokgenin; kenar sayısı **$n$**, bir kenar uzunluğu **$s$** olsun.

### 1\. Basit Hesaplamalar

  * **Çevre:** Tüm kenarlar eşittir.
      * `Çevre = n * s`
  * **İç Açı:** Bir köşedeki iç açının derecesi.
      * `İç Açı = (n - 2) * 180 / n`
  * **Dış Açı:** Bir köşedeki dış açının derecesi.
      * `Dış Açı = 360 / n`
  * **Köşegen Sayısı:** Bir çokgenin içinden geçen toplam çizgi sayısı.
      * `Köşegen Sayısı = n * (n - 3) / 2`

### 2\. Alan Hesabı (Trigonometri İçerir 📐)

Düzgün bir çokgenin alanını hesaplamak için trigonometrik "tanjant" fonksiyonunu kullanırız. Python'da bunu yapmak çok kolaydır.

$$\text{Alan} = \frac{n \times s^2}{4 \times \tan(\frac{\pi}{n})}$$

**Python'da Nasıl Yazılır?**
Bu formülü koda dökmek için `math` kütüphanesini kullanmalıyız.

1.  Kodunuzun en tepesine `import math` yazın.
2.  $\pi$ sayısı için `math.pi` kullanın.
3.  Tanjant fonksiyonu için `math.tan(...)` kullanın.
4.  Formülün Pythoncası:
    ```python
    alan = (n * s**2) / (4 * math.tan(math.pi / n))
    ```

-----

## 🚀 Görev Tanımı

`DuzgunCokgen` adında bir sınıf (class) yazacaksınız. Bu sınıfın özellikleri ve kuralları şunlardır:

### 1\. Kurucu Metod (`__init__`) ve Kontroller

Sınıf oluşturulurken `kenar_sayisi` ve `kenar_uzunlugu` parametrelerini almalıdır. Ancak hatalı girişleri engellemek için şu kontrolleri yapmalısınız:

  * **Kenar Sayısı Kontrolü:** Bir çokgen en az 3 kenarlı olabilir.
      * *Kural:* Eğer girilen kenar sayısı 3'ten küçükse; ekrana `"HATA: Kenar sayısı en az 3 olmalıdır. Varsayılan (3) kullanılıyor."` yazdırın ve kenar sayısını **3** olarak ayarlayın.
  * **Kenar Uzunluğu Kontrolü:** Uzunluk negatif veya sıfır olamaz.
      * *Kural:* Eğer uzunluk 0 veya daha küçükse; ekrana `"HATA: Kenar uzunluğu pozitif olmalı. Varsayılan (1) kullanılıyor."` yazdırın ve uzunluğu **1** olarak ayarlayın.

### 2\. İstenen Metodlar

Sınıfınızın içinde şu fonksiyonlar (metodlar) bulunmalıdır:

  * `cevre_hesapla()`: Çevreyi hesaplayıp döndürür (return).
  * `alan_hesapla()`: Alanı hesaplayıp döndürür.
  * `kosegen_sayisi_hesapla()`: Köşegen sayısını hesaplayıp döndürür. (Sonucun tam sayı `int` çıkmasına dikkat edin).
  * `ic_aci_hesapla()`: Bir iç açıyı hesaplayıp döndürür.
  * `dis_aci_hesapla()`: Bir dış açıyı hesaplayıp döndürür.
  * `bilgileri_goster()`: Çokgenin türünü (örn: "5-gen") ve yukarıdaki tüm hesaplanmış verileri ekrana düzgünce yazdırır.

-----

## 💻 Başlangıç Kodu (Template)

Ödeve başlamak için aşağıdaki kodu kopyalayıp üzerinde çalışabilirsiniz. `TODO` yazan yerleri doldurmanız gerekmektedir.

```python
import math  # Matematiksel işlemler için gerekli

class DuzgunCokgen:
    def __init__(self, kenar_sayisi, kenar_uzunlugu):
        # --- TODO: Kenar Sayısı Kontrolü ---
        # Eğer kenar_sayisi 3'ten küçükse, hata mesajı yaz ve 3'e eşitle.
        # Değilse, self.kenar_sayisi'na ata.
        
        # ÖRNEK MANTIK (Bunu koda dökün):
        # if kenar_sayisi < 3:
        #     print("Hata...")
        #     self.kenar_sayisi = 3
        # else:
        #     self.kenar_sayisi = kenar_sayisi

        
        # --- TODO: Kenar Uzunluğu Kontrolü ---
        # Eğer kenar_uzunlugu 0 veya daha az ise, hata mesajı yaz ve 1'e eşitle.
        # Değilse, self.kenar_uzunlugu'na ata.
        pass # Bu satırı silip kodunuzu yazın

    def cevre_hesapla(self):
        return 0 # Burayı düzeltin

    def alan_hesapla(self):
        return 0 # Burayı düzeltin

    def kosegen_sayisi_hesapla(self):
        # İpucu: Sonuç ondalıklı (float) çıkabilir, int() ile tam sayıya çevirin.
        return 0 # Burayı düzeltin
    
    def ic_aci_hesapla(self):
        return 0

    def dis_aci_hesapla(self):
        return 0

    def bilgileri_goster(self):
        print("\n" + "="*30)
        print(f"ŞEKİL: Düzgün {self.kenar_sayisi}-gen")
        print("="*30)
        # TODO: Diğer metodları çağırarak sonuçları yazdırın.
        # Örnek: print(f"Çevre: {self.cevre_hesapla()}")

# --- TEST KODLARI ---
# Kodu çalıştırdığınızda aşağıdaki çıktıları görmelisiniz.

print("--- Test 1: Kare (4 kenar, 10 birim) ---")
kare = DuzgunCokgen(4, 10)
kare.bilgileri_goster()
# Beklenen Alan: 100.0

print("\n--- Test 2: Hatalı Giriş Testi ---")
hatali_sekil = DuzgunCokgen(1, -5) 
hatali_sekil.bilgileri_goster()
# Beklenen: Hata mesajları çıkmalı ve şekil 3 kenarlı (üçgen), 1 birim uzunluğunda olmalı.

print("\n--- Test 3: Altıgen (6 kenar, 5 birim) ---")
altigen = DuzgunCokgen(6, 5)
altigen.bilgileri_goster()
```

-----

## 📤 Nasıl Teslim Edeceğim?

1.  https://classroom.github.com/a/0XWigUDW bağlantısındaki davetiyeyi kabul edin ve ardından GitHub Classroom tarafından oluşturulan reponuzu açın.
2.  Burada `main.py` isimli bir dosya oluşturun.
3.  PyCharm'da sorunsuz çalıştırdığınız (tesleri geçen) kodu `main.py` dosyasına kopyalayınız.
4.  Değişiklikleri `commit` yapın ve GitHub'a `push` edin. (Commit, sonra Commit Changes)
5.  Ödevi Commit etme konusunda sorun yaşarsanız 0. ödev için hazırlanan ödev gönderim dökümanını (https://github.com/abtmyo/vy-algoritma/blob/main/github-classroom-gonderim.pdf) da inceleyebilirsiniz.
-----

## ⏰ Son Teslim Tarihi

**Tarih:** 7 Aralık 2025
**Saat:** 23:59

Başarılar\! Kodunuzda takılırsanız dersteki "Dikdörtgen" ve "Üçgen" örneklerini https://gusanmaz.github.io/alg21nov/siniflar.html bağlantısından inceleyebilirsiniz.
