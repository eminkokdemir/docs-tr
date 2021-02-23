# Kurulum

### Uyumluluk Notu

Vue, IE8 ve önceki sürümleri **desteklemez**, çünkü IE8'de değiştirilemeyen ECMAScript 5 özelliklerini kullanıyor. Ancak tüm [ECMAScript 5 uyumlu **tarayıcıları**](https://caniuse.com/#feat=es5) destekler.

### Anlamsal Sürüm Oluşturma

Vue, belgelenmiş özellikler ve davranışlar için tüm resmi projelerinde [Anlamsal Sürümlemeyi](https://semver.org/) takip eder. Belgelenmemiş davranışlar veya açıkta kalan dahili öğeler için, değişiklikler [sürüm notlarında](https://github.com/vuejs/vue/releases) açıklanmıştır.

### Sürüm Notları

Latest stable version: 2.6.12

Her sürüm için ayrıntılı sürüm notları [GitHub](https://github.com/vuejs/vue/releases)'da mevcuttur.

## Vue Devtools

Vue kullanırken, [Vue Devtools](https://github.com/vuejs/vue-devtools#vue-devtools)'u tarayıcınıza yüklemenizi de öneririz, bu da Vue uygulamalarınızı daha kullanıcı dostu bir arayüzde incelemenizi ve hatalarını ayıklamanızı sağlar.

## Doğrudan Dahil Etme `<script>`

Basitçe indirin ve bir `<script>` etiketi ile ekleyin. Vue, global bir değişken olarak kaydedilecektir.

> Geliştirme sırasında küçültülmüş sürümü kullanmayın. Yaygın hatalar için tüm güzel uyarıları kaçıracaksınız!

[Geliştirme Versiyonu](https://vuejs.org/js/vue.js) - Tam uyarılar ve hata ayıklama modu ile.

[Canlı Versiyonu](https://vuejs.org/js/vue.min.js) - Uyarılar kaldırıldı, 33,30 KB dk + gzip

### CDN

Prototip oluşturma veya öğrenme amacıyla en son sürümü aşağıdakilerle kullanabilirsiniz:

```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script>
```

Üretim için, daha yeni sürümlerden beklenmedik kırılmaları önlemek için belirli bir sürüm numarasına bağlanmanızı ve derlemenizi öneririz:

```html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.12"></script>
```

Yerel ES Modülleri kullanıyorsanız, ES Modülleri ile uyumlu bir yapı da vardır:

```html
<script type="module">
  import Vue from 'https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.esm.browser.js'
</script>
```

NPM paketinin kaynağına [cdn.jsdelivr.net/npm/vue](https://cdn.jsdelivr.net/npm/vue/) adresinden göz atabilirsiniz.

Vue ayrıca, [unpkg](https://unpkg.com/vue@2.6.12/dist/vue.js) ve [cdnjs](https://cdnjs.cloudflare.com/ajax/libs/vue/2.6.12/vue.js)'de de mevcuttur (cdnj'lerin senkronize edilmesi biraz zaman alır, bu nedenle en son sürüm henüz mevcut olmayabilir).

[Vue'nun farklı yapılarını](https://vuejs.org/v2/guide/installation.html#Explanation-of-Different-Builds) okuduğunuzdan ve yayınlanan sitenizde **canlı sürümünü** kullandığınızdan emin olun, `vue.js`'yi `vue.min.js` ile değiştirin. Bu, geliştirme deneyimi yerine hız için optimize edilmiş daha küçük bir yapıdır.

## NPM

NPM, Vue ile büyük ölçekli uygulamalar oluştururken önerilen kurulum yöntemidir. [Webpack](https://webpack.js.org/) veya [Browserify](http://browserify.org/) gibi modül paketleyicileriyle güzel bir şekilde eşleşir. Vue ayrıca Tek Dosya Bileşenlerini yazmak için eşlik eden araçlar sağlar.

```shell
# latest stable
$ npm install vue
```

## CLI

Vue, iddialı Tek Sayfa Uygulamalarını hızlı bir şekilde desteklemek için [resmi bir CLI](https://github.com/vuejs/vue-cli) sağlar. Modern bir ön uç iş akışı için pil içeren yapı kurulumları sağlar. Çalışırken yeniden yükleme, kaydetme üzerine tüy bırakma ve üretime hazır yapılarla çalışmaya başlamak yalnızca birkaç dakika sürer. Daha fazla ayrıntı için [Vue CLI belgelerine](https://cli.vuejs.org/) bakın.

> CLI, Node.js ve ilişkili oluşturma araçları hakkında önceden bilgi sahibi olduğunu varsayar. Vue veya ön uç oluşturma araçları konusunda yeniyseniz, CLI'yi kullanmadan önce herhangi bir oluşturma aracı olmadan [kılavuzu](https://vuejs.org/v2/guide/) incelemenizi şiddetle öneririz.

## [Explanation of Different Builds](https://vuejs.org/v2/guide/installation.html#Explanation-of-Different-Builds)

[NPM paketinin](https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/) `dist/` dizininde Vue.js'nin birçok farklı yapısını bulacaksınız. İşte aralarındaki farka genel bir bakış:

|                               | UMD                | CommonJS              | ES Module (for bundlers) | ES Module (for browsers) |
| ----------------------------- | ------------------ | --------------------- | ------------------------ | ------------------------ |
| **Full**                      | vue.js             | vue.common.js         | vue.esm.js               | vue.esm.browser.js       |
| **Runtime-only**              | vue.runtime.js     | vue.runtime.common.js | vue.runtime.esm.js       | -                        |
| **Full (production)**         | vue.min.js         | -                     | -                        | vue.esm.browser.min.js   |
| **Runtime-only (production**) | vue.runtime.min.js | -                     | -                        | -                        |

### Dönem

- **Full:** Hem derleyiciyi hem de çalışma zamanını içeren derlemeler.
- **Compiler:** Şablon dizelerini JavaScript oluşturma işlevlerine derlemekten sorumlu olan kod.
- **Runtime**: Vue örneklerini oluşturmaktan, sanal DOM'u oluşturmaktan ve yamalamaktan sorumlu olan kod. Temelde her şey derleyici hariç.
- **[UMD](https://github.com/umdjs/umd)**: UMD yapıları, bir `<script>` etiketi aracılığıyla doğrudan tarayıcıda kullanılabilir. https://cdn.jsdelivr.net/npm/vue@2.6.12 adresindeki jsDelivr CDN'deki varsayılan dosya, Runtime + Compiler UMD derlemesidir (`vue.js`).

