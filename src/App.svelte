<script>
  import Cards from "./lib/Cards.svelte";
  const urlbase = 'https://rickandmortyapi.com/api/character?page=';
  let personajes = [];
  let pagina = 1;

  async function characters(){
    try{
      const promesa = await fetch(`${urlbase}${pagina}`);
      const response = await promesa.json();
      personajes = response.results;
      console.log(personajes)
    } catch (error){
      console.error(error)
    }
  }
  characters();

  function sgt(){
    pagina++;
    characters();
  }

  function ant(){
    pagina--;
    characters();
  }

  function ini(){
    pagina = 1;
    characters();
  }

  function fin(){
    pagina = 42;
    characters();
  }

</script>

<svelte:head>
  <title>Rick and Morty</title>
</svelte:head>

<h1 class="title">Rick and Morty Svelte</h1>
<h2 class="title">Pagina: {pagina} </h2>

<div class="main">
  <div class="botones">
    <button class="boton" on:click={ini} disabled={pagina===1}> Primera</button>
    <button class="boton" on:click={ant} disabled={pagina===1}>Anterior</button>
    <button class="boton" on:click={sgt} disabled={pagina===42} >Siguiente</button>
    <button class="boton" on:click={fin} disabled={pagina===42} >Ultima</button>
  </div>
  <div class="grid">
    {#each personajes as personaje}
      <Cards {personaje}/>
    {/each}
  </div>
</div>