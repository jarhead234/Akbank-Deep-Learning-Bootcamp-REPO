## GİRİŞ

Bu repo, Global AI Hub bootcamp sürecinde oluşturduğum araç tespiti (object detection) çalışmasının şablonuna uygun halidir. Projemde araçları tespit etmek için YOLO tabanlı bir yaklaşımı benimsedim. Ham etiketleri (xmin, ymin, xmax, ymax) YOLO formatına (x_center, y_center, w, h) dönüştürüp veri kümesini eğitim/doğrulama olarak ayırdım. Ayrıca, veri kalitesini görmek için görselleştirmeler ve temel istatistikler oluşturdum.

Bu README dosyasında projenin kısa özetini bulabilirsiniz. Teknik detayların tamamı, notebook dosyalarındaki markdown hücrelerinde yer alır. Yalnızca kod çıktılarından oluşan bir notebook yerine, adım adım açıklamalar da eklenmiştir.

- Ana not defteri: `car2_kaggle.ipynb`
- Yardımcı betik: `car2.py`
- Konfigürasyon: `yolo_config.yaml`
- Görseller: `training_images/`, `testing_images/`
- YOLO veri seti: `yolo_dataset/{images,labels}/{train,val}`

## METRİKLER

Çalışmanın sonuçlarını değerlendirirken şu metrikleri dikkate alıyorum:

- mAP@0.5 ve mAP@0.5:0.95: Farklı IoU eşiklerinde ortalama doğruluk
- Precision ve Recall: Yanlış pozitif/negatif dengesini yorumlamak için
- İnferans süresi/FPS: Uygulamanın gerçek-zamanlı ihtiyacına göre performans değerlendirmesi

Bu projede ana odak veri hazırlama ve keşiftir. Eğitim metrikleri; kullanılan YOLO sürümü (ör. Ultralytics) ve eğitim komutlarına bağlıdır. Elde ettiğim sonuçları, notebook içinde yorumlayarak neden-sonuç ilişkisi kurmaya özellikle özen gösterdim.

## EKLER

Proje kapsamında temel akışa ek olarak aşağıdaki bileşenler yer alır:

- `yolo_config.yaml`: Eğitim için örnek konfigürasyon dosyası
- `car2_kaggle.ipynb`: Keşif analizi, görselleştirmeler, veri dönüşümü
- `yolo_dataset/`: Eğitime hazır görsel ve etiket klasör yapısı (train/val)
- `visualize_prediction_results`: Tahmin çıktılarını hızlıca gözden geçirmek için fonksiyon (notebook içinde)

Eğer ek çalışmalar yaparsam (deployment, end-to-end GPU pipeline, UI), bu bölümde ayrı başlıklar halinde anlatacağım. Örneğin, `UI/` klasörü altında Streamlit ile basit bir arayüz hazırlanabilir ve modelin çıktıları canlı olarak gösterilebilir.

## SONUÇ VE GELECEK ÇALIŞMALAR

Bu çalışmada, veriyi YOLO formatına dönüştürerek eğitime hazır hale getirdim ve keşif analizi ile veri yapısını doğruladım. Gelecekte şunları eklemeyi planlıyorum:

- Veri artırma (augmentation) stratejileri (mosaic, hsv gain, flip vb.)
- Farklı YOLO mimarileri ve ön-eğitimli ağırlıkların denenmesi
- Hiperparametre arayışı (batch size, img size, learning rate, epoch sayısı)
- K-fold cross validation ile daha sağlam değerlendirme
- Basit bir UI (Streamlit) ile interaktif demo

Bu repo bootcampten sonra da gelişmeye açıktır. Yeni veri kaynakları, farklı problem tanımları veya ek modelleme teknikleri ile proje sürekli güncellenebilir.

## LİNKLER

- Kaggle Notebook: [buraya Kaggle not defteri linkinizi ekleyin]
- Kaggle Yarışma/Veri Seti: [ilgili yarışma veya veri seti linkini ekleyin]
- Proje Deposu: Bu repo (Public)


