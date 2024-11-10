## Tugas 7

###### 1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.

Stateless widget merupakan widget yang tidak dapat berubah selama aplikasi running. Widget ini hanya dirender sekali saat pertama kali dibuat dan tidak akan diperbarui meskipun suatu data atau variabel berubah.
Stateful widget merupakan widget yang dapat berubah selama aplikasi running. Widget ini dapat merender ulang widget ketika terdapat suatu data yang mengalami perubahan. Hal ini dapat dilakukan dengan menggunakan object `State` dan memanggil function `setState()` untuk mengubah tampilan User Interfacenya.
Perbedaan Stateless widget dengan Stateful widget adalah stateful widget bersifat statis dan tidak berubah setelah dirender. Widget ini cocok untuk tampilan yang tidak memerlukan perubahan selama aplikasi berjalan. Sedangkan,stateful widget dapat berubah dan memperbarui tampilan berdasarkan perubahan state internal atau interaksi pengguna.

###### 2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.

1. MaterialApp = Widget root untuk aplikasi Flutter yang menerapkan Material Design.
2. Scaffold = Berfungsi untuk menyediakan struktur dasar halaman seperti AppBar, Body, dan FloatingActionButton.
3. AppBar = Berfungsi untuk menampilkan bar aplikasi di bagian atas yang dapat digunakan untuk menampilkan judul halaman atau aplikasi.
4. Text = Berfungsi untuk menampilkan teks dengan berbagai style dan pengaturan yang diinginkan.
5. Padding = Berfungsi untuk menambahkan ruang atau jarak di sekitar widget yang dapat membantu agar layout lebhi rapi.
6. Row = Berfungsi untuk menyusun widget secara horizontal atau sejajar ke samping
7. Card = Berfungsi untuk menampilkan sebuah kontainer berbentuk kotak dengan sudut melengkung dan bayangan.
8. SizedBox = Berfungsi untuk memberikan spasi atau pembatas antar widget.
9. Center = Berfungsi untuk menempatkan child widget di tengah secara horizontal dan vertikal dalam parentnya.
10. Column = Berfungsi untuk menyusun widget secara vertikal atau sejajar ke bawah
11. GridView.count = Berfungsi untuk menampilkan daftar widget dalam bentuk grid dengan jumlah kolom yang ditentukan.
12. Material = Berfungsi untuk membungkus widget child dengan menggunakan Material Design, seperti warna dan borderRadius.
13. InkWell = Berfungsi untuk menangani interaksi sentuhan layar dan memberikan efek ripple saat widget ditekan.
14. ScaffoldMessenger = Berfungsi untuk mengelola dan menampilkan SnackBar dalam aplikasi yang dapat menampilkan pesan sementara di layar.
15. SnackBar = Berfungsi untuk menampilkan pesan singkat di bagian bawah layar.
16. Container = Berfungsi untuk mengatur layout, seperti padding, margin, dan dekorasi. Selain itu, container juga digunakan untuk membungkus dan mengatur posisi child widget.
17. Icon = Berfungsi untuk menampilkan icon dari icon-icon Material Design.
18. StatelessWidget = Berfungsi untuk membuat widget yang statis dan tidak interaktif.

###### 3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.

Fungsi setState() digunakan untuk memberi tahu aplikasi bahwa ada perubahan pada state internal yang memerlukan pembaruan User Interface. Flutter akan menjalankan ulang method build() atau merender ulang bagian dari User Interface yang terpengaruh sehingga perubahan pada state akan terlihat pada tampilan saat method setState() dipanggil. setState() berfungsi untuk memastikan bahwa User Interface diperbarui sesuai dengan perubahan data atau variabel yang telah diubah di dalamnya dan hanya merender ulang widget yang terpengaruh di dalam widget build() tertentu sehingga lebih efisien. Variabel yang terdampak oleh setState() adalah semua variabel yang dideklarasikan di dalam kelas State dan digunakan dalam method build(). Hanya variabel yang mengalami perubahan di dalam setState() yang akan menyebabkan User Interface dirender ulang.

###### 4. Jelaskan perbedaan antara const dengan final.

