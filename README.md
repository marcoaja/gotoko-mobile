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

## TUGAS 9

###### 1. Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?

Kita perlu membuat model untuk mempermudah pengelolaan dan manipulasi data yang akan dikirim atau diterima dalam format JSON. Model berfungsi sebagai representasi struktur data dalam aplikasi kita sehingga memudahkan proses `serialize` atau mengubah objek menjadi JSON dan `deserialize` atau mengubah JSON menjadi objek. Dengan membuat model, kita dapat memastikan bahwa data yang dikirim dan diterima memiliki format dan tipe data yang konsisten.

Jika kita tidak membuat model terlebih dahulu, kemungkinan akan terjadi error ketika menerima data JSON ke dalam penyimpanan data aplikasi. Error dapat terjadi pada saat proses parsing atau saat mencoba mengakses atribut yang tidak terdefinisi. Tanpa model, kode kita juga menjadi kurang terstruktur dan lebih rentan terhadap bug karena tidak ada kerangka yang jelas untuk data yang sedang diproses.

###### 2. Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini

Library `http` digunakan untuk melakukan permintaan HTTP dari aplikasi Flutter ke web service atau API (django). Library http pada tugas ini berguna untuk mengambil data JSON dari server Django dengan menggunakan metode `GET` dan mengirim data JSON ke server Django dengan menggunakan metode `POST`, contohnya adalah saat melakukan login atau mengirim data melalui form.

contoh penggunaan http.get pada tugas ini adalah menambil data JSON dari django:

```dart
final response = await request.get('http://[APP_URL_KAMU]/json/');
```

###### 3. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

CookieRequest adalah class yang digunakan untuk mengelola permintaan HTTP yang memerlukan penyimpanan dan pengiriman cookie terutama dalam autentikasi dengan web service Django. Fungsi CookieRequest adalah menyimpan session cookies, menambahkan session cookie dalam header request, dan menyimpan status apakah pengguna sedang login atau tidak.

Instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter karena dengan berbagi instance yang sama, semua bagian aplikasi flutter menggunakan cookie yang sama untuk autentikasi sehingga sesi pengguna tetap konsisten dan komponen mana pun yang membutuhkan akses ke web service yang memerlukan autentikasi dapat menggunakan instance CookieRequest yang sama tanpa perlu melakukan login ulang. Selain itu, dengan menggunakan `Provider`, kita dapat mengelola state secara global sehingga perubahan pada CookieRequest akan terdeteksi oleh komponen yang menggunaka data tersebut.

###### 4. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.

1. Input data oleh pengguna
   - User mengisi form atau memasukkan data pada aplikasi Flutter. Contohnya: `String username = _usernameController.text;`
2. Kirim data ke server django
   - Data yang diinput user dikirim ke server Django melalui permintaan HTTP POST.
   - Menggunakan CookieRequest.postJson untuk mengirim data dalam format JSON. Contohnya:
   ```dart
    final response = await request.postJson(
        "http://[APP_URL_KAMU]/auth/register/",
        jsonEncode({
          "username": username,
          "password1": password1,
          "password2": password2,
        }));
   ```
3. Proses data di server django

   - Server Django menerima permintaan POST dan data JSON.
   - Data diparsing dan divalidasi.
   - Objek baru dibuat dan disimpan ke database. Contoh:

   ```python
   @csrf_exempt
   def register(request):
    if request.method == 'POST':
        data = json.loads(request.body)
        username = data['username']
        password1 = data['password1']
        password2 = data['password2']

        # Check if the passwords match
        if password1 != password2:
            return JsonResponse({
                "status": False,
                "message": "Passwords do not match."
            }, status=400)

        # Check if the username is already taken
        if User.objects.filter(username=username).exists():
            return JsonResponse({
                "status": False,
                "message": "Username already exists."
            }, status=400)

        # Create the new user
        user = User.objects.create_user(username=username, password=password1)
        user.save()

        return JsonResponse({
            "username": user.username,
            "status": 'success',
            "message": "User created successfully!"
        }, status=200)

    else:
        return JsonResponse({
            "status": False,
            "message": "Invalid request method."
        }, status=400)

   ```

4. Terima response di Flutter
   - Aplikasi Flutter menerima respons dari server.
   - Jika sukses, memberikan notifikasi kepada user dan mungkin mengarahkan ke halaman lain. Conoth:
   ```dart
    if (response['status'] == 'success') {
    ScaffoldMessenger.of(context).showSnackBar(
      const SnackBar(
        content: Text('Successfully registered!'),
      ),
    );
    Navigator.pushReplacement(
      context,
      MaterialPageRoute(
          builder: (context) => const LoginPage()),
    );
   } else {
    ScaffoldMessenger.of(context).showSnackBar(
      const SnackBar(
        content: Text('Failed to register!'),
      ),
    );
   };
   ```
