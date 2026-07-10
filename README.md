🕵️‍♂️ Jakarta F&B KOL Audit: Separating Real Influence from Bot Farms (DaaS MVP)

Banyak brand F&B dan agensi digital di Jakarta tanpa sadar "membakar" anggaran marketing mereka. Mereka membayar mahal Influencer/KOL berdasarkan tingginya angka likes dan comments, tanpa tahu berapa persen dari interaksi tersebut yang berasal dari audiens nyata, dan berapa yang berasal dari click-farms (bot).

Proyek ini adalah bentuk Minimum Viable Product (MVP) untuk layanan Data-as-a-Service (DaaS). Tujuannya sederhana: Mengaudit metrik KOL secara otomatis untuk menyelamatkan anggaran marketing dari fake engagement.

🔗 Lihat Interactive Dashboard (Looker Studio)
🔗 Download/Lihat Executive Deck (PPTX)

🛠️ Bagaimana Saya Membangun Ini?

Saya mengaudit 3 KOL F&B ternama di Jakarta (@sibungbung, @anakjajan, @henjiwong) dengan mengambil sampel 295 komentar teratas. Alur kerjanya adalah sebagai berikut:

Ekstraksi Data: Melakukan scraping pada top post dan komentar menggunakan Apify.

Transformasi: Membersihkan ratusan kolom metadata yang berantakan dan menggabungkan relasi data menggunakan Python (Pandas).

Membangun Detektor Bot (NLP): Ini adalah bagian paling menantang. Awalnya, algoritma saya mendeteksi kata "jual" atau "murah" sebagai spam promosi. Padahal, audiens F&B asli sering memakai kata itu untuk review murni ("bakmi ini murah", "yang jual ramah"). Saya akhirnya merombak algoritma menggunakan Regex Word Boundaries khusus leksikon F&B Indonesia untuk menekan angka False Positives hingga nyaris nol.

Visualisasi: Menyajikan hasil akhir ke dalam dashboard Looker Studio yang interaktif agar mudah dibaca oleh level eksekutif.

📊 Apa yang Data Katakan? (Hasil Audit)

Dari 295 sampel komentar teratas yang diaudit, ini temuan utamanya:

Pemenang Autentisitas: @sibungbung adalah pilihan teraman untuk brand. 98.3% interaksinya berasal dari manusia asli. Interaksi di akun ini sangat murni dan minim manipulasi.

Modus Operandi Bot: 100% dari 14 bot yang terdeteksi masuk dalam kategori "Low Effort / Emoji Spam" (misal: spam emotikon atau komen 1 huruf). Ini ciri khas click-farm gratisan yang disewa hanya untuk mendongkrak vanity metrics (metrik palsu).

Fenomena "Sentimen Netral": Dari seluruh manusia asli yang berkomentar, 84.7% bersentimen netral. Di industri F&B, audiens ternyata lebih suka tag teman atau memberi reaksi singkat ketimbang menulis opini yang emosional.

💡 Rekomendasi untuk Brand F&B

Gunakan data untuk negosiasi: Jika KOL target memiliki indikasi fake engagement yang lumayan (seperti @henjiwong di angka 7.84%), gunakan data audit ini untuk menegosiasikan harga (CPA/CPM) yang lebih masuk akal.

Ubah strategi konten (CTA): Karena 84% audiens organik cenderung netral/pasif, brand harus memandu KOL untuk menggunakan Call-to-Action yang memancing opini. Jangan sekadar "Review makanan X", tapi ubah menjadi "Tim pedas atau manis? Komen di bawah!" untuk memecah kebuntuan sentimen.

📂 Struktur Repositori

Jika Anda ingin mereplikasi atau melihat source code proyek ini, silakan telusuri file berikut:

01_ETL_and_Bot_Detection.ipynb : Script Python berisi logika cleaning, Regex bot detection, dan analisis sentimen.

KOL_Audit_Presentation.pptx : Executive slide deck yang merangkum temuan bisnis dari proyek ini.

DB_Master_KOL_Audit.csv : Dataset mentah hasil ekstraksi awal.

final_daas_dataset.csv : Dataset final (sudah diklasifikasi) yang dihubungkan ke Looker Studio.

preview_dashboard.png : Gambar tangkapan layar dari hasil akhir dashboard.

David Sebastian Aritonang

Data Analyst | Turning messy data into strategic business decisions.

📩 LinkedIn | 🌐 Portfolio/Medium
