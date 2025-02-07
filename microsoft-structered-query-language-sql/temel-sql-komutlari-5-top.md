---
description: Top komutu ne işe yarar ? Nasıl kullanılır ?
icon: server
---

# Temel SQL komutları-5 (TOP)

SQL'de TOP komutu, bir sorgu sonucunda döndürülen satır sayısını sınırlamak için kullanılır. Ancak, TOP komutu yalnızca Microsoft SQL Server ve Sybase gibi bazı SQL dillerinde desteklenir. Diğer veritabanı sistemlerinde benzer işlevsellik LIMIT veya FETCH FIRST gibi komutlarla sağlanır.

#### Kullanımı

TOP komutu, SELECT ifadesiyle birlikte kullanılır ve genellikle en üstteki belirli sayıda satırı döndürmek için kullanılır.

```sql
// Some code
SELECT TOP n * FROM tablo_adi
```

Burada n, döndürmek istediğiniz satır sayısını belirtir.

#### Örnek Kullanımlar

1\. Belirli Sayıda Satır Döndürme:  &#x20;

```sql
// Some code
SELECT TOP 5 * FROM urunler
```

Bu sorgu, urunler tablosundaki ilk 5 satırı döndürecektir.

* Yüzdelik Dilim Kullanımı:

SQL Server'da, TOP komutunu yüzdelik dilimle de kullanabilirsiniz:&#x20;

```sql
// Some code
  SELECT TOP 10 PERCENT * FROM urunler
```

Bu sorgu, urunler tablosundaki satırların ilk %10'unu döndürecektir.

#### Diğer Veritabanı Sistemlerinde Eşdeğerleri

* MySQL ve PostgreSQL: LIMIT kullanılır. &#x20;

```sql
// Some code
SELECT * FROM urunler LIMIT 5;
```

* Oracle: FETCH FIRST kullanılır.&#x20;

```sql
// Some code
 SELECT * FROM urunler FETCH FIRST 5 ROWS ONLY;
```

#### Özet

* TOP, sorgu sonucunda döndürülen satır sayısını sınırlamak için kullanılır.
* Yalnızca belirli SQL dillerinde desteklenir (örneğin, SQL Server).
* Diğer veritabanı sistemlerinde LIMIT veya FETCH FIRST gibi komutlar kullanılır.

TOP komutu, büyük veri setlerinde performansı artırmak ve yalnızca gerekli verileri almak için oldukça kullanışlıdır.
