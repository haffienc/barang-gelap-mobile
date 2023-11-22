# Barang Gelap Mobile.

# Tugas 7
#### 1. Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?
- Stateless Widget:
    - Stateless widget adalah jenis widget yang tidak memiliki data berubah (state) di dalamnya. Ini berarti tampilan widget ini tetap konstan dan tidak berubah sepanjang siklus hidupnya.
    - Stateless widget umumnya digunakan untuk tampilan yang tidak memerlukan perubahan data atau interaksi pengguna yang kompleks.
    - Ketika menggunakan stateless widget, setiap kali ingin memperbarui tampilan, kita harus membuat widget baru dengan properti yang berbeda.
- Stateful Widget:
    - Stateful widget adalah jenis widget yang memiliki data yang dapat berubah (state) di dalamnya. Data ini dapat diperbarui selama siklus hidup widget.
    - Stateful widget umumnya digunakan untuk tampilan yang memerlukan pembaruan data atau interaksi pengguna yang kompleks, seperti formulir atau daftar item yang dapat digulir.
    - Ketika data di dalam stateful widget berubah, widget tersebut dapat membangun kembali tampilan secara otomatis.

#### 2. Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.
- **Scaffold**: Scaffold adalah widget yang digunakan sebagai kerangka dasar untuk halaman aplikasi. Ia mengatur elemen-elemen seperti AppBar dan body, membuat tata letak umum untuk halaman.
- **AppBar**: AppBar adalah bagian atas halaman yang menampilkan judul aplikasi. Ini memberikan ruang untuk menampilkan judul aplikasi dan ikon lainnya.
- **SingleChildScrollView**: SingleChildScrollView adalah widget yang digunakan untuk membuat halaman dapat digulir. Ini berguna ketika konten halaman melebihi ukuran layar sehingga pengguna dapat menggulir ke bawah untuk melihat lebih banyak konten.
- **Padding**: Padding adalah widget yang digunakan untuk menambahkan ruang kosong (padding) di sekitar elemen-elemen dalam tata letak. Ini membantu dalam mengatur jarak antara elemen-elemen.
- **Column**: Column adalah widget yang digunakan untuk menata elemen-elemen secara vertikal. Ini memungkinkan penempatan beberapa widget dalam satu kolom.
- **GridView.count**: GridView adalah widget yang digunakan untuk menampilkan elemen dalam bentuk grid. Dalam kasus ini, GridView.count digunakan untuk membuat grid dengan jumlah kolom yang tetap.
- **InkWell**: InkWell adalah widget yang digunakan untuk membuat area yang responsif terhadap sentuhan pengguna. Ketika digunakan dalam tampilan item, ini memungkinkan item tersebut merespons ketika diklik.
- **Material**: Material adalah widget yang digunakan untuk memberikan latar belakang berwarna pada tampilan item dalam bentuk kartu.
- **SnackBar**: SnackBar adalah widget yang digunakan untuk menampilkan pesan singkat kepada pengguna ketika sesuatu terjadi, seperti ketika salah satu item di klik. Ini memberikan umpan balik singkat kepada pengguna.
- **Text**: Text adalah widget yang digunakan untuk menampilkan teks. Dalam aplikasi ini, digunakan untuk menampilkan judul dan nama item.
- **Icon**: Widget Icon digunakan untuk menampilkan ikon pada tampilan item di dalam grid. Ikon ini dapat bervariasi sesuai dengan item yang direpresentasikan. 

