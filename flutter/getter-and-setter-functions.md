---
description: Getter ve setter fonksiyonlarının kullanımları ve özet anlatımlarını içerir.
icon: down-left-and-up-right-to-center
---

# Getter & Setter Functions

```dart
// Some code

class student {
  String firstName = "";
  String lastName = "";
  int grade = 0;
  String status = "";

  student(String firstName, String lastName, int grade) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.grade = grade;
    this.status = "geçti";
  }

  String get getFirstName {
    return "AD--> " + this.firstName;
  }

  void set setFirstName(String value) {
    this.firstName = value;
  }

  String get getStatus{
    String message = "";
    if (this.grade >= 50) {
      message = "geçti";
    } else if (this.grade >= 40) {
      message = "Bütünlemeye kaldi.";
    } else {
      message = "Kaldi";
    }
    return message;
  }
}

```



## _Getter Fonksiyonları_

* **Amaç**: Bir sınıfın özel alanlarının değerlerini dışarıya sunmak için kullanılır. Getter fonksiyonları, bir alanın değerini okumanıza olanak tanır.
* **Kullanım:** Getter fonksiyonları, bir alanın değerini döndürmek için kullanılır ve genellikle get anahtar kelimesi ile tanımlanır.

```dart
// Some code
String get getFirstName {
    return "AD--> " + this.firstName;
}
```

* **Örnek:** Yukarıdaki kodda getFirstName bir getter fonksiyonudur. Bu fonksiyon, firstName alanının değerini "AD--> " ön eki ile birlikte döndürür.

## _Setter Fonksiyonları_

* **Amaç:** Bir sınıfın özel alanlarının değerlerini değiştirmek için kullanılır. Setter fonksiyonları, bir alanın değerini ayarlamanıza olanak tanır.
* **Kullanım:** Setter fonksiyonları, bir alanın değerini ayarlamak için kullanılır ve genellikle set anahtar kelimesi ile tanımlanır.

```dart
// Some code
void set setFirstName(String value) {
    this.firstName = value;
}
```

* **Örnek**: Yukarıdaki kodda setFirstName bir setter fonksiyonudur. Bu fonksiyon, firstName alanının değerini dışarıdan gelen value ile değiştirir.

## _Neden Kullanılır?_&#x20;

&#x20;1\.  Veri Gizliliği: Sınıfın iç yapısını dışarıdan gizlemek ve sadece belirli bir arayüz üzerinden erişim sağlamak.

2. Veri Doğrulama: Setter fonksiyonları içinde, atanan değerin geçerli olup olmadığını kontrol edebiliriz.
3. Kapsülleme: Sınıfın iç yapısını değiştirmeden, dışarıya sunulan arayüzü sabit tutmak.

Getter ve setter'lar, nesne yönelimli programlamada kapsülleme ilkesinin önemli bir parçasıdır ve verilerin güvenli bir şekilde yönetilmesine yardımcı olur.
