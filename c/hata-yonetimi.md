---
description: Try-Catch-Finally
icon: circle-exclamation
---

# Hata Yönetimi

````csharp
// Some code

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp
{
    class Program
    {
        static void Main(string[] args)
        {
         try{
            System.Console.WriteLine("bir sayi girin: ");
          int sayi1 = Convert.ToInt32(Console.ReadLine());

          System.Console.WriteLine("bir sayi daha girin: ");
          int sayi2 = Convert.ToInt32(Console.ReadLine());

         var bol = sayi1 / sayi2;
         System.Console.WriteLine("bolum: " + bol);
          }

          catch(Exception ex){
            System.Console.WriteLine("hata: " + ex.Message);
          }

          finally{
            System.Console.WriteLine("program sonlandi");
          }

        }
    }
    }



```
````
