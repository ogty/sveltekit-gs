# Svelte Kit Getting Started

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
$ npm i
$ npm run dev

# Tailwindcss
$ npx svelte-add tailwindcss
$ npm i --save svelte-preprocess
```

### OR

```bash
$ npx degit sveltejs/template <app-name>
$ cd <app-name>
$ npm i
```

`i=install`

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

### File and Folder

 - `global.css`: CSS applied to all files
 - `App.svelte`: Foundation (just import and place components)
 - `components/*.svelte`: Manage main parts


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
 - Data receiver: expand with `<slot></slot>`
 - Data caller: expand with `<Name></Name>`
 - `<Path>`: Relative or absolute. Maybe svelte needs an extension, js doesn't (maybe).
 - The arguments are passed as`<Name type="submit" disabled={xxx}></Name>`
 - The argument is received by`<button {type} {disabled}><slot></slot></button>`

***

## Example

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
