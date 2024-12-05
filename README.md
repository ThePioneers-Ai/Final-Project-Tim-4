# **NutriLabel: Al-Based Nutritional Label Categorization System for Food Safety**


## Project Description
NutriLabel adalah sebuah sistem berbasis kecerdasan buatan (AI) yang dirancang untuk membantu pengguna menganalisis informasi label nutrisi pada produk makanan. Sistem ini memanfaatkan model EasyOCR untuk membaca dan mengolah informasi dari gambar label makanan, kemudian memberikan penilaian berupa grade berdasarkan kualitas kandungan nutrisi. Selain itu, program ini juga memberikan rekomendasi apakah kandungan nutrisi tersebut sesuai dengan kebutuhan gizi pengguna.

**Fitur Utama**
1. Pengenalan Teks pada Label Nutrisi
   Menggunakan model EasyOCR untuk mendeteksi teks dari label makanan dengan akurasi tinggi, bahkan untuk berbagai jenis dan gaya penulisan.
2. Kategorisasi Grade Nutrisi
   Sistem akan mengkategorikan label makanan ke dalam grade tertentu (misalnya: A, B, C, D) berdasarkan kandungan nutrisi seperti protein, gula, garam, lemak total, kalori, takaran saji.
3. Evaluasi Kesesuaian Nutrisi
   Membantu pengguna menentukan apakah kandungan nutrisi pada label makanan sesuai dengan kebutuhan gizi harian pengguna.
4. Antarmuka Pengguna Sederhana
   Program ini dirancang untuk kemudahan penggunaan, sehingga dapat digunakan oleh siapa saja, mulai dari individu hingga profesional di bidang kesehatan.

**Manfaat**
- Membantu masyarakat meningkatkan kesadaran tentang pentingnya membaca dan memahami label nutrisi pada produk makanan.
- Memberikan rekomendasi gizi yang lebih akurat dan sesuai dengan kebutuhan individu.
- Mendukung pengambilan keputusan yang lebih baik dalam memilih makanan yang sehat dan aman.

**Cara Kerja**
1. Unggah Gambar Label
   Pengguna mengunggah gambar label makanan yang ingin dianalisis.
2. Analisis Teks dengan EasyOCR
   Gambar diproses oleh sistem untuk mendeteksi dan mengenali teks pada label.
3. Kategorisasi dan Evaluasi
   Kandungan nutrisi dianalisis, dikategorikan ke dalam grade tertentu, dan dievaluasi terhadap kebutuhan pengguna.
4. Hasil Akhir
   Sistem memberikan hasil berupa grade, analisis kandungan nutrisi, dan rekomendasi yang dapat digunakan untuk memilih produk makanan yang sesuai.

