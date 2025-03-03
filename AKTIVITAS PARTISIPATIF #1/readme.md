a. Memanggil Data
Langkah pertama adalah membaca dataset dari file Excel yang telah diunggah ke sistem menggunakan `pd.read_excel()`. Data kemudian disimpan dalam variabel `df` agar dapat digunakan dalam analisis lebih lanjut.

b. Menampilkan Data
Setelah data dimuat, 5 baris pertama ditampilkan menggunakan `df.head()`. Ini bertujuan untuk memahami struktur dataset, termasuk jenis kolom dan beberapa contoh nilai yang terdapat di dalamnya.

c. Preprocessing Data
Langkah ini diawali dengan pengecekan jumlah nilai kosong menggunakan `df.isnull().sum()`, yang bertujuan untuk mengetahui apakah ada data yang hilang. Jika ditemukan nilai kosong, maka penanganannya dilakukan sesuai dengan tipe data dari kolom tersebut. Untuk kolom bertipe kategorikal (string), nilai kosong diisi dengan modus atau nilai yang paling sering muncul dalam kolom tersebut. Sedangkan untuk kolom bertipe numerik, nilai kosong diisi dengan median untuk menghindari pengaruh dari outlier yang dapat mengganggu distribusi data.

d. Mengubah Semua Kolom Menjadi Numerik
Agar data dapat digunakan oleh model machine learning, semua kolom harus dikonversi ke dalam bentuk numerik. `LabelEncoder` digunakan untuk mengubah nilai dalam kolom bertipe string menjadi angka. Jika ditemukan kolom yang memiliki campuran tipe data antara angka dan teks, maka semua nilai dalam kolom tersebut terlebih dahulu dikonversi ke string sebelum dilakukan encoding. Hal ini dilakukan untuk menghindari error akibat perbedaan tipe data dalam satu kolom.

e. Normalisasi Data
Tahap terakhir adalah melakukan normalisasi menggunakan `MinMaxScaler()`, yang mengubah semua nilai dalam dataset ke dalam rentang 0 hingga 1. Normalisasi ini penting agar setiap fitur memiliki skala yang sama, sehingga model machine learning dapat bekerja lebih optimal tanpa bias terhadap fitur dengan skala yang lebih besar. Setelah proses normalisasi selesai, hasil akhirnya ditampilkan menggunakan `df_scaled.head()` untuk memastikan bahwa proses telah berjalan dengan baik.