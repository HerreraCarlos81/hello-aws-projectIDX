<script>
  import svelteLogo from './assets/svelte.svg'
  import idxLogo from './assets/idx-logo.gif'
  import awsLogo from './assets/aws-icon.svg'
  import Counter from './lib/Counter.svelte'
</script>

<main>
  <div>
    <a href="https://developers.google.com/idx" target="_blank" rel="noreferrer">
      <img src={idxLogo} class="logo" alt="IDX Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
    <a href="https://aws.amazon.com/" target="_blank" rel="noreferrer">
      <img src={awsLogo} class="logo aws" alt="AWS Logo" />
    </a>
  </div>
  <h2>Project IDX + Svelte + AWS</h2>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Project IDX, Svelte and AWS logos to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 1em #a806ff);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 1em #ff3e00aa);
  }
  .logo.aws:hover {
    filter: drop-shadow(0 0 1em #ffffffaa);
  }
  .read-the-docs {
    color: #888;
  }

</style>
