## 🧩 Judul 3 — Lab 3.4.6: Konfigurasi VLAN, Trunking, dan Inter-VLAN Routing

<img width="575" height="314" alt="Topologi" src="https://github.com/user-attachments/assets/5a8460f5-cb8a-4125-bf51-3ba20ba9d880" />


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
* `TA Judul 3 - M.Favian Rizki.pkt`
  
---

### 📊 Analisis Hasil & Verifikasi

Screenshot berikut menunjukkan evolusi konektivitas jaringan, dari sebelum dan sesudah Inter-VLAN routing diaktifkan.

#### Tahap 1: Trunking Aktif, Belum Ada Routing (Ping dari PC-A)

<img width="869" height="612" alt="ping beda vlan dari pc" src="https://github.com/user-attachments/assets/1eafbe3e-b5f2-4c43-b3dc-02ec816b0118" />

* **`ping 192.168.10.4` (ke PC-B) -> SUKSES**
    * **Kenapa:** PC-A dan PC-B berada di **VLAN yang sama (VLAN 10)**. Koneksi trunk antar-switch S1 dan S2 sudah dikonfigurasi, sehingga traffic VLAN 10 bisa lewat dari S1 ke S2.

* **`ping 192.168.1.11` (ke S1) -> GAGAL (Request timed out)**
    * **Kenapa:** PC-A (VLAN 10) mencoba menghubungi S1 (VLAN 99). Karena mereka berada di **VLAN (dan subnet) yang berbeda**, diperlukan perangkat Layer 3 (router) untuk menjembataninya. Pada tahap ini, router belum dikonfigurasi.

#### Tahap 1: Trunking Aktif, Belum Ada Routing (Ping dari S1)

<img width="825" height="302" alt="ping beda vlan dari switch" src="https://github.com/user-attachments/assets/f0f5d506-73b5-4f26-89fe-a9fb99f6c5e5" />

* **`ping 192.168.1.12` (ke S2) -> SUKSES**
    * **Kenapa:** S1 dan S2 berada di **VLAN yang sama (VLAN 99)**. Koneksi trunk F0/1 mengizinkan traffic VLAN 99 (traffic manajemen) lewat.

* **`ping 192.168.10.3` (ke PC-A) -> GAGAL (0 percent)**
    * **Kenapa:** Sama seperti sebelumnya, S1 (VLAN 99) tidak bisa berkomunikasi dengan PC-A (VLAN 10) tanpa adanya router.

* **(Pesan Tambahan):** `%CDP-4-NATIVE_VLAN_MISMATCH...`
    * **Kenapa:** Pesan ini muncul karena port trunk F0/1 di S1 sudah diatur untuk menggunakan Native VLAN 1000, tetapi F0/1 di S2 masih menggunakan Native VLAN 1 (default). Ini adalah kesalahan konfigurasi sementara yang dideteksi oleh Cisco Discovery Protocol (CDP) saat lab berlangsung.

#### Tahap 2: Inter-VLAN Routing ("Router-on-a-Stick") Aktif

<img width="551" height="669" alt="ping dari PC-A" src="https://github.com/user-attachments/assets/014ac6b4-ff4b-4712-8ea7-3725561c4ca9" />

* **`ping 192.168.1.11` (ke S1) -> SUKSES**
* **`ping 192.168.1.12` (ke S2) -> SUKSES**
    * **Kenapa:** Ping dari PC-A (VLAN 10) ke S1/S2 (VLAN 99) **sekarang berhasil**. Traffic dikirim dari PC-A ke gateway-nya (R1 sub-interface `.10`), router me-routing paket tersebut ke sub-interface `.99`, lalu mengirimkannya ke S1/S2. Balasan dari S1/S2 juga di-routing kembali oleh R1 ke PC-A.

* **`ping 192.168.10.4` (ke PC-B) -> SUKSES**
    * **Kenapa:** Komunikasi ini tetap sukses karena masih berada di dalam VLAN yang sama (VLAN 10).

### 🎥 Video Demo
[Klik untuk menonton di YouTube](https://youtu.be/AucfRNUlrWk)
