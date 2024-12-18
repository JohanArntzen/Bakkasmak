<script lang="ts">
    import logo from '$lib/assets/MatUtenHatLogo.png';
    import search from '$lib/assets/search.png';

    let query = '';

    function handleSearch() {
    console.log('Search query:', query);
    // Perform your search logic here
    }
</script>


<nav>
    <div class="logo">
    <a class="navbar-logo" href="/">
        <img class="navbar-logo" src={logo} alt="MatUtenHat">
    </a>
    </div>

    <div class="info">
        <div class="header">
            <a class="title"href="/">
                <h1 class="navbar-header">Bakkasmak</h1>
            </a>
            <div class="search-bar">
                <input
                    type="text"
                    placeholder="Søk..."
                    bind:value={query}
                />
                <button on:click={handleSearch}>
                    <img class="search-icon" src={search} alt="Search icon">
                </button>
            </div>
        </div>
        
    
        <div class="spacer-line"></div>
    
        <ul>
            <li>
                <a class="active" href="/snacks">Snacks</a>
            </li>
            <li>
                <a class="active" href="/stem-her">Stem her</a>
            </li>
            <li>
                <a class="active" href="/about">Om oss</a>
            </li>
            
        </ul>  
    </div>
    
</nav>




<slot/>

<style>
    nav {
    display: flex;
    position: fixed;
    top: 0; left: 0;
    width: 100%;
    z-index: 1000;
    padding: 10px;
    background-color: #F5FCF5;
    margin-bottom: 10em;
}

ul {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    gap: 20px;
    list-style: none; 
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: 1.45em;  
    margin: 0;
}



li {
    display: flex;
    margin-right: 50px;


}

a {
    text-decoration: none;
    color: #5FB49C;
}

.active:hover {
    padding: 5px;

    color: #3c7b69;
    font-size: larger;
}


.logo {
    align-items: center; 
}

.navbar-logo {
    height: 8em;
    width: auto;
}

.info {
    flex-direction: column;
    align-items: center; 
    justify-content: center; 
    flex-grow: 1; 
    text-align: center;
    margin-top: 20px;
}

.navbar-header {
    display: flex;
    flex-direction: row;

    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: 3em;
    color: #5FB49C;
    margin: 0;
}

.navbar-header:hover {
    color: #3c7b69;
}

.spacer-line {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    width: 97%; 
    height: 2px;
    background-color: #5FB49C;
    margin: 10px 0;
    margin-left: 2em;
}

.search-icon {
    height: 1.5em;
    width: auto;
}

.search-bar {
    display: flex;
    gap: 0.5rem;
    width: 20em;
    height: 2.5em;
    margin-right: 3em;

  }

  input {
    padding: 0.5rem;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 10px;
    flex: 1;
  }

  button {
    padding: 0.5rem 1rem;
    font-size: 1rem;
    border: none;
    border: 1px solid #5FB49C;
    border-radius: 10px;
    background: transparent;
    color: white;
    cursor: pointer;
  }

  button:hover {
    background: #5FB49C;
  }

.header{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-left: 40em;

}


@media (max-width: 1280px) {
    .header{
        margin-left: 20em;
    }
}


@media (max-width: 990px) {
    .header{
        margin-left: 1em;
    }
}

@media (max-width: 800px) {
    .header{
        display: block;
    }

    .search-bar{
        width: 10em;
        height: 2.5em;
    }

    ul {
        gap: 0;
    }

    .spacer-line{
        width: 80%;
    }
}



</style>

