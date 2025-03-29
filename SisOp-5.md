# Merangkum Appendix dan Timeline Os
## Timeline Perkembangan Sistem Operasi

| Tahun      | Sistem Operasi/Konsep Penting                                     | Kontribusi Utama                                                                 |
|------------|-------------------------------------------------------------------|---------------------------------------------------------------------------------|
| **1949**   | Manchester Mark 1                                                 | Komputer stored-program pertama.                                                |
| **1950-an**| Sistem Batch Awal                                                 | Penggunaan operator manusia, kontrol kartu, dan spooling.                       |
| **1961**   | CTSS (Compatible Time-Sharing System)                             | Sistem time-sharing pertama, dasar untuk MULTICS.                               |
| **1962**   | Atlas OS                                                          | Pengenalan demand paging dan cache memory.                                      |
| **1965**   | MULTICS                                                           | Konsep sistem time-sharing utility dan proteksi berbasis ring.                   |
| **1960-an**| THE OS                                                            | Struktur berlapis, penggunaan semaphore, dan algoritma banker untuk deadlock.  |
| **1960-an**| RC 4000                                                           | Konsep kernel modular dan komunikasi via pesan.                                 |
| **1969**   | UNIX                                                              | Portabilitas, hierarki filesystem, dan filosofi "do one thing well".            |
| **1970-an**| CP/M                                                              | OS standar untuk komputer mikro 8-bit (Intel 8080).                             |
| **1981**   | MS-DOS                                                            | OS dominan untuk PC IBM, berbasis command-line.                                 |
| **1984**   | Macintosh System 1                                                | GUI pertama untuk pengguna rumahan dengan mouse.                                |
| **1985**   | Windows 1.0                                                       | Antarmuka grafis untuk PC kompatibel IBM.                                       |
| **1987**   | Mach                                                              | Microkernel modular, dasar untuk macOS dan GNU HURD.                            |
| **1991**   | Linux                                                             | OS open-source berbasis kernel UNIX.                                            |
| **2001**   | macOS (berbasis Mach)                                             | Integrasi kernel Mach dengan BSD, GUI modern.                                   |

---

## Rangkuman Appendix

### 1. **Atlas (1962)**
   - **Kontribusi**:  
     - Penggunaan *demand paging* untuk manajemen memori.  
     - Cache memory (core memory) untuk mempercepat akses drum.  
   - **Fitur Unik**:  
     - Algoritma prediksi akses memori berbasis riwayat (*t₁* dan *t₂*).  

### 2. **CTSS (1961)**
   - **Kontribusi**:  
     - Sistem time-sharing pertama yang mendukung 32 pengguna.  
     - Multilevel feedback queue untuk penjadwalan CPU.  

### 3. **MULTICS (1965)**
   - **Kontribusi**:  
     - Konsep "utilitas komputasi" seperti listrik.  
     - Segmentasi dan paging untuk virtual memory.  
   - **Pengaruh**: Menjadi dasar untuk pengembangan UNIX.  

### 4. **THE OS (1960-an)**
   - **Kontribusi**:  
     - Struktur berlapis dengan proses statis.  
     - Algoritma banker untuk menghindari deadlock.  

### 5. **RC 4000 (1960-an)**
   - **Kontribusi**:  
     - Kernel modular yang memisahkan kebijakan dan mekanisme.  
     - Komunikasi antar-proses via pesan (*message passing*).  

### 6. **UNIX (1969)**
   - **Kontribusi**:  
     - Portabilitas antar arsitektur.  
     - Filosofi "tools kecil yang terintegrasi".  

### 7. **Mach (1987)**
   - **Kontribusi**:  
     - Microkernel untuk fleksibilitas dan keamanan.  
     - Dasar untuk macOS (XNU kernel) dan GNU HURD.  

### 8. **MS-DOS (1981)**
   - **Kontribusi**:  
     - OS dominan untuk PC awal.  
     - Dukungan memori hingga 640 KB (dengan ekstensi).  

### 9. **Macintosh System 1 (1984)**
   - **Kontribusi**:  
     - GUI pertama untuk pengguna rumahan.  
     - Integrasi mouse dan antarmuka grafis.  

### 10. **Linux (1991)**
   - **Kontribusi**:  
     - Open-source, mendorong kolaborasi global.  
     - Kompatibilitas dengan standar POSIX.  

---

## Konsep Kunci dalam Perkembangan OS
1. **Spooling**: Overlap I/O dengan komputasi untuk meningkatkan utilisasi CPU.  
2. **Multiprogramming**: Menjalankan banyak proses secara bersamaan.  
3. **Paging/Segmentasi**: Manajemen memori virtual untuk efisiensi.  
4. **Microkernel**: Memisahkan fungsi inti OS untuk modularitas.  
5. **GUI**: Transformasi antarmuka pengguna dari teks ke grafis.  

---
