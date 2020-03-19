# DECISION TREES

## Classification

Decision tree membangun model klasifikasi atau regresi dalam bentuk struktur pohon. Ini memecah dataset menjadi himpunan bagian yang lebih kecil dan lebih kecil sementara pada saat yang sama pohon keputusan terkait dikembangkan secara bertahap. Hasil akhirnya adalah pohon dengan simpul keputusan dan simpul daun. Node keputusan (mis., Outlook) memiliki dua atau lebih cabang (mis., Sunny, Overcast, dan Rainy). Node daun (mis., Play) mewakili klasifikasi atau keputusan. Node keputusan teratas dalam pohon yang sesuai dengan prediktor terbaik disebut simpul akar. Pohon keputusan dapat menangani data kategorikal dan numerik.

### Decision Tree terdiri dari:

1. Node: Tes untuk nilai atribut tertentu.
2. Edges / Branch Sesuai dengan hasil tes dan terhubung ke simpul atau daun berikutnya.
3. Leaf Node: Node terminal yang memprediksi hasil (mewakili label kelas atau distribusi kelas).

## Algorithm

Algoritma inti untuk membangun pohon keputusan yang disebut ID3 oleh J. R. Quinlan yang menggunakan pencarian serakah top-down melalui ruang cabang yang mungkin tanpa backtracking. ID3 menggunakan Entropi dan Penguatan Informasi untuk membangun pohon keputusan. Dalam model ZeroR tidak ada prediktor, dalam model OneR kami mencoba menemukan prediktor tunggal terbaik, Bayesian naif mencakup semua prediktor yang menggunakan aturan Bayes dan asumsi independensi antara prediktor, tetapi pohon keputusan mencakup semua prediktor dengan asumsi ketergantungan antara prediktor.

## Entropy

Pohon keputusan dibangun dari atas ke bawah dari simpul akar dan melibatkan mempartisi data ke dalam himpunan bagian yang berisi instance dengan nilai yang sama (homogen). Algoritma ID3 menggunakan entropi untuk menghitung homogenitas sampel. Jika sampel benar-benar homogen, entropinya nol dan jika sampel dibagi rata, entropinya satu.
$$
Entropy(S) = \sum_{i=1}^n {-P_i\log_2{P_i}}
$$
Keterangan :

S = ruang sampel data yang di gunakaan untuk data pelatihan

n = jumlah partisi

Pi = Probability dari Pi terhadap P

## Information Gain

Gain informasi didasarkan pada penurunan entropi setelah dataset dibagi pada atribut. Membangun pohon keputusan adalah tentang menemukan atribut yang mengembalikan perolehan informasi tertinggi (mis., Cabang yang paling homogen).
$$
Gain(S,A) = entropy(S)-\sum_{i=1}^n \frac{|s_i|}{|s|}\quad x \quad entropy(S_i)
$$
Keterangan :

T = ruang sampel data yang di gunakaan untuk data pelatihan

n = jumlah partisi

Si = Probability dari Si terhadap S

#### Data Berikut untuk menghitung Entropy,Gain yang ada di tiap data tersebut menggunakan hitugan manual :

| Customer ID | Gender | Car Type | Shirt Size  | Class |
| ----------- | ------ | -------- | ----------- | ----- |
| 1           | M      | Family   | Small       | C0    |
| 2           | M      | Sports   | Medium      | C0    |
| 3           | M      | Sports   | Medium      | C0    |
| 4           | M      | Sports   | Large       | C0    |
| 5           | M      | Sports   | Extra Large | C0    |
| 6           | M      | Sports   | Extra Large | C0    |
| 7           | F      | Sports   | Small       | C0    |
| 8           | F      | Sports   | Small       | C0    |
| 9           | F      | Sports   | Medium      | C0    |
| 10          | F      | Luxury   | Large       | C0    |
| 11          | M      | Family   | Large       | C1    |
| 12          | M      | Family   | Extra Large | C1    |
| 13          | M      | Family   | Medium      | C1    |
| 14          | M      | Luxury   | Extra Large | C1    |
| 15          | F      | Luxury   | Small       | C1    |
| 16          | F      | Luxury   | Small       | C1    |
| 17          | F      | Luxury   | Medium      | C1    |
| 18          | F      | Luxury   | Medium      | C1    |
| 19          | F      | Luxury   | Medium      | C1    |
| 20          | F      | Luxury   | Large       | C1    |

Kita harus menghitung Entropy terlebih dahulu dengan menggunakan rumus Entropy(S)
$$
P_i = C0 = , P(C0)=P_1 = \frac{10}{20}
$$

$$
P_i = C0 = , P(C1)=P_2 = \frac{10}{20}
$$

$$
Entropy(S) = {-\frac{10}{20}\log_2{\frac{10}{20}}}{-\frac{10}{20}\log_2{\frac{10}{20}}}= 1
$$

