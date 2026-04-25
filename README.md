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
