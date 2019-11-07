# Mengukur Jarak Data

Komponen utama dalam algoritma clustering berbasis jarak adalah mengukur jarak antar data. Untuk Melakukan suat pengelompokan algoritma yang dipakai adalah algoritma Partisioning misal K-Mean, K-medoidm dan fuzzy c-mean dan rough clustering tergantung pada jaraknya.

Ukuran kesamaan adalah ukuran seberapa mirip dua objek data. Ukuran kesamaan dalam konteks data mining adalah jarak dengan dimensi yang mewakili fitur dari objek. Jika jarak ini kecil, itu akan menjadi tingkat kesamaan yang tinggi di mana jarak yang besar akan menjadi tingkat kesamaan yang rendah.

Kesamaannya adalah subyektif dan sangat tergantung pada domain dan aplikasi. Misalnya, dua buah serupa karena warna atau ukuran atau rasa. Perhatian harus diambil saat menghitung jarak lintas dimensi / fitur yang tidak terkait. Nilai-nilai relatif dari setiap elemen harus dinormalisasi, atau satu fitur bisa berakhir mendominasi perhitungan jarak.

## Manhattan Distance

Mahattan Distance sensitif terhadap outlier. Rumus Mahattan cenderung lebih cepat dibandingkan  dengan rumus Euclidean namun dari beberapa percobaan hasil proses clustering Euclidean lebih baik dari Manhattan.
$$
d _ { \operatorname { man } } = \sum _ { i = 1 } ^ { n } \left| x _ { i } - y _ { i } \right|
$$

##### Contoh Implementasi Program Python Menggunakan Manhattan Distance

```py
from math import*
def manhattan_distance(x,y):
	return sum(abs(a-b) for a,b in zip(x,y))
print manhattan_distance([10,20,10],[10,20,20])
```

```python
10
[Finished in 0.0s]
```

## Euclidean Distance

metode ini merupakan metode paling terkenal.  untuk mempelajari hubungan antara sudut dan jarak.  Euclidean distance adalah metode yang lebih baik dari pada Mahattan Distance. Jarak Euclidean adalah penggunaan jarak yang paling umum. Dalam kebanyakan kasus ketika orang mengatakan tentang jarak, mereka akan merujuk pada jarak Euclidean. Jarak Euclidean juga dikenal sebagai jarak sederhana. Ketika data padat atau kontinu, ini adalah ukuran kedekatan terbaik.

Jarak Euclidean antara dua titik adalah panjang jalur yang menghubungkannya. Teorema Pythagoras memberikan jarak ini antara dua titik.
$$
d _ { m a h } = \sqrt { ( x - y ) S ^ { - 1 } ( x - y ) ^ { T } }
$$

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {inlineMath: [['$$','$$']]}
});
</script>
  <script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

##### Contoh Implementasi Euclidean Distance pada python

```python
from math import*
 
def euclidean_distance(x,y):
 
    return sqrt(sum(pow(a-b,2) for a, b in zip(x, y)))
 
print euclidean_distance([0,3,4,5],[7,6,3,-1])
```

```python
9.74679434481
[Finished in 0.0s]
```

### **Manhattan distance implementation in python:**

```python
def manhattan_distance(x,y):
 
    return sum(abs(a-b) for a,b in zip(x,y))
 
print manhattan_distance([10,20,10],[10,20,20])
```

```python
10
[Finished in 0.0s]
```



## Minkowski Distance

Jarak Minkowski adalah bentuk metrik umum jarak Euclidean dan jarak Manhattan. Cara jarak diukur dengan metrik Minkowski dengan urutan berbeda antara dua objek dengan tiga variabel (Pada gambar ditampilkan dalam sistem koordinat dengan sumbu x, y, z).
$$
d _ { m a h } = \sqrt { ( x - y ) S ^ { - 1 } ( x - y ) ^ { T } }
$$


### **Minkowski distance implementation in python:**

```python
from math import*
from decimal import Decimal
 
def nth_root(value, n_root):
 
    root_value = 1/float(n_root)
    return round (Decimal(value) ** Decimal(root_value),3)
 
def minkowski_distance(x,y,p_value):
 
    return nth_root(sum(pow(abs(a-b),p_value) for a,b in zip(x, y)),p_value)
 
print minkowski_distance([0,3,4,5],[7,6,3,-1],3)
```

```python

```