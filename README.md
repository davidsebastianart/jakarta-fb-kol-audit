# Jakarta F&B KOL Audit: Separating Real Influence from Bot Farms (DaaS MVP)

Banyak brand F&B dan agensi digital di Jakarta tanpa sadar "membakar" anggaran marketing mereka. Mereka membayar mahal Influencer/KOL berdasarkan tingginya angka *likes* dan *comments*, tanpa tahu berapa persen dari interaksi tersebut yang berasal dari audiens nyata, dan berapa yang berasal dari *click-farms* (bot).

Proyek ini adalah bentuk Minimum Viable Product (MVP) untuk layanan **Data-as-a-Service (DaaS)**. Tujuannya sederhana: Mengaudit metrik KOL secara otomatis untuk menyelamatkan anggaran marketing dari *fake engagement*.

### Bagaimana Saya Membangun Ini?

Saya mengaudit 3 KOL F&B ternama di Jakarta (@sibungbung, @anakjajan, @henjiwong) dengan mengambil sampel 300 komentar teratas. Alur kerjanya adalah sebagai berikut:

1. **Ekstraksi Data:** Melakukan *scraping* pada *top post* dan komentar menggunakan Apify.
2. **Transformasi:** Membersihkan ratusan kolom metadata yang berantakan dan menggabungkan relasi data menggunakan Python (Pandas).
3. **Membangun Detektor Bot (NLP):** *Ini adalah bagian paling menantang.* Awalnya, algoritma saya mendeteksi kata "jual" atau "murah" sebagai spam promosi. Padahal, audiens F&B asli sering memakai kata itu untuk *review* murni ("bakmi ini murah", "yang jual ramah"). Saya akhirnya merombak algoritma menggunakan *Regex Word Boundaries* khusus leksikon F&B Indonesia untuk menekan angka *False Positives* hingga nyaris nol.
4. **Visualisasi:** Menyajikan hasil akhir ke dalam *dashboard* Looker Studio yang interaktif agar mudah dibaca oleh level eksekutif.

### Apa yang Data Katakan? (Hasil Audit)

Dari sampel komentar teratas yang diaudit, ini temuan utamanya:

* **Pemenang Autentisitas:** **@sibungbung** adalah pilihan teraman untuk brand. Proporsi audiens organiknya mencapai 98.3%, menandakan interaksi di akun ini sangat murni dan minim manipulasi.
* **Modus Operandi Bot:** Dari seluruh bot yang terdeteksi, 100% masuk dalam kategori *"Low Effort / Emoji Spam"* (misal: spam emotikon atau komen 1 huruf). Ini ciri khas *click-farm* gratisan yang disewa hanya untuk mendongkrak *vanity metrics* (metrik palsu).
* **Fenomena "Sentimen Netral":** Dari seluruh manusia asli yang berkomentar, **84.7% bersentimen netral**. Di industri F&B, audiens ternyata lebih suka *tag* teman atau memberi reaksi singkat ketimbang menulis opini yang emosional.

### Rekomendasi untuk Brand F&B

1. **Gunakan data untuk negosiasi:** Jika KOL target memiliki indikasi *fake engagement* yang lumayan (seperti @henjiwong di angka 7.84%), gunakan data audit ini untuk menegosiasikan harga (CPA/CPM) yang lebih masuk akal.
2. **Ubah strategi konten (CTA):** Karena 84% audiens organik cenderung netral/pasif, brand harus memandu KOL untuk menggunakan *Call-to-Action* yang memancing opini. Jangan sekadar *"Review makanan X"*, tapi ubah menjadi *"Tim pedas atau manis? Komen di bawah!"* untuk memecah kebuntuan sentimen.

## 📊 Dashboard Preview

![Jakarta F&B KOL Authenticity Audit Dashboard](dashboard/jakarta_kol_audit.png)

> **Interactive Version:** [View the Live Google Data Studio Dashboard Here](https://datastudio.google.com/reporting/fa952fc2-3cd4-4353-b6b3-6b2d91f87861)

---
**David Sebastian Aritonang**  
Data Analyst | Turning messy data into strategic business decisions.  
Email: [davidsebastianartt@gmail.com](mailto:davidsebastianartt@gmail.com)  
LinkedIn: [linkedin.com/in/david-sartt](https://www.linkedin.com/in/david-sartt/) 
