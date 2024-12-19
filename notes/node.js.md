---
icon: node
description: Öğrenelimm.
---

# Node.js

<figure><img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/0*qlOGcybSv1XQ1ISL.png" alt=""><figcaption></figcaption></figure>

**Node.js**, JavaScript dilini sunucu tarafında kullanmamızı sağlayan bir compiler demek yanlış olmaz. İlk kez 2009 yılında Ryan Dahl tarafından geliştirildi. V8 JS motoru kullanarak hızlı ve verimli sunucu uygulamaları geliştirmemizi sağlar.

JS, uzun yıllar boyunca yalnızca web tarayıcılarında çalışan bir dil olarak biliniyordu. Fakat Nodejs sayesinde artık bu dili sunucu tarafında da kullanabiliyoruz. Bu da geliştiricilerin hem istemci hem de sunucu tarafında aynı dili kullanabilmelerini sağlayarak (buna uçtan uca JavaScript ile geliştirme fırsatı diyebilirim sanıyorum) büyük bir avantaj sağlar.

Peki neden Nodejs kullanmalıyız? Bu sorunun cevabını bir önceki paragrafta az çok vermiş olsak da aslında daha birçok avantajı olduğunu söyleyebilirim. Mesela hızlı, ölçeklenebilir ve verimli web uygulamaları geliştirebiliriz. Önceden geleneksel sunucu tarafı teknolojileri, çok sayıda eşzamanlı kullanıcıyı yönetmede zorlanıyordu. Nodejs, olay tabanlı yapısı sayesinde bu sorunu aşmış oldu. Özellikle asenkron I/O (input/output, girdi/çıktı) yapısı sayesinde, bloklama olmadan çok sayıda işlemi aynı anda yürütebiliyor. Kullanım alanı olarak da en çok da real-time yani gerçek zamanlı uygulamalar için idealdir diyebiliriz. Örnek olarak sohbet uygulamaları, oyun sunucuları ya da canlı yayın platformlarını verebiliriz.

**1. Nodejs Nedir??**

Nodejs, istemci ve sunucu arasında veri alışverişini kolaylaştıran bir çalışma ortamıdır. Mesela bir web tarayıcısından gelen bir HTTP isteğine yanıt olarak bit HTML dosyası döndüren bir sunucu yazabiliriz.

```javascript
// Some code
const http = require('http');

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Beyza\n');
});

server.listen(3000, () => {
  console.log('Sunucu http://localhost:3000 adresinde çalışıyor');
});
```

**2. Kurulum**\
Buradaki [resmi web sitesi](https://nodejs.org/)nden işletim sistemimize uygun sürümü indirip kurabiliriz. Kurulduktan sonra terminale; node -v yazıyoruz.

**3. REPL**\
&#xNAN;_**REPL (Read-Eval-Print Loop)**_, Nodejs komut satırı aracıdır. REPL, JS kodunu yazıp hemen çalıştırmamızı sağlar. Başlatmak için terminalde `node` komutunu yazmamız yeterlidir.

```javascript
// Some code
$ node
> 2 + 2
4
> console.log('Merhaba Nodejs');
Merhaba Nodejs
```

