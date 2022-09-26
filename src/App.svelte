<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  // import Counter from './lib/Counter.svelte'
  import Header from './lib/Header.svelte';
  // import InputNumer from './lib/InputNumer.svelte';
  // import InputText from './lib/InputText.svelte';

let name = 'Your name'
let weight = 0
let height = 0

function bmiCalc() {
  let result = weight / (height * height)
  let bmi = document.getElementById('result')
  bmi.innerHTML = `Your BMI is ${result.toFixed(1)}`
}
</script>

<main>
  <div>
    <a href="https://vitejs.dev" target="_blank"> 
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank"> 
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>
  <Header />
  <div class="card">
    <div>
      <label for="name">Name</label>
    <input type="text" bind:value={name}>
    </div>
    <div>
      <label for="weigth">Weight</label>
      <input type="text" bind:value={weight}>
    </div>
    <div>
      <label for="name">Heigth</label>
      <input type="text" bind:value={height}>
    </div>
  </div>
  <button on:click={bmiCalc}>calcular</button>
  <div id="result"></div>
</main>

<style>
  .logo {
    height: 3em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  /* .read-the-docs {
    color: #888;
  } */
</style>