# Penjelasan Forking dan Analisis Kode

<br>

## Pengertian Forking

Forking merupakan suatu mekanisme di mana sebuah proses utama (parent process) menciptakan salinan dirinya yang disebut sebagai proses anak (child process). Dalam bahasa C, proses ini dilakukan dengan memanggil sistem call `fork()`. Setelah pemanggilan `fork()`, akan terbentuk dua proses terpisah yang berjalan secara mandiri—proses induk yang memiliki PID asli, dan proses anak dengan PID baru. Kedua proses akan melanjutkan eksekusi dari titik setelah `fork()` dipanggil.

<br>

## Implementasi Forking di Bahasa C

```c
#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid = fork();

    if (pid < 0) {
        perror("Fork gagal");
        return 1;
    } else if (pid == 0) {
        printf("Ini adalah proses anak dengan PID %d\n", getpid());
    } else {
        printf("Ini adalah proses induk dengan PID %d dan anak dengan PID %d\n", getpid(), pid);
    }

    return 0;
}
```
Penjelasan kode di atas:
Pemanggilan fork() bertujuan menciptakan proses baru (anak).

Bila pid bernilai negatif, berarti terjadi error saat membuat proses anak.
Bila pid sama dengan nol, itu menunjukkan eksekusi berada di proses anak.
Bila pid bernilai positif, eksekusi dilakukan oleh proses induk, dan nilai pid merujuk ke PID dari proses anak.

<br>
Apakah print123thread.c Memanfaatkan Fork?
Tidak. Program dalam print123thread.c tidak menggunakan mekanisme forking. Sebaliknya, kode tersebut menerapkan threading menggunakan pustaka pthread untuk mengeksekusi 
tiga thread yang bekerja secara sinkron.

<br>

Ulasan Kode print123thread.c
Berdasarkan peninjauan terhadap kode di tautan tersebut, dapat disimpulkan bahwa program tersebut mengandalkan threading (bukan forking).
Kode tersebut memanfaatkan pustaka pthread untuk mencetak angka 1, 2, dan 3 secara bergiliran dalam sebuah loop tanpa batas. Berikut alur logikanya:

Inisialisasi: Program memuat pustaka yang dibutuhkan serta mendefinisikan variabel global, termasuk mutex (pthread_mutex_t) dan condition variable (pthread_cond_t) untuk keperluan sinkronisasi antar thread.

Variabel Global:

pthread_mutex_t lock: Berfungsi untuk menghindari race condition antara thread.
pthread_cond_t cond1, cond2, cond3: Tiga variabel kondisi yang digunakan untuk mengatur giliran eksekusi thread.
int done = 1: Menandakan thread mana yang sedang mendapat giliran untuk dijalankan.

Fungsi Thread (foo):

Fungsi menerima parameter berupa pointer ke angka (1, 2, atau 3) yang mengidentifikasi masing-masing thread.
Thread masuk ke loop tak hingga dan mencoba mengunci mutex.
Jika done tidak sesuai dengan nomor thread, maka thread akan menunggu pada condition variable-nya.
Ketika done sesuai, thread mencetak angkanya, mengubah nilai done agar thread berikutnya bisa jalan, dan memberi sinyal pada condition variable thread selanjutnya.
Mutex kemudian dilepaskan untuk memberi kesempatan pada thread lain.

Fungsi main:

Membuat tiga thread (tid1, tid2, tid3) yang menjalankan fungsi foo dengan masing-masing argumen 1, 2, dan 3.
Program utama menggunakan pthread_join untuk menunggu ketiga thread selesai.
