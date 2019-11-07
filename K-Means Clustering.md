# K-Means Clustering

## Pendahuluan

K-Means salah satu metode penganalisaan data yang melakukan proses pemodelan tanpa supervisi (unsupervised) dan merupakan 
salah satu metode yang melakukan pengelompokan data dengan sistem 
partisi.

untuk mencapai ini, kita akan menggunakan algoritma K-Means; algoritma pembelajaran tanpa pengawasan.

## Algoritma

Algoritma K-Means Clustering akan mengkategorikan item ke dalam kelompok k kesamaan.  Untuk menghitung kesamaan itu, akan menggunakan jarak euclidean sebagai pengukuran.

Algoritma bekerja sebagai berikut:

1. menentukan jumlah cluster
2. menginisialisasi poin k secara acak ke dalam cluster
3. menghitung rata-rata yang dari setiap cluster
4. mengelompokkan masing-masing data ke dalam rata-rata terdekat
5. mengulangi langkah ketiga sampai tidak ada data yeng berpindah ketika rata-rata selesai dihitung.

## Langkah-langkah untuk melakukan K-Means Clustering

Langkah-langkah akan dilakukan tanpa mengimport library apapun. jadi pada tugas kali ini, akan melakukan coding murni menggunakan bahasa pemograman Python.

