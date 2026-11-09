# 🌴 Pelesir Palembang

> **Platform Eksplorasi & Panduan Wisata Kota Palembang Berbasis Web**  
> Temukan keindahan ikonik, situs bersejarah, kuliner legendaris, serta *hidden gems* Kota Sriwijaya dengan mudah, interaktif, dan terencana.

---

[![React](https://img.shields.io/badge/React-19.1-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.1-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.1-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Leaflet](https://img.shields.io/badge/Leaflet-Maps-199900?style=for-the-badge&logo=leaflet&logoColor=white)](https://leafletjs.com/)

---

## 📌 Tentang Proyek

**Pelesir Palembang** adalah aplikasi web modern yang dirancang untuk mempermudah wisatawan lokal maupun mancanegara dalam menjelajahi Kota Palembang, Sumatera Selatan. Aplikasi ini menyajikan informasi komprehensif seputar destinasi populer, situs sejarah, wisata religi, dan *hidden gems*, dilengkapi peta interaktif rute perjalanan, kalkulator rencana liburan (*itinerary planner*), serta sistem ulasan komunitas.

---

## ✨ Fitur Utama

- 🗺️ **Peta Wisata Interaktif (Interactive Maps)**
  - Integrasi Leaflet & OpenStreetMap untuk visualisasi titik-titik wisata di Palembang.
  - Fitur deteksi lokasi terkini pengguna (*Geolocation*).
  - Navigasi dan rute otomatis antar destinasi dengan estimasi mode transportasi: **Mobil**, **Motor**, dan **Jalan Kaki** via OpenRouteService API.
  - Simulasi animasi penunjuk rute kendaraan secara *real-time*.

- 🏛️ **Katalog Destinasi Lengkap**
  - Kategori destinasi: **Populer**, **Rekomendasi**, dan **Hidden Gem**.
  - Detail wisata menyeluruh: informasi sejarah/latar belakang, alamat lengkap, jam operasional, harga tiket masuk, fasilitas, galeri foto, dan kontak pengelola.
  - Tombol cepat untuk membuka langsung lokasi destinasi pada peta rute.

- 📅 **Rencana Pelesir (Itinerary Planner)**
  - Susun daftar tempat wisata yang ingin dikunjungi ke dalam rencana perjalanan pribadi.
  - Kalkulasi otomatis total estimasi biaya tiket masuk untuk membantu perencanaan anggaran wisata.
  - Kemudahan menambah, memperbarui (*edit*), dan menghapus daftar kunjungan.

- ⭐ **Ulasan & Rating Komunitas**
  - Berikan rating bintang (1-5) dan ulasan pengalaman berkunjung.
  - Rangkuman rating otomatis (*average rating*, total ulasan, dan diagram distribusi bintang).

- ❤️ **Destinasi Favorit**
  - Simpan destinasi impian ke daftar favorit (*bookmark*) untuk akses cepat kapan saja.

- 👤 **Autentikasi & Manajemen Profil Pengguna**
  - Pendaftaran akun baru (*Sign Up*) dan masuk (*Login*) terlindungi dengan JWT (*JSON Web Token*) & enkripsi kata sandi menggunakan `bcrypt`.
  - Halaman profil personal: perbarui data diri (nama, jenis kelamin, tanggal lahir, nomor telepon) dan unggah foto profil (*avatar*).
  - Fitur Lupa Password (*Forgot Password*).

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: [React 19](https://react.dev/) + [Vite 7](https://vitejs.dev/)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/) & Custom CSS
- **Routing**: [React Router DOM v7](https://reactrouter.com/)
- **State Management**: [Redux Toolkit](https://redux-toolkit.js.org/) & React Context API
- **Icons**: [Lucide React](https://lucide.dev/)
- **Peta & Geospasial**: [Leaflet](https://leafletjs.com/) + OpenRouteService API
- **HTTP Client**: [Axios](https://axios-http.com/)

### Backend
- **Runtime Environment**: [Node.js](https://nodejs.org/)
- **Framework**: [Express.js 5](https://expressjs.com/)
- **Database**: [MySQL](https://www.mysql.com/) (menggunakan driver `mysql2/promise`)
- **Autentikasi & Keamanan**: [JSON Web Token (JWT)](https://jwt.io/) & [Bcryptjs](https://www.npmjs.com/package/bcryptjs)
- **Upload File**: [Multer](https://github.com/expressjs/multer)
- **CORS & Environment**: `cors`, `dotenv`

---

## 📂 Struktur Direktori

```text
MassiveProject/
├── backend/
│   ├── config/
│   │   └── db.js                 # Koneksi database MySQL
│   ├── middleware/
│   │   ├── authMiddleware.js     # Validasi JWT token
│   │   └── upload.js             # Konfigurasi multer untuk upload foto
│   ├── routes/
│   │   ├── auth.js               # Route signup, login, forgot password
│   │   ├── favorites.js          # Route CRUD destinasi favorit
│   │   ├── itinerary.js          # Route manajemen rencana perjalanan
│   │   ├── profile.js            # Route get & update profil pengguna
│   │   └── reviews.js            # Route ulasan dan rating
│   ├── scripts/
│   │   └── migrate-passwords.js  # Utilitas migrasi password hash
│   ├── uploads/                  # Penyimpanan berkas foto profil yang diunggah
│   ├── .env.example              # Contoh variabel environment backend
│   ├── package.json
│   └── server.js                 # Entry point server Express
│
├── frontend/
│   ├── public/
│   │   ├── icon/                 # Ikon penunjuk dan navigasi
│   │   ├── img/                  # Aset gambar destinasi utama
│   │   └── reco/                 # Gambar rekomendasi tempat wisata
│   ├── src/
│   │   ├── assets/               # Aset statis frontend
│   │   ├── components/           # Komponen UI modular
│   │   │   ├── common/           # Navbar, Footer, ProtectedRoute
│   │   │   ├── destinations/     # Filter bar & komponen list destinasi
│   │   │   ├── detail/           # Komponen halaman detail tempat
│   │   │   ├── home/             # Hero banner, slider, interactive map preview
│   │   │   ├── maps/             # Komponen utama Peta Leaflet & Rute
│   │   │   └── popup/            # Modal dialog / popup interaktif
│   │   ├── config/               # Konfigurasi URL API
│   │   ├── context/              # Context Auth & Favorites
│   │   ├── data/                 # Dataset statis destinasi & rincian tempat
│   │   ├── hooks/                # Custom React Hooks
│   │   ├── pages/                # Halaman utama aplikasi (Home, Destinasi, Detail, dll)
│   │   ├── styles/               # Styling CSS spesifik modul
│   │   ├── App.jsx               # Konfigurasi route aplikasi
│   │   └── main.jsx              # Entry point React
│   ├── .env.example              # Contoh variabel environment frontend
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
└── README.md
```

---

## 🗄️ Skema Database (MySQL)

Buat database MySQL baru dengan nama `massive_project`, lalu jalankan query tabel berikut:

```sql
CREATE DATABASE IF NOT EXISTS massive_project;
USE massive_project;

-- 1. Tabel Profil Pengguna
CREATE TABLE IF NOT EXISTS profile (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nama VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    foto VARCHAR(255) DEFAULT '/avatar-default.png',
    gender ENUM('Laki-laki', 'Perempuan') DEFAULT NULL,
    tanggal_lahir DATE DEFAULT NULL,
    no_telpon VARCHAR(20) DEFAULT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 2. Tabel Destinasi Favorit
CREATE TABLE IF NOT EXISTS favorites (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    place_id VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    UNIQUE KEY unique_fav (user_id, place_id),
    FOREIGN KEY (user_id) REFERENCES profile(id) ON DELETE CASCADE
);

-- 3. Tabel Ulasan & Rating
CREATE TABLE IF NOT EXISTS reviews (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    place_id VARCHAR(100) NOT NULL,
    rating INT NOT NULL CHECK (rating >= 1 AND rating <= 5),
    comment TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES profile(id) ON DELETE CASCADE
);

-- 4. Tabel Rencana Pelesir (Itinerary)
CREATE TABLE IF NOT EXISTS itinerary (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    place_id VARCHAR(100) NOT NULL,
    ticket_price DECIMAL(10,2) DEFAULT 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES profile(id) ON DELETE CASCADE
);
```

---

## 🚀 Panduan Instalasi & Menjalankan

### 1. Prasyarat Sistem
Pastikan perangkat Anda telah terpasang:
- [Node.js](https://nodejs.org/) (versi 18 ke atas disarankan)
- [MySQL Server](https://dev.mysql.com/downloads/mysql/) atau XAMPP / Laragon
- [Git](https://git-scm.com/)

### 2. Kloning Repositori
```bash
git clone https://github.com/limaribuu/MassiveProject.git
cd MassiveProject
```

### 3. Konfigurasi & Menjalankan Backend

1. Masuk ke direktori `backend`:
   ```bash
   cd backend
   ```
2. Pasang dependensi:
   ```bash
   npm install
   ```
3. Buat file `.env` berdasarkan template:
   ```bash
   cp .env.example .env
   ```
4. Sesuaikan konfigurasi pada file `.env`:
   ```env
   PORT=5000
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_mysql_password
   DB_NAME=massive_project
   UPLOAD_DIR=uploads
   JWT_SECRET=rahasia_kunci_jwt_anda
   JWT_EXPIRES_IN=7d
   ```
5. Jalankan server backend:
   ```bash
   npm run dev
   # Server berjalan di http://localhost:5000
   ```

### 4. Konfigurasi & Menjalankan Frontend

1. Buka terminal baru dan masuk ke direktori `frontend`:
   ```bash
   cd frontend
   ```
2. Pasang dependensi:
   ```bash
   npm install
   ```
3. (Opsional) Buat file `.env` jika ingin mengubah URL backend default:
   ```bash
   cp .env.example .env
   ```
4. Jalankan server pengembang (*development server*):
   ```bash
   npm run dev
   # Akses aplikasi di browser melalui http://localhost:5173
   ```

---

## 📡 Dokumentasi Endpoint API

| Kategori | Method | Endpoint | Keterangan | Autentikasi |
| :--- | :---: | :--- | :--- | :---: |
| **Auth** | `POST` | `/api/signup` | Pendaftaran akun baru | Tidak |
| **Auth** | `POST` | `/api/login` | Masuk & peroleh token JWT | Tidak |
| **Auth** | `POST` | `/api/forgot` | Permintaan reset/lupa kata sandi | Tidak |
| **Profile** | `GET` | `/api/profile` | Mengambil data profil yang sedang login | Ya (Bearer) |
| **Profile** | `PUT` | `/api/profile` | Memperbarui data diri pengguna | Ya (Bearer) |
| **Profile** | `POST` | `/api/profile/avatar` | Mengunggah foto profil (*multipart*) | Ya (Bearer) |
| **Favorites**| `GET` | `/api/favorites` | Menampilkan seluruh ID tempat favorit | Ya (Bearer) |
| **Favorites**| `POST` | `/api/favorites` | Menambahkan tempat ke favorit | Ya (Bearer) |
| **Favorites**| `DELETE`| `/api/favorites/:placeId` | Menghapus tempat dari favorit | Ya (Bearer) |
| **Itinerary**| `GET` | `/api/itinerary` | Mengambil daftar rencana & total biaya | Ya (Bearer) |
| **Itinerary**| `POST` | `/api/itinerary/add` | Menambah/memperbarui item rencana | Ya (Bearer) |
| **Itinerary**| `DELETE`| `/api/itinerary/:id` | Menghapus item dari rencana pelesir | Ya (Bearer) |
| **Reviews** | `GET` | `/api/reviews/:placeId`| Mengambil daftar ulasan & ringkasan rating | Tidak |
| **Reviews** | `POST` | `/api/reviews` | Mengirim ulasan & rating bintang | Ya (Bearer) |

---

## 👥 Kontributor & Pengembang

Proyek ini dikembangkan sebagai karya kolaboratif untuk memajukan pariwisata digital Kota Palembang:
- **Muhammad Alif Ramadhani** ([@muhalif1604](https://github.com/limaribuu))
- Tim Pengembang **Massive Project**

---

## 📄 Lisensi

Didistribusikan di bawah Lisensi **ISC**. Silakan periksa file lisensi untuk informasi selengkapnya.
