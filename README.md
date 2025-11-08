# 🌐 Arsip Proyek Jaringan – Cisco Packet Tracer

Selamat datang di repositori proyek jaringan saya!  
Repositori ini berisi kumpulan file `.pkt` dari **Cisco Packet Tracer**, yang mendokumentasikan implementasi dan konfigurasi berbagai skenario **lab jaringan dasar hingga routing antar-subnet** menggunakan **IPv4 dan IPv6 (Dual-Stack)**.

**👤 Kontributor:** M. Favian Rizki  
**🧰 Platform:** Cisco Packet Tracer  

---

## 🧩 Judul 1 — Lab 2.9.2: Basic Switch and End Device Configuration

<img width="406" height="333" alt="Topologi" src="https://github.com/user-attachments/assets/953529c9-b0a7-4584-be0d-89fd5c96dcfc" />

### 📖 Deskripsi
Lab ini mencakup **konfigurasi dasar switch dan perangkat akhir (PC)** dalam topologi sederhana untuk membangun fondasi jaringan yang aman dan mudah dikelola.

### ⚙️ Poin Konfigurasi Utama
- Penetapan **hostname** unik pada setiap switch  
- Pengaturan **password konsol & privileged EXEC**  
- Penerapan **banner MOTD** sebagai peringatan keamanan  
- Konfigurasi **SVI (VLAN 1)** untuk manajemen switch  
- Pengaturan **alamat IP statis** pada PC-A dan PC-B  
- **Verifikasi konektivitas** menggunakan `ping`  

### 📂 File Proyek
  Judul 1/TA Judul 1 - M.Favian Rizki.pkt
  
### 🖧 Topologi
Judul 1/Topologi.png
🎥 Video Demo: [Klik untuk menonton di YouTube](https://youtu.be/HlFI6bUdTJc)

---

## 🚀 Judul 2 — Lab 10.4.4: Build a Switch and Router Network

<img width="479" height="200" alt="Topologi" src="https://github.com/user-attachments/assets/b2f46052-32c6-45f4-914a-7314e164017e" />

### 📖 Deskripsi
Lab ini merupakan implementasi jaringan **router dan switch** yang menghubungkan dua subnet berbeda dengan dukungan **Dual-Stack (IPv4 & IPv6)**.

### ⚙️ Poin Konfigurasi Utama
- **Konfigurasi dasar router (hostname, password, banner MOTD)**  
- Pengaturan **interface GigabitEthernet** dengan IPv4 & IPv6  
- Aktivasi **IPv6 routing** menggunakan `ipv6 unicast-routing`  
- **Routing antar-subnet** untuk komunikasi antara dua jaringan  
- Konfigurasi **SVI VLAN 1** dan `ip default-gateway` pada switch  
- Uji konektivitas menggunakan `ping`, `show ip route`, dan `show ipv6 route`

### 📂 File Proyek
Judul 2/TA Judul 2 - M.Favian Rizki.pkt

### 🖧 Topologi
Judul 2/Topologi.png

🎥 Video Demo: [Klik untuk menonton di YouTube](https://youtu.be/Rx4NL9ceT74)

## 🧩 Judul 3 — Lab 3.4.6: Konfigurasi VLAN, Trunking, dan Inter-VLAN Routing

<img width="575" height="314" alt="Topologi" src="https://github.com/user-attachments/assets/69b0521e-e216-4f63-a228-e403706f8d04" />

### 📖 Deskripsi
Lab ini mendemonstrasikan implementasi jaringan yang lebih kompleks, dimulai dari pemisahan jaringan menggunakan **VLAN**, menghubungkan switch menggunakan **Trunking (802.1Q)**, hingga mengaktifkan komunikasi antar-VLAN menggunakan metode **"Router-on-a-Stick"**.

### ⚙️ Poin Konfigurasi Utama
- Pembuatan **VLAN** (VLAN 10 untuk Operasi & VLAN 99 untuk Manajemen) di kedua switch.
- Penetapan port switch ke VLAN spesifik (mode akses), seperti F0/6 di S1 dan F0/18 di S2 ke VLAN 10.
- Konfigurasi **Trunking 802.1Q** secara manual antar switch (S1 & S2) pada port F0/1.
- Penyesuaian **Native VLAN** ke VLAN 1000 untuk keamanan.
- Penambahan **Router (R1)** untuk melakukan **Inter-VLAN Routing**.
- Pembuatan **sub-interface** pada router untuk setiap VLAN (misalnya, `g0/0/1.10` & `g0/0/1.99`) dengan enkapsulasi `dot1q`.
- Konfigurasi port trunk pada switch (f0/3) yang terhubung ke router R1.
- Pengaturan **`ip default-gateway`** pada SVI switch (S1 & S2) ke alamat sub-interface router VLAN 99.
- **Verifikasi konektivitas penuh** antar perangkat di VLAN yang berbeda (misalnya, PC-A di VLAN 10 kini dapat ping ke S1 di VLAN 99).

### 📂 File Proyek
  Judul 3/TA Judul 3 - M.Favian Rizki.pkt
  
### 🖧 Aset Pendukung (Topologi & Hasil)
* `Judul 3/Topologi.png`
* `Judul 3/ping dari PC-A.png` (Hasil akhir konektivitas penuh)
* `Judul 3/ping beda vlan dari pc.png` (Kondisi sebelum Inter-VLAN routing)
* `Judul 3/ping beda vlan dari switch.png` (Kondisi sebelum Inter-VLAN routing)

🎥 Video Demo: [Klik untuk menonton di YouTube](https://youtu.be/AucfRNUlrWk)

---

## 🛠️ Cara Menggunakan
1. **Instal Cisco Packet Tracer** versi 8.0 atau lebih baru → [Download di NetAcad](https://www.netacad.com/courses/packet-tracer)  
2. **Buka file `.pkt`** dari direktori `Judul 1` atau `Judul 2`.  
3. **Jalankan simulasi** dan analisis konfigurasi jaringan di setiap perangkat.  
4. Gunakan perintah seperti `show running-config` untuk mempelajari konfigurasi aktual.  

---

📌 *Repositori ini dibuat sebagai dokumentasi pembelajaran dan referensi konfigurasi jaringan dasar & menengah menggunakan Cisco Packet Tracer.*

