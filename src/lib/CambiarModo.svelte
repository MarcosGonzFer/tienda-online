<script>
    let DarkMode= false;
    function togleTheme(){
DarkMode= !DarkMode
    }
  
 
</script>
<div
  class:dark-mode={DarkMode}
  class:light-mode={!DarkMode}>
</div>
<button on:click={togleTheme}>Cambiar a {DarkMode ? 'Modo Claro' : 'Modo Oscuro'}</button>
<style>

    div {
        width: 100%;
        height: 20vh; 
    }
    .light-mode {
        background-color: white; 
    }
    .dark-mode {
        background-color: black; 
    }
</style>