1. Membaca data

   program menerima input dari file sebagai text ('.txt').  Setiap baris mewakili suatu item, dan itu berisi nilai numerik (satu untuk setiap fitur) dibagi dengan koma.  

   ```html
   5.1,3.5,1.4,0.2,Iris-setosa
   4.9,3.0,1.4,0.2,Iris-setosa
   4.7,3.2,1.3,0.2,Iris-setosa
   4.6,3.1,1.5,0.2,Iris-setosa
   5.0,3.6,1.4,0.2,Iris-setosa
   5.4,3.9,1.7,0.4,Iris-setosa
   4.6,3.4,1.4,0.3,Iris-setosa
   5.0,3.4,1.5,0.2,Iris-setosa
   4.4,2.9,1.4,0.2,Iris-setosa
   4.9,3.1,1.5,0.1,Iris-setosa
   5.4,3.7,1.5,0.2,Iris-setosa
   4.8,3.4,1.6,0.2,Iris-setosa
   4.8,3.0,1.4,0.1,Iris-setosa
   4.3,3.0,1.1,0.1,Iris-setosa
   5.8,4.0,1.2,0.2,Iris-setosa
   5.7,4.4,1.5,0.4,Iris-setosa
   5.4,3.9,1.3,0.4,Iris-setosa
   5.1,3.5,1.4,0.3,Iris-setosa
   5.7,3.8,1.7,0.3,Iris-setosa
   5.1,3.8,1.5,0.3,Iris-setosa
   5.4,3.4,1.7,0.2,Iris-setosa
   5.1,3.7,1.5,0.4,Iris-setosa
   4.6,3.6,1.0,0.2,Iris-setosa
   5.1,3.3,1.7,0.5,Iris-setosa
   4.8,3.4,1.9,0.2,Iris-setosa
   5.0,3.0,1.6,0.2,Iris-setosa
   5.0,3.4,1.6,0.4,Iris-setosa
   5.2,3.5,1.5,0.2,Iris-setosa
   5.2,3.4,1.4,0.2,Iris-setosa
   4.7,3.2,1.6,0.2,Iris-setosa
   4.8,3.1,1.6,0.2,Iris-setosa
   5.4,3.4,1.5,0.4,Iris-setosa
   5.2,4.1,1.5,0.1,Iris-setosa
   5.5,4.2,1.4,0.2,Iris-setosa
   4.9,3.1,1.5,0.1,Iris-setosa
   5.0,3.2,1.2,0.2,Iris-setosa
   5.5,3.5,1.3,0.2,Iris-setosa
   4.9,3.1,1.5,0.1,Iris-setosa
   4.4,3.0,1.3,0.2,Iris-setosa
   5.1,3.4,1.5,0.2,Iris-setosa
   5.0,3.5,1.3,0.3,Iris-setosa
   4.5,2.3,1.3,0.3,Iris-setosa
   4.4,3.2,1.3,0.2,Iris-setosa
   5.0,3.5,1.6,0.6,Iris-setosa
   5.1,3.8,1.9,0.4,Iris-setosa
   4.8,3.0,1.4,0.3,Iris-setosa
   5.1,3.8,1.6,0.2,Iris-setosa
   4.6,3.2,1.4,0.2,Iris-setosa
   5.3,3.7,1.5,0.2,Iris-setosa
   5.0,3.3,1.4,0.2,Iris-setosa
   7.0,3.2,4.7,1.4,Iris-versicolor
   6.4,3.2,4.5,1.5,Iris-versicolor
   6.9,3.1,4.9,1.5,Iris-versicolor
   5.5,2.3,4.0,1.3,Iris-versicolor
   6.5,2.8,4.6,1.5,Iris-versicolor
   5.7,2.8,4.5,1.3,Iris-versicolor
   6.3,3.3,4.7,1.6,Iris-versicolor
   4.9,2.4,3.3,1.0,Iris-versicolor
   6.6,2.9,4.6,1.3,Iris-versicolor
   5.2,2.7,3.9,1.4,Iris-versicolor
   5.0,2.0,3.5,1.0,Iris-versicolor
   5.9,3.0,4.2,1.5,Iris-versicolor
   6.0,2.2,4.0,1.0,Iris-versicolor
   6.1,2.9,4.7,1.4,Iris-versicolor
   5.6,2.9,3.6,1.3,Iris-versicolor
   6.7,3.1,4.4,1.4,Iris-versicolor
   5.6,3.0,4.5,1.5,Iris-versicolor
   5.8,2.7,4.1,1.0,Iris-versicolor
   6.2,2.2,4.5,1.5,Iris-versicolor
   5.6,2.5,3.9,1.1,Iris-versicolor
   5.9,3.2,4.8,1.8,Iris-versicolor
   6.1,2.8,4.0,1.3,Iris-versicolor
   6.3,2.5,4.9,1.5,Iris-versicolor
   6.1,2.8,4.7,1.2,Iris-versicolor
   6.4,2.9,4.3,1.3,Iris-versicolor
   6.6,3.0,4.4,1.4,Iris-versicolor
   6.8,2.8,4.8,1.4,Iris-versicolor
   6.7,3.0,5.0,1.7,Iris-versicolor
   6.0,2.9,4.5,1.5,Iris-versicolor
   5.7,2.6,3.5,1.0,Iris-versicolor
   5.5,2.4,3.8,1.1,Iris-versicolor
   5.5,2.4,3.7,1.0,Iris-versicolor
   5.8,2.7,3.9,1.2,Iris-versicolor
   6.0,2.7,5.1,1.6,Iris-versicolor
   5.4,3.0,4.5,1.5,Iris-versicolor
   6.0,3.4,4.5,1.6,Iris-versicolor
   6.7,3.1,4.7,1.5,Iris-versicolor
   6.3,2.3,4.4,1.3,Iris-versicolor
   5.6,3.0,4.1,1.3,Iris-versicolor
   5.5,2.5,4.0,1.3,Iris-versicolor
   5.5,2.6,4.4,1.2,Iris-versicolor
   6.1,3.0,4.6,1.4,Iris-versicolor
   5.8,2.6,4.0,1.2,Iris-versicolor
   5.0,2.3,3.3,1.0,Iris-versicolor
   5.6,2.7,4.2,1.3,Iris-versicolor
   5.7,3.0,4.2,1.2,Iris-versicolor
   5.7,2.9,4.2,1.3,Iris-versicolor
   6.2,2.9,4.3,1.3,Iris-versicolor
   5.1,2.5,3.0,1.1,Iris-versicolor
   5.7,2.8,4.1,1.3,Iris-versicolor
   6.3,3.3,6.0,2.5,Iris-virginica
   5.8,2.7,5.1,1.9,Iris-virginica
   7.1,3.0,5.9,2.1,Iris-virginica
   6.3,2.9,5.6,1.8,Iris-virginica
   6.5,3.0,5.8,2.2,Iris-virginica
   7.6,3.0,6.6,2.1,Iris-virginica
   4.9,2.5,4.5,1.7,Iris-virginica
   7.3,2.9,6.3,1.8,Iris-virginica
   6.7,2.5,5.8,1.8,Iris-virginica
   7.2,3.6,6.1,2.5,Iris-virginica
   6.5,3.2,5.1,2.0,Iris-virginica
   6.4,2.7,5.3,1.9,Iris-virginica
   6.8,3.0,5.5,2.1,Iris-virginica
   5.7,2.5,5.0,2.0,Iris-virginica
   5.8,2.8,5.1,2.4,Iris-virginica
   6.4,3.2,5.3,2.3,Iris-virginica
   6.5,3.0,5.5,1.8,Iris-virginica
   7.7,3.8,6.7,2.2,Iris-virginica
   7.7,2.6,6.9,2.3,Iris-virginica
   6.0,2.2,5.0,1.5,Iris-virginica
   6.9,3.2,5.7,2.3,Iris-virginica
   5.6,2.8,4.9,2.0,Iris-virginica
   7.7,2.8,6.7,2.0,Iris-virginica
   6.3,2.7,4.9,1.8,Iris-virginica
   6.7,3.3,5.7,2.1,Iris-virginica
   7.2,3.2,6.0,1.8,Iris-virginica
   6.2,2.8,4.8,1.8,Iris-virginica
   6.1,3.0,4.9,1.8,Iris-virginica
   6.4,2.8,5.6,2.1,Iris-virginica
   7.2,3.0,5.8,1.6,Iris-virginica
   7.4,2.8,6.1,1.9,Iris-virginica
   7.9,3.8,6.4,2.0,Iris-virginica
   6.4,2.8,5.6,2.2,Iris-virginica
   6.3,2.8,5.1,1.5,Iris-virginica
   6.1,2.6,5.6,1.4,Iris-virginica
   7.7,3.0,6.1,2.3,Iris-virginica
   6.3,3.4,5.6,2.4,Iris-virginica
   6.4,3.1,5.5,1.8,Iris-virginica
   6.0,3.0,4.8,1.8,Iris-virginica
   6.9,3.1,5.4,2.1,Iris-virginica
   6.7,3.1,5.6,2.4,Iris-virginica
   6.9,3.1,5.1,2.3,Iris-virginica
   5.8,2.7,5.1,1.9,Iris-virginica
   6.8,3.2,5.9,2.3,Iris-virginica
   6.7,3.3,5.7,2.5,Iris-virginica
   6.7,3.0,5.2,2.3,Iris-virginica
   6.3,2.5,5.0,1.9,Iris-virginica
   6.5,3.0,5.2,2.0,Iris-virginica
   6.2,3.4,5.4,2.3,Iris-virginica
   5.9,3.0,5.1,1.8,Iris-virginica
   ```

   

   Program akan membaca data dari file, menyimpannya ke dalam daftar.  Setiap elemen daftar adalah daftar lain yang berisi nilai item untuk fitur.  Program melakukan ini dengan fungsi berikut: 

   ```python
   def ReadData(fileName): 
        # Read the file, splitting by lines 
         f = open (fileName, 'r' ); 
         lines = f.read().splitlines(); 
        f.close(); 
         items = []; 
         for i in range ( 1 , len (lines)): 
             line = lines[i].split( ',' ); 
             itemFeatures = []; 
             for j in range ( len (line) - 1 ): 
                 v = float (line[j]); # Convert feature value to float 
                itemFeatures.append(v); # Add feature value to dict 
            items.append(itemFeatures);
        shuffle(items); 
         return items; 
   ```

   

