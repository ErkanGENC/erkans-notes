---
description: Turner kullanımı (koşullu karşılaştırma)
icon: t
---

# Turner

````csharp
//some code
```csharp
while(true){
    System.Console.WriteLine("yaşinizi giriniz.");
int yas = Convert.ToInt32(Console.ReadLine());

// turner
var sonuc = (yas <=18) ? "Giriş yapamazsiniz." : "Giriş yapabilirsiniz.";


System.Console.WriteLine(sonuc);
System.Console.Write("Devam etmek istiyor musunuz? (E/H)");
string? devam = Console.ReadLine();
if(devam == "H"){
    break;
}

System.Console.WriteLine("\n");
}
```
````
