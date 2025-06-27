# 📘 Template LaTeX Proposal Praktik Industri

**Program Sarjana Terapan Teknik Elektronika — Fakultas Vokasi UNY**

Repositori ini menyediakan **template LaTeX** resmi untuk penulisan **Proposal Praktik Industri** mahasiswa Program Sarjana Terapan Teknik Elektronika, Fakultas Vokasi, Universitas Negeri Yogyakarta (UNY).

Template ini dirancang agar mahasiswa dapat menyusun laporan dengan format yang **terstandar**, **profesional**, dan mudah disesuaikan. Dengan menggunakan LaTeX, mahasiswa dapat fokus pada konten teknis tanpa direpotkan oleh masalah tata letak dan format dokumen.

---

## 📂 Struktur Folder

```

.
├── LICENSE                      # Lisensi proyek (MIT)                  
├── Project
│   ├── a0-identitas.tex         # Identitas mahasiswa, dosen pembimbing, judul laporan, dll
│   ├── a1-database.hyphenate.tex # Pengaturan pemenggalan kata
│   ├── a2-lampiran.tex          # Daftar lampiran (dapat disesuaikan)
│   ├── b1-bab1.tex              # BAB 1 laporan
│   ├── b2-bab2.tex              # BAB 2 laporan
│   ├── b3-bab3.tex              # BAB 3 laporan
│   ├── b4-bab4.tex              # Tutorial LaTeX (jangan disertakan dalam laporan akhir)
│   ├── gambar/                  # Folder gambar yang digunakan dalam laporan
│   │   ├── gambar-kucing.jpg
│   │   ├── logo-uny.png
│   │   ├── screenshot-miktex.png
│   │   ├── screenshot-texstudio-macos.png
│   │   └── screenshot-texstudio-windows.png
│   ├── kode/                    # Folder kode program (C++, Python, Arduino, Java, dll)
│   │   ├── code_sample.cpp
│   │   ├── code_sample.ino
│   │   ├── code_sample.java
│   │   └── code_sample.py
│   ├── proposal-pi.tex          # File utama (jangan diubah langsung)
│   ├── proposal-pi.pdf          # Contoh hasil kompilasi
│   ├── pustaka.bib              # Daftar referensi dalam format BibTeX
│   └── untouch/                 # Komponen LaTeX penting (jangan diubah)
│       ├── xx-daftar.tex
│       ├── xx-daftarpustaka.tex
│       ├── xx-pengesahan.tex
│       ├── xx-preambles.tex
│       └── xx-sampul.tex
└── README.md                   # Dokumentasi ini

```

---

## 🚀 Compilation Script (`compile.sh`)

Template ini dilengkapi dengan script kompilasi canggih yang mempermudah proses build dokumen LaTeX dengan fitur dependency management dan caching system.

### ✨ **Fitur Script Compile**

#### 🎯 **Smart Dependency Management**
- **Auto-detection**: Deteksi otomatis LaTeX installation dan package requirements
- **Auto-installation**: Install missing packages secara otomatis via `tlmgr`
- **Cross-platform**: Support macOS, Windows, dan Linux
- **Fallback instructions**: Panduan manual jika auto-install gagal

#### ⚡ **Performance Optimization**
- **Dependency Caching**: Cache status dependencies untuk 7 hari
- **Speed Improvement**: ~65% lebih cepat pada subsequent runs
- **Smart Cache**: Auto-invalidation jika LaTeX version berubah
- **Background Processing**: Multiple verbosity levels untuk berbagai use cases

#### 🛠️ **Advanced Options**
- **Multiple Build Passes**: 4-pass compilation untuk resolving semua references
- **BibTeX Integration**: Automatic bibliography processing
- **Cleanup**: Auto-cleanup temporary files
- **Error Handling**: Comprehensive error reporting dan troubleshooting

### 📋 **Quick Start**

```bash
# Masuk ke direktori Project
cd Project/

# Kompilasi normal (menggunakan cache jika tersedia)
./compile.sh

# Kompilasi silent (untuk automation)
./compile.sh --quiet

# Lihat semua opsi yang tersedia
./compile.sh --help
```

### 🎛️ **Command Line Options**

| Option | Deskripsi |
|--------|-----------|
| `--help` | Tampilkan bantuan lengkap |
| `--quiet` | Mode silent (hanya hasil akhir) |
| `--verbose` | Mode verbose (output lengkap) |
| `--debug` | Mode debug (maximum verbosity) |
| `--error-only` | Hanya tampilkan errors |
| `--warning` | Tampilkan warnings dan errors |
| `--final-warnings` | Hanya warnings dari kompilasi terakhir |
| `--clean` | Bersihkan temporary files |
| `--skip-deps` | Skip dependency checking |
| `--force-deps-check` | Force full dependency recheck |
| `--clear-cache` | Clear dependency cache |

### 📊 **Performance Comparison**

