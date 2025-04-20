## 4. Jawaban Exercise Chapter 4

### **4.1**  
**Program** adalah sekumpulan instruksi statis, sedangkan **proses** adalah program yang sedang dieksekusi. Proses mencakup state eksekusi, nilai register, counter, dan resources seperti file dan memori.

### **4.2**  
Beberapa informasi yang disimpan dalam Process Control Block (PCB):
- Process state
- Program counter
- CPU register
- CPU scheduling information
- Memory management information
- Accounting information
- I/O status information

### **4.3**  
Diagram tiga-state proses terdiri dari:
- **Ready**: proses siap dijalankan
- **Running**: proses sedang dijalankan CPU
- **Waiting**: proses menunggu event (misal I/O)

Transisi:
- Ready → Running (scheduler memilih)
- Running → Waiting (menunggu I/O)
- Waiting → Ready (I/O selesai)
- Running → Ready (preemption)

### **4.4**  
Pendekatan `new → ready → running → terminated` memungkinkan OS mengatur semua state proses dan mengontrol sumber daya yang digunakan tiap proses.

### **4.5**  
Context switch adalah proses menyimpan state proses saat ini dan memuat state proses berikutnya. Ini terjadi saat proses diganti, misal oleh interrupt atau scheduler.

### **4.6**  
Multithreading bermanfaat karena:
- Responsif (UI tetap responsif saat ada proses latar belakang)
- Berbagi sumber daya antar thread
- Ekonomis (tidak seberat proses )
