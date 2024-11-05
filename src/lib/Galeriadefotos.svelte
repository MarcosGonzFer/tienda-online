<script>
    let images = [
        'imagenes/descarga.png',
        'imagenes/descarga.png',
        'imagenes/descarga.png'
    ];
    let seleccionImagenes = null; 

   
    function abrir(image) {
        seleccionImagenes  = image;
    }

    
    function cerrar() {
        seleccionImagenes  = null;
    }
</script>

<style>
   
    .container {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
    }
    .gallery-image {
        width: 150px;
        cursor: pointer;
        transition: transform 0.2s ease;
    }
    .gallery-image:hover {
        transform: scale(1.05);
    }

 
    .modal {
        display: flex;
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.8);
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }
    .modal-content {
        position: relative;
        max-width: 80%;
        max-height: 80%;
    }
    .modal-content img {
        width: 100%;
        height: 480px;
    }
</style>


<div class="container">
    {#each images as image}
        <!-- svelte-ignore a11y_click_events_have_key_events -->
        <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
        <img src={image} alt="Galería" class="gallery-image" on:click={() => abrir(image)} />
    {/each}
</div>


{#if seleccionImagenes }
    <!-- svelte-ignore a11y_click_events_have_key_events -->
    <!-- svelte-ignore a11y_no_static_element_interactions -->
    <div class="modal" on:click={cerrar}>
        <div class="modal-content" on:click|stopPropagation>
            <img src={seleccionImagenes } alt="Imagen seleccionada" />
        </div>
    </div>
{/if}