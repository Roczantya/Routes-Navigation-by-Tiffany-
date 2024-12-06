# Routes-Navigator App
  Aplikasi Flutter sederhana untuk navigasi antar layar dengan fitur UI kustom, termasuk bottom navigation bar, dan rute-rute yang mudah digunakan.

## Fitur
- `Bottom Navigation Bar` untuk navigasi antar layar (Home, Search, Settings dan Profile).
- Tombol AppBar untuk kembali ke layar utama.
- Tombol dinamis untuk berpindah antar layar.
  
## Persyaratan
Sebelum memulai, pastikan Anda telah memenuhi persyaratan berikut:
  1. Install Flutter (disarankan versi 3.x atau lebih baru).
  2. Pastikan lingkungan Flutter Anda sudah siap:
     - Jalankan `flutter doctor` di terminal untuk memastikan semua komponen telah terinstal dengan benar.

## Instalasi
1. Clone repositori ini ke komputer Anda:
  ```bash
  git clone https://github.com/Roczantya/Routes-Navigation-by-Tiffany-.git
  cd Routes-Navigation-by-Tiffany
  ```
2. Instal semua dependensi yang diperlukan:
  ```bash
  flutter pub get
  ```
3. Jalankan aplikasi:
  ```bash
  flutter run
  ```

## Penggunaan
  ### Navigasi
  1. __Home Screen__
     - Layar default saat aplikasi dibuka.
     - Terdapat tombol untuk menuju First Screen atau membuka dialog.
  2. __Bottom Navigation Bar__
     - Gunakan ikon di bagian bawah layar untuk berpindah antar layar: `HomeScreen`, `FirstScreen`. `Secondscreen`, dan `ThirdScreen`
  3. __Tombol Kembali di AppBar__
     - Pada layar `First Screen`, `Second Screen` dan `Third Screen`, tombol ini akan membawa Anda kembali ke First Screen.
       
## Challenge(Tantangan)
  - Pada `Appbar` di __SecondScreen__ dan __ThirdScreen__, sempat tidak mau kembali ke halaman utama
  - Pada `BottoomNavigationBar`, icon yang digunakan untuk berpindah halaman tidak bisa berpindah ke halaman  `FirstScreen`. `Secondscreen`, dan `ThirdScreen`
    
## Approach (Pendekatan)
  - Untuk masalah pertama, pendekatan yang klakukan memberikan `leanding` yang berfungsi untuk membuat Icon Arrowback bisa berpindah ke halaman dashboard
  - Untuk masalah kedua, saya membuat route tersendiri guna dapat memudahkan menampilkan membuat navigasi antar screen. jadi pemanggilannya akan seperti ini  ini memudahkan dalam memuat halaman screen. Contoh code:
 ``` bash
  initialRoute: '/',
      routes: {
        '/': (context) => const HomeScreen(),
        '/first': (context) => const FirstScreen(),
        '/second': (context) => const SecondScreen(),
        '/third': (context) => const ThirdScreen(),
      },
```
  - Untuk masalah  `BottoomNavigationBar`, `final List<Widget> _pages` ini adalah pemanggilan list widget yang berfungsi untuk menampilkan screen pada halaman yang dipilih. `body: _pages[_selectedIndex],` ini akan memanggil list widget berdasarkan index yang dipilih pada `BottoomNavigationBar`. Jika indeksnya adalah 0, maka HomePage akan ditampilkan, jika 1, maka FirstScreen yang ditampilkan, dan seterusnya.

    
## Struktur Folder
  Struktur folder aplikasi mengikuti format standar Flutter:

```plaintext
lib/
├── main.dart           # Titik masuk aplikasi dan widget pada bottom navigasi bar
├── first_screen.dart   # Logika dan UI layar pertama
├── second_screen.dart  # Logika dan UI layar kedua
├── third_screen.dart   # Logika dan UI layar ketiga
```
