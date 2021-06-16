# Lab11Web : PHP Framework (Codeigniter)
# PERSIAPAN :
1. Gunakan text editor, saya menggunakan sublime.

2. Menggunakan Xampp

3. Membuat folder baru lab11_php_ci

Diperlukan konfigurasi pada webserver, mengaktifkan ekstensi PHP intl. buka xampp di apache klik konfigurasi dan buka php.ini

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/Screenshot%20(87).png)

Untuk mengaktifkan extension nya hapus tanda titik kome (;)

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/pad.JPG)

langkah selanjutnya unduh codeigniter, extrack filenya dan masukan ke dalam xampp/htdock

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/Screenshot%20(86).png)

Bukalah localhost:8080 di browser.

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/welcome.JPG)

Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
dan gunakan "php spark"

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/phpspark.jpg)

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/whoops.JPG)

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRINMENT menjadi development.

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/.env.jpg)

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/notepad.jpg)

Dan hasil Eror Nya :

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/notepad.jpg)

# PENJELASAN TENTANG DIREKTORI CODEIGNETER
. github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk build dengan github action;
. app folder ini akan berisi kode dari aplikasi yang kita kembangkan;
. public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php, robots.txt, favicon.ico, ads.txt, dll;
. tests folder ini berisi kode untuk melakukan testing dengna PHPunit;
. vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk kode core dari system CI.
. writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk menyimpan file yang di-upload, logs, session, dll.

# Sedangkan file-file yang berada pada root direktori CI sebagai berikut.
. env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.
. gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git.
. build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi release (stabil) dan development (labil).
. composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.
. composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan aplikasi.
. license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter;
. phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit.
.  README.md adalah file keterangan tentang codebase CI. Ini biasanya akan dibutuhkan pada repo github atau gitlab.
. spark adalah program atau script yang berfungsi untuk menjalankan server, generate kode, dll.

# Folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.
# Pada folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.

# Memahami Konsep MVC

Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari Model-View-Controller. MVC merupakan konsep arsitektur yang umum digunakan dalam pengembangan aplikasi. Konsep MVC adalah memisahkan kode program berdasarkan logic proses, data, dan tampilan. Untuk logic proses diletakkan pada direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan diletakkan pada direktori View.

# Codeigniter menggunakan konsep pemrograman berorientasi objek dalam mengimplementasikan konsep MVC.

# Model

Merupakan kode program yang berisi pemodelan data. Data dapat berupa database ataupun sumber lainnya.

# View

Merupakan kode program yang berisi bagian yang menangani terkait tampilan user interface sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan dengan html dan css.

# Controller

Merupakaan kode program yang berkaitan dengan logic proses yang menghubungkan antara view dan model. Controller berfungsi untuk menerima request dan data dari user kemudian diproses dengan menghubungkan bagian model dan view.

# Routing dan Controller

Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau script yang bertanggung jawab merespon sebuah request.

Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file app/config/Routes.php
Membuat Route


![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/route.jpg)

Memeriksa penambahan route di CLI dengan perintah "php spark routes"

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/routes.jpg)

Mengakses file about.php akan terlihat seperti berikut , karena tidak ada isinya.

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/gambar/notfound.jpg)

Membuat controller dengan nama file page.php



