---
description: Group by terimi SQL 'de neyi ifade eder. Kullanımı nasıldır ?
icon: g
---

# Group By

**GROUP BY ifadesi**, SQL'de verileri belirli bir veya birden fazla sütuna göre gruplamak için kullanılır. Bu ifade, genellikle toplu (aggregate) fonksiyonlarla birlikte kullanılarak, her grup için özet bilgiler elde edilmesini sağlar. GROUP BY, veritabanı sorgularında veri analizi ve raporlama için oldukça önemlidir.

#### _GROUP BY Kullanımı_

GROUP BY ifadesi, bir SQL sorgusunda SELECT ifadesinden sonra ve ORDER BY ifadesinden önce kullanılır. İşte temel yapısı:SELECT sütun1, sütun2, aggregate\_function(sütun3)FROM tablo\_adiWHERE koşulGROUP BY sütun1, sütun2;

#### Örnekler

**1-Basit Kullanım:**

Bir tablodaki her departman için toplam çalışan sayısını bulmak:

```sql
// Some code
SELECT departman_adi, COUNT(*)   FROM calisanlar   GROUP BY departman_adi
```

Bu sorgu, calisanlar tablosundaki her departman\_adi için çalışan sayısını döndürecektir.

**2-Birden Fazla Sütunla Kullanım:**

Her departman ve pozisyon için ortalama maaşı bulmak:&#x20;

```sql
// Some code
SELECT departman_adi, pozisyon, AVG(maas)   FROM calisanlar   GROUP BY departman_adi, pozisyon
```

&#x20;Bu sorgu, her departman\_adi ve pozisyon kombinasyonu için ortalama maaşı hesaplar.

**3-Koşullu Kullanım:**

Belirli bir maaşın üzerinde olan çalışanlar için her departmandaki toplam çalışan sayısını bulmak:  &#x20;

```sql
// Some code
SELECT departman_adi, COUNT(*)   FROM calisanlar   WHERE maas > 5000   GROUP BY departman_adi
```

Bu sorgu, maaşı 5000'den fazla olan çalışanları gruplar ve her departman için sayar.

#### Dikkat Edilmesi Gerekenler

* GROUP BY ifadesinde belirtilen sütunlar, SELECT ifadesinde de yer almalıdır. Aksi takdirde, SQL hata verebilir.
* GROUP BY ile birlikte kullanılan sütunlar, genellikle toplu fonksiyonlar dışında kalan sütunlardır.
* GROUP BY ifadesi, verileri gruplandırırken sıralama yapmaz. Eğer sıralama isteniyorsa, ORDER BY ifadesi kullanılmalıdır.

GROUP BY, veritabanı sorgularında verileri anlamlı gruplara ayırarak analiz yapmayı kolaylaştırır. Bu, özellikle raporlama ve veri analizi süreçlerinde oldukça faydalıdır.
