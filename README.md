Olympic Athletes — Spor Tahmin Modeli
120 yıllık olimpiyat verisini analiz ettim, sonra atletin fiziksel ve demografik özelliklerinden hangi sporu yaptığını tahmin eden bir model kurdum.
Dataset
Kaggle'dan aldım: 120 Years of Olympic History
271.116 satır, 15 sütun. 1896'dan 2016'ya kadar tüm olimpiyat katılımları.
Ne Yaptım
Önce hikaye odaklı bir EDA yaptım. Yıllar içinde atlet sayısı, cinsiyet eşitliğinin evrimi, ülke madalya tablosu, spor branşlarına göre fiziksel profiller gibi soruları görselleştirdim. Lollipop chart, stacked area gibi farklı grafik tiplerini denedim.
Multi-class classification için en popüler 10 sporu seçtim. Eksik değerleri spor bazında ortalama ile doldurdum (basketbolcunun NULL boyu = basketbolcuların ortalama boyu). Ülke kolonunda en popüler 20'yi tuttum, gerisini "Other" yaptım — yoksa 230 sütun açılacaktı.
Random Forest, XGBoost ve Logistic Regression denedim. Random Forest %89 accuracy ile öne çıktı. RandomizedSearchCV ile tuning yaptım ama yine işe yaramadı — bu üçüncü projem ve hâlâ default parametreler kazanıyor.
Önemli Bulgular
Bazı sporlar fiziksel profilden çok kolay tahmin edilebiliyor (recall %100), bazıları model tarafından sürekli karıştırılıyor — yakın profile sahip sporlarda model zorlanıyor.
Kullanılanlar
Python, Pandas, Scikit-learn, XGBoost, Matplotlib, Seaborn
