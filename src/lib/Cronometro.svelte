<script>
    let segundos = 0;
    let empieza = false;
    let intervalo;

    function iniciar() {
        if (!empieza) {
            empieza = true;
            intervalo = setInterval(() => {
                segundos += 1;
            }, 1000);
        }
    }

    function pausar() {
        if (empieza) {
            empieza = false;
            clearInterval(intervalo);
        }
    }

    function reiniciar() {
        empieza = false;
        clearInterval(intervalo);
        segundos = 0;
    }
</script>

<main>
    <p>{segundos} segundos</p>
    <button on:click={iniciar}>Iniciar</button>
    <button on:click={pausar}>Pausar</button>
    <button on:click={reiniciar}>Reiniciar</button>
</main>

<style>
    main {
        text-align: center;
        margin: 2em;
    }
    button {
        margin: 0.5em;
        padding: 0.5em 1em;
    }
</style>
