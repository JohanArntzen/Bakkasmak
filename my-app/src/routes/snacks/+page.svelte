<script lang="ts">
    import Footer from "../Footer.svelte"

    function Skroller(id: string) {
        const element = document.getElementById(id);
        if (element) {
            element.scrollIntoView({ behavior: 'smooth', block: "center",});
        }
    }
</script>

<div class="snacks_side">

<div class="spacer"></div>
<div class="spacer"></div>


<div class="overskrift">
    <button on:click={() => Skroller('skroll1')}>
        <h1>DRIKKE</h1>
    </button>
    <button on:click={() => Skroller('skroll2')}>
        <h1>SALATBAR</h1>
    </button>
    <button on:click={() => Skroller('skroll3')}>
        <h1>MATVARER</h1>
    </button>
</div>

<div class="varer">


<div class="drikke" id="skroll1">
    <div class="liste_overskrift">
        <h1>DRIKKE</h1>
        <h1 id="pant">(priser inkludert pant)</h1>
    </div>
    <div class="drikke_liste">
        <div class="section1">
            <h2>Cola-Zero 27,-</h2>
            <h2>Solo-Super 27,-</h2>
            <h2>Fanta Exotic 27,-</h2>
            <h2>Sprite 27,-</h2>
        </div>

        <div class="section2">
            <h2>RedBull 32,-</h2>
            <h2>Burn 35,-</h2>
            <h2>Smoothie 25,-</h2>
            <h2>Iste</h2>
        </div>

        <div class="section3">
            <h2>Iskaffe</h2>
            <h2>Eplejuice</h2>
            <h2>Sjokolademelk</h2>
            <h2>Vann</h2>
        </div>

    </div>

</div>

<div class="salat" id="skroll2">
    <div class="liste_overskrift">
        <h1>SALAT</h1>
        <h1 id="pris">(13KR PER HEKTO)</h1>
    </div>
    <div class="salat_liste">
        <div class="section4">
            <h2>Salatmix</h2>
            <h2>Blomkål</h2>
            <h2>Tomat</h2>
            <h2>Wok nudler</h2>
        </div>

        <div class="section5">
            <h2>Søt potet</h2>
            <h2>Oliven</h2>
            <h2>Tunfisk</h2>
            <h2>Egg</h2>
        </div>

        <div class="section6">
            <h2>Revet ost</h2>
            <h2>Cottage cheese</h2>
            <h2>Falafel</h2>
            <h2>Pasta-pesto</h2>

        </div>

    </div>


</div>


<div class="matvarer" id="skroll3">
    <div class="liste_overskrift">
        <h1>MATVARER</h1>
    </div>
    <div class="matvarer_liste">
        <div class="section7">
            <h2>Store baguetter 49,-</h2>
            <h2>Små baguetter 21,-</h2>
            <h2>Wraps 49,-</h2>
            <h2>Rett i koppen nudler 35,-</h2>
        </div>

        <div class="section5">
            <h2>Cookies 25,-</h2>
            <h2>Vestlands lefse 25,-</h2>
            <h2>Sjokolade 29,-</h2>
            <h2>Pringles 15,-</h2>

        </div>

    </div>


</div>




</div>

<div class="spacer"></div>

</div>
<Footer/>

<style>

    .snacks_side{
        background-color: #DCFFA5;
    }

    .overskrift{
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
        align-items: center;
        border: 2px solid black;

        width: 50%;
        height: 8em;
        margin-left: 25%;
        margin-top: 2em;
        margin-bottom: 2em;
        background-color: white;

        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        font-size: 1em;
        color: #5FB49C;
    }


    button {

        font-size: 1rem;
        border: none;
        border-radius: 10px;
        background: transparent;
        color: #5FB49C;
        cursor: pointer;
        height: fit-content;
        width: fit-content;
    }

    button:hover {
        background: #5FB49C;
        color: white;
    }

    .varer{
        display: flex;
        flex-direction: column;
        gap: 2em;
        margin-top: 2em;
    }

    .drikke {
        display: flex;
        flex-direction: column;
        width: 70%;
        margin-left: 15%;
        background-color: white;
        border: 2px solid black;

        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        color: #5FB49C;
    }

    .liste_overskrift{
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
        margin-left: 1em;
        gap: 2em;
        font-size: 1.5em;

    }

    .drikke_liste{
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }

    #pant{
        font-size: 1em;
    }

    h2{
        font-size: 1.5em;
    }

    .section1{
        color: #98DFAF;
    }

    .section3{
        color: #98DFAF;
    }

    .salat {
        display: flex;
        flex-direction: column;
        width: 70%;
        margin-left: 15%;
        background-color: white;
        border: 2px solid black;

        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        color: #5FB49C;
    }


    .salat_liste{
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }

    #pris{
        font-size: 1em;
    }

    .section5{
        color: #98DFAF;
    }

    .matvarer {
        display: flex;
        flex-direction: column;
        width: 70%;
        margin-left: 15%;
        background-color: white;
        border: 2px solid black;

        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        color: #5FB49C;
    }


    .matvarer_liste{
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
    }


    .section5{
        color: #98DFAF;
    }



    .spacer{
        height: 5em;
    }


    @media (max-width: 570px) {
        h2 {
            font-size: 1em;
        }

        .liste_overskrift {
            font-size: 1em;
        }
    }


</style>