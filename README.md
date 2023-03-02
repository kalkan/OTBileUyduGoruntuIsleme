# Orfeo Toolbox ile Temel Uydu Görüntü İşleme

Bu repoda Monteverdi OTB yazılımı ile temel uydu görüntü işlemleri özetlenecektir. Bu repo Eskişehir Teknik Üniversitesi, Yer ve Uzay Bilimleri Enstitüsü, Uzaktan Algılama ve Coğrafi Bilgi Sistemleri Doktora Programı UCS635 Uydu Görüntü İşleme dersi kapsamında ve diğer eğitimlerimde ortam kullanmak için hazırlanmıştır. Rahatlıkla kullanabilirsiniz. İyi görüntü işlemeler :)

Derslerimde OTB ve SNAP gibi yazılımları seçmem bu yazılımların ücretsiz ve açık kaynaklı olmalarından kolay ulaşılabilir olmalarıdır. OTB yazılımı hakkında bilgi sahibi olmak için: https://www.orfeo-toolbox.org/packages/doc/otb-general-en.pdf

> 1. OTB yazılımını https://www.orfeo-toolbox.org/download/ adresinden indirerek klasörü zipten çıkarıyoruz.  
* OTB klasöründeki monteverdi.bat dosyası çift tıklanarak açıldığında OTB kullanıma hazır olur herhangi bir kurulum gerekmiyor. 

