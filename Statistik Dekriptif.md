## **STATISTIK DESKRIPTIF**

**1. PENGERTIAN**

Statistik deskritif memberikan informasi tentang data yang dipunyai dan sama sekali tidak menarik inferensia atau kesimpulan apapun tentang gugus induknya yang lebih besar. Dengan statistik ini, kumpulan data yang diperoleh akan tersaji denga ringkas dan rapi serta dapat memberikan informasi inti dari kumpulan data yang ada.

**2. UKURAN TENDENSI SENTRAL**

Ukuran tendensi sentral adalah setiap pengukuran aritmatika yang ditujukan untuk menggambarkan suatu nilai yang mewakili nilai pusat atau nilai sentral dari suatu gugus data (himpunan pengamatan)

berikut adalah bebrapa jenis ukuran tendensi sentral yang sering digunakan:

a. Mean

Mean adalah *nilai rata-rata* dari beberapa buah data. Nilai mean dapat ditentukan dengan membagi jumlah data dengan banyaknya data.

Mean (rata-rata) merupakan suatu ukuran pemusatan data. Mean suatu  data juga merupakan statistik karena mampu menggambarkan bahwa data  tersebut berada pada kisaran mean data tersebut. Mean tidak dapat  digunakan sebagai ukuran pemusatan untuk jenis data nominal dan ordinal.
$$
\bar x ={\sum \limits_{i=1}^{n} x_i \over N} = {x_1 + x_2 + x_3 + ... + x_n \over N}
$$
Dimana:
x bar = x rata-rata = nilai rata-rata sampel
x = data ke n
n = banyaknya data

b. Modus

Modus adalah nilai yang sering muncul. Jika kita tertarik pada data frekuensi, jumlah dari suatu nilai dari kumpulan data, maka kita menggunakan modus. Modus sangat baik bila digunakan untuk data yang memiliki sekala kategorik yaitu nominal atau ordinal.
$$
M_o = Tb + p{b_1 \over b_1 + b_2}
$$
Dimana: 
Mo = modus dari kelompok data
Tb = tepi bawah dari elemen modus
b1 = selisih frekuensi antara elemen modus dengan elemet sebelumnya 
b2 = selisih frekuensi antara elemen modus dengan elemen sesudahnya
p = panjang interval

nilai b1 dan b2 –> adalah mutlak (selalu positif)

c. Median

Median menentukan letak tengah data setelah data disusun menurut urutan  nilainya. Bisa juga *nilai tengah dari data-data yang terurut**.*** Simbol untuk median adalah Me.  Dengan median Me, maka 50% dari banyak data nilainya paling tinggi sama dengan Me, dan 50% dari banyak data nilainya paling rendah sama dengan Me. Dalam  mencari median, dibedakan  untuk  banyak data ganjil  dan banyak data genap.  Untuk  banyak data ganjil, setelah data disusun menurut nilainya, maka median Me adalah data yang terletak tepat di tengah. Median bisa dihitung menggunakan rumus sebagai
berikut:
$$
Me=Q_2 =\left( \begin{matrix}
  n+1 \over 2
\end{matrix} \right), jika\quad n\quad ganjil
$$

$$
Me=Q_2 =\left( \begin{matrix}
  {xn \over 2 } {xn+1\over 2} \over 2
\end{matrix} \right), jika\quad n\quad genap
$$

Dimana : 
Me = Median dari kelompok data
n = banyak data 

d. Varians

Varians adalah suatu ukuran penyebaran data, yang diukur dalam pangkat dua dari selisih data terhadap rata-ratanya.

![img](https://junaidichaniago.files.wordpress.com/2008/06/062308-0135-ukuranukura6.png?w=468)

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {inlineMath: [['$$','$$']]}
});
</script>
  <script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

e. Standard Deviasi

Standar deviasi merupakan akar dari  varians (ingat, karena pada varians kita mengkuadratkan selisih data  dari rata-ratanya, maka dengan mengakarkannya, kita mendapatkan kembali  nilai asalnya).

![img](https://junaidichaniago.files.wordpress.com/2008/06/062308-0135-ukuranukura11.png?w=468)

**3. ALAT DAN BAHAN**

pada tugas kali ini saya menggunakan data random sebanyak 500 data yang disimpan dalam bentuk .csv. Saya juga menggunakan IDLE Python dan Library pandas, matplotlib juga scipy. pandas berguna untuk membaca file .csv dan untuk mengolah data. Mtpolotlib berguna untuk memvisualisasikan data dengan lebih indah dan rapi. Sedangkan scipy berguna untuk menangani operasi aljabar dan matriks serta operasi matematika lainnya.

a. Langkah Pertama

Memasukkan library

```python
from scipy import stats
import pandas as pd
import matplotlib.pyplot as plt
```

b. Langkah Kedua

mengimport data .csv yang telah disipakan

```python
df = pd.read_csv('tugas1.csv',sep=';')
df
```

c. Langkah Ketiga

Menampung nilai yang akan ditampilkan didalam data penyimpanan (dictionary). Membuat iterasi yang akan mengambil data pada file yangtelah diimport.

```py
data={"stats": ['Min','Max','Mean','Standard deviasi','Variasi','Skewnes','Q1','Q2','Q3','Median','Modus']}
for i in df.columns:
    data[i]=[df[i].min(),df[i].max(),df[i].mean(),round(df[i].std(),2),round(df[i].var(),2),round(df[i].skew(),2),df[i].quantile(0.25),df[i].quantile(0.5),df[i].quantile(0.75),df[i].median(),stats.mode(df[i]).mode[0]]
tes=pd.DataFrame(data,columns=['stats']+[x for x in df.columns])
tes
```

d. Langkah Keempat

memvisualisasikan hasil tersebut dalam bentuk dataframe

```python
data={"stats": ['Min','Max','Mean','Standard deviasi','Variasi','Skewnes','Q1','Q2','Q3','Median','Modus']}
for i in df.columns:
    data[i]=[df[i].min(),df[i].max(),df[i].mean(),round(df[i].std(),2),round(df[i].var(),2),round(df[i].skew(),2),df[i].quantile(0.25),df[i].quantile(0.5),df[i].quantile(0.75),df[i].median(),stats.mode(df[i]).mode[0]]
tes=pd.DataFrame(data,columns=['stats']+[x for x in df.columns])
tes
```

<table>
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>stats</th>
      <th>x1</th>
      <th>x2</th>
      <th>x3</th>
      <th>x4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>Min</td>
      <td>60.000</td>
      <td>60.00</td>
      <td>60.000</td>
      <td>60.000</td>
    </tr>
    <tr>
      <td>1</td>
      <td>Max</td>
      <td>100.000</td>
      <td>100.00</td>
      <td>100.000</td>
      <td>100.000</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Mean</td>
      <td>79.478</td>
      <td>80.29</td>
      <td>80.334</td>
      <td>80.256</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Standard deviasi</td>
      <td>12.080</td>
      <td>11.25</td>
      <td>11.540</td>
      <td>11.790</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Variasi</td>
      <td>145.990</td>
      <td>126.66</td>
      <td>133.260</td>
      <td>139.080</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Skewnes</td>
      <td>0.060</td>
      <td>-0.06</td>
      <td>0.010</td>
      <td>-0.000</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Q1</td>
      <td>69.000</td>
      <td>71.00</td>
      <td>71.000</td>
      <td>70.000</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Q2</td>
      <td>78.500</td>
      <td>81.00</td>
      <td>80.500</td>
      <td>80.000</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Q3</td>
      <td>90.000</td>
      <td>89.00</td>
      <td>90.000</td>
      <td>90.000</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Median</td>
      <td>78.500</td>
      <td>81.00</td>
      <td>80.500</td>
      <td>80.000</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Modus</td>
      <td>72.000</td>
      <td>86.00</td>
      <td>71.000</td>
      <td>93.000</td>
    </tr>
  </tbody>
</table>