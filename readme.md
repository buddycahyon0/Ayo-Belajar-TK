# 🦉 Belajar Seru TK A

Aplikasi pembelajaran interaktif berbasis web (PWA) yang dirancang khusus untuk anak-anak usia TK A (4–5 tahun). Dilengkapi dengan karakter pemandu ceria **Kak Owi**, efek suara interaktif, latihan menebalkan huruf/angka dengan jari, serta kurikulum tematik yang mencakup **Semester 1**, **Semester 2**, dan **Belajar Al-Qur'an**.

---

## ✨ Fitur Utama

* **3 Kategori Pembelajaran Lengkap:**
  * **Semester 1 (4 Topik):** *Aku Istimewa*, *Rumahku Penuh Cinta*, *Teman yang Peduli*, dan *Ayo Bergerak*.
  * **Semester 2 (4 Topik):** *Alam Semesta Ajaib*, *Tanaman Tumbuh*, *Kemah Ramadan*, dan *Bumi Bersih & Bahagia*.
  * **Belajar Al-Qur'an (2 Bab):** *Huruf Hijaiyah (Alif – Ro)* dan *Harakat Dasar (Fathah, Kasrah, Dhomah)*.
* **Permainan Edukatif Beragam:**
  * Berhitung benda, melengkapi deret angka, penjumlahan & pengurangan sederhana (1–5).
  * Mengenal huruf vokal, huruf awal kosakata, dan ekspresi emosi.
  * Mengenal dan membaca huruf Hijaiyah berharakat.
  * **Papan Tulis Digital (Tracing):** Latihan menebalkan huruf Latin, angka, dan huruf Hijaiyah langsung di layar sentuh dengan deteksi akurasi goresan.
* **Sistem Audio Offline-First & Anti-Duplikat Soal:**
  * Mendukung pemutaran file audio lokal (`.wav` / `.mp3`) dengan *fallback* otomatis ke suara browser (*Web Speech API*).
  * Efek suara interaktif menggunakan *Tone.js* serta animasi bintang penghargaan.
* **Dapat Di-install (Progressive Web App / PWA):**
  * Bisa dipasang langsung ke layar utama HP Android/iOS maupun desktop dan tetap berjalan lancar saat offline.

---

## 📁 Struktur Folder Repository

Pastikan susunan file di repository GitHub atau server kamu tersusun seperti berikut agar aplikasi dan audio berjalan normal:

```text
belajar-seru-tk-a/
├── index.html          # Aplikasi utama (UI, logika kuis, & kanvas tracing)
├── manifest.json       # Konfigurasi instalasi PWA (ikon, nama, tema)
├── sw.js               # Service Worker untuk mode offline & caching
├── icon-192.png        # Ikon aplikasi ukuran 192x192 px
├── icon-512.png        # Ikon aplikasi ukuran 512x512 px
├── generate_audio.py   # Script Python untuk generate audio via Gemini TTS
├── README.md           # Dokumentasi aplikasi
└── audio/              # Folder berisi seluruh file suara (.wav / .mp3)
    ├── halo.wav
    ├── benar.wav
    ├── q_count.wav
    └── ... (total 106 file audio)
```

---

## 🚀 Cara Menjalankan & Deploy (GitHub Pages)

1. **Upload ke GitHub:** Unggah seluruh file (`index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`, dan folder `audio/`) ke repository GitHub kamu.
2. **Aktifkan GitHub Pages:**
   * Buka tab **Settings** → **Pages** di repository GitHub.
   * Pada bagian **Source**, pilih branch `main` (folder `/root`), lalu klik **Save**.
3. **Install di HP (PWA):**
   * Buka tautan GitHub Pages di Chrome (Android) atau Safari (iOS).
   * Pilih menu browser (**⋮** atau ikon **Share**) → klik **Install App** / **Add to Home Screen**.

---

## 🎙️ Membuat File Audio Tambahan

Jika kamu ingin membuat ulang atau menambah rekaman suara menggunakan suara AI Bahasa Indonesia yang natural:

1. Buka file `generate_audio.py` di Google Colab atau lingkungan Python lokal.
2. Masukkan API Key Gemini milikmu pada variabel `API_KEYS`.
3. Jalankan script untuk menghasilkan paket file `.wav` dan mengekstraknya ke dalam folder `audio/`.

---

## 🛠️ Teknologi yang Digunakan

* **HTML5, CSS3, & Vanilla JavaScript** (tanpa ketergantungan framework berat).
* **HTML5 Canvas API** untuk fitur menebalkan huruf dan deteksi akurasi tulisan anak.
* **Tone.js** untuk efek suara interaktif (*pop*, *win*, *fanfare*).
* **Service Worker & Web App Manifest** untuk dukungan offline penuh dan instalasi layaknya aplikasi native.
