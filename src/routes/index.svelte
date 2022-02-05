<script>
  import SearchForm from "../lib/searchForm.svelte"

  let results = []
</script>

<div class="container">
  <SearchForm />
</div>

<style>
  :global(:root) {
    --bg-color: #2E3532; 
    --lighter-bg: #424C48;
    --text-color: #E0E2DB;
    --primary: #D3EFBD;
    --accent: #7692FF;
    color: var(--text-color);
  }

  :root {
    background-color: var(--bg-color);
  }

  .container {
    display: flex;
    justify-content: center;
  }

</style>