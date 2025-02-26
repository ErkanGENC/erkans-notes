---
description: Model Binding, Tag Helpers, Model Validation kavramlarını açıklar.
icon: rocket
---

# Model binding, Tag helpers, model validation

#### _1. Model Binding:_

Model Binding, HTTP isteklerinden gelen verilerin (form verileri, route değerleri, query string parametreleri vb.) otomatik olarak C# nesnelerine dönüştürülmesi işlemidir.

```csharp
// Some code
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
}
```

```csharp
// Some code
public class ProductController : Controller
{
    [HttpPost]
    public IActionResult Create(Product product) // Model Binding örneği
    {
        // product parametresi form verilerinden otomatik oluşturulur
        if (ModelState.IsValid)
        {
            // Ürün kaydetme işlemleri
            return RedirectToAction(nameof(Index));
        }
        return View(product);
    }

    // Kompleks model binding örneği
    public IActionResult Search([FromQuery]string category, [FromRoute]int page)
    {
        // [FromQuery]: Query string'den binding
        // [FromRoute]: Route değerlerinden binding
        // [FromBody]: Request body'den binding
        // [FromForm]: Form verilerinden binding
    }
}
```

#### _2. Tag Helpers:_

Tag Helper'lar, HTML elementlerini sunucu tarafında zenginleştiren ve dinamik içerik oluşturmayı sağlayan yapılardır.

```csharp
//.cshtml
@model Product

<form asp-controller="Product" asp-action="Create" method="post">
    <div class="form-group">
        <label asp-for="Name"></label>
        <input asp-for="Name" class="form-control" />
        <span asp-validation-for="Name" class="text-danger"></span>
    </div>

    <div class="form-group">
        <label asp-for="Price"></label>
        <input asp-for="Price" class="form-control" />
        <span asp-validation-for="Price" class="text-danger"></span>
    </div>

    <button type="submit" class="btn btn-primary">Kaydet</button>
</form>
```

Özel Tag Helper Oluşturma:

```csharp
// Some code
public class EmailTagHelper : TagHelper
{
    public string MailTo { get; set; }

    public override void Process(TagHelperContext context, TagHelperOutput output)
    {
        output.TagName = "a";
        output.Attributes.SetAttribute("href", $"mailto:{MailTo}");
        output.Content.SetContent(MailTo);
    }
}
```

#### 3. Model Validation

Model Validation, model verilerinin doğruluğunu kontrol etmek için kullanılan yapıdır.

```csharp
// Some code
public class Product
{
    public int Id { get; set; }

    [Required(ErrorMessage = "Ürün adı zorunludur")]
    [StringLength(100, MinimumLength = 3)]
    public string Name { get; set; }

    [Required]
    [Range(0, 1000000)]
    [Display(Name = "Ürün Fiyatı")]
    public decimal Price { get; set; }

    [DataType(DataType.Date)]
    public DateTime CreatedDate { get; set; }

    [EmailAddress]
    public string ContactEmail { get; set; }
}
```

Özel Validation Attribute Oluşturma:

```csharp
// Some code
public class FutureDateAttribute : ValidationAttribute
{
    protected override ValidationResult IsValid(object value, ValidationContext validationContext)
    {
        DateTime date = (DateTime)value;
        if (date <= DateTime.Now)
        {
            return new ValidationResult("Tarih gelecekte olmalıdır.");
        }
        return ValidationResult.Success;
    }
}
```

Controller'da Validation Kullanımı:

```csharp
// Some code
public class ProductController : Controller
{
    [HttpPost]
    public IActionResult Create(Product product)
    {
        // Manuel validation ekleme
        if (product.Name != null && product.Name.Contains("test"))
        {
            ModelState.AddModelError("Name", "Ürün adı 'test' içeremez");
        }

        if (ModelState.IsValid)
        {
            // Kaydetme işlemleri
            return RedirectToAction(nameof(Index));
        }

        // Validation hatası varsa formu tekrar göster
        return View(product);
    }
}
```

View'da Validation Mesajlarının Gösterimi:

```csharp
// .cshtml
@model Product

<form asp-action="Create">
    @* Tüm validation hatalarını göster *@
    <div asp-validation-summary="All" class="text-danger"></div>

    <div class="form-group">
        <label asp-for="Name"></label>
        <input asp-for="Name" class="form-control" />
        <span asp-validation-for="Name" class="text-danger"></span>
    </div>

    @* Client-side validation için gerekli script'ler *@
    @section Scripts {
        <partial name="_ValidationScriptsPartial" />
    }
</form>
```

#### Önemli Noktalar:

_**1-Model Binding:**_

* Otomatik tip dönüşümü yapar
* Kompleks modelleri destekler
* Özelleştirilebilir binding kaynakları sunar

_**2-Tag Helpers:**_

* HTML elementlerini dinamik hale getirir
* IntelliSense desteği sağlar
* Özelleştirilebilir ve genişletilebilir

_**3-Model Validation:**_

* Client ve server tarafında doğrulama sağlar
* Hazır validation attribute'ları sunar
* Özel validation kuralları oluşturulabilir
* FluentValidation gibi alternatif kütüphanelerle de kullanılabilir
