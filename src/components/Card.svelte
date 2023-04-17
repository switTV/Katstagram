<script>
    import Comments from "./Comments.svelte";
    import Modal from "./Modal.svelte";
    import Share from "./Share.svelte"

    import { blur } from "svelte/transition";
    import { likeCount } from "../store/store";

    export let photo
    export let username
    export let location
    export let avatar
    export let postComment
    export let comments

    let isModal = false
    let like = false
    let bookmark = false

    function handleClick() {
        isModal = !isModal;
    }
    function handleLike() {
        like = !like

        if(like) {
            likeCount.update(n => n + 1)
        } else {
            likeCount.update(n => n - 1)
        }
    }
    function handleBookmark() {
        bookmark = !bookmark
    }
</script>

<style>
    .Card {
        border: 1px #c7c7c7 solid;
        border-radius: 5px;
        margin-bottom: 40px;
    }

    .Card .Card_container .Card_body .Card_photo figure {
        margin: 0;
    }

    .Card .Card_container .Card_body .Card_photo figure img {
        width: 100%;
    }

    .Card .Card_container .Card_header {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        margin: 10px;
    }

    .Card .Card_container .Card_header .Card_profile_info {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .Card .Card_container .Card_header .Card_profile_info img {
        width: 50px;
        height: 50px;
        margin-right: 10px;
        border-radius: 100%;
    }

    .Card .Card_container .Card_icons {
        display: flex;
        justify-content: space-between;
        margin: 10px ;
    }

    .Card .Card_container .Card_icons .Card_icons_first i {
        margin-right: 10px;
    }

    .Card .Card_container .Card_description {
        margin-left: 10px;
        margin-bottom: 10px;
    }

    .Card .Card_container .Card_description h3 {
        font-size: 1.6rem;
        font-weight: 700;
    }

    .Card .Card_container .Card_description span {
        font-size: 1.4rem;
        color: #555555;
    }

    .active-like {
        color: #bc1888;
        animation: animacionCorazon 2s ease 0s 1 normal forwards;
    }
    .active-bookmark {
        color: #bc1888;
        animation: animacionBookmark 2s ease 0s 1 normal forwards;
    }

    @keyframes animacionCorazon {
	    0% {
	    	transform: scale3d(1, 1, 1);
	    }

	    30% {
	    	transform: scale3d(1.25, 0.75, 1);
	    }

	    40% {
	    	transform: scale3d(0.75, 1.25, 1);
	    }

	    50% {
	    	transform: scale3d(1.15, 0.85, 1);
	    }

	    65% {
	    	transform: scale3d(0.95, 1.05, 1);
	    }

	    75% {
	    	transform: scale3d(1.05, 0.95, 1);
	    }

	    100% {
	    	transform: scale3d(1, 1, 1);
	    }
    }
    @keyframes animacionBookmark {
	    0%,
	    100% {
    		transform: translateY(0);
	    }

	    10%,
	    30%,
	    50%,
	    70% {
    		transform: translateY(-8px);
	    }

	    20%,
	    40%,
	    60% {
    		transform: translateY(8px);
	    }

	    80% {
    		transform: translateY(6.4px);
	    }

	    90% {
    		transform: translateY(-6.4px);
	    }
}
</style>

<!-- markup (zero or more items) goes here -->

<div class="Card">
    {#if isModal}
        <div transition:blur>
            <Modal>
                <Share on:click={handleClick}/>
            </Modal>
        </div>
    {/if}

    <div class="Card_container">
        <div class="Card_header">
            <div class="Card_profile_info">
                <div class="Card_profile_img">
                    <img src={avatar} alt={username}>
                </div>
                <div class="Card_profile_text">
                    <h3>{username}</h3>
                    <span>{location}</span>
                </div>
            </div>
            <div class="Card_settings">
                <i class="fas fa-ellipsis-h"></i>
            </div>
        </div>
        <div class="Card_body">
            <div class="Card_photo">
                <figure on:dblclick={handleLike}>
                    <img src={photo} alt="foto del perro de {username}">
                </figure>
            </div>
            <div class="Card_icons">
                <div class="Card_icons_first">
                    <!-- svelte-ignore a11y-click-events-have-key-events -->
                    <i class="fas fa-heart" class:active-like={like} on:click={handleLike} />
                    <!-- svelte-ignore a11y-click-events-have-key-events -->
                    <i class="fas fa-paper-plane" on:click={handleClick}></i>
                </div>
                <div class="Card_icons_second">
                    <!-- svelte-ignore a11y-click-events-have-key-events -->
                    <i class="fas fa-bookmark" class:active-bookmark={bookmark} on:click={handleBookmark}></i>
                </div>
            </div>
            <div class="Card_description">
                <h3>{username}</h3>
                <span>{postComment}</span>
            </div>
            <Comments {comments}/>
        </div>
    </div>
</div>