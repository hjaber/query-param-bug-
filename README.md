# Query Parameter Navigation Bug

Minimal reproduction of a SvelteKit navigation bug when using the experimental async compiler.

## The Bug

When `compilerOptions.experimental.async: true` is enabled, links with query parameters fail to navigate after hovering over multiple links. The URL updates but the page doesn't load.

## Reproduce

1. Hover over 2+ links with query params (e.g., `/search?q=1`, `/search?q=2`)
2. Click any link
3. URL changes but page doesn't navigate

Links without query params work fine.

## Configuration

```js
// svelte.config.js
compilerOptions: {
  experimental: {
    async: true;
  }
}
```

## Notes

- Only occurs with `async: true`
- Affects static and dynamic hrefs
- Related to query parameter preloading on hover
- Potentially related to SvelteKit issue #14827
