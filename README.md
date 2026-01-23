# Smart Digital Piggy Bank (Celengan Digital Pintar) - ESP32

Proyek ini adalah prototipe celengan pintar berbasis ESP32 yang dapat menghitung saldo secara otomatis, memantau kondisi keamanan kotak, dan memberikan peringatan suara serta visual.

## 🚀 Fitur Utama
* **Penghitung Saldo Otomatis:** Menggunakan sensor untuk mendeteksi koin/uang yang masuk (diwakili oleh simulasi LDR/Potensio).
* **Sistem Keamanan Kelembapan:** Memantau agar uang kertas di dalam tidak lembap/berjamur menggunakan sensor DHT22.
* **Alarm Anti-Maling:** Buzzer akan berbunyi jika terdeteksi suhu ekstrem atau upaya pembukaan paksa (simulasi sensor).
* **Indikator Kapasitas:** LED akan menyala jika celengan sudah mencapai target atau penuh.
* **Layar Informasi:** Menampilkan total saldo dan kondisi suhu internal pada LCD 16x2.

## 🛠️ Komponen yang Digunakan
* **ESP32 DevKit V1** (Otak sistem)
* **Sensor DHT22** (Memantau kelembapan agar uang tidak rusak)
* **Potentiometer** (Simulasi sensor penghitung nilai koin)
* **Sensor LDR** (Mendeteksi cahaya masuk - indikator celengan dibuka)
* **LCD 16x2 dengan Modul I2C** (Menampilkan Saldo & Status)
* **Relay Module** (Kunci pintu otomatis / Selenoid Door Lock)
* **Active Buzzer** (Alarm Keamanan)
* **LED Merah** (Indikator Penuh/Error)

## 📋 Skema Sambungan (Wiring)
| Komponen | Pin ESP32 | Fungsi di Celengan |
|---|---|---|
| DHT22 | GPIO 15 | Cek Suhu/Lembap Kotak |
| Potentiometer | GPIO 34 | Simulasi Input Uang |
| LDR | GPIO 35 | Sensor Deteksi Bukaan Pintu |
| LCD SDA/SCL | GPIO 21/22 | Layar Informasi Saldo |
| Relay | GPIO 2 | Kunci Elektronik |
| LED | GPIO 13 | Lampu Indikator |
| Buzzer | GPIO 4 | Alarm Keamanan |

## 📖 Logika Operasional
- **Tabungan:** Setiap perubahan pada Potentiometer/LDR akan dihitung sebagai nilai uang yang masuk dan menambah saldo di layar.
- **Keamanan:** Jika celengan dibuka tanpa izin (LDR terkena cahaya), Buzzer akan berbunyi.
- **Perawatan:** Jika kelembapan udara (DHT22) > 70%, LCD akan memberi peringatan "Kotak Lembap" untuk mencegah uang kertas rusak.

---
*Proyek ini diunggah untuk dokumentasi tugas IoT/Sistem Tertanam menggunakan Wokwi.*
