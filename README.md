# Smart Garden System Penyiram Tanaman Otomatis
Smart Garden berbasis Arduino yang berfungsi untuk memantau kelembapan tanah secara real-time. Jika tanah terdeteksi kering, sistem akan memberikan peringatan melalui suara dan lampu, serta melakukan penyiraman otomatis menggunakan motor servo sebagai simulasi pompa air. Proses ini berjalan sepenuhnya otomatis tanpa perlu intervensi manual.
# Daftar Komponen dan Konfigurasi PIN
| No | Nama Komponen           | Pin Arduino              | Fungsi                                      |
|----|-------------------------|--------------------------|---------------------------------------------|
| 1  | Arduino Uno R3          | -                        | Pengendali Utama (Microcontroller)          |
| 2  | LCD 16x2 I2C            | SDA (A4), SCL (A5)       | Menampilkan nilai sensor & status tanah     |
| 3  | Soil Moisture Sensor    | A0                       | Mendeteksi tingkat kelembapan tanah         |
| 4  | Motor Servo (SG90)      | 7                        | Simulasi katup kran / pompa air             |
| 5  | LED Red                 | 8                        | Indikator visual saat penyiraman aktif      |
| 6  | Buzzer                  | 9                        | Alarm suara saat kondisi tanah kering       |
| 7  | Resistor 330 Ohm        | Terhubung ke LED         | Menghambat arus berlebih pada LED           |
| 8  | Breadboard & Kabel      | -                        | Media penghubung antar komponen             |
# Cara Kerja
Sistem Smart Garden ini beroperasi secara otomatis menggunakan siklus deteksi dan aksi yang dikendalikan oleh Arduino Uno. Proses dimulai ketika Soil Moisture Sensor mendeteksi tingkat kelembapan tanah melalui pin analog A0. Sensor ini bekerja dengan membaca resistansi tanah, di mana nilai analog yang dihasilkan akan semakin tinggi seiring dengan semakin keringnya kondisi tanah. Data analog tersebut kemudian diproses secara real-time oleh mikrokontroler untuk dibandingkan dengan nilai ambang batas (threshold) yang telah ditentukan di dalam program.

Apabila sensor mendeteksi bahwa tanah berada dalam kondisi kering (nilai sensor di atas 400), maka sistem akan memicu tiga respon sekaligus sebagai bentuk peringatan dan aksi. Pertama, LCD 16x2 akan menampilkan status "KERING" beserta nilai kelembapannya. Kedua, Buzzer akan berbunyi selama satu detik diikuti dengan menyalanya LED Merah sebagai indikator visual penyiraman. Ketiga, Motor Servo yang berfungsi sebagai simulasi katup kran atau pompa air akan bergerak secara perlahan dari posisi 0 ke 180 derajat untuk menyalurkan air ke tanaman.

Sebaliknya, jika sensor mendeteksi bahwa tanah sudah kembali basah atau lembap (nilai sensor di bawah 400), sistem secara otomatis akan menghentikan seluruh aktivitas penyiraman. Pada kondisi ini, LCD akan memperbarui status menjadi "BASAH", LED dan Buzzer akan mati, serta Motor Servo akan bergerak kembali ke posisi awal (0 derajat) untuk menutup aliran air. Seluruh proses ini berjalan dalam perulangan terus-menerus setiap 500 milidetik, memastikan tanaman selalu mendapatkan asupan air yang tepat tanpa perlu pengawasan manual secara konstan.