2. Inisialisasi poin K yang dipilih secara acak

   Program akan menginisialisasi masing-masing nilai rata-rata dalam kisaran nilai fitur item.  Untuk itu, program perlu menemukan min dan maks untuk setiap fitur.  Program mencapainya dengan fungsi berikut:

   ```python
   def FindColMinMax(items): 
         n = len (items[ 0 ]); 
         minima = [sys.maxint for i in range (n)]; 
         maxima = [ - sys.maxint - 1 for i in range (n)]; 
         for item in items: 
             for f in range ( len (item)): 
                 if (item[f] < minima[f]): 
                     minima[f] = item[f]; 
                 if (item[f] > maxima[f]): 
                     maxima[f] = item[f]; 
     return minima,maxima; 
   ```

   Variabel *minima, maxima* adalah daftar yang berisi nilai min dan max masing-masing item.  Program menginisialisasi setiap nilai fitur rata-rata secara acak antara minimum dan maksimum yang sesuai pada dua daftar di atas:

   ```python
   def InitializeMeans(items, k, cMin, cMax): 
        # Initialize means to random numbers between 
        # the min and max of each column/feature 
         f = len (items[ 0 ]); # number of features 
         means = [[ 0 for i in range (f)] for j in range (k)]; 
         for mean in means: 
             for i in range ( len (mean)): 
                # Set value to a random float 
                # (adding +-1 to avoid a wide placement of a mean) 
                 mean[i] = uniform(cMin[i] + 1 , cMax[i] - 1 ); 
         return means; 
   ```

   

