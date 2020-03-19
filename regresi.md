## **Regresi Linear Sederhana dan Regresi Linear Berganda**

**PENGERTIAN**

Regresi secara umum adalah studi mengenai ketergantungan suatu variabel dependen (terikat) dengan satu atau lebih variabel independent (variabel penjelas/bebas). Tujuannya adalah untuk mengestimasi dan/atau memprediksi rata-rata populasi atau niiai rata-rata variabel dependen berdasarkan nilai variabel independen yang diketahui. Pusat perhatian adalah pada upaya menjelaskan dan mengevalusihubungan antara suatu variabel dengan satu atau lebih variabel independen.

Hasil analisis regresi adalah berupa koefisien regresi untuk masing-masing variable independent. Koefisien ini diperoleh dengan cara memprediksi nilai variable dependen dengan suatu persamaan. Koefisien regresi dihitung dengan dua tujuan sekaligus : Pertama, meminimumkan penyimpangan antara nilai actual dan nilai estimasi variable dependen; Kedua, mengoptimalkan korelasi antara nilai actual dan nilai estimasi variable dependen berdasarkan data yang ada. Teknik estimasi variable dependen yang melandasi analisis regresi disebut Ordinary Least Squares (pangkat kuadrat terkecil biasa).

**1. REGRESI LINEAR SEDERHANA**

![img](F:\penambangan1\docs\050510_0237_regresiline12.png)

Persamaan di atas adalah rumus dari persamaan regresi linear sederhana. *Y* adalah variabel tak bebas, *a* adalah koefisien intersep, *b* adalah kemiringan dan *t* adalah variabel bebas. Rumus untuk *b* adalah :

![img](F:\penambangan1\docs\050510_0237_regresiline22.png)

Dan rumus untuk mendapatkan nilai *a* adalah sebagai berikut :

![img](F:\penambangan1\docs\050510_0237_regresiline32.png)

Dalam regresi linear sederhana juga ada yang disebut dengan koefisien korelasi yang menunjukkan bahwa nilai suatu variabel bergantung pada perubahan nilai variabel yang lain. Rumus untuk menghitung koefisien korelasi adalah sebagai berikut :

![img](F:\penambangan1\docs\050510_0237_regresiline41.png)

**2. REGRESI LINEAR BERGANDA**

 Analisis regresi linier berganda adalah hubungan secara linear antara dua atau lebih variabel independen (X1, X2,….Xn)  dengan variabel dependen (Y). Analisis ini untuk mengetahui arah  hubungan antara variabel independen dengan variabel dependen apakah  masing-masing variabel independen berhubungan positif atau negatif dan  untuk memprediksi nilai dari variabel dependen apabila nilai variabel independen mengalami kenaikan atau penurunan. Data yang digunakan biasanya berskala interval atau rasio.

​             Persamaan regresi linear berganda sebagai berikut:

Y’ = a + b1X1+ b2X2+…..+ bnXn

 Keterangan:

 Y’                    =   Variabel dependen (nilai yang diprediksikan)

 X1 dan X2      =   Variabel independen

 a                      =   Konstanta (nilai Y’ apabila X1, X2…..Xn = 0)

 b                            =    Koefisien regresi (nilai peningkatan ataupun penurunan)

 

 Contoh kasus:

 Kita  mengambil contoh kasus pada uji normalitas, yaitu sebagai berikut:  Seorang mahasiswa bernama Bambang melakukan penelitian tentang  faktor-faktor yang mempengaruhi harga saham pada perusahaan di BEJ.  Bambang dalam penelitiannya ingin mengetahui hubungan antara rasio  keuangan PER dan ROI terhadap harga saham. Dengan ini Bambang  menganalisis dengan bantuan program SPSS dengan alat analisis regresi  linear berganda. Dari uraian di atas maka didapat variabel dependen (Y)  adalah harga saham, sedangkan variabel independen (X1 dan X2) adalah PER dan ROI.

 Data-data yang di dapat berupa data rasio dan ditabulasikan sebagai berikut:             

​                 

​                      Tabel. Tabulasi Data (Data Fiktif)

 

