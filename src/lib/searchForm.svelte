<script lang=ts>
  let term;
  let type;

  function handleSearch () {
    if ( term === undefined || term === "" ) { return; }
    console.log(`Search: ${term} for ${type}`)
  }
</script>

<div class="form">
  <div class="smalls">
    <input type="text" name="languageSearch" id="languageSearch" placeholder="Language" bind:value={term}>
    <select id="type" bind:value={type}>
      <option value="All">All</option>
      <option value="Servers">Servers</option>
      <option value="Bots">Bots</option>
    </select>
  </div>
  <button on:click={handleSearch}>Search</button>
</div>

<style>
  .form {
    margin-top: .5rem;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .smalls {
    margin-bottom: .25rem;
    display: flex;
    justify-content: space-evenly;

  }

  input {
    font-size: 1.1rem;
    border: .125rem solid var(--primary);
    background-color: var(--lighter-bg);
    border-radius: 20px;
    padding: .5rem 1rem .5rem 1rem;
    color: var(--text-color);
    margin-right: .25rem;
    width: 20ch;
    transition: border-color 250ms ease;
  }
  input:hover, input:focus-visible {
    border-color: var(--accent) ;
    outline: none;
  }

  select {
    padding: .25rem .5rem .25rem .5rem;
    font-size: 1.1rem;
    background-color: var(--lighter-bg);
    outline: none;
    border: .125rem solid var(--primary);
    color: var(--text-color);
    border-radius: 20px;
    transition: border-color 250ms ease;
  }
  select:hover, select:focus-visible {
    cursor: pointer;
    border-color: var(--accent);
  }

  button {
    padding: .5rem 1rem .5rem 1rem;
    font-size: 1.1rem;
    background-color: var(--primary);
    border: .125rem solid var(--lighter-bg);
    border-radius: 20px;
    color: var(--bg-color);
    font-weight: bold;
    width: 10ch;
    outline: none;
    transition: background-color 250ms ease;
  }
  button:hover, button:focus-visible {
    background-color: var(--accent);
    cursor: pointer;
  }

</style>