---
description: Aggregated Fonksiyonlar nelerdir? Kullanımları nasıldır ?
icon: f
---

# Aggregate Functions

SQL'de toplu (aggregate) fonksiyonlar, bir grup veri üzerinde hesaplamalar yaparak tek bir sonuç döndüren fonksiyonlardır. İşte yaygın kullanılan SQL toplu fonksiyonları ve kullanımları:

_**1-COUNT():**_

* Özellikler: Belirtilen sütundaki satır sayısını döndürür.
* **Kullanım:**    &#x20;

```sql
// Some code
SELECT COUNT(*) FROM tablo_adi
```

\- Örnek: Bir tablodaki toplam satır sayısını bulmak için kullanılır.

_**2-SUM():**_

* Özellikler: Belirtilen sütundaki tüm değerlerin toplamını döndürür.
* Kullanım:   &#x20;

```sql
// Some code
 SELECT SUM(sutun_adi) FROM tablo_adi
```

\- Örnek: Satış miktarlarının toplamını hesaplamak için kullanılır.

_**3-AVG():**_

* Özellikler: Belirtilen sütundaki değerlerin ortalamasını döndürür.
* Kullanım:    &#x20;

```sql
// Some code
SELECT AVG(sutun_adi) FROM tablo_adi
```

\- Örnek: Öğrencilerin not ortalamasını bulmak için kullanılır.

_**4-MIN():**_

* Özellikler: Belirtilen sütundaki en küçük değeri döndürür.
* **Kullanım:**

```sql
// Some code
 SELECT MIN(sutun_adi) FROM tablo_adi
```

\- Örnek: Ürünler arasındaki en düşük fiyatı bulmak için kullanılır.

_**5-MAX():**_

* Özellikler: Belirtilen sütundaki en büyük değeri döndürür.
* Kullanım:    &#x20;

```sql
// Some code
SELECT MAX(sutun_adi) FROM tablo_adi
```

\- Örnek: Çalışanlar arasındaki en yüksek maaşı bulmak için kullanılır.

Bu fonksiyonlar genellikle GROUP BY ifadesi ile birlikte kullanılarak, belirli gruplar üzerinde toplu hesaplamalar yapılabilir. Örneğin, her departmandaki çalışan sayısını bulmak için:

```sql
// Some code
SELECT departman_adi, COUNT(*) FROM calisanlar GROUP BY departman_adi
```

Bu sorgu, her departman için çalışan sayısını döndürecektir. Toplu fonksiyonlar, veritabanı sorgularında veri analizi ve raporlama için oldukça kullanışlıdır.



