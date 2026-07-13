# 📸 Product Requirements Document (PRD): Online Photobooth

## 📑 Product Overview
* **Product Name:** Online Photobooth
* **Objective:** Membangun aplikasi web photobooth interaktif yang memungkinkan pengguna mengambil foto bersama secara real-time, baik secara lokal maupun kolaborasi jarak jauh (LDR), dengan fitur yang mendukung untuk kostumisasi frame, stiker, dan filter.
* **Due Date:** 6 September 2026
* **Status:** NOT STARTED / IN PROGRESS / COMPLETE

### Contributors
| Role | Name |
| :--- | :--- |
| **Project Manager (PM)** | Zahrah Syifa |
| **Frontend Developer** | Abhinaya Aghni |
| **Backend Developer** | Zaky Arkan |
| **Infrastructure** | Fadiyah Irbati |

---

## 💡 Problem Statement
Photobooth kini menjadi tren gaya hidup bagi anak muda yang rela mengeluarkan uang, namun pasangan LDR terhalang jarak untuk menciptakan kenangan bersama. Kami yakin aplikasi photobooth real-time dengan opsi frame terjangkau hingga gratis dapat menjembatani kesenjangan ini, dan kami akan sukses jika pengguna dapat melakukan sesi foto bersama dengan kualitas tinggi, memperoleh berbagai format output (PNG/GIF/Live Photo), serta mendapatkan kepuasan pengalaman yang setara dengan photobooth fisik.

---

## 🎯 Goals
* **Sistem Katalog Frame:** Berhasil menerapkan sistem counter sesi foto yang memicu alur login/registrasi otomatis setelah 3x sesi foto, guna meningkatkan jumlah registered user tanpa menghambat konversi di awal (user onboarding).
* **Implementasi Fitur Real-Time:** Berhasil menghadirkan sinkronisasi kamera shutter antar pengguna LDR dengan latensi rendah (< 500ms) menggunakan Socket.io.
* **Kualitas & Format Output:** Pengguna dapat mengunduh hasil foto dalam berbagai format (PNG, GIF, dan Live Photo) dengan kualitas visual tinggi yang setara dengan hasil photobooth fisik.
* **Skalabilitas Penyimpanan:** Seluruh aset frame dan hasil foto tersimpan secara aman dan efisien di Cloudflare R2, memastikan kecepatan akses global melalui CDN.

---

## 👥 Target Users
* Pasangan & sahabat jarak jauh
* Gen Z & anak muda
* Content creator
* Pemilik usaha (optional)

---

## ⚙️ Requirements

### Functional Requirements
* **Manajemen Sesi:** Menangani pemilihan mode (Lokal/LDR), pembuatan/validasi kode room, serta sinkronisasi kamera real-time via Socket.io.
* **Editing & Output:** Menyediakan fitur pilih frame, editing (stiker/filter), serta sistem unduhan (PNG/GIF/Live Photo).
* **Growth Hacking:** Menghitung sesi foto dan mewajibkan login setelah 3x penggunaan untuk akses lanjutan.
* **Alur Pengguna:** Menghubungkan sesi foto ke halaman editing/download, serta menyediakan opsi *Take Another Photo* untuk pengulangan sesi.

### Non-Functional Requirements
* **Performa & Latensi:** Sinkronisasi kamera real-time untuk mode LDR harus memiliki latensi rendah (di bawah 500ms) untuk memastikan pengalaman foto yang mulus.
* **Skalabilitas:** Sistem harus mampu menangani banyak room LDR secara bersamaan tanpa degradasi performa yang signifikan menggunakan arsitektur backend yang efisien.
* **Ketersediaan (Availability):** Aplikasi harus dapat diakses 24/7 melalui web browser, dengan waktu uptime yang tinggi didukung oleh infrastruktur cloud.
* **Keamanan Data:** Data pengguna dan hasil foto harus aman, dengan akses yang terenkripsi terutama setelah fitur login diterapkan.
* **Kompatibilitas:** Aplikasi harus responsif dan berjalan lancar di berbagai perangkat (mobile dan desktop) melalui web browser modern tanpa instalasi tambahan.
* **Efisiensi Penyimpanan:** Pengelolaan aset gambar harus dioptimalkan menggunakan CDN (seperti Cloudflare R2) untuk menjamin kecepatan loading frame dan unduhan foto di mana pun lokasi pengguna.

---

## 📌 Scope

### Must Have (MVP)
* Fitur login & register
* Fitur kustomisasi (Stiker, Filter)
* Sistem unduhan (PNG, GIF, Live Photo)
* Fitur sinkronisasi kamera real-time untuk mode LDR

### Nice to Have
* Fitur kustomisasi frame (harus login)
* Popular frame

### Not in Scope
* Payment gateway
* Add print
* Timer

---

## 🛠️ Tech Stack

### Frontend
* **Framework:** React JS + Vite
* **State Management:** Zustand
* **Canvas & Image Processing:** Konva.js
* **Webcam/Stream:** react-webcam
* **Styling:** Tailwind CSS
* **Real-time Client:** socket.io-client

### Backend
* **Framework:** NestJS
* **Real-time Engine:** Socket.io
* **Database:** PostgreSQL (rekomendasi)
* **Validation:** class-validator (untuk payload)
* **Image Processing:** Sharp
* **Authentication:** Passport.js 

### Infra
* **Containerization:** Docker
* **Web Server:** Nginx
* **Deployment Server:** (To be defined)
* **Storage:** Cloudflare R2

---

## 📅 Milestones and Deadlines

| Milestone | Owner | Deadline | Status |
| :--- | :--- | :--- | :--- |
| **PRD** | Zahrah | 8/7/2026 | ✅ COMPLETE |
| **Finalisasi Wireframe & UI/UX (Figma)** | Zahrah & Abhinaya | 12/7/2026 | 🔄 IN PROGRESS |
| **Setup Repo (Frontend/Backend) & Docker** | Fadiyah | 15/7/2026 | ❌ NOT STARTED |
| **Setup Database (PostgreSQL) & Prisma** | Zaky | 20/7/2026 | ❌ NOT STARTED |
| **Auth API (Passport.js & JWT)** | Zaky & Fadiyah | 25/7/2026 | ❌ NOT STARTED |
| **Core Feature: Real-time Socket.io (LDR)** | Abhinaya & Zaky | 05/8/2026 | ❌ NOT STARTED |
| **UI Implementation & Konva.js Editor** | Abhinaya | 15/8/2026 | ❌ NOT STARTED |
| **Cloudflare R2 Integration (Image Storage)** | Fadiyah | 20/8/2026 | ❌ NOT STARTED |
| **Integration & Bug Fixing (QA)** | All | 1/9/2026 | ❌ NOT STARTED |
| **Deployment (Production) & Launch** | Fadiyah | 6/9/2026 | ❌ NOT STARTED |

---

## 🔗 Resources
* **Figma Link:** [Online Photobooth Figma Design](https://www.figma.com/design/ydftBLA9GmkF3vRRN4BmjG/Online-Photobooth?node-id=0-1&t=6WtTLvIJDqFRVqFv-1)