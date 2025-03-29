# Tugas Sistem Operasi

## 1. Beda Multiprogramming vs Multitasking

### **Multiprogramming:**
- **Definisi:** Multiprogramming adalah teknik di mana beberapa program (atau proses) dimuat ke dalam memori utama (RAM) secara bersamaan, tetapi hanya satu program yang dijalankan oleh CPU pada satu waktu.
- **Tujuan:** Meningkatkan utilisasi CPU dengan memastikan bahwa CPU selalu memiliki pekerjaan untuk dilakukan, bahkan ketika satu program sedang menunggu I/O (input/output).
- **Cara Kerja:** Sistem operasi akan beralih ke program lain ketika program yang sedang berjalan menunggu I/O atau sumber daya lainnya.
- **Contoh:** Pada sistem batch, beberapa program dijalankan secara bergantian tanpa interaksi pengguna.

### **Multitasking:**
- **Definisi:** Multitasking adalah teknik di mana beberapa tugas (atau proses) dijalankan secara bersamaan oleh CPU dengan cara membagi waktu (time-sharing).
- **Tujuan:** Memberikan ilusi bahwa beberapa program berjalan secara bersamaan, sehingga pengguna dapat melakukan banyak tugas dalam waktu yang sama.
- **Cara Kerja:** CPU secara cepat beralih antara tugas-tugas yang berbeda, memberikan waktu yang sangat singkat untuk setiap tugas.
- **Contoh:** Pada sistem operasi modern seperti Windows, Linux, atau macOS, pengguna dapat membuka browser, editor teks, dan pemutar musik secara bersamaan.

### **Perbedaan Utama:**
- **Multiprogramming** fokus pada efisiensi CPU dengan menjalankan beberapa program secara bergantian, sementara **Multitasking** fokus pada interaksi pengguna dengan menjalankan beberapa tugas secara "bersamaan" melalui time-sharing.
- **Multiprogramming** biasanya digunakan dalam sistem batch, sedangkan **Multitasking** digunakan dalam sistem interaktif.

---

## 2. Fungsi OS (Sistem Operasi)

Sistem Operasi (OS) memiliki beberapa fungsi utama, antara lain:

1. **Manajemen Proses:**  
   - Mengatur dan mengelola proses yang berjalan di sistem, termasuk penjadwalan CPU, alokasi sumber daya, dan sinkronisasi antar-proses.

2. **Manajemen Memori:**  
   - Mengelola alokasi dan dealokasi memori untuk proses yang sedang berjalan, serta memastikan bahwa setiap proses memiliki ruang memori yang cukup.

3. **Manajemen File dan Sistem Berkas:**  
   - Mengatur penyimpanan, pengorganisasian, dan akses ke file dan direktori pada media penyimpanan seperti hard disk atau SSD.

4. **Manajemen Perangkat (Device Management):**  
   - Mengontrol dan mengkoordinasikan penggunaan perangkat keras seperti printer, keyboard, mouse, dan perangkat I/O lainnya.

5. **Keamanan dan Proteksi:**  
   - Melindungi sistem dan data dari akses yang tidak sah, serta memastikan bahwa setiap pengguna atau proses hanya memiliki akses ke sumber daya yang diizinkan.

6. **Antarmuka Pengguna (User Interface):**  
   - Menyediakan antarmuka bagi pengguna untuk berinteraksi dengan sistem, baik melalui antarmuka grafis (GUI) atau antarmuka baris perintah (CLI).

7. **Manajemen Jaringan:**  
   - Mengatur komunikasi antara sistem komputer dalam jaringan, termasuk pengiriman dan penerimaan data melalui protokol jaringan.

8. **Manajemen Penyimpanan Sekunder:**  
   - Mengelola penyimpanan data pada media sekunder seperti hard disk, SSD, atau flash drive.

---

## 3. Virtualisasi Container

### **Definisi:**
Virtualisasi container adalah teknologi yang memungkinkan aplikasi dan dependensinya (seperti library, konfigurasi, dan lingkungan runtime) dijalankan dalam lingkungan yang terisolasi (container) di atas sistem operasi host. Container berbagi kernel sistem operasi host tetapi memiliki ruang pengguna (user space) yang terpisah.

### **Fungsi Virtualisasi Container:**
1. **Isolasi:**  
   - Setiap container berjalan dalam lingkungan yang terisolasi, sehingga aplikasi dalam satu container tidak akan mengganggu aplikasi di container lain.

2. **Portabilitas:**  
   - Container dapat dijalankan di berbagai lingkungan (development, testing, production) tanpa perlu perubahan kode, karena semua dependensi sudah termasuk dalam container.

3. **Efisiensi Sumber Daya:**  
   - Container lebih ringan dibandingkan virtual machine (VM) karena tidak memerlukan sistem operasi terpisah untuk setiap container. Mereka berbagi kernel host, sehingga penggunaan sumber daya lebih efisien.

4. **Skalabilitas:**  
   - Container dapat dengan mudah di-scale up atau down sesuai kebutuhan, membuatnya ideal untuk aplikasi yang membutuhkan fleksibilitas tinggi.

5. **Konsistensi Lingkungan:**  
   - Dengan container, lingkungan pengembangan, testing, dan produksi dapat dibuat konsisten, mengurangi masalah "works on my machine".

### **Contoh Teknologi Container:**
- **Docker:** Platform paling populer untuk membuat, mengelola, dan menjalankan container.
- **Kubernetes:** Sistem orkestrasi untuk mengelola container dalam skala besar.
- **LXC/LXD:** Teknologi container yang lebih tradisional, sering digunakan di lingkungan Linux.

### **Perbedaan dengan Virtual Machine (VM):**
- **Container** berbagi kernel sistem operasi host, sedangkan **VM** memerlukan hypervisor dan sistem operasi terpisah untuk setiap VM.
- **Container** lebih ringan dan cepat dibandingkan VM karena tidak memerlukan overhead sistem operasi tambahan.

---

## Kesimpulan

- **Multiprogramming** dan **Multitasking** adalah teknik manajemen proses yang berbeda, di mana multiprogramming fokus pada efisiensi CPU, sedangkan multitasking fokus pada interaksi pengguna.
- **Fungsi OS** mencakup manajemen proses, memori, file, perangkat, keamanan, antarmuka pengguna, jaringan, dan penyimpanan.
- **Virtualisasi container** adalah teknologi yang memungkinkan aplikasi berjalan dalam lingkungan terisolasi dengan efisiensi sumber daya yang tinggi, portabilitas, dan skalabilitas.

---
