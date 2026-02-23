# Reflection

Anya Aleena Wardhany

2406401773

<details>
<summary><b>Module 2</b></summary>

## Code Quality Issues
Missing Gradle Execution Permission
- Masalah: Docker tidak memiliki izin untuk eksekusi `./gradlew` karena perbedaan penanganan file permission antara 
sistem operasi lokal dan Linux di Docker
- Fix: menambahkan baris `RUN chmod +x ./gradlew` sebelum perintah build dijalankan


## CI/CD Implementation
Menurut saya, implementasi workflow pada project ini sudah memenuhi CI/CD
- **CI:** Setiap kali dilakukan `push` atau `pull request`, Github Actions menjalankan script verfikasi. Verifikasi 
tersebut mencakup build, unit test, code quality check with _SonarCloud_, laporan code coverage dari _Jacoco_. Hal 
ini sesuai dengan prinsip CI yang mana setiap perubahan kode secara kontinu dan diverifikasi secara otomatis untuk 
mendeteksi kesalahan secepat mungkin.
- **CD:** setiap perubahan yang telah divalidasi dan di-merge ke branch utama, `master`, akan memicu 
proses otomatisasi untuk mengirim aplikasinya langsung ke platform _Koyeb_ (dengan wrapper Docker). Hal ini sesuai 
dengan prinsip CD yang mana aplikasi selalu berada dalam kondisi siap pakai (deployed).
</details>