#### 3. Step by Step
- Buat file baru bernama `menu.dart` dalam direktori `barang_gelap/lib` dan pindahkan kode class `MyHomePage` ke file `menu.dart`.
- Tambahkan import `package:barang_gelap/menu.dart` di awal file `main.dart` untuk mengatasi masalah class MyHomePage yang dipindahkan.
- Mengubah widget halaman menu dari **stateful** menjadi **stateless** dengan menghapus parameter title pada `MyHomePage` di `menu.dart` dan menghapus fungsi `State`.
- Menambahkan class `ShopItem` dengan atribut nama, icon, dan color agar nantinya memungkinkan implementasi warna yang berbeda tiap card. **(Bonus)**
- Menambahkan daftar menu dalam bentuk list `ShopItem` di `menu.dart`.
- Menambahkan kode untuk menampilkan teks dan card yang mewakili barang-barang yang dijual di dalam method build di `menu.dart`.
- Membuat widget stateless baru dengan nama `ShopCard` untuk menampilkan setiap card barang di dalam grid layout.
- Mengimplementasikan tampilan card dengan ikon dan teks, serta menambahkan fungsi onTap untuk menampilkan `SnackBar` ketika card di-tap.

# Tugas 8
#### 1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai contoh!
- `Navigator.push()`: **Menambahkan halaman baru ke tumpukan navigasi, memungkinkan pengguna untuk kembali ke halaman sebelumnya.**
    - Misal pada aplikasi dengan halaman daftar item, dan ketika pengguna memilih salah satu item, kita ingin menavigasikannya ke halaman detail item. Dalam hal ini, `Navigator.push()` akan sesuai karena kita ingin menambahkan halaman detail ke tumpukan navigasi dan membiarkan pengguna kembali ke halaman daftar.
```dart
Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => DetailItemPage(selectedItem)),
);
```

- `Navigator.pushReplacement()`: **Menambahkan halaman baru dan menggantikan halaman saat ini dalam tumpukan, mencegah pengguna untuk kembali ke halaman sebelumnya.**
    - Misal pada formulir login, setelah pengguna berhasil login, halaman login akan digantikan dengan halaman beranda. Dalam hal ini, kita menggunakan `Navigator.pushReplacement()` agar pengguna tidak dapat kembali ke halaman login setelah login berhasil.
```dart
Navigator.pushReplacement(
  context,
  MaterialPageRoute(builder: (context) => BerandaPage()),
);
```

#### 2. Jelaskan masing-masing layout widget pada Flutter dan Konteks Penggunaannya masing-masing!
- Container:
    - **Deskripsi**: Container adalah widget yang dapat mengandung widget lain dan memberikan kontrol atas properti seperti padding, margin, dan dekorasi.
    - **Konteks Penggunaan**: Digunakan untuk mengelompokkan dan mengatur widget lain dengan memberikan properti seperti padding, margin, dan dekorasi.

- Column:
    - **Deskripsi**: Column adalah widget yang mengatur anak-anaknya dalam kolom vertikal.
    - **Konteks Penggunaan**: Berguna ketika Anda ingin menyusun widget secara vertikal, seperti dalam daftar atau tata letak kolom pada layar.

- Row:
    - **Deskripsi**: Row adalah widget yang mengatur anak-anaknya dalam baris horizontal.
    - **Konteks Penggunaan**: Cocok untuk menyusun widget secara horizontal, seperti dalam baris tombol atau tata letak baris pada layar.

- ListView:
    - **Deskripsi**: ListView adalah widget yang menyusun anak-anaknya dalam daftar bergulir.
    - **Konteks Penggunaan**: Ideal untuk menampilkan daftar elemen yang mungkin lebih besar dari layar, seperti daftar kontak atau pesan.

- GridView:
    - **Deskripsi**: GridView adalah widget yang menyusun anak-anaknya dalam bentuk grid.
    - **Konteks Penggunaan**: Berguna ketika Anda ingin menampilkan elemen dalam bentuk grid, seperti galeri gambar atau tampilan produk.

- Stack:
    - **Deskripsi**: Stack adalah widget yang menyusun anak-anaknya secara tumpuk, satu di atas yang lain.
    - **Konteks Penggunaan**: Digunakan untuk menyusun widget secara bersamaan, seperti tumpukan kartu atau tata letak lapisan pada layar.

#### 3. Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan alasannya!
- `TextFormField` digunakan untuk mengambil input teks seperti nama, harga, dan deskripsi. 
    - Memiliki dukungan untuk validasi input melalui properti `validator`, memastikan bahwa data yang dimasukkan sesuai dengan aturan yang diinginkan.
    - Memungkinkan untuk menyesuaikan tampilan input, seperti menambahkan placeholder, label, dan border melalui properti `decoration`.