3. Menghitung jarak Euclidean

   Program akan menggunakan jarak euclidean sebagai metrik kesamaan untuk set data kami (catatan: tergantung pada item Anda, Anda dapat menggunakan metrik kesamaan lainnya).

   ```python
   def EuclideanDistance(x, y): 
         S = 0 ; #  The sum of the squared differences of the elements 
         for i in range ( len (x)): 
             S + = math.  pow (x[i] - y[i], 2 ); 
    
         return math.sqrt(S); #The square root of the sum 
   ```

   

4. Menghitung rata-rata

   ```python
   def UpdateMean(n,mean,item): 
         for i in range ( len (mean)): 
             m = mean[i]; 
             m = (m * (n - 1 ) + item[i]) / float (n); 
             mean[i] = round (m, 3 ); 
        
         return mean; 
   ```

   

5. Klasifikasi Item

   ```python
   def Classify(means,item): 
        # Classify item to the mean with minimum distance 
         minimum = sys.maxint; 
         index = - 1 ; 
         for i in range ( len (means)): 
            # Find distance from item to mean 
             dis = EuclideanDistance(item, means[i]); 
             if (dis < minimum): 
                 minimum = dis; 
                 index = i; 
         index; return index; 
   
   
   ```

   

6. Menghitung kembali rata-rata cluster

   Untuk  benar-benar menemukan rata-rata, program akan mengulang semua item,  mengklasifikasikannya ke kluster terdekat dan memperbarui rata-rata  klaster.  Program akan mengulangi proses untuk beberapa iterasi tetap.   Jika antara dua iterasi tidak ada perubahan item klasifikasi, program menghentikan proses sebagai algoritma telah menemukan solusi optimal. 

    Fungsi di bawah ini diambil sebagai input *k* (jumlah klaster yang diinginkan), item dan jumlah iterasi maksimum, dan mengembalikan sarana dan kluster.  Klasifikasi item disimpan dalam array milik *To* dan jumlah item dalam sebuah cluster disimpan di *Ukuran cluster* .

   ```python
   def CalculateMeans(k,items,maxIterations = 100000 ): 
    
        # Find the minima and maxima for columns 
         cMin, cMax = FindColMinMax(items); 
        
        # Initialize means at random points 
         means = InitializeMeans(items,k,cMin,cMax); 
        
        # Initialize clusters, the array to hold 
        # the number of items in a class 
         clusterSizes = [ 0 for i in range ( len (means))]; 
    
        # An array to hold the cluster an item is in 
         belongsTo = [ 0 for i in range ( len (items))]; 
    
        # Calculate means 
         for e in range (maxIterations): 
    
            # If no change of cluster occurs, halt 
             noChange = True ; 
             for i in range ( len (items)): 
    
                 item = items[i]; 
    
                # Classify item into a cluster and update the 
                # corresponding means. 
                 index = Classify(means,item); 
    
                 clusterSizes[index] + = 1 ; 
                 cSize = clusterSizes[index]; 
                 means[index] = UpdateMean(cSize,means[index],item); 
    
                # Item changed cluster 
                 if (index ! = belongsTo[i]): 
                     noChange = False ; 
    
                 belongsTo[i] = index; 
    
            # Nothing changed, return 
             if (noChange): 
                 break ; 
    
         return means; 
   ```

7. Klasifikasi item ke cluster terdekat

   Program akan mengulangi semua item dan akan mengklasifikasikan setiap item ke kluster terdekat.

   ```python
   def FindClusters(means,items): 
         clusters = [[] for i in range ( len (means))]; # Init clusters 
        
         for item in items: 
    
            # Classify item into a cluster 
             index = Classify(means,item); 
    
            # Add item to cluster 
            clusters[index].append(item); 
    
         clusters; return clusters; 
   ```

   