| Run Type | Waktu | Improvement |
|----------|-------|-------------|
| First run (dengan dependency check) | ~12s | Baseline |
| Cached run (menggunakan cache) | ~4s | **65% faster** |
| Skip dependencies | ~4s | **68% faster** |

### 🔧 **Usage Examples**

```bash
# Development workflow (daily use)
./compile.sh                        # Fast compilation dengan cache

# CI/CD pipeline  
./compile.sh --quiet --skip-deps     # Maximum speed untuk automation

# Troubleshooting
./compile.sh --debug                 # Full diagnostic output
./compile.sh --force-deps-check      # Refresh dependency cache

# Maintenance
./compile.sh --clear-cache           # Reset cache system
./compile.sh --clean                 # Clean temporary files only
```

### 🗂️ **Cache System**

Script menggunakan intelligent caching system yang disimpan di `.latex_deps_cache/`:

```
.latex_deps_cache/
├── dependency_status.log    # Status package dependencies
└── versions.log            # LaTeX version tracking
```

- **Cache Validity**: 7 hari (168 jam)
- **Auto-Invalidation**: Jika LaTeX version berubah
- **Size**: ~500 bytes total
- **Git Integration**: Otomatis ditambahkan ke `.gitignore`

---

## 🛠️ Persiapan & Instalasi

### 1. Instalasi MikTeX dan TeXstudio

* **MikTeX**: [https://miktex.org/download](https://miktex.org/download)

  > *Wajib pilih opsi* **for all users** dan **Always** pada on-the-fly installation (khusus Windows).
* **TeXstudio**: [https://www.texstudio.org](https://www.texstudio.org)

### 2. Update MikTeX Packages

Buka **MikTeX Console**, lalu klik **Update All** agar semua paket LaTeX tersedia.

### 3. Unduh Template

* Pilih salah satu:

  * Klik tombol **Code > Download ZIP**
  * Gunakan Git:

    ```bash
    git clone https://github.com/2black0/Template-LaTeX-Proposal-Praktik-Industri.git
    ```

---

## ✍️ Cara Menggunakan Template

1. **Buka `proposal-pi.tex`** di TeXstudio (jangan ubah file ini).
2. **Edit bagian-bagian berikut:**

   * `a0-identitas.tex` → Isi nama, NIM, judul, pembimbing, dsb.
   * `b1-bab1.tex` s.d. `b3-bab3.tex` → Tulis isi laporan sesuai struktur bab.
   * `a2-lampiran.tex` → Tambahkan lampiran (jika ada).
   * `pustaka.bib` → Tambahkan referensi menggunakan Mendeley/Zotero/JabRef.
3. **Kompilasi** dengan klik tombol **Build & View** (`F5` atau ikon panah hijau).
4. **Output laporan** tersedia dalam `proposal-pi.pdf`.

---

## 📺 Video Tutorial

| Materi                                 | Link                                       |
| -------------------------------------- | ------------------------------------------ |
| Tutorial 1 - Dasar Penggunaan Template | [🎥 YouTube](https://youtu.be/lnPTVrOGB90) |
| Tutorial 2 - Penulisan Isi             | [🎥 YouTube](https://youtu.be/4Qk_2pknhsM) |
| Tutorial 3 - Gambar dan Tabel          | [🎥 YouTube](https://youtu.be/oxY1mbZgv94) |
| Tutorial 4 - Referensi & Sitasi        | [🎥 YouTube](https://youtu.be/goq-IS4WJW4) |
| Tutorial 5 - Penulisan Kode Program    | [🎥 YouTube](https://youtu.be/JeSJ0mYfxA0) |
| Workshop Lengkap                       | [🎥 YouTube](https://youtu.be/anMLRydjDOE) |

---

## 📚 Pengelolaan Referensi BibTeX

Disarankan menggunakan salah satu tools berikut untuk mengelola file `pustaka.bib`:

* [Mendeley](https://www.mendeley.com/)
* [Zotero](https://www.zotero.org/)
* [JabRef](https://www.jabref.org/)

---

## 🖼️ Cuplikan Tampilan

| TeXstudio - macOS                                     | TeXstudio - Windows                                     |
| ----------------------------------------------------- | ------------------------------------------------------- |
| ![Mac](Project/gambar/screenshot-texstudio-macos.png) | ![Win](Project/gambar/screenshot-texstudio-windows.png) |

---

## 📄 Lisensi

Template ini dilisensikan dengan [MIT License](LICENSE).

---

## 🤝 Kontribusi

Kami sangat terbuka untuk perbaikan dan pengembangan template ini.
Silakan buat **pull request** atau ajukan **issue** untuk menyampaikan saran atau laporan bug.

---

## 📬 Kontak

Untuk informasi lebih lanjut hubungi:
**Ardy Seto Priambodo**
✉️ [ardyseto@uny.ac.id](mailto:ardyseto@uny.ac.id)
👤 GitHub: [@2black0](https://github.com/2black0)

---