5. Tampilkan data di Flutter
   - Aplikasi melakukan fetch data dari server untuk mendapatkan data terbaru.
   - Menggunakan metode GET untuk mengambil data dalam format JSON.
   - Data JSON dikonversi menjadi objek model dan ditampilkan pada aplikasi user.

###### 5. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

### 1) Register

1. Input data pada Flutter

- Pengguna mengisi form registrasi dengan username dan password.

```dart
String username = _usernameController.text;
String password1 = _passwordController.text;
String password2 = _confirmPasswordController.text;
```

2. Kirim data ke server Django:

-Data dikirim menggunakan request.postJson ke endpoint /auth/register/.

```dart
final response = await request.postJson(
  "http://[APP_URL_KAMU]/auth/register/",
  jsonEncode({
  "username": username,
  "password1": password1,
  "password2": password2,
}));
```

3. Proses data di Django:

- Fungsi view register menerima data dan melakukan validasi.
  Jika valid, membuat user baru dan menyimpannya ke database.

```python
@csrf_exempt
def register(request):
    if request.method == 'POST':
        data = json.loads(request.body)
        username = data['username']
        password1 = data['password1']
        password2 = data['password2']

        # Check if the passwords match
        if password1 != password2:
            return JsonResponse({
                "status": False,
                "message": "Passwords do not match."
            }, status=400)

        # Check if the username is already taken
        if User.objects.filter(username=username).exists():
            return JsonResponse({
                "status": False,
                "message": "Username already exists."
            }, status=400)

        # Create the new user
        user = User.objects.create_user(username=username, password=password1)
        user.save()

        return JsonResponse({
            "username": user.username,
            "status": 'success',
            "message": "User created successfully!"
        }, status=200)

    else:
        return JsonResponse({
            "status": False,
            "message": "Invalid request method."
        }, status=400)

```

4. Terima Response di Flutter:

- Jika registrasi berhasil, menampilkan pesan sukses dan mengarahkan pengguna ke halaman login.

```dart
if (response['status'] == 'success') {
    ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Successfully registered!')),
    );
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => const LoginPage()),
    );
  } else {
    ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Failed to register!')),
    );
}
```

### 2) Login:

1. Input data pada Flutter:

- Pengguna memasukkan username dan password.

```dart
String username = _usernameController.text;
String password = _passwordController.text;
```

2. Kirim data ke server Django:

- Menggunakan request.login untuk mengirim data ke endpoint /auth/login/.

```dart
final response = await request.login(
  "http://[APP_URL_KAMU]/auth/login/",
  {
  'username': username,
  'password': password,
  },
);
```

3. Proses data di Django:

- Fungsi view login melakukan autentikasi dan, jika berhasil, melakukan auth_login dan mengembalikan cookie sesi.

```python
@csrf_exempt
def register(request):
    if request.method == 'POST':
        data = json.loads(request.body)
        username = data['username']
        password1 = data['password1']
        password2 = data['password2']

        # Check if the passwords match
        if password1 != password2:
            return JsonResponse({
                "status": False,
                "message": "Passwords do not match."
            }, status=400)

        # Check if the username is already taken
        if User.objects.filter(username=username).exists():
            return JsonResponse({
                "status": False,
                "message": "Username already exists."
            }, status=400)

        # Create the new user
        user = User.objects.create_user(username=username, password=password1)
        user.save()

        return JsonResponse({
            "username": user.username,
            "status": 'success',
            "message": "User created successfully!"
        }, status=200)

    else:
        return JsonResponse({
            "status": False,
            "message": "Invalid request method."
        }, status=400)
```

4. Terima response di Flutter:

- Jika login berhasil, CookieRequest menyimpan cookie sesi.
- Aplikasi mengarahkan pengguna ke halaman utama dan menampilkan pesan selamat datang.

```dart
if (request.loggedIn) {
        String message = response['message'];
        String uname = response['username'];
        Navigator.pushReplacement(
            context,
            MaterialPageRoute(builder: (context) => MyHomePage()),
        );
        ScaffoldMessenger.of(context).showSnackBar(
            SnackBar(content: Text("$message Selamat datang, $uname.")),
        );
    } else {
        showDialog(
            context: context,
            builder: (context) => AlertDialog(
                title: const Text('Login Gagal'),
                content: Text(response['message']),
                actions: [
                    TextButton(
                        child: const Text('OK'),
                        onPressed: () {
                            Navigator.pop(context);
                        },
                    ),
                ],
            ),
        );
    }
```