Sudah dicari Entropynya = 1 maka selanjutnya mencari tiap Gainnya

Gain  dari Gender dari tiap Value,berikut Rumus untuk menghitung entropy dari tiap value 

Gain dari CarType dari tiap Value,berikut Rumus untuk menghitung entropy dari tiap value

Gain dari Shirt Size dari tiap Value,berikut Rumus untuk menghitung entropy dari tiap value 
$$
Entropy(Male) = {-\frac{6}{10}\log_2{\frac{6}{10}}}{-\frac{4}{10}\log_2{\frac{4}{10}}}=0,97051
$$

$$
Entropy(Female) = {-\frac{4}{10}\log_2{\frac{4}{10}}}{-\frac{6}{10}\log_2{\frac{6}{10}}}=0,97051
$$

$$
Entropy(Family) = {-\frac{1}{4}\log_2{\frac{1}{4}}}{-\frac{3}{4}\log_2{\frac{3}{4}}}=0,81128
$$

$$
Entropy(Sports) = {-\frac{8}{8}\log_2{\frac{8}{8}}}{-\frac{0}{8}\log_2{\frac{0}{8}}}=0
$$

$$
Entropy(Luxury) = {-\frac{1}{8}\log_2{\frac{1}{8}}}{-\frac{7}{8}\log_2{\frac{7}{8}}}=0,54356
$$

