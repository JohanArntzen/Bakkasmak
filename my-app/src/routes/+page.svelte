<script lang="ts">
    import Footer from '../routes/Footer.svelte';
    import burger from '../lib/assets/burger.jpg';
    import chickenCurry from '../lib/assets/chicken-curry.jpg';
    import fishAndChips from '../lib/assets/fish-and-chips.jpg';
    import meatballs from '../lib/assets/meatballs.jpg';
    import spaghetti from '../lib/assets/spaghetti.jpg';

    function Skroller(id: string) {
        const element = document.getElementById(id);
        if (element) {
            element.scrollIntoView({ behavior: 'smooth', block: "end", inline: "nearest" });
        }
    }

    $: Bakgrunnsbilde = {
        'MANDAG': `url(${burger})`,
        'TIRSDAG': `url(${chickenCurry})`,
        'ONSDAG': `url(${fishAndChips})`,
        'TORSDAG': `url(${meatballs})`,
        'FREDAG': `url(${spaghetti})`
    }[Dagen];

    $: matBeskrivelser = {
        'MANDAG': 'En burger er en klassisk favoritt som består av et saftig kjøttstykke i et mykt burgerbrød. Du kan få den med ost, salat, tomat, løk, sylteagurk og forskjellige sauser som ketchup og majones. Ofte serveres den med pommes frites eller en liten salat ved siden av. Enkelt, godt og alltid populært!',
        'TIRSDAG': 'Kylling curry er en smakfull rett laget med møre biter av kylling i en krydret saus. Den kan inneholde ingredienser som kokosmelk, løk, hvitløk, ingefær og en blanding av deilige krydder. Serveres gjerne med ris og kanskje litt naanbrød ved siden av. En varm og mettende favoritt!',
        'ONSDAG': 'Panert fisk og pommes frites er en enkel og god klassiker. Den sprø, gyldne fisken serveres sammen med sprø pommes frites og gjerne remulade eller sitron ved siden av. Perfekt som et lett og smakfullt måltid!',
        'TORSDAG': 'Kjøttboller og potetmos er en skikkelig hverdagsfavoritt. Saftige kjøttboller serveres med kremet potetmos, gjerne med en god saus og litt tyttebærsyltetøy eller grønnsaker ved siden av. Enkelt, smakfullt og mettende!',
        'FREDAG': 'Spaghetti bolognese er en klassiker som aldri slår feil. Det er spagetti servert med en rik og smakfull kjøttsaus laget av tomater, løk, hvitløk og krydder. Toppes gjerne med litt revet parmesan for ekstra smak. En enkel og deilig hverdagsrett!'
    }[Dagen];

    let Dagen = 'MANDAG';
    
    function VelgDag(id: string) {
        Skroller('skroll');
        Dagen = id;
    }
</script>

<div class="break"></div>

<div class="uke">
    <div id="mandag" tabindex="0" on:click={() => VelgDag('MANDAG')}>
        <p>MANDAG</p>
    </div>
    <div id="tirsdag" on:click={() => VelgDag('TIRSDAG')}>
        <p>TIRSDAG</p>
    </div>
    <div id="onsdag" on:click={() => VelgDag('ONSDAG')}>
        <p>ONSDAG</p>
    </div>
    <div id="torsdag" on:click={() => VelgDag('TORSDAG')}>
        <p>TORSDAG</p>
    </div>
    <div id="fredag" on:click={() => VelgDag('FREDAG')}>
        <p>FREDAG</p>
    </div>
</div>


<div class="dagensRett" id="skroll">
    <div class="matbilde" style="background-image: {Bakgrunnsbilde};"></div>
    <div class="matinfo">
        <h1>{Dagen}</h1>
        <p>{matBeskrivelser}</p>
    </div>
</div>

<Footer/>

<style>
.break {
    height: 16rem;
    background-color: #DCFFA5;
}

.uke{ 
    position: relative;  
    background-color: whitesmoke;
    display: flex;
    flex-direction: row;
    width: 100%;
    height: 38rem;
    font-family: Impact;
    font-size: 2em;
    color: whitesmoke;
}

#mandag, #tirsdag, #onsdag, #torsdag, #fredag {
    position: relative;
    background-position: center;
    background-size: cover;
    height: 100%;
    width: 20%;
    display: flex;
    justify-content: center;
    align-items: flex-end;
}

#mandag::after, #tirsdag::after, #onsdag::after, #torsdag::after, #fredag::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    z-index: 1;
}

#mandag p, #tirsdag p, #onsdag p, #torsdag p, #fredag p {
    position: relative;
    z-index: 2;
}

#mandag:hover, #tirsdag:hover, #onsdag:hover, #torsdag:hover, #fredag:hover {
    font-size: 1.5em;
    transition: all 0.2s ease;
    background-color: rgba(0, 0, 0, 0.5);
}


#mandag {
    background-image: url('../lib/assets/burger.jpg');
}

#tirsdag {
    background-image: url('../lib/assets/chicken-curry.jpg');
}

#onsdag {
    background-image: url('../lib/assets/fish-and-chips.jpg');
}

#torsdag {
    background-image: url('../lib/assets/meatballs.jpg');
}

#fredag {
    background-image: url('../lib/assets/spaghetti.jpg');
}

.dagensRett {
    position: relative;
    background-color: #DCFFA5;
    display: flex;
    justify-content: space-evenly;
    flex-direction: row;
    width: 100%;
    height: 30rem;
    padding-top: 6rem;
    padding-bottom: 6rem;
}
.matbilde{
    background-color: #ffffff;
    background-position: center;
    background-size: cover;
    width: 30%;
    border-radius: 3em;
}
.matinfo{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 50%;
    height: 100%;
    font-family: Impact;
    font-size: 2em;
    color: #5FB49C;
}
</style>