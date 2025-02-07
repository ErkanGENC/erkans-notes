---
description: TEMEL SQL Hakkında bilgilendirmeler içerir.
icon: server
---

# Temel SQL komutları-(SELECT-INSERT-UPDATE)

SQL (Structured Query Language), veritabanlarıyla etkileşimde bulunmak için kullanılan bir dildir. İşte SQL'in temel komutları:

_**SELECT**_**:** Veritabanından veri sorgulamak için kullanılır.

```sql
// Some code

SELECT * FROM tablo_adi;

```

_**INSERT:**_ Veritabanına yeni veri eklemek için kullanılır.

```sql
// Some code
   INSERT INTO tablo_adi (kolon1, kolon2) VALUES (deger1, deger2);
```

_**UPDATE:**_ Var olan veriyi güncellemek için kullanılır.

```sql
// Some code
   UPDATE tablo_adi SET kolon1 = deger1 WHERE kosul;
```

_**DELETE:**_ Veritabanından veri silmek için kullanılır.

```sql
// Some code
   DELETE FROM tablo_adi WHERE kosul;
```

_**ALTER TABLE:**_ Var olan bir tabloyu değiştirmek için kullanılır.

```sql
// Some code
   ALTER TABLE tablo_adi ADD kolon3 tip3;
```

_**DROP TABLE:**_ Bir tabloyu silmek için kullanılır.

```sql
// Some code
   DROP TABLE tablo_adi;
```

_**JOIN:**_ Birden fazla tabloyu birleştirmek için kullanılır.

```sql
// Some code
   SELECT * FROM tablo1 INNER JOIN tablo2 ON tablo1.kolon = tablo2.kolon;
```

Bu komutlar, veritabanı yönetimi ve veri manipülasyonu için en sık kullanılan temel SQL komutlarıdır. Her biri, veritabanı ile farklı türde etkileşimler kurmanıza olanak tanır.



**Soru 1: Data manipülasyon ve veritabanı manipülasyon komutları ne demektir? ne işe yarar ?**

Veritabanı yönetiminde, SQL komutları genellikle iki ana kategoriye ayrılır: Veri Manipülasyon Komutları (DML - Data Manipulation Language) ve Veritabanı Manipülasyon Komutları (DDL - Data Definition Language). Her iki tür de farklı amaçlar için kullanılır ve veritabanı ile etkileşimde bulunmanıza olanak tanır.

#### Veri Manipülasyon Komutları (DML)

DML komutları, veritabanındaki verileri eklemek, güncellemek, silmek ve sorgulamak için kullanılır. Bu komutlar, veritabanının içeriği üzerinde değişiklik yapar.

1. SELECT: Veritabanından veri sorgulamak için kullanılır.
2. INSERT: Veritabanına yeni veri eklemek için kullanılır.
3. UPDATE: Var olan veriyi güncellemek için kullanılır.
4. DELETE: Veritabanından veri silmek için kullanılır.

#### Veritabanı Manipülasyon Komutları (DDL)

DDL komutları, veritabanının yapısını tanımlamak veya değiştirmek için kullanılır. Bu komutlar, veritabanı nesneleri üzerinde değişiklik yapar.

1. CREATE TABLE: Yeni bir tablo oluşturmak için kullanılır.
2. ALTER TABLE: Var olan bir tabloyu değiştirmek için kullanılır.
3. DROP TABLE: Bir tabloyu silmek için kullanılır.
4. TRUNCATE TABLE: Bir tablodaki tüm verileri silmek için kullanılır, ancak tablo yapısını korur.

Truncate Table kullanımı için ;&#x20;

```sql
// Some code
   TRUNCATE TABLE tablo_adi;
```

#### Özet

* DML komutları, veritabanındaki verilerle doğrudan etkileşimde bulunur ve bu verileri manipüle eder.
* DDL komutları, veritabanının yapısını tanımlar veya değiştirir, yani veritabanı nesneleri üzerinde çalışır.

Bu komutlar, veritabanı yönetimi ve veri manipülasyonu için temel araçlardır ve veritabanı ile etkili bir şekilde çalışmanıza olanak tanır.

