# 🌙 Hisab Qomariyah Pro V2

**Hisab Qomariyah Pro V2** adalah aplikasi web kalkulator astronomis (ilmu falak) modern untuk menghitung dan memprediksi penentuan awal bulan Hijriyah (Qomariyah) di Indonesia. 

Dirancang dengan antarmuka *dark glassmorphism* yang ringan dan responsif, aplikasi ini menghitung posisi Matahari dan Bulan secara presisi tepat pada saat Matahari terbenam (*Ghurub*) berdasarkan algoritma astronomi **Jean Meeus (*Astronomical Algorithms*)**.

![Developer](https://img.shields.io/badge/Developer-fatur62-f39c12?style=flat-square)
![Version](https://img.shields.io/badge/Version-2.0%20Pro-00f2fe?style=flat-square)
![License](https://img.shields.io/badge/Status-Open%20Use-10b981?style=flat-square)

---

## ✨ Fitur Utama

1. **Perhitungan Astronomis Presisi Tinggi**
   Menghitung waktu *Ijtimak* (konjungsi geosentris), waktu *Ghurub* (terbenam Matahari), Tinggi Hilal (*Mar'i* & *Haqiqi*), Sudut Elongasi 2D, dan Azimuth tepat pada detik Matahari terbenam di lokasi pengamat.
2. **Dukungan 2 Kriteria Utama di Indonesia**
   * **MABIMS Baru (Pemerintah / Kemenag / NU):** Syarat *Ijtimak Qablal Ghurub*, Tinggi Hilal Mar'i minimal **3°**, dan Sudut Elongasi minimal **6,4°**.
   * **Wujudul Hilal (Muhammadiyah):** Syarat *Ijtimak Qablal Ghurub* dan piringan Bulan sudah berada di atas ufuk (**Tinggi > 0°**) saat Matahari terbenam.
3. **Deteksi GPS & Zona Waktu Otomatis**
   Mengambil koordinat Lintang dan Bujur secara otomatis dari perangkat pengguna serta menyesuaikan zona waktu secara cerdas (**WIB, WITA, atau WIT**).
4. **Visualisasi Bentuk & Kemiringan Hilal**
   Menampilkan simulasi grafis (Canvas HTML5) ketebalan sabit dan arah kemiringan hilal sesuai posisi azimuthnya terhadap Matahari.
5. **Ekspor Laporan Gambar (PNG)**
   Unduh hasil hisab dalam satu klik menjadi gambar resolusi tinggi yang siap dibagikan ke WhatsApp atau media sosial.

---

## 📖 Panduan Penggunaan Aplikasi

Aplikasi ini sangat mudah digunakan hanya dalam **4 langkah**:

### 1. Pilih Tanggal Pengamatan (Masehi)
* Klik pada kolom **Tanggal Pengamatan (Masehi)**.
* Pilih tanggal yang bertepatan dengan **hari ke-29 bulan Hijriyah** (hari pelaksanaan *Rukyatul Hilal* / Sidang Isbat).
* *Catatan:* Jika Anda memilih tanggal di pertengahan bulan (jauh dari fase konjungsi/ijtimak), aplikasi akan memberikan peringatan otomatis bahwa tanggal tersebut berada di luar fase pengamatan hilal.

### 2. Atur Koordinat Lokasi Pengamatan
Anda bisa menentukan lokasi dengan dua cara:
* **Otomatis (Disarankan):** Klik tombol **"Gunakan Lokasi Saya (GPS)"**, lalu klik **Izinkan (*Allow*)** saat browser meminta akses lokasi. Koordinat Lintang dan Bujur akan terisi otomatis.
* **Manual:** Masukkan angka **Lintang** (gunakan tanda minus `-` untuk Lintang Selatan, contoh: `-6.1754` untuk Jakarta) dan **Bujur** (contoh: `106.8272` untuk Jakarta).

### 3. Pilih Kriteria Penentuan Awal Bulan
Klik pada menu dropdown **Kriteria Penentuan Awal Bulan** dan pilih metode yang ingin digunakan:
* Pilih **MABIMS Baru** untuk melihat prediksi berdasarkan standar Pemerintah (Kemenag RI).
* Pilih **Wujudul Hilal** untuk melihat prediksi berdasarkan kriteria hisab hakiki wujudul hilal.

### 4. Hitung & Unduh Laporan
* Klik tombol **"Hitung Awal Bulan"**.
* Hasil perhitungan akan langsung muncul lengkap dengan kesimpulan apakah **malam ini sudah masuk tanggal 1 bulan baru** atau **digenapkan (Istikmal) 30 hari**.
* Klik tombol **"Unduh Laporan Gambar"** di bagian bawah untuk menyimpan kartu hasil hisab ke galeri perangkat Anda dalam format `.png`.

---

## 🧪 Tabel Contoh Pengujian (Test Case)

Untuk menguji akurasi perhitungan dan logika kesimpulan aplikasi (menggunakan koordinat default **Jakarta: Lintang `-6.1754`, Bujur `106.8272`**), silakan masukkan tanggal-tanggal penting berikut:

| Momen Pengamatan | Input Tanggal Masehi | Kondisi Astronomis (Saat Ghurub di Jakarta) | Hasil Kriteria MABIMS Baru | Hasil Kriteria Wujudul Hilal |
| :--- | :---: | :--- | :--- | :--- |
| **Menjelang 1 Ramadhan 1448 H**<br>*(29 Sya'ban 1448 H)* | `2027-02-07` | • Ijtimak: ±12:56 WIB<br>• Tinggi Hilal: ±2,1° *(di atas ufuk, tapi < 3°)*<br>• Elongasi: ±3,8° *(< 6,4°)* | ❌ **Belum Masuk (Istikmal)**<br>*(1 Ramadhan = 9 Feb 2027)* | ✅ **Sudah Masuk Tanggal 1**<br>*(1 Ramadhan = 8 Feb 2027)* |
| **Menjelang 1 Syawal 1448 H**<br>*(29 Ramadhan 1448 H)* | `2027-03-08` | • Ijtimak: ±16:29 WIB<br>• Tinggi Hilal: ±-0,3° *(di bawah ufuk)*<br>• Elongasi: ±1,5° | ❌ **Belum Masuk (Istikmal)**<br>*(1 Syawal = 10 Mar 2027)* | ❌ **Belum Masuk (Istikmal)**<br>*(1 Syawal = 10 Mar 2027)* |
| **Menjelang 1 Syawal 1448 H**<br>*(Uji H+1 / 30 Ramadhan 1448 H)* | `2027-03-09` | • Ijtimak: Kemarin (8 Mar)<br>• Tinggi Hilal: ±11,5° *(≥ 3°)*<br>• Elongasi: ±13,2° *(≥ 6,4°)* | ✅ **Sudah Masuk Tanggal 1**<br>*(1 Syawal = 10 Mar 2027)* | ✅ **Sudah Masuk Tanggal 1**<br>*(1 Syawal = 10 Mar 2027)* |
| **Menjelang 1 Dzulhijjah 1448 H**<br>*(29 Dzulqa'dah 1448 H)* | `2027-05-06` | • Ijtimak: ±17:58 WIB *(Setelah Ghurub Jakarta)*<br>• Status: *Ijtimak Ba'dal Ghurub* | ❌ **Belum Masuk (Istikmal)**<br>*(1 Dzulhijjah = 8 Mei 2027)* | ❌ **Belum Masuk (Istikmal)**<br>*(1 Dzulhijjah = 8 Mei 2027)* |
| **Menjelang 1 Ramadhan 1449 H**<br>*(29 Sya'ban 1449 H)* | `2028-01-27` | • Ijtimak: ±22:12 WIB *(Malam hari setelah Ghurub)*<br>• Tinggi Hilal: Negatif | ❌ **Belum Masuk (Istikmal)**<br>*(1 Ramadhan = 29 Jan 2028)* | ❌ **Belum Masuk (Istikmal)**<br>*(1 Ramadhan = 29 Jan 2028)* |
| **Menjelang 1 Syawal 1449 H**<br>*(29 Ramadhan 1449 H)* | `2028-02-26` | • Ijtimak: ±17:37 WIB<br>• Tinggi Hilal: ±8,2° *(≥ 3°)*<br>• Elongasi: ±10,1° *(≥ 6,4°)* | ✅ **Sudah Masuk Tanggal 1**<br>*(1 Syawal = 27 Feb 2028)* | ✅ **Sudah Masuk Tanggal 1**<br>*(1 Syawal = 27 Feb 2028)* |
| **Uji Tanggal di Luar Fase Hilal**<br>*(Pertengahan Bulan / Purnama)* | `2027-02-20` | • Umur Bulan: ±13 hari dari Ijtimak<br>• Posisi Bulan jauh dari Matahari | ⚠️ **Peringatan Kuning**<br>*(Di luar fase pengamatan hilal)* | ⚠️ **Peringatan Kuning**<br>*(Di luar fase pengamatan hilal)* |

---

## 📊 Cara Membaca Hasil Hisab

Agar tidak salah memahami data yang tampil di layar, berikut penjelasan singkat setiap istilahnya:

| Parameter | Penjelasan Mudah |
| :--- | :--- |
| **Status Badge (Kotak Atas)** | Kesimpulan akhir disertai alasan logisnya: **Hijau** (Sudah masuk tanggal 1 mulai Maghrib nanti), **Merah** (Belum masuk / Istikmal 30 hari), atau **Kuning** (Tanggal yang dipilih bukan hari pengamatan hilal). |
| **Waktu Ijtimak (Konjungsi)** | Detik ketika posisi Bulan dan Matahari berada pada satu garis bujur ekliptika yang sama (fase Bulan Baru astronomis). Syarat mutlak awal bulan adalah Ijtimak harus terjadi **sebelum** Matahari terbenam. |
| **Terbenam Matahari (Ghurub)** | Waktu Maghrib (terbenamnya piringan atas Matahari di ufuk barat) pada lokasi koordinat yang dimasukkan. |
| **Tinggi Hilal (Mar'i / Haqiqi)** | Ketinggian Bulan di atas ufuk saat Matahari terbenam.<br>• **Mar'i (Tampak):** Tinggi yang sudah dikoreksi parallaks & pembiasan atmosfer (dipakai untuk standar MABIMS).<br>• **Haqiqi (Geosentris):** Tinggi Bulan dihitung dari titik pusat Bumi. |
| **Sudut Elongasi** | Jarak sudut lengkung antara pusat piringan Bulan dan pusat piringan Matahari. Semakin besar elongasinya, semakin tebal sabit hilal yang terlihat. |
| **Azimuth & Posisi Hilal** | Arah mata angin posisi Bulan dari Utara searah jarum jam (barat = sekitar 270°), disertai keterangan apakah posisi Bulan berada di sebelah **Utara** atau **Selatan** titik terbenamnya Matahari. |

---

## 🚀 Cara Menjalankan di Perangkat Lokal

Aplikasi ini bersifat *standalone* (mandiri) dan tidak memerlukan instalasi database atau server khusus:

1. Unduh atau *clone* repositori ini.
2. Buka file `index.html` langsung menggunakan browser modern (Chrome, Edge, Safari, atau Firefox).
3. Pastikan perangkat terhubung ke internet saat pertama kali membuka aplikasi untuk memuat ikon (*FontAwesome*), font (*Google Fonts*), dan pustaka cetak gambar (*html2canvas*).
   > **Tips:** Fitur pendeteksi lokasi GPS pada browser memerlukan koneksi aman (`https://`) atau dijalankan melalui `localhost`.

---

## 👨‍💻 Kredit & Informasi Pengembang

* **Developer:** **fatur62**
* **Referensi Algoritma:** Jean Meeus (*Astronomical Algorithms*) & Transformasi Koordinat Bola Ekuatorial-Horizontal.
