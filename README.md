Bu repository içerisinde Search Engine Optimization ile ilgili notlarım ve örnek uygulamalarım yer alıyor.

# Giriş
Semantik web programlamada kullanılan etiketlerin anlamlı olmalarıdır böylece arama motorları siteye baktığında sitede ne olduğu ve içeriği konusunda anlamlı bir bilgi edinir.

|Semantik etiket| Açıklama|
|---|---|
|article|bağımsız içerikleri ve makaleleri tanımlar|
|aside|kenar çubuklarını tanımlar|
|details|ek ayrıntıları tanımlar|
|figure|görsel içeriği tanımlar|
|figcaption|görsel içeriğin başlığını tanımlar|
|footer|sayfa için alt bilgiyi tanımlar|
|header|sayfa için başlık tanımlar|
|hgroup|başlık grubunu tanımlar|
|nav|sayfadaki bağlantıları ve menüyü tanımlar|
|mark|işaretlenmiş içeriği tanımlar|
|section|sayfa içindeki bir bölümü tanımlar|
|summary|özet içeriği tanımlar|
|time|oluşturulma zamanını tanımlar|
|main|sayfa içeriğinin ana kökünü belirtir.|

![semantik-etiket-1](./img/semantic-etiketler-1.jpg.crdownload)
![semantic-etiket-2](./img/semantic-etiketler-2.jpg)

- **article**
    içeriği içindeki etiketleri işyerek olduğu gibi gösterir.
    ```html
    <article>
        <h1>makale</h1>
        <p>makale içeriği</p>
    </article>
    ```
- **aside**
    içeriği içindeki etiketleri işyerek olduğu gibi gösterir.
    ```html
    <aside>
        <h1>makale</h1>
        <p>makale içeriği</p>
    </aside>
    ```
- **detail**
    içeriği gizler ve tıklanabilir bir akordeon menü haline getirir
    ```html
    <details>
        <p>details etiketi özelliği</p>
    </details>
    ```
- **figure**
    içinde resim gösterilir içindek img etiketi kullanılır
    ```html
    <figure>
        <img src="http://hdresim.net/resimler/r6/yaz15(34).jpg" alt="yaz manzarası" width="350" height="240">
    </figure>
    ```
    <figure>
        <img src="http://hdresim.net/resimler/r6/yaz15(34).jpg" alt="yaz manzarası" width="350" height="240">
    </figure>
- **figcaption**
    içinde resim gösterilir içindek img etiketi kullanılır
    ```html
    <figure>
        <figcaption>yaz manzarası</figcaption>
        <img src="http://hdresim.net/resimler/r6/yaz15(34).jpg" alt="yaz manzarası" width="350" height="240">
    </figure>
    ```
    <figure>
        <figcaption>yaz manzarası</figcaption>
        <img src="http://hdresim.net/resimler/r6/yaz15(34).jpg" alt="yaz manzarası" width="350" height="240">
    </figure>
- **footer**
    içinde resim gösterilir içindek img etiketi kullanılır
    ```html
    <footer>
        <p>sayfayı hazırlayan kişinin adı</p>
    </footer>
    ```
- **header**
    başlık grubudur.bir başlık yazılması gerekiyorsa bu başlık içerisine yazılmalıdır.
    ```html
    <article>
        <header>
            <h1>başlık</h1>
            <p>paragraf 1</p>
            <p>paragraf 2</p>
        </header>
    </article>
    ```
**hgroup**
    header ile aynı mantıkta çalışmaktadır.
**mark**
    işaretlenmiş yazıları belirtir.
    zemin rengini sarı yapar.
```html
<p>bu paragrafta <mark>işaretlenmiş</mark> kelime var </p>
```
**nav**
    menüleri,butonları ve bağlantıları içeren etiket grubudur.
```html
<nav>
    <div style="background-color:silver; padding:5px;">
        <a href="/sayfa1.html">sayfa 1</a>
        <a href="/sayfa2.html">sayfa 2</a>
    </div>
</nav>
```
**section**
    bölüm kesiti anlamındadır bir yazının bir parçasını göstermek için kullanılabilir.
```html
<section>
    <h3>başlık</h3>
    <p>burası bir paragraftır.</p>
    <p>bu paragrafı yazan kişinin adıdır.</p>
</section>
```
**summary**
bir içeriğin özetini göstermekte kullanılır tıklandığında devamını gösterir.details etiketi ile birlikte kullanılır.
```html
<details>
    <summary>&copy; Copyright</summary>
    <p>bu sayfadaki içerikler tefif hakkı ile korunmaktadır.</p>
</details>
```
> <details><summary>&copy; Copyright</summary><p>bu sayfadaki içerikler tefif hakkı ile korunmaktadır.</p> </details>

**time**
    zaman tanımlamaları yaparken kullanılır.
```html
<time>makalenin yazılma tarihi</time>
```

**Offline cache -manifest hazırlamak**
önbelleklenecek sayfayı belirtme
html etiketinde manifest adında bir attribute tanımlamaktır, tanımlanan manifesto dosya okuma durumlarını belirtecek olan **.appcache** uzantılı dosya ismi yazılır.

HTML5 Cache Manifest dosya biçimini kullanarak web uygulamalarının çevrimdışı çalışmasını sağlayan bir dosyadır.
Bu dosya biçiminde, CACHE MANIFEST başlığı ile başlayan ve .appcache uzantılı bir dosya oluşturmanız gerekir.
Bu dosyada, cache lenmesini istediğiniz dosyaları CACHE bölümüne, her zaman yeniden yüklenmesini istediğiniz dosyaları NETWORK bölümüne ve cache lenemeyen dosyalar için alternatif dosyaları FALLBACK bölümüne yazabilirsiniz.
Örneğin, aşağıdaki gibi bir index_manifest.apache dosyası oluşturabilirsiniz:
```html
<html manifest="index_manifest.appcache">
```
bu tanımlamada index_onbellek.appcache adlı bir dosyayı okumasını ve önbellek durumuna bakmasını belirtmiş olduk.

**Örnek bir cache dosyası içeriği**
```apache
CACHE MANIFEST
# Bu bir yorum satırıdır

CACHE:
index.html
stylesheet.css
images/logo.png
scripts/main.js

NETWORK:
http://cdn.example.com/scripts/main.js

FALLBACK:
/images/ /images/offline.png

```