### a. Penerapan Thread pada `SumTask.java`
Pada `SumTask.java` kita menggunakan kerangka Fork/Join di Java, yang mengimplementasikan paradigma **divide-and-conquer** dengan `RecursiveTask`. Array sepanjang `SIZE` dibagi menjadi dua bagian saat panjang segmen melewati `THRESHOLD`. Bagian kiri dan kanan di-*fork()* sebagai subtask, lalu hasilnya di-*join()* dan dijumlahkan. `ForkJoinPool` secara otomatis mengelola pool thread dan work-stealing, memaksimalkan pemanfaatan core CPU. Ini cocok untuk beban kerja yang dapat dipecah berulang dengan cepat,...

### b. Penerapan Thread di POSIX (`thrd-posix.c`)
Program `thrd-posix.c` mendemonstrasikan penggunaan **pthread** di sistem POSIX. Pertama, atribut thread (`pthread_attr_t`) diinisialisasi, lalu `pthread_create` memanggil fungsi runner (`void *runner(void*)`) untuk menghitung jumlah bilangan 1…N. Setelah pembuatan thread, `pthread_join` memastikan thread utama menunggu sampai subthread selesai sebelum mencetak hasil. Variabel `sum` dideklarasikan di global agar dapat diakses bersama, dan runtime POSIX menjamin eksekusi sinkron dengan `pthread_join`.

### c. Penerapan Thread di Windows (`thrd-win32.c`)
Di Windows, `CreateThread` digunakan untuk membuat thread lewat Win32 API. Fungsi `Summation` diimplementasikan sesuai konvensi `DWORD WINAPI`, mengambil parameter upper-bound lewat pointer. Setelah thread dibuat, `WaitForSingleObject` menunggu hingga thread selesai, lalu `CloseHandle` membersihkan handle. Perbedaan utama dengan POSIX adalah penamaan fungsi, tipe data DWORD, dan mekanisme penanganan handle thread, meski konsepnya—membuat thread yang menjalankan fungsi terpisah—sangat mirip.

---
