---
description: Tek ve çok boyutlu dizi
icon: rocket
---

# Application 1

````csharp
// Some code

// not ortalaması programı

string[] isimler = {"ali", "veli", "selami"};

int[,] notlar = new int[3,3];
// ali
notlar[0,0]= 10;
notlar[0,1]= 20;
notlar[0,2]= 30;
System.Console.WriteLine("ali notlari: " + notlar[0,0] + " " + notlar[0,1] + " " + notlar[0,2]);
// ortalaması
var toplam1 = notlar[0,0] + notlar[0,1] + notlar[0,2];
// veli
notlar[1,0]=40;
notlar[1,1]=50;
notlar[1,2]=60;
System.Console.WriteLine("veli notlari: " + notlar[1,0] + " " + notlar[1,1] + " " + notlar[1,2]);
// ortalaması
var toplam2 =notlar[1,0] + notlar[1,1] + notlar[1,2];
// selami



notlar[2,0]=70;
notlar[2,1]=80;
notlar[2,2]=90;
System.Console.WriteLine("selami notlari: " + notlar[2,0] + " " + notlar[2,1] + " " + notlar[2,2]);
// ortalaması
var toplam3 = notlar[2,0] + notlar[2,1] + notlar[2,2];




System.Console.WriteLine("3 kisinin notlari ortalamasi: " +(toplam1+toplam2+toplam3)/3);










```
````