| Tahun | Harga Saham (Rp) | PER (%) | ROI (%) |
| ----- | ---------------- | ------- | ------- |
| 1990  | 8300             | 4.90    | 6.47    |
| 1991  | 7500             | 3.28    | 3.14    |
| 1992  | 8950             | 5.05    | 5.00    |
| 1993  | 8250             | 4.00    | 4.75    |
| 1994  | 9000             | 5.97    | 6.23    |
| 1995  | 8750             | 4.24    | 6.03    |
| 1996  | 10000            | 8.00    | 8.75    |
| 1997  | 8200             | 7.45    | 7.72    |
| 1998  | 8300             | 7.47    | 8.00    |
| 1999  | 10900            | 12.68   | 10.40   |
| 2000  | 12800            | 14.45   | 12.42   |
| 2001  | 9450             | 10.50   | 8.62    |
| 2002  | 13000            | 17.24   | 12.07   |
| 2003  | 8000             | 15.56   | 5.83    |
| 2004  | 6500             | 10.85   | 5.20    |
| 2005  | 9000             | 16.56   | 8.53    |
| 2006  | 7600             | 13.24   | 7.37    |
| 2007  | 10200            | 16.98   | 9.38    |

 

 **Langkah-langkah pada program SPSS**

 Ø  Masuk program SPSS

 Ø  Klik variable view pada SPSS data editor

 Ø  Pada kolom Name ketik y, kolom Name pada baris kedua ketik x1, kemudian untuk baris kedua ketik x2.

 Ø  Pada  kolom Label, untuk kolom pada baris pertama ketik Harga Saham, untuk  kolom pada baris kedua ketik PER, kemudian pada baris ketiga ketik ROI.

 Ø  Untuk kolom-kolom lainnya boleh dihiraukan (isian default)

 Ø  Buka data view pada SPSS data editor, maka didapat kolom variabel y, x1, dan x2.

 Ø  Ketikkan data sesuai dengan variabelnya

 Ø  Klik Analyze  - Regression - Linear

 Ø  Klik  variabel Harga Saham dan masukkan ke kotak Dependent, kemudian klik  variabel PER dan ROI kemudian masukkan ke kotak Independent.

 Ø  Klik Statistics, klik Casewise diagnostics, klik All cases. Klik Continue

 Ø  Klik OK, maka hasil output yang didapat pada kolom Coefficients dan Casewise diagnostics adalah sebagai berikut:

 

​            Tabel. Hasil Analisis Regresi Linear Berganda

 

 [![img](F:\penambangan1\docs\tbl1.JPG)](http://2.bp.blogspot.com/-ZSccVz19UAE/TtJeIR_kUNI/AAAAAAAAADs/NAf7oOfRGWY/s1600/tbl1.JPG)

 

 [![img](F:\penambangan1\docs\tbl1_002.JPG)](http://3.bp.blogspot.com/-0iIjAIVmEZU/TtJeXV4NHzI/AAAAAAAAAD0/q-NiIcboIIk/s1600/tbl1.JPG)

 

 Persamaan regresinya sebagai berikut:

 

 Y’ = a + b1X1+ b2X2

 Y’ =  4662,491 + (-74,482)X1 + 692,107X2

 Y’ =  4662,491 - 74,482X1 + 692,107X2

 

 Keterangan:

 Y’        = Harga saham yang diprediksi (Rp)

 a          = konstanta

 b1,b2    = koefisien regresi

 X1        = PER (%)

 X2        = ROI (%)

 

 Persamaan regresi di atas dapat dijelaskan sebagai berikut:

 \- Konstanta sebesar 4662,491; artinya jika PER (X1) dan ROI (X2) nilainya adalah 0, maka harga saham (Y’) nilainya adalah Rp.4662,491.

 \-  Koefisien regresi variabel PER (X1)  sebesar -74,482; artinya jika variabel independen lain nilainya tetap  dan PER mengalami kenaikan 1%, maka harga saham (Y’) akan mengalami  penurunan sebesar Rp.74,482. Koefisien bernilai negatif artinya terjadi  hubungan negatif antara PER dengan harga saham, semakin naik PER maka  semakin turun harga saham. 

 \-  Koefisien regresi variabel ROI (X2)  sebesar 692,107; artinya jika variabel independen lain nilainya tetap  dan ROI mengalami kenaikan 1%, maka harga saham (Y’) akan mengalami  peningkatan sebesar Rp.692,107. Koefisien bernilai positif artinya  terjadi hubungan positif antara ROI dengan harga saham, semakin naik ROI  maka semakin meningkat harga saham.

 

 Nilai  harga saham yang diprediksi (Y’) dapat dilihat pada tabel Casewise  Diagnostics (kolom Predicted Value). Sedangkan Residual (*unstandardized residual*) adalah selisih antara harga saham dengan Predicted Value, dan Std. Residual (*standardized residual*)  adalah nilai residual yang telah terstandarisasi (nilai semakin  mendekati 0 maka model regresi semakin baik dalam melakukan prediksi,  sebaliknya semakin menjauhi 0 atau lebih dari 1 atau -1 maka semakin  tidak baik model regresi dalam melakukan prediksi).