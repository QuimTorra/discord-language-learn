<script lang=ts>
  export let item;
</script>

<div class="card">
  <div class="title">
    {item["name"]}
  </div>
  <div class="lang-disp">
    <span class="bold">· language:</span> {item["language"]}
  </div>
  <div class="native-disp">
    <span class="bold">· native:</span> {item["native"]}
  </div>
</div>

<style>

  .card {
    margin: .5rem;
    background-color: var(--lighter-bg);
    border-radius: 9px;
    width: 20rem;
    height: 5rem;
    padding: 1rem;
    box-shadow: 0px .125rem 5px #111111;

    transition: transform 250ms ease,
      box-shadow 250ms ease;
  }
  .card:hover, .card:focus-within {
    border: 1px solid var(--accent);
    
    box-shadow: 0px .5rem 5px #222222;
    transform: translateY(-.5rem);
  }

  .title {
    font-weight: 900;
  }

  .bold {
    font-weight: bold;
  }
</style>