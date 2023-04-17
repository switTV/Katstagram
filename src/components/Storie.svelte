<script>
    export let img_perfil
    export let nombre_perfil
    export let hrs_antes
</script>

<style>
    img {
        width: 50px;
        height: 50px;
    }

    .Storie .Storie_container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        text-align: right;
    }

    .Storie .Storie_container .Storie_perfil_photo img {
        border-radius: 50%;
    }

    .Storie {
        margin-top: 15px;
    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Storie">
    <div class="Storie_container">
        <div class="Storie_perfil_photo">
            <img src="{img_perfil}" alt="imagen de perfil">
        </div>
        <div class="Storie_perfil_texto">
            <h2>{nombre_perfil}</h2>
            <span>{hrs_antes} horas antes</span>
        </div>
    </div>
</div>