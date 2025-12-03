# 🚀 SQL Basic Queries Portfolio Case Study

[cite_start]Proyek ini mendokumentasikan serangkaian **query SQL dasar** [cite: 1] [cite_start]yang dibuat untuk praktik manipulasi dan pengambilan data dari dua skema database: **`dibimbing`** (pembuatan skema baru) [cite: 2] dan **`dvdrental`** (kueri pada data yang sudah ada).

[cite_start]Case study ini mencakup pembuatan tabel (DDL), penyisipan data (DML)[cite: 2], fungsi agregasi, logika kondisional (`CASE`), penggabungan tabel (`JOIN`), dan operasi set (`UNION`).

---

## 🛠️ Case Study 1: Pembuatan Skema Baru (`dibimbing`)

Tujuan utama dari bagian ini adalah mendemonstrasikan kemampuan untuk membuat struktur database dan memasukkan data.

### 📝 Tugas

1.  [cite_start]Membuat database bernama `dibimbing`[cite: 3].
2.  [cite_start]Membuat tabel `students` dengan skema: `id` (PK, int), `nama` (varchar), `institute` (varchar), `berat_badan` (float), dan `tinggi_badan` (float)[cite: 7, 8, 9, 10, 11, 12].
3.  [cite_start]Memasukkan minimal 5 data ke dalam tabel `students`[cite: 21].

### 📂 File Terkait

* `Case Study Basic SQL Queries (No 1).sql`

---

## 💻 Case Study 2: Query Data pada Skema `dvdrental`

Bagian ini berfokus pada pengambilan dan analisis data menggunakan operator SQL standar dan lanjutan.

### 1. Kueri dengan `WHERE` dan `IN`

[cite_start]Menampilkan `first_name` dan `last_name` dari aktor yang memiliki `first_name` "Jennifer", "Nick", atau "Ed"[cite: 33].

```sql
SELECT first_name, last_name
FROM actor
WHERE first_name IN ('Jennifer', 'Nick', 'Ed');
