<script>
  import ServerCard from "$lib/serverCard.svelte"
import { is_empty } from "svelte/internal"
  import SearchForm from "../lib/searchForm.svelte"

  let loading
  let results = [
    {
      "id": "WotuBLgX2WQjkxSgL4GW",
      "language": "japanese",
      "link": "https://www.tomorrowtides.com/ad1677.html",
      "name": "Test Server - Eng - Japanese",
      "native": "english",
      "verified": true
    }
  ]
</script>

<header>
  <div class="logo">
    <span class="l1">discord</span> <span>learn</span> <span>language</span>
  </div>
  <SearchForm bind:loading bind:results />
  <div class="info-btns">
    <button>
      <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="currentColor" class="bi bi-plus-circle" viewBox="0 0 16 16">
        <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
        <path d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4z"/>
      </svg>
    </button>
    <button>
      <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" fill="currentColor" class="bi bi-info-circle" viewBox="0 0 16 16">
        <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z"/>
        <path d="m8.93 6.588-2.29.287-.082.38.45.083c.294.07.352.176.288.469l-.738 3.468c-.194.897.105 1.319.808 1.319.545 0 1.178-.252 1.465-.598l.088-.416c-.2.176-.492.246-.686.246-.275 0-.375-.193-.304-.533L8.93 6.588zM9 4.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0z"/>
      </svg>
    </button>
  </div>
</header>

<div class="container">
  {#if results.length != 0}
    {#each results as item, i}
      <ServerCard item={item} />
    {/each}
  {:else}
    <p>No Results Found :(</p>
  {/if}
</div>

<style>

  :global(:root) {
    --bg-color: #2E3532; 
    --lighter-bg: #424C48;
    --text-color: #E0E2DB;
    --primary: #D3EFBD;
    --accent: #7692FF;
    --text-font: 'Nunito', sans-serif; 
    color: var(--text-color);
    font-family: var(--text-font);
  }

  :root {
    background-color: var(--bg-color);
  }

  header {
    padding-top: .5rem;
    padding-bottom: .5rem;
    height: 3rem;
    width: 100vw;
    box-shadow: #111111 0 0 9px;
    background-color: var(--lighter-bg);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    font-size: 1.175rem;
    text-transform: uppercase;
    letter-spacing: 0.2ch;
    font-weight: 900;
    margin-left: .5rem;
  }
  .logo > span {
    transition: 1500ms ease;
  }
  .logo span:hover {
    color: var(--accent);
    transition: 250ms ease;
  }

  .info-btns {
    display: flex;
    justify-content: center;
    margin-right: 1.5rem;
  }
  .info-btns button {
    background: none;
    border: none;
    color: var(--primary)
  }
  .info-btns button:hover {
    cursor: pointer;
    color: var(--accent)
  }
  .info-btns svg {
    color: inherit;
    transition: 250ms ease;
  }

  .container {
    display: flex;
    justify-content: center;
    
    padding-top: 1rem;
  }

  @media(max-width: 800px) {
    header {
      flex-direction: column;
      height: fit-content;
    }
    .info-btns {
      position: absolute;
      flex-direction: column-reverse;
      top: .5rem;
      left: .125rem;
    }
  }

  @media(max-width: 370px) {
    .logo {
      font-size: 1rem;
    }
    .info-btns {
      flex-direction: row-reverse;
      top: 9.125rem;
    }
    .container {
      padding-top: 2.125rem;
    }
  }

</style>

<svelte:head>
  <meta name="theme-color" content="#424C48" >
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;500;600;700;800;900&display=swap');
  </style>
</svelte:head>