5. Akses page yang terproteksi:

- Setelah login, semua permintaan HTTP yang dilakukan melalui CookieRequest akan membawa cookie sesi.
- Server Django akan mengenali sesi pengguna dan memberikan akses ke resource yang sesuai.

### 3) Logout:

1. Klik button logout pada Flutter:

- Pengguna memilih opsi logout, misalnya dengan menekan tombol logout.

2. Mengirim Permintaan Logout ke Server Django:

- Menggunakan request.logout untuk mengirim permintaan ke endpoint /auth/logout/.

`final response = await request.logout("http://[APP_URL_KAMU]/auth/logout/");`

3. Proses data di Django:

- Fungsi view logout memanggil auth_logout untuk menghapus sesi pengguna.

```python
@csrf_exempt
def logout(request):
    username = request.user.username

    try:
        auth_logout(request)
        return JsonResponse({
            "username": username,
            "status": True,
            "message": "Logout berhasil!"
        }, status=200)
    except:
        return JsonResponse({
        "status": False,
        "message": "Logout gagal."
        }, status=401)
```

4. Menerima Respons di Flutter:

   - CookieRequest menghapus cookie sesi.
   - Aplikasi mengarahkan pengguna kembali ke halaman login dan menampilkan pesan perpisahan.

```dart
if (response['status']) {
    String uname = response["username"];
    ScaffoldMessenger.of(context).showSnackBar(SnackBar(
        content: Text("$message Sampai jumpa, $uname."),
    ));
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => const LoginPage()),
    );
} else {
    ScaffoldMessenger.of(context).showSnackBar(
        SnackBar(
            content: Text(message),
        ),
    );
}
```

###### 6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).

1.  Memastikan deployment proyek tugas Django kamu telah berjalan dengan baik.

- Menyiapkan Proyek Django: Saya memastikan bahwa semua aplikasi dan modul yang diperlukan sudah ada dalam proyek Django. Menggunakan virtual environment untuk mengelola dependencies agar terisolasi dari sistem.
- Konfigurasi Settings untuk Deployment: Mengatur ALLOWED_HOSTS di settings.py agar mencakup domain yang digunakan saat development dan deployment Mengatur DEBUG=False untuk mode produksi. Menambahkan konfigurasi untuk static files dan media files jika diperlukan.
- Menginstall Dependencies di Server: Menjalankan pip install -r requirements.txt pada server untuk memastikan semua package yang dibutuhkan terinstal.
- Migrasi Database: Menjalankan python manage.py migrate di server untuk menerapkan migrasi database.

2. Mengimplementasikan fitur registrasi akun pada proyek tugas Flutter.

- Buat django app baru bernama authentication pada django project sebelumnya
- Tambahkan fungsi register pada authentication/views.py

```python
@csrf_exempt
def register(request):
    if request.method == 'POST':
        data = json.loads(request.body)
        username = data['username']
        password1 = data['password1']
        password2 = data['password2']

        if password1 != password2:
            return JsonResponse({
                "status": False,
                "message": "Passwords do not match."
            }, status=400)

        if User.objects.filter(username=username).exists():
            return JsonResponse({
                "status": False,
                "message": "Username already exists."
            }, status=400)

        user = User.objects.create_user(username=username, password=password1)
        user.save()

        return JsonResponse({
            "username": user.username,
            "status": 'success',
            "message": "User created successfully!"
        }, status=200)

    return JsonResponse({
        "status": False,
        "message": "Invalid request method."
    }, status=400)
```

- Tambahkan route pada authentication/urls.py
- Buat file baru register.dart di folder screens.
- Implementasikan form registrasi dengan tiga input (username, password, dan confirm password) menggunakan TextFormField.
- Tambahkan logika untuk mengirim data ke endpoint Django menggunakan request.postJson:

```python
final response = await request.postJson(
    "http://[APP_URL_KAMU]/auth/register/",
    jsonEncode({
        "username": username,
        "password1": password1,
        "password2": password2,
    }),
);
```

- Jika registrasi berhasil, pengguna diarahkan ke halaman login:

```python
if (response['status'] == 'success') {
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => const LoginPage()),
    );
}
```

3. Membuat halaman login pada proyek tugas Flutter

- Tambahkan fungsi login pada authentication/views.py

```python
@csrf_exempt
def login(request):
    username = request.POST['username']
    password = request.POST['password']
    user = authenticate(username=username, password=password)
    if user is not None and user.is_active:
        auth_login(request, user)
        return JsonResponse({
            "username": user.username,
            "status": True,
            "message": "Login sukses!"
        }, status=200)
    return JsonResponse({
        "status": False,
        "message": "Login gagal, periksa kembali email atau kata sandi."
    }, status=401)
```

