<script>
  import Character from "./lib/Character.svelte";
  
  let characters=[]
  let page=1
  async function getDatos(){
     let response = await fetch("https://rickandmortyapi.com/api/character?page="+page)
      let datos = await response.json()
      characters=datos.results
      console.log(datos.results);

  }
  
  function previus(){
    page--;
    getDatos()
  }

  function next(){
    page++;
    getDatos()
  }


  getDatos()
</script>
<main>
  <div class="container">
    <h2>Personajes de Rick y Morty</h2>
    <div>
      <button type="button" class="btn btn-primary" on:click={previus} disabled={page===1}>Previus</button>
      <button type="button" class="btn btn-primary" on:click={next} >Next</button>

    </div>
    <br>
    <div class="row">
      
      
        {#each characters as character}
      <Character character={character}></Character>
      {/each}
   
    </div>
  </div>
</main>