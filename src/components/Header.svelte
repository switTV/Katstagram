<script>
    import { likeCount } from "../store/store";
</script>

<style>
      h1 {
        padding: 0;
        margin: 0;
        font-size: 28px;
        color: black;
        font-family: "Pacifico", cursive;
        cursor: pointer;
        position: relative;
        background: #fff;
        mix-blend-mode: multiply;
        display: inline-block;
    }

    h1:before {
        content: "";
        display: block;
        width: 100%;
        height: 100%;
        background: radial-gradient(circle at top left, #f09433, #bc1888);
        mix-blend-mode: screen;
        position: absolute;
        top: 0;
        left: 0;
    }

    .Header .Header_container .Header_content{
        display: flex;
        justify-content: space-between;
    }

    .Header .Header_container .Header_content .Header_nav ul{
        display: flex;
        flex-direction: row;
    }
    .Header .Header_container .Header_content .Header_nav ul li{
        margin-left: 15px;
        list-style: none;
    }

    .Header .Header_container .Header_content .Header_nav ul .icon-heart i{
        position: relative;
        
    }

    .Header .Header_container .Header_content .Header_nav ul .icon-heart p{
        position: absolute;
        top: 0.3%;
        right: 27.1%;
        z-index: 999;
        color: #fff;
    }
</style>

<!-- markup (zero or more items) goes here -->

<div class="Header">
    <div class="Header_container">
        <div class="Header_content">
            <div class="Header_logo">
                <h1>Katstagram</h1>
            </div>

            <div class="Header_nav">
                <ul>
                    <li class="icon-heart">
                        <i class="fa-solid fa-heart"></i>
                        <p>{$likeCount == 0 ? "" : $likeCount}</p>
                    </li>
                    <li><i class="fa-solid fa-user"></i></li>
                </ul>
            </div>
        </div>
    </div>
</div>