- Tambahkan route pada authentication/urls.py

```python
path('login/', login, name='login'),
```

- Buat file baru login.dart di folder screens.
- Buat form login dengan dua input (username dan password) menggunakan TextField.
- Tambhakan tombol untuk mengirim data login ke endpoint Django

```dart
final response = await request.login(
    "http://[APP_URL_KAMU]/auth/login/",
    {'username': username, 'password': password},
);
```

- Jika login berhasil, pengguna diarahkan ke halaman utama aplikasi

```dart
if (request.loggedIn) {
    Navigator.pushReplacement(
        context,
        MaterialPageRoute(builder: (context) => const HomePage()),
    );
}
```

4. Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter

- Tambahkan Middleware dan CORS pada Django:
- Instal django-cors-headers dengan `pip install django-cors-headers`
- Tambahkan corsheaders ke INSTALLED_APPS di settings.py

```python
INSTALLED_APPS = [
    ...
    'corsheaders',
    ...
]
```

- Tambahkan CorsMiddleware ke MIDDLEWARE di settings.py

```python
MIDDLEWARE = [
    ...
    'corsheaders.middleware.CorsMiddleware',
    ...
]
```

- Konfigurasikan pengaturan CORS

```python
CORS_ALLOW_ALL_ORIGINS = True
CORS_ALLOW_CREDENTIALS = True
CSRF_COOKIE_SECURE = True
SESSION_COOKIE_SECURE = True
CSRF_COOKIE_SAMESITE = 'None'
SESSION_COOKIE_SAMESITE = 'None'
```

- Instal package provide dan pbp_django_auth pada Flutter dengan perintah

```dart
flutter pub add provider
flutter pub add pbp_django_auth
```

- Konfigurasi main.dart untuk membagikan instance CookieRequest ke seluruh aplikasi:

```dart
return Provider(
    create: (_) {
        CookieRequest request = CookieRequest();
        return request;
    },
    ...
```

4.Membuat model kustom sesuai dengan proyek aplikasi Django.

- Akses endpoint JSON pada django, yaitu pada endpoin /json dan copy contoh data jsonnya
- Konversi JSON menjadi model Dart pada web Quicktype
- Atur nama model sesuai, yaitu ProductEntry
- Buat direktori models di dalam lib/.
- Buat file product_entry.dart dan masukkan kode model yang didapat dari web Quicktype.
- Pastikan model memiliki metode fromJson dan toJson untuk serialisasi.
- Ubah tipe data atau nama field agar sesuai dengan data yang diterima.

5.  Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.

- Tambahkan package http dengan perintah `flutter pub add http`
- Pada file android/app/src/main/AndroidManifest.xml, tambahkan izin akses internet

```xml
    <application>
    ...
    </application>
    <!-- Required to fetch data from the Internet. -->
    <uses-permission android:name="android.permission.INTERNET" />
```

- Di file list_productentry.dart, buat fungsi untuk mengambil data

```dart
Future<List<Item>> fetchItems(CookieRequest request) async {
  final response = await request.get('http://[APP_URL_KAMU]/items/json/');
  List<Item> items = [];
  for (var d in response) {
    items.add(Item.fromJson(d));
  }
  return items;
}
```

- Tampilkan Data menggunakan FutureBuilder dalam build method
- Tampilkan pesan jika data kosong.

6. Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.

- Buat file product_detail.dart di direktori screens
- Buat class ProductDetailPage yang menerima parameter Item melalui constructor:
- Tambahkan navigasi pada setiap product card
- Pada ListView.builder di item_list.dart, tambahkan onTap pada setiap ListTile

```dart
return GestureDetector(
    onTap: () {
        Navigator.push(
        context,
        MaterialPageRoute(
            builder: (context) => ProductDetailPage(product: product),
        ),
        );
    },
    ...
)
```

- Di halaman detail product, tampilkan semua informasi yang dimiliki product.
- Tambahkan button navigasi untuk kembali ke product list dengan ElevatedButton

```dart
Center(
    child: ElevatedButton(
    onPressed: () {
        Navigator.pop(context);
    },
    child: const Text("Back to Product List"),
    ...
```

7.  Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.

- Pada django project dan pada file views.py di main gunakan filter untuk mendapatkan item yang terasosiasi dengan pengguna yang login

```python
def show_json(request):
    data = Product.objects.filter(user=request.user)
    return HttpResponse(serializers.serialize("json", data), content_type="application/json")
```
