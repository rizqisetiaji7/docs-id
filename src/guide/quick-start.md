---
footer: false
---

<script setup>
import { VTCodeGroup, VTCodeGroupTab } from '@vue/theme'
</script>

# Mulai Cepat {#quick-start}

## Coba Vue Online {#try-vue-online}

- Untuk segera mencoba Vue, Anda bisa mencoba langsung di [_Playground_](https://play.vuejs.org/#eNo9jcEKwjAMhl/lt5fpQYfXUQfefAMvvRQbddC1pUuHUPrudg4HIcmXjyRZXEM4zYlEJ+T0iEPgXjn6BB8Zhp46WUZWDjCa9f6w9kAkTtH9CRinV4fmRtZ63H20Ztesqiylphqy3R5UYBqD1UyVAPk+9zkvV1CKbCv9poMLiTEfR2/IXpSoXomqZLtti/IFwVtA9A==) kami.

- Jika Anda lebih suka _setup_ HTML biasa tanpa langkah pembuatan apa pun, Anda dapat menggunakan [JSFiddle](https://jsfiddle.net/yyx990803/2ke1ab0z/) ini sebagai permulaan.

- Jika Anda sudah familiar dengan Node.js, dan konsep _build tools_, Anda juga dapat mencoba _build setup_ lengkap secara langsung pada browser Anda di [StackBlitz](https://vite.new/vue).

- Untuk mendapatkan panduan _setup_ yang direkomendasikan, tonton tutorial interaktif [Scrimba](http://scrimba.com/links/vue-quickstart) yang akan menunjukkan kepada Anda cara menjalankan, mengedit, dan men-_deploy_ aplikasi Vue pertama Anda.

## Membuat Aplikasi Vue {#creating-a-vue-application}

:::tip Prasyarat

- Familiar dengan _command line_
- Instal [Node.js](https://nodejs.org/) versi 18.3 atau lebih tinggi
  :::

Di bagian ini kami akan memperkenalkan cara membuat Vue [Single-Page Application](/guide/extras/ways-of-using-vue#single-page-application-spa) di komputer lokal Anda. Proyek yang dibuat akan menggunakan _build setup_ berbasis [Vite](https://vitejs.dev), dan memungkinkan kita menggunakan Vue [Single-File Components](/guide/scaling-up/sfc) (SFCs).

Pastikan Anda telah menginstal versi [Node.js](https://nodejs.org/) terbaru dan direktori Anda saat ini adalah tempat yang diperuntukkan membuat proyek. Jalankan perintah berikut pada _command line_ Anda (tanpa tanda `$`):

::: code-group

```sh [npm]
$ npm create vue@latest
```

```sh [pnpm]
$ pnpm create vue@latest
```

```sh [yarn]
# Untuk Yarn (v1+)
$ yarn create vue

# Untuk Yarn Modern (v2+)
$ yarn create vue@latest
  
# Untuk Yarn ^v4.11
$ yarn dlx create-vue@latest
```

```sh [bun]
$ bun create vue@latest
```
:::

Perintah ini akan menginstal dan menjalankan [create-vue](https://github.com/vuejs/create-vue), _scaffolding tool_ resmi Vue. Anda akan diberikan petunjuk untuk beberapa pilihan fitur seperti TypeScript dan dukungan pengujian:

<div class="language-sh"><pre><code><span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Project name: <span style="color:#888;">… <span style="color:#89DDFF;">&lt;</span><span style="color:#888;">your-project-name</span><span style="color:#89DDFF;">&gt;</span></span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add TypeScript? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add JSX Support? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add Vue Router for Single Page Application development? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add Pinia for state management? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add Vitest for Unit testing? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add an End-to-End Testing Solution? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Cypress / Nightwatch / Playwright</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add ESLint for code quality? <span style="color:#888;">… No / <span style="color:#89DDFF;text-decoration:underline">Yes</span></span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add Prettier for code formatting? <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span style="color:var(--vt-c-green);">✔</span> <span style="color:#A6ACCD;">Add Vue DevTools 7 extension for debugging? (experimental) <span style="color:#888;">… <span style="color:#89DDFF;text-decoration:underline">No</span> / Yes</span></span>
<span></span>
<span style="color:#A6ACCD;">Scaffolding project in ./<span style="color:#89DDFF;">&lt;</span><span style="color:#888;">your-project-name</span><span style="color:#89DDFF;">&gt;</span>...</span>
<span style="color:#A6ACCD;">Done.</span></code></pre></div>

Jika Anda tidak yakin mengenai suatu pilihan, cukup pilih `No` dengan menekan _enter_ untuk saat ini. Setelah proyek dibuat, ikuti petunjuk untuk menginstal dependensi dan menjalankan _dev server_:

::: code-group

```sh-vue [npm]
$ cd {{'<your-project-name>'}}
$ npm install
$ npm run dev
```

```sh-vue [pnpm]
$ cd {{'<your-project-name>'}}
$ pnpm install
$ pnpm run dev
```

```sh-vue [yarn]
$ cd {{'<your-project-name>'}}
$ yarn
$ yarn dev
```

```sh-vue [bun]
$ cd {{'<your-project-name>'}}
$ bun install
$ bun run dev
```

:::


Anda sekarang seharusnya sudah menjalankan proyek Vue pertama Anda! Perhatikan bahwa contoh komponen dalam proyek yang dihasilkan, ditulis menggunakan [Composition API](/guide/introduction#composition-api) dan `<script setup>`, daripada [Options API](/guide/introduction#options-api). Berikut beberapa tips tambahan:

- _Setup_ IDE yang direkomendasikan adalah [Visual Studio Code](https://code.visualstudio.com/) + [Vue - Official extension](https://marketplace.visualstudio.com/items?itemName=Vue.volar). Jika Anda menggunakan editor lain, silahkan lihat [bagian dukungan IDE](/guide/scaling-up/tooling#ide-support).
- Detail _tooling_ lebih lanjut, termasuk integrasi dengan kerangka kerja _backend_, dibahas dalam [Panduan Tooling](/guide/scaling-up/tooling).
- Untuk mempelajari lebih lanjut tentang _build tool_ yang mendasari Vite, silahkan lihat [dokumentasi Vite](https://vitejs.dev).
- Jika Anda memilih untuk menggunakan TypeScript, silahkan lihat [Panduan Penggunaan TypeScript](typescript/overview).

Saat Anda siap menjalankan aplikasi ke _production_, jalankan perintah berikut: 

::: code-group

```sh [npm]
$ npm run build
```

```sh [pnpm]
$ pnpm run build
```

```sh [yarn]
$ yarn build
```

```sh [bun]
$ bun run build
```

:::


Ini akan membuat versi aplikasi Anda yang siap produksi di proyek direktori `./dist`. Lihat [Panduan _Production Deployment_](/guide/best-practices/production-deployment) untuk mempelajari lebih lanjut tentang pengiriman aplikasi Anda ke _production_.

[Langkah Selanjutnya >](#next-steps)

## Menggunakan Vue CDN {#using-vue-from-cdn}

Anda bisa menggunakan Vue langsung dari CDN melalui tag _script_:

```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

Di sini kita menggunakan [unpkg](https://unpkg.com/), namun Anda juga bisa menggunakan CDN manapun yang menyediakan paket npm, misalnya [jsdelivr](https://www.jsdelivr.com/package/npm/vue) atau [cdnjs](https://cdnjs.com/libraries/vue). Tentu saja, Anda juga bisa mengunduh file tersebut dan menjalankannya sendiri.

Ketika menggunakan Vue dari CDN, disana tidak ada "build step" yang dijalankan. Hal ini membuat _setup_ menjadi jauh lebih mudah, dan cocok untuk meningkatkan HTML statis atau mengintegrasikan dengan kerangka kerja _backend_. Namun, Anda tidak akan bisa menggunakan sintaks _Single-File Component_ (SFC).

### Menggunakan Global Build {#using-the-global-build}

Tautan di atas memuat _global build_ Vue, di mana semua _top-level APIs_ diekspos sebagai properti pada global objek `Vue`. Berikut adalah contoh lengkap menggunakan _global build_:

<div class="options-api">

```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<div id="app">{{ message }}</div>

<script>
  const { createApp } = Vue

  createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/QWJwJLp)

</div>

<div class="composition-api">

```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<div id="app">{{ message }}</div>

<script>
  const { createApp, ref } = Vue

  createApp({
    setup() {
      const message = ref('Hello vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/eYQpQEG)

:::tip
Banyak contoh untuk _Composition API_ di seluruh panduan ini akan menggunakan sintaks `<script setup>`, yang membutuhkan _build tools_. Jika Anda bermaksud menggunakan _Composition API_ tanpa langkah _build_, konsultasikan penggunaan [opsi `setup()`](/api/composition-api-setup).
:::

</div>

### Menggunakan _ES Module Build_ {#using-the-es-module-build}

Di sepanjang sisa dokumentasi, kita akan mengutamakan penggunaan sintaks [_ES Module_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules). Sebagian besar browser modern saat ini mendukung _ES Module_ secara native, jadi kita bisa menggunakan Vue dari CDN melalui _ES Module_ secara native seperti ini: 

<div class="options-api">

```html{3,4}
<div id="app">{{ message }}</div>

<script type="module">
  import { createApp } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js'

  createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

</div>

<div class="composition-api">

```html{3,4}
<div id="app">{{ message }}</div>

<script type="module">
  import { createApp, ref } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js'

  createApp({
    setup() {
      const message = ref('Hello Vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

</div>

Perhatikan bahwa kita menggunakan `<script type="module">`, dan URL CDN yang diimpor mengarah ke **ES modules build** Vue.

<div class="options-api">

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/VwVYVZO)

</div>
<div class="composition-api">

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/MWzazEv)

</div>

### Mengaktifkan _Import Maps_ {#enabling-import-maps}

Pada contoh diatas, kita mengimpor dari URL CDN secara lengkap, tetapi di sisa dokumentasi Anda akan melihat kode seperti ini:

```js
import { createApp } from 'vue'
```

Kita dapat memberitahu browser di mana menempatkan impor `vue` dengan menggunakan [Import Maps](https://caniuse.com/import-maps):

<div class="options-api">

```html{1-7,12}
<script type="importmap">
  {
    "imports": {
      "vue": "https://unpkg.com/vue@3/dist/vue.esm-browser.js"
    }
  }
</script>

<div id="app">{{ message }}</div>

<script type="module">
  import { createApp } from 'vue'

  createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/wvQKQyM)

</div>

<div class="composition-api">

```html{1-7,12}
<script type="importmap">
  {
    "imports": {
      "vue": "https://unpkg.com/vue@3/dist/vue.esm-browser.js"
    }
  }
</script>

<div id="app">{{ message }}</div>

<script type="module">
  import { createApp, ref } from 'vue'

  createApp({
    setup() {
      const message = ref('Hello Vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

[Demo CodePen >](https://codepen.io/vuejs-examples/pen/YzRyRYM)

</div>

Anda juga dapat menambahkan entri untuk dependensi lain ke _import map_ - namun pastikan mereka menuju ke versi _ES modules_ dari pustaka yang ingin Anda gunakan.

:::tip Dukungan Browser _Import Maps_
_Import Maps_ adalah fitur browser yang relatif baru. Pastikan untuk menggunakan browser dalam [jangkauan dukungan](https://caniuse.com/import-maps). Secara khusus, ini hanya didukung di Safari 16.4+.
:::

:::warning Catatan pada penggunaan _Production_
Contoh sejauh ini menggunakan versi _development_ dari Vue - jika Anda berniat menggunakan Vue dari CDN dalam _production_, pastikan untuk memeriksa [Panduan _Production Deployment_](/guide/best-practices/production-deployment#without-build-tools). 

Meskipun memungkinkan untuk menggunakan Vue tanpa sistem _build_, pendekatan alternatif yang dapat dipertimbangkan adalah menggunakan [`vuejs/petite-vue`](https://github.com/vuejs/petite-vue) yang lebih sesuai dengan konteks di mana [`jquery/jquery`](https://github.com/jquery/jquery) (di masa lalu) atau [`alpinejs/alpine`](https://github.com/alpinejs/alpine) (di masa sekarang) mungkin digunakan sebagai gantinya.
:::

### Splitting Up the Modules {#splitting-up-the-modules}

As we dive deeper into the guide, we may need to split our code into separate JavaScript files so that they are easier to manage. For example:

```html [index.html]
<div id="app"></div>

<script type="module">
  import { createApp } from 'vue'
  import MyComponent from './my-component.js'

  createApp(MyComponent).mount('#app')
</script>
```

<div class="options-api">

```js [my-component.js]
export default {
  data() {
    return { count: 0 }
  },
  template: `<div>Count is: {{ count }}</div>`
}
```

</div>
<div class="composition-api">

```js [my-component.js]
import { ref } from 'vue'
export default {
  setup() {
    const count = ref(0)
    return { count }
  },
  template: `<div>Count is: {{ count }}</div>`
}
```

</div>

If you directly open the above `index.html` in your browser, you will find that it throws an error because ES modules cannot work over the `file://` protocol, which is the protocol the browser uses when you open a local file.

Due to security reasons, ES modules can only work over the `http://` protocol, which is what the browsers use when opening pages on the web. In order for ES modules to work on our local machine, we need to serve the `index.html` over the `http://` protocol, with a local HTTP server.

To start a local HTTP server, first make sure you have [Node.js](https://nodejs.org/en/) installed, then run `npx serve` from the command line in the same directory where your HTML file is. You can also use any other HTTP server that can serve static files with the correct MIME types.

You may have noticed that the imported component's template is inlined as a JavaScript string. If you are using VS Code, you can install the [es6-string-html](https://marketplace.visualstudio.com/items?itemName=Tobermory.es6-string-html) extension and prefix the strings with a `/*html*/` comment to get syntax highlighting for them.

## Next Steps {#next-steps}

If you skipped the [Introduction](/guide/introduction), we strongly recommend reading it before moving on to the rest of the documentation.

<div class="vt-box-container next-steps">
  <a class="vt-box" href="/guide/essentials/application.html">
    <p class="next-steps-link">Continue with the Guide</p>
    <p class="next-steps-caption">The guide walks you through every aspect of the framework in full detail.</p>
  </a>
  <a class="vt-box" href="/tutorial/">
    <p class="next-steps-link">Try the Tutorial</p>
    <p class="next-steps-caption">For those who prefer learning things hands-on.</p>
  </a>
  <a class="vt-box" href="/examples/">
    <p class="next-steps-link">Check out the Examples</p>
    <p class="next-steps-caption">Explore examples of core features and common UI tasks.</p>
  </a>
</div>
