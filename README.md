# Tugas CI/CD Pipeline – Minggu 11

[![CI](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/ci.yml/badge.svg)](https://github.com/a7305260-beep/ci-cd-minggu11/actions/workflows/ci.yml)

## 1. Identitas

- **Nama:** Maria Stevania Ananda
- **NIM:** 202557201017
- **Program Studi:** Sistem Informasi
- **Mata Kuliah:** Teknologi Open Source
- **Tugas:** Minggu 11 – CI/CD Pipeline

## 2. Deskripsi Proyek

Proyek ini merupakan implementasi Continuous Integration (CI) menggunakan GitHub Actions pada aplikasi kalkulator sederhana berbasis Python.

CI digunakan untuk menjalankan pengujian program secara otomatis dan membangun Docker image setiap kali terdapat perubahan pada repository.

## 3. Teknologi yang Digunakan

- Python 3.11
- Pytest
- Docker
- Git dan GitHub
- GitHub Actions

## 4. Struktur Repository

```text
ci-cd-minggu11/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── Dockerfile
├── kalkulator.py
├── test_kalkulator.py
└── README.md
```

## 5. Alur CI/CD Pipeline

Workflow CI dibuat menggunakan file `ci.yml` yang berada pada folder `.github/workflows/`.

Tahapan proses CI meliputi:

1. Mengambil kode dari repository menggunakan GitHub Actions.
2. Menyiapkan lingkungan Python versi 3.11.
3. Memasang library pytest.
4. Menjalankan pengujian otomatis menggunakan perintah `pytest -v`.
5. Membuat Docker image dengan nama `kalkulator:ci`.
6. Menjalankan container menggunakan perintah `docker run --rm kalkulator:ci`.

## 6. Pengujian Otomatis

Pengujian dilakukan menggunakan framework Pytest dengan file `test_kalkulator.py`.

Perintah yang digunakan:

```bash
pytest -v
```

Pengujian ini bertujuan memastikan fungsi-fungsi pada program kalkulator berjalan sesuai dengan hasil yang diharapkan.

## 7. Docker

Docker digunakan untuk mengemas aplikasi kalkulator ke dalam sebuah image agar dapat dijalankan melalui container.

Perintah untuk membangun image:

```bash
docker build -t kalkulator:ci .
```

Perintah untuk menjalankan container:

```bash
docker run --rm kalkulator:ci
```

## 8. Hasil Praktikum

Penerapan CI/CD dilakukan menggunakan GitHub Actions. Proses workflow mencakup persiapan Python, instalasi Pytest, pengujian otomatis, pembuatan Docker image, dan menjalankan container.

Status workflow dapat dipantau melalui badge CI pada bagian atas README dan tab Actions pada repository GitHub.

## 9. Repository GitHub

Link repository:

https://github.com/a7305260-beep/ci-cd-minggu11

## 10. Kesimpulan

Melalui praktikum ini, mahasiswa mempelajari penerapan Continuous Integration menggunakan GitHub Actions. Pengujian otomatis dengan Pytest membantu memeriksa program kalkulator, sedangkan Docker digunakan untuk membangun image dan menjalankan aplikasi dalam container.

Dengan adanya CI, proses pemeriksaan dan validasi proyek dapat dilakukan secara otomatis sehingga membantu meningkatkan keandalan pengembangan perangkat lunak.
