# **NutriLabel: Al-Based Nutritional Label Categorization System for Food Safety**


## Project Description
NutriLabel is an artificial intelligence (AI) based system designed to help users analyze nutrition label information on food products. This system utilizes the EasyOCR model to read and process information from food label images, then provides an assessment in the form of a grade based on the quality of the nutritional content. In addition, the program also provides recommendations on whether the nutritional content is in accordance with the user's nutritional needs.

**Main Features**
1. Text Recognition on Nutrition Labels
   Uses the EasyOCR model to detect text from food labels with high accuracy, even for different types and styles of writing.
2. Nutrition Grade Categorization
   The system will categorize food labels into specific grades (e.g. A, B, C, D) based on nutritional content such as protein, sugar, salt, total fat, calories, serving size.
3. Evaluation of Nutritional Appropriateness
   Helps users determine whether the nutritional content of food labels is in accordance with the user's daily nutritional needs.
4. Simple User Interface
   The program is designed for ease of use, so it can be used by anyone, from individuals to healthcare professionals.

**Benefits**
- Help people raise awareness about the importance of reading and understanding nutrition labels on food products.
- Provides more accurate nutritional recommendations tailored to individual needs.
- Support better decision making in choosing healthy and safe food.

**How it works**
1. Label Image Upload
   Users upload an image of the food label they wish to analyze.
2. Text Analysis with EasyOCR
   The image is processed by the system to detect and recognize the text on the label.
3. Categorization and Evaluation
   Nutritional content is analyzed, categorized into specific grades, and evaluated against user requirements.
4. Final Result
   The system provides results in the form of grade, nutritional content analysis, and recommendations that can be used to select suitable food products.

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
| Component | Specification |
| --- | --- |
| CPU | Example: Apple M3 Pro 12-core CPU |
| GPU | Example: Nvidia A100 (x1) |
| ROM | Example: 1 TB SSD |
| RAM | Example: 36 GB |
| OS | Example: macOS Sonoma v14.1.1 |

## Dataset
The dataset used in the *NutriLabel* project was manually collected by The Pioneers (Team 4). The data was obtained by taking photos of nutrition labels from various food products available in supermarkets, then processed and verified to ensure accuracy. This manual approach was taken to ensure the diversity of data from different brands and types of products, so that the system can provide more relevant and useful analysis results for users.
- Link: https://drive.google.com/drive/folders/11vDffgAP8aZ7kpM1sArhAjvqWFDTl3V-?usp=sharing

## Results
### Model Performance
Several OCR models were evaluated, including KerasOCR, PaddleOCR, EasyOCR, and Pytesseract OCR, each with its own strengths and weaknesses:
- KerasOCR: Challenging to implement, with repeated errors during setup. Due to these issues, it was excluded from further evaluation.
- PaddleOCR: Demonstrated excellent data extraction capabilities but was hindered by complex visualization, making further development difficult.
- Pytesseract OCR: Featured a flexible architecture but delivered less accurate detection compared to other models.
- EasyOCR: Provided ease of use and high-quality extraction results, making it the most efficient and suitable choice for this project.
Based on these findings, EasyOCR was selected as the primary model for implementation.

#### 1. Metrics
Inform your model validation performances, as follows:
- For classification tasks, use **Precision and Recall**.
- For object detection tasks, use **Precision and Recall**. Additionaly, you may also use **Intersection over Union (IoU)**.
- For image retrieval tasks, use **Precision and Recall**.
- For optical character recognition (OCR) tasks, use **Word Error Rate (WER) and Character Error Rate (CER)**.
- For adversarial-based generative tasks, use **Peak Signal-to-Noise Ratio (PNSR)**. Additionally, for specific GAN tasks,
  - For single-image super resolution (SISR) tasks, use **Structural Similarity Index Measure (SSIM)**.
  - For conditional image-to-image translation tasks (e.g., Pix2Pix), use **Inception Score**.

| **Model** | **Amount of Detected Information** | **Average Confidence Score** | **Visualization Capability** | **Suitability for Complex Text** | **WER** | **CER** | **Levenshtein Distance** | **Conclusion** |  
|---|---|---|---|---|---|---|---|---|  
| **PytesseractOCR** | 14 | - | Good | Fair | 88.6 | 60.5 | 1212 | The poor amount of detected information and the difficulty of configuration led to the decision to use other models. |  
| **PaddlePaddleOCR** | 33 | 0.9237 | Difficult to visualize | Good | - | - | - | Optimal for complex text, but difficulties in generating visualizations with bounding boxes and challenges in reading documentation (mostly in Chinese) made us choose EasyOCR instead. |  
| **EasyOCR** | 35 | 0.8223 | Excellent | Good | 42.3 | 35.85 | 717 | Easy to use with a fairly high confidence rate. Its flexibility in supporting multiple languages makes EasyOCR the most suitable model for our project. |  
| **KerasOCR** | 35 | - | Excellent | Good | 42.00 | 34.85 | 697 | Highly effective for detection but difficult to configure and further develop. |  

#### 2. Ablation Study
Several improvements were implemented based on experiments and research conducted. An image sharpening enhancement was introduced for use cases where the user's photo quality was suboptimal. Sharpening images using an auto-kernel proved to be highly effective in increasing model accuracy, as shown by the increase in detected data from 14 to 26 entries.  Additionally, an **ImageRotate** feature was developed. Since another model, **YOLOv8** object detection, occasionally detected tilted images, these tilted images could not be processed by OCR. This issue was mitigated by implementing an auto-rotate feature.  Experiments were also conducted using binary images developed during the research phase. However, after testing various thresholding methods, no improvement in OCR performance was observed. As a result, the binary image approach was ultimately abandoned.  

| **Model** | **Method** | **Matrix Used** | **Number of Words Before Method** | **Number of Words After Method** | **Conclusion** |  
| --- | --- | --- | --- | --- | --- |  
| **EasyOCR** | Sharped Image | AutoKernel | 14 | 26 | The Sharped Image method proved to be effective in improving model accuracy, especially for low-resolution images. This method helps enhance pixel quality for better detection. |  
| **EasyOCR** | Image AutoRotate | Auto (90 degrees) | 0 | 21 | Since OCR cannot detect tilted text, the AutoRotate method is crucial for detecting text in unexpected user-submitted photos. |  

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
