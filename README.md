# Category_Prediction_With_SVM
SVM(Support Vector Machine) Modeli İle Kategori Tahmini

## İstanbul Büyükşehir Belediyesi Ve Ecodation İş Birliğiyle Yapılan Veri Bilimi Bootcamp Bitirme Projesi.
Bu projeyi Başakşehir de bulunan İBB Veri Laboratuvarında sundum ve bu proje ile sertifika almaya hak kazandım.

## Proje Hakkında:
Flo firmasının müşterilerinin geçmiş satın alma verilerine göre hangi kategoride ürün alacaklarını tahmin eden bir model kurdum.
Bu model sonucunda firma hangi müşterinin hangi kategorilerde ürün alacağını önceden %70,%80 doğruluk oranında tahmin edebilir.
Ve bu tahminler sonucunda pazarlama politikasında değişikliğe gidebilir ve bunun gibi aksiyonlar alınabilir.

## Veri Setimizi Tanıyalım
* Bu veri setinde 19,945 adet müşterinin alışveriş geçmişleri 12 veri seti değişkeni ile tanımlanmıştır.
* 
![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/shape.png)
### Veri Setimizdeki Değişkenlerin Veri Tipleri
* Bu veriden yola çıkarak date olarak adlandırılan, tarih içeren veriler object olarak yer alıyor. Bu verilerin tipini Datetime olarak değiştirmeliyiz.

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/typeOfData.png)
### Veri setinde bulunan kategorilerin omnichannel olarak satın alınma adetleri ve parasal değerleri

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/bigGraph.png)
### Aylara Göre Verilen Sipariş Adetleri

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/months.png)
### Aylara göre siparişlere ödenen tutar

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/numberOfOrder.png)
### Online Kanal Siparişleri

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/channelGraph.png)
### Ürün Kategorileri

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/categoryGraph.png)
## Veri Hazırlığı

* Veri setinde, tarih verileri object tipinde verilmiştir. Hazırlık aşamasında öncelikle bu düzenlenmiştir.

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/tipDonusum.png)
* Modelin ‘Accuracy’ değerinin yüksek olması için yeni değişkenler eklenmelidir. Bunun için de analiz yapılan günün tarihi gereklidir. Analizin gerçekçi sonuç verebilmesi için veri setindeki son alışveriş tarihine bakılmış ve bu tarihe yakın tarih seçilmiştir.

* Veri setinin daha doğru sonuçlar vermesi için alışveriş tarihlerinden müşterilere özel yeni değişkenler oluşturuldu. Örneğin ilk alışverişinden analiz yapılan zamana ne kadar zaman geçtiğini ifade eden bu veriye CLTV analizinde müşterinin yaşı denir ve "T" olarak ifade edilir. Bu ve buna benzer bilgiler de veri setine eklendi.

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/cltv.png)
* Veri setindeki müşterilerin satın aldığı ürünlerin kategorisi düzensiz, toplu ve object tipinde verilmekteydi.
Bu şekilde bir tahmin yapıldığında, accuracy değerinin çok düşük düzeyde olduğu görüldü.

*Bu sonuçtan yola çıkarak her bir kategori için ayrı feature oluşturulup boolean değerlerle ifade edildi.
Bu yolla accuracy oranı oldukça yükseldi.

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/accuracy.png)
## SVM(Support Vector Machine) İle Tahminleme Yapılması
* Kategori değişkenleri, tabloda görüldüğü gibi tanımlandı ve her biri için model birer kez, toplam da 5 kez çalıştırıldı.
Her bir tahminde bağımsız değişken olarak diğer 4 kategori de dahil edildi. Böylece modelin doğruluk oranını daha da yükselmiş oldu. 
Veri seti hazırlığının son aşaması olarak da kullanılmayacak değişkenler veri setinden silindi. 

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/categoryBool.png)
* Modele örnek olarak öncelikle ERKEK kategorisinde tahmin yapıldı ve 0.72 oranında doğru sonuç elde edildi. Daha sonra tekrara düşmemek adına fonksiyonlaştırılarak diğer kategoriler için de tahminler yapıldı.

## Kategorilerin Confusion Matrixleri
![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/erkekConf.png)

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/kadınConf.png)

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/aktıfsporConf.png)

![](https://github.com/HuseyinEfkanAlp/Category_Prediction_With_SVM/blob/main/Images/aktıfcocukConf.png)


