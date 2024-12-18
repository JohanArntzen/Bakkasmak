<!-- about us -->
<script lang="ts">
    /*scripts*/
    import logo from '$lib/assets/MatUtenHatLogo.png';
    import ansatte from '$lib/assets/bilder_av_oss.svg';
    import Footer from "../Footer.svelte";
</script>

<div class="break"></div>

<div class="aboutus">
    <div class="tekst">
        <h1>Om oss</h1>
    </div>
    <!-- <img  class="MatUtenHat-logo" src={logo} alt="MatUtenHat">  -->
    <div class="informasjon">
        <p>Vi er fire engasjerte elever fra Elvebakken videregående skole som har en enkel, men spennende idé: å gjøre matvalgene på skolen bedre og mer demokratiske.</p>
        <p>Gjennom prosjektet vårt har vi laget en nettside der alle elever kan:</p>
        <p>     •	Se dagens meny: Hold deg oppdatert på hva kantinen tilbyr.</p>
        <p>     •	Stem på favorittene dine: Hjelp oss med å finne ut hvilke retter som virkelig slår an blant elevene.</p>
        <p>     •	Sjekke prisene: Ingen flere overraskelser! få full kontroll på hva maten koster.</p>
    </div>
    <img class="ansatte_bilde" src={ansatte} alt="MatUtenHat">
</div>

<Footer/>

<slot/>

<style>
    h1{
        font-size: 4em;
        font-family: impact;
        padding: 10px;
        color:#DCFFA5;
    }
    p{
        font-size: 1.5em;
        font-family: impact;
        padding: 10px;
        color:#DCFFA5;
    }

    .break{
        height: 10em;
    }

    .aboutus{
        width: 100%;
        height: 100%;
        background-color: #3c7b69;
        padding-bottom: 10em;
        display: flex;
        align-items: center;
        flex-direction: column;
    }


    .tekst{
        display: flex;
        justify-content: center;
        align-items: flex-start;
        width: 100%;
        height: 100%;
        padding-top: 20px; 
    }

    h1{
        font-family: Impact;
    }

</style>