![image](https://user-images.githubusercontent.com/3392893/222256252-2aebd78a-b987-4c87-a476-41d777bbe4fc.png)

> 2. https://github.com/kalkan/SNAPileSentinel-2 tutorial'ındaki 6. aşamaya kadar olan kısım aynı olacak şekilde Sentinel-2 verimizi indirip zipten çıkarıyoruz. Bu çalışmada sadece B03-B04 ve B08 bantlarını kullanacağız. 

> 3. Bu 3 bandın .jp2 uzantılı dosyalarını sürükleyip Monteverdi ekranına atarak görüntüleri açıyoruz. Bu noktada istediğiniz bant ile çalışabilirsiniz. Sonraki aşamada bu 3 bandı birleştirip tek görüntü elde edeceğiz. 

![image](https://user-images.githubusercontent.com/3392893/222401832-5b0a978d-cfb6-4bd1-80a1-1fe94c4ac32f.png)

> 4. Bir sonraki aşamada sağ tarafta bululan "Color dynamics" tabından "No data" değerini "0" yaparak uygulayalım. Bu işlemden sonra görüntünün histogramı anlamlı olarak görüntülenebilir hale gelecektir. 

> 5. Görüntünün histogramını görüntülemek için sağ üstteki "Histogram" tabına basıyoruz. 

![image](https://user-images.githubusercontent.com/3392893/222403109-5bce456a-99a6-4873-8a6d-00af82559beb.png)

> 6. Şimdi tüm işlemlerin listelendiği toolbox'u açmak için View menüsünden OTB Application Browser'ı açalım. 

![image](https://user-images.githubusercontent.com/3392893/222412871-01a383da-38b8-488b-958d-f8d9cb22ebcd.png)

Tüm araçlar sağ üste eklenmiş olmalı. 

![image](https://user-images.githubusercontent.com/3392893/222413044-4b7b34a0-55b1-4f77-8ce2-2b0a4bfe0e98.png)

> 7. İlk işlemimiz diğer uygulamlarda "Layer Stack" olarakda bulabileceğimiz "ConcatenateImages" olacak. Arama bölümünden bu seçeneği seçerek devam ediyoruz işleme. 

* ++ butonu ile ilgili 3 bandı ekleyerek, Output alanına çıkacak görüntünün adını .tif uzantılı olarak oluştururak işlemi çalıştırıyoruz. 

![image](https://user-images.githubusercontent.com/3392893/222414277-a130f848-b44b-404b-85ce-9bac012bda41.png)

Görüntümüz yüklendi fakat bantların kombinasyonu istediğimiz gibi olmadı. False colour renklendirmek istiyoruz. Bir sonraki işlemde band kombinasyonlarını değiştireceğiz. 

![image](https://user-images.githubusercontent.com/3392893/222415359-66333707-8475-42b8-a77a-f2e9f5c9681d.png)

> 8. Band kombinasyonunu NIR-Red-Green olacak şekilde,  Color setup menüsünden değiştirdikten sonra Color dynamics ekranından yine No data değerini 0 yaparak görselleştirelim.

![image](https://user-images.githubusercontent.com/3392893/222419617-f12635ba-0313-4074-b02d-8ab56f23ad17.png)

Görüntümüz istediğimiz formatta görüntülenmeye hazır. 

![image](https://user-images.githubusercontent.com/3392893/222419676-28d03133-9550-4f9f-b12b-1445c9f74b21.png)

> 9. Görüntü kesme için daha önce benim QGIS'de çizdiğim subset.kml dosyası ile çıktı dosyası için bir isim vererek "ExtractROI" komutu ile görüntüyü kesiyoruz. Extraction Mode ekranından "Fit" seçebiliriz.

![image](https://user-images.githubusercontent.com/3392893/222426289-8c7fca54-8831-4bf2-af18-17dd0304e5e8.png)

Kesilen görüntü ile işlemlere devam edeceğiz.

![image](https://user-images.githubusercontent.com/3392893/222426953-95dc0785-8efb-450d-b67d-01be854e657e.png)

> 10. Kontrast İyileştirme işlemi için, "ContrastEnhancement" komutu ile Global parametreleri kullanarak görüntüye kontrast düzeltmeesi uygulayalım. Çıktı görüntüsünü subsetiyi.tif olarak adlandırabiliriz. 

![image](https://user-images.githubusercontent.com/3392893/222427798-482cbcf9-4836-4873-92fb-9f8dc975ece0.png)

> 11. Kenar belirleme işlemi için "EdgeExtraction" komutu ile kenar.tif dosyası oluşacak şekilde Sobel yöntemi ile kenar belirleyelim.

![image](https://user-images.githubusercontent.com/3392893/222428436-5f9dc761-d8c0-409c-bef6-2cd2628721fd.png)

![image](https://user-images.githubusercontent.com/3392893/222428495-eca8480d-e40f-4386-b798-f3e260d1b058.png)

> 12. Görüntü istatistiklerini belirlemek için, "ComputeImageStatistics" komutu ile Mean, Min, Max ve Stdev değerlerini hesaplatalım.

![image](https://user-images.githubusercontent.com/3392893/222430066-b58e6146-46bf-4144-82b5-5c8915ee9a37.png)

> 13. NDVI değerini hesaplamak için bu uygulamada bant aritmetiği yerine Monteverdi'de ön tanımlı radyometrik indeksleri kullanmayı göstereceğiz. Bu amaçla "RadiometricIndices" komutu ile NIR ve RED bantların konumu gösterildikten sonra subset.tif görüntümüzden NDVI indeksini hesaplayalım. ndvi.tif dosyasına kaydedelim. 

![image](https://user-images.githubusercontent.com/3392893/222432049-cee6f11a-9c60-495c-93cb-e4bbc4ec19b6.png)

> 14. Görüntüdeki piksel değerlerini 0-1 arasına normalize etmek için Rescale komutu ile scaled.tif görüntüsünü oluşturalım.

![image](https://user-images.githubusercontent.com/3392893/222432582-d8e59143-c7ee-4997-9738-6b75e5129b5a.png)

> 15. Zonal Statistics işlem adımında size verilen pivot.kml dosyası sınırları için bölgesel istatistikleri hesaplamak için, "ZonalStatistics" komutunu çalıştıralım.

![image](https://user-images.githubusercontent.com/3392893/222440099-16d3e97e-2bf9-4d94-bf4a-63dc442e5e8a.png)

![image](https://user-images.githubusercontent.com/3392893/222439850-75d51c23-6133-403f-bef9-fb4cc57ceed5.png)

> 16. K-means sınıflandırması için "KmeanSClassification" komutu ile 2 sınıfta kmeans.tif dosyasını oluşturalım.

![image](https://user-images.githubusercontent.com/3392893/222441325-e611aaf9-e818-4d51-bc50-5977e5e79dd3.png)

Eğitimsiz/Kontrolsüz bir kümeleme algoritması olan kmeans ile görüntünün bitki örtülü alanlar ve bitki örtüsüz alanlar olarak nasıl 2 ayrı sınıfa ayrıldığını görebilirsiniz. 

![image](https://user-images.githubusercontent.com/3392893/222441902-9e680188-2116-4fe4-b153-7b8cfa875298.png)

> 17. Son işlem adımı olarak Mean-shift Segmentasyonu ile görüntü süper piksellere veya bölütlere ayıralım. Bunun için "Segmentation" komutunu çağırarak, kmeans.tif görüntümüzden bolut.shp çıktısı üretecek şekilde öntanımlı ayarlar ile Mean-shift yöntemi ile görüntü süper piksellere ayıralım. 

![image](https://user-images.githubusercontent.com/3392893/222442837-938b9bc3-9c0e-4ee2-8e4c-9021a99fee43.png)

Oluşan vektör dosyasını QGIS ile açtığımızda aşağıdaki vektör alanları görebilirsiniz. 

![image](https://user-images.githubusercontent.com/3392893/222443720-8130cd09-1bd5-4168-963f-522fe14d1e19.png)

