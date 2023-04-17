<script>
    import {onMount} from  "svelte"
    
    import Header from "../components/Header.svelte"
    import Main from "../components/Main.svelte"
    import Timeline from "../components/Timeline.svelte"
    import Sidebar from "../components/Sidebar.svelte"

    let data = {}
    const API = "https://kittygram-api.vercel.app/"

    onMount(async () => {
        const response = await fetch(API)
        data = await response.json()
        console.log(data.posts)
    })



</script>

<style>
    :global(body) {
        margin: 0 auto;
        padding: 0;

        background-color: #fafafa;
        color: #0b0b0c;

        font-family: "Lato", sans-serif;

        width: 50%;

    }

    :global(i) {
        font-size: 20px;
        color: #f09433;
        cursor: pointer;
    }

    :global(h2) {
        font-size: 1.8rem;
        color: #3b3b41;
    }

    :global(html) {
        font-size: 62.5%;
    }

    :global(h1,h2,h3) {
        margin: 0;
        padding: 0;
    }
</style>

<!-- markup (zero or more items) goes here -->

<Header />
<Main>
    <Timeline posts={data.posts}/>
    <Sidebar />
</Main>