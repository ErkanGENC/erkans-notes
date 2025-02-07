---
description: Truncate ile delete arasındaki temel farklar nelerdir ?
icon: server
---

# Temel SQL komutları-(TRUNCATE-DELETE)

## Truncate ile delete arasındaki temel farklar nelerdir ?&#x20;

TRUNCATE ve DELETE komutları, SQL'de veritabanından veri silmek için kullanılır, ancak aralarında önemli farklar vardır. İşte bu iki komutun kullanımı ve farkları:

#### Truncate Komutu:&#x20;

**Kullanım:** Bir tablodaki tüm verileri hızlı bir şekilde silmek için kullanılır.

**Sözdizimi:**

```sql
// Some code
  TRUNCATE TABLE tablo_adi;
```

**Özellikler:**

* Hızlıdır: TRUNCATE, tabloyu satır satır silmek yerine tüm verileri bir kerede kaldırır, bu yüzden genellikle daha hızlıdır.
* Geri Alınamaz: TRUNCATE işlemi genellikle geri alınamaz, bu yüzden dikkatli kullanılmalıdır.
* Tetikleyiciler: TRUNCATE, tetikleyicileri tetiklemez.
* Otomatik Artış: TRUNCATE, otomatik artışlı bir sütun varsa, bu sütunun sayacını sıfırlayabilir.
* WHERE Desteği Yoktur: TRUNCATE komutu, belirli koşullara göre silme işlemi yapamaz.

#### DELETE Komutu

**Kullanım:** Bir tablodan belirli satırları silmek için kullanılır.

**Sözdizimi:**

```sql
// Some code
  DELETE FROM tablo_adi WHERE kosul;
```

**Özellikler:**

* Esneklik: DELETE, WHERE koşulu ile belirli satırları silmenize olanak tanır.
* Tetikleyiciler: DELETE, tetikleyicileri tetikler.
* Geri Alınabilir: DELETE işlemi, bir işlem (transaction) içinde kullanıldığında geri alınabilir.
* Otomatik Artış: DELETE, otomatik artışlı sütunların sayacını sıfırlamaz

#### Farklar:

* Performans: TRUNCATE genellikle DELETE'den daha hızlıdır çünkü satır satır silme işlemi yapmaz.
* Geri Alınabilirlik: DELETE işlemi geri alınabilirken, TRUNCATE genellikle geri alınamaz.
* Koşullu Silme: DELETE, WHERE koşulu ile belirli satırları silmenize olanak tanır, TRUNCATE ise tüm satırları siler.
* Tetikleyiciler: DELETE tetikleyicileri tetiklerken, TRUNCATE tetiklemez.
* Otomatik Artış: TRUNCATE, otomatik artışlı sütunların sayacını sıfırlayabilir, DELETE ise sıfırlamaz.

Bu farklar, hangi komutun kullanılacağına karar verirken dikkate alınmalıdır. TRUNCATE, tüm verileri hızlı bir şekilde silmek istediğinizde ve geri alma ihtiyacınız olmadığında tercih edilirken, DELETE daha kontrollü ve koşullu silme işlemleri için kullanılır.



