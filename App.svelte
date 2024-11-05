<script>
  import Header from "./lib/Header.svelte";
  import Counter from "./lib/Counter.svelte";
  import CambiarModo from "./lib/CambiarModo.svelte";
  import GaleriaModal from "./lib/GaleriaModal.svelte";
  import Cronometro from "./lib/Cronometro.svelte";
  let colores = ["blue", "red", "pink", "orange"]
</script>


{#each colores as color, i}
  {#if i%2}
  <Header color ={color} titulo= {color} tam="3"/>
  {:else}
  <Header color ={color} titulo= {color} tam="2"/>
  {/if}

{/each}

<Counter/>
<CambiarModo/>
<GaleriaModal/>
<Cronometro/>




