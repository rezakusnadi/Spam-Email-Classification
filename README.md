# Spam-Email-Classification

Bertujuan untuk mengembangkan model klasifikasi yang dapat membedakan antara email Spam dan Non Spam. Model ini akan menggunakan teknik machine learning, algoritma klasifikasi, untuk mengidentifikasi pola dan ciri-ciri yang membedakan antara kedua jenis email tersebut. Dengan menggunakan dataset email yang telah dikategorikan sebagai Spam dan Non Spam untuk melatih model, dengan mengevaluasi performa bebeapa model tersebut menggunakan metrik-metrik seperti akurasi, presisi, recall, dan F1 score.
dengan menggunakan algoritma machine learning untuk menangani masalah klasifikasi email, dan pembuatan model juga mengevaluasi model klasifikasi.


# Data

Data yang di gunakan dalam model berisikan data untuk modeling Spam Email Classification, dataset berisikan features yang akan di gunakan dalam modeling nantinya seperti
Email, Subject, Sender, Recipient, Link Count, HTML Tags Count, Uppercase Count, Word Count, Spam Indicator dan lainnya

Penggunaan Library seperti NumPy, Pandas, seaborn, matplotlib, sklearn, xgboost

Data Process :
- DataFrame Understanding
- Correlation Analysis
- Drop Columns
- Target Analysis
- Split Data Train and Test
- Scale Data
- Modeling and Evaluate (use several model to find best result accuracy, precision, recall, F1-SCore & AUC)
- Hyperparameter

# DataFrame Understanding

Pengecekan DataFrame, Unique Value, Info, Missing Value, Duplicate Check yang dapat di lihat pada Script File mendeskripsikan bahwa

- Dari DataFrame terdapat 6000 data dan 16 kolom
- Spam Indicator (1) is Spam (0) Non Spam
- Target kolom Spam Indicator menjelaskan bahwa 50% data adalah NonSpam (1)
- Dari Mean Link Count up to 5 kemungkinan Spam 49%
- sama dengen Uppercase Count 75% likely sebagai Spam 49%
- HTML Tags Count pada 2.5 dari maks 5.0 juga kemungkinan sebagai Spam 49%
- Dari Deskripsi data di atas akan di pastikan kembali menggunakan Correlation Heatmap apakah kolom-kolom tersebut sangat berpengaruh pada penentuan Spam Indicator
- Data Fill 100%
- Tidak adanya data Duplicate

# Correlation Analysis