Const merupakan nilai konstan yang dibuat saat waktu kompilasi dan nilainya harus langsung diassign ke variable const tersebut. Const bersifat immutable yang artinya nilainya tidak dapat diubah setelah dibuat. Const digunakan untuk membuat nilai konstan yang tidak dapat diubah dan diketahui saat waktu kompilasi. Sedangkan, Final merupakan variabel yang nilainya ditetapkan hanya sekali dan tidak dapat diubah setelahnya. Nilai dari Final dapat ditentukan pada saat waktu runtime. Final digunakan untuk nilai yang ditetapkan sekali dan dapat ditentukan pada waktu runtime.

###### 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.

1. Buat sebuah direktori dan generate proyek Flutter dengan command `flutter create gotoko`.
2. Buat repositori baru di github dengan nama gotoko-mobile, lalu lakukan add, commit, dan push ke repositori baru tersebut.
3. Pada direktori gotoko/lib bauat sebuah file baru dengan nama menu.dart dan lakukan import material.dart `import 'package:flutter/material.dart';`.
4. Pada file main.dart, hapus class \_MyHomePageState dan pindahkan class MyHomePage ke file menu.dart
5. Pada file main.dart, import menu.dart dengan `import 'package:gotoko/menu.dart';`
6. Pada file main.dart, ubah title (tepat setelah line return MaterialApp) menjadi GOTOKO dan ubah tema warna aplikasi menjadi indigo dengan kode seperti ini

```
colorScheme: ColorScheme.fromSwatch(primarySwatch: Colors.indigo,).copyWith(secondary: Colors.indigo[900]),
```

7. Pada file main.dart, hapus const MyHomePage(title: 'Flutter Demo Home Page') dan ganti menjadi MyHomePage()
8. Pada file menu.dart dan class myHomePage, ubah extends StatefulWidget menjadi extends StatelessWidget dan hapus semua isi dari class tersebut.
9. Tambah sebuah constructor untuk class MyHomePage dengan `MyHomePage({super.key})` dan Widget build hingga menjadi seperti ini

```
class MyHomePage extends StatelessWidget {
    MyHomePage({super.key});

    @override
    Widget build(BuildContext context) {
	return Scaffold(
    ...
	);
    }
```

10. Pada class MyHomePage, buat tiga variable bertipe string yang berisi data diri, seperti NPM, nama, dan kelas.
11. Buat sebuah class baru yang bernama InfoCard yang bersifat Stateless yang berfungsi untuk menampilkan card dari data diri yang dibuat dalam variabel.
12. Buat sebuah class baru yang bernama ItemHomePage yang berisi atribut-atribut dari button card yang akan dibuat pada step selanjutnya, seperti atribut nama, icon, dan warna.
13. Pada class MyHomePage buat List yang memanggil ItemHomePage tadi dengan memasukkan atribut nama, icon, dan warnanya masing-masing. Buat tiga tombol, yaitu Lihat Daftar Produk, Tambah Produk, dan Logout.
14. Untuk menampilakn tombol, buat sebuah class baru bernama ItemCard yang bersifat Stateless.
15. Buat sebuah variabel bernama item dengan tipe data ItemHomePage yang sudah dibuat sebelumnya.
16. Untuk menampilkan warna yang berbeda pada tiap button, gunakan atribut dari item yaitu item.color untuk mengatur background dari button. `color: item.color,`
17. Untuk menampilkan Snackbar dengan tulisan nama masing-masing button, gunakan atribut dari item yaitu item.name agar pesan Snackbar sesuai dengan button yang diklik.

```
onTap: () {
          // Menampilkan pesan SnackBar saat kartu ditekan.
          ScaffoldMessenger.of(context)
            ..hideCurrentSnackBar()
            ..showSnackBar(
                SnackBar(content: Text("Kamu telah menekan tombol ${item.name}!"))
            );
        },
```

18. Setelah itu, buat Container yang menyimpan Icon dan Text dengan menggunakan atribut dari item yaitu item.icon untuk menampilkan icon dan item.name untuk menampilkan nama
19. Integrasikan semua class untuk button dan card tadi pada class MyHomePage pada Widget build() agar seluruh elemen dapat ditampilkan dalam aplikasi
20. Lakukan `flutter analyze `untuk memeriksa apakah ada error atau isu pada kode aplikasi

