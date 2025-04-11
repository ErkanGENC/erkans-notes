---
description: >-
  (Dart Language), Dart dilinde bilmemiz gereken temel kuralların bilgisi, diğer
  dillerle olan ilişkisi hakkında bilgi verir.
icon: bullseye-arrow
---

# Dart

* _**Degisken Türleriyle Çalışmak:**_&#x20;



```dart
// Some code

void main() {
  
  //camelCase 
  //PascalCase

  String mesaj = "Merhaba Engin";
  int dogumYili = 1985;
  double oran = 1.15;
  bool loginMi = false;


  print(mesaj);
  print("Doğum yılı : "+dogumYili.toString());
  print("Oran : " + oran.toString());


}
```



* _**Şart bloklarıyla çalışmak:**_

<pre class="language-dart"><code class="lang-dart">// Some code
<strong>void main() {
</strong>  var sistemeGirmisMi = false;

  if(sistemeGirmisMi == true){
    print("anasayfaya gidildi");
  }else{
    print("login sayfasına gidildi");
  }
  
  
  int puan = 15;
  if(puan>=50){
     print("Geçti");
  }else if(puan>=40){
    print("Bütünleme");
  }else{
    print("Kaldı");
  }


  String not ="A";
  switch(not){
    case "A": {print("Süper");}
    break;
    case "B": {print("İyi");}
    break;
    case "C": {print("İdare eder");}
    break;
    case "D": {print("Kötü");}
    break;
    default: {print("Bilinmiyor");}
    break;

  }

}
</code></pre>

* _**Listelerle Çalışmak:**_

```dart
// Some code

void main() {

   //Fixed length list
   var urunler = new List(5);
   urunler[0] = "Laptop";
   urunler[1] = "Mouse";
   urunler[2]="Keyboard";
   urunler[3] ="Monitor";
   urunler[4] ="Mic";
  
   //urunler[5]="Speaker";

   print(urunler);
   print(urunler[2]);
   //print(urunler[5]);

   //Growable List
   var sehirler = ["Ankara","İstanbul","İzmir"];
   print(sehirler);
   sehirler.add("Diyarbakır");
   print(sehirler);

   print(sehirler.where((s)=>s.contains("a")));

   print(sehirler.first);

}
```

* _**Döngülerle Çalışmak:**_

```dart
// Some code

void main(){
  for(var i = 1;i<=10;i=i+2){
    print(i);
  }

  var products = ["Laptop","Mouse","Keyboard"];

  for(var i=0;i<products.length;i++){
      print(products[i]);
  }

  for(var product in products){
      print(product);
  }

  int sayi = 1;
  while(sayi<=10){
    print(sayi);
    sayi++;
  }

  var sayi2 = 10;
  do{
    print("Sayı 2 = " + sayi2.toString());
    sayi2++;
  }while(sayi2>1000);
}
```

* _**Map yapısıyla çalışmak:**_

```dart
// Some code

void main(){
 var dictionary1 = new Map();
 dictionary1["book"]="kitap";
 dictionary1["little"]="küçük";


 var dictionary2 = {"kitap":"book","küçük":"little"} ;
 dictionary2["büyük"]="big";

 print(dictionary1);
 print(dictionary2);


 dictionary1.remove("book");
 print(dictionary1);

 for(var key in dictionary2.keys){
      print(key + " : " + dictionary2[key]);
 }

 for(var value in dictionary2.values){
      print(value);
 }

 print(dictionary2.containsKey("kitap"));

 dictionary2.forEach((k,v)=>{
  print(k + " : " + v)
 });
}
```

* _**Fonksiyonlarla çalışmak:**_

```dart
// Some code

void main(){
  selamVer2("Engin");
  selamVer2("Engin");
  selamVer2("Ayşe");
  selamVer2("Engin");
  selamVer2("Engin");

  var hesapSonucu = hesapla(100000,15);
  print(hesapSonucu);

  test1(1,2);
  test2(sayi2:1,sayi3:2,sayi1:3);
}

void selamVer(){
  print("Selam");

}

void selamVer2(String kullanici){
  print("Selam " + kullanici);
}

double hesapla(double krediTutari, double yuzde){
   var sonuc =  krediTutari * yuzde /100;
   return sonuc;
}

void test1(int sayi1, [int sayi2, int sayi3]){
  print(sayi1);
  print(sayi2);
  print(sayi3);
}

void test2({int sayi1, int sayi2, int sayi3}){
  print(sayi1);
  print(sayi2);
  print(sayi3);
}

```

