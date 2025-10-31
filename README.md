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


---

## 🛠️ Cara Menggunakan
1. **Instal Cisco Packet Tracer** versi 8.0 atau lebih baru → [Download di NetAcad](https://www.netacad.com/courses/packet-tracer)  
2. **Buka file `.pkt`** dari direktori `Judul 1` atau `Judul 2`.  
3. **Jalankan simulasi** dan analisis konfigurasi jaringan di setiap perangkat.  
4. Gunakan perintah seperti `show running-config` untuk mempelajari konfigurasi aktual.  

---

📌 *Repositori ini dibuat sebagai dokumentasi pembelajaran dan referensi konfigurasi jaringan dasar & menengah menggunakan Cisco Packet Tracer.*

