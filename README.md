# YouTube-likes-prediction

Data dari https://www.kaggle.com/c/kaggle-pog-series-s01e01

train dataset = digunakan untuk pemodelan, terdiri dari 20 kolom dan 92275 baris.
test dataset = target untuk aplikasi model, terdiri dari 16 kolom dan 5800 baris.

**Proses**

Pembersihan data
- Tidak ada video duplikat.
- Menyimpan data null di kolom tag dan deskripsi.
- Imputasi dengan median untuk nilai null di kolom durasi.
- Tidak ada penanganan outlier
- Menghapus data dengan 'rating_disabled'
- Menyimpan data dengan 'comment_disabled'

Rekayasa fitur
- Mengubah tanggal menjadi ordinal.
- Menambahkan kolom jumlah hari sejak diterbitkan.
- Mengimputasi kolom kategori dari data kategorikal menjadi data numerik.
- Mengubah kolom tag dan deskripsi menjadi boolean.
- Menghapus kolom dengan tipe data objek (thumbnail_link, id, video_id, title, channelId, channeltitle).

Pemodelan
- Train test split dengan train size 20%.
- mencoba model regresi LightGBM, XGBoost, Regresi Linier, Decision tree dan Random Forest.
- XGboost memiliki performa terbaik.
- HyperParameter Tuning XGboost meningkatkan performa 30%.

**Hasil**

Model dapat memprediksi variabel target dengan skor r2 = 0,8413. Video pendek memiliki rasio Like to View yang lebih tinggi. Pada hari pertama diupload, rasio memiliki skor tinggi kemudian menurun setelah beberapa hari.
