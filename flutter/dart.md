---
description: Dart Language
icon: bullseye-arrow
---

# Dart

* _**Degisken Türleriyle Çalışmak:**_



```
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

```
// Some code
void main() {
  var sistemeGirmisMi = false;

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
```

* _**Listelerle Çalışmak:**_

```
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

*

