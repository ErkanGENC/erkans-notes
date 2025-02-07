---
description: Where şartı ile sorgu nasıl filtrelenir ?
icon: server
---

# Temel SQL komutları-(WHERE)

SQL'de, veritabanı sorgularında koşullar belirlemek için çeşitli operatörler kullanılır. İşte =, >, <, <>, LIKE ve BETWEEN operatörlerinin kullanımı ve ne işe yaradıkları:

#### = Operatörü

Eşitlik kontrolü yapmak için kullanılır. Bir sütunun belirli bir değere eşit olup olmadığını kontrol eder.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi = deger;
```

#### > Operatörü

Büyüklük kontrolü yapmak için kullanılır. Bir sütunun belirli bir değerden büyük olup olmadığını kontrol eder.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi > deger;
```

#### < Operatörü

Küçüklük kontrolü yapmak için kullanılır. Bir sütunun belirli bir değerden küçük olup olmadığını kontrol eder.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi < deger;
```

#### <> Operatörü

Eşit olmama kontrolü yapmak için kullanılır. Bir sütunun belirli bir değere eşit olmadığını kontrol eder. Bazı SQL dillerinde != de kullanılabilir.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi <> deger;
```

#### LIKE Operatörü

Desen eşleştirme yapmak için kullanılır. Genellikle joker karakterlerle (% ve \_) birlikte kullanılır.

* %: Sıfır veya daha fazla karakteri temsil eder.
* \_: Tek bir karakteri temsil eder.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi LIKE 'deger%';
```

#### BETWEEN Operatörü

Bir aralık içinde olup olmadığını kontrol etmek için kullanılır. Genellikle sayısal veya tarihsel aralıklar için kullanılır.

```sql
// Some code
SELECT * FROM tablo_adi WHERE kolon_adi BETWEEN deger1 AND deger2;
```

#### Özet

* \=: Eşitlik kontrolü.
* \>: Büyüklük kontrolü.
* <: Küçüklük kontrolü.
* <>: Eşit olmama kontrolü.
* LIKE: Desen eşleştirme.
* BETWEEN: Aralık kontrolü.

Bu operatörler, SQL sorgularında koşullar belirlemek ve verileri filtrelemek için kullanılır. Her biri, farklı türde karşılaştırmalar yapmanıza olanak tanır.
