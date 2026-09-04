# TESTING MERMAID.JS

```mermaid
graph TD
    S0("(0,0) Start") -->|Aturan 1| S1("(4,0)")
    S0 -->|Aturan 2| S2("(0,3)")
    
    %% Jalur Kiri (Mulai dari Isi Galon A)
    S1 -->|Aturan 8| S3("(1,3)")
    S3 -->|Aturan 6| S4("(1,0)")
    S4 -->|Aturan 10| S5("(0,1)")
    S5 -->|Aturan 1| S6("(4,1)")
    S6 -->|Aturan 8| S7("(2,3) TERCAPAI!")
    
    %% Penyelesaian dari (2,3) ke Tujuan Lainnya
    S7 -->|Aturan 6| S13("(2,0) TERCAPAI!")
    S7 -->|Aturan 4, d=2| S14("(2,1) TERCAPAI!")
    S7 -->|Aturan 4, d=1| S15("(2,2) TERCAPAI!")
    
    %% Jalur Kanan (Mulai dari Isi Galon B)
    S2 -->|Aturan 9| S8("(3,0)")
    S8 -->|Aturan 2| S9("(3,3)")
    S9 -->|Aturan 7| S10("(4,2)")
    
    %% Penyelesaian dari (4,2)
    S10 -->|Aturan 5| S11("(0,2)")
    S11 -->|Aturan 9| S12("(2,0) TERCAPAI!")
    S10 -->|Aturan 3, d=2| S16("(2,2) TERCAPAI!")
    
    classDef goal fill:#28a745,stroke:#fff,stroke-width:2px,color:#fff;
    class S7,S12,S13,S14,S15,S16 goal;


# TESTING PENGGUNAAN TABEL PADA README.md

| Isi ember A | Isi ember B | Aturan yg dipakai |
| :---: | :---: | :--- |
| 0 | 0 | 2 (Isi galon B sampai penuh) |
| 0 | 3 | 9 (Tuang seluruh air galon B ke A) |
| 3 | 0 | 2 (Isi galon B sampai penuh) |
| 3 | 3 | 7 (Tuang air galon B ke A sampai A penuh) |
| 4 | 2 | 5 (Kosongkan galon A) |
| 0 | 2 | 9 (Tuang seluruh air galon B ke A) |
| **2** | **0** | **Solusi Tercapai** |

#### Solusi untuk Tujuan: (2,1)

| Isi ember A | Isi ember B | Aturan yg dipakai |
| :---: | :---: | :--- |
| 0 | 0 | 1 (Isi galon A sampai penuh) |
| 4 | 0 | 8 (Tuang air galon A ke B sampai B penuh) |
| 1 | 3 | 6 (Kosongkan galon B) |
| 1 | 0 | 10 (Tuang seluruh air galon A ke B) |
| 0 | 1 | 1 (Isi galon A sampai penuh) |
| 4 | 1 | 8 (Tuang air galon A ke B sampai B penuh) |
| 2 | 3 | 4 (Buang sebagian air, d=2, dari galon B) |
| **2** | **1** | **Solusi Tercapai** |

#### Solusi untuk Tujuan: (2,2)

| Isi ember A | Isi ember B | Aturan yg dipakai |
| :---: | :---: | :--- |
| 0 | 0 | 2 (Isi galon B sampai penuh) |
| 0 | 3 | 9 (Tuang seluruh air galon B ke A) |
| 3 | 0 | 2 (Isi galon B sampai penuh) |
| 3 | 3 | 7 (Tuang air galon B ke A sampai A penuh) |
| 4 | 2 | 3 (Buang sebagian air, d=2, dari galon A) |
| **2** | **2** | **Solusi Tercapai** |




# Mengenal Peran AI dalam Mendeteksi Serangan Cybersecurity
oleh: Athaya Nabil Putra Halby - 2407134906



## Latar Belakang

Kalau kita perhatikan, perkembangan dunia digital belakangan ini berlari sangat cepat. Bersamaan dengan itu, ancaman keamanan siber (*cybersecurity*) juga ikut berevolusi menjadi jauh lebih kompleks. Dulu, tim IT mungkin masih sanggup mengandalkan perlindungan standar seperti *firewall* atau antivirus konvensional untuk menjaga sebuah sistem. Mereka memonitor lalu lintas jaringan secara manual dan memeriksa *log* harian. Sayangnya, cara manual seperti ini sudah tidak lagi relevan.Peretas masa kini sudah menggunakan metode otomatis yang masif dan tersebar. Jika sebuah perusahaan hanya mengandalkan tenaga manusia untuk memeriksa ribuan atau bahkan jutaan baris lalu lintas data setiap harinya, sistem mereka pasti akan kewalahan dan akhirnya jebol. Di sinilah pendekatan keamanan jaringan membutuhkan cara pandang yang baru.



## Contoh Penerapan AI dalam Keamanan Siber

Untuk mengatasi keterbatasan sistem tradisional dan tenaga manusia, Kecerdasan Buatan (AI) masuk untuk mengambil alih tugas-tugas komputasi berat. AI mengubah cara kita bertahan, dari yang awalnya hanya pasrah menunggu diserang (pendekatan reaktif) menjadi lebih waspada dan bersiap sebelum serangan terjadi (pendekatan proaktif).

Berikut adalah beberapa contoh nyata bagaimana AI diterapkan dalam mengamankan ekosistem digital kita:

**1. Sistem Deteksi Intrusi (IDS) yang Proaktif**  
Sistem keamanan lama umumnya bekerja dengan cara mencocokkan "tanda tangan" (*signature*) virus. Kelemahannya, kalau ada virus varian baru yang belum ada di pangkalan data, sistem akan dengan mudah kebobolan. AI menyelesaikan masalah ini dengan cara mempelajari "perilaku normal" dari sebuah jaringan. Bayangkan AI ini seperti satpam yang sangat hafal dengan kebiasaan karyawan di sebuah gedung. Kalau tiba-tiba ada lalu lintas data yang mencurigakan—misalnya ada aktivitas pengunduhan data berskala besar di jam 3 pagi dari lokasi yang tidak biasa—AI akan langsung menganggap hal tersebut sebagai anomali dan membunyikan peringatan sebelum sistem utama berhasil ditembus.

**2. Analisis Malware Lanjutan (Ancaman *Zero-Day*)**  
Saat ini, pembuat virus sangat pintar merancang *malware* yang bisa bermutasi atau mengubah kodenya sendiri untuk mengelabui deteksi. Untuk menghadapi taktik ini, algoritma AI dilatih untuk tidak sekadar melihat struktur kodenya, melainkan menganalisis perilaku dan niat dari program tersebut. Walaupun program jahat itu adalah jenis baru yang belum pernah dikenali sebelumnya (*zero-day threat*), AI tetap bisa memprediksi pola bahayanya dan memblokir eksekusi program tersebut secara otomatis.

**3. Intelijen Ancaman (*Threat Intelligence*)**  
AI juga bertugas sebagai agen pengumpul intelijen yang bekerja dengan kecepatan kilat. Sistem AI dapat disetel untuk secara otomatis merayapi ribuan forum internet, situs web, hingga *dark web* dalam waktu singkat. Tujuannya adalah mencari tahu tren celah keamanan apa yang sedang ramai didiskusikan oleh komunitas peretas. Lewat peringatan dini dari AI ini, tim keamanan TI memiliki cukup waktu untuk segera melakukan penambalan (*patching*) pada kerentanan sistem mereka jauh hari sebelum peretas benar-benar melancarkan eksploitasi.

### Kesimpulan

Kehadiran Kecerdasan Buatan dalam ranah keamanan siber jelas membawa perubahan yang luar biasa. Namun, penting untuk dicatat bahwa AI bukanlah entitas yang akan menggantikan peran seorang insinyur keamanan (*Security Engineer*). AI lebih tepat disebut sebagai alat kolaborasi tingkat tinggi. Mesin bertugas memproses jutaan data, menyaring anomali, dan menahan serangan awal dalam hitungan detik. Di sisi lain, manusia tetap memegang kendali untuk melakukan investigasi mendalam, merumuskan kebijakan keamanan, dan mengambil keputusan strategis. Sinergi antara kecepatan komputasi mesin dan logika analitis manusia inilah yang menjadi kunci utama pertahanan jaringan di masa depan.



\---



### Referensi

Artikel ini disusun berdasarkan studi literatur dari jurnal akademik berikut:

1. Widalala, R. R., dkk. (2024). *"Dampak Penggunaan Artificial Intelligence Pada Keamanan Siber: Sebuah Kajian Terhadap Potensi Keuntungan dan Ancaman"*. Berajah Journal, 4(8), 1541–1552.  
🔗 [Tautan Publikasi Jurnal](https://ojs.berajah.com/index.php/go/article/view/458)
2. Purnomo, A., dkk. (2024). *"Peran Artificial Intelligence dalam Deteksi Dini Ancaman Keamanan Jaringan"*. Jurnal Minfo Polgan, 13(2).  
🔗 [Tautan Publikasi Jurnal](https://jurnal.polgan.ac.id/index.php/jmp/article/download/14356/2931/20482)
3. Abast, B. R., dkk. (2025). *"Pengaruh Teknologi AI Terhadap Evolusi Modus Kejahatan Siber di Indonesia dan Implikasinya Terhadap Penegakan Hukum"*. Jurnal Nusantara (JICN), 2(6).  
🔗 [Tautan Publikasi Jurnal](https://jicnusantara.com/index.php/jicn/article/download/6108/6137/34433)