## Tugas 8

###### 1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?

Const di flutter digunakan untuk membuat sebuah widget, variabel, atau value yang immutable. Widget atau value yang menggunakan const akan dibuat satu kali selama lifecycle aplikasi sehingga akan meningkatkan performa aplikasi dan menghemat memori. Selain dua keuntungan tadi, dengan menggunakan const, manajemen widget tree menjadi efisien dan kontruktor konstan menunjukkan dengan jelas tujuan membuat object sehingga akan meningkatkan readability dan maintainability kode program dan memperjelas flow data pada aplikasi.

Const baik digunakan pada saat membuat immutable data object, seperti warna, konfigurasi, dan data-data yang tidak akan diubah selama lifecycle aplikasi. Contoh `const Color myPrimaryBlue = const Color(0xFF89CFF0);`. Selain itu, const baik digunakan pada saat pre-defined values, seperti API endpoint atau nilai statik. Contoh `const String myApi = const "https://my.api.com";`. Const juga baik digunakan untuk mengomptimalkan widget trees. Widget yang menggunakan const dianggap sudah dibuild sebelumnya dan akan digunakan kembali selama proses rebuild apabila referensinya tidak berubah sehingga terhindar dari pembuatan widget yang tidak perlu dan meningkatkan performa dari widget trees. Contoh `final myText = const Text('Hello World');`. Const sebaiknya tidak digunakan ketika membuat dynamic data dan network calls, contohnya user input atau data yang difetch dari sebuah network calls.

###### 2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!

Row digunakan untuk menempatkan widget secara horizontal atau ke samping pada layar, sedangkan Column digunakan untuk menempatkan widget secara vertikal atau ke bawah pada layar.

Contoh implementasi Row:

```
Row(
  mainAxisAlignment: MainAxisAlignment.spaceBetween,
  children: <Widget>[
    Text('Home'),
    Text('About'),
    Text('Menu'),
  ],
)
```

Contoh implementasi Column:

```
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  children: <Widget>[
    Text('Item ke-1'),
    Text('Item ke-2'),
    Text('Item ke-3'),
  ],
)
```

###### 3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!

Pada tugas ini, saya hanya menggunakan elemen input TextFormField pada halaman tambah produk. Banyak elemen input flutter yang lain yang tidak digunakan pada tugas ini, seperti DropdownButton, Checkbox, Radio, Slider, DatePicker, TimePicker, RangeSlider, FilePicker, dan lain sebagainya.

###### 4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?

Saya mengatur tema aplikasi Flutter agar konsisten dengan menggunakan `ThemeData` dalam `MaterialApp`. Pada file main.dart, saya mendefinisikan tema global untuk aplikasi menggunakan `ThemeData` dan `ColorScheme`. Dengan cara ini, saya bisa menentukan warna utama (primarySwatch) yaitu indigo dan warna aksen (secondary) yaitu indigo[900]. Selain itu, saya menggunakan `useMaterial3: true` untuk mendapatkan tampilan Material Design versi terbaru. Dengan menggunakan tema global ini, saya memastikan semua widget yang sesuai dengan warna primary atau secondary akan mengikuti skema warna yang telah ditentukan tanpa perlu mendefinisikan warna tersebut berulang kali pada setiap widget.

###### 5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?

Untuk menangani navigasi pada aplikasi Flutter dengan banyak halaman, saya menggunakan `Navigator` dengan `pushReplacement` dan `push`. Saya menggunakan pushReplacement untuk menggantikan halaman saat ini dengan halaman baru tanpa menumpuk halaman sebelumnya di stack. Misalnya, ketika saya memilih "Halaman Utama" di lrft drawer, saya menggunakan pushReplacement untuk memastikan halaman utama menggantikan halaman yang sedang dibuka. Saya menggunakan `push` untuk fitur "Tambah Produk", yang akan menambahkan halaman baru di atas halaman yang sedang dibuka dengan menggunakan stack. Dengan cara ini, saya dapat kembali ke halaman sebelumnya menggunakan `pop`. Selain itu, saya menggunakan sebuah drawer yang akan muncul disebelah kiri aplikasi ketika icon hamburger diklik untuk memberikan navigasi ke halaman utama dan halaman tambah prooduk.
