
# Laporan Chapter 4: Thread dan Evolusi Processor

## 1. Konsep Single-Thread dan Multithread

### Penjelasan
Pada model **single-thread**, sebuah proses hanya memiliki satu alur eksekusi (thread) tunggal. Semua tugas—misalnya A, B, dan C—dijalankan satu per satu secara berurutan dalam satu jalur kontrol. Hal ini membuat eksekusi sederhana dan mudah di-debug karena tidak ada race condition atau sinkronisasi yang rumit. Namun, performanya terbatas: jika salah satu tugas memblok (misalnya menunggu I/O), keseluruhan proses pun terhenti—CPU tidak bisa memanfaatkan waktu tunggu untuk menjalankan tugas lain.

Sebaliknya, pada model **multithread**, satu proses dapat memiliki beberapa thread yang berjalan secara “paralel” (baik di CPU multicore maupun secara timellice pada single core). Misalnya pada gambar, thread 1 dan thread 2 dapat mengeksekusi tugas A & B secara bersamaan, sementara thread 3 bisa menjalankan C. Dengan multithread, proses dapat tetap responsif saat satu thread memblok—thread lain tetap bisa memproses tugas berbeda. Tentunya, perlu mekanisme sinkronisasi (mutex, semaphore) untuk menghindari konflik data antar-thread di memori bersama.

![Konsep Single-thread vs Multithread](A_2x1_digital_diagram_in_the_educational_image_vis.png)

---

## 2. Programming Exercise

### a. Penerapan Thread pada `SumTask.java`
Pada `SumTask.java` kita menggunakan kerangka Fork/Join di Java, yang mengimplementasikan paradigma **divide-and-conquer** dengan `RecursiveTask`. Array sepanjang `SIZE` dibagi menjadi dua bagian saat panjang segmen melewati `THRESHOLD`. Bagian kiri dan kanan di-*fork()* sebagai subtask, lalu hasilnya di-*join()* dan dijumlahkan. `ForkJoinPool` secara otomatis mengelola pool thread dan work-stealing, memaksimalkan pemanfaatan core CPU. Ini cocok untuk beban kerja yang dapat dipecah berulang dengan cepat, karena overhead pembagian tugas dan manajemen thread relatif kecil dibandingkan jumlah pekerjaan yang diparalelkan.

### b. Penerapan Thread di POSIX (`thrd-posix.c`)
Program `thrd-posix.c` mendemonstrasikan penggunaan **pthread** di sistem POSIX. Pertama, atribut thread (`pthread_attr_t`) diinisialisasi, lalu `pthread_create` memanggil fungsi runner (`void *runner(void*)`) untuk menghitung jumlah bilangan 1…N. Setelah pembuatan thread, `pthread_join` memastikan thread utama menunggu sampai subthread selesai sebelum mencetak hasil. Variabel `sum` dideklarasikan di global agar dapat diakses bersama, dan runtime POSIX menjamin eksekusi sinkron dengan `pthread_join`.

### c. Penerapan Thread di Windows (`thrd-win32.c`)
Di Windows, `CreateThread` digunakan untuk membuat thread lewat Win32 API. Fungsi `Summation` diimplementasikan sesuai konvensi `DWORD WINAPI`, mengambil parameter upper-bound lewat pointer. Setelah thread dibuat, `WaitForSingleObject` menunggu hingga thread selesai, lalu `CloseHandle` membersihkan handle. Perbedaan utama dengan POSIX adalah penamaan fungsi, tipe data DWORD, dan mekanisme penanganan handle thread, meski konsepnya—membuat thread yang menjalankan fungsi terpisah—sangat mirip.

---

## 3. Evolusi Teknologi Processor Intel (Outline PPT)

1. **Judul**: Evolusi Teknologi Processor Intel  
2. **Sejarah Awal**: Intel 4004 (1971) – 4-bit, 0.06 MHz  
3. **Generasi Awal**: 8008 → 8080 → 8086 (16-bit, 5 MHz)  
4. **Era Mikroprosesor 16-bit**: 286 (1982), 386 (1985)  
5. **Arsitektur 32-bit**: 386 → 486 (1989)  
6. **Munculnya Pentium**: Pentium I/II/III (1993–1999)  
7. **Pentium 4 & Ke bawah**: Pentium 4, Pentium M (2000-an awal)  
8. **Arsitektur Core**: Core Duo → Core 2 Duo (2006)  
9. **Generasi Core i**: i3/i5/i7 (2010)  
10. **Hybrid Architecture**: Alder Lake (12th Gen) – P‑cores & E‑cores (2021)  
11. **Raptor Lake & Meteor Lake**: 13th & 14th Gen – AI engine, DDR5, PCIe 5.0  
12. **Intel Core Ultra**: Arsitektur terbaru – NPU & GPU terintegrasi  
13. **Masa Depan**: Roadmap 2025+ (Granite Rapids, Lunar Lake)  
14. **Kesimpulan**: Tren ke arah heterogen computing dan AI acceleration  

---

## 4. Jawaban Exercise Chapter 4 

### 4.1
**Program** adalah sekumpulan instruksi statis, sedangkan **proses** adalah program yang sedang dieksekusi. Proses mencakup state eksekusi, nilai register, counter, dan resources seperti file dan memori.

### 4.2
Beberapa informasi yang disimpan dalam Process Control Block (PCB):
- Process state
- Program counter
- CPU register
- CPU scheduling information
- Memory management information
- Accounting information
- I/O status information

### 4.3
Diagram tiga-state proses terdiri dari:
- **Ready**: proses siap dijalankan
- **Running**: proses sedang dijalankan CPU
- **Waiting**: proses menunggu event (misal I/O)

Transisi:
- Ready → Running (scheduler memilih)
- Running → Waiting (menunggu I/O)
- Waiting → Ready (I/O selesai)
- Running → Ready (preemption)

### 4.4
Pendekatan `new → ready → running → terminated` memungkinkan OS mengatur semua state proses dan mengontrol sumber daya yang digunakan tiap proses.

### 4.5
Context switch adalah proses menyimpan state proses saat ini dan memuat state proses berikutnya. Ini terjadi saat proses diganti, misal oleh interrupt atau scheduler.

### 4.6
Multithreading bermanfaat karena:
- Responsif (UI tetap responsif saat ada proses latar belakang)
- Berbagi sumber daya antar thread
- Ekonomis (tidak seberat proses baru)
