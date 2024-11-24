# AplikasiPenghitungHari
 Tugas4 - Muhammad Ihsan - 2210010286

## 1. Deskripsi Program
Aplikasi ini digunakan untuk menghitung jumlah hari dalam bulan tertentu pada tahun yang dipilih oleh pengguna, serta memberikan informasi tentang hari pertama dan terakhir dalam bulan tersebut. Program ini juga dapat menghitung selisih hari antara dua tanggal yang dipilih melalui kalender.

### Fitur:
- **Hitung Jumlah Hari**: Menghitung jumlah hari dalam bulan tertentu berdasarkan tahun yang dipilih.
- **Hitung Selisih Hari**: Menghitung jumlah hari antara dua tanggal yang dipilih.
- **Reset**: Menghapus atau mereset inputan bulan, tahun, dan kalender.
- **Keluar**: Menutup aplikasi.

## 2. Komponen GUI:
- **JFrame**: Untuk tampilan utama aplikasi.
- **JPanel**: Sebagai wadah untuk menampung komponen lainnya.
- **JLabel**: Untuk menampilkan informasi dan hasil perhitungan.
- **JComboBox**: Untuk memilih bulan.
- **JSpinner**: Untuk memilih tahun.
- **JCalendar**: Untuk memilih tanggal secara visual.
- **JButton**: Untuk tombol-tombol interaksi (Hitung, Hitung Selisih Hari, Hapus, Keluar).

## 3. Logika Program:
- **Menggunakan API `LocalDate` dan `YearMonth`**: Untuk mengelola tanggal dan bulan.
- **Perhitungan Jumlah Hari dalam Bulan**: Menggunakan `YearMonth` untuk menghitung jumlah hari dalam bulan tertentu.
- **Tahun Kabisat**: Menentukan apakah tahun tersebut adalah tahun kabisat atau bukan.
- **Selisih Hari**: Menggunakan `ChronoUnit.DAYS` untuk menghitung selisih hari antara dua tanggal yang dipilih.

## 4. Events:
- **ActionListener pada Tombol Hitung**:
  Tombol Hitung akan memanggil metode untuk menghitung jumlah hari dalam bulan yang dipilih.
  
```java
private void TombolHitungActionPerformed(java.awt.event.ActionEvent evt) {
    TombolHitung.addActionListener((ActionEvent e) -> {
        HitungHari();
    });
}
```

- **ActionListener pada Tombol Hitung Selisih Hari**:
  Tombol Hitung Selisih Hari akan memanggil metode untuk menghitung selisih hari antara dua tanggal.

```java
private void TombolHitungSelisihHariActionPerformed(java.awt.event.ActionEvent evt) {
    TombolHitungSelisihHari.addActionListener((ActionEvent e) -> {
        HitungSelisih();
    });
}
```

- **ActionListener pada Tombol Hapus**:
  Tombol Hapus akan memanggil metode untuk menghapus atau mereset semua inputan dan hasil perhitungan.

```java
private void TombolHapusActionPerformed(java.awt.event.ActionEvent evt) {
    TombolHapus.addActionListener((ActionEvent e) -> {
        HapusInputan();
    });
}
```

- **ActionListener pada Tombol Keluar**:
  Tombol Keluar akan menutup aplikasi.

```java
private void TombolKeluarActionPerformed(java.awt.event.ActionEvent evt) {
    System.exit(0);
}
```

## 5. Variasi:
- **Tampilkan informasi hari pertama dan hari terakhir dalam bulan**:
  Setelah menghitung jumlah hari, aplikasi juga menampilkan hari pertama dan hari terakhir dalam bulan yang dipilih.

```java
String hariAwal = HariBahasaIndo(hariPertama.getDayOfWeek());
String hariAkhir = HariBahasaIndo(hariTerakhir.getDayOfWeek());
```

- **Hitung Selisih Hari**:
  Menghitung jumlah hari antara dua tanggal menggunakan `ChronoUnit.DAYS`:

```java
private void HitungSelisih() {
    Calendar startCal = KalenderAwal.getCalendar();
    Calendar endCal = KalenderAkhir.getCalendar();
    
    LocalDate startDate = startCal.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
    LocalDate endDate = endCal.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
    
    long daysBetween = ChronoUnit.DAYS.between(startDate, endDate);
    LabelHasilSelisihHari.setText("Selisih hari antara dua tanggal: " + daysBetween + " hari");
}
```

## 6. Hasil Gambar Project Ketika Di-Run

![Tugas4](https://github.com/user-attachments/assets/6f3c3d56-927d-4d1e-9870-6ff06cb03b46)


## 7. Indikator Penilaian:

| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    10        |
|  2  | Logika Program   |    20        |
|  3  | Event            |    20        |
|  4  | Kesesuaian UI    |    20        |
|  5  | Memenuhi Variasi |    40        |
|     | **TOTAL**        | **100**      |

## Pembuat

- **Nama**: Muhammad Ihsan
- **NPM**: 2210010286
- **Kelas**: 5A Ti Reg Pagi BJM
