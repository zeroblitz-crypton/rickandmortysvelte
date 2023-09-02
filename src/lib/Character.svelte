<script>
    export let character;
</script>
<div class="card col-4">
    
    <div class="card-body">
        <p>Nombre : {character.name}</p>
    <p>Tipo : {character.species}</p>
    <p>Estado : {character.status}</p>
    <img src="{character.image}" alt="">
    </div>
</div>
    
