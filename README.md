# Analisis Kinerja Kredit Nasabah (Final Project)
## Project-Based Internship Virtual: Data Scientist Home Credit Indonesia x Rakamin Academy

## 1. Problem Reserach
- Masalah:
Menganalisis kinerja kredit nasabah berdasarkan data pada tabel "bureau" dan "bureau_balance" untuk mengidentifikasi pola-pola yang dapat membantu dalam pengambilan keputusan terkait penilaian kredit.

- Tujuan:
Meningkatkan akurasi penilaian kredit, mengurangi risiko kredit macet, dan meningkatkan profitabilitas perusahaan.

## 2. Data Pre-Processing
- Tools yang digunakan adalah Google Colaboratory
- Import Library. Library yang digunakan adalah pandas, matplotlib.pyplot, dan scikitlearn.
  ```bash
  import pandas as pd
  import matplotlib.pyplot as plt
  from sklearn.model_selection import train_test_split
  from sklearn.linear_model import LogisticRegression
  from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
- Load Dataset. Tabel yang digunakan adalah bureau dan bureau_balance.
  ```bash
  # Memuat data dari file CSV
  bureau = pd.read_csv('/content/sample_data/bureau.csv')
  bureau_balance = pd.read_csv('/content/sample_data/bureau_balance.csv')
- Cek dan handle missing value.
- Cek dan handle data duplikat.
- Gabungkan semua data berdasarkan kolom yang sama, yakni kolom SK_ID_BUREAU
  ```bash
  # Merge bureau and bureau_balance data on SK_ID_BUREAU
  merged_data = pd.merge(bureau, bureau_balance, on='SK_ID_BUREAU', how='left')
  merged_data.head()

## 3. Data Vizualization and Business Insight
![image](https://github.com/mieffarohi/pbi-hci/assets/103298951/d61044a8-81b4-49c8-a0dc-2ef8db0597ed)
- ## Insight:
Permohonan kredit terbanyak ada pada kisaran 500 hari sebelum data direkam.

## 4. Machine Learning Implementation and Evaluation
### Menggunakan regresi logistik untuk memprediksi CREDIT_ACTIVE
![image](https://github.com/mieffarohi/pbi-hci/assets/103298951/524de1dc-4e45-47b6-a846-49ba24daaa97)

### Evaluas performa model
![image](https://github.com/mieffarohi/pbi-hci/assets/103298951/7a9bf6b2-dc8a-45f3-b962-6aaa5a27c10e)
![image](https://github.com/mieffarohi/pbi-hci/assets/103298951/f200b66e-229b-4210-8e3c-44061cab65d2)
![image](https://github.com/mieffarohi/pbi-hci/assets/103298951/34f488b3-9f28-4004-b640-97e25b52f57b)
- Insight:

Dari hasil model yang diberikan, terdapat beberapa insight yang dapat diambil, antara lain: Akurasi model sebesar 70.27%, yang menunjukkan bahwa model tersebut cukup baik dalam memprediksi kategori-kategori yang ada.

Namun, terdapat beberapa kategori yang sulit diprediksi, seperti "Bad debt" dan "Sold", yang memiliki nilai precision dan recall sebesar 0. Hal ini menunjukkan bahwa model perlu diperbaiki untuk dapat memprediksi kategori-kategori ini dengan lebih baik.

## 5. Business Recommendations
Berdasarkan insight-insight yang ditemukan dari analisis data, beberapa rekomendasi bisnis yang dapat diberikan adalah:
- Perlu dilakukan evaluasi ulang terhadap kebijakan penilaian kredit yang digunakan. Hal ini dapat meliputi peninjauan kembali terhadap faktor-faktor yang digunakan dalam penilaian kredit, serta penyesuaian terhadap model penilaian kredit yang digunakan.
- Perlu dilakukan penelitian lebih lanjut untuk mengetahui penyebab dari kategori-kategori yang sulit diprediksi. Hal ini dapat meliputi peninjauan kembali terhadap data yang digunakan, serta penyesuaian terhadap fitur-fitur yang digunakan dalam model penilaian kredit.
- Perlu dilakukan monitoring secara berkala terhadap model penilaian kredit yang digunakan. Hal ini dapat meliputi pemantauan terhadap performa model penilaian kredit, serta peninjauan kembali terhadap model penilaian kredit yang digunakan.

