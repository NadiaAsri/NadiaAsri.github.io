# Eror Dalam Komputasi Numerik

## Pengertian

Komputer Numerik bertujuan untuk menentukan suatu akurasi dari hasil perhitungan atau percobaan.

Komputer numerik dapat dikatakan sebagai komputasi yang mengikuti suatu algoritma pendekatan (*aproksimasi*) untuk menyelesaikan suatu persoalan, yang dengan demikian besar kemungkinan di
situ terkandung “kesalahan”.

Error/Galat merupakan perbedaan antara hasil penyelesaian suatu model matematik secara numeric dengan penyelesaian secara analitis.

## Nilai Galat (Nilai Kesalahan)

Besarnya kesalahan atas suatu nilai taksiran dapat dinyatakan secara kuantitatif dan kualitatif.

Besarnya kesalahan yang dinyatakan secara kuantitatif disebut **Kesalahan Absolut.** 

Besarnya kesalahan yang dinyatakan secara kualitatif disebut dengan **Kesalahan**  **Relatif**.

## Absolute Error

Kesalahan absolut suatu kuantitas adalah nilai absolut dari selisih antara nilai sebenarnya X dan nilai perkiraan x. Ini dilambangkan dengan![1583319652816](C:\Users\NADIYA-PC\AppData\Roaming\Typora\typora-user-images\1583319652816.png)

## Relative Error

Relative error biasa disebut sebagai kesalahan relatif dari suatu kuantitas  adalah rasio kesalahan absolutnya terhadap nilai sebenarnya.

## Penyabab Terjadinya Error

1. Round-off-errors
2. Truncation errors
3. Inherent error

```py
import math

x=int(input("masukan nilai x="))
coba =1
a = 0
b=1
while coba>0.001:
    f_x = 0
    f_y = 0
    for i in range(a):
        f_x += (3*i)*x*i/math.factorial(i)

    for j in range(b):
        f_y += (3*j)*x*j/math.factorial(j)
    print("suku ke",a,"=",f_x)
    print("suku ke",b,"=",f_y)

    coba = f_y-f_x
    a+=1
    b+=1
    print("hasil seliih =",coba)
```

