# Svelte Getting Started

 - [SVELTE](https://svelte.dev/)
 - [SVELTEKIT](https://kit.svelte.dev/)
 - [tailwindcss](https://tailwindcss.com/)
 - [Vercel](https://vercel.com/)

### Set up Svelte

```bash
# Svelte
$ npm init svelte@next <app-name>
$ # Press enter and setting 
$ cd <app-name>
$ npm install
$ npm run dev

# Tailwindcss
$ npx svelte-add tailwindcss
$ npm install --save svelte-preprocess
```

### Tailwindcss Example

```svelte
<section class="text-center w-full h-screen bg-gradient-to-r from-yellow-200 via-red-300 to-pink-300">
    <h1 class="pt-10 text-7xl">About page</h1>
    <div class="font-serif pt-12 text-2xl">Ciao!</div>
</section>
```

***

### IF

```svelte
{#if}
{:else}
{/if}
```

### Range
```svelte
<ul>
  {#each Array(11) as _, i}
    <li>i</li>
  {/each}
</ul>
```

***

### ファイルとフォルダー

 - `global.css`: 全てのファイルに適応されるCSS
 - `App.svelte`: 土台（componentsをimportして配置するだけ）
 - `components/*.svelte`: メインパーツを管理


```
├─ public
│   ├─ ...
│   └─ global.css
├─ src
│   ├─ components
│   │   └─ *.svelte
│   ├─ *.js 
│   └─ App.svelte
└─ ...
```

***

### Svelte書き方

 - `import <Name> from '<Path>'`
 - `export let <Name>`
 - データ受け取る側: `<slot></slot>`で展開
 - データ呼ぶ側: `<Name></Name>`で展開
 - `<Path>`: 相対か絶対。多分svelteは拡張子必要。jsはいらない（多分）
 - 引数の渡し方は`<Name type="submit" disabled={xxx}></Name>`
 - 引数の受け取り方は`<button {type} {disabled}><slot></slot></button>`
 - 
***

## 例

#### App.svelte

```svelte
<script>
	import Xxx from './components/Xxx.svelte'
	import Yyy from './components/Yyy.svelte'
	import Zzz from './components/Zzz.svelte'
</script>

<main class="container">
	<Xxx />
	<Yyy />
	<Zzz />
</main>
```

#### components/Button.svelte

```svelte
<button {type} {disabled} class={style}>
  <slot></slot>
</button>
```
