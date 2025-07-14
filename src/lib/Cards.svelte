<script>
    export let personaje;
</script>

<div class="card">
    <img src=" {personaje.image} " alt=" {personaje.name} ">
    <p><strong>Nombre:</strong> {personaje.name} </p>
    <p><strong>Genero:</strong> {personaje.gender} </p>
    <p><strong>Especie:</strong> {personaje.species} </p>
    <p><strong>Origen:</strong> {personaje.origin.name} </p>
    <p><strong>Ubicacion:</strong> {personaje.location.name} </p>
    <p><strong>Estado:</strong> {personaje.status} </p>
</div>