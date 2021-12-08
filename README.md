# Svelte Getting Started

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

 - `global.css`: Djangoでの`base.html`に使うCSS
 - `App.svelte`: SPAのベース（componentsをimportして配置するだけ）
 - `components/*.svelte`: SPAで使うメインパーツ


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

### svelte書き方

 - `import <Name> from '<Path>'`
 - `export let <Name>`
 - データ受けとる側: `<slot></slot>`で展開
 - データ呼ぶ側: `<Name></Name>`で展開
 - `<Path>`: 相対か絶対
 - 多分svelteは拡張子必要。jsはいらない？
