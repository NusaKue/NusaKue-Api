# 🌟 NusaKue API 🍰🏪  
**Kenali, Jelajahi, dan Cintai Kue Tradisional Indonesia Lewat Gambar!**

NusaKue API adalah jembatan pintar yang menghubungkan teknologi dengan kekayaan kuliner Nusantara.  
Dengan kekuatan **TensorFlow.js** dan **Hapi.js**, API ini mampu mengenali kue tradisional Indonesia hanya dari gambar 📷.  
Tak hanya itu, Anda juga dapat mengelola data kue, UMKM lokal, melihat statistik tren kue, dan mendapatkan rekomendasi UMKM terbaik! 🇮🇩✨

---
## 📦 NusaKueApi Dokumentasi
[https://documenter.getpostman.com/view/34670049/2sB2qgcxna](https://documenter.getpostman.com/view/34670049/2sB2qgcxna)


## 🚀 Cara Memulai

### 🔑 Persiapan Firebase
Project ini membutuhkan file kredensial Firebase (`firebaseKey.json`).  
Pastikan Anda memiliki file ini dan letakkan di folder src/config sebelum menjalankan server.



### 1. Clone repositori
```bash
git clone https://github.com/username/nusakueapi.git
cd nusakueapi
```

### 2. Pasang dependensi
```bash
npm install
```

### 3. Jalankan server
```bash
npm run start
```

### 4. Akses API di browser atau tool API seperti Postman
```
http://localhost:3000
```

---

## 📦 Teknologi yang Digunakan

- 🧠 **TensorFlow.js** – Prediksi kue dari gambar
- ⚙️ **Hapi.js** – Framework backend untuk menyusun API
- 🔥 **Firebase Firestore** – Penyimpanan data kue & UMKM
- 🖼️ **Firebase Cloud Storage** – Penyimpanan gambar
- ✂️ **Sharp** – Preprocessing gambar agar siap diprediksi

---

## 🔗 Base URL
```
http://localhost:3000
```

---

## 📌 Endpoints

### 🍰 Kue – Jelajahi Aneka Kue Tradisional
| Method | Endpoint       | Deskripsi                                      |
|--------|----------------|-----------------------------------------------|
| GET    | `/cakes`       | Lihat daftar lengkap kue Nusantara            |
| GET    | `/cakes/{id}`  | Lihat detail kue berdasarkan ID               |
| POST   | `/cakes`       | Tambah kue baru                               |
| PUT    | `/cakes/{id}`  | Perbarui data kue                             |
| DELETE | `/cakes/{id}`  | Hapus data kue                                |

**Form-data untuk `POST /cakes`:**
- `nama`: string
- `asal`: JSON array string (contoh: ["Jawa", "Sumatra"])
- `bahan_pembuatan`: JSON array string
- `budaya`: string
- `cara_pembuatan`: string
- `deskripsi`: string
- `image`: file

---

### 🤖 Prediksi – Kue Apa Ya Ini?
| Method | Endpoint           | Deskripsi                                   |
|--------|--------------------|---------------------------------------------|
| POST   | `/predict`         | Upload gambar, dapatkan prediksi nama kue   |
| GET    | `/top-predictions` | 5 kue yang paling sering dikenali model     |

**Form-data untuk `POST /predict`:**
- `image`: file (gambar kue)

---

### 🏪 UMKM – Dukung Pelaku Usaha Lokal
| Method | Endpoint       | Deskripsi                                      |
|--------|----------------|-----------------------------------------------|
| GET    | `/umkms`       | Ambil semua data UMKM                         |
| GET    | `/umkms/{id}`  | Ambil detail UMKM berdasarkan ID              |
| POST   | `/umkms`       | Tambah UMKM baru                              |
| PUT    | `/umkms/{id}`  | Perbarui data UMKM                            |
| DELETE | `/umkms/{id}`  | Hapus UMKM berdasarkan ID                     |

**Form-data untuk `POST /umkms`:**
- `nama`: string
- `alamat`: string
- `no_telp`: string
- `paling_diminati`: JSON array string (contoh: ["Kue A","Kue B"])
- `image`: file (opsional)

---

### 🎯 Rekomendasi UMKM – Cocok Buat Kamu!
| Method | Endpoint                | Deskripsi                                      |
|--------|-------------------------|-----------------------------------------------|
| GET    | `/recommendation/{id}`  | Rekomendasi UMKM berdasarkan ID kue tertentu  |

---

## 📄 Format Respon

- **Cake** – Info lengkap: nama, asal, bahan, budaya, cara, gambar
- **Umkm** – Info UMKM: nama, alamat, kontak, produk favorit
- **PredictionData** – Hasil prediksi: nama kue, skor keyakinan, metadata
- **TopPrediction** – Daftar 5 kue yang paling sering dikenali
- **FailResponse / ErrorResponse** – Format error standar: status dan pesan

---

## 🎉 Misi NusaKue
> NusaKue API adalah langkah awal untuk mendigitalisasi dan mempopulerkan warisan kuliner Indonesia.  
Dukung UMKM lokal, edukasi generasi muda, dan bangkitkan kembali kecintaan terhadap kue-kue tradisional Nusantara! 🇮🇩🍽️
