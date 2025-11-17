<script lang="ts">
  import type { PageData } from "./$types";

  let { data }: { data: PageData } = $props();
</script>

<svelte:head>
  <title>Search Page</title>
</svelte:head>

<main>
  <h1>Search Page</h1>

  <section>
    <p><strong>URL:</strong> {data.fullUrl}</p>
    <p><strong>Timestamp:</strong> {data.timestamp}</p>
  </section>

  <nav>
    <a href="/">← Back to home</a>
  </nav>
</main>

<style>
  main {
    max-width: 600px;
    margin: 2rem auto;
    padding: 0 1rem;
  }

  section {
    padding: 1rem;
    margin: 1rem 0;
    border: 1px solid #000;
  }
</style>
