---
description: SQL veri tipleri ve kullanım alanları
icon: t
---

# SQL Veri Tipleri

SQL veri tipleri, veritabanlarında saklanan verilerin türünü ve boyutunu belirlemek için kullanılır. İşte yaygın SQL veri tipleri ve özellikleri:

**1-INTEGER:**

* _**Özellikler:**_ Tam sayıları saklar. Genellikle 4 bayt yer kaplar.
* _**Kullanım Alanları:**_ Yaş, sayım gibi tam sayı değerleri için kullanılır.

**2-FLOAT/REAL/DOUBLE:**

* Özellikler: Ondalıklı sayıları saklar. Hassasiyet ve boyut farklılık gösterebilir.
* Kullanım Alanları: Finansal hesaplamalar, bilimsel veriler gibi ondalıklı sayılar gerektiren durumlar.

**3-CHAR(n):**

* Özellikler: Sabit uzunlukta karakter dizileri saklar. n kadar karakter yer kaplar.
* Kullanım Alanları: Sabit uzunlukta metinler, örneğin ülke kodları.

**4-VARCHAR(n):**

* Özellikler: Değişken uzunlukta karakter dizileri saklar. Maksimum n karakter uzunluğunda olabilir.
* Kullanım Alanları: İsimler, adresler gibi değişken uzunlukta metinler.

**5-TEXT:**

* Özellikler: Çok büyük metin verilerini saklar.
* Kullanım Alanları: Blog yazıları, açıklamalar gibi uzun metinler.

**6-DATE:**

* Özellikler: Tarih verilerini saklar (Yıl, Ay, Gün).
* Kullanım Alanları: Doğum tarihi, etkinlik tarihi gibi tarih bilgileri.

**7-TIME:**

* Özellikler: Zaman verilerini saklar (Saat, Dakika, Saniye).
* Kullanım Alanları: Çalışma saatleri, randevu saatleri gibi zaman bilgileri.

**8-DATETIME:**

* Özellikler: Tarih ve zaman verilerini birlikte saklar.
* Kullanım Alanları: Zaman damgaları, olay kayıtları gibi tarih ve zaman bilgileri.

**9-BOOLEAN:**

* Özellikler: Doğru veya yanlış değerlerini saklar.
* Kullanım Alanları: Durum bayrakları, aktif/pasif durumlar.

**10-BLOB (Binary Large Object):**

* Özellikler: İkili verileri saklar, genellikle büyük boyutludur.
* Kullanım Alanları: Resimler, ses dosyaları gibi ikili veriler.

Bu veri tipleri, veritabanı tasarımında verilerin doğru ve verimli bir şekilde saklanmasını sağlar. Her bir veri tipi, belirli bir veri türü için optimize edilmiştir ve doğru kullanımı, veritabanı performansını artırabilir.