$$
Gain(S,CarType) = 1-(\frac{4}{20}X({-\frac{1}{4}\log_2{\frac{1}{4}}}{-\frac{3}{4}\log_2{\frac{3}{4}}})+\frac{8}{20}X({-\frac{8}{8}\log_2{\frac{8}{8}}}{-\frac{0}{8}\log_2{\frac{0}{8}}}+\frac{8}{20}X({-\frac{1}{8}\log_2{\frac{1}{8}}}{-\frac{7}{8}\log_2{\frac{7}{8}}}) = 0,62032
$$

$$
Entropy(Small) = {-\frac{3}{5}\log_2{\frac{3}{5}}}{-\frac{2}{5}\log_2{\frac{2}{5}}}=0,97095
$$

$$
Entropy(Medium) = {-\frac{3}{7}\log_2{\frac{3}{7}}}{-\frac{4}{7}\log_2{\frac{4}{7}}}=0,98523
$$

$$
Entropy(Large) = {-\frac{2}{4}\log_2{\frac{2}{4}}}{-\frac{2}{4}\log_2{\frac{2}{4}}}=1
$$

$$
Entropy(ExtraLarge) = {-\frac{2}{4}\log_2{\frac{2}{4}}}{-\frac{2}{4}\log_2{\frac{2}{4}}}=1
$$

$$
Gain(S,ShirtSize) = 1-(\frac{5}{20}X({-\frac{3}{5}\log_2{\frac{3}{5}}}{-\frac{2}{5}\log_2{\frac{2}{5}}})+\frac{7}{20}X({-\frac{3}{7}\log_2{\frac{3}{7}}}{-\frac{4}{7}\log_2{\frac{4}{7}}}+\frac{4}{20}X({-\frac{2}{4}\log_2{\frac{2}{4}}}{-\frac{2}{4}\log_2{\frac{2}{4}}}+\frac{4}{20}X({-\frac{2}{4}\log_2{\frac{2}{4}}}{-\frac{2}{4}\log_2{\frac{2}{4}}}) = 0,012433
$$

Program untuk menghitung entropy, gain dengan program:

```python
import pandas as pd 
from sklearn.preprocessing import LabelEncoder
from sklearn.tree import DecisionTreeClassifier
from sklearn import tree
data = pd.read_excel("data_informationgain.xlsx")
df = pd.DataFrame(data)
df.style.hide_index()
```

| Customer ID | Gender | Car Type | Shirt Size  | Class |
| ----------- | ------ | -------- | ----------- | ----- |
| 1           | M      | Family   | Small       | C0    |
| 2           | M      | Sports   | Medium      | C0    |
| 3           | M      | Sports   | Medium      | C0    |
| 4           | M      | Sports   | Large       | C0    |
| 5           | M      | Sports   | Extra Large | C0    |
| 6           | M      | Sports   | Extra Large | C0    |
| 7           | F      | Sports   | Small       | C0    |
| 8           | F      | Sports   | Small       | C0    |
| 9           | F      | Sports   | Medium      | C0    |
| 10          | F      | Luxury   | Large       | C0    |
| 11          | M      | Family   | Large       | C1    |
| 12          | M      | Family   | Extra Large | C1    |
| 13          | M      | Family   | Medium      | C1    |
| 14          | M      | Luxury   | Extra Large | C1    |
| 15          | F      | Luxury   | Small       | C1    |
| 16          | F      | Luxury   | Small       | C1    |
| 17          | F      | Luxury   | Medium      | C1    |
| 18          | F      | Luxury   | Medium      | C1    |
| 19          | F      | Luxury   | Medium      | C1    |
| 20          | F      | Luxury   | Large       | C1    |

Merubah label / kolom yang ada di data diatas untuk bisa dihitung dengan
menggunakan code python,yaitu untuk memudahkan pengguna agar bisa 
menghitung code yang nanti akan digunakan . Pada gender hanya 
menggunakan biner (0,1){F,M}. Pada cartype menggunakan inisialisasi 
angka urutan (0,1,2){Familiy,Luxury,Sports} . Pada Shirt Size 
menggunakan inisialisasi angka urutan 
(0,1,2,3){Small,Medium,Large,ExtraLarge}.Berikut codenya

```python
lab= LabelEncoder()
df["gender_n"] = lab.fit_transform(df["Gender"])
df["car_type_n"] = lab.fit_transform(df["Car Type"])
df["shirt_size_n"] = lab.fit_transform(df["Shirt Size"])
df["class_n"] = lab.fit_transform(df["Class"])
df.style.hide_index()
```

| Customer ID | Gender | Car Type | Shirt Size  | Class | gender_n | car_type_n | shirt_size_n | class_n |
| ----------- | ------ | -------- | ----------- | ----- | -------- | ---------- | ------------ | ------- |
| 1           | M      | Family   | Small       | C0    | 1        | 0          | 3            | 0       |
| 2           | M      | Sports   | Medium      | C0    | 1        | 2          | 2            | 0       |
| 3           | M      | Sports   | Medium      | C0    | 1        | 2          | 2            | 0       |
| 4           | M      | Sports   | Large       | C0    | 1        | 2          | 1            | 0       |
| 5           | M      | Sports   | Extra Large | C0    | 1        | 2          | 0            | 0       |
| 6           | M      | Sports   | Extra Large | C0    | 1        | 2          | 0            | 0       |
| 7           | F      | Sports   | Small       | C0    | 0        | 2          | 3            | 0       |
| 8           | F      | Sports   | Small       | C0    | 0        | 2          | 3            | 0       |
| 9           | F      | Sports   | Medium      | C0    | 0        | 2          | 2            | 0       |
| 10          | F      | Luxury   | Large       | C0    | 0        | 1          | 1            | 0       |
| 11          | M      | Family   | Large       | C1    | 1        | 0          | 1            | 1       |
| 12          | M      | Family   | Extra Large | C1    | 1        | 0          | 0            | 1       |
| 13          | M      | Family   | Medium      | C1    | 1        | 0          | 2            | 1       |
| 14          | M      | Luxury   | Extra Large | C1    | 1        | 1          | 0            | 1       |
| 15          | F      | Luxury   | Small       | C1    | 0        | 1          | 3            | 1       |
| 16          | F      | Luxury   | Small       | C1    | 0        | 1          | 3            | 1       |
| 17          | F      | Luxury   | Medium      | C1    | 0        | 1          | 2            | 1       |
| 18          | F      | Luxury   | Medium      | C1    | 0        | 1          | 2            | 1       |
| 19          | F      | Luxury   | Medium      | C1    | 0        | 1          | 2            | 1       |
| 20          | F      | Luxury   | Large       | C1    | 0        | 1          |              |         |

Setelah merubah label menjadi inisialisasi angka (numerik) melanjutkan 
ke code berikutnya untuk bisa dihitung dan code berikut untuk 
penghapusan fitur /label yang tidak diperlukan

```python
inputs = df.drop(["Customer ID","Gender","Car Type","Shirt Size", "Class","class_n"],axis="columns")
target = df["class_n"]
```

Membuat Klasifikasi fitur untuk bisa dibuat Pohon Keputusan (Decision Tree)untuk bisa di classifier .

```py
model = DecisionTreeClassifier(criterion="entropy",random_state=100)
model.fit(inputs,target)
```

DecisionTreeClassifier(class_weight=None, criterion='entropy', max_depth=None,
max_features=None, max_leaf_nodes=None,
min_impurity_decrease=0.0, min_impurity_split=None,
min_samples_leaf=1, min_samples_split=2,
min_weight_fraction_leaf=0.0, presort=False,
random_state=100, splitter='best')

```python
from matplotlib import pyplot as plt
tree.plot_tree(model.fit(inputs,target), max_depth=None, feature_names=["Customer ID","Gender","Car Type","Shirt Size"],class_names=["C0","C1"], label="all", filled=True, impurity=True, node_ids=True, proportion=True, rotate=True, rounded=True, precision=3, ax=None, fontsize=None)

```

<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {inlineMath: [['$$','$$']]}
});
</script>
  <script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>