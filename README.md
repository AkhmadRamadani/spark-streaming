
## Spark Streaming

##  Perbedaan spark streaming dengan metode stateless dan stateful stream processing
```sh
Spark Streaming adalah komponen dari Apache Spark yang dirancang untuk memproses aliran data secara real-time. Dalam Spark Streaming, ada dua metode pengolahan aliran data yang umum digunakan, yaitu stateless (tanpa status) dan stateful (dengan status). Berikut adalah penjelasan perbedaan antara keduanya:

1.  Stateless Stream Processing: Stateless stream processing adalah pendekatan di mana setiap record (data) dalam aliran diperlakukan secara independen. Setiap record diolah secara terpisah tanpa mempertimbangkan informasi dari record sebelumnya atau dari aliran data secara keseluruhan. Stateless stream processing tidak mempertahankan keadaan atau status apa pun antara batch yang berbeda.

Contoh penggunaan stateless stream processing adalah saat Anda perlu menerapkan transformasi sederhana, seperti pemetaan (mapping) atau filter, pada setiap record dalam aliran data secara terpisah. Setiap record dianggap sebagai entitas terpisah yang tidak bergantung pada record sebelumnya.

2.  Stateful Stream Processing: Stateful stream processing melibatkan pemeliharaan status atau keadaan (state) yang terkait dengan aliran data. Ini berarti setiap record diolah dengan mempertimbangkan informasi dari record sebelumnya dan status global dari aliran data. Status ini dapat berupa nilai terkini, jumlah akumulasi, atau keadaan lain yang relevan.

Dalam stateful stream processing, data yang tiba di aliran diperlakukan sebagai bagian dari urutan yang lebih besar, dan status diperbarui secara berkelanjutan sesuai dengan record baru yang tiba. Hal ini memungkinkan analisis yang lebih kompleks, seperti perhitungan jendela waktu (windowed computations) atau analisis tren.
```
## Penjelasan Sintaks
  ```sh
  -   `sys.argv`: Mengacu pada daftar argumen baris perintah yang diberikan saat menjalankan program. Ini digunakan untuk membaca argumen yang diberikan kepada program Spark Streaming.
-   `sys.stderr`: Merujuk ke objek aliran standar kesalahan (stderr). Ini digunakan untuk menulis pesan kesalahan atau informasi di output standar kesalahan.
-   `StreamingContext`: Kelas inti dalam Spark Streaming yang menginisialisasi konteks streaming dengan konfigurasi dan waktu batch tertentu.
-   `sc`: Merujuk ke objek konteks Spark (SparkContext) yang digunakan dalam Spark Streaming.
-   `socketTextStream`: Metode dalam objek StreamingContext yang menginisialisasi sumber aliran data dengan menggunakan soket. Ini membaca data baris demi baris dari soket yang ditentukan.
-   `reduceByKey`: Metode dalam DStream (objek aliran) yang menggabungkan nilai-nilai yang sesuai dengan kunci yang sama menggunakan fungsi pengurangan.
-   `lambda line`: Ini adalah ekspresi lambda yang digunakan dalam operasi transformasi pada aliran data. Di sini, "line" adalah parameter yang mewakili setiap baris data dalam aliran.
-   `awaitTermination`: Metode dalam objek StreamingContext yang memulai eksekusi aliran dan memblokir pemanggil hingga streaming dihentikan secara manual atau karena kesalahan.

-   `nc`: Merujuk ke objek Netcat, yang digunakan sebagai sumber data dalam contoh kode tersebut.
-   `lk`: Merupakan singkatan dari "listen key" yang mengacu pada kunci yang digunakan dalam aliran data untuk mengelompokkan atau mengurutkan data.

-   `spark-submit`: Perintah yang digunakan untuk mengirimkan aplikasi Spark ke cluster untuk dieksekusi.
-   `master`: Parameter dalam perintah spark-submit yang digunakan untuk menentukan "master" atau URL manajer cluster yang digunakan untuk menjalankan aplikasi Spark (misalnya, local[*], yarn, dll.).
-   `local[*]`: Nilai yang diberikan kepada parameter "master" yang menunjukkan penggunaan mode lokal pada satu mesin dengan menggunakan semua inti prosesor yang tersedia.

-   `ssc.checkpoint`: Metode dalam objek StreamingContext yang mengatur titik kontrol (checkpoint) untuk StreamingContext. Titik kontrol digunakan untuk mempertahankan keadaan aliran data yang sedang diproses dan memungkinkan pemulihan jika ada kegagalan.
-   `parallelize`: Metode dalam objek SparkContext (sc) yang membuat RDD (Resilient Distributed Dataset) dari koleksi yang ada di dalam program.
-   `updateStateByKey`: Metode dalam DStream yang digunakan untuk memelihara keadaan (state) dengan memperbarui nilai state berdasarkan kunci (key) yang sesuai.
-   `flatMap`: Metode dalam DStream atau RDD yang menghasilkan output baru dengan menerapkan fungsi ke setiap elemen dan mengembalikan nol atau lebih hasil.

-   `rdd.take(5)`: Metode dalam RDD yang mengembalikan array yang berisi n elemen pertama dari RDD.
-   `transform`: Metode dalam DStream yang digunakan untuk mengubah setiap RDD dalam DStream dengan menerapkan fungsi transformasi.
-   `rdd.sortByKey(False)`: Metode dalam RDD yang mengurutkan elemen berdasarkan kunci (key). Nilai boolean `False` menunjukkan pengurutan dalam urutan menurun (descending).
  ```

## Screenshot Hasil
<table>
  <tr align="center">
    <td>
    Praktik Dasar Spark Streaming (stateless)
    <td> 
      <img src="https://github.com/AkhmadRamadani/spark-streaming/blob/main/images/WhatsApp%20Image%202023-06-20%20at%2010.27.27.jpeg?raw=true"><br><br>
      <img src="https://github.com/AkhmadRamadani/spark-streaming/blob/main/images/WhatsApp%20Image%202023-06-20%20at%2010.27.27%20(1).jpeg?raw=true">
      <br><br>
    </td>
    </td>
    </tr>
    <tr align="center">
    <td>    
    Praktik Dasar Spark Streaming (stateful)
    <td>
      <img src="https://github.com/AkhmadRamadani/spark-streaming/blob/main/images/WhatsApp%20Image%202023-06-20%20at%2010.27.27.jpeg?raw=true" width=80% height=80%><br><br>
      <img src="https://github.com/AkhmadRamadani/spark-streaming/blob/main/images/WhatsApp%20Image%202023-06-20%20at%2010.27.28%20(1).jpeg?raw=true" width=80% height=80%><br><br>
  </td>
    </td>
    </tr>
    <tr align="center">
    <td>
     Melakukan Transformasi di Spark Streaming (transformasi word sentiment)
    <td>
      <img src="https://github.com/AkhmadRamadani/spark-streaming/blob/main/images/WhatsApp%20Image%202023-06-20%20at%2010.27.27%20(2).jpeg?raw=true" width=80% height=80%><br><br>
      <img src="https://raw.githubusercontent.com/AkhmadRamadani/spark-streaming/main/images/a62bd724-66c0-4241-8fd5-c6f178714be4.jpeg" width=80% height=80%><br><br>
  </td>
    </td>
    </tr>
 </table>
