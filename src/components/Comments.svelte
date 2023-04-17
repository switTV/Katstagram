<script>
    export let comments = []

    function addComment(e) {
        const msg = e.target.text.value

        if (msg.length > 0) {
            const message = {
                id: Date.now(),
                text: msg,
                username: "Maximo"
            }

            comments = [...comments, message]
            e.target.text.value = ""
        }
    }
    
</script>

<style>
    .Comments .Comments_users {
        display: flex;
        flex-direction: row;
        align-items: center;
        margin: 10px 0px 5px 0px;
    }

    .Comments .Comments_users h3 {
        margin-left: 10px;
        font-size: 1.4rem;
        font-weight: 600;
    }

    .Comments .Comments_users span {
        font-size: 1.4rem;
        font-weight: 300;
        color: #5c5c5c;
    }

    .Comments h3 {
        font-size: 14px;
        color: black;
        font-weight: bold;
        margin: 0;
        padding: 0;
    }
    .Comments span {
        font-size: 14px;
        margin: 0 0 0 0.5em;
        font-weight: normal;
        color: rgba(black, 0.9);
        margin-left: 10px;
    }


    
    .Comments_add {
        padding: 1em 1em 1em 1em;
        border-top: 1px solid rgba(219, 219, 219, 0.8);
    }
    .Comments_add form {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    /* .Comments_users {
        margin: 0 0 0.5em 0;
        display: flex;
    } */

    input {
        border: solid 1px #e9e9e9;
        border-radius: 5px;
        color: #696969;
        border: 1px solid transparent;
        font-size: 12px;
        outline: none;
        width: 100%;
        background: none;
        display: flex;
    }
    button {
        border: none;
        color: #3897f0;
        font-size: 12px;
        outline: none;
        cursor: pointer;
        background: none;
    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Comments">
    <div class="Comments_container">
        {#each comments as comment (comment.id)}
            
            <div class="Comments_users">
                <h3>{comment.username}</h3>
                <span>
                    {comment.text}
                </span>
    
            </div>
        {/each}


        <div class="Comments_add">
            <form on:submit|preventDefault = {addComment}>
                <input type="text"
                class="Comments-input"
                placeholder="Agregar Comentario..."
                id="text"
            >
            <button type="submit">Post</button>
            </form>
        </div>
    </div>
    
</div>