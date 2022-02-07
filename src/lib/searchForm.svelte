<script lang=ts>
  export let loading = false;

  let language
  let native

  let myHeaders = new Headers()

// Access to fetch blocked by CORS Policy
  async function handleSearch () {
    loading = true
    if ( language === "" ) {
      if ( native === "" ) {
        loading = false
        return
      }
      return nativeSearch()
    }

    if ( native === "" ) {
      return languageSearch()
    }

    return fullSearch()
  }

  async function languageSearch() {
    const res = await fetch(`http://localhost:8080/${language}`) 
      .then(res => { return res.json() })
      .then(data => {
        loading = false
        console.log(data)
      })
  }

  async function nativeSearch() {
    const res = await fetch(`http://localhost:8080/native/${native}`) 
      .then(res => { return res.json() })
      .then(data => {
        loading = false
        console.log(data)
      })
  }

  async function fullSearch() {
    const res = await fetch(`http://localhost:8080/${language}/${native}`) 
      .then(res => { return res.json() })
      .then(data => {
        loading = false
        console.log(data)
      })
  }
</script>

<div class="form">
  <div class="smalls">
    <div class="label lang-label">
      <span>
        Language
      </span>
      <select id="language" bind:value={language}>
        <option value="">---</option>
        <option value="english">English</option>
        <option value="japanese">Japanese</option>
        <option value="spanish">Spanish</option>
      </select>
    </div>
    <div class="label nat-label">
      <span>
        Native
      </span>
      <select id="native" bind:value={native} >
        <option value="">---</option>
        <option value="english">English</option>
        <option value="spanish">Spanish</option>
      </select>
    </div>
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
  .label {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-weight: bold;
  }
  span {
    margin-bottom: .125rem;
  }

  select {
    font-family: var(--text-font);
    padding: .25rem .5rem .25rem .5rem;
    font-size: 1.1rem;
    background-color: var(--lighter-bg);
    outline: none;
    border: .125rem solid var(--primary);
    color: var(--text-color);
    border-radius: 20px;
    transition: border-color 250ms ease;
    width: 8rem;
    margin-left: .25rem;
    margin-right: .25rem;
  }
  select:hover, select:focus-visible {
    cursor: pointer;
    border-color: var(--accent);
  }

  button {
    font-family: var(--text-font);
    padding: .45rem 1.1rem .45rem 1.1rem;
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