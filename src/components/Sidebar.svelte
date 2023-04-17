<script>
    import Profile from "./Profile.svelte"
    import Stories from "./Stories.svelte"
    import Footer from "./Footer.svelte"
    
</script>

<style>
   .Sidebar {
        position: relative;
    }
    .Sidebar_container {
        position: fixed;
    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Sidebar">
    <div class="Sidebar_container">
        <Profile />
        <Stories />
        <Footer />
    </div>
</div>