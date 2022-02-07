<script>
  import SearchForm from "../lib/searchForm.svelte"

  let loading
  let results = []
</script>

<div class="container">
  <SearchForm bind:loading />
</div>
{#if loading}
  <h1>LOADING...</h1>
{/if}

<style>
  :global(:root) {
    --bg-color: #2E3532; 
    --lighter-bg: #424C48;
    --text-color: #E0E2DB;
    --primary: #D3EFBD;
    --accent: #7692FF;
    --text-font: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color: var(--text-color);
    font-family: var(--text-font);
  }

  :root {
    background-color: var(--bg-color);
  }

  .container {
    display: flex;
    justify-content: center;
  }

</style>