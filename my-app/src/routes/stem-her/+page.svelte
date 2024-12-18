<script lang="ts">
    import Footer from "../Footer.svelte";
    import { onMount } from 'svelte';

    let valgtAlternativ: string = '';
    let stemmer: { [key: string]: number } = {
        "Alternativ 1": 0,
        "Alternativ 2": 0,
        "Alternativ 3": 0
    };

    onMount(() => {
        const savedStemmer = localStorage.getItem('stemmer');
        if (savedStemmer) {
            stemmer = JSON.parse(savedStemmer);
        }
    });

    function sendInnStemme() {
        if (valgtAlternativ) {
            stemmer[valgtAlternativ]++;
            console.log(`Stemme innsendt for: ${valgtAlternativ}`);
            console.log('Alle stemmer:', stemmer);
            localStorage.setItem('stemmer', JSON.stringify(stemmer));
            valgtAlternativ = '';
        } else {
            alert('Vennligst velg et alternativ før du sender inn stemmen.');
        }
    }
</script>

<div class="break"></div>

<div class="alternativer">
  <h1>Alternativ 1</h1>
  <div class="alternativ1"></div>
  <h1>Alternativ 2</h1>
  <div class="alternativ2"></div>
  <h1>Alternativ 3</h1>
  <div class="alternativ3"></div>
</div>

<div class="stemmeing-resultat">
  <div class="stemming">
    <form on:submit|preventDefault={sendInnStemme}>
        <label>
            <input type="radio" name="stemme" value="Alternativ 1" bind:group={valgtAlternativ}>
            Alternativ 1
        </label>
        <br>
        <label>
            <input type="radio" name="stemme" value="Alternativ 2" bind:group={valgtAlternativ}>
            Alternativ 2
        </label>
        <br>
        <label>
            <input type="radio" name="stemme" value="Alternativ 3" bind:group={valgtAlternativ}>
            Alternativ 3
        </label>
        <br>
        <button type="submit">Send inn stemme</button>
    </form>
  </div>
  <div class="resultat">
    <p>Resultat:</p>
    <ul>
        {#each Object.entries(stemmer) as [alternativ, antall]}
            <li>{alternativ}: {antall} stemmer</li>
        {/each}
    </ul>
  </div>
</div>

<Footer/>

<style>
  .break {
    height: 16rem;
    background-color: #DCFFA5;
  }

  .alternativer {
    font-family: impact;
    display: flex;
    flex-direction: column;
    align-items: left;
    background-color: #DCFFA5;
    padding: 1rem;
    border-radius: 0.5rem;
    width: 70%;
    padding-left: 15%;
    padding-right: 15%;
  }

  .alternativ1,.alternativ2,.alternativ3{
    position: relative;
    background-position: center;
    background-size: cover;
    height: 20rem;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-end;
  }

  .alternativ1{
    background-image: url('../../lib/assets/Alternativ1.png');
  }

  .alternativ2{
    background-image: url('../../lib/assets/Alternativ2.png');
  }

  .alternativ3{
    background-image: url('../../lib/assets/Alternativ3.png');
  }





  .stemmeing-resultat {
    font-family: Impact;
    font-size: 1.2em;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-evenly;
    background-color: #DCFFA5;
    padding: 1rem;
    border-radius: 0.5rem;
  }

  .stemming {
    background-color: #5FB49C;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    border-radius: 0.5rem;
    width: 20em;
  }

  .resultat {
    background-color: #5FB49C;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    border-radius: 0.5rem;
    width: 20em;
  }

  form {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem;
    border-radius: 0.5rem;
  }

  label {
    margin-bottom: 0.5rem;
    font-size: 1.2em;
  }

  button {
    margin-top: 1rem;
    padding: 0.5rem 1rem;
    background-color: #3c7b69;
    color: white;
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
  }

  button:hover {
    background-color: #2c6b60;
    transform: scale(1.1);
    transition-duration: 300ms;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin: 0.5rem 0;
    padding: 0.5rem;
    border-radius: 0.5rem;
  }
</style>