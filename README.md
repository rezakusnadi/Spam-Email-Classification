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

Korelasi Ceck sebelum drop data pada kolom untuk pengurangan dimensi dan meningkatkan interpretabilitas model dan kolom
Check the correlation on data before drop the columns for dimensional reduction and improve model interpretabilty and dependecies of the columns

![image](https://github.com/user-attachments/assets/dc31729a-9542-4cd2-bc1e-e352773e2cd9)


# Drop Columns

Drop kolom yang tidak dibutuhkan dalam interpreasi model (['Email','Subject','Sender','Recipient','Date','Time'])


# Target Analysis

Pengecekan Target Analysis [Spam Indicator] pada data set
Karena data target balanced, tidak di perlukan over maupun undersampling, sehingga langsung split data

 Spam Indicator |   count    |	percentage
      0	        |    3018	   |       50.3
      1	        |    2982	   |       49.7

![image](https://github.com/user-attachments/assets/2b37d734-3535-4461-ac52-c794f0526084)


#Split Data Train And Test


