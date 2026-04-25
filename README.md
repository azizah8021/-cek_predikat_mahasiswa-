# Cek Predikat Mahasiswa

Repositori ini memuat kode *Stored Procedure* MySQL sederhana untuk menentukan predikat akademik dan status kelulusan mahasiswa berdasarkan nilai akhirnya. Kode ini dirancang efisien memanfaatkan alur turun (*Top-Down*) pada struktur kondisinya (`IF - ELSEIF`).

## 📋 Deskripsi Logika

Prosedur bernama `cek_predikat_mahasiswa` mendefinisikan satu buah input `p_nilai` (bertipe `INT`).
Setelah nilai dimasukkan, prosedur akan melakukan dua pengecekan sekaligus:

### 1. Penentuan Predikat
- Nilai **≥ 90**: Sangat Memuaskan
- Nilai **≥ 80**: Memuaskan
- Nilai **≥ 70**: Baik
- Nilai **≥ 60**: Cukup
- Nilai **< 60** : Kurang

### 2. Penentuan Kelulusan
- **Lulus** jika nilai minimal `70`
- **Tidak Lulus** jika nilainya di bawah `70`

## 🚀 Cara Menjalankan

1. Eksekusi (*Run* / *Go*) blok kode mulai dari tulisan `DELIMITER //` hingga `DELIMITER ;` pada *tab* **SQL** di aplikasi Database Management Anda (XAMPP phpMyAdmin, DBeaver, DataGrip, dll) untuk menciptakan prosedurnya.
2. Panggil prosedurnya dengan nilai ujian yang mau Anda tes menggunakan pernyataan `CALL`. 

**Contoh Perintah Eksekusi:**
```sql
CALL cek_predikat_mahasiswa(90);
```

**Hasil yang didapatkan:**
Akan muncul sebuah tabel *Select* yang berisi 3 kolom yakni `nilai`, `predikat`, dan `status`.

| nilai | predikat | status |
|---|---|---|
| 90 | Memuaskan | Lulus |# -cek_predikat_mahasiswa-
