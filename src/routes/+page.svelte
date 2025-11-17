<main>
  <header>
    <h1>Query Parameter Navigation Bug</h1>
    <p>With Experimental Async Compiler Enabled</p>
  </header>

  <p>
    Links with query parameters fail to navigate after hovering over multiple
    links. The URL changes in the address bar, but the page does not load. This
    only occurs when
    <code>compilerOptions.experimental.async: true</code> is enabled in svelte.config.js.
  </p>

  <p>
    <strong>How to reproduce:</strong> Hover over 2+ links below before clicking
    any. Notice that clicking a link updates the URL but doesn't navigate to the
    new page.
  </p>

  <section>
    <h2>✅ Working: Links without query params</h2>
    <nav>
      <a href="/search">Link 1</a>
      <a href="/search">Link 2</a>
      <a href="/search">Link 3</a>
    </nav>
  </section>

  <section>
    <h2>❌ Broken: Links with query params</h2>
    <nav>
      <a href="/search?q=1">Link 1</a>
      <a href="/search?q=2">Link 2</a>
      <a href="/search?q=3">Link 3</a>
    </nav>
  </section>
</main>

<style>
  main {
    max-width: 700px;
    margin: 2rem auto;
    padding: 0 1rem;
  }

  header {
    margin-bottom: 2rem;
  }

  h1 {
    font-size: 2rem;
    margin-bottom: 0.5rem;
  }

  header p {
    font-size: 1.2rem;
    font-weight: normal;
    color: #666;
    margin: 0;
  }

  main > p:first-of-type {
    font-size: 1.1rem;
    line-height: 1.6;
    margin-bottom: 1rem;
  }

  main > p:nth-of-type(2) {
    color: #666;
    line-height: 1.6;
    margin-bottom: 2rem;
  }

  section {
    margin: 3rem 0;
  }

  h2 {
    margin-bottom: 1rem;
  }

  nav a {
    display: block;
    padding: 0.5rem;
    margin: 0.5rem 0;
    border: 1px solid #000;
    text-decoration: none;
    color: #000;
  }

  nav a:hover {
    background: #f0f0f0;
  }
</style>
