
# Tugas CI/CD Pipeline – Minggu 11

[![CI](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/ci.yml/badge.svg)](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/ci.yml)

[![Compose Check](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/compose-check.yml/badge.svg)](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/compose-check.yml)

## 1. Identitas

- **Nama:** Maria Stevania Ananda
- **NIM:** 202557201017
- **Program Studi:** Sistem Informasi
- **Mata Kuliah:** Teknologi Open Source
- **Tugas:** Minggu 11 – CI/CD Pipeline

## 2. Deskripsi Proyek

Proyek ini merupakan implementasi Continuous Integration (CI) menggunakan GitHub Actions pada aplikasi kalkulator sederhana berbasis Python serta validasi konfigurasi Docker Compose.

Pipeline dibuat untuk menjalankan pengujian program secara otomatis dan memeriksa konfigurasi layanan Docker Compose setiap kali terdapat perubahan pada repository.

## 3. Teknologi yang Digunakan

- Python 3.11
- Pytest
- Docker
- Docker Compose
- Git dan GitHub
- GitHub Actions
- YAML

## 4. Struktur Repository

```text
ci-cd-minggu11/
│
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── compose-check.yml
│
├── .env.example
├── .gitignore
├── compose.yaml
├── Dockerfile
├── kalkulator.py
├── test_kalkulator.py
└── README.md
```

## 5. Alur CI Pipeline

Workflow CI menggunakan file `ci.yml` yang berada pada folder `.github/workflows/`.

Tahapan proses CI meliputi:

1. Mengambil kode dari repository menggunakan GitHub Actions.
2. Menyiapkan lingkungan Python versi 3.11.
3. Memasang library Pytest.
4. Menjalankan pengujian otomatis menggunakan perintah `pytest -v`.
5. Membuat Docker image dengan nama `kalkulator:ci`.
6. Menjalankan container menggunakan perintah `docker run --rm kalkulator:ci`.

## 6. Validasi Docker Compose

Validasi Docker Compose menggunakan file `compose.yaml` dan workflow `compose-check.yml`.

Tahapan validasi meliputi:

1. Mengambil kode repository menggunakan GitHub Actions.
2. Menyalin `.env.example` menjadi `.env`.
3. Menjalankan perintah `docker compose config -q`.
4. Memeriksa apakah konfigurasi Docker Compose sudah benar.

Konfigurasi menggunakan layanan WordPress dan MariaDB.

## 7. Pengujian Workflow

Pengujian dilakukan melalui dua kondisi:

1. Kondisi berhasil: konfigurasi Docker Compose diperbaiki sehingga workflow menunjukkan status berhasil (hijau).
2. Kondisi gagal: indentation pada bagian `volumes` sengaja diubah sehingga konfigurasi tidak valid dan workflow menunjukkan status gagal (merah).

Setelah kesalahan diperbaiki, perubahan dikirim kembali ke GitHub dan Pull Request digabungkan ke branch `main`.

## 8. Hasil Praktikum

Praktikum berhasil menerapkan dua workflow GitHub Actions, yaitu:

- CI untuk pengujian program Python dan pembuatan Docker image.
- Compose Check untuk validasi konfigurasi Docker Compose.

Status kedua workflow dapat dipantau melalui badge pada README dan tab Actions di GitHub.

## 9. Repository GitHub

Link repository:

https://github.com/a7305260-beep/ci-cd-minggu11

## 10. Kesimpulan

Melalui praktikum ini, mahasiswa mempelajari penerapan Continuous Integration menggunakan GitHub Actions, pengujian otomatis, penggunaan Docker, serta validasi konfigurasi Docker Compose.

Praktikum ini juga memberikan pemahaman mengenai pentingnya pengujian otomatis untuk mendeteksi kesalahan konfigurasi sebelum perubahan diterapkan ke branch utama.

