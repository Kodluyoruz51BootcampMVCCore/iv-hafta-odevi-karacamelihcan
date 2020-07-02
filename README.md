# iv-hafta-odevi
*  Geri dönen bilgiye göre yeşil renkte onay mesajı gösterilmesi. (örneğin:view bag)

*  AddMVC - AddMVCCore - AddDateAnnotations nedir? Nerelerde eklenmelidir?

 * Shanpshot nedir? nasıl değişir? neden alınır?

*  Jquery Calender--> [Datapicker](https://jqueryui.com/datepicker/) --> DueAt'i takvim tipinde eklemek nasıl yapılır? Araştırınız. (DateTimeUffset tipinden atamalar oluşucak)

*  First- FirstOrDefault ve Single- SingleOrDefault nedir? Aralarındaki farkı araştırınız.

*  En kısa null check nasıl yapılır?

* partial view nedir?

* Farklı authentication bulup,aynı işleri farklı yollar ile yapanları araştırınız.

* Ödev- Razor Pages/MVC Projects karşılaştırmasını yapınız.

# IV. HAFTA ÖDEV CEVAPLARI

## 1) AddMvc vs AddMvcCore
AddMvc() is adding Authorization, the RazorViewEngine and the JsonFormatters we need to get our output going. And most interesting it is also calling the `AddMvcCore()` method itself, the highlighted part, where as

AddMvcCore() lot shorter and only adding the basic things to get started. But both methods are returning an IMvcCoreBuilder. Interesting is the `AddMvcCoreServices(services);` method which is adding the ability to return FileContents, RedirectToRouteResults, ActionResolvers, use Controllers, use routing and so on. Really basic functionality.

## 2) AddDateAnnotations nedir?
MVC uygulamasında veri tabanı tablolarını Code First yöntemi ile oluşturmaya başladığımızda yapılan validasyon işlemlerine Data Annotations denir.

## 3) First- FirstOrDefault ve Single- SingleOrDefault nedir?


**SingleOrDefault:**  Eğer dizi içinden sadece bir tane sayı seçmek istiyorsak ve seçim şartımız sağlanmıyorsa, bu durumda  **int**  tipinin varsayılan değeri olan 0(sıfır) döndürülsün istiyorsak  **SingleOrDefault**  seçimini kullanmalıyız.

`int [] oddNumbers = { 1, 3, 5, 7, 9 };`

`int number = oddNumbers.SingleOrDefault(n => n.Equals(4));`

`Console.WriteLine(number);`

Yukarda görüldüğü üzere dizi içerisinde 4 değeri olmadığı için program çıktısı 0 olacaktır.

Eğer seçim sonucunda birden fazla değer dönerse  **InvalidOperationException**  fırlatılacaktır.

`int [] oddNumbers = { 1, 3, 5, 7, 9 };`

`int number = oddNumbers.SingleOrDefault(n => n > 1);`

`Console.WriteLine(number);`

Yukarıdaki kod parçası hata fırlatılacaktır. Çünkü 1’den büyük olan, birden fazla eleman vardır.

**Single:** Eğer seçimimiz sonucunda sadece bir tane eleman geleceği garanti ise, bu durumda  **Single**  seçimini kullanabiliriz. Eğer şartımızı sağlayan hiçbir eleman dönmezse veya şartımızı sağlayan birden fazla eleman dönerse, bu iki durumda da istisnalar fırlatılacak ve hata ile karşılaşmış olacağız.

`int [] oddNumbers = { 1, 3, 5, 7, 9 };`

`int number = oddNumbers.Single(n => n.Equals(3));`

`Console.WriteLine(number);`

Yukarıdaki örnekte şartımız sağlandığı için 3 sonucu çıktı olarak gösterilecektir.

`int``[] oddNumbers = { 1, 3, 5, 7, 9 };`

`int number = oddNumbers.Single(n => n.Equals(2));`

`Console.WriteLine(number);`

Yukarıdaki örnekte ise 2’ye eşit olan herhangi bir eleman olmadığı için  **InvalidOperationException**  istisnası fırlatılacaktır.

**FirstOrDefault:** Bu seçimde de mantık  **SingleOrDefault**  ile aynıdır. Ancak bu seçimde istenen şartta ilk eleman seçilir. Örneğin dizinin ilk elemanı, dizinin 2’den büyük ilk elemanı gibi.

**First:**  Mantık Single ile aynıdır, ancak seçilen ilk elemandır.

`int [] oddNumbers = { 1, 3, 5, 7, 9 };`

`int number = 0;`

`number = oddNumbers.FirstOrDefault(n => n > 9);` `// Sonuç: 0`

`number = oddNumbers.FirstOrDefault(n => n == 3);` `// Sonuç: 3`

`number = oddNumbers.First(n => n == 5);` `// Sonuç: 5`

`number = oddNumbers.First(n => n > 2);` `// Sonuç: 3`

`number = oddNumbers.First(n => n > 9);` `// Sonuç: HATA`

`Console.WriteLine(number);`

## 4) En kısa null check nasıl yapılır?
In C#,  **_IsNullOrEmpty()_**  is a string method. It is used to check whether the specified string is null or an Empty string. A string will be  **null**  if it has not been assigned a value. A string will be  **empty** if it is assigned “” or  _String.Empty_  (A constant for empty strings).

**Syntax:**

` static bool IsNullOrEmpty(String str) ` 

**Explanation:** This method will take a parameter which is of type  **System.String**  and this method will returns a boolean value. If the  _str_ parameter is null or an empty string (“”) then return True otherwise return False.
## 5) Partial View nedir?
Bir işlemi birden fazla kez yapacaksak bir kalıp kullanırız. Öğreğin oluşturacağımız bir resim galerisini web sitesinde birden fazla sayfada kullanacağımızı düşünelim. Aynı galeriyi her sayfa için tekrar tekrar oluşturmak gereksiz ve zaman kaybıdır. Tam da burada Partial View imdadımıza yetişiyor. Partial View kendi başına hiçbir işlevi olmayan bir yapıdır. Bulunduğu sayfa içerisinde çalışır. 

