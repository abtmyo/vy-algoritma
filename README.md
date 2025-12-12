# Veri Yapıları ve Algoritmalar

Güvenç Usanmaz

guvencu@anadolu.edu.tr

Oda: 115

Ofis Saatleri

## Python

### Kaynaklar

* https://docs.python.org/3/tutorial/index.html
* https://docs.python.org/3/tutorial/index.html
* https://erdincuzun.com/python/01-python/
* https://www.btkakademi.gov.tr/portal/course/player/deliver/veri-yapilari-ve-algoritmalar-ryz-yok-32057
* https://www.youtube.com/playlist?list=PLKYEe2WisBTFEr6laH5bR2J19j7sl5O8R
* https://www.youtube.com/watch?v=DMeD8trbj6A&t=7846s
* https://www.youtube.com/watch?v=kQDxmjfkIKY

* https://algs4.cs.princeton.edu/home/
* https://www.coursera.org/learn/algorithms-part1
  
* https://exercism.org/tracks/python
* https://github.com/TheAlgorithms/Python

* https://visualgo.net/en
* https://algorithm-visualizer.org/

### Kitaplar

* Data Structures and Algorithms in Python 1st Edition - https://www.amazon.com/Structures-Algorithms-Python-Michael-Goodrich/dp/1118290275/
* A Common-Sense Guide to Data Structures and Algorithms in Python, Volume 1: Level Up Your Core Programming Skills - https://www.amazon.com/Common-Sense-Guide-Structures-Algorithms-Python/dp/B0CPB51GT5/

### Programlar

* PyCharm (https://www.jetbrains.com/pycharm/)
* VS Code (?)
* Google Colab https://colab.google/ (?)
* GitHub

### Yapay Zeka

* OpenAI - GPTx
* Antrophic - Cluade
* x.ai - Grok
* Google - Gemini


* https://gist.github.com/gusanmaz/baea54c3c0bda654851b9e3e1b5ca738
* https://programming-25.mooc.fi/


### Odev 0

https://classroom.github.com/a/pCzT7-dq

## 24 Ekim Ders Notlari

https://gist.github.com/gusanmaz/e695840f0d4e2a4dfb100d094fb81ae9

## 31 Ekim Notlari

https://gist.github.com/gusanmaz/05d25d8e93751c5d571b1d0213ffbe90

# 21 Kasim Notlari

* https://gusanmaz.github.io/alg21nov/fonksiyonlar.html
* https://gusanmaz.github.io/alg21nov/siniflar.html

# 28 Kasim Notlari

* https://gusanmaz.github.io/algs/1a_analiz_giris.html

```python
import numpy as np
class Queue:
    def __init__(self, capacity):
        self.capacity = capacity
        self.data = np.zeros(capacity, dtype=int)
        self.head = 0
        self.tail = 0
        self.size = 0

    def enqueue(self, val):
        # Dairesel olmadığı için tail sona geldiyse, 
        # baş tarafta yer olsa bile ekleme yapamayız (Shifting yapmadığımız sürece).
        if self.tail == self.capacity:
            print("❌ Dolu! (Kuyruk sonuna ulaşıldı)")
            return

        self.data[self.tail] = val
        self.tail += 1  # Modülo (%) operatörünü kaldırdık, sadece artırıyoruz
        self.size += 1
        print(f"Enqueue({val}) -> {self.data}")

    def dequeue(self):
        if self.size == 0:
            print("❌ Boş!")
            return

        val = self.data[self.head]
        self.data[self.head] = 0  # Görsel temizlik için (zorunlu değil)
        self.head += 1  # Modülo (%) operatörünü kaldırdık, sadece artırıyoruz
        self.size -= 1
        print(f"Dequeue() -> {val}")

        # Eğer kuyruk tamamen boşaldıysa pointerları başa çekebiliriz (Optimasyon)
        if self.size == 0:
            self.head = 0
            self.tail = 0
            print("ℹ️ Kuyruk boşaldı, pointerlar sıfırlandı.")

        return val


# Test Adımları
q = Queue(5)
q.enqueue(10)
q.enqueue(20)
q.dequeue()
q.enqueue(30)
```




  
