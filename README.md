# 🚀 SQL Basic Queries Portfolio Case Study

Proyek ini mendokumentasikan serangkaian **query SQL dasar** yang dibuat untuk praktik manipulasi dan pengambilan data dari dua skema database: **`dibimbing`** (pembuatan skema baru) dan **`dvdrental`** (kueri pada data yang sudah ada).

Case study ini mencakup pembuatan tabel (DDL), penyisipan data (DML), fungsi agregasi, logika kondisional (`CASE`), penggabungan tabel (`JOIN`), dan operasi set (`UNION`).

---

## 1. 🛠️ Pembuatan Database dan Tabel Students

Bagian ini berfokus pada perintah dasar DDL (Data Definition Language) dan DML (Data Manipulation Language) untuk membuat lingkungan database dan mengisi data.

### 📝 Tugas

1.  Membuat database bernama **`dibimbing`**.
2.  Membuat tabel **`students`** dengan skema: `id` (PK, int), `nama` (varchar), `institute` (varchar), `berat_badan` (float), dan `tinggi_badan` (float).
3.  Memasukkan minimal 5 data ke dalam tabel `students`.

### 📄 Query Utama

```sql
-- Membuat database
CREATE DATABASE dibimbing;

-- Membuat table
CREATE TABLE students (
    id INT PRIMARY KEY,
    nama VARCHAR(100),
    institute VARCHAR(100),
    berat_badan FLOAT,
    tinggi_badan FLOAT
);

-- Insert value
INSERT INTO students (id, nama, institute, berat_badan, tinggi_badan)
VALUES
(1, 'Ayman Ahnaf', 'Universitas Muhammadiyah Yogyakarta', 65.5, 172.0),
(2, 'Nadia Putri', 'Universitas Indonesia', 54.2, 160.3),
(3, 'Rizky Pratama', 'Institut Teknologi Bandung', 70.8, 178.4),
(4, 'Siti Nurhaliza', 'Universitas Airlangga', 49.7, 158.9),
(5, 'Dimas Saputra', 'Universitas Gadjah Mada', 80.1, 182.5);

select * from students;
```

## 2. 💻 Query Data pada Skema `dvdrental`

Bagian ini berfokus pada pengambilan dan analisis data menggunakan operator SQL standar dan lanjutan.

### 2.1. Memilih Aktor Tertentu

Menampilkan `first_name` dan `last_name` dari aktor yang memiliki `first_name` **"Jennifer", "Nick", atau "Ed"**.

```sql
SELECT first_name, last_name
FROM actor
WHERE first_name IN ('Jennifer', 'Nick', 'Ed');
```

## 2.2. Agregasi dan Subquery
Menghitung total pembayaran (`amount`) untuk setiap `payment_id` yang lebih besar dari 5.99. Query ini menggunakan fungsi agregasi (SUM) dan subquery untuk menampilkan total transaksi dan total pembayaran keseluruhan yang memenuhi kriteria.

```sql
SELECT 
    p.payment_id,
    SUM(p.amount) AS "total_amount (>5.99)",
    (SELECT COUNT(*) FROM payment WHERE amount > 5.99) AS "jumlah_transaksi_total (>5.99)",
    (SELECT SUM(amount) FROM payment WHERE amount > 5.99) AS "total_pembayaran (>5.99)"
FROM payment p
WHERE p.amount > 5.99
GROUP BY p.payment_id;
```
