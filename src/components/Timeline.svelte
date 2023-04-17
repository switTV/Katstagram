<script>
    import Card from "./Card.svelte"
    import Loading from "./Loading.svelte";
    export let posts = []
</script>

<style>
    
</style>

<!-- markup (zero or more items) goes here -->

<div class="Timeline">
    <div class="Timeline_container">
        {#each posts as post}
            <Card {...post}/>

            {:else}
                <Loading/>
        {/each}
    </div>
</div>