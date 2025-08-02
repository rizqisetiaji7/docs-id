# Membuat Aplikasi Vue {#creating-a-vue-application}

## _Instance_ Aplikasi {#the-application-instance}

Setiap aplikasi Vue dimulai dengan membuat **instance aplikasi** baru dengan fungsi [`createApp()`](/api/application#createapp):

```js
import { createApp } from 'vue'

const app = createApp({
  /* Opsi komponen root */
})
```

## Komponen _Root_ {#the-root-component}

Objek yang kita masukkan ke `createApp` sebenarnya adalah sebuah komponen. Setiap aplikasi membutuhkan "komponen _root_" yang dapat berisi komponen lain sebagai turunannya (_children_).

Jika Anda menggunakan _Single-File Components_, kita biasanya mengimpor komponen _root_ dari file lain:

```js
import { createApp } from 'vue'
// Mengimpor komponen root App dari single-file component.
import App from './App.vue'

const app = createApp(App)
```

Meskipun banyak contoh dalam panduan ini hanya membutuhkan satu komponen, sebagian besar aplikasi nyatanya disusun dalam pohon (_tree_) bersarang (_nested_), komponen yang dapat digunakan kembali. Misalnya, komponen _tree_ aplikasi Todo mungkin terlihat seperti ini:

```
App (root component)
├─ TodoList
│  └─ TodoItem
│     ├─ TodoDeleteButton
│     └─ TodoEditButton
└─ TodoFooter
   ├─ TodoClearButton
   └─ TodoStatistics
```

Pada bagian panduan selanjutnya, kita akan membahas cara mendefinisikan dan menyusun beberapa komponen bersama-sama. Sebelum itu, kita akan fokus pada apa yang terjadi di dalam satu komponen.

## _Mounting_ Aplikasi {#mounting-the-app}

Suatu _instance_ aplikasi tidak akan me-render apa pun sampai _method_ `.mount()` dipanggil. Ia mengharapkan argumen "kontainer", yang bisa berupa elemen DOM aktual atau _selector_ string:

```html
<div id="app"></div>
```

```js
app.mount('#app')
```

Konten komponen _root_ aplikasi akan dirender di dalam elemen kontainer. Elemen kontainer itu sendiri tidak dianggap sebagai bagian dari aplikasi.

_Method_ `.mount()` harus selalu dipanggil setelah semua konfigurasi aplikasi dan registrasi aset selesai. Perlu diperhatikan juga bahwa nilai kembaliannya, tidak seperti _method_ registrasi aset, merupakan _instance_ komponen _root_, bukan _instance_ aplikasi.

### Template Komponen _Root_ In-DOM {#in-dom-root-component-template}

Template untuk komponen _root_ biasanya merupakan bagian dari komponen itu sendiri, tetapi juga memungkinkan untuk menyediakan template secara terpisah dengan menuliskannya langsung di dalam pemasangan (_mount_) kontainer:

```html
<div id="app">
  <button @click="count++">{{ count }}</button>
</div>
```

```js
import { createApp } from 'vue'

const app = createApp({
  data() {
    return {
      count: 0
    }
  }
})

app.mount('#app')
```

Vue akan secara otomatis menggunakan `innerHTML` kontainer sebagai template jika komponen _root_ belum memiliki opsi `template`.

Template In-DOM sering digunakan dalam aplikasi yang [menggunakan Vue tanpa langkah build](/guide/quick-start.html#using-vue-from-cdn). Mereka juga dapat digunakan bersama dengan kerangka kerja sisi server, di mana template _root_ dapat dibuat secara dinamis oleh server.

## Konfigurasi Aplikasi {#app-configurations}

_Instance_ aplikasi memaparkan objek `.config` yang memungkinkan kita mengkonfigurasi beberapa opsi level-aplikasi, misalnya, mendefinisikan penangan _error_ level-aplikasi yang menangkap _error_ dari semua komponen turunan:

```js
app.config.errorHandler = (err) => {
  /* penanganan error */
}
```

_Instance_ aplikasi juga menyediakan beberapa metode untuk me-registrasikan aset yang dicakup aplikasi. Misalnya, me-registrasikan komponen:

```js
app.component('TodoDeleteButton', TodoDeleteButton)
```

Ini membuat `TodoDeleteButton` tersedia untuk digunakan dimana saja didalam aplikasi kita. Kami akan membahas registrasi komponen dan jenis aset lain dibagian panduan selanjutnya. Anda juga dapat menelusuri daftar lengkap API _instance_ aplikasi di [referensi API](/api/application).

Pastikan untuk menerapkan semua konfigurasi aplikasi sebelum _mounting_ aplikasi!

## Multi _instance_ aplikasi {#multiple-application-instances}

Anda tidak terbatas pada satu _instance_ aplikasi pada halaman yang sama. API `createApp` memungkinkan beberapa aplikasi Vue untuk berdampingan di halaman yang sama, masing-masing memiliki cakupannya sendiri untuk konfigurasi dan aset global:

```js
const app1 = createApp({
  /* ... */
})
app1.mount('#container-1')

const app2 = createApp({
  /* ... */
})
app2.mount('#container-2')
```

Jika Anda menggunakan Vue untuk meningkatkan HTML yang ditampilkan di server dan hanya membutuhkan Vue untuk mengontrol bagian tertentu dari halaman besar, hindari _mounting_ satu _instance_ aplikasi Vue pada seluruh halaman. Sebaliknya, buatlah beberapa contoh aplikasi kecil dan pasang pada elemen yang menjadi tanggung jawabnya.
