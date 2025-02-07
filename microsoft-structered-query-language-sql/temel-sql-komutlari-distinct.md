---
description: DISTINCT komutu ne işe yarar ? Nasıl kullanılır ?
icon: server
---

# Temel SQL komutları-(DISTINCT)

DISTINCT komutu, SQL'de bir sorgu sonucunda döndürülen verilerdeki yinelenen satırları kaldırmak için kullanılır. Bu komut, belirli bir sütun veya sütunlar kombinasyonundaki benzersiz değerleri elde etmenizi sağlar.

#### Kullanımı

DISTINCT komutu, genellikle SELECT ifadesiyle birlikte kullanılır. İşte temel kullanımı:

```sql
// Some code
SELECT DISTINCT kolon_adi FROM tablo_adi
```

Bu sorgu, belirtilen kolon\_adi sütunundaki benzersiz değerleri döndürecektir.

#### Örnek Kullanımlar

1\. Tek Sütun Üzerinde Kullanım:Eğer bir tablodaki belirli bir sütunun benzersiz değerlerini almak istiyorsanız:&#x20;

```sql
// Some code
  SELECT DISTINCT sehir FROM musteriler
```

Bu sorgu, musteriler tablosundaki sehir sütununda yer alan benzersiz şehir isimlerini döndürecektir.

* Birden Fazla Sütun Üzerinde Kullanım:

Birden fazla sütunun kombinasyonundaki benzersiz satırları almak için:  &#x20;

```sql
// Some code
SELECT DISTINCT sehir, ulke FROM musteriler
```

Bu sorgu, musteriler tablosundaki sehir ve ulke sütunlarının kombinasyonundaki benzersiz satırları döndürecektir.

#### Özet

* DISTINCT, yinelenen satırları kaldırarak benzersiz değerleri elde etmenizi sağlar.
* Tek bir sütun veya birden fazla sütun kombinasyonu üzerinde kullanılabilir.
* Veritabanı sorgularında veri temizliği ve analiz için sıkça kullanılır.

DISTINCT komutu, özellikle büyük veri setlerinde yinelenen verileri filtrelemek ve daha anlamlı sonuçlar elde etmek için oldukça kullanışlıdır.
