<script>
    import Storie from "./Storie.svelte";

    
</script>

<style>

    .Stories .Stories_container .Stories_header{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }

    .Stories .Stories_container{
        background-color: #ffffff;
        padding: 10px;
        border: 1px #c7c7c7 solid;
        width: 200px;

    }

    .Stories .Stories_container .Stories_cards{

    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Stories">
    <div class="Stories_container">
        <div class="Stories_header">
            <p>Historias</p>
            <span>ver todas</span>
        </div>

        <section class="Stories_cards">

            <Storie 
            img_perfil="https://randomuser.me/api/portraits/men/75.jpg"
            nombre_perfil = "ElPela"
            hrs_antes = 7
            ></Storie>

            <Storie 
            img_perfil="https://randomuser.me/api/portraits/men/72.jpg"
            nombre_perfil = "Robert Smith"
            hrs_antes = 9
            ></Storie>

            <Storie 
            img_perfil="https://tn.com.ar/resizer/FkQPf__eAoZgkQmefsIe_07VkPI=/1440x0/smart/filters:format(webp)/cloudfront-us-east-1.images.arcpublishing.com/artear/BL6PFHRWURAMDKX6ZVDRCPP5FM.jfif"
            nombre_perfil = "Maximo"
            hrs_antes = 2
            ></Storie>
            
        </section>
    </div>
</div>