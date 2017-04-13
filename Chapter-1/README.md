## Bab 1: Mengenal arsitektur x86 dan OS kita

### Apa itu arsitektur x86?

> Istilah x86 merujuk pada sebuah keluarga set instruksi arsitektur yang *backward compatible* yang berbasis pada Intel 8086 CPU.

Arsitektur x86 merupakan set instruksi arsitektur yang paling umum digunakan sejak dikenalkan pada tahun 1981 untuk IBM PC. Banyak software, termasuk sistem operasi (OS) seperti DOS, Windows, Linux, BSD, Solaris, dan Mac OS X, bekerja menggunakan hardware berbasis x86.

Dalam materi ini, Kita akan mendesain sebuah sistem operasi untuk arsitektur x86-32 bukan x86-64. Berkat *backward compatibility*, sistem operasi yang kita buat akan tetap *compatible* dengan PC yang lebih baru (namun Anda perlu berhati-hati jika ingin menjalankannya di mesin komputer Anda secara langsung).

### Sistem Operasi yang akan kita buat

Tujuan dari materi ini adalah untuk membangun sebuah sistem operasi sederhana sungguhan yang berbasiskan UNIX dengan menggunakan bahasa pemrograman C++, bukan hanya sekedar sebagai *"proof-of-concept"*. Sistem operasi harus dapat melakukan booting, memulai sebuah shell untuk user, dan juga harus *extensible*.

Sistem Operasi akan dikembangkan untuk arsitektur x86, yang berjalan pada prosesor 32 bit, dan *compatible* dengan IBM PC.

**Spesifikasi:**

* Kode dalam bahasa pemrograman C++
* Arsitektur x86, 32 bit
* Boot menggunakan Grub
* Untuk driver, menggunakan sistem seperti sistem modular
* Memiliki gaya seperti *UNIX style*
* Multitasking
* ELF executable di *userland* (lingkungan di mana user berinteraksi dengan sistem)
* Module (dapat diakses di *userland* melalui `/dev/...`) :
    * IDE disks
    * DOS partitions
    * Clock
    * EXT2 (read only)
    * Boch VBE
* Userland :
    * API Posix
    * LibC
    * "Dapat" menjalankan sebuah shell atau beberapa program *executable* lainnya (seperti lua)
