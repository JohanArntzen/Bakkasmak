<script>
    import address from '$lib/assets/address.png';
    import telefon from "$lib/assets/telefon.png";
    import email from "$lib/assets/mail.png";
</script>

<footer>
    <div class="section1">
        <h1 class="title">Elvebakken</h1>
        <h1 class="title">Kantinen</h1>
    </div>

    <div class="section2">
        <div class="adress">
            <img class="icon" src="{address}" alt="Address">
            <div class="text">
                <h1 class="text">Vestre elvebakke 3</h1>
                <h1 class="text">0182, Oslo</h1>
            </div>
        </div>

        <div class="telefon">
            <img class= "icon" src="{telefon}" alt="Telefon nummer">
            <div class="text">
                <h1>+47 456 53 657</h1>
            </div>
        </div>

        <div class="email">
            <img class="icon" src="{email}" alt="Email">
            <div class="text">
                <h1>postmottak.elvebakken.vgs@osloskolen.no</h1>
            </div>
        </div>
    </div>

    <div class="section3">
        <a href="../about">
            <button class="Om_oss">
                <h1>Om oss</h1>
            </button>
        </a>
        
    </div>
</footer>



<style>
    footer{
        display: flex;
        flex-direction: row;
        background-color: #707070;
        height: 20em;
        width: 100%;
    }

    .section1{
        display: flex;
        flex-direction: column;
        margin-top: 1em;
    }

    .section2{
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        margin-left: 10em;
        
    }

    .section3{
        display: flex;
        flex-direction: column;
        margin-left: 10em;
        margin-top: 1.5em;
    }

    .adress{
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 2em;
    }

    h1 {
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        margin: 0;
    }

    .title{
        margin-top: 0.5em;
        font-size: 3em;
        color: #DEEFB7;
        margin: 0;
        margin-left: 0.5em;
    }

    .icon {
        height: 2em;
        width: auto;
    }



    .telefon {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 2em;
    }


    .email {
        display: flex;
        flex-direction: row;
        align-items: center;
        gap: 2em;
    }

    .text {
        margin: 0;
        color: #DEEFB7;
        font-family: Impact, Haettenschweiler, 'Bold', sans-serif;
        font-style:inherit;
    }

    .Om_oss {
        background-color: #5FB49C;
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        -webkit-transition-duration: 0.4s; /* Safari */
        transition-duration: 0.4s;

        width: 10em;
        height: auto;

    }

    .Om_oss:hover {
        background-color: #DEEFB7;
        color: #5FB49C;
    }

</style>