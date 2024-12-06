---
icon: w
description: >-
  Temel widget yapısının açıklanması.Stateless Widget ve Stateful Widget
  tanımlamaları, farkları ve kullanım alanları açıklanır.
---

# Widget Çeşitleri

## _Widget Nedir .?_&#x20;

&#x20; Widgetlar, kullanıcıya sunulan grafik öğelerin (butonlar, metin kutuları, resimler vb.) temel yapı taşlarıdır. Ancak, widgetların nasıl yönetildiği ve durumlarının nasıl takip edildiği, geliştirme sürecinde önemli bir fark yaratabilir.

&#x20;  İki yaygın widget tipi, **Stateless** (durumsuz) ve **Stateful**(durumlu) widgetlardır. Bu yazıda, stateless ve stateful widgetları karşılaştırarak, her birinin ne olduğunu, nasıl çalıştığını ve hangi senaryolarda tercih edilebileceğini inceleyeceğiz. &#x20;

&#x20;  Öncelikle Temel widget mimarisine bir göz atalım;&#x20;

<div data-full-width="false"><figure><img src="../.gitbook/assets/image (3).png" alt="Temel widget mimarisi"><figcaption><p>Widget Mimarisi</p></figcaption></figure></div>



## _Stateless (Durumsuz) Widget:_&#x20;

&#x20;  Kullanacağımız ekranda değişen herhangi bir yapımız yoksa bunu **Stateless Widget** kullanarak oluştururuz.(Yani Statik bir durum söz konusuysa)

&#x20;  Stateless widgetlar bir kez oluşturduktan sonra içeriği ve durumu güncellenemeyen widgetlar olarak çalışır.

&#x20;  Gerçek hayat örneği olarak değerlendirecek olursak, Sokakta gördüğümüz tabelalar veya afişler değişmeyen sabit bir durumu örneklendirmek için kullanılırlar sadece var olan bir durum için bilgilendirme geçerler. Zamanla değişim gösterme gibi bir durum söz konusu degildir.

&#x20;  Daha basit bir kod zincirinden oluşması sebebiyle hafızada fazla yer tutmaz ve basit bir syntax'a sahiptir. Örnek verecek olursam;&#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p><strong>Sta</strong><em><strong>teless Widget Örnek</strong></em></p></figcaption></figure>

&#x20;  Bu örnekte, HelloWorldWidget adında basit bir **Stateless Widget** tanımladık. Bu widget ekranda “Merhaba Dünya!” metnini görüntüler. Bu widget bir kez oluşturulduktan sonra **durumu güncellenmeyen** bir widgettır. Bu nedenle, stateless widget sadece **statik** içeriği göstermek için kullanılır.



## _Stateful (Durumsal) Widget:_ &#x20;

&#x20; _Kullanacağımız ekranda widgetlarda değişiklik olacaksa bunu **Stateful Widget** kullanarak oluştururuz._

&#x20;  Stateful Widget bir satranç oyununa benzer. Burada birçok taş hareket ettirilirken, sadece bir taşın hareket ettirilmesi bile durum değişikliği gerektirmek için yeterlidir. Çok farklı değişikliklere ihtiyacınız yoktur. Sadece bir değişiklik, stateless widget’ınızı stateful widget’a dönüştürmek için yeterlidir. Stateless widget’ların ise hiçbir değişikliği yoktur.

&#x20;  Şimdi bir kod parçacığında durumu gözlemleyelim;

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p><em><strong>Stateful Widget Örnek1</strong></em></p></figcaption></figure>

&#x20;  Bu widget bir sayacı temsil eder ve sayacın değerini attırmak için bir düğme içerir. **“createState”** ile bir sınıf oluşturulur ve bu sınıf state’i (durumu) yönetir. Ardından count yaratılır ve **setState** ile bu count her seferinde +1 artacak şekilde fonksiyona tanımlanır. &#x20;

&#x20;  Daha karmaşık bir örnekle durumu pekiştirmeye çalışalım;&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p><em><strong>Stateful Widget Örnek2</strong></em></p></figcaption></figure>

&#x20;  Bu yazdığımız kodda **“Metni güncelle”** yazan butona tıkladığımızda metinimiz **“Güncellenen Metin”** olarak değişecektir.

1. Kod, kendi değiştirilebilir durumunu yöneten **`MyStatefulWidget`** adında bir Flutter bileşeni tanımlar.
2. Bileşenin içinde, başlangıç metin değerini tutan **`text`** adında bir değişken bulunur.
3. **`build`** metodu, bileşenin kullanıcı arayüzünü oluşturmak için **`Scaffold`**, **`Center`**, **`Column`**, **`Text`**, **`SizedBox`** ve **`ElevatedButton`** bileşenlerini kullanır.
4. Düğme tıklandığında, **`text`** değişkeni güncellenir ve bileşenin yeniden oluşturulmasıyla yeni metin değeri görüntülenir.

&#x20;  Şimdi ise bu anlattıklarımızı basit ve özet şeklinde tekrarlayalım:

* Eğer bir **bileşenin içeriği değişmeyecekse** evet **‘Stateless’**… Stateless yapı olarak **çok daha basit ve daha az karmaşıktır.** Bu sebeplede **az bellek** kullanır ve **hızlı** çalışır.
* Eğer bir **bileşenin içeriği zaman içerisinde değişkenlik göstereceksede** **‘Stateful’** kullanmak en doğrusu olacaktır. Stateful Widget ise **dinamik** ve **etkileşimiyle** kullanıcının eylemine göre uyarlanabilir. **Daha karmaşık olan uygulamalar** için uygun olacaktır.

&#x20;  Bu anlattıklarımıza dikkat ederek projelerimizde uygun widget mimarileriyle devam etmemiz projenin estetikliğini arttıracaktır.&#x20;

&#x20;
