# Orfeo Toolbox ile Temel Uydu Görüntü İşleme

Bu repoda Monteverdi OTB yazılımı ile temel uydu görüntü işlemleri özetlenecektir. Bu repo Eskişehir Teknik Üniversitesi, Yer ve Uzay Bilimleri Enstitüsü, Uzaktan Algılama ve Coğrafi Bilgi Sistemleri Doktora Programı UCS635 Uydu Görüntü İşleme dersi kapsamında ve diğer eğitimlerimde ortam kullanmak için hazırlanmıştır. Rahatlıkla kullanabilirsiniz. İyi görüntü işlemeler :)

Derslerimde OTB ve SNAP gibi yazılımları seçmem bu yazılımların ücretsiz ve açık kaynaklı olmalarından kolay ulaşılabilir olmalarıdır. OTB yazılımı hakkında bilgi sahibi olmak için: https://www.orfeo-toolbox.org/packages/doc/otb-general-en.pdf

1. OTB yazılımını https://www.orfeo-toolbox.org/download/ adresinden indirerek klasörü zipten çıkarıyoruz.  
* OTB klasöründeki monteverdi.bat dosyası çift tıklanarak açıldığında OTB kullanıma hazır olur herhangi bir kurulum gerekmiyor. 

![image](https://user-images.githubusercontent.com/3392893/222256252-2aebd78a-b987-4c87-a476-41d777bbe4fc.png)

2. https://github.com/kalkan/SNAPileSentinel-2 tutorial'ındaki 6. aşamaya kadar olan kısım aynı olacak şekilde Sentinel-2 verimizi indirip zipten çıkarıyoruz. Bu çalışmada sadece B03-B04 ve B08 bantlarını kullanacağız. 

3. Bu 3 bandın .jp2 uzantılı dosyalarını sürükleyip Monteverdi ekranına atarak görüntüleri açıyoruz. Bu noktada istediğiniz bant ile çalışabilirsiniz. Sonraki aşamada bu 3 bandı birleştirip tek görüntü elde edeceğiz. 

![image](https://user-images.githubusercontent.com/3392893/222401832-5b0a978d-cfb6-4bd1-80a1-1fe94c4ac32f.png)

4. Bir sonraki aşamada sağ tarafta bululan "Color dynamics" tabından "No data" değerini "0" yaparak uygulayalım. Bu işlemden sonra görüntünün histogramı anlamlı olarak görüntülenebilir hale gelecektir. 

5. Görüntünün histogramını görüntülemek için sağ üstteki "Histogram" tabına basıyoruz. 

![image](https://user-images.githubusercontent.com/3392893/222403109-5bce456a-99a6-4873-8a6d-00af82559beb.png)

6. Şimdi tüm işlemlerin listelendiği toolbox'u açmak için View menüsünden OTB Application Browser'ı açalım. 

![image](https://user-images.githubusercontent.com/3392893/222412871-01a383da-38b8-488b-958d-f8d9cb22ebcd.png)

Tüm araçlar sağ üste eklenmiş olmalı. 

![image](https://user-images.githubusercontent.com/3392893/222413044-4b7b34a0-55b1-4f77-8ce2-2b0a4bfe0e98.png)

7. 

8. Farklı Bandları Birleştirme (ConcatenateImages) 	
9. Band Kombinasyonu	
10. Görüntü Kesme	
11. Contrast İyileştirme
12. PixelValue	
13. Kenar Belirleme	
14. Görüntü İstatistiklerini Belirleme	
15.	Quicklook Görüntü Üretme	
16.	NDVI ve NDWI
17.	Rescale	
18.	4/2 Band Oranlaması
19.	Zonal Statistics	
20.	Gauss Yumuşatma Operatörü	
21.	Görüntü Karşılaştırma	
22.	Bandlarını Ayırma	
23. Kmeans Sınıflandırması	
24.	Mean-shift Segmentasyonu