- `ElevatedButton` digunakan untuk memicu aksi simpan formulir. 
    - Memberikan tombol yang dapat diklik untuk memicu aksi terkait formulir, dalam hal ini, menyimpan data produk ke daftar.

#### 4. Bagaimana penerapan clean architecture pada aplikasi Flutter?
Penerapan **Clean Architecture** pada aplikasi Flutter melibatkan pemisahan kode ke dalam lapisan-lapisan yang berbeda, dengan setiap lapisan memiliki tanggung jawab dan aturan tertentu. Berikut adalah tiga lapisan utama **Clean Architecture** dan penerapannya dalam konteks Flutter:

##### 1. Domain Layer:
**Entities**: Model objek bisnis.
**Repositories**: Interface untuk mengakses data.
**Use Cases / Interactors**: Aturan bisnis aplikasi.

##### 2. Data Layer:
**Repositories Implementations**: Implementasi dari repository untuk mendapatkan data dari sumber eksternal.
**Data Models**: Representasi data yang diperoleh dari sumber eksternal.

##### 3. Presentation Layer:
**UI (User Interface)**: Menampilkan informasi dan menerima input dari pengguna.
**ViewModels / Presenters**: Mengelola logika presentasi dan berinteraksi dengan use cases.
**Dependency Injection (DI)**: Menggunakan DI untuk menyediakan dependensi pada lapisan Presentation.

#### 5. Step by Step
- Menambah Drawer Menu untuk Navigasi
    - Membuat folder `widgets` berisikan `left_drawer.dart`.
    - Impor untuk halaman-halaman yang kita ingin masukkan navigasinya ke dalam `left_drawer.dart`.
    - Memasukkan routing untuk halaman-halaman yang kita impor.
    - Memasukkan drawer tersebut ke halaman yang ingin kamu tambahkan drawer (`menu.dart`, `shoplist_form.dart`, dan `shoplist_items.dart`)
    - Menghias drawer.
- Menambahkan Form dan Elemen Input
    - Membuat folder `screens` dengan file baru `shoplist_form.dart`.
    - Membuat widget `TextFormField` untuk input dan `ElevatedButton` untuk tombol submit.
- Memunculkan Data
    - Menambahkan fungsi `showDialog()` di bagian `onPressed()` pada widget `ElevatedButton` dan munculkan widget `AlertDialog`
    berisikan detail (nama, price, deskripsi) dari product.
- Bonus
    - Membuat List baru `products` pada folder `main.dart` 
    - Menambahkan file baru `shoplist_items.dart` pada folder `screens` untuk memunculkan produk-produk yang pernah dibuat.
    - Membuat fungsi untuk membuat objek baru dari class `Product`, dan menambahkannya ke list `products` setiap tombol save pada `shoplist_form.dart` ditekan.
    - Membuat `ListTile` baru dengan nama **Lihat Produk** pada Left Drawer
    - Membuat routing dari **Left Drawer** dan tombol **Lihat Produk** di home ke page untuk melihat semua prduk (`shoplist_items.dart`)

# Tugas 9
#### 1. Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?
Ya, kita bisa mengambil data JSON dari Django ke Flutter tanpa membuat model di Flutter, tetapi membuat model di Flutter umumnya lebih baik karena memberikan validasi tipe data, abstraksi tingkat tinggi, dan kemudahan pemeliharaan kode.

#### 2. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
**CookieRequest** memastikan konsistensi sumber data, memudahkan pembaruan dan akses data, mengurangi redundansi kode, mendukung pemodelan arsitektur yang terstruktur, dan memberikan fleksibilitas dalam pembaharuan.

