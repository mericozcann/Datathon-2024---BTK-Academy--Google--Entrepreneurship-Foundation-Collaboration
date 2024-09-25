# Datathon 2024: Evaluation Score Prediction
## Competition Link: https://www.kaggle.com/competitions/datathon-2024/overview
## Project Link: https://www.kaggle.com/code/merizcan/datathon-2024-evaluation-score-prediction/notebook
## Project Overview
This project is part of Datathon 2024, focusing on predicting the "Degerlendirme Puani" (Evaluation Score) for a set of applicants. The provided dataset includes anonymized information on applicants from the Girişimcilik Vakfı, ranging from personal background to educational and socio-economic data.
The task involves building predictive models that estimate the missing evaluation scores for a group of 11,049 applicants from the year 2023. The evaluation metric for this competition is Root Mean Square Error (RMSE).
### Files in the Project
•	train.csv: Contains the data from previous applicants, including their Evaluation Scores.
•	test_x.csv: Holds the anonymized data for 11,049 applicants from 2023, missing only the Evaluation Score.
•	sample_submission.csv: A template for submission, with two columns: id and Degerlendirme Puani.
•	submission.csv: Your final submission file containing predicted Evaluation Scores for the test set.
## Objective
The objective is to predict the missing Degerlendirme Puani for the test set and submit the results in a format similar to the sample_submission.csv file, containing two columns: id and Degerlendirme Puani.
## Approach
### Data Preprocessing
1.	Handling Missing Values:
o	For numerical columns, missing values were filled using the mean.
o	For categorical columns, missing values were filled using the most frequent strategy.
2.	Categorical Encoding:
o	Two different approaches were used: Label Encoding for the first model and Target Encoding for the second, to handle categorical features effectively.
3.	Outlier Detection and Removal:
o	The Interquartile Range (IQR) method was used to identify and remove outliers in numerical columns.
Model Training
Two machine learning models were trained, optimized, and combined for an ensemble approach:
1.	RandomForestRegressor:
o	Hyperparameter tuning was done using GridSearchCV to find the best model configuration.
o	Recursive Feature Elimination (RFE) was applied to select the most important features.
2.	XGBoost:
o	Similarly, hyperparameter tuning was done with GridSearchCV to identify the best set of parameters.
o	A stratified k-fold cross-validation approach was used to ensure robustness.
Ensemble Model
•	The final predictions were made using an ensemble of both RandomForestRegressor and XGBoost, where the predictions from both models were averaged to improve accuracy.
### Evaluation
The model's performance was evaluated using RMSE on the validation set. RMSE provides a measure of the error between predicted and actual evaluation scores.
Exploratory Data Analysis (EDA)
•	Visualizations were made to understand the distribution of target variables and feature relationships.
•	A heatmap was generated to analyze the correlation between features, providing insights into data relationships.
Results and Submission
•	The predicted scores were saved in submission_ensemble.csv, following the format provided in sample_submission.csv.
## Conclusion
This project demonstrated the power of using ensemble models with careful preprocessing and feature selection to achieve better predictions for the Evaluation Score. The final ensemble model combined Random Forest and XGBoost for optimal performance on the test set.


# Datathon 2024: Değerlendirme Puanı Tahmini
## Yarışma Bağlantısı: https://www.kaggle.com/competitions/datathon-2024/overview
## Proje Linki: https://www.kaggle.com/code/merizcan/datathon-2024-evaluation-score-prediction/notebook
## Proje Genel Bakışı
Bu proje, bir dizi başvuru sahibi için "Değerlendirme Puanı"nı (Evaluation Score) tahmin etmeye odaklanan Datathon 2024'ün bir parçasıdır. Sağlanan veri seti, Girişimcilik Vakfı'ndan başvuru sahiplerine ait kişisel geçmişten eğitim ve sosyo-ekonomik verilere kadar anonimleştirilmiş bilgiler içerir.
Görev, 2023 yılından itibaren 11.049 başvuru sahibinden oluşan bir grup için eksik değerlendirme puanlarını tahmin eden tahmini modeller oluşturmayı içerir. Bu yarışma için değerlendirme metriği Root Mean Square Error'dur (RMSE).
### Projedeki Dosyalar
• train.csv: Değerlendirme Puanları dahil olmak üzere önceki başvuru sahiplerinin verilerini içerir. • test_x.csv: 2023'ten itibaren 11.049 başvuranın anonimleştirilmiş verilerini tutar, yalnızca Değerlendirme Puanı eksiktir.
• sample_submission.csv: İki sütunlu bir gönderim şablonu: id ve Değerlendirme Puanı.
• submission.csv: Test seti için tahmini Değerlendirme Puanlarını içeren son gönderim dosyanız.
## Amaç
Amaç, test seti için eksik Değerlendirme Puanını tahmin etmek ve sonuçları iki sütun içeren sample_submission.csv dosyasına benzer bir biçimde göndermektir: id ve Değerlendirme Puanı.
## Yaklaşım
### Veri Ön İşleme
1. Eksik Değerlerin İşlenmesi:
o Sayısal sütunlar için, eksik değerler ortalama kullanılarak dolduruldu.
o Kategorik sütunlar için, eksik değerler en sık kullanılan strateji kullanılarak dolduruldu.
2. Kategorik Kodlama:
o Kategorik özellikleri etkili bir şekilde işlemek için iki farklı yaklaşım kullanıldı: İlk model için Etiket Kodlaması ve ikinci model için Hedef Kodlaması. 3. Aykırı Değer Algılama ve Kaldırma:
o Sayısal sütunlardaki aykırı değerleri belirlemek ve kaldırmak için Interquartile Range (IQR) yöntemi kullanıldı.
Model Eğitimi
İki makine öğrenimi modeli eğitildi, optimize edildi ve bir topluluk yaklaşımı için birleştirildi:
1. RandomForestRegressor:
o En iyi model yapılandırmasını bulmak için GridSearchCV kullanılarak hiperparametre ayarı yapıldı.
o En önemli özellikleri seçmek için Özyinelemeli Özellik Eleme (RFE) uygulandı.
2. XGBoost:
o Benzer şekilde, en iyi parametre kümesini belirlemek için GridSearchCV ile hiperparametre ayarı yapıldı.
o Sağlamlığı sağlamak için katmanlı k katlı çapraz doğrulama yaklaşımı kullanıldı.
Toplu Model
• Son tahminler, doğruluğu artırmak için her iki modelden gelen tahminlerin ortalamasının alındığı RandomForestRegressor ve XGBoost'un bir topluluğu kullanılarak yapıldı.
### Değerlendirme
Modelin performansı, doğrulama kümesinde RMSE kullanılarak değerlendirildi. RMSE, tahmin edilen ve gerçek değerlendirme puanları arasındaki hatanın bir ölçüsünü sağlar.
Keşifsel Veri Analizi (EDA)
• Hedef değişkenlerin ve özellik ilişkilerinin dağılımını anlamak için görselleştirmeler yapıldı.
• Özellikler arasındaki korelasyonu analiz etmek için bir ısı haritası oluşturuldu ve veri ilişkileri hakkında içgörüler sağlandı.
Sonuçlar ve Gönderim
• Tahmin edilen puanlar, sample_submission.csv'de sağlanan formatı izleyerek submission_ensemble.csv'ye kaydedildi.
## Sonuç
Bu proje, Değerlendirme Puanı için daha iyi tahminler elde etmek amacıyla dikkatli ön işleme ve özellik seçimiyle topluluk modellerinin kullanılmasının gücünü gösterdi. Son topluluk modeli, test setinde optimum performans için Random Forest ve XGBoost'u birleştirdi.
