<script>
    // your script goes here
</script>

<style>
    .Share {
        width: 300px;
        height: 100px;

        z-index: 2;
        position: absolute;

        left: calc(30%);
        top: 300px;

        background-color: #fafafa;
        border-radius: 10px;
        border: #0b0b0c 1px solid;
    }

    .Share_head {
        display: flex;
        justify-content: space-between;
        margin: 5px 10px 5px 10px;
    }

    .Share_content {
        display: flex;
        flex-direction: column;
    }

    .Share_content .Share_content_card {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;

        margin-left: 10px;
        margin-top: 10px;
    }

    .Share_content .Share_content_card a{
        font-family: Lato, sans-serif;
        font-size: 14px;
        color: #0b0b0c;
    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Share">
    <div class="Share_head">
        <h2>Compartir</h2>
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <i class="fas fa-times-circle" on:click />
    </div>

    <div class="Share_content">
        <div class="Share_content_card">
            <a href="https://www.facebook.com/sharer/sharer.php?@u=https://pugstagram.com">
                <i class="fab fa-facebook-square" style="margin-right: 10px;"></i>
                compartir en facebook
            </a>
        </div>
    </div>
</div>