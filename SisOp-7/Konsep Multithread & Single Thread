## 1. Konsep Single-Thread dan Multithread

### Penjelasan
Pada model **single-thread**, sebuah proses hanya memiliki satu alur eksekusi (thread) tunggal. 
Semua tugas—misalnya A, B, dan C—dijalankan satu per satu secara berurutan dalam satu jalur kontrol. 
Hal ini membuat eksekusi sederhana dan mudah di-debug karena tidak ada race condition atau sinkronisasi yang rumit.
Namun, performanya terbatas: jika salah satu tugas memblok (misalnya menunggu I/O), keseluruhan proses pun terhenti—CPU tidak bisa memanfaatkan waktu tunggu untuk menjalankan tugas lain.

Sebaliknya, pada model **multithread**, satu proses dapat memiliki beberapa thread yang berjalan secara “paralel” (baik di CPU multicore maupun secara timellice pada single core). Misalnya pada gambar, thread 1 dan thread 2 dapat mengeksekusi tugas A & B secara bersamaan, sementara thread 3 bisa menjalankan C. Dengan multithread, proses dapat tetap responsif saat satu thread memblok—thread lain tetap bisa memproses tugas berbeda. Tentunya, perlu mekanisme sinkronisasi (mutex, semaphore) untuk menghindari...

![Konsep Single-thread vs Multithread](https://raw.githubusercontent.com/iniaaqilah/SisOp-2025/refs/heads/main/singlevsmulti.webp)
