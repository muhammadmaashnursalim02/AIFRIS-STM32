# Dual-Mode PID Controller with Hysteresis for DC Motor (STM32)

Repositori ini berisi *source code* dan file simulasi untuk implementasi **Pengendali PID Dual-Mode dengan Logika Histeresis** pada *plant* Motor DC. Proyek ini dijalankan menggunakan metode *Software-in-the-Loop* (SIL) menggunakan mikrokontroler STM32F103C8T6 yang disimulasikan di Proteus.

## 📌 Deskripsi Proyek
Sistem kendali PID konvensional seringkali kesulitan menyeimbangkan antara waktu respons yang cepat (*fast rise time*) dan stabilitas (tanpa *overshoot* / *chattering*). Proyek ini menyelesaikan masalah tersebut dengan menggunakan **Dual-Mode PID**:
1. **Mode Agresif (Kp=2.20, Ki=0.30, Kd=0.08):** Digunakan saat *error* besar untuk mempercepat respons.
2. **Mode Normal (Kp=1.50, Ki=0.70, Kd=0.05):** Digunakan saat *error* kecil untuk menjaga stabilitas dan presisi di sekitar titik target (*setpoint*).

**Logika Histeresis** ditambahkan sebagai batas transisi antar mode (berpindah ke agresif saat $|error| > 12\%$, dan kembali ke normal saat $|error| < 4.5\%$) untuk mencegah fenomena *chattering* (perpindahan mode terus-menerus yang tidak stabil).

## 🚀 Fitur Utama
* **Pemodelan Plant Motor DC Orde-1:** Diimplementasikan secara matematis dengan metode diskritisasi *Euler Forward*.
* **Dual-Mode PID:** Transisi dinamis dua set parameter PID berdasarkan nilai error aktual.
* **Hysteresis Logic:** Sistem transisi dengan batas atas dan batas bawah yang mencegah *noise* pada sinyal kendali.
* **Serial Telemetry:** Pengiriman data secara *real-time* (Nilai PWM, Error, RPM) via UART (Virtual Terminal).

## 🛠️ Perangkat & Software
* **Mikrokontroler:** STM32F103C8T6 (Blue Pill)
* **Motor Driver:** L298N (H-Bridge)
* **Simulator:** Proteus Professional (v8.x atau lebih baru)
* **Visualisasi Data:** GNUplot / Python (untuk plotting data UART)