## Contributor
| Full Name | Affiliation | Email | LinkedIn | Role |
| --- | --- | --- | --- | --- |
| Tata Aditya Pamungkas | Universitas Krisnadwipayana | tataadityapa@gmail.com | [link](https://www.linkedin.com/in/tata-aditya-pamungkas) | Team Lead |
| Elvhan Chatisla Cosaken | President University | elvhancc@gmail.com | [link](https://www.linkedin.com/in/elvhan-chatisla-cosaken-296a5324b) | Team Member |
| Fakhira Ammara Raisa | Universitas Sebelas Maret | fakhiraraisa@student.uns.ac.id | [link](http://linkedin.com/in/fakhira-ammara-raisa) |Team Member |
| Farrelly Theo Ariela | Universitas Sebelas Maret | farrellytheoariela@gmail.com | [link](http://www.linkedin.com/in/farrellytheo) | Team Member |
| Karina Aurellia Putri Murti | Universitas Sebelas Maret | karinau100704@gmail.com | [link](https://www.linkedin.com/in/karinaaurellia/) | Team Member |
| Muhammad Fatihaturrizqi | Universitas Sebelas Maret | fatihaturrizqi@student.uns.ac.id | [link](www.linkedin.com/in/muhammad-fatihaturrizqi-b25032304) | Team Member |
| Muhammad Raihan Rifki Asdhar | Universitas Hasanuddin | muhammadraihanrifki973@gmail.com | [link](https://www.linkedin.com/in/muhammad-raihan-rifki-asdhar) | Team Member |

## Setup
### Prerequisite Packages (Dependencies)
- pandas==2.1.0
- OpenCV== 4.10.0
- Matplotlib==3.8.0
- PIL (pillow)==11.0.0
- Numpy==1.26.4
- Yolo==Yolov8
- Easyocr==1.7.2

### Environment
| | |
| --- | --- |
| CPU | Example: Apple M3 Pro 12-core CPU |
| GPU | Example: Nvidia A100 (x1) |
| ROM | Example: 1 TB SSD |
| RAM | Example: 36 GB |
| OS | Example: macOS Sonoma v14.1.1 |

## Dataset
Dataset yang digunakan dalam proyek *NutriLabel* dikumpulkan secara manual oleh The Pioneers (Tim 4). Data diperoleh dengan mengambil foto label nutrisi dari berbagai produk makanan yang tersedia di supermarket, kemudian diolah dan diverifikasi untuk memastikan keakuratannya. Pendekatan manual ini dilakukan untuk memastikan keberagaman data dari berbagai merek dan jenis produk, sehingga sistem dapat memberikan hasil analisis yang lebih relevan dan bermanfaat bagi pengguna..
- Link: https://drive.google.com/drive/folders/11vDffgAP8aZ7kpM1sArhAjvqWFDTl3V-?usp=sharing

## Results
### Model Performance
Kami mencoba beberapa model yaitu KerasOCR, PaddleOCR, EasyOCR, dan Pytesseract OCR. Keempat model memiliki kekurangan dan kelebihanya masing masing. Pada KerasOCR, sangat sulit dibuat hingga beberapa kali error, maka dari itu kami tidak memasukanya kedalam tabel. Pada PaddleOCR mampu mengekstrak data dengan sangat baik, namun terkendala dengan visualisasi yang sangat rumit yang menyusahkan kami mengembangkan model tersebut.Pytesseract OCR memiliki arsitektur yang cukup rumit namun pendeteksian yang tidak lebih baik, model ini sangat fleksibel namun kami memutuskan untuk memilih EasyOCR. Kemudahan dalam memakai dan hasil ekstrak yang sangat baik, membuat lebih efisien bagi kami untuk mengembangkanya.

#### 1. Metrics
Inform your model validation performances, as follows:
- For classification tasks, use **Precision and Recall**.
- For object detection tasks, use **Precision and Recall**. Additionaly, you may also use **Intersection over Union (IoU)**.
- For image retrieval tasks, use **Precision and Recall**.
- For optical character recognition (OCR) tasks, use **Word Error Rate (WER) and Character Error Rate (CER)**.
- For adversarial-based generative tasks, use **Peak Signal-to-Noise Ratio (PNSR)**. Additionally, for specific GAN tasks,
  - For single-image super resolution (SISR) tasks, use **Structural Similarity Index Measure (SSIM)**.
  - For conditional image-to-image translation tasks (e.g., Pix2Pix), use **Inception Score**.

Feel free to adjust the columns in the table below.

| Model | Jumlah Informasi Terdeteksi | Rata Rata Skor kepercayaan diri | Kemampuan Visualisasi | Kesesuaian dengan Teks yang Rumit | WER | CER | Levenshtein DIistance | Kesimpulan |
|---|---|---|---|---|---|---|---|---|
| PytesseractOCR | 14 | - | Baik | Cukup Baik | 88.6 | 60.5 | 1212 | Buruknya jumlah informasik yang terdeteksi dan sulitnya konfigurasi membuat kami memilih untuk memakai model lain|
| PaddlePaddleOCR | 33 | 0.9237 | Sulit untuk visualisasi | Baik  | - | - | - | Optimal untuk teks kompleks, namun kami selalu gagal dalam mengeluarkan visualisasi dengan bounding box  dan sulitnya membaca dokumentasi karena berbahasa china, membuat kami lebih memilih EasyOCR |
| EasyOCR | 35 | 0.8223  | Sangat baik | baik   | 42.3 | 35.85 | 717 | Mudah digunakan dengan akurasi confidence rate yang cukup tinggi, fleksibelitas bahasa membuat kami yakin EasyOCR sangat cocok untuk model kami |
| KerasOCR | 35 | -  | Sangat baik | baik   | 42.00 | 34.85 | 697 | Sangat baik untuk mendeteksi namun sulit dikonfigurasi dan dikembangkan |


#### 2. Ablation Study
Kami memberikan beberapa peningkatan dari eksperiment dan penelitian yang telah kami lakukan. Kami memberikan pertajam gambar untuk usecase apabila foto dari user kurang baik. Sharped image dengan autokernel sangat efektif dalam meningkatkan akurasi model. Bisa dilihat dengan peningkatan dari 14 data menjadi 26 data yang terdeteksi. Selanjutnya ImageRotate, Karena kami membangun model lainya yaitu object detection menggunakan yolov8, beberapa kali yolo mendeteksi gambar menjadi miring, gambar miring tidak bisa diekstrak oleh OCR. Hal ini bisa di antisipasi dengan autorotate yang kami buat. Kami juga melakukan uji coba menggunakan binary Image yang telah kami bangun. namun selama penelitian, Setelah mencoba berbegai theresholding tidak ada peningkatan yang ada oleh model OCR. Sehingga, kami mengurungkan niat memakai metode tersebut.

| model | Metode | Matriks Yang dipakai | Banyak kata sebelum metode | Banyak kata sesudah metode | Kesimpulan |
| --- | --- | --- | --- | --- | --- |
| EasyOCR | Sharped Image | AutoKernel | 14 | 26 | Sharped Image terbukti efektif untuk meningkatkan akurasi model, diharapkanya gambar yang rendah pixel dapat terbantu dengan adanya metode ini | 
| EasyOCR | Image AutoRotate | Auto(90 derajat) | 0 | 21 | Karena OCR tidak bisa mendeteksi kata apabila miring. Metode autorotate sangat krusial untuk pendeteksian dari foto user yang tidak terduga | 

#### 3. Training/Validation Curve
Kami menggunakan training manual menggunakan spreadsheet. Setelah berkonsultasi dan meneliti, cara paling efektif adalah secara langsung membandingkan hasil penilaian OCR dan label pada Spreedsheet. berikut adalah link spredsheetnya, namun kami benar benar minta maaf karena ini masih on progress https://docs.google.com/spreadsheets/d/1qcEFGM26WgQUjSyybPk2mEAPaGHQIteSwozumr9TvGQ/edit?usp=sharing
 
### Testing
(On Progress)

### Deployment (Optional)
Describe and show how you deploy this project (e.g., using Streamlit or Flask), if any.

## Supporting Documents
### Presentation Deck
- Link: https://...

### Business Model Canvas
Provide a screenshot of your Business Model Canvas (BMC). Give some explanations, if necessary.

### Short Video
Provide a link to your short video, that should includes the project background and how it works.
- Link: https://...

## References
Provide all links that support this final project, i.e., papers, GitHub repositories, websites, etc.
- Link: https://...
- Link: https://...
- Link: https://...

## Additional Comments
Provide your team's additional comments or final remarks for this project. For example,
1. ...
2. ...
3. ...

## How to Cite
If you find this project useful, we'd grateful if you cite this repository:
```
@article{
...
}
```

## License
For academic and non-commercial use only.

## Acknowledgement
This project entitled <b>"YOUR PROJECT TITLE HERE"</b> is supported and funded by Startup Campus Indonesia and Indonesian Ministry of Education and Culture through the "**Kampus Merdeka: Magang dan Studi Independen Bersertifikasi (MSIB)**" program.