#### 3. Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.
- Pengguna membuka aplikasi Flutter.
- Aplikasi Flutter melakukan pemanggilan fungsi `fetchData`.
- Fungsi `fetchData` mengirim permintaan HTTP GET ke backend Django.
- Django mengambil data dari database melalui model dan serializer.
- Django merespons dengan data JSON.
- Aplikasi Flutter menerima respons JSON dan mengonversinya menjadi objek Flutter menggunakan model.
- Data ditampilkan dalam widget Flutter, memberikan pengguna antarmuka pengguna yang sesuai dengan data yang diterima.

#### 4.  Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
- Permintaan Login dari Flutter ke Django:
    - Pengguna memasukkan informasi login di Flutter.
    - Permintaan HTTP POST dikirim ke endpoint login Django.
- Fungsi Login di Django:
    - Django memverifikasi kredensial dengan authenticate.
    - Jika valid, pengguna ditandai sebagai terautentikasi dengan auth_login.
- Respon ke Flutter:
    - Django mengirimkan respons JSON ke Flutter dengan status login.
    - Sukses: Berisi informasi pengguna dan pesan sukses.
    - Gagal: Berisi pesan kesalahan dan status 401 jika tidak diizinkan.
- Pengolahan Respon di Flutter:
    - Flutter mengelola respons, menyimpan token atau mengambil tindakan selanjutnya.

#### 5. Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.
- **Drawer (LeftDrawer):**
Menyediakan menu navigasi kiri di layar, mungkin berisi opsi navigasi tambahan.
- **Form:**
Mengelompokkan dan mengatur TextFormField dalam satu formulir.
Menggunakan GlobalKey<FormState> untuk validasi formulir.
- **TextFormField (Nama Produk, Harga, Deskripsi):**
Input field untuk memasukkan nama produk, harga, dan deskripsi.
Dilengkapi dengan fungsi onChanged untuk memperbarui nilai variabel terkait.
- **ElevatedButton:**
Tombol yang digunakan untuk mengirimkan data formulir ke server Django.
Menggunakan metode POST untuk mengirim data JSON ke endpoint tertentu.
- **SnackBar:**
Menampilkan pesan pemberitahuan di bagian bawah layar setelah mengirimkan data ke server.
Dua snackbar berbeda untuk kasus keberhasilan dan kegagalan.
- **ListTile:**
Digunakan untuk membuat item daftar di drawer.
Setiap ListTile memiliki ikon, judul, dan fungsi onTap yang menentukan tindakan saat item daftar diklik.
- **Navigator.pushReplacement:**
Mengaktifkan navigasi ke halaman lain dan menggantikan halaman saat ini, berguna untuk kembali ke halaman utama atau mengganti halaman setelah tindakan tertentu.
- **Navigator.push:**
Menangani navigasi ke halaman lain tanpa menggantikan halaman saat ini, seperti ketika pengguna memilih untuk melihat daftar produk.

#### 6. Step by Step
- Django
    - Auth
        - Membuat app baru dengan nama `authentication`.
        - Menambahkan fungsi login dan logout pada `views.py` di app `authentication`.
        - Menghubungkan url ke views dengan menambah path login dan logout pada `urls.py`.
        - Menghubungkan path pada app `authentication` dengan menambah path penghubung pada `urls.py` di app utama `barang_gelap`.
        
    - Tambah Produk
        - Menambah fungsi `create_product_flutter` di `views.py` di app `main` untuk membuat produk baru.
    
    - Lihat Produk
        - Menggunakan url JSON untuk membuat model kustom dengan bantuan website [QuickType](http://app.quicktype.io/).
- Flutter
    - Auth
        - Menyediakan **CookieRequest** library ke semua child widgets dengan menggunakan `Provider` di `main.dart`.
        - Membuat tampilan login dengan menambah file `login.dart` pada folder lib/screens.
    
    - Tambah Produk
        - Mengubah `onPressed:()` pada file `shoplist_form.dart` menjadi request ke django untuk menjalankan fungsi `create_product_flutter`.

    - Lihat Produk
        - Membuat model kustom dengan bantuan website [QuickType](http://app.quicktype.io/)
        - Membuat tampilan daftar produk dengan menambah file `list_product.dart` pada folder lib/screens.
        - Membuat fungsi fetch data JSON dari django pada file `list_product.dart`
