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


# Split Data Train And Test

Split data menbjadi training (X_train, y_train) dan testing (X_test, y_test) 

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)

# Scale Data

Melakukan scale data sesudah Split data train test, agar tidak adanya kebocoran data, dengan kata lain mempengaruhi proses train data pada model

# Model & Evaluate
melakukan uji dengan banyak model untuk menentukan accuracy, precision, recall, F1-SCore & AUC terbaik

 ## Logistic Regression
 
    hasil yang di dapatkan dengan model tersebut dalam %
    
     accuracy  = 0.506000
     precision =	0.494764
     recall    =	0.515689
     f1_score  =	0.506215
     AUC	      = 0.505010
   
     
   ![image](https://github.com/user-attachments/assets/6a687467-23f3-4031-ab53-7e6e33938059)
   
     - Penggunaan model menunjukkan Logistic Regression hanya mencapai 50% accuracy
     - F1-Score 50% kinerja seimbang antara Precision dan Recall
     - Confusion matrix, Model cenderung overpredict. Jumlah False Positive (386) lebih tinggi dibandingkan False Negative (355). Model cenderung mengklasifikasikan sampel sebagai      
       Spam(1) meskipun ternyata NonSpam (0).

  ## Decision Tree

     accuracy  = 0.512000
     precision =	0.500703
     recall    =	0.485675
     f1_score  =	0.511417
     AUC	      = 0.493075

   ![image](https://github.com/user-attachments/assets/6990eaa0-e475-4e83-9228-b3d0b6a10adc)

     - Model lebih baik dalam memprediksi NonSpam (0)
     - kinerja presentase accuracy 51% lebih tinggi dibandingkan Logistic Regression

   ## Random Forest

      accuracy  = 0.493333
      precision =	0.480349
      recall    =	0.450205
      f1_score  =	0.492377
      AUC	      = 0.464789

   ![image](https://github.com/user-attachments/assets/e98afeec-22cd-4961-99ac-2b7b4cbeff55)

      - Overal Evaluasi menunjukkan penggunaan Random Forest Classifier hanya mencapai 49% accuracy lebih rendah dibandingan Logistic Regression
      - Nilai Recall lebih rendah pada kategori Spam(1) mengidentifikasikan bahwa model masih kesulitan dalam menentukan Spam
      - Precision yang rendah 0.48 model masih sering mengidentifikasi NonSpam(0) menjadi Spam(1) False Positive
      - Confusion matrix, Model cenderung seimbang. Jumlah False Positive (357) lebih dan False Negative (403). Model tidak bias ke salah satu kategori

   ## XGBoost
   
      accuracy  = 0.503333
      precision =	0.491758
      recall    =	0.488404
      f1_score  =	0.503002
      AUC	      = 0.490075

   ![image](https://github.com/user-attachments/assets/954ce6b3-6200-4544-8330-2de901312783)

   ## XGBoost

      accuracy  = 0.517333
      precision =	0.506494
      recall    =	0.478854
      f1_score  =	0.516480
      AUC	      = 0.492286

   ![image](https://github.com/user-attachments/assets/ba76a4eb-7efb-41fd-80ca-d55d72eb3f94)

