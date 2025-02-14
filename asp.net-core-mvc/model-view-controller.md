---
description: >-
  Model, View, Controller mimarileri ile ilgili detaylı bilgi ve kullanım
  gerekliliklerini açıklar.
icon: diaspora
---

# Model, View, Controller

#### _1. Model (Veri Yapısı)_

Model, uygulamanın veri yapısını temsil eder.

```csharp
// Some code
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
    public string Description { get; set; }
    public DateTime CreatedDate { get; set; }
}
```

_**2. Controller (Kontrolcü)**_

Controller, kullanıcı isteklerini karşılayan ve işleyen sınıflardır.

```csharp
// Some code
public class ProductController : Controller
{
    private readonly IProductService _productService;

    public ProductController(IProductService productService)
    {
        _productService = productService;
    }

    // Ürünleri listeler
    public IActionResult Index()
    {
        var products = _productService.GetAllProducts();
        return View(products);
    }

    // Yeni ürün ekleme sayfasını gösterir
    public IActionResult Create()
    {
        return View();
    }

    // Yeni ürün ekler
    [HttpPost]
    public IActionResult Create(Product product)
    {
        if (ModelState.IsValid)
        {
            _productService.AddProduct(product);
            return RedirectToAction(nameof(Index));
        }
        return View(product);
    }
}
```

#### _3. View (Görünüm)_

View, kullanıcı arayüzünü oluşturan Razor sayfalarıdır.

```csharp
// Some code
@model IEnumerable<Product>

<h2>Ürün Listesi</h2>

<table class="table">
    <thead>
        <tr>
            <th>@Html.DisplayNameFor(m => m.Name)</th>
            <th>@Html.DisplayNameFor(m => m.Price)</th>
            <th>İşlemler</th>
        </tr>
    </thead>
    <tbody>
        @foreach (var item in Model)
        {
            <tr>
                <td>@item.Name</td>
                <td>@item.Price</td>
                <td>
                    <a asp-action="Edit" asp-route-id="@item.Id">Düzenle</a>
                    <a asp-action="Delete" asp-route-id="@item.Id">Sil</a>
                </td>
            </tr>
        }
    </tbody>
</table>
```

#### Önemli Noktalar:

<mark style="color:red;">**1. Model:**</mark>

* Veritabanı tablolarını temsil eder
* Veri doğrulama (validation) kurallarını içerir
* ViewModel'ler ile karmaşık view yapıları oluşturulabilir

<mark style="color:red;">**2. Controller:**</mark>

* Route yönetimini sağlar
* HTTP isteklerini karşılar (GET, POST, PUT, DELETE)
* Model ve View arasında veri akışını yönetir
* Dependency Injection ile bağımlılıkları yönetir

<mark style="color:red;">**3.View:**</mark>

* Razor syntax kullanır
* Layout sayfaları ile şablon yapısı oluşturur
* Partial View'lar ile kod tekrarını önler
* Tag Helper'lar ile HTML oluşturmayı kolaylaştırır

#### Veri Akışı:

1-Kullanıcı bir URL'e istek yapar

2-Routing sistemi isteği uygun Controller'a yönlendirir

3-Controller gerekli Model verilerini hazırlar

4- View, Model verilerini kullanarak HTML oluşturur

5-Oluşturulan HTML kullanıcıya gönderilir

#### Örnek Kullanım Senaryosu:

```csharp
// Some code
public class HomeController : Controller
{
    public IActionResult Index()
    {
        // ViewModel oluşturma
        var viewModel = new HomeViewModel
        {
            Title = "Anasayfa",
            Products = _productService.GetFeaturedProducts()
        };
        
        return View(viewModel);
    }
}
```

```csharp
// Some code
public class HomeViewModel
{
    public string Title { get; set; }
    public List<Product> Products { get; set; }
}
```

```csharp
// Some code
@model HomeViewModel

<h1>@Model.Title</h1>

<div class="products">
    @foreach (var product in Model.Products)
    {
        <partial name="_ProductCard" model="product" />
    }
</div>
```

Bu yapı sayesinde:

* Kod organizasyonu daha düzenli olur
* Sorumluluklar ayrılır (Separation of Concerns)
* Bakım ve geliştirme kolaylaşır
* Test edilebilirlik artar
* Tekrar kullanılabilir kod yazılabilir
