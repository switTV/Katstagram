<script>
</script>

<style>
    .Main {
        display: grid;
        grid-template-columns: minmax(auto, 936px);
        justify-content: center;
        background-color: #fafafa;
    }
    .Main-container {
        display: grid;
        grid-template-columns: 3fr 1fr;
        grid-gap: 2em;
        padding: 2em 0;
    }
</style>

<!-- markup (zero or more items) goes here -->
<div class="Main">
    <div class="Main-container">
        <slot/>
    </div>
</div>