# Mencari Data Hilang Menggunakan K-Nearest Neighbour

salah satu permasalahan yang sering terjadi adalah adanya data yang hilang dalam suatu database. Metode yang paling mudah untuk menyelesaikan masalah ini adalah menggunakan Knn atau K-Nearest Neighbour. Kelemahan metode ini adalah pemilihan nilai k yang  tidak tepat  dapat menurunkan  kinerja klasifikasi. Metode ini juga merupakan metode yang sederhana dan fleksibel dikarenakan dapat  digunakan baik pada  variabel  dengan data  kontinu maupun data diskrit. langkah penting dalam knn adalah menentukan nilai k  dimana sejumlah k tetangga terdekat dari dataset akan dijadikan sebagai  nilai estimator. Pemilihan sejumlah  tetangga  didasarkan  pada  jarak  salah satu instance  dengan seluruh instance  yang ada pada  dataset.  Dari  informasi  tetangga  tersebut diperoleh estimasi nilai yang kemudian digunakan sebagai  nilai  imputasi  pada  data  yang  hilang. Perhitungan  dalam  menentukan  nilai  imputasi tergantung  pada  jenis  data,  untuk  data  kontinu digunakan  rata-rata  dari  tetangga  terdekat, sedangkan  untuk  data  kualitatif  nilai  imputasi diambil  dari  nilai  yang  seringkali  keluar.

## Algoritma KNN



1. Tentukan nilai k 

2. Tentukan  jarak  Euclidian  antar  instance  pada dataset Dm dan dataset Dc 

3. Imputasi  data  hilang  dengan  rata-rata k tetangga terdekat di Dc 

```python
# importing pandas as pd 
import pandas as pd 
  
# importing numpy as np 
import numpy as np 
  
# dictionary of lists 
dict = {'First Score':[95, 70, np.nan, 90], 
        'Second Score': [75, 70, 91, np.nan], 
        'Third Score':[np.nan, 75, 85, 90]}
  
# creating a dataframe from dictionary 
df = pd.DataFrame(dict) 
  
# filling missing value using fillna()   
df.fillna(0)
```

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {inlineMath: [['$$','$$']]}
});
</script>
  <script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script><table border="1" class="dataframe">
  <table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>First Score</th>
      <th>Second Score</th>
      <th>Third Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>95.0</td>
      <td>75.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <td>1</td>
      <td>70.0</td>
      <td>70.0</td>
      <td>75.0</td>
    </tr>
    <tr>
      <td>2</td>
      <td>0.0</td>
      <td>91.0</td>
      <td>85.0</td>
    </tr>
    <tr>
      <td>3</td>
      <td>90.0</td>
      <td>0.0</td>
      <td>90.0</td>
    </tr>
  </tbody>
</